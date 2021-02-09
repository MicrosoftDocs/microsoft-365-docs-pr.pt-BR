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
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150815"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a><span data-ttu-id="9ee75-103">Relatório de domínio não aceito no Centro de Conformidade e Segurança & segurança</span><span class="sxs-lookup"><span data-stu-id="9ee75-103">Non-accepted domain report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9ee75-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9ee75-104">**Applies to**</span></span>
- [<span data-ttu-id="9ee75-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9ee75-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="9ee75-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="9ee75-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="9ee75-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9ee75-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="9ee75-108">O  relatório de domínio não [](mail-flow-insights-v2.md) aceito no painel Fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens de sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito em sua organização do Microsoft 365. [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="9ee75-108">The **Non-accepted domain** report in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages from your on-premises email organization where the sender's domain isn't configured as an accepted domain in your Microsoft 365 organization.</span></span>

<span data-ttu-id="9ee75-109">O Microsoft 365 pode acelerar essas mensagens se temos dados para provar que a intenção dessas mensagens é mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="9ee75-109">Microsoft 365 might throttle these messages if we have data to prove that the intent of these messages is malicious.</span></span> <span data-ttu-id="9ee75-110">Portanto, é importante que você entenda o que está acontecendo e corrige o problema.</span><span class="sxs-lookup"><span data-stu-id="9ee75-110">Therefore, it's important for you to understand what's happening and to fix the issue.</span></span>

![Widget de domínio não aceito no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="9ee75-112">Exibição de relatório para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="9ee75-112">Report view for the Non-accepted domain report</span></span>

<span data-ttu-id="9ee75-113">Clicar no gráfico no widget **de** domínio não aceito levará você ao relatório **de domínio não aceito.**</span><span class="sxs-lookup"><span data-stu-id="9ee75-113">Clicking the chart on the **Non-accepted domain** widget will take you to the **Non-accepted domain** report.</span></span>

<span data-ttu-id="9ee75-114">Por padrão, a atividade de todos os conectores afetados é mostrada.</span><span class="sxs-lookup"><span data-stu-id="9ee75-114">By default, the activity for all affected connectors is shown.</span></span> <span data-ttu-id="9ee75-115">Se você clicar **em Mostrar dados** para , você pode selecionar um conector específico na lista suspenso.</span><span class="sxs-lookup"><span data-stu-id="9ee75-115">If you click **Show data for**, you can select a specific connector from the dropdown.</span></span>

<span data-ttu-id="9ee75-116">Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens para o conector.</span><span class="sxs-lookup"><span data-stu-id="9ee75-116">If you hover over a data point (day) in the chart, you'll see the total number of messages for the connector.</span></span>

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a><span data-ttu-id="9ee75-118">Exibição de tabela de detalhes para o relatório de domínio não aceito</span><span class="sxs-lookup"><span data-stu-id="9ee75-118">Details table view for the Non-accepted domain report</span></span>

<span data-ttu-id="9ee75-119">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="9ee75-119">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9ee75-120">**Date**</span><span class="sxs-lookup"><span data-stu-id="9ee75-120">**Date**</span></span>
- <span data-ttu-id="9ee75-121">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="9ee75-121">**Inbound connector name**</span></span>
- <span data-ttu-id="9ee75-122">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="9ee75-122">**Sender domain**</span></span>
- <span data-ttu-id="9ee75-123">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="9ee75-123">**Message count**</span></span>
- <span data-ttu-id="9ee75-124">**Mensagens de** exemplo: as IDs de mensagem de uma amostra de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="9ee75-124">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="9ee75-125">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="9ee75-125">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9ee75-126">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**</span><span class="sxs-lookup"><span data-stu-id="9ee75-126">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="9ee75-127">Quando você seleciona uma linha na tabela, um flyout é exibido com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9ee75-127">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="9ee75-128">**Date**</span><span class="sxs-lookup"><span data-stu-id="9ee75-128">**Date**</span></span>
- <span data-ttu-id="9ee75-129">**Nome do conector de entrada**</span><span class="sxs-lookup"><span data-stu-id="9ee75-129">**Inbound connector name**</span></span>
- <span data-ttu-id="9ee75-130">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="9ee75-130">**Sender domain**</span></span>
- <span data-ttu-id="9ee75-131">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="9ee75-131">**Message count**</span></span>
- <span data-ttu-id="9ee75-132">**Exemplos de** mensagens: você pode clicar **em Exibir mensagens de exemplo** para ver os resultados [do](message-trace-scc.md) rastreamento de mensagens para uma amostra das mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="9ee75-132">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

<span data-ttu-id="9ee75-134">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="9ee75-134">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ee75-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9ee75-135">Related topics</span></span>

<span data-ttu-id="9ee75-136">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="9ee75-136">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
