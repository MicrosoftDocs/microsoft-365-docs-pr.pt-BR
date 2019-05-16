---
title: Configuração de base leve
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este Guia de Laboratório de Teste para criar um ambiente de teste leve para testar o Microsoft 365 Enterprise.
ms.openlocfilehash: a189cb63847f2b95402a864422257a38d1f098d1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072181"
---
# <a name="the-lightweight-base-configuration"></a>A configuração de base leve

Este artigo fornece instruções passo a passo para criar um ambiente simplificado com a assinatura do Microsoft 365 E5 e um computador com o Windows 10 Enterprise. 

![O ambiente de teste leve do Microsoft 3656 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Use o ambiente resultante para testar os recursos e as funcionalidades do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.

## <a name="phase-1-create-your-office-365-e5-subscription"></a>Fase 1: criar uma assinatura do Office 365 E5

Siga as etapas da Fase 2 e Fase 3 do [Ambiente de desenvolvimento/teste do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) para criar um leve ambiente de desenvolvimento/teste do Office 365.

>[!Note]
>A criação de uma assinatura de avaliação do Office 365 é necessária para que seu ambiente de desenvolvimento/teste tenha um locatário do Azure AD separado de qualquer assinatura paga que você possua. Este separação significa que você pode adicionar e remover usuários e grupos no locatário de teste sem afetar suas assinaturas de produção.
>
  
## <a name="phase-2-add-a-microsoft-365-e5-trial-subscription"></a>Fase 2: adicionar uma assinatura de avaliação do Microsoft 365 E5.

Nesta fase, inscreva-se para a assinatura de avaliação do Microsoft 365 E5 e adicione-a à mesma organização de sua assinatura de avaliação do Office 365 E5.
  
Primeiro, adicione a assinatura de avaliação do Microsoft 365 E5 e atribua uma licença do Microsoft 365 à sua conta de administrador global.
  
1. Com uma instância particular de um navegador da Internet, acesse o Centro de administração do Microsoft 365 na [http://admin.microsoft.com](http://admin.microsoft.com) com suas credenciais da conta de administrador global.
    
2. Na página **Centro de administração do Microsoft 365**, na navegação à esquerda, clique em **Cobrança > Serviços de compra**.
    
3. Na página **Serviços de compra**, encontre o item **Microsoft 365 E5**. Passe o ponteiro do mouse sobre ele e clique em **Iniciar avaliação gratuita**.

4. Na página **Avaliação do Microsoft 365 E5**, escolha receber uma chamada ou um texto, insira seu número de telefone e clique em **Receber mensagem de texto** ou **Receber chamada**.

5. Na página **Confirmar seu pedido**, clique em **Experimentar agora**.

6. Na página **Recibo do pedido**, clique em **Continuar**.

7. No Centro de administração do Microsoft 365 clique em **Usuários ativos**e, em seguida, sua conta de administrador.

8. Clique em **Editar** para **Licenças de produto**.

9. Desative a licença do Office 365 Enterprise E5 e habilite a licença do Microsoft 365 E5.

10. Clique em **Salvar> Fechar >Fechar**.

Em seguida, ***se você concluiu a Fase 3 do*** [Ambiente de desenvolvimento/teste do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), repita as etapas de 8 a 11 do procedimento anterior para todas as suas contas (Usuário 2, Usuário 3, Usuário 4 e Usuário 5).
  
> [!NOTE]
> A assinatura de avaliação do Microsoft 365 E5 é de 30 dias. Para um ambiente de teste permanente, converta esta assinatura de avaliação para uma assinatura paga com uma pequena quantidade de licenças. 
  
Seu ambiente de teste agora tem:
  
- Uma assinatura de avaliação do Microsoft 365 E5.
- Todas as suas contas de usuário apropriadas (tanto a conta de administrador global como todas as cinco contas de usuário) são habilitadas para usar o Microsoft 365 E5.
    
A figura 1 mostra sua configuração resultante, que adiciona o Microsoft 365 E5, que inclui o Office 365 e o Enterprise Security + Management (EMS).
  
**Figura 1: adicionar a assinatura de avaliação do Microsoft 365**

![Fase 2 do ambiente de teste do Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a>Fase 3: criar um computador com o Windows 10 Enterprise

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
  
```
Connect-AzAccount
```

Para obter o nome de sua assinatura, use este comando.
  
```
Get-AzSubscription | Sort Name | Select Name
```

Defina sua assinatura do Azure. Substitua tudo o que está entre aspas, incluindo os caracteres \< e >, pelo nome correto.
  
```
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Depois, crie um novo grupo de recursos. Para determinar um nome exclusivo para o grupo de recursos, use este comando para listar os grupos de recursos existentes.
  
```
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Crie seu novo grupo de recursos com estes comandos. Substitua tudo o que está entre aspas, incluindo os caracteres \< e >, pelos nomes corretos.
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Em seguida, crie uma nova rede virtual e uma máquina virtual WIN10 com estes comandos. Quando solicitado, forneça o nome e a senha da conta de administrador local para WIN10 e armazene-os em um local seguro.
  
```
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a>Fase 4: adicionar o computador com Windows 10 no Azure AD

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
    
Em seguida, instale o Office 365 ProPlus no computador WIN10.
  
1. Abra o navegador Microsoft Edge e entre no portal do Office com as credenciais da conta de administrador global. Para obter ajuda, consulte [Onde entrar no Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Na guia **Microsoft Office Home**, clique em **Instalar o Office**.
    
3. Quando solicitado sobre o que fazer, clique em **Executar** e em **Sim** para **Controle de Conta de Usuário**.
    
4. Aguarde até concluir a instalação do Office. Quando você vir **Tudo pronto!**, clique duas vezes em **Fechar**.
    
A Figura 3 mostra o ambiente resultante, que inclui o computador do WIN10 que:

- Ingressou no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.
- Registrou um dispositivo do Azure AD no Microsoft Intune (EMS).
- Instalou o Office 365 ProPlus.
  
**Figura 2: a configuração final de um ambiente de teste do Microsoft 365**

![Fase 4 do ambiente de teste do Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
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
