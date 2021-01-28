---
title: Exibir relatórios de fluxo de emails no painel Relatórios
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre os relatórios de fluxo de emails que estão disponíveis no painel Relatórios no Centro de Conformidade & Segurança.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e69085d1fad845ab519f2590b0527316463373a7
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029793"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="6d9c4-103">Exibir relatórios de fluxo de emails no painel Relatórios no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="6d9c4-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6d9c4-104">Além dos relatórios de fluxo de emails [](mail-flow-insights-v2.md) que estão disponíveis no painel Fluxo de emails no Centro de Conformidade e Segurança, uma variedade de relatórios de fluxo de emails adicionais estão disponíveis no painel Relatórios para ajudá-lo & a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="6d9c4-105">Se você tiver as [permissões necessárias,](#what-permissions-are-needed-to-view-these-reports)poderá exibir esses relatórios no Centro de Conformidade & segurança [indo](https://protection.office.com) para o Painel **de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="6d9c4-106">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel relatórios no Centro de Conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="6d9c4-108">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="6d9c4-108">Connector report</span></span>

<span data-ttu-id="6d9c4-109">O **relatório conector** mostra a atividade de fluxo de emails nos conectores de entrada e de saída [configurados](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="6d9c4-110">Para exibir o relatório, abra o [Centro de Conformidade & Segurança,](https://protection.office.com)vá para o Painel de Relatórios e selecione o relatório do  \>  **Conector.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="6d9c4-111">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de relatório do conector no painel Relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="6d9c4-113">Exibição de relatório para o relatório conector</span><span class="sxs-lookup"><span data-stu-id="6d9c4-113">Report view for the Connector report</span></span>

<span data-ttu-id="6d9c4-114">Os gráficos a seguir estão disponíveis no visualização de relatório:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="6d9c4-115">**Exibir dados por: Fluxo de emails:** este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="6d9c4-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-116">**Total**</span></span>
  - <span data-ttu-id="6d9c4-117">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="6d9c4-118">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="6d9c4-119">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="6d9c4-120">Para isolar os dados no gráfico, use show **data for** control to select one of these options or All **mail flow**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório do Conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="6d9c4-122">**Exibir dados por: uso de TLS:** este gráfico mostra a porcentagem de uso da versão TLS (Transport Layer Security) para fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="6d9c4-123">Para isolar os dados no gráfico, use Show **data for** control para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="6d9c4-124">**Todo o fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-124">**All mail flow**</span></span>
  - <span data-ttu-id="6d9c4-125">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="6d9c4-126">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="6d9c4-127">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-127">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso de TLS no relatório do Conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="6d9c4-129">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="6d9c4-130">Details table view for the Connector report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-130">Details table view for the Connector report</span></span>

<span data-ttu-id="6d9c4-131">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6d9c4-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-132">**Date**</span></span>
- <span data-ttu-id="6d9c4-133">**Nome e direção do conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-133">**Connector direction and name**</span></span>
- <span data-ttu-id="6d9c4-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-134">**Connector type**</span></span>
- <span data-ttu-id="6d9c4-135">**TLS forçado?**: o valor **True** ou **False**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="6d9c4-136">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="6d9c4-137">**TLS 1.0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="6d9c4-138">**TLS 1.1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="6d9c4-139">**TLS 1.2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="6d9c4-140">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="6d9c4-141">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6d9c4-142">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="6d9c4-143">Relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="6d9c4-143">Exchange transport rule report</span></span>

<span data-ttu-id="6d9c4-144">O **relatório de regras de transporte** do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="6d9c4-145">Para exibir o relatório, abra o [Centro de Conformidade & Segurança,](https://protection.office.com)vá para o Painel de Relatórios e selecione a regra de Transporte do  \>  **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="6d9c4-146">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regra de transporte do Exchange no painel Relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="6d9c4-148">Exibição de relatório para o relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="6d9c4-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="6d9c4-149">Os gráficos a seguir estão disponíveis no visualização de relatório:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="6d9c4-150">**Exibir dados por: regras de transporte do** \> Exchange **Down by: Direction :** This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="6d9c4-151">**Exibir dados por: Regras de transporte do** \> Exchange **Intervalo por: Gravidade:** Este gráfico mostra  o número de mensagens de gravidade alta e **média** e **de baixa** gravidade.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="6d9c4-152">Você pode definir o nível de severidade como uma ação na regra (**Auditar** esta regra com nível de severidade _ou SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="6d9c4-153">Para saber mais, confira [Ações de regra de fluxo de emails no Exchange Online.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="6d9c4-154">**Exibir dados por: regras de transporte do Exchange** \> DLP **Intervalo por: Direção:** este gráfico  mostra o  número de mensagens de Entrada e Saída que foram afetadas pelas regras de transporte de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="6d9c4-155">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="6d9c4-156">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="6d9c4-157">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="6d9c4-158">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Act dos EUA**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="6d9c4-159">**Exibir dados por: regras de transporte do Exchange** \> DLP **Down by: Direction:** This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="6d9c4-160">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="6d9c4-161">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="6d9c4-162">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="6d9c4-163">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Act dos EUA**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="6d9c4-164">Se você clicar **em Filtros** em uma exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="6d9c4-165">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="6d9c4-166">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="6d9c4-166">Direction values</span></span>
- <span data-ttu-id="6d9c4-167">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="6d9c4-167">Severity values</span></span>

![Exibição de relatório no relatório de regras de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="6d9c4-169">Visão de tabela de detalhes do relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="6d9c4-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="6d9c4-170">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6d9c4-171">**Exibir dados por: Regras de Transporte do Exchange:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="6d9c4-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-172">**Date**</span></span>
  - <span data-ttu-id="6d9c4-173">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-173">**Transport rule**</span></span>
  - <span data-ttu-id="6d9c4-174">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-174">**Subject**</span></span>
  - <span data-ttu-id="6d9c4-175">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-175">**Sender address**</span></span>
  - <span data-ttu-id="6d9c4-176">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-176">**Recipient address**</span></span>
  - <span data-ttu-id="6d9c4-177">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-177">**Severity**</span></span>
  - <span data-ttu-id="6d9c4-178">**Direção**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-178">**Direction**</span></span>

- <span data-ttu-id="6d9c4-179">**Exibir dados por: regras de transporte do Exchange DLP:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="6d9c4-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-180">**Date**</span></span>
  - <span data-ttu-id="6d9c4-181">**Política de DLP**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-181">**DLP policy**</span></span>
  - <span data-ttu-id="6d9c4-182">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-182">**Transport rule**</span></span>
  - <span data-ttu-id="6d9c4-183">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-183">**Subject**</span></span>
  - <span data-ttu-id="6d9c4-184">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-184">**Sender address**</span></span>
  - <span data-ttu-id="6d9c4-185">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-185">**Recipient address**</span></span>
  - <span data-ttu-id="6d9c4-186">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-186">**Severity**</span></span>
  - <span data-ttu-id="6d9c4-187">**Direção**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-187">**Direction**</span></span>

<span data-ttu-id="6d9c4-188">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6d9c4-189">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="6d9c4-190">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="6d9c4-190">Direction values</span></span>
- <span data-ttu-id="6d9c4-191">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="6d9c4-191">Severity values</span></span>

<span data-ttu-id="6d9c4-192">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="6d9c4-193">Relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="6d9c4-193">Forwarding report</span></span>

<span data-ttu-id="6d9c4-194">O **relatório de encaminhamento mostra** as mensagens encaminhadas automaticamente da sua organização para domínios externos das caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="6d9c4-195">As mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="6d9c4-196">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione o relatório de  \>  **encaminhamento.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="6d9c4-197">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Forwarding report widget in the Reports dashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="6d9c4-199">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="6d9c4-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="6d9c4-200">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6d9c4-201">**Mostrar dados para: métodos de encaminhamento:** os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="6d9c4-202">**Regra de** transporte: também conhecida como [regras de fluxo de emails.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="6d9c4-203">**Regra de caixa** de correio: também conhecida como [regras de Caixa de Entrada.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Modo de exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="6d9c4-205">**Mostrar dados para: Domínios de** encaminhamento: esta exibição mostra os domínios do destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="6d9c4-207">**Mostrar dados para: Encaminhadores:** os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="6d9c4-208">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-208">**Transport rule**</span></span>
  - <span data-ttu-id="6d9c4-209">A caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="6d9c4-211">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="6d9c4-212">Details table view for the Forwarding report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="6d9c4-213">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="6d9c4-214">**Encaminhadores**: a regra de **transporte de** valor ou a caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="6d9c4-215">**Tipo de encaminhamento: a** regra de **caixa de correio de** valor ou regra de **transporte**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="6d9c4-216">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-216">**Recipient name**</span></span>
- <span data-ttu-id="6d9c4-217">**Domínio do destinatário**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-217">**Recipient domain**</span></span>
- <span data-ttu-id="6d9c4-218">**Detalhes:** este é o valor de GUID da regra de fluxo de emails ou o valor ruleIdentity da regra de Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="6d9c4-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-219">**Count**</span></span>
- <span data-ttu-id="6d9c4-220">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-220">**First forward date**</span></span>

<span data-ttu-id="6d9c4-221">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6d9c4-222">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="6d9c4-223">Relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-223">Mailflow status report</span></span>

<span data-ttu-id="6d9c4-224">O **relatório de status do fluxo** de mensagens é semelhante ao relatório de emails enviados [e](#sent-and-received-email-report)recebidos, com informações adicionais sobre emails permitidos ou bloqueados na borda.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="6d9c4-225">Este é o único relatório que contém informações de proteção de borda e mostra quantos emails são bloqueados antes de serem permitidos no serviço para avaliação pelo Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="6d9c4-226">É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="6d9c4-227">Para exibir o relatório, abra o [Centro de Conformidade e &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione o relatório de status do fluxo de  \>  **mensagens.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="6d9c4-228">Para ir diretamente para o relatório **de status de fluxo de emails,** abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de relatório de status do fluxo de mensagens no painel Relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="6d9c4-230">Type view for the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="6d9c4-231">Quando você abre o relatório, a **guia** Tipo é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="6d9c4-232">Por padrão, esse modo de exibição contém um gráfico e uma tabela de dados configurados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6d9c4-233">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="6d9c4-234">**Direção:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-234">**Direction**:</span></span>

  - <span data-ttu-id="6d9c4-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-235">**Inbound**</span></span>
  - <span data-ttu-id="6d9c4-236">**Saída**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-236">**Outbound**</span></span>
  - <span data-ttu-id="6d9c4-237">**Dentro da organização:** essa contagem é para mensagens em um locatário, ou seja,</span><span class="sxs-lookup"><span data-stu-id="6d9c4-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="6d9c4-238">sender abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="6d9c4-239">**Tipo:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-239">**Type**:</span></span>

  - <span data-ttu-id="6d9c4-240">**Email bom**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-240">**Good mail**</span></span>
  - <span data-ttu-id="6d9c4-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-241">**Malware**</span></span>
  - <span data-ttu-id="6d9c4-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-242">**Spam**</span></span>
  - <span data-ttu-id="6d9c4-243">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-243">**Edge protection**</span></span>
  - <span data-ttu-id="6d9c4-244">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-244">**Rule messages**</span></span>
  - <span data-ttu-id="6d9c4-245">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-245">**Phishing email**</span></span>

<span data-ttu-id="6d9c4-246">O gráfico é organizado pelos valores **Type.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="6d9c4-247">Você pode alterar esses filtros clicando em **Filtro** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="6d9c4-248">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-248">The data table contains the following information:</span></span>

- <span data-ttu-id="6d9c4-249">**Direção**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-249">**Direction**</span></span>
- <span data-ttu-id="6d9c4-250">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-250">**Type**</span></span>
- <span data-ttu-id="6d9c4-251">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-251">**24 hours**</span></span>
- <span data-ttu-id="6d9c4-252">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-252">**3 days**</span></span>
- <span data-ttu-id="6d9c4-253">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-253">**7 days**</span></span>
- <span data-ttu-id="6d9c4-254">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-254">**15 days**</span></span>
- <span data-ttu-id="6d9c4-255">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-255">**30 days**</span></span>

<span data-ttu-id="6d9c4-256">Se você clicar **em Escolher uma categoria para obter mais** detalhes, poderá selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="6d9c4-257">**Email de phishing:** essa seleção leva você ao relatório de [status de Proteção contra Ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="6d9c4-258">**Malware no email:** essa seleção leva você ao relatório de [status de Proteção contra Ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="6d9c4-259">**Detecções de** spam: essa seleção leva você ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="6d9c4-260">**Spam bloqueado por borda:** essa seleção leva você ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="6d9c4-261">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-261">**Export**:</span></span>

<span data-ttu-id="6d9c4-262">Para a exibição de detalhes, você só pode exportar dados para um dia.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="6d9c4-263">Portanto, se você quiser exportar dados por sete dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="6d9c4-264">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6d9c4-265">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="6d9c4-266">Type view in the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="6d9c4-267">Exibição de direção para o relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="6d9c4-268">Se você clicar na guia **Direção,** os mesmos filtros padrão do modo **de exibição** Tipo serão usados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="6d9c4-269">O gráfico é organizado por valores **de** direção.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="6d9c4-270">Você pode alterar esses filtros clicando em **Filtro** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="6d9c4-271">Os mesmos filtros do modo **de exibição** Tipo são usados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="6d9c4-272">A tabela de dados contém as mesmas informações do modo **de exibição** Tipo.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="6d9c4-273">A **opção Escolher uma categoria para obter mais detalhes** sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição** Tipo.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="6d9c4-274">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-274">**Export**:</span></span>

<span data-ttu-id="6d9c4-275">Para a exibição de detalhes, você só pode exportar dados para um dia.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="6d9c4-276">Portanto, se você quiser exportar dados por sete dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="6d9c4-277">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6d9c4-278">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="6d9c4-279">Exibição de direção no relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="6d9c4-280">Exibição de funil para o relatório de status do Fluxo de Mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="6d9c4-281">A **exibição** de funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e de saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="6d9c4-282">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="6d9c4-283">Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6d9c4-284">**Data:** os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="6d9c4-285">**Direção:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-285">**Direction**:</span></span>

  - <span data-ttu-id="6d9c4-286">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-286">**Inbound**</span></span>
  - <span data-ttu-id="6d9c4-287">**Saída**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-287">**Outbound**</span></span>
  - <span data-ttu-id="6d9c4-288">**Dentro da organização:** essa contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente da entrada e da saída).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="6d9c4-289">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="6d9c4-290">Se você clicar **em Filtro,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="6d9c4-291">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="6d9c4-292">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-292">**Total email**</span></span>
- <span data-ttu-id="6d9c4-293">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-293">**Email after edge protection**</span></span>
- <span data-ttu-id="6d9c4-294">**Email após anti-malware, reputação do arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="6d9c4-295">**Email após anti-phishing, reputação da URL, representação de marca, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="6d9c4-296">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="6d9c4-297">**Email após a representação de usuário e domínio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6d9c4-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="6d9c4-298">**Email após o arquivo e o a detonação de URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6d9c4-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="6d9c4-299">**Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique de URL)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="6d9c4-300"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="6d9c4-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="6d9c4-301">Para exibir o email filtrado pelo EOP ou pelo Defender para Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="6d9c4-302">A tabela de dados contém as seguintes informações, mostradas em ordem decrescente:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="6d9c4-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-303">**Date**</span></span>
- <span data-ttu-id="6d9c4-304">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-304">**Total email**</span></span>
- <span data-ttu-id="6d9c4-305">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-305">**Edge protection**</span></span>
- <span data-ttu-id="6d9c4-306">**Anti-malware, reputação do arquivo, bloco de tipo de arquivo:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="6d9c4-307">**Reputação do** arquivo: mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="6d9c4-308">**Bloco de tipo de** arquivo: Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="6d9c4-309">**Anti-phishing, reputação da URL, representação de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="6d9c4-310">**Reputação da URL:** mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="6d9c4-311">**Representação de marca:** mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="6d9c4-312">**Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence, ou a um domínio que o remetente da mensagem não possui.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="6d9c4-313">**Anti-spam, filtragem de email em massa:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="6d9c4-314">**Filtragem de email em massa:** mensagens filtradas devido a uma tentativa de entregar emails em massa a seus destinatários.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="6d9c4-315">**Representação de usuário e domínio (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="6d9c4-316">**Representação de usuário:** mensagens filtradas devido a uma tentativa de representar um usuário (remetente da mensagem) definida nas configurações de proteção contra representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="6d9c4-317">**Representação de domínio:** mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção contra representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="6d9c4-318">**Detonação de arquivo e URL (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="6d9c4-319">**Detonação de** arquivo: mensagens filtradas por uma política de Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="6d9c4-320">**Detonação de URL:** mensagem filtrada por uma política de Links seguros.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="6d9c4-321">**Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: a ZAP indica a limpeza automática zero hora.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="6d9c4-322">Se você selecionar uma linha na tabela de dados, uma divisão posterior das contagens de email será mostrada no flyout.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="6d9c4-323">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-323">**Export**:</span></span>

<span data-ttu-id="6d9c4-324">Depois de clicar **em Exportar** **em Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="6d9c4-325">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="6d9c4-326">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="6d9c4-327">Em **Data,** escolha um intervalo e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="6d9c4-328">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="6d9c4-329">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6d9c4-330">Se os dados contiverem mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="6d9c4-331">Exibição de funil no relatório de status do Fluxo de Mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="6d9c4-332">Exibição técnica do relatório de status do Fluxo de Mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="6d9c4-333">O **modo de exibição** Técnico é semelhante **ao** modo de exibição funil, fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="6d9c4-334">No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="6d9c4-335">Se você clicar na **guia Modo de** Exibição Técnico, por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="6d9c4-336">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="6d9c4-337">**Direção:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-337">**Direction**:</span></span>

  - <span data-ttu-id="6d9c4-338">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-338">**Inbound**</span></span>
  - <span data-ttu-id="6d9c4-339">**Saída**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-339">**Outbound**</span></span>
  - <span data-ttu-id="6d9c4-340">**Dentro da organização:** essa contagem é para mensagens em um locatário, ou seja,</span><span class="sxs-lookup"><span data-stu-id="6d9c4-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="6d9c4-341">remetente abc@domain.com envia ao destinatário xyz@domain.com (contadas separadamente de Entrada e Saída)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="6d9c4-342">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="6d9c4-343">Se você clicar **em Filtro,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="6d9c4-344">Este gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="6d9c4-345">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-345">**Total email**</span></span>
- <span data-ttu-id="6d9c4-346">**Permitir borda** e **borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="6d9c4-347">**Not malware**, **Safe Attachments detection**, <sup>\*</sup> **Anti-malware engine detection,** and **Rule messages**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="6d9c4-348">**Não phishing,** **falha do DMARC,** **detecção de representação,** detecção **de spoof** e detecção **de phishing**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="6d9c4-349">**Nenhuma detecção com a detonação de URL** e detecção **de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6d9c4-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="6d9c4-350">**Não é spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="6d9c4-351">**Email não mal-intencionado,** **detecção de Links seguros** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="6d9c4-352"><sup>\*</sup> Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6d9c4-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="6d9c4-353">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="6d9c4-354">A tabela de dados contém as seguintes informações, mostradas em ordem decrescente:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="6d9c4-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-355">**Date**</span></span>
- <span data-ttu-id="6d9c4-356">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-356">**Total email**</span></span>
- <span data-ttu-id="6d9c4-357">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-357">**Edge filtered**</span></span>
- <span data-ttu-id="6d9c4-358">**Mecanismo anti-malware, Anexos Seguros, regra filtrada:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="6d9c4-359">**Regra filtrada:** Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="6d9c4-360">**DMARC, representação, spoof, phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="6d9c4-361">**DMARC:** Mensagens filtradas devido à falha da mensagem na verificação de autenticação do DMARC.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="6d9c4-362">**Detecção de detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-362">**URL detonation detection**</span></span>
- <span data-ttu-id="6d9c4-363">**Anti-spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="6d9c4-364">**ZAP removida**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-364">**ZAP removed**</span></span>
- <span data-ttu-id="6d9c4-365">**Detecção por Links Seguros**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="6d9c4-366">Se você selecionar uma linha na tabela de dados, uma divisão posterior das contagens de email será mostrada no flyout.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="6d9c4-367">**Exportar:**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-367">**Export**:</span></span>

<span data-ttu-id="6d9c4-368">Ao clicar em **Exportar,** em **Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="6d9c4-369">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="6d9c4-370">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="6d9c4-371">Em **Data,** escolha um intervalo e clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="6d9c4-372">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="6d9c4-373">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="6d9c4-374">Se os dados contiverem mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="6d9c4-375">Exibição técnica no relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="6d9c4-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="6d9c4-376">Relatório de emails enviados e recebidos</span><span class="sxs-lookup"><span data-stu-id="6d9c4-376">Sent and received email report</span></span>

<span data-ttu-id="6d9c4-377">O **relatório de emails** enviados e recebidos é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bons".</span><span class="sxs-lookup"><span data-stu-id="6d9c4-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="6d9c4-378">A diferença entre esse relatório e o relatório de [status do fluxo](#mailflow-status-report) de mensagens é: esse relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda. É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="6d9c4-379">A exibição agregada e a exibição detalhada do relatório permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="6d9c4-380">Para exibir o relatório, abra o [Centro de Conformidade e Segurança &,](https://protection.office.com)vá para o Painel de Relatórios e selecione Enviar e receber  \>  **emails.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="6d9c4-381">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de email enviado e recebido no painel Relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="6d9c4-383">Exibição de relatório para o relatório de emails enviados e recebidos</span><span class="sxs-lookup"><span data-stu-id="6d9c4-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="6d9c4-384">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6d9c4-385">**Quebrar por: Tipo: o** gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="6d9c4-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-386">**Total**</span></span>
  - <span data-ttu-id="6d9c4-387">**Email bom**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-387">**Good mail**</span></span>
  - <span data-ttu-id="6d9c4-388">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="6d9c4-389">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-389">**Spam detections**</span></span>
  - <span data-ttu-id="6d9c4-390">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-390">**Rule messages**</span></span>
  - <span data-ttu-id="6d9c4-391">**Malware avançado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="6d9c4-392">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Type view in the Sent and received email report](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="6d9c4-394">**Quebra por: direção: o** gráfico mostra **total**, **dados** de entrada e **saída.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="6d9c4-395">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de emails enviados e recebidos](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="6d9c4-397">**Faça drill down por** \> **Malware (anti-malware)**: essa seleção leva você para as detecções [de malware no relatório de email.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="6d9c4-398">**Faça drill down por** \> **Detecções de spam)**: essa seleção leva você para o relatório de [detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="6d9c4-399">Se você clicar **em Filtros** em uma exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6d9c4-400">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="6d9c4-401">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="6d9c4-401">Direction values</span></span>
- <span data-ttu-id="6d9c4-402">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="6d9c4-402">Type values</span></span>

<span data-ttu-id="6d9c4-403">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="6d9c4-404">Exibição de tabela de detalhes para o relatório de emails enviados e recebidos</span><span class="sxs-lookup"><span data-stu-id="6d9c4-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="6d9c4-405">Se você clicar **em Exibir tabela de** detalhes no intervalo **por:** direção ou **quebra por:** exibição de direção, as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="6d9c4-406">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-406">**Date (UTC)**</span></span>
- <span data-ttu-id="6d9c4-407">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-407">**Type**</span></span>
- <span data-ttu-id="6d9c4-408">**Direção**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-408">**Direction**</span></span>
- <span data-ttu-id="6d9c4-409">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-409">**Message count**</span></span>

<span data-ttu-id="6d9c4-410">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="6d9c4-411">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="6d9c4-412">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="6d9c4-412">Direction values</span></span>
- <span data-ttu-id="6d9c4-413">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="6d9c4-413">Type values</span></span>

<span data-ttu-id="6d9c4-414">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="6d9c4-415">Relatório de principais destinatários e destinatários</span><span class="sxs-lookup"><span data-stu-id="6d9c4-415">Top senders and recipients report</span></span>

<span data-ttu-id="6d9c4-416">O **relatório de principais destinatários e destinatários** é um gráfico de pizza que mostra seus principais destinatários e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="6d9c4-417">Para exibir o relatório, abra o Centro de  [Conformidade e Segurança &,](https://protection.office.com)vá para o Painel de Relatórios e selecione Os \>  **principais destinatários e os destinatários.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="6d9c4-418">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="6d9c4-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Principal widget de destinatários e de envios no painel Relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="6d9c4-420">Report view for the Top senders and recipient report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="6d9c4-421">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="6d9c4-422">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="6d9c4-423">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="6d9c4-424">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="6d9c4-425">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="6d9c4-426">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="6d9c4-427">A composição do gráfico de pizza muda com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="6d9c4-428">Quando você passar o mouse sobre um insunte no gráfico de pizza, poderá ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="6d9c4-429">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no relatório de exibição no relatório principais destinatários e destinatários](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="6d9c4-431">Details table view for the Top senders and recipient report</span><span class="sxs-lookup"><span data-stu-id="6d9c4-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="6d9c4-432">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="6d9c4-433">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="6d9c4-434">**Principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-434">**Top mail senders**</span></span>
  - <span data-ttu-id="6d9c4-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-435">**Count**</span></span>

- <span data-ttu-id="6d9c4-436">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="6d9c4-437">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="6d9c4-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-438">**Count**</span></span>

- <span data-ttu-id="6d9c4-439">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="6d9c4-440">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="6d9c4-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-441">**Count**</span></span>

- <span data-ttu-id="6d9c4-442">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="6d9c4-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="6d9c4-443">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="6d9c4-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-444">**Count**</span></span>

- <span data-ttu-id="6d9c4-445">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="6d9c4-446">**Principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="6d9c4-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-447">**Count**</span></span>

<span data-ttu-id="6d9c4-448">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="6d9c4-449">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="6d9c4-450">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="6d9c4-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="6d9c4-451">Para exibir e usar os relatórios descritos neste artigo &, você precisa ser membro de um dos seguintes grupos de função no Centro de Conformidade e Segurança:</span><span class="sxs-lookup"><span data-stu-id="6d9c4-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="6d9c4-452">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-452">**Organization Management**</span></span>
- <span data-ttu-id="6d9c4-453">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-453">**Security Administrator**</span></span>
- <span data-ttu-id="6d9c4-454">**Leitor de segurança**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-454">**Security Reader**</span></span>
- <span data-ttu-id="6d9c4-455">**Leitor global**</span><span class="sxs-lookup"><span data-stu-id="6d9c4-455">**Global Reader**</span></span>

<span data-ttu-id="6d9c4-456">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-456">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6d9c4-457">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d9c4-457">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6d9c4-458">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6d9c4-458">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6d9c4-459">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6d9c4-459">Related topics</span></span>

[<span data-ttu-id="6d9c4-460">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="6d9c4-460">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="6d9c4-461">Insights de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="6d9c4-461">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="6d9c4-462">Exibir relatórios de segurança de email no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="6d9c4-462">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="6d9c4-463">Exibir relatórios do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6d9c4-463">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
