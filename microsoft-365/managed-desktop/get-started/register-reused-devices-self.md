---
title: Registre dispositivos existentes por conta própria
description: Registre os dispositivos reutilizáveis que você já pode ter para que eles possam ser gerenciados pela Área de Trabalho Gerenciada da Microsoft
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840510"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="0bf94-103">Registre dispositivos existentes por conta própria</span><span class="sxs-lookup"><span data-stu-id="0bf94-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="0bf94-104">Este tópico descreve as etapas para reutilizar dispositivos que você já tem e registrá-los na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf94-104">This topic describes the steps for you to reuse devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="0bf94-105">Se você estiver trabalhando com dispositivos novos, siga as etapas em Registrar novos dispositivos na Área de Trabalho [Gerenciada da Microsoft.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="0bf94-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="0bf94-106">O processo para parceiros está documentado em [etapas para parceiros registrar dispositivos.](register-devices-partner.md)</span><span class="sxs-lookup"><span data-stu-id="0bf94-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="0bf94-107">A Área de Trabalho Gerenciada da Microsoft pode trabalhar com dispositivos novos ou você pode reutilizar dispositivos que talvez já tenha (o que exigirá que você os reimage).</span><span class="sxs-lookup"><span data-stu-id="0bf94-107">Microsoft Managed Desktop can work with brand-new devices or you can reuse devices you might already have (which will require that you reimage them).</span></span> <span data-ttu-id="0bf94-108">Você pode registrar dispositivos com a Área de Trabalho Gerenciada da Microsoft no portal do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="0bf94-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="0bf94-109">Preparar-se para registrar dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="0bf94-109">Prepare to register existing devices</span></span>


<span data-ttu-id="0bf94-110">Para registrar dispositivos existentes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0bf94-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="0bf94-111">Obtenha o hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="0bf94-112">Mesclar os dados de hash</span><span class="sxs-lookup"><span data-stu-id="0bf94-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="0bf94-113">[Registre os dispositivos na Área de Trabalho Gerenciada da Microsoft.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="0bf94-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="0bf94-114">Verifique se a imagem está correta.</span><span class="sxs-lookup"><span data-stu-id="0bf94-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="0bf94-115">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="0bf94-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="0bf94-116">Obter o hash de hardware</span><span class="sxs-lookup"><span data-stu-id="0bf94-116">Obtain the hardware hash</span></span>

