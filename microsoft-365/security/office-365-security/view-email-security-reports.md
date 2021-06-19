---
title: Exibir relatórios de segurança de email
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
description: Os administradores podem saber como encontrar e usar os relatórios de segurança de email disponíveis no portal do Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029531"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="34c46-103">Exibir relatórios de segurança de email no portal do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34c46-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="34c46-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="34c46-104">**Applies to**</span></span>
- [<span data-ttu-id="34c46-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="34c46-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="34c46-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="34c46-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="34c46-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34c46-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="34c46-108">Vários relatórios estão disponíveis no portal do Microsoft 365 Defender para ajudá-lo a ver como os recursos de segurança de email, como anti-spam, anti-malware e recursos de criptografia no Microsoft 365 estão protegendo sua <https://security.microsoft.com> organização.</span><span class="sxs-lookup"><span data-stu-id="34c46-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="34c46-109">Se você tiver as permissões [necessárias,](#what-permissions-are-needed-to-view-these-reports)poderá exibir esses relatórios no portal  do Microsoft 365 Defender, indo para Relatórios Email & colaboração \>  \> **Email & relatórios de colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-110">Para ir diretamente para a página Relatórios de **colaboração & email,** abra <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="34c46-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Página & relatórios de colaboração de email no portal do Microsoft 365 Defender](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="34c46-112">Alguns dos relatórios na página Relatórios de & **de** colaboração exigem o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="34c46-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="34c46-113">Para obter informações sobre esses relatórios, consulte [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="34c46-114">Os relatórios relacionados ao fluxo de emails agora estão no Centro de administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="34c46-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="34c46-115">Para obter mais informações sobre esses relatórios, consulte [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span><span class="sxs-lookup"><span data-stu-id="34c46-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="34c46-116">Relatório de usuários comprometidos</span><span class="sxs-lookup"><span data-stu-id="34c46-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="34c46-117">Este relatório está disponível em organizações do Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="34c46-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="34c46-118">Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="34c46-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="34c46-119">O **relatório Usuários Comprometidos** mostra o número de contas de usuário que foram marcadas como **Suspeitas** ou **Restritas** nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="34c46-120">As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas.</span><span class="sxs-lookup"><span data-stu-id="34c46-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="34c46-121">Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="34c46-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="34c46-122">Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="34c46-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget de usuários comprometidos na página Relatórios de colaboração & email](../../media/compromised-users-report-widget.png)

<span data-ttu-id="34c46-124">A exibição agregada mostra os dados dos últimos 90 dias e a exibição de detalhes mostra os dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="34c46-125">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-126">Na página **Relatórios de colaboração &** email, encontre **Usuários** comprometidos e clique em **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="34c46-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="34c46-127">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="34c46-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="34c46-128">Na página **Usuários comprometidos,** você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="34c46-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="34c46-129">**Data (UTC)**: Data **de início** **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="34c46-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="34c46-130">**Atividade**:</span><span class="sxs-lookup"><span data-stu-id="34c46-130">**Activity**:</span></span>
  - <span data-ttu-id="34c46-131">**Suspeito**: a conta de usuário enviou emails suspeitos e corre o risco de ser restringida ao envio de emails.</span><span class="sxs-lookup"><span data-stu-id="34c46-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="34c46-132">**Restrito**: a conta de usuário foi restrita ao envio de emails devido a padrões altamente suspeitos.</span><span class="sxs-lookup"><span data-stu-id="34c46-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="34c46-133">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![Exibir relatório no relatório Usuários Comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="34c46-135">Na tabela de detalhes abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="34c46-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="34c46-136">**Hora da criação**</span><span class="sxs-lookup"><span data-stu-id="34c46-136">**Creation time**</span></span>
- <span data-ttu-id="34c46-137">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="34c46-137">**User ID**</span></span>
- <span data-ttu-id="34c46-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="34c46-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="34c46-139">Relatório de regra de transporte do Exchange</span><span class="sxs-lookup"><span data-stu-id="34c46-139">Exchange transport rule report</span></span>

<span data-ttu-id="34c46-140">O **relatório de regra de** transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="34c46-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="34c46-141">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-142">Na página **Relatórios de colaboração de &** email, encontre a regra de transporte do **Exchange** e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="34c46-143">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/ETRRuleReport> .</span><span class="sxs-lookup"><span data-stu-id="34c46-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Widget de regra de transporte do Exchange na página Relatórios de colaboração & email](../../media/transport-rule-report-widget.png)

<span data-ttu-id="34c46-145">Na página Relatório de regras de **transporte do Exchange,** os gráficos e dados disponíveis são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="34c46-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="34c46-146">Divisão de gráficos por Direção</span><span class="sxs-lookup"><span data-stu-id="34c46-146">Chart breakdown by Direction</span></span>

![Exibição de direção para regras de Transporte do Exchange no relatório de regra de transporte do Exchange](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="34c46-148">Se você selecionar **Chart breakdown by Direction**, os gráficos a seguir estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="34c46-149">**Exibir dados por regras de transporte** do  Exchange : O número **de** mensagens de entrada e de saída que foram afetadas pelas regras de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="34c46-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="34c46-150">Exibir dados por regras de transporte  do Exchange  de **DLP**: O número de mensagens de entrada e saída que foram afetadas pelas regras de fluxo de emails de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="34c46-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="34c46-151">As informações a seguir são mostradas na tabela de detalhes abaixo do gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="34c46-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-152">**Date**</span></span>
- <span data-ttu-id="34c46-153">**Política de DLP** ( Exibir dados somente por regras de transporte **do Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="34c46-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="34c46-154">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="34c46-154">**Transport rule**</span></span>
- <span data-ttu-id="34c46-155">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-155">**Subject**</span></span>
- <span data-ttu-id="34c46-156">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="34c46-156">**Sender address**</span></span>
- <span data-ttu-id="34c46-157">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="34c46-157">**Recipient address**</span></span>
- <span data-ttu-id="34c46-158">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="34c46-158">**Severity**</span></span>
- <span data-ttu-id="34c46-159">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-159">**Direction**</span></span>

<span data-ttu-id="34c46-160">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="34c46-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="34c46-161">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-162">**Direção**: **Saída** e **Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="34c46-163">**Severidade**: **alta gravidade,** **gravidade média** e baixa **gravidade**</span><span class="sxs-lookup"><span data-stu-id="34c46-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="34c46-164">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="34c46-165">Divisão de gráficos por severidade</span><span class="sxs-lookup"><span data-stu-id="34c46-165">Chart breakdown by Severity</span></span>

![Exibição de severidade para regras de Transporte do Exchange no relatório de regra de transporte do Exchange](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="34c46-167">Se você selecionar **Divisão de gráfico por Severidade,** os gráficos a seguir estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="34c46-168">**Exibir dados por regras de transporte do Exchange**: o número de **mensagens** de alta gravidade, gravidade **média** e **Baixa gravidade.**</span><span class="sxs-lookup"><span data-stu-id="34c46-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="34c46-169">Você definirá o nível de gravidade como uma ação na regra (**Audite essa** regra com nível de gravidade ou _SetAuditSeverity_).</span><span class="sxs-lookup"><span data-stu-id="34c46-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="34c46-170">Para obter mais informações, consulte [Ações de regra de fluxo de email no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span><span class="sxs-lookup"><span data-stu-id="34c46-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="34c46-171">**Exibir dados por regras** de transporte do Exchange de DLP  : O número de Mensagens de Alta **gravidade,** Gravidade Média e Baixa gravidade que foram afetadas pelas regras de fluxo de emails DLP.</span><span class="sxs-lookup"><span data-stu-id="34c46-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="34c46-172">As informações a seguir são mostradas na tabela de detalhes abaixo do gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="34c46-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-173">**Date**</span></span>
- <span data-ttu-id="34c46-174">**Política de DLP** ( Exibir dados somente por regras de transporte **do Exchange DLP)**</span><span class="sxs-lookup"><span data-stu-id="34c46-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="34c46-175">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="34c46-175">**Transport rule**</span></span>
- <span data-ttu-id="34c46-176">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-176">**Subject**</span></span>
- <span data-ttu-id="34c46-177">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="34c46-177">**Sender address**</span></span>
- <span data-ttu-id="34c46-178">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="34c46-178">**Recipient address**</span></span>
- <span data-ttu-id="34c46-179">**Gravidade**</span><span class="sxs-lookup"><span data-stu-id="34c46-179">**Severity**</span></span>
- <span data-ttu-id="34c46-180">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-180">**Direction**</span></span>

<span data-ttu-id="34c46-181">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="34c46-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="34c46-182">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-183">**Direção**: **Saída** e **Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="34c46-184">**Severidade**: **alta gravidade,** **gravidade média** e baixa **gravidade**</span><span class="sxs-lookup"><span data-stu-id="34c46-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="34c46-185">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="34c46-186">Relatório de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="34c46-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="34c46-187">O **relatório de encaminhamento** agora está disponível no EAC.</span><span class="sxs-lookup"><span data-stu-id="34c46-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="34c46-188">Para obter mais informações, consulte Relatório automático de mensagens [encaminhadas no novo EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span><span class="sxs-lookup"><span data-stu-id="34c46-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="34c46-189">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="34c46-189">Mailflow status report</span></span>

<span data-ttu-id="34c46-190">O relatório de status de **fluxo** de emails é um relatório inteligente que mostra informações sobre emails de entrada e saída, detecções de spam, malware, email identificado como "bom" e informações sobre emails permitidos ou bloqueados na borda.</span><span class="sxs-lookup"><span data-stu-id="34c46-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="34c46-191">Este é o único relatório que contém informações de proteção de borda e mostra a quantos emails são bloqueados antes de serem permitidos no serviço para avaliação pela Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="34c46-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="34c46-192">É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="34c46-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="34c46-193">Para exibir o relatório no portal do Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-194">Na página **Relatórios de colaboração de &** email, encontre o resumo de status do **fluxo** de emails e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="34c46-195">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/mailflowStatusReport> .</span><span class="sxs-lookup"><span data-stu-id="34c46-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![Widget de resumo de status de fluxo de email na página Relatórios de colaboração & email](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="34c46-197">Exibição de tipo para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="34c46-197">Type view for the Mailflow status report</span></span>

![Type view in the Mailflow status report](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="34c46-199">Na página **Relatório de status de fluxo de** emails, a guia **Tipo** é selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="34c46-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="34c46-200">Por padrão, esse modo de exibição contém um gráfico e uma tabela de detalhes configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="34c46-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="34c46-201">**Data (UTC)** Os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="34c46-202">**Direção do email**:</span><span class="sxs-lookup"><span data-stu-id="34c46-202">**Mail direction**:</span></span>
  - <span data-ttu-id="34c46-203">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-203">**Inbound**</span></span>
  - <span data-ttu-id="34c46-204">**Saída**</span><span class="sxs-lookup"><span data-stu-id="34c46-204">**Outbound**</span></span>
  - <span data-ttu-id="34c46-205">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="34c46-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="34c46-206">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)</span><span class="sxs-lookup"><span data-stu-id="34c46-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="34c46-207">**Tipo**:</span><span class="sxs-lookup"><span data-stu-id="34c46-207">**Type**:</span></span>
  - <span data-ttu-id="34c46-208">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="34c46-208">**Good mail**</span></span>
  - <span data-ttu-id="34c46-209">**Malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-209">**Malware**</span></span>
  - <span data-ttu-id="34c46-210">**Spam**</span><span class="sxs-lookup"><span data-stu-id="34c46-210">**Spam**</span></span>
  - <span data-ttu-id="34c46-211">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="34c46-211">**Edge protection**</span></span>
  - <span data-ttu-id="34c46-212">**Mensagens de regra**</span><span class="sxs-lookup"><span data-stu-id="34c46-212">**Rule messages**</span></span>
  - <span data-ttu-id="34c46-213">**Email de phishing**</span><span class="sxs-lookup"><span data-stu-id="34c46-213">**Phishing email**</span></span>
- <span data-ttu-id="34c46-214">**Domínio**: **Todos**</span><span class="sxs-lookup"><span data-stu-id="34c46-214">**Domain**: **All**</span></span>

<span data-ttu-id="34c46-215">O gráfico é organizado pelos valores **Type.**</span><span class="sxs-lookup"><span data-stu-id="34c46-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="34c46-216">Você pode alterar esses filtros clicando em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="34c46-217">As informações a seguir são mostradas na tabela de detalhes abaixo do gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="34c46-218">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-218">**Direction**</span></span>
- <span data-ttu-id="34c46-219">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="34c46-219">**Type**</span></span>
- <span data-ttu-id="34c46-220">**24 horas**</span><span class="sxs-lookup"><span data-stu-id="34c46-220">**24 hours**</span></span>
- <span data-ttu-id="34c46-221">**3 dias**</span><span class="sxs-lookup"><span data-stu-id="34c46-221">**3 days**</span></span>
- <span data-ttu-id="34c46-222">**7 dias**</span><span class="sxs-lookup"><span data-stu-id="34c46-222">**7 days**</span></span>
- <span data-ttu-id="34c46-223">**15 dias**</span><span class="sxs-lookup"><span data-stu-id="34c46-223">**15 days**</span></span>
- <span data-ttu-id="34c46-224">**30 dias**</span><span class="sxs-lookup"><span data-stu-id="34c46-224">**30 days**</span></span>

<span data-ttu-id="34c46-225">Se você clicar **em Escolher uma categoria para obter** mais detalhes, você poderá selecionar entre os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="34c46-226">**Email de phishing**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="34c46-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="34c46-227">**Malware no email**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="34c46-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="34c46-228">**Detecções de** spam: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="34c46-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="34c46-229">**Spam bloqueado de borda:** essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)</span><span class="sxs-lookup"><span data-stu-id="34c46-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="34c46-230">Exportar do tipo de exibição</span><span class="sxs-lookup"><span data-stu-id="34c46-230">Export from Type view</span></span>

<span data-ttu-id="34c46-231">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="34c46-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="34c46-232">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="34c46-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="34c46-233">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="34c46-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="34c46-234">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="34c46-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="34c46-235">Exibição de direção para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="34c46-235">Direction view for the Mailflow status report</span></span>

![Exibição de direção no relatório de status de fluxo de emails](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="34c46-237">Se você clicar na guia **Direção,** os mesmos filtros padrão do modo de exibição **Tipo** serão usados.</span><span class="sxs-lookup"><span data-stu-id="34c46-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="34c46-238">O gráfico é organizado pelos **valores Direction.**</span><span class="sxs-lookup"><span data-stu-id="34c46-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="34c46-239">Você pode alterar esses filtros clicando em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="34c46-240">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="34c46-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="34c46-241">A tabela de detalhes contém as mesmas informações do modo **de exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="34c46-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="34c46-242">A **opção Escolher uma categoria para obter** mais detalhes sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição Tipo.**</span><span class="sxs-lookup"><span data-stu-id="34c46-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="34c46-243">Exportar do ponto de vista De direção</span><span class="sxs-lookup"><span data-stu-id="34c46-243">Export from Direction view</span></span>

<span data-ttu-id="34c46-244">Para a exibição de detalhes, você só pode exportar dados por um dia.</span><span class="sxs-lookup"><span data-stu-id="34c46-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="34c46-245">Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.</span><span class="sxs-lookup"><span data-stu-id="34c46-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="34c46-246">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="34c46-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="34c46-247">Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="34c46-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="34c46-248">Exibição de funil para o relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="34c46-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="34c46-249">A **exibição** Funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e saída em sua organização.</span><span class="sxs-lookup"><span data-stu-id="34c46-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="34c46-250">Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.</span><span class="sxs-lookup"><span data-stu-id="34c46-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![Exibição de funil no relatório de status de fluxo de emails](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="34c46-252">Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de detalhes configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="34c46-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="34c46-253">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="34c46-254">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="34c46-254">**Direction**:</span></span>
  - <span data-ttu-id="34c46-255">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-255">**Inbound**</span></span>
  - <span data-ttu-id="34c46-256">**Saída**</span><span class="sxs-lookup"><span data-stu-id="34c46-256">**Outbound**</span></span>
  - <span data-ttu-id="34c46-257">**Intra-org**: esta contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de Entrada e Saída).</span><span class="sxs-lookup"><span data-stu-id="34c46-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="34c46-258">A exibição agregada e a exibição da tabela de detalhes permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="34c46-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="34c46-259">Você pode alterar esses filtros clicando em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="34c46-260">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="34c46-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="34c46-261">Este gráfico mostra a contagem de emails organizada por:</span><span class="sxs-lookup"><span data-stu-id="34c46-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="34c46-262">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="34c46-262">**Total email**</span></span>
- <span data-ttu-id="34c46-263">**Email após proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="34c46-263">**Email after edge protection**</span></span>
- <span data-ttu-id="34c46-264">**Regra de email após transporte** (regra de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="34c46-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="34c46-265">**Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="34c46-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="34c46-266">**Email após anti-phishing, reputação de URL, representação de marca, anti-spoof**</span><span class="sxs-lookup"><span data-stu-id="34c46-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="34c46-267">**Email após anti-spam, filtragem de email em massa**</span><span class="sxs-lookup"><span data-stu-id="34c46-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="34c46-268">**Email após a representação de usuário e domínio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-269">**Email após a detonação de arquivo e URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-270">**Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique na URL)**</span><span class="sxs-lookup"><span data-stu-id="34c46-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="34c46-271"><sup>\*</sup>Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="34c46-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="34c46-272">Para exibir o email filtrado por EOP ou Defender Office 365 separadamente, clique no valor na legenda do gráfico.</span><span class="sxs-lookup"><span data-stu-id="34c46-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="34c46-273">A tabela de detalhes contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="34c46-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="34c46-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-274">**Date**</span></span>
- <span data-ttu-id="34c46-275">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="34c46-275">**Total email**</span></span>
- <span data-ttu-id="34c46-276">**Proteção de borda**</span><span class="sxs-lookup"><span data-stu-id="34c46-276">**Edge protection**</span></span>
- <span data-ttu-id="34c46-277">**Anti-malware, reputação de arquivo, bloco de tipo de arquivo**:</span><span class="sxs-lookup"><span data-stu-id="34c46-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="34c46-278">**Reputação do** arquivo : Mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34c46-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="34c46-279">**Bloco de tipo de** arquivo : Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="34c46-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="34c46-280">**Anti-phish, reputação de URL, representação de marca, anti-spoof**:</span><span class="sxs-lookup"><span data-stu-id="34c46-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="34c46-281">**Reputação da URL**: Mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="34c46-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="34c46-282">**Representação de marca**: Mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.</span><span class="sxs-lookup"><span data-stu-id="34c46-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="34c46-283">**Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence ou a um domínio que o remetente da mensagem não possui.</span><span class="sxs-lookup"><span data-stu-id="34c46-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="34c46-284">**Anti-spam, filtragem de email em massa:**</span><span class="sxs-lookup"><span data-stu-id="34c46-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="34c46-285">**Filtragem de emails** em massa: Mensagens filtradas com base no limite de bcl (nível de reclamação em massa) em uma política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="34c46-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="34c46-286">**Representação de usuário e domínio (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="34c46-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="34c46-287">**Representação do** usuário : Mensagens filtradas devido a uma tentativa de representar um usuário (remetente de mensagem) definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="34c46-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="34c46-288">**Representação de domínio**: Mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.</span><span class="sxs-lookup"><span data-stu-id="34c46-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="34c46-289">**Detonação de arquivo e URL (Defender para Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="34c46-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="34c46-290">**Detonação de** arquivo : Mensagens filtradas por uma política Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="34c46-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="34c46-291">**Detonação de URL**: Mensagem filtrada por uma política Cofre Links.</span><span class="sxs-lookup"><span data-stu-id="34c46-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="34c46-292">**Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: Limpeza automática zero hora (ZAP) para malware, spam e phishing.</span><span class="sxs-lookup"><span data-stu-id="34c46-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="34c46-293">Se você selecionar uma linha na tabela de detalhes, uma nova divisão das contagens de email será mostrada no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="34c46-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="34c46-294">Exportar do exibição Funil</span><span class="sxs-lookup"><span data-stu-id="34c46-294">Export from Funnel view</span></span>

<span data-ttu-id="34c46-295">Depois de clicar **em Exportar** **em Opções,** selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="34c46-296">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="34c46-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="34c46-297">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="34c46-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="34c46-298">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="34c46-299">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="34c46-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="34c46-300">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="34c46-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="34c46-301">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="34c46-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="34c46-302">Exibição técnica do relatório de status mailflow</span><span class="sxs-lookup"><span data-stu-id="34c46-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="34c46-303">O **modo de exibição** Tech é semelhante ao modo de exibição **Funil,** fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="34c46-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="34c46-304">No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="34c46-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="34c46-305">Se você clicar na **guia Modo de** exibição de tecnologia, por padrão, esse modo de exibição conterá um gráfico e uma tabela de detalhes configurada com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="34c46-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="34c46-306">**Data**: os últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="34c46-307">**Direção**:</span><span class="sxs-lookup"><span data-stu-id="34c46-307">**Direction**:</span></span>
  - <span data-ttu-id="34c46-308">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-308">**Inbound**</span></span>
  - <span data-ttu-id="34c46-309">**Saída**</span><span class="sxs-lookup"><span data-stu-id="34c46-309">**Outbound**</span></span>
  - <span data-ttu-id="34c46-310">**Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja,</span><span class="sxs-lookup"><span data-stu-id="34c46-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="34c46-311">remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de Entrada e Saída)</span><span class="sxs-lookup"><span data-stu-id="34c46-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="34c46-312">A exibição agregada e a exibição da tabela de detalhes permitem 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="34c46-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="34c46-313">Você pode alterar esses filtros clicando em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="34c46-314">Os mesmos filtros do modo **de exibição Type** são usados.</span><span class="sxs-lookup"><span data-stu-id="34c46-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="34c46-315">Este gráfico mostra mensagens organizadas nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="34c46-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="34c46-316">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="34c46-316">**Total email**</span></span>
- <span data-ttu-id="34c46-317">**Permitir borda** e **Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="34c46-318">**Regra de transporte permitir** e **regra de transporte filtrada** (regras de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="34c46-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="34c46-319">**Não malware,** **Cofre detecção de anexos** <sup>\*</sup> e detecção de mecanismo **anti-malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="34c46-320">**Não phish**, **falha de DMARC,** detecção **de representação,** detecção de <sup>\*</sup> **spoof** e **detecção de phishing**</span><span class="sxs-lookup"><span data-stu-id="34c46-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="34c46-321">**Nenhuma detecção com detonação de URL** e detecção **de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-322">**Não spam** e  **spam**</span><span class="sxs-lookup"><span data-stu-id="34c46-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="34c46-323">**Email não mal-intencionado,** **Cofre de links** e <sup>\*</sup> **ZAP**</span><span class="sxs-lookup"><span data-stu-id="34c46-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="34c46-324"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="34c46-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="34c46-325">Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="34c46-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="34c46-326">A tabela de detalhes contém as seguintes informações, mostradas na ordem de data decrescente:</span><span class="sxs-lookup"><span data-stu-id="34c46-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="34c46-327">**Data (UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-327">**Date (UTC)**</span></span>
- <span data-ttu-id="34c46-328">**Total de emails**</span><span class="sxs-lookup"><span data-stu-id="34c46-328">**Total email**</span></span>
- <span data-ttu-id="34c46-329">**Borda filtrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-329">**Edge filtered**</span></span>
- <span data-ttu-id="34c46-330">**Mensagens de regra**: Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="34c46-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="34c46-331">**Mecanismo anti-malware**, **Cofre Anexos** <sup>\*</sup> :</span><span class="sxs-lookup"><span data-stu-id="34c46-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="34c46-332">**DMARC, representação** <sup>\*</sup> , **spoof**, **phish filtered**:</span><span class="sxs-lookup"><span data-stu-id="34c46-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="34c46-333">**DMARC**: Mensagens filtradas devido à falha da mensagem em sua verificação de autenticação DMARC.</span><span class="sxs-lookup"><span data-stu-id="34c46-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="34c46-334">**Detecção de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-335">**Anti-spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="34c46-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="34c46-336">**ZAP removido**</span><span class="sxs-lookup"><span data-stu-id="34c46-336">**ZAP removed**</span></span>
- <span data-ttu-id="34c46-337">**Detecção por Cofre Links**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="34c46-338"><sup>\*</sup>Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="34c46-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="34c46-339">Se você selecionar uma linha na tabela de detalhes, uma nova divisão das contagens de email será mostrada no sobremenu.</span><span class="sxs-lookup"><span data-stu-id="34c46-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="34c46-340">Exportar do ponto de vista tech</span><span class="sxs-lookup"><span data-stu-id="34c46-340">Export from Tech view</span></span>

<span data-ttu-id="34c46-341">Ao clicar em **Exportar**, em **Opções,** você pode selecionar um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="34c46-342">**Resumo (com dados dos últimos 90 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="34c46-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="34c46-343">**Detalhes (com dados dos últimos 30 dias no máximo)**</span><span class="sxs-lookup"><span data-stu-id="34c46-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="34c46-344">Em **Data**, escolha um intervalo e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="34c46-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="34c46-345">Os dados dos filtros atuais serão exportados para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="34c46-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="34c46-346">Cada arquivo .csv é limitado a 150.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="34c46-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="34c46-347">Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.</span><span class="sxs-lookup"><span data-stu-id="34c46-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![Exibição técnica no relatório de status do fluxo de mensagens](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="34c46-349">Relatório de detecções de malware</span><span class="sxs-lookup"><span data-stu-id="34c46-349">Malware detections report</span></span>

<span data-ttu-id="34c46-350">O **relatório de detecções** de malware mostra informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado por Proteção do Exchange Online ou EOP).</span><span class="sxs-lookup"><span data-stu-id="34c46-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="34c46-351">Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="34c46-352">O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="34c46-353">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-354">Na página **Relatórios de colaboração &** email, encontre Malware detectado no **email** e clique em **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="34c46-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="34c46-355">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="34c46-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Detecções de malware no widget de email na página Relatórios de colaboração & email](../../media/malware-detections-widget.png)

<span data-ttu-id="34c46-357">Na página **Relatório de detecções** de malware, você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="34c46-358">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-359">**Direção**: **Entrada** e **Saída**</span><span class="sxs-lookup"><span data-stu-id="34c46-359">**Direction**: **Inbound** and **Outbound**</span></span>

![Exibir relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

<span data-ttu-id="34c46-361">Na tabela de detalhes abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="34c46-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="34c46-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-362">**Date**</span></span>
- <span data-ttu-id="34c46-363">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="34c46-363">**Sender address**</span></span>
- <span data-ttu-id="34c46-364">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="34c46-364">**Recipient address**</span></span>
- <span data-ttu-id="34c46-365">**ID da** mensagem : disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="34c46-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="34c46-366">Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="34c46-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="34c46-367">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-367">**Subject**</span></span>
- <span data-ttu-id="34c46-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="34c46-368">**Filename**</span></span>
- <span data-ttu-id="34c46-369">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="34c46-370">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="34c46-370">Mail latency report</span></span>

<span data-ttu-id="34c46-371">O **relatório de latência de** email no Defender para Office 365 contém informações sobre a entrega de emails e a latência de detonação experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="34c46-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="34c46-372">Para obter mais informações, consulte [Relatório de latência de email](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="34c46-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="34c46-373">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="34c46-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="34c46-374">O **relatório de detecções de spam** eventualmente desaparecerá.</span><span class="sxs-lookup"><span data-stu-id="34c46-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="34c46-375">As mesmas informações estão disponíveis no relatório de [status de proteção contra ameaças.](#threat-protection-status-report)</span><span class="sxs-lookup"><span data-stu-id="34c46-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="34c46-376">Relatório de detecções de spoof</span><span class="sxs-lookup"><span data-stu-id="34c46-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="34c46-377">O relatório aprimorado de detecções de Spoof conforme descrito neste artigo está em Visualização, está sujeito a alterações e não está disponível em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="34c46-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="34c46-378">A versão mais antiga do relatório mostra apenas **Emails bons e** **capturados como spam.**</span><span class="sxs-lookup"><span data-stu-id="34c46-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="34c46-379">O **relatório de detecções Spoof** mostra informações sobre mensagens que foram bloqueadas ou permitidas devido à fraude.</span><span class="sxs-lookup"><span data-stu-id="34c46-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="34c46-380">Para obter mais informações sobre a spoofing, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="34c46-381">A exibição agregada do relatório permite 45 dias de filtragem, enquanto a exibição de detalhes permite apenas <sup>\*</sup> dez dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="34c46-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="34c46-382"><sup>\*</sup> Eventualmente, você poderá usar até 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="34c46-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="34c46-383">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-384">Na página **Relatórios de colaboração &** email, encontre detecções de **Spoof** e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="34c46-385">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/SpoofMailReportV2> .</span><span class="sxs-lookup"><span data-stu-id="34c46-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![Widget de detecções de spoof na página Relatórios de colaboração & email](../../media/spoof-detections-widget.png)

<span data-ttu-id="34c46-387">O gráfico mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="34c46-387">The chart shows the following information:</span></span>

- <span data-ttu-id="34c46-388">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="34c46-388">**Pass**</span></span>
- <span data-ttu-id="34c46-389">**Fail**</span><span class="sxs-lookup"><span data-stu-id="34c46-389">**Fail**</span></span>
- <span data-ttu-id="34c46-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="34c46-390">**SoftPass**</span></span>
- <span data-ttu-id="34c46-391">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="34c46-391">**None**</span></span>
- <span data-ttu-id="34c46-392">**Outros**</span><span class="sxs-lookup"><span data-stu-id="34c46-392">**Other**</span></span>

<span data-ttu-id="34c46-393">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens falsas foram detectadas e por quê.</span><span class="sxs-lookup"><span data-stu-id="34c46-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="34c46-394">Na página Relatório de email de **Spoof,** você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="34c46-395">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-396">**Resultado**:</span><span class="sxs-lookup"><span data-stu-id="34c46-396">**Result**:</span></span>
  - <span data-ttu-id="34c46-397">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="34c46-397">**Pass**</span></span>
  - <span data-ttu-id="34c46-398">**Fail**</span><span class="sxs-lookup"><span data-stu-id="34c46-398">**Fail**</span></span>
  - <span data-ttu-id="34c46-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="34c46-399">**SoftPass**</span></span>
  - <span data-ttu-id="34c46-400">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="34c46-400">**None**</span></span>
  - <span data-ttu-id="34c46-401">**Outros**</span><span class="sxs-lookup"><span data-stu-id="34c46-401">**Other**</span></span>
- <span data-ttu-id="34c46-402">**Tipo de spoof**: **Interno** e **Externo**</span><span class="sxs-lookup"><span data-stu-id="34c46-402">**Spoof type**: **Internal** and **External**</span></span>

![Página de relatório de email de spoof no portal Microsoft 365 Defender página](../../media/spoof-detections-report-page.png)

<span data-ttu-id="34c46-404">Na tabela de detalhes abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="34c46-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="34c46-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-405">**Date**</span></span>
- <span data-ttu-id="34c46-406">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="34c46-406">**Spoofed user**</span></span>
- <span data-ttu-id="34c46-407">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="34c46-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="34c46-408">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="34c46-408">**Spoof type**</span></span>
- <span data-ttu-id="34c46-409">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="34c46-409">**Result**</span></span>
- <span data-ttu-id="34c46-410">**Código de resultado**</span><span class="sxs-lookup"><span data-stu-id="34c46-410">**Result code**</span></span>
- <span data-ttu-id="34c46-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="34c46-411">**SPF**</span></span>
- <span data-ttu-id="34c46-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="34c46-412">**DKIM**</span></span>
- <span data-ttu-id="34c46-413">**DMARCDMARC**</span><span class="sxs-lookup"><span data-stu-id="34c46-413">**DMARC**</span></span>
- <span data-ttu-id="34c46-414">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="34c46-414">**Message count**</span></span>

<span data-ttu-id="34c46-415">Para obter mais informações sobre códigos de resultados de autenticação composta, consulte [Headers de mensagem anti-spam em Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="34c46-416">Relatório de envios</span><span class="sxs-lookup"><span data-stu-id="34c46-416">Submissions report</span></span>

<span data-ttu-id="34c46-417">O **relatório Envios** mostra informações sobre itens que os administradores relataram à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="34c46-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="34c46-418">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="34c46-419">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-420">Na página **Relatórios & de colaboração** de email, encontre **Envios** e clique em **Exibir detalhes.**</span><span class="sxs-lookup"><span data-stu-id="34c46-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="34c46-421">Para ir diretamente para o relatório, abra <https://security.microsoft.com/adminSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="34c46-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="34c46-422">Para acessar [envios de administrador no portal Microsoft 365 Defender,](admin-submission.md)clique **em Ir para Envios**.</span><span class="sxs-lookup"><span data-stu-id="34c46-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget de envios na página Relatórios de & de colaboração](../../media/submissions-report-widget.png)

<span data-ttu-id="34c46-424">O gráfico mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="34c46-424">The chart shows the following information:</span></span>

- <span data-ttu-id="34c46-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="34c46-425">**Pending**</span></span>
- <span data-ttu-id="34c46-426">**Concluída**</span><span class="sxs-lookup"><span data-stu-id="34c46-426">**Completed**</span></span>

<span data-ttu-id="34c46-427">Na página **Envios,** você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="34c46-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="34c46-428">**Data relatada**: **Hora de início** e hora de **término**</span><span class="sxs-lookup"><span data-stu-id="34c46-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="34c46-429">**Tipo de envio**:</span><span class="sxs-lookup"><span data-stu-id="34c46-429">**Submission type**:</span></span>
  - <span data-ttu-id="34c46-430">**Email**</span><span class="sxs-lookup"><span data-stu-id="34c46-430">**Email**</span></span>
  - <span data-ttu-id="34c46-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="34c46-431">**URL**</span></span>
  - <span data-ttu-id="34c46-432">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="34c46-432">**File**</span></span>
- <span data-ttu-id="34c46-433">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="34c46-433">**Submission ID**</span></span>
- <span data-ttu-id="34c46-434">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="34c46-434">**Network Message ID**</span></span>
- <span data-ttu-id="34c46-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-435">**Sender**</span></span>
- <span data-ttu-id="34c46-436">**Nome**</span><span class="sxs-lookup"><span data-stu-id="34c46-436">**Name**</span></span>
- <span data-ttu-id="34c46-437">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-437">**Submitted by**</span></span>
- <span data-ttu-id="34c46-438">**Motivo para enviar**:</span><span class="sxs-lookup"><span data-stu-id="34c46-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="34c46-439">**Não é lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="34c46-439">**Not junk**</span></span>
  - <span data-ttu-id="34c46-440">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="34c46-440">**Phish**</span></span>
  - <span data-ttu-id="34c46-441">**Malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-441">**Malware**</span></span>
  - <span data-ttu-id="34c46-442">**Spam**</span><span class="sxs-lookup"><span data-stu-id="34c46-442">**Spam**</span></span>
- <span data-ttu-id="34c46-443">**Status da varredura novamente:**</span><span class="sxs-lookup"><span data-stu-id="34c46-443">**Rescan status**:</span></span>
  - <span data-ttu-id="34c46-444">**Pending**</span><span class="sxs-lookup"><span data-stu-id="34c46-444">**Pending**</span></span>
  - <span data-ttu-id="34c46-445">**Concluída**</span><span class="sxs-lookup"><span data-stu-id="34c46-445">**Completed**</span></span>

<span data-ttu-id="34c46-446">A tabela de detalhes abaixo do gráfico  mostra as mesmas informações e  tem as mesmas opções de colunas Group ou Customize como na guia Enviado para análise em  **Envios** de colaboração de email & \> .</span><span class="sxs-lookup"><span data-stu-id="34c46-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="34c46-447">Para obter mais informações, consulte [Exibir envios de administrador para a Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="34c46-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![Página de relatório de envios no portal Microsoft 365 Defender de envio](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="34c46-449">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="34c46-449">Threat protection status report</span></span>

<span data-ttu-id="34c46-450">O **relatório de status de** proteção contra ameaças está disponível no EOP e no Defender para Office 365; no entanto, os relatórios contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="34c46-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="34c46-451">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectados no email, mas não informações sobre arquivos [mal-intencionados detectados](mdo-for-spo-odb-and-teams.md)por Cofre Anexos para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="34c46-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="34c46-452">O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) bloqueados pelo mecanismo anti-malware, zap (limpeza automática zero [hora)](zero-hour-auto-purge.md)e o Defender para recursos do Office 365, como [links Cofre,](safe-links.md) [anexos Cofre](safe-attachments.md)e recursos de proteção contra representação em políticas [anti-phishing.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="34c46-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="34c46-453">Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="34c46-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="34c46-454">**Observação**: é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="34c46-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="34c46-455">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-456">Na página **Relatórios de colaboração &** email, encontre o status da proteção contra **ameaças** e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="34c46-457">Para ir diretamente ao relatório, abra uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="34c46-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="34c46-458">Defender para Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="34c46-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="34c46-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="34c46-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![Widget de status de proteção contra ameaças na página Relatórios de colaboração & email](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="34c46-461">Por padrão, o gráfico mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="34c46-462">Se você clicar **em Filtrar** na página relatório de **status** de proteção contra ameaças, poderá selecionar um intervalo de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias).</span><span class="sxs-lookup"><span data-stu-id="34c46-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="34c46-463">A tabela de detalhes permite a filtragem por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="34c46-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="34c46-464">As exibições disponíveis são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="34c46-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="34c46-465">Exibir dados por Visão Geral</span><span class="sxs-lookup"><span data-stu-id="34c46-465">View data by Overview</span></span>

![Visão geral no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="34c46-467">Na **exibição Exibir dados por visão** geral, as seguintes informações de detecção são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="34c46-468">**Malware de email**</span><span class="sxs-lookup"><span data-stu-id="34c46-468">**Email malware**</span></span>
- <span data-ttu-id="34c46-469">**Phishing de email**</span><span class="sxs-lookup"><span data-stu-id="34c46-469">**Email phish**</span></span>
- <span data-ttu-id="34c46-470">**Malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="34c46-470">**Content malware**</span></span>

<span data-ttu-id="34c46-471">Nenhuma tabela de detalhes está disponível abaixo do gráfico.</span><span class="sxs-lookup"><span data-stu-id="34c46-471">No details table is available below the chart.</span></span>

<span data-ttu-id="34c46-472">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-473">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-474">**Detecção**: **malware de email,** **phishing** de email ou **malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="34c46-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="34c46-475">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-476">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-477">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-478">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-478">**Direction**</span></span>
- <span data-ttu-id="34c46-479">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-479">**Domain**</span></span>
- <span data-ttu-id="34c46-480">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-480">**Policy type**</span></span>

<span data-ttu-id="34c46-481">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="34c46-482">Exibir dados por Email \> Phish and Chart breakdown by Detection Technology</span><span class="sxs-lookup"><span data-stu-id="34c46-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![Exibição de tecnologia de detecção para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="34c46-484">Na **exibição Exibir dados por \> phishing** de email e **gráfico** por tecnologia de detecção, as seguintes informações são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="34c46-485">**Reputação mal-intencionada** da URL : reputação de URL mal-intencionada gerada pelo <sup>\*</sup> Defender para Office 365 detonações em outros Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="34c46-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="34c46-486">**Filtro avançado**: sinais de phishing com base no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="34c46-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="34c46-487">**Filtro geral**: sinais de phishing com base em regras de analista.</span><span class="sxs-lookup"><span data-stu-id="34c46-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="34c46-488">**Spoof intra-org**: O remetente está tentando fazer a spoof do domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="34c46-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="34c46-489">**Spoof external domain**: O remetente está tentando fazer a spoof de algum outro domínio.</span><span class="sxs-lookup"><span data-stu-id="34c46-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="34c46-490">**Spoof DMARC**: Falha de autenticação DMARC em mensagens.</span><span class="sxs-lookup"><span data-stu-id="34c46-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="34c46-491">**Marca de representação**: Representação de marcas conhecidas com base em senders.</span><span class="sxs-lookup"><span data-stu-id="34c46-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="34c46-492">**Detecção de análise mista**</span><span class="sxs-lookup"><span data-stu-id="34c46-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="34c46-493">**Reputação de arquivos**</span><span class="sxs-lookup"><span data-stu-id="34c46-493">**File reputation**</span></span>
- <span data-ttu-id="34c46-494">**Correspondência de impressão digital**</span><span class="sxs-lookup"><span data-stu-id="34c46-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="34c46-495">**Reputação de detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-496">**Detonação de URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-497">**Usuário de representação**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-498">**Domínio de representação** <sup>\*</sup> : Representação de domínios que o cliente possui ou define.</span><span class="sxs-lookup"><span data-stu-id="34c46-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="34c46-499">**Representação de inteligência de caixa de** correio : Representação de usuários <sup>\*</sup> definidos pelo administrador ou aprendidos por meio da inteligência da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="34c46-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="34c46-500">**Detonação de arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-501">**Campanha**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="34c46-502">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-503">**Date**</span></span>
- <span data-ttu-id="34c46-504">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-504">**Subject**</span></span>
- <span data-ttu-id="34c46-505">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-505">**Sender**</span></span>
- <span data-ttu-id="34c46-506">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-506">**Recipients**</span></span>
- <span data-ttu-id="34c46-507">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-507">**Detected by**</span></span>
- <span data-ttu-id="34c46-508">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-508">**Delivery Status**</span></span>
- <span data-ttu-id="34c46-509">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="34c46-509">**Source of Compromise**</span></span>
- <span data-ttu-id="34c46-510">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-510">**Tags**</span></span>

<span data-ttu-id="34c46-511">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-512">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-513">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="34c46-513">**Detection**</span></span>
- <span data-ttu-id="34c46-514">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-515">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-515">**Direction**</span></span>
- <span data-ttu-id="34c46-516">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-517">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-518">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-518">**Domain**</span></span>
- <span data-ttu-id="34c46-519">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-519">**Policy type**</span></span>
- <span data-ttu-id="34c46-520">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="34c46-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="34c46-521">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-521">**Recipients**</span></span>

<span data-ttu-id="34c46-522">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="34c46-523">Exibir dados por \> Malware de Email e Divisão de Gráficos pela Tecnologia de Detecção</span><span class="sxs-lookup"><span data-stu-id="34c46-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![Exibição de tecnologia de detecção para malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="34c46-525">Na **exibição Exibir dados por \> Malware** de Email e **Gráfico** pela Tecnologia de Detecção, as seguintes informações são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="34c46-526">**Detonação de** <sup>\*</sup> arquivo : detecção por Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="34c46-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="34c46-527">**Reputação de detonação de** <sup>\*</sup> arquivo : toda a reputação de arquivo mal-intencionado gerada pelo Defender para Office 365 detonações.</span><span class="sxs-lookup"><span data-stu-id="34c46-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="34c46-528">**Reputação de arquivos**</span><span class="sxs-lookup"><span data-stu-id="34c46-528">**File reputation**</span></span>
- <span data-ttu-id="34c46-529">**Mecanismo anti-malware** <sup>\*</sup> : Detecção de mecanismos anti-malware.</span><span class="sxs-lookup"><span data-stu-id="34c46-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="34c46-530">Bloco de tipo de arquivo de **política anti-malware**: São mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="34c46-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="34c46-531">**Reputação mal-intencionada de URL**</span><span class="sxs-lookup"><span data-stu-id="34c46-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="34c46-532">**Detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="34c46-532">**URL detonation**</span></span>
- <span data-ttu-id="34c46-533">**Reputação da detonação de URL**</span><span class="sxs-lookup"><span data-stu-id="34c46-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="34c46-534">**Campanha**</span><span class="sxs-lookup"><span data-stu-id="34c46-534">**Campaign**</span></span>

<span data-ttu-id="34c46-535">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-536">**Date**</span></span>
- <span data-ttu-id="34c46-537">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-537">**Subject**</span></span>
- <span data-ttu-id="34c46-538">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-538">**Sender**</span></span>
- <span data-ttu-id="34c46-539">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-539">**Recipients**</span></span>
- <span data-ttu-id="34c46-540">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-540">**Detected by**</span></span>
- <span data-ttu-id="34c46-541">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-541">**Delivery Status**</span></span>
- <span data-ttu-id="34c46-542">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="34c46-542">**Source of Compromise**</span></span>
- <span data-ttu-id="34c46-543">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-543">**Tags**</span></span>

<span data-ttu-id="34c46-544">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-545">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-546">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="34c46-546">**Detection**</span></span>
- <span data-ttu-id="34c46-547">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-548">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-548">**Direction**</span></span>
- <span data-ttu-id="34c46-549">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-550">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-551">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-551">**Domain**</span></span>
- <span data-ttu-id="34c46-552">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-552">**Policy type**</span></span>
- <span data-ttu-id="34c46-553">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="34c46-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="34c46-554">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-554">**Recipients**</span></span>

<span data-ttu-id="34c46-555">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="34c46-556">Divisão de gráfico por tipo de política e Exibir dados por Phishing de Email \> ou Exibir dados por Malware de \> Email</span><span class="sxs-lookup"><span data-stu-id="34c46-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Exibição de tipo de política para email de phishing ou email de malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="34c46-558">Na divisão **Gráfico por Tipo** de Política e Exibir dados por **Phishing \>** de Email ou Exibir dados por exibição de Malware de **Email, \>** as seguintes informações são mostradas nos gráficos:</span><span class="sxs-lookup"><span data-stu-id="34c46-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="34c46-559">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-559">**Anti-malware**</span></span>
- <span data-ttu-id="34c46-560">**Cofre Anexos**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="34c46-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="34c46-561">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="34c46-561">**Anti-phish**</span></span>
- <span data-ttu-id="34c46-562">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="34c46-562">**Anti-spam**</span></span>
- <span data-ttu-id="34c46-563">**Regra de fluxo de emails** (também conhecida como regra de transporte)</span><span class="sxs-lookup"><span data-stu-id="34c46-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="34c46-564">**Outros**</span><span class="sxs-lookup"><span data-stu-id="34c46-564">**Others**</span></span>

<span data-ttu-id="34c46-565">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-566">**Date**</span></span>
- <span data-ttu-id="34c46-567">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-567">**Subject**</span></span>
- <span data-ttu-id="34c46-568">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-568">**Sender**</span></span>
- <span data-ttu-id="34c46-569">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-569">**Recipients**</span></span>
- <span data-ttu-id="34c46-570">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-570">**Detected by**</span></span>
- <span data-ttu-id="34c46-571">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-571">**Delivery Status**</span></span>
- <span data-ttu-id="34c46-572">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="34c46-572">**Source of Compromise**</span></span>
- <span data-ttu-id="34c46-573">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-573">**Tags**</span></span>

<span data-ttu-id="34c46-574">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-575">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-576">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="34c46-576">**Detection**</span></span>
- <span data-ttu-id="34c46-577">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-578">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-578">**Direction**</span></span>
- <span data-ttu-id="34c46-579">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-580">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-581">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-581">**Domain**</span></span>
- <span data-ttu-id="34c46-582">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-582">**Policy type**</span></span>
- <span data-ttu-id="34c46-583">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="34c46-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="34c46-584">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-584">**Recipients**</span></span>

<span data-ttu-id="34c46-585">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="34c46-586">Divisão de gráficos por status de entrega e Exibir dados por Phishing de Email \> ou Exibir dados por Malware de \> Email</span><span class="sxs-lookup"><span data-stu-id="34c46-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![Exibição de status de entrega para email de phishing e email de malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="34c46-588">Na divisão **gráfico por status** de entrega e Exibir dados por **Phishing \>** de Email ou Exibir dados por exibição **de \> Malware** de Email, as seguintes informações são mostradas nos gráficos:</span><span class="sxs-lookup"><span data-stu-id="34c46-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="34c46-589">**Caixa de correio hospedada: Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="34c46-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="34c46-590">**Caixa de correio hospedada: Lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="34c46-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="34c46-591">**Caixa de correio hospedada: Pasta personalizada**</span><span class="sxs-lookup"><span data-stu-id="34c46-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="34c46-592">**Caixa de correio hospedada: itens excluídos**</span><span class="sxs-lookup"><span data-stu-id="34c46-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="34c46-593">**Encaminhado**</span><span class="sxs-lookup"><span data-stu-id="34c46-593">**Forwarded**</span></span>
- <span data-ttu-id="34c46-594">**Servidor local: Entregue**</span><span class="sxs-lookup"><span data-stu-id="34c46-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="34c46-595">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="34c46-595">**Quarantine**</span></span>
- <span data-ttu-id="34c46-596">**Falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-596">**Delivery failed**</span></span>
- <span data-ttu-id="34c46-597">**Descartado**</span><span class="sxs-lookup"><span data-stu-id="34c46-597">**Dropped**</span></span>

<span data-ttu-id="34c46-598">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-599">**Date**</span></span>
- <span data-ttu-id="34c46-600">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-600">**Subject**</span></span>
- <span data-ttu-id="34c46-601">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-601">**Sender**</span></span>
- <span data-ttu-id="34c46-602">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-602">**Recipients**</span></span>
- <span data-ttu-id="34c46-603">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-603">**Detected by**</span></span>
- <span data-ttu-id="34c46-604">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-604">**Delivery Status**</span></span>
- <span data-ttu-id="34c46-605">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="34c46-605">**Source of Compromise**</span></span>
- <span data-ttu-id="34c46-606">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-606">**Tags**</span></span>

<span data-ttu-id="34c46-607">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-608">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-609">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="34c46-609">**Detection**</span></span>
- <span data-ttu-id="34c46-610">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-611">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-611">**Direction**</span></span>
- <span data-ttu-id="34c46-612">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-613">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-614">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-614">**Domain**</span></span>
- <span data-ttu-id="34c46-615">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-615">**Policy type**</span></span>
- <span data-ttu-id="34c46-616">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="34c46-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="34c46-617">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-617">**Recipients**</span></span>

<span data-ttu-id="34c46-618">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="34c46-619">Exibir dados por Malware de \> Conteúdo</span><span class="sxs-lookup"><span data-stu-id="34c46-619">View data by Content \> Malware</span></span>

![Exibição de malware de conteúdo no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="34c46-621">Na **exibição Exibir dados por \> Malware** de Conteúdo, as informações a seguir são mostradas no gráfico do Microsoft Defender para Office 365 organizações:</span><span class="sxs-lookup"><span data-stu-id="34c46-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="34c46-622">**Mecanismo anti-malware**: arquivos mal-intencionados detectados no Sharepoint, OneDrive e Microsoft Teams pela detecção interna de [vírus no Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="34c46-623">**Detonação de** arquivo : Arquivos mal-intencionados [detectados por Cofre anexos](mdo-for-spo-odb-and-teams.md)para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="34c46-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="34c46-624">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-625">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-626">**Localização**</span><span class="sxs-lookup"><span data-stu-id="34c46-626">**Location**</span></span>
- <span data-ttu-id="34c46-627">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-627">**Detected by**</span></span>
- <span data-ttu-id="34c46-628">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-628">**Malware name**</span></span>

<span data-ttu-id="34c46-629">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-630">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-631">**Detecção**: **mecanismo anti-malware ou** **detonação de arquivo**</span><span class="sxs-lookup"><span data-stu-id="34c46-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="34c46-632">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="34c46-633">Exibir dados por substituição do sistema</span><span class="sxs-lookup"><span data-stu-id="34c46-633">View data by System override</span></span>

![Exibição de substituição de mensagens no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="34c46-635">No **exibição Exibir dados por substituição do** sistema, as informações do motivo de substituição a seguir são mostradas no gráfico:</span><span class="sxs-lookup"><span data-stu-id="34c46-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="34c46-636">**Ignorar local**</span><span class="sxs-lookup"><span data-stu-id="34c46-636">**On-premises skip**</span></span>
- <span data-ttu-id="34c46-637">**Ip allow**</span><span class="sxs-lookup"><span data-stu-id="34c46-637">**IP allow**</span></span>
- <span data-ttu-id="34c46-638">**Exchange de transporte de email** (regra de fluxo de emails)</span><span class="sxs-lookup"><span data-stu-id="34c46-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="34c46-639">**Senders permitidos pela organização**</span><span class="sxs-lookup"><span data-stu-id="34c46-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="34c46-640">**Domínios permitidos pela organização**</span><span class="sxs-lookup"><span data-stu-id="34c46-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="34c46-641">**ZAP não habilitado**</span><span class="sxs-lookup"><span data-stu-id="34c46-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="34c46-642">**Pasta Lixo Eletrônico não habilitada**</span><span class="sxs-lookup"><span data-stu-id="34c46-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="34c46-643">**Usuário Cofre Remetente**</span><span class="sxs-lookup"><span data-stu-id="34c46-643">**User Safe Sender**</span></span>
- <span data-ttu-id="34c46-644">**Domínio Cofre usuário**</span><span class="sxs-lookup"><span data-stu-id="34c46-644">**User Safe Domain**</span></span>

<span data-ttu-id="34c46-645">Na tabela de detalhes abaixo do gráfico, as seguintes informações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="34c46-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="34c46-646">**Date**</span></span>
- <span data-ttu-id="34c46-647">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="34c46-647">**Subject**</span></span>
- <span data-ttu-id="34c46-648">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-648">**Sender**</span></span>
- <span data-ttu-id="34c46-649">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-649">**Recipients**</span></span>
- <span data-ttu-id="34c46-650">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-650">**Detected by**</span></span>
- <span data-ttu-id="34c46-651">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="34c46-651">**Delivery Status**</span></span>
- <span data-ttu-id="34c46-652">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="34c46-652">**Source of Compromise**</span></span>
- <span data-ttu-id="34c46-653">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-653">**Tags**</span></span>

<span data-ttu-id="34c46-654">Se você clicar em **Filtrar,** os seguintes filtros estarão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="34c46-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="34c46-655">Data de início e data **de** **término** **(UTC)**</span><span class="sxs-lookup"><span data-stu-id="34c46-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="34c46-656">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="34c46-656">**Detection**</span></span>
- <span data-ttu-id="34c46-657">**Protegido por**: **MDO** (Defender para Office 365) ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="34c46-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="34c46-658">**Direção**</span><span class="sxs-lookup"><span data-stu-id="34c46-658">**Direction**</span></span>
- <span data-ttu-id="34c46-659">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="34c46-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="34c46-660">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="34c46-661">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="34c46-661">**Domain**</span></span>
- <span data-ttu-id="34c46-662">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="34c46-662">**Policy type**</span></span>
- <span data-ttu-id="34c46-663">**Nome da política** (somente tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="34c46-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="34c46-664">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="34c46-664">**Recipients**</span></span>

<span data-ttu-id="34c46-665">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="34c46-666"><sup>\*</sup>Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="34c46-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="34c46-667">Relatório de malware principal</span><span class="sxs-lookup"><span data-stu-id="34c46-667">Top malware report</span></span>

<span data-ttu-id="34c46-668">O **relatório de malware** Top mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="34c46-669">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-670">Na página **Relatórios de colaboração &** email, encontre o malware **principal** e clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="34c46-671">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="34c46-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Principal widget de malware na página Relatórios de & de colaboração](../../media/top-malware-report-widget.png)

<span data-ttu-id="34c46-673">Quando você passar o mouse sobre uma cunha no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="34c46-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="34c46-674">Na página **Relatório de malware superior,** uma versão maior do gráfico de pizza é exibida na página de relatório. A tabela de detalhes abaixo do gráfico mostra as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="34c46-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="34c46-675">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="34c46-675">**Top malware**</span></span>
- <span data-ttu-id="34c46-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="34c46-676">**Count**</span></span>

<span data-ttu-id="34c46-677">Se você clicar **em Filtrar,** poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="34c46-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![Exibição de relatório de malware principal](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="34c46-679">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="34c46-679">URL threat protection report</span></span>

<span data-ttu-id="34c46-680">O **relatório de proteção contra** ameaças de URL está disponível apenas no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="34c46-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="34c46-681">Para obter mais informações, consulte [RELATÓRIO de proteção contra ameaças de URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="34c46-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="34c46-682">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="34c46-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34c46-683">Para que o relatório de mensagens **relatadas** pelo usuário funcione corretamente, o **log** de auditoria deve ser ligado para seu ambiente Microsoft 365 ambiente.</span><span class="sxs-lookup"><span data-stu-id="34c46-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="34c46-684">Isso normalmente é feito por alguém que tem a função Logs de Auditoria atribuída Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="34c46-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="34c46-685">Para obter mais informações, consulte Ativar ou desativar [Microsoft 365 pesquisa de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="34c46-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="34c46-686">O **relatório** de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento [Mensagem](enable-the-report-message-add-in.md) de Relatório ou o complemento Relatar [Phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="34c46-687">Para exibir o relatório no portal Microsoft 365 Defender, acesse **Relatórios** \> **Email & colaboração** Email & relatórios de \> **colaboração**.</span><span class="sxs-lookup"><span data-stu-id="34c46-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="34c46-688">Na página **Relatórios de colaboração de &** email, encontre mensagens **relatadas pelo** usuário e clique em Exibir **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="34c46-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="34c46-689">Para ir diretamente para o relatório, abra <https://security.microsoft.com/reports/userSubmissionReport> .</span><span class="sxs-lookup"><span data-stu-id="34c46-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="34c46-690">Para acessar [envios de administrador no portal Microsoft 365 Defender,](admin-submission.md)clique **em Ir para Envios**.</span><span class="sxs-lookup"><span data-stu-id="34c46-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![Widget de mensagens relatadas pelo usuário na página Relatórios de & de colaboração](../../media/user-reported-messages-widget.png)

<span data-ttu-id="34c46-692">Na página **Mensagens relatadas pelo** usuário, você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtrar** e selecionando um ou mais dos seguintes valores no flyout que aparece:</span><span class="sxs-lookup"><span data-stu-id="34c46-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="34c46-693">**Data relatada**: **Hora de início** e hora de **término**</span><span class="sxs-lookup"><span data-stu-id="34c46-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="34c46-694">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-694">**Reported by**</span></span>
- <span data-ttu-id="34c46-695">**Assunto do email**</span><span class="sxs-lookup"><span data-stu-id="34c46-695">**Email subject**</span></span>
- <span data-ttu-id="34c46-696">**ID da mensagem relatada**</span><span class="sxs-lookup"><span data-stu-id="34c46-696">**Message reported ID**</span></span>
- <span data-ttu-id="34c46-697">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="34c46-697">**Network Message ID**</span></span>
- <span data-ttu-id="34c46-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-698">**Sender**</span></span>
- <span data-ttu-id="34c46-699">**Motivo relatado**</span><span class="sxs-lookup"><span data-stu-id="34c46-699">**Reported reason**</span></span>
  - <span data-ttu-id="34c46-700">**Não é lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="34c46-700">**Not junk**</span></span>
  - <span data-ttu-id="34c46-701">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="34c46-701">**Phish**</span></span>
  - <span data-ttu-id="34c46-702">**Spam**</span><span class="sxs-lookup"><span data-stu-id="34c46-702">**Spam**</span></span>
- <span data-ttu-id="34c46-703">**Simulação de phishing**: **Sim** ou **Não**</span><span class="sxs-lookup"><span data-stu-id="34c46-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="34c46-704">Quando terminar de configurar os filtros, clique em **Aplicar,** **Cancelar** ou **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="34c46-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="34c46-705">Para agrupar as entradas, clique em **Grupo** e selecione um dos seguintes valores na listada:</span><span class="sxs-lookup"><span data-stu-id="34c46-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="34c46-706">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="34c46-706">**None**</span></span>
- <span data-ttu-id="34c46-707">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="34c46-707">**Reason**</span></span>
- <span data-ttu-id="34c46-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-708">**Sender**</span></span>
- <span data-ttu-id="34c46-709">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-709">**Reported by**</span></span>
- <span data-ttu-id="34c46-710">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="34c46-710">**Rescan result**</span></span>
- <span data-ttu-id="34c46-711">**Simulação de phishing**</span><span class="sxs-lookup"><span data-stu-id="34c46-711">**Phish simulation**</span></span>

![Relatório de mensagens relatadas pelo usuário](../../media/user-reported-messages-report.png)

<span data-ttu-id="34c46-713">Na tabela de detalhes abaixo do gráfico, você pode ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="34c46-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="34c46-714">**Assunto do email**</span><span class="sxs-lookup"><span data-stu-id="34c46-714">**Email subject**</span></span>
- <span data-ttu-id="34c46-715">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="34c46-715">**Reported by**</span></span>
- <span data-ttu-id="34c46-716">**Data relatada**</span><span class="sxs-lookup"><span data-stu-id="34c46-716">**Date reported**</span></span>
- <span data-ttu-id="34c46-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="34c46-717">**Sender**</span></span>
- <span data-ttu-id="34c46-718">**Motivo relatado**</span><span class="sxs-lookup"><span data-stu-id="34c46-718">**Reported reason**</span></span>
- <span data-ttu-id="34c46-719">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="34c46-719">**Rescan result**</span></span>
- <span data-ttu-id="34c46-720">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="34c46-720">**Tags**</span></span>

<span data-ttu-id="34c46-721">Para enviar uma mensagem à Microsoft para análise, selecione a entrada da mensagem na tabela, clique em Enviar para a **Microsoft** para análise e selecione um dos seguintes valores na lista abaixo:</span><span class="sxs-lookup"><span data-stu-id="34c46-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="34c46-722">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="34c46-722">**Report clean**</span></span>
- <span data-ttu-id="34c46-723">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="34c46-723">**Report phishing**</span></span>
- <span data-ttu-id="34c46-724">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="34c46-724">**Report malware**</span></span>
- <span data-ttu-id="34c46-725">**Relatar spam**'</span><span class="sxs-lookup"><span data-stu-id="34c46-725">**Report spam**'</span></span>
- <span data-ttu-id="34c46-726">**Investigação de gatilho** (Defender para Office 365)</span><span class="sxs-lookup"><span data-stu-id="34c46-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="34c46-727">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="34c46-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="34c46-728">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de função no portal Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="34c46-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="34c46-729">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="34c46-729">**Organization Management**</span></span>
- <span data-ttu-id="34c46-730">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="34c46-730">**Security Administrator**</span></span>
- <span data-ttu-id="34c46-731">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="34c46-731">**Security Reader**</span></span>
- <span data-ttu-id="34c46-732">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="34c46-732">**Global Reader**</span></span>

<span data-ttu-id="34c46-733">Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender .](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="34c46-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="34c46-734">**Observação**: adicionar usuários à função Active Directory do Azure correspondente no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no _portal_ do Microsoft 365 Defender e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="34c46-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="34c46-735">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="34c46-736">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="34c46-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="34c46-737">Se você não estiver vendo dados em seus relatórios, verifique duas vezes se suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="34c46-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="34c46-738">Para saber mais, confira [Proteger contra ameaças](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="34c46-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="34c46-739">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="34c46-739">Related topics</span></span>

[<span data-ttu-id="34c46-740">Proteção anti-spam e anti-malware no EOP</span><span class="sxs-lookup"><span data-stu-id="34c46-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="34c46-741">Relatórios inteligentes e percepções no portal Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="34c46-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="34c46-742">Exibir relatórios de fluxo de emails no portal Microsoft 365 Defender de email</span><span class="sxs-lookup"><span data-stu-id="34c46-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="34c46-743">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="34c46-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
