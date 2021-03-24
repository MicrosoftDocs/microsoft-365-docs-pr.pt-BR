---
title: Configurar o Microsoft Defender ATP para políticas macOS no Jamf Pro
description: Saiba como configurar o Microsoft Defender ATP para políticas macOS no Jamf Pro
keywords: policies, microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1559d8dca6b6909f22473c5a8f4d25d4bac501d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052897"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="e20ef-104">Configurar o Microsoft Defender para Endpoint para políticas macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="e20ef-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e20ef-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e20ef-105">**Applies to:**</span></span>

- [<span data-ttu-id="e20ef-106">Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="e20ef-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="e20ef-107">Esta página o guiará pelas etapas necessárias para configurar políticas macOS no Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="e20ef-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="e20ef-108">Você precisará seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e20ef-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="e20ef-109">Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="e20ef-110">Criar um perfil de configuração no Jamf Pro usando o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="e20ef-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="e20ef-111">Configurar configurações do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="e20ef-112">Configurar configurações de notificação do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="e20ef-113">Configurar o Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="e20ef-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="e20ef-114">Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="e20ef-115">Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="e20ef-116">Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="e20ef-117">Configurar Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="e20ef-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="e20ef-118">Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="e20ef-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="e20ef-119">Implantar o Microsoft Defender para Ponto de Extremidade para macOS</span><span class="sxs-lookup"><span data-stu-id="e20ef-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="e20ef-120">Etapa 1: Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="e20ef-121">No [Centro de Segurança do Microsoft Defender,](https://securitycenter.microsoft.com )navegue até **Configurações > Integração**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="e20ef-122">Selecione macOS como o sistema operacional e o Gerenciamento de Dispositivo Móvel /Microsoft Intune como o método de implantação.</span><span class="sxs-lookup"><span data-stu-id="e20ef-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Imagem do Centro de Segurança do Microsoft Defender](images/onboarding-macos.png)

