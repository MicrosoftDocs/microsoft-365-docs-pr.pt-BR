---
title: Implantação manual do Microsoft Defender para Ponto de Extremidade no macOS
description: Instale o Microsoft Defender para Ponto de Extremidade no macOS manualmente, a partir da linha de comando.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: d8458f1bacc6577d83878a94c24e649371d90038
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935324"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="cac45-104">Implantação manual do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="cac45-104">Manual deployment for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cac45-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cac45-105">**Applies to:**</span></span>
- [<span data-ttu-id="cac45-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cac45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cac45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cac45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cac45-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cac45-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cac45-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cac45-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="cac45-110">Este tópico descreve como implantar o Microsoft Defender para Ponto de Extremidade no macOS manualmente.</span><span class="sxs-lookup"><span data-stu-id="cac45-110">This topic describes how to deploy Microsoft Defender for Endpoint on macOS manually.</span></span> <span data-ttu-id="cac45-111">Uma implantação bem-sucedida requer a conclusão de todas as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="cac45-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="cac45-112">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="cac45-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="cac45-113">Instalação do aplicativo (macOS 10.15 e versões anteriores)</span><span class="sxs-lookup"><span data-stu-id="cac45-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="cac45-114">Instalação do aplicativo (macOS 11 e versões mais recentes)</span><span class="sxs-lookup"><span data-stu-id="cac45-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="cac45-115">Configuração do cliente</span><span class="sxs-lookup"><span data-stu-id="cac45-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="cac45-116">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="cac45-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="cac45-117">Antes de começar, consulte a página principal do Microsoft Defender para Ponto de Extremidade no [macOS](microsoft-defender-endpoint-mac.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.</span><span class="sxs-lookup"><span data-stu-id="cac45-117">Before you get started, see [the main Microsoft Defender for Endpoint on macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="cac45-118">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="cac45-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="cac45-119">Baixe os pacotes de instalação e integração do Centro de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="cac45-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="cac45-120">No Centro de Segurança do Microsoft Defender, acesse **Configurações > Gerenciamento de Dispositivos > Integração**.</span><span class="sxs-lookup"><span data-stu-id="cac45-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="cac45-121">Na Seção 1 da página, de definir o sistema operacional como **macOS** e o método Deployment como **script local**.</span><span class="sxs-lookup"><span data-stu-id="cac45-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="cac45-122">Na Seção 2 da página, selecione **Baixar pacote de instalação**.</span><span class="sxs-lookup"><span data-stu-id="cac45-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="cac45-123">Salve-o como wdav.pkg em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="cac45-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="cac45-124">Na Seção 2 da página, selecione **Baixar pacote de integração**.</span><span class="sxs-lookup"><span data-stu-id="cac45-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="cac45-125">Salve-o como WindowsDefenderATPOnboardingPackage.zip no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="cac45-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Captura de tela do Centro de Segurança do Microsoft Defender](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="cac45-127">Em um prompt de comando, verifique se você tem os dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="cac45-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="cac45-128">Instalação do aplicativo (macOS 10.15 e versões anteriores)</span><span class="sxs-lookup"><span data-stu-id="cac45-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="cac45-129">Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cac45-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="cac45-130">Navegue até o wdav.pkg baixado no Finder e abra-o.</span><span class="sxs-lookup"><span data-stu-id="cac45-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de tela de instalação do aplicativo1](images/mdatp-28-appinstall.png)

2. <span data-ttu-id="cac45-132">Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="cac45-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Captura de tela de instalação do aplicativo2](images/mdatp-29-appinstalllogin.png)

   > [!IMPORTANT]
   > <span data-ttu-id="cac45-134">Você será solicitado a permitir que um driver da Microsoft seja instalado ("Bloqueio de Extensão do Sistema" ou "Instalação está em espera" ou ambos.</span><span class="sxs-lookup"><span data-stu-id="cac45-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="cac45-135">O driver deve ter permissão para ser instalado.</span><span class="sxs-lookup"><span data-stu-id="cac45-135">The driver must be allowed to be installed.</span></span>

   ![Captura de tela de instalação do aplicativo3](images/mdatp-30-systemextension.png)

3. <span data-ttu-id="cac45-137">Selecione **Abrir Preferências de Segurança** ou Abrir **Preferências do Sistema > Segurança & Privacidade**.</span><span class="sxs-lookup"><span data-stu-id="cac45-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="cac45-138">Selecione **Permitir**:</span><span class="sxs-lookup"><span data-stu-id="cac45-138">Select **Allow**:</span></span>

    ![Captura de tela de janela de segurança e privacidade](images/mdatp-31-securityprivacysettings.png)

   <span data-ttu-id="cac45-140">A instalação continua.</span><span class="sxs-lookup"><span data-stu-id="cac45-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="cac45-141">Se você não selecionar **Permitir**, a instalação prosseguirá após 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="cac45-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="cac45-142">O Microsoft Defender para Ponto de Extremidade será carregado, mas alguns recursos, como proteção em tempo real, serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="cac45-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="cac45-143">Consulte [Solucionar problemas de extensão do kernel](mac-support-kext.md) para obter informações sobre como resolver isso.</span><span class="sxs-lookup"><span data-stu-id="cac45-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="cac45-144">O macOS pode solicitar a reinicialização do dispositivo na primeira instalação do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="cac45-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="cac45-145">A proteção em tempo real não estará disponível até que o dispositivo seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="cac45-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="cac45-146">Instalação do aplicativo (macOS 11 e versões mais recentes)</span><span class="sxs-lookup"><span data-stu-id="cac45-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="cac45-147">Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cac45-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="cac45-148">Navegue até o wdav.pkg baixado no Finder e abra-o.</span><span class="sxs-lookup"><span data-stu-id="cac45-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de tela de instalação do aplicativo4](images/big-sur-install-1.png)

