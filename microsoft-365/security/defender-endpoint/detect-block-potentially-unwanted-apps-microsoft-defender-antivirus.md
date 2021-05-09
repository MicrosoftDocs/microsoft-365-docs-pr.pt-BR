---
title: Bloquear aplicativos potencialmente indesejados com o Microsoft Defender Antivírus
description: Habilite o recurso antivírus de aplicativo potencialmente indesejado (PUA) para bloquear software indesejado, como o adware.
keywords: pua, habilitar, software indesejado, aplicativos indesejados, adware, barra de ferramentas do navegador, detectar, bloquear, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: fbd897b025db2317dd1c213e5adf5d64ba88e7ac
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275235"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a><span data-ttu-id="d3dfc-104">Detectar e bloquear aplicativos potencialmente indesejados</span><span class="sxs-lookup"><span data-stu-id="d3dfc-104">Detect and block potentially unwanted applications</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d3dfc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d3dfc-105">**Applies to:**</span></span>

- [<span data-ttu-id="d3dfc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d3dfc-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="d3dfc-107">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d3dfc-107">Microsoft Edge</span></span>](/microsoft-edge/deploy/microsoft-edge)

<span data-ttu-id="d3dfc-108">Os aplicativos potencialmente indesejados (PUA) são uma categoria de software que pode fazer sua máquina funcionar lentamente, exibir anúncios inesperados ou, pior ainda, instalar outro software inesperado ou indesejado.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-108">Potentially unwanted applications (PUA) are a category of software that can cause your machine to run slowly, display unexpected ads, or at worst, install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="d3dfc-109">O PUA não é considerado um vírus, malware ou outro tipo de ameaça, mas pode executar ações nos pontos de extremidade que afetam negativamente o desempenho ou uso do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-109">PUA is not considered a virus, malware, or other type of threat, but it might perform actions on endpoints that adversely affect endpoint performance or use.</span></span> <span data-ttu-id="d3dfc-110">O termo *PUA* também pode se referir a um aplicativo que tem uma reputação ruim, conforme avaliado pelo Microsoft Defender ATP, devido a certos tipos de comportamento indesejável.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-110">The term *PUA* can also refer to an application that has a poor reputation, as assessed by Microsoft Defender for Endpoint, due to certain kinds of undesirable behavior.</span></span>

<span data-ttu-id="d3dfc-111">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="d3dfc-111">Here are some examples:</span></span>

- <span data-ttu-id="d3dfc-112">**Software de anúncio** que exibe anúncios ou promoções, incluindo software que insere anúncios em páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-112">**Advertising software** that displays advertisements or promotions, including software that inserts advertisements to webpages.</span></span>
- <span data-ttu-id="d3dfc-113">**Software de agrupamento** que oferece a instalação de outro software que não é assinado digitalmente pela mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-113">**Bundling software** that offers to install other software that is not digitally signed by the same entity.</span></span> <span data-ttu-id="d3dfc-114">Além disso, o software que oferece a instalação de outro software qualificado como PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-114">Also, software that offers to install other software that qualifies as PUA.</span></span>
- <span data-ttu-id="d3dfc-115">**Software de evasão** que tenta ativamente evitar a detecção por produtos de segurança, incluindo software que se comporta de maneira diferente na presença de produtos de segurança.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-115">**Evasion software** that actively tries to evade detection by security products, including software that behaves differently in the presence of security products.</span></span>

> [!TIP]
> <span data-ttu-id="d3dfc-116">Para obter mais exemplos e uma discussão sobre os critérios que usamos para rotular aplicativos a fim de obter atenção especial dos recursos de segurança, confira [Como a Microsoft identifica malware e aplicativos potencialmente indesejados](/windows/security/threat-protection/intelligence/criteria).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-116">For more examples and a discussion of the criteria we use to label applications for special attention from security features, see [How Microsoft identifies malware and potentially unwanted applications](/windows/security/threat-protection/intelligence/criteria).</span></span>

