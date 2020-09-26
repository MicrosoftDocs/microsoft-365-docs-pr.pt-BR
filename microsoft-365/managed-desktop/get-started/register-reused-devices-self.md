---
title: Registre dispositivos existentes por conta própria
description: Registrar os dispositivos reutilizados que você já pode ter para que eles possam ser gerenciados pelo Microsoft Managed desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1ad83dbf323e431e1694b408e09e581ff5b76348
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279555"
---
# <a name="register-existing-devices-yourself"></a><span data-ttu-id="b7d60-103">Registre dispositivos existentes por conta própria</span><span class="sxs-lookup"><span data-stu-id="b7d60-103">Register existing devices yourself</span></span>

>[!NOTE]
><span data-ttu-id="b7d60-104">Este tópico descreve as etapas para reutilizar os dispositivos que você já tem e registrá-los na área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7d60-104">This topic describes the steps for you to re-use devices you already have and register them in Microsoft Managed Desktop.</span></span> <span data-ttu-id="b7d60-105">Se você estiver trabalhando com dispositivos novos, siga as etapas em [registrar novos dispositivos na área de trabalho gerenciada da Microsoft](register-devices-self.md) em seu lugar.</span><span class="sxs-lookup"><span data-stu-id="b7d60-105">If you are working with brand-new devices, follow the steps in [Register new devices in Microsoft Managed Desktop yourself](register-devices-self.md) instead.</span></span>

