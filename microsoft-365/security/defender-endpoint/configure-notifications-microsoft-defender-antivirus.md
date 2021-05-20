---
title: Configure notificações Microsoft Defender Antivírus
description: Saiba como configurar e personalizar notificações de Microsoft Defender Antivírus padrão e adicionais em pontos finais.
keywords: notificações, defender, antivírus, ponto final, gerenciamento, administração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572340"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="9ea92-104">Configure as notificações que aparecem em pontos finais</span><span class="sxs-lookup"><span data-stu-id="9ea92-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="9ea92-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9ea92-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ea92-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9ea92-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9ea92-107">Em Windows 10, as notificações de aplicativos sobre detecção e remediação de malware são mais robustas, consistentes e concisas.</span><span class="sxs-lookup"><span data-stu-id="9ea92-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="9ea92-108">As notificações aparecem nos pontos finais quando acionadas manualmente e as varreduras programadas são concluídas e as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="9ea92-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="9ea92-109">Essas notificações também aparecem na Central de **Notificação**, e um resumo de varreduras e detecções de ameaças aparecem em intervalos de tempo regulares.</span><span class="sxs-lookup"><span data-stu-id="9ea92-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="9ea92-110">Você também pode configurar como as notificações padrão aparecem em pontos finais, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.</span><span class="sxs-lookup"><span data-stu-id="9ea92-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="9ea92-111">Configure as notificações adicionais que aparecem em pontos finais</span><span class="sxs-lookup"><span data-stu-id="9ea92-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="9ea92-112">Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no [aplicativo Segurança do Windows](microsoft-defender-security-center-antivirus.md) e com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="9ea92-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="9ea92-113">Em Windows 10, a versão 1607 do recurso foi chamada **de Notificações Aprimoradas** e poderia ser configurada sob **Windows Configurações**  >  **Update & Windows Defender de segurança**  >  .</span><span class="sxs-lookup"><span data-stu-id="9ea92-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="9ea92-114">Nas configurações de Política de Grupo em todas as versões de Windows 10, são **chamadas notificações aprimoradas**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ea92-115">A desativação de notificações adicionais não desativará notificações críticas, como alertas de detecção e remediação de ameaças.</span><span class="sxs-lookup"><span data-stu-id="9ea92-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="9ea92-116">**Use o aplicativo Segurança do Windows para desativar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="9ea92-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="9ea92-117">Abra o aplicativo Segurança do Windows clicando no ícone do escudo na barra de tarefas ou pesquisando no menu iniciar para **segurança**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="9ea92-118">Selecione o vírus & ladrilho **de proteção contra ameaças** (ou o ícone do escudo na barra de menu esquerda) e, em seguida, selecione **Configurações de proteção contra ameaças do Vírus &**</span><span class="sxs-lookup"><span data-stu-id="9ea92-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="9ea92-119">Role para a seção **Notificações** e clique em **Alterar as configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="9ea92-120">Deslize o interruptor para **Desligar** ou **Ligar** para desativar ou ativar notificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="9ea92-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="9ea92-121">**Use a Política de Grupo para desativar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="9ea92-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="9ea92-122">No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9ea92-123">No **Editor de Gerenciamento de Políticas de Grupo** vá para **configuração de computador**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9ea92-124">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9ea92-125">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="9ea92-126">Clique duas **vezes Desligue notificações aprimoradas** e defina a opção para **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="9ea92-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-127">Click **OK**.</span></span> <span data-ttu-id="9ea92-128">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="9ea92-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="9ea92-129">Configure notificações padrão em pontos finais</span><span class="sxs-lookup"><span data-stu-id="9ea92-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="9ea92-130">Você pode usar a Política de Grupo para:</span><span class="sxs-lookup"><span data-stu-id="9ea92-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="9ea92-131">Exibir texto adicional e personalizado em pontos finais quando o usuário precisa executar uma ação</span><span class="sxs-lookup"><span data-stu-id="9ea92-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="9ea92-132">Ocultar todas as notificações em pontos finais</span><span class="sxs-lookup"><span data-stu-id="9ea92-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="9ea92-133">Ocultar notificações de reinicialização em pontos finais</span><span class="sxs-lookup"><span data-stu-id="9ea92-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="9ea92-134">Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a interface Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="9ea92-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="9ea92-135">Consulte [Impedir que os usuários vejam ou interajam com a interface de usuário Microsoft Defender Antivírus](prevent-end-user-interaction-microsoft-defender-antivirus.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9ea92-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="9ea92-136">Ocultar notificações só ocorrerá em pontos finais aos quais a política foi implantada.</span><span class="sxs-lookup"><span data-stu-id="9ea92-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="9ea92-137">Notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda aparecerão no [painel de monitoramento de Microsoft Endpoint Manager Endpoint Protection e relatórios](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="9ea92-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="9ea92-138">Consulte [Personalizar o aplicativo Segurança do Windows para sua organização](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em suas máquinas.</span><span class="sxs-lookup"><span data-stu-id="9ea92-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="9ea92-139">**Use a Política de Grupo para ocultar notificações:**</span><span class="sxs-lookup"><span data-stu-id="9ea92-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="9ea92-140">No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="9ea92-141">No **Editor de Gerenciamento de Políticas de Grupo** vá para a **configuração de computador** e clique em **modelos administrativos**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9ea92-142">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > interface cliente**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="9ea92-143">Clique duas vezes **em Suprimir todas as notificações** e defina a opção para **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="9ea92-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-144">Click **OK**.</span></span> <span data-ttu-id="9ea92-145">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="9ea92-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="9ea92-146">**Use a política do grupo para ocultar notificações de reinicialização:**</span><span class="sxs-lookup"><span data-stu-id="9ea92-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="9ea92-147">No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9ea92-148">No **Editor de Gerenciamento de Políticas de Grupo** vá para **configuração de computador**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="9ea92-149">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="9ea92-150">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > interface cliente**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="9ea92-151">Clique duas vezes **em Suprimir notificações de reinicialização** e defina a opção para **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="9ea92-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ea92-152">Click **OK**.</span></span> <span data-ttu-id="9ea92-153">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="9ea92-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ea92-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ea92-154">Related topics</span></span>

- [<span data-ttu-id="9ea92-155">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="9ea92-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9ea92-156">Configure a interação do usuário final com Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="9ea92-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