<span data-ttu-id="d3dfc-117">Aplicativos potencialmente indesejados podem aumentar o risco de sua rede ser infectada com malware real, dificultar a identificação das infecções por malware ou desperdiçar recursos de TI para limpá-los.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-117">Potentially unwanted applications can increase the risk of your network being infected with actual malware, make malware infections harder to identify, or waste IT resources in cleaning them up.</span></span> <span data-ttu-id="d3dfc-118">A proteção contra PUA tem suporte no Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-118">PUA protection is supported on Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="d3dfc-119">No Windows 10 (versão 2004 e posterior), o Microsoft Defender Antivírus bloqueia os aplicativos considerados PUA para dispositivos Enterprise (E5) por padrão.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-119">In Windows 10 (version 2004 and later), Microsoft Defender Antivirus blocks apps that are considered PUA for Enterprise (E5) devices by default.</span></span>

## <a name="microsoft-edge"></a><span data-ttu-id="d3dfc-120">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d3dfc-120">Microsoft Edge</span></span>

<span data-ttu-id="d3dfc-121">O [novo Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), que é baseado no Chromium, bloqueia downloads de aplicativos potencialmente indesejados e URLs de recursos associados.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-121">The [new Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea), which is Chromium-based, blocks potentially unwanted application downloads and associated resource URLs.</span></span> <span data-ttu-id="d3dfc-122">Este recurso é fornecido por meio do [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-122">This feature is provided via [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview).</span></span>

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a><span data-ttu-id="d3dfc-123">Habilitar a proteção contra PUA no Microsoft Edge baseado no Chromium</span><span class="sxs-lookup"><span data-stu-id="d3dfc-123">Enable PUA protection in Chromium-based Microsoft Edge</span></span>

<span data-ttu-id="d3dfc-124">Embora a proteção de aplicativos potencialmente indesejados no Microsoft Edge (baseado no Chromium, versão 80.0.361.50) esteja desativada por padrão, pode ser facilmente ativada a partir do navegador.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-124">Although potentially unwanted application protection in Microsoft Edge (Chromium-based, version 80.0.361.50) is turned off by default, it can easily be turned on from within the browser.</span></span>

1. <span data-ttu-id="d3dfc-125">No navegador Microsoft Edge, selecione as reticências e escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-125">In your Edge browser, select the ellipses, and then choose **Settings**.</span></span>

2. <span data-ttu-id="d3dfc-126">Selecione **Privacidade, pesquisa e serviços**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-126">Select **Privacy, search, and services**.</span></span>

3. <span data-ttu-id="d3dfc-127">Na seção **Segurança**, ative **Bloquear aplicativos potencialmente indesejados**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-127">Under the **Security** section, turn on **Block potentially unwanted apps**.</span></span>

