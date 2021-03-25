---
title: Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)
description: Implante o pacote de configuração no dispositivo VDI (infraestrutura de área de trabalho virtual) para que eles sejam integrados ao serviço do Microsoft Defender ATP.
keywords: configurar dispositivo VDI (infraestrutura de área de trabalho virtual), vdi, gerenciamento de dispositivos, configurar pontos de extremidade do Windows ATP, configurar o Microsoft Defender para pontos de extremidade do ponto de extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 167db9b5da841528e95f167b3af6a840b6c71eb4
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165556"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e3836-104">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e3836-104">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e3836-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e3836-105">**Applies to:**</span></span>
- [<span data-ttu-id="e3836-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e3836-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e3836-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e3836-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="e3836-108">Dispositivos VDI (infraestrutura de área de trabalho virtual)</span><span class="sxs-lookup"><span data-stu-id="e3836-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="e3836-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="e3836-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="e3836-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e3836-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e3836-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e3836-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="e3836-112">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="e3836-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="e3836-113">O Defender para Ponto de Extremidade dá suporte à integração de sessão VDI não persistente.</span><span class="sxs-lookup"><span data-stu-id="e3836-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="e3836-114">Pode haver desafios associados ao integração de VDIs.</span><span class="sxs-lookup"><span data-stu-id="e3836-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="e3836-115">Veja a seguir os desafios típicos para este cenário:</span><span class="sxs-lookup"><span data-stu-id="e3836-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="e3836-116">Integração instantânea inicial de uma sessão de curta duração, que deve ser integrada ao Defender para o Ponto de Extremidade antes do provisionamento real.</span><span class="sxs-lookup"><span data-stu-id="e3836-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="e3836-117">O nome do dispositivo normalmente é reutilizável para novas sessões.</span><span class="sxs-lookup"><span data-stu-id="e3836-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="e3836-118">Dispositivos VDI podem aparecer no portal do Defender para Ponto de Extremidade como:</span><span class="sxs-lookup"><span data-stu-id="e3836-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="e3836-119">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3836-119">Single entry for each device.</span></span>  
<span data-ttu-id="e3836-120">Observe que, nesse caso, *o* mesmo nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônoma.</span><span class="sxs-lookup"><span data-stu-id="e3836-120">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="e3836-121">Várias entradas para cada dispositivo - uma para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="e3836-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="e3836-122">As etapas a seguir orientarão você através da integração de dispositivos VDI e destacarão etapas para entradas simples e múltiplas.</span><span class="sxs-lookup"><span data-stu-id="e3836-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="e3836-123">Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode atrasar a integração do sensor Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e3836-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="e3836-124">Para Windows 10 ou Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="e3836-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="e3836-125">Abra o arquivo .zip do pacote de configuração da VDI *(WindowsDefenderATPOnboardingPackage.zip*) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="e3836-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="e3836-126">Você também pode obter o pacote do [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/):</span><span class="sxs-lookup"><span data-stu-id="e3836-126">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1.  <span data-ttu-id="e3836-127">No painel de navegação, selecione **Configurações**  >  **Integração**.</span><span class="sxs-lookup"><span data-stu-id="e3836-127">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="e3836-128">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e3836-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="e3836-129">No campo **Método de implantação,** selecione scripts de **integração VDI para pontos de extremidade** não persistentes .</span><span class="sxs-lookup"><span data-stu-id="e3836-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="e3836-130">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="e3836-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="e3836-131">Copie os arquivos da pasta WindowsDefenderATPOnboardingPackage extraída do arquivo .zip para a imagem `golden/master` sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="e3836-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="e3836-132">Se você não estiver implementando uma única entrada para cada dispositivo, copie WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e3836-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="e3836-133">Se você estiver implementando uma única entrada para cada dispositivo, copie o Onboard-NonPersistentMachine.ps1 e WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="e3836-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3836-134">Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta.</span><span class="sxs-lookup"><span data-stu-id="e3836-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="e3836-135">Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="e3836-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="e3836-136">Abra uma janela Editor de Política de Grupo Local e navegue até **Configuração** do  >  **Computador Configuração** do Windows  >  **Scripts**  >  **Inicialização**.</span><span class="sxs-lookup"><span data-stu-id="e3836-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e3836-137">A Política de Grupo de Domínio também pode ser usada para a integração de dispositivos VDI não persistentes.</span><span class="sxs-lookup"><span data-stu-id="e3836-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="e3836-138">Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:</span><span class="sxs-lookup"><span data-stu-id="e3836-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span> <br>
   <span data-ttu-id="e3836-139">**Para entrada única para cada dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="e3836-139">**For single entry for each device**:</span></span><br>
   
   <span data-ttu-id="e3836-140">Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="e3836-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e3836-141">Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração.</span><span class="sxs-lookup"><span data-stu-id="e3836-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="e3836-142">**Para várias entradas para cada dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="e3836-142">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="e3836-143">Selecione a **guia Scripts** e clique em **Adicionar** (o Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="e3836-143">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="e3836-144">Navegue até o script bash de `WindowsDefenderATPOnboardingScript.cmd` integração.</span><span class="sxs-lookup"><span data-stu-id="e3836-144">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="e3836-145">Teste sua solução:</span><span class="sxs-lookup"><span data-stu-id="e3836-145">Test your solution:</span></span>

   1. <span data-ttu-id="e3836-146">Crie um pool com um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3836-146">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="e3836-147">Logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3836-147">Logon to device.</span></span>
      
   1. <span data-ttu-id="e3836-148">Logoff do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3836-148">Logoff from device.</span></span>

   1. <span data-ttu-id="e3836-149">Fazer logon no dispositivo com outro usuário.</span><span class="sxs-lookup"><span data-stu-id="e3836-149">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="e3836-150">**Para entrada única para cada dispositivo**: Verifique apenas uma entrada no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e3836-150">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="e3836-151">**Para várias entradas para cada dispositivo**: Verifique várias entradas no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e3836-151">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="e3836-152">Clique **na lista Dispositivos** no painel De navegação.</span><span class="sxs-lookup"><span data-stu-id="e3836-152">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="e3836-153">Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo como** tipo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e3836-153">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="e3836-154">Para SKUs de nível baixo</span><span class="sxs-lookup"><span data-stu-id="e3836-154">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="e3836-155">O registro a seguir é relevante somente quando o objetivo é alcançar uma "Entrada única para cada dispositivo".</span><span class="sxs-lookup"><span data-stu-id="e3836-155">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="e3836-156">De definir o valor do Registro como:</span><span class="sxs-lookup"><span data-stu-id="e3836-156">Set registry value to:</span></span>

    ```reg
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="e3836-157">ou usando a linha de comando:</span><span class="sxs-lookup"><span data-stu-id="e3836-157">or using command line:</span></span>

    ```
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="e3836-158">Siga o [processo de integração do servidor](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="e3836-158">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="e3836-159">Atualizando imagens VDI (infraestrutura de área de trabalho virtual não persistente)</span><span class="sxs-lookup"><span data-stu-id="e3836-159">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="e3836-160">Como prática prática, recomendamos usar ferramentas de manutenção offline para corrigir imagens douradas/mestras.</span><span class="sxs-lookup"><span data-stu-id="e3836-160">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="e3836-161">Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:</span><span class="sxs-lookup"><span data-stu-id="e3836-161">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="e3836-162">Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:</span><span class="sxs-lookup"><span data-stu-id="e3836-162">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="e3836-163">Modificar uma imagem do Windows usando o DISM</span><span class="sxs-lookup"><span data-stu-id="e3836-163">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="e3836-164">Opções de gerenciamento de imagens Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="e3836-164">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="e3836-165">Reduzir o tamanho do Armazenamento de Componentes em uma imagem offline do Windows</span><span class="sxs-lookup"><span data-stu-id="e3836-165">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="e3836-166">Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:</span><span class="sxs-lookup"><span data-stu-id="e3836-166">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="e3836-167">Depois de inicializar a imagem mestra para manutenção ou correção online, execute um script de offboard para desativar o sensor Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e3836-167">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="e3836-168">Para obter mais informações, consulte [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="e3836-168">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="e3836-169">Verifique se o sensor é interrompido executando o comando abaixo em uma janela CMD:</span><span class="sxs-lookup"><span data-stu-id="e3836-169">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="e3836-170">Service the image as needed.</span><span class="sxs-lookup"><span data-stu-id="e3836-170">Service the image as needed.</span></span>

4. <span data-ttu-id="e3836-171">Execute os comandos abaixo usando PsExec.exe (que podem ser baixados para limpar o conteúdo da pasta cibernética que o sensor pode ter acumulado desde https://download.sysinternals.com/files/PSTools.zip) a inicialização:</span><span class="sxs-lookup"><span data-stu-id="e3836-171">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="e3836-172">Sele a imagem dourada/mestra como normalmente faria.</span><span class="sxs-lookup"><span data-stu-id="e3836-172">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e3836-173">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e3836-173">Related topics</span></span>
- [<span data-ttu-id="e3836-174">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="e3836-174">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="e3836-175">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e3836-175">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="e3836-176">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="e3836-176">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="e3836-177">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="e3836-177">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="e3836-178">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="e3836-178">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)