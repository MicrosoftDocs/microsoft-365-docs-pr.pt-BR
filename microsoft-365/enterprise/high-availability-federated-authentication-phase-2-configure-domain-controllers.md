---
title: Autenticação federada de alta disponibilidade fase 2 configure os controladores de domínio
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Resumo: Configure os controladores de domínio e o servidor de sincronização de diretório para a autenticação federada de alta disponibilidade para o Microsoft 365 no Microsoft Azure.'
ms.openlocfilehash: 1c3fd686ee553a57d66dcfd51a6045167a12de8a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687307"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a>Autenticação federada de alta disponibilidade Fase 2: configurar controladores de domínio

Nesta fase de implantação de alta disponibilidade para a autenticação federada do Microsoft 365 nos serviços de infraestrutura do Azure, configure dois controladores de domínio e o servidor de sincronização de diretório na rede virtual do Azure. Solicitações da Web de clientes para autenticação podem então ser autenticadas na rede virtual do Azure, em vez de o tráfego de autenticação ser enviado na conexão de VPN site a site à sua rede local.
  
> [!NOTE]
> Os serviços de Federação do Active Directory (AD FS) não podem usar o Azure Active Directory (Azure AD) como um substituto para os controladores de domínio dos serviços de domínio Active Directory (AD DS). 
  
