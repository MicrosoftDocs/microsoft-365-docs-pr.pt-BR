---
title: Implantação baseada no Intune para o Microsoft Defender para Ponto de Extremidade no macOS
description: Instale o Microsoft Defender para Ponto de Extremidade no macOS, usando o Microsoft Intune.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: dbb4e3a558256f19594ab0aa4efbd2c9eed6b7f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764210"
---
# <a name="intune-based-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="2b13e-104">Implantação baseada no Intune para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="2b13e-104">Intune-based deployment for Microsoft Defender for Endpoint on macOS</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> [!NOTE]
> <span data-ttu-id="2b13e-105">Esta documentação explica o método herdados para implantar e configurar o Microsoft Defender para Ponto de Extremidade em dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="2b13e-105">This documentation explains the legacy method for deploying and configuring Microsoft Defender for Endpoint on macOS devices.</span></span> <span data-ttu-id="2b13e-106">A experiência nativa agora está disponível no console do MEM.</span><span class="sxs-lookup"><span data-stu-id="2b13e-106">The native experience is now available in the MEM console.</span></span> <span data-ttu-id="2b13e-107">A versão da interface do usuário nativa no console do MEM oferece aos administradores uma maneira muito mais simples de configurar e implantar o aplicativo e enviá-lo para dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="2b13e-107">The release of the native UI in the MEM console provide admins with a much simpler way to configure and deploy the application and send it down to macOS devices.</span></span> <br> <br>
><span data-ttu-id="2b13e-108">A postagem [do blog MEM simplifica a implantação do Microsoft Defender para Endpoint para macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explica os novos recursos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-108">The blog post [MEM simplifies deployment of Microsoft Defender for Endpoint for macOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/microsoft-endpoint-manager-simplifies-deployment-of-microsoft/ba-p/1322995) explains the new features.</span></span> <span data-ttu-id="2b13e-109">Para configurar o aplicativo, vá para Configurações do Microsoft Defender para Ponto de [Extremidade no macOS no Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span><span class="sxs-lookup"><span data-stu-id="2b13e-109">To configure the app, go to [Settings for Microsoft Defender for Endpoint on macOS in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/antivirus-microsoft-defender-settings-macos).</span></span> <span data-ttu-id="2b13e-110">Para implantar o aplicativo, vá para Adicionar o Microsoft Defender para Ponto de Extremidade a [dispositivos macOS usando o Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span><span class="sxs-lookup"><span data-stu-id="2b13e-110">To deploy the app, go to [Add Microsoft Defender for Endpoint to macOS devices using Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos).</span></span>

<span data-ttu-id="2b13e-111">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2b13e-111">**Applies to:**</span></span>

- [<span data-ttu-id="2b13e-112">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="2b13e-112">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

<span data-ttu-id="2b13e-113">Este tópico descreve como implantar o Microsoft Defender para Ponto de Extremidade no macOS por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="2b13e-113">This topic describes how to deploy Microsoft Defender for Endpoint on macOS through Intune.</span></span> <span data-ttu-id="2b13e-114">Uma implantação bem-sucedida requer a conclusão de todas as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="2b13e-114">A successful deployment requires the completion of all of the following steps:</span></span>

1. [<span data-ttu-id="2b13e-115">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="2b13e-115">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
1. [<span data-ttu-id="2b13e-116">Configuração de dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="2b13e-116">Client device setup</span></span>](#client-device-setup)
1. [<span data-ttu-id="2b13e-117">Aprovar extensões do sistema</span><span class="sxs-lookup"><span data-stu-id="2b13e-117">Approve system extensions</span></span>](#approve-system-extensions)
1. [<span data-ttu-id="2b13e-118">Criar perfis de configuração do sistema</span><span class="sxs-lookup"><span data-stu-id="2b13e-118">Create System Configuration profiles</span></span>](#create-system-configuration-profiles)
1. [<span data-ttu-id="2b13e-119">Publicar aplicativo</span><span class="sxs-lookup"><span data-stu-id="2b13e-119">Publish application</span></span>](#publish-application)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="2b13e-120">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="2b13e-120">Prerequisites and system requirements</span></span>

<span data-ttu-id="2b13e-121">Antes de começar, consulte a página principal do Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.</span><span class="sxs-lookup"><span data-stu-id="2b13e-121">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>


## <a name="overview"></a><span data-ttu-id="2b13e-122">Visão geral</span><span class="sxs-lookup"><span data-stu-id="2b13e-122">Overview</span></span>

<span data-ttu-id="2b13e-123">A tabela a seguir resume as etapas necessárias para implantar e gerenciar o Microsoft Defender para Ponto de Extremidade em Macs, por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="2b13e-123">The following table summarizes the steps you would need to take to deploy and manage Microsoft Defender for Endpoint on Macs, via Intune.</span></span> <span data-ttu-id="2b13e-124">Etapas mais detalhadas estão disponíveis abaixo.</span><span class="sxs-lookup"><span data-stu-id="2b13e-124">More detailed steps are available below.</span></span>

| <span data-ttu-id="2b13e-125">Etapa</span><span class="sxs-lookup"><span data-stu-id="2b13e-125">Step</span></span> | <span data-ttu-id="2b13e-126">Exemplo de nomes de arquivo</span><span class="sxs-lookup"><span data-stu-id="2b13e-126">Sample file names</span></span> | <span data-ttu-id="2b13e-127">BundleIdentifier</span><span class="sxs-lookup"><span data-stu-id="2b13e-127">BundleIdentifier</span></span> |
|-|-|-|
| [<span data-ttu-id="2b13e-128">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="2b13e-128">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="2b13e-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-129">WindowsDefenderATPOnboarding__MDATP_wdav.atp.xml</span></span> | <span data-ttu-id="2b13e-130">com.microsoft.wdav.atp</span><span class="sxs-lookup"><span data-stu-id="2b13e-130">com.microsoft.wdav.atp</span></span> |
| [<span data-ttu-id="2b13e-131">Aprovar Extensão do Sistema para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2b13e-131">Approve System Extension for Microsoft Defender for Endpoint</span></span>](#approve-system-extensions) | <span data-ttu-id="2b13e-132">MDATP_SysExt.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-132">MDATP_SysExt.xml</span></span> | <span data-ttu-id="2b13e-133">N/D</span><span class="sxs-lookup"><span data-stu-id="2b13e-133">N/A</span></span> |
| [<span data-ttu-id="2b13e-134">Aprovar Extensão de Kernel para o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2b13e-134">Approve Kernel Extension for Microsoft Defender for Endpoint</span></span>](#download-installation-and-onboarding-packages) | <span data-ttu-id="2b13e-135">MDATP_KExt.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-135">MDATP_KExt.xml</span></span> | <span data-ttu-id="2b13e-136">N/D</span><span class="sxs-lookup"><span data-stu-id="2b13e-136">N/A</span></span> |
| [<span data-ttu-id="2b13e-137">Conceder acesso em disco completo ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2b13e-137">Grant full disk access to Microsoft Defender for Endpoint</span></span>](#create-system-configuration-profiles-step-8) | <span data-ttu-id="2b13e-138">MDATP_tcc_Catalina_or_newer.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-138">MDATP_tcc_Catalina_or_newer.xml</span></span> | <span data-ttu-id="2b13e-139">com.microsoft.wdav.tcc</span><span class="sxs-lookup"><span data-stu-id="2b13e-139">com.microsoft.wdav.tcc</span></span> |
| [<span data-ttu-id="2b13e-140">Política de Extensão de Rede</span><span class="sxs-lookup"><span data-stu-id="2b13e-140">Network Extension policy</span></span>](#create-system-configuration-profiles-step-9) | <span data-ttu-id="2b13e-141">MDATP_NetExt.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-141">MDATP_NetExt.xml</span></span> | <span data-ttu-id="2b13e-142">N/D</span><span class="sxs-lookup"><span data-stu-id="2b13e-142">N/A</span></span> |
| [<span data-ttu-id="2b13e-143">Configurar o Microsoft AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="2b13e-143">Configure Microsoft AutoUpdate (MAU)</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-updates#intune) | <span data-ttu-id="2b13e-144">MDATP_Microsoft_AutoUpdate.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-144">MDATP_Microsoft_AutoUpdate.xml</span></span> | <span data-ttu-id="2b13e-145">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="2b13e-145">com.microsoft.autoupdate2</span></span> |
| [<span data-ttu-id="2b13e-146">Configurações do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2b13e-146">Microsoft Defender for Endpoint configuration settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-preferences#intune-profile-1)<br/><br/> <span data-ttu-id="2b13e-147">**Observação:** Se você estiver planejando executar um AV de terceiros para macOS, de acordo `passiveMode` com `true` .</span><span class="sxs-lookup"><span data-stu-id="2b13e-147">**Note:** If you're planning to run a third-party AV for macOS, set `passiveMode` to `true`.</span></span> | <span data-ttu-id="2b13e-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-148">MDATP_WDAV_and_exclusion_settings_Preferences.xml</span></span> | <span data-ttu-id="2b13e-149">com.microsoft.wdav</span><span class="sxs-lookup"><span data-stu-id="2b13e-149">com.microsoft.wdav</span></span> |
| [<span data-ttu-id="2b13e-150">Configurar notificações do Microsoft Defender para Endpoint e MS AutoUpdate (MAU)</span><span class="sxs-lookup"><span data-stu-id="2b13e-150">Configure Microsoft Defender for Endpoint and MS AutoUpdate (MAU) notifications</span></span>](#create-system-configuration-profiles-step-10) | <span data-ttu-id="2b13e-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span><span class="sxs-lookup"><span data-stu-id="2b13e-151">MDATP_MDAV_Tray_and_AutoUpdate2.mobileconfig</span></span> | <span data-ttu-id="2b13e-152">com.microsoft.autoupdate2 ou com.microsoft.wdav.tray</span><span class="sxs-lookup"><span data-stu-id="2b13e-152">com.microsoft.autoupdate2 or com.microsoft.wdav.tray</span></span> |

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="2b13e-153">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="2b13e-153">Download installation and onboarding packages</span></span>

<span data-ttu-id="2b13e-154">Baixe os pacotes de instalação e integração do Centro de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="2b13e-154">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="2b13e-155">No Centro de Segurança do Microsoft Defender, acesse **Configurações**  >  **gerenciamento de**  >  **dispositivos integrando**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-155">In Microsoft Defender Security Center, go to **Settings** > **Device Management** > **Onboarding**.</span></span>

2. <span data-ttu-id="2b13e-156">Defina o sistema operacional como **macOS** e o método de implantação como Gerenciamento de Dispositivo **Móvel / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-156">Set the operating system to **macOS** and the deployment method to **Mobile Device Management / Microsoft Intune**.</span></span>

    ![Captura de tela de configurações de integração](images/atp-mac-install.png)

3. <span data-ttu-id="2b13e-158">Selecione **Baixar pacote de instalação**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-158">Select **Download installation package**.</span></span> <span data-ttu-id="2b13e-159">Salve-o _como wdav.pkg_ em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="2b13e-159">Save it as _wdav.pkg_ to a local directory.</span></span>

4. <span data-ttu-id="2b13e-160">Selecione **Baixar pacote de integração**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-160">Select **Download onboarding package**.</span></span> <span data-ttu-id="2b13e-161">Salve-o _comoWindowsDefenderATPOnboardingPackage.zip_ no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="2b13e-161">Save it as _WindowsDefenderATPOnboardingPackage.zip_ to the same directory.</span></span>

5. <span data-ttu-id="2b13e-162">Baixe **IntuneAppUtil** de [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos) .</span><span class="sxs-lookup"><span data-stu-id="2b13e-162">Download **IntuneAppUtil** from [https://docs.microsoft.com/intune/lob-apps-macos](https://docs.microsoft.com/intune/lob-apps-macos).</span></span>

6. <span data-ttu-id="2b13e-163">Em um prompt de comando, verifique se você tem os três arquivos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-163">From a command prompt, verify that you have the three files.</span></span>
  

    ```bash
    ls -l
    ```

    ```Output
    total 721688
    -rw-r--r--  1 test  staff     269280 Mar 15 11:25 IntuneAppUtil
    -rw-r--r--  1 test  staff      11821 Mar 15 09:23 WindowsDefenderATPOnboardingPackage.zip
    -rw-r--r--  1 test  staff  354531845 Mar 13 08:57 wdav.pkg
    ```
7. <span data-ttu-id="2b13e-164">Extraia o conteúdo dos arquivos .zip:</span><span class="sxs-lookup"><span data-stu-id="2b13e-164">Extract the contents of the .zip files:</span></span>

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    warning:  WindowsDefenderATPOnboardingPackage.zip appears to use backslashes as path separators
      inflating: intune/kext.xml
      inflating: intune/WindowsDefenderATPOnboarding.xml
      inflating: jamf/WindowsDefenderATPOnboarding.plist
    ```

8. <span data-ttu-id="2b13e-165">Tornar IntuneAppUtil um executável:</span><span class="sxs-lookup"><span data-stu-id="2b13e-165">Make IntuneAppUtil an executable:</span></span>

    ```bash
    chmod +x IntuneAppUtil
    ```

9. <span data-ttu-id="2b13e-166">Crie o pacote wdav.pkg.intunemac de wdav.pkg:</span><span class="sxs-lookup"><span data-stu-id="2b13e-166">Create the wdav.pkg.intunemac package from wdav.pkg:</span></span>

    ```bash
    ./IntuneAppUtil -c wdav.pkg -o . -i "com.microsoft.wdav" -n "1.0.0"
    ```
    ```Output
    Microsoft Intune Application Utility for Mac OS X
    Version: 1.0.0.0
    Copyright 2018 Microsoft Corporation

    Creating intunemac file for /Users/test/Downloads/wdav.pkg
    Composing the intunemac file output
    Output written to ./wdav.pkg.intunemac.

    IntuneAppUtil successfully processed "wdav.pkg",
    to deploy refer to the product documentation.
    ```

## <a name="client-device-setup"></a><span data-ttu-id="2b13e-167">Configuração de dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="2b13e-167">Client device setup</span></span>

<span data-ttu-id="2b13e-168">Você não precisa de nenhum provisionamento especial para um dispositivo Mac além de uma instalação padrão [do Portal da Empresa.](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)</span><span class="sxs-lookup"><span data-stu-id="2b13e-168">You don't need any special provisioning for a Mac device beyond a standard [Company Portal installation](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp).</span></span>

1. <span data-ttu-id="2b13e-169">Confirme o gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-169">Confirm device management.</span></span>

   ![Confirmar captura de tela de gerenciamento de dispositivo](images/mdatp-3-confirmdevicemgmt.png)

    <span data-ttu-id="2b13e-171">Selecione **Abrir Preferências do Sistema,** localize **o Perfil** de Gerenciamento na lista e selecione **Aprovar...**. Seu Perfil de Gerenciamento seria exibido como **Verificado**:</span><span class="sxs-lookup"><span data-stu-id="2b13e-171">Select **Open System Preferences**, locate **Management Profile** on the list, and select **Approve...**. Your Management Profile would be displayed as **Verified**:</span></span>

    ![Captura de tela de perfil de gerenciamento](images/mdatp-4-managementprofile.png)

2. <span data-ttu-id="2b13e-173">Selecione **Continuar** e conclua o registro.</span><span class="sxs-lookup"><span data-stu-id="2b13e-173">Select **Continue** and complete the enrollment.</span></span>

   <span data-ttu-id="2b13e-174">Agora você pode registrar mais dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-174">You may now enroll more devices.</span></span> <span data-ttu-id="2b13e-175">Você também pode inscrevi-los mais tarde, depois de terminar de provisionar a configuração do sistema e os pacotes de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-175">You can also enroll them later, after you have finished provisioning system configuration and application packages.</span></span>

3. <span data-ttu-id="2b13e-176">No Intune, abra **Gerenciar**  >  **Dispositivos**  >  **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-176">In Intune, open **Manage** > **Devices** > **All devices**.</span></span> <span data-ttu-id="2b13e-177">Aqui você pode ver seu dispositivo entre os listados:</span><span class="sxs-lookup"><span data-stu-id="2b13e-177">Here you can see your device among those listed:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b13e-178">![Adicionar captura de tela dispositivos](images/mdatp-5-alldevices.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-178">![Add Devices screenshot](images/mdatp-5-alldevices.png)</span></span>

## <a name="approve-system-extensions"></a><span data-ttu-id="2b13e-179">Aprovar extensões do sistema</span><span class="sxs-lookup"><span data-stu-id="2b13e-179">Approve System Extensions</span></span>

<span data-ttu-id="2b13e-180">Para aprovar as extensões do sistema:</span><span class="sxs-lookup"><span data-stu-id="2b13e-180">To approve the system extensions:</span></span>

1. <span data-ttu-id="2b13e-181">No Intune, abra **Gerenciar**  >  **configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-181">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="2b13e-182">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-182">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="2b13e-183">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="2b13e-183">Choose a name for the profile.</span></span> <span data-ttu-id="2b13e-184">Alterar **Platform=macOS** para **Profile type=Extensions**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-184">Change **Platform=macOS** to **Profile type=Extensions**.</span></span> <span data-ttu-id="2b13e-185">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-185">Select **Create**.</span></span>

3. <span data-ttu-id="2b13e-186">Na guia **Noções Básicas,** dê um nome a esse novo perfil.</span><span class="sxs-lookup"><span data-stu-id="2b13e-186">In the **Basics** tab, give a name to this new profile.</span></span>

4. <span data-ttu-id="2b13e-187">Na guia **Configuração de configurações,** adicione as seguintes entradas na seção **Extensões do sistema permitidos:**</span><span class="sxs-lookup"><span data-stu-id="2b13e-187">In the **Configuration settings** tab, add the following entries in the **Allowed system extensions** section:</span></span>

    <span data-ttu-id="2b13e-188">Identificador de pacote</span><span class="sxs-lookup"><span data-stu-id="2b13e-188">Bundle identifier</span></span>         | <span data-ttu-id="2b13e-189">Identificador de equipe</span><span class="sxs-lookup"><span data-stu-id="2b13e-189">Team identifier</span></span>
    --------------------------|----------------
    <span data-ttu-id="2b13e-190">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="2b13e-190">com.microsoft.wdav.epsext</span></span> | <span data-ttu-id="2b13e-191">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="2b13e-191">UBF8T346G9</span></span>
    <span data-ttu-id="2b13e-192">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="2b13e-192">com.microsoft.wdav.netext</span></span> | <span data-ttu-id="2b13e-193">UBF8T346G9</span><span class="sxs-lookup"><span data-stu-id="2b13e-193">UBF8T346G9</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-194">![Captura de tela das configurações de extensão nas configurações da guia Noções Básicas](images/mac-system-extension-intune2.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-194">![Screenshot of the extension settings in Configuration settings on the Basics tab](images/mac-system-extension-intune2.png)</span></span>

5. <span data-ttu-id="2b13e-195">Na guia **Atribuições,** atribua esse perfil a **Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-195">In the **Assignments** tab, assign this profile to **All Users & All devices**.</span></span>

6. <span data-ttu-id="2b13e-196">Revise e crie esse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="2b13e-196">Review and create this configuration profile.</span></span>

## <a name="create-system-configuration-profiles"></a><span data-ttu-id="2b13e-197">Criar perfis de configuração do sistema</span><span class="sxs-lookup"><span data-stu-id="2b13e-197">Create System Configuration profiles</span></span>

1. <span data-ttu-id="2b13e-198">No Intune, abra **Gerenciar**  >  **configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-198">In Intune, open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="2b13e-199">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-199">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="2b13e-200">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="2b13e-200">Choose a name for the profile.</span></span> <span data-ttu-id="2b13e-201">Alterar **Platform=macOS** para **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-201">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="2b13e-202">Selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-202">Select **Configure**.</span></span>

3. <span data-ttu-id="2b13e-203">Abra o perfil de configuração e carregue o intune/kext.xml.</span><span class="sxs-lookup"><span data-stu-id="2b13e-203">Open the configuration profile and upload intune/kext.xml.</span></span> <span data-ttu-id="2b13e-204">Esse arquivo foi criado em uma das seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="2b13e-204">This file was created in one of the preceding sections.</span></span>

4. <span data-ttu-id="2b13e-205">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-205">Select **OK**.</span></span>

    ![Importar uma configuração de um arquivo para o Perfil de Configuração Personalizado](images/mdatp-6-systemconfigurationprofiles.png)

5. <span data-ttu-id="2b13e-207">Selecione **Gerenciar**  >  **atribuições**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-207">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="2b13e-208">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-208">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

6. <span data-ttu-id="2b13e-209">Repita as etapas de 1 a 5 para mais perfis.</span><span class="sxs-lookup"><span data-stu-id="2b13e-209">Repeat steps 1 through 5 for more profiles.</span></span>

7. <span data-ttu-id="2b13e-210">Crie outro perfil, dê um nome e carregue o arquivo do intune/WindowsDefenderATPOnboarding.xml.</span><span class="sxs-lookup"><span data-stu-id="2b13e-210">Create another profile, give it a name, and upload the intune/WindowsDefenderATPOnboarding.xml file.</span></span>

8. <span data-ttu-id="2b13e-211">Baixe **fulldisk.mobileconfig** do [repositório do GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) e salve-o como **tcc.xml**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-211">Download **fulldisk.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) and save it as **tcc.xml**.</span></span> <span data-ttu-id="2b13e-212">Crie outro perfil, dê qualquer nome e carregue esse arquivo nele.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span><span class="sxs-lookup"><span data-stu-id="2b13e-212">Create another profile, give it any name and upload this file to it.<a name="create-system-configuration-profiles-step-8" id = "create-system-configuration-profiles-step-8"></a></span></span>

   > [!CAUTION]
   > <span data-ttu-id="2b13e-213">O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="2b13e-213">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="2b13e-214">A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito.</span><span class="sxs-lookup"><span data-stu-id="2b13e-214">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="2b13e-215">Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b13e-215">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
   >
   > <span data-ttu-id="2b13e-216">Esse perfil de configuração concede acesso total em disco ao Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2b13e-216">This configuration profile grants Full Disk Access to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2b13e-217">Se você configurou anteriormente o Microsoft Defender para Ponto de Extremidade por meio do Intune, recomendamos atualizar a implantação com esse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="2b13e-217">If you previously configured Microsoft Defender for Endpoint through Intune, we recommend you update the deployment with this configuration profile.</span></span>

9. <span data-ttu-id="2b13e-218">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade no macOS inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2b13e-218">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on macOS inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="2b13e-219">A política a seguir permite que a extensão de rede execute essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2b13e-219">The following policy allows the network extension to perform this functionality.</span></span> <span data-ttu-id="2b13e-220">Baixe **netfilter.mobileconfig** do repositório [do GitHub,](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig)salve-o como netext.xml e implante-o usando as mesmas etapas das seções anteriores.</span><span class="sxs-lookup"><span data-stu-id="2b13e-220">Download **netfilter.mobileconfig** from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/netfilter.mobileconfig), save it as netext.xml and deploy it using the same steps as in the previous sections.</span></span> <a name = "create-system-configuration-profiles-step-9" id = "create-system-configuration-profiles-step-9"></a>

10. <span data-ttu-id="2b13e-221">Para permitir que o Microsoft Defender para o Ponto de Extremidade no macOS e o Microsoft Auto Update eximem notificações na interface do usuário no macOS 10.15 (Catalina), baixe do repositório `notif.mobileconfig` [do GitHub](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) e importe-o como uma carga personalizada.</span><span class="sxs-lookup"><span data-stu-id="2b13e-221">To allow Microsoft Defender for Endpoint on macOS and Microsoft Auto Update to display notifications in UI on macOS 10.15 (Catalina), download `notif.mobileconfig` from [our GitHub repository](https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/macos/mobileconfig/profiles/notif.mobileconfig) and import it as a custom payload.</span></span> <a name = "create-system-configuration-profiles-step-10" id = "create-system-configuration-profiles-step-10"></a>

11. <span data-ttu-id="2b13e-222">Selecione **Gerenciar > atribuições**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-222">Select **Manage > Assignments**.</span></span>  <span data-ttu-id="2b13e-223">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-223">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

<span data-ttu-id="2b13e-224">Depois que as alterações do Intune são propagadas para os dispositivos inscritos, você pode vê-las listadas em **Monitor**  >  **Device status**:</span><span class="sxs-lookup"><span data-stu-id="2b13e-224">Once the Intune changes are propagated to the enrolled devices, you can see them listed under **Monitor** > **Device status**:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2b13e-225">![Exibição do status do dispositivo no Monitor](images/mdatp-7-devicestatusblade.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-225">![View of Device Status in Monitor](images/mdatp-7-devicestatusblade.png)</span></span>

## <a name="publish-application"></a><span data-ttu-id="2b13e-226">Publicar aplicativo</span><span class="sxs-lookup"><span data-stu-id="2b13e-226">Publish application</span></span>

1. <span data-ttu-id="2b13e-227">No Intune, abra a folha Gerenciar > **aplicativos cliente.**</span><span class="sxs-lookup"><span data-stu-id="2b13e-227">In Intune, open the **Manage > Client apps** blade.</span></span> <span data-ttu-id="2b13e-228">Selecione **Aplicativos > Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-228">Select **Apps > Add**.</span></span>

2. <span data-ttu-id="2b13e-229">Selecione **Tipo de aplicativo=Outro/Aplicativo de Linha de Negócios.**</span><span class="sxs-lookup"><span data-stu-id="2b13e-229">Select **App type=Other/Line-of-business app**.</span></span>

3. <span data-ttu-id="2b13e-230">Selecione **file=wdav.pkg.intunemac**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-230">Select **file=wdav.pkg.intunemac**.</span></span> <span data-ttu-id="2b13e-231">Selecione **OK** para carregar.</span><span class="sxs-lookup"><span data-stu-id="2b13e-231">Select **OK** to upload.</span></span>

4. <span data-ttu-id="2b13e-232">Selecione **Configurar** e adicionar as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="2b13e-232">Select **Configure** and add the required information.</span></span>

5. <span data-ttu-id="2b13e-233">Use **macOS High Sierra 10.14** como o sistema operacional mínimo.</span><span class="sxs-lookup"><span data-stu-id="2b13e-233">Use **macOS High Sierra 10.14** as the minimum OS.</span></span>

6. <span data-ttu-id="2b13e-234">Definir *Ignorar versão do aplicativo* como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-234">Set *Ignore app version* to **Yes**.</span></span> <span data-ttu-id="2b13e-235">Outras configurações podem ser qualquer valor arbitrário.</span><span class="sxs-lookup"><span data-stu-id="2b13e-235">Other settings can be any arbitrary value.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="2b13e-236">Definir *Ignorar versão do aplicativo* como **Nenhuma** afeta a capacidade do aplicativo de receber atualizações por meio do Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="2b13e-236">Setting *Ignore app version* to **No** impacts the ability of the application to receive updates through Microsoft AutoUpdate.</span></span> <span data-ttu-id="2b13e-237">Consulte [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) para obter informações adicionais sobre como o produto é atualizado.</span><span class="sxs-lookup"><span data-stu-id="2b13e-237">See [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) for additional information about how the product is updated.</span></span>
    >
    > <span data-ttu-id="2b13e-238">Se a versão carregada pelo Intune for menor do que a versão no dispositivo, a versão inferior será instalada, rebaixando efetivamente o Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2b13e-238">If the version uploaded by Intune is lower than the version on the device, then the lower version will be installed, effectively downgrading Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2b13e-239">Isso pode resultar em um aplicativo que não está funcionando.</span><span class="sxs-lookup"><span data-stu-id="2b13e-239">This could result in a non-functioning application.</span></span> <span data-ttu-id="2b13e-240">Consulte [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) para obter informações adicionais sobre como o produto é atualizado.</span><span class="sxs-lookup"><span data-stu-id="2b13e-240">See [Deploy updates for Microsoft Defender for Endpoint on macOS](mac-updates.md) for additional information about how the product is updated.</span></span> <span data-ttu-id="2b13e-241">Se você implantou o Microsoft Defender para Ponto de Extremidade *com Ignorar a* versão do aplicativo definida como **Não**, altere-a para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-241">If you deployed Microsoft Defender for Endpoint with *Ignore app version* set to **No**, please change it to **Yes**.</span></span> <span data-ttu-id="2b13e-242">Se o Microsoft Defender for Endpoint ainda não puder ser instalado em um dispositivo cliente, desinstale o Microsoft Defender para Ponto de Extremidade e pressione a política atualizada.</span><span class="sxs-lookup"><span data-stu-id="2b13e-242">If Microsoft Defender for Endpoint still cannot be installed on a client device, then uninstall Microsoft Defender for Endpoint and push the updated policy.</span></span>
     
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-243">![Exibição de informações do aplicativo no app add](images/mdatp-8-intuneappinfo.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-243">![Display of App information in App add](images/mdatp-8-intuneappinfo.png)</span></span>

7. <span data-ttu-id="2b13e-244">Selecione **OK** e **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-244">Select **OK** and **Add**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-245">![Status do dispositivo mostrado na janela Notificações](images/mdatp-9-intunepkginfo.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-245">![Device status shown in Notifications window](images/mdatp-9-intunepkginfo.png)</span></span>

8. <span data-ttu-id="2b13e-246">Pode levar alguns instantes para carregar o pacote.</span><span class="sxs-lookup"><span data-stu-id="2b13e-246">It may take a few moments to upload the package.</span></span> <span data-ttu-id="2b13e-247">Depois de terminar, selecione o pacote na lista e vá para **Atribuições** e **Adicionar grupo**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-247">After it's done, select the package from the list and go to **Assignments** and **Add group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-248">![Captura de tela de aplicativos cliente](images/mdatp-10-clientapps.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-248">![Client apps screenshot](images/mdatp-10-clientapps.png)</span></span>

9. <span data-ttu-id="2b13e-249">Alterar **o tipo de** atribuição para **Obrigatório.**</span><span class="sxs-lookup"><span data-stu-id="2b13e-249">Change **Assignment type** to **Required**.</span></span>

10. <span data-ttu-id="2b13e-250">Selecione **Grupos Incluídos**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-250">Select **Included Groups**.</span></span> <span data-ttu-id="2b13e-251">Selecione **Tornar esse aplicativo necessário para todos os dispositivos=Sim**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-251">Select **Make this app required for all devices=Yes**.</span></span> <span data-ttu-id="2b13e-252">Selecione **Selecionar grupo para incluir** e adicionar um grupo que contém os usuários que você deseja direcionar.</span><span class="sxs-lookup"><span data-stu-id="2b13e-252">Select **Select group to include** and add a group that contains the users you want to target.</span></span> <span data-ttu-id="2b13e-253">Selecione **OK** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2b13e-253">Select **OK** and **Save**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-254">![Captura de tela de informações de atribuições do Intune](images/mdatp-11-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-254">![Intune assignments info screenshot](images/mdatp-11-assignments.png)</span></span>

11. <span data-ttu-id="2b13e-255">Após algum tempo, o aplicativo será publicado em todos os dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="2b13e-255">After some time the application will be published to all enrolled devices.</span></span> <span data-ttu-id="2b13e-256">Você pode vê-lo listado em **Monitor**  >  **Device**, em **Status de instalação do dispositivo**:</span><span class="sxs-lookup"><span data-stu-id="2b13e-256">You can see it listed in **Monitor** > **Device**, under **Device install status**:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-257">![Captura de tela de status do dispositivo do Intune](images/mdatp-12-deviceinstall.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-257">![Intune device status screenshot](images/mdatp-12-deviceinstall.png)</span></span>

## <a name="verify-client-device-state"></a><span data-ttu-id="2b13e-258">Verificar o estado do dispositivo cliente</span><span class="sxs-lookup"><span data-stu-id="2b13e-258">Verify client device state</span></span>

1. <span data-ttu-id="2b13e-259">Depois que os perfis de configuração são implantados em seus **dispositivos,** abra Perfis de Preferências do Sistema  >   em seu dispositivo Mac.</span><span class="sxs-lookup"><span data-stu-id="2b13e-259">After the configuration profiles are deployed to your devices, open **System Preferences** > **Profiles** on your Mac device.</span></span>

    <span data-ttu-id="2b13e-260">![Captura de tela preferências do sistema](images/mdatp-13-systempreferences.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-260">![System Preferences screenshot](images/mdatp-13-systempreferences.png)</span></span><br/>
    <span data-ttu-id="2b13e-261">![Captura de tela Perfis de Preferências do Sistema](images/mdatp-14-systempreferencesprofiles.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-261">![System Preferences Profiles screenshot](images/mdatp-14-systempreferencesprofiles.png)</span></span>

2. <span data-ttu-id="2b13e-262">Verifique se os perfis de configuração a seguir estão presentes e instalados.</span><span class="sxs-lookup"><span data-stu-id="2b13e-262">Verify that the following configuration profiles are present and installed.</span></span> <span data-ttu-id="2b13e-263">O **Perfil de Gerenciamento** deve ser o perfil do sistema do Intune.</span><span class="sxs-lookup"><span data-stu-id="2b13e-263">The **Management Profile** should be the Intune system profile.</span></span> <span data-ttu-id="2b13e-264">_Wdav-config_ e _wdav-kext_ são perfis de configuração do sistema que foram adicionados ao Intune: Captura de tela ![ perfis](images/mdatp-15-managementprofileconfig.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-264">_Wdav-config_ and _wdav-kext_ are system configuration profiles that were added in Intune: ![Profiles screenshot](images/mdatp-15-managementprofileconfig.png)</span></span>

3. <span data-ttu-id="2b13e-265">Você também deve ver o ícone do Microsoft Defender no canto superior direito:</span><span class="sxs-lookup"><span data-stu-id="2b13e-265">You should also see the Microsoft Defender icon in the top-right corner:</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2b13e-266">![Ícone do Microsoft Defender na captura de tela da barra de status](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="2b13e-266">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2b13e-267">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="2b13e-267">Troubleshooting</span></span>

<span data-ttu-id="2b13e-268">Problema: nenhuma licença encontrada</span><span class="sxs-lookup"><span data-stu-id="2b13e-268">Issue: No license found</span></span>

<span data-ttu-id="2b13e-269">Solução: siga as etapas acima para criar um perfil de dispositivo usando WindowsDefenderATPOnboarding.xml</span><span class="sxs-lookup"><span data-stu-id="2b13e-269">Solution: Follow the steps above to create a device profile using WindowsDefenderATPOnboarding.xml</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="2b13e-270">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="2b13e-270">Logging installation issues</span></span>

<span data-ttu-id="2b13e-271">Para obter mais informações sobre como encontrar o log gerado automaticamente que é criado pelo instalador quando ocorre um [erro,](mac-resources.md#logging-installation-issues)consulte Logging installation issues .</span><span class="sxs-lookup"><span data-stu-id="2b13e-271">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Logging installation issues](mac-resources.md#logging-installation-issues).</span></span>

## <a name="uninstallation"></a><span data-ttu-id="2b13e-272">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="2b13e-272">Uninstallation</span></span>

<span data-ttu-id="2b13e-273">Consulte [Desinstalar](mac-resources.md#uninstalling) para obter detalhes sobre como remover o Microsoft Defender para o Ponto de Extremidade no macOS de dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="2b13e-273">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
