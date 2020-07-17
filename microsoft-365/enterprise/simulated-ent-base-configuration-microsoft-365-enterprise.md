---
title: Configuração base corporativa simulada para Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este Guia de laboratório de teste para criar um ambiente de teste corporativo simulado para o Microsoft 365 Enterprise.
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818490"
---
# <a name="the-simulated-enterprise-base-configuration"></a>A configuração base corporativa simulada

*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*

Este artigo fornece instruções passo a passo para criar um ambiente simplificado do Microsoft 365 Enterprise, que inclui:

- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, composta por três máquinas virtuais em uma Rede Virtual do Microsoft Azure (DC1 APP1 e CLIENT1).
 
![A configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

Você pode usar o ambiente resultante para testar os recursos e a funcionalidade do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) com os [Guias de laboratório de teste](m365-enterprise-test-lab-guides.md) adicionais ou por sua própria conta.

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Acesse [Guia de laboratório de teste do Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para obter um mapa visual de todos os artigos da pilha do Guia de laboratório de teste do Microsoft 365 Enterprise.

## <a name="phase-1-create-a-simulated-intranet"></a>Fase 1: criar uma intranet simulada

Nesta fase, você cria uma intranet simulada nos serviços de infraestrutura do Azure, que inclui um controlador de domínio dos Serviços de Domínio do Active Directory (AD DS), um servidor de aplicativos e um computador cliente. 

Você usará esses computadores em outros [Guias de laboratório de teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para configurar e demonstrar a identidade híbrida e outros recursos.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Método 1: criar sua intranet simulada com um modelo do Azure Resource Manager

Nesse método, você usa um modelo do Azure Resource Manager (ARM) para criar uma intranet simulada. Os modelos do ARM contêm todas as instruções para criar a infraestrutura de rede do Azure, as máquinas virtuais e suas configurações.

Antes de implantar o modelo, leia toda a [página LEIAME do modelo](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) e tenha as seguintes informações em mãos:

- O nome de domínio DNS público do seu ambiente de teste (testlab.\<your public domain>). Você precisará inserir esse nome no **campo Nome de domínio** da página **Implantação personalizada**.
- Um prefixo de rótulo DNS das URLs dos endereços de IP públicos das suas máquinas virtuais. Você precisará inserir esse rótulo no campo **Prefixo do rótulo DNS** da página**Implantação personalizada**.

Depois de ler todas as instruções, clique em **Implantar no Azure** na [página LEIAME do modelo](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) para começar.

>[!Note]
>A intranet simulada criada pelo modelo do ARM requer uma assinatura paga do Azure.
>

Esta é sua configuração após a conclusão do modelo.

![A intranet simulada nos serviços de infraestrutura do Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Método 2: criar sua intranet simulada com o Azure PowerShell

Nesse método, use o módulo do Windows PowerShell e do Azure PowerShell para criar a infraestrutura de rede, as máquinas virtuais e suas configurações.

Use esse método caso deseje obter a experiência de criação de elementos de infraestrutura do Azure uma etapa por vez com o PowerShell. Assim, é possível personalizar os blocos de comando do PowerShell para sua própria implantação de outras máquinas virtuais no Azure.

#### <a name="step-1-create-dc1"></a>Etapa 1: criar DC1

Nessa etapa, criamos uma rede virtual do Azure e adicionamos a DC1, uma máquina virtual que se trata de um controlador de domínio para um domínio do AD DS.

Primeiro, inicie o prompt de comando do Windows PowerShell no computador local.
  
> [!NOTE]
> O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Entre na sua conta do Azure usando o comando a seguir.
  
```powershell
Connect-AzAccount
```

Para obter o nome de sua assinatura, use este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Configure a assinatura do Azure. Substitua tudo o que está entre aspas, inclusive os caracteres < e >, pelo nome correto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Depois, crie um novo grupo de recursos para o laboratório de testes simulado. Para determinar um nome de grupo de recursos exclusivo, use este comando para relacionar os grupos de recurso existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Crie um novo grupo de recursos com estes comandos. Substitua tudo o que está entre aspas, incluindo os caracteres < e >, pelos nomes corretos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Em seguida, crie a rede virtual do TestLab que hospedará a sub-rede da rede corporativa do ambiente corporativo simulado e a protegerá com um grupo de segurança de rede. Preencha o nome do grupo de recursos e execute esses comandos no prompt de comando do PowerShell, no computador local.
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Em seguida, você cria a máquina virtual DC1 e a configura como um controlador de domínio para o **testlab.**\<your public domain> Domínio do AD DS e um servidor DNS para as máquinas virtuais da rede virtual TestLab. Por exemplo, se seu nome de domínio público for **<span>contoso</span>.com**, a máquina virtual DC 1 será um controlador de domínio para o domínio do **<span>testlab</span>.contoso.com**.
  
Para criar uma máquina virtual como DC1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando do PowerShell, no computador local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Será solicitado que você insira um nome de usuário e uma senha para a conta de administrador local na DC1. Use uma senha forte e armazene ambos, a senha e o nome, em um local seguro.
  
Em seguida, conecte-se à máquina virtual DC1.
  
1. No [portal do Azure](https://portal.azure.com), clique em **Grupos de Recursos >** [nome do novo grupo de recursos] **> DC1 > Conectar**.
    
2. No painel aberto, clique em **Baixar o arquivo RDP**. Abra o arquivo DC1.rdp que foi baixado e clique em **Conectar**.
    
3. Especifique o nome da conta de administrador local na DC1:
    
   - No Windows 7:
    
     Na caixa de diálogo **Segurança do Windows**, clique em **Usar outra conta**. Em **Nome de usuário**, digite **DC1\\**[nome da conta de administrador local].
    
   - No Windows 8 ou Windows 10:
    
     Na caixa de diálogo **Segurança do Windows**, clique em **Mais opções** e, então, clique em **Usar uma conta diferente**. Em **Nome de usuário**, digite **DC1\\**[nome da conta de administrador local].
    
4. Em **Senha**, digite a senha da conta de administrador local e clique em **OK**.
    
5. Quando solicitado, clique em **Sim**.
    
Em seguida, adicione um disco de dados extra como um novo volume com a letra de unidade F:, com este comando, em um prompt de comando do Windows PowerShell de nível de administrador no DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Em seguida, configure o DC1 como um controlador de domínio e servidor DNS para o **testlab.**\<your public domain> domínio. Especifique seu nome de domínio público, remova os \< and > caracteres e execute esses comandos em um prompt de comando do Windows PowerShell no nível de administrador no DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Será preciso especificar uma senha de administrador no modo de segurança. Armazene essa senha em um local seguro.
  
Esses comandos podem levar alguns minutos para serem concluídos.
  
Após a reinicialização da DC1, reconecte-se à máquina virtual DC1.
  
1. No [portal do Azure](https://portal.azure.com), clique em **Grupos de Recursos >** [nome do seu grupo de recursos] **> DC1 > Conectar**.
    
2. Execute o arquivo DC1.rdp que foi baixado e clique em **Conectar**.
    
3. Em **Segurança do Windows**, clique em **Usar outra conta**. Em **Nome de usuário**, digite **TestLab\\**[Nome da conta do administrador local].
    
4. Em **Senha**, digite a senha da conta de administrador local e clique em **OK**.
    
5. Quando solicitado, clique em **Sim**.
    
Em seguida, crie uma conta de usuário no Active Directory que será usada quando entrar nos computadores membros do domínio TestLab. Execute este comando em um prompt de comando do Windows PowerShell em nível de administrador.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Este comando o solicita a fornecer a senha da conta Usuário1. Como essa conta será usada para conexões de área de trabalho remota para todos os computadores membros do domínio do TestLab, escolha uma senha forte. Registre a senha da conta Usuário1 e armazene-a em local seguro.
  
Em seguida, configure a nova conta Usuário1 como um administrador de domínio, corporativo e de esquema. Execute este comando no prompt de comando do Windows PowerShell em nível de administrador.
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

Encerre a sessão da Área de Trabalho Remota com a DC1 e reconecte-se usando a conta \\Usuário1 do TestLab.
  
Em seguida, para permitir o tráfego da ferramenta Ping, execute este comando no prompt de comando de nível de administrador do Windows PowerShell.
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

Essa é sua configuração atual.
  
![Etapa 1 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a>Etapa 2: configurar o APP1

Nessa etapa, você cria e configura o APP1, que se trata de um servidor de aplicativos que inicialmente fornece serviços de compartilhamento de arquivos e da Web.

Para criar uma Máquina Virtual do Microsoft Azure para a APP1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando, no computador local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Em seguida, conecte-se à máquina virtual APP1 usando o nome da conta e a senha do administrador local APP1 e depois abra um prompt de comando do Windows PowerShell.
  
Para verificar a resolução de nomes e a comunicação de rede entre APP1 e DC1, execute o **ping dc1.testlab.**\<your public domain name> comando e verifique se há quatro respostas.
  
Em seguida, adicione a máquina virtual APP1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Você deve fornecer as credenciais de conta de domínio do \\Usuário1 do TestLab, depois de executar o comando **Add-Computer**.
  
Depois de reiniciar a APP1, conecte-se a ele usando a conta \\Usuário1 do TestLab e abra um prompt de comando do Windows PowerShell em nível de administrador.
  
Em seguida, transforme a APP1 em um servidor Web usando este comando, em um prompt de comando do Windows PowerShell na APP1.
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

Em seguida, crie uma pasta compartilhada e um arquivo de texto dentro da pasta da APP1 com estes comandos no PowerShell.
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

Essa é sua configuração atual.
  
![Etapa 2 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Etapa 3: configurar o CLIENT1

Nessa etapa, você cria e configura o CLIENT1, que atua como um laptop, tablet ou computador típico na intranet.

> [!NOTE]  
> O seguinte conjunto de comandos cria a CLIENT1 executando o Windows Server 2016 Datacenter, o que pode ser feito em todos os tipos de assinaturas do Azure. Se você tiver uma assinatura do Azure baseada em Visual Studio, será possível criar a CLIENT1 executando o Windows 10 no [Portal do Azure](https://portal.azure.com). 
  
Para criar uma Máquina Virtual do Microsoft Azure para CLIENT1, preencha o nome do grupo de recursos e execute estes comandos no prompt de comando, no computador local.
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Em seguida, conecte-se à máquina virtual CLIENT1 usando o nome da conta e a senha do administrador local da CLIENT1 e depois abra um prompt de comando de nível de administrador no Windows PowerShell.
  
Para verificar a resolução de nomes e a comunicação de rede entre CLIENT1 e DC1, execute o **ping dc1.testlab.**\<your public domain name> comando em um prompt de comando do Windows PowerShell e verifique se há quatro respostas.
  
Em seguida, adicione a máquina virtual do CLIENT1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Você deve fornecer as credenciais de conta de domínio \\Usuário1 do TestLab, depois de executar o comando **Add-Computer**.
  
Depois de reiniciar a CLIENT1, conecte-se a ela usando o nome da conta e a senha do \\Usuário1 do TestLab e abra um prompt de comando do Windows PowerShell em nível de administrador.
  
Após esse procedimento, verifique se você consegue acessar os recursos de compartilhamento de arquivo e da Web no APP1 a partir do CLIENT1.
  
1. No Gerenciador do servidor, na árvore do painel, clique em **Servidor Local**.
    
2. Em **Propriedades do CLIENT1**, clique em **Ativar** ao lado da **Configuração de Segurança Aprimorada do IE**.
    
3. Na **Configuração de Segurança Aprimorada do Internet Explorer**, clique em **Desativar** para **Administradores** e **Usurários** e, então, clique em **OK**.
    
4. Na tela Inicial, clique em **Internet Explorer** e, então, em**OK**.
    
5. Na Barra de endereços, digite **http<span>://</span>app1.testab.**\<your public domain name>**/**, e clique em ENTER. Você deverá ver a página da Web padrão dos Serviços de informações da Internet do APP1.
    
6. Na barra de tarefas da área de trabalho, clique no ícone do Explorador de Arquivos.
    
7. Na barra de endereços, digite **\\\\app1\\Files** e pressione Enter. Você verá uma janela de pasta com o conteúdo da pasta compartilhada de arquivos.
    
8. Na janela da pasta compartilhada **Arquivos**, clique duas vezes no arquivo **Example.txt**. Você verá o conteúdo do arquivo Example.txt.
    
9. Feche o **Bloco de notas do Example.txt ** e a janela da pasta compartilhada **Arquivos**.
    
Essa é sua configuração atual.
  
![Etapa 3 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Fase 2: criar sua assinatura do Microsoft 365 E5

Nesta fase, você criará uma nova assinatura do Microsoft 365 E5 que usa um novo locatário do Azure AD, que é separado da sua assinatura de produção. É possível fazer isso de duas formas:

- Use uma assinatura de avaliação do Microsoft 365 E5. 

  A assinatura de avaliação do Microsoft 365 E5 é de 30 dias e pode ser facilmente estendida por até 60 dias. Quando essa assinatura expira, você deve convertê-la em uma assinatura paga ou criar uma nova assinatura de avaliação. Criar uma nova assinatura de avaliação significa abrir mão de sua configuração, o que pode incluir cenários complexos.  

- Use uma assinatura de produção separada do Microsoft 365 E5 com uma pequena quantidade de licenças.

  Isso representa um custo adicional, mas garante um ambiente de teste funcional para testar recursos, configurações e cenários que não expiram. Você pode usar o mesmo ambiente de teste a longo prazo para validação de conceitos, demonstração aos colegas, também para desenvolvimento, gerenciamento e teste de aplicativos. Este e o método recomendado.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Inscrever-se em uma assinatura de avaliação do Office 365 E5

Conectar-se ao CLIENT1 com a conta CORP\Usuário1 do portal do Azure.

Para criar uma nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) do Guia de Laboratório de Teste da configuração de base leve.

Para configurar sua nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) do Guia de Laboratório de Teste da configuração de base leve.

#### <a name="using-an-office-365-e5-test-environment"></a>Usando um ambiente de teste do Office 365 E5

Se você quiser apenas um ambiente de teste do Office 365, você pode parar aqui. 

Confira [Guias de Laboratório de Testes do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para Guias de Laboratório de Testes adicionais que se aplicam ao Office 365 e ao Microsoft 365.

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Adicionar uma assinatura de avaliação do Microsoft 365 E5

Para uma assinatura de avaliação do Microsoft 365 E5 e configurar suas contas de usuários com licenças, siga as instruções na [Fase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) do Guia de Laboratório de Teste da configuração de base leve.

  
## <a name="results"></a>Resultados

Seu ambiente de teste agora tem:
  
- Assinatura de avaliação do Microsoft 365 E5.
- Todas as suas contas de usuário apropriadas estão habilitadas para usar o Microsoft 365 E5.
- Uma intranet simulada e simplificada.
    
Esta é sua configuração final.
  
![Fase 2 da configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Agora você está pronto para experimentar os recursos adicionais do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Próximas etapas

Explore esses conjuntos adicionais de guias de laboratório de teste:
  
- [Identidade](m365-enterprise-test-lab-guides.md#identity)
- [Gerenciamento de dispositivo móvel](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Proteção de informações](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
