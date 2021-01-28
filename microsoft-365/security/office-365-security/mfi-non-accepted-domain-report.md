---
title: Relatório de domínio não aceito no painel fluxo de emails
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
description: Os administradores podem aprender a usar o relatório de domínio não aceito no painel Fluxo de emails no Centro de Conformidade e Segurança para monitorar mensagens de sua organização local onde o domínio do remetente não está configurado no Microsoft 365. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 401d566158ca3f730af94fab60c471484e244a16
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029841"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="dc266-103">Relatório de domínio não aceito no Centro de Conformidade e Segurança & segurança</span><span class="sxs-lookup"><span data-stu-id="dc266-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="dc266-104">O  relatório de domínio não [](mail-flow-insights-v2.md) aceito no painel Fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens de sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito em sua organização do Microsoft 365. [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="dc266-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="dc266-105">O Microsoft 365 pode acelerar essas mensagens se temos dados para provar que a intenção dessas mensagens é mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="dc266-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="dc266-106">Portanto, é importante que você entenda o que está acontecendo e corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="dc266-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget de domínio não aceito no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc266-108">Exibição de relatório para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="dc266-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc266-109">Clicar no gráfico no widget **de** domínio não aceito levará você ao relatório **de domínio não aceito.**</span><span class="sxs-lookup"><span data-stu-id="dc266-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="dc266-110">Por padrão, a atividade de todos os conectores afetados é mostrada.</span><span class="sxs-lookup"><span data-stu-id="dc266-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="dc266-111">Se você clicar **em Mostrar dados** para , você pode selecionar um conector específico na lista suspenso.</span><span class="sxs-lookup"><span data-stu-id="dc266-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="dc266-112">Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens para o conector.</span><span class="sxs-lookup"><span data-stu-id="dc266-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="dc266-114">Exibição de tabela de detalhes para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="dc266-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="dc266-115">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="dc266-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="dc266-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="dc266-116">**Date**</span></span>
- <span data-ttu-id="dc266-117">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="dc266-117">**Inbound connector name**</span></span>
- <span data-ttu-id="dc266-118">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="dc266-118">**Sender domain**</span></span>
- <span data-ttu-id="dc266-119">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="dc266-119">**Message count**</span></span>
- <span data-ttu-id="dc266-120">**Mensagens de** exemplo: as IDs de mensagem de uma amostra de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="dc266-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="dc266-121">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="dc266-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="dc266-122">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**</span><span class="sxs-lookup"><span data-stu-id="dc266-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="dc266-123">Quando você seleciona uma linha na tabela, um flyout é exibido com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="dc266-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="dc266-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="dc266-124">**Date**</span></span>
- <span data-ttu-id="dc266-125">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="dc266-125">**Inbound connector name**</span></span>
- <span data-ttu-id="dc266-126">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="dc266-126">**Sender domain**</span></span>
- <span data-ttu-id="dc266-127">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="dc266-127">**Message count**</span></span>
- <span data-ttu-id="dc266-128">**Exemplos de** mensagens: você pode clicar **em Exibir mensagens de exemplo** para ver os resultados do rastreamento de mensagens para um exemplo das mensagens afetadas. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="dc266-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="dc266-130">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="dc266-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dc266-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dc266-131">Related topics</span></span>

<span data-ttu-id="dc266-132">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="dc266-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
