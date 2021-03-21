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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este Guia de Laboratório de Teste para criar um ambiente de teste empresarial simulado para o Microsoft 365 para empresas.
ms.openlocfilehash: 8df63e1a580b57aa263c11dccaed947f46f2cbb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926039"
---
# <a name="the-simulated-enterprise-base-configuration"></a>A configuração base corporativa simulada

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e office 365 Enterprise.*

Este artigo descreve como criar um ambiente simplificado para o Microsoft 365 para empresas que inclua:

- Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.
- Uma intranet de organização simplificada conectada à Internet, que consiste em três máquinas virtuais em uma rede virtual do Azure (DC1, APP1 e CLIENT1).
 
![A configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

A criação de um ambiente de teste simplificado envolve duas fases:
- [Fase 1: criar uma intranet simulada](#phase-1-create-a-simulated-intranet)
- [Fase 2: criar sua assinatura do Microsoft 365 E5](#phase-2-create-your-microsoft-365-e5-subscription)

Você pode usar o ambiente resultante para testar os recursos e a [](m365-enterprise-test-lab-guides.md) funcionalidade do [Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise) para empresas com guias de laboratório de teste adicionais ou por conta própria.

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para um mapa visual de todos os artigos na pilha guia de laboratório de teste do Microsoft 365 para empresas, vá para [o Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-create-a-simulated-intranet"></a>Fase 1: criar uma intranet simulada

Nesta fase, crie uma intranet simulada nos serviços de infraestrutura do Azure que inclua um controlador de domínio dos Serviços de Domínio do Active Directory (AD DS), um servidor de aplicativos e um computador cliente.

Você usará esses computadores em guias adicionais do [Microsoft 365](m365-enterprise-test-lab-guides.md) para laboratórios de teste corporativos para configurar e demonstrar a identidade híbrida e outros recursos.

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a>Método 1: criar sua intranet simulada com um modelo do Azure Resource Manager

Neste método, você usa um modelo do Gerenciador de Recursos do Azure para criar a intranet simulada. Os modelos do Gerenciador de Recursos do Azure contêm todas as instruções para criar a infraestrutura de rede do Azure, as máquinas virtuais e sua configuração.

Antes de implantar o modelo, leia a página [README do modelo](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) e tenha as seguintes informações prontas:

- O nome de domínio DNS público do seu ambiente de teste (testlab. \<*your public domain*> ). Você inserirá esse nome no campo **Nome de** Domínio da **página implantação** personalizada.
- Um prefixo de rótulo DNS das URLs dos endereços de IP públicos das suas máquinas virtuais. Você precisará inserir esse rótulo no campo **Prefixo do rótulo DNS** da página **Implantação personalizada**.

Depois de ler as instruções, selecione **Implantar no Azure** na página [README](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) do modelo para começar.

>[!Note]
>A intranet simulada criada pelo modelo do Gerenciador de Recursos do Azure requer uma assinatura paga do Azure.

Depois que o modelo for concluído, sua configuração será assim:

![A intranet simulada nos serviços de infraestrutura do Azure](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a>Método 2: criar sua intranet simulada com o Azure PowerShell

Nesse método, use o módulo do Windows PowerShell e do Azure PowerShell para criar a infraestrutura de rede, as máquinas virtuais e suas configurações.

Use esse método caso deseje obter a experiência de criação de elementos de infraestrutura do Azure uma etapa por vez com o PowerShell. Assim, é possível personalizar os blocos de comando do PowerShell para sua própria implantação de outras máquinas virtuais no Azure.

#### <a name="step-1-create-dc1"></a>Etapa 1: criar DC1

Nesta etapa, você cria uma rede virtual do Azure e adiciona DC1, uma máquina virtual que é um controlador de domínio para um domínio do AD DS.

Primeiro, inicie o prompt de comando do Windows PowerShell no computador local.
  
> [!NOTE]
> O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](/powershell/azureps-cmdlets-docs/). 
  
Entre na sua conta do Azure usando o comando a seguir.
  
```powershell
Connect-AzAccount
```

Para obter o nome de sua assinatura, use este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Defina sua assinatura do Azure. Substitua tudo entre aspas, incluindo os colchetes angulares ("<" e ">"), pelo nome correto.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Depois, crie um novo grupo de recursos para o laboratório de testes simulado. Para determinar um nome de grupo de recursos exclusivo, use este comando para relacionar os grupos de recurso existentes.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Crie o novo grupo de recursos com estes comandos. Substitua tudo entre aspas, incluindo os colchetes angulares, com os nomes corretos.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Em seguida, crie a rede virtual TestLab que hospedará a sub-rede de rede corporativa do ambiente empresarial simulado e o proteja com um grupo de segurança de rede. Preencha o nome do seu grupo de recursos e execute esses comandos no prompt de comando do PowerShell no computador local.
  
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
  
Em seguida, conecte-se à máquina virtual DC1:
  
1. No portal [do Azure,](https://portal.azure.com)selecione **Grupos** de Recursos > <o nome do seu novo grupo de recursos ***_> > _* DC1**  >  **Connect**.
    
2. No painel aberto, selecione **Baixar arquivo RDP**. Abra o arquivo DC1.rdp baixado e selecione **Conectar**.
    
3. Especifique o nome da conta de administrador local na DC1:
    
   - No Windows 7:
    
     Na caixa de diálogo Segurança do **Windows,** selecione **Usar outra conta**. Em **Nome do usuário,** insira o nome da conta de administrador local **\\ DC1** < *>.*
    
   - No Windows 8 ou Windows 10:
    
     Na caixa de diálogo Segurança do **Windows,** selecione **Mais opções** e, em seguida, **selecione Usar uma conta diferente**. Em **Nome do usuário,** insira o nome da conta de administrador local **\\ DC1** < *>.*
    
4. Em **Senha,** insira a senha da conta de administrador local e selecione **OK**.
    
5. Quando solicitado, selecione **Sim**.
    
Em seguida, adicione um disco de dados extra como um novo volume com a letra de unidade F:, com este comando, em um prompt de comando do Windows PowerShell de nível de administrador no DC1.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Em seguida, configure o DC1 como um controlador de domínio e servidor DNS para o **testlab.**\<*your public domain*> domínio. Especifique seu nome de domínio público, remova os colchetes angulares e execute esses comandos em um prompt de comando de nível de administrador Windows PowerShell DC1.
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
Será preciso especificar uma senha de administrador no modo de segurança. Armazene essa senha em um local seguro.
  
Esses comandos podem levar alguns minutos para serem concluídos.
  
Após a reinicialização da DC1, reconecte-se à máquina virtual DC1.
  
1. No portal [do Azure,](https://portal.azure.com)selecione **Grupos** de Recursos > <nome do *grupo* de recursos> > **DC1**  >  **Connect**.
    
2. Execute o arquivo DC1.rdp baixado e selecione **Conectar**.
    
3. Em **Segurança do Windows,** selecione **Usar outra conta**. Em **Nome do usuário,** digite **TESTLAB \\** local administrator account name < *>.*
    
4. Na caixa **Senha,** insira a senha da conta de administrador local e selecione **OK**.
    
5. Quando solicitado, selecione **Sim**.
    
Em seguida, crie uma conta de usuário no Active Directory que será usada ao entrar em computadores membros do domínio TESTLAB. Execute esse comando em um prompt de Windows PowerShell de comando de nível de administrador.
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

Observe que este comando solicita que você fornece a senha da conta User1. Essa conta será usada para conexões de área de trabalho remota para todos os computadores membros do domínio TESTLAB, portanto, escolha uma senha forte. Grave a senha da conta User1 e armazene-a em um local seguro.
  
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

Sua configuração atual tem esta aparência:
  
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
  
Para verificar a resolução de nomes e a comunicação de rede entre APP1 e DC1, execute o **ping dc1.testlab.**\<*your public domain name*> comando e verifique se há quatro respostas.
  
Em seguida, adicione a máquina virtual APP1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Observe que, depois de executar o comando **Add-Computer,** você deve fornecer as credenciais da conta de domínio TESTLAB \\ User1.
  
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

Sua configuração atual tem esta aparência:
  
![Etapa 2 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a>Etapa 3: configurar o CLIENT1

Nessa etapa, você cria e configura o CLIENT1, que atua como um laptop, tablet ou computador típico na intranet.

> [!NOTE]  
> O seguinte conjunto de comandos cria a CLIENT1 executando o Windows Server 2016 Datacenter, o que pode ser feito em todos os tipos de assinaturas do Azure. Se você tiver uma assinatura do Azure baseada em Visual Studio, será possível criar a CLIENT1 executando o Windows 10 no [Portal do Azure](https://portal.azure.com).
  
Para criar uma Máquina Virtual do Azure para CLIENT1, preencha o nome do seu grupo de recursos e execute esses comandos no prompt de comando no computador local.
  
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
  
Para verificar a resolução de nomes e a comunicação de rede entre CLIENT1 e DC1, execute o **ping dc1.testlab.**\<*your public domain name*> comando em um prompt de comando do Windows PowerShell e verifique se há quatro respostas.
  
Em seguida, adicione a máquina virtual do CLIENT1 ao domínio TestLab com estes comandos, no prompt do Windows PowerShell.
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

Você deve fornecer as credenciais de conta de domínio \\Usuário1 do TestLab, depois de executar o comando **Add-Computer**.
  
Depois de reiniciar a CLIENT1, conecte-se a ela usando o nome da conta e a senha do \\Usuário1 do TestLab e abra um prompt de comando do Windows PowerShell em nível de administrador.
  
Após esse procedimento, verifique se você consegue acessar os recursos de compartilhamento de arquivo e da Web no APP1 a partir do CLIENT1.
  
1. No Gerenciador de Servidores, no painel de árvore, selecione **Servidor Local**.
    
2. Em **Propriedades para CLIENT1,** selecione **Ao** lado de **Configuração de Segurança Avançada do IE.**
    
3. Em **Configuração de Segurança Avançada do Internet Explorer,** selecione **Desligar** para **Administradores** e **Usuários** e selecione **OK**.
    
4. Na tela Inicial, selecione **Internet Explorer** e, em seguida, selecione **OK**.
    
5. Na barra de endereços, **digite http <span>://</span>app1.testab.** \<*your public domain name*> **/** e pressione **Enter**. Você deverá ver a página da Web padrão dos Serviços de informações da Internet do APP1.
    
6. Na barra de tarefas da área de trabalho, selecione o ícone Explorador de Arquivos.
    
7. Na barra de endereços, insira **\\ \\ arquivos app1 \\** e pressione **Enter**. Você deve ver uma janela de pasta com o conteúdo da pasta compartilhada Arquivos.
    
8. Na janela da pasta compartilhada **Arquivos**, clique duas vezes no arquivo **Example.txt**. Você verá o conteúdo do arquivo Example.txt.
    
9. Feche o **Bloco de notas do Example.txt** e a janela da pasta compartilhada **Arquivos**.
    
Sua configuração atual tem esta aparência:
  
![Etapa 3 da configuração da base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a>Fase 2: criar sua assinatura do Microsoft 365 E5

Nesta fase, você criará uma nova assinatura do Microsoft 365 E5 que usa um novo locatário do Azure AD, que é separado da sua assinatura de produção. É possível fazer isso de duas formas:

- Use uma assinatura de avaliação do Microsoft 365 E5.

  A assinatura de avaliação do Microsoft 365 E5 é de 30 dias e pode ser facilmente estendida por até 60 dias. Quando essa assinatura expira, você deve convertê-la em uma assinatura paga ou criar uma nova assinatura de avaliação. Criar uma nova assinatura de avaliação significa abrir mão de sua configuração, o que pode incluir cenários complexos.  

- Use uma assinatura de produção separada do Microsoft 365 E5 com uma pequena quantidade de licenças.

  Esse é um custo adicional, mas garante que você tenha um ambiente de teste de trabalho que não expire; nele, você pode experimentar recursos, configurações e cenários. Você pode usar o mesmo ambiente de teste a longo prazo para provas de conceito, demonstração para colegas e gerenciamento e desenvolvimento e teste de aplicativos. Este e o método recomendado.

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Inscrever-se em uma assinatura de avaliação do Office 365 E5

No portal do Azure, conecte-se ao CLIENT1 com a conta CORP\User1.

Para criar uma nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) do Guia de Laboratório de Teste da configuração de base leve.

Para configurar sua nova assinatura de avaliação do Office 365 E5, siga as instruções na [Fase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) do Guia de Laboratório de Teste da configuração de base leve.

#### <a name="using-an-office-365-e5-test-environment"></a>Usando um ambiente de teste do Office 365 E5

Se você precisar apenas de um ambiente de teste do Office 365, não precisará ler o restante deste artigo.

Para obter guias de laboratório de teste adicionais que se aplicam ao Microsoft 365 e ao Office 365, consulte [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).

### <a name="add-a-microsoft-365-e5-trial-subscription"></a>Adicionar uma assinatura de avaliação do Microsoft 365 E5

Para adicionar uma assinatura de avaliação do Microsoft 365 E5 e configurar suas contas de usuários com licenças, execute as instruções na Fase [3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) do Guia de Laboratório de Teste de configuração de base leve.

  
## <a name="results"></a>Resultados

Seu ambiente de teste agora tem:
  
- Assinatura de avaliação do Microsoft 365 E5.
- Todas as suas contas de usuário apropriadas estão habilitadas para usar o Microsoft 365 E5.
- Uma intranet simulada e simplificada.
    
Sua configuração final tem esta aparência:
  
![Fase 2 da configuração base corporativa simulada](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Agora você está pronto para experimentar recursos adicionais do [Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)
  
## <a name="next-steps"></a>Próximas etapas

Explore esses conjuntos adicionais de guias de laboratório de teste:
  
- [Identidade](m365-enterprise-test-lab-guides.md#identity)
- [Gerenciamento de dispositivo móvel](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Proteção de informações](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)