2. <span data-ttu-id="cac45-150">Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="cac45-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="cac45-151">No final do processo de instalação, você será promovido a aprovar as extensões do sistema usadas pelo produto.</span><span class="sxs-lookup"><span data-stu-id="cac45-151">At the end of the installation process, you'll be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="cac45-152">Selecione **Abrir Preferências de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="cac45-152">Select **Open Security Preferences**.</span></span>

    ![Aprovação de extensão do sistema](images/big-sur-install-2.png)

4. <span data-ttu-id="cac45-154">Na janela **Segurança & Privacidade,** selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="cac45-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Preferências de segurança de extensão do sistema1](images/big-sur-install-3.png)

5. <span data-ttu-id="cac45-156">Repita as etapas 3 & 4 para todas as extensões do sistema distribuídas com o Microsoft Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="cac45-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint on Mac.</span></span>

6. <span data-ttu-id="cac45-157">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade no Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="cac45-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint on Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="cac45-158">Quando solicitado a conceder permissões do Microsoft Defender para o Ponto de Extremidade para filtrar o tráfego de rede, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="cac45-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Preferências de segurança de extensão do sistema2](images/big-sur-install-4.png)

7. <span data-ttu-id="cac45-160">Abra **Preferências do** Sistema Segurança & Privacidade e navegue até a guia Privacidade. Conceda permissão de Acesso em Disco Completo para o Microsoft Defender ATP e a Extensão de Segurança do Ponto de Extremidade do  >   Microsoft Defender **ATP.**   </span><span class="sxs-lookup"><span data-stu-id="cac45-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Acesso em disco completo](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="cac45-162">Configuração do cliente</span><span class="sxs-lookup"><span data-stu-id="cac45-162">Client configuration</span></span>

1. <span data-ttu-id="cac45-163">Copie wdav.pkg e MicrosoftDefenderATPOnboardingMacOs.py para o dispositivo onde você implanta o Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="cac45-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint on macOS.</span></span>

    <span data-ttu-id="cac45-164">O dispositivo cliente não está associado ao org_id.</span><span class="sxs-lookup"><span data-stu-id="cac45-164">The client device isn't associated with org_id.</span></span> <span data-ttu-id="cac45-165">Observe que o *atributo org_id* está em branco.</span><span class="sxs-lookup"><span data-stu-id="cac45-165">Note that the *org_id* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="cac45-166">Execute o script Python para instalar o arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="cac45-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="cac45-167">Verifique se o dispositivo agora está associado à sua organização e relata uma ID da organização válida:</span><span class="sxs-lookup"><span data-stu-id="cac45-167">Verify that the device is now associated with your organization and reports a valid org ID:</span></span>

    ```bash
    mdatp health --field org_id
    ```

    <span data-ttu-id="cac45-168">Após a instalação, você verá o ícone do Microsoft Defender na barra de status do macOS no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="cac45-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cac45-169">![Ícone do Microsoft Defender na captura de tela da barra de status](images/mdatp-icon-bar.png)</span><span class="sxs-lookup"><span data-stu-id="cac45-169">![Microsoft Defender icon in status bar screenshot](images/mdatp-icon-bar.png)</span></span>


## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="cac45-170">Como permitir o acesso total ao disco</span><span class="sxs-lookup"><span data-stu-id="cac45-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="cac45-171">O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="cac45-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="cac45-172">A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito.</span><span class="sxs-lookup"><span data-stu-id="cac45-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="cac45-173">Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cac45-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

