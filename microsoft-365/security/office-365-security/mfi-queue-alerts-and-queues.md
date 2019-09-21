---
title: Alertas de filas e filas
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: Os administradores podem aprender sobre alertas de fila e filas no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: ef8b4acd4008f3039030049893f83a5e49e1efc2
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073671"
---
# <a name="queue-alerts-and-queues"></a><span data-ttu-id="bda0c-103">Alertas de filas e filas</span><span class="sxs-lookup"><span data-stu-id="bda0c-103">Queue alerts and Queues</span></span>

## <a name="queue-alerts"></a><span data-ttu-id="bda0c-104">Alertas de fila</span><span class="sxs-lookup"><span data-stu-id="bda0c-104">Queue alerts</span></span>

<span data-ttu-id="bda0c-105">Quando as mensagens não podem ser enviadas da sua organização do Office 365 para seus servidores de email locais ou parceiros usando conectores, as mensagens são enfileiradas no Office 365.</span><span class="sxs-lookup"><span data-stu-id="bda0c-105">When messages can't be sent from your Office 365 organization to your on-premises or partner email servers using connectors, the messages are queued in Office 365.</span></span> <span data-ttu-id="bda0c-106">Exemplos comuns que causam essa condição são:</span><span class="sxs-lookup"><span data-stu-id="bda0c-106">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="bda0c-107">O conector está configurado incorretamente.</span><span class="sxs-lookup"><span data-stu-id="bda0c-107">The connector is incorrectly configured.</span></span>

- <span data-ttu-id="bda0c-108">Houve alterações de rede ou firewall no seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="bda0c-108">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="bda0c-109">O Office 365 continuará a tentar a entrega por 48 horas.</span><span class="sxs-lookup"><span data-stu-id="bda0c-109">Office 365 will continue to retry to delivery for 48 hours.</span></span> <span data-ttu-id="bda0c-110">Após 48 horas, as mensagens expirarão e serão retornadas para os remetentes nas notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução).</span><span class="sxs-lookup"><span data-stu-id="bda0c-110">After 48 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="bda0c-111">Se o volume de email em fila exceder o limite predefinido (o valor padrão é 2000), os alertas estarão disponíveis no painel de fluxo de emails em **alertas recentes**, e os administradores receberão uma notificação por email (para o endereço de email alternativo) .</span><span class="sxs-lookup"><span data-stu-id="bda0c-111">If the queued email volume exceeds the pre-defined threshold (the default value is 2000 messages), the alerts will be available in the mail flow dashboard at **Recent alerts**, and admins will receive an email notification (to their alternative email address).</span></span> <span data-ttu-id="bda0c-112">Para configurar o limite de alerta, o limite de notificação diária e/ou os destinatários do alerta, consulte a seção **Personalizar alertas de fila** abaixo.</span><span class="sxs-lookup"><span data-stu-id="bda0c-112">To configure the alert threshold, daily notification limit, and/or recipients of the alert, see the **Customize queue alerts** section below.</span></span>

![Enfileirar alertas na área de alertas recentes do painel de fluxo de emails no centro de conformidade & segurança](../media/5fc4a51c-6118-4270-960b-c6b176ef94ae.png)

## <a name="customize-queue-alerts"></a><span data-ttu-id="bda0c-114">Personalizar alertas de fila</span><span class="sxs-lookup"><span data-stu-id="bda0c-114">Customize queue alerts</span></span>

<span data-ttu-id="bda0c-115">Informações de fluxo de emails criar uma política de alerta chamada **mensagens atrasadas** (a caixa de seleção **enviar notificações por email** na captura de tela de exemplo abaixo) foi encontrada em **alertas** \> **políticas de alerta**.</span><span class="sxs-lookup"><span data-stu-id="bda0c-115">Mail flow insights create an alert policy named **Messages have been delayed** (the **Send email notifications** check box in the example screen shot below) found in **Alerts** \> **Alert Policies**.</span></span> <span data-ttu-id="bda0c-116">Você pode modificar os destinatários de limite e alerta clicando na política.</span><span class="sxs-lookup"><span data-stu-id="bda0c-116">You can modify the threshold and alert recipients by clicking on the policy.</span></span>

![Navegação de alertas](../media/efb95976-9e0b-484e-a2fd-093c5bc7a40f.png)

<span data-ttu-id="bda0c-118">Você verá uma nova folha de informações de política, agora é possível clicar em **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="bda0c-118">You'll see a new policy information blade, you can now click **Edit Policy**.</span></span>

