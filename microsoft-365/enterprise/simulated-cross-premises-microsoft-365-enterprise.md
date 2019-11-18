---
title: Rede virtual simulada entre locais em um ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
description: 'Resumo: crie uma rede virtual simulada entre locais no Microsoft Azure como um ambiente de teste do Microsoft 365.'
ms.openlocfilehash: be753251670f882b277305f808354791efc38547
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673307"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Rede virtual simulada entre instalações em um ambiente de teste do Microsoft 365

*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste do Microsoft 365 Enterprise e do Office 365 Enterprise.*

Este artigo ajuda você a criar um ambiente simulado de nuvem híbrida com o Microsoft Azure usando duas redes virtuais do Azure. Veja a configuração resultante. 
  
![Fase 3 do ambiente de desenvolvimento/teste da rede virtual simulada entre locais, com a máquina virtual DC2 na VNet XPrem](media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Isso simula um ambiente de produção de nuvem híbrida para o IaaS do Azure e consiste em:
  
- Uma rede local simulada e simplificada hospedada na rede virtual do Azure (a rede virtual TestLab). 
    
- Uma rede virtual simulada entre locais hospedada no Azure (XPrem).
    
- Uma relação de emparelhamento de VNets entre as duas redes virtuais.
    
- Um controlador de domínio secundário na rede virtual XPrem.
    
Isso fornece uma base e um ponto de partida comuns a partir dos quais você pode: 
  
- Desenvolver e testar aplicativos em um ambiente simulado de nuvem híbrida para o IaaS do Azure.
    
- Criar configurações de teste para computadores, algumas na rede virtual TestLab e outras na rede virtual XPrem, para simular cargas de trabalho de TI baseadas na nuvem híbrida.
    
Há três fases principais para configurar esse ambiente de desenvolvimento/teste:
  
1. Configurar a rede virtual TestLab.
    
2. Criar a rede virtual entre locais.
    
3. Configurar o DC2.
    
> [!NOTE]
> Essa configuração requer uma assinatura paga do Azure. 

Você pode usar o ambiente resultante para testar os recursos e a funcionalidade do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) com os [Guias de laboratório de teste](m365-enterprise-test-lab-guides.md) adicionais ou por sua própria conta.

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.

## <a name="phase-1-configure-the-testlab-virtual-network"></a>Fase 1: configurar a rede virtual TestLab

Use as instruções na **Fase 1** da [configuração base corporativa simulada](simulated-ent-base-configuration-microsoft-365-enterprise.md) para configurar os computadores DC1, APP1 e CLIENT1 na rede virtual Azure chamada TestLab.
  
Essa é sua configuração atual. 
  
![A configuração base corporativa simulada no Azure.](media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>Fase 2: criar uma rede virtual XPrem

Nesta fase, crie e configure a nova rede virtual XPrem e conecte-se à rede virtual TestLab com emparelhamento de VNets.
  
Primeiro, inicie um prompt do Azure PowerShell em seu computador local.
  
> [!NOTE]
> O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [Introdução aos cmdlets do Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Em seguida, entre com sua conta do Azure usando este comando.
  
```powershell
Connect-AzAccount
```

Para obter o nome de sua assinatura, use este comando.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Defina sua assinatura do Azure. Substitua tudo o que está entre aspas, incluindo os caracteres \< e >, pelos nomes corretos.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Em seguida, crie a rede virtual XPrem e proteja-a usando um grupo de segurança de rede com estes comandos.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Depois, crie a relação de emparelhamento de VNets entre as VNets TestLab e XPrem com estes comandos.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

Esta é sua configuração atual. 
  
![Fase 2 do ambiente de desenvolvimento/teste da rede virtual simulada entre locais, com a relação de emparelhamento de VNet e VNet XPrem](media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>Fase 3: configurar o DC2

Nesta fase, crie a máquina virtual DC2 na rede virtual XPrem e configure-a como um controlador de domínio de réplica.
  
Primeiro, crie uma máquina virtual para o DC2. Execute esses comandos no prompt de comando do Azure PowerShell em seu computador local.
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Em seguida, conecte-se à nova máquina virtual DC2 a partir do [portal do Azure](https://portal.azure.com) usando o nome e a senha da conta de administrador local.
  
Em seguida, configure uma regra de Firewall do Windows para permitir o tráfego para testes básicos de conectividade. No DC2, em um prompt de comando de nível de administrador do Windows PowerShell, execute esses comandos. 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

O comando ping deve resultar em quatro respostas bem-sucedidas do endereço IP 10.0.0.4. Este é um teste de tráfego entre a relação de emparelhamento de VNets. 
  
Em seguida, adicione o disco de dados extra como um novo volume com a letra de unidade F:, com este comando em um prompt de comando do Windows PowerShell no DC2.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Depois, configure o DC2 como controlador de domínio de réplica para o domínio corp.contoso.com. Execute estes comandos em um prompt de comando do Windows PowerShell no DC2.
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

Observe que você será solicitado a fornecer a senha de CORP\\Usuário1 e uma senha do Modo de Restauração dos Serviços de Diretório (DSRM) e a reiniciar o DC2. 
  
Agora que a rede virtual XPrem tem seu próprio servidor DNS (DC2), você deve configurá-la para usar esse servidor DNS. Execute esses comandos no prompt de comando do Azure PowerShell em seu computador local.
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

No portal do Azure no computador local, conecte-se ao DC1 com as credenciais CORP\\Usuário1. Para configurar o domínio CORP de modo que os computadores e usuários usem seu controlador de domínio local para autenticação, execute esses comandos em um prompt de comando do Windows PowerShell como administrador no DC1.
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

Esta é sua configuração atual. 
  
![Fase 3 do ambiente de desenvolvimento/teste da rede virtual simulada entre locais, com a máquina virtual DC2 na VNet XPrem](media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Seu ambiente simulado de nuvem híbrida do Azure já está pronto para testes.
  
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
