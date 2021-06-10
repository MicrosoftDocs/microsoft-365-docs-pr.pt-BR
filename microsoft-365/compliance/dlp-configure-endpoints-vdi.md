---
title: Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Implante o pacote de configuração no dispositivo VDI (infraestrutura de área de trabalho virtual) para que eles sejam ingressados no serviço Microsoft 365 de prevenção contra perda de dados do ponto de extremidade.
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917947"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="fc143-103">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="fc143-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="fc143-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fc143-104">**Applies to:**</span></span>
- [<span data-ttu-id="fc143-105">Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)</span><span class="sxs-lookup"><span data-stu-id="fc143-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="fc143-106">Dispositivos VDI (infraestrutura de área de trabalho virtual)</span><span class="sxs-lookup"><span data-stu-id="fc143-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="fc143-107">Microsoft 365 O suporte à prevenção contra perda de dados do ponto de extremidade para Windows Virtual Desktop oferece suporte a cenários de sessão única.</span><span class="sxs-lookup"><span data-stu-id="fc143-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="fc143-108">Cenários de várias sessões Windows área de trabalho virtual não são suportados no momento.</span><span class="sxs-lookup"><span data-stu-id="fc143-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="fc143-109">Dispositivos VDI de integração</span><span class="sxs-lookup"><span data-stu-id="fc143-109">Onboard VDI devices</span></span>