![Editar Política ](../media/ed2aceae-3ee2-4849-a17e-87915987a7dd.png)

<span data-ttu-id="bda0c-120">A lâmina de informações será alterada para a **política de edição**.</span><span class="sxs-lookup"><span data-stu-id="bda0c-120">The information blade will change to the **Edit Policy**.</span></span> <span data-ttu-id="bda0c-121">Agora você pode alterar os destinatários para o email de alerta, o limite do número de notificações enviadas por dia e o limite mínimo para acionar o alerta (200 ou mais).</span><span class="sxs-lookup"><span data-stu-id="bda0c-121">You can now change the recipients for the alert email, the limit on the number of notifications sent per day, and the minimum threshold to trigger the alert (200 or more).</span></span>

![Editar folha de política](../media/c657cc74-7867-474c-b2c9-dc478449f990.png)

## <a name="queue-alert-details"></a><span data-ttu-id="bda0c-123">Detalhes de alerta da fila</span><span class="sxs-lookup"><span data-stu-id="bda0c-123">Queue alert details</span></span>

<span data-ttu-id="bda0c-124">Quando você clica no alerta, os detalhes de alerta aparecem em um painel de submenu.</span><span class="sxs-lookup"><span data-stu-id="bda0c-124">When you click the alert, the alert details appear in a flyout pane.</span></span>

![Selecione um alerta de fila na área de alerta recentes do painel de fluxo de emails no centro de conformidade & segurança](../media/1f6b0e96-5b2c-41ef-9684-9d813b3fabe6.png)

![O submenu detalhes da fila de alerta no centro de conformidade & segurança](../media/105c8fff-912f-4763-8806-2740ebdecd4b.png)

<span data-ttu-id="bda0c-127">Você pode clicar em **Exibir fila** nos detalhes do alerta para ver os detalhes da fila, os problemas e os links para as correções disponíveis em um novo painel de submenu.</span><span class="sxs-lookup"><span data-stu-id="bda0c-127">You can click **View queue** in the alert details to see the queue details, problems, and links to the available fixes in a new flyout pane.</span></span>

![O submenu detalhes da fila de alerta no centro de conformidade & segurança](../media/8ff60955-55ef-4f32-a966-85e02cb608d1.png)

![Exibir fila nos detalhes do alerta](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="queues"></a><span data-ttu-id="bda0c-130">Filas</span><span class="sxs-lookup"><span data-stu-id="bda0c-130">Queues</span></span>

<span data-ttu-id="bda0c-131">Mesmo que o volume da mensagem na fila não tenha excedido o limite, você ainda pode usar a área **filas** do painel de fluxo de email para ver as mensagens que foram enfileiradas por mais de uma hora.</span><span class="sxs-lookup"><span data-stu-id="bda0c-131">Even if the queued message volume hasn't exceeded the threshold, you can still use the **Queues** area of the mail flow dashboard to see messages that have been queued for more than one hour.</span></span> <span data-ttu-id="bda0c-132">Você pode usar a área **filas** para monitorar o número de mensagens em fila (o valor 0 indica que o fluxo de emails está ok) e tomar medidas antes que o número de mensagens na fila fique muito grande.</span><span class="sxs-lookup"><span data-stu-id="bda0c-132">You can use the **Queues** area to monitor the number of queued messages (the value 0 indicates mail flow is OK) and take action before the number of queued messages becomes too large.</span></span>

![Filas no painel de fluxo de emails no centro de conformidade de & de segurança](../media/0ef6e2ef-dd22-4363-9d4a-b20a00babc9f.png)

<span data-ttu-id="bda0c-134">Quando você **clica no número**de mensagens em filas, os detalhes e a orientação da fila para corrigir o problema aparecerão em um painel de submenu (o mesmo submenu exibido depois que você clicar em **Exibir fila** nos detalhes de um alerta de fila).</span><span class="sxs-lookup"><span data-stu-id="bda0c-134">When you click the number of queued messages in **Queues**, the queue details and guidance for how to fix the issue will appear in a flyout pane (the same flyout that appears after you click **View queue** in the details of a queue alert).</span></span>

![Detalhes da fila](../media/4eb088fe-5dd9-4bf4-b959-c1bb2545c515.png)

## <a name="see-also"></a><span data-ttu-id="bda0c-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="bda0c-136">See also</span></span>

<span data-ttu-id="bda0c-137">Para obter mais informações sobre outros insights de fluxo de email no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="bda0c-137">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
