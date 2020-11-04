---
title: Mapa de fluxo de email
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o mapa de fluxo de emails no painel de fluxo de emails no centro de conformidade de & de segurança para visualizar e controlar como o email flui para e de sua organização sobre os conectores e sem usar conectores.
ms.openlocfilehash: fc03f05db77c40dbf726692e6fb6069d587a5ffc
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877760"
---
# <a name="mail-flow-map-in-the-security--compliance-center"></a><span data-ttu-id="9973a-103">Mapa de fluxo de emails no centro de conformidade de & de segurança</span><span class="sxs-lookup"><span data-stu-id="9973a-103">Mail flow map in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9973a-104">O **mapa de fluxo de emails** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade do & de segurança](https://protection.office.com) fornece informações sobre como os emails fluem pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="9973a-104">The **Mail flow map** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives insight as to how mail flows through your organization.</span></span> <span data-ttu-id="9973a-105">Você pode usar essas informações para aprender padrões, identificar anomalias e corrigir problemas conforme eles ocorrem.</span><span class="sxs-lookup"><span data-stu-id="9973a-105">You can use this information to learn patterns, identify anomalies, and fix issues as they occur.</span></span>

![Widget mapa de fluxo de emails no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-mail-flow-map-widget.png)

<span data-ttu-id="9973a-107">Por padrão, o widget mostra o padrão de fluxo de emails do dia anterior em um gráfico conhecido como diagrama *Sankey* .</span><span class="sxs-lookup"><span data-stu-id="9973a-107">By default, the widget shows the mail flow pattern from the previous day in a chart known as a *Sankey* diagram.</span></span> <span data-ttu-id="9973a-108">Você pode usar a seta para a esquerda seta para a ![ esquerda e seta para ](../../media/scc-left-arrow.png) a direita ![ ](../../media/scc-right-arrow.png) para mostrar informações de diferentes dias.</span><span class="sxs-lookup"><span data-stu-id="9973a-108">You can use the left arrow ![Left arrow](../../media/scc-left-arrow.png) and right arrow ![Right arrow](../../media/scc-right-arrow.png) to show information from different days.</span></span> <span data-ttu-id="9973a-109">Cada cor diferente representa o fluxo de mensagens por um conector de entrada ou saída diferente (ou sem usar conectores).</span><span class="sxs-lookup"><span data-stu-id="9973a-109">Each different color represents mail flow over a different inbound or outbound connector (or without using connectors).</span></span> <span data-ttu-id="9973a-110">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="9973a-110">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

## <a name="report-view-for-the-mail-flow-map"></a><span data-ttu-id="9973a-111">Exibição de relatório para o mapa de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9973a-111">Report view for the Mail flow map</span></span>

<span data-ttu-id="9973a-112">Clicar no widget **mapa de fluxo de emails** o levará para o relatório de **mapa de fluxo de emails** .</span><span class="sxs-lookup"><span data-stu-id="9973a-112">Clicking on the **Mail flow map** widget will take you to the **Mail flow map** report.</span></span>

<span data-ttu-id="9973a-113">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="9973a-113">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9973a-114">**Show data for: Overview** : Este é basicamente uma visão maior do widget.</span><span class="sxs-lookup"><span data-stu-id="9973a-114">**Show data for: Overview** : This is basically a larger view of the widget.</span></span> <span data-ttu-id="9973a-115">Se você passar o mouse sobre uma cor específica, o número de mensagens será exibido para esse tipo de conector.</span><span class="sxs-lookup"><span data-stu-id="9973a-115">If you hover over a specific color, the number of messages is displayed for that type of connector.</span></span>

  ![Exibição de visão geral no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-overview.png)

- <span data-ttu-id="9973a-117">**Mostrar dados de: Detail** : este modo de exibição mostra detalhes sobre os conectores e domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="9973a-117">**Show data for: Detail** : This view shows details about the connectors and destination domains.</span></span> <span data-ttu-id="9973a-118">Os principais remetentes e domínios de destinatário são listados e o restante é colocado em **outros**.</span><span class="sxs-lookup"><span data-stu-id="9973a-118">The top sender and recipient domains are listed, and the rest are put in **Others**.</span></span> <span data-ttu-id="9973a-119">Se você passar o mouse sobre uma cor e seção específica, o número de mensagens será exibido.</span><span class="sxs-lookup"><span data-stu-id="9973a-119">If you hover over a specific color and section, the number of messages is displayed.</span></span>

  ![Exibição de detalhes no relatório de mapa de fluxo de emails](../../media/mfi-mail-flow-map-report-detail.png)

<span data-ttu-id="9973a-121">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="9973a-121">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9973a-122">Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="9973a-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9973a-123">Os insights relacionados são mostrados abaixo do mapa de fluxo de emails, se estiverem disponíveis (por exemplo, a [correção de possíveis informações de loop de email](mfi-mail-loop-insight.md)).</span><span class="sxs-lookup"><span data-stu-id="9973a-123">Related insights are shown beneath the Mail flow map if they're available (for example, the [Fix possible mail loop insight](mfi-mail-loop-insight.md)).</span></span>

## <a name="details-table-view-for-the-mail-flow-map"></a><span data-ttu-id="9973a-124">Exibição da tabela de detalhes para o mapa de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9973a-124">Details table view for the Mail flow map</span></span>

<span data-ttu-id="9973a-125">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="9973a-125">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9973a-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="9973a-126">**Date**</span></span>
- <span data-ttu-id="9973a-127">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="9973a-127">**Category**</span></span>
- <span data-ttu-id="9973a-128">**Conector/provedor de serviços terceirizado**</span><span class="sxs-lookup"><span data-stu-id="9973a-128">**Connector / Third-party service provider**</span></span>
- <span data-ttu-id="9973a-129">**Domínio do remetente/destinatário**</span><span class="sxs-lookup"><span data-stu-id="9973a-129">**Sender/Recipient domain**</span></span>
- <span data-ttu-id="9973a-130">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="9973a-130">**Message count**</span></span>

<span data-ttu-id="9973a-131">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="9973a-131">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9973a-132">Se você selecionar uma linha, os detalhes semelhantes serão mostrados em um submenu:</span><span class="sxs-lookup"><span data-stu-id="9973a-132">If you select a row, similar details are shown in a flyout:</span></span>

![Submenu de detalhes da tabela detalhes no mapa de fluxo de emails](../../media/mfi-mail-flow-map-view-details-table-details.png)

<span data-ttu-id="9973a-134">Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="9973a-134">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9973a-135">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9973a-135">To go back to the reports view, click **View report**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9973a-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="9973a-136">See also</span></span>

<span data-ttu-id="9973a-137">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="9973a-137">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
