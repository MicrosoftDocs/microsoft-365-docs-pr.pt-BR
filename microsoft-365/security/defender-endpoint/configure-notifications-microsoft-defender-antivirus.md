---
title: Configurar Microsoft Defender Antivírus notificações
description: Saiba como configurar e personalizar notificações Microsoft Defender Antivírus padrão e adicionais nos pontos de extremidade.
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
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926233"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="b2dfa-104">Configurar as notificações exibidas nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="b2dfa-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-105">**Applies to:**</span></span>

- [<span data-ttu-id="b2dfa-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b2dfa-107">Em Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="b2dfa-108">As notificações são exibidas nos pontos de extremidade quando as verificações acionadas manualmente e agendadas são concluídas e as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="b2dfa-109">Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="b2dfa-110">Você também pode configurar como as notificações padrão aparecem nos pontos de extremidade, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="b2dfa-111">Configurar as notificações adicionais que aparecem nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="b2dfa-112">Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo Segurança do Windows [e](microsoft-defender-security-center-antivirus.md) com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="b2dfa-113">No Windows 10, versão 1607, o  recurso era chamado notificações aprimoradas e poderia ser configurado em **Windows Configurações**  >  **Atualização &** segurança  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="b2dfa-114">Nas configurações da Política de Grupo em todas as versões do Windows 10, ela é chamada **notificações aprimoradas**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2dfa-115">Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="b2dfa-116">**Use o Segurança do Windows para desabilitar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="b2dfa-117">Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="b2dfa-118">Selecione **O &** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, selecione **Configurações** de proteção contra vírus & ameaças</span><span class="sxs-lookup"><span data-stu-id="b2dfa-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="b2dfa-119">Role até a **seção Notificações** e clique em **Alterar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="b2dfa-120">Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="b2dfa-121">**Use a Política de Grupo para desabilitar notificações adicionais:**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="b2dfa-122">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b2dfa-123">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b2dfa-124">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="b2dfa-125">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="b2dfa-126">Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="b2dfa-127">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-127">Click **OK**.</span></span> <span data-ttu-id="b2dfa-128">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="b2dfa-129">Configurar notificações padrão em pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="b2dfa-130">Você pode usar a Política de Grupo para:</span><span class="sxs-lookup"><span data-stu-id="b2dfa-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="b2dfa-131">Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação</span><span class="sxs-lookup"><span data-stu-id="b2dfa-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="b2dfa-132">Ocultar todas as notificações nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="b2dfa-133">Ocultar notificações de reinicialização nos pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b2dfa-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="b2dfa-134">Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a Microsoft Defender Antivírus interface.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="b2dfa-135">Consulte [Impedir que os usuários vejam ou interajam](prevent-end-user-interaction-microsoft-defender-antivirus.md) com Microsoft Defender Antivírus interface do usuário para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="b2dfa-136">Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="b2dfa-137">As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento Microsoft Endpoint Manager Endpoint Protection [relatórios.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="b2dfa-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="b2dfa-138">Consulte [Personalizar o aplicativo Segurança do Windows para sua](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) organização para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em seus máquinas.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="b2dfa-139">**Use a Política de Grupo para ocultar notificações:**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="b2dfa-140">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="b2dfa-141">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="b2dfa-142">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Interface do Cliente.**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="b2dfa-143">Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="b2dfa-144">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-144">Click **OK**.</span></span> <span data-ttu-id="b2dfa-145">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="b2dfa-146">**Use a Política de Grupo para ocultar notificações de reinicialização:**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="b2dfa-147">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b2dfa-148">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b2dfa-149">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="b2dfa-150">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Interface do Cliente.**</span><span class="sxs-lookup"><span data-stu-id="b2dfa-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="b2dfa-151">Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="b2dfa-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-152">Click **OK**.</span></span> <span data-ttu-id="b2dfa-153">Isso impedirá que notificações adicionais apareçam.</span><span class="sxs-lookup"><span data-stu-id="b2dfa-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2dfa-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b2dfa-154">Related topics</span></span>

- [<span data-ttu-id="b2dfa-155">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="b2dfa-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b2dfa-156">Configurar a interação do usuário final com Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="b2dfa-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
