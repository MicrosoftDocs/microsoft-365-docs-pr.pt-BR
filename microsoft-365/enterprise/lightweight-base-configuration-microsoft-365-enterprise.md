---
title: Configuração de base leve
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este guia de laboratório de teste para criar um ambiente de teste leve para testar o Microsoft 365 para empresas.
ms.openlocfilehash: 5de9e44f83d4c6bbae2b4148ce39ca371ead2d34
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686773"
---
# <a name="the-lightweight-base-configuration"></a>A configuração de base leve

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Este artigo fornece instruções passo a passo para criar um ambiente simplificado com a assinatura do Microsoft 365 E5 e um computador com o Windows 10 Enterprise. 

![O ambiente de teste leve do Microsoft 3656 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Use o ambiente resultante para testar os recursos e a funcionalidade do [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Clique em [pilha do guia do laboratório de teste do microsoft 365 for Enterprise](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 para empresas.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: criar sua assinatura do Microsoft 365 e5

Começamos com uma assinatura de avaliação do Microsoft 365 E5 e, em seguida, adicionamos a assinatura do Microsoft 365 e5.

Para começar a usar a sua assinatura de avaliação do Microsoft 365 E5, primeiro é necessário um nome de empresa fictícia e uma nova conta da Microsoft.
  
1. Recomendamos que você use uma variante do nome de empresa Contoso para o nome da sua empresa, que é uma empresa fictícia usada no conteúdo de exemplo da Microsoft, mas não é necessário. Registre o seu nome de empresa fictícia aqui: ![Linha](../media/Common-Images/TableLine.png)
    
2. Para se inscrever em uma nova conta da Microsoft, acesse [https://outlook.com](https://outlook.com) e crie uma conta com um novo endereço e conta de email. Você usará essa conta para se inscrever no Office 365.
    
  - Armazene o nome e sobrenome da sua nova conta aqui: ![Linha](../media/Common-Images/TableLine.png)
    
  - Armazene o novo endereço da conta de email aqui:  ![Linha](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Inscrever-se em uma assinatura de avaliação do Office 365 E5

1. Abra o navegador da Internet no computador e vá para [https://aka.ms/e5trial](https://aka.ms/e5trial).
    
2. Na página **Obrigado por escolher o Office 365 E5**, especifique o endereço de sua nova conta de email na etapa 1.
3. Na etapa 2 do processo de assinatura de avaliação, digite as informações solicitadas e execute a verificação.
4. Na etapa 3, digite o nome da organização e, em seguida, o nome da conta que será o administrador global da assinatura. 
5. Para a etapa 4, armazene a URL da página de entrada aqui (selecione e copie):  ![Linha](../media/Common-Images/TableLine.png) 
6. Armazene a ID de usuário aqui: ![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Armazene a senha que você digitou em um local seguro.
   Esse valor será chamado de **nome do administrador global**.
8. Clique em **Ir para Configuração**.
9. Na configuração do Office 365 E5, clique em **Continuar usando *sua organização*.onmicrosoft.com para o email e para entrar** e clique em **Sair e continuar mais tarde**.

Você deve ver o centro de administração do Microsoft 365.
  
A criação de uma assinatura de avaliação do Office 365 é necessária para que seu ambiente de teste tenha um locatário do Azure AD separado de qualquer assinatura paga que você possua. Este separação significa que você pode adicionar e remover usuários e grupos no locatário de teste sem afetar suas assinaturas de produção.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurar a sua assinatura de avaliação do Office 365

Nesta fase, você configurará a sua assinatura com outros usuários, atribuindo a eles licenças do Office 365 E5.
  
Use as instruções em [conectar-se ao Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module) para se conectar à sua assinatura com o módulo PowerShell do Azure Active Directory para Graph do seu computador.
    
Na caixa de diálogo **Solicitação de credenciais do Windows PowerShell**, digite o nome do administrador global (exemplo: jdoe@contosotoycompany.onmicrosoft.com) e senha.
  
Preencha o nome de sua organização (exemplo: contosotoycompany), o código de país com dois caracteres para a sua localização e execute os seguintes comandos no prompt do PowerShell:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de teste. Obviamente, isso é recomendado para assinaturas de produção. 

### <a name="record-key-information-for-future-reference"></a>Registrar principais informações para referência futura

Talvez você queira imprimir este artigo para registrar as informações específicas necessárias para esse ambiente pelos 30 dias da assinatura de avaliação do Office 365. É possível estender facilmente a assinatura de avaliação por mais 30 dias. Para um ambiente de teste permanente, crie uma nova assinatura paga com um locatário do Azure AD separado e uma pequena quantidade de licenças.

Registre esses valores:
  
- nome do administrador global: ![Linha](../media/Common-Images/TableLine.png)onmicrosoft.com (na etapa 6 da Fase 1)
    
    Também armazene a senha dessa conta em um local seguro.
    
- Nome da sua organização de assinatura de avaliação:  ![Linha](../media/Common-Images/TableLine.png) (na etapa 4 da Fase 1)
    
- Para listar as contas do usuário 2, Usuário 3, Usuário 4 e Usuário 5, execute o seguinte comando no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Armazene os nomes de contas aqui:
    
  - Nome da conta do usuário 2: usuário2@![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome da conta do usuário 3: usuário3@![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome da conta do usuário 4: usuário4@![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Nome da conta do usuário 5: usuário5@![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Também registre a senha em comum dessas contas em um local seguro.
   

### <a name="using-an-office-365-test-environment"></a>Usando um ambiente de teste do Office 365

Se você quiser apenas um ambiente de teste do Office 365, você pode parar aqui. 

Confira os [guias de laboratório de teste do Microsoft 365 for Enterprise](m365-enterprise-test-lab-guides.md) para obter guias de laboratório de teste adicionais que se apliquem ao Office 365 e ao Microsoft 365.
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: adicionar uma assinatura de avaliação do Microsoft 365 E5

Nesta fase, inscreva-se para a assinatura de avaliação do Microsoft 365 E5 e adicione-a à mesma organização de sua assinatura de avaliação do Office 365 E5.
  
Primeiro, adicione a assinatura de avaliação do Microsoft 365 E5 e atribua a nova licença do Microsoft 365 à sua conta de administrador global.
  
1. Com uma instância particular de um navegador da Internet, acesse o Centro de administração do Microsoft 365 na [https://admin.microsoft.com](https://admin.microsoft.com) com suas credenciais da conta de administrador global.
    
2. Na página **Centro de administração do Microsoft 365**, na navegação à esquerda, clique em **Cobrança > Serviços de compra**.
    
3. Na página **Serviços de compra**, clique em **Microsoft 365 E5** e, em seguida, clique em **Obter avaliação gratuita**.

4. Na página **Avaliação do Microsoft 365 E5**, escolha receber uma chamada ou um texto, insira seu número de telefone e clique em **Receber mensagem de texto** ou **Receber chamada**. Execute a verificação.

5. Na página **Confirmar seu pedido**, clique em **Experimentar agora**.

6. Na página **Recibo do pedido**, clique em **Continuar**.

7. No centro de administração do Microsoft 365, clique em **Usuários > Usuários ativos**.

8. Em **Usuários ativos**, clique na sua conta de administrador.

9. Clique em **Licenças e aplicativos**.

10. Desabilite a licença do Office 365 Enterprise E5 e habilite a licença do Microsoft 365 E5.

11. Clique em **Salvar alterações** e feche o painel de informações da conta do usuário.

Em seguida, repita as etapas de 8 a 11 do procedimento anterior para todas as outras contas (Usuário 2, Usuário 3, Usuário 4 e Usuário 5).
  
> [!NOTE]
> A assinatura de avaliação do Microsoft 365 E5 é de 30 dias. Para um ambiente de teste permanente, converta esta assinatura de avaliação em uma assinatura paga com uma pequena quantidade de licenças. 
  
Seu ambiente de teste agora tem:
  
- Uma assinatura de avaliação do Microsoft 365 E5.
- Todas as suas contas de usuário apropriadas (tanto a conta de administrador global como todas as cinco contas de usuário) são habilitadas para usar o Microsoft 365 E5.
    
Aqui está a configuração resultante, que adiciona o Microsoft 365 e5.
  
![Fase 3 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: criar um computador com o Windows 10 Enterprise

Nesta fase, crie um computador autônomo executando o Windows 10 Enterprise como um computador físico, uma máquina virtual ou uma máquina virtual do Azure.
  
### <a name="physical-computer"></a>Computador físico

Obtenha um computador pessoal e instale o Windows 10 Enterprise. Você pode baixar a versão de avaliação do Windows 10 Enterprise [aqui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Máquina virtual

Crie uma máquina virtual usando o hipervisor de sua escolha e instale o Windows 10 Enterprise. Você pode baixar a versão de avaliação do Windows 10 Enterprise [aqui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Máquina virtual no Azure

Para criar uma máquina virtual do Windows 10 no Microsoft Azure, ***você deve ter uma assinatura baseada no Visual Studio***, que tem acesso à imagem do Windows 10 Enterprise. Outros tipos de assinatura do Azure, como assinaturas de avaliação e pagas, não têm acesso a esta imagem. Confira as informações mais recentes em [Usar o cliente do Windows no Azure para cenários de desenvolvimento/teste](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Os conjuntos de comandos a seguir usam a versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Esses conjuntos de comandos montam uma máquina virtual do Windows 10 Enterprise chamada WIN10 e toda a infraestrutura necessária, incluindo um grupo de recursos, uma conta de armazenamento e uma rede virtual. Se você já estiver familiarizado com os serviços de infraestrutura Azure, adapte estas instruções para se ajustar à sua infraestrutura implantada no momento. 
  
Inicie um prompt do Microsoft PowerShell.
  
Entre na sua conta do Azure usando o comando a seguir.
  
```powershell
Connect-AzAccount
```

Para obter o nome de sua assinatura, use este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Defina sua assinatura do Azure. Substitua tudo o que está entre aspas, incluindo os \< and > caracteres com os nomes corretos.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Depois, crie um novo grupo de recursos. Para determinar um nome exclusivo para o grupo de recursos, use este comando para listar os grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Crie seu novo grupo de recursos com esses comandos. Substitua tudo dentro das aspas, incluindo os \< and > caracteres com os nomes corretos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Em seguida, crie uma nova rede virtual e uma máquina virtual WIN10 com estes comandos. Quando solicitado, forneça o nome e a senha da conta de administrador local para WIN10 e armazene-os em um local seguro.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Fase 5: adicionar o computador com Windows 10 no Azure AD

Depois de criar a máquina física ou virtual com Windows 10 Enterprise, entre com uma conta Administrador local.
  
> [!NOTE]
> Para uma máquina virtual no Azure, conecte-se usando [estas instruções](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
  
Em seguida, adicione o computador com Windows 10 no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.
  
1. Na área de trabalho do computador WIN10, clique em **Iniciar > Configurações > Contas > Acessar trabalho ou escola > Conectar**.
    
2. Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, clique em **Adicionar este dispositivo ao Azure Active Directory**.
    
3. Em **Conta corporativa ou de estudante**, digite o nome da conta do administrador global da sua assinatura do Microsoft 365 E5 e depois clique em **Avançar**.
    
4. Em **Digitar Senha**, digite a senha da conta de administrador global e clique em **Entrar**.
    
5. Quando solicitado para garantir que esta é sua organização, clique em **Ingressar** e em **Concluído**.
    
6. Feche a janela de configurações.
    
Em seguida, instale os Aplicativos do Microsoft 365 para empresas no computador do WIN10.
  
1. Abra o navegador Microsoft Edge e entre no centro de [Administração do microsoft 365](https://admin.microsoft.com) com suas credenciais de conta de administrador global.
    
2. Na guia **Microsoft Office Home**, clique em **Instalar o Office**.
    
3. Quando solicitado sobre o que fazer, clique em **Executar** e em **Sim** para **Controle de Conta de Usuário**.
    
4. Aguarde até concluir a instalação do Office. Quando você vir **Tudo pronto!**, clique duas vezes em **Fechar**.
    
Este é o ambiente resultante.

![Fase 5 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Isso inclui o computador WIN10 que tem:

- Ingressou no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.
- Registrou um dispositivo do Azure AD no Microsoft Intune (EMS).
- Tenha os Aplicativos do Microsoft 365 para empresas instalados.
  
Agora você está pronto para experimentar os recursos adicionais do [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).
  
## <a name="next-steps"></a>Próximas etapas

Explore esses conjuntos adicionais de guias de laboratório de teste:
  
- [Identidade](m365-enterprise-test-lab-guides.md#identity)
- [Gerenciamento de dispositivo móvel](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Proteção de informações](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