<span data-ttu-id="0bf94-117">A Área de Trabalho Gerenciada da Microsoft identifica cada dispositivo exclusivamente referenciando seu hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="0bf94-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="0bf94-118">Você tem quatro opções para obter essas informações de dispositivos que já está usando:</span><span class="sxs-lookup"><span data-stu-id="0bf94-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="0bf94-119">Peça ao fornecedor do OEM o arquivo de registro do AutoPilot, que incluirá os hashes de hardware.</span><span class="sxs-lookup"><span data-stu-id="0bf94-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="0bf94-120">Coletar informações no [Microsoft Endpoint Configuration Manager.](#microsoft-endpoint-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="0bf94-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="0bf94-121">Execute um script do Windows PowerShell usando o [Active Directory ou](#active-directory-powershell-script-method) [manualmente](#manual-powershell-script-method) em cada dispositivo e colete os resultados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="0bf94-122">Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e colete [os hashes em uma unidade flash removível.](#flash-drive-method)</span><span class="sxs-lookup"><span data-stu-id="0bf94-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="0bf94-123">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bf94-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="0bf94-124">Você pode usar o Microsoft Endpoint Configuration Manager para coletar os hashes de hardware de dispositivos existentes que você deseja registrar na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf94-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bf94-125">Todos os dispositivos para os que você deseja obter essas informações devem estar executando o Windows 10, versão 1703 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="0bf94-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="0bf94-126">Se você atendeu a todos esses pré-requisitos, está pronto para coletar as informações seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0bf94-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="0bf94-127">No console do Configuration Manager, selecione **Monitoramento.**</span><span class="sxs-lookup"><span data-stu-id="0bf94-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="0bf94-128">No espaço de trabalho Monitoramento, expanda o **nó Relatórios,** expanda **Relatórios** e selecione o nó **Hardware -** Geral.</span><span class="sxs-lookup"><span data-stu-id="0bf94-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="0bf94-129">Execute o relatório, informações **de dispositivo do Windows Autopilot** e veja os resultados.</span><span class="sxs-lookup"><span data-stu-id="0bf94-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="0bf94-130">No visualizador de relatório, selecione o ícone Exportar e escolha a opção **CSV (delimitado por** vírgula). </span><span class="sxs-lookup"><span data-stu-id="0bf94-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="0bf94-131">Depois de salvar o arquivo, você precisará filtrar os resultados para apenas os dispositivos que planeja registrar na Área de Trabalho Gerenciada da Microsoft e carregar os dados na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0bf94-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="0bf94-132">Abra o Microsoft Endpoint Manager e navegue até **o** menu Dispositivos, procure a seção Área de Trabalho Gerenciada da Microsoft e selecione **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="0bf94-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="0bf94-133">Selecione **+ Registrar dispositivos**, que abre um sub-in para registrar novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-133">Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="0bf94-134">Consulte Registrar [dispositivos usando o Portal de Administração](#register-devices-by-using-the-admin-portal) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0bf94-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="0bf94-135">Método de script do PowerShell do Active Directory</span><span class="sxs-lookup"><span data-stu-id="0bf94-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="0bf94-136">Em um ambiente do Active Directory, você pode usar o cmdlet do PowerShell para coletar remotamente as informações de dispositivos nos Grupos do Active Directory usando `Get-WindowsAutoPilotInfo` o WinRM.</span><span class="sxs-lookup"><span data-stu-id="0bf94-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="0bf94-137">Você também pode usar o cmdlet e obter resultados filtrados para um nome de modelo de hardware específico `Get-AD Computer` incluído no catálogo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model name included in the catalog.</span></span> <span data-ttu-id="0bf94-138">Antes de prosseguir, primeiro confirme esses pré-requisitos e prossiga com as etapas:</span><span class="sxs-lookup"><span data-stu-id="0bf94-138">Before you proceed, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="0bf94-139">O WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="0bf94-139">WinRM is enabled.</span></span>
- <span data-ttu-id="0bf94-140">Os dispositivos que você deseja registrar estão ativos na rede (ou seja, não estão desconectados ou desativados).</span><span class="sxs-lookup"><span data-stu-id="0bf94-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="0bf94-141">Certifique-se de que você tenha um parâmetro de credencial de domínio que tenha permissão para ser executado remotamente nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="0bf94-142">Certifique-se de que o Firewall do Windows permita acesso ao WMI.</span><span class="sxs-lookup"><span data-stu-id="0bf94-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="0bf94-143">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0bf94-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="0bf94-144">Abra o painel **de controle do Windows Defender Firewall** e selecione Permitir um aplicativo ou recurso por meio do Windows Defender **Firewall.**</span><span class="sxs-lookup"><span data-stu-id="0bf94-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="0bf94-145">Encontre **a Instrumentação de Gerenciamento do Windows (WMI)** na lista, habilitada para privada e pública **e** selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bf94-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="0bf94-146">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="0bf94-147">Execute *um* destes scripts:</span><span class="sxs-lookup"><span data-stu-id="0bf94-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="0bf94-148">Acesse todos os diretórios em que possam haver entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="0bf94-149">Remova as entradas de cada dispositivo de todos *os* diretórios, incluindo os Serviços de Domínio do Active Directory do Windows Server e o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0bf94-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="0bf94-150">Esteja ciente de que a remoção pode levar algumas horas para ser completamente processda.</span><span class="sxs-lookup"><span data-stu-id="0bf94-150">Be aware that removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="0bf94-151">Acessar serviços de gerenciamento onde pode haver entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="0bf94-152">Remova as entradas de cada dispositivo de *todos* os serviços de gerenciamento, incluindo o Microsoft Endpoint Configuration Manager, o Microsoft Intune e o Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0bf94-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="0bf94-153">Esteja ciente de que a remoção pode levar algumas horas para ser completamente processda.</span><span class="sxs-lookup"><span data-stu-id="0bf94-153">Be aware that removal could take a few hours to completely process.</span></span>

<span data-ttu-id="0bf94-154">Agora você pode continuar a registrar [dispositivos.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="0bf94-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="0bf94-155">Método de script manual do PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bf94-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="0bf94-156">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="0bf94-157">Executar `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="0bf94-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="0bf94-158">Executar `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="0bf94-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="0bf94-159">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="0bf94-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="0bf94-160">Método de unidade flash</span><span class="sxs-lookup"><span data-stu-id="0bf94-160">Flash drive method</span></span>

1. <span data-ttu-id="0bf94-161">Em um dispositivo diferente do que você está registrando, insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="0bf94-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="0bf94-162">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="0bf94-163">Executar `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="0bf94-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="0bf94-164">Ligue o dispositivo que você está registrando, mas *não inicie a experiência de instalação.*</span><span class="sxs-lookup"><span data-stu-id="0bf94-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="0bf94-165">Se você iniciar acidentalmente a experiência de instalação, terá que redefinir ou reimage o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="0bf94-166">Insira a unidade USB e pressione SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="0bf94-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="0bf94-167">Abra um prompt do PowerShell com direitos administrativos e `cd <pathToUsb>` execute.</span><span class="sxs-lookup"><span data-stu-id="0bf94-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="0bf94-168">Executar `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="0bf94-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="0bf94-169">Executar `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="0bf94-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="0bf94-170">Remova a unidade USB e desligue o dispositivo executando `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="0bf94-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="0bf94-171">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="0bf94-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="0bf94-172">Não a power on the device you are registering again until you've completed registration for it.</span><span class="sxs-lookup"><span data-stu-id="0bf94-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="0bf94-173">Mesclar dados de hash</span><span class="sxs-lookup"><span data-stu-id="0bf94-173">Merge hash data</span></span>

<span data-ttu-id="0bf94-174">Se você coletou os dados de hash de hardware pelos métodos manuais do PowerShell ou da unidade flash, agora precisa ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="0bf94-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="0bf94-175">Veja um exemplo de script do PowerShell para facilitar:</span><span class="sxs-lookup"><span data-stu-id="0bf94-175">Here's a sample PowerShell script to make it easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="0bf94-176">Com os dados de hash mesclados em um arquivo CSV, agora você pode continuar a [registrar os dispositivos.](#register-devices-by-using-the-admin-portal)</span><span class="sxs-lookup"><span data-stu-id="0bf94-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="0bf94-177">Registrar dispositivos usando o Portal de Administração</span><span class="sxs-lookup"><span data-stu-id="0bf94-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="0bf94-178">No [Microsoft Endpoint Manager,](https://endpoint.microsoft.com/)selecione **Dispositivos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="0bf94-179">Procure a seção Área de Trabalho Gerenciada da Microsoft do menu e selecione **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="0bf94-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="0bf94-180">No espaço de trabalho Dispositivos de Área de Trabalho Gerenciada da Microsoft, Selecione **+ Registrar dispositivos**, que abre um sub-in para registrar novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0bf94-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices**, which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="0bf94-181">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0bf94-181">Follow these steps:</span></span>

1. <span data-ttu-id="0bf94-182">Em **Carregamento de arquivo,** forneça um caminho para o arquivo CSV que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0bf94-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="0bf94-183">Selecione **Registrar dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="0bf94-183">Select **Register devices**.</span></span> <span data-ttu-id="0bf94-184">O sistema adicionará os dispositivos à sua lista de dispositivos na **folha** Dispositivos , marcado como **Registro Pendente**.</span><span class="sxs-lookup"><span data-stu-id="0bf94-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="0bf94-185">O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo é a primeira vez que aparece como Pronto para o usuário, o que significa que ele está pronto e aguardando que um usuário comece a usá-lo. </span><span class="sxs-lookup"><span data-stu-id="0bf94-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="0bf94-186">Você pode monitorar o progresso do registro do dispositivo na página principal.</span><span class="sxs-lookup"><span data-stu-id="0bf94-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="0bf94-187">Os possíveis estados relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="0bf94-187">Possible states reported there include:</span></span>

| <span data-ttu-id="0bf94-188">Estado</span><span class="sxs-lookup"><span data-stu-id="0bf94-188">State</span></span> | <span data-ttu-id="0bf94-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="0bf94-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="0bf94-190">Registro Pendente</span><span class="sxs-lookup"><span data-stu-id="0bf94-190">Registration Pending</span></span> | <span data-ttu-id="0bf94-191">O registro ainda não foi feito.</span><span class="sxs-lookup"><span data-stu-id="0bf94-191">Registration is not done yet.</span></span> <span data-ttu-id="0bf94-192">Verifique novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="0bf94-192">Check back later.</span></span> |
| <span data-ttu-id="0bf94-193">Falha no registro</span><span class="sxs-lookup"><span data-stu-id="0bf94-193">Registration failed</span></span> | <span data-ttu-id="0bf94-194">Não foi possível concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="0bf94-194">Registration could not be completed.</span></span> <span data-ttu-id="0bf94-195">Consulte Solução [de problemas de registro de dispositivos](#troubleshooting-device-registration) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0bf94-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="0bf94-196">Pronto para o usuário</span><span class="sxs-lookup"><span data-stu-id="0bf94-196">Ready for user</span></span> | <span data-ttu-id="0bf94-197">O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário.</span><span class="sxs-lookup"><span data-stu-id="0bf94-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="0bf94-198">A Área de Trabalho Gerenciada da Microsoft os orientará durante a configuração pela primeira vez, portanto, não é necessário fazer outras preparações.</span><span class="sxs-lookup"><span data-stu-id="0bf94-198">Microsoft Managed Desktop will guide them through first-time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="0bf94-199">Ativo</span><span class="sxs-lookup"><span data-stu-id="0bf94-199">Active</span></span> | <span data-ttu-id="0bf94-200">O dispositivo foi entregue ao usuário e ele se registrou em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0bf94-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="0bf94-201">Isso também indica que eles estão usando regularmente o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="0bf94-202">Inativo</span><span class="sxs-lookup"><span data-stu-id="0bf94-202">Inactive</span></span> | <span data-ttu-id="0bf94-203">O dispositivo foi entregue ao usuário e ele se registrou em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0bf94-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="0bf94-204">No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).</span><span class="sxs-lookup"><span data-stu-id="0bf94-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="0bf94-205">Solução de problemas de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0bf94-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="0bf94-206">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="0bf94-206">Error message</span></span> | <span data-ttu-id="0bf94-207">Detalhes</span><span class="sxs-lookup"><span data-stu-id="0bf94-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="0bf94-208">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="0bf94-208">Device not found</span></span> | <span data-ttu-id="0bf94-209">Não foi possível registrar esse dispositivo porque não foi possível encontrar uma combinação para o fabricante, o modelo ou o número de série fornecido.</span><span class="sxs-lookup"><span data-stu-id="0bf94-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="0bf94-210">Confirme esses valores com o fornecedor do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="0bf94-211">Hash de hardware não válido</span><span class="sxs-lookup"><span data-stu-id="0bf94-211">Hardware hash not valid</span></span> | <span data-ttu-id="0bf94-212">O hash de hardware fornecido para esse dispositivo não foi formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="0bf94-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="0bf94-213">Verifique o hash de hardware e, em seguida, resubmita.</span><span class="sxs-lookup"><span data-stu-id="0bf94-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="0bf94-214">Dispositivo já registrado</span><span class="sxs-lookup"><span data-stu-id="0bf94-214">Device already registered</span></span> | <span data-ttu-id="0bf94-215">Esse dispositivo já está registrado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0bf94-215">This device is already registered to your organization.</span></span> <span data-ttu-id="0bf94-216">Nenhuma outra ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="0bf94-216">No further action required.</span></span> |
| <span data-ttu-id="0bf94-217">Dispositivo reivindicado por outra organização</span><span class="sxs-lookup"><span data-stu-id="0bf94-217">Device claimed by another organization</span></span> | <span data-ttu-id="0bf94-218">Esse dispositivo já foi reivindicado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="0bf94-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="0bf94-219">Verifique com o fornecedor do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0bf94-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="0bf94-220">Erro inesperado</span><span class="sxs-lookup"><span data-stu-id="0bf94-220">Unexpected error</span></span> | <span data-ttu-id="0bf94-221">Sua solicitação não pôde ser processada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0bf94-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="0bf94-222">Entre em contato com o suporte e forneça a ID da solicitação: <requestId></span><span class="sxs-lookup"><span data-stu-id="0bf94-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="0bf94-223">Verificar a imagem</span><span class="sxs-lookup"><span data-stu-id="0bf94-223">Check the image</span></span>

<span data-ttu-id="0bf94-224">Se o dispositivo tiver vindo de um fornecedor de parceiro da Área de Trabalho Gerenciada da Microsoft, a imagem deverá estar correta.</span><span class="sxs-lookup"><span data-stu-id="0bf94-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="0bf94-225">Você também pode aplicar a imagem por conta própria, se preferir.</span><span class="sxs-lookup"><span data-stu-id="0bf94-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="0bf94-226">Para começar, entre em contato com o representante da Microsoft com quem você está trabalhando e ele fornecerá o local e as etapas para aplicar a imagem.</span><span class="sxs-lookup"><span data-stu-id="0bf94-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="0bf94-227">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="0bf94-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bf94-228">Antes de entregar o dispositivo ao usuário, certifique-se de ter obtido e aplicado as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="0bf94-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="0bf94-229">Se todas as licenças são [](get-started-devices.md)aplicadas, você pode preparar seus usuários para usar dispositivos e, em seguida, o usuário pode iniciar o dispositivo e continuar com a experiência de configuração do Windows.</span><span class="sxs-lookup"><span data-stu-id="0bf94-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