<span data-ttu-id="fc143-110">Microsoft 365 A prevenção contra perda de dados do ponto de extremidade oferece suporte à integração de sessão VDI não persistente.</span><span class="sxs-lookup"><span data-stu-id="fc143-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="fc143-111">Para fazer a integração de sessões VDI não persistentes, os dispositivos VDI devem estar Windows 10 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="fc143-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="fc143-112">Pode haver desafios associados ao integração de VDIs.</span><span class="sxs-lookup"><span data-stu-id="fc143-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="fc143-113">Veja a seguir os desafios típicos para este cenário:</span><span class="sxs-lookup"><span data-stu-id="fc143-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="fc143-114">Integração instantânea inicial de uma sessão de curta duração, que deve ser integrada para Microsoft 365 prevenção contra perda de dados do Ponto de Extremidade antes do provisionamento real.</span><span class="sxs-lookup"><span data-stu-id="fc143-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="fc143-115">O nome do dispositivo normalmente é reutilizável para novas sessões.</span><span class="sxs-lookup"><span data-stu-id="fc143-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="fc143-116">Os dispositivos VDI podem aparecer no centro Microsoft 365 Conformidade como:</span><span class="sxs-lookup"><span data-stu-id="fc143-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="fc143-117">Entrada única para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc143-117">Single entry for each device.</span></span>  
<span data-ttu-id="fc143-118">Observe que, nesse caso, *o* mesmo nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônoma.</span><span class="sxs-lookup"><span data-stu-id="fc143-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="fc143-119">Várias entradas para cada dispositivo - uma para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="fc143-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="fc143-120">As etapas a seguir orientarão você através da integração de dispositivos VDI e destacarão etapas para entradas simples e múltiplas.</span><span class="sxs-lookup"><span data-stu-id="fc143-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="fc143-121">Para ambientes em que há configurações de baixo recurso, o procedimento de inicialização VDI pode atrasar a integração Microsoft 365 prevenção contra perda de dados do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="fc143-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="fc143-122">Abra o arquivo de pacote de configuração .zip *VDI*(DeviceCompliancePackage.zip) que você baixou do assistente de integração do serviço.</span><span class="sxs-lookup"><span data-stu-id="fc143-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="fc143-123">No painel de navegação, **selecione** Configurações  >  **Integração do**  >  **dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="fc143-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="fc143-124">No campo **Método de implantação,** selecione scripts de **integração VDI para pontos de extremidade** não persistentes .</span><span class="sxs-lookup"><span data-stu-id="fc143-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="fc143-125">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc143-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="fc143-126">Copie os arquivos da pasta DeviceCompliancePackage extraída do arquivo .zip para a imagem `golden/master` sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="fc143-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="fc143-127">Se você não estiver implementando uma única entrada para cada dispositivo, copie DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="fc143-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="fc143-128">Se você estiver implementando uma única entrada para cada dispositivo, copie o Onboard-NonPersistentMachine.ps1 e DeviceComplianceOnboardingScript.cmd.</span><span class="sxs-lookup"><span data-stu-id="fc143-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fc143-129">Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta.</span><span class="sxs-lookup"><span data-stu-id="fc143-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="fc143-130">Você precisará escolher a opção Mostrar arquivos **e pastas ocultos** no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc143-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="fc143-131">Abra uma janela Editor de Política de Grupo Local e navegue até **Configuração** do  >  **Computador Windows Configurações**  >  **Inicialização de**  >  **Scripts**.</span><span class="sxs-lookup"><span data-stu-id="fc143-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fc143-132">A Política de Grupo de Domínio também pode ser usada para a integração de dispositivos VDI não persistentes.</span><span class="sxs-lookup"><span data-stu-id="fc143-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="fc143-133">Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:</span><span class="sxs-lookup"><span data-stu-id="fc143-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="fc143-134">**Para entrada única para cada dispositivo**</span><span class="sxs-lookup"><span data-stu-id="fc143-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="fc143-135">Selecione a **guia Scripts** do PowerShell e clique em **Adicionar** (Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="fc143-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="fc143-136">Navegue até o script do PowerShell de `Onboard-NonPersistentMachine.ps1` integração.</span><span class="sxs-lookup"><span data-stu-id="fc143-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="fc143-137">**Para várias entradas para cada dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="fc143-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="fc143-138">Selecione a **guia Scripts** e clique em **Adicionar** (Windows Explorer abrirá diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="fc143-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="fc143-139">Navegue até o script bash de `DeviceComplianceOnboardingScript.cmd` integração.</span><span class="sxs-lookup"><span data-stu-id="fc143-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="fc143-140">Teste sua solução:</span><span class="sxs-lookup"><span data-stu-id="fc143-140">Test your solution:</span></span>

   1. <span data-ttu-id="fc143-141">Crie um pool com um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc143-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="fc143-142">Logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc143-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="fc143-143">Logoff do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fc143-143">Logoff from device.</span></span>

   1. <span data-ttu-id="fc143-144">Fazer logon no dispositivo com outro usuário.</span><span class="sxs-lookup"><span data-stu-id="fc143-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="fc143-145">**Para entrada única para cada dispositivo:** verifique apenas uma entrada no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="fc143-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="fc143-146">**Para várias entradas para cada dispositivo**: Verifique várias entradas no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="fc143-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="fc143-147">Clique **na lista Dispositivos** no painel De navegação.</span><span class="sxs-lookup"><span data-stu-id="fc143-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="fc143-148">Use a função de pesquisa inserindo o nome do dispositivo e selecione **Dispositivo como** tipo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc143-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="fc143-149">Atualizando imagens VDI (infraestrutura de área de trabalho virtual não persistente)</span><span class="sxs-lookup"><span data-stu-id="fc143-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="fc143-150">Como prática prática, recomendamos usar ferramentas de manutenção offline para corrigir imagens douradas/mestras.</span><span class="sxs-lookup"><span data-stu-id="fc143-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="fc143-151">Por exemplo, você pode usar os comandos abaixo para instalar uma atualização enquanto a imagem permanece offline:</span><span class="sxs-lookup"><span data-stu-id="fc143-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="fc143-152">Para obter mais informações sobre comandos DISM e manutenção offline, consulte os artigos abaixo:</span><span class="sxs-lookup"><span data-stu-id="fc143-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="fc143-153">Modificar uma Windows usando DISM</span><span class="sxs-lookup"><span data-stu-id="fc143-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="fc143-154">Opções de gerenciamento de imagens Command-Line DISM</span><span class="sxs-lookup"><span data-stu-id="fc143-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="fc143-155">Reduzir o tamanho do Armazenamento de Componentes em uma imagem Windows Offline</span><span class="sxs-lookup"><span data-stu-id="fc143-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="fc143-156">Se a manutenção offline não for uma opção viável para seu ambiente VDI não persistente, as etapas a seguir devem ser tomadas para garantir a consistência e a saúde do sensor:</span><span class="sxs-lookup"><span data-stu-id="fc143-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="fc143-157">Depois de inicializar a imagem mestra para manutenção ou correção online, execute um script de offboard para desativar o sensor de prevenção contra perda de dados Microsoft 365 endpoint.</span><span class="sxs-lookup"><span data-stu-id="fc143-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="fc143-158">Para obter mais informações, consulte [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="fc143-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="fc143-159">Verifique se o sensor é interrompido executando o comando abaixo em uma janela CMD:</span><span class="sxs-lookup"><span data-stu-id="fc143-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="fc143-160">Service the image as needed.</span><span class="sxs-lookup"><span data-stu-id="fc143-160">Service the image as needed.</span></span>

4. <span data-ttu-id="fc143-161">Execute os comandos abaixo usando PsExec.exe (que podem ser baixados para limpar o conteúdo da pasta cibernética que o sensor pode ter acumulado desde https://download.sysinternals.com/files/PSTools.zip) a inicialização:</span><span class="sxs-lookup"><span data-stu-id="fc143-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="fc143-162">Sele a imagem dourada/mestra como normalmente faria.</span><span class="sxs-lookup"><span data-stu-id="fc143-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc143-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fc143-163">Related topics</span></span>
- [<span data-ttu-id="fc143-164">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="fc143-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="fc143-165">Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fc143-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="fc143-166">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="fc143-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="fc143-167">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="fc143-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="fc143-168">Solucionar Proteção Avançada contra Ameaças do Microsoft Defender problemas de integração</span><span class="sxs-lookup"><span data-stu-id="fc143-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)