3. <span data-ttu-id="e20ef-124">Selecione **Baixar pacote de integração** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="e20ef-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="e20ef-125">Extrair `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="e20ef-126">Copie o arquivo para o local preferencial.</span><span class="sxs-lookup"><span data-stu-id="e20ef-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="e20ef-127">Por exemplo, `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="e20ef-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="e20ef-128">Etapa 2: Criar um perfil de configuração no Jamf Pro usando o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="e20ef-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="e20ef-129">Localize o `WindowsDefenderATPOnboarding.plist` arquivo da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="e20ef-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Imagem do arquivo WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="e20ef-131">No painel Jamf Pro, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Imagem da criação de um novo painel do Jamf Pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="e20ef-133">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-133">Enter the following details:</span></span>

   <span data-ttu-id="e20ef-134">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-134">**General**</span></span>
   - <span data-ttu-id="e20ef-135">Nome: integração MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="e20ef-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="e20ef-136">Descrição: integração de EDR MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="e20ef-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="e20ef-137">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="e20ef-137">Category: None</span></span>
   - <span data-ttu-id="e20ef-138">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="e20ef-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="e20ef-139">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="e20ef-139">Level: Computer Level</span></span>

4. <span data-ttu-id="e20ef-140">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem de configuração de aplicativo e configurações personalizadas](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="e20ef-142">Selecione **Carregar Arquivo (arquivo PLIST)** em **Domínio de Preferência** insira: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Imagem do arquivo de carregamento de jamfpro plist](images/jamfpro-plist-upload.png)

    ![Imagem da propriedade De lista de propriedades de arquivo de carregamento](images/jamfpro-plist-file.png)

7. <span data-ttu-id="e20ef-145">Selecione **Abrir** e selecione o arquivo de integração.</span><span class="sxs-lookup"><span data-stu-id="e20ef-145">Select **Open** and select the onboarding file.</span></span>

    ![Imagem do arquivo de integração](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="e20ef-147">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-147">Select **Upload**.</span></span> 

    ![Imagem do carregamento de arquivo plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="e20ef-149">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-149">Select the **Scope** tab.</span></span>

    ![Imagem da guia escopo](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="e20ef-151">Selecione os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="e20ef-151">Select the target computers.</span></span>

    ![Imagem de computadores de destino](images/jamfpro-target-computer.png)

    ![Imagem de destinos](images/jamfpro-targets.png) 

11. <span data-ttu-id="e20ef-154">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-154">Select **Save**.</span></span>

    ![Imagem de computadores de destino de implantação](images/jamfpro-deployment-target.png)

    ![Imagem dos computadores de destino selecionados](images/jamfpro-target-selected.png)

12. <span data-ttu-id="e20ef-157">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-157">Select **Done**.</span></span>

    ![Imagem de computadores de grupo de destino](images/jamfpro-target-group.png)

    ![Lista de perfis de configuração](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="e20ef-160">Etapa 3: Configurar o Microsoft Defender para configurações de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="e20ef-161">Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="e20ef-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="e20ef-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="e20ef-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="e20ef-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="e20ef-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="e20ef-164">Não está ligado por padrão, se você estiver planejando executar um AV de terceiros para macOS, de defini-lo como `true` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="e20ef-165">exclusões</span><span class="sxs-lookup"><span data-stu-id="e20ef-165">exclusions</span></span>
    - <span data-ttu-id="e20ef-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="e20ef-166">excludedPath</span></span>
    - <span data-ttu-id="e20ef-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="e20ef-167">excludedFileExtension</span></span>
    - <span data-ttu-id="e20ef-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="e20ef-168">excludedFileName</span></span>
    - <span data-ttu-id="e20ef-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="e20ef-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="e20ef-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="e20ef-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="e20ef-171">EICAR está no exemplo, se você estiver passando por uma prova de conceito, remova-o especialmente se estiver testando o EICAR.</span><span class="sxs-lookup"><span data-stu-id="e20ef-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="e20ef-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="e20ef-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="e20ef-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="e20ef-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="e20ef-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="e20ef-174">archive_bomb</span></span>
    - <span data-ttu-id="e20ef-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="e20ef-175">cloudService</span></span>
    - <span data-ttu-id="e20ef-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="e20ef-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="e20ef-177">tags</span><span class="sxs-lookup"><span data-stu-id="e20ef-177">tags</span></span>
    - <span data-ttu-id="e20ef-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="e20ef-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="e20ef-179">Para obter informações, consulte [Lista de propriedades para perfil de configuração jamf](mac-preferences.md#property-list-for-jamf-configuration-profile).</span><span class="sxs-lookup"><span data-stu-id="e20ef-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. <span data-ttu-id="e20ef-180">Salve o arquivo como `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="e20ef-181">No painel Jamf Pro, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Imagem do novo painel do Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="e20ef-183">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-183">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-184">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-184">**General**</span></span>
    
    - <span data-ttu-id="e20ef-185">Nome: configurações MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="e20ef-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="e20ef-186">Descrição:\<blank\></span><span class="sxs-lookup"><span data-stu-id="e20ef-186">Description:\<blank\></span></span>
    - <span data-ttu-id="e20ef-187">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-187">Category: None (default)</span></span>
    - <span data-ttu-id="e20ef-188">Método Distribution: Install Automatically(default)</span><span class="sxs-lookup"><span data-stu-id="e20ef-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="e20ef-189">Nível: Nível do Computador(padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-189">Level: Computer Level(default)</span></span>

    ![Imagem das configurações MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="e20ef-191">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem do aplicativo e configurações personalizadas](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="e20ef-193">Selecione **Carregar Arquivo (arquivo PLIST)**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-193">Select **Upload File (PLIST file)**.</span></span>

    ![Imagem do arquivo plist de configurações](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="e20ef-195">Em **Domínio preferências**, digite `com.microsoft.wdav` , em seguida, selecione Carregar Arquivo  **PLIST**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Imagem do domínio de preferências de configurações](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="e20ef-197">Selecione **Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-197">Select **Choose File**.</span></span>

    ![Imagem das configurações de configuração escolha arquivo](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="e20ef-199">Selecione o **MDATP_MDAV_configuration_settings.plist** e, em seguida, **selecione Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Imagem das configurações do mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="e20ef-201">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-201">Select **Upload**.</span></span>

    ![Imagem de carregamento da configuração de configuração](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Imagem de configurações configurações carregando imagem](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="e20ef-204">Se você carregar o arquivo do Intune, obterá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="e20ef-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="e20ef-205">![Imagem das configurações de carregamento de arquivo do intune](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="e20ef-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="e20ef-206">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-206">Select **Save**.</span></span> 

    ![Imagem das configurações Salvar imagem](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="e20ef-208">O arquivo é carregado.</span><span class="sxs-lookup"><span data-stu-id="e20ef-208">The file is uploaded.</span></span>

    ![Imagem do arquivo carregado de configurações de configurações](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Imagem do arquivo de configurações de configuração carregado](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="e20ef-211">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-211">Select the **Scope** tab.</span></span>

    ![Imagem do escopo das configurações](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="e20ef-213">Selecione **Grupo de Máquinas da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="e20ef-214">Selecione **Adicionar** e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-214">Select **Add**, then select **Save**.</span></span>

    ![Imagem das configurações de configuração addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Imagem das configurações salvar adicionar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="e20ef-217">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-217">Select **Done**.</span></span> <span data-ttu-id="e20ef-218">Você verá o novo perfil **de configuração.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-218">You'll see the new **Configuration profile**.</span></span>

    ![Imagem das configurações configurações config imagem de perfil](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="e20ef-220">Etapa 4: Configurar configurações de notificações</span><span class="sxs-lookup"><span data-stu-id="e20ef-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="e20ef-221">Essas etapas são aplicáveis ao macOS 10.15 (Catalina) ou mais novo.</span><span class="sxs-lookup"><span data-stu-id="e20ef-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="e20ef-222">Baixar `notif.mobileconfig` em nosso repositório do [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span><span class="sxs-lookup"><span data-stu-id="e20ef-222">Download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig)</span></span>

2. <span data-ttu-id="e20ef-223">Salve-o como `MDATP_MDAV_notification_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-223">Save it as `MDATP_MDAV_notification_settings.plist`.</span></span>

3. <span data-ttu-id="e20ef-224">No painel Jamf Pro, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-224">In the Jamf Pro dashboard, select **General**.</span></span> 
       
4. <span data-ttu-id="e20ef-225">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-225">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-226">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-226">**General**</span></span> 
    
    - <span data-ttu-id="e20ef-227">Nome: Configurações de Notificação MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="e20ef-227">Name: MDATP MDAV Notification settings</span></span>
    - <span data-ttu-id="e20ef-228">Descrição: macOS 10.15 (Catalina) ou mais novo</span><span class="sxs-lookup"><span data-stu-id="e20ef-228">Description: macOS 10.15 (Catalina) or newer</span></span>
    - <span data-ttu-id="e20ef-229">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-229">Category: None (default)</span></span>
    - <span data-ttu-id="e20ef-230">Método Distribution: Install Automatically(default)</span><span class="sxs-lookup"><span data-stu-id="e20ef-230">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="e20ef-231">Nível: Nível do Computador(padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-231">Level: Computer Level(default)</span></span>

    ![Imagem das configurações mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)


5. <span data-ttu-id="e20ef-233">Selecione **Carregar Arquivo (arquivo PLIST)**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-233">Select **Upload File (PLIST file)**.</span></span>

    ![Imagem das configurações carregando plistfile](images/7f9138053dbcbf928e5182ee7b295ebe.png)
 

6. <span data-ttu-id="e20ef-235">Selecione **Escolher Arquivo**  >  **MDATP_MDAV_Notification_Settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-235">Select **Choose File** > **MDATP_MDAV_Notification_Settings.plist**.</span></span>


    ![Imagem de configurações de configurações de notsettings mdatpmdav](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)


    ![Imagem das configurações de notifsettings mdatpmdav](images/20e33b98eb54447881dc6c89e58b890f.png)

7. <span data-ttu-id="e20ef-238">Selecione **Abrir**  >  **Carregamento**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-238">Select **Open** > **Upload**.</span></span>

    ![Imagem das configurações upl img](images/7697c33b9fd376ae5a8023d01f9d3857.png)


    ![Imagem de configuração configurações imagem upl](images/2bda9244ec25d1526811da4ea91b1c86.png)

8. <span data-ttu-id="e20ef-241">Selecione a **guia Escopo** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-241">Select the **Scope** tab, then select **Add**.</span></span>

    ![Imagem do escopo de configurações adicionar](images/441aa2ecd36abadcdd8aed03556080b5.png)


9. <span data-ttu-id="e20ef-243">Selecione **Grupo de Máquinas da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-243">Select **Contoso's Machine Group**.</span></span> 

10. <span data-ttu-id="e20ef-244">Selecione **Adicionar** e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-244">Select **Add**, then select **Save**.</span></span>
    
    ![Imagem das configurações contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)

    
    ![Imagem de configurações configurações adicionar salvar](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

11. <span data-ttu-id="e20ef-247">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-247">Select **Done**.</span></span> <span data-ttu-id="e20ef-248">Você verá o novo perfil **de configuração.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-248">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="e20ef-249">![Imagem da configuração configuração feita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="e20ef-249">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="e20ef-250">Etapa 5: Configurar o Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="e20ef-250">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="e20ef-251">Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="e20ef-251">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. <span data-ttu-id="e20ef-252">Salve-o como `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-252">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="e20ef-253">No painel Jamf Pro, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-253">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Imagem da configuração de configuração de imagem geral](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="e20ef-255">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-255">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-256">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-256">**General**</span></span> 
    
    - <span data-ttu-id="e20ef-257">Nome: configurações MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="e20ef-257">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="e20ef-258">Descrição: Configurações do Microsoft AutoUpdate para MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="e20ef-258">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="e20ef-259">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-259">Category: None (default)</span></span>
    - <span data-ttu-id="e20ef-260">Método Distribution: Install Automatically(default)</span><span class="sxs-lookup"><span data-stu-id="e20ef-260">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="e20ef-261">Nível: Nível do Computador(padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-261">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="e20ef-262">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-262">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem do aplicativo de configuração e configurações personalizadas](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="e20ef-264">Selecione **Carregar Arquivo (arquivo PLIST)**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-264">Select **Upload File (PLIST file)**.</span></span>

    ![Imagem da configuração plist de configuração](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="e20ef-266">In **Preference Domain** enter: , then select Upload `com.microsoft.autoupdate2` **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-266">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Imagem da configuração de configuração de domínio pref](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="e20ef-268">Selecione **Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-268">Select **Choose File**.</span></span>

    ![Imagem da configuração de configuração choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="e20ef-270">Selecione **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-270">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Imagem de configuração definindo configurações mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="e20ef-272">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-272">Select **Upload**.</span></span>
    <span data-ttu-id="e20ef-273">![Imagem da configuração de configuração de](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="e20ef-273">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Imagem da configuração configurando uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="e20ef-275">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-275">Select **Save**.</span></span>

    ![Imagem da configuração saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="e20ef-277">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-277">Select the **Scope** tab.</span></span>
   
     ![Imagem de escopo de configuração](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="e20ef-279">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-279">Select **Add**.</span></span>
    
    ![Imagem da configuração addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Imagem da configuração addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Imagem da configuração addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="e20ef-283">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-283">Select **Done**.</span></span>
    
    ![Imagem da configuração configuração doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="e20ef-285">Etapa 6: Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-285">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="e20ef-286">No painel Jamf Pro, selecione **Perfis de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-286">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Imagem do perfil de configuração de configuração de configuração](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="e20ef-288">Selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-288">Select **+ New**.</span></span> 

3. <span data-ttu-id="e20ef-289">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-289">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-290">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-290">**General**</span></span> 
    - <span data-ttu-id="e20ef-291">Nome: MDATP MDAV - conceder acesso de disco completo a EDR e AV</span><span class="sxs-lookup"><span data-stu-id="e20ef-291">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="e20ef-292">Descrição: no macOS Catalina ou mais novo, o novo Controle de Política de Preferências de Privacidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-292">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="e20ef-293">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="e20ef-293">Category: None</span></span>
    - <span data-ttu-id="e20ef-294">Método de distribuição: Instalar Automaticamente</span><span class="sxs-lookup"><span data-stu-id="e20ef-294">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="e20ef-295">Nível: nível do computador</span><span class="sxs-lookup"><span data-stu-id="e20ef-295">Level: Computer level</span></span>


    ![Imagem da configuração geral](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="e20ef-297">Em **Configurar o Controle de Política de Preferências de Privacidade,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-297">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Imagem do controle de política de privacidade de configuração](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="e20ef-299">No **Controle de Política de Preferências de Privacidade,** insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-299">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="e20ef-300">Identificador: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="e20ef-300">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="e20ef-301">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="e20ef-301">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="e20ef-302">Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="e20ef-302">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Imagem de configuração definindo detalhes de controle de política de preferência de privacidade](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="e20ef-304">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-304">Select **+ Add**.</span></span>

    ![Imagem da configuração de configuração adicionar política do sistema todos os arquivos](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="e20ef-306">Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="e20ef-306">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="e20ef-307">Em "access": Definir como **Permitir**</span><span class="sxs-lookup"><span data-stu-id="e20ef-307">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="e20ef-308">Selecione **Salvar** (não o da parte inferior direita).</span><span class="sxs-lookup"><span data-stu-id="e20ef-308">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagem da configuração configuração salvar imagens](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="e20ef-310">Clique na `+` entrada ao lado do App **Access** para adicionar uma nova entrada.</span><span class="sxs-lookup"><span data-stu-id="e20ef-310">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Imagem da configuração de configuração de acesso ao aplicativo](images/tcc-add-entry.png)

9. <span data-ttu-id="e20ef-312">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-312">Enter the following details:</span></span>

    - <span data-ttu-id="e20ef-313">Identificador: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="e20ef-313">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="e20ef-314">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="e20ef-314">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="e20ef-315">Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="e20ef-315">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="e20ef-316">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-316">Select **+ Add**.</span></span>

    ![Imagem da configuração de configuração tcc epsext entry](images/tcc-epsext-entry.png)

    - <span data-ttu-id="e20ef-318">Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="e20ef-318">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="e20ef-319">Em "access": Definir como **Permitir**</span><span class="sxs-lookup"><span data-stu-id="e20ef-319">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="e20ef-320">Selecione **Salvar** (não o da parte inferior direita).</span><span class="sxs-lookup"><span data-stu-id="e20ef-320">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagem da configuração de configuração tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="e20ef-322">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-322">Select the **Scope** tab.</span></span>

    ![Imagem do escopo de configuração](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="e20ef-324">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-324">Select **+ Add**.</span></span>

    ![Imagem da configuração addimage de configuração](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="e20ef-326">Selecione **Grupos de >** em **Nome** do Grupo > selecione **MachineGroup da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-326">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Imagem da configuração de configuração contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="e20ef-328">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-328">Select **Add**.</span></span> 

16. <span data-ttu-id="e20ef-329">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-329">Select **Save**.</span></span> 
    
17. <span data-ttu-id="e20ef-330">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-330">Select **Done**.</span></span>
    
    ![Imagem da configuração donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Imagem da configuração donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)


## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="e20ef-333">Etapa 7: Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-333">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="e20ef-334">Nos **Perfis de Configuração,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-334">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="e20ef-336">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-336">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-337">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-337">**General**</span></span> 
    
    - <span data-ttu-id="e20ef-338">Nome: Extensão de Kernel MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="e20ef-338">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="e20ef-339">Descrição: extensão de kernel MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="e20ef-339">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="e20ef-340">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="e20ef-340">Category: None</span></span>
    - <span data-ttu-id="e20ef-341">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="e20ef-341">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="e20ef-342">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="e20ef-342">Level: Computer Level</span></span>

    ![Imagem das configurações do kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="e20ef-344">Em **Configurar Extensões de Kernel Aprovados,** **selecione Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-344">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Imagem das configurações do kernel ext aprovado](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="e20ef-346">Em **Extensões de Kernel Aprovadas** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-346">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="e20ef-347">Nome para exibição: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="e20ef-347">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="e20ef-348">ID da equipe: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="e20ef-348">Team ID: UBF8T346G9</span></span>

    ![Imagem das configurações de extensão do kernel do appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="e20ef-350">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-350">Select the **Scope** tab.</span></span>

    ![Imagem da guia de escopo de configurações img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="e20ef-352">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-352">Select **+ Add**.</span></span>

7. <span data-ttu-id="e20ef-353">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-353">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="e20ef-354">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-354">Select **+ Add**.</span></span>

    ![Imagem das configurações configurações adicionam imagens](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="e20ef-356">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-356">Select **Save**.</span></span>

    ![Imagem das configurações saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="e20ef-358">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-358">Select **Done**.</span></span>

    ![Imagem das configurações doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)


## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="e20ef-360">Etapa 8: Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e20ef-360">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="e20ef-361">Nos **Perfis de Configuração,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-361">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="e20ef-363">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-363">Enter the following details:</span></span>

    <span data-ttu-id="e20ef-364">**Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-364">**General**</span></span>
    
    - <span data-ttu-id="e20ef-365">Nome: Extensões do Sistema MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="e20ef-365">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="e20ef-366">Descrição: extensões do sistema MDATP</span><span class="sxs-lookup"><span data-stu-id="e20ef-366">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="e20ef-367">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="e20ef-367">Category: None</span></span>
    - <span data-ttu-id="e20ef-368">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="e20ef-368">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="e20ef-369">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="e20ef-369">Level: Computer Level</span></span>

    ![Imagem das configurações sysext novo prof](images/sysext-new-profile.png)

3. <span data-ttu-id="e20ef-371">Em **Extensões do Sistema,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-371">In **System Extensions** select **Configure**.</span></span>

   ![Imagem de configuração configurações sysext config](images/sysext-configure.png)

4. <span data-ttu-id="e20ef-373">Em **Extensões do Sistema,** insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-373">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="e20ef-374">Nome da exibição: Microsoft Corp. Extensões do sistema</span><span class="sxs-lookup"><span data-stu-id="e20ef-374">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="e20ef-375">Tipos de extensão do sistema: Extensões permitidas do sistema</span><span class="sxs-lookup"><span data-stu-id="e20ef-375">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="e20ef-376">Identificador de equipe: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="e20ef-376">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="e20ef-377">Extensões de sistema permitidas:</span><span class="sxs-lookup"><span data-stu-id="e20ef-377">Allowed System Extensions:</span></span>
     - <span data-ttu-id="e20ef-378">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="e20ef-378">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="e20ef-379">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="e20ef-379">**com.microsoft.wdav.netext**</span></span>

    ![Imagem das configurações sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="e20ef-381">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-381">Select the **Scope** tab.</span></span>

    ![Imagem de escopo de configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="e20ef-383">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-383">Select **+ Add**.</span></span>

7. <span data-ttu-id="e20ef-384">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-384">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="e20ef-385">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-385">Select **+ Add**.</span></span>

   ![Imagem de addima de configurações de configuração](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="e20ef-387">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-387">Select **Save**.</span></span>

   ![Imagem do escopo sysext das configurações](images/sysext-scope.png)

10. <span data-ttu-id="e20ef-389">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-389">Select **Done**.</span></span>

    ![Imagem das configurações sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="e20ef-391">Etapa 9: Configurar a Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="e20ef-391">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="e20ef-392">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade para Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e20ef-392">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="e20ef-393">A política a seguir permite que a extensão de rede execute essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e20ef-393">The following policy allows the network extension to perform this functionality.</span></span>

>[!NOTE]
><span data-ttu-id="e20ef-394">O JAMF não tem suporte integrado para políticas de filtragem de conteúdo, que são um pré-requisito para habilitar as extensões de rede que o Microsoft Defender para Ponto de Extremidade para Mac instala no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e20ef-394">JAMF doesn’t have built-in support for content filtering policies, which are a pre-requisite for enabling the network extensions that Microsoft Defender for Endpoint for Mac installs on the device.</span></span> <span data-ttu-id="e20ef-395">Além disso, o JAMF às vezes altera o conteúdo das políticas que estão sendo implantadas.</span><span class="sxs-lookup"><span data-stu-id="e20ef-395">Furthermore, JAMF sometimes changes the content of the policies being deployed.</span></span>
><span data-ttu-id="e20ef-396">Dessa forma, as etapas a seguir fornecem uma solução alternativa que envolve a assinatura do perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="e20ef-396">As such, the following steps provide a workaround that involve signing the configuration profile.</span></span>

1. <span data-ttu-id="e20ef-397">Baixe `netfilter.mobileconfig` do repositório do [GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) para seu dispositivo e salve-o como `com.microsoft.network-extension.mobileconfig`</span><span class="sxs-lookup"><span data-stu-id="e20ef-397">Download `netfilter.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig) to your device and save it as `com.microsoft.network-extension.mobileconfig`</span></span>

2. <span data-ttu-id="e20ef-398">Siga as instruções nesta [página para](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) criar um certificado de assinatura usando a autoridade de certificação in-loco do JAMF</span><span class="sxs-lookup"><span data-stu-id="e20ef-398">Follow the instructions on [this page](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) to create a signing certificate using JAMF’s built-in certificate authority</span></span>

3. <span data-ttu-id="e20ef-399">Depois que o certificado for criado e instalado em seu dispositivo, execute o seguinte comando do Terminal de um dispositivo macOS:</span><span class="sxs-lookup"><span data-stu-id="e20ef-399">After the certificate is created and installed to your device, run the following command from the Terminal from a macOS device:</span></span>

   ```bash
   $ security cms -S -N "<certificate name>" -i com.microsoft.network-extension.mobileconfig -o com.microsoft.network-extension.signed.mobileconfig
   ```

   ![Janela de terminal com comando para criar configuração assinada](images/netext-create-profile.png)

4. <span data-ttu-id="e20ef-401">No portal JAMF, navegue até **Perfis de Configuração** e clique no **botão Carregar.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-401">From the JAMF portal, navigate to **Configuration Profiles** and click the **Upload** button.</span></span> 

   ![Imagem da janela de carregamento](images/netext-upload-file.png)

5. <span data-ttu-id="e20ef-403">Selecione **Escolher Arquivo** e selecione `microsoft.network-extension.signed.mobileconfig` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-403">Select **Choose File** and select `microsoft.network-extension.signed.mobileconfig`.</span></span>

   ![Imagem do netext da janela de carregamento escolher arquivo](images/netext-choose-file.png)

6. <span data-ttu-id="e20ef-405">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-405">Select **Upload**.</span></span>

   ![Imagem do arquivo de upload de netext da janela de carregamento2](images/netext-upload-file2.png)

7. <span data-ttu-id="e20ef-407">Depois de carregar o arquivo, você será redirecionado para uma nova página para finalizar a criação desse perfil.</span><span class="sxs-lookup"><span data-stu-id="e20ef-407">After uploading the file, you are redirected to a new page to finalize the creation of this profile.</span></span>

   ![Imagem da nova página de perfil de netexto de perfil de configuração](images/netext-profile-page.png)

8. <span data-ttu-id="e20ef-409">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-409">Select the **Scope** tab.</span></span>

   ![Guia Descarr da imagem das configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

9. <span data-ttu-id="e20ef-411">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-411">Select **+ Add**.</span></span>

10. <span data-ttu-id="e20ef-412">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-412">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

11. <span data-ttu-id="e20ef-413">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-413">Select **+ Add**.</span></span>

    ![Imagem das configurações adim](images/0dde8a4c41110dbc398c485433a81359.png)

12. <span data-ttu-id="e20ef-415">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-415">Select **Save**.</span></span>

    ![Imagem das configurações savimg netextscop](images/netext-scope.png)

13. <span data-ttu-id="e20ef-417">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-417">Select **Done**.</span></span>

    ![Imagem das configurações netextfinal](images/netext-final.png)

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="e20ef-419">Etapa 10: Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="e20ef-419">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="e20ef-420">Siga as instruções em [Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="e20ef-420">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="e20ef-421">Etapa 11: Implantar o Microsoft Defender para Ponto de Extremidade para macOS</span><span class="sxs-lookup"><span data-stu-id="e20ef-421">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="e20ef-422">Navegue até onde você salvou `wdav.pkg` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-422">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Imagem do explorador de arquivos wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="e20ef-424">Renomeie-o para `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-424">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Imagem do explorador de arquivos1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="e20ef-426">Abra o painel Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="e20ef-426">Open the Jamf Pro dashboard.</span></span>

    ![Imagem das configurações jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="e20ef-428">Selecione o computador e clique no ícone de engrenagem na parte superior e selecione **Gerenciamento de Computador**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-428">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Imagem das configurações compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="e20ef-430">Em **Pacotes,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-430">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="e20ef-431">![Uma imagem que contém a descrição do pacote gerado automaticamente automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="e20ef-431">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="e20ef-432">Em **Novo Pacote** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-432">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="e20ef-433">**Guia Geral**</span><span class="sxs-lookup"><span data-stu-id="e20ef-433">**General tab**</span></span>
    - <span data-ttu-id="e20ef-434">Nome da exibição: deixe em branco por enquanto.</span><span class="sxs-lookup"><span data-stu-id="e20ef-434">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="e20ef-435">Porque ele será redefinido quando você escolher seu pkg.</span><span class="sxs-lookup"><span data-stu-id="e20ef-435">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="e20ef-436">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="e20ef-436">Category: None (default)</span></span>
    - <span data-ttu-id="e20ef-437">Nome do arquivo: Escolher Arquivo</span><span class="sxs-lookup"><span data-stu-id="e20ef-437">Filename: Choose File</span></span>

    ![Imagem da guia geral configurações](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="e20ef-439">Abra o arquivo e aponte para `wdav.pkg` ou `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="e20ef-439">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Uma captura de tela de uma tela do computador Descrição gerada automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="e20ef-441">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-441">Select **Open**.</span></span> <span data-ttu-id="e20ef-442">De definir **o Nome de Exibição** **como Proteção Avançada contra Ameaças do Microsoft Defender e o Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-442">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="e20ef-443">**O Arquivo de Manifesto** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="e20ef-443">**Manifest File** is not required.</span></span> <span data-ttu-id="e20ef-444">A Proteção Avançada contra Ameaças do Microsoft Defender funciona sem o Arquivo de Manifesto.</span><span class="sxs-lookup"><span data-stu-id="e20ef-444">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="e20ef-445">**Guia Opções**</span><span class="sxs-lookup"><span data-stu-id="e20ef-445">**Options tab**</span></span><br> <span data-ttu-id="e20ef-446">Mantenha valores padrão.</span><span class="sxs-lookup"><span data-stu-id="e20ef-446">Keep default values.</span></span>

    <span data-ttu-id="e20ef-447">**Guia Limitações**</span><span class="sxs-lookup"><span data-stu-id="e20ef-447">**Limitations tab**</span></span><br> <span data-ttu-id="e20ef-448">Mantenha valores padrão.</span><span class="sxs-lookup"><span data-stu-id="e20ef-448">Keep default values.</span></span>
    
     ![Guia de limitação de configurações da imagem](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="e20ef-450">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-450">Select **Save**.</span></span> <span data-ttu-id="e20ef-451">O pacote é carregado para o Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="e20ef-451">The package is uploaded to Jamf Pro.</span></span> 

   ![Imagem das configurações pacote upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="e20ef-453">Pode levar alguns minutos para o pacote estar disponível para implantação.</span><span class="sxs-lookup"><span data-stu-id="e20ef-453">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Imagem das configurações empacotam upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="e20ef-455">Navegue até **a página Políticas.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-455">Navigate to the **Policies** page.</span></span>

    ![Imagem das configurações de configurações de polônias](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="e20ef-457">Selecione **+ Novo** para criar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="e20ef-457">Select **+ New** to create a new policy.</span></span>

    ![Imagem das configurações configurações nova política](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="e20ef-459">Em **Geral** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e20ef-459">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="e20ef-460">Nome para exibição: MDATP Onboarding Contoso 200329 v100.86.92 ou posterior</span><span class="sxs-lookup"><span data-stu-id="e20ef-460">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="e20ef-461">Imagem das configuraçõesmdatponboard</span><span class="sxs-lookup"><span data-stu-id="e20ef-461">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="e20ef-462">Selecione **Check-in recorrente**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-462">Select **Recurring Check-in**.</span></span> 
    
    ![Imagem de configurações configurações recorrem à verificação](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="e20ef-464">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-464">Select **Save**.</span></span> 
 
14. <span data-ttu-id="e20ef-465">Selecione **Pacotes > Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-465">Select **Packages > Configure**.</span></span>
 
    ![Imagem do pacote de configurações configurações](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="e20ef-467">Selecione o **botão Adicionar** ao lado da Proteção Avançada contra Ameaças do Microsoft Defender e do Microsoft **Defender Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-467">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Imagem das configurações MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="e20ef-469">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-469">Select **Save**.</span></span>

    ![Imagem das configurações de configuraçãossavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="e20ef-471">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="e20ef-471">Select the **Scope** tab.</span></span>  

    ![Imagem das configurações scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="e20ef-473">Selecione os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="e20ef-473">Select the target computers.</span></span>

    ![Imagem das configurações tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="e20ef-475">**Scope**</span><span class="sxs-lookup"><span data-stu-id="e20ef-475">**Scope**</span></span>
    
    <span data-ttu-id="e20ef-476">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-476">Select **Add**.</span></span>
    
    ![Imagem das configurações do ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Imagem das configurações do ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="e20ef-479">**Autoatend**</span><span class="sxs-lookup"><span data-stu-id="e20ef-479">**Self-Service**</span></span>
    
    ![Imagem de autoatendiço de configurações](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="e20ef-481">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e20ef-481">Select **Done**.</span></span> 

    ![Imagem das configurações do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Imagem das configurações do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




