---
title: Notificação de falha na entrega no painel de fluxo de emails
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
description: Os administradores podem aprender a usar o relatório de detalhes de falha na entrega no painel de fluxo de emails no centro de conformidade do & de segurança para monitorar os códigos de erro encontrados com mais frequência nas notificações de falha na entrega (também conhecidas como NDRs ou mensagens de devolução) de remetentes em sua organização.
ms.openlocfilehash: 4967b3b5c294566e46bbc715dd6702c23d618105
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877676"
---
# <a name="non-delivery-report-in-the-security--compliance-center"></a><span data-ttu-id="3e9b7-103">Notificação de falha na entrega no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="3e9b7-103">Non-delivery report in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3e9b7-104">A notificação de falha na **entrega** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade de & de segurança](https://protection.office.com) mostra os códigos de erro mais encontrados em notificações de falha na entrega (também conhecidos como NDRs ou mensagens de devolução) para os usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-104">The **Non-delivery report** in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) shows the most-encountered error codes in non-delivery reports (also known as NDRs or bounce messages) for users in your organization.</span></span> <span data-ttu-id="3e9b7-105">Este relatório mostra os detalhes dos NDRs para que você possa solucionar problemas de entrega de email.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-105">This report shows the details of NDRs so you can troubleshoot email delivery problems.</span></span>

![Widget notificação de falha na entrega no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-non-delivery-report-widget.png)

## <a name="report-view-for-the-non-delivery-report"></a><span data-ttu-id="3e9b7-107">Exibição de relatório para a notificação de falha na entrega</span><span class="sxs-lookup"><span data-stu-id="3e9b7-107">Report view for the Non-delivery report</span></span>

<span data-ttu-id="3e9b7-108">Ao clicar no widget notificação de falha na **entrega** , você será direcionado para o relatório de falha na **entrega**.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-108">Clicking on the **Non-delivery report** widget will take you to the **Non-delivery report**.</span></span>

<span data-ttu-id="3e9b7-109">Por padrão, a atividade de todos os códigos de erro é mostrada.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-109">By default, the activity for all error codes is shown.</span></span> <span data-ttu-id="3e9b7-110">Se você clicar em **Mostrar dados para** , poderá selecionar um código de erro específico na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-110">If you click **Show data for** , you can select a specific error code from the dropdown.</span></span>

<span data-ttu-id="3e9b7-111">Se você passar o mouse sobre uma cor específica (código de erro) em um dia específico no gráfico, verá o número total de mensagens para o erro.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-111">If you hover over a specific color (error code) on a specific day in the chart, you'll see the total number of messages for the error.</span></span>

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-delivery-report-overview-view.png)

## <a name="details-table-view-for-the-non-delivery-report"></a><span data-ttu-id="3e9b7-113">Exibição da tabela de detalhes para a notificação de falha na entrega</span><span class="sxs-lookup"><span data-stu-id="3e9b7-113">Details table view for the Non-delivery report</span></span>

<span data-ttu-id="3e9b7-114">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="3e9b7-114">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="3e9b7-115">**Date**</span><span class="sxs-lookup"><span data-stu-id="3e9b7-115">**Date**</span></span>
- <span data-ttu-id="3e9b7-116">**Código de notificação de falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="3e9b7-116">**Non-delivery report code**</span></span>
- <span data-ttu-id="3e9b7-117">**Count**</span><span class="sxs-lookup"><span data-stu-id="3e9b7-117">**Count**</span></span>
- <span data-ttu-id="3e9b7-118">**Mensagens de exemplo** : as IDs de mensagem de uma amostra de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-118">**Sample messages** : The message IDs of a sample of affected messages.</span></span>

<span data-ttu-id="3e9b7-119">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-119">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="3e9b7-120">Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-120">To email the report for a specific date range to one or more recipients, click **Request download**.</span></span>

<span data-ttu-id="3e9b7-121">Quando você seleciona uma linha na tabela, um submenu aparece com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3e9b7-121">When you select a row in the table, a flyout appears with the following information:</span></span>

- <span data-ttu-id="3e9b7-122">**Date**</span><span class="sxs-lookup"><span data-stu-id="3e9b7-122">**Date**</span></span>
- <span data-ttu-id="3e9b7-123">**Código** de notificação de falha na entrega: você pode clicar no link para encontrar mais informações sobre as causas e soluções para o código de erro específico.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-123">**Non-delivery report code** : You can click on the link to find for more information about the causes and solutions for the specific error code.</span></span>
- <span data-ttu-id="3e9b7-124">**Count**</span><span class="sxs-lookup"><span data-stu-id="3e9b7-124">**Count**</span></span>
- <span data-ttu-id="3e9b7-125">**Exemplos de mensagens** : você pode clicar em **Exibir mensagens de amostra** para ver os resultados de [rastreamento](message-trace-scc.md) de mensagens para um exemplo de mensagens afetadas.</span><span class="sxs-lookup"><span data-stu-id="3e9b7-125">**Sample messages** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the affected messages.</span></span>

![Submenu de detalhes depois de selecionar uma linha no modo de exibição de tabela detalhes na notificação de falha na entrega](../../media/mfi-non-delivery-report-details-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="3e9b7-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3e9b7-127">Related topics</span></span>

<span data-ttu-id="3e9b7-128">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="3e9b7-128">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
