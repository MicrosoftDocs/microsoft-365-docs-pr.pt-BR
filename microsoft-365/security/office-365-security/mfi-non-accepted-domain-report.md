---
title: Relatório de domínio não aceito no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o relatório de domínio não aceito no painel de fluxo de emails no centro de conformidade de & de segurança para monitorar mensagens de sua organização local onde o domínio do remetente não está configurado no Microsoft 365.
ms.openlocfilehash: ef5f1c26168347b6696e90292d9c957e63615c0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826936"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="5f549-103">Relatório de domínio não aceito no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="5f549-103">Non-accepted domain report in the Security & Compliance Center</span></span>

<span data-ttu-id="5f549-104">O relatório de **domínio não aceito** no [painel de fluxo de emails](mail-flow-insights-v2.md) no centro de conformidade & segurança exibe informações sobre as mensagens da sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito na sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f549-104">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="5f549-105">O Microsoft 365 pode reduzir essas mensagens se houver dados que comprovam que a intenção dessas mensagens é mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="5f549-105">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="5f549-106">Portanto, é importante entender o que está acontecendo e corrigir o problema.</span><span class="sxs-lookup"><span data-stu-id="5f549-106">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget domínio não aceito no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="5f549-108">Exibição de relatório para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="5f549-108">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="5f549-109">Ao clicar no gráfico no widget **domínio não aceito** , você será direcionado para o relatório de **domínio não aceito** .</span><span class="sxs-lookup"><span data-stu-id="5f549-109">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="5f549-110">Por padrão, a atividade de todos os conectores afetados é mostrada.</span><span class="sxs-lookup"><span data-stu-id="5f549-110">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="5f549-111">Se você clicar em **Mostrar dados para**, poderá selecionar um conector específico na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5f549-111">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="5f549-112">Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens do conector.</span><span class="sxs-lookup"><span data-stu-id="5f549-112">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="5f549-114">Exibição da tabela de detalhes para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="5f549-114">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="5f549-115">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="5f549-115">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="5f549-116">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f549-116">**Date**</span></span>
- <span data-ttu-id="5f549-117">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="5f549-117">**Inbound connector name**</span></span>
- <span data-ttu-id="5f549-118">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="5f549-118">**Sender domain**</span></span>
- <span data-ttu-id="5f549-119">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="5f549-119">**Message count**</span></span>
- <span data-ttu-id="5f549-120">**Mensagens de exemplo**: as IDs de mensagem de uma amostra de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="5f549-120">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="5f549-121">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="5f549-121">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="5f549-122">Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="5f549-122">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="5f549-123">Quando você seleciona uma linha na tabela, um submenu aparece com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5f549-123">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="5f549-124">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f549-124">**Date**</span></span>
- <span data-ttu-id="5f549-125">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="5f549-125">**Inbound connector name**</span></span>
- <span data-ttu-id="5f549-126">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="5f549-126">**Sender domain**</span></span>
- <span data-ttu-id="5f549-127">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="5f549-127">**Message count**</span></span>
- <span data-ttu-id="5f549-128">**Exemplos de mensagens**: você pode clicar em **Exibir mensagens de amostra** para ver os resultados de [rastreamento](message-trace-scc.md) de mensagens para um exemplo de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="5f549-128">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Submenu de detalhes depois de selecionar uma linha no modo de exibição de tabela detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="5f549-130">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="5f549-130">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f549-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5f549-131">Related topics</span></span>

<span data-ttu-id="5f549-132">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="5f549-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
