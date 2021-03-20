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
description: Os administradores podem aprender sobre os relatórios de fluxo de emails disponíveis no painel Relatórios no Centro de Conformidade & Segurança.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1fea50ff0eaa5ed7d671485483ecb297b404db9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906547"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="e0264-103">Exibir relatórios de fluxo de emails no painel Relatórios no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="e0264-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0264-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e0264-104">**Applies to**</span></span>
- [<span data-ttu-id="e0264-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0264-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e0264-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0264-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e0264-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0264-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="e0264-108">Além dos relatórios de fluxo de emails [](mail-flow-insights-v2.md) que estão disponíveis no painel fluxo de email no Centro de Conformidade e segurança, uma variedade de relatórios de fluxo de emails adicionais estão disponíveis no painel Relatórios para ajudá-lo & a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0264-108">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="e0264-109">Se você tiver as [permissões](#what-permissions-are-needed-to-view-these-reports)necessárias, poderá exibir esses relatórios no Centro de Conformidade e Segurança [&](https://protection.office.com) indo para **Painel de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="e0264-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e0264-110">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e0264-110">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="e0264-112">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="e0264-112">Connector report</span></span>

<span data-ttu-id="e0264-113">O **relatório conector** mostra a atividade de fluxo de emails nos conectores de entrada e de saída [configurados](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e0264-113">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="e0264-114">Para exibir o relatório, abra o Centro de Conformidade & [Segurança,](https://protection.office.com)vá **para** Painel de Relatórios e selecione \>  Relatório do **Conector.**</span><span class="sxs-lookup"><span data-stu-id="e0264-114">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="e0264-115">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="e0264-115">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de relatório do conector no painel Relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="e0264-117">Exibição de relatório para o relatório conector</span><span class="sxs-lookup"><span data-stu-id="e0264-117">Report view for the Connector report</span></span>

<span data-ttu-id="e0264-118">Os gráficos a seguir estão disponíveis no relatório:</span><span class="sxs-lookup"><span data-stu-id="e0264-118">The following charts are available in report view:</span></span>

- <span data-ttu-id="e0264-119">**Exibir dados por: Fluxo de emails**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="e0264-119">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="e0264-120">**Total**</span><span class="sxs-lookup"><span data-stu-id="e0264-120">**Total**</span></span>
  - <span data-ttu-id="e0264-121">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-121">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e0264-122">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-122">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e0264-123">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="e0264-123">A specific connector that you've configured.</span></span>

  <span data-ttu-id="e0264-124">Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma dessas opções ou Todo o fluxo de **emails.**</span><span class="sxs-lookup"><span data-stu-id="e0264-124">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="e0264-126">**Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão TLS (Transport Layer Security) para o fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="e0264-126">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="e0264-127">Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e0264-127">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="e0264-128">**Todo o fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="e0264-128">**All mail flow**</span></span>
  - <span data-ttu-id="e0264-129">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-129">**From the internet without a connector**</span></span>
  - <span data-ttu-id="e0264-130">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-130">**To the internet without a connector**</span></span>
  - <span data-ttu-id="e0264-131">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="e0264-131">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso TLS no relatório conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="e0264-133">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-133">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="e0264-134">Exibição de tabela de detalhes para o relatório conector</span><span class="sxs-lookup"><span data-stu-id="e0264-134">Details table view for the Connector report</span></span>

<span data-ttu-id="e0264-135">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="e0264-135">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e0264-136">**Date**</span><span class="sxs-lookup"><span data-stu-id="e0264-136">**Date**</span></span>
- <span data-ttu-id="e0264-137">**Nome e direção do conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-137">**Connector direction and name**</span></span>
- <span data-ttu-id="e0264-138">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="e0264-138">**Connector type**</span></span>
- <span data-ttu-id="e0264-139">**TLS forçado?**: O valor **True** ou **False**.</span><span class="sxs-lookup"><span data-stu-id="e0264-139">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="e0264-140">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="e0264-140">**No TLS** (percentage)</span></span>
- <span data-ttu-id="e0264-141">**TLS 1.0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="e0264-141">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="e0264-142">**TLS 1.1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="e0264-142">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="e0264-143">**TLS 1.2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="e0264-143">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="e0264-144">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="e0264-144">**Volume**: The number of messages.</span></span>

<span data-ttu-id="e0264-145">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-145">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e0264-146">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-146">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="e0264-147">Relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="e0264-147">Exchange transport rule report</span></span>

<span data-ttu-id="e0264-148">O **relatório de regra de transporte** do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e0264-148">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="e0264-149">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios \>  e selecione Regra de Transporte **do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e0264-149">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="e0264-150">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="e0264-150">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regra de transporte do Exchange no painel Relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e0264-152">Exibição de relatório para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="e0264-152">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="e0264-153">Os gráficos a seguir estão disponíveis no relatório:</span><span class="sxs-lookup"><span data-stu-id="e0264-153">The following charts are available in report view:</span></span>

- <span data-ttu-id="e0264-154">**Exibir dados por: Regras de transporte do** \> Exchange **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="e0264-154">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="e0264-155">**Exibir dados por: Regras de transporte do** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="e0264-155">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="e0264-156">Você definirá o nível de gravidade como uma ação na regra (**Audite essa** regra com nível de gravidade ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="e0264-156">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="e0264-157">Para obter mais informações, consulte [Ações de regra de fluxo de email no Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="e0264-157">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="e0264-158">**Exibir dados por: regras de transporte do Exchange** \> DLP **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="e0264-158">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="e0264-159">Você pode refinar ainda mais o gráfico selecionando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e0264-159">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e0264-160">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="e0264-160">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e0264-161">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="e0264-161">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e0264-162">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**</span><span class="sxs-lookup"><span data-stu-id="e0264-162">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="e0264-163">**Exibir dados por: regras de transporte do Exchange** \> DLP **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="e0264-163">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="e0264-164">Você pode refinar ainda mais o gráfico selecionando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e0264-164">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="e0264-165">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="e0264-165">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="e0264-166">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="e0264-166">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="e0264-167">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**</span><span class="sxs-lookup"><span data-stu-id="e0264-167">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="e0264-168">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros::</span><span class="sxs-lookup"><span data-stu-id="e0264-168">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="e0264-169">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e0264-169">**Start date** and **End date**</span></span>
- <span data-ttu-id="e0264-170">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e0264-170">Direction values</span></span>
- <span data-ttu-id="e0264-171">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="e0264-171">Severity values</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="e0264-173">Exibição de tabela de detalhes para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="e0264-173">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="e0264-174">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="e0264-174">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e0264-175">**Exibir dados por: Regras de Transporte do Exchange**:</span><span class="sxs-lookup"><span data-stu-id="e0264-175">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="e0264-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="e0264-176">**Date**</span></span>
  - <span data-ttu-id="e0264-177">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="e0264-177">**Transport rule**</span></span>
  - <span data-ttu-id="e0264-178">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e0264-178">**Subject**</span></span>
  - <span data-ttu-id="e0264-179">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e0264-179">**Sender address**</span></span>
  - <span data-ttu-id="e0264-180">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e0264-180">**Recipient address**</span></span>
  - <span data-ttu-id="e0264-181">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="e0264-181">**Severity**</span></span>
  - <span data-ttu-id="e0264-182">**Direção**</span><span class="sxs-lookup"><span data-stu-id="e0264-182">**Direction**</span></span>

- <span data-ttu-id="e0264-183">**Exibir dados por: regras de transporte do Exchange DLP:**</span><span class="sxs-lookup"><span data-stu-id="e0264-183">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="e0264-184">**Date**</span><span class="sxs-lookup"><span data-stu-id="e0264-184">**Date**</span></span>
  - <span data-ttu-id="e0264-185">**Política de DLP**</span><span class="sxs-lookup"><span data-stu-id="e0264-185">**DLP policy**</span></span>
  - <span data-ttu-id="e0264-186">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="e0264-186">**Transport rule**</span></span>
  - <span data-ttu-id="e0264-187">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e0264-187">**Subject**</span></span>
  - <span data-ttu-id="e0264-188">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e0264-188">**Sender address**</span></span>
  - <span data-ttu-id="e0264-189">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e0264-189">**Recipient address**</span></span>
  - <span data-ttu-id="e0264-190">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="e0264-190">**Severity**</span></span>
  - <span data-ttu-id="e0264-191">**Direção**</span><span class="sxs-lookup"><span data-stu-id="e0264-191">**Direction**</span></span>

<span data-ttu-id="e0264-192">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-192">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e0264-193">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e0264-193">**Start date** and **End date**</span></span>
- <span data-ttu-id="e0264-194">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e0264-194">Direction values</span></span>
- <span data-ttu-id="e0264-195">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="e0264-195">Severity values</span></span>

<span data-ttu-id="e0264-196">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-196">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="e0264-197">Relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="e0264-197">Forwarding report</span></span>

<span data-ttu-id="e0264-198">O **relatório de encaminhamento** mostra as mensagens encaminhadas automaticamente para domínios externos de caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e0264-198">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="e0264-199">As mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="e0264-199">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="e0264-200">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de \>  Relatórios e selecione Relatório **de Encaminhamento.**</span><span class="sxs-lookup"><span data-stu-id="e0264-200">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="e0264-201">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="e0264-201">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de relatório de encaminhamento no painel Relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="e0264-203">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="e0264-203">Report view for the Forwarding report</span></span>

<span data-ttu-id="e0264-204">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="e0264-204">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e0264-205">**Mostrar dados para: métodos de encaminhamento**: Os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="e0264-205">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="e0264-206">**Regra de transporte**: Também conhecidas como regras [de fluxo de emails.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="e0264-206">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="e0264-207">**Regra de caixa de** correio : Também conhecidas como [regras de Caixa de Entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="e0264-207">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Modo de exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="e0264-209">**Mostrar dados para: Domínios de** encaminhamento : Esta exibição mostra os domínios do destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="e0264-209">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="e0264-211">**Mostrar dados para: Encaminhadores**: Os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="e0264-211">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="e0264-212">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="e0264-212">**Transport rule**</span></span>
  - <span data-ttu-id="e0264-213">A caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="e0264-213">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="e0264-215">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-215">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="e0264-216">Exibição de tabela de detalhes para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="e0264-216">Details table view for the Forwarding report</span></span>

<span data-ttu-id="e0264-217">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="e0264-217">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="e0264-218">**Encaminhadores**: a regra **de transporte de** valor ou a caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="e0264-218">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="e0264-219">**Tipo de encaminhamento**: a regra **de caixa de correio de** valor ou a regra de **Transporte.**</span><span class="sxs-lookup"><span data-stu-id="e0264-219">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="e0264-220">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e0264-220">**Recipient name**</span></span>
- <span data-ttu-id="e0264-221">**Domínio de destinatário**</span><span class="sxs-lookup"><span data-stu-id="e0264-221">**Recipient domain**</span></span>
- <span data-ttu-id="e0264-222">**Detalhes**: este é o valor GUID da regra de fluxo de emails ou o valor RuleIdentity da regra caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="e0264-222">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="e0264-223">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-223">**Count**</span></span>
- <span data-ttu-id="e0264-224">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="e0264-224">**First forward date**</span></span>

<span data-ttu-id="e0264-225">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-225">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e0264-226">Para voltar à exibição de relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-226">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e0264-227">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-227">Mailflow status report</span></span>

<span data-ttu-id="e0264-228">O **relatório de status de fluxo** de emails é semelhante ao relatório de [email](#sent-and-received-email-report)Enviado e recebido, com informações adicionais sobre emails permitidos ou bloqueados na borda.</span><span class="sxs-lookup"><span data-stu-id="e0264-228">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="e0264-229">Este é o único relatório que contém informações de proteção de borda e mostra a quantos emails são bloqueados antes de serem permitidos no serviço para avaliação pela Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="e0264-229">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="e0264-230">É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e0264-230">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="e0264-231">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Relatório de status de fluxo **de emails.**</span><span class="sxs-lookup"><span data-stu-id="e0264-231">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="e0264-232">Para ir diretamente para o relatório de **status de fluxo de email**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="e0264-232">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de relatório de status de fluxo de emails no painel Relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="e0264-234">Exibição de tipo para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-234">Type view for the Mailflow status report</span></span>

<span data-ttu-id="e0264-235">Quando você abre o relatório, a guia **Tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e0264-235">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="e0264-236">Por padrão, esse modo de exibição contém um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-236">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e0264-237">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e0264-237">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="e0264-238">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="e0264-238">**Direction**:</span></span>

  - <span data-ttu-id="e0264-239">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="e0264-239">**Inbound**</span></span>
  - <span data-ttu-id="e0264-240">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e0264-240">**Outbound**</span></span>
  - <span data-ttu-id="e0264-241">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="e0264-241">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e0264-242">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)</span><span class="sxs-lookup"><span data-stu-id="e0264-242">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="e0264-243">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="e0264-243">**Type**:</span></span>

  - <span data-ttu-id="e0264-244">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="e0264-244">**Good mail**</span></span>
  - <span data-ttu-id="e0264-245">**Malware**</span><span class="sxs-lookup"><span data-stu-id="e0264-245">**Malware**</span></span>
  - <span data-ttu-id="e0264-246">**Spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-246">**Spam**</span></span>
  - <span data-ttu-id="e0264-247">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="e0264-247">**Edge protection**</span></span>
  - <span data-ttu-id="e0264-248">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="e0264-248">**Rule messages**</span></span>
  - <span data-ttu-id="e0264-249">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="e0264-249">**Phishing email**</span></span>

<span data-ttu-id="e0264-250">O gráfico é organizado pelos valores **Type.**</span><span class="sxs-lookup"><span data-stu-id="e0264-250">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="e0264-251">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="e0264-251">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="e0264-252">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e0264-252">The data table contains the following information:</span></span>

- <span data-ttu-id="e0264-253">**Direção**</span><span class="sxs-lookup"><span data-stu-id="e0264-253">**Direction**</span></span>
- <span data-ttu-id="e0264-254">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e0264-254">**Type**</span></span>
- <span data-ttu-id="e0264-255">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="e0264-255">**24 hours**</span></span>
- <span data-ttu-id="e0264-256">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="e0264-256">**3 days**</span></span>
- <span data-ttu-id="e0264-257">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="e0264-257">**7 days**</span></span>
- <span data-ttu-id="e0264-258">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="e0264-258">**15 days**</span></span>
- <span data-ttu-id="e0264-259">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="e0264-259">**30 days**</span></span>

<span data-ttu-id="e0264-260">Se você clicar **em Escolher uma categoria para obter** mais detalhes, você poderá selecionar entre os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e0264-260">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="e0264-261">**Email de phishing**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-261">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e0264-262">**Malware no email**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-262">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="e0264-263">**Detecções de** spam: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-263">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="e0264-264">**Spam bloqueado de borda:** essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-264">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e0264-265">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="e0264-265">**Export**:</span></span>

<span data-ttu-id="e0264-266">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="e0264-266">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e0264-267">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="e0264-267">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e0264-268">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="e0264-268">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e0264-269">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="e0264-269">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e0264-270">Type view in the Mailflow status report</span><span class="sxs-lookup"><span data-stu-id="e0264-270">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="e0264-271">Exibição de direção para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-271">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="e0264-272">Se você clicar na guia **Direção,** os mesmos filtros padrão do modo de exibição **Tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="e0264-272">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="e0264-273">O gráfico é organizado pelos **valores Direction.**</span><span class="sxs-lookup"><span data-stu-id="e0264-273">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="e0264-274">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="e0264-274">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="e0264-275">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="e0264-275">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="e0264-276">A tabela de dados contém as mesmas informações do modo **de exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="e0264-276">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="e0264-277">A **opção Escolher uma categoria para obter** mais detalhes sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="e0264-277">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="e0264-278">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="e0264-278">**Export**:</span></span>

<span data-ttu-id="e0264-279">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="e0264-279">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="e0264-280">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="e0264-280">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="e0264-281">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="e0264-281">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e0264-282">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="e0264-282">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="e0264-283">Exibição de direção no relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-283">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="e0264-284">Exibição de funil para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-284">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="e0264-285">A **exibição** Funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e0264-285">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="e0264-286">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="e0264-286">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="e0264-287">Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-287">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e0264-288">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e0264-288">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e0264-289">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="e0264-289">**Direction**:</span></span>

  - <span data-ttu-id="e0264-290">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="e0264-290">**Inbound**</span></span>
  - <span data-ttu-id="e0264-291">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e0264-291">**Outbound**</span></span>
  - <span data-ttu-id="e0264-292">**Intra-org**: esta contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de Entrada e Saída).</span><span class="sxs-lookup"><span data-stu-id="e0264-292">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="e0264-293">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="e0264-293">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e0264-294">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="e0264-294">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e0264-295">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="e0264-295">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="e0264-296">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="e0264-296">**Total email**</span></span>
- <span data-ttu-id="e0264-297">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="e0264-297">**Email after edge protection**</span></span>
- <span data-ttu-id="e0264-298">**Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="e0264-298">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="e0264-299">**Email após anti-phishing, reputação de URL, representação de marca, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="e0264-299">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="e0264-300">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="e0264-300">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="e0264-301">**Email após a representação de usuário e domínio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e0264-301">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="e0264-302">**Email após a detonação de arquivo e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e0264-302">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="e0264-303">**Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique na URL)**</span><span class="sxs-lookup"><span data-stu-id="e0264-303">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="e0264-304"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="e0264-304"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="e0264-305">Para exibir o email filtrado pelo EOP ou pelo Defender para Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="e0264-305">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="e0264-306">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="e0264-306">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e0264-307">**Date**</span><span class="sxs-lookup"><span data-stu-id="e0264-307">**Date**</span></span>
- <span data-ttu-id="e0264-308">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="e0264-308">**Total email**</span></span>
- <span data-ttu-id="e0264-309">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="e0264-309">**Edge protection**</span></span>
- <span data-ttu-id="e0264-310">**Anti-malware, reputação de arquivo, bloco de tipo de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="e0264-310">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="e0264-311">**Reputação do** arquivo : Mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0264-311">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="e0264-312">**Bloco de tipo de** arquivo : Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="e0264-312">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="e0264-313">**Anti-phish, reputação de URL, representação de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="e0264-313">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="e0264-314">**Reputação da URL**: Mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e0264-314">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="e0264-315">**Representação de marca**: Mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.</span><span class="sxs-lookup"><span data-stu-id="e0264-315">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="e0264-316">**Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence ou a um domínio que o remetente da mensagem não possui.</span><span class="sxs-lookup"><span data-stu-id="e0264-316">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="e0264-317">**Anti-spam, filtragem de email em massa:**</span><span class="sxs-lookup"><span data-stu-id="e0264-317">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="e0264-318">**Filtragem em massa de** emails : Mensagens filtradas devido a uma tentativa de entregar emails em massa para seus destinatários.</span><span class="sxs-lookup"><span data-stu-id="e0264-318">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="e0264-319">**Representação de usuário e domínio (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e0264-319">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e0264-320">**Representação do** usuário : Mensagens filtradas devido a uma tentativa de representar um usuário (remetente de mensagem) definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="e0264-320">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="e0264-321">**Representação de domínio**: Mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="e0264-321">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="e0264-322">**Detonação de arquivo e URL (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="e0264-322">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="e0264-323">**Detonação de** arquivo : mensagens filtradas por uma política de Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="e0264-323">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="e0264-324">**Detonação de URL**: Mensagem filtrada por uma política de Links Seguros.</span><span class="sxs-lookup"><span data-stu-id="e0264-324">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="e0264-325">**Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: ZAP indica limpeza automática de zero hora.</span><span class="sxs-lookup"><span data-stu-id="e0264-325">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="e0264-326">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="e0264-326">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e0264-327">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="e0264-327">**Export**:</span></span>

<span data-ttu-id="e0264-328">Depois de clicar **em Exportar** **em Opções,** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e0264-328">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="e0264-329">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="e0264-329">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e0264-330">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="e0264-330">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e0264-331">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e0264-331">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e0264-332">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="e0264-332">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e0264-333">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="e0264-333">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e0264-334">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="e0264-334">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e0264-335">Exibição de funil no relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e0264-335">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="e0264-336">Exibição técnica do relatório de status mailflow</span><span class="sxs-lookup"><span data-stu-id="e0264-336">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="e0264-337">O **modo de exibição** Tech é semelhante ao modo de exibição **Funil,** fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="e0264-337">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="e0264-338">No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="e0264-338">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="e0264-339">Se você clicar na **guia Modo de** Exibição de Tecnologia, por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-339">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="e0264-340">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e0264-340">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="e0264-341">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="e0264-341">**Direction**:</span></span>

  - <span data-ttu-id="e0264-342">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="e0264-342">**Inbound**</span></span>
  - <span data-ttu-id="e0264-343">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e0264-343">**Outbound**</span></span>
  - <span data-ttu-id="e0264-344">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="e0264-344">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="e0264-345">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de Entrada e Saída)</span><span class="sxs-lookup"><span data-stu-id="e0264-345">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="e0264-346">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="e0264-346">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="e0264-347">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="e0264-347">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="e0264-348">Este gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="e0264-348">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="e0264-349">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="e0264-349">**Total email**</span></span>
- <span data-ttu-id="e0264-350">**Permitir borda** e **Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="e0264-350">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="e0264-351">**Não malware,** **detecção de anexos seguros,** <sup>\*</sup> detecção de mecanismo **anti-malware** e **mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="e0264-351">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="e0264-352">**Não phish**, **falha de DMARC,** detecção de **representação,** detecção **de spoof** e **detecção de phishing**</span><span class="sxs-lookup"><span data-stu-id="e0264-352">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="e0264-353">**Nenhuma detecção com detonação de URL** e detecção **de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0264-353">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="e0264-354">**Não spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-354">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="e0264-355">**Email não mal-intencionado,** **detecção de Links Seguros** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="e0264-355">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="e0264-356"><sup>\*</sup> Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0264-356"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="e0264-357">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="e0264-357">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="e0264-358">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="e0264-358">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="e0264-359">**Date**</span><span class="sxs-lookup"><span data-stu-id="e0264-359">**Date**</span></span>
- <span data-ttu-id="e0264-360">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="e0264-360">**Total email**</span></span>
- <span data-ttu-id="e0264-361">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="e0264-361">**Edge filtered**</span></span>
- <span data-ttu-id="e0264-362">**Mecanismo anti-malware, Anexos Seguros, regra filtrada**:</span><span class="sxs-lookup"><span data-stu-id="e0264-362">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="e0264-363">**Regra filtrada**: Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="e0264-363">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="e0264-364">**DMARC, representação, spoof, phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="e0264-364">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="e0264-365">**DMARC**: Mensagens filtradas devido à falha da mensagem em sua verificação de autenticação DMARC.</span><span class="sxs-lookup"><span data-stu-id="e0264-365">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="e0264-366">**Detecção de detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="e0264-366">**URL detonation detection**</span></span>
- <span data-ttu-id="e0264-367">**Anti-spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="e0264-367">**Anti-spam filtered**</span></span>
- <span data-ttu-id="e0264-368">**ZAP removido**</span><span class="sxs-lookup"><span data-stu-id="e0264-368">**ZAP removed**</span></span>
- <span data-ttu-id="e0264-369">**Detecção por Links Seguros**</span><span class="sxs-lookup"><span data-stu-id="e0264-369">**Detection by Safe Links**</span></span>

<span data-ttu-id="e0264-370">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="e0264-370">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="e0264-371">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="e0264-371">**Export**:</span></span>

<span data-ttu-id="e0264-372">Ao clicar em **Exportar**, em **Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e0264-372">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="e0264-373">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="e0264-373">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="e0264-374">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="e0264-374">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="e0264-375">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e0264-375">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="e0264-376">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="e0264-376">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="e0264-377">Cada arquivo .csv exportado é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="e0264-377">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="e0264-378">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="e0264-378">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="e0264-379">Exibição técnica no relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="e0264-379">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e0264-380">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="e0264-380">Sent and received email report</span></span>

<span data-ttu-id="e0264-381">O **relatório de email** enviado e recebido é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bons".</span><span class="sxs-lookup"><span data-stu-id="e0264-381">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="e0264-382">A diferença entre este relatório e o relatório de status de [fluxo](#mailflow-status-report) de emails é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda. É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e0264-382">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="e0264-383">A exibição agregada e a exibição detalhada do relatório permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="e0264-383">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="e0264-384">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Enviar e **receber emails**.</span><span class="sxs-lookup"><span data-stu-id="e0264-384">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="e0264-385">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="e0264-385">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de email enviado e recebido no painel Relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e0264-387">Exibição de relatório para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="e0264-387">Report view for the Sent and received email report</span></span>

<span data-ttu-id="e0264-388">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="e0264-388">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e0264-389">**Break down by: Type**: O gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e0264-389">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="e0264-390">**Total**</span><span class="sxs-lookup"><span data-stu-id="e0264-390">**Total**</span></span>
  - <span data-ttu-id="e0264-391">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="e0264-391">**Good mail**</span></span>
  - <span data-ttu-id="e0264-392">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e0264-392">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="e0264-393">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-393">**Spam detections**</span></span>
  - <span data-ttu-id="e0264-394">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="e0264-394">**Rule messages**</span></span>
  - <span data-ttu-id="e0264-395">**Malware avançado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="e0264-395">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="e0264-396">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.</span><span class="sxs-lookup"><span data-stu-id="e0264-396">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Type view in the Sent and received email report](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="e0264-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="e0264-398">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="e0264-399">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.</span><span class="sxs-lookup"><span data-stu-id="e0264-399">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="e0264-401">**Detalhar por** \> **Malware (anti-malware)**: essa seleção leva você para as detecções [de malware no relatório de email.](view-email-security-reports.md#malware-detections-in-email-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-401">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="e0264-402">**Detalhar por** \> **Detecções de spam)**: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="e0264-402">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="e0264-403">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-403">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e0264-404">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e0264-404">**Start date** and **End date**</span></span>
- <span data-ttu-id="e0264-405">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e0264-405">Direction values</span></span>
- <span data-ttu-id="e0264-406">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="e0264-406">Type values</span></span>

<span data-ttu-id="e0264-407">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-407">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="e0264-408">Exibição de tabela de detalhes para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="e0264-408">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="e0264-409">Se você clicar **em Exibir tabela de** detalhes na tabela Break down **by: Direction** or Break down **by: Direction** view, the following information is shown:</span><span class="sxs-lookup"><span data-stu-id="e0264-409">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="e0264-410">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="e0264-410">**Date (UTC)**</span></span>
- <span data-ttu-id="e0264-411">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e0264-411">**Type**</span></span>
- <span data-ttu-id="e0264-412">**Direção**</span><span class="sxs-lookup"><span data-stu-id="e0264-412">**Direction**</span></span>
- <span data-ttu-id="e0264-413">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="e0264-413">**Message count**</span></span>

<span data-ttu-id="e0264-414">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e0264-414">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e0264-415">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e0264-415">**Start date** and **End date**</span></span>
- <span data-ttu-id="e0264-416">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e0264-416">Direction values</span></span>
- <span data-ttu-id="e0264-417">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="e0264-417">Type values</span></span>

<span data-ttu-id="e0264-418">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-418">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="e0264-419">Relatório de destinatários e destinatários principais</span><span class="sxs-lookup"><span data-stu-id="e0264-419">Top senders and recipients report</span></span>

<span data-ttu-id="e0264-420">O **relatório Principais destinatários e destinatários** é um gráfico de pizza mostrando seus principais destinatários e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="e0264-420">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="e0264-421">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Principais destinatários e destinatários.**</span><span class="sxs-lookup"><span data-stu-id="e0264-421">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="e0264-422">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="e0264-422">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Principais destinatários e destinatários do widget no painel Relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e0264-424">Exibição de relatório para os principais destinatários e destinatários</span><span class="sxs-lookup"><span data-stu-id="e0264-424">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="e0264-425">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="e0264-425">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e0264-426">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-426">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="e0264-427">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-427">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="e0264-428">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-428">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="e0264-429">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e0264-429">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="e0264-430">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e0264-430">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="e0264-431">A composição do gráfico de pizza muda com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="e0264-431">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="e0264-432">Ao passar o mouse sobre uma cunha no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="e0264-432">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="e0264-433">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-433">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no relatório no relatório Principais destinatários e destinatários](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="e0264-435">Exibição de tabela de detalhes para o relatório de destinatários e destinatários principais</span><span class="sxs-lookup"><span data-stu-id="e0264-435">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="e0264-436">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="e0264-436">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e0264-437">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-437">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="e0264-438">**Principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-438">**Top mail senders**</span></span>
  - <span data-ttu-id="e0264-439">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-439">**Count**</span></span>

- <span data-ttu-id="e0264-440">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-440">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="e0264-441">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="e0264-441">**Top mail recipients**</span></span>
  - <span data-ttu-id="e0264-442">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-442">**Count**</span></span>

- <span data-ttu-id="e0264-443">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-443">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="e0264-444">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="e0264-444">**Top spam recipients**</span></span>
  - <span data-ttu-id="e0264-445">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-445">**Count**</span></span>

- <span data-ttu-id="e0264-446">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="e0264-446">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="e0264-447">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="e0264-447">**Top malware recipients**</span></span>
  - <span data-ttu-id="e0264-448">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-448">**Count**</span></span>

- <span data-ttu-id="e0264-449">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e0264-449">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="e0264-450">**Principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="e0264-450">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="e0264-451">**Count**</span><span class="sxs-lookup"><span data-stu-id="e0264-451">**Count**</span></span>

<span data-ttu-id="e0264-452">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="e0264-452">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="e0264-453">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e0264-453">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e0264-454">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="e0264-454">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e0264-455">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="e0264-455">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e0264-456">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="e0264-456">**Organization Management**</span></span>
- <span data-ttu-id="e0264-457">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="e0264-457">**Security Administrator**</span></span>
- <span data-ttu-id="e0264-458">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="e0264-458">**Security Reader**</span></span>
- <span data-ttu-id="e0264-459">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="e0264-459">**Global Reader**</span></span>

<span data-ttu-id="e0264-460">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e0264-460">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e0264-461">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e0264-461">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e0264-462">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e0264-462">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e0264-463">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e0264-463">Related topics</span></span>

[<span data-ttu-id="e0264-464">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="e0264-464">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e0264-465">Insights de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="e0264-465">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="e0264-466">Exibir relatórios de segurança de email no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="e0264-466">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="e0264-467">Exibir relatórios do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e0264-467">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)