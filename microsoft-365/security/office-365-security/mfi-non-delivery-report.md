---
title: Relatório de não entrega no painel fluxo de emails
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
description: Os administradores podem aprender a usar o relatório de detalhes de falha na entrega no painel de fluxo de emails no Centro de Conformidade de & de Segurança para monitorar os códigos de erro encontrados com mais frequência em notificações de falha na entrega (também conhecidas como NDRs ou mensagens de rejeição) dos envios em sua organização.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af4beefb8ba15fd7d98b11ec2571eee65a99e4e3
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150154"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="e6391-103">Relatório de falha na entrega no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="e6391-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e6391-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e6391-104">**Applies to**</span></span>
- [<span data-ttu-id="e6391-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e6391-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="e6391-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="e6391-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="e6391-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e6391-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="e6391-108">O  relatório de falha [](mail-flow-insights-v2.md) na entrega no painel fluxo de emails no Centro de Conformidade e Segurança mostra os códigos de erro mais encontrados em notificações de falha na entrega (também conhecidas como NDRs ou mensagens de rejeição) para usuários em sua organização. [&](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="e6391-108">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="e6391-109">Este relatório mostra os detalhes das NDRs para que você possa solucionar problemas de entrega de email.</span><span class="sxs-lookup"><span data-stu-id="e6391-109">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget de relatório de falha na entrega no painel fluxo de emails no Centro de Conformidade e Segurança &](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="e6391-111">Exibição de relatório para o relatório de não entrega</span><span class="sxs-lookup"><span data-stu-id="e6391-111">Report view for the Non-delivery report</span></span>

<span data-ttu-id="e6391-112">Clicar no widget de **relatório de não** entrega levará você ao relatório de não **entrega.**</span><span class="sxs-lookup"><span data-stu-id="e6391-112">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="e6391-113">Por padrão, a atividade de todos os códigos de erro é mostrada.</span><span class="sxs-lookup"><span data-stu-id="e6391-113">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="e6391-114">Se você clicar **em Mostrar dados** para , você pode selecionar um código de erro específico na lista suspenso.</span><span class="sxs-lookup"><span data-stu-id="e6391-114">If you click **Show data for**, you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="e6391-115">Se você passar o mouse sobre uma cor específica (código de erro) em um dia específico no gráfico, verá o número total de mensagens do erro.</span><span class="sxs-lookup"><span data-stu-id="e6391-115">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="e6391-117">Exibição de tabela de detalhes para o relatório de não entrega</span><span class="sxs-lookup"><span data-stu-id="e6391-117">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="e6391-118">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="e6391-118">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e6391-119">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6391-119">**Date**</span></span>
- <span data-ttu-id="e6391-120">**Código do relatório de não entrega**</span><span class="sxs-lookup"><span data-stu-id="e6391-120">**Non-delivery report code**</span></span>
- <span data-ttu-id="e6391-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6391-121">**Count**</span></span>
- <span data-ttu-id="e6391-122">**Mensagens de** exemplo: as IDs de mensagem de uma amostra de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="e6391-122">**Sample messages**: The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="e6391-123">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="e6391-123">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e6391-124">Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**</span><span class="sxs-lookup"><span data-stu-id="e6391-124">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="e6391-125">Quando você seleciona uma linha na tabela, um flyout é exibido com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e6391-125">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="e6391-126">**Date**</span><span class="sxs-lookup"><span data-stu-id="e6391-126">**Date**</span></span>
- <span data-ttu-id="e6391-127">**Código do relatório de falha** na entrega: você pode clicar no link para encontrar mais informações sobre as causas e soluções para o código de erro específico.</span><span class="sxs-lookup"><span data-stu-id="e6391-127">**Non-delivery report code**: You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="e6391-128">**Count**</span><span class="sxs-lookup"><span data-stu-id="e6391-128">**Count**</span></span>
- <span data-ttu-id="e6391-129">**Exemplos de** mensagens: você pode clicar **em Exibir mensagens de exemplo** para ver os resultados do rastreamento de mensagens para um exemplo das mensagens afetadas. [](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="e6391-129">**Sample messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de não entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="e6391-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e6391-131">Related topics</span></span>

<span data-ttu-id="e6391-132">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="e6391-132">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