Você deve concluir essa fase antes de passar para a [fase 3: configurar servidores do AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Consulte [implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) para todas as fases.
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a>Criar máquinas virtuais de controlador de domínio no Azure

Em primeiro lugar, você precisa preencher a coluna **Nome da máquina virtual** da Tabela M e modificar tamanhos de máquina virtual, conforme necessário, na coluna **Tamanho mínimo**.
  
|**Item**|**Nome da máquina virtual**|**Imagem da galeria**|**Tipo de armazenamento**|**Tamanho mínimo**|
|:-----|:-----|:-----|:-----|:-----|
|1.  <br/> |![linha](../media/Common-Images/TableLine.png)  (primeiro controlador de domínio, DC1 de exemplo)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|2.  <br/> |![linha](../media/Common-Images/TableLine.png)  (segundo controlador de domínio, DC2 de exemplo)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|3.  <br/> |![linha](../media/Common-Images/TableLine.png) (servidor de sincronização de diretório, exemplo DS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|4.  <br/> |![linha](../media/Common-Images/TableLine.png) (primeiro servidor AD FS, exemplo ADFS1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|5.  <br/> |![linha](../media/Common-Images/TableLine.png) (segundo servidor AD FS, exemplo ADFS2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|6.  <br/> |![linha](../media/Common-Images/TableLine.png) (primeiro servidor de proxy de aplicativo Web, exemplo WEB1)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
|7.  <br/> |![linha](../media/Common-Images/TableLine.png) (segundo servidor de proxy de aplicativo Web, exemplo WEB2)  <br/> |Windows Server 2016 Datacenter  <br/> |Standard_LRS  <br/> |Standard_D2  <br/> |
   
 **Tabela M-máquinas virtuais para a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure**
  
Para obter a lista completa de tamanhos de máquinas virtuais, confira [Tamanhos das máquinas virtuais](https://docs.microsoft.com/azure/virtual-machines/virtual-machines-windows-sizes).
  
O seguinte bloco de comandos do Azure PowerShell cria as máquinas virtuais para os dois controladores de domínio. Especifique os valores para as variáveis, removendo os \< and > caracteres. Observe que este bloco de comandos do Azure PowerShell usa valores para as tabelas a seguir:
  
- Tabela M, para suas máquinas virtuais
    
- Tabela R, para seus grupos de recursos
    
- Tabela V, para suas configurações de rede virtual
    
- Tabela S, para suas sub-redes
    
- Tabela I, para seu endereço IP estático
    
- Tabela A, para seus conjuntos de disponibilidade
    
Lembre-se de que você definiu as tabelas R, V, S, I e A na [fase 1: configurar o Azure](high-availability-federated-authentication-phase-1-configure-azure.md).
  
> [!NOTE]
> [!OBSERVAçãO] O comando a seguir define o uso da versão mais recente do Azure PowerShell. Confira [introdução ao PowerShell do Azure](https://docs.microsoft.com/powershell/azure/get-started-azureps). 
  
Quando tiver fornecido todos os valores corretos, execute o bloco resultante no prompt do Azure PowerShell ou no Ambiente de Script Integrado (ISE) do PowerShell no computador local.
  
> [!TIP]
> Para gerar blocos de comando prontos para executar do PowerShell com base em suas configurações personalizadas, use esta [pasta de trabalho de configuração do Microsoft Excel](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx). 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Como essas máquinas virtuais são para um aplicativo de intranet, elas não recebem um endereço IP público ou um rótulo de nome de domínio DNS, nem estão expostas à Internet. No entanto, isso também significa que você não pode se conectar a eles no portal do Azure. A opção **Conectar** não está disponível quando você visualiza as propriedades da máquina virtual. Use o acessório Conexão de Área de Trabalho Remota ou outra ferramenta de Área de Trabalho Remota para se conectar à máquina virtual usando seu endereço IP privado ou o nome DNS da intranet.
  
## <a name="configure-the-first-domain-controller"></a>Configurar o primeiro controlador de domínio

Use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota com a primeira máquina virtual de controlador de domínio. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.
  
Em seguida, adicione o disco de dados extra ao primeiro controlador de domínio com esse comando a partir de um prompt de comando do Windows PowerShell **na primeira máquina virtual do controlador de domínio**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Em seguida, teste a conectividade do primeiro controlador de domínio com os locais na rede da sua organização usando o comando **ping** para executar ping em nomes e endereços IP de recursos nessa rede.
  
Esse procedimento assegura que a resolução de nomes DNS esteja funcionando corretamente (que a máquina virtual esteja corretamente configurada com os servidores DNS locais) e que pacotes possam ser enviados de e para a rede virtual entre locais. Se esse teste básico falhar, entre em contato com seu departamento de TI para solucionar problemas de entrega de pacotes e resolução de nomes DNS.
  
Em seguida, no prompt de comandos do Windows PowerShell no primeiro controlador de domínio, execute os seguintes comandos:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

Você será solicitado a fornecer as credenciais de uma conta de administrador de domínio. O computador será reiniciado.
  
## <a name="configure-the-second-domain-controller"></a>Configurar o segundo controlador de domínio

Use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota com a segunda máquina virtual de controlador de domínio. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.
  
Em seguida, você precisa adicionar o disco de dados extra ao segundo controlador de domínio com esse comando a partir de um prompt de comando do Windows PowerShell **na segunda máquina virtual de controlador de domínio**:
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Em seguida, execute os seguintes comandos:
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

Você será solicitado a fornecer as credenciais de uma conta de administrador de domínio. O computador será reiniciado.
  
Em seguida, você precisará atualizar os servidores DNS da sua rede virtual, para que o Azure atribua máquinas virtuais aos endereços IP dos dois novos controladores de domínio para uso como seus servidores DNS. Preencha as variáveis e, em seguida, execute esses comandos em um prompt de comando do Windows PowerShell no computador local:
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

Observe que reiniciamos os dois controladores de domínio para que eles não sejam configurados com os servidores DNS locais como servidores DNS. Como ambos são servidores DNS, eles foram configurados automaticamente com os servidores DNS locais como encaminhadores de DNS quando foram promovidos para controladores de domínio.
  
Em seguida, precisamos criar um site de replicação do Active Directory para garantir que os servidores na rede virtual do Azure usem os controladores de domínio locais. Conecte a um dos controlador de domínio com uma conta de administrador de domínio e execute os seguintes comandos em um prompt do Windows PowerShell em nível de administrador:
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a>Configurar o servidor de sincronização de diretórios

Use o cliente de área de trabalho remota de sua preferência e crie uma conexão de área de trabalho remota com a máquina virtual do servidor de sincronização de diretório. Use seu nome de computador ou DNS de intranet e as credenciais da conta de administrador local.
  
Em seguida, ingresse-o no domínio do AD DS apropriado com estes comandos no prompt do Windows PowerShell.
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

Veja a seguir a configuração resultante da conclusão bem-sucedida dessa fase, com nomes de computador de espaço reservado.
  
**Fase 2: os controladores de domínio e o servidor de sincronização de diretório para a infraestrutura de autenticação federada de alta disponibilidade no Azure**

![Fase 2 da infraestrutura de autenticação federada de alta disponibilidade da Microsoft 365 no Azure com controladores de domínio](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a>Próxima etapa

Use a [fase 3: configurar servidores do AD FS](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) para continuar Configurando essa carga de trabalho.
  
## <a name="see-also"></a>Confira também

[Implantar a autenticação federada de alta disponibilidade para o Microsoft 365 no Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[Identidade federada para seu ambiente de desenvolvimento/teste do Microsoft 365](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[Centro de soluções e arquitetura do Microsoft 365](../solutions/solution-architecture-center.md)


