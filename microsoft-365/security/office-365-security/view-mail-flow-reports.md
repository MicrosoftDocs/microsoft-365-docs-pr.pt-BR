---
title: Exibir relatórios de fluxo de emails no painel relatórios
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
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
ms.openlocfilehash: 840b9920fc3f994140702eae0bf5ddbdeac4b465
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357918"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a><span data-ttu-id="93bdd-103">Exibir relatórios de fluxo de emails no painel de relatórios no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="93bdd-103">View mail flow reports in the Reports dashboard in Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="93bdd-104">Além dos relatórios de fluxo de emails disponíveis no painel de [fluxo de emails](mail-flow-insights-v2.md) no centro de conformidade com segurança &, vários relatórios de fluxo de email adicionais estão disponíveis no painel de relatórios para ajudá-lo a monitorar sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93bdd-104">In addition to the mail flow reports that are available in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center, a variety of additional mail flow reports are available in the Reports dashboard to help you monitor your Microsoft 365 organization.</span></span>

<span data-ttu-id="93bdd-105">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de [conformidade & de segurança](https://office.protection.com) acessando **Reports** o \> **painel** relatórios.</span><span class="sxs-lookup"><span data-stu-id="93bdd-105">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the [Security & Compliance Center](https://office.protection.com) by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="93bdd-106">Para ir diretamente para o painel relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-106">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a><span data-ttu-id="93bdd-108">Relatório do conector</span><span class="sxs-lookup"><span data-stu-id="93bdd-108">Connector report</span></span>

<span data-ttu-id="93bdd-109">O **relatório do conector** mostra a atividade de fluxo de emails nos [conectores de entrada e saída](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) que estão configurados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="93bdd-109">The **Connector report** shows mail flow activity on the [inbound and outbound connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) that are configured for your organization.</span></span>

<span data-ttu-id="93bdd-110">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório do conector**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-110">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Connector report**.</span></span> <span data-ttu-id="93bdd-111">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-111">To go directly to the report, open <https://protection.office.com/reportv2?id=ConnectorReport>.</span></span>

![Widget relatório do conector no painel relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a><span data-ttu-id="93bdd-113">Exibição de relatório para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="93bdd-113">Report view for the Connector report</span></span>

<span data-ttu-id="93bdd-114">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="93bdd-114">The following charts are available in report view:</span></span>

- <span data-ttu-id="93bdd-115">**Exibir dados por: fluxo de email**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:</span><span class="sxs-lookup"><span data-stu-id="93bdd-115">**View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:</span></span>

  - <span data-ttu-id="93bdd-116">**Total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-116">**Total**</span></span>
  - <span data-ttu-id="93bdd-117">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-117">**From the internet without a connector**</span></span>
  - <span data-ttu-id="93bdd-118">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-118">**To the internet without a connector**</span></span>
  - <span data-ttu-id="93bdd-119">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="93bdd-119">A specific connector that you've configured.</span></span>

  <span data-ttu-id="93bdd-120">Para isolar os dados no gráfico, use o recurso **Mostrar dados do** controle para selecionar uma destas opções ou **todo o fluxo de emails**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-120">To isolate the data in the chart, use the **Show data for** control to select one of these options or **All mail flow**.</span></span>

  ![Exibir dados por fluxo de emails no relatório do conector](../../media/connector-report-view-data-by-mail-flow.png)

- <span data-ttu-id="93bdd-122">**Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão do protocolo TLS para o fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="93bdd-122">**View data by: TLS usage**: This chart shows the percentage of Transport Layer Security (TLS) version usage for mail flow.</span></span>

  <span data-ttu-id="93bdd-123">Para isolar os dados no gráfico, use a opção **Mostrar dados do** controle para selecionar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="93bdd-123">To isolate the data in the chart, use the **Show data for** control to select one of the following options:</span></span>

  - <span data-ttu-id="93bdd-124">**Todo o fluxo de email**</span><span class="sxs-lookup"><span data-stu-id="93bdd-124">**All mail flow**</span></span>
  - <span data-ttu-id="93bdd-125">**Da Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-125">**From the internet without a connector**</span></span>
  - <span data-ttu-id="93bdd-126">**Para a Internet sem um conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-126">**To the internet without a connector**</span></span>
  - <span data-ttu-id="93bdd-127">Um conector específico que você configurou.</span><span class="sxs-lookup"><span data-stu-id="93bdd-127">A specific connector that you've configured.</span></span>

  ![Exibir dados por uso de TLS no relatório do conector](../../media/connector-report-view-data-by-tls-usage.png)

<span data-ttu-id="93bdd-129">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-129">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-connector-report"></a><span data-ttu-id="93bdd-130">Exibição da tabela de detalhes para o relatório do conector</span><span class="sxs-lookup"><span data-stu-id="93bdd-130">Details table view for the Connector report</span></span>

<span data-ttu-id="93bdd-131">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="93bdd-131">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="93bdd-132">**Date**</span><span class="sxs-lookup"><span data-stu-id="93bdd-132">**Date**</span></span>
- <span data-ttu-id="93bdd-133">**Direção e nome do conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-133">**Connector direction and name**</span></span>
- <span data-ttu-id="93bdd-134">**Tipo de conector**</span><span class="sxs-lookup"><span data-stu-id="93bdd-134">**Connector type**</span></span>
- <span data-ttu-id="93bdd-135">**TLS forçado?**: o valor **true** ou **false**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-135">**Forced TLS?**: The value **True** or **False**.</span></span>
- <span data-ttu-id="93bdd-136">**Sem TLS** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="93bdd-136">**No TLS** (percentage)</span></span>
- <span data-ttu-id="93bdd-137">**TLS 1,0** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="93bdd-137">**TLS 1.0** (percentage)</span></span>
- <span data-ttu-id="93bdd-138">**TLS 1,1** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="93bdd-138">**TLS 1.1** (percentage)</span></span>
- <span data-ttu-id="93bdd-139">**TLS 1,2** (porcentagem)</span><span class="sxs-lookup"><span data-stu-id="93bdd-139">**TLS 1.2** (percentage)</span></span>
- <span data-ttu-id="93bdd-140">**Volume**: o número de mensagens.</span><span class="sxs-lookup"><span data-stu-id="93bdd-140">**Volume**: The number of messages.</span></span>

<span data-ttu-id="93bdd-141">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-141">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="93bdd-142">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-142">To go back to the report view, click **View report**.</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="93bdd-143">Relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="93bdd-143">Exchange transport rule report</span></span>

<span data-ttu-id="93bdd-144">O **relatório** de regras de transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e de saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="93bdd-144">The **Exchange transport rule report** shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="93bdd-145">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione regra de **transporte do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-145">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Exchange Transport rule**.</span></span> <span data-ttu-id="93bdd-146">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-146">To go directly to the report, open <https://protection.office.com/reportv2?id=ETRRuleReport>.</span></span>

![Widget regra de transporte do Exchange no painel relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="93bdd-148">Exibição de relatório para o relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="93bdd-148">Report view for the Exchange transport rule report</span></span>

<span data-ttu-id="93bdd-149">Os gráficos a seguir estão disponíveis no modo de exibição relatório:</span><span class="sxs-lookup"><span data-stu-id="93bdd-149">The following charts are available in report view:</span></span>

- <span data-ttu-id="93bdd-150">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas por regras de transporte.</span><span class="sxs-lookup"><span data-stu-id="93bdd-150">**View data by: Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.</span></span>

- <span data-ttu-id="93bdd-151">**Exibir dados por: regras** \> de transporte do Exchange **Dividir em: severidade**: Este gráfico mostra o número de **alta gravidade** e **severidade média** e mensagens de **baixa gravidade** .</span><span class="sxs-lookup"><span data-stu-id="93bdd-151">**View data by: Exchange transport rules** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="93bdd-152">Você define o nível de severidade como uma ação na regra (**auditar esta regra com nível de severidade** ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="93bdd-152">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="93bdd-153">Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="93bdd-153">For more information, see [Mail flow rule actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="93bdd-154">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas pelas regras de transporte de prevenção de perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="93bdd-154">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules.</span></span> <span data-ttu-id="93bdd-155">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="93bdd-155">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="93bdd-156">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="93bdd-156">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="93bdd-157">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="93bdd-157">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="93bdd-158">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="93bdd-158">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

- <span data-ttu-id="93bdd-159">**Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: este modo de exibição mostra o número de **alta** gravidade e **severidade média** e mensagens de **baixa gravidade** que foram afetadas pelas regras de transporte DLP.</span><span class="sxs-lookup"><span data-stu-id="93bdd-159">**View data by: DLP Exchange transport rules** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules.</span></span> <span data-ttu-id="93bdd-160">Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="93bdd-160">You can further refine the chart by selecting on of the following options:</span></span>

  - <span data-ttu-id="93bdd-161">**Mostrar dados de: todas as regras de transporte DLP**</span><span class="sxs-lookup"><span data-stu-id="93bdd-161">**Show data for: All DLP transport rules**</span></span>
  - <span data-ttu-id="93bdd-162">**Mostrar dados de: usuários comprometidos**</span><span class="sxs-lookup"><span data-stu-id="93bdd-162">**Show data for: Compromised users**</span></span>
  - <span data-ttu-id="93bdd-163">**Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**</span><span class="sxs-lookup"><span data-stu-id="93bdd-163">**Show data for: Low volume of content detected U.S. Patriot Act**</span></span>

<span data-ttu-id="93bdd-164">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-164">If you click **Filters** in a report view, you can modify the results with the following filters::</span></span>

- <span data-ttu-id="93bdd-165">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="93bdd-165">**Start date** and **End date**</span></span>
- <span data-ttu-id="93bdd-166">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="93bdd-166">Direction values</span></span>
- <span data-ttu-id="93bdd-167">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="93bdd-167">Severity values</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a><span data-ttu-id="93bdd-169">Exibição da tabela de detalhes para o relatório de regras de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="93bdd-169">Details table view for the Exchange transport rule report</span></span>

<span data-ttu-id="93bdd-170">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="93bdd-170">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="93bdd-171">**Exibir dados por: regras de transporte do Exchange**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-171">**View data by: Exchange Transport rules**:</span></span>

  - <span data-ttu-id="93bdd-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="93bdd-172">**Date**</span></span>
  - <span data-ttu-id="93bdd-173">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="93bdd-173">**Transport rule**</span></span>
  - <span data-ttu-id="93bdd-174">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="93bdd-174">**Subject**</span></span>
  - <span data-ttu-id="93bdd-175">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-175">**Sender address**</span></span>
  - <span data-ttu-id="93bdd-176">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="93bdd-176">**Recipient address**</span></span>
  - <span data-ttu-id="93bdd-177">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="93bdd-177">**Severity**</span></span>
  - <span data-ttu-id="93bdd-178">**Direção**</span><span class="sxs-lookup"><span data-stu-id="93bdd-178">**Direction**</span></span>

- <span data-ttu-id="93bdd-179">**Exibir dados por: regras de transporte do Exchange DLP**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-179">**View data by: DLP Exchange transport rules**:</span></span>

  - <span data-ttu-id="93bdd-180">**Date**</span><span class="sxs-lookup"><span data-stu-id="93bdd-180">**Date**</span></span>
  - <span data-ttu-id="93bdd-181">**Política de DLP**</span><span class="sxs-lookup"><span data-stu-id="93bdd-181">**DLP policy**</span></span>
  - <span data-ttu-id="93bdd-182">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="93bdd-182">**Transport rule**</span></span>
  - <span data-ttu-id="93bdd-183">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="93bdd-183">**Subject**</span></span>
  - <span data-ttu-id="93bdd-184">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-184">**Sender address**</span></span>
  - <span data-ttu-id="93bdd-185">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="93bdd-185">**Recipient address**</span></span>
  - <span data-ttu-id="93bdd-186">**Severidade**</span><span class="sxs-lookup"><span data-stu-id="93bdd-186">**Severity**</span></span>
  - <span data-ttu-id="93bdd-187">**Direção**</span><span class="sxs-lookup"><span data-stu-id="93bdd-187">**Direction**</span></span>

<span data-ttu-id="93bdd-188">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-188">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="93bdd-189">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="93bdd-189">**Start date** and **End date**</span></span>
- <span data-ttu-id="93bdd-190">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="93bdd-190">Direction values</span></span>
- <span data-ttu-id="93bdd-191">Valores de gravidade</span><span class="sxs-lookup"><span data-stu-id="93bdd-191">Severity values</span></span>

<span data-ttu-id="93bdd-192">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-192">To go back to the report view, click **View report**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="93bdd-193">Encaminhando relatório</span><span class="sxs-lookup"><span data-stu-id="93bdd-193">Forwarding report</span></span>

<span data-ttu-id="93bdd-194">O **relatório de encaminhamento** mostra as mensagens automaticamente encaminhadas de sua organização para domínios externos de caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93bdd-194">The **Forwarding report** shows your organization's automatically forwarded messages to external domains from Exchange Online mailboxes.</span></span> <span data-ttu-id="93bdd-195">As mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="93bdd-195">Forwarded messages can pose a security or compliance risk, and might indicate a compromised account.</span></span>

<span data-ttu-id="93bdd-196">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório de encaminhamento**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-196">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Forwarding report**.</span></span> <span data-ttu-id="93bdd-197">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-197">To go directly to the report, open <https://protection.office.com/reportv2?id=MailFlowForwarding>.</span></span>

![Widget de encaminhamento de relatório no painel relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a><span data-ttu-id="93bdd-199">Exibição de relatório para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="93bdd-199">Report view for the Forwarding report</span></span>

<span data-ttu-id="93bdd-200">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="93bdd-200">The following charts are available in the report view:</span></span>

- <span data-ttu-id="93bdd-201">**Mostrar dados para: métodos de encaminhamento**: os seguintes métodos são mostrados:</span><span class="sxs-lookup"><span data-stu-id="93bdd-201">**Show data for: Forwarding methods**: The following methods are shown:</span></span>

  - <span data-ttu-id="93bdd-202">**Regra de transporte**: também conhecida como [regras de fluxo de emails](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="93bdd-202">**Transport rule**: Also known as [mail flow rules](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).</span></span>
  - <span data-ttu-id="93bdd-203">**Regra de caixa de correio**: também conhecida como [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span><span class="sxs-lookup"><span data-stu-id="93bdd-203">**Mailbox rule**: Also known as [Inbox rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).</span></span>

  ![Exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- <span data-ttu-id="93bdd-205">**Mostrar dados para: encaminhar domínios**: este modo de exibição mostra os domínios de destinatário que são os destinos para encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="93bdd-205">**Show data for: Forwarding domains**: This view shows the recipient domains that are the destinations for forwarding.</span></span>

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- <span data-ttu-id="93bdd-207">**Mostrar dados para: encaminhadores**: os seguintes encaminhadores são mostrados:</span><span class="sxs-lookup"><span data-stu-id="93bdd-207">**Show data for: Forwarders**: The following forwarders are shown:</span></span>

  - <span data-ttu-id="93bdd-208">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="93bdd-208">**Transport rule**</span></span>
  - <span data-ttu-id="93bdd-209">A caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="93bdd-209">The mailbox that contains the forwarding Inbox rule.</span></span>

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

<span data-ttu-id="93bdd-211">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-211">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-report"></a><span data-ttu-id="93bdd-212">Exibição da tabela de detalhes para o relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="93bdd-212">Details table view for the Forwarding report</span></span>

<span data-ttu-id="93bdd-213">Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:</span><span class="sxs-lookup"><span data-stu-id="93bdd-213">If you click **View details table** in a report view, the following information is shown:</span></span>

- <span data-ttu-id="93bdd-214">**Encaminhadores**: a **regra de transporte** de valor ou a caixa de correio que contém a regra de caixa de entrada de encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="93bdd-214">**Forwarders**: The value **Transport rule** or the mailbox that contains the forwarding Inbox rule.</span></span>
- <span data-ttu-id="93bdd-215">**Tipo de encaminhamento**: a **regra de caixa de correio** de valor ou a **regra de transporte**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-215">**Forwarding type**: The value **Mailbox rule** or **Transport rule**.</span></span>
- <span data-ttu-id="93bdd-216">**Nome do destinatário**</span><span class="sxs-lookup"><span data-stu-id="93bdd-216">**Recipient name**</span></span>
- <span data-ttu-id="93bdd-217">**Domínio do destinatário**</span><span class="sxs-lookup"><span data-stu-id="93bdd-217">**Recipient domain**</span></span>
- <span data-ttu-id="93bdd-218">**Detalhes**: Este é o valor de GUID da regra de fluxo de emails ou o valor RuleIdentity da regra de caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="93bdd-218">**Details**: This is the GUID value of the mail flow rule, or the RuleIdentity value of the Inbox rule.</span></span>
- <span data-ttu-id="93bdd-219">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-219">**Count**</span></span>
- <span data-ttu-id="93bdd-220">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="93bdd-220">**First forward date**</span></span>

<span data-ttu-id="93bdd-221">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-221">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="93bdd-222">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-222">To go back to the reports view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="93bdd-223">Relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-223">Mailflow status report</span></span>

<span data-ttu-id="93bdd-224">O **relatório de status do fluxo** é semelhante ao [relatório de email enviado e recebido](#sent-and-received-email-report), com informações adicionais sobre o email permitido ou bloqueado na borda.</span><span class="sxs-lookup"><span data-stu-id="93bdd-224">The **Mailflow status report** is similar to the [Sent and received email report](#sent-and-received-email-report), with additional information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="93bdd-225">Este é o único relatório que contém as informações de proteção de borda e mostra o quanto o email é bloqueado antes de ser permitido ao serviço para avaliação pelo Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="93bdd-225">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="93bdd-226">É importante entender que, se uma mensagem for enviada para cinco destinatários, contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-226">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>
<span data-ttu-id="93bdd-227">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **fluxo relatório de status**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-227">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Mailflow status report**.</span></span> <span data-ttu-id="93bdd-228">Para ir diretamente para o **relatório de status de fluxo de emails**, abra <https://protection.office.com/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-228">To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport>.</span></span>

![Widget relatório de status do fluxo no painel relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="93bdd-230">Modo de exibição de tipo para o relatório de status fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-230">Type view for the Mailflow status report</span></span>

<span data-ttu-id="93bdd-231">Quando você abre o relatório, a guia **tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="93bdd-231">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="93bdd-232">Por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-232">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="93bdd-233">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="93bdd-233">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="93bdd-234">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-234">**Direction**:</span></span>

  - <span data-ttu-id="93bdd-235">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="93bdd-235">**Inbound**</span></span>
  - <span data-ttu-id="93bdd-236">**Saída**</span><span class="sxs-lookup"><span data-stu-id="93bdd-236">**Outbound**</span></span>
  - <span data-ttu-id="93bdd-237">**Intra-org**: essa contagem é para mensagens dentro de um locatário, ou seja,</span><span class="sxs-lookup"><span data-stu-id="93bdd-237">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="93bdd-238">o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de **entrada** e **saída**)</span><span class="sxs-lookup"><span data-stu-id="93bdd-238">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>

- <span data-ttu-id="93bdd-239">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-239">**Type**:</span></span>

  - <span data-ttu-id="93bdd-240">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="93bdd-240">**Good mail**</span></span>
  - <span data-ttu-id="93bdd-241">**Malware**</span><span class="sxs-lookup"><span data-stu-id="93bdd-241">**Malware**</span></span>
  - <span data-ttu-id="93bdd-242">**Spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-242">**Spam**</span></span>
  - <span data-ttu-id="93bdd-243">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="93bdd-243">**Edge protection**</span></span>
  - <span data-ttu-id="93bdd-244">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="93bdd-244">**Rule messages**</span></span>
  - <span data-ttu-id="93bdd-245">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="93bdd-245">**Phishing email**</span></span>

<span data-ttu-id="93bdd-246">O gráfico é organizado pelos valores de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="93bdd-246">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="93bdd-247">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="93bdd-247">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="93bdd-248">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="93bdd-248">The data table contains the following information:</span></span>

- <span data-ttu-id="93bdd-249">**Direção**</span><span class="sxs-lookup"><span data-stu-id="93bdd-249">**Direction**</span></span>
- <span data-ttu-id="93bdd-250">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="93bdd-250">**Type**</span></span>
- <span data-ttu-id="93bdd-251">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="93bdd-251">**24 hours**</span></span>
- <span data-ttu-id="93bdd-252">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="93bdd-252">**3 days**</span></span>
- <span data-ttu-id="93bdd-253">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="93bdd-253">**7 days**</span></span>
- <span data-ttu-id="93bdd-254">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="93bdd-254">**15 days**</span></span>
- <span data-ttu-id="93bdd-255">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="93bdd-255">**30 days**</span></span>

<span data-ttu-id="93bdd-256">Se você clicar em **escolher uma categoria para obter mais detalhes**, poderá selecionar os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="93bdd-256">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="93bdd-257">**Email de phishing**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-257">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="93bdd-258">**Malware em email**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-258">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="93bdd-259">**Detecções de spam**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-259">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="93bdd-260">**Bloqueio de spam bloqueado**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-260">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="93bdd-261">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-261">**Export**:</span></span>

<span data-ttu-id="93bdd-262">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="93bdd-262">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="93bdd-263">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="93bdd-263">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="93bdd-264">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="93bdd-264">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93bdd-265">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-265">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="93bdd-266">Modo de exibição de tipo no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-266">Type view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="93bdd-267">Exibição de direção para o relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-267">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="93bdd-268">Se você clicar na guia **direção** , os mesmos filtros padrão do modo de exibição de **tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-268">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="93bdd-269">O gráfico é organizado por valores de **direção** .</span><span class="sxs-lookup"><span data-stu-id="93bdd-269">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="93bdd-270">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="93bdd-270">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="93bdd-271">Os mesmos filtros do **tipo** de exibição são usados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-271">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="93bdd-272">A tabela de dados contém as mesmas informações do **tipo** de exibição.</span><span class="sxs-lookup"><span data-stu-id="93bdd-272">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="93bdd-273">A **escolha uma categoria para obter detalhes sobre** as seleções e o comportamento disponíveis são os mesmos que o modo de exibição de **tipo** .</span><span class="sxs-lookup"><span data-stu-id="93bdd-273">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

<span data-ttu-id="93bdd-274">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-274">**Export**:</span></span>

<span data-ttu-id="93bdd-275">Para o modo de exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="93bdd-275">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="93bdd-276">Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.</span><span class="sxs-lookup"><span data-stu-id="93bdd-276">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="93bdd-277">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="93bdd-277">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93bdd-278">Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-278">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![<span data-ttu-id="93bdd-279">Exibição de direção no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-279">Direction view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="93bdd-280">Exibição de funil para o relatório de status fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-280">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="93bdd-281">O modo de exibição do **funil** mostra como os recursos de proteção contra ameaças de email da Microsoft filtram os emails de entrada e de saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="93bdd-281">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="93bdd-282">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configuradas, incluindo proteção de borda, Antimalware, anti-phishing, antispam e anti-falsificação, afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-282">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="93bdd-283">Se você clicar na guia **funil** , por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-283">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="93bdd-284">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="93bdd-284">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="93bdd-285">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-285">**Direction**:</span></span>

  - <span data-ttu-id="93bdd-286">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="93bdd-286">**Inbound**</span></span>
  - <span data-ttu-id="93bdd-287">**Saída**</span><span class="sxs-lookup"><span data-stu-id="93bdd-287">**Outbound**</span></span>
  - <span data-ttu-id="93bdd-288">**Intra-org**: essa contagem é para mensagens enviadas dentro de um locatário; ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de entrada e saída).</span><span class="sxs-lookup"><span data-stu-id="93bdd-288">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="93bdd-289">O modo de exibição de agregação e o modo de exibição de tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-289">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="93bdd-290">Se você clicar em **filtro**, poderá filtrar tanto o gráfico quanto a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-290">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="93bdd-291">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="93bdd-291">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="93bdd-292">**Email total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-292">**Total email**</span></span>
- <span data-ttu-id="93bdd-293">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="93bdd-293">**Email after edge protection**</span></span>
- <span data-ttu-id="93bdd-294">**Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="93bdd-294">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="93bdd-295">**Email após anti-Phish, reputação da URL, representação da marca, antifalsificação**</span><span class="sxs-lookup"><span data-stu-id="93bdd-295">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="93bdd-296">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="93bdd-296">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="93bdd-297">**Email após representação de usuário e domínio**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93bdd-297">**Email after user and domain impersonation**<sup>1</sup></span></span>
- <span data-ttu-id="93bdd-298">**Email após arquivo e URL acionamento**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="93bdd-298">**Email after file and URL detonation**<sup>1</sup></span></span>
- <span data-ttu-id="93bdd-299">**Email detectado como benigno após a proteção após a entrega (URL clique em proteção de tempo)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-299">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="93bdd-300"><sup>1</sup> defender apenas para o Office 365</span><span class="sxs-lookup"><span data-stu-id="93bdd-300"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="93bdd-301">Para exibir o email filtrado pelo EOP ou defender para Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="93bdd-301">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="93bdd-302">A tabela de dados contém as informações a seguir, mostradas em ordem decrescente de data:</span><span class="sxs-lookup"><span data-stu-id="93bdd-302">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="93bdd-303">**Date**</span><span class="sxs-lookup"><span data-stu-id="93bdd-303">**Date**</span></span>
- <span data-ttu-id="93bdd-304">**Email total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-304">**Total email**</span></span>
- <span data-ttu-id="93bdd-305">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="93bdd-305">**Edge protection**</span></span>
- <span data-ttu-id="93bdd-306">**Anti-malware, reputação de arquivos, bloqueio de tipo de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-306">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="93bdd-307">**Reputação do arquivo**: mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93bdd-307">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="93bdd-308">**Bloqueio de tipo de arquivo**: mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-308">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="93bdd-309">**Anti-Phish, reputação da URL, representação da marca,** anti-falsificação:</span><span class="sxs-lookup"><span data-stu-id="93bdd-309">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="93bdd-310">**Reputação da URL**: mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93bdd-310">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="93bdd-311">**Representação de marca**: mensagens filtradas devido à mensagem vindo de remetentes de marca conhecidos.</span><span class="sxs-lookup"><span data-stu-id="93bdd-311">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="93bdd-312">**Anti-falsificação**: mensagens filtradas devido à mensagem que está tentando falsificar um domínio ao qual o destinatário pertence ou um domínio que não é proprietário do remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-312">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="93bdd-313">**Anti-spam, filtragem de email em massa**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-313">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="93bdd-314">**Filtragem de email em massa**: mensagens filtradas devido a uma tentativa de entrega de email em massa para seus destinatários.</span><span class="sxs-lookup"><span data-stu-id="93bdd-314">**Bulk mail filtering**: Messages filtered due to an attempt to deliver bulk mail to its recipients.</span></span>
- <span data-ttu-id="93bdd-315">**Personificação de usuário e domínio (defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-315">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="93bdd-316">**Representação do usuário**: mensagens filtradas devido a uma tentativa de representar um usuário (remetente da mensagem) que está definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="93bdd-316">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="93bdd-317">**Representação de domínio**: mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="93bdd-317">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="93bdd-318">**Arquivo e URL acionamento (defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-318">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="93bdd-319">**Acionamento de arquivo**: mensagens filtradas por uma política de anexos seguros.</span><span class="sxs-lookup"><span data-stu-id="93bdd-319">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="93bdd-320">**URL acionamento**: mensagem filtrada por uma política de links seguros.</span><span class="sxs-lookup"><span data-stu-id="93bdd-320">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="93bdd-321">**Proteção de pós-entrega e zap (ATP) ou zap (EOP)**: zap indica exclusão automática em zero hora.</span><span class="sxs-lookup"><span data-stu-id="93bdd-321">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: ZAP indicates zero hour auto-purge.</span></span>

<span data-ttu-id="93bdd-322">Se você selecionar uma linha na tabela de dados, uma divisão adicional das contagens de email será mostrada no submenu.</span><span class="sxs-lookup"><span data-stu-id="93bdd-322">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="93bdd-323">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-323">**Export**:</span></span>

<span data-ttu-id="93bdd-324">Depois de clicar em **Exportar** em **Opções**, você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="93bdd-324">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="93bdd-325">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-325">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="93bdd-326">**Detalhes (com dados nos últimos 30 dias)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-326">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="93bdd-327">Em **Data**, escolha um intervalo e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-327">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="93bdd-328">Os dados dos filtros atuais serão exportados para um arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="93bdd-328">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="93bdd-329">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="93bdd-329">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93bdd-330">Se os dados contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-330">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="93bdd-331">Exibição do funil no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-331">Funnel view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="93bdd-332">Exibição de Tech para o relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-332">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="93bdd-333">O **modo de exibição técnico** é semelhante ao modo de exibição do **funil** , fornecendo detalhes mais granulares para os recursos configurados de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="93bdd-333">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="93bdd-334">No gráfico, você pode ver como as mensagens são categorizadas em diferentes estágios de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="93bdd-334">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="93bdd-335">Se você clicar na guia **Tech View** , por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-335">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="93bdd-336">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="93bdd-336">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="93bdd-337">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-337">**Direction**:</span></span>

  - <span data-ttu-id="93bdd-338">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="93bdd-338">**Inbound**</span></span>
  - <span data-ttu-id="93bdd-339">**Saída**</span><span class="sxs-lookup"><span data-stu-id="93bdd-339">**Outbound**</span></span>
  - <span data-ttu-id="93bdd-340">**Intra-org**: essa contagem é para mensagens dentro de um locatário, ou seja,</span><span class="sxs-lookup"><span data-stu-id="93bdd-340">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="93bdd-341">o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de entrada e saída)</span><span class="sxs-lookup"><span data-stu-id="93bdd-341">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="93bdd-342">O modo de exibição de agregação e o modo de exibição de tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-342">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="93bdd-343">Se você clicar em **filtro**, poderá filtrar tanto o gráfico quanto a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-343">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="93bdd-344">Este gráfico mostra as mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="93bdd-344">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="93bdd-345">**Email total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-345">**Total email**</span></span>
- <span data-ttu-id="93bdd-346">**Permissão de borda** e **borda filtradas**</span><span class="sxs-lookup"><span data-stu-id="93bdd-346">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="93bdd-347">**Não malware**, **detecção de anexos seguros** <sup>\*</sup> , **detecção de mecanismo anti-malware** e **mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="93bdd-347">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, **Anti-malware engine detection**, and **Rule messages**</span></span>
- <span data-ttu-id="93bdd-348">**Não Phish**, **falha DMARC**, **detecção de personificação**, **detecção de falsificação** e **detecção de phishing**</span><span class="sxs-lookup"><span data-stu-id="93bdd-348">**Not phish**, **DMARC failure**, **Impersonation detection**, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="93bdd-349">**Nenhuma detecção com URL acionamento** e **detecção de URL acionamento**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="93bdd-349">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="93bdd-350">**Não spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-350">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="93bdd-351">**Email não mal-intencionado**, **detecção de links seguros** <sup>\*</sup> e **zap**</span><span class="sxs-lookup"><span data-stu-id="93bdd-351">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="93bdd-352"><sup>\*</sup> Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="93bdd-352"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="93bdd-353">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="93bdd-353">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="93bdd-354">A tabela de dados contém as informações a seguir, mostradas em ordem decrescente de data:</span><span class="sxs-lookup"><span data-stu-id="93bdd-354">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="93bdd-355">**Date**</span><span class="sxs-lookup"><span data-stu-id="93bdd-355">**Date**</span></span>
- <span data-ttu-id="93bdd-356">**Email total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-356">**Total email**</span></span>
- <span data-ttu-id="93bdd-357">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="93bdd-357">**Edge filtered**</span></span>
- <span data-ttu-id="93bdd-358">**Mecanismo Antimalware, anexos seguros, regra filtrada**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-358">**Anti-malware engine, Safe Attachments, rule filtered**:</span></span>
  - <span data-ttu-id="93bdd-359">**Regra filtrada**: mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="93bdd-359">**Rule filtered**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="93bdd-360">**DMARC, representação, falsificação, phishing filtrado**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-360">**DMARC, impersonation, spoof, phish filtered**:</span></span>
  - <span data-ttu-id="93bdd-361">**DMARC**: mensagens filtradas devido à falha da mensagem de verificação de autenticação do DMARC.</span><span class="sxs-lookup"><span data-stu-id="93bdd-361">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="93bdd-362">**Detecção de URL acionamento**</span><span class="sxs-lookup"><span data-stu-id="93bdd-362">**URL detonation detection**</span></span>
- <span data-ttu-id="93bdd-363">**Filtrado por antispam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-363">**Anti-spam filtered**</span></span>
- <span data-ttu-id="93bdd-364">**ZAP removido**</span><span class="sxs-lookup"><span data-stu-id="93bdd-364">**ZAP removed**</span></span>
- <span data-ttu-id="93bdd-365">**Detecção por links seguros**</span><span class="sxs-lookup"><span data-stu-id="93bdd-365">**Detection by Safe Links**</span></span>

<span data-ttu-id="93bdd-366">Se você selecionar uma linha na tabela de dados, uma divisão adicional das contagens de email será mostrada no submenu.</span><span class="sxs-lookup"><span data-stu-id="93bdd-366">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

<span data-ttu-id="93bdd-367">**Exportar**:</span><span class="sxs-lookup"><span data-stu-id="93bdd-367">**Export**:</span></span>

<span data-ttu-id="93bdd-368">Ao clicar em **Exportar**, em **Opções** , você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="93bdd-368">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="93bdd-369">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-369">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="93bdd-370">**Detalhes (com dados nos últimos 30 dias)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-370">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="93bdd-371">Em **Data**, escolha um intervalo e clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-371">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="93bdd-372">Os dados dos filtros atuais serão exportados para um arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="93bdd-372">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="93bdd-373">Cada arquivo. csv exportado está limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="93bdd-373">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="93bdd-374">Se os dados contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="93bdd-374">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

 ![<span data-ttu-id="93bdd-375">Exibição de Tech no relatório de status do fluxo</span><span class="sxs-lookup"><span data-stu-id="93bdd-375">Tech view in the Mailflow status report</span></span> ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a><span data-ttu-id="93bdd-376">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="93bdd-376">Sent and received email report</span></span>

<span data-ttu-id="93bdd-377">O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom".</span><span class="sxs-lookup"><span data-stu-id="93bdd-377">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> <span data-ttu-id="93bdd-378">A diferença entre este relatório e o [relatório de status do fluxo](#mailflow-status-report) é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda. É importante entender que, se uma mensagem for enviada para cinco destinatários, contaremos como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-378">The difference between this report and the [Mailflow status report](#mailflow-status-report) is: this report doesn't include data about messages blocked by edge protection.It's important to understand that if a message is sent to five recipients we count it as one message.</span></span>

<span data-ttu-id="93bdd-379">O modo de exibição de agregação e o modo de exibição de detalhes do relatório permitem que 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="93bdd-379">The aggregate view and the detail view of the report allow for 90 days of filtering.</span></span>

<span data-ttu-id="93bdd-380">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **email enviado e recebido**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-380">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Sent and received email**.</span></span> <span data-ttu-id="93bdd-381">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-381">To go directly to the report, open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP>.</span></span>

![Widget email enviado e recebido no painel relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="93bdd-383">Exibição de relatório para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="93bdd-383">Report view for the Sent and received email report</span></span>

<span data-ttu-id="93bdd-384">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="93bdd-384">The following charts are available in the report view:</span></span>

- <span data-ttu-id="93bdd-385">**Divisão por: digite**: o gráfico mostra todas as categorias disponíveis:</span><span class="sxs-lookup"><span data-stu-id="93bdd-385">**Break down by: Type**: The chart shows all available categories:</span></span>

  - <span data-ttu-id="93bdd-386">**Total**</span><span class="sxs-lookup"><span data-stu-id="93bdd-386">**Total**</span></span>
  - <span data-ttu-id="93bdd-387">**Boa mensagem**</span><span class="sxs-lookup"><span data-stu-id="93bdd-387">**Good mail**</span></span>
  - <span data-ttu-id="93bdd-388">**Malware (anti-malware)** (EOP)</span><span class="sxs-lookup"><span data-stu-id="93bdd-388">**Malware (anti-malware)** (EOP)</span></span>
  - <span data-ttu-id="93bdd-389">**Detecções de spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-389">**Spam detections**</span></span>
  - <span data-ttu-id="93bdd-390">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="93bdd-390">**Rule messages**</span></span>
  - <span data-ttu-id="93bdd-391">**Malware avançado** (Microsoft defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="93bdd-391">**Advanced malware** (Microsoft Defender for Office 365)</span></span>

  <span data-ttu-id="93bdd-392">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="93bdd-392">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de tipo no relatório de email enviado e recebido](../../media/sent-and-received-email-report-type-view.png)

- <span data-ttu-id="93bdd-394">**Divisão por: direção**: o gráfico mostra os dados **total**, de **entrada** e de **saída** .</span><span class="sxs-lookup"><span data-stu-id="93bdd-394">**Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data.</span></span> <span data-ttu-id="93bdd-395">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.</span><span class="sxs-lookup"><span data-stu-id="93bdd-395">When you hover over a day (data point) in the chart, you can see details for that day.</span></span>

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- <span data-ttu-id="93bdd-397">**Aprofundar por** \> **Malware (Antimalware)**: esta seleção leva você para as [detecções de malware no relatório de email](view-email-security-reports.md#malware-detections-in-email-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-397">**Drill down by** \> **Malware (anti-malware)**: This selection takes you to the [Malware detections in email report](view-email-security-reports.md#malware-detections-in-email-report).</span></span>

- <span data-ttu-id="93bdd-398">**Aprofundar por** \> **Detecções de spam)**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).</span><span class="sxs-lookup"><span data-stu-id="93bdd-398">**Drill down by** \> **Spam detections)**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

<span data-ttu-id="93bdd-399">Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-399">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="93bdd-400">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="93bdd-400">**Start date** and **End date**</span></span>
- <span data-ttu-id="93bdd-401">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="93bdd-401">Direction values</span></span>
- <span data-ttu-id="93bdd-402">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="93bdd-402">Type values</span></span>

<span data-ttu-id="93bdd-403">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-403">To go back to the report view, click **View report**.</span></span>

### <a name="details-table-view-for-the-sent-and-received-email-report"></a><span data-ttu-id="93bdd-404">Exibição da tabela de detalhes para o relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="93bdd-404">Details table view for the Sent and received email report</span></span>

<span data-ttu-id="93bdd-405">Se você clicar em **Exibir tabela de detalhes** na tela **dividir por: direção** ou **dividir em: direção** , as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="93bdd-405">If you click **View details table** in the **Break down by: Direction** or **Break down by: Direction** view, the following information is shown:</span></span>

- <span data-ttu-id="93bdd-406">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-406">**Date (UTC)**</span></span>
- <span data-ttu-id="93bdd-407">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="93bdd-407">**Type**</span></span>
- <span data-ttu-id="93bdd-408">**Direção**</span><span class="sxs-lookup"><span data-stu-id="93bdd-408">**Direction**</span></span>
- <span data-ttu-id="93bdd-409">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="93bdd-409">**Message count**</span></span>

<span data-ttu-id="93bdd-410">Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="93bdd-410">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="93bdd-411">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="93bdd-411">**Start date** and **End date**</span></span>
- <span data-ttu-id="93bdd-412">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="93bdd-412">Direction values</span></span>
- <span data-ttu-id="93bdd-413">Valores de tipo</span><span class="sxs-lookup"><span data-stu-id="93bdd-413">Type values</span></span>

<span data-ttu-id="93bdd-414">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-414">To go back to the report view, click **View report**.</span></span>

## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="93bdd-415">Relatório de principais remetentes e destinatários</span><span class="sxs-lookup"><span data-stu-id="93bdd-415">Top senders and recipients report</span></span>

<span data-ttu-id="93bdd-416">O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes e destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="93bdd-416">The **Top senders and recipients** report is a pie chart showing your top email senders and recipients.</span></span>

<span data-ttu-id="93bdd-417">Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **os principais remetentes e destinatários**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-417">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top senders and recipients**.</span></span> <span data-ttu-id="93bdd-418">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .</span><span class="sxs-lookup"><span data-stu-id="93bdd-418">To go directly to the report, open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP>.</span></span>

![Widget principais remetentes e destinatários no painel relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="93bdd-420">Exibição de relatório para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="93bdd-420">Report view for the Top senders and recipient report</span></span>

<span data-ttu-id="93bdd-421">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="93bdd-421">The following charts are available in the report view:</span></span>

- <span data-ttu-id="93bdd-422">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="93bdd-422">**Show data for \> Top mail senders**</span></span>
- <span data-ttu-id="93bdd-423">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="93bdd-423">**Show data for \> Top mail recipients**</span></span>
- <span data-ttu-id="93bdd-424">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-424">**Show data for \> Top spam recipients**</span></span>
- <span data-ttu-id="93bdd-425">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="93bdd-425">**Show data for \> Top malware recipients** (EOP)</span></span>
- <span data-ttu-id="93bdd-426">**Mostrar dados para \> destinatários de malware principais (defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-426">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

<span data-ttu-id="93bdd-427">A composição do gráfico de pizza é alterada com base nessas seleções.</span><span class="sxs-lookup"><span data-stu-id="93bdd-427">The composition of the pie chart changes based on these selections.</span></span>

<span data-ttu-id="93bdd-428">Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.</span><span class="sxs-lookup"><span data-stu-id="93bdd-428">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>

<span data-ttu-id="93bdd-429">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-429">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

![Gráfico de pizza no modo de exibição de relatório no relatório de remetentes e destinatários principais](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a><span data-ttu-id="93bdd-431">Exibição da tabela de detalhes para os principais remetentes e o relatório de destinatários</span><span class="sxs-lookup"><span data-stu-id="93bdd-431">Details table view for the Top senders and recipient report</span></span>

<span data-ttu-id="93bdd-432">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="93bdd-432">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="93bdd-433">**Mostrar dados para os \> principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="93bdd-433">**Show data for \> Top mail senders**</span></span>

  - <span data-ttu-id="93bdd-434">**Principais remetentes de email**</span><span class="sxs-lookup"><span data-stu-id="93bdd-434">**Top mail senders**</span></span>
  - <span data-ttu-id="93bdd-435">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-435">**Count**</span></span>

- <span data-ttu-id="93bdd-436">**Mostrar dados para \> destinatários de email principais**</span><span class="sxs-lookup"><span data-stu-id="93bdd-436">**Show data for \> Top mail recipients**</span></span>

  - <span data-ttu-id="93bdd-437">**Principais destinatários de email**</span><span class="sxs-lookup"><span data-stu-id="93bdd-437">**Top mail recipients**</span></span>
  - <span data-ttu-id="93bdd-438">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-438">**Count**</span></span>

- <span data-ttu-id="93bdd-439">**Mostrar dados para \> os principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-439">**Show data for \> Top spam recipients**</span></span>

  - <span data-ttu-id="93bdd-440">**Principais destinatários de spam**</span><span class="sxs-lookup"><span data-stu-id="93bdd-440">**Top spam recipients**</span></span>
  - <span data-ttu-id="93bdd-441">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-441">**Count**</span></span>

- <span data-ttu-id="93bdd-442">**Mostrar dados para \> Principais destinatários de malware** (EOP)</span><span class="sxs-lookup"><span data-stu-id="93bdd-442">**Show data for \> Top malware recipients** (EOP)</span></span>

  - <span data-ttu-id="93bdd-443">**Principais destinatários de malware**</span><span class="sxs-lookup"><span data-stu-id="93bdd-443">**Top malware recipients**</span></span>
  - <span data-ttu-id="93bdd-444">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-444">**Count**</span></span>

- <span data-ttu-id="93bdd-445">**Mostrar dados para \> destinatários de malware principais (defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-445">**Show data for \> Top malware recipients (Defender for Office 365)**</span></span>

  - <span data-ttu-id="93bdd-446">**Principais destinatários de malware (defender para Office 365)**</span><span class="sxs-lookup"><span data-stu-id="93bdd-446">**Top malware recipients (Defender for Office 365)**</span></span>
  - <span data-ttu-id="93bdd-447">**Count**</span><span class="sxs-lookup"><span data-stu-id="93bdd-447">**Count**</span></span>

<span data-ttu-id="93bdd-448">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-448">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="93bdd-449">Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="93bdd-449">To go back to the report view, click **View report**.</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="93bdd-450">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="93bdd-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="93bdd-451">Para exibir e usar os relatórios, você precisa ser membro do grupo de função especificado no centro de conformidade e segurança & **e** no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="93bdd-451">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="93bdd-452">No centro de conformidade & segurança, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="93bdd-452">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="93bdd-453">– Gerenciamento de organização-administrador de segurança (você também pode fazer isso no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) -leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="93bdd-453">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="93bdd-454">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="93bdd-454">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="93bdd-455">No Exchange Online, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="93bdd-455">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="93bdd-456">– Gerenciamento de organização – gerenciamento de organização somente de exibição-somente os destinatários do gerenciamento de conformidade</span><span class="sxs-lookup"><span data-stu-id="93bdd-456">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="93bdd-457">Para obter mais informações, consulte [permissões no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gerenciar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="93bdd-457">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="related-topics"></a><span data-ttu-id="93bdd-458">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="93bdd-458">Related topics</span></span>

[<span data-ttu-id="93bdd-459">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="93bdd-459">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="93bdd-460">Insights de fluxo de emails no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="93bdd-460">Mail flow insights in the Security & Compliance Center</span></span>](mail-flow-insights-v2.md)

[<span data-ttu-id="93bdd-461">Exibir relatórios de segurança de email no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="93bdd-461">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="93bdd-462">Exibir relatórios do Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="93bdd-462">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-atp.md)
