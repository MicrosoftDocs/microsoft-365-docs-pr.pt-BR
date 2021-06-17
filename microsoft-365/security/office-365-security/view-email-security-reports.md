---
title: Exibir relatórios de segurança de email no portal do Microsoft 365 Defender
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Saiba como encontrar e usar relatórios de segurança de email para sua organização. Os relatórios de segurança de email estão disponíveis no portal do Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985135"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="66935-104">Exibir relatórios de segurança de email no portal do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66935-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="66935-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="66935-105">**Applies to**</span></span>
- [<span data-ttu-id="66935-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="66935-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="66935-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="66935-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="66935-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66935-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="66935-109">Vários relatórios estão disponíveis no portal do Microsoft 365 Defender para ajudá-lo a ver como os recursos de segurança de email, como anti-spam, anti-malware e recursos de criptografia no Microsoft 365 estão protegendo sua <https://security.microsoft.com> organização.</span><span class="sxs-lookup"><span data-stu-id="66935-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="66935-110">Se você tiver as permissões [necessárias,](#what-permissions-are-needed-to-view-these-reports)poderá exibir esses relatórios no portal  do Microsoft 365 Defender, indo para Relatórios Email & colaboração \>  \> **Email & relatórios de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-111">Para ir diretamente para a página Relatórios de **colaboração & email,** abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="66935-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & relatórios de colaboração de email no portal do Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="66935-113">Alguns dos relatórios na página Relatórios de & **de** colaboração exigem o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="66935-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="66935-114">Para obter informações sobre esses relatórios, consulte [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="66935-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="66935-115">Os relatórios relacionados ao fluxo de emails agora estão no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="66935-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="66935-116">Para obter mais informações sobre esses relatórios, consulte [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="66935-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="66935-117">Relatório de usuários comprometidos</span><span class="sxs-lookup"><span data-stu-id="66935-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="66935-118">Este relatório está disponível em organizações do Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="66935-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="66935-119">Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="66935-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="66935-120">O **relatório Usuários Comprometidos** mostra o número de contas de usuário que foram marcadas como **Suspeitas** ou **Restritas** nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="66935-121">As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas.</span><span class="sxs-lookup"><span data-stu-id="66935-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="66935-122">Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="66935-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="66935-123">Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="66935-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget de usuários comprometidos na página Relatórios de colaboração & email](../../media/compromised-users-report-widget.png)

<span data-ttu-id="66935-125">A exibição agregada mostra os dados dos últimos 90 dias e a exibição de detalhes mostra os dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="66935-126">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-127">Em **Usuários comprometidos,** clique **em Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="66935-128">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="66935-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="66935-129">Depois de clicar em **Exibir** detalhes, você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="66935-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="66935-130">**Data (UTC)**: Data **de início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="66935-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="66935-131">**Atividade**:</span><span class="sxs-lookup"><span data-stu-id="66935-131">**Activity**:</span></span>
  - <span data-ttu-id="66935-132">**Suspeito**: a conta de usuário enviou emails suspeitos e corre o risco de ser restringida ao envio de emails.</span><span class="sxs-lookup"><span data-stu-id="66935-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="66935-133">**Restrito**: a conta de usuário foi restrita ao envio de emails devido a padrões altamente suspeitos.</span><span class="sxs-lookup"><span data-stu-id="66935-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="66935-134">Quando terminar a filtragem, clique em **Aplicar ou** **Cancelar.**</span><span class="sxs-lookup"><span data-stu-id="66935-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![Exibir relatório no relatório Usuários Comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="66935-136">Na tabela abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="66935-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="66935-137">**Hora da criação**</span><span class="sxs-lookup"><span data-stu-id="66935-137">**Creation time**</span></span>
- <span data-ttu-id="66935-138">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="66935-138">**User ID**</span></span>
- <span data-ttu-id="66935-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="66935-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="66935-140">Relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="66935-140">Exchange transport rule report</span></span>

<span data-ttu-id="66935-141">O **relatório de regra de** transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="66935-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="66935-142">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-143">Na **regra de transporte do Exchange,** clique em Exibir **detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="66935-144">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="66935-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget de regra de transporte do Exchange na página Relatórios de colaboração & email](../../media/transport-rule-report-widget.png)

<span data-ttu-id="66935-146">Depois de clicar **em Exibir detalhes,** os seguintes gráficos e dados estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="66935-147">**Exibir dados por regras de transporte do** \> Exchange **Divisão de gráficos por Direção**: este  gráfico mostra o número **de** mensagens de Entrada e Saída que foram afetadas pelas regras de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="66935-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="66935-148">**Exibir dados por regras de transporte do** \> Exchange **Divisão de gráficos por Gravidade**: este gráfico mostra o número de mensagens de Alta **gravidade,** Gravidade **média** e **Baixa gravidade.**</span><span class="sxs-lookup"><span data-stu-id="66935-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="66935-149">Você definirá o nível de gravidade como uma ação na regra (**Audite essa** regra com nível de gravidade ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="66935-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="66935-150">Para obter mais informações, consulte [Ações de regra de fluxo de email no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="66935-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="66935-151">**Exibir dados por regras de transporte do Exchange** \> DLP **Divisão de gráficos** por Direção  : este  gráfico mostra o número de mensagens de entrada e saída que foram afetadas pelas regras de fluxo de emails de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="66935-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="66935-152">**Exibir dados por regras de transporte do Exchange** \> DLP **Divisão de gráficos por Severidade**: Este ponto de exibição mostra o número de mensagens de alta **gravidade,** gravidade média e Baixa gravidade que foram afetadas pelas regras de fluxo de emails DLP. </span><span class="sxs-lookup"><span data-stu-id="66935-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="66935-153">Para **Exibir dados por seleções** de regras de transporte do Exchange, as seguintes informações são mostradas na tabela de detalhes abaixo do gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="66935-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-154">**Date**</span></span>
- <span data-ttu-id="66935-155">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="66935-155">**Transport rule**</span></span>
- <span data-ttu-id="66935-156">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-156">**Subject**</span></span>
- <span data-ttu-id="66935-157">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="66935-157">**Sender address**</span></span>
- <span data-ttu-id="66935-158">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="66935-158">**Recipient address**</span></span>
- <span data-ttu-id="66935-159">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="66935-159">**Severity**</span></span>
- <span data-ttu-id="66935-160">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-160">**Direction**</span></span>

<span data-ttu-id="66935-161">Para **exibir dados por seleções** de regras de transporte do Exchange DLP, as seguintes informações são mostradas na tabela de detalhes abaixo do gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="66935-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-162">**Date**</span></span>
- <span data-ttu-id="66935-163">**Política DLP**</span><span class="sxs-lookup"><span data-stu-id="66935-163">**DLP policy**</span></span>
- <span data-ttu-id="66935-164">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="66935-164">**Transport rule**</span></span>
- <span data-ttu-id="66935-165">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-165">**Subject**</span></span>
- <span data-ttu-id="66935-166">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="66935-166">**Sender address**</span></span>
- <span data-ttu-id="66935-167">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="66935-167">**Recipient address**</span></span>
- <span data-ttu-id="66935-168">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="66935-168">**Severity**</span></span>
- <span data-ttu-id="66935-169">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-169">**Direction**</span></span>

<span data-ttu-id="66935-170">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="66935-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="66935-171">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="66935-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="66935-172">**Direção**: **Saída** e **Entrada**</span><span class="sxs-lookup"><span data-stu-id="66935-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="66935-173">**Severidade**: **alta gravidade,** **gravidade média** e baixa **gravidade**</span><span class="sxs-lookup"><span data-stu-id="66935-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="66935-175">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="66935-175">Mailflow status report</span></span>

<span data-ttu-id="66935-176">O relatório de status de **fluxo** de emails é um relatório inteligente que mostra informações sobre emails de entrada e saída, detecções de spam, malware, email identificado como "bom" e informações sobre emails permitidos ou bloqueados na borda.</span><span class="sxs-lookup"><span data-stu-id="66935-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="66935-177">Este é o único relatório que contém informações de proteção de borda e mostra a quantos emails são bloqueados antes de serem permitidos no serviço para avaliação pela Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="66935-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="66935-178">É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="66935-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="66935-179">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-180">No **resumo de status do fluxo de emails,** clique em Exibir **detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="66935-181">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="66935-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget de resumo de status de fluxo de email na página Relatórios de colaboração & email](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="66935-183">Exibição de tipo para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="66935-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="66935-184">Quando você abre o relatório, a guia **Tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="66935-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="66935-185">Por padrão, esse modo de exibição contém um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="66935-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="66935-186">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="66935-187">**Direção do email**:</span><span class="sxs-lookup"><span data-stu-id="66935-187">**Mail direction**:</span></span>
  - <span data-ttu-id="66935-188">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="66935-188">**Inbound**</span></span>
  - <span data-ttu-id="66935-189">**Saída**</span><span class="sxs-lookup"><span data-stu-id="66935-189">**Outbound**</span></span>
  - <span data-ttu-id="66935-190">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="66935-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="66935-191">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)</span><span class="sxs-lookup"><span data-stu-id="66935-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="66935-192">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="66935-192">**Type**:</span></span>
  - <span data-ttu-id="66935-193">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="66935-193">**Good mail**</span></span>
  - <span data-ttu-id="66935-194">**Malware**</span><span class="sxs-lookup"><span data-stu-id="66935-194">**Malware**</span></span>
  - <span data-ttu-id="66935-195">**Spam**</span><span class="sxs-lookup"><span data-stu-id="66935-195">**Spam**</span></span>
  - <span data-ttu-id="66935-196">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="66935-196">**Edge protection**</span></span>
  - <span data-ttu-id="66935-197">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="66935-197">**Rule messages**</span></span>
  - <span data-ttu-id="66935-198">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="66935-198">**Phishing email**</span></span>
- <span data-ttu-id="66935-199">**Domínio**: **Todos**</span><span class="sxs-lookup"><span data-stu-id="66935-199">**Domain**: **All**</span></span>

<span data-ttu-id="66935-200">O gráfico é organizado pelos valores **Type.**</span><span class="sxs-lookup"><span data-stu-id="66935-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="66935-201">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="66935-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="66935-202">A tabela de dados contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="66935-202">The data table contains the following information:</span></span>

- <span data-ttu-id="66935-203">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-203">**Direction**</span></span>
- <span data-ttu-id="66935-204">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66935-204">**Type**</span></span>
- <span data-ttu-id="66935-205">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="66935-205">**24 hours**</span></span>
- <span data-ttu-id="66935-206">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="66935-206">**3 days**</span></span>
- <span data-ttu-id="66935-207">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="66935-207">**7 days**</span></span>
- <span data-ttu-id="66935-208">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="66935-208">**15 days**</span></span>
- <span data-ttu-id="66935-209">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="66935-209">**30 days**</span></span>

<span data-ttu-id="66935-210">Se você clicar **em Escolher uma categoria para obter** mais detalhes, você poderá selecionar entre os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="66935-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="66935-211">**Email de phishing**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="66935-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="66935-212">**Malware no email**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="66935-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="66935-213">**Detecções de** spam: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="66935-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="66935-214">**Spam bloqueado de borda:** essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="66935-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="66935-215">Exportar do tipo de exibição</span><span class="sxs-lookup"><span data-stu-id="66935-215">Export from Type view</span></span>

<span data-ttu-id="66935-216">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="66935-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="66935-217">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="66935-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="66935-218">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="66935-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="66935-219">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="66935-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Type view in the Mailflow status report](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="66935-221">Exibição de direção para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="66935-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="66935-222">Se você clicar na guia **Direção,** os mesmos filtros padrão do modo de exibição **Tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="66935-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="66935-223">O gráfico é organizado pelos **valores Direction.**</span><span class="sxs-lookup"><span data-stu-id="66935-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="66935-224">Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="66935-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="66935-225">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="66935-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="66935-226">A tabela de dados contém as mesmas informações do modo **de exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="66935-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="66935-227">A **opção Escolher uma categoria para obter** mais detalhes sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="66935-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="66935-228">Exportar do ponto de vista De direção</span><span class="sxs-lookup"><span data-stu-id="66935-228">Export from Direction view</span></span>

<span data-ttu-id="66935-229">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="66935-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="66935-230">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="66935-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="66935-231">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="66935-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="66935-232">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="66935-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Exibição de direção no relatório de status de fluxo de emails](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="66935-234">Exibição de funil para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="66935-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="66935-235">A **exibição** Funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="66935-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="66935-236">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="66935-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="66935-237">Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="66935-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="66935-238">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="66935-239">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="66935-239">**Direction**:</span></span>

  - <span data-ttu-id="66935-240">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="66935-240">**Inbound**</span></span>
  - <span data-ttu-id="66935-241">**Saída**</span><span class="sxs-lookup"><span data-stu-id="66935-241">**Outbound**</span></span>
  - <span data-ttu-id="66935-242">**Intra-org**: esta contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de Entrada e Saída).</span><span class="sxs-lookup"><span data-stu-id="66935-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="66935-243">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="66935-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="66935-244">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="66935-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="66935-245">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="66935-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="66935-246">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="66935-246">**Total email**</span></span>
- <span data-ttu-id="66935-247">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="66935-247">**Email after edge protection**</span></span>
- <span data-ttu-id="66935-248">**Regra de email após transporte** (regra de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="66935-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="66935-249">**Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="66935-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="66935-250">**Email após anti-phishing, reputação de URL, representação de marca, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="66935-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="66935-251">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="66935-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="66935-252">**Email após a representação de usuário e domínio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-253">**Email após a detonação de arquivo e URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-254">**Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique na URL)**</span><span class="sxs-lookup"><span data-stu-id="66935-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="66935-255"><sup>\*</sup>Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="66935-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="66935-256">Para exibir o email filtrado por EOP ou Defender Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="66935-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="66935-257">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="66935-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="66935-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-258">**Date**</span></span>
- <span data-ttu-id="66935-259">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="66935-259">**Total email**</span></span>
- <span data-ttu-id="66935-260">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="66935-260">**Edge protection**</span></span>
- <span data-ttu-id="66935-261">**Anti-malware, reputação de arquivo, bloco de tipo de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="66935-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="66935-262">**Reputação do** arquivo : Mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66935-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="66935-263">**Bloco de tipo de** arquivo : Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="66935-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="66935-264">**Anti-phish, reputação de URL, representação de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="66935-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="66935-265">**Reputação da URL**: Mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="66935-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="66935-266">**Representação de marca**: Mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.</span><span class="sxs-lookup"><span data-stu-id="66935-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="66935-267">**Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence ou a um domínio que o remetente da mensagem não possui.</span><span class="sxs-lookup"><span data-stu-id="66935-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="66935-268">**Anti-spam, filtragem de email em massa:**</span><span class="sxs-lookup"><span data-stu-id="66935-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="66935-269">**Filtragem de emails** em massa: Mensagens filtradas com base no limite de bcl (nível de reclamação em massa) em uma política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="66935-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="66935-270">**Representação de usuário e domínio (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="66935-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="66935-271">**Representação do** usuário : Mensagens filtradas devido a uma tentativa de representar um usuário (remetente de mensagem) definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="66935-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="66935-272">**Representação de domínio**: Mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="66935-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="66935-273">**Detonação de arquivo e URL (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="66935-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="66935-274">**Detonação de** arquivo : Mensagens filtradas por uma política Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="66935-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="66935-275">**Detonação de URL**: Mensagem filtrada por uma política Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="66935-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="66935-276">**Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: Limpeza automática zero hora (ZAP) para malware, spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="66935-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="66935-277">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="66935-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="66935-278">Exportar do exibição Funil</span><span class="sxs-lookup"><span data-stu-id="66935-278">Export from Funnel view</span></span>

<span data-ttu-id="66935-279">Depois de clicar **em Exportar** **em Opções,** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="66935-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="66935-280">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="66935-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="66935-281">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="66935-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="66935-282">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="66935-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="66935-283">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="66935-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="66935-284">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="66935-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="66935-285">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="66935-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Exibição de funil no relatório de status de fluxo de emails](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="66935-287">Exibição técnica do relatório de status mailflow</span><span class="sxs-lookup"><span data-stu-id="66935-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="66935-288">O **modo de exibição** Tech é semelhante ao modo de exibição **Funil,** fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="66935-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="66935-289">No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="66935-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="66935-290">Se você clicar na **guia Modo de** Exibição de Tecnologia, por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="66935-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="66935-291">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="66935-292">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="66935-292">**Direction**:</span></span>

  - <span data-ttu-id="66935-293">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="66935-293">**Inbound**</span></span>
  - <span data-ttu-id="66935-294">**Saída**</span><span class="sxs-lookup"><span data-stu-id="66935-294">**Outbound**</span></span>
  - <span data-ttu-id="66935-295">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="66935-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="66935-296">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de Entrada e Saída)</span><span class="sxs-lookup"><span data-stu-id="66935-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="66935-297">A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="66935-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="66935-298">Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.</span><span class="sxs-lookup"><span data-stu-id="66935-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="66935-299">Este gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="66935-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="66935-300">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="66935-300">**Total email**</span></span>
- <span data-ttu-id="66935-301">**Permitir borda** e **Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="66935-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="66935-302">**Regra de transporte permitir** e **regra de transporte filtrada** (regras de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="66935-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="66935-303">**Não malware,** **Cofre detecção de anexos** <sup>\*</sup> e detecção de mecanismo **anti-malware**</span><span class="sxs-lookup"><span data-stu-id="66935-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="66935-304">**Não phish**, **falha de DMARC,** detecção **de representação,** detecção de <sup>\*</sup> **spoof** e **detecção de phishing**</span><span class="sxs-lookup"><span data-stu-id="66935-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="66935-305">**Nenhuma detecção com detonação de URL** e detecção **de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-306">**Não spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="66935-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="66935-307">**Email não mal-intencionado,** **Cofre de links** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="66935-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="66935-308"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="66935-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="66935-309">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="66935-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="66935-310">A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="66935-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="66935-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-311">**Date**</span></span>
- <span data-ttu-id="66935-312">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="66935-312">**Total email**</span></span>
- <span data-ttu-id="66935-313">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="66935-313">**Edge filtered**</span></span>
- <span data-ttu-id="66935-314">**Mensagens de regra**: Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="66935-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="66935-315">**Mecanismo anti-malware**, **Cofre Anexos** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="66935-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="66935-316">**DMARC, representação** <sup>\*</sup> , **spoof**, **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="66935-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="66935-317">**DMARC**: Mensagens filtradas devido à falha da mensagem em sua verificação de autenticação DMARC.</span><span class="sxs-lookup"><span data-stu-id="66935-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="66935-318">**Detecção de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-319">**Anti-spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="66935-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="66935-320">**ZAP removido**</span><span class="sxs-lookup"><span data-stu-id="66935-320">**ZAP removed**</span></span>
- <span data-ttu-id="66935-321">**Detecção por Cofre Links**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="66935-322"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="66935-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="66935-323">Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="66935-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="66935-324">Exportar do ponto de vista tech</span><span class="sxs-lookup"><span data-stu-id="66935-324">Export from Tech view</span></span>

<span data-ttu-id="66935-325">Ao clicar em **Exportar**, em **Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="66935-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="66935-326">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="66935-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="66935-327">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="66935-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="66935-328">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="66935-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="66935-329">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="66935-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="66935-330">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="66935-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="66935-331">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="66935-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Exibição técnica no relatório de status do fluxo de mensagens](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="66935-333">Relatório de detecções de malware</span><span class="sxs-lookup"><span data-stu-id="66935-333">Malware detections report</span></span>

<span data-ttu-id="66935-334">O **relatório de detecções** de malware mostra informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado por Proteção do Exchange Online ou EOP).</span><span class="sxs-lookup"><span data-stu-id="66935-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="66935-335">Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="66935-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="66935-336">O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="66935-337">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-338">Em **Malware detectado no email,** clique em Exibir **detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="66935-339">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="66935-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Detecções de malware no widget de email na página Relatórios de colaboração & email](../../media/malware-detections-widget.png)

<span data-ttu-id="66935-341">Depois de clicar **em Exibir detalhes,** você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando:</span><span class="sxs-lookup"><span data-stu-id="66935-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="66935-342">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-343">**Direção**: **Entrada** e **Saída**</span><span class="sxs-lookup"><span data-stu-id="66935-343">**Direction**: **Inbound** and **Outbound**</span></span>

![Exibir relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

<span data-ttu-id="66935-345">Na tabela de detalhes abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="66935-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="66935-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-346">**Date**</span></span>
- <span data-ttu-id="66935-347">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="66935-347">**Sender address**</span></span>
- <span data-ttu-id="66935-348">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="66935-348">**Recipient address**</span></span>
- <span data-ttu-id="66935-349">**ID da** mensagem : disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="66935-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="66935-350">Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="66935-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="66935-351">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-351">**Subject**</span></span>
- <span data-ttu-id="66935-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="66935-352">**Filename**</span></span>
- <span data-ttu-id="66935-353">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="66935-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="66935-354">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="66935-354">Mail latency report</span></span>

<span data-ttu-id="66935-355">O **relatório de latência de** email no Defender para Office 365 contém informações sobre a entrega de emails e a latência de detonação experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="66935-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="66935-356">Para obter mais informações, consulte [Relatório de latência de email](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="66935-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="66935-357">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="66935-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="66935-358">O **relatório de detecções de spam** desaparecerá em 30 de junho de 2021.</span><span class="sxs-lookup"><span data-stu-id="66935-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="66935-359">As mesmas informações estão disponíveis no relatório de [status de proteção contra ameaças.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="66935-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="66935-360">Relatório de detecções de spoof</span><span class="sxs-lookup"><span data-stu-id="66935-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="66935-361">O relatório aprimorado de detecções de Spoof conforme descrito neste artigo está em Visualização, está sujeito a alterações e não está disponível em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="66935-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="66935-362">A versão mais antiga do relatório mostra apenas **Emails bons e** **capturados como spam.**</span><span class="sxs-lookup"><span data-stu-id="66935-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="66935-363">O **relatório de detecções Spoof** mostra informações sobre mensagens que foram bloqueadas ou permitidas devido à fraude.</span><span class="sxs-lookup"><span data-stu-id="66935-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="66935-364">Para obter mais informações sobre a spoofing, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="66935-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="66935-365">A exibição agregada do relatório permite 45 dias de filtragem, enquanto a exibição de detalhes permite apenas <sup>\*</sup> dez dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="66935-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="66935-366"><sup>\*</sup> Eventualmente, você poderá usar até 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="66935-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="66935-367">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-368">Em **Detecções de Spoof,** clique **em Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="66935-369">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="66935-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget de detecções de spoof na página Relatórios de colaboração & email](../../media/spoof-detections-widget.png)

<span data-ttu-id="66935-371">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens falsas foram detectadas e por quê.</span><span class="sxs-lookup"><span data-stu-id="66935-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="66935-372">Depois de clicar em **Exibir detalhes,** você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="66935-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="66935-373">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-374">**Resultado**:</span><span class="sxs-lookup"><span data-stu-id="66935-374">**Result**:</span></span>
  - <span data-ttu-id="66935-375">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="66935-375">**Pass**</span></span>
  - <span data-ttu-id="66935-376">**Fail**</span><span class="sxs-lookup"><span data-stu-id="66935-376">**Fail**</span></span>
  - <span data-ttu-id="66935-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="66935-377">**SoftPass**</span></span>
  - <span data-ttu-id="66935-378">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="66935-378">**None**</span></span>
  - <span data-ttu-id="66935-379">**Outros**</span><span class="sxs-lookup"><span data-stu-id="66935-379">**Other**</span></span>
- <span data-ttu-id="66935-380">**Tipo de spoof**: **Interno** e **Externo**</span><span class="sxs-lookup"><span data-stu-id="66935-380">**Spoof type**: **Internal** and **External**</span></span>

![Página de relatório de email de spoof no portal Microsoft 365 Defender página](../../media/spoof-detections-report-page.png)

<span data-ttu-id="66935-382">Na tabela abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="66935-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="66935-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-383">**Date**</span></span>
- <span data-ttu-id="66935-384">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="66935-384">**Spoofed user**</span></span>
- <span data-ttu-id="66935-385">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="66935-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="66935-386">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="66935-386">**Spoof type**</span></span>
- <span data-ttu-id="66935-387">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="66935-387">**Result**</span></span>
- <span data-ttu-id="66935-388">**Código de resultado**</span><span class="sxs-lookup"><span data-stu-id="66935-388">**Result code**</span></span>
- <span data-ttu-id="66935-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="66935-389">**SPF**</span></span>
- <span data-ttu-id="66935-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="66935-390">**DKIM**</span></span>
- <span data-ttu-id="66935-391">**DMARCDMARC**</span><span class="sxs-lookup"><span data-stu-id="66935-391">**DMARC**</span></span>
- <span data-ttu-id="66935-392">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="66935-392">**Message count**</span></span>

<span data-ttu-id="66935-393">Para obter mais informações sobre códigos de resultados de autenticação composta, consulte [Headers de mensagem anti-spam em Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="66935-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="66935-394">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="66935-394">Threat protection status report</span></span>

<span data-ttu-id="66935-395">O **relatório de status de** proteção contra ameaças está disponível no EOP e no Defender para Office 365; no entanto, os relatórios contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="66935-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="66935-396">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectados no email, mas não informações sobre arquivos [mal-intencionados detectados](mdo-for-spo-odb-and-teams.md)por Cofre Anexos para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="66935-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="66935-397">O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) bloqueados pelo mecanismo anti-malware, zap (limpeza automática zero [hora)](zero-hour-auto-purge.md)e o Defender para recursos do Office 365, como [links Cofre,](safe-links.md) [anexos Cofre](safe-attachments.md)e recursos de proteção contra representação em políticas [anti-phishing.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="66935-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="66935-398">Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="66935-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="66935-399">**Observação**: é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="66935-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="66935-400">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-401">Em **Status de proteção contra ameaças,** clique em Exibir **detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="66935-402">Para ir diretamente ao relatório, abra uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="66935-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="66935-403">Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="66935-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="66935-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="66935-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget de status de proteção contra ameaças na página Relatórios de colaboração & email](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="66935-406">Por padrão, depois de clicar em **Exibir detalhes,** o gráfico mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="66935-407">Se você clicar **em Filtrar**, você poderá selecionar um intervalo de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias).</span><span class="sxs-lookup"><span data-stu-id="66935-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="66935-408">A tabela de detalhes permite a filtragem por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="66935-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="66935-409">As exibições disponíveis são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="66935-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="66935-410">Exibir dados por Visão Geral</span><span class="sxs-lookup"><span data-stu-id="66935-410">View data by Overview</span></span>

![Visão geral no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="66935-412">Na **exibição Exibir dados por visão** geral, as seguintes informações de detecção são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="66935-413">**Malware de email**</span><span class="sxs-lookup"><span data-stu-id="66935-413">**Email malware**</span></span>
- <span data-ttu-id="66935-414">**Phishing de email**</span><span class="sxs-lookup"><span data-stu-id="66935-414">**Email phish**</span></span>
- <span data-ttu-id="66935-415">**Malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="66935-415">**Content malware**</span></span>

<span data-ttu-id="66935-416">Nenhuma tabela de detalhes está disponível abaixo do gráfico.</span><span class="sxs-lookup"><span data-stu-id="66935-416">No details table is available below the chart.</span></span>

<span data-ttu-id="66935-417">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-418">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-419">**Detecção**: **malware de email,** **phishing** de email ou **malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="66935-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="66935-420">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-421">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-422">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-423">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-423">**Direction**</span></span>
- <span data-ttu-id="66935-424">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-424">**Domain**</span></span>
- <span data-ttu-id="66935-425">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-425">**Policy type**</span></span>

<span data-ttu-id="66935-426">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="66935-427">Exibir dados por Email \> Phish and Chart breakdown by Detection Technology</span><span class="sxs-lookup"><span data-stu-id="66935-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Exibição de tecnologia de detecção para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="66935-429">Na **exibição Exibir dados por \> phishing** de email e **gráfico** por tecnologia de detecção, as seguintes informações são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="66935-430">**Reputação mal-intencionada** da URL : reputação de URL mal-intencionada gerada pelo <sup>\*</sup> Defender para Office 365 detonações em outros Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="66935-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="66935-431">**Filtro avançado**: sinais de phishing com base no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="66935-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="66935-432">**Filtro geral**: sinais de phishing com base em regras de analista.</span><span class="sxs-lookup"><span data-stu-id="66935-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="66935-433">**Spoof intra-org**: O remetente está tentando fazer a spoof do domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="66935-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="66935-434">**Spoof external domain**: O remetente está tentando fazer a spoof de algum outro domínio.</span><span class="sxs-lookup"><span data-stu-id="66935-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="66935-435">**Spoof DMARC**: Falha de autenticação DMARC em mensagens.</span><span class="sxs-lookup"><span data-stu-id="66935-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="66935-436">**Marca de representação**: Representação de marcas conhecidas com base em senders.</span><span class="sxs-lookup"><span data-stu-id="66935-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="66935-437">**Detecção de análise mista**</span><span class="sxs-lookup"><span data-stu-id="66935-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="66935-438">**Reputação de arquivos**</span><span class="sxs-lookup"><span data-stu-id="66935-438">**File reputation**</span></span>
- <span data-ttu-id="66935-439">**Correspondência de impressão digital**</span><span class="sxs-lookup"><span data-stu-id="66935-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="66935-440">**Reputação de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-441">**Detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-442">**Usuário de representação**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-443">**Domínio de representação** <sup>\*</sup> : Representação de domínios que o cliente possui ou define.</span><span class="sxs-lookup"><span data-stu-id="66935-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="66935-444">**Representação de inteligência de caixa de** correio : Representação de usuários <sup>\*</sup> definidos pelo administrador ou aprendidos por meio da inteligência da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="66935-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="66935-445">**Detonação de arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-446">**Campanha**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="66935-447">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-448">**Date**</span></span>
- <span data-ttu-id="66935-449">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-449">**Subject**</span></span>
- <span data-ttu-id="66935-450">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-450">**Sender**</span></span>
- <span data-ttu-id="66935-451">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-451">**Recipients**</span></span>
- <span data-ttu-id="66935-452">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-452">**Detected by**</span></span>
- <span data-ttu-id="66935-453">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-453">**Delivery Status**</span></span>
- <span data-ttu-id="66935-454">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="66935-454">**Source of Compromise**</span></span>
- <span data-ttu-id="66935-455">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-455">**Tags**</span></span>

<span data-ttu-id="66935-456">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-457">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-458">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="66935-458">**Detection**</span></span>
- <span data-ttu-id="66935-459">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-460">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-460">**Direction**</span></span>
- <span data-ttu-id="66935-461">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-462">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-463">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-463">**Domain**</span></span>
- <span data-ttu-id="66935-464">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-464">**Policy type**</span></span>
- <span data-ttu-id="66935-465">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="66935-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="66935-466">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-466">**Recipients**</span></span>

<span data-ttu-id="66935-467">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="66935-468">Exibir dados por \> Malware de Email e Divisão de Gráficos pela Tecnologia de Detecção</span><span class="sxs-lookup"><span data-stu-id="66935-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Exibição de tecnologia de detecção para malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="66935-470">Na **exibição Exibir dados por \> Malware** de Email e **Gráfico** pela Tecnologia de Detecção, as seguintes informações são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="66935-471">**Detonação de** <sup>\*</sup> arquivo : detecção por Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="66935-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="66935-472">**Reputação de detonação de** <sup>\*</sup> arquivo : toda a reputação de arquivo mal-intencionado gerada pelo Defender para Office 365 detonações.</span><span class="sxs-lookup"><span data-stu-id="66935-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="66935-473">**Reputação de arquivos**</span><span class="sxs-lookup"><span data-stu-id="66935-473">**File reputation**</span></span>
- <span data-ttu-id="66935-474">**Mecanismo anti-malware** <sup>\*</sup> : Detecção de mecanismos anti-malware.</span><span class="sxs-lookup"><span data-stu-id="66935-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="66935-475">Bloco de tipo de arquivo de **política anti-malware**: São mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="66935-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="66935-476">**Reputação mal-intencionada de URL**</span><span class="sxs-lookup"><span data-stu-id="66935-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="66935-477">**Detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="66935-477">**URL detonation**</span></span>
- <span data-ttu-id="66935-478">**Reputação da detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="66935-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="66935-479">**Campanha**</span><span class="sxs-lookup"><span data-stu-id="66935-479">**Campaign**</span></span>

<span data-ttu-id="66935-480">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-481">**Date**</span></span>
- <span data-ttu-id="66935-482">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-482">**Subject**</span></span>
- <span data-ttu-id="66935-483">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-483">**Sender**</span></span>
- <span data-ttu-id="66935-484">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-484">**Recipients**</span></span>
- <span data-ttu-id="66935-485">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-485">**Detected by**</span></span>
- <span data-ttu-id="66935-486">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-486">**Delivery Status**</span></span>
- <span data-ttu-id="66935-487">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="66935-487">**Source of Compromise**</span></span>
- <span data-ttu-id="66935-488">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-488">**Tags**</span></span>

<span data-ttu-id="66935-489">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-490">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-491">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="66935-491">**Detection**</span></span>
- <span data-ttu-id="66935-492">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-493">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-493">**Direction**</span></span>
- <span data-ttu-id="66935-494">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-495">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-496">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-496">**Domain**</span></span>
- <span data-ttu-id="66935-497">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-497">**Policy type**</span></span>
- <span data-ttu-id="66935-498">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="66935-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="66935-499">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-499">**Recipients**</span></span>

<span data-ttu-id="66935-500">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="66935-501">Divisão de gráfico por tipo de política e Exibir dados por Phishing de Email \> ou Exibir dados por Malware de \> Email</span><span class="sxs-lookup"><span data-stu-id="66935-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Exibição de tipo de política para email de phishing ou email de malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="66935-503">Na divisão **Gráfico por Tipo** de Política e Exibir dados por **Phishing \>** de Email ou Exibir dados por exibição de Malware de **Email, \>** as seguintes informações são mostradas nos gráficos:</span><span class="sxs-lookup"><span data-stu-id="66935-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="66935-504">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="66935-504">**Anti-malware**</span></span>
- <span data-ttu-id="66935-505">**Cofre Anexos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="66935-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="66935-506">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="66935-506">**Anti-phish**</span></span>
- <span data-ttu-id="66935-507">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="66935-507">**Anti-spam**</span></span>
- <span data-ttu-id="66935-508">**Regra de fluxo de emails** (também conhecida como regra de transporte)</span><span class="sxs-lookup"><span data-stu-id="66935-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="66935-509">**Outros**</span><span class="sxs-lookup"><span data-stu-id="66935-509">**Others**</span></span>

<span data-ttu-id="66935-510">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-511">**Date**</span></span>
- <span data-ttu-id="66935-512">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-512">**Subject**</span></span>
- <span data-ttu-id="66935-513">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-513">**Sender**</span></span>
- <span data-ttu-id="66935-514">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-514">**Recipients**</span></span>
- <span data-ttu-id="66935-515">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-515">**Detected by**</span></span>
- <span data-ttu-id="66935-516">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-516">**Delivery Status**</span></span>
- <span data-ttu-id="66935-517">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="66935-517">**Source of Compromise**</span></span>
- <span data-ttu-id="66935-518">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-518">**Tags**</span></span>

<span data-ttu-id="66935-519">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-520">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-521">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="66935-521">**Detection**</span></span>
- <span data-ttu-id="66935-522">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-523">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-523">**Direction**</span></span>
- <span data-ttu-id="66935-524">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-525">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-526">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-526">**Domain**</span></span>
- <span data-ttu-id="66935-527">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-527">**Policy type**</span></span>
- <span data-ttu-id="66935-528">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="66935-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="66935-529">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-529">**Recipients**</span></span>

<span data-ttu-id="66935-530">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="66935-531">Divisão de gráficos por status de entrega e Exibir dados por Phishing de Email \> ou Exibir dados por Malware de \> Email</span><span class="sxs-lookup"><span data-stu-id="66935-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Exibição de status de entrega para email de phishing e email de malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="66935-533">Na divisão **gráfico por status** de entrega e Exibir dados por **Phishing \>** de Email ou Exibir dados por exibição **de \> Malware** de Email, as seguintes informações são mostradas nos gráficos:</span><span class="sxs-lookup"><span data-stu-id="66935-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="66935-534">**Caixa de correio hospedada: Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="66935-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="66935-535">**Caixa de correio hospedada: Lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="66935-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="66935-536">**Caixa de correio hospedada: Pasta personalizada**</span><span class="sxs-lookup"><span data-stu-id="66935-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="66935-537">**Caixa de correio hospedada: itens excluídos**</span><span class="sxs-lookup"><span data-stu-id="66935-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="66935-538">**Encaminhado**</span><span class="sxs-lookup"><span data-stu-id="66935-538">**Forwarded**</span></span>
- <span data-ttu-id="66935-539">**Servidor local: Entregue**</span><span class="sxs-lookup"><span data-stu-id="66935-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="66935-540">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="66935-540">**Quarantine**</span></span>
- <span data-ttu-id="66935-541">**Falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-541">**Delivery failed**</span></span>
- <span data-ttu-id="66935-542">**Descartado**</span><span class="sxs-lookup"><span data-stu-id="66935-542">**Dropped**</span></span>

<span data-ttu-id="66935-543">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-544">**Date**</span></span>
- <span data-ttu-id="66935-545">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-545">**Subject**</span></span>
- <span data-ttu-id="66935-546">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-546">**Sender**</span></span>
- <span data-ttu-id="66935-547">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-547">**Recipients**</span></span>
- <span data-ttu-id="66935-548">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-548">**Detected by**</span></span>
- <span data-ttu-id="66935-549">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-549">**Delivery Status**</span></span>
- <span data-ttu-id="66935-550">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="66935-550">**Source of Compromise**</span></span>
- <span data-ttu-id="66935-551">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-551">**Tags**</span></span>

<span data-ttu-id="66935-552">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-553">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-554">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="66935-554">**Detection**</span></span>
- <span data-ttu-id="66935-555">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-556">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-556">**Direction**</span></span>
- <span data-ttu-id="66935-557">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-558">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-559">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-559">**Domain**</span></span>
- <span data-ttu-id="66935-560">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-560">**Policy type**</span></span>
- <span data-ttu-id="66935-561">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="66935-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="66935-562">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-562">**Recipients**</span></span>

<span data-ttu-id="66935-563">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="66935-564">Exibir dados por Malware de \> Conteúdo</span><span class="sxs-lookup"><span data-stu-id="66935-564">View data by Content \> Malware</span></span>

![Exibição de malware de conteúdo no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="66935-566">Na **exibição Exibir dados por \> Malware** de Conteúdo, as informações a seguir são mostradas no gráfico do Microsoft Defender para Office 365 organizações:</span><span class="sxs-lookup"><span data-stu-id="66935-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="66935-567">**Mecanismo anti-malware**: arquivos mal-intencionados detectados no Sharepoint, OneDrive e Microsoft Teams pela detecção interna de [vírus no Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="66935-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="66935-568">**Detonação de** arquivo : Arquivos mal-intencionados [detectados por Cofre anexos](mdo-for-spo-odb-and-teams.md)para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="66935-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="66935-569">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-570">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-571">**Localização**</span><span class="sxs-lookup"><span data-stu-id="66935-571">**Location**</span></span>
- <span data-ttu-id="66935-572">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-572">**Detected by**</span></span>
- <span data-ttu-id="66935-573">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="66935-573">**Malware name**</span></span>

<span data-ttu-id="66935-574">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-575">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-576">**Detecção**: **mecanismo anti-malware ou** **detonação de arquivo**</span><span class="sxs-lookup"><span data-stu-id="66935-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="66935-577">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="66935-578">Exibir dados por substituição do sistema</span><span class="sxs-lookup"><span data-stu-id="66935-578">View data by System override</span></span>

![Exibição de substituição de mensagens no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="66935-580">No **exibição Exibir dados por substituição do** sistema, as informações do motivo de substituição a seguir são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="66935-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="66935-581">**Ignorar local**</span><span class="sxs-lookup"><span data-stu-id="66935-581">**On-premises skip**</span></span>
- <span data-ttu-id="66935-582">**Ip allow**</span><span class="sxs-lookup"><span data-stu-id="66935-582">**IP allow**</span></span>
- <span data-ttu-id="66935-583">**Exchange de transporte de email** (regra de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="66935-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="66935-584">**Senders permitidos pela organização**</span><span class="sxs-lookup"><span data-stu-id="66935-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="66935-585">**Domínios permitidos pela organização**</span><span class="sxs-lookup"><span data-stu-id="66935-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="66935-586">**ZAP não habilitado**</span><span class="sxs-lookup"><span data-stu-id="66935-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="66935-587">**Pasta Lixo Eletrônico não habilitada**</span><span class="sxs-lookup"><span data-stu-id="66935-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="66935-588">**Usuário Cofre Remetente**</span><span class="sxs-lookup"><span data-stu-id="66935-588">**User Safe Sender**</span></span>
- <span data-ttu-id="66935-589">**Domínio Cofre usuário**</span><span class="sxs-lookup"><span data-stu-id="66935-589">**User Safe Domain**</span></span>

<span data-ttu-id="66935-590">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="66935-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="66935-591">**Date**</span></span>
- <span data-ttu-id="66935-592">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="66935-592">**Subject**</span></span>
- <span data-ttu-id="66935-593">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-593">**Sender**</span></span>
- <span data-ttu-id="66935-594">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-594">**Recipients**</span></span>
- <span data-ttu-id="66935-595">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="66935-595">**Detected by**</span></span>
- <span data-ttu-id="66935-596">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="66935-596">**Delivery Status**</span></span>
- <span data-ttu-id="66935-597">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="66935-597">**Source of Compromise**</span></span>
- <span data-ttu-id="66935-598">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-598">**Tags**</span></span>

<span data-ttu-id="66935-599">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="66935-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="66935-600">**Data**: **Data de início** e data de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="66935-601">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="66935-601">**Detection**</span></span>
- <span data-ttu-id="66935-602">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="66935-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="66935-603">**Direção**</span><span class="sxs-lookup"><span data-stu-id="66935-603">**Direction**</span></span>
- <span data-ttu-id="66935-604">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="66935-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="66935-605">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="66935-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="66935-606">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="66935-606">**Domain**</span></span>
- <span data-ttu-id="66935-607">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="66935-607">**Policy type**</span></span>
- <span data-ttu-id="66935-608">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="66935-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="66935-609">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="66935-609">**Recipients**</span></span>

<span data-ttu-id="66935-610">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="66935-611"><sup>\*</sup>Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="66935-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="66935-612">Relatório de malware principal</span><span class="sxs-lookup"><span data-stu-id="66935-612">Top malware report</span></span>

<span data-ttu-id="66935-613">O **relatório de malware** Top mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="66935-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="66935-614">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="66935-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="66935-615">Em **Malware superior,** clique **em Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="66935-616">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="66935-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Principal widget de malware na página Relatórios de & de colaboração](../../media/top-malware-report-widget.png)

<span data-ttu-id="66935-618">Quando você passar o mouse sobre uma cunha no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="66935-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="66935-619">Depois de clicar **em Exibir detalhes,** uma versão maior do gráfico de pizza será exibida na página de relatório. A tabela de detalhes abaixo do gráfico mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="66935-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="66935-620">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="66935-620">**Top malware**</span></span>
- <span data-ttu-id="66935-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="66935-621">**Count**</span></span>

<span data-ttu-id="66935-622">Se você clicar **em Filtrar,** poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="66935-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Exibição de relatório de malware principal](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="66935-624">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="66935-624">URL threat protection report</span></span>

<span data-ttu-id="66935-625">O **relatório de proteção contra** ameaças de URL está disponível no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="66935-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="66935-626">Para obter mais informações, consulte [RELATÓRIO de proteção contra ameaças de URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="66935-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="66935-627">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="66935-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66935-628">Para que o relatório de mensagens **relatadas** pelo usuário funcione corretamente, o **log** de auditoria deve ser ligado para seu ambiente Microsoft 365 ambiente.</span><span class="sxs-lookup"><span data-stu-id="66935-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="66935-629">Isso normalmente é feito por alguém que tem a função Logs de Auditoria atribuída Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="66935-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="66935-630">Para obter mais informações, consulte Ativar ou desativar [Microsoft 365 pesquisa de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="66935-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="66935-631">O **relatório** de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento [Mensagem](enable-the-report-message-add-in.md) de Relatório ou o complemento Relatar [Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="66935-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="66935-632">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** Email & colaboração Email & relatórios de colaboração \>  \>  \> **Mensagens relatadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="66935-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="66935-633">Em **Mensagens relatadas pelo usuário,** clique **em Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="66935-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="66935-634">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="66935-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="66935-635">Para acessar [envios de administrador no portal Microsoft 365 Defender,](admin-submission.md)clique **em Ir para Envios**.</span><span class="sxs-lookup"><span data-stu-id="66935-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget de mensagens relatadas pelo usuário na página Relatórios de & de colaboração](../../media/user-reported-messages-widget.png)

<span data-ttu-id="66935-637">Depois de clicar em **Exibir** detalhes, você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="66935-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="66935-638">**Data relatada**: **Hora de início** e hora de **término**</span><span class="sxs-lookup"><span data-stu-id="66935-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="66935-639">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="66935-639">**Reported by**</span></span>
- <span data-ttu-id="66935-640">**Assunto do email**</span><span class="sxs-lookup"><span data-stu-id="66935-640">**Email subject**</span></span>
- <span data-ttu-id="66935-641">**ID da mensagem relatada**</span><span class="sxs-lookup"><span data-stu-id="66935-641">**Message reported ID**</span></span>
- <span data-ttu-id="66935-642">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="66935-642">**Network Message ID**</span></span>
- <span data-ttu-id="66935-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-643">**Sender**</span></span>
- <span data-ttu-id="66935-644">**Motivo relatado**</span><span class="sxs-lookup"><span data-stu-id="66935-644">**Reported reason**</span></span>
  - <span data-ttu-id="66935-645">**Não é lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="66935-645">**Not junk**</span></span>
  - <span data-ttu-id="66935-646">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="66935-646">**Phish**</span></span>
  - <span data-ttu-id="66935-647">**Spam**</span><span class="sxs-lookup"><span data-stu-id="66935-647">**Spam**</span></span>
- <span data-ttu-id="66935-648">**Simulação de phishing**: **Sim** ou **Não**</span><span class="sxs-lookup"><span data-stu-id="66935-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="66935-649">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="66935-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="66935-650">Para agrupar as entradas, clique em **Grupo** e selecione um dos seguintes valores na listada:</span><span class="sxs-lookup"><span data-stu-id="66935-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="66935-651">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="66935-651">**None**</span></span>
- <span data-ttu-id="66935-652">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="66935-652">**Reason**</span></span>
- <span data-ttu-id="66935-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-653">**Sender**</span></span>
- <span data-ttu-id="66935-654">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="66935-654">**Reported by**</span></span>
- <span data-ttu-id="66935-655">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="66935-655">**Rescan result**</span></span>
- <span data-ttu-id="66935-656">**Simulação de phishing**</span><span class="sxs-lookup"><span data-stu-id="66935-656">**Phish simulation**</span></span>

![Relatório de mensagens relatadas pelo usuário](../../media/user-reported-messages-report.png)

<span data-ttu-id="66935-658">Na tabela abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="66935-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="66935-659">**Assunto do email**</span><span class="sxs-lookup"><span data-stu-id="66935-659">**Email subject**</span></span>
- <span data-ttu-id="66935-660">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="66935-660">**Reported by**</span></span>
- <span data-ttu-id="66935-661">**Data relatada**</span><span class="sxs-lookup"><span data-stu-id="66935-661">**Date reported**</span></span>
- <span data-ttu-id="66935-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="66935-662">**Sender**</span></span>
- <span data-ttu-id="66935-663">**Motivo relatado**</span><span class="sxs-lookup"><span data-stu-id="66935-663">**Reported reason**</span></span>
- <span data-ttu-id="66935-664">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="66935-664">**Rescan result**</span></span>
- <span data-ttu-id="66935-665">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="66935-665">**Tags**</span></span>

<span data-ttu-id="66935-666">Para enviar uma mensagem à Microsoft para análise, selecione a entrada da mensagem na tabela, clique em Enviar para a **Microsoft** para análise e selecione um dos seguintes valores na lista abaixo:</span><span class="sxs-lookup"><span data-stu-id="66935-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="66935-667">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="66935-667">**Report clean**</span></span>
- <span data-ttu-id="66935-668">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="66935-668">**Report phishing**</span></span>
- <span data-ttu-id="66935-669">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="66935-669">**Report malware**</span></span>
- <span data-ttu-id="66935-670">**Relatar spam**'</span><span class="sxs-lookup"><span data-stu-id="66935-670">**Report spam**'</span></span>
- <span data-ttu-id="66935-671">**Investigação de gatilho** (Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="66935-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="66935-672">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="66935-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="66935-673">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de função no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="66935-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="66935-674">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="66935-674">**Organization Management**</span></span>
- <span data-ttu-id="66935-675">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="66935-675">**Security Administrator**</span></span>
- <span data-ttu-id="66935-676">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="66935-676">**Security Reader**</span></span>
- <span data-ttu-id="66935-677">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="66935-677">**Global Reader**</span></span>

<span data-ttu-id="66935-678">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender .](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="66935-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="66935-679">**Observação**: adicionar usuários à função Active Directory do Azure correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ do Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66935-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="66935-680">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="66935-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="66935-681">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="66935-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="66935-682">Se você não estiver vendo dados em seus relatórios, verifique duas vezes se suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="66935-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="66935-683">Para saber mais, confira [Proteger contra ameaças](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="66935-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="66935-684">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66935-684">Related topics</span></span>

[<span data-ttu-id="66935-685">Proteção anti-spam e anti-malware no EOP</span><span class="sxs-lookup"><span data-stu-id="66935-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="66935-686">Relatórios inteligentes e percepções no portal Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="66935-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="66935-687">Exibir relatórios de fluxo de emails no portal Microsoft 365 Defender de email</span><span class="sxs-lookup"><span data-stu-id="66935-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="66935-688">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="66935-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
