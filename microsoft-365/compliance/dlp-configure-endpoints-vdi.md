---
title: Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)
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
description: Implante o pacote de configuração no dispositivo virtual Desktop Infrastructure (VDI) para que eles sejam integrados ao serviço de prevenção de perda de dados de ponto de extremidade do Microsoft 365.
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769385"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="fe538-103">Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="fe538-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="fe538-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fe538-104">**Applies to:**</span></span>
- [<span data-ttu-id="fe538-105">Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="fe538-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="fe538-106">Dispositivos de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="fe538-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="fe538-107">Microsoft 365 Endpoint Data Loss Prevention support for Windows Virtual Desktop suporta cenários de sessão única.</span><span class="sxs-lookup"><span data-stu-id="fe538-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="fe538-108">Cenários de várias sessões na área de trabalho virtual do Windows atualmente não são suportados.</span><span class="sxs-lookup"><span data-stu-id="fe538-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="fe538-109">Dispositivos VDI integrados</span><span class="sxs-lookup"><span data-stu-id="fe538-109">Onboard VDI devices</span></span>

<span data-ttu-id="fe538-110">A prevenção de perda de dados de ponto de extremidade do Microsoft 365 suporta integração de sessão VDI não persistente.</span><span class="sxs-lookup"><span data-stu-id="fe538-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="fe538-111">Para sessões de VDI não persistente integradas, os dispositivos VDI devem estar no Windows 10 1809 ou superior.</span><span class="sxs-lookup"><span data-stu-id="fe538-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="fe538-112">Pode haver desafios associados durante a integração do VDIs.</span><span class="sxs-lookup"><span data-stu-id="fe538-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="fe538-113">Estes são os desafios típicos para este cenário:</span><span class="sxs-lookup"><span data-stu-id="fe538-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="fe538-114">A integração instantânea antecipada de uma sessão de curta duração, que deve ser integrada à prevenção de perda de dados de ponto de extremidade do Microsoft 365 antes do provisionamento real.</span><span class="sxs-lookup"><span data-stu-id="fe538-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="fe538-115">O nome do dispositivo é normalmente reutilizado para novas sessões.</span><span class="sxs-lookup"><span data-stu-id="fe538-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="fe538-116">Os dispositivos VDI podem aparecer no centro de conformidade da Microsoft 365 como:</span><span class="sxs-lookup"><span data-stu-id="fe538-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="fe538-117">Única entrada para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe538-117">Single entry for each device.</span></span>  
<span data-ttu-id="fe538-118">Observe que, nesse caso, o *mesmo* nome de dispositivo deve ser configurado quando a sessão é criada, por exemplo, usando um arquivo de resposta autônomo.</span><span class="sxs-lookup"><span data-stu-id="fe538-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="fe538-119">Várias entradas para cada dispositivo-um para cada sessão.</span><span class="sxs-lookup"><span data-stu-id="fe538-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="fe538-120">As etapas a seguir irão orientá-lo na integração de dispositivos de VDI e destacará as etapas de entradas únicas e múltiplas.</span><span class="sxs-lookup"><span data-stu-id="fe538-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="fe538-121">Para ambientes onde há configurações de poucos recursos, o procedimento de inicialização do VDI pode diminuir a integração do Microsoft 365 Endpoint Data Loss Prevention.</span><span class="sxs-lookup"><span data-stu-id="fe538-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="fe538-122">Abra o arquivo. zip do pacote de configuração VDI ( *DeviceCompliancePackage.zip* ) que você baixou a partir do assistente de integração de serviço.</span><span class="sxs-lookup"><span data-stu-id="fe538-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="fe538-123">No painel de navegação, selecione integração de integração do dispositivo de **configuração**  >  **Device onboarding**  >  **Onboarding** .</span><span class="sxs-lookup"><span data-stu-id="fe538-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="fe538-124">No campo **método de implantação** , selecione **scripts de integração VDI para pontos de extremidade não persistentes** .</span><span class="sxs-lookup"><span data-stu-id="fe538-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="fe538-125">Clique em **baixar pacote** e salve o arquivo. zip.</span><span class="sxs-lookup"><span data-stu-id="fe538-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="fe538-126">Copie os arquivos da pasta DeviceCompliancePackage extraídos do arquivo. zip para a `golden/master` imagem sob o caminho `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` .</span><span class="sxs-lookup"><span data-stu-id="fe538-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="fe538-127">Se você não estiver implementando uma única entrada para cada dispositivo, copie DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="fe538-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="fe538-128">Se você estiver implementando uma única entrada para cada dispositivo, copie Onboard-NonPersistentMachine.ps1 e DeviceComplianceOnboardingScript. cmd.</span><span class="sxs-lookup"><span data-stu-id="fe538-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fe538-129">Se você não vir a `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` pasta, ela poderá estar oculta.</span><span class="sxs-lookup"><span data-stu-id="fe538-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="fe538-130">Você precisará escolher a opção **mostrar pastas e arquivos ocultos** no explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fe538-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="fe538-131">Abra uma janela do editor de política de grupo local e navegue até **configuração do computador**  >  scripts de **configurações do Windows**  >  **Scripts**  >  **Startup** .</span><span class="sxs-lookup"><span data-stu-id="fe538-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="fe538-132">A política de grupo de domínio também pode ser usada para a integração de dispositivos não persistentes de VDI.</span><span class="sxs-lookup"><span data-stu-id="fe538-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="fe538-133">Dependendo do método que você gostaria de implementar, siga as etapas apropriadas:</span><span class="sxs-lookup"><span data-stu-id="fe538-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="fe538-134">**Para entrada única para cada dispositivo**</span><span class="sxs-lookup"><span data-stu-id="fe538-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="fe538-135">Selecione a guia **scripts do PowerShell** e, em seguida, clique em **Adicionar** (o Windows Explorer será aberto diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="fe538-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="fe538-136">Navegue até script do PowerShell de integração `Onboard-NonPersistentMachine.ps1` .</span><span class="sxs-lookup"><span data-stu-id="fe538-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="fe538-137">**Para várias entradas para cada dispositivo** :</span><span class="sxs-lookup"><span data-stu-id="fe538-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="fe538-138">Selecione a guia **scripts** e clique em **Adicionar** (o Windows Explorer será aberto diretamente no caminho onde você copiou o script de integração anteriormente).</span><span class="sxs-lookup"><span data-stu-id="fe538-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="fe538-139">Navegue até o script de bash de integração `DeviceComplianceOnboardingScript.cmd` .</span><span class="sxs-lookup"><span data-stu-id="fe538-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="fe538-140">Teste sua solução:</span><span class="sxs-lookup"><span data-stu-id="fe538-140">Test your solution:</span></span>

   1. <span data-ttu-id="fe538-141">Criar um pool com um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe538-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="fe538-142">Faça logon no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe538-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="fe538-143">Faça logoff do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fe538-143">Logoff from device.</span></span>

   1. <span data-ttu-id="fe538-144">Faça logon no dispositivo com outro usuário.</span><span class="sxs-lookup"><span data-stu-id="fe538-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="fe538-145">**Para entrada única para cada dispositivo** : Verifique apenas uma entrada na central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="fe538-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="fe538-146">**Para várias entradas para cada dispositivo** : marque várias entradas na central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="fe538-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="fe538-147">Clique em **lista de dispositivos** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="fe538-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="fe538-148">Use a função de pesquisa inserindo o nome do dispositivo e selecione **dispositivo** como tipo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fe538-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="fe538-149">Atualizando imagens não persistentes de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="fe538-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="fe538-150">Como prática recomendada, recomendamos o uso de ferramentas de serviço offline para corrigir imagens de ouro/Master.</span><span class="sxs-lookup"><span data-stu-id="fe538-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="fe538-151">Por exemplo, você pode usar os comandos a seguir para instalar uma atualização enquanto a imagem permanecer offline:</span><span class="sxs-lookup"><span data-stu-id="fe538-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="fe538-152">Para obter mais informações sobre os comandos DISM e a manutenção offline, consulte os artigos a seguir:</span><span class="sxs-lookup"><span data-stu-id="fe538-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="fe538-153">Modificar uma imagem do Windows usando o DISM</span><span class="sxs-lookup"><span data-stu-id="fe538-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="fe538-154">Opções de Command-Line de gerenciamento de imagem DISM</span><span class="sxs-lookup"><span data-stu-id="fe538-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="fe538-155">Reduzir o tamanho do repositório de componentes em uma imagem offline do Windows</span><span class="sxs-lookup"><span data-stu-id="fe538-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="fe538-156">Se a manutenção offline não for uma opção viável para seu ambiente de VDI não persistente, as seguintes etapas devem ser seguidas para garantir a consistência e a integridade do sensor:</span><span class="sxs-lookup"><span data-stu-id="fe538-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="fe538-157">Após a inicialização da imagem mestra para manutenção ou correção online, execute um script de remoção para desativar o sensor de prevenção de perda de dados de ponto de extremidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fe538-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="fe538-158">Para obter mais informações, consulte [externamente dispositivos usando um script local](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span><span class="sxs-lookup"><span data-stu-id="fe538-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="fe538-159">Verifique se o sensor foi interrompido executando o comando abaixo em uma janela CMD:</span><span class="sxs-lookup"><span data-stu-id="fe538-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="fe538-160">Atender a imagem, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="fe538-160">Service the image as needed.</span></span>

4. <span data-ttu-id="fe538-161">Execute os comandos a seguir usando PsExec.exe (que pode ser baixado de https://download.sysinternals.com/files/PSTools.zip) para limpar o conteúdo da pasta da CyberSource que o sensor pode ter acumulado desde a inicialização:</span><span class="sxs-lookup"><span data-stu-id="fe538-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="fe538-162">Lacrar novamente a imagem de ouro/Master como faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="fe538-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fe538-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fe538-163">Related topics</span></span>
- [<span data-ttu-id="fe538-164">Dispositivos Windows 10 integrados usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="fe538-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="fe538-165">Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="fe538-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="fe538-166">Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="fe538-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="fe538-167">Dispositivos integrados do Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="fe538-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="fe538-168">Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="fe538-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
