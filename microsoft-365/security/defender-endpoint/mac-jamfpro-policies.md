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
ms.openlocfilehash: be01d5908e4c79f642cdbbddd75115f6ebc2c713
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499611"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-for-macos-policies-in-jamf-pro"></a><span data-ttu-id="2a28b-104">Configurar o Microsoft Defender para Endpoint para políticas macOS no Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="2a28b-104">Set up the Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2a28b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2a28b-105">**Applies to:**</span></span>

- [<span data-ttu-id="2a28b-106">Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2a28b-106">Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="2a28b-107">Esta página o guiará pelas etapas necessárias para configurar políticas macOS no Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="2a28b-107">This page will guide you through the steps you need to take to set up macOS policies in Jamf Pro.</span></span>

<span data-ttu-id="2a28b-108">Você precisará seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2a28b-108">You'll need to take the following steps:</span></span>

1. [<span data-ttu-id="2a28b-109">Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-109">Get the Microsoft Defender for Endpoint onboarding package</span></span>](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [<span data-ttu-id="2a28b-110">Criar um perfil de configuração no Jamf Pro usando o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="2a28b-110">Create a configuration profile in Jamf Pro using the onboarding package</span></span>](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [<span data-ttu-id="2a28b-111">Configurar configurações do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-111">Configure Microsoft Defender for Endpoint settings</span></span>](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [<span data-ttu-id="2a28b-112">Configurar configurações de notificação do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-112">Configure Microsoft Defender for Endpoint notification settings</span></span>](#step-4-configure-notifications-settings)

5. [<span data-ttu-id="2a28b-113">Configurar o Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="2a28b-113">Configure Microsoft AutoUpdate (MAU)</span></span>](#step-5-configure-microsoft-autoupdate-mau)

6. [<span data-ttu-id="2a28b-114">Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-114">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [<span data-ttu-id="2a28b-115">Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-115">Approve Kernel extension for Microsoft Defender for Endpoint</span></span>](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [<span data-ttu-id="2a28b-116">Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-116">Approve System extensions for Microsoft Defender for Endpoint</span></span>](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [<span data-ttu-id="2a28b-117">Configurar Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="2a28b-117">Configure Network Extension</span></span>](#step-9-configure-network-extension)

10. [<span data-ttu-id="2a28b-118">Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2a28b-118">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [<span data-ttu-id="2a28b-119">Implantar o Microsoft Defender para Ponto de Extremidade para macOS</span><span class="sxs-lookup"><span data-stu-id="2a28b-119">Deploy Microsoft Defender for Endpoint for macOS</span></span>](#step-11-deploy-microsoft-defender-for-endpoint-for-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a><span data-ttu-id="2a28b-120">Etapa 1: Obter o pacote de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-120">Step 1: Get the Microsoft Defender for Endpoint onboarding package</span></span>

1. <span data-ttu-id="2a28b-121">No [Centro de Segurança do Microsoft Defender,](https://securitycenter.microsoft.com )navegue até **Configurações > Integração**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-121">In [Microsoft Defender Security Center](https://securitycenter.microsoft.com ), navigate to **Settings > Onboarding**.</span></span> 

2. <span data-ttu-id="2a28b-122">Selecione macOS como o sistema operacional e o Gerenciamento de Dispositivo Móvel /Microsoft Intune como o método de implantação.</span><span class="sxs-lookup"><span data-stu-id="2a28b-122">Select macOS as the operating system and Mobile Device Management / Microsoft Intune as the deployment method.</span></span>

    ![Imagem do Centro de Segurança do Microsoft Defender](images/onboarding-macos.png)

3. <span data-ttu-id="2a28b-124">Selecione **Baixar pacote de integração** (WindowsDefenderATPOnboardingPackage.zip).</span><span class="sxs-lookup"><span data-stu-id="2a28b-124">Select **Download onboarding package** (WindowsDefenderATPOnboardingPackage.zip).</span></span>

4. <span data-ttu-id="2a28b-125">Extrair `WindowsDefenderATPOnboardingPackage.zip` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-125">Extract `WindowsDefenderATPOnboardingPackage.zip`.</span></span>

5. <span data-ttu-id="2a28b-126">Copie o arquivo para o local preferencial.</span><span class="sxs-lookup"><span data-stu-id="2a28b-126">Copy the file to your preferred location.</span></span> <span data-ttu-id="2a28b-127">Por exemplo, `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span><span class="sxs-lookup"><span data-stu-id="2a28b-127">For example,  `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.</span></span>


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a><span data-ttu-id="2a28b-128">Etapa 2: Criar um perfil de configuração no Jamf Pro usando o pacote de integração</span><span class="sxs-lookup"><span data-stu-id="2a28b-128">Step 2: Create a configuration profile in Jamf Pro using the onboarding package</span></span>

1. <span data-ttu-id="2a28b-129">Localize o `WindowsDefenderATPOnboarding.plist` arquivo da seção anterior.</span><span class="sxs-lookup"><span data-stu-id="2a28b-129">Locate the file `WindowsDefenderATPOnboarding.plist` from the previous section.</span></span>

   ![Imagem do arquivo WindowsDefenderATPOnboarding](images/plist-onboarding-file.png)

 
2. <span data-ttu-id="2a28b-131">No painel Jamf Pro, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-131">In the Jamf Pro dashboard, select **New**.</span></span>

    ![Imagem da criação de um novo painel do Jamf Pro](images/jamf-pro-configure-profile.png)

3. <span data-ttu-id="2a28b-133">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-133">Enter the following details:</span></span>

   <span data-ttu-id="2a28b-134">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-134">**General**</span></span>
   - <span data-ttu-id="2a28b-135">Nome: integração MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="2a28b-135">Name: MDATP onboarding for macOS</span></span>
   - <span data-ttu-id="2a28b-136">Descrição: integração de EDR MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="2a28b-136">Description: MDATP EDR onboarding for macOS</span></span>
   - <span data-ttu-id="2a28b-137">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a28b-137">Category: None</span></span>
   - <span data-ttu-id="2a28b-138">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="2a28b-138">Distribution Method: Install Automatically</span></span>
   - <span data-ttu-id="2a28b-139">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="2a28b-139">Level: Computer Level</span></span>

4. <span data-ttu-id="2a28b-140">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-140">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem de configuração de aplicativo e configurações personalizadas](images/jamfpro-mac-profile.png)

5. <span data-ttu-id="2a28b-142">Selecione **Carregar Arquivo (arquivo PLIST)** em **Domínio de Preferência** insira: `com.microsoft.wdav.atp` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-142">Select **Upload File (PLIST file)** then in **Preference Domain** enter: `com.microsoft.wdav.atp`.</span></span> 

    ![Imagem do arquivo de carregamento de jamfpro plist](images/jamfpro-plist-upload.png)

    ![Imagem da propriedade De lista de propriedades de arquivo de carregamento](images/jamfpro-plist-file.png)

7. <span data-ttu-id="2a28b-145">Selecione **Abrir** e selecione o arquivo de integração.</span><span class="sxs-lookup"><span data-stu-id="2a28b-145">Select **Open** and select the onboarding file.</span></span>

    ![Imagem do arquivo de integração](images/jamfpro-plist-file-onboard.png)

8. <span data-ttu-id="2a28b-147">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-147">Select **Upload**.</span></span> 

    ![Imagem do carregamento de arquivo plist](images/jamfpro-upload-plist.png)


9. <span data-ttu-id="2a28b-149">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-149">Select the **Scope** tab.</span></span>

    ![Imagem da guia escopo](images/jamfpro-scope-tab.png)

10. <span data-ttu-id="2a28b-151">Selecione os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="2a28b-151">Select the target computers.</span></span>

    ![Imagem de computadores de destino](images/jamfpro-target-computer.png)

    ![Imagem de destinos](images/jamfpro-targets.png) 

11. <span data-ttu-id="2a28b-154">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-154">Select **Save**.</span></span>

    ![Imagem de computadores de destino de implantação](images/jamfpro-deployment-target.png)

    ![Imagem dos computadores de destino selecionados](images/jamfpro-target-selected.png)

12. <span data-ttu-id="2a28b-157">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-157">Select **Done**.</span></span>

    ![Imagem de computadores de grupo de destino](images/jamfpro-target-group.png)

    ![Lista de perfis de configuração](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a><span data-ttu-id="2a28b-160">Etapa 3: Configurar o Microsoft Defender para configurações de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-160">Step 3: Configure Microsoft Defender for Endpoint settings</span></span>

1.  <span data-ttu-id="2a28b-161">Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="2a28b-161">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

    - <span data-ttu-id="2a28b-162">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="2a28b-162">enableRealTimeProtection</span></span>
    - <span data-ttu-id="2a28b-163">passiveMode</span><span class="sxs-lookup"><span data-stu-id="2a28b-163">passiveMode</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="2a28b-164">Não está ligado por padrão, se você estiver planejando executar um AV de terceiros para macOS, de defini-lo como `true` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-164">Not turned on by default, if you are planning to run a third-party AV for macOS, set it to `true`.</span></span>

    - <span data-ttu-id="2a28b-165">exclusões</span><span class="sxs-lookup"><span data-stu-id="2a28b-165">exclusions</span></span>
    - <span data-ttu-id="2a28b-166">excludedPath</span><span class="sxs-lookup"><span data-stu-id="2a28b-166">excludedPath</span></span>
    - <span data-ttu-id="2a28b-167">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="2a28b-167">excludedFileExtension</span></span>
    - <span data-ttu-id="2a28b-168">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="2a28b-168">excludedFileName</span></span>
    - <span data-ttu-id="2a28b-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="2a28b-169">exclusionsMergePolicy</span></span>
    - <span data-ttu-id="2a28b-170">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="2a28b-170">allowedThreats</span></span>
    
    >[!NOTE]
    ><span data-ttu-id="2a28b-171">EICAR está no exemplo, se você estiver passando por uma prova de conceito, remova-o especialmente se estiver testando o EICAR.</span><span class="sxs-lookup"><span data-stu-id="2a28b-171">EICAR is on the sample, if you are going through a proof-of-concept, remove it especially if you are testing EICAR.</span></span>
        
    - <span data-ttu-id="2a28b-172">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="2a28b-172">disallowedThreatActions</span></span>
    - <span data-ttu-id="2a28b-173">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="2a28b-173">potentially_unwanted_application</span></span>
    - <span data-ttu-id="2a28b-174">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="2a28b-174">archive_bomb</span></span>
    - <span data-ttu-id="2a28b-175">cloudService</span><span class="sxs-lookup"><span data-stu-id="2a28b-175">cloudService</span></span>
    - <span data-ttu-id="2a28b-176">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="2a28b-176">automaticSampleSubmission</span></span>
    - <span data-ttu-id="2a28b-177">tags</span><span class="sxs-lookup"><span data-stu-id="2a28b-177">tags</span></span>
    - <span data-ttu-id="2a28b-178">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="2a28b-178">hideStatusMenuIcon</span></span>
    
     <span data-ttu-id="2a28b-179">Para obter informações, consulte [Lista de propriedades para perfil de configuração jamf](mac-preferences.md#property-list-for-jamf-configuration-profile).</span><span class="sxs-lookup"><span data-stu-id="2a28b-179">For information, see [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).</span></span>

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

2. <span data-ttu-id="2a28b-180">Salve o arquivo como `MDATP_MDAV_configuration_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-180">Save the file as `MDATP_MDAV_configuration_settings.plist`.</span></span>


3.  <span data-ttu-id="2a28b-181">No painel Jamf Pro, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-181">In the Jamf Pro dashboard, select **General**.</span></span>

    ![Imagem do novo painel do Jamf Pro](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. <span data-ttu-id="2a28b-183">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-183">Enter the following details:</span></span>

    <span data-ttu-id="2a28b-184">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-184">**General**</span></span>
    
    - <span data-ttu-id="2a28b-185">Nome: configurações MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="2a28b-185">Name: MDATP MDAV configuration settings</span></span>
    - <span data-ttu-id="2a28b-186">Descrição:\<blank\></span><span class="sxs-lookup"><span data-stu-id="2a28b-186">Description:\<blank\></span></span>
    - <span data-ttu-id="2a28b-187">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="2a28b-187">Category: None (default)</span></span>
    - <span data-ttu-id="2a28b-188">Método Distribution: Install Automatically(default)</span><span class="sxs-lookup"><span data-stu-id="2a28b-188">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="2a28b-189">Nível: Nível do Computador(padrão)</span><span class="sxs-lookup"><span data-stu-id="2a28b-189">Level: Computer Level(default)</span></span>

    ![Imagem das configurações MDATP MDAV](images/3160906404bc5a2edf84d1d015894e3b.png)

5. <span data-ttu-id="2a28b-191">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-191">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem do aplicativo e configurações personalizadas](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. <span data-ttu-id="2a28b-193">Selecione **Carregar Arquivo (arquivo PLIST)**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-193">Select **Upload File (PLIST file)**.</span></span>

    ![Imagem do arquivo plist de configurações](images/6f85269276b2278eca4bce84f935f87b.png)

7. <span data-ttu-id="2a28b-195">Em **Domínio preferências**, digite `com.microsoft.wdav` , em seguida, selecione Carregar Arquivo  **PLIST**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-195">In **Preferences Domain**, enter `com.microsoft.wdav`, then select  **Upload PLIST File**.</span></span>

    ![Imagem do domínio de preferências de configurações](images/db15f147dd959e872a044184711d7d46.png)

8. <span data-ttu-id="2a28b-197">Selecione **Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-197">Select **Choose File**.</span></span>

    ![Imagem das configurações de configuração escolha arquivo](images/526e978761fc571cca06907da7b01fd6.png)

9. <span data-ttu-id="2a28b-199">Selecione o **MDATP_MDAV_configuration_settings.plist** e, em seguida, **selecione Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-199">Select the **MDATP_MDAV_configuration_settings.plist**, then select **Open**.</span></span>

    ![Imagem das configurações do mdatpmdav](images/98acea3750113b8dbab334296e833003.png)

10. <span data-ttu-id="2a28b-201">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-201">Select **Upload**.</span></span>

    ![Imagem de carregamento da configuração de configuração](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Imagem de configurações configurações carregando imagem](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    ><span data-ttu-id="2a28b-204">Se você carregar o arquivo do Intune, obterá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="2a28b-204">If you happen to upload the Intune file, you'll get the following error:</span></span><br>
    ><span data-ttu-id="2a28b-205">![Imagem das configurações de carregamento de arquivo do intune](images/8e69f867664668796a3b2904896f0436.png)</span><span class="sxs-lookup"><span data-stu-id="2a28b-205">![Image of configuration settings intune file upload](images/8e69f867664668796a3b2904896f0436.png)</span></span>


11. <span data-ttu-id="2a28b-206">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-206">Select **Save**.</span></span> 

    ![Imagem das configurações Salvar imagem](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. <span data-ttu-id="2a28b-208">O arquivo é carregado.</span><span class="sxs-lookup"><span data-stu-id="2a28b-208">The file is uploaded.</span></span>

    ![Imagem do arquivo carregado de configurações de configurações](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Imagem do arquivo de configurações de configuração carregado](images/a422e57fe8d45689227e784443e51bd1.png)

13. <span data-ttu-id="2a28b-211">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-211">Select the **Scope** tab.</span></span>

    ![Imagem do escopo das configurações](images/9fc17529e5577eefd773c658ec576a7d.png)

14. <span data-ttu-id="2a28b-213">Selecione **Grupo de Máquinas da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-213">Select **Contoso's Machine Group**.</span></span> 

15. <span data-ttu-id="2a28b-214">Selecione **Adicionar** e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-214">Select **Add**, then select **Save**.</span></span>

    ![Imagem das configurações de configuração addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Imagem das configurações salvar adicionar](images/6f093e42856753a3955cab7ee14f12d9.png)

16. <span data-ttu-id="2a28b-217">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-217">Select **Done**.</span></span> <span data-ttu-id="2a28b-218">Você verá o novo perfil **de configuração.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-218">You'll see the new **Configuration profile**.</span></span>

    ![Imagem das configurações configurações config imagem de perfil](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a><span data-ttu-id="2a28b-220">Etapa 4: Configurar configurações de notificações</span><span class="sxs-lookup"><span data-stu-id="2a28b-220">Step 4: Configure notifications settings</span></span>

<span data-ttu-id="2a28b-221">Essas etapas são aplicáveis ao macOS 10.15 (Catalina) ou mais novo.</span><span class="sxs-lookup"><span data-stu-id="2a28b-221">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="2a28b-222">No painel Jamf Pro, selecione **Computadores** e, em seguida, **Perfis de Configuração.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-222">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="2a28b-223">Clique **em Novo** e insira os seguintes detalhes para **Opções**:</span><span class="sxs-lookup"><span data-stu-id="2a28b-223">Click **New**, and enter the following details for **Options**:</span></span>
    
    - <span data-ttu-id="2a28b-224">Guia **Geral**:</span><span class="sxs-lookup"><span data-stu-id="2a28b-224">Tab **General**:</span></span> 
        - <span data-ttu-id="2a28b-225">**Nome**: Configurações de Notificação MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="2a28b-225">**Name**: MDATP MDAV Notification settings</span></span>
        - <span data-ttu-id="2a28b-226">**Descrição**: macOS 10.15 (Catalina) ou mais novo</span><span class="sxs-lookup"><span data-stu-id="2a28b-226">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="2a28b-227">**Categoria**: Nenhum *(padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-227">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="2a28b-228">**Método Distribution**: Instalar Automaticamente *(padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-228">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="2a28b-229">**Nível**: Nível do *computador (padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-229">**Level**: Computer Level *(default)*</span></span>

        ![Imagem das configurações mdatpmdav](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - <span data-ttu-id="2a28b-231">Notificações **de tabulação,** clique **em Adicionar** e insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2a28b-231">Tab **Notifications**, click **Add**, and enter the following values:</span></span>
        - <span data-ttu-id="2a28b-232">**ID do pacote:**`com.microsoft.wdav.tray`</span><span class="sxs-lookup"><span data-stu-id="2a28b-232">**Bundle ID**: `com.microsoft.wdav.tray`</span></span>
        - <span data-ttu-id="2a28b-233">**Alertas críticos:** clique em **Desabilitar**</span><span class="sxs-lookup"><span data-stu-id="2a28b-233">**Critical Alerts**: Click **Disable**</span></span>
        - <span data-ttu-id="2a28b-234">**Notificações**: Clique em **Habilitar**</span><span class="sxs-lookup"><span data-stu-id="2a28b-234">**Notifications**: Click **Enable**</span></span>
        - <span data-ttu-id="2a28b-235">**Tipo de alerta de faixa**: Selecione **Incluir** **e Temporário** *(padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-235">**Banner alert type**: Select **Include** and **Temporary** *(default)*</span></span>
        - <span data-ttu-id="2a28b-236">**Notificações na tela de bloqueio**: Clique em **Ocultar**</span><span class="sxs-lookup"><span data-stu-id="2a28b-236">**Notifications on lock screen**: Click **Hide**</span></span>
        - <span data-ttu-id="2a28b-237">**Notificações na Central de Notificações**: Clique em **Exibir**</span><span class="sxs-lookup"><span data-stu-id="2a28b-237">**Notifications in Notification Center**: Click **Display**</span></span>
        - <span data-ttu-id="2a28b-238">**Ícone do aplicativo selo:** clique em **Exibir**</span><span class="sxs-lookup"><span data-stu-id="2a28b-238">**Badge app icon**: Click **Display**</span></span>

        ![Imagem das configurações configurações bandeja de notificações mdatpmdav](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - <span data-ttu-id="2a28b-240">Notificações **de tabulação**, clique em **Adicionar** mais uma vez, role para baixo até **Novas Configurações de Notificações**</span><span class="sxs-lookup"><span data-stu-id="2a28b-240">Tab **Notifications**, click **Add** one more time, scroll down to **New Notifications Settings**</span></span>
        - <span data-ttu-id="2a28b-241">**ID do pacote:**`com.microsoft.autoupdate2`</span><span class="sxs-lookup"><span data-stu-id="2a28b-241">**Bundle ID**: `com.microsoft.autoupdate2`</span></span>
        - <span data-ttu-id="2a28b-242">Configurar o restante das configurações para os mesmos valores acima</span><span class="sxs-lookup"><span data-stu-id="2a28b-242">Configure the rest of the settings to the same values as above</span></span>

        ![Imagem de configurações configurações mdatpmdav notifications mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        <span data-ttu-id="2a28b-244">Observe que agora você tem duas "tabelas" com configurações de notificação, uma para iD do **pacote: com.microsoft.wdav.tray** e outra para iD do **pacote: com.microsoft.autoupdate2**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-244">Note that now you have two 'tables' with notification configurations, one for **Bundle ID: com.microsoft.wdav.tray**, and another for **Bundle ID: com.microsoft.autoupdate2**.</span></span> <span data-ttu-id="2a28b-245">Embora você possa configurar as configurações de alerta de acordo com seus  **requisitos,** as IDs de pacote devem ser exatamente as mesmas descritas anteriormente, e a opção Incluir deve estar Em **para** Notificações .</span><span class="sxs-lookup"><span data-stu-id="2a28b-245">While you can configure alert settings per your requirements, Bundle IDs must be exactly the same as described before, and **Include** switch must be **On** for **Notifications**.</span></span>

3. <span data-ttu-id="2a28b-246">Selecione a **guia Escopo** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-246">Select the **Scope** tab, then select **Add**.</span></span>

    ![Imagem do escopo de configurações adicionar](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. <span data-ttu-id="2a28b-248">Selecione **Grupo de Máquinas da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-248">Select **Contoso's Machine Group**.</span></span> 

5. <span data-ttu-id="2a28b-249">Selecione **Adicionar** e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-249">Select **Add**, then select **Save**.</span></span>
    
    ![Imagem das configurações contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Imagem de configurações configurações adicionar salvar](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. <span data-ttu-id="2a28b-252">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-252">Select **Done**.</span></span> <span data-ttu-id="2a28b-253">Você verá o novo perfil **de configuração.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-253">You'll see the new **Configuration profile**.</span></span>
    <span data-ttu-id="2a28b-254">![Imagem da configuração configuração feita img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span><span class="sxs-lookup"><span data-stu-id="2a28b-254">![Image of configuration setting done img](images/633ad26b8bf24ec683c98b2feb884bdf.png)</span></span>

## <a name="step-5-configure-microsoft-autoupdate-mau"></a><span data-ttu-id="2a28b-255">Etapa 5: Configurar o Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="2a28b-255">Step 5: Configure Microsoft AutoUpdate (MAU)</span></span>

1. <span data-ttu-id="2a28b-256">Use as seguintes configurações do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="2a28b-256">Use the following Microsoft Defender for Endpoint configuration settings:</span></span>

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

2. <span data-ttu-id="2a28b-257">Salve-o como `MDATP_MDAV_MAU_settings.plist` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-257">Save it as `MDATP_MDAV_MAU_settings.plist`.</span></span>

3. <span data-ttu-id="2a28b-258">No painel Jamf Pro, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-258">In the Jamf Pro dashboard, select **General**.</span></span> 

    ![Imagem da configuração de configuração de imagem geral](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. <span data-ttu-id="2a28b-260">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-260">Enter the following details:</span></span>

    <span data-ttu-id="2a28b-261">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-261">**General**</span></span> 
    
    - <span data-ttu-id="2a28b-262">Nome: configurações MDATP MDAV MAU</span><span class="sxs-lookup"><span data-stu-id="2a28b-262">Name: MDATP MDAV MAU settings</span></span>
    - <span data-ttu-id="2a28b-263">Descrição: Configurações do Microsoft AutoUpdate para MDATP para macOS</span><span class="sxs-lookup"><span data-stu-id="2a28b-263">Description: Microsoft AutoUpdate settings for MDATP for macOS</span></span>
    - <span data-ttu-id="2a28b-264">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="2a28b-264">Category: None (default)</span></span>
    - <span data-ttu-id="2a28b-265">Método Distribution: Install Automatically(default)</span><span class="sxs-lookup"><span data-stu-id="2a28b-265">Distribution Method: Install Automatically(default)</span></span>
    - <span data-ttu-id="2a28b-266">Nível: Nível do Computador(padrão)</span><span class="sxs-lookup"><span data-stu-id="2a28b-266">Level: Computer Level(default)</span></span>

5. <span data-ttu-id="2a28b-267">No **Aplicativo & Configurações Personalizadas** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-267">In **Application & Custom Settings** select **Configure**.</span></span>

    ![Imagem do aplicativo de configuração e configurações personalizadas](images/1f72e9c15eaafcabf1504397e99be311.png)

6. <span data-ttu-id="2a28b-269">Selecione **Carregar Arquivo (arquivo PLIST)**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-269">Select **Upload File (PLIST file)**.</span></span>

    ![Imagem da configuração plist de configuração](images/1213872db5833aa8be535da57653219f.png)  

7. <span data-ttu-id="2a28b-271">In **Preference Domain** enter: , then select Upload `com.microsoft.autoupdate2` **PLIST File**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-271">In **Preference Domain** enter: `com.microsoft.autoupdate2`, then select **Upload PLIST File**.</span></span>

    ![Imagem da configuração de configuração de domínio pref](images/1213872db5833aa8be535da57653219f.png)

8. <span data-ttu-id="2a28b-273">Selecione **Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-273">Select **Choose File**.</span></span>

    ![Imagem da configuração de configuração choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. <span data-ttu-id="2a28b-275">Selecione **MDATP_MDAV_MAU_settings.plist**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-275">Select **MDATP_MDAV_MAU_settings.plist**.</span></span>

    ![Imagem de configuração definindo configurações mdatpmdavmau](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. <span data-ttu-id="2a28b-277">Selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-277">Select **Upload**.</span></span>
    <span data-ttu-id="2a28b-278">![Imagem da configuração de configuração de](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span><span class="sxs-lookup"><span data-stu-id="2a28b-278">![Image of configuration setting uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)</span></span>

    ![Imagem da configuração configurando uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. <span data-ttu-id="2a28b-280">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-280">Select **Save**.</span></span>

    ![Imagem da configuração saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. <span data-ttu-id="2a28b-282">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-282">Select the **Scope** tab.</span></span>
   
     ![Imagem de escopo de configuração](images/10ab98358b2d602f3f67618735fa82fb.png)

13. <span data-ttu-id="2a28b-284">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-284">Select **Add**.</span></span>
    
    ![Imagem da configuração addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Imagem da configuração addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Imagem da configuração addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. <span data-ttu-id="2a28b-288">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-288">Select **Done**.</span></span>
    
    ![Imagem da configuração configuração doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="2a28b-290">Etapa 6: Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-290">Step 6: Grant full disk access to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="2a28b-291">No painel Jamf Pro, selecione **Perfis de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-291">In the Jamf Pro dashboard, select **Configuration Profiles**.</span></span>

    ![Imagem do perfil de configuração de configuração de configuração](images/264493cd01e62c7085659d6fdc26dc91.png)

2. <span data-ttu-id="2a28b-293">Selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-293">Select **+ New**.</span></span> 

3. <span data-ttu-id="2a28b-294">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-294">Enter the following details:</span></span>

    <span data-ttu-id="2a28b-295">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-295">**General**</span></span> 
    - <span data-ttu-id="2a28b-296">Nome: MDATP MDAV - conceder acesso de disco completo a EDR e AV</span><span class="sxs-lookup"><span data-stu-id="2a28b-296">Name: MDATP MDAV - grant Full Disk Access to EDR and AV</span></span>
    - <span data-ttu-id="2a28b-297">Descrição: no macOS Catalina ou mais novo, o novo Controle de Política de Preferências de Privacidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-297">Description: On macOS Catalina or newer, the new Privacy Preferences Policy Control</span></span>
    - <span data-ttu-id="2a28b-298">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a28b-298">Category: None</span></span>
    - <span data-ttu-id="2a28b-299">Método de distribuição: Instalar Automaticamente</span><span class="sxs-lookup"><span data-stu-id="2a28b-299">Distribution method: Install Automatically</span></span>
    - <span data-ttu-id="2a28b-300">Nível: nível do computador</span><span class="sxs-lookup"><span data-stu-id="2a28b-300">Level: Computer level</span></span>


    ![Imagem da configuração geral](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. <span data-ttu-id="2a28b-302">Em **Configurar o Controle de Política de Preferências de Privacidade,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-302">In **Configure Privacy Preferences Policy Control** select **Configure**.</span></span>

    ![Imagem do controle de política de privacidade de configuração](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. <span data-ttu-id="2a28b-304">No **Controle de Política de Preferências de Privacidade,** insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-304">In **Privacy Preferences Policy Control**, enter the following details:</span></span>

    - <span data-ttu-id="2a28b-305">Identificador: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="2a28b-305">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="2a28b-306">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="2a28b-306">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="2a28b-307">Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="2a28b-307">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>


    ![Imagem de configuração definindo detalhes de controle de política de preferência de privacidade](images/22cb439de958101c0a12f3038f905b27.png)

6. <span data-ttu-id="2a28b-309">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-309">Select **+ Add**.</span></span>

    ![Imagem da configuração de configuração adicionar política do sistema todos os arquivos](images/bd93e78b74c2660a0541af4690dd9485.png)

    - <span data-ttu-id="2a28b-311">Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="2a28b-311">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="2a28b-312">Em "access": Definir como **Permitir**</span><span class="sxs-lookup"><span data-stu-id="2a28b-312">Under "access": Set to **Allow**</span></span>

7. <span data-ttu-id="2a28b-313">Selecione **Salvar** (não o da parte inferior direita).</span><span class="sxs-lookup"><span data-stu-id="2a28b-313">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagem da configuração configuração salvar imagens](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. <span data-ttu-id="2a28b-315">Clique na `+` entrada ao lado do App **Access** para adicionar uma nova entrada.</span><span class="sxs-lookup"><span data-stu-id="2a28b-315">Click the `+` sign next to **App Access** to add a new entry.</span></span>

    ![Imagem da configuração de configuração de acesso ao aplicativo](images/tcc-add-entry.png)

9. <span data-ttu-id="2a28b-317">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-317">Enter the following details:</span></span>

    - <span data-ttu-id="2a28b-318">Identificador: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="2a28b-318">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="2a28b-319">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="2a28b-319">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="2a28b-320">Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="2a28b-320">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

10. <span data-ttu-id="2a28b-321">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-321">Select **+ Add**.</span></span>

    ![Imagem da configuração de configuração tcc epsext entry](images/tcc-epsext-entry.png)

    - <span data-ttu-id="2a28b-323">Em Aplicativo ou serviço: Definir como **SystemPolicyAllFiles**</span><span class="sxs-lookup"><span data-stu-id="2a28b-323">Under App or service: Set to **SystemPolicyAllFiles**</span></span>

    - <span data-ttu-id="2a28b-324">Em "access": Definir como **Permitir**</span><span class="sxs-lookup"><span data-stu-id="2a28b-324">Under "access": Set to **Allow**</span></span>

11. <span data-ttu-id="2a28b-325">Selecione **Salvar** (não o da parte inferior direita).</span><span class="sxs-lookup"><span data-stu-id="2a28b-325">Select **Save** (not the one at the bottom right).</span></span>

    ![Imagem da configuração de configuração tcc epsext image2](images/tcc-epsext-entry2.png)

12. <span data-ttu-id="2a28b-327">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-327">Select the **Scope** tab.</span></span>

    ![Imagem do escopo de configuração](images/2c49b16cd112729b3719724f581e6882.png)

13. <span data-ttu-id="2a28b-329">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-329">Select **+ Add**.</span></span>

    ![Imagem da configuração addimage de configuração](images/57cef926d1b9260fb74a5f460cee887a.png)

14. <span data-ttu-id="2a28b-331">Selecione **Grupos de >** em **Nome** do Grupo > selecione **MachineGroup da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-331">Select **Computer Groups** > under **Group Name** > select **Contoso's MachineGroup**.</span></span> 

    ![Imagem da configuração de configuração contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. <span data-ttu-id="2a28b-333">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-333">Select **Add**.</span></span> 

16. <span data-ttu-id="2a28b-334">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-334">Select **Save**.</span></span> 
    
17. <span data-ttu-id="2a28b-335">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-335">Select **Done**.</span></span>
    
    ![Imagem da configuração donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Imagem da configuração donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

<span data-ttu-id="2a28b-338">Como alternativa, você pode baixar [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) e enviá-lo para Perfis de Configuração JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="2a28b-338">Alternatively, you can download [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="2a28b-339">Etapa 7: Aprovar extensão de kernel para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-339">Step 7: Approve Kernel extension for Microsoft Defender for Endpoint</span></span>

> [!CAUTION]
> <span data-ttu-id="2a28b-340">Os dispositivos Apple Silicon (M1) não suportam KEXT.</span><span class="sxs-lookup"><span data-stu-id="2a28b-340">Apple Silicon (M1) devices do not support KEXT.</span></span> <span data-ttu-id="2a28b-341">A instalação de um perfil de configuração que consiste em políticas KEXT falhará nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2a28b-341">Installation of a configuration profile consisting KEXT policies will fail on these devices.</span></span>

1. <span data-ttu-id="2a28b-342">Nos **Perfis de Configuração,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-342">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="2a28b-344">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-344">Enter the following details:</span></span>

    <span data-ttu-id="2a28b-345">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-345">**General**</span></span> 
    
    - <span data-ttu-id="2a28b-346">Nome: Extensão de Kernel MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="2a28b-346">Name: MDATP MDAV Kernel Extension</span></span>
    - <span data-ttu-id="2a28b-347">Descrição: extensão de kernel MDATP (kext)</span><span class="sxs-lookup"><span data-stu-id="2a28b-347">Description: MDATP kernel extension (kext)</span></span>
    - <span data-ttu-id="2a28b-348">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a28b-348">Category: None</span></span>
    - <span data-ttu-id="2a28b-349">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="2a28b-349">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="2a28b-350">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="2a28b-350">Level: Computer Level</span></span>

    ![Imagem das configurações do kernel mdatpmdav](images/24e290f5fc309932cf41f3a280d22c14.png)

3. <span data-ttu-id="2a28b-352">Em **Configurar Extensões de Kernel Aprovados,** **selecione Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-352">In **Configure Approved Kernel Extensions** select **Configure**.</span></span>

    ![Imagem das configurações do kernel ext aprovado](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. <span data-ttu-id="2a28b-354">Em **Extensões de Kernel Aprovadas** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-354">In **Approved Kernel Extensions** Enter the following details:</span></span>

    - <span data-ttu-id="2a28b-355">Nome para exibição: Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="2a28b-355">Display Name: Microsoft Corp.</span></span>
    - <span data-ttu-id="2a28b-356">ID da equipe: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="2a28b-356">Team ID: UBF8T346G9</span></span>

    ![Imagem das configurações de extensão do kernel do appr](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. <span data-ttu-id="2a28b-358">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-358">Select the **Scope** tab.</span></span>

    ![Imagem da guia de escopo de configurações img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="2a28b-360">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-360">Select **+ Add**.</span></span>

7. <span data-ttu-id="2a28b-361">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-361">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="2a28b-362">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-362">Select **+ Add**.</span></span>

    ![Imagem das configurações configurações adicionam imagens](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="2a28b-364">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-364">Select **Save**.</span></span>

    ![Imagem das configurações saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. <span data-ttu-id="2a28b-366">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-366">Select **Done**.</span></span>

    ![Imagem das configurações doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

<span data-ttu-id="2a28b-368">Como alternativa, você pode baixar [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) e enviá-lo para Perfis de Configuração JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="2a28b-368">Alternatively, you can download [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="2a28b-369">Etapa 8: Aprovar extensões do sistema para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a28b-369">Step 8: Approve System extensions for Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="2a28b-370">Nos **Perfis de Configuração,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-370">In the **Configuration Profiles**, select **+ New**.</span></span>

    ![Uma captura de tela de uma postagem de mídia social Descrição gerada automaticamente](images/6c8b406ee224335a8c65d06953dc756e.png)

2. <span data-ttu-id="2a28b-372">Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-372">Enter the following details:</span></span>

    <span data-ttu-id="2a28b-373">**Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-373">**General**</span></span>
    
    - <span data-ttu-id="2a28b-374">Nome: Extensões do Sistema MDATP MDAV</span><span class="sxs-lookup"><span data-stu-id="2a28b-374">Name: MDATP MDAV System Extensions</span></span>
    - <span data-ttu-id="2a28b-375">Descrição: extensões do sistema MDATP</span><span class="sxs-lookup"><span data-stu-id="2a28b-375">Description: MDATP system extensions</span></span>
    - <span data-ttu-id="2a28b-376">Categoria: Nenhum</span><span class="sxs-lookup"><span data-stu-id="2a28b-376">Category: None</span></span>
    - <span data-ttu-id="2a28b-377">Método Distribution: Install Automatically</span><span class="sxs-lookup"><span data-stu-id="2a28b-377">Distribution Method: Install Automatically</span></span>
    - <span data-ttu-id="2a28b-378">Nível: Nível do computador</span><span class="sxs-lookup"><span data-stu-id="2a28b-378">Level: Computer Level</span></span>

    ![Imagem das configurações sysext novo prof](images/sysext-new-profile.png)

3. <span data-ttu-id="2a28b-380">Em **Extensões do Sistema,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-380">In **System Extensions** select **Configure**.</span></span>

   ![Imagem de configuração configurações sysext config](images/sysext-configure.png)

4. <span data-ttu-id="2a28b-382">Em **Extensões do Sistema,** insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-382">In **System Extensions** enter the following details:</span></span>

   - <span data-ttu-id="2a28b-383">Nome da exibição: Microsoft Corp. Extensões do sistema</span><span class="sxs-lookup"><span data-stu-id="2a28b-383">Display Name: Microsoft Corp. System Extensions</span></span>
   - <span data-ttu-id="2a28b-384">Tipos de extensão do sistema: Extensões permitidas do sistema</span><span class="sxs-lookup"><span data-stu-id="2a28b-384">System Extension Types: Allowed System Extensions</span></span>
   - <span data-ttu-id="2a28b-385">Identificador de equipe: UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="2a28b-385">Team Identifier: UBF8T346G9</span></span>
   - <span data-ttu-id="2a28b-386">Extensões de sistema permitidas:</span><span class="sxs-lookup"><span data-stu-id="2a28b-386">Allowed System Extensions:</span></span>
     - <span data-ttu-id="2a28b-387">**com.microsoft.wdav.epsext**</span><span class="sxs-lookup"><span data-stu-id="2a28b-387">**com.microsoft.wdav.epsext**</span></span>
     - <span data-ttu-id="2a28b-388">**com.microsoft.wdav.netext**</span><span class="sxs-lookup"><span data-stu-id="2a28b-388">**com.microsoft.wdav.netext**</span></span>

    ![Imagem das configurações sysextconfig2](images/sysext-configure2.png)

5. <span data-ttu-id="2a28b-390">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-390">Select the **Scope** tab.</span></span>

    ![Imagem de escopo de configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

6. <span data-ttu-id="2a28b-392">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-392">Select **+ Add**.</span></span>

7. <span data-ttu-id="2a28b-393">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-393">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

8. <span data-ttu-id="2a28b-394">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-394">Select **+ Add**.</span></span>

   ![Imagem de addima de configurações de configuração](images/0dde8a4c41110dbc398c485433a81359.png)

9. <span data-ttu-id="2a28b-396">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-396">Select **Save**.</span></span>

   ![Imagem do escopo sysext das configurações](images/sysext-scope.png)

10. <span data-ttu-id="2a28b-398">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-398">Select **Done**.</span></span>

    ![Imagem das configurações sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a><span data-ttu-id="2a28b-400">Etapa 9: Configurar a Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="2a28b-400">Step 9: Configure Network Extension</span></span>

<span data-ttu-id="2a28b-401">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade para Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2a28b-401">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="2a28b-402">A política a seguir permite que a extensão de rede execute essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2a28b-402">The following policy allows the network extension to perform this functionality.</span></span>

<span data-ttu-id="2a28b-403">Essas etapas são aplicáveis ao macOS 10.15 (Catalina) ou mais novo.</span><span class="sxs-lookup"><span data-stu-id="2a28b-403">These steps are applicable of macOS 10.15 (Catalina) or newer.</span></span>

1. <span data-ttu-id="2a28b-404">No painel Jamf Pro, selecione **Computadores** e, em seguida, **Perfis de Configuração.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-404">In the Jamf Pro dashboard, select **Computers**, then **Configuration Profiles**.</span></span>

2. <span data-ttu-id="2a28b-405">Clique **em Novo** e insira os seguintes detalhes para **Opções**:</span><span class="sxs-lookup"><span data-stu-id="2a28b-405">Click **New**, and enter the following details for **Options**:</span></span>

    - <span data-ttu-id="2a28b-406">Guia **Geral**:</span><span class="sxs-lookup"><span data-stu-id="2a28b-406">Tab **General**:</span></span> 
        - <span data-ttu-id="2a28b-407">**Nome**: Extensão de Rede do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2a28b-407">**Name**: Microsoft Defender ATP Network Extension</span></span>
        - <span data-ttu-id="2a28b-408">**Descrição**: macOS 10.15 (Catalina) ou mais novo</span><span class="sxs-lookup"><span data-stu-id="2a28b-408">**Description**: macOS 10.15 (Catalina) or newer</span></span>
        - <span data-ttu-id="2a28b-409">**Categoria**: Nenhum *(padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-409">**Category**: None *(default)*</span></span>
        - <span data-ttu-id="2a28b-410">**Método Distribution**: Instalar Automaticamente *(padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-410">**Distribution Method**: Install Automatically *(default)*</span></span>
        - <span data-ttu-id="2a28b-411">**Nível**: Nível do *computador (padrão)*</span><span class="sxs-lookup"><span data-stu-id="2a28b-411">**Level**: Computer Level *(default)*</span></span>

    - <span data-ttu-id="2a28b-412">Filtro **de Conteúdo de Tabulação**:</span><span class="sxs-lookup"><span data-stu-id="2a28b-412">Tab **Content Filter**:</span></span>
        - <span data-ttu-id="2a28b-413">**Nome do filtro**: Filtro de Conteúdo do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="2a28b-413">**Filter Name**: Microsoft Defender ATP Content Filter</span></span>
        - <span data-ttu-id="2a28b-414">**Identificador**: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="2a28b-414">**Identifier**: `com.microsoft.wdav`</span></span>
        - <span data-ttu-id="2a28b-415">Deixar **Endereço de Serviço,** **Organização,** **Nome de Usuário,** **Senha,** **Certificado** em branco (**Incluir** não *está* selecionado)</span><span class="sxs-lookup"><span data-stu-id="2a28b-415">Leave **Service Address**, **Organization**, **User Name**, **Password**, **Certificate** blank (**Include** is *not* selected)</span></span>
        - <span data-ttu-id="2a28b-416">**Ordem de Filtro**: Inspector</span><span class="sxs-lookup"><span data-stu-id="2a28b-416">**Filter Order**: Inspector</span></span>
        - <span data-ttu-id="2a28b-417">**Filtro soquete**: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="2a28b-417">**Socket Filter**: `com.microsoft.wdav.netext`</span></span>
        - <span data-ttu-id="2a28b-418">**Requisito designado do filtro de soquete:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="2a28b-418">**Socket Filter Designated Requirement**: `identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
        - <span data-ttu-id="2a28b-419">Deixar **campos de Filtro de** Rede em branco (**Incluir** não *está* selecionado)</span><span class="sxs-lookup"><span data-stu-id="2a28b-419">Leave **Network Filter** fields blank (**Include** is *not* selected)</span></span>

        <span data-ttu-id="2a28b-420">Observe que **Os valores exatos de Identificador,** **Filtro de Soquete** e Filtro **de Soquete designados,** conforme especificado acima.</span><span class="sxs-lookup"><span data-stu-id="2a28b-420">Note that **Identifier**, **Socket Filter** and **Socket Filter Designated Requirement** exact values as specified above.</span></span>

        ![Imagem das configurações mdatpmdav](images/netext-create-profile.png)

3. <span data-ttu-id="2a28b-422">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-422">Select the **Scope** tab.</span></span>

   ![Guia Descarr da imagem das configurações](images/0df36fc308ba569db204ee32db3fb40a.png)

4. <span data-ttu-id="2a28b-424">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-424">Select **+ Add**.</span></span>

5. <span data-ttu-id="2a28b-425">Selecione **Grupos de >** em Nome **do** Grupo > selecione Grupo de Máquinas **da Contoso.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-425">Select **Computer Groups** > under **Group Name** > select **Contoso's Machine Group**.</span></span>

6. <span data-ttu-id="2a28b-426">Selecione **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-426">Select **+ Add**.</span></span>

    ![Imagem das configurações adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. <span data-ttu-id="2a28b-428">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-428">Select **Save**.</span></span>

    ![Imagem das configurações savimg netextscop](images/netext-scope.png)

8. <span data-ttu-id="2a28b-430">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-430">Select **Done**.</span></span>

    ![Imagem das configurações netextfinal](images/netext-final.png)

<span data-ttu-id="2a28b-432">Como alternativa, você pode baixar [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) e carregar nos Perfis de Configuração DO JAMF conforme descrito em [Deploying Custom Configuration Profiles using Jamf Pro| Método 2: Carregar um Perfil de Configuração para Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span><span class="sxs-lookup"><span data-stu-id="2a28b-432">Alternatively, you can download [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) and upload it to JAMF Configuration Profiles as described in [Deploying Custom Configuration Profiles using Jamf Pro|Method 2: Upload a Configuration Profile to Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).</span></span>

## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2a28b-433">Etapa 10: Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="2a28b-433">Step 10: Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>
<span data-ttu-id="2a28b-434">Siga as instruções em [Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span><span class="sxs-lookup"><span data-stu-id="2a28b-434">Follow the instructions on [Schedule scans with Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).</span></span>

## <a name="step-11-deploy-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="2a28b-435">Etapa 11: Implantar o Microsoft Defender para Ponto de Extremidade para macOS</span><span class="sxs-lookup"><span data-stu-id="2a28b-435">Step 11: Deploy Microsoft Defender for Endpoint for macOS</span></span>

1. <span data-ttu-id="2a28b-436">Navegue até onde você salvou `wdav.pkg` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-436">Navigate to where you saved `wdav.pkg`.</span></span>

    ![Imagem do explorador de arquivos wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. <span data-ttu-id="2a28b-438">Renomeie-o para `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-438">Rename it to `wdav_MDM_Contoso_200329.pkg`.</span></span>

    ![Imagem do explorador de arquivos1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. <span data-ttu-id="2a28b-440">Abra o painel Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="2a28b-440">Open the Jamf Pro dashboard.</span></span>

    ![Imagem das configurações jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. <span data-ttu-id="2a28b-442">Selecione o computador e clique no ícone de engrenagem na parte superior e selecione **Gerenciamento de Computador**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-442">Select your computer and click the gear icon at the top, then select **Computer Management**.</span></span>

    ![Imagem das configurações compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. <span data-ttu-id="2a28b-444">Em **Pacotes,** selecione **+ Novo**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-444">In **Packages**, select **+ New**.</span></span> 
    <span data-ttu-id="2a28b-445">![Uma imagem que contém a descrição do pacote gerado automaticamente automaticamente](images/57aa4d21e2ccc65466bf284701d4e961.png)</span><span class="sxs-lookup"><span data-stu-id="2a28b-445">![A picture containing bird Description automatically generated package new](images/57aa4d21e2ccc65466bf284701d4e961.png)</span></span>

6. <span data-ttu-id="2a28b-446">Em **Novo Pacote** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-446">In **New Package** Enter the following details:</span></span>

    <span data-ttu-id="2a28b-447">**Guia Geral**</span><span class="sxs-lookup"><span data-stu-id="2a28b-447">**General tab**</span></span>
    - <span data-ttu-id="2a28b-448">Nome da exibição: deixe em branco por enquanto.</span><span class="sxs-lookup"><span data-stu-id="2a28b-448">Display Name: Leave it blank for now.</span></span> <span data-ttu-id="2a28b-449">Porque ele será redefinido quando você escolher seu pkg.</span><span class="sxs-lookup"><span data-stu-id="2a28b-449">Because it will be reset when you choose your pkg.</span></span>
    - <span data-ttu-id="2a28b-450">Categoria: Nenhum (padrão)</span><span class="sxs-lookup"><span data-stu-id="2a28b-450">Category: None (default)</span></span>
    - <span data-ttu-id="2a28b-451">Nome do arquivo: Escolher Arquivo</span><span class="sxs-lookup"><span data-stu-id="2a28b-451">Filename: Choose File</span></span>

    ![Imagem da guia geral configurações](images/21de3658bf58b1b767a17358a3f06341.png)

    <span data-ttu-id="2a28b-453">Abra o arquivo e aponte para `wdav.pkg` ou `wdav_MDM_Contoso_200329.pkg` .</span><span class="sxs-lookup"><span data-stu-id="2a28b-453">Open the file and point it to `wdav.pkg` or `wdav_MDM_Contoso_200329.pkg`.</span></span>
    
    ![Uma captura de tela de uma tela do computador Descrição gerada automaticamente](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. <span data-ttu-id="2a28b-455">Selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-455">Select **Open**.</span></span> <span data-ttu-id="2a28b-456">De definir **o Nome de Exibição** **como Proteção Avançada contra Ameaças do Microsoft Defender e o Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-456">Set the **Display Name** to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    <span data-ttu-id="2a28b-457">**O Arquivo de Manifesto** não é necessário.</span><span class="sxs-lookup"><span data-stu-id="2a28b-457">**Manifest File** is not required.</span></span> <span data-ttu-id="2a28b-458">A Proteção Avançada contra Ameaças do Microsoft Defender funciona sem o Arquivo de Manifesto.</span><span class="sxs-lookup"><span data-stu-id="2a28b-458">Microsoft Defender Advanced Threat Protection works without Manifest File.</span></span>
    
    <span data-ttu-id="2a28b-459">**Guia Opções**</span><span class="sxs-lookup"><span data-stu-id="2a28b-459">**Options tab**</span></span><br> <span data-ttu-id="2a28b-460">Mantenha valores padrão.</span><span class="sxs-lookup"><span data-stu-id="2a28b-460">Keep default values.</span></span>

    <span data-ttu-id="2a28b-461">**Guia Limitações**</span><span class="sxs-lookup"><span data-stu-id="2a28b-461">**Limitations tab**</span></span><br> <span data-ttu-id="2a28b-462">Mantenha valores padrão.</span><span class="sxs-lookup"><span data-stu-id="2a28b-462">Keep default values.</span></span>
    
     ![Guia de limitação de configurações da imagem](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. <span data-ttu-id="2a28b-464">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-464">Select **Save**.</span></span> <span data-ttu-id="2a28b-465">O pacote é carregado para o Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="2a28b-465">The package is uploaded to Jamf Pro.</span></span> 

   ![Imagem das configurações pacote upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   <span data-ttu-id="2a28b-467">Pode levar alguns minutos para o pacote estar disponível para implantação.</span><span class="sxs-lookup"><span data-stu-id="2a28b-467">It can take a few minutes for the package to be available for deployment.</span></span>
   
   ![Imagem das configurações empacotam upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. <span data-ttu-id="2a28b-469">Navegue até **a página Políticas.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-469">Navigate to the **Policies** page.</span></span>

    ![Imagem das configurações de configurações de polônias](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. <span data-ttu-id="2a28b-471">Selecione **+ Novo** para criar uma nova política.</span><span class="sxs-lookup"><span data-stu-id="2a28b-471">Select **+ New** to create a new policy.</span></span>

    ![Imagem das configurações configurações nova política](images/847b70e54ed04787e415f5180414b310.png)


11. <span data-ttu-id="2a28b-473">Em **Geral** Insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2a28b-473">In **General** Enter the following details:</span></span>

    - <span data-ttu-id="2a28b-474">Nome para exibição: MDATP Onboarding Contoso 200329 v100.86.92 ou posterior</span><span class="sxs-lookup"><span data-stu-id="2a28b-474">Display name: MDATP Onboarding Contoso 200329 v100.86.92 or later</span></span>

    ![<span data-ttu-id="2a28b-475">Imagem das configuraçõesmdatponboard</span><span class="sxs-lookup"><span data-stu-id="2a28b-475">Image of configuration settingsmdatponboard</span></span> ](images/625ba6d19e8597f05e4907298a454d28.png)

12. <span data-ttu-id="2a28b-476">Selecione **Check-in recorrente**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-476">Select **Recurring Check-in**.</span></span> 
    
    ![Imagem de configurações configurações recorrem à verificação](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. <span data-ttu-id="2a28b-478">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-478">Select **Save**.</span></span> 
 
14. <span data-ttu-id="2a28b-479">Selecione **Pacotes > Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-479">Select **Packages > Configure**.</span></span>
 
    ![Imagem do pacote de configurações configurações](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. <span data-ttu-id="2a28b-481">Selecione o **botão Adicionar** ao lado da Proteção Avançada contra Ameaças do Microsoft Defender e do Microsoft **Defender Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-481">Select the **Add** button next to **Microsoft Defender Advanced Threat Protection and Microsoft Defender Antivirus**.</span></span>

    ![Imagem das configurações MDATP e MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. <span data-ttu-id="2a28b-483">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-483">Select **Save**.</span></span>

    ![Imagem das configurações de configuraçãossavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. <span data-ttu-id="2a28b-485">Selecione a **guia Escopo.**</span><span class="sxs-lookup"><span data-stu-id="2a28b-485">Select the **Scope** tab.</span></span>  

    ![Imagem das configurações scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. <span data-ttu-id="2a28b-487">Selecione os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="2a28b-487">Select the target computers.</span></span>

    ![Imagem das configurações tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    <span data-ttu-id="2a28b-489">**Scope**</span><span class="sxs-lookup"><span data-stu-id="2a28b-489">**Scope**</span></span>
    
    <span data-ttu-id="2a28b-490">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-490">Select **Add**.</span></span>
    
    ![Imagem das configurações do ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Imagem das configurações do ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    <span data-ttu-id="2a28b-493">**Autoatend**</span><span class="sxs-lookup"><span data-stu-id="2a28b-493">**Self-Service**</span></span>
    
    ![Imagem de autoatendiço de configurações](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. <span data-ttu-id="2a28b-495">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2a28b-495">Select **Done**.</span></span> 

    ![Imagem das configurações do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Imagem das configurações do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




