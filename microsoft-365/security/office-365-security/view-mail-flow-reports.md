---
title: Exibir relatórios de fluxo de emails no painel relatórios
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
description: Os administradores podem saber mais sobre os relatórios de fluxo de emails disponíveis no painel de relatórios no centro de conformidade do & de segurança.
ms.custom: ''
ms.openlocfilehash: 69b2c3383862860b4616d95c2a6a1bb3a525d842
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578013"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="fc639-103">Exibir relatórios de fluxo de emails no painel de relatórios no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="fc639-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

<span data-ttu-id="fc639-104">Além dos relatórios de fluxo de emails disponíveis no painel de [fluxo de emails](mail-flow-insights-v2.md) no centro de conformidade com segurança &, vários relatórios de fluxo de email adicionais estão disponíveis no painel de relatórios para ajudá-lo a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fc639-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="fc639-105">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de [conformidade & de segurança](https://office.protection.com) acessando **Reports** o \> **painel**relatórios.</span><span class="sxs-lookup"><span data-stu-id="fc639-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="fc639-106">Para ir diretamente para o painel relatórios, abra <https://office.protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="fc639-106">To go directly to the Reports dashboard, open <https://office.protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="fc639-108">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="fc639-108">Connector report</span></span>

<span data-ttu-id="fc639-109">O **relatório do conector** mostra a atividade de fluxo de emails nos [conectores de entrada e saída](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) que estão configurados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fc639-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="fc639-110">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório do conector**.</span><span class="sxs-lookup"><span data-stu-id="fc639-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="fc639-111">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="fc639-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget relatório do conector no painel relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="fc639-113">Exibição de relatório para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="fc639-113">Report view for the Connector report</span></span>

<span data-ttu-id="fc639-114">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="fc639-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="fc639-115">**Exibir dados por: fluxo de email**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="fc639-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="fc639-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="fc639-116">**Total**</span></span>
  - <span data-ttu-id="fc639-117">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fc639-118">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fc639-119">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="fc639-119">A specific connector that you've configured.</span></span>
  
  <span data-ttu-id="fc639-120">Para isolar os dados no gráfico, use o recurso **Mostrar dados do** controle para selecionar uma destas opções ou **todo o fluxo de emails**.</span><span class="sxs-lookup"><span data-stu-id="fc639-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório do conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="fc639-122">**Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão do protocolo TLS para o fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="fc639-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="fc639-123">Para isolar os dados no gráfico, use a opção **Mostrar dados do** controle para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fc639-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="fc639-124">**Todo o fluxo de email**</span><span class="sxs-lookup"><span data-stu-id="fc639-124">**All mail flow**</span></span>
  - <span data-ttu-id="fc639-125">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="fc639-126">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="fc639-127">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="fc639-127">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso de TLS no relatório do conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="fc639-129">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="fc639-130">Exibição da tabela de detalhes para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="fc639-130">Details table view for the Connector report</span></span>

<span data-ttu-id="fc639-131">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="fc639-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fc639-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="fc639-132">**Date**</span></span>
- <span data-ttu-id="fc639-133">**Direção e nome do conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-133">**Connector direction and name**</span></span>
- <span data-ttu-id="fc639-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="fc639-134">**Connector type**</span></span>
- <span data-ttu-id="fc639-135">**TLS forçado?**: o valor **true** ou **false**.</span><span class="sxs-lookup"><span data-stu-id="fc639-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="fc639-136">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="fc639-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="fc639-137">**TLS 1,0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="fc639-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="fc639-138">**TLS 1,1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="fc639-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="fc639-139">**TLS 1,2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="fc639-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="fc639-140">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="fc639-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="fc639-141">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc639-142">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="fc639-143">Relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="fc639-143">Exchange transport rule report</span></span>

<span data-ttu-id="fc639-144">O **relatório** de regras de transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e de saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="fc639-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="fc639-145">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione regra de **transporte do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="fc639-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="fc639-146">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="fc639-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget regra de transporte do Exchange no painel relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fc639-148">Exibição de relatório para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="fc639-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="fc639-149">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="fc639-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="fc639-150">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas por regras de transporte.</span><span class="sxs-lookup"><span data-stu-id="fc639-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="fc639-151">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: severidade**: Este gráfico mostra o número de **alta gravidade** e **severidade média**e mensagens de **baixa gravidade** .</span><span class="sxs-lookup"><span data-stu-id="fc639-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="fc639-152">Você define o nível de severidade como uma ação na regra (**auditar esta regra com nível de severidade** ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="fc639-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="fc639-153">Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="fc639-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="fc639-154">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas pelas regras de transporte de prevenção de perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="fc639-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="fc639-155">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fc639-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fc639-156">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="fc639-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fc639-157">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="fc639-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fc639-158">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="fc639-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="fc639-159">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: este modo de exibição mostra o número de **alta** gravidade e **severidade média**e mensagens de **baixa gravidade** que foram afetadas pelas regras de transporte DLP.</span><span class="sxs-lookup"><span data-stu-id="fc639-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="fc639-160">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="fc639-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="fc639-161">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="fc639-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="fc639-162">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="fc639-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="fc639-163">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="fc639-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="fc639-164">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="fc639-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="fc639-165">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="fc639-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="fc639-166">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="fc639-166">Direction values</span></span>
- <span data-ttu-id="fc639-167">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="fc639-167">Severity values</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="fc639-169">Exibição da tabela de detalhes para o relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="fc639-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="fc639-170">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="fc639-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fc639-171">**Exibir dados por: regras de transporte do Exchange**:</span><span class="sxs-lookup"><span data-stu-id="fc639-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="fc639-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="fc639-172">**Date**</span></span>
  - <span data-ttu-id="fc639-173">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="fc639-173">**Transport rule**</span></span>
  - <span data-ttu-id="fc639-174">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="fc639-174">**Subject**</span></span>
  - <span data-ttu-id="fc639-175">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="fc639-175">**Sender address**</span></span>
  - <span data-ttu-id="fc639-176">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="fc639-176">**Recipient address**</span></span>
  - <span data-ttu-id="fc639-177">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="fc639-177">**Severity**</span></span>
  - <span data-ttu-id="fc639-178">**Direção**</span><span class="sxs-lookup"><span data-stu-id="fc639-178">**Direction**</span></span>

- <span data-ttu-id="fc639-179">**Exibir dados por: regras de transporte do Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="fc639-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="fc639-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="fc639-180">**Date**</span></span>
  - <span data-ttu-id="fc639-181">**Política de DLP**</span><span class="sxs-lookup"><span data-stu-id="fc639-181">**DLP policy**</span></span>
  - <span data-ttu-id="fc639-182">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="fc639-182">**Transport rule**</span></span>
  - <span data-ttu-id="fc639-183">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="fc639-183">**Subject**</span></span>
  - <span data-ttu-id="fc639-184">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="fc639-184">**Sender address**</span></span>
  - <span data-ttu-id="fc639-185">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="fc639-185">**Recipient address**</span></span>
  - <span data-ttu-id="fc639-186">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="fc639-186">**Severity**</span></span>
  - <span data-ttu-id="fc639-187">**Direção**</span><span class="sxs-lookup"><span data-stu-id="fc639-187">**Direction**</span></span>

<span data-ttu-id="fc639-188">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="fc639-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fc639-189">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="fc639-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="fc639-190">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="fc639-190">Direction values</span></span>
- <span data-ttu-id="fc639-191">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="fc639-191">Severity values</span></span>

<span data-ttu-id="fc639-192">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="fc639-193">Encaminhando relatório</span><span class="sxs-lookup"><span data-stu-id="fc639-193">Forwarding report</span></span>

<span data-ttu-id="fc639-194">O **relatório de encaminhamento** mostra as mensagens automaticamente encaminhadas de sua organização para domínios externos de caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fc639-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="fc639-195">As mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="fc639-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="fc639-196">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório de encaminhamento**.</span><span class="sxs-lookup"><span data-stu-id="fc639-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="fc639-197">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="fc639-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de encaminhamento de relatório no painel relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="fc639-199">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="fc639-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="fc639-200">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="fc639-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fc639-201">**Mostrar dados para: métodos de encaminhamento**: os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="fc639-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="fc639-202">**Regra de transporte**: também conhecida como [regras de fluxo de emails](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="fc639-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="fc639-203">**Regra de caixa de correio**: também conhecida como [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="fc639-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="fc639-205">**Mostrar dados para: encaminhar domínios**: este modo de exibição mostra os domínios de destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="fc639-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="fc639-207">**Mostrar dados para: encaminhadores**: os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="fc639-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="fc639-208">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="fc639-208">**Transport rule**</span></span>
  - <span data-ttu-id="fc639-209">A caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="fc639-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="fc639-211">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="fc639-212">Exibição da tabela de detalhes para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="fc639-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="fc639-213">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="fc639-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="fc639-214">**Encaminhadores**: a **regra de transporte** de valor ou a caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="fc639-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="fc639-215">**Tipo de encaminhamento**: a **regra de caixa de correio** de valor ou a **regra de transporte**.</span><span class="sxs-lookup"><span data-stu-id="fc639-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="fc639-216">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="fc639-216">**Recipient name**</span></span>
- <span data-ttu-id="fc639-217">**Domínio do destinatário**</span><span class="sxs-lookup"><span data-stu-id="fc639-217">**Recipient domain**</span></span>
- <span data-ttu-id="fc639-218">**Detalhes**: Este é o valor de GUID da regra de fluxo de emails ou o valor RuleIdentity da regra de caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="fc639-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="fc639-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-219">**Count**</span></span>
- <span data-ttu-id="fc639-220">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="fc639-220">**First forward date**</span></span>

<span data-ttu-id="fc639-221">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc639-222">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="fc639-223">Relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="fc639-223">Mailflow status report</span></span>

<span data-ttu-id="fc639-224">O **relatório de status do fluxo** é semelhante ao [relatório de email enviado e recebido](#sent-and-received-email-report), com informações adicionais sobre o email permitido ou bloqueado na borda.</span><span class="sxs-lookup"><span data-stu-id="fc639-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="fc639-225">Este é o único relatório que contém as informações de proteção de borda e mostra o quanto o email é bloqueado antes de ser permitido ao serviço para avaliação pelo Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="fc639-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="fc639-226">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **fluxo relatório de status**.</span><span class="sxs-lookup"><span data-stu-id="fc639-226">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="fc639-227">Para ir diretamente para o **relatório de status de fluxo de emails**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="fc639-227">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget relatório de status do fluxo no painel relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="fc639-229">Modo de exibição de tipo para o relatório de status fluxo</span><span class="sxs-lookup"><span data-stu-id="fc639-229">Type view for the Mailflow status report</span></span>

<span data-ttu-id="fc639-230">Quando você abre o relatório, a guia **tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="fc639-230">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="fc639-231">Por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="fc639-231">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="fc639-232">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="fc639-232">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="fc639-233">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="fc639-233">**Direction**:</span></span>

  - <span data-ttu-id="fc639-234">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="fc639-234">**Inbound**</span></span>
  - <span data-ttu-id="fc639-235">**Saída**</span><span class="sxs-lookup"><span data-stu-id="fc639-235">**Outbound**</span></span>
  - <span data-ttu-id="fc639-236">**Intra-org** (contado separadamente de **entrada** e **saída**)</span><span class="sxs-lookup"><span data-stu-id="fc639-236">**Intra-org** (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="fc639-237">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="fc639-237">**Type**:</span></span>

  - <span data-ttu-id="fc639-238">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="fc639-238">**Good mail**</span></span>
  - <span data-ttu-id="fc639-239">**Malware**</span><span class="sxs-lookup"><span data-stu-id="fc639-239">**Malware**</span></span>
  - <span data-ttu-id="fc639-240">**Spam**</span><span class="sxs-lookup"><span data-stu-id="fc639-240">**Spam**</span></span>
  - <span data-ttu-id="fc639-241">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="fc639-241">**Edge protection**</span></span>
  - <span data-ttu-id="fc639-242">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="fc639-242">**Rule messages**</span></span>
  - <span data-ttu-id="fc639-243">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="fc639-243">**Phishing email**</span></span>

<span data-ttu-id="fc639-244">O gráfico é organizado pelos valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="fc639-244">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="fc639-245">Você pode alterar esses filtros clicando em **filtro** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="fc639-245">You can changes these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="fc639-246">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="fc639-246">The data table contains the following information:</span></span>

- <span data-ttu-id="fc639-247">**Direção**</span><span class="sxs-lookup"><span data-stu-id="fc639-247">**Direction**</span></span>
- <span data-ttu-id="fc639-248">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc639-248">**Type**</span></span>
- <span data-ttu-id="fc639-249">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="fc639-249">**24 hours**</span></span>
- <span data-ttu-id="fc639-250">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="fc639-250">**3 days**</span></span>
- <span data-ttu-id="fc639-251">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="fc639-251">**7 days**</span></span>
- <span data-ttu-id="fc639-252">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="fc639-252">**15 days**</span></span>
- <span data-ttu-id="fc639-253">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="fc639-253">**30 days**</span></span>

<span data-ttu-id="fc639-254">Se você clicar em **escolher uma categoria para obter mais detalhes**, poderá selecionar os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fc639-254">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="fc639-255">**Email de phishing**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-255">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fc639-256">**Malware em email**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-256">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="fc639-257">**Detecções de spam**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-257">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="fc639-258">**Bloqueio de spam bloqueado**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-258">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fc639-259">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="fc639-259">**Export**:</span></span>

<span data-ttu-id="fc639-260">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="fc639-260">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fc639-261">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="fc639-261">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fc639-262">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="fc639-262">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fc639-263">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="fc639-263">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="fc639-264">Modo de exibição de tipo no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="fc639-264">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="fc639-265">Exibição de direção para o relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="fc639-265">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="fc639-266">Se você clicar na guia **direção** , os mesmos filtros padrão do modo de exibição de **tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="fc639-266">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="fc639-267">O gráfico é organizado por valores de **direção** .</span><span class="sxs-lookup"><span data-stu-id="fc639-267">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="fc639-268">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="fc639-268">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="fc639-269">Os mesmos filtros do **tipo** de exibição são usados.</span><span class="sxs-lookup"><span data-stu-id="fc639-269">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="fc639-270">A tabela de dados contém as mesmas informações do **tipo** de exibição.</span><span class="sxs-lookup"><span data-stu-id="fc639-270">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="fc639-271">A **escolha uma categoria para obter detalhes sobre** as seleções e o comportamento disponíveis são os mesmos que o modo de exibição de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="fc639-271">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="fc639-272">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="fc639-272">**Export**:</span></span>

<span data-ttu-id="fc639-273">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="fc639-273">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="fc639-274">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="fc639-274">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="fc639-275">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="fc639-275">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="fc639-276">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="fc639-276">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="fc639-277">Exibição de direção no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="fc639-277">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="fc639-278">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="fc639-278">Sent and received email report</span></span>

<span data-ttu-id="fc639-279">O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom".</span><span class="sxs-lookup"><span data-stu-id="fc639-279">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="fc639-280">A diferença entre este relatório e o [relatório de status do fluxo](#mailflow-status-report) é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda.</span><span class="sxs-lookup"><span data-stu-id="fc639-280">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.</span></span>

<span data-ttu-id="fc639-281">O modo de exibição de agregação e o modo de exibição de detalhes do relatório permitem que 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="fc639-281">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="fc639-282">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **email enviado e recebido**.</span><span class="sxs-lookup"><span data-stu-id="fc639-282">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="fc639-283">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="fc639-283">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget email enviado e recebido no painel relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fc639-285">Exibição de relatório para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="fc639-285">Report view for the Sent and received email report</span></span>

<span data-ttu-id="fc639-286">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="fc639-286">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fc639-287">**Divisão por: digite**: o gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fc639-287">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="fc639-288">**Total**</span><span class="sxs-lookup"><span data-stu-id="fc639-288">**Total**</span></span>
  - <span data-ttu-id="fc639-289">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="fc639-289">**Good mail**</span></span>
  - <span data-ttu-id="fc639-290">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fc639-290">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="fc639-291">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="fc639-291">**Spam detections**</span></span>
  - <span data-ttu-id="fc639-292">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="fc639-292">**Rule messages**</span></span>
  - <span data-ttu-id="fc639-293">**Malware avançado** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="fc639-293">**Advanced malware** (Office 365 ATP)</span></span>

  <span data-ttu-id="fc639-294">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="fc639-294">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de tipo no relatório de email enviado e recebido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="fc639-296">**Divisão por: direção**: o gráfico mostra os dados **total**, de **entrada**e de **saída** .</span><span class="sxs-lookup"><span data-stu-id="fc639-296">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="fc639-297">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="fc639-297">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="fc639-299">**Aprofundar por** \> **Malware (Antimalware)**: esta seleção leva você para as [detecções de malware no relatório de email](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-299">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="fc639-300">**Aprofundar por** \> **Detecções de spam)**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="fc639-300">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="fc639-301">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="fc639-301">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fc639-302">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="fc639-302">**Start date** and **End date**</span></span>
- <span data-ttu-id="fc639-303">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="fc639-303">Direction values</span></span>
- <span data-ttu-id="fc639-304">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="fc639-304">Type values</span></span>

<span data-ttu-id="fc639-305">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-305">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="fc639-306">Exibição da tabela de detalhes para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="fc639-306">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="fc639-307">Se você clicar em **Exibir tabela de detalhes** na tela **dividir por: direção** ou **dividir em: direção** , as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="fc639-307">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="fc639-308">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="fc639-308">**Date (UTC)**</span></span>
- <span data-ttu-id="fc639-309">**Type**</span><span class="sxs-lookup"><span data-stu-id="fc639-309">**Type**</span></span>
- <span data-ttu-id="fc639-310">**Direção**</span><span class="sxs-lookup"><span data-stu-id="fc639-310">**Direction**</span></span>
- <span data-ttu-id="fc639-311">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="fc639-311">**Message count**</span></span>

<span data-ttu-id="fc639-312">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="fc639-312">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="fc639-313">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="fc639-313">**Start date** and **End date**</span></span>
- <span data-ttu-id="fc639-314">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="fc639-314">Direction values</span></span>
- <span data-ttu-id="fc639-315">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="fc639-315">Type values</span></span>

<span data-ttu-id="fc639-316">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-316">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="fc639-317">Relatório de principais remetentes e destinatários</span><span class="sxs-lookup"><span data-stu-id="fc639-317">Top senders and recipients report</span></span>

<span data-ttu-id="fc639-318">O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="fc639-318">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="fc639-319">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **os principais remetentes e destinatários**.</span><span class="sxs-lookup"><span data-stu-id="fc639-319">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="fc639-320">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="fc639-320">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget principais remetentes e destinatários no painel relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fc639-322">Exibição de relatório para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="fc639-322">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="fc639-323">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="fc639-323">The following charts are available in the report view:</span></span>

- <span data-ttu-id="fc639-324">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="fc639-324">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="fc639-325">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="fc639-325">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="fc639-326">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="fc639-326">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="fc639-327">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fc639-327">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="fc639-328">**Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="fc639-328">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

<span data-ttu-id="fc639-329">A composição do gráfico de pizza é alterada com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="fc639-329">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="fc639-330">Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="fc639-330">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="fc639-331">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-331">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no modo de exibição de relatório no relatório de remetentes e destinatários principais](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="fc639-333">Exibição da tabela de detalhes para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="fc639-333">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="fc639-334">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="fc639-334">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="fc639-335">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="fc639-335">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="fc639-336">**Principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="fc639-336">**Top mail senders**</span></span>
  - <span data-ttu-id="fc639-337">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-337">**Count**</span></span>

- <span data-ttu-id="fc639-338">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="fc639-338">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="fc639-339">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="fc639-339">**Top mail recipients**</span></span>
  - <span data-ttu-id="fc639-340">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-340">**Count**</span></span>

- <span data-ttu-id="fc639-341">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="fc639-341">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="fc639-342">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="fc639-342">**Top spam recipients**</span></span>
  - <span data-ttu-id="fc639-343">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-343">**Count**</span></span>

- <span data-ttu-id="fc639-344">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="fc639-344">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="fc639-345">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="fc639-345">**Top malware recipients**</span></span>
  - <span data-ttu-id="fc639-346">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-346">**Count**</span></span>

- <span data-ttu-id="fc639-347">**Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="fc639-347">**Show data for \> Top malware recipients (ATP)** (Office 365 ATP)</span></span>

  - <span data-ttu-id="fc639-348">**Principais destinatários de malware (ATP)**</span><span class="sxs-lookup"><span data-stu-id="fc639-348">**Top malware recipients (ATP)**</span></span>
  - <span data-ttu-id="fc639-349">**Count**</span><span class="sxs-lookup"><span data-stu-id="fc639-349">**Count**</span></span>

<span data-ttu-id="fc639-350">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="fc639-350">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="fc639-351">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="fc639-351">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="fc639-352">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="fc639-352">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="fc639-353">Para exibir e usar os relatórios, você precisa ser membro do grupo de função especificado no centro de conformidade e segurança & **e** no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="fc639-353">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="fc639-354">No centro de conformidade & segurança, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="fc639-354">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="fc639-355">– Gerenciamento de organização-administrador de segurança (você também pode fazer isso no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) -leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="fc639-355">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="fc639-356">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="fc639-356">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="fc639-357">No Exchange Online, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="fc639-357">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="fc639-358">– Gerenciamento de organização – gerenciamento de organização somente de exibição-somente os destinatários do gerenciamento de conformidade</span><span class="sxs-lookup"><span data-stu-id="fc639-358">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="fc639-359">Para obter mais informações, consulte [permissões no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gerenciar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="fc639-359">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc639-360">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fc639-360">Related topics</span></span>

[<span data-ttu-id="fc639-361">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="fc639-361">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="fc639-362">Insights de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="fc639-362">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="fc639-363">Exibir relatórios de segurança de email no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="fc639-363">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="fc639-364">Exibir relatórios para a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="fc639-364">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
