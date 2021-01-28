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
description: Os administradores podem aprender a usar o mapa de fluxo de emails no painel Fluxo de emails no Centro de Conformidade e Segurança para visualizar e controlar como os emails fluem de e para sua organização sobre conectores e sem usar conectores. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c07730f3abcec8905285cdfdf1579ffb71573ec1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029913"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="18ecc-103">Mapa de fluxo de emails no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="18ecc-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="18ecc-104">O **mapa de fluxo de** emails no painel [Fluxo](mail-flow-insights-v2.md) de emails no Centro de Conformidade e Segurança & [fornece](https://protection.office.com) informações sobre como os emails fluem pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="18ecc-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="18ecc-105">Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas à medida que eles ocorrem.</span><span class="sxs-lookup"><span data-stu-id="18ecc-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget de mapa de fluxo de emails no painel Fluxo de emails no Centro de Conformidade e & Segurança](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="18ecc-107">Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como *diagrama Sankey.*</span><span class="sxs-lookup"><span data-stu-id="18ecc-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="18ecc-108">Você pode usar a seta para a esquerda e a seta para a direita para ![ mostrar informações de dias ](../../media/scc-left-arrow.png) ![ ](../../media/scc-right-arrow.png) diferentes.</span><span class="sxs-lookup"><span data-stu-id="18ecc-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="18ecc-109">Cada cor diferente representa o fluxo de emails em um conector de entrada ou de saída diferente (ou sem usar conectores).</span><span class="sxs-lookup"><span data-stu-id="18ecc-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="18ecc-110">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="18ecc-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="18ecc-111">Exibição de relatório para o mapa de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="18ecc-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="18ecc-112">Clicar no widget mapa de **fluxo de** emails levará você para o relatório de mapa de **fluxo de** email.</span><span class="sxs-lookup"><span data-stu-id="18ecc-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="18ecc-113">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="18ecc-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="18ecc-114">**Mostrar dados para: Visão geral:** é basicamente uma exibição maior do widget.</span><span class="sxs-lookup"><span data-stu-id="18ecc-114">**Show data for: Overview**: This is basically a larger view of the widget.</span></span> <span data-ttu-id="18ecc-115">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="18ecc-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="18ecc-117">**Mostrar dados para: Detalhe:** esta exibição mostra detalhes sobre os conectores e domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="18ecc-117">**Show data for: Detail**: This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="18ecc-118">Os principais domínios de remetentes e destinatários são listados, e o restante é colocado em **Outros.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="18ecc-119">Se você passar o mouse sobre uma cor e uma seção específicas, o número de mensagens será exibido.</span><span class="sxs-lookup"><span data-stu-id="18ecc-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Exibição detalhada no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="18ecc-121">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="18ecc-122">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="18ecc-123">Informações relacionadas são mostradas abaixo do mapa de fluxo de email se elas estão disponíveis (por exemplo, o insight de correção de [possível loop de email).](mfi-mail-loop-insight.md)</span><span class="sxs-lookup"><span data-stu-id="18ecc-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="18ecc-124">Details table view for the Mail flow map</span><span class="sxs-lookup"><span data-stu-id="18ecc-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="18ecc-125">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="18ecc-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="18ecc-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="18ecc-126">**Date**</span></span>
- <span data-ttu-id="18ecc-127">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="18ecc-127">**Category**</span></span>
- <span data-ttu-id="18ecc-128">**Conector/Provedor de serviços de terceiros**</span><span class="sxs-lookup"><span data-stu-id="18ecc-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="18ecc-129">**Domínio remetente/destinatário**</span><span class="sxs-lookup"><span data-stu-id="18ecc-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="18ecc-130">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="18ecc-130">**Message count**</span></span>

<span data-ttu-id="18ecc-131">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="18ecc-132">Se você selecionar uma linha, detalhes semelhantes serão mostrados em um flyout:</span><span class="sxs-lookup"><span data-stu-id="18ecc-132">If you select a row, similar details are shown in a flyout:</span></span>

![Detalhes do flyout da tabela de detalhes no mapa de fluxo de emails](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="18ecc-134">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="18ecc-135">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="18ecc-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="18ecc-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="18ecc-136">See also</span></span>

<span data-ttu-id="18ecc-137">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="18ecc-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
