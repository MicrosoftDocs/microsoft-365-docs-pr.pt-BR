---
title: Exibir relatórios de fluxo de emails no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Saiba como localizar e usar relatórios de segurança de fluxo de emails para sua organização. Os relatórios de fluxo de emails estão disponíveis no centro de conformidade e segurança &.
ms.custom: ''
ms.openlocfilehash: e891d9373b169dc01cfd89f114e31b23e1bd8480
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434174"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a><span data-ttu-id="450ba-104">Exibir relatórios de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="450ba-104">View mail flow reports in the Security & Compliance Center</span></span>

<span data-ttu-id="450ba-105">Além das informações sobre o [fluxo de emails](mail-flow-insights-v2.md) que estão disponíveis no centro de conformidade de & de segurança, vários relatórios de fluxo de emails estão disponíveis para ajudá-lo a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="450ba-105">In addition to the [Mail flow insights](mail-flow-insights-v2.md) that are available in the Security & Compliance Center, a variety of mail flow reports are also available to help you monitor your Microsoft 365 organization.</span></span> <span data-ttu-id="450ba-106">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de conformidade do & de segurança em <https://office.protection.com> , no **Reports** \> **painel**relatórios.</span><span class="sxs-lookup"><span data-stu-id="450ba-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center at <https://office.protection.com> by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="450ba-107">Para ir diretamente para o painel relatórios, abra <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="450ba-107">To go directly to the reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="450ba-109">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="450ba-109">Connector report</span></span>

<span data-ttu-id="450ba-110">O **relatório do conector** mostra a atividade de fluxo de emails nos [conectores de entrada e saída](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) que estão configurados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="450ba-110">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="450ba-111">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório do conector**.</span><span class="sxs-lookup"><span data-stu-id="450ba-111">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="450ba-112">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="450ba-112">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget relatório do conector no painel relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="450ba-114">Exibição de relatório para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="450ba-114">Report view for the Connector report</span></span>

<span data-ttu-id="450ba-115">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="450ba-115">The following charts are available in report view:</span></span>

- <span data-ttu-id="450ba-116">**Exibir dados por: fluxo de email**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="450ba-116">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="450ba-117">**Total**</span><span class="sxs-lookup"><span data-stu-id="450ba-117">**Total**</span></span>
  - <span data-ttu-id="450ba-118">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-118">**From the internet without a connector**</span></span>
  - <span data-ttu-id="450ba-119">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-119">**To the internet without a connector**</span></span>
  - <span data-ttu-id="450ba-120">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="450ba-120">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="450ba-121">Para isolar os dados no gráfico, use o recurso **Mostrar dados do** controle para selecionar uma destas opções ou **todo o fluxo de emails**.</span><span class="sxs-lookup"><span data-stu-id="450ba-121">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório do conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="450ba-123">**Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão do protocolo TLS para o fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="450ba-123">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="450ba-124">Para isolar os dados no gráfico, use a opção **Mostrar dados do** controle para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="450ba-124">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="450ba-125">**Todo o fluxo de email**</span><span class="sxs-lookup"><span data-stu-id="450ba-125">**All mail flow**</span></span>
  - <span data-ttu-id="450ba-126">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-126">**From the internet without a connector**</span></span>
  - <span data-ttu-id="450ba-127">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-127">**To the internet without a connector**</span></span>
  - <span data-ttu-id="450ba-128">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="450ba-128">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso de TLS no relatório do conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="450ba-130">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-130">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="450ba-131">Exibição da tabela de detalhes para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="450ba-131">Details table view for the Connector report</span></span>

<span data-ttu-id="450ba-132">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="450ba-132">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="450ba-133">**Date**</span><span class="sxs-lookup"><span data-stu-id="450ba-133">**Date**</span></span>
- <span data-ttu-id="450ba-134">**Direção e nome do conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-134">**Connector direction and name**</span></span>
- <span data-ttu-id="450ba-135">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="450ba-135">**Connector type**</span></span>
- <span data-ttu-id="450ba-136">**TLS forçado?**: o valor **true** ou **false**.</span><span class="sxs-lookup"><span data-stu-id="450ba-136">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="450ba-137">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="450ba-137">**No TLS** (percentage)</span></span>
- <span data-ttu-id="450ba-138">**TLS 1,0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="450ba-138">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="450ba-139">**TLS 1,1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="450ba-139">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="450ba-140">**TLS 1,2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="450ba-140">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="450ba-141">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="450ba-141">**Volume**: The number of messages.</span></span>