> [!TIP]
> <span data-ttu-id="d3dfc-128">Se estiver executando o Microsoft Edge (baseado no Chromium), você poderá explorar com segurança o recurso de bloqueio de URL da proteção contra PUA testando-o em uma de nossas [páginas de demonstração do Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-128">If you are running Microsoft Edge (Chromium-based), you can safely explore the URL-blocking feature of PUA protection by testing it out on one of our [Microsoft Defender SmartScreen demo pages](https://demo.smartscreen.msft.net/).</span></span>

### <a name="block-urls-with-microsoft-defender-smartscreen"></a><span data-ttu-id="d3dfc-129">Bloquear URLs com o Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="d3dfc-129">Block URLs with Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="d3dfc-130">No Microsoft Edge baseado no Chromium com a proteção contra PUA ativada, o Microsoft Defender SmartScreen protege você contra URLs associadas ao PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-130">In Chromium-based Edge with PUA protection turned on, Microsoft Defender SmartScreen protects you from PUA-associated URLs.</span></span>

<span data-ttu-id="d3dfc-131">Os administradores de segurança podem [configurar](/DeployEdge/configure-microsoft-edge) como o Microsoft Edge e o Microsoft Defender SmartScreen trabalham juntos para proteger grupos de usuários contra URLs associadas ao PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-131">Security admins can [configure](/DeployEdge/configure-microsoft-edge) how Microsoft Edge and Microsoft Defender SmartScreen work together to protect groups of users from PUA-associated URLs.</span></span> <span data-ttu-id="d3dfc-132">Há várias [configurações de política de grupo](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitamente disponíveis para o Microsoft Defender SmartScreen, incluindo [uma para bloquear o PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-132">There are several [group policy settings](/DeployEdge/microsoft-edge-policies#smartscreen-settings) explicitly for Microsoft Defender SmartScreen available, including [one for blocking PUA](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled).</span></span> <span data-ttu-id="d3dfc-133">Além disso, os administradores podem [configurar o Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) como um todo, usando configurações de política de grupo para ativar ou desativar o Microsoft Defender SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-133">In addition, admins can [configure Microsoft Defender SmartScreen](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) as a whole, using group policy settings to turn Microsoft Defender SmartScreen on or off.</span></span>

<span data-ttu-id="d3dfc-134">Embora o Microsoft Defender ATP tenha sua própria lista de bloqueio com base em um conjunto de dados gerenciado pela Microsoft, você pode personalizar essa lista com base em sua própria inteligência contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-134">Although Microsoft Defender for Endpoint has its own blocklist based upon a data set managed by Microsoft, you can customize this list based on your own threat intelligence.</span></span> <span data-ttu-id="d3dfc-135">Se você [criar e gerenciar indicadores](manage-indicators.md) no portal Microsoft Defender ATP, o Microsoft Defender SmartScreen respeitará as novas configurações.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-135">If you [create and manage indicators](manage-indicators.md) in the Microsoft Defender for Endpoint portal, Microsoft Defender SmartScreen respects the new settings.</span></span>

## <a name="microsoft-defender-antivirus-and-pua-protection"></a><span data-ttu-id="d3dfc-136">Proteção contra PUA e Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d3dfc-136">Microsoft Defender Antivirus and PUA protection</span></span>

<span data-ttu-id="d3dfc-137">O recurso de proteção do aplicativo potencialmente indesejado (PUA) no Microsoft Defender Antivírus detecta e bloqueia o PUA em pontos de extremidade da sua rede.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-137">The potentially unwanted application (PUA) protection feature in Microsoft Defender Antivirus can detect and block PUA on endpoints in your network.</span></span>

> [!NOTE]
> <span data-ttu-id="d3dfc-138">Esse recurso está disponível no Windows 10, Windows Server 2019 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-138">This feature is available in Windows 10, Windows Server 2019, and Windows Server 2016.</span></span>

<span data-ttu-id="d3dfc-139">O Microsoft Defender Antivírus bloqueia arquivos PUA detectados e qualquer tentativa de baixar, mover, executar ou instalá-los.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-139">Microsoft Defender Antivirus blocks detected PUA files and any attempts to download, move, run, or install them.</span></span> <span data-ttu-id="d3dfc-140">Em seguida, os arquivos PUA bloqueados são movidos para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-140">Blocked PUA files are then moved to quarantine.</span></span> <span data-ttu-id="d3dfc-141">Quando um arquivo PUA é detectado em um ponto de extremidade, o Microsoft Defender Antivírus envia uma notificação ao usuário ([a menos que as notificações tenham sido desabilitadas](configure-notifications-microsoft-defender-antivirus.md)) no mesmo formato que outras detecções de ameaças.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-141">When a PUA file is detected on an endpoint, Microsoft Defender Antivirus sends a notification to the user ([unless notifications have been disabled](configure-notifications-microsoft-defender-antivirus.md)) in the same format as other threat detections.</span></span> <span data-ttu-id="d3dfc-142">A notificação é precedida de `PUA:` para indicar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-142">The notification is prefaced with `PUA:` to indicate its content.</span></span>

<span data-ttu-id="d3dfc-143">A notificação aparece na [lista de quarentena normal dentro do aplicativo Windows Security](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-143">The notification appears in the usual [quarantine list within the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a><span data-ttu-id="d3dfc-144">Configurar a proteção contra PUA no Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d3dfc-144">Configure PUA protection in Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d3dfc-145">Você pode habilitar a proteção contra PUA com o [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Política de Grupo](/azure/active-directory-domain-services/manage-group-policy) ou por meio de [cmdlets do PowerShell](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-145">You can enable PUA protection with [Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [Group Policy](/azure/active-directory-domain-services/manage-group-policy), or via [PowerShell cmdlets](/powershell/module/defender/?preserve-view=true&view=win10-ps).</span></span>

<span data-ttu-id="d3dfc-146">Você também pode usar a proteção contra PUA no modo de auditoria para detectar aplicativos potencialmente indesejados sem bloqueá-los.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-146">You can also use PUA protection in audit mode to detect potentially unwanted applications without blocking them.</span></span> <span data-ttu-id="d3dfc-147">As detecções são capturadas no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-147">The detections are captured in the Windows event log.</span></span>

> [!TIP]
> <span data-ttu-id="d3dfc-148">Visite o site de demonstração do Microsoft Defender ATP em [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) para confirmar se o recurso está funcionando e vê-lo em ação.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-148">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep) to confirm that the feature is working, and see it in action.</span></span>

<span data-ttu-id="d3dfc-149">A proteção contra PUA no modo de auditoria é útil se sua empresa estiver realizando uma verificação de conformidade de segurança de software interna, e se você quiser evitar falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-149">PUA protection in audit mode is useful if your company is conducting an internal software security compliance check and you'd like to avoid any false positives.</span></span>

### <a name="use-intune-to-configure-pua-protection"></a><span data-ttu-id="d3dfc-150">Usar o Intune para configurar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-150">Use Intune to configure PUA protection</span></span>

<span data-ttu-id="d3dfc-151">Confira [Definir as configurações de restrição de dispositivo no Microsoft Intune](/intune/device-restrictions-configure) e [Configurações de restrição de dispositivo do Microsoft Defender Antivírus para Windows 10 no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-151">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-configuration-manager-to-configure-pua-protection"></a><span data-ttu-id="d3dfc-152">Usar o Configuration Manager para configurar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-152">Use Configuration Manager to configure PUA protection</span></span>

<span data-ttu-id="d3dfc-153">A proteção contra PUA está habilitada por padrão no Microsoft Endpoint Manager (Branch Atual).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-153">PUA protection is enabled by default in the Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d3dfc-154">Confira [Como criar e implantar políticas antimalware: configurações de verificações programadas](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) para obter detalhes sobre a configuração do Microsoft Endpoint Manager (Branch Atual).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-154">See [How to create and deploy antimalware policies: Scheduled scans settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) for details on configuring Microsoft Endpoint Manager (Current Branch).</span></span>

<span data-ttu-id="d3dfc-155">Para o System Center 2012 Configuration Manager, confira [Como implantar a Política de Proteção do Aplicativo Potencialmente Indesejado para a Proteção do Ponto de Extremidade no Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-155">For System Center 2012 Configuration Manager, see [How to Deploy Potentially Unwanted Application Protection Policy for Endpoint Protection in Configuration Manager](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA).</span></span>

> [!NOTE]
> <span data-ttu-id="d3dfc-156">Os eventos PUA bloqueados pelo Microsoft Defender Antivírus são relatados no Visualizador de Eventos do Windows e não no Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-156">PUA events blocked by Microsoft Defender Antivirus are reported in the Windows Event Viewer and not in Microsoft Endpoint Configuration Manager.</span></span>

### <a name="use-group-policy-to-configure-pua-protection"></a><span data-ttu-id="d3dfc-157">Usar a Política de Grupo para configurar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-157">Use Group Policy to configure PUA protection</span></span>

1. <span data-ttu-id="d3dfc-158">Baixe e instale os [Modelos Administrativos (.admx) para a Atualização de outubro de 2020 do Windows 10 (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span><span class="sxs-lookup"><span data-stu-id="d3dfc-158">Download and install [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/details.aspx?id=102157)</span></span>

2. <span data-ttu-id="d3dfc-159">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-159">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

3. <span data-ttu-id="d3dfc-160">Selecione o Objeto de Política de Grupo que deseja configurar e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-160">Select the Group Policy Object you want to configure, and then choose **Edit**.</span></span>

4. <span data-ttu-id="d3dfc-161">No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-161">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

5. <span data-ttu-id="d3dfc-162">Expanda a árvore para **Componentes do Windows** > **Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-162">Expand the tree to **Windows Components** > **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="d3dfc-163">Clique duas vezes em **Configurar a detecção de aplicativos potencialmente indesejados**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-163">Double-click **Configure detection for potentially unwanted applications**.</span></span>

7. <span data-ttu-id="d3dfc-164">Selecione **Habilitado** para habilitar a proteção contra PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-164">Select **Enabled** to enable PUA protection.</span></span>

8. <span data-ttu-id="d3dfc-165">Em **Opções**, selecione **Bloquear** para bloquear aplicativos potencialmente indesejados ou selecione **Modo de auditoria** para testar como a configuração funciona em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-165">In **Options**, select **Block** to block potentially unwanted applications, or select **Audit Mode** to test how the setting works in your environment.</span></span> <span data-ttu-id="d3dfc-166">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-166">Select **OK**.</span></span>

9. <span data-ttu-id="d3dfc-167">Implante seu objeto de Política de Grupo como de costume.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-167">Deploy your Group Policy object as you usually do.</span></span>

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a><span data-ttu-id="d3dfc-168">Usar cmdlets do PowerShell para configurar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-168">Use PowerShell cmdlets to configure PUA protection</span></span>

#### <a name="to-enable-pua-protection"></a><span data-ttu-id="d3dfc-169">Para habilitar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-169">To enable PUA protection</span></span>

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

<span data-ttu-id="d3dfc-170">Definir o valor deste cmdlet para `Enabled` ativa o recurso, caso ele tenha sido desabilitado.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-170">Setting the value for this cmdlet to `Enabled` turns on the feature if it has been disabled.</span></span>

#### <a name="to-set-pua-protection-to-audit-mode"></a><span data-ttu-id="d3dfc-171">Para definir a proteção contra PUA para o modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="d3dfc-171">To set PUA protection to audit mode</span></span>

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

<span data-ttu-id="d3dfc-172">Definir o `AuditMode` detecta PUAs sem bloqueá-los.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-172">Setting `AuditMode` detects PUAs without blocking them.</span></span>

#### <a name="to-disable-pua-protection"></a><span data-ttu-id="d3dfc-173">Para desabilitar a proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-173">To disable PUA protection</span></span>

<span data-ttu-id="d3dfc-174">Recomendamos manter a proteção contra PUA ativada.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-174">We recommend keeping PUA protection turned on.</span></span> <span data-ttu-id="d3dfc-175">No entanto, você pode desativá-lo usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d3dfc-175">However, you can turn it off by using the following cmdlet:</span></span>

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

<span data-ttu-id="d3dfc-176">Definir o valor deste cmdlet para `Disabled` desativa o recurso, caso ele tenha sido habilitado.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-176">Setting the value for this cmdlet to `Disabled` turns off the feature if it has been enabled.</span></span>

<span data-ttu-id="d3dfc-177">Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-177">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

## <a name="view-pua-events-using-powershell"></a><span data-ttu-id="d3dfc-178">Exibir eventos PUA usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3dfc-178">View PUA events using PowerShell</span></span>

<span data-ttu-id="d3dfc-179">Os eventos PUA são relatados no Visualizador de Eventos do Windows, mas não no Microsoft Endpoint Manager ou no Intune.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-179">PUA events are reported in the Windows Event Viewer, but not in Microsoft Endpoint Manager or in Intune.</span></span> <span data-ttu-id="d3dfc-180">Você também pode usar o cmdlet `Get-MpThreat` para visualizar as ameaças manipuladas pelo Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-180">You can also use the `Get-MpThreat` cmdlet to view threats that Microsoft Defender Antivirus handled.</span></span> <span data-ttu-id="d3dfc-181">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="d3dfc-181">Here's an example:</span></span>

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

## <a name="get-email-notifications-about-pua-detections"></a><span data-ttu-id="d3dfc-182">Receber notificações por email sobre detecções de PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-182">Get email notifications about PUA detections</span></span>

<span data-ttu-id="d3dfc-183">Você pode ativar as notificações por email para receber emails sobre detecções de PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-183">You can turn on email notifications to receive mail about PUA detections.</span></span>

<span data-ttu-id="d3dfc-184">Confira [Solução de problemas de IDs de eventos](troubleshoot-microsoft-defender-antivirus.md) para obter detalhes sobre a visualização de eventos do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-184">See [Troubleshoot event IDs](troubleshoot-microsoft-defender-antivirus.md) for details on viewing Microsoft Defender Antivirus events.</span></span> <span data-ttu-id="d3dfc-185">Os eventos PUA são registrados na ID do evento **1160**.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-185">PUA events are recorded under event ID **1160**.</span></span>

## <a name="view-pua-events-using-advanced-hunting"></a><span data-ttu-id="d3dfc-186">Visualizar eventos PUA usando a busca avançada de ameaças</span><span class="sxs-lookup"><span data-stu-id="d3dfc-186">View PUA events using advanced hunting</span></span>

<span data-ttu-id="d3dfc-187">Se estiver usando o [Microsoft Defender ATP](microsoft-defender-endpoint.md), você pode usar uma consulta de busca avançada de ameaças para visualizar eventos PUA.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-187">If you're using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), you can use an advanced hunting query to view PUA events.</span></span> <span data-ttu-id="d3dfc-188">Veja um exemplo de consulta:</span><span class="sxs-lookup"><span data-stu-id="d3dfc-188">Here's an example query:</span></span>

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

<span data-ttu-id="d3dfc-189">Para saber mais sobre a busca avançada de ameaças, confira [Buscar proativamente as ameaças com a busca avançada de ameaças](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3dfc-189">To learn more about advanced hunting, see [Proactively hunt for threats with advanced hunting](advanced-hunting-overview.md).</span></span>

## <a name="exclude-files-from-pua-protection"></a><span data-ttu-id="d3dfc-190">Excluir arquivos da proteção contra PUA</span><span class="sxs-lookup"><span data-stu-id="d3dfc-190">Exclude files from PUA protection</span></span>

<span data-ttu-id="d3dfc-191">Às vezes, um arquivo é bloqueado erroneamente pela proteção contra PUA ou um recurso de um PUA é necessário para concluir uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-191">Sometimes a file is erroneously blocked by PUA protection, or a feature of a PUA is required to complete a task.</span></span> <span data-ttu-id="d3dfc-192">Nesses casos, é possível adicionar um arquivo a uma lista de exclusão.</span><span class="sxs-lookup"><span data-stu-id="d3dfc-192">In these cases, a file can be added to an exclusion list.</span></span>

<span data-ttu-id="d3dfc-193">Para obter mais informações, confira [Configurar e validar exclusões com base na extensão do arquivo e no local da pasta.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d3dfc-193">For more information, see [Configure and validate exclusions based on file extension and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3dfc-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="d3dfc-194">See also</span></span>

- [<span data-ttu-id="d3dfc-195">Proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="d3dfc-195">Next-generation protection</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d3dfc-196">Configurar a proteção comportamental, heurística e em tempo real</span><span class="sxs-lookup"><span data-stu-id="d3dfc-196">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)