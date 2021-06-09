---
title: Exibir relatórios de segurança de email no Centro de Conformidade e Segurança
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
description: Saiba como encontrar e usar relatórios de segurança de email para sua organização. Os relatórios de segurança de email estão disponíveis no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11fe6fd76d21b2dbd7a3e651d40efaa79f675a43
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52531002"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="b0be7-104">Exibir relatórios de segurança de email no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="b0be7-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b0be7-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="b0be7-105">**Applies to**</span></span>
- [<span data-ttu-id="b0be7-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b0be7-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b0be7-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b0be7-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="b0be7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b0be7-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="b0be7-109">Vários relatórios estão disponíveis no Centro de Conformidade e Segurança & para ajudá-lo [a](https://protection.office.com) ver como os recursos de segurança de email, como anti-spam, anti-malware e recursos de criptografia no Microsoft 365 estão protegendo sua organização.</span><span class="sxs-lookup"><span data-stu-id="b0be7-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="b0be7-110">Se você tiver as [permissões necessárias,](#what-permissions-are-needed-to-view-these-reports)poderá exibir esses relatórios no Centro de Conformidade e Segurança & indo para **Painel de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="b0be7-111">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="b0be7-113">Relatório de usuários comprometidos</span><span class="sxs-lookup"><span data-stu-id="b0be7-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="b0be7-114">Este relatório está disponível em organizações Microsoft 365 com Exchange Online caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="b0be7-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="b0be7-115">Ele não está disponível em organizações autônomas Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="b0be7-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="b0be7-116">O **relatório Usuários Comprometidos** mostra o número de contas de usuário que foram marcadas como **Suspeitas** ou **Restritas** nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="b0be7-117">As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas.</span><span class="sxs-lookup"><span data-stu-id="b0be7-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="b0be7-118">Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="b0be7-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="b0be7-119">Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="b0be7-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget de usuários comprometidos no painel Relatórios](../../media/compromised-users-report-widget.png)

<span data-ttu-id="b0be7-121">A exibição agregada mostra os dados dos últimos 90 dias e a exibição de detalhes mostra os dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="b0be7-122">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de Relatórios \>  e selecione **Usuários comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="b0be7-123">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="b0be7-124">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b0be7-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b0be7-125">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="b0be7-126">**Suspeito**: a conta de usuário enviou emails suspeitos e corre o risco de ser restringida ao envio de emails.</span><span class="sxs-lookup"><span data-stu-id="b0be7-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="b0be7-127">**Restrito**: a conta de usuário foi restrita ao envio de emails devido a padrões altamente suspeitos.</span><span class="sxs-lookup"><span data-stu-id="b0be7-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Exibir relatório no relatório Usuários Comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="b0be7-129">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b0be7-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b0be7-130">**Hora da criação**</span><span class="sxs-lookup"><span data-stu-id="b0be7-130">**Creation time**</span></span>
- <span data-ttu-id="b0be7-131">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-131">**User ID**</span></span>
- <span data-ttu-id="b0be7-132">**Action**</span><span class="sxs-lookup"><span data-stu-id="b0be7-132">**Action**</span></span>

<span data-ttu-id="b0be7-133">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="b0be7-134">Relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-134">Encryption report</span></span>

<span data-ttu-id="b0be7-135">O **relatório de criptografia** está disponível no EOP (assinaturas com caixas de correio no Exchange Online ou EOP autônomo sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="b0be7-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="b0be7-136">A equipe de segurança da sua organização pode usar informações neste relatório para identificar padrões e aplicar ou ajustar de forma proativa políticas para mensagens de email confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b0be7-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="b0be7-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b0be7-137">For example:</span></span>

- <span data-ttu-id="b0be7-138">Se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="b0be7-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="b0be7-139">Para obter mais informações, consulte [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="b0be7-140">Se você tiver vários modelos de criptografia disponíveis, mas ninguém os estiver usando, poderá explorar se os usuários precisam de treinamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="b0be7-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="b0be7-141">A exibição agregada permite a filtragem dos últimos 90 dias, enquanto a exibição de detalhes permite a filtragem por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="b0be7-142">Para exibir o relatório, abra o [Centro](https://protection.office.com)de Conformidade & segurança, vá **para** Painel de Relatórios \>  e selecione Relatório **de criptografia.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="b0be7-143">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="b0be7-144">Para saber mais sobre criptografia, consulte [Criptografia de email em Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="b0be7-145">Exibição de relatório para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-145">Report view for the Encryption report</span></span>

<span data-ttu-id="b0be7-146">Você pode usar os seguintes filtros no gráfico:</span><span class="sxs-lookup"><span data-stu-id="b0be7-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="b0be7-147">**Exibir dados por: Relatório de Criptografia** de Mensagens e Quebra **por: Método de** criptografia : Os seguintes métodos de criptografia estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b0be7-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="b0be7-148">**Criptografia por usuário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-148">**Encryption by user**</span></span>
  - <span data-ttu-id="b0be7-149">**Criptografia por política**</span><span class="sxs-lookup"><span data-stu-id="b0be7-149">**Encryption by policy**</span></span>

  <span data-ttu-id="b0be7-150">Se você clicar em **Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="b0be7-151">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-152">Método de criptografia.</span><span class="sxs-lookup"><span data-stu-id="b0be7-152">Encryption method.</span></span>
  - <span data-ttu-id="b0be7-153">Modelo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="b0be7-153">Encryption template.</span></span>

- <span data-ttu-id="b0be7-154">**Exibir dados por: Relatório de Criptografia** de Mensagens e Quebra **por: Modelo** de criptografia : Os seguintes métodos de criptografia estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b0be7-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="b0be7-155">**Não encaminhar**</span><span class="sxs-lookup"><span data-stu-id="b0be7-155">**Do not forward**</span></span>
  - <span data-ttu-id="b0be7-156">**Criptografar somente**</span><span class="sxs-lookup"><span data-stu-id="b0be7-156">**Encrypt only**</span></span>
  - <span data-ttu-id="b0be7-157">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="b0be7-157">**OME previous**</span></span>
  - <span data-ttu-id="b0be7-158">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="b0be7-158">**Custom**</span></span>

  <span data-ttu-id="b0be7-159">Se você clicar em **Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="b0be7-160">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-161">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-161">Encryption method</span></span>
  - <span data-ttu-id="b0be7-162">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-162">Encryption template</span></span>

- <span data-ttu-id="b0be7-163">**Exibir dados por: Os 5** principais domínios de destinatários : Este exibição mostra um gráfico de pizza com contagens de mensagens enviadas para os cinco domínios de destinatário principais.</span><span class="sxs-lookup"><span data-stu-id="b0be7-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="b0be7-164">Se você clicar **em Filtros,** você poderá selecionar uma data **de início** e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="b0be7-165">Exibição de tabela de detalhes para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="b0be7-166">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="b0be7-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b0be7-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="b0be7-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="b0be7-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-168">**Date**</span></span>
  - <span data-ttu-id="b0be7-169">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-169">**Sender address**</span></span>
  - <span data-ttu-id="b0be7-170">**Modelo de criptografia**</span><span class="sxs-lookup"><span data-stu-id="b0be7-170">**Encryption template**</span></span>
  - <span data-ttu-id="b0be7-171">**Método de criptografia**</span><span class="sxs-lookup"><span data-stu-id="b0be7-171">**Encryption method**</span></span>
  - <span data-ttu-id="b0be7-172">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-172">**Recipient address**</span></span>
  - <span data-ttu-id="b0be7-173">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b0be7-173">**Subject**</span></span>

- <span data-ttu-id="b0be7-174">**Exibir dados por: Principais 5 domínios de destinatário:**</span><span class="sxs-lookup"><span data-stu-id="b0be7-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="b0be7-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-175">**Date**</span></span>
  - <span data-ttu-id="b0be7-176">**Domínio de destinatário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-176">**Recipient domain**</span></span>
  - <span data-ttu-id="b0be7-177">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="b0be7-177">**Message count**</span></span>

<span data-ttu-id="b0be7-178">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b0be7-179">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="b0be7-180">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-180">Encryption method</span></span>
- <span data-ttu-id="b0be7-181">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="b0be7-181">Encryption template</span></span>

<span data-ttu-id="b0be7-182">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="b0be7-183">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="b0be7-183">Mailflow status report</span></span>

<span data-ttu-id="b0be7-184">O **relatório de status de fluxo de emails** contém informações sobre malware, spam, phishing e mensagens bloqueadas de borda.</span><span class="sxs-lookup"><span data-stu-id="b0be7-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="b0be7-185">Para obter mais detalhes, consulte [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="b0be7-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="b0be7-186">Detecções de malware no relatório de email</span><span class="sxs-lookup"><span data-stu-id="b0be7-186">Malware detections in email report</span></span>

<span data-ttu-id="b0be7-187">As **detecções de malware** no relatório de email mostram informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado por Proteção do Exchange Online ou EOP).</span><span class="sxs-lookup"><span data-stu-id="b0be7-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="b0be7-188">Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="b0be7-189">O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="b0be7-190">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Detecções de malware no email**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="b0be7-191">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecções de malware no widget de email no painel Relatórios](../../media/malware-detections-widget.png)

<span data-ttu-id="b0be7-193">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando:</span><span class="sxs-lookup"><span data-stu-id="b0be7-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="b0be7-194">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="b0be7-195">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="b0be7-195">**Inbound**</span></span>
- <span data-ttu-id="b0be7-196">**Saída**</span><span class="sxs-lookup"><span data-stu-id="b0be7-196">**Outbound**</span></span>

![Exibir relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

<span data-ttu-id="b0be7-198">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b0be7-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b0be7-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-199">**Date**</span></span>
- <span data-ttu-id="b0be7-200">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-200">**Sender address**</span></span>
- <span data-ttu-id="b0be7-201">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-201">**Recipient address**</span></span>
- <span data-ttu-id="b0be7-202">**ID da** mensagem : disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="b0be7-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="b0be7-203">Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="b0be7-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="b0be7-204">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b0be7-204">**Subject**</span></span>
- <span data-ttu-id="b0be7-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="b0be7-205">**Filename**</span></span>
- <span data-ttu-id="b0be7-206">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="b0be7-206">**Malware name**</span></span>

<span data-ttu-id="b0be7-207">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="b0be7-208">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="b0be7-208">Mail latency report</span></span>

<span data-ttu-id="b0be7-209">O **relatório de latência de email** contém informações sobre a entrega de email e a latência de detonação experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b0be7-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="b0be7-210">Para obter mais informações, consulte [Relatório de latência de email](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="b0be7-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="b0be7-211">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="b0be7-211">Sent and received email report</span></span>

<span data-ttu-id="b0be7-212">O **relatório de email** enviado e recebido contém informações sobre malware, spam, regras de fluxo de emails (também conhecidas como regras de transporte) e detecções avançadas de malware depois que o email entra no serviço.</span><span class="sxs-lookup"><span data-stu-id="b0be7-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="b0be7-213">Para obter mais informações, consulte [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="b0be7-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="b0be7-214">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="b0be7-214">Spam detections report</span></span>

<span data-ttu-id="b0be7-215">O **relatório de detecções de** spam mostra mensagens de email de spam que foram bloqueadas pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="b0be7-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="b0be7-216">As mensagens são contadas individualmente, não por destinatário.</span><span class="sxs-lookup"><span data-stu-id="b0be7-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="b0be7-217">Por exemplo, se a mesma mensagem de spam foi enviada para 100 destinatários em sua organização, ela conta como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0be7-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="b0be7-218">A exibição agregada permite a filtragem de 90 dias, enquanto a tabela de detalhes permite a filtragem de 10 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="b0be7-219">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios \>  e selecione Detecções **de spam.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="b0be7-220">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget de detecções de spam no painel Relatórios](../../media/spam-detections-report-widget.png)

<span data-ttu-id="b0be7-222">Para obter mais informações sobre a proteção anti-spam, consulte [Anti-spam protection in EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="b0be7-223">Exibição de relatório para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="b0be7-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="b0be7-224">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="b0be7-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b0be7-225">**Break down by: Action**: Os seguintes tipos de evento são mostrados:</span><span class="sxs-lookup"><span data-stu-id="b0be7-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="b0be7-226">**Conteúdo de spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="b0be7-227">**Bloqueio de IP de spam**</span><span class="sxs-lookup"><span data-stu-id="b0be7-227">**Spam IP block**</span></span>
  - <span data-ttu-id="b0be7-228">**Bloqueio de envelope de spam**</span><span class="sxs-lookup"><span data-stu-id="b0be7-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="b0be7-229">**Filtro DBEB de spam**: Bloqueio de borda baseado em diretório (DBEB)</span><span class="sxs-lookup"><span data-stu-id="b0be7-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="b0be7-230">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantos itens foram bloqueados nesse dia, bem como como esses itens são categorizados.</span><span class="sxs-lookup"><span data-stu-id="b0be7-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Exibição de ação no relatório de detecções de spam](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="b0be7-232">**Break down by: Direction**: The following directions are shown:</span><span class="sxs-lookup"><span data-stu-id="b0be7-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="b0be7-233">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="b0be7-233">**Inbound**</span></span>
  - <span data-ttu-id="b0be7-234">**Saída**</span><span class="sxs-lookup"><span data-stu-id="b0be7-234">**Outbound**</span></span>

  ![Exibição de direção no relatório de detecções de spam](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="b0be7-236">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b0be7-237">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="b0be7-238">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="b0be7-238">Direction values</span></span>
- <span data-ttu-id="b0be7-239">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="b0be7-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="b0be7-240">Exibição de tabela de detalhes para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="b0be7-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="b0be7-241">Se você clicar em **Exibir tabela de detalhes** em qualquer exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="b0be7-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-242">**Date**</span></span>
- <span data-ttu-id="b0be7-243">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-243">**Sender address**</span></span>
- <span data-ttu-id="b0be7-244">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-244">**Recipient address**</span></span>
- <span data-ttu-id="b0be7-245">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="b0be7-245">**Event type**</span></span>
- <span data-ttu-id="b0be7-246">**Action**</span><span class="sxs-lookup"><span data-stu-id="b0be7-246">**Action**</span></span>
- <span data-ttu-id="b0be7-247">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b0be7-247">**Subject**</span></span>

<span data-ttu-id="b0be7-248">Se você clicar **em Filtros** em uma tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="b0be7-249">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="b0be7-250">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="b0be7-250">Direction values</span></span>
- <span data-ttu-id="b0be7-251">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="b0be7-251">Event type values</span></span>

<span data-ttu-id="b0be7-252">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="b0be7-253">Relatório de detecções de spoof</span><span class="sxs-lookup"><span data-stu-id="b0be7-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="b0be7-254">O relatório aprimorado de detecções de Spoof conforme descrito neste artigo está em Visualização, está sujeito a alterações e não está disponível em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="b0be7-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="b0be7-255">A versão mais antiga do relatório mostrava apenas **Emails bons e** **capturados como spam.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="b0be7-256">O **relatório de detecções Spoof** mostra informações sobre mensagens que foram bloqueadas ou permitidas devido à fraude.</span><span class="sxs-lookup"><span data-stu-id="b0be7-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="b0be7-257">Para obter mais informações sobre a spoofing, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b0be7-258">A exibição agregada do relatório permite 45 dias de filtragem, enquanto a exibição de detalhes permite apenas <sup>\*</sup> dez dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="b0be7-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="b0be7-259"><sup>\*</sup> Eventualmente, você poderá usar até 90 dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="b0be7-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="b0be7-260">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Detecções de Spoof**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-260">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="b0be7-261">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-261">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget de detecções de spoof no painel Relatórios](../../media/spoof-detections-widget.png)

<span data-ttu-id="b0be7-263">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens falsas foram detectadas e por quê.</span><span class="sxs-lookup"><span data-stu-id="b0be7-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="b0be7-264">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b0be7-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="b0be7-265">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="b0be7-266">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-266">**Result**</span></span>
  - <span data-ttu-id="b0be7-267">**Passagem**</span><span class="sxs-lookup"><span data-stu-id="b0be7-267">**Pass**</span></span>
  - <span data-ttu-id="b0be7-268">**Fail**</span><span class="sxs-lookup"><span data-stu-id="b0be7-268">**Fail**</span></span>
  - <span data-ttu-id="b0be7-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="b0be7-269">**SoftPass**</span></span>
  - <span data-ttu-id="b0be7-270">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="b0be7-270">**None**</span></span>
  - <span data-ttu-id="b0be7-271">**Outros**</span><span class="sxs-lookup"><span data-stu-id="b0be7-271">**Other**</span></span>

- <span data-ttu-id="b0be7-272">**Tipo de spoof**: **Interno** e **Externo**</span><span class="sxs-lookup"><span data-stu-id="b0be7-272">**Spoof type**: **Internal** and **External**</span></span>

![Exibição de relatório no relatório de detecções de Spoof](../../media/spoof-detections-report-view.png)

<span data-ttu-id="b0be7-274">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b0be7-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b0be7-275">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-275">**Date**</span></span>
- <span data-ttu-id="b0be7-276">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="b0be7-276">**Spoofed user**</span></span>
- <span data-ttu-id="b0be7-277">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="b0be7-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="b0be7-278">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="b0be7-278">**Spoof type**</span></span>
- <span data-ttu-id="b0be7-279">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-279">**Result**</span></span>
- <span data-ttu-id="b0be7-280">**Código de resultado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-280">**Result code**</span></span>
- <span data-ttu-id="b0be7-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="b0be7-281">**SPF**</span></span>
- <span data-ttu-id="b0be7-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="b0be7-282">**DKIM**</span></span>
- <span data-ttu-id="b0be7-283">**DMARCDMARC**</span><span class="sxs-lookup"><span data-stu-id="b0be7-283">**DMARC**</span></span>
- <span data-ttu-id="b0be7-284">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="b0be7-284">**Message count**</span></span>

<span data-ttu-id="b0be7-285">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="b0be7-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="b0be7-286">Para obter mais informações sobre códigos de resultados de autenticação composta, consulte [Headers de mensagem anti-spam em Microsoft 365](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="b0be7-287">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="b0be7-287">Threat protection status report</span></span>

<span data-ttu-id="b0be7-288">O **relatório de status de** proteção contra ameaças está disponível no EOP e no Microsoft Defender para Office 365; no entanto, os relatórios contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="b0be7-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="b0be7-289">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectados no email, mas não informações sobre arquivos [mal-intencionados detectados](mdo-for-spo-odb-and-teams.md)por Cofre Anexos para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="b0be7-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="b0be7-290">O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) que foram bloqueados pelo mecanismo anti-malware, pela limpeza automática zero hora [(ZAP)](zero-hour-auto-purge.md)e pelo Defender para recursos do [Office 365,](safe-links.md)como links Cofre , [anexos Cofre](safe-attachments.md)e [anti-phishing](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="b0be7-291">Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="b0be7-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="b0be7-292">**Observação**: é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0be7-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="b0be7-293">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de \>  Relatórios e selecione Status de proteção **contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-293">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="b0be7-294">Para ir diretamente ao relatório, abra uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="b0be7-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="b0be7-295">Microsoft Defender para Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="b0be7-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="b0be7-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="b0be7-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget de status de proteção contra ameaças no painel Relatórios](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="b0be7-298">Por padrão, o gráfico mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="b0be7-299">Se você clicar **em Filtros,** poderá selecionar um intervalo de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias).</span><span class="sxs-lookup"><span data-stu-id="b0be7-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="b0be7-300">A exibição da tabela de detalhes permite a filtragem por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="b0be7-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="b0be7-301">Exibição de relatório para o relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="b0be7-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="b0be7-302">As seguintes visualizações estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b0be7-302">The following views are available:</span></span>

- <span data-ttu-id="b0be7-303">**Exibir dados por: Visão geral**: As seguintes informações de detecção são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="b0be7-304">**Malware de email**</span><span class="sxs-lookup"><span data-stu-id="b0be7-304">**Email malware**</span></span>
  - <span data-ttu-id="b0be7-305">**Phishing de email**</span><span class="sxs-lookup"><span data-stu-id="b0be7-305">**Email phish**</span></span>
  - <span data-ttu-id="b0be7-306">**Malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="b0be7-306">**Content malware**</span></span>

  ![Visão geral no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="b0be7-308">**Exibir dados por: Conteúdo \> Malware**<sup>1</sup>: As informações a seguir são mostradas para o Microsoft Defender para Office 365 organizações:</span><span class="sxs-lookup"><span data-stu-id="b0be7-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="b0be7-309">**Mecanismo anti-malware**: arquivos mal-intencionados detectados no Sharepoint, OneDrive e Microsoft Teams pela detecção interna de [vírus no Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="b0be7-310">**Detonação de** arquivo : Arquivos mal-intencionados [detectados por Cofre anexos](mdo-for-spo-odb-and-teams.md)para SharePoint, OneDrive e Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="b0be7-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Exibição de malware de conteúdo no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="b0be7-312">**Exibir dados por: Substituição de Mensagem**: As seguintes informações de motivo de substituição são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="b0be7-313">**Ignorar local**</span><span class="sxs-lookup"><span data-stu-id="b0be7-313">**On-premises skip**</span></span>
  - <span data-ttu-id="b0be7-314">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="b0be7-314">**IP Allow**</span></span>
  - <span data-ttu-id="b0be7-315">**Regra de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="b0be7-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="b0be7-316">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="b0be7-316">**Sender allow**</span></span>
  - <span data-ttu-id="b0be7-317">**Permitir domínio**</span><span class="sxs-lookup"><span data-stu-id="b0be7-317">**Domain allow**</span></span>
  - <span data-ttu-id="b0be7-318">**ZAP não habilitado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="b0be7-319">**Pasta Lixo Eletrônico não habilitada**</span><span class="sxs-lookup"><span data-stu-id="b0be7-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="b0be7-320">**Usuário Cofre Remetente**</span><span class="sxs-lookup"><span data-stu-id="b0be7-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="b0be7-321">**Domínio Cofre usuário**</span><span class="sxs-lookup"><span data-stu-id="b0be7-321">**User Safe Domain**</span></span>

  ![Exibição de substituição de mensagens no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="b0be7-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="b0be7-324">**Reputação de URL** gerada pela ATP <sup>1</sup>: reputação de URL mal-intencionada gerada pelo Defender para Office 365 detonações em outros clientes Microsoft 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="b0be7-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="b0be7-325">**Filtro de phishing avançado**: sinais de phishing com base no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="b0be7-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="b0be7-326">**Anti-spoof - Falha de DMARC**: falha de autenticação DMARC em mensagens.</span><span class="sxs-lookup"><span data-stu-id="b0be7-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="b0be7-327">**Anti-spoof - intra-org**: O remetente está tentando despojar o domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="b0be7-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="b0be7-328">**Anti-spoof - domínio externo**: o remetente está tentando despojar algum outro domínio.</span><span class="sxs-lookup"><span data-stu-id="b0be7-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="b0be7-329">**Representação de marca**: Representação de marcas conhecidas com base em senders.</span><span class="sxs-lookup"><span data-stu-id="b0be7-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="b0be7-330">**Representação de domínio**<sup>1</sup>: Representação de domínios que o cliente possui ou define.</span><span class="sxs-lookup"><span data-stu-id="b0be7-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="b0be7-331">**Reputação da URL do EOP:** reputação de URL mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="b0be7-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="b0be7-332">**Filtro de phishing geral**: sinais de phishing com base em regras de analista.</span><span class="sxs-lookup"><span data-stu-id="b0be7-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="b0be7-333">**Outros**</span><span class="sxs-lookup"><span data-stu-id="b0be7-333">**Others**</span></span>
  - <span data-ttu-id="b0be7-334">**Phish ZAP**<sup>2</sup>: Limpeza automática de hora zero de mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="b0be7-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="b0be7-335">**Detonação de URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0be7-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="b0be7-336">**Representação do usuário**<sup>1</sup>: Representação de usuários definidos pelo administrador ou aprendidos por meio da inteligência da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="b0be7-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Exibição de tecnologia de detecção para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="b0be7-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b0be7-339">**Reputação de arquivo gerado pela ATP**<sup>1</sup>: Toda a reputação de arquivo mal-intencionado gerada pelo Defender para Office 365 detonações.</span><span class="sxs-lookup"><span data-stu-id="b0be7-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="b0be7-340">**Mecanismo anti-malware**<sup>1</sup>: Detecção de mecanismos anti-malware.</span><span class="sxs-lookup"><span data-stu-id="b0be7-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="b0be7-341">Bloco de tipo de arquivo de **política anti-malware**: São mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="b0be7-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="b0be7-342">**Detonação de**<sup>arquivo 1</sup>: Detecção por Cofre Anexos.</span><span class="sxs-lookup"><span data-stu-id="b0be7-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="b0be7-343">**Reputação de arquivo mal-intencionado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="b0be7-344">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b0be7-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="b0be7-345">**Outros**</span><span class="sxs-lookup"><span data-stu-id="b0be7-345">**Others**</span></span>

  ![Exibição de tecnologia de detecção para malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="b0be7-347">**Break down by: Policy type and** **View data by: Email \> Phish** **or View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b0be7-348">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="b0be7-348">**Anti-malware**</span></span>
  - <span data-ttu-id="b0be7-349">**Cofre Anexos**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b0be7-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="b0be7-350">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="b0be7-350">**Anti-phish**</span></span>
  - <span data-ttu-id="b0be7-351">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="b0be7-351">**Anti-spam**</span></span>
  - <span data-ttu-id="b0be7-352">**Regra de fluxo de emails** (também conhecida como regra de transporte)</span><span class="sxs-lookup"><span data-stu-id="b0be7-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="b0be7-353">**Outros**</span><span class="sxs-lookup"><span data-stu-id="b0be7-353">**Others**</span></span>

  ![Exibição de tipo de política para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="b0be7-355">**Break down by: Status de entrega** e **Exibir dados por: Email \> Phish** or **View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="b0be7-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="b0be7-356">**Falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="b0be7-356">**Delivery failed**</span></span>
  - <span data-ttu-id="b0be7-357">**Descartado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-357">**Dropped**</span></span>
  - <span data-ttu-id="b0be7-358">**Encaminhado**</span><span class="sxs-lookup"><span data-stu-id="b0be7-358">**Forwarded**</span></span>
  - <span data-ttu-id="b0be7-359">**Caixa de correio hospedada: Pasta personalizada**</span><span class="sxs-lookup"><span data-stu-id="b0be7-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="b0be7-360">**Caixa de correio hospedada: itens excluídos**</span><span class="sxs-lookup"><span data-stu-id="b0be7-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="b0be7-361">**Caixa de correio hospedada: Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="b0be7-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="b0be7-362">**Caixa de correio hospedada: Lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="b0be7-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="b0be7-363">**Servidor local: Entregue**</span><span class="sxs-lookup"><span data-stu-id="b0be7-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="b0be7-364">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="b0be7-364">**Quarantine**</span></span>

  ![Exibição de status de entrega para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="b0be7-366"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="b0be7-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="b0be7-367"><sup>2</sup> A limpeza automática zero hora (ZAP) não está disponível no EOP autônomo (ele só funciona Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="b0be7-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="b0be7-368">Se você clicar **em Filtros,** os filtros disponíveis dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="b0be7-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b0be7-369">Para **Exibir dados por: Malware de \> Conteúdo**, você pode modificar o relatório por **Data** de Início e **Data** de Término e o **valor detecção.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="b0be7-370">Para **Exibir dados por: Substituição de Mensagens**, você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b0be7-371">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-372">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="b0be7-372">**Override Reason**</span></span>
  - <span data-ttu-id="b0be7-373">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="b0be7-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b0be7-374">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b0be7-375">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b0be7-375">**Domain**</span></span>

- <span data-ttu-id="b0be7-376">Para todas as outras exibições, você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b0be7-377">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-378">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="b0be7-378">**Detection**</span></span>
  - <span data-ttu-id="b0be7-379">**Protegido por**: **ATP** ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="b0be7-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="b0be7-380">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="b0be7-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b0be7-381">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b0be7-382">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b0be7-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="b0be7-383">Exibição de tabela de detalhes para o relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="b0be7-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="b0be7-384">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="b0be7-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b0be7-385">**Exibir dados por: Visão geral**: o botão de **tabela sem exibir detalhes** está disponível.</span><span class="sxs-lookup"><span data-stu-id="b0be7-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="b0be7-386">**Exibir dados por: Conteúdo \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="b0be7-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="b0be7-387">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-387">**Date**</span></span>
  - <span data-ttu-id="b0be7-388">**Location**</span><span class="sxs-lookup"><span data-stu-id="b0be7-388">**Location**</span></span>
  - <span data-ttu-id="b0be7-389">**Direcionado por**</span><span class="sxs-lookup"><span data-stu-id="b0be7-389">**Directed by**</span></span>
  - <span data-ttu-id="b0be7-390">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="b0be7-390">**Malware name**</span></span>

  <span data-ttu-id="b0be7-391">Se você clicar **em Filtros** neste exibição, poderá modificar o relatório por data de início e data de término **e** o **valor detecção.** </span><span class="sxs-lookup"><span data-stu-id="b0be7-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="b0be7-392">**Exibir dados por: Substituição de Mensagens**:</span><span class="sxs-lookup"><span data-stu-id="b0be7-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="b0be7-393">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-393">**Date**</span></span>
  - <span data-ttu-id="b0be7-394">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b0be7-394">**Subject**</span></span>
  - <span data-ttu-id="b0be7-395">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b0be7-395">**Sender**</span></span>
  - <span data-ttu-id="b0be7-396">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="b0be7-396">**Recipients**</span></span>
  - <span data-ttu-id="b0be7-397">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="b0be7-397">**Detected by**</span></span>
  - <span data-ttu-id="b0be7-398">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="b0be7-398">**Override Reason**</span></span>
  - <span data-ttu-id="b0be7-399">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="b0be7-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="b0be7-400">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="b0be7-400">**Tags**</span></span>

  <span data-ttu-id="b0be7-401">Se você clicar **em Filtros** neste visualização, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b0be7-402">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-403">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="b0be7-403">**Override Reason**</span></span>
  - <span data-ttu-id="b0be7-404">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="b0be7-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b0be7-405">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b0be7-406">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b0be7-406">**Domain**</span></span>
  - <span data-ttu-id="b0be7-407">**Destinatários** (Observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="b0be7-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="b0be7-408">Todos os outros gráficos:</span><span class="sxs-lookup"><span data-stu-id="b0be7-408">All other charts:</span></span>

  - <span data-ttu-id="b0be7-409">**Date**</span><span class="sxs-lookup"><span data-stu-id="b0be7-409">**Date**</span></span>
  - <span data-ttu-id="b0be7-410">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="b0be7-410">**Subject**</span></span>
  - <span data-ttu-id="b0be7-411">**Sender**</span><span class="sxs-lookup"><span data-stu-id="b0be7-411">**Sender**</span></span>
  - <span data-ttu-id="b0be7-412">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="b0be7-412">**Recipients**</span></span>
  - <span data-ttu-id="b0be7-413">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="b0be7-413">**Detected by**</span></span>
  - <span data-ttu-id="b0be7-414">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="b0be7-414">**Delivery Status**</span></span>
  - <span data-ttu-id="b0be7-415">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="b0be7-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="b0be7-416">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="b0be7-416">**Tags**</span></span>

  <span data-ttu-id="b0be7-417">Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="b0be7-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="b0be7-418">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="b0be7-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="b0be7-419">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="b0be7-419">**Detection**</span></span>
  - <span data-ttu-id="b0be7-420">**Protegido por**: **Defender para Office 365** ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="b0be7-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="b0be7-421">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="b0be7-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="b0be7-422">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="b0be7-423">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b0be7-423">**Domain**</span></span>
  - <span data-ttu-id="b0be7-424">**Destinatários** (Observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="b0be7-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="b0be7-425">Relatório de malware principal</span><span class="sxs-lookup"><span data-stu-id="b0be7-425">Top malware report</span></span>

<span data-ttu-id="b0be7-426">O **relatório de malware** Top mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="b0be7-427">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de Relatórios \>  e selecione **Malware Superior.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-427">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="b0be7-428">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="b0be7-428">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Principal widget de malware no painel Relatórios](../../media/top-malware-report-widget.png)

<span data-ttu-id="b0be7-430">Quando você passar o mouse sobre uma cunha no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="b0be7-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Exibição de relatório de malware principal](../../media/top-malware-report-view.png)

<span data-ttu-id="b0be7-432">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b0be7-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="b0be7-433">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="b0be7-433">**Top malware**</span></span>
- <span data-ttu-id="b0be7-434">**Count**</span><span class="sxs-lookup"><span data-stu-id="b0be7-434">**Count**</span></span>

<span data-ttu-id="b0be7-435">Se você clicar **em Filtros** no exibição de relatório ou no exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="b0be7-436">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="b0be7-436">URL threat protection report</span></span>

<span data-ttu-id="b0be7-437">O **relatório de proteção contra** ameaças de URL está disponível no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0be7-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b0be7-438">Para obter mais informações, consulte [RELATÓRIO de proteção contra ameaças de URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="b0be7-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="b0be7-439">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="b0be7-439">User-reported messages report</span></span>

<span data-ttu-id="b0be7-440">O **relatório** de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento Mensagem de Relatório ou o [add-in](enable-the-report-message-add-in.md) Relatório [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-440">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="b0be7-441">Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, uma exceção de política de spam ou uma regra de fluxo de emails configurada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b0be7-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="b0be7-442">Para exibir detalhes, selecione um item na lista de relatórios do usuário e, em seguida, exibir as informações nas guias **Resumo** **e** Detalhes.</span><span class="sxs-lookup"><span data-stu-id="b0be7-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![O User-Reported mensagens mostra mensagens que os usuários rotulam como lixo eletrônico, não tentativas de lixo eletrônico ou phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="b0be7-444">Para exibir este relatório, no Centro de Conformidade & [segurança,](https://protection.office.com)faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="b0be7-444">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="b0be7-445">Vá para **Painel de Gerenciamento de** \> **Ameaças** \> **Mensagens relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-445">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="b0be7-446">Vá para **Gerenciamento de ameaças** Revisar \> **mensagens** \> **relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="b0be7-446">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![No Centro de Conformidade & segurança, escolha Gerenciamento de ameaças \> Revisar \> mensagens relatadas pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="b0be7-448">Para que o relatório de mensagens relatadas pelo usuário funcione corretamente, o **log** de auditoria deve estar ligado para seu ambiente Office 365 ambiente.</span><span class="sxs-lookup"><span data-stu-id="b0be7-448">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="b0be7-449">Isso normalmente é feito por alguém que tem a função Logs de Auditoria atribuída Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b0be7-449">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="b0be7-450">Para obter mais informações, consulte Ativar ou desativar [Microsoft 365 pesquisa de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="b0be7-450">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="b0be7-451">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="b0be7-451">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="b0be7-452">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="b0be7-452">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="b0be7-453">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="b0be7-453">**Organization Management**</span></span>
- <span data-ttu-id="b0be7-454">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="b0be7-454">**Security Administrator**</span></span>
- <span data-ttu-id="b0be7-455">**Leitor de segurança**</span><span class="sxs-lookup"><span data-stu-id="b0be7-455">**Security Reader**</span></span>
- <span data-ttu-id="b0be7-456">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="b0be7-456">**Global Reader**</span></span>

<span data-ttu-id="b0be7-457">Para saber mais, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-457">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="b0be7-458">**Observação**: a adição de usuários à função de Azure Active Directory correspondente no centro de administração Microsoft 365 fornece  aos usuários as permissões necessárias no Centro de Conformidade & segurança e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0be7-458">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="b0be7-459">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-459">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="b0be7-460">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="b0be7-460">What if the reports aren't showing data?</span></span>

<span data-ttu-id="b0be7-461">Se você não estiver vendo dados em seus relatórios, verifique duas vezes se suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="b0be7-461">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="b0be7-462">Para saber mais, confira [Proteger contra ameaças](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="b0be7-462">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0be7-463">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b0be7-463">Related topics</span></span>

[<span data-ttu-id="b0be7-464">Proteção anti-spam e anti-malware no EOP</span><span class="sxs-lookup"><span data-stu-id="b0be7-464">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="b0be7-465">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="b0be7-465">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="b0be7-466">Exibir relatórios de fluxo de emails no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="b0be7-466">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="b0be7-467">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="b0be7-467">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
