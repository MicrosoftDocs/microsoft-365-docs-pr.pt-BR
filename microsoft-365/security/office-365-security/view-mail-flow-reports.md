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
ms.openlocfilehash: 5f2bdb32d2afde3d0d40261cd3ecf30740dc0ccf
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029435"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="9af5f-103">Exibir relatórios de fluxo de emails no painel Relatórios no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="9af5f-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9af5f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9af5f-104">**Applies to**</span></span>
- [<span data-ttu-id="9af5f-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9af5f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9af5f-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9af5f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9af5f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9af5f-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="9af5f-108">A maioria dos relatórios descritos neste tópico está disponível no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="9af5f-108">The majority of the reports that are described in this topic are available in the Exchange admin center (EAC).</span></span> <span data-ttu-id="9af5f-109">Para obter mais informações, consulte [Relatórios de fluxo de emails no novo centro de administração do Exchange.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)</span><span class="sxs-lookup"><span data-stu-id="9af5f-109">For more information, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span> <span data-ttu-id="9af5f-110">O [relatório de regra de transporte](view-email-security-reports.md#exchange-transport-rule-report) do Exchange está disponível no portal do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9af5f-110">The [Exchange transport rule report](view-email-security-reports.md#exchange-transport-rule-report) is available in the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="9af5f-111">Além dos relatórios de fluxo de emails [](mail-flow-insights-v2.md) que estão disponíveis no painel fluxo de email no Centro de Conformidade e segurança, uma variedade de relatórios de fluxo de emails adicionais estão disponíveis no painel Relatórios para ajudá-lo & a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9af5f-111">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="9af5f-112">Se você tiver as [permissões](#what-permissions-are-needed-to-view-these-reports)necessárias, poderá exibir esses relatórios no Centro de Conformidade e Segurança [&](https://protection.office.com) indo para **Painel de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-112">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://protection.office.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="9af5f-113">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-113">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="9af5f-115">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="9af5f-115">Connector report</span></span>

<span data-ttu-id="9af5f-116">O **relatório conector** mostra a atividade de fluxo de emails nos conectores de entrada e de saída [configurados](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9af5f-116">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="9af5f-117">Para exibir o relatório, abra o Centro de Conformidade & [Segurança,](https://protection.office.com)vá **para** Painel de Relatórios e selecione \>  Relatório do **Conector.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-117">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="9af5f-118">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-118">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget de relatório do conector no painel Relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="9af5f-120">Exibição de relatório para o relatório conector</span><span class="sxs-lookup"><span data-stu-id="9af5f-120">Report view for the Connector report</span></span>

<span data-ttu-id="9af5f-121">Os gráficos a seguir estão disponíveis no relatório:</span><span class="sxs-lookup"><span data-stu-id="9af5f-121">The following charts are available in report view:</span></span>

- <span data-ttu-id="9af5f-122">**Exibir dados por: Fluxo de emails**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="9af5f-122">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="9af5f-123">**Total**</span><span class="sxs-lookup"><span data-stu-id="9af5f-123">**Total**</span></span>
  - <span data-ttu-id="9af5f-124">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-124">**From the internet without a connector**</span></span>
  - <span data-ttu-id="9af5f-125">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-125">**To the internet without a connector**</span></span>
  - <span data-ttu-id="9af5f-126">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="9af5f-126">A specific connector that you've configured.</span></span>

  <span data-ttu-id="9af5f-127">Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma dessas opções ou Todo o fluxo de **emails.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-127">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="9af5f-129">**Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão TLS (Transport Layer Security) para o fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="9af5f-129">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="9af5f-130">Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9af5f-130">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="9af5f-131">**Todo o fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="9af5f-131">**All mail flow**</span></span>
  - <span data-ttu-id="9af5f-132">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-132">**From the internet without a connector**</span></span>
  - <span data-ttu-id="9af5f-133">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-133">**To the internet without a connector**</span></span>
  - <span data-ttu-id="9af5f-134">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="9af5f-134">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso TLS no relatório conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="9af5f-136">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-136">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="9af5f-137">Exibição de tabela de detalhes para o relatório conector</span><span class="sxs-lookup"><span data-stu-id="9af5f-137">Details table view for the Connector report</span></span>

<span data-ttu-id="9af5f-138">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="9af5f-138">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9af5f-139">**Date**</span><span class="sxs-lookup"><span data-stu-id="9af5f-139">**Date**</span></span>
- <span data-ttu-id="9af5f-140">**Nome e direção do conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-140">**Connector direction and name**</span></span>
- <span data-ttu-id="9af5f-141">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="9af5f-141">**Connector type**</span></span>
- <span data-ttu-id="9af5f-142">**TLS forçado?**: O valor **True** ou **False**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-142">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="9af5f-143">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="9af5f-143">**No TLS** (percentage)</span></span>
- <span data-ttu-id="9af5f-144">**TLS 1.0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="9af5f-144">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="9af5f-145">**TLS 1.1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="9af5f-145">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="9af5f-146">**TLS 1.2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="9af5f-146">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="9af5f-147">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9af5f-147">**Volume**: The number of messages.</span></span>

<span data-ttu-id="9af5f-148">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9af5f-149">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-149">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="9af5f-150">Relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="9af5f-150">Exchange transport rule report</span></span>

<span data-ttu-id="9af5f-151">O **relatório de regra de transporte** do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9af5f-151">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="9af5f-152">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios \>  e selecione Regra de Transporte **do Exchange.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-152">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="9af5f-153">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-153">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget de regra de transporte do Exchange no painel Relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="9af5f-155">Exibição de relatório para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="9af5f-155">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="9af5f-156">Os gráficos a seguir estão disponíveis no relatório:</span><span class="sxs-lookup"><span data-stu-id="9af5f-156">The following charts are available in report view:</span></span>

- <span data-ttu-id="9af5f-157">**Exibir dados por: Regras de transporte do** \> Exchange **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span><span class="sxs-lookup"><span data-stu-id="9af5f-157">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="9af5f-158">**Exibir dados por: Regras de transporte do** \> Exchange **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span><span class="sxs-lookup"><span data-stu-id="9af5f-158">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="9af5f-159">Você definirá o nível de gravidade como uma ação na regra (**Audite essa** regra com nível de gravidade ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="9af5f-159">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="9af5f-160">Para obter mais informações, consulte [Ações de regra de fluxo de email no Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="9af5f-160">For more information, see [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="9af5f-161">**Exibir dados por: regras de transporte do Exchange** \> DLP **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span><span class="sxs-lookup"><span data-stu-id="9af5f-161">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="9af5f-162">Você pode refinar ainda mais o gráfico selecionando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9af5f-162">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="9af5f-163">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="9af5f-163">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="9af5f-164">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="9af5f-164">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="9af5f-165">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**</span><span class="sxs-lookup"><span data-stu-id="9af5f-165">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="9af5f-166">**Exibir dados por: regras de transporte do Exchange** \> DLP **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span><span class="sxs-lookup"><span data-stu-id="9af5f-166">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="9af5f-167">Você pode refinar ainda mais o gráfico selecionando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9af5f-167">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="9af5f-168">**Mostrar dados para: Todas as regras de transporte de DLP**</span><span class="sxs-lookup"><span data-stu-id="9af5f-168">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="9af5f-169">**Mostrar dados para: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="9af5f-169">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="9af5f-170">**Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**</span><span class="sxs-lookup"><span data-stu-id="9af5f-170">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="9af5f-171">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros::</span><span class="sxs-lookup"><span data-stu-id="9af5f-171">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="9af5f-172">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="9af5f-172">**Start date** and **End date**</span></span>
- <span data-ttu-id="9af5f-173">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="9af5f-173">Direction values</span></span>
- <span data-ttu-id="9af5f-174">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="9af5f-174">Severity values</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="9af5f-176">Exibição de tabela de detalhes para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="9af5f-176">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="9af5f-177">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="9af5f-177">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9af5f-178">**Exibir dados por: Regras de Transporte do Exchange**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-178">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="9af5f-179">**Date**</span><span class="sxs-lookup"><span data-stu-id="9af5f-179">**Date**</span></span>
  - <span data-ttu-id="9af5f-180">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="9af5f-180">**Transport rule**</span></span>
  - <span data-ttu-id="9af5f-181">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="9af5f-181">**Subject**</span></span>
  - <span data-ttu-id="9af5f-182">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-182">**Sender address**</span></span>
  - <span data-ttu-id="9af5f-183">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="9af5f-183">**Recipient address**</span></span>
  - <span data-ttu-id="9af5f-184">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="9af5f-184">**Severity**</span></span>
  - <span data-ttu-id="9af5f-185">**Direção**</span><span class="sxs-lookup"><span data-stu-id="9af5f-185">**Direction**</span></span>

- <span data-ttu-id="9af5f-186">**Exibir dados por: regras de transporte do Exchange DLP:**</span><span class="sxs-lookup"><span data-stu-id="9af5f-186">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="9af5f-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="9af5f-187">**Date**</span></span>
  - <span data-ttu-id="9af5f-188">**Política DLP**</span><span class="sxs-lookup"><span data-stu-id="9af5f-188">**DLP policy**</span></span>
  - <span data-ttu-id="9af5f-189">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="9af5f-189">**Transport rule**</span></span>
  - <span data-ttu-id="9af5f-190">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="9af5f-190">**Subject**</span></span>
  - <span data-ttu-id="9af5f-191">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-191">**Sender address**</span></span>
  - <span data-ttu-id="9af5f-192">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="9af5f-192">**Recipient address**</span></span>
  - <span data-ttu-id="9af5f-193">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="9af5f-193">**Severity**</span></span>
  - <span data-ttu-id="9af5f-194">**Direção**</span><span class="sxs-lookup"><span data-stu-id="9af5f-194">**Direction**</span></span>

<span data-ttu-id="9af5f-195">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-195">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9af5f-196">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="9af5f-196">**Start date** and **End date**</span></span>
- <span data-ttu-id="9af5f-197">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="9af5f-197">Direction values</span></span>
- <span data-ttu-id="9af5f-198">Valores de severidade</span><span class="sxs-lookup"><span data-stu-id="9af5f-198">Severity values</span></span>

<span data-ttu-id="9af5f-199">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-199">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="9af5f-200">Relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="9af5f-200">Forwarding report</span></span>

<span data-ttu-id="9af5f-201">O **relatório de encaminhamento** mostra as mensagens encaminhadas automaticamente da sua organização para domínios externos Exchange Online caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="9af5f-201">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="9af5f-202">As mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="9af5f-202">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="9af5f-203">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de \>  Relatórios e selecione Relatório **de Encaminhamento.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-203">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="9af5f-204">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-204">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de relatório de encaminhamento no painel Relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="9af5f-206">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="9af5f-206">Report view for the Forwarding report</span></span>

<span data-ttu-id="9af5f-207">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="9af5f-207">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9af5f-208">**Mostrar dados para: métodos de encaminhamento**: Os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="9af5f-208">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="9af5f-209">**Regra de transporte**: Também conhecidas como regras [de fluxo de emails.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="9af5f-209">**Transport rule**: Also known as [mail flow rules](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="9af5f-210">**Regra de caixa de** correio : Também conhecidas como [regras de Caixa de Entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="9af5f-210">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Modo de exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="9af5f-212">**Mostrar dados para: Domínios de** encaminhamento : Esta exibição mostra os domínios do destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="9af5f-212">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="9af5f-214">**Mostrar dados para: Encaminhadores**: Os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="9af5f-214">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="9af5f-215">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="9af5f-215">**Transport rule**</span></span>
  - <span data-ttu-id="9af5f-216">A caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="9af5f-216">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="9af5f-218">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-218">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="9af5f-219">Exibição de tabela de detalhes para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="9af5f-219">Details table view for the Forwarding report</span></span>

<span data-ttu-id="9af5f-220">Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="9af5f-220">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="9af5f-221">**Encaminhadores**: a regra **de transporte de** valor ou a caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="9af5f-221">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="9af5f-222">**Tipo de encaminhamento**: a regra **de caixa de correio de** valor ou a regra de **Transporte.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-222">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="9af5f-223">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="9af5f-223">**Recipient name**</span></span>
- <span data-ttu-id="9af5f-224">**Domínio de destinatário**</span><span class="sxs-lookup"><span data-stu-id="9af5f-224">**Recipient domain**</span></span>
- <span data-ttu-id="9af5f-225">**Detalhes**: este é o valor GUID da regra de fluxo de emails ou o valor RuleIdentity da regra caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="9af5f-225">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="9af5f-226">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-226">**Count**</span></span>
- <span data-ttu-id="9af5f-227">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="9af5f-227">**First forward date**</span></span>

<span data-ttu-id="9af5f-228">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-228">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9af5f-229">Para voltar à exibição de relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-229">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="9af5f-230">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9af5f-230">Mailflow status report</span></span>

<span data-ttu-id="9af5f-231">O **relatório de status de fluxo** de emails é semelhante ao relatório de [email](#sent-and-received-email-report)Enviado e recebido, com informações adicionais sobre emails permitidos ou bloqueados na borda.</span><span class="sxs-lookup"><span data-stu-id="9af5f-231">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="9af5f-232">Este é o único relatório que contém informações de proteção de borda e mostra a quantos emails são bloqueados antes de serem permitidos no serviço para avaliação por Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="9af5f-232">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="9af5f-233">É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-233">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="9af5f-234">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Relatório de status de fluxo **de emails.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-234">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="9af5f-235">Para ir diretamente para o relatório de **status de fluxo de email**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-235">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget de relatório de status de fluxo de emails no painel Relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="9af5f-237">Exibição de tipo para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9af5f-237">Type view for the Mailflow status report</span></span>

<span data-ttu-id="9af5f-238">Quando você abre o relatório, a guia **Tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="9af5f-238">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="9af5f-239">Por padrão, esse modo de exibição contém um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-239">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9af5f-240">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="9af5f-240">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="9af5f-241">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-241">**Direction**:</span></span>

  - <span data-ttu-id="9af5f-242">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="9af5f-242">**Inbound**</span></span>
  - <span data-ttu-id="9af5f-243">**Saída**</span><span class="sxs-lookup"><span data-stu-id="9af5f-243">**Outbound**</span></span>
  - <span data-ttu-id="9af5f-244">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="9af5f-244">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="9af5f-245">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)</span><span class="sxs-lookup"><span data-stu-id="9af5f-245">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="9af5f-246">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-246">**Type**:</span></span>

  - <span data-ttu-id="9af5f-247">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-247">**Good mail**</span></span>
  - <span data-ttu-id="9af5f-248">**Malware**</span><span class="sxs-lookup"><span data-stu-id="9af5f-248">**Malware**</span></span>
  - <span data-ttu-id="9af5f-249">**Spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-249">**Spam**</span></span>
  - <span data-ttu-id="9af5f-250">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="9af5f-250">**Edge protection**</span></span>
  - <span data-ttu-id="9af5f-251">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="9af5f-251">**Rule messages**</span></span>
  - <span data-ttu-id="9af5f-252">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="9af5f-252">**Phishing email**</span></span>

<span data-ttu-id="9af5f-253">O gráfico é organizado pelos valores **Type.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-253">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="9af5f-254">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="9af5f-254">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="9af5f-255">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9af5f-255">The data table contains the following information:</span></span>

- <span data-ttu-id="9af5f-256">**Direção**</span><span class="sxs-lookup"><span data-stu-id="9af5f-256">**Direction**</span></span>
- <span data-ttu-id="9af5f-257">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9af5f-257">**Type**</span></span>
- <span data-ttu-id="9af5f-258">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="9af5f-258">**24 hours**</span></span>
- <span data-ttu-id="9af5f-259">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="9af5f-259">**3 days**</span></span>
- <span data-ttu-id="9af5f-260">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="9af5f-260">**7 days**</span></span>
- <span data-ttu-id="9af5f-261">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="9af5f-261">**15 days**</span></span>
- <span data-ttu-id="9af5f-262">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="9af5f-262">**30 days**</span></span>

<span data-ttu-id="9af5f-263">Se você clicar **em Escolher uma categoria para obter** mais detalhes, você poderá selecionar entre os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9af5f-263">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="9af5f-264">**Email de phishing**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-264">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="9af5f-265">**Malware no email**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-265">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="9af5f-266">**Detecções de** spam: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-266">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="9af5f-267">**Spam bloqueado de borda:** essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-267">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="9af5f-268">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-268">**Export**:</span></span>

<span data-ttu-id="9af5f-269">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="9af5f-269">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="9af5f-270">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="9af5f-270">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="9af5f-271">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="9af5f-271">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9af5f-272">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-272">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Type view in the Mailflow status report](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="9af5f-274">Exibição de direção para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9af5f-274">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="9af5f-275">Se você clicar na guia **Direção,** os mesmos filtros padrão do modo de exibição **Tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-275">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="9af5f-276">O gráfico é organizado pelos **valores Direction.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-276">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="9af5f-277">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="9af5f-277">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="9af5f-278">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-278">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="9af5f-279">A tabela de dados contém as mesmas informações do modo **de exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-279">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="9af5f-280">A **opção Escolher uma categoria para obter** mais detalhes sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-280">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="9af5f-281">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-281">**Export**:</span></span>

<span data-ttu-id="9af5f-282">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="9af5f-282">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="9af5f-283">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="9af5f-283">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="9af5f-284">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="9af5f-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9af5f-285">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-285">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Exibição de direção no relatório de status de fluxo de emails](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="9af5f-287">Exibição de funil para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="9af5f-287">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="9af5f-288">A **exibição** Funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9af5f-288">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="9af5f-289">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-289">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="9af5f-290">Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-290">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9af5f-291">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="9af5f-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="9af5f-292">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-292">**Direction**:</span></span>

  - <span data-ttu-id="9af5f-293">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="9af5f-293">**Inbound**</span></span>
  - <span data-ttu-id="9af5f-294">**Saída**</span><span class="sxs-lookup"><span data-stu-id="9af5f-294">**Outbound**</span></span>
  - <span data-ttu-id="9af5f-295">**Intra-org**: esta contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de Entrada e Saída).</span><span class="sxs-lookup"><span data-stu-id="9af5f-295">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="9af5f-296">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-296">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="9af5f-297">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-297">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="9af5f-298">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="9af5f-298">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="9af5f-299">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="9af5f-299">**Total email**</span></span>
- <span data-ttu-id="9af5f-300">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="9af5f-300">**Email after edge protection**</span></span>
- <span data-ttu-id="9af5f-301">**Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="9af5f-301">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="9af5f-302">**Email após anti-phishing, reputação de URL, representação de marca, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="9af5f-302">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="9af5f-303">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="9af5f-303">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="9af5f-304">**Email após a representação de usuário e domínio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9af5f-304">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="9af5f-305">**Email após a detonação de arquivo e URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9af5f-305">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="9af5f-306">**Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique na URL)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-306">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="9af5f-307"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="9af5f-307"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="9af5f-308">Para exibir o email filtrado por EOP ou Defender Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="9af5f-308">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="9af5f-309">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="9af5f-309">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="9af5f-310">**Date**</span><span class="sxs-lookup"><span data-stu-id="9af5f-310">**Date**</span></span>
- <span data-ttu-id="9af5f-311">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="9af5f-311">**Total email**</span></span>
- <span data-ttu-id="9af5f-312">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="9af5f-312">**Edge protection**</span></span>
- <span data-ttu-id="9af5f-313">**Anti-malware, reputação de arquivo, bloco de tipo de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-313">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="9af5f-314">**Reputação do** arquivo : Mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9af5f-314">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="9af5f-315">**Bloco de tipo de** arquivo : Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-315">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="9af5f-316">**Anti-phish, reputação de URL, representação de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-316">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="9af5f-317">**Reputação da URL**: Mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9af5f-317">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="9af5f-318">**Representação de marca**: Mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.</span><span class="sxs-lookup"><span data-stu-id="9af5f-318">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="9af5f-319">**Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence ou a um domínio que o remetente da mensagem não possui.</span><span class="sxs-lookup"><span data-stu-id="9af5f-319">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="9af5f-320">**Anti-spam, filtragem de email em massa:**</span><span class="sxs-lookup"><span data-stu-id="9af5f-320">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="9af5f-321">**Filtragem em massa de** emails : Mensagens filtradas devido a uma tentativa de entregar emails em massa para seus destinatários.</span><span class="sxs-lookup"><span data-stu-id="9af5f-321">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="9af5f-322">**Representação de usuário e domínio (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-322">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="9af5f-323">**Representação do** usuário : Mensagens filtradas devido a uma tentativa de representar um usuário (remetente de mensagem) definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="9af5f-323">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="9af5f-324">**Representação de domínio**: Mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="9af5f-324">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="9af5f-325">**Detonação de arquivo e URL (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-325">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="9af5f-326">**Detonação de** arquivo : Mensagens filtradas por uma política Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="9af5f-326">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="9af5f-327">**Detonação de URL**: Mensagem filtrada por uma política Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="9af5f-327">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="9af5f-328">**Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: ZAP indica limpeza automática de zero hora.</span><span class="sxs-lookup"><span data-stu-id="9af5f-328">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="9af5f-329">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="9af5f-329">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="9af5f-330">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-330">**Export**:</span></span>

<span data-ttu-id="9af5f-331">Depois de clicar **em Exportar** **em Opções,** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9af5f-331">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="9af5f-332">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-332">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="9af5f-333">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-333">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="9af5f-334">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-334">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="9af5f-335">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="9af5f-335">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="9af5f-336">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="9af5f-336">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9af5f-337">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-337">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Exibição de funil no relatório de status de fluxo de emails](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="9af5f-339">Exibição técnica do relatório de status mailflow</span><span class="sxs-lookup"><span data-stu-id="9af5f-339">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="9af5f-340">O **modo de exibição** Tech é semelhante ao modo de exibição **Funil,** fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="9af5f-340">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="9af5f-341">No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="9af5f-341">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="9af5f-342">Se você clicar na **guia Modo de** Exibição de Tecnologia, por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-342">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="9af5f-343">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="9af5f-343">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="9af5f-344">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-344">**Direction**:</span></span>

  - <span data-ttu-id="9af5f-345">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="9af5f-345">**Inbound**</span></span>
  - <span data-ttu-id="9af5f-346">**Saída**</span><span class="sxs-lookup"><span data-stu-id="9af5f-346">**Outbound**</span></span>
  - <span data-ttu-id="9af5f-347">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="9af5f-347">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="9af5f-348">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de Entrada e Saída)</span><span class="sxs-lookup"><span data-stu-id="9af5f-348">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="9af5f-349">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-349">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="9af5f-350">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-350">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="9af5f-351">Este gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="9af5f-351">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="9af5f-352">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="9af5f-352">**Total email**</span></span>
- <span data-ttu-id="9af5f-353">**Permitir borda** e **Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="9af5f-353">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="9af5f-354">**Não malware,** **Cofre de anexos,** <sup>\*</sup> detecção de mecanismo **anti-malware** e **mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="9af5f-354">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="9af5f-355">**Não phish**, **falha de DMARC,** detecção de **representação,** detecção **de spoof** e **detecção de phishing**</span><span class="sxs-lookup"><span data-stu-id="9af5f-355">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="9af5f-356">**Nenhuma detecção com detonação de URL** e detecção **de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9af5f-356">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="9af5f-357">**Não spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-357">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="9af5f-358">**Email não mal-intencionado,** **Cofre de links** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="9af5f-358">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="9af5f-359"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9af5f-359"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="9af5f-360">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="9af5f-360">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="9af5f-361">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="9af5f-361">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="9af5f-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="9af5f-362">**Date**</span></span>
- <span data-ttu-id="9af5f-363">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="9af5f-363">**Total email**</span></span>
- <span data-ttu-id="9af5f-364">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="9af5f-364">**Edge filtered**</span></span>
- <span data-ttu-id="9af5f-365">**Mecanismo anti-malware, Cofre anexos, regra filtrada**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-365">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="9af5f-366">**Regra filtrada**: Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="9af5f-366">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="9af5f-367">**DMARC, representação, spoof, phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-367">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="9af5f-368">**DMARC**: Mensagens filtradas devido à falha da mensagem em sua verificação de autenticação DMARC.</span><span class="sxs-lookup"><span data-stu-id="9af5f-368">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="9af5f-369">**Detecção de detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="9af5f-369">**URL detonation detection**</span></span>
- <span data-ttu-id="9af5f-370">**Anti-spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="9af5f-370">**Anti-spam filtered**</span></span>
- <span data-ttu-id="9af5f-371">**ZAP removido**</span><span class="sxs-lookup"><span data-stu-id="9af5f-371">**ZAP removed**</span></span>
- <span data-ttu-id="9af5f-372">**Detecção por Cofre Links**</span><span class="sxs-lookup"><span data-stu-id="9af5f-372">**Detection by Safe Links**</span></span>

<span data-ttu-id="9af5f-373">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="9af5f-373">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="9af5f-374">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="9af5f-374">**Export**:</span></span>

<span data-ttu-id="9af5f-375">Ao clicar em **Exportar**, em **Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9af5f-375">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="9af5f-376">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-376">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="9af5f-377">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-377">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="9af5f-378">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-378">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="9af5f-379">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="9af5f-379">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="9af5f-380">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="9af5f-380">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="9af5f-381">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="9af5f-381">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![Exibição técnica no relatório de status do fluxo de mensagens](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="9af5f-383">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="9af5f-383">Sent and received email report</span></span>

<span data-ttu-id="9af5f-384">O **relatório de email** enviado e recebido é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bons".</span><span class="sxs-lookup"><span data-stu-id="9af5f-384">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="9af5f-385">A diferença entre este relatório e o relatório de status de [fluxo](#mailflow-status-report) de emails é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda.</span><span class="sxs-lookup"><span data-stu-id="9af5f-385">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="9af5f-386">**Observação**: é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-386">**Note**: It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="9af5f-387">A exibição agregada e a exibição detalhada do relatório permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="9af5f-387">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="9af5f-388">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Enviar e **receber emails**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-388">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="9af5f-389">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-389">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget de email enviado e recebido no painel Relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="9af5f-391">Exibição de relatório para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="9af5f-391">Report view for the Sent and received email report</span></span>

<span data-ttu-id="9af5f-392">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="9af5f-392">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9af5f-393">**Break down by: Type**: O gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9af5f-393">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="9af5f-394">**Total**</span><span class="sxs-lookup"><span data-stu-id="9af5f-394">**Total**</span></span>
  - <span data-ttu-id="9af5f-395">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-395">**Good mail**</span></span>
  - <span data-ttu-id="9af5f-396">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="9af5f-396">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="9af5f-397">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-397">**Spam detections**</span></span>
  - <span data-ttu-id="9af5f-398">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="9af5f-398">**Rule messages**</span></span>
  - <span data-ttu-id="9af5f-399">**Malware avançado** (Microsoft Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="9af5f-399">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="9af5f-400">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.</span><span class="sxs-lookup"><span data-stu-id="9af5f-400">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Type view in the Sent and received email report](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="9af5f-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span><span class="sxs-lookup"><span data-stu-id="9af5f-402">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="9af5f-403">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.</span><span class="sxs-lookup"><span data-stu-id="9af5f-403">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="9af5f-405">**Detalhar por** \> **Malware (anti-malware)**: essa seleção leva você ao relatório de [detecções de malware.](view-email-security-reports.md#malware-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-405">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections report](view-email-security-reports.md#malware-detections-report).</span></span>

- <span data-ttu-id="9af5f-406">**Detalhar por** \> **Detecções de spam)**: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="9af5f-406">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="9af5f-407">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-407">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9af5f-408">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="9af5f-408">**Start date** and **End date**</span></span>
- <span data-ttu-id="9af5f-409">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="9af5f-409">Direction values</span></span>
- <span data-ttu-id="9af5f-410">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="9af5f-410">Type values</span></span>

<span data-ttu-id="9af5f-411">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-411">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="9af5f-412">Exibição de tabela de detalhes para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="9af5f-412">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="9af5f-413">Se você clicar **em Exibir tabela de** detalhes na tabela Break down **by: Direction** or Break down **by: Direction** view, the following information is shown:</span><span class="sxs-lookup"><span data-stu-id="9af5f-413">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="9af5f-414">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-414">**Date (UTC)**</span></span>
- <span data-ttu-id="9af5f-415">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9af5f-415">**Type**</span></span>
- <span data-ttu-id="9af5f-416">**Direção**</span><span class="sxs-lookup"><span data-stu-id="9af5f-416">**Direction**</span></span>
- <span data-ttu-id="9af5f-417">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="9af5f-417">**Message count**</span></span>

<span data-ttu-id="9af5f-418">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="9af5f-418">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="9af5f-419">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="9af5f-419">**Start date** and **End date**</span></span>
- <span data-ttu-id="9af5f-420">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="9af5f-420">Direction values</span></span>
- <span data-ttu-id="9af5f-421">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="9af5f-421">Type values</span></span>

<span data-ttu-id="9af5f-422">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-422">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="9af5f-423">Relatório de destinatários e destinatários principais</span><span class="sxs-lookup"><span data-stu-id="9af5f-423">Top senders and recipients report</span></span>

<span data-ttu-id="9af5f-424">O **relatório Principais destinatários e destinatários** é um gráfico de pizza mostrando seus principais destinatários e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="9af5f-424">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="9af5f-425">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Principais destinatários e destinatários.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-425">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="9af5f-426">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="9af5f-426">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Principais destinatários e destinatários do widget no painel Relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="9af5f-428">Exibição de relatório para os principais destinatários e destinatários</span><span class="sxs-lookup"><span data-stu-id="9af5f-428">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="9af5f-429">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="9af5f-429">The following charts are available in the report view:</span></span>

- <span data-ttu-id="9af5f-430">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-430">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="9af5f-431">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-431">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="9af5f-432">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-432">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="9af5f-433">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="9af5f-433">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="9af5f-434">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-434">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="9af5f-435">A composição do gráfico de pizza muda com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="9af5f-435">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="9af5f-436">Ao passar o mouse sobre uma cunha no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="9af5f-436">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="9af5f-437">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-437">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no relatório no relatório Principais destinatários e destinatários](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="9af5f-439">Exibição de tabela de detalhes para o relatório de destinatários e destinatários principais</span><span class="sxs-lookup"><span data-stu-id="9af5f-439">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="9af5f-440">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="9af5f-440">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="9af5f-441">**Mostrar dados para \> os principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-441">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="9af5f-442">**Principais envios de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-442">**Top mail senders**</span></span>
  - <span data-ttu-id="9af5f-443">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-443">**Count**</span></span>

- <span data-ttu-id="9af5f-444">**Mostrar dados para \> os principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-444">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="9af5f-445">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="9af5f-445">**Top mail recipients**</span></span>
  - <span data-ttu-id="9af5f-446">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-446">**Count**</span></span>

- <span data-ttu-id="9af5f-447">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-447">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="9af5f-448">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="9af5f-448">**Top spam recipients**</span></span>
  - <span data-ttu-id="9af5f-449">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-449">**Count**</span></span>

- <span data-ttu-id="9af5f-450">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="9af5f-450">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="9af5f-451">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="9af5f-451">**Top malware recipients**</span></span>
  - <span data-ttu-id="9af5f-452">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-452">**Count**</span></span>

- <span data-ttu-id="9af5f-453">**Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-453">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="9af5f-454">**Principais destinatários de malware (Defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="9af5f-454">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="9af5f-455">**Count**</span><span class="sxs-lookup"><span data-stu-id="9af5f-455">**Count**</span></span>

<span data-ttu-id="9af5f-456">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="9af5f-456">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="9af5f-457">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="9af5f-457">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="9af5f-458">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="9af5f-458">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="9af5f-459">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="9af5f-459">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="9af5f-460">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="9af5f-460">**Organization Management**</span></span>
- <span data-ttu-id="9af5f-461">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="9af5f-461">**Security Administrator**</span></span>
- <span data-ttu-id="9af5f-462">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="9af5f-462">**Security Reader**</span></span>
- <span data-ttu-id="9af5f-463">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="9af5f-463">**Global Reader**</span></span>

<span data-ttu-id="9af5f-464">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="9af5f-464">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

> [!NOTE]
> <span data-ttu-id="9af5f-465">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9af5f-465">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="9af5f-466">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9af5f-466">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9af5f-467">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9af5f-467">Related topics</span></span>

[<span data-ttu-id="9af5f-468">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="9af5f-468">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="9af5f-469">Insights de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="9af5f-469">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="9af5f-470">Exibir relatórios de segurança de email no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="9af5f-470">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="9af5f-471">Exibir relatórios do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9af5f-471">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)
