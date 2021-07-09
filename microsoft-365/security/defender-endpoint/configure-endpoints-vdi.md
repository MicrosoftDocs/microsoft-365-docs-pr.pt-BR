---
title: Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)
description: Implante o pacote de configuração no dispositivo VDI (infraestrutura de área de trabalho virtual) para que eles sejam integrados ao serviço do Microsoft Defender para Ponto de Extremidade.
keywords: configurar dispositivo VDI (infraestrutura de área de trabalho virtual), vdi, gerenciamento de dispositivos, configurar o Microsoft Defender para Ponto de Extremidade, pontos de extremidade
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
ms.openlocfilehash: 555f96dc1f45fb6a406b5993d0b8e4a3745c283b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339629"
---
# <a name="onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="4c400-104">Integrando os dispositivos VDI (infraestrutura de área de trabalho virtual não persistente)</span><span class="sxs-lookup"><span data-stu-id="4c400-104">Onboard the non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4c400-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4c400-105">**Applies to:**</span></span>
- [<span data-ttu-id="4c400-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4c400-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4c400-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4c400-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="4c400-108">Dispositivos VDI (infraestrutura de área de trabalho virtual)</span><span class="sxs-lookup"><span data-stu-id="4c400-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="4c400-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="4c400-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="4c400-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4c400-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4c400-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4c400-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="4c400-112">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="4c400-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="4c400-113">O Defender para Ponto de Extremidade dá suporte à integração de sessão VDI não persistente.</span><span class="sxs-lookup"><span data-stu-id="4c400-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="4c400-114">Pode haver desafios associados ao integração de VDIs.</span><span class="sxs-lookup"><span data-stu-id="4c400-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="4c400-115">Veja a seguir os desafios típicos para este cenário:</span><span class="sxs-lookup"><span data-stu-id="4c400-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="4c400-116">Integração instantânea inicial de uma sessão de curta duração, que deve ser integrada ao Defender para o Ponto de Extremidade antes do provisionamento real.</span><span class="sxs-lookup"><span data-stu-id="4c400-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="4c400-117">O nome do dispositivo normalmente é reutilizável para novas sessões.</span><span class="sxs-lookup"><span data-stu-id="4c400-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="4c400-118">Dispositivos VDI podem aparecer no portal do Defender para Ponto de Extremidade como:</span><span class="sxs-lookup"><span data-stu-id="4c400-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="4c400-119">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c400-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="4c400-120">Nesse caso, o *mesmo nome* de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônoma.</span><span class="sxs-lookup"><span data-stu-id="4c400-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="4c400-121">Várias entradas para cada dispositivo - uma para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="4c400-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="4c400-122">As etapas a seguir orientarão você através da integração de dispositivos VDI e destacarão etapas para entradas simples e múltiplas.</span><span class="sxs-lookup"><span data-stu-id="4c400-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="4c400-123">Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode atrasar a integração do sensor Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4c400-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="4c400-124">Para Windows 10 ou Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4c400-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="4c400-125">Abra o arquivo de pacote de configuração .zip *VDI*(WindowsDefenderATPOnboardingPackage.zip) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="4c400-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="4c400-126">Você também pode obter o pacote do [Microsoft 365 Defender portal](https://security.microsoft.com/):</span><span class="sxs-lookup"><span data-stu-id="4c400-126">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="4c400-127">No painel de navegação, **selecione** Configurações  >  **Endpoints Gerenciamento** de  >    >  **dispositivos Integrando**.</span><span class="sxs-lookup"><span data-stu-id="4c400-127">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

    1. <span data-ttu-id="4c400-128">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4c400-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="4c400-129">No campo **Método de implantação,** selecione scripts de **integração VDI para pontos de extremidade** não persistentes .</span><span class="sxs-lookup"><span data-stu-id="4c400-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="4c400-130">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c400-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="4c400-131">Copie os arquivos da pasta WindowsDefenderATPOnboardingPackage extraída do arquivo .zip para a imagem `golden/master` sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="4c400-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="4c400-132">Se você não estiver implementando uma única entrada para cada dispositivo, copie WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="4c400-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="4c400-133">Se você estiver implementando uma única entrada para cada dispositivo, copie o Onboard-NonPersistentMachine.ps1 e WindowsDefenderATPOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="4c400-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c400-134">Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta.</span><span class="sxs-lookup"><span data-stu-id="4c400-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="4c400-135">Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="4c400-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="4c400-136">Abra uma janela Editor de Política de Grupo Local e navegue até **Configuração** do  >  **Computador Windows Configurações**  >  **Inicialização de**  >  **Scripts**.</span><span class="sxs-lookup"><span data-stu-id="4c400-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4c400-137">A Política de Grupo de Domínio também pode ser usada para a integração de dispositivos VDI não persistentes.</span><span class="sxs-lookup"><span data-stu-id="4c400-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="4c400-138">Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:</span><span class="sxs-lookup"><span data-stu-id="4c400-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="4c400-139">Para entrada única para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4c400-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="4c400-140">Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="4c400-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="4c400-141">Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração.</span><span class="sxs-lookup"><span data-stu-id="4c400-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="4c400-142">Não é necessário especificar o outro arquivo, pois ele será disparado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4c400-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="4c400-143">Para várias entradas para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4c400-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="4c400-144">Selecione a **guia Scripts** e clique em **Adicionar** (Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="4c400-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="4c400-145">Navegue até o script bash de `WindowsDefenderATPOnboardingScript.cmd` integração.</span><span class="sxs-lookup"><span data-stu-id="4c400-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="4c400-146">Teste sua solução:</span><span class="sxs-lookup"><span data-stu-id="4c400-146">Test your solution:</span></span>

   1. <span data-ttu-id="4c400-147">Crie um pool com um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c400-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="4c400-148">Logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c400-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="4c400-149">Logoff do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c400-149">Logoff from device.</span></span>

   1. <span data-ttu-id="4c400-150">Fazer logon no dispositivo com outro usuário.</span><span class="sxs-lookup"><span data-stu-id="4c400-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="4c400-151">Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:</span><span class="sxs-lookup"><span data-stu-id="4c400-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="4c400-152">Para entrada única para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4c400-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="4c400-153">Verifique apenas uma entrada no Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="4c400-153">Check only one entry in Microsoft 365 Defender portal.</span></span>

      - <span data-ttu-id="4c400-154">Para várias entradas para cada dispositivo:</span><span class="sxs-lookup"><span data-stu-id="4c400-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="4c400-155">Verifique várias entradas no Microsoft 365 Defender portal.</span><span class="sxs-lookup"><span data-stu-id="4c400-155">Check multiple entries in Microsoft 365 Defender portal.</span></span>

6. <span data-ttu-id="4c400-156">Clique **na lista Dispositivos** no painel De navegação.</span><span class="sxs-lookup"><span data-stu-id="4c400-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="4c400-157">Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo como** tipo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4c400-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="4c400-158">Para SKUs de nível baixo</span><span class="sxs-lookup"><span data-stu-id="4c400-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="4c400-159">O registro a seguir é relevante somente quando o objetivo é alcançar uma "Entrada única para cada dispositivo".</span><span class="sxs-lookup"><span data-stu-id="4c400-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="4c400-160">De definir o valor do Registro como:</span><span class="sxs-lookup"><span data-stu-id="4c400-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="4c400-161">ou usando a linha de comando:</span><span class="sxs-lookup"><span data-stu-id="4c400-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="4c400-162">Siga o [processo de integração do servidor](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="4c400-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="4c400-163">Atualizando imagens VDI (infraestrutura de área de trabalho virtual não persistente)</span><span class="sxs-lookup"><span data-stu-id="4c400-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="4c400-164">Como prática prática, recomendamos usar ferramentas de manutenção offline para corrigir imagens douradas/mestras.</span><span class="sxs-lookup"><span data-stu-id="4c400-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="4c400-165">Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:</span><span class="sxs-lookup"><span data-stu-id="4c400-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="4c400-166">Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:</span><span class="sxs-lookup"><span data-stu-id="4c400-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="4c400-167">Modificar uma Windows usando DISM</span><span class="sxs-lookup"><span data-stu-id="4c400-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="4c400-168">Opções de gerenciamento de imagens Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="4c400-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="4c400-169">Reduzir o tamanho do Armazenamento de Componentes em uma imagem Windows Offline</span><span class="sxs-lookup"><span data-stu-id="4c400-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="4c400-170">Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:</span><span class="sxs-lookup"><span data-stu-id="4c400-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="4c400-171">Depois de inicializar a imagem mestra para manutenção ou correção online, execute um script de offboard para desativar o sensor Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4c400-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="4c400-172">Para obter mais informações, consulte [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="4c400-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="4c400-173">Verifique se o sensor é interrompido executando o comando abaixo em uma janela CMD:</span><span class="sxs-lookup"><span data-stu-id="4c400-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="4c400-174">Service the image as needed.</span><span class="sxs-lookup"><span data-stu-id="4c400-174">Service the image as needed.</span></span>

4. <span data-ttu-id="4c400-175">Execute os comandos abaixo usando PsExec.exe (que podem ser baixados para limpar o conteúdo da pasta cibernética que o sensor pode ter acumulado desde https://download.sysinternals.com/files/PSTools.zip) a inicialização:</span><span class="sxs-lookup"><span data-stu-id="4c400-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="4c400-176">Sele a imagem dourada/mestra como normalmente faria.</span><span class="sxs-lookup"><span data-stu-id="4c400-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c400-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4c400-177">Related topics</span></span>
- [<span data-ttu-id="4c400-178">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="4c400-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="4c400-179">Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4c400-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="4c400-180">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="4c400-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="4c400-181">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="4c400-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="4c400-182">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="4c400-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