1. <span data-ttu-id="cac45-174">Para conceder consentimento, abra **o System Preferences**  >  **Security & Privacidade**  >  **Acesso**  >  **total ao disco**.</span><span class="sxs-lookup"><span data-stu-id="cac45-174">To grant consent, open **System Preferences** > **Security & Privacy** > **Privacy** > **Full Disk Access**.</span></span> <span data-ttu-id="cac45-175">Clique no ícone de bloqueio para fazer alterações (parte inferior da caixa de diálogo).</span><span class="sxs-lookup"><span data-stu-id="cac45-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="cac45-176">Selecione Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="cac45-176">Select Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="cac45-177">Execute um teste de detecção de AV para verificar se o dispositivo está corretamente conectado e relatando ao serviço.</span><span class="sxs-lookup"><span data-stu-id="cac45-177">Run an AV detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="cac45-178">Execute as seguintes etapas no dispositivo recém-integrado:</span><span class="sxs-lookup"><span data-stu-id="cac45-178">Perform the following steps on the newly onboarded device:</span></span>

    1. <span data-ttu-id="cac45-179">Verifique se a proteção em tempo real está habilitada (denotada por um resultado de 1 da execução do seguinte comando):</span><span class="sxs-lookup"><span data-stu-id="cac45-179">Ensure that real-time protection is enabled (denoted by a result of 1 from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    1. <span data-ttu-id="cac45-180">Abra uma janela de Terminal.</span><span class="sxs-lookup"><span data-stu-id="cac45-180">Open a Terminal window.</span></span> <span data-ttu-id="cac45-181">Copie e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cac45-181">Copy and execute the following command:</span></span>

        ```bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    1. <span data-ttu-id="cac45-182">O arquivo deve ter sido colocado em quarentena pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="cac45-182">The file should have been quarantined by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="cac45-183">Use o seguinte comando para listar todas as ameaças detectadas:</span><span class="sxs-lookup"><span data-stu-id="cac45-183">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

3. <span data-ttu-id="cac45-184">Execute um teste de detecção de EDR para verificar se o dispositivo está corretamente conectado e relatando ao serviço.</span><span class="sxs-lookup"><span data-stu-id="cac45-184">Run an EDR detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="cac45-185">Execute as seguintes etapas no dispositivo recém-integrado:</span><span class="sxs-lookup"><span data-stu-id="cac45-185">Perform the following steps on the newly onboarded device:</span></span>

   1. <span data-ttu-id="cac45-186">No navegador, como o Microsoft Edge para Mac ou Safari.</span><span class="sxs-lookup"><span data-stu-id="cac45-186">In your browser such as Microsoft Edge for Mac or Safari.</span></span>

   1. <span data-ttu-id="cac45-187">Baixe o MDATP MacOS DIY.zip https://aka.ms/mdatpmacosdiy e extraia.</span><span class="sxs-lookup"><span data-stu-id="cac45-187">Download MDATP MacOS DIY.zip from https://aka.ms/mdatpmacosdiy and extract.</span></span>

      <span data-ttu-id="cac45-188">Você pode ser solicitado:</span><span class="sxs-lookup"><span data-stu-id="cac45-188">You may be prompted:</span></span>

      > <span data-ttu-id="cac45-189">Deseja permitir downloads em "mdatpclientanalyzer.blob.core.windows.net"?</span><span class="sxs-lookup"><span data-stu-id="cac45-189">Do you want to allow downloads on "mdatpclientanalyzer.blob.core.windows.net"?</span></span><br/>
      > <span data-ttu-id="cac45-190">Você pode alterar quais sites podem baixar arquivos em Preferências de Sites.</span><span class="sxs-lookup"><span data-stu-id="cac45-190">You can change which websites can download files in Websites Preferences.</span></span>

4. <span data-ttu-id="cac45-191">Clique **em Permitir**.</span><span class="sxs-lookup"><span data-stu-id="cac45-191">Click **Allow**.</span></span>

5. <span data-ttu-id="cac45-192">Abrir **Downloads**.</span><span class="sxs-lookup"><span data-stu-id="cac45-192">Open **Downloads**.</span></span>

6. <span data-ttu-id="cac45-193">Você deve ver **MDATP MacOS DIY**.</span><span class="sxs-lookup"><span data-stu-id="cac45-193">You should see **MDATP MacOS DIY**.</span></span>

   > [!TIP]
   > <span data-ttu-id="cac45-194">Se você clicar duas vezes, receberá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="cac45-194">If you double-click, you will get the following message:</span></span>
   > 
   > > <span data-ttu-id="cac45-195">**"MDATP MacOS DIY" não pode ser aberto porque o desenvolvedor não pode ser verificador.**</span><span class="sxs-lookup"><span data-stu-id="cac45-195">**"MDATP MacOS DIY" cannot be opened because the developer cannot be verifier.**</span></span><br/>
   > > <span data-ttu-id="cac45-196">O macOS não pode verificar se esse aplicativo está livre de malware.</span><span class="sxs-lookup"><span data-stu-id="cac45-196">macOS cannot verify that this app is free from malware.</span></span><br/>
   > > <span data-ttu-id="cac45-197">**\[ Mover para \] o Cancelamento de** **\[ Lixo \]**</span><span class="sxs-lookup"><span data-stu-id="cac45-197">**\[Move to Trash\]** **\[Cancel\]**</span></span> 
  
7. <span data-ttu-id="cac45-198">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="cac45-198">Click **Cancel**.</span></span>

8. <span data-ttu-id="cac45-199">Clique com o botão direito do **mouse em MDATP MacOS DIY** e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="cac45-199">Right-click **MDATP MacOS DIY**, and then click **Open**.</span></span> 

    <span data-ttu-id="cac45-200">O sistema deve exibir a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="cac45-200">The system should display the following message:</span></span>

    > <span data-ttu-id="cac45-201">**macOS não pode verificar o desenvolvedor **do MDATP MacOS DIY**. Tem certeza de que deseja abri-lo?**</span><span class="sxs-lookup"><span data-stu-id="cac45-201">**macOS cannot verify the developer of **MDATP MacOS DIY**. Are you sure you want to open it?**</span></span><br/>
    > <span data-ttu-id="cac45-202">Ao abrir este aplicativo, você estará substituindo a segurança do sistema que pode expor seu computador e informações pessoais a malware que podem prejudicar seu Mac ou comprometer sua privacidade.</span><span class="sxs-lookup"><span data-stu-id="cac45-202">By opening this app, you will be overriding system security which can expose your computer and personal information to malware that may harm your Mac or compromise your privacy.</span></span>

10. <span data-ttu-id="cac45-203">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="cac45-203">Click **Open**.</span></span>

    <span data-ttu-id="cac45-204">O sistema deve exibir a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="cac45-204">The system should display the following message:</span></span>

    > <span data-ttu-id="cac45-205">Microsoft Defender para Ponto de Extremidade - arquivo de teste macOS EDR DIY</span><span class="sxs-lookup"><span data-stu-id="cac45-205">Microsoft Defender for Endpoint - macOS EDR DIY test file</span></span><br/>
    > <span data-ttu-id="cac45-206">O alerta correspondente estará disponível no portal MDATP.</span><span class="sxs-lookup"><span data-stu-id="cac45-206">Corresponding alert will be available in the MDATP portal.</span></span>

11. <span data-ttu-id="cac45-207">Clique em **Abrir**. </span><span class="sxs-lookup"><span data-stu-id="cac45-207">Click **Open**.</span></span>

    <span data-ttu-id="cac45-208">Em alguns minutos, um alerta chamado "alerta de teste EDR do macOS" deve ser a gerado.</span><span class="sxs-lookup"><span data-stu-id="cac45-208">In a few minutes an alert named "macOS EDR Test Alert" should be raised.</span></span>

12. <span data-ttu-id="cac45-209">Vá para o Centro de Segurança do Microsoft Defender ( https://SecurityCenter.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="cac45-209">Go to Microsoft Defender Security Center (https://SecurityCenter.microsoft.com).</span></span>

13. <span data-ttu-id="cac45-210">Vá para a Fila de Alertas.</span><span class="sxs-lookup"><span data-stu-id="cac45-210">Go to the Alert Queue.</span></span>

    :::image type="content" source="images/b8db76c2-c368-49ad-970f-dcb87534d9be.png" alt-text="Exemplo de um alerta de teste EDR do macOS que mostra gravidade, categoria, fonte de detecção e um menu de ações recolhido.":::
    
    <span data-ttu-id="cac45-212">Veja os detalhes do alerta e a linha do tempo do dispositivo e execute as etapas de investigação regulares.</span><span class="sxs-lookup"><span data-stu-id="cac45-212">Look at the alert details and the device timeline, and perform the regular investigation steps.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="cac45-213">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="cac45-213">Logging installation issues</span></span>

<span data-ttu-id="cac45-214">Consulte [Log de problemas de](mac-resources.md#logging-installation-issues) instalação para obter mais informações sobre como encontrar o log gerado automaticamente que é criado pelo instalador quando ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="cac45-214">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="cac45-215">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="cac45-215">Uninstallation</span></span>

<span data-ttu-id="cac45-216">Consulte [Desinstalar](mac-resources.md#uninstalling) para obter detalhes sobre como remover o Microsoft Defender para o Ponto de Extremidade no macOS de dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="cac45-216">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint on macOS from client devices.</span></span>