<span data-ttu-id="b7d60-106">O processo para parceiros está documentado em [etapas para que os parceiros registrem dispositivos](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="b7d60-106">The process for Partners is documented in [Steps for Partners to register devices](register-devices-partner.md).</span></span>

<span data-ttu-id="b7d60-107">A área de trabalho gerenciada da Microsoft pode funcionar com dispositivos novos ou você pode reutilizar os dispositivos que você já tem (o que exigirá que você os Insira novamente).</span><span class="sxs-lookup"><span data-stu-id="b7d60-107">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="b7d60-108">Você pode registrar dispositivos com a área de trabalho gerenciada da Microsoft no portal do Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="b7d60-108">You can register devices with Microsoft Managed Desktop in the Microsoft Endpoint Manager portal.</span></span>

## <a name="prepare-to-register-existing-devices"></a><span data-ttu-id="b7d60-109">Preparar-se para registrar dispositivos existentes</span><span class="sxs-lookup"><span data-stu-id="b7d60-109">Prepare to register existing devices</span></span>


<span data-ttu-id="b7d60-110">Para registrar dispositivos existentes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7d60-110">To register existing devices, follow these steps:</span></span>

1. [<span data-ttu-id="b7d60-111">Obtenha o hash de hardware para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7d60-111">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="b7d60-112">Mesclar os dados de hash</span><span class="sxs-lookup"><span data-stu-id="b7d60-112">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="b7d60-113">[Registre os dispositivos na área de trabalho gerenciada da Microsoft](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="b7d60-113">[Register the devices in Microsoft Managed Desktop](#register-devices-by-using-the-admin-portal).</span></span>
4. [<span data-ttu-id="b7d60-114">Verifique se a imagem está correta.</span><span class="sxs-lookup"><span data-stu-id="b7d60-114">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="b7d60-115">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7d60-115">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="b7d60-116">Obter o hash de hardware</span><span class="sxs-lookup"><span data-stu-id="b7d60-116">Obtain the hardware hash</span></span>

<span data-ttu-id="b7d60-117">A área de trabalho gerenciada da Microsoft identifica cada dispositivo exclusivamente fazendo referência a seu hash de hardware.</span><span class="sxs-lookup"><span data-stu-id="b7d60-117">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="b7d60-118">Você tem quatro opções para obter essas informações de dispositivos que você já está usando:</span><span class="sxs-lookup"><span data-stu-id="b7d60-118">You have four options for getting this information from devices you're already using:</span></span>

- <span data-ttu-id="b7d60-119">Pergunte ao seu fornecedor de OEM o arquivo de registro do piloto automático, que inclui os hashes de hardware.</span><span class="sxs-lookup"><span data-stu-id="b7d60-119">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="b7d60-120">Coletar informações no [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span><span class="sxs-lookup"><span data-stu-id="b7d60-120">Collect information in [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager).</span></span>
- <span data-ttu-id="b7d60-121">Executar um script do Windows PowerShell, usando o [Active Directory](#active-directory-powershell-script-method) ou [manualmente](#manual-powershell-script-method) em cada dispositivo, e coletar os resultados em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7d60-121">Run a Windows PowerShell script--either by using [Active Directory](#active-directory-powershell-script-method) or [manually](#manual-powershell-script-method) on each device--and collect the results in a file.</span></span>
- <span data-ttu-id="b7d60-122">Inicie cada dispositivo, mas não conclua a experiência de instalação do Windows, e [colete os hashes em uma unidade flash removível](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="b7d60-122">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="b7d60-123">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="b7d60-123">Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="b7d60-124">Você pode usar o Microsoft Endpoint Configuration Manager para coletar os hashes de hardware de dispositivos existentes que você deseja registrar com a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7d60-124">You can use Microsoft Endpoint Configuration Manager to collect the hardware hashes from existing devices that you want to register with Microsoft Managed Desktop.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7d60-125">Todos os dispositivos para os quais você deseja obter essas informações devem estar executando o Windows 10, versão 1703 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b7d60-125">Any devices you want to get this information for must be running Windows 10, version 1703 or later.</span></span> 

<span data-ttu-id="b7d60-126">Se você atendeu a todos esses pré-requisitos, você está pronto para coletar as informações seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7d60-126">If you've met all these prerequisites, you're ready to collect the information by following these steps:</span></span>

1. <span data-ttu-id="b7d60-127">No console do Gerenciador de configurações, selecione **monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-127">In the Configuration Manager console, select **Monitoring**.</span></span> 
2. <span data-ttu-id="b7d60-128">No espaço de trabalho monitoramento, expanda o nó **relatórios** , expanda **relatórios**e selecione o nó **hardware-geral** .</span><span class="sxs-lookup"><span data-stu-id="b7d60-128">In the Monitoring workspace, expand the **Reporting** node, expand **Reports**, and select the **Hardware - General** node.</span></span> 
3. <span data-ttu-id="b7d60-129">Execute o relatório, **as informações do dispositivo piloto automático do Windows**e exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="b7d60-129">Run the report, **Windows Autopilot Device Information**, and view the results.</span></span>
4. <span data-ttu-id="b7d60-130">No Visualizador de relatórios, selecione o ícone **Exportar** e escolha a opção **CSV (delimitado por vírgulas)** .</span><span class="sxs-lookup"><span data-stu-id="b7d60-130">In the report viewer, select the **Export** icon, and choose the **CSV (comma-delimited)** option.</span></span>
5. <span data-ttu-id="b7d60-131">Depois de salvar o arquivo, você precisará filtrar os resultados apenas para os dispositivos que pretende registrar na área de trabalho gerenciada da Microsoft e carregar os dados para a área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7d60-131">After saving the file, you will need to filter results to just those devices you plan to register with Microsoft Managed Desktop and upload the data to Microsoft Managed Desktop.</span></span> <span data-ttu-id="b7d60-132">Abra o Microsoft Endpoint Manager e navegue até o menu **dispositivos** e procure na seção Microsoft Managed desktop e selecione **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-132">Open Microsoft Endpoint Manager and navigate to the **Devices** menu, then look for Microsoft Managed Desktop section and select **Devices**.</span></span> <span data-ttu-id="b7d60-133">Selecione **+ registrar dispositivos** que abrem um surgimento para registrar novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-133">Select **+ Register devices** which opens a fly-in to register new devices.</span></span>


<span data-ttu-id="b7d60-134">Consulte [registrar dispositivos usando o portal de administração](#register-devices-by-using-the-admin-portal) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b7d60-134">Refer to [Register devices by using the Admin Portal](#register-devices-by-using-the-admin-portal) for more information.</span></span>


#### <a name="active-directory-powershell-script-method"></a><span data-ttu-id="b7d60-135">Método de script do PowerShell do Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7d60-135">Active Directory PowerShell script method</span></span>

<span data-ttu-id="b7d60-136">Em um ambiente do Active Directory, você pode usar o `Get-WindowsAutoPilotInfo` cmdlet do PowerShell para coletar remotamente as informações de dispositivos nos grupos do Active Directory usando o WinRM.</span><span class="sxs-lookup"><span data-stu-id="b7d60-136">In an Active Directory environment, you can use the `Get-WindowsAutoPilotInfo` PowerShell cmdlet to remotely collect the information from devices in Active Directory Groups by using WinRM.</span></span> <span data-ttu-id="b7d60-137">Você também pode usar o `Get-AD Computer` cmdlet e obter resultados filtrados para um determinado nome de modelo de hardware incluído no catálogo.</span><span class="sxs-lookup"><span data-stu-id="b7d60-137">You can also use the `Get-AD Computer` cmdlet and get filtered results for a specific hardware model names included in the catalog.</span></span> <span data-ttu-id="b7d60-138">Para fazer isso, primeiro confirme esses pré-requisitos e prossiga com as etapas:</span><span class="sxs-lookup"><span data-stu-id="b7d60-138">To do this, first confirm these prerequisites, and then proceed with the steps:</span></span>

- <span data-ttu-id="b7d60-139">O WinRM está habilitado.</span><span class="sxs-lookup"><span data-stu-id="b7d60-139">WinRM is enabled.</span></span>
- <span data-ttu-id="b7d60-140">Os dispositivos que você deseja registrar estão ativos na rede (ou seja, eles não são desconectados ou desativados).</span><span class="sxs-lookup"><span data-stu-id="b7d60-140">The devices you want to register are active on the network (that is, they are not disconnected or turned off).</span></span>
- <span data-ttu-id="b7d60-141">Verifique se você tem um parâmetro de credencial de domínio que tenha permissão para executar remotamente nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-141">Make sure you have a domain credential parameter that has permission to execute remotely on the devices.</span></span>
- <span data-ttu-id="b7d60-142">Verifique se o Firewall do Windows permite acesso ao WMI.</span><span class="sxs-lookup"><span data-stu-id="b7d60-142">Make sure that Windows Firewall allows access to WMI.</span></span> <span data-ttu-id="b7d60-143">Para fazer isso, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7d60-143">To do that, follow these steps:</span></span>

    1. <span data-ttu-id="b7d60-144">Abra o painel de controle do **Windows Defender firewall** e selecione **permitir um aplicativo ou recurso por meio do Windows Defender firewall**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-144">Open the **Windows Defender Firewall** control panel and select **Allow an app or feature through Windows Defender Firewall**.</span></span>
    
    2. <span data-ttu-id="b7d60-145">Encontre **Instrumentação de gerenciamento do Windows (WMI)** na lista, habilite para **privado e público**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-145">Find **Windows Management Instrumentation (WMI)** in the list, enable for both **Private and Public**, and then select **OK**.</span></span>

1.  <span data-ttu-id="b7d60-146">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-146">Open a PowerShell prompt with administrative rights.</span></span>

2.  <span data-ttu-id="b7d60-147">Execute *um* destes scripts:</span><span class="sxs-lookup"><span data-stu-id="b7d60-147">Run *either one* of these scripts:</span></span>

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. <span data-ttu-id="b7d60-148">Acessar os diretórios em que pode haver entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-148">Access any directories where there might be entries for the devices.</span></span> <span data-ttu-id="b7d60-149">Remova as entradas de cada dispositivo de *todos os* diretórios, incluindo os serviços de domínio do Active Directory do Windows Server e o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7d60-149">Remove entries for each device from *all* directories, including Windows Server Active Directory Domain Services and Azure Active Directory.</span></span> <span data-ttu-id="b7d60-150">Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.</span><span class="sxs-lookup"><span data-stu-id="b7d60-150">Be aware that this removal could take a few hours to completely process.</span></span>

4. <span data-ttu-id="b7d60-151">Serviços de gerenciamento de acesso onde podem existir entradas para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-151">Access management services where there might be entries for the devices.</span></span> <span data-ttu-id="b7d60-152">Remova as entradas de cada dispositivo de *todos os* serviços de gerenciamento, incluindo o Microsoft Endpoint Configuration Manager, o Microsoft Intune e o Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="b7d60-152">Remove entries for each device from *all* management services, including Microsoft Endpoint Configuration Manager, Microsoft Intune, and Windows Autopilot.</span></span> <span data-ttu-id="b7d60-153">Lembre-se de que essa remoção pode levar algumas horas para ser completamente processada.</span><span class="sxs-lookup"><span data-stu-id="b7d60-153">Be aware that this removal could take a few hours to completely process.</span></span>

<span data-ttu-id="b7d60-154">Agora você pode prosseguir para [registrar dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="b7d60-154">Now you can proceed to [register devices](#register-devices-by-using-the-admin-portal).</span></span>

#### <a name="manual-powershell-script-method"></a><span data-ttu-id="b7d60-155">Método de script do PowerShell manual</span><span class="sxs-lookup"><span data-stu-id="b7d60-155">Manual PowerShell script method</span></span>

1.  <span data-ttu-id="b7d60-156">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-156">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="b7d60-157">Sejam `Install-Script -Name Get-WindowsAutoPilotInfo`</span><span class="sxs-lookup"><span data-stu-id="b7d60-157">Run `Install-Script -Name Get-WindowsAutoPilotInfo`</span></span>
3.  <span data-ttu-id="b7d60-158">Sejam `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="b7d60-158">Run `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
4. [<span data-ttu-id="b7d60-159">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="b7d60-159">Merge the hash data.</span></span>](#merge-hash-data)

#### <a name="flash-drive-method"></a><span data-ttu-id="b7d60-160">Método de unidade flash</span><span class="sxs-lookup"><span data-stu-id="b7d60-160">Flash drive method</span></span>

1. <span data-ttu-id="b7d60-161">Em um dispositivo diferente daquele que você está registrando, insira uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="b7d60-161">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="b7d60-162">Abra um prompt do PowerShell com direitos administrativos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-162">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="b7d60-163">Sejam `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="b7d60-163">Run `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="b7d60-164">Ative o dispositivo que você está registrando, mas *não inicie a experiência de instalação*.</span><span class="sxs-lookup"><span data-stu-id="b7d60-164">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="b7d60-165">Se você iniciar acidentalmente a experiência de instalação, será necessário redefinir ou recriar a imagem do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7d60-165">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="b7d60-166">Insira a unidade USB e, em seguida, pressione SHIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="b7d60-166">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="b7d60-167">Abra um prompt do PowerShell com direitos administrativos e, em seguida, execute `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="b7d60-167">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="b7d60-168">Sejam `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="b7d60-168">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="b7d60-169">Sejam `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="b7d60-169">Run `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="b7d60-170">Remova a unidade USB e desligue o dispositivo executando `shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="b7d60-170">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>
10. [<span data-ttu-id="b7d60-171">Mesclar os dados de hash.</span><span class="sxs-lookup"><span data-stu-id="b7d60-171">Merge the hash data.</span></span>](#merge-hash-data)

>[!IMPORTANT]
><span data-ttu-id="b7d60-172">Não ligue o dispositivo que você está registrando novamente até concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="b7d60-172">Do not power on the device you are registering again until you've completed registration for it.</span></span> 



### <a name="merge-hash-data"></a><span data-ttu-id="b7d60-173">Mesclar dados de hash</span><span class="sxs-lookup"><span data-stu-id="b7d60-173">Merge hash data</span></span>

<span data-ttu-id="b7d60-174">Se você coletou os dados de hash de hardware pelos métodos manuais do PowerShell ou unidade flash, agora precisará ter os dados nos arquivos CSV combinados em um único arquivo para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="b7d60-174">If you collected the hardware hash data by the manual PowerShell or flash drive methods, you now need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="b7d60-175">Veja um exemplo de script do PowerShell para facilitar:</span><span class="sxs-lookup"><span data-stu-id="b7d60-175">Here's a sample PowerShell script to make this easy:</span></span>

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

<span data-ttu-id="b7d60-176">Com os dados de hash mesclados em um arquivo CSV, agora você pode prosseguir para [registrar os dispositivos](#register-devices-by-using-the-admin-portal).</span><span class="sxs-lookup"><span data-stu-id="b7d60-176">With the hash data merged into one CSV file, you can now proceed to [register the devices](#register-devices-by-using-the-admin-portal).</span></span>


#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="b7d60-177">Registrar dispositivos usando o portal de administração</span><span class="sxs-lookup"><span data-stu-id="b7d60-177">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="b7d60-178">No [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), selecione **dispositivos** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="b7d60-178">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="b7d60-179">Procure a seção área de trabalho gerenciada da Microsoft do menu e selecione **dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-179">Look for the Microsoft Managed Desktop section of the menu and select **Devices**.</span></span> <span data-ttu-id="b7d60-180">No espaço de trabalho dispositivos de área de trabalho gerenciada da Microsoft, selecione **+ registrar dispositivos** que abrem um surgimento para registrar novos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-180">In the Microsoft Managed Desktop Devices workspace, Select **+ Register devices** which opens a fly-in to register new devices.</span></span>

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="b7d60-181">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b7d60-181">Follow these steps:</span></span>

1. <span data-ttu-id="b7d60-182">Em **upload de arquivo**, forneça um caminho para o arquivo CSV que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b7d60-182">In **File upload**, provide a path to the CSV file you created previously.</span></span>

1. <span data-ttu-id="b7d60-183">Selecione **registrar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-183">Select **Register devices**.</span></span> <span data-ttu-id="b7d60-184">O sistema adicionará os dispositivos à sua lista de dispositivos na **lâmina de dispositivos**, marcada como **registro pendente**.</span><span class="sxs-lookup"><span data-stu-id="b7d60-184">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="b7d60-185">O registro geralmente leva menos de 10 minutos e, quando bem-sucedido, o dispositivo aparecerá como **pronto para o usuário** , o que significa que ele está pronto e esperando que um usuário comece a usar o.</span><span class="sxs-lookup"><span data-stu-id="b7d60-185">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for a user to start using.</span></span>


<span data-ttu-id="b7d60-186">Você pode monitorar o progresso do registro de dispositivo na página principal.</span><span class="sxs-lookup"><span data-stu-id="b7d60-186">You can monitor the progress of device registration on the main page.</span></span> <span data-ttu-id="b7d60-187">Os Estados possíveis relatados incluem:</span><span class="sxs-lookup"><span data-stu-id="b7d60-187">Possible states reported there include:</span></span>

| <span data-ttu-id="b7d60-188">Estado</span><span class="sxs-lookup"><span data-stu-id="b7d60-188">State</span></span> | <span data-ttu-id="b7d60-189">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7d60-189">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="b7d60-190">Registro pendente</span><span class="sxs-lookup"><span data-stu-id="b7d60-190">Registration Pending</span></span> | <span data-ttu-id="b7d60-191">O registro ainda não foi feito.</span><span class="sxs-lookup"><span data-stu-id="b7d60-191">Registration is not done yet.</span></span> <span data-ttu-id="b7d60-192">Verifique novamente mais tarde.</span><span class="sxs-lookup"><span data-stu-id="b7d60-192">Check back later.</span></span> |
| <span data-ttu-id="b7d60-193">Falha no registro</span><span class="sxs-lookup"><span data-stu-id="b7d60-193">Registration failed</span></span> | <span data-ttu-id="b7d60-194">Não foi possível concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="b7d60-194">Registration could not be completed.</span></span> <span data-ttu-id="b7d60-195">Consulte [Solucionando problemas de registro de dispositivo](#troubleshooting-device-registration) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b7d60-195">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="b7d60-196">Pronto para o usuário</span><span class="sxs-lookup"><span data-stu-id="b7d60-196">Ready for user</span></span> | <span data-ttu-id="b7d60-197">O registro foi bem-sucedido e o dispositivo agora está pronto para ser entregue ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b7d60-197">Registration succeeded and the device is now ready to be delivered to the user.</span></span> <span data-ttu-id="b7d60-198">A área de trabalho gerenciada da Microsoft irá orientá-lo pela primeira vez na configuração, portanto, não é necessário fazer mais preparativos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-198">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="b7d60-199">Ativo</span><span class="sxs-lookup"><span data-stu-id="b7d60-199">Active</span></span> | <span data-ttu-id="b7d60-200">O dispositivo foi entregue ao usuário e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b7d60-200">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="b7d60-201">Isso também indica que eles estão usando o dispositivo regularmente.</span><span class="sxs-lookup"><span data-stu-id="b7d60-201">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="b7d60-202">Inativa</span><span class="sxs-lookup"><span data-stu-id="b7d60-202">Inactive</span></span> | <span data-ttu-id="b7d60-203">O dispositivo foi entregue ao usuário e foi registrado com seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b7d60-203">The device has been delivered to the user and they have registered with your tenant.</span></span> <span data-ttu-id="b7d60-204">No entanto, eles não usaram o dispositivo recentemente (nos últimos 7 dias).</span><span class="sxs-lookup"><span data-stu-id="b7d60-204">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="b7d60-205">Solucionando problemas de registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7d60-205">Troubleshooting device registration</span></span>

| <span data-ttu-id="b7d60-206">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="b7d60-206">Error message</span></span> | <span data-ttu-id="b7d60-207">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b7d60-207">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="b7d60-208">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="b7d60-208">Device not found</span></span> | <span data-ttu-id="b7d60-209">Não foi possível registrar este dispositivo porque não foi possível encontrar uma correspondência para o fabricante, modelo ou número de série fornecido.</span><span class="sxs-lookup"><span data-stu-id="b7d60-209">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="b7d60-210">Confirme esses valores com seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-210">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="b7d60-211">Hash de hardware inválido</span><span class="sxs-lookup"><span data-stu-id="b7d60-211">Hardware hash not valid</span></span> | <span data-ttu-id="b7d60-212">O hash de hardware fornecido para este dispositivo não foi formatado corretamente.</span><span class="sxs-lookup"><span data-stu-id="b7d60-212">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="b7d60-213">Verifique novamente o hash de hardware e envie novamente.</span><span class="sxs-lookup"><span data-stu-id="b7d60-213">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="b7d60-214">Dispositivo já registrado</span><span class="sxs-lookup"><span data-stu-id="b7d60-214">Device already registered</span></span> | <span data-ttu-id="b7d60-215">Este dispositivo já está registrado na sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7d60-215">This device is already registered to your organization.</span></span> <span data-ttu-id="b7d60-216">Nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="b7d60-216">No further action required.</span></span> |
| <span data-ttu-id="b7d60-217">Dispositivo solicitado por outra organização</span><span class="sxs-lookup"><span data-stu-id="b7d60-217">Device claimed by another organization</span></span> | <span data-ttu-id="b7d60-218">Este dispositivo já foi reivindicado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="b7d60-218">This device has already been claimed by another organization.</span></span> <span data-ttu-id="b7d60-219">Consulte seu fornecedor de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7d60-219">Check with your device supplier.</span></span> |
| <span data-ttu-id="b7d60-220">Erro inesperado</span><span class="sxs-lookup"><span data-stu-id="b7d60-220">Unexpected error</span></span> | <span data-ttu-id="b7d60-221">Sua solicitação não pôde ser processada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b7d60-221">Your request could not be automatically processed.</span></span> <span data-ttu-id="b7d60-222">Entre em contato com o suporte e forneça a ID da solicitação: <requestId></span><span class="sxs-lookup"><span data-stu-id="b7d60-222">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="b7d60-223">Verificar a imagem</span><span class="sxs-lookup"><span data-stu-id="b7d60-223">Check the image</span></span>

<span data-ttu-id="b7d60-224">Se o seu dispositivo vier de um fornecedor de parceiros de área de trabalho gerenciada da Microsoft, a imagem deve estar correta.</span><span class="sxs-lookup"><span data-stu-id="b7d60-224">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="b7d60-225">Você também poderá aplicar a imagem sozinho, se preferir.</span><span class="sxs-lookup"><span data-stu-id="b7d60-225">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="b7d60-226">Para começar, entre em contato com o representante da Microsoft com o qual você está trabalhando e forneça o local e as etapas para a aplicação da imagem.</span><span class="sxs-lookup"><span data-stu-id="b7d60-226">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="b7d60-227">Entregar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7d60-227">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7d60-228">Antes de entregar o dispositivo ao usuário, verifique se você obteve e aplicou as [licenças apropriadas](../get-ready/prerequisites.md) para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="b7d60-228">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="b7d60-229">Se todas as licenças forem aplicadas, você poderá preparar [seus usuários para usar dispositivos](get-started-devices.md)e o usuário poderá iniciar o dispositivo e prosseguir com a experiência de instalação do Windows.</span><span class="sxs-lookup"><span data-stu-id="b7d60-229">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>









