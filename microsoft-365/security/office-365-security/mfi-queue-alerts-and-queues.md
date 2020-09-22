---
title: Ideias de filas no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender a usar o widget filas no painel de fluxo de emails no centro de conformidade do & de segurança para monitorar o fluxo de emails sem êxito em suas organizações locais ou de parceiros em relação a conectores de saída.
ms.openlocfilehash: 3291a21828215d0a2a99c2226147bb1b748b8469
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199284"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="8605d-103">Informações sobre filas no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="8605d-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8605d-104">Quando as mensagens não podem ser enviadas da sua organização para seus servidores de email locais ou parceiros usando conectores, as mensagens são enfileiradas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8605d-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="8605d-105">Exemplos comuns que causam essa condição são:</span><span class="sxs-lookup"><span data-stu-id="8605d-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="8605d-106">O conector está configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="8605d-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="8605d-107">Houve alterações de rede ou firewall no seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="8605d-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="8605d-108">A Microsoft 365 continuará a tentar a entrega por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8605d-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="8605d-109">Após 24 horas, as mensagens expirarão e serão retornadas aos remetentes nas notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução).</span><span class="sxs-lookup"><span data-stu-id="8605d-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="8605d-110">Se o volume de email em fila exceder o limite predefinido (o valor padrão é 200), as informações estarão disponíveis nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="8605d-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="8605d-111">As **filas** insights no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade de & de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="8605d-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8605d-112">Para obter mais informações, consulte a [visão de filas no painel de fluxo de emails](#queues-insight-in-the-mail-flow-dashboard) deste tópico.</span><span class="sxs-lookup"><span data-stu-id="8605d-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="8605d-113">Um alerta é exibido em **alertas recentes** no painel de alertas no [centro de conformidade & segurança](https://protection.office.com) (painel de**alertas** \> **Dashboard** ou <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="8605d-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Alertas recentes no painel de alertas no centro de conformidade & segurança](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="8605d-115">Os administradores receberão uma notificação por email com base na configuração da política de alerta padrão chamada **as mensagens foram atrasadas**.</span><span class="sxs-lookup"><span data-stu-id="8605d-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="8605d-116">Para definir as configurações de notificação para este alerta, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="8605d-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="8605d-117">Para obter mais informações sobre políticas de alerta, consulte [políticas de alerta no centro de conformidade de & de segurança](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8605d-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="8605d-118">Personalizar alertas de fila</span><span class="sxs-lookup"><span data-stu-id="8605d-118">Customize queue alerts</span></span>

1. <span data-ttu-id="8605d-119">No [centro de conformidade & segurança](https://protection.office.com), vá para **Alerts** \> **políticas de alerta** de alertas ou abrir <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="8605d-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="8605d-120">Na página **políticas de alerta** , localize e selecione a política denominada **mensagens foram atrasadas**.</span><span class="sxs-lookup"><span data-stu-id="8605d-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="8605d-121">Na **mensagem com submenu com atraso** que é aberto, você pode ativar ou desativar o alerta e definir as configurações de notificação.</span><span class="sxs-lookup"><span data-stu-id="8605d-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Detalhes da política de alerta de mensagens atrasadas o centro de conformidade & segurança](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="8605d-123">**Status**: você pode ativar ou desativar o alerta.</span><span class="sxs-lookup"><span data-stu-id="8605d-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="8605d-124">**Destinatários de email** e **limite de notificação diária**: clique em **Editar** para definir as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8605d-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="8605d-125">Para definir as configurações de notificação, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8605d-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="8605d-126">No submenu **Editar política** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8605d-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8605d-127">**Enviar notificações por email**: o valor padrão é ativado.</span><span class="sxs-lookup"><span data-stu-id="8605d-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="8605d-128">**Destinatários de email**: o valor padrão é **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="8605d-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="8605d-129">**Limite diário de notificação**: o valor padrão é **sem limite**.</span><span class="sxs-lookup"><span data-stu-id="8605d-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="8605d-130">**Limite**: o valor padrão é 200.</span><span class="sxs-lookup"><span data-stu-id="8605d-130">**Threshold**: The default value is 200.</span></span>

   ![As configurações de notificação nas mensagens foram atrasadas detalhes da política de alerta o centro de conformidade & segurança](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="8605d-132">Quando tiver terminado, clique em **salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="8605d-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="8605d-133">Ideias de filas no painel de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="8605d-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="8605d-134">Mesmo que o volume da mensagem na fila não tenha excedido o limite e gerado um alerta, você ainda pode usar a percepção de **filas** no [painel de fluxo de emails](mail-flow-insights-v2.md) para ver as mensagens que foram enfileiradas por mais de uma hora e tomar medidas antes que o número de mensagens em fila fique muito grande.</span><span class="sxs-lookup"><span data-stu-id="8605d-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget filas no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-queues-widget.png)

<span data-ttu-id="8605d-136">Se você clicar no número de mensagens no widget, um submenu de **mensagens em fila** aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8605d-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="8605d-137">**Número de mensagens em fila**</span><span class="sxs-lookup"><span data-stu-id="8605d-137">**Number of queued messages**</span></span>
- <span data-ttu-id="8605d-138">**Nome do conector**: clique no nome do conector para gerenciar o conector no centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="8605d-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="8605d-139">**Hora da fila de início**</span><span class="sxs-lookup"><span data-stu-id="8605d-139">**Queue started time**</span></span>
- <span data-ttu-id="8605d-140">**As mensagens mais antigas expiraram**</span><span class="sxs-lookup"><span data-stu-id="8605d-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="8605d-141">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="8605d-141">**Destination server**</span></span>
- <span data-ttu-id="8605d-142">**Último endereço IP**</span><span class="sxs-lookup"><span data-stu-id="8605d-142">**Last IP address**</span></span>
- <span data-ttu-id="8605d-143">**Último erro**</span><span class="sxs-lookup"><span data-stu-id="8605d-143">**Last error**</span></span>
- <span data-ttu-id="8605d-144">**Como corrigir**: problemas comuns e soluções estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8605d-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="8605d-145">Se houver um link **corrigir agora** disponível, clique nele para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="8605d-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="8605d-146">Caso contrário, clique em qualquer link disponível para obter mais informações sobre o erro e as soluções possíveis.</span><span class="sxs-lookup"><span data-stu-id="8605d-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Detalhes depois de clicar na visão filas no painel de fluxo de emails](../../media/mfi-queues-details.png)

<span data-ttu-id="8605d-148">O mesmo submenu é exibido depois que você clica em **Exibir fila** nos detalhes de um alerta de **mensagens foram atrasadas** .</span><span class="sxs-lookup"><span data-stu-id="8605d-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Os detalhes de alerta de mensagens foram atrasadas no centro de conformidade de & de segurança](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="8605d-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="8605d-150">See also</span></span>

<span data-ttu-id="8605d-151">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="8605d-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
