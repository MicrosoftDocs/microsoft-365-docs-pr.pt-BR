---
title: Implantação manual do Microsoft Defender ATP para macOS
description: Instale o Microsoft Defender ATP para macOS manualmente, na linha de comando.
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
ms.openlocfilehash: 382abd78ffa5e30c79804f9eaed211dffba7589c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052906"
---
# <a name="manual-deployment-for-microsoft-defender-for-endpoint-for-macos"></a><span data-ttu-id="8dc50-104">Implantação manual do Microsoft Defender para Ponto de Extremidade para macOS</span><span class="sxs-lookup"><span data-stu-id="8dc50-104">Manual deployment for Microsoft Defender for Endpoint for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8dc50-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8dc50-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dc50-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8dc50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8dc50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dc50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8dc50-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8dc50-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8dc50-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8dc50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="8dc50-110">Este tópico descreve como implantar o Microsoft Defender para Ponto de Extremidade para macOS manualmente.</span><span class="sxs-lookup"><span data-stu-id="8dc50-110">This topic describes how to deploy Microsoft Defender for Endpoint for macOS manually.</span></span> <span data-ttu-id="8dc50-111">Uma implantação bem-sucedida requer a conclusão de todas as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="8dc50-111">A successful deployment requires the completion of all of the following steps:</span></span>
- [<span data-ttu-id="8dc50-112">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="8dc50-112">Download installation and onboarding packages</span></span>](#download-installation-and-onboarding-packages)
- [<span data-ttu-id="8dc50-113">Instalação do aplicativo (macOS 10.15 e versões anteriores)</span><span class="sxs-lookup"><span data-stu-id="8dc50-113">Application installation (macOS 10.15 and older versions)</span></span>](#application-installation-macos-1015-and-older-versions)
- [<span data-ttu-id="8dc50-114">Instalação do aplicativo (macOS 11 e versões mais recentes)</span><span class="sxs-lookup"><span data-stu-id="8dc50-114">Application installation (macOS 11 and newer versions)</span></span>](#application-installation-macos-11-and-newer-versions)
- [<span data-ttu-id="8dc50-115">Configuração do cliente</span><span class="sxs-lookup"><span data-stu-id="8dc50-115">Client configuration</span></span>](#client-configuration)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="8dc50-116">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="8dc50-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="8dc50-117">Antes de começar, consulte a página principal do Microsoft Defender para Ponto de Extremidade para [macOS](microsoft-defender-endpoint-mac.md) para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.</span><span class="sxs-lookup"><span data-stu-id="8dc50-117">Before you get started, see [the main Microsoft Defender for Endpoint for macOS page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="download-installation-and-onboarding-packages"></a><span data-ttu-id="8dc50-118">Baixar pacotes de instalação e integração</span><span class="sxs-lookup"><span data-stu-id="8dc50-118">Download installation and onboarding packages</span></span>

<span data-ttu-id="8dc50-119">Baixe os pacotes de instalação e integração do Centro de Segurança do Microsoft Defender:</span><span class="sxs-lookup"><span data-stu-id="8dc50-119">Download the installation and onboarding packages from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="8dc50-120">No Centro de Segurança do Microsoft Defender, acesse **Configurações > Gerenciamento de Dispositivos > Integração**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-120">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="8dc50-121">Na Seção 1 da página, de definir o sistema operacional como **macOS** e o método Deployment como **script local**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-121">In Section 1 of the page, set operating system to **macOS** and Deployment method to **Local script**.</span></span>
3. <span data-ttu-id="8dc50-122">Na Seção 2 da página, selecione **Baixar pacote de instalação**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-122">In Section 2 of the page, select **Download installation package**.</span></span> <span data-ttu-id="8dc50-123">Salve-o como wdav.pkg em um diretório local.</span><span class="sxs-lookup"><span data-stu-id="8dc50-123">Save it as wdav.pkg to a local directory.</span></span>
4. <span data-ttu-id="8dc50-124">Na Seção 2 da página, selecione **Baixar pacote de integração**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-124">In Section 2 of the page, select **Download onboarding package**.</span></span> <span data-ttu-id="8dc50-125">Salve-o como WindowsDefenderATPOnboardingPackage.zip no mesmo diretório.</span><span class="sxs-lookup"><span data-stu-id="8dc50-125">Save it as WindowsDefenderATPOnboardingPackage.zip to the same directory.</span></span>

    ![Captura de tela do Centro de Segurança do Microsoft Defender](images/atp-portal-onboarding-page.png)

5. <span data-ttu-id="8dc50-127">Em um prompt de comando, verifique se você tem os dois arquivos.</span><span class="sxs-lookup"><span data-stu-id="8dc50-127">From a command prompt, verify that you have the two files.</span></span>
    
## <a name="application-installation-macos-1015-and-older-versions"></a><span data-ttu-id="8dc50-128">Instalação do aplicativo (macOS 10.15 e versões anteriores)</span><span class="sxs-lookup"><span data-stu-id="8dc50-128">Application installation (macOS 10.15 and older versions)</span></span>

<span data-ttu-id="8dc50-129">Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dc50-129">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="8dc50-130">Navegue até o wdav.pkg baixado no Finder e abra-o.</span><span class="sxs-lookup"><span data-stu-id="8dc50-130">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de tela de instalação do aplicativo1](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-28-appinstall)

2. <span data-ttu-id="8dc50-132">Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="8dc50-132">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

    ![Captura de tela de instalação do aplicativo2](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-29-appinstalllogin)

   > [!IMPORTANT]
   > <span data-ttu-id="8dc50-134">Você será solicitado a permitir que um driver da Microsoft seja instalado ("Bloqueio de Extensão do Sistema" ou "Instalação está em espera" ou ambos.</span><span class="sxs-lookup"><span data-stu-id="8dc50-134">You will be prompted to allow a driver from Microsoft to be installed (either "System Extension Blocked" or "Installation is on hold" or both.</span></span> <span data-ttu-id="8dc50-135">O driver deve ter permissão para ser instalado.</span><span class="sxs-lookup"><span data-stu-id="8dc50-135">The driver must be allowed to be installed.</span></span>

   ![Captura de tela de instalação do aplicativo3](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-30-systemextension)

3. <span data-ttu-id="8dc50-137">Selecione **Abrir Preferências de Segurança** ou Abrir **Preferências do Sistema > Segurança & Privacidade**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-137">Select **Open Security Preferences** or **Open System Preferences > Security & Privacy**.</span></span> <span data-ttu-id="8dc50-138">Selecione **Permitir**:</span><span class="sxs-lookup"><span data-stu-id="8dc50-138">Select **Allow**:</span></span>

    ![Captura de tela de janela de segurança e privacidade](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-31-securityprivacysettings)

   <span data-ttu-id="8dc50-140">A instalação continua.</span><span class="sxs-lookup"><span data-stu-id="8dc50-140">The installation proceeds.</span></span>

   > [!CAUTION]
   > <span data-ttu-id="8dc50-141">Se você não selecionar **Permitir**, a instalação prosseguirá após 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="8dc50-141">If you don't select **Allow**, the installation will proceed after 5 minutes.</span></span> <span data-ttu-id="8dc50-142">O Microsoft Defender para Ponto de Extremidade será carregado, mas alguns recursos, como proteção em tempo real, serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="8dc50-142">Microsoft Defender for Endpoint will be loaded, but some features, such as real-time protection, will be disabled.</span></span> <span data-ttu-id="8dc50-143">Consulte [Solucionar problemas de extensão do kernel](mac-support-kext.md) para obter informações sobre como resolver isso.</span><span class="sxs-lookup"><span data-stu-id="8dc50-143">See [Troubleshoot kernel extension issues](mac-support-kext.md) for information on how to resolve this.</span></span>

> [!NOTE]
> <span data-ttu-id="8dc50-144">O macOS pode solicitar a reinicialização do dispositivo na primeira instalação do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="8dc50-144">macOS may request to reboot the device upon the first installation of Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="8dc50-145">A proteção em tempo real não estará disponível até que o dispositivo seja reiniciado.</span><span class="sxs-lookup"><span data-stu-id="8dc50-145">Real-time protection will not be available until the device is rebooted.</span></span>

## <a name="application-installation-macos-11-and-newer-versions"></a><span data-ttu-id="8dc50-146">Instalação do aplicativo (macOS 11 e versões mais recentes)</span><span class="sxs-lookup"><span data-stu-id="8dc50-146">Application installation (macOS 11 and newer versions)</span></span>

<span data-ttu-id="8dc50-147">Para concluir esse processo, você deve ter privilégios de administrador no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dc50-147">To complete this process, you must have admin privileges on the device.</span></span>

1. <span data-ttu-id="8dc50-148">Navegue até o wdav.pkg baixado no Finder e abra-o.</span><span class="sxs-lookup"><span data-stu-id="8dc50-148">Navigate to the downloaded wdav.pkg in Finder and open it.</span></span>

    ![Captura de tela de instalação do aplicativo4](images/big-sur-install-1.png)

2. <span data-ttu-id="8dc50-150">Selecione **Continuar**, concordar com os termos de Licença e insira a senha quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="8dc50-150">Select **Continue**, agree with the License terms, and enter the password when prompted.</span></span>

3. <span data-ttu-id="8dc50-151">No final do processo de instalação, você será promovido a aprovar as extensões do sistema usadas pelo produto.</span><span class="sxs-lookup"><span data-stu-id="8dc50-151">At the end of the installation process, you will be promoted to approve the system extensions used by the product.</span></span> <span data-ttu-id="8dc50-152">Selecione **Abrir Preferências de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-152">Select **Open Security Preferences**.</span></span>

    ![Aprovação de extensão do sistema](images/big-sur-install-2.png)

4. <span data-ttu-id="8dc50-154">Na janela **Segurança & Privacidade,** selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-154">From the **Security & Privacy** window, select **Allow**.</span></span>

    ![Preferências de segurança de extensão do sistema1](images/big-sur-install-3.png)

5. <span data-ttu-id="8dc50-156">Repita as etapas 3 & 4 para todas as extensões do sistema distribuídas com o Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="8dc50-156">Repeat steps 3 & 4 for all system extensions distributed with Microsoft Defender for Endpoint for Mac.</span></span>

6. <span data-ttu-id="8dc50-157">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade para Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="8dc50-157">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="8dc50-158">Quando solicitado a conceder permissões do Microsoft Defender para o Ponto de Extremidade para filtrar o tráfego de rede, selecione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="8dc50-158">When prompted to grant Microsoft Defender for Endpoint permissions to filter network traffic, select **Allow**.</span></span>

    ![Preferências de segurança de extensão do sistema2](images/big-sur-install-4.png)

7. <span data-ttu-id="8dc50-160">Abra **Preferências do** Sistema Segurança & Privacidade e navegue até a guia Privacidade. Conceda permissão de Acesso em Disco Completo para o Microsoft Defender ATP e a Extensão de Segurança do Ponto de Extremidade do  >   Microsoft Defender **ATP.**   </span><span class="sxs-lookup"><span data-stu-id="8dc50-160">Open **System Preferences** > **Security & Privacy** and navigate to the **Privacy** tab. Grant **Full Disk Access** permission to **Microsoft Defender ATP** and **Microsoft Defender ATP Endpoint Security Extension**.</span></span>

    ![Acesso em disco completo](images/big-sur-install-5.png)

## <a name="client-configuration"></a><span data-ttu-id="8dc50-162">Configuração do cliente</span><span class="sxs-lookup"><span data-stu-id="8dc50-162">Client configuration</span></span>

1. <span data-ttu-id="8dc50-163">Copie wdav.pkg e MicrosoftDefenderATPOnboardingMacOs.py para o dispositivo onde você implanta o Microsoft Defender para Ponto de Extremidade para macOS.</span><span class="sxs-lookup"><span data-stu-id="8dc50-163">Copy wdav.pkg and MicrosoftDefenderATPOnboardingMacOs.py to the device where you deploy Microsoft Defender for Endpoint for macOS.</span></span>

    <span data-ttu-id="8dc50-164">O dispositivo cliente não está associado a orgId.</span><span class="sxs-lookup"><span data-stu-id="8dc50-164">The client device is not associated with orgId.</span></span> <span data-ttu-id="8dc50-165">Observe que o *atributo orgId* está em branco.</span><span class="sxs-lookup"><span data-stu-id="8dc50-165">Note that the *orgId* attribute is blank.</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="8dc50-166">Execute o script Python para instalar o arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="8dc50-166">Run the Python script to install the configuration file:</span></span>

    ```bash
    /usr/bin/python MicrosoftDefenderATPOnboardingMacOs.py
    ```

3. <span data-ttu-id="8dc50-167">Verifique se o dispositivo agora está associado à sua organização e relata uma *orgId válida*:</span><span class="sxs-lookup"><span data-stu-id="8dc50-167">Verify that the device is now associated with your organization and reports a valid *orgId*:</span></span>

    ```bash
    mdatp health --field org_id
    ```

<span data-ttu-id="8dc50-168">Após a instalação, você verá o ícone do Microsoft Defender na barra de status do macOS no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="8dc50-168">After installation, you'll see the Microsoft Defender icon in the macOS status bar in the top-right corner.</span></span>

   ![Ícone do Microsoft Defender na captura de tela da barra de status](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-icon-bar)
   

## <a name="how-to-allow-full-disk-access"></a><span data-ttu-id="8dc50-170">Como permitir o acesso total ao disco</span><span class="sxs-lookup"><span data-stu-id="8dc50-170">How to Allow Full Disk Access</span></span>

> [!CAUTION]
> <span data-ttu-id="8dc50-171">O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="8dc50-171">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="8dc50-172">A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito.</span><span class="sxs-lookup"><span data-stu-id="8dc50-172">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="8dc50-173">Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8dc50-173">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>

<span data-ttu-id="8dc50-174">Para conceder consentimento, abra Preferências do Sistema -> Segurança & Privacidade -> Privacidade -> Acesso total em disco.</span><span class="sxs-lookup"><span data-stu-id="8dc50-174">To grant consent, open System Preferences -> Security & Privacy -> Privacy -> Full Disk Access.</span></span> <span data-ttu-id="8dc50-175">Clique no ícone de bloqueio para fazer alterações (parte inferior da caixa de diálogo).</span><span class="sxs-lookup"><span data-stu-id="8dc50-175">Click the lock icon to make changes (bottom of the dialog box).</span></span> <span data-ttu-id="8dc50-176">Selecione Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="8dc50-176">Select Microsoft Defender for Endpoint.</span></span>

## <a name="logging-installation-issues"></a><span data-ttu-id="8dc50-177">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="8dc50-177">Logging installation issues</span></span>

<span data-ttu-id="8dc50-178">Consulte [Log de problemas de](mac-resources.md#logging-installation-issues) instalação para obter mais informações sobre como encontrar o log gerado automaticamente que é criado pelo instalador quando ocorre um erro.</span><span class="sxs-lookup"><span data-stu-id="8dc50-178">See [Logging installation issues](mac-resources.md#logging-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="8dc50-179">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="8dc50-179">Uninstallation</span></span>

<span data-ttu-id="8dc50-180">Consulte [Desinstalar](mac-resources.md#uninstalling) para obter detalhes sobre como remover o Microsoft Defender for Endpoint para macOS de dispositivos cliente.</span><span class="sxs-lookup"><span data-stu-id="8dc50-180">See [Uninstalling](mac-resources.md#uninstalling) for details on how to remove Microsoft Defender for Endpoint for macOS from client devices.</span></span>
