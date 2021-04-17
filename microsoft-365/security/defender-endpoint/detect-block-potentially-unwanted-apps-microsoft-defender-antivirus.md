---
title: Bloquear aplicativos potencialmente indesejados com o Microsoft Defender Antivírus
description: Habilita o recurso antivírus de aplicativo potencialmente indesejado (PUA) para bloquear softwares indesejados, como o adware.
keywords: pua, habilitar, software indesejado, aplicativos indesejados, adware, barra de ferramentas do navegador, detectar, bloquear, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 20d4767f9813b741c55109d617f78302feaa0f7e
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765018"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="36952-104">Detectar e bloquear aplicativos potencialmente indesejados</span><span class="sxs-lookup"><span data-stu-id="36952-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="36952-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="36952-105">**Applies to:**</span></span>

- [<span data-ttu-id="36952-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="36952-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="36952-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36952-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

> [!NOTE]
> <span data-ttu-id="36952-108">Aplicativos potencialmente indesejados (PUA) são uma categoria de software que pode fazer com que seu computador seja executado lentamente, exibir anúncios inesperados ou, na pior das hipóteses, instalar outros softwares que podem ser inesperados ou indesejados.</span><span class="sxs-lookup"><span data-stu-id="36952-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software which might be unexpected or unwanted.</span></span> <span data-ttu-id="36952-109">Por padrão, no Windows 10 (versão 2004 e posterior), o Microsoft Defender Antivírus bloqueia aplicativos que são considerados PUA, para dispositivos Enterprise (E5).</span><span class="sxs-lookup"><span data-stu-id="36952-109">By default in Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA, for Enterprise (E5) devices.</span></span>

<span data-ttu-id="36952-110">Aplicativos potencialmente indesejados (PUA) não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações em pontos de extremidade que afetam adversamente o desempenho ou o uso do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="36952-110">Potentially unwanted applications (PUA) are not considered viruses, malware, or other types of threats, but they might perform actions on endpoints which adversely affect endpoint performance or use.</span></span> <span data-ttu-id="36952-111">_O PUA_ também pode se referir a um aplicativo que tem uma reputação ruim, conforme avaliado pelo Microsoft Defender para Ponto de Extremidade, devido a determinados tipos de comportamento indesejável.</span><span class="sxs-lookup"><span data-stu-id="36952-111">_PUA_ can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="36952-112">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="36952-112">Here are some examples:</span></span>

- <span data-ttu-id="36952-113">**Software de publicidade** que exibe anúncios ou promoções, incluindo software que insere anúncios em páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="36952-113">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="36952-114">**Software de grupo** que oferece para instalar outros softwares que não são assinados digitalmente pela mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="36952-114">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="36952-115">Além disso, software que oferece para instalar outros softwares que se qualificam como PUA.</span><span class="sxs-lookup"><span data-stu-id="36952-115">Also, software that offers to install other software that qualify as PUA.</span></span>
- <span data-ttu-id="36952-116">**Software de evasão** que tenta ativamente evitar a detecção por produtos de segurança, incluindo softwares que se comportam de forma diferente na presença de produtos de segurança.</span><span class="sxs-lookup"><span data-stu-id="36952-116">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="36952-117">Para obter mais exemplos e uma discussão sobre os critérios que usamos para rotular aplicativos para atenção especial de recursos de segurança, consulte Como a Microsoft identifica malware e aplicativos potencialmente [indesejados.](/windows/security/threat-protection/intelligence/criteria)</span><span class="sxs-lookup"><span data-stu-id="36952-117">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="36952-118">Aplicativos potencialmente indesejados podem aumentar o risco de sua rede ser infectado por malware real, tornar as infecções de malware mais difíceis de identificar ou desperdiçar recursos de IT na limpeza.</span><span class="sxs-lookup"><span data-stu-id="36952-118">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="36952-119">A proteção pua é suportada no Windows 10, no Windows Server 2019 e no Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="36952-119">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="36952-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="36952-120">Microsoft Edge</span></span>

<span data-ttu-id="36952-121">O [novo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), baseado em Chromium, bloqueia downloads de aplicativos potencialmente indesejados e URLs de recursos associados.</span><span class="sxs-lookup"><span data-stu-id="36952-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="36952-122">Esse recurso é fornecido por meio [do Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="36952-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="36952-123">Habilitar a proteção pua no Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="36952-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="36952-124">Embora a proteção de aplicativo potencialmente indesejada no Microsoft Edge (baseada em Chromium, versão 80.0.361.50) está desligada por padrão, ela pode ser facilmente 2016 a partir do navegador.</span><span class="sxs-lookup"><span data-stu-id="36952-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="36952-125">Selecione as releições e, em seguida, escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="36952-125">Select the ellipses, and then choose **Settings**.</span></span>
2. <span data-ttu-id="36952-126">Selecione **Privacidade, pesquisa e serviços.**</span><span class="sxs-lookup"><span data-stu-id="36952-126">Select **Privacy, search, and services**.</span></span>
3. <span data-ttu-id="36952-127">Na seção **Segurança,** a turn on **Block potentially unwanted apps**.</span><span class="sxs-lookup"><span data-stu-id="36952-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="36952-128">Se você estiver executando o Microsoft Edge (baseado em Chromium), poderá explorar com segurança o recurso de bloqueio de URL da proteção PUA testando-o em uma de nossas páginas de demonstração do [Microsoft Defender SmartScreen.](https://demo.smartscreen.msft.net/)</span><span class="sxs-lookup"><span data-stu-id="36952-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="36952-129">Bloqueando URLs com o Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="36952-129">Blocking URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="36952-130">No Edge baseado em Chromium com a proteção PUA ligada, o Microsoft Defender SmartScreen protege você contra URLs associadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="36952-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="36952-131">Os administradores de segurança podem [configurar](/DeployEdge/configure-microsoft-edge) como o Microsoft Edge e o Microsoft Defender SmartScreen trabalham juntos para proteger grupos de usuários de URLs associadas a PUA.</span><span class="sxs-lookup"><span data-stu-id="36952-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="36952-132">Há várias [configurações de política de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitamente para o Microsoft Defender SmartScreen disponíveis, incluindo uma para bloquear [PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="36952-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="36952-133">Além disso, os administradores podem configurar o [Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) como um todo, usando as configurações de política de grupo para ativar ou desativar o Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="36952-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="36952-134">Embora o Microsoft Defender para Ponto de Extremidade tenha sua própria lista de bloqueios com base em um conjunto de dados gerenciado pela Microsoft, você pode personalizar essa lista com base em sua própria inteligência contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="36952-134">Although Microsoft Defender for Endpoint has its own block list based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="36952-135">Se você [criar e gerenciar indicadores](/microsoft-365/security/defender-endpoint/manage-indicators) no portal do Microsoft Defender para Ponto de Extremidade, o Microsoft Defender SmartScreen respeitará as novas configurações.</span><span class="sxs-lookup"><span data-stu-id="36952-135">If you [create and manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus"></a><span data-ttu-id="36952-136">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="36952-136">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="36952-137">O recurso de proteção de aplicativos potencialmente indesejados (PUA) no Microsoft Defender Antivírus pode detectar e bloquear PUAs em pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="36952-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUAs on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="36952-138">Esse recurso está disponível no Windows 10, no Windows Server 2019 e no Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="36952-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="36952-139">O Microsoft Defender Antivírus bloqueia arquivos PUA detectados e qualquer tentativa de baixar, mover, executar ou instalá-los.</span><span class="sxs-lookup"><span data-stu-id="36952-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="36952-140">Os arquivos PUA bloqueados são movidos para quarentena.</span><span class="sxs-lookup"><span data-stu-id="36952-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="36952-141">Quando um arquivo PUA é detectado em um ponto de extremidade, o Microsoft Defender Antivírus envia uma notificação para o usuário[(](configure-notifications-microsoft-defender-antivirus.md)a menos que as notificações tenham sido desabilitadas ) no mesmo formato que outras detecções de ameaças.</span><span class="sxs-lookup"><span data-stu-id="36952-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="36952-142">A notificação é prefigurada para `PUA:` indicar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="36952-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="36952-143">A notificação aparece na lista de [quarentenas usuais dentro do aplicativo segurança do Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="36952-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="36952-144">Configurar a proteção pua no Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="36952-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="36952-145">Você pode habilitar a proteção PUA com [o Microsoft Intune,](/mem/intune/protect/device-protect) [o Microsoft Endpoint Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)a Política de Grupo [ou](/azure/active-directory-domain-services/manage-group-policy)por [meio de cmdlets do PowerShell.](/powershell/module/defender/?preserve-view=true&view=win10-ps)</span><span class="sxs-lookup"><span data-stu-id="36952-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="36952-146">Você também pode usar a proteção PUA no modo de auditoria para detectar aplicativos potencialmente indesejados sem bloqueá-los.</span><span class="sxs-lookup"><span data-stu-id="36952-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="36952-147">As detecções são capturadas no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="36952-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="36952-148">Visite o site de demonstração do Microsoft Defender para Ponto de Extremidade no demo.wd.microsoft.com [para](https://demo.wd.microsoft.com/Page/UrlRep) confirmar se o recurso está funcionando e vê-lo em ação.</span><span class="sxs-lookup"><span data-stu-id="36952-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="36952-149">A proteção pua no modo de auditoria é útil se sua empresa estiver realizando uma verificação de conformidade de segurança de software interna e você quiser evitar falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="36952-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

#### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="36952-150">Usar o Intune para configurar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="36952-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="36952-151">Consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender [Antivírus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="36952-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

#### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="36952-152">Usar o Configuration Manager para configurar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="36952-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="36952-153">A proteção pua é habilitada por padrão no Microsoft Endpoint Manager (Branch Atual).</span><span class="sxs-lookup"><span data-stu-id="36952-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="36952-154">Consulte [Como criar e implantar políticas antimalware: Configurações](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) de verificações agendadas para obter detalhes sobre como configurar o Microsoft Endpoint Manager (Branch Atual).</span><span class="sxs-lookup"><span data-stu-id="36952-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="36952-155">Para o System Center 2012 Configuration Manager, consulte [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="36952-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="36952-156">Os eventos PUA bloqueados pelo Microsoft Defender Antivírus são relatados no Visualizador de Eventos do Windows e não no Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="36952-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

#### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="36952-157">Usar a Política de Grupo para configurar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="36952-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="36952-158">Baixar e instalar [Modelos Administrativos (.admx) para Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="36952-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="36952-159">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="36952-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="36952-160">Selecione o Objeto de Política de Grupo que você deseja configurar e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="36952-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="36952-161">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="36952-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="36952-162">Expanda a árvore para **Componentes do Windows**  >  **Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="36952-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="36952-163">Clique duas vezes em **Configurar detecção para aplicativos potencialmente indesejados.**</span><span class="sxs-lookup"><span data-stu-id="36952-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="36952-164">Selecione **Habilitado para** habilitar a proteção PUA.</span><span class="sxs-lookup"><span data-stu-id="36952-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="36952-165">Em **Opções,** selecione **Bloquear** para bloquear aplicativos potencialmente indesejados ou selecione **Modo** de Auditoria para testar como a configuração funciona em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="36952-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="36952-166">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="36952-166">Select **OK**.</span></span>

9. <span data-ttu-id="36952-167">Implante seu objeto de Política de Grupo como você costuma fazer.</span><span class="sxs-lookup"><span data-stu-id="36952-167">Deploy your Group Policy object as you usually do.</span></span>

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="36952-168">Usar cmdlets do PowerShell para configurar a proteção PUA</span><span class="sxs-lookup"><span data-stu-id="36952-168">Use PowerShell cmdlets to configure PUA protection</span></span>

##### <a name="to-enable-pua-protection"></a><span data-ttu-id="36952-169">Para habilitar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="36952-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="36952-170">A definição do valor desse cmdlet para `Enabled` aticá-lo se tiver sido desabilitado.</span><span class="sxs-lookup"><span data-stu-id="36952-170">Setting the value for this cmdlet to `Enabled` turns the feature on if it has been disabled.</span></span>

##### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="36952-171">Para definir a proteção pua como modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="36952-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="36952-172">A `AuditMode` configuração detecta PUAs sem bloqueá-los.</span><span class="sxs-lookup"><span data-stu-id="36952-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

##### <a name="to-disable-pua-protection"></a><span data-ttu-id="36952-173">Para desabilitar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="36952-173">To disable PUA protection</span></span>

<span data-ttu-id="36952-174">Recomendamos manter a proteção PUA 2016 2016.</span><span class="sxs-lookup"><span data-stu-id="36952-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="36952-175">No entanto, você pode desativar usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="36952-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="36952-176">Definir o valor desse cmdlet para `Disabled` desligar o recurso se tiver sido habilitado.</span><span class="sxs-lookup"><span data-stu-id="36952-176">Setting the value for this cmdlet to `Disabled` turns the feature off if it has been enabled.</span></span>

<span data-ttu-id="36952-177">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/index) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="36952-177">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="view-pua-events"></a><span data-ttu-id="36952-178">Exibir eventos PUA</span><span class="sxs-lookup"><span data-stu-id="36952-178">View PUA events</span></span>

<span data-ttu-id="36952-179">Os eventos PUA são relatados no Visualizador de Eventos do Windows, mas não no Microsoft Endpoint Manager ou no Intune.</span><span class="sxs-lookup"><span data-stu-id="36952-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="36952-180">Você também pode usar o `Get-MpThreat` cmdlet para exibir as ameaças que o Microsoft Defender Antivírus lidou.</span><span class="sxs-lookup"><span data-stu-id="36952-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="36952-181">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="36952-181">Here's an example:</span></span>

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

<span data-ttu-id="36952-182">Você pode ativar notificações por email para receber emails sobre detecções de PUA.</span><span class="sxs-lookup"><span data-stu-id="36952-182">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="36952-183">Consulte [Solucionar problemas de IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obter detalhes sobre como exibir eventos do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="36952-183">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="36952-184">Os eventos PUA são registrados na ID do evento **1160**.</span><span class="sxs-lookup"><span data-stu-id="36952-184">PUA events are recorded under event ID **1160**.</span></span>

## <a name="excluding-files"></a><span data-ttu-id="36952-185">Excluindo arquivos</span><span class="sxs-lookup"><span data-stu-id="36952-185">Excluding files</span></span>

<span data-ttu-id="36952-186">Às vezes, um arquivo é bloqueado erroneamente pela proteção pua ou um recurso de pua é necessário para concluir uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="36952-186">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="36952-187">Nesses casos, um arquivo pode ser adicionado a uma lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="36952-187">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="36952-188">Para obter mais informações, [consulte Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="36952-188">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36952-189">Confira também</span><span class="sxs-lookup"><span data-stu-id="36952-189">See also</span></span>

- [<span data-ttu-id="36952-190">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="36952-190">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="36952-191">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="36952-191">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)