<span data-ttu-id="450ba-142">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-142">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="450ba-143">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-143">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="450ba-144">Relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="450ba-144">Exchange transport rule report</span></span>

<span data-ttu-id="450ba-145">O **relatório** de regras de transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e de saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="450ba-145">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="450ba-146">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione regra de **transporte do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="450ba-146">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="450ba-147">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="450ba-147">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget regra de transporte do Exchange no painel relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="450ba-149">Exibição de relatório para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="450ba-149">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="450ba-150">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="450ba-150">The following charts are available in report view:</span></span>

- <span data-ttu-id="450ba-151">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas por regras de transporte.</span><span class="sxs-lookup"><span data-stu-id="450ba-151">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="450ba-152">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: severidade**: Este gráfico mostra o número de **alta gravidade** e **severidade média**e mensagens de **baixa gravidade** .</span><span class="sxs-lookup"><span data-stu-id="450ba-152">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="450ba-153">Você define o nível de severidade como uma ação na regra (**auditar esta regra com nível de severidade** ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="450ba-153">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="450ba-154">Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="450ba-154">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="450ba-155">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas pelas regras de transporte de prevenção de perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="450ba-155">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="450ba-156">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="450ba-156">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="450ba-157">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="450ba-157">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="450ba-158">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="450ba-158">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="450ba-159">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="450ba-159">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="450ba-160">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: este modo de exibição mostra o número de **alta** gravidade e **severidade média**e mensagens de **baixa gravidade** que foram afetadas pelas regras de transporte DLP.</span><span class="sxs-lookup"><span data-stu-id="450ba-160">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="450ba-161">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="450ba-161">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="450ba-162">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="450ba-162">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="450ba-163">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="450ba-163">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="450ba-164">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="450ba-164">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="450ba-165">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="450ba-165">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="450ba-166">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="450ba-166">**Start date** and **End date**</span></span>
- <span data-ttu-id="450ba-167">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="450ba-167">Direction values</span></span>
- <span data-ttu-id="450ba-168">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="450ba-168">Severity values</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="450ba-170">Exibição da tabela de detalhes para o relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="450ba-170">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="450ba-171">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="450ba-171">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="450ba-172">**Exibir dados por: regras de transporte do Exchange**:</span><span class="sxs-lookup"><span data-stu-id="450ba-172">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="450ba-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="450ba-173">**Date**</span></span>
  - <span data-ttu-id="450ba-174">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="450ba-174">**Transport rule**</span></span>
  - <span data-ttu-id="450ba-175">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="450ba-175">**Subject**</span></span>
  - <span data-ttu-id="450ba-176">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="450ba-176">**Sender address**</span></span>
  - <span data-ttu-id="450ba-177">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="450ba-177">**Recipient address**</span></span>
  - <span data-ttu-id="450ba-178">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="450ba-178">**Severity**</span></span>
  - <span data-ttu-id="450ba-179">**Direção**</span><span class="sxs-lookup"><span data-stu-id="450ba-179">**Direction**</span></span>

- <span data-ttu-id="450ba-180">**Exibir dados por: regras de transporte do Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="450ba-180">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="450ba-181">**Date**</span><span class="sxs-lookup"><span data-stu-id="450ba-181">**Date**</span></span>
  - <span data-ttu-id="450ba-182">**Política de DLP**</span><span class="sxs-lookup"><span data-stu-id="450ba-182">**DLP policy**</span></span>
  - <span data-ttu-id="450ba-183">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="450ba-183">**Transport rule**</span></span>
  - <span data-ttu-id="450ba-184">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="450ba-184">**Subject**</span></span>
  - <span data-ttu-id="450ba-185">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="450ba-185">**Sender address**</span></span>
  - <span data-ttu-id="450ba-186">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="450ba-186">**Recipient address**</span></span>
  - <span data-ttu-id="450ba-187">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="450ba-187">**Severity**</span></span>
  - <span data-ttu-id="450ba-188">**Direção**</span><span class="sxs-lookup"><span data-stu-id="450ba-188">**Direction**</span></span>

<span data-ttu-id="450ba-189">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="450ba-189">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="450ba-190">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="450ba-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="450ba-191">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="450ba-191">Direction values</span></span>
- <span data-ttu-id="450ba-192">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="450ba-192">Severity values</span></span>

<span data-ttu-id="450ba-193">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-193">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="450ba-194">Encaminhando relatório</span><span class="sxs-lookup"><span data-stu-id="450ba-194">Forwarding report</span></span>

<span data-ttu-id="450ba-195">O **relatório de encaminhamento** mostra as mensagens automaticamente encaminhadas de sua organização para domínios externos de caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="450ba-195">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="450ba-196">As mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="450ba-196">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="450ba-197">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório de encaminhamento**.</span><span class="sxs-lookup"><span data-stu-id="450ba-197">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="450ba-198">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="450ba-198">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de encaminhamento de relatório no painel relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="450ba-200">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="450ba-200">Report view for the Forwarding report</span></span>

<span data-ttu-id="450ba-201">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="450ba-201">The following charts are available in the report view:</span></span>

- <span data-ttu-id="450ba-202">**Mostrar dados para: métodos de encaminhamento**: os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="450ba-202">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="450ba-203">**Regra de transporte**: também conhecida como [regras de fluxo de emails](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="450ba-203">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="450ba-204">**Regra de caixa de correio**: também conhecida como [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="450ba-204">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="450ba-206">**Mostrar dados para: encaminhar domínios**: este modo de exibição mostra os domínios de destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="450ba-206">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="450ba-208">**Mostrar dados para: encaminhadores**: os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="450ba-208">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="450ba-209">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="450ba-209">**Transport rule**</span></span>
  - <span data-ttu-id="450ba-210">A caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="450ba-210">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="450ba-212">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-212">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="450ba-213">Exibição da tabela de detalhes para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="450ba-213">Details table view for the Forwarding report</span></span>

<span data-ttu-id="450ba-214">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="450ba-214">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="450ba-215">**Encaminhadores**: a **regra de transporte** de valor ou a caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="450ba-215">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="450ba-216">**Tipo de encaminhamento**: a **regra de caixa de correio** de valor ou a **regra de transporte**.</span><span class="sxs-lookup"><span data-stu-id="450ba-216">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="450ba-217">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="450ba-217">**Recipient name**</span></span>
- <span data-ttu-id="450ba-218">**Domínio do destinatário**</span><span class="sxs-lookup"><span data-stu-id="450ba-218">**Recipient domain**</span></span>
- <span data-ttu-id="450ba-219">**Detalhes**: Este é o valor de GUID da regra de fluxo de emails ou o valor RuleIdentity da regra de caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="450ba-219">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="450ba-220">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-220">**Count**</span></span>
- <span data-ttu-id="450ba-221">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="450ba-221">**First forward date**</span></span>

<span data-ttu-id="450ba-222">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-222">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="450ba-223">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-223">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="450ba-224">Relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="450ba-224">Mailflow status report</span></span>

<span data-ttu-id="450ba-225">O **relatório de status do fluxo** é semelhante ao [relatório de email enviado e recebido](#sent-and-received-email-report), com informações adicionais sobre o email permitido ou bloqueado na borda.</span><span class="sxs-lookup"><span data-stu-id="450ba-225">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="450ba-226">Este é o único relatório que contém as informações de proteção de borda e mostra o quanto o email é bloqueado antes de ser permitido ao serviço para avaliação pelo Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="450ba-226">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="450ba-227">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **fluxo relatório de status**.</span><span class="sxs-lookup"><span data-stu-id="450ba-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="450ba-228">Para ir diretamente para o **relatório de status de fluxo de emails**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="450ba-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget relatório de status do fluxo no painel relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="450ba-230">Modo de exibição de tipo para o relatório de status fluxo</span><span class="sxs-lookup"><span data-stu-id="450ba-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="450ba-231">Quando você abre o relatório, a guia **tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="450ba-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="450ba-232">Por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="450ba-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="450ba-233">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="450ba-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="450ba-234">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="450ba-234">**Direction**:</span></span>

  - <span data-ttu-id="450ba-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="450ba-235">**Inbound**</span></span>
  - <span data-ttu-id="450ba-236">**Saída**</span><span class="sxs-lookup"><span data-stu-id="450ba-236">**Outbound**</span></span>
  - <span data-ttu-id="450ba-237">**Intra-org** (contado separadamente de **entrada** e **saída**)</span><span class="sxs-lookup"><span data-stu-id="450ba-237">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="450ba-238">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="450ba-238">**Type**:</span></span>

  - <span data-ttu-id="450ba-239">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="450ba-239">**Good mail**</span></span>
  - <span data-ttu-id="450ba-240">**Malware**</span><span class="sxs-lookup"><span data-stu-id="450ba-240">**Malware**</span></span>
  - <span data-ttu-id="450ba-241">**Spam**</span><span class="sxs-lookup"><span data-stu-id="450ba-241">**Spam**</span></span>
  - <span data-ttu-id="450ba-242">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="450ba-242">**Edge protection**</span></span>
  - <span data-ttu-id="450ba-243">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="450ba-243">**Rule messages**</span></span>
  - <span data-ttu-id="450ba-244">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="450ba-244">**Phishing email**</span></span>

<span data-ttu-id="450ba-245">O gráfico é organizado pelos valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="450ba-245">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="450ba-246">Você pode alterar esses filtros clicando em **filtro** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="450ba-246">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="450ba-247">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="450ba-247">The data table contains the following information:</span></span>

- <span data-ttu-id="450ba-248">**Direção**</span><span class="sxs-lookup"><span data-stu-id="450ba-248">**Direction**</span></span>
- <span data-ttu-id="450ba-249">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="450ba-249">**Type**</span></span>
- <span data-ttu-id="450ba-250">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="450ba-250">**24 hours**</span></span>
- <span data-ttu-id="450ba-251">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="450ba-251">**3 days**</span></span>
- <span data-ttu-id="450ba-252">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="450ba-252">**7 days**</span></span>
- <span data-ttu-id="450ba-253">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="450ba-253">**15 days**</span></span>
- <span data-ttu-id="450ba-254">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="450ba-254">**30 days**</span></span>

<span data-ttu-id="450ba-255">Se você clicar em **escolher uma categoria para obter mais detalhes**, poderá selecionar os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="450ba-255">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="450ba-256">**Email de phishing**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-256">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="450ba-257">**Malware em email**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-257">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="450ba-258">**Detecções de spam**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-258">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="450ba-259">**Bloqueio de spam bloqueado**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-259">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="450ba-260">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="450ba-260">**Export**:</span></span>

<span data-ttu-id="450ba-261">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="450ba-261">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="450ba-262">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="450ba-262">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="450ba-263">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="450ba-263">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="450ba-264">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="450ba-264">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="450ba-265">Modo de exibição de tipo no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="450ba-265">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="450ba-266">Exibição de direção para o relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="450ba-266">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="450ba-267">Se você clicar na guia **direção** , os mesmos filtros padrão do modo de exibição de **tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="450ba-267">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="450ba-268">O gráfico é organizado por valores de **direção** .</span><span class="sxs-lookup"><span data-stu-id="450ba-268">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="450ba-269">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="450ba-269">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="450ba-270">Os mesmos filtros do **tipo** de exibição são usados.</span><span class="sxs-lookup"><span data-stu-id="450ba-270">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="450ba-271">A tabela de dados contém as mesmas informações do **tipo** de exibição.</span><span class="sxs-lookup"><span data-stu-id="450ba-271">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="450ba-272">A **escolha uma categoria para obter detalhes sobre** as seleções e o comportamento disponíveis são os mesmos que o modo de exibição de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="450ba-272">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="450ba-273">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="450ba-273">**Export**:</span></span>

<span data-ttu-id="450ba-274">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="450ba-274">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="450ba-275">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="450ba-275">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="450ba-276">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="450ba-276">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="450ba-277">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="450ba-277">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="450ba-278">Exibição de direção no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="450ba-278">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="450ba-279">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="450ba-279">Sent and received email report</span></span>

<span data-ttu-id="450ba-280">O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom".</span><span class="sxs-lookup"><span data-stu-id="450ba-280">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="450ba-281">A diferença entre este relatório e o [relatório de status do fluxo](#mailflow-status-report) é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda.</span><span class="sxs-lookup"><span data-stu-id="450ba-281">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="450ba-282">O modo de exibição de agregação e o modo de exibição de detalhes do relatório permitem que 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="450ba-282">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="450ba-283">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **email enviado e recebido**.</span><span class="sxs-lookup"><span data-stu-id="450ba-283">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="450ba-284">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="450ba-284">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget email enviado e recebido no painel relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="450ba-286">Exibição de relatório para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="450ba-286">Report view for the Sent and received email report</span></span>

<span data-ttu-id="450ba-287">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="450ba-287">The following charts are available in the report view:</span></span>

- <span data-ttu-id="450ba-288">**Divisão por: digite**: o gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="450ba-288">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="450ba-289">**Total**</span><span class="sxs-lookup"><span data-stu-id="450ba-289">**Total**</span></span>
  - <span data-ttu-id="450ba-290">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="450ba-290">**Good mail**</span></span>
  - <span data-ttu-id="450ba-291">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="450ba-291">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="450ba-292">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="450ba-292">**Spam detections**</span></span>
  - <span data-ttu-id="450ba-293">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="450ba-293">**Rule messages**</span></span>
  - <span data-ttu-id="450ba-294">**Malware avançado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="450ba-294">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="450ba-295">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="450ba-295">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de tipo no relatório de email enviado e recebido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="450ba-297">**Divisão por: direção**: o gráfico mostra os dados **total**, de **entrada**e de **saída** .</span><span class="sxs-lookup"><span data-stu-id="450ba-297">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="450ba-298">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="450ba-298">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="450ba-300">**Aprofundar por** \> **Malware (Antimalware)**: esta seleção leva você para as [detecções de malware no relatório de email](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-300">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="450ba-301">**Aprofundar por** \> **Detecções de spam)**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="450ba-301">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="450ba-302">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="450ba-302">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="450ba-303">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="450ba-303">**Start date** and **End date**</span></span>
- <span data-ttu-id="450ba-304">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="450ba-304">Direction values</span></span>
- <span data-ttu-id="450ba-305">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="450ba-305">Type values</span></span>

<span data-ttu-id="450ba-306">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-306">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="450ba-307">Exibição da tabela de detalhes para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="450ba-307">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="450ba-308">Se você clicar em **Exibir tabela de detalhes** na tela **dividir por: direção** ou **dividir em: direção** , as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="450ba-308">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="450ba-309">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="450ba-309">**Date (UTC)**</span></span>
- <span data-ttu-id="450ba-310">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="450ba-310">**Type**</span></span>
- <span data-ttu-id="450ba-311">**Direção**</span><span class="sxs-lookup"><span data-stu-id="450ba-311">**Direction**</span></span>
- <span data-ttu-id="450ba-312">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="450ba-312">**Message count**</span></span>

<span data-ttu-id="450ba-313">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="450ba-313">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="450ba-314">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="450ba-314">**Start date** and **End date**</span></span>
- <span data-ttu-id="450ba-315">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="450ba-315">Direction values</span></span>
- <span data-ttu-id="450ba-316">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="450ba-316">Type values</span></span>

<span data-ttu-id="450ba-317">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-317">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="450ba-318">Relatório de principais remetentes e destinatários</span><span class="sxs-lookup"><span data-stu-id="450ba-318">Top senders and recipients report</span></span>

<span data-ttu-id="450ba-319">O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="450ba-319">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="450ba-320">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **os principais remetentes e destinatários**.</span><span class="sxs-lookup"><span data-stu-id="450ba-320">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="450ba-321">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="450ba-321">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget principais remetentes e destinatários no painel relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="450ba-323">Exibição de relatório para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="450ba-323">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="450ba-324">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="450ba-324">The following charts are available in the report view:</span></span>

- <span data-ttu-id="450ba-325">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="450ba-325">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="450ba-326">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="450ba-326">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="450ba-327">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="450ba-327">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="450ba-328">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="450ba-328">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="450ba-329">**Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="450ba-329">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="450ba-330">A composição do gráfico de pizza é alterada com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="450ba-330">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="450ba-331">Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="450ba-331">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="450ba-332">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-332">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no modo de exibição de relatório no relatório de remetentes e destinatários principais](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="450ba-334">Exibição da tabela de detalhes para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="450ba-334">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="450ba-335">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="450ba-335">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="450ba-336">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="450ba-336">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="450ba-337">**Principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="450ba-337">**Top mail senders**</span></span>
  - <span data-ttu-id="450ba-338">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-338">**Count**</span></span>

- <span data-ttu-id="450ba-339">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="450ba-339">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="450ba-340">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="450ba-340">**Top mail recipients**</span></span>
  - <span data-ttu-id="450ba-341">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-341">**Count**</span></span>

- <span data-ttu-id="450ba-342">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="450ba-342">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="450ba-343">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="450ba-343">**Top spam recipients**</span></span>
  - <span data-ttu-id="450ba-344">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-344">**Count**</span></span>

- <span data-ttu-id="450ba-345">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="450ba-345">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="450ba-346">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="450ba-346">**Top malware recipients**</span></span>
  - <span data-ttu-id="450ba-347">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-347">**Count**</span></span>

- <span data-ttu-id="450ba-348">**Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="450ba-348">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="450ba-349">**Principais destinatários de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="450ba-349">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="450ba-350">**Count**</span><span class="sxs-lookup"><span data-stu-id="450ba-350">**Count**</span></span>

<span data-ttu-id="450ba-351">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="450ba-351">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="450ba-352">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="450ba-352">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="450ba-353">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="450ba-353">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="450ba-354">Para exibir e usar os relatórios, você precisa ser membro do grupo de função especificado no centro de conformidade e segurança & **e** no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="450ba-354">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="450ba-355">No centro de conformidade & segurança, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="450ba-355">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="450ba-356">-Gerenciamento de organização</span><span class="sxs-lookup"><span data-stu-id="450ba-356">-Organization Management</span></span>

  <span data-ttu-id="450ba-357">– Administrador de segurança (você também pode fazer isso no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) -leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="450ba-357">-Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="450ba-358">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="450ba-358">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="450ba-359">No Exchange Online, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="450ba-359">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="450ba-360">-Gerenciamento de organização</span><span class="sxs-lookup"><span data-stu-id="450ba-360">-Organization Management</span></span>

  <span data-ttu-id="450ba-361">– Gerenciamento de organização somente para exibição</span><span class="sxs-lookup"><span data-stu-id="450ba-361">-View-only Organization Management</span></span>

  <span data-ttu-id="450ba-362">-Somente destinatários de exibição</span><span class="sxs-lookup"><span data-stu-id="450ba-362">-View-Only Recipients</span></span>

  <span data-ttu-id="450ba-363">-Gerenciamento de conformidade</span><span class="sxs-lookup"><span data-stu-id="450ba-363">-Compliance Management</span></span>

<span data-ttu-id="450ba-364">Para obter mais informações, consulte [permissões no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gerenciar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="450ba-364">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="450ba-365">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="450ba-365">Related topics</span></span>

[<span data-ttu-id="450ba-366">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="450ba-366">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="450ba-367">Exibir relatórios de segurança de email no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="450ba-367">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)
