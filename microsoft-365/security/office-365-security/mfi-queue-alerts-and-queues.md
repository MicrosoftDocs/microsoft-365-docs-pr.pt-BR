---
title: Informações sobre filas no painel fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender a usar o & widget Filas no painel Fluxo de emails no Centro de Conformidade e Segurança para monitorar o fluxo de emails malsucedidos para suas organizações locais ou parceiras em conectores de saída.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8ee5ea37fa5a63b8035572059e419c400d66f3
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289432"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="8a3bb-103">Informações sobre filas no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="8a3bb-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8a3bb-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-104">**Applies to**</span></span>
- [<span data-ttu-id="8a3bb-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8a3bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8a3bb-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8a3bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="8a3bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a3bb-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="8a3bb-108">Quando as mensagens não puderem ser enviadas de sua organização para seus servidores de email locais ou parceiros usando conectores, as mensagens serão en filas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="8a3bb-109">Exemplos comuns que causam essa condição são:</span><span class="sxs-lookup"><span data-stu-id="8a3bb-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="8a3bb-110">O conector está configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="8a3bb-111">Houve alterações de rede ou firewall em seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="8a3bb-112">O Microsoft 365 continuará tentando fazer a entrega por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="8a3bb-113">Após 24 horas, as mensagens expiram e serão devolvidas aos rementes em notificações de não entrega (também conhecidas como NDRs ou mensagens de rejeição).</span><span class="sxs-lookup"><span data-stu-id="8a3bb-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="8a3bb-114">Se o volume de email na fila exceder o limite predefinido (o valor padrão é 200 mensagens), as informações estarão disponíveis nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="8a3bb-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="8a3bb-115">O **insight filas** no painel [de fluxo de](mail-flow-insights-v2.md) emails no Centro de conformidade & [segurança.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="8a3bb-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="8a3bb-116">Para obter mais informações, consulte o [insight filas na seção painel](#queues-insight-in-the-mail-flow-dashboard) de fluxo de email neste artigo.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="8a3bb-117">Um alerta é exibido em **Alertas** recentes do painel Alertas no Centro de Conformidade e Segurança [&](https://protection.office.com) ( Painel de **Alertas** \>  ou <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="8a3bb-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Alertas recentes no painel Alertas no Centro de Conformidade e & Segurança](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="8a3bb-119">Os administradores receberão uma notificação por email com base na configuração da política de alerta padrão chamada **Mensagens que foram adiadas.**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="8a3bb-120">Para definir as configurações de notificação para esse alerta, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="8a3bb-121">Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no Centro de Conformidade e & Segurança.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8a3bb-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="8a3bb-122">Personalizar alertas de fila</span><span class="sxs-lookup"><span data-stu-id="8a3bb-122">Customize queue alerts</span></span>

1. <span data-ttu-id="8a3bb-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="8a3bb-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="8a3bb-124">Na página **Políticas de alerta,** encontre e selecione a política chamada **Mensagens que foram atrasadas.**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="8a3bb-125">Na mensagem **que foi adiada, você** pode ativar ou desativar o alerta e definir as configurações de notificação.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![As mensagens atrasaram detalhes da política de alerta no Centro de Conformidade e & Segurança](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="8a3bb-127">**Status**: Você pode alternar ou desligar o alerta.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="8a3bb-128">**Destinatários de email** e **limite de notificação diária:** clique **em Editar** para definir as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8a3bb-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="8a3bb-129">Para definir as configurações de notificação, clique em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="8a3bb-130">No menu **Editar política** exibido, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8a3bb-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="8a3bb-131">**Enviar notificações por email:** o valor padrão está on.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="8a3bb-132">**Destinatários de email:** o valor padrão é **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="8a3bb-133">**Limite de notificação** diária: o valor padrão é **Sem limite.**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="8a3bb-134">**Limite:** o valor padrão é 200.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-134">**Threshold**: The default value is 200.</span></span>

   ![As configurações de notificação nas Mensagens atrasaram os detalhes da política de alerta no Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="8a3bb-136">Quando terminar, clique em **Salvar** e **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="8a3bb-137">Informações sobre filas no painel fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="8a3bb-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="8a3bb-138">Mesmo que o volume de mensagens na fila não tenha excedido o limite e [](mail-flow-insights-v2.md) gerado um alerta, você ainda poderá usar o insight de **Filas** no painel fluxo de emails para ver as mensagens que foram enfileiradas por mais de uma hora e tomar medidas antes que o número de mensagens na fila se torne muito grande.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget Filas no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-queues-widget.png)

<span data-ttu-id="8a3bb-140">Se você clicar no número de mensagens no widget, um flyout Mensagens **em fila** aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8a3bb-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="8a3bb-141">**Número de mensagens na fila**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-141">**Number of queued messages**</span></span>
- <span data-ttu-id="8a3bb-142">**Nome do** conector: clique no nome do conector para gerenciar o conector no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="8a3bb-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="8a3bb-143">**Hora de início da fila**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-143">**Queue started time**</span></span>
- <span data-ttu-id="8a3bb-144">**Mensagens mais antigas expiradas**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="8a3bb-145">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-145">**Destination server**</span></span>
- <span data-ttu-id="8a3bb-146">**Último endereço IP**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-146">**Last IP address**</span></span>
- <span data-ttu-id="8a3bb-147">**Último erro**</span><span class="sxs-lookup"><span data-stu-id="8a3bb-147">**Last error**</span></span>
- <span data-ttu-id="8a3bb-148">**Como corrigir:** Problemas comuns e soluções estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="8a3bb-149">Se for um **link Corrigir agora** está disponível, clique nele para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="8a3bb-150">Caso contrário, clique em qualquer link disponível para obter mais informações sobre o erro e possíveis soluções.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Detalhes depois de clicar no insight Filas no painel Fluxo de emails](../../media/mfi-queues-details.png)

<span data-ttu-id="8a3bb-152">O mesmo flyout é exibido depois que você **clica** em Exibir fila nos detalhes de um alerta de **atraso de** mensagens.</span><span class="sxs-lookup"><span data-stu-id="8a3bb-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Mensagens atrasaram detalhes de alerta no Centro de Conformidade e Segurança & segurança](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="8a3bb-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a3bb-154">See also</span></span>

<span data-ttu-id="8a3bb-155">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8a3bb-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
