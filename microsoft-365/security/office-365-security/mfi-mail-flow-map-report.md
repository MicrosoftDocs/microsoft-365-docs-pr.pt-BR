---
title: Mapa de fluxo de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o mapa de fluxo de email no painel de fluxo de email no Centro de Conformidade de Segurança & para visualizar e rastrear como o email flui de e para sua organização através de conectores e sem usar conectores.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e806dde2e6f3ddde5cce3b61c85fe0b024ba2fe
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203410"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="bcd18-103">Mapa de fluxo de emails no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="bcd18-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bcd18-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="bcd18-104">**Applies to**</span></span>
- [<span data-ttu-id="bcd18-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bcd18-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bcd18-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="bcd18-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="bcd18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcd18-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="bcd18-108">O **mapa de fluxo de** email [](https://protection.office.com) no [painel de](mail-flow-insights-v2.md) fluxo de email no Centro de Conformidade e Segurança & fornece informações sobre como o email flui pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="bcd18-108">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="bcd18-109">Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas à medida que elas ocorrem.</span><span class="sxs-lookup"><span data-stu-id="bcd18-109">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget de mapa de fluxo de email no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="bcd18-111">Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como diagrama *Sankey.*</span><span class="sxs-lookup"><span data-stu-id="bcd18-111">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="bcd18-112">Você pode usar a seta esquerda Seta à esquerda e a ![ ](../../media/scc-left-arrow.png) seta direita ![ para mostrar informações de dias ](../../media/scc-right-arrow.png) diferentes.</span><span class="sxs-lookup"><span data-stu-id="bcd18-112">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="bcd18-113">Cada cor diferente representa o fluxo de emails sobre um conector de entrada ou de saída diferente (ou sem usar conectores).</span><span class="sxs-lookup"><span data-stu-id="bcd18-113">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="bcd18-114">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="bcd18-114">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="bcd18-115">Exibição de relatório para o mapa de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="bcd18-115">Report view for the Mail flow map</span></span>

<span data-ttu-id="bcd18-116">Clicar no widget de mapa **de fluxo** de email levará você ao relatório de mapa de **fluxo de** email.</span><span class="sxs-lookup"><span data-stu-id="bcd18-116">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="bcd18-117">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="bcd18-117">The following charts are available in the report view:</span></span>

- <span data-ttu-id="bcd18-118">**Mostrar dados para: Visão geral:** é basicamente uma exibição maior do widget.</span><span class="sxs-lookup"><span data-stu-id="bcd18-118">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="bcd18-119">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="bcd18-119">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="bcd18-121">**Mostrar dados para: Detalhe**: Este exibição mostra detalhes sobre os conectores e domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="bcd18-121">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="bcd18-122">Os domínios do remetente superior e do destinatário são listados, e o restante é colocado em **Outros**.</span><span class="sxs-lookup"><span data-stu-id="bcd18-122">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="bcd18-123">Se você passar o mouse sobre uma cor e seção específicas, o número de mensagens será exibido.</span><span class="sxs-lookup"><span data-stu-id="bcd18-123">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Exibição detalhada no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="bcd18-125">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="bcd18-125">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bcd18-126">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="bcd18-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="bcd18-127">Informações relacionadas são mostradas abaixo do mapa de fluxo de email se eles estão disponíveis (por exemplo, o [insight corrigir possível loop de email](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="bcd18-127">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="bcd18-128">Exibição de tabela de detalhes para o mapa de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="bcd18-128">Details table view for the Mail flow map</span></span>

<span data-ttu-id="bcd18-129">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="bcd18-129">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="bcd18-130">**Date**</span><span class="sxs-lookup"><span data-stu-id="bcd18-130">**Date**</span></span>
- <span data-ttu-id="bcd18-131">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="bcd18-131">**Category**</span></span>
- <span data-ttu-id="bcd18-132">**Conector / provedor de serviços de terceiros**</span><span class="sxs-lookup"><span data-stu-id="bcd18-132">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="bcd18-133">**Domínio remetente/destinatário**</span><span class="sxs-lookup"><span data-stu-id="bcd18-133">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="bcd18-134">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="bcd18-134">**Message count**</span></span>

<span data-ttu-id="bcd18-135">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="bcd18-135">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="bcd18-136">Se você selecionar uma linha, detalhes semelhantes serão mostrados em um sobremenu:</span><span class="sxs-lookup"><span data-stu-id="bcd18-136">If you select a row, similar details are shown in a flyout:</span></span>

![Detalhes do sobremenu da tabela de detalhes no mapa de fluxo de email](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="bcd18-138">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="bcd18-138">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="bcd18-139">Para voltar à exibição de relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="bcd18-139">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcd18-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="bcd18-140">See also</span></span>

<span data-ttu-id="bcd18-141">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="bcd18-141">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
