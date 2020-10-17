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
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487383"
---
# <a name="the-lightweight-base-configuration"></a>A configuração de base leve

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Este artigo descreve como criar um ambiente simplificado com uma assinatura do Microsoft 365 E5 e um computador executando o Windows 10 Enterprise.

![O ambiente de teste leve do Microsoft 3656 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

A criação de um ambiente de teste leve envolve cinco fases:
- [Fase 1: criar sua assinatura do Microsoft 365 e5](#phase-1-create-your-microsoft-365-e5-subscription)
- [Fase 2: configurar a sua assinatura de avaliação do Office 365](#phase-2-configure-your-office-365-trial-subscription)
- [Fase 3: adicionar uma assinatura de avaliação do Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Fase 4: criar um computador com o Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Fase 5: adicionar o computador com Windows 10 no Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Use o ambiente resultante para testar os recursos e a funcionalidade do [Microsoft 365 para empresas](https://www.microsoft.com/microsoft-365/enterprise).

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Para ver um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, consulte [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Talvez você queira imprimir este artigo para registrar as informações específicas necessárias para esse ambiente pelos 30 dias da assinatura de avaliação do Office 365. É possível estender facilmente a assinatura de avaliação por mais 30 dias. Para um ambiente de teste permanente, crie uma nova assinatura paga com um locatário do Azure AD separado e uma pequena quantidade de licenças.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Fase 1: criar sua assinatura do Microsoft 365 e5

Começamos com uma assinatura de avaliação do Microsoft 365 E5 e, em seguida, adicionamos a assinatura do Microsoft 365 e5.

>[!NOTE]
>Recomendamos que você crie uma assinatura de avaliação do Office 365 para que seu ambiente de teste tenha um locatário do Azure AD separado de todas as assinaturas pagas no momento. Essa separação significa que você pode adicionar e remover usuários e grupos no locatário de teste sem afetar suas assinaturas de produção.

Para começar a usar a sua assinatura de avaliação do Microsoft 365 E5, primeiro é necessário um nome de empresa fictícia e uma nova conta da Microsoft.
  
1. Recomendamos que você use uma variante do nome de empresa Contoso para o nome da sua empresa, que é uma empresa fictícia usada no conteúdo de exemplo da Microsoft, mas não é necessário. Registre o seu nome de empresa fictícia aqui: ![Linha](../media/Common-Images/TableLine.png)
    
2. Para se inscrever em uma nova conta da Microsoft, acesse [https://outlook.com](https://outlook.com) e crie uma conta com um novo endereço e conta de email. Você usará essa conta para se inscrever no Office 365.
    
    - Armazene o nome e sobrenome da sua nova conta aqui: ![Linha](../media/Common-Images/TableLine.png)
    
    - Armazene o novo endereço da conta de email aqui:  ![Linha](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Inscrever-se em uma assinatura de avaliação do Office 365 E5

1. No navegador, vá para [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. Na etapa 1 da página **Obrigado por escolher o Office 365 E5** , insira seu novo endereço de conta de email.
3. Na etapa 2 do processo de inscrição de trilha, insira as informações solicitadas e execute a verificação.
4. Na etapa 3, insira um nome de organização e, em seguida, um nome de conta que será o administrador global da assinatura.
5. Para a etapa 4, armazene a URL da página de entrada aqui (selecione e copie):  ![Linha](../media/Common-Images/TableLine.png)
6. Armazene a ID de usuário aqui: ![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Registre a senha que você inseriu em um local seguro.
   Esse valor será chamado de **nome do administrador global**.
7. Selecione **ir para a configuração**.
8. Na configuração do Office 365 e5, selecione **continuar usando *sua organização*. onmicrosoft.com para email e entrada**e, em seguida, selecione **sair e continuar mais tarde**.

Você deve ver o centro de administração do Microsoft 365.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Fase 2: configurar a sua assinatura de avaliação do Office 365

Nesta fase, você configurará a sua assinatura com outros usuários, atribuindo a eles licenças do Office 365 E5.
  
Para se conectar à sua assinatura com o módulo do PowerShell do Azure Active Directory para Graph a partir do seu computador, use as instruções em [conectar-se ao Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
    
Na caixa de diálogo **solicitação de credencial do Windows PowerShell** , digite o nome do administrador global (por exemplo, *jdoe@contosotoycompany.onmicrosoft.com*) e a senha.
  
Preencha o nome da sua organização (por exemplo, *contosotoycompany*), o código de país de dois caracteres do seu local, uma senha de conta comum e, em seguida, execute os seguintes comandos no prompt do PowerShell:

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

Se você ainda não gravou esses valores, registre-os agora:
  
- Nome do administrador global: ![Linha](../media/Common-Images/TableLine.png)onmicrosoft.com (na etapa 6 da Fase 1)
    
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

Se você precisar apenas de um ambiente de teste do Office 365, não será necessário ler o restante deste artigo.

Para obter guias de laboratório de teste adicionais que se aplicam ao Office 365 e ao Microsoft 365, consulte [microsoft 365 para Enterprise Test Lab guias](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Fase 3: adicionar uma assinatura de avaliação do Microsoft 365 E5

Nesta fase, inscreva-se para a assinatura de avaliação do Microsoft 365 E5 e adicione-a à mesma organização de sua assinatura de avaliação do Office 365 E5.
  
Primeiro, adicione a assinatura de avaliação do Microsoft 365 E5 e atribua a nova licença do Microsoft 365 à sua conta de administrador global.
  
1. Em uma janela privada do navegador da Internet, use suas credenciais de conta de administrador global para entrar no centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. Na página **centro de administração do Microsoft 365** , no painel de navegação à esquerda, selecione **cobrança > comprar serviços**.
    
3. Na página **comprar serviços** , selecione **Microsoft 365 E5**e, em seguida, selecione **obter avaliação gratuita**.

4. Na página de **avaliação do Microsoft 365 E5** , opte por receber uma mensagem de texto ou chamada telefônica, insira seu número de telefone e, em seguida, selecione o **texto me** ou **telefonar**. Execute a verificação.

5. Na página **confirmar sua encomenda** , selecione **experimentar agora**.

6. Na página **recibo do pedido** , selecione **continuar**.

7. No centro de administração do Microsoft 365, selecione **usuários > usuários ativos**.

8. Em **usuários ativos**, selecione sua conta de administrador.

9. Selecione **licenças e aplicativos**.

10. Desabilite a licença do Office 365 Enterprise E5 e habilite a licença do Microsoft 365 E5.

11. Selecione **salvar alterações**e feche o painel de informações da conta de usuário.

Em seguida, repita as etapas de 8 a 11 do procedimento anterior para todas as outras contas (Usuário 2, Usuário 3, Usuário 4 e Usuário 5).
  
> [!NOTE]
> O comprimento da assinatura de avaliação do Microsoft 365 E5 é de 30 dias. Para um ambiente de teste permanente, converta esta assinatura de avaliação em uma assinatura paga com uma pequena quantidade de licenças.
  
Seu ambiente de teste agora tem:
  
- Uma assinatura de avaliação do Microsoft 365 E5.
- Todas as suas contas de usuário apropriadas (tanto a conta de administrador global como todas as cinco contas de usuário) são habilitadas para usar o Microsoft 365 E5.
    
A configuração resultante, que adiciona o Microsoft 365 e5, tem a seguinte aparência:
  
![Fase 3 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Fase 4: criar um computador com o Windows 10 Enterprise

Nesta fase, crie um computador autônomo executando o Windows 10 Enterprise como um computador físico, uma máquina virtual ou uma máquina virtual do Azure.
  
### <a name="physical-computer"></a>Computador físico

Em um computador pessoal, instale o Windows 10 Enterprise. Você pode baixar a versão de avaliação do Windows 10 Enterprise [aqui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine"></a>Máquina virtual

Use o hipervisor de sua escolha para criar uma máquina virtual e, em seguida, instale o Windows 10 Enterprise nele. Você pode baixar a versão de avaliação do Windows 10 Enterprise [aqui](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).
  
### <a name="virtual-machine-in-azure"></a>Máquina virtual no Azure

Para criar uma máquina virtual do Windows 10 no Microsoft Azure, ***você deve ter uma assinatura baseada no Visual Studio***, que tem acesso à imagem do Windows 10 Enterprise. Outros tipos de assinatura do Azure, como assinaturas de avaliação e pagas, não têm acesso a esta imagem. Confira as informações mais recentes em [Usar o cliente do Windows no Azure para cenários de desenvolvimento/teste](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> [!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estes conjuntos de comandos criam uma máquina virtual do Windows 10 Enterprise chamada WIN10 e toda a infraestrutura necessária, incluindo um grupo de recursos, uma conta de armazenamento e uma rede virtual. Se você já estiver familiarizado com os serviços de infraestrutura do Azure, adapte estas instruções para se adequar à infraestrutura atualmente implantada.
  
Inicie um prompt do Microsoft PowerShell.
  
Em seguida, entre com sua conta do Azure usando este comando.
  
```powershell
Connect-AzAccount
```

Obtenha o nome da sua assinatura usando este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Defina sua assinatura do Azure. Substitua tudo dentro das aspas, incluindo os \< and > caracteres, pelo nome correto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Depois, crie um novo grupo de recursos. Para determinar um nome exclusivo para o grupo de recursos, use este comando para listar os grupos de recursos existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Crie o novo grupo de recursos com estes comandos. Substitua tudo dentro das aspas, incluindo os \< and > caracteres, com os nomes corretos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Em seguida, crie uma nova rede virtual e a máquina virtual do WIN10 com esses comandos. Quando solicitado, forneça o nome e a senha da conta de administrador local para o WIN10 e armazene-os em um local seguro.
  
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
> Para uma máquina virtual no Azure, use  [estas instruções](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) para se conectar a ela.
  
Em seguida, adicione o computador com Windows 10 no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.
  
1. Na área de trabalho do computador WIN10, selecione **Iniciar Configurações de > > contas > acessar trabalho ou escola > conectar**.
    
2. Na caixa de diálogo **Configurar uma conta corporativa ou de estudante** , selecione **Adicionar este dispositivo ao Azure Active Directory**.
    
3. Em **conta corporativa ou de estudante**, insira o nome da conta de administrador global da sua assinatura do Microsoft 365 E5 e, em seguida, selecione **Avançar**.
    
4. Em **Inserir senha**, digite a senha da sua conta de administrador global e selecione **entrar**.
    
5. Quando solicitado a garantir que esta é sua organização, selecione **ingressar**e selecione **concluído**.
    
6. Feche a janela de configurações.
    
Em seguida, instale o Microsoft 365 aplicativos para empresas no computador do WIN10:
  
1. Abra o navegador Microsoft Edge e entre no centro de [Administração do microsoft 365](https://admin.microsoft.com) com suas credenciais de conta de administrador global.
    
2. Na guia **Microsoft Office Home** , selecione **instalar o Office**.
    
3. Quando solicitado, selecione **executar**e, em seguida, selecione **Sim** para controle de **conta de usuário**.
    
4. Aguarde o Office concluir sua instalação. Ao ver **que você está pronto!**, selecione **fechar** duas vezes.
    
O ambiente resultante tem a seguinte aparência:

![Fase 5 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Isso inclui o computador WIN10 que tem:

- Ingressou no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.
- Registrou um dispositivo do Azure AD no Microsoft Intune (EMS).
- Microsoft 365 aplicativos para Enterprise instalado.
  
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
