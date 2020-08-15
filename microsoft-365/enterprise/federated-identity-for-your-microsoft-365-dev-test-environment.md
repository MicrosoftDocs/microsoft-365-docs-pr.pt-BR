---
title: Identidade federada para o seu ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Resumo: configure a autenticação federada para o seu ambiente de teste do Microsoft 365.'
ms.openlocfilehash: c7ff838522c0bd97da4ffff5122454b128f97bf2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687459"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Identidade federada para o seu ambiente de teste do Microsoft 365

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

O Microsoft 365 suporta a identidade federada. Isto significa que em vez de executar a validação das credenciais em si, o Microsoft 365 remete o utilizador de ligação a um servidor de autenticação federado que o Microsoft 365 confia. Se as credenciais do usuário estiverem corretas, o servidor de autenticação federado emite um token de segurança que, por sua vez, o cliente envia ao Microsoft 365 como prova de autenticação. A identidade federada permite o descarregamento e a ampliação da autenticação para uma inscrição no Microsoft 365 e cenários avançados de autenticação e segurança.
  
Este artigo descreve como você pode configurar a autenticação federada para seu ambiente de teste do Microsoft 365, resultando no seguinte:

![A autenticação federada para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Esta configuração consiste em: 
  
- Uma assinatura de avaliação ou produção do Microsoft 365 e5.
    
- Uma intranet de organização simplificada conectada à Internet, que consiste em cinco máquinas virtuais em uma sub-rede de uma rede virtual do Azure (DC1, APP1, CLIENT1, ADFS1 e PROXY1). O Azure AD Connect é executado no APP1 para sincronizar a lista de contas no domínio dos serviços de domínio Active Directory para a Microsoft 365. O PROXY1 recebe as solicitações de autenticação de entrada. ADFS1 valida as credenciais com o DC1 e emite tokens de segurança.
    
Há cinco etapas para configurar esse ambiente de teste:
  
1. Criar o ambiente de teste de empresa simulada com sincronização de hash de senha.
    
2. Crie o servidor AD FS (ADFS1).
    
3. Crie o servidor de proxy da web (PROXY1).
    
4. Crie um certificado autoassinado e configure o ADFS1 e o PROXY1.
    
5. Configure o Microsoft 365 da identidade federada.
    
> [!NOTE]
> Você não pode configurar o ambiente de teste com uma assinatura de avaliação do Azure. 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365

Siga as instruções em [sincronização de hash de senha para o Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Aqui está a configuração resultante.
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Esta configuração consiste em: 
  
- Uma assinatura de avaliação ou pagamento da Microsoft 365 e5.
- Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure. O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD das suas assinaturas do Microsoft 365 periodicamente.

## <a name="phase-2-create-the-ad-fs-server"></a>Fase 2: Criar o servidor AD FS

Um servidor AD FS fornece autenticação federada entre o Microsoft 365 e as contas no domínio corp.contoso.com hospedado no DC1.
  
Para criar uma máquina virtual do Azure para ADFS1, preencha o nome da assinatura e do grupo de recursos, o local do Azure para a Configuração da base e execute estes comandos no prompt de comando do Azure PowerShell no computador local.
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do ADFS1 usando o nome da conta e a senha do administrador local do ADFS1, depois abra um prompt de comando do Windows PowerShell.
  
Para verificar a comunicação da rede e a resolução de nome entre o ADFS1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.
  
Em seguida, associe a máquina virtual do ADFS1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Esta é a configuração resultante.
  
![O servidor AD FS adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Fase 3: crie o servidor de proxy da web

O PROXY1 fornece proxy de mensagens de autenticação entre ADFS1 e os usuários que tentarem se autenticar.
  
Para criar uma máquina virtual do Azure para o PROXY1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do Azure PowerShell no computador local.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Um endereço IP estático público é atribuído ao PROXY1 porque você cria um registro DNS público que aponta para ele e não deverá ser alterado ao reiniciar a máquina virtual do PROXY1. 
  
Em seguida, adicione uma regra ao grupo de segurança de rede para a sub-rede da CorpNet para permitir o tráfego de entrada não solicitada da Internet para o endereço IP particular do PROXY1 e da porta 443 de TCP. Execute esses comandos no prompt de comando do Azure PowerShell no computador local.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual do PROXY1 usando o nome e a senha da conta do administrador local do PROXY1, depois abra um prompt de comando do Windows PowerShell no PROXY1.
  
Para verificar a comunicação da rede e a resolução de nome entre o PROXY1 e o DC1, execute o comando **ping dc1.corp.contoso.com** e verifique se há quatro respostas.
  
Em seguida, associe a máquina virtual do PROXY1 ao domínio CORP com estes comandos no prompt do Windows PowerShell no PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Exiba o endereço IP público do PROXY1 com estes comandos do Azure PowerShell no computador local:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Em seguida, trabalhe com seu provedor de DNS público e crie um novo registro público de DNS A para **fs.testlab.**\<your DNS domain name>que resolve para o endereço IP exibido pelo comando **Write-Host**. De agora em diante, o **fs.testlab.**\<your DNS domain name>seu nome de domínio DNS> é conhecido como o *FQDN do serviço de federação*.
  
Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e execute este comando em um prompt de comando do Windows PowerShell de nível de administrador:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Esses comandos criam um registro DNS A interno para que as máquinas virtuais na rede virtual do Azure possam resolver o FQDN da federação interna para o endereço IP privado do ADFS1.
  
Esta é a configuração resultante.
  
![O servidor proxy do aplicativo Web adicionado ao DirSync para o ambiente de teste do Microsoft 365](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Fase 4: crie um certificado autoassinado e configure o ADFS1 e o PROXY1

Nesta fase, crie um certificado digital autoassinado para o seu FQDN de serviço de federação e configure o ADFS1 e o PROXY1 como um farm do AD FS.
  
Em seguida, use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual DC1 usando as credenciais CORP\\Usuário1 e abra um prompt de comando de nível de administrador do Windows PowerShell:
  
Depois crie a conta de serviço do AD FS usando esse comando no prompt de comando do Windows PowerShell em DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Observe que esse comando solicita que você forneça a senha da conta. Escolha uma senha forte e anote-a em um local seguro. Você precisará dela neste fase e na fase 5.
  
Use o [portal do Azure](https://portal.azure.com) para se conectar à máquina virtual ADFS1 usando as credenciais CORP\\Usuário1. Abra um prompt de comando do Windows PowerShell de nível de administrador no ADFS1, preencha o FQDN de serviço de Federação e execute estes comandos para criar um certificado autoassinado:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Em seguida, use estas etapas para salvar o novo certificado autoassinado como um arquivo.
  
1. Clique em **Iniciar**, digite **mmc.exe** e pressione **Enter**.
    
2. Clique em **Arquivo > Adicionar/Remover Snap-in**.
    
3. Em **Adicionar/Remover Snap-in**, clique duas vezes em **Certificados** na lista de snap-ins disponíveis, clique em **Conta do computador** e em **Avançar**.
    
4. Em **Selecionar Computador**, clique em **Concluir** e em **OK**.
    
5. No painel da árvore, abra **Certificados (Computador Local) > Pessoal > Certificados**.
    
6. Clique com o botão direito do mouse no certificado com FQDN de serviço de federação, clique em **Todas as Tarefas** e em **Exportar**.
    
7. Na página **Bem-vindo**, clique em **Avançar**.
    
8. Na página **Exportar Chave Privada**, clique em **Sim** e em **Avançar**.
    
9. Na página **Formato de Arquivo de Exportação**, clique em **Exportar Todas as Propriedades Estendidas** e em **Avançar**.
    
10. Na pagina **Segurança**, clique em **Senha**, digite uma senha em **Senha** e clique em **Confirmar Senha.**
    
11. Na página **Arquivo a Ser Exportado**, clique em **Procurar**.
    
12. Navegue até a pasta **C:\\Certs**, digite **SSL** em **Nome do Arquivo** e clique em **Salvar.**
    
13. Na página **Arquivo a Ser Exportado**, clique em **Avançar**.
    
14. Na página **Concluindo o Assistente para Exportação de Certificados**, clique em **Concluir** e, quando solicitado, clique em **OK**.
    
Depois instale o serviço do AD FS usando esse comando no prompt de comando do Windows PowerShell em ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Aguarde a instalação ser concluída.
  
Em seguida, configure o serviço do AD FS com estas etapas:
  
1. Clique em **Iniciar** e no ícone **Gerenciador do Servidor**.
    
2. No painel da árvore do Gerenciador de Servidores, clique em **AD FS**.
    
3. Na barra de ferramentas, na parte superior, clique no símbolo de cuidado laranja e, em seguida, clique em **Configurar o Serviço de Federação neste Servidor**.
    
4. Na página **Bem-vindo** do Assistente de Configuração de Serviços de Federação do Active Directory (AD FS), clique em **Avançar**.
    
5. Na página **Conectar aos AD DS**, clique em **Avançar**.
    
6. Na página **Especificar Propriedades do Serviço**:
    
  - Para o **Certificado SSL**, clique na seta para baixo e, em seguida, clique no certificado com o nome do seu FQDN de serviço de federação.
    
  - No **Nome de Exibição de Serviços de Federação**, digite o nome da sua organização fictícia.
    
  - Clique em **Avançar**.
    
7. Na página **Especificar Conta de Serviço**, clique em **Selecionar** para **Nome da Conta**.
    
8. Em **Selecionar Usuário ou Conta de Serviço**, digite **Serviço ADFS**, clique em **Verificar Nomes** e em **OK**.
    
9. Em **Senha da Conta**, digite a senha da conta de serviço do ADFS e, em seguida, clique em **Avançar**.
    
10. Na página **Especificar Banco de Dados de Configurações**, clique em **Avançar**:
    
11. Na página **Opções de Revisão**, clique em **Avançar**.
    
12. Na página **Verificações de Pré-requisitos**, clique em **Configurar**.
    
13. Na página **Resultados**, clique em **Fechar**.
    
14. Clique em **Iniciar**, clique no ícone de Energia, clique em **Reiniciar** e, em seguida, em **Continuar**.
    
No [portal do Azure](https://portal.azure.com), conecte-se ao PROXY1 com as credenciais da conta CORP\\Usuário1.
  
Em seguida, use estas etapas para instalar o certificado autoassinado em **ambos PROXY1 e APP1**.
  
1. Clique em **Iniciar**, digite **mmc.exe** e pressione **Enter**.
    
2. Clique em **Arquivo > Adicionar/Remover Snap-in**.
    
3. Em **Adicionar/Remover Snap-in**, clique duas vezes em **Certificados** na lista de snap-ins disponíveis, clique em **Conta do computador** e em **Avançar**.
    
4. Em **Selecionar Computador**, clique em **Concluir** e em **OK**.
    
5. No painel da árvore, abra **Certificados (Computador Local) > Pessoal > Certificados**.
    
6. Clique com o botão direito do mouse em **Pessoal**, selecione **Todas as Tarefas** e clique em **Importar**.
    
7. Na página **Bem-vindo**, clique em **Avançar**.
    
8. Na página **Arquivo a Ser Importado**, digite**\\\\adfs1\\certs\\ssl.pfx** e, em seguida, clique em **Avançar**.
    
9. Na página **Proteção de Chave Privada**, digite a senha de certificado na **Senha** e, em seguida, clique em **Avançar.**
    
10. Na página **Repositório de certificados**, clique em **Avançar**.
    
11. Na página **Concluindo**, clique em **Concluir**.
    
12. Na página **Repositório de Certificados**, clique em **Avançar**.
    
13. Quando solicitado, clique em **OK**.
    
14. Clique em **Certificados** no painel de árvore.
    
15. Clique com o botão direito do mouse no certificado e depois em **Copiar**.
    
16. No painel de árvore, abra **Autoridades de Certificação Raiz Confiáveis > Certificados**.
    
17. Passe o ponteiro do cursor abaixo da lista de certificados instalados, clique com o botão direito do mouse e clique em **Colar**.
    
Abra um prompt de comando do Windows PowerShell de nível de administrador e execute o seguinte comando:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Aguarde a instalação ser concluída.
  
Use estas etapas para configurar o serviço de proxy de aplicativo web para usar o ADFS1 como seu servidor de federação:
  
1. Clique em **Iniciar** e em **Gerenciador do Servidor**.
    
2. No painel de árvore, clique em **Acesso Remoto**.
    
3. Na barra de ferramentas, na parte superior, clique no símbolo de cuidado laranja e, em seguida, clique em **Abrir o Assistente de Proxy de Aplicativo Web**.
    
4. Na página **Bem-vindo** do Assistente de Configuração do Proxy de Aplicativo Web, clique em **Avançar**.
    
5. Na página **Servidor de Federação**:
    
  - Digite o FQDN do serviço de federação em **Nome do Serviço de Federação**.
    
  - Digite **CORP\\Usuário1** no **Nome de Usuário**.
    
  - Digite a senha da conta do Usuário1 em **Senha**.
    
  - Clique em **Avançar**.
    
6. Na página **Certificado Proxy AD FS**, clique na seta para baixo, clique no certificado com o nome do seu FQDN de serviço de federação e depois em **Avançar**.
    
7. Na página **Confirmação**, clique em **Configurar**.
    
8. Na página **Resultados**, clique em **Fechar**.

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Fase 5: configure o Microsoft 365 da identidade federada.

Use o [portal do Azure](https://portal.azure.com) para conectar a máquina virtual APP1 com as credenciais da conta CORP\\Usuário1.
  
Use estas etapas para configurar o Azure AD Connect e sua assinatura do Microsoft 365 da autenticação federada:
  
1. Na área de trabalho, clique duas vezes em **Azure AD Connect**.
    
2. Na página **Bem-vindo ao Azure AD Connect**, clique em **Configurar**.
    
3. Na página **Tarefas Adicionais**, clique em **Alterar entrada do usuário** e em **Avançar**.
    
4. Na página **Conectar-se ao Azure AD** digite o nome e a senha da sua conta de administrador global e clique em **Avançar**.
    
5. Na página **Entrada do usuário**, clique em **Federação com AD FS** e em **Avançar**.
    
6. Na página **Farm do AD FS**, clique em **Usar um farm do AD FS existente**, digite **ADFS1** no **Nome do servidor** e clique em **Avançar**.
    
7. Nas credenciais do servidor, insira as credenciais da conta CORP\\Usuário1 e clique em **OK**.
    
8. Na página de credenciais **Administrador de domínio**, digite **CORP\\Usuário1** no **Nome de usuário** e a senha da conta em **Senha** e clique em **Avançar**.
    
9. Na página **Conta de Serviço do AD FS**, digite **CORP\\ADFS serviço** no **Nome de Usuário de Domínio** e a senha da conta em **Senha de Usuário de Domínio** e clique em **Avançar**.
    
10. Na página **Domínio do Azure AD**, em **Domínio**, selecione o nome do domínio que você criou anteriormente e adicionou à sua assinatura na Fase 1 e clique em **Avançar**.
    
11. Na página **Pronto para configurar**, clique em **Configurar**.
    
12. Na página **Instalação Completa**, clique em **Verificar**.
    
    Você verá mensagens indicando que as configurações da intranet e da Internet foram verificadas.
    
13. Na página **Instalação Completa**, clique em **Fechar**.
    
Para demonstrar que a autenticação federada está funcionando, faça o seguinte:
  
1. Abra uma nova instância privada no navegador do computador local e acesse [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Para as credenciais de entrada, digite **user1@**\<the domain created in Phase 1>. 
    
    Por exemplo, se seu domínio de teste for **testlab.contoso.com**, digite usuário1@testlab.contoso.com. Pressione a tecla TAB ou deixe que o Microsoft 365 o redirecione automaticamente.
    
    Agora você deverá ver a página **Sua conexão não é particular** porque você instalou o certificado autoassinado em ADFS1 que seu computador desktop não consegue validar. Em uma implantação de produção com autenticação federada, será necessário usar um certificado de autoridade de certificação confiável e os usuários não verão esta página.
    
3. Na página **Sua conexão não é privada**, clique em **Avançado** e depois clique em**Vá para \<your federation service FQDN>**. 
    
4. Na página com o nome da sua organização fictícia, entre com o seguinte:
    
  - **CORP\\Usuário1** como o nome
    
  - A senha da conta Usuário1
    
    Você verá a **home page do Microsoft Office**.
    
Esse procedimento demonstra que sua assinatura de avaliação está federada com o domínio AD DS corp.contoso.com hospedado no DC1. Aqui estão os conceitos básicos do processo de autenticação:
  
1. Quando você usa o domínio federado criado na Fase 1 no nome da conta de login, o Microsoft 365 redireciona o navegador para o seu serviço de federação FQDN e PROXY1.
    
2. PROXY1 envia a página de entrada da empresa fictícia para o seu computador local.
    
3. Quando você envia CORP\\Usuário1 e a senha PROXY1, ele o encaminha para o ADFS1.
    
4. O ADFS1 valida CORP\\Usuário1 e a senha com o DC1 e envia um token de segurança para o seu computador local.
    
5. Seu computador local envia o token de segurança para o Microsoft 365.
    
6. O Microsoft 365 valida que o token de segurança foi criado pelo ADFS1 e permite o acesso.
    
Sua assinatura de avaliação já está configurada com autenticação federada. Você pode usar esse ambiente de desenvolvimento/teste dos cenários de autenticação avançados.
  
## <a name="next-step"></a>Próxima etapa

Quando você estiver pronto para implantar a autenticação federada de alta disponibilidade e pronta para produção para o Microsoft 365 no Azure, confira [implantar a autenticação federada de alta disponibilidade para o microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
