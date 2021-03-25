---
title: Introspecção de filas no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender a usar o widget Queues no painel de fluxo de email no Centro de Conformidade de Segurança & para monitorar o fluxo de emails malsucedido para suas organizações locais ou parceiras por meio de conectores de saída.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203407"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="a4bdf-103">Visão de filas no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="a4bdf-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4bdf-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-104">**Applies to**</span></span>
- [<span data-ttu-id="a4bdf-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4bdf-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a4bdf-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a4bdf-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a4bdf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a4bdf-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a4bdf-108">Quando as mensagens não podem ser enviadas da sua organização para seus servidores de email locais ou parceiros usando conectores, as mensagens são enluadas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="a4bdf-109">Exemplos comuns que causam essa condição são:</span><span class="sxs-lookup"><span data-stu-id="a4bdf-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="a4bdf-110">O conector está configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="a4bdf-111">Houve alterações de rede ou firewall em seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="a4bdf-112">O Microsoft 365 continuará a tentar novamente a entrega por 24 horas.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="a4bdf-113">Após 24 horas, as mensagens expiram e serão retornadas para os envios em relatórios de não entrega (também conhecidos como NDRs ou mensagens de rejeição).</span><span class="sxs-lookup"><span data-stu-id="a4bdf-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="a4bdf-114">Se o volume de email em fila exceder o limite pré-definido (o valor padrão é 200 mensagens), as informações estarão disponíveis nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="a4bdf-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="a4bdf-115">O **insight Filas** no [painel de fluxo de](mail-flow-insights-v2.md) emails no Centro de Conformidade & [Segurança.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="a4bdf-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="a4bdf-116">Para obter mais informações, consulte o [insight Filas na seção Painel de fluxo de](#queues-insight-in-the-mail-flow-dashboard) emails neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="a4bdf-117">Um alerta é exibido em **Alertas** recentes do painel Alertas no Centro de Conformidade & Segurança [(](https://protection.office.com) Painel de **Alertas** \>  ou <https://protection.office.com/alertsdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="a4bdf-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![Alertas recentes no painel Alertas no Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="a4bdf-119">Os administradores receberão uma notificação de email com base na configuração da política de alerta padrão chamada **Mensagens foram adiadas.**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="a4bdf-120">Para definir as configurações de notificação para esse alerta, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="a4bdf-121">Para obter mais informações sobre políticas de alerta, consulte Políticas de alerta no Centro de [Conformidade & Segurança.](../../compliance/alert-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a4bdf-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="a4bdf-122">Personalizar alertas de fila</span><span class="sxs-lookup"><span data-stu-id="a4bdf-122">Customize queue alerts</span></span>

1. <span data-ttu-id="a4bdf-123">No Centro [de Conformidade & segurança,](https://protection.office.com)acesse **Políticas de** \> **Alertas ou** abra <https://protection.office.com/alertpolicies> .</span><span class="sxs-lookup"><span data-stu-id="a4bdf-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="a4bdf-124">Na página **Políticas de alerta,** encontre e selecione a política chamada **Mensagens que foram adiadas**.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="a4bdf-125">Na **mensagem que foi adiada,** você pode ativar ou desativar o alerta e definir as configurações de notificação.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![Mensagens foram adiadas detalhes da política de alerta do Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="a4bdf-127">**Status**: você pode alternar ou desligar o alerta.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="a4bdf-128">**Destinatários de email** e **limite de notificação diária**: Clique em **Editar** para definir as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a4bdf-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="a4bdf-129">Para definir as configurações de notificação, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="a4bdf-130">No **sobrevoo Editar política** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a4bdf-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a4bdf-131">**Enviar notificações por email**: o valor padrão está em.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="a4bdf-132">**Destinatários de email**: o valor padrão **é TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="a4bdf-133">**Limite de notificação diário**: o valor padrão é **Sem limite**.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="a4bdf-134">**Limite**: o valor padrão é 200.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-134">**Threshold**: The default value is 200.</span></span>

   ![As configurações de notificação nas Mensagens foram adiadas detalhes da política de alerta do Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="a4bdf-136">Quando terminar, clique em **Salvar** e **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="a4bdf-137">Introspecção de filas no painel de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="a4bdf-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="a4bdf-138">Mesmo que o volume da mensagem enfileirada não tenha excedido o limite e [](mail-flow-insights-v2.md) gerado um alerta, você ainda poderá usar o insight **Filas** no painel de fluxo de emails para ver mensagens que foram enfileiradas por mais de uma hora e tomar medidas antes que o número de mensagens enfileiradas se torne muito grande.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![Widget de filas no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-queues-widget.png)

<span data-ttu-id="a4bdf-140">Se você clicar no número de  mensagens no widget, um sobrevoo de mensagens em fila aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="a4bdf-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="a4bdf-141">**Número de mensagens em fila**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-141">**Number of queued messages**</span></span>
- <span data-ttu-id="a4bdf-142">**Nome do** conector : clique no nome do conector para gerenciar o conector no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="a4bdf-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="a4bdf-143">**Hora de início da fila**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-143">**Queue started time**</span></span>
- <span data-ttu-id="a4bdf-144">**Mensagens mais antigas expiradas**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="a4bdf-145">**Servidor de destino**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-145">**Destination server**</span></span>
- <span data-ttu-id="a4bdf-146">**Último endereço IP**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-146">**Last IP address**</span></span>
- <span data-ttu-id="a4bdf-147">**Último erro**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-147">**Last error**</span></span>
- <span data-ttu-id="a4bdf-148">**Como corrigir**: Problemas comuns e soluções estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="a4bdf-149">Se for um **link Corrigir agora** está disponível, clique nele para corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="a4bdf-150">Caso contrário, clique em quaisquer links disponíveis para obter mais informações sobre o erro e possíveis soluções.</span><span class="sxs-lookup"><span data-stu-id="a4bdf-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![Detalhes após clicar no insight Filas no painel fluxo de emails](../../media/mfi-queues-details.png)

<span data-ttu-id="a4bdf-152">O mesmo flyout é exibido depois que você clica em **Exibir** fila nos detalhes de um alerta de mensagens **que foram adiadas.**</span><span class="sxs-lookup"><span data-stu-id="a4bdf-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![Mensagens foram adiadas detalhes do alerta no Centro de Conformidade & Segurança](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="a4bdf-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="a4bdf-154">See also</span></span>

<span data-ttu-id="a4bdf-155">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="a4bdf-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
