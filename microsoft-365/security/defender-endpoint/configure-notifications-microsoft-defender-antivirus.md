---
title: Configurar Microsoft Defender Antivírus notificações
description: Saiba como configurar e personalizar notificações padrão e outras Microsoft Defender Antivírus nos pontos de extremidade.
keywords: notificações, defender, antivírus, ponto de extremidade, gerenciamento, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985403"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="0eb14-104">Configurar Microsoft Defender Antivírus notificações que aparecem nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="0eb14-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="0eb14-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0eb14-105">**Applies to:**</span></span>

- [<span data-ttu-id="0eb14-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0eb14-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0eb14-107">Em Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas.</span><span class="sxs-lookup"><span data-stu-id="0eb14-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="0eb14-108">Microsoft Defender Antivírus as notificações aparecem nos pontos de extremidade quando as verificações são concluídas e as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="0eb14-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="0eb14-109">As notificações seguem verificações agendadas e disparadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="0eb14-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="0eb14-110">Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.</span><span class="sxs-lookup"><span data-stu-id="0eb14-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="0eb14-111">Se você faz parte da equipe de segurança da sua organização, pode configurar como as notificações aparecem nos pontos de extremidade, como notificações que solicitam uma reinicialização do sistema ou que indicam que uma ameaça foi detectada e remediada.</span><span class="sxs-lookup"><span data-stu-id="0eb14-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="0eb14-112">Configurar notificações antivírus usando a Política de Grupo ou o Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="0eb14-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="0eb14-113">Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo Segurança do Windows [e](microsoft-defender-security-center-antivirus.md) com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="0eb14-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="0eb14-114">No Windows 10, versão 1607, o  recurso era chamado notificações aprimoradas e foi configurado em **Windows Configurações**  >  **Atualização & segurança**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="0eb14-115">Nas configurações da Política de Grupo para todas as versões do Windows 10, o recurso de notificação é chamado **notificações aprimoradas.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="0eb14-116">Usar a Política de Grupo para desabilitar notificações adicionais</span><span class="sxs-lookup"><span data-stu-id="0eb14-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="0eb14-117">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="0eb14-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="0eb14-118">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="0eb14-119">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="0eb14-120">Selecione **Modelos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="0eb14-121">Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus** > Reporting\*\*.</span><span class="sxs-lookup"><span data-stu-id="0eb14-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="0eb14-122">Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="0eb14-123">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-123">Then select **OK**.</span></span> <span data-ttu-id="0eb14-124">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="0eb14-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0eb14-125">Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="0eb14-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="0eb14-126">Usar o Segurança do Windows para desabilitar notificações adicionais</span><span class="sxs-lookup"><span data-stu-id="0eb14-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="0eb14-127">Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="0eb14-128">Selecione **O &** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, selecione **Configurações** de proteção contra vírus & ameaças</span><span class="sxs-lookup"><span data-stu-id="0eb14-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="0eb14-129">Role até a **seção Notificações** e selecione **Alterar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="0eb14-130">Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="0eb14-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0eb14-131">Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="0eb14-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="0eb14-132">Configurar notificações padrão em pontos de extremidade usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="0eb14-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="0eb14-133">Você pode usar a Política de Grupo para:</span><span class="sxs-lookup"><span data-stu-id="0eb14-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="0eb14-134">Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação</span><span class="sxs-lookup"><span data-stu-id="0eb14-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="0eb14-135">Ocultar todas as notificações nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="0eb14-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="0eb14-136">Ocultar notificações de reinicialização nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="0eb14-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="0eb14-137">Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a Microsoft Defender Antivírus interface.</span><span class="sxs-lookup"><span data-stu-id="0eb14-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="0eb14-138">Consulte [Impedir que os usuários vejam ou interajam](prevent-end-user-interaction-microsoft-defender-antivirus.md) com Microsoft Defender Antivírus interface do usuário para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0eb14-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="0eb14-139">Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada.</span><span class="sxs-lookup"><span data-stu-id="0eb14-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="0eb14-140">As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento Microsoft Endpoint Manager Endpoint Protection [relatórios.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="0eb14-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="0eb14-141">Para adicionar informações de contato personalizadas às notificações do ponto de extremidade, consulte [Personalizar o aplicativo Segurança do Windows para sua organização.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="0eb14-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="0eb14-142">Usar a Política de Grupo para ocultar notificações</span><span class="sxs-lookup"><span data-stu-id="0eb14-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="0eb14-143">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="0eb14-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="0eb14-144">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="0eb14-145">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador e selecione **Modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="0eb14-146">Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **interface do cliente.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="0eb14-147">Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="0eb14-148">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-148">Select **OK**.</span></span> <span data-ttu-id="0eb14-149">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="0eb14-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="0eb14-150">Usar a Política de Grupo para ocultar notificações de reinicialização</span><span class="sxs-lookup"><span data-stu-id="0eb14-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="0eb14-151">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="0eb14-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="0eb14-152">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="0eb14-153">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="0eb14-154">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="0eb14-155">Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **interface do cliente.**</span><span class="sxs-lookup"><span data-stu-id="0eb14-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="0eb14-156">Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="0eb14-157">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0eb14-157">Select **OK**.</span></span> <span data-ttu-id="0eb14-158">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="0eb14-158">This will prevent additional notifications from appearing.</span></span>

