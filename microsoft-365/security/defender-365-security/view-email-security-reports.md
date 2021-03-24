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
ms.openlocfilehash: 5d9f6d12fef8a2ef6241fbbd5e0e2a980284e9cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053082"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="e14cb-104">Exibir relatórios de segurança de email no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="e14cb-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e14cb-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e14cb-105">**Applies to**</span></span>
- [<span data-ttu-id="e14cb-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e14cb-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e14cb-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e14cb-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e14cb-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e14cb-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e14cb-109">Vários relatórios estão disponíveis no Centro de Conformidade e Segurança & para ajudá-lo a ver como os recursos de segurança de email, como anti-spam, anti-malware e recursos de criptografia no Microsoft 365 estão protegendo [sua](https://protection.office.com) organização.</span><span class="sxs-lookup"><span data-stu-id="e14cb-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="e14cb-110">Se você tiver as [permissões necessárias,](#what-permissions-are-needed-to-view-these-reports)poderá exibir esses relatórios no Centro de Conformidade e Segurança & indo para **Painel de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="e14cb-111">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel de relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="e14cb-113">Relatório de usuários comprometidos</span><span class="sxs-lookup"><span data-stu-id="e14cb-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="e14cb-114">Este relatório está disponível em organizações do Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e14cb-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="e14cb-115">Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e14cb-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="e14cb-116">O **relatório Usuários Comprometidos** mostra o número de contas de usuário que foram marcadas como **Suspeitas** ou **Restritas** nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="e14cb-117">As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas.</span><span class="sxs-lookup"><span data-stu-id="e14cb-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="e14cb-118">Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="e14cb-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="e14cb-119">Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="e14cb-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget de usuários comprometidos no painel Relatórios](../../media/compromised-users-report-widget.png)

<span data-ttu-id="e14cb-121">A exibição agregada mostra os dados dos últimos 90 dias e a exibição de detalhes mostra os dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="e14cb-122">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de Relatórios \>  e selecione **Usuários comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="e14cb-123">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="e14cb-124">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e14cb-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e14cb-125">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="e14cb-126">**Suspeito**: a conta de usuário enviou emails suspeitos e corre o risco de ser restringida ao envio de emails.</span><span class="sxs-lookup"><span data-stu-id="e14cb-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="e14cb-127">**Restrito**: a conta de usuário foi restrita ao envio de emails devido a padrões altamente suspeitos.</span><span class="sxs-lookup"><span data-stu-id="e14cb-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Exibir relatório no relatório Usuários Comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="e14cb-129">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e14cb-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e14cb-130">**Hora da criação**</span><span class="sxs-lookup"><span data-stu-id="e14cb-130">**Creation time**</span></span>
- <span data-ttu-id="e14cb-131">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-131">**User ID**</span></span>
- <span data-ttu-id="e14cb-132">**Ação**</span><span class="sxs-lookup"><span data-stu-id="e14cb-132">**Action**</span></span>

<span data-ttu-id="e14cb-133">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="e14cb-134">Relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-134">Encryption report</span></span>

<span data-ttu-id="e14cb-135">O **relatório de criptografia** está disponível no EOP (assinaturas com caixas de correio no Exchange Online ou EOP autônomo sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e14cb-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="e14cb-136">A equipe de segurança da sua organização pode usar informações neste relatório para identificar padrões e aplicar ou ajustar de forma proativa políticas para mensagens de email confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e14cb-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="e14cb-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e14cb-137">For example:</span></span>

- <span data-ttu-id="e14cb-138">Se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="e14cb-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="e14cb-139">Para obter mais informações, consulte Definir regras de fluxo de emails [para criptografar mensagens de email no Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="e14cb-140">Se você tiver vários modelos de criptografia disponíveis, mas ninguém os estiver usando, poderá explorar se os usuários precisam de treinamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="e14cb-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="e14cb-141">A exibição agregada permite a filtragem dos últimos 90 dias, enquanto a exibição de detalhes permite a filtragem por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="e14cb-142">Para exibir o relatório, abra o [Centro](https://protection.office.com)de Conformidade & segurança, vá **para** Painel de Relatórios \>  e selecione Relatório **de criptografia.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="e14cb-143">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="e14cb-144">Para saber mais sobre criptografia, consulte [Criptografia de email no Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="e14cb-145">Exibição de relatório para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-145">Report view for the Encryption report</span></span>

<span data-ttu-id="e14cb-146">Você pode usar os seguintes filtros no gráfico:</span><span class="sxs-lookup"><span data-stu-id="e14cb-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="e14cb-147">**Exibir dados por: Relatório de Criptografia** de Mensagens e Quebra **por: Método de** criptografia : Os seguintes métodos de criptografia estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e14cb-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e14cb-148">**Criptografia por usuário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-148">**Encryption by user**</span></span>
  - <span data-ttu-id="e14cb-149">**Criptografia por política**</span><span class="sxs-lookup"><span data-stu-id="e14cb-149">**Encryption by policy**</span></span>

  <span data-ttu-id="e14cb-150">Se você clicar em **Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e14cb-151">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-152">Método de criptografia.</span><span class="sxs-lookup"><span data-stu-id="e14cb-152">Encryption method.</span></span>
  - <span data-ttu-id="e14cb-153">Modelo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="e14cb-153">Encryption template.</span></span>

- <span data-ttu-id="e14cb-154">**Exibir dados por: Relatório de Criptografia** de Mensagens e Quebra **por: Modelo** de criptografia : Os seguintes métodos de criptografia estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e14cb-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="e14cb-155">**Não encaminhar**</span><span class="sxs-lookup"><span data-stu-id="e14cb-155">**Do not forward**</span></span>
  - <span data-ttu-id="e14cb-156">**Criptografar somente**</span><span class="sxs-lookup"><span data-stu-id="e14cb-156">**Encrypt only**</span></span>
  - <span data-ttu-id="e14cb-157">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="e14cb-157">**OME previous**</span></span>
  - <span data-ttu-id="e14cb-158">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="e14cb-158">**Custom**</span></span>

  <span data-ttu-id="e14cb-159">Se você clicar em **Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="e14cb-160">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-161">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-161">Encryption method</span></span>
  - <span data-ttu-id="e14cb-162">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-162">Encryption template</span></span>

- <span data-ttu-id="e14cb-163">**Exibir dados por: Os 5** principais domínios de destinatários : Este exibição mostra um gráfico de pizza com contagens de mensagens enviadas para os cinco domínios de destinatário principais.</span><span class="sxs-lookup"><span data-stu-id="e14cb-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="e14cb-164">Se você clicar **em Filtros,** você poderá selecionar uma data **de início** e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="e14cb-165">Exibição de tabela de detalhes para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="e14cb-166">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="e14cb-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e14cb-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span><span class="sxs-lookup"><span data-stu-id="e14cb-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="e14cb-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-168">**Date**</span></span>
  - <span data-ttu-id="e14cb-169">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-169">**Sender address**</span></span>
  - <span data-ttu-id="e14cb-170">**Modelo de criptografia**</span><span class="sxs-lookup"><span data-stu-id="e14cb-170">**Encryption template**</span></span>
  - <span data-ttu-id="e14cb-171">**Método de criptografia**</span><span class="sxs-lookup"><span data-stu-id="e14cb-171">**Encryption method**</span></span>
  - <span data-ttu-id="e14cb-172">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-172">**Recipient address**</span></span>
  - <span data-ttu-id="e14cb-173">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e14cb-173">**Subject**</span></span>

- <span data-ttu-id="e14cb-174">**Exibir dados por: Principais 5 domínios de destinatário:**</span><span class="sxs-lookup"><span data-stu-id="e14cb-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="e14cb-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-175">**Date**</span></span>
  - <span data-ttu-id="e14cb-176">**Domínio de destinatário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-176">**Recipient domain**</span></span>
  - <span data-ttu-id="e14cb-177">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="e14cb-177">**Message count**</span></span>

<span data-ttu-id="e14cb-178">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e14cb-179">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="e14cb-180">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-180">Encryption method</span></span>
- <span data-ttu-id="e14cb-181">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="e14cb-181">Encryption template</span></span>

<span data-ttu-id="e14cb-182">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="e14cb-183">Relatório de status de fluxo de emails</span><span class="sxs-lookup"><span data-stu-id="e14cb-183">Mailflow status report</span></span>

<span data-ttu-id="e14cb-184">O **relatório de status de fluxo de emails** contém informações sobre malware, spam, phishing e mensagens bloqueadas de borda.</span><span class="sxs-lookup"><span data-stu-id="e14cb-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="e14cb-185">Para obter mais detalhes, consulte [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="e14cb-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="e14cb-186">Detecções de malware no relatório de email</span><span class="sxs-lookup"><span data-stu-id="e14cb-186">Malware detections in email report</span></span>

<span data-ttu-id="e14cb-187">As **detecções de malware** no relatório de email mostram informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado pela Proteção do Exchange Online ou pelo EOP).</span><span class="sxs-lookup"><span data-stu-id="e14cb-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="e14cb-188">Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="e14cb-189">O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="e14cb-190">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Detecções de malware no email**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="e14cb-191">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecções de malware no widget de email no painel Relatórios](../../media/malware-detections-widget.png)

<span data-ttu-id="e14cb-193">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando:</span><span class="sxs-lookup"><span data-stu-id="e14cb-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="e14cb-194">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="e14cb-195">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="e14cb-195">**Inbound**</span></span>
- <span data-ttu-id="e14cb-196">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e14cb-196">**Outbound**</span></span>

![Exibir relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

<span data-ttu-id="e14cb-198">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e14cb-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e14cb-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-199">**Date**</span></span>
- <span data-ttu-id="e14cb-200">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-200">**Sender address**</span></span>
- <span data-ttu-id="e14cb-201">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-201">**Recipient address**</span></span>
- <span data-ttu-id="e14cb-202">**ID da** mensagem : disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e14cb-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="e14cb-203">Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="e14cb-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="e14cb-204">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e14cb-204">**Subject**</span></span>
- <span data-ttu-id="e14cb-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="e14cb-205">**Filename**</span></span>
- <span data-ttu-id="e14cb-206">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="e14cb-206">**Malware name**</span></span>

<span data-ttu-id="e14cb-207">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="e14cb-208">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="e14cb-208">Mail latency report</span></span>

<span data-ttu-id="e14cb-209">O **relatório de latência de email** contém informações sobre a entrega de email e a latência de detonação experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e14cb-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="e14cb-210">Para obter mais informações, consulte [Relatório de latência de email](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="e14cb-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="e14cb-211">Relatório de email enviado e recebido</span><span class="sxs-lookup"><span data-stu-id="e14cb-211">Sent and received email report</span></span>

<span data-ttu-id="e14cb-212">O **relatório de email** enviado e recebido contém informações sobre malware, spam, regras de fluxo de emails (também conhecidas como regras de transporte) e detecções avançadas de malware depois que o email entra no serviço.</span><span class="sxs-lookup"><span data-stu-id="e14cb-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="e14cb-213">Para obter mais informações, consulte [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="e14cb-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="e14cb-214">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="e14cb-214">Spam detections report</span></span>

<span data-ttu-id="e14cb-215">O **relatório de detecções de** spam mostra mensagens de email de spam que foram bloqueadas pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="e14cb-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="e14cb-216">As mensagens são contadas individualmente, não por destinatário.</span><span class="sxs-lookup"><span data-stu-id="e14cb-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="e14cb-217">Por exemplo, se a mesma mensagem de spam foi enviada para 100 destinatários em sua organização, ela conta como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e14cb-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="e14cb-218">A exibição agregada permite a filtragem de 90 dias, enquanto a tabela de detalhes permite a filtragem de 10 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="e14cb-219">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios \>  e selecione Detecções **de spam.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="e14cb-220">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget de detecções de spam no painel Relatórios](../../media/spam-detections-report-widget.png)

<span data-ttu-id="e14cb-222">Para obter mais informações sobre a proteção anti-spam, consulte [Anti-spam protection in EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="e14cb-223">Exibição de relatório para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="e14cb-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="e14cb-224">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="e14cb-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="e14cb-225">**Break down by: Action**: Os seguintes tipos de evento são mostrados:</span><span class="sxs-lookup"><span data-stu-id="e14cb-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="e14cb-226">**Conteúdo de spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="e14cb-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="e14cb-227">**Bloqueio de IP de spam**</span><span class="sxs-lookup"><span data-stu-id="e14cb-227">**Spam IP block**</span></span>
  - <span data-ttu-id="e14cb-228">**Bloqueio de envelope de spam**</span><span class="sxs-lookup"><span data-stu-id="e14cb-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="e14cb-229">**Filtro DBEB de spam**: Bloqueio de borda baseado em diretório (DBEB)</span><span class="sxs-lookup"><span data-stu-id="e14cb-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="e14cb-230">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantos itens foram bloqueados nesse dia, bem como como esses itens são categorizados.</span><span class="sxs-lookup"><span data-stu-id="e14cb-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Exibição de ação no relatório de detecções de spam](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="e14cb-232">**Break down by: Direction**: The following directions are shown:</span><span class="sxs-lookup"><span data-stu-id="e14cb-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="e14cb-233">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="e14cb-233">**Inbound**</span></span>
  - <span data-ttu-id="e14cb-234">**Saída**</span><span class="sxs-lookup"><span data-stu-id="e14cb-234">**Outbound**</span></span>

  ![Exibição de direção no relatório de detecções de spam](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="e14cb-236">Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e14cb-237">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="e14cb-238">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e14cb-238">Direction values</span></span>
- <span data-ttu-id="e14cb-239">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="e14cb-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="e14cb-240">Exibição de tabela de detalhes para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="e14cb-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="e14cb-241">Se você clicar em **Exibir tabela de detalhes** em qualquer exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="e14cb-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-242">**Date**</span></span>
- <span data-ttu-id="e14cb-243">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-243">**Sender address**</span></span>
- <span data-ttu-id="e14cb-244">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-244">**Recipient address**</span></span>
- <span data-ttu-id="e14cb-245">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="e14cb-245">**Event type**</span></span>
- <span data-ttu-id="e14cb-246">**Ação**</span><span class="sxs-lookup"><span data-stu-id="e14cb-246">**Action**</span></span>
- <span data-ttu-id="e14cb-247">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e14cb-247">**Subject**</span></span>

<span data-ttu-id="e14cb-248">Se você clicar **em Filtros** em uma tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="e14cb-249">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="e14cb-250">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="e14cb-250">Direction values</span></span>
- <span data-ttu-id="e14cb-251">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="e14cb-251">Event type values</span></span>

<span data-ttu-id="e14cb-252">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="e14cb-253">Relatório de detecções de spoof</span><span class="sxs-lookup"><span data-stu-id="e14cb-253">Spoof detections report</span></span>

<span data-ttu-id="e14cb-254">O relatório de detecções **Spoof** mostra quantas mensagens de email falsas foram detectadas e dessas, quais foram consideradas "boas" (email de spoof feito por motivos comerciais legítimos).</span><span class="sxs-lookup"><span data-stu-id="e14cb-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="e14cb-255">Para obter mais informações sobre a spoofing, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e14cb-256">A exibição agregada do relatório permite 90 dias de filtragem, enquanto a exibição de detalhes permite apenas dez dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="e14cb-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="e14cb-257">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Detecções de Spoof**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="e14cb-258">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget de detecções de spoof no painel Relatórios](../../media/spoof-detections-widget.png)

<span data-ttu-id="e14cb-260">Quando você passa o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens de email falsas passaram.</span><span class="sxs-lookup"><span data-stu-id="e14cb-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="e14cb-261">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e14cb-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="e14cb-262">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="e14cb-263">**Bom email**</span><span class="sxs-lookup"><span data-stu-id="e14cb-263">**Good mail**</span></span>

- <span data-ttu-id="e14cb-264">**Capturado como spam**</span><span class="sxs-lookup"><span data-stu-id="e14cb-264">**Caught as spam**</span></span>

![Exibição de relatório no relatório de detecções de Spoof](../../media/spoof-detections-report-view.png)

<span data-ttu-id="e14cb-266">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e14cb-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e14cb-267">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-267">**Date**</span></span>
- <span data-ttu-id="e14cb-268">**Remetentes com spoofed**</span><span class="sxs-lookup"><span data-stu-id="e14cb-268">**Spoofed sender**</span></span>
- <span data-ttu-id="e14cb-269">**Remetente verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="e14cb-269">**True sender**</span></span>
- <span data-ttu-id="e14cb-270">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="e14cb-270">**Sender IP**</span></span>
- <span data-ttu-id="e14cb-271">**Ação**</span><span class="sxs-lookup"><span data-stu-id="e14cb-271">**Action**</span></span>
- <span data-ttu-id="e14cb-272">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="e14cb-272">**Message count**</span></span>

<span data-ttu-id="e14cb-273">Para voltar à exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e14cb-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="e14cb-274">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="e14cb-274">Threat protection status report</span></span>

<span data-ttu-id="e14cb-275">O **relatório de status de** proteção contra ameaças está disponível no EOP e no Microsoft Defender para Office 365; no entanto, os relatórios contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="e14cb-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="e14cb-276">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectados no email, mas não informações sobre arquivos mal-intencionados detectados por Anexos Seguros para [SharePoint, OneDrive e Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e14cb-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="e14cb-277">O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) bloqueados pelo mecanismo anti-malware, pela limpeza [automática zero hora (ZAP)](zero-hour-auto-purge.md)e pelos recursos do Defender for Office 365, como Links [Seguros,](safe-links.md) [Anexos](safe-attachments.md)Seguros e [Anti-phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e14cb-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="e14cb-278">Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajustes.</span><span class="sxs-lookup"><span data-stu-id="e14cb-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="e14cb-279">**Observação**: é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="e14cb-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="e14cb-280">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de \>  Relatórios e selecione Status de proteção **contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="e14cb-281">Para ir diretamente ao relatório, abra uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="e14cb-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="e14cb-282">Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="e14cb-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="e14cb-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="e14cb-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget de status de proteção contra ameaças no painel Relatórios](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="e14cb-285">Por padrão, o gráfico mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="e14cb-286">Se você clicar **em Filtros,** poderá selecionar um intervalo de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias).</span><span class="sxs-lookup"><span data-stu-id="e14cb-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="e14cb-287">A exibição da tabela de detalhes permite a filtragem por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e14cb-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e14cb-288">Exibição de relatório para o relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="e14cb-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="e14cb-289">As exibições a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e14cb-289">The following views are available:</span></span>

- <span data-ttu-id="e14cb-290">**Exibir dados por: Visão geral**: As seguintes informações de detecção são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="e14cb-291">**Malware de email**</span><span class="sxs-lookup"><span data-stu-id="e14cb-291">**Email malware**</span></span>
  - <span data-ttu-id="e14cb-292">**Phishing de email**</span><span class="sxs-lookup"><span data-stu-id="e14cb-292">**Email phish**</span></span>
  - <span data-ttu-id="e14cb-293">**Malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="e14cb-293">**Content malware**</span></span>

  ![Visão geral no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="e14cb-295">**Exibir dados por: Conteúdo \> Malware**<sup>1</sup>: As informações a seguir são mostradas para organizações do Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="e14cb-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="e14cb-296">**Mecanismo anti-malware**: arquivos mal-intencionados detectados no Sharepoint, OneDrive e Microsoft Teams pela detecção interna de [vírus no Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="e14cb-297">**Detonação de** arquivo : arquivos mal-intencionados detectados por [Anexos Seguros para SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Exibição de malware de conteúdo no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="e14cb-299">**Exibir dados por: Substituição de Mensagem**: As seguintes informações de motivo de substituição são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="e14cb-300">**Ignorar local**</span><span class="sxs-lookup"><span data-stu-id="e14cb-300">**On-premises skip**</span></span>
  - <span data-ttu-id="e14cb-301">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="e14cb-301">**IP Allow**</span></span>
  - <span data-ttu-id="e14cb-302">**Regra de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="e14cb-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="e14cb-303">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="e14cb-303">**Sender allow**</span></span>
  - <span data-ttu-id="e14cb-304">**Permitir domínio**</span><span class="sxs-lookup"><span data-stu-id="e14cb-304">**Domain allow**</span></span>
  - <span data-ttu-id="e14cb-305">**ZAP não habilitado**</span><span class="sxs-lookup"><span data-stu-id="e14cb-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="e14cb-306">**Pasta Lixo Eletrônico não habilitada**</span><span class="sxs-lookup"><span data-stu-id="e14cb-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="e14cb-307">**Remetente seguro do usuário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="e14cb-308">**Domínio Seguro do Usuário**</span><span class="sxs-lookup"><span data-stu-id="e14cb-308">**User Safe Domain**</span></span>

  ![Exibição de substituição de mensagens no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="e14cb-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="e14cb-311">**Reputação de URL** gerada pela ATP <sup>1</sup>: Reputação de URL mal-intencionada gerada a partir de detonações do Defender para Office 365 em outros clientes do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e14cb-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="e14cb-312">**Filtro de phishing avançado**: sinais de phishing com base no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="e14cb-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="e14cb-313">**Anti-spoof - Falha de DMARC**: falha de autenticação DMARC em mensagens.</span><span class="sxs-lookup"><span data-stu-id="e14cb-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="e14cb-314">**Anti-spoof - intra-org**: O remetente está tentando despojar o domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="e14cb-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="e14cb-315">**Anti-spoof - domínio externo**: o remetente está tentando despojar algum outro domínio.</span><span class="sxs-lookup"><span data-stu-id="e14cb-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="e14cb-316">**Representação de marca**: Representação de marcas conhecidas com base em senders.</span><span class="sxs-lookup"><span data-stu-id="e14cb-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="e14cb-317">**Representação de domínio**<sup>1</sup>: Representação de domínios que o cliente possui ou define.</span><span class="sxs-lookup"><span data-stu-id="e14cb-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="e14cb-318">**Reputação da URL do EOP:** reputação de URL mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="e14cb-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="e14cb-319">**Filtro de phishing geral**: sinais de phishing com base em regras de analista.</span><span class="sxs-lookup"><span data-stu-id="e14cb-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="e14cb-320">**Outros**</span><span class="sxs-lookup"><span data-stu-id="e14cb-320">**Others**</span></span>
  - <span data-ttu-id="e14cb-321">**Phish ZAP**<sup>2</sup>: Limpeza automática de hora zero de mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="e14cb-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="e14cb-322">**Detonação de URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e14cb-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="e14cb-323">**Representação do usuário**<sup>1</sup>: Representação de usuários definidos pelo administrador ou aprendidos por meio da inteligência da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="e14cb-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Exibição de tecnologia de detecção para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="e14cb-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e14cb-326">**Reputação de arquivo gerado pela ATP**<sup>1</sup>: Toda a reputação de arquivo mal-intencionado gerada pelas detonações do Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e14cb-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="e14cb-327">**Mecanismo anti-malware**<sup>1</sup>: Detecção de mecanismos anti-malware.</span><span class="sxs-lookup"><span data-stu-id="e14cb-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="e14cb-328">Bloco de tipo de arquivo de **política anti-malware**: São mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="e14cb-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="e14cb-329">**Detonação de**<sup>arquivo 1</sup>: Detecção por Anexos Seguros.</span><span class="sxs-lookup"><span data-stu-id="e14cb-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="e14cb-330">**Reputação de arquivo mal-intencionado**</span><span class="sxs-lookup"><span data-stu-id="e14cb-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="e14cb-331">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="e14cb-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="e14cb-332">**Outros**</span><span class="sxs-lookup"><span data-stu-id="e14cb-332">**Others**</span></span>

  ![Exibição de tecnologia de detecção para malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="e14cb-334">**Break down by: Policy type and** **View data by: Email \> Phish** **or View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e14cb-335">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="e14cb-335">**Anti-malware**</span></span>
  - <span data-ttu-id="e14cb-336">**Anexos Seguros**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e14cb-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="e14cb-337">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="e14cb-337">**Anti-phish**</span></span>
  - <span data-ttu-id="e14cb-338">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="e14cb-338">**Anti-spam**</span></span>
  - <span data-ttu-id="e14cb-339">**Regra de fluxo de emails** (também conhecida como regra de transporte)</span><span class="sxs-lookup"><span data-stu-id="e14cb-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="e14cb-340">**Outros**</span><span class="sxs-lookup"><span data-stu-id="e14cb-340">**Others**</span></span>

  ![Exibição de tipo de política para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="e14cb-342">**Break down by: Status de entrega** e **Exibir dados por: Email \> Phish** or **View data by: Email \> Malware**: As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="e14cb-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="e14cb-343">**Falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="e14cb-343">**Delivery failed**</span></span>
  - <span data-ttu-id="e14cb-344">**Descartado**</span><span class="sxs-lookup"><span data-stu-id="e14cb-344">**Dropped**</span></span>
  - <span data-ttu-id="e14cb-345">**Encaminhado**</span><span class="sxs-lookup"><span data-stu-id="e14cb-345">**Forwarded**</span></span>
  - <span data-ttu-id="e14cb-346">**Caixa de correio hospedada: Pasta personalizada**</span><span class="sxs-lookup"><span data-stu-id="e14cb-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="e14cb-347">**Caixa de correio hospedada: itens excluídos**</span><span class="sxs-lookup"><span data-stu-id="e14cb-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="e14cb-348">**Caixa de correio hospedada: Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="e14cb-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="e14cb-349">**Caixa de correio hospedada: Lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="e14cb-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="e14cb-350">**Servidor local: Entregue**</span><span class="sxs-lookup"><span data-stu-id="e14cb-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="e14cb-351">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="e14cb-351">**Quarantine**</span></span>

  ![Exibição de status de entrega para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="e14cb-353"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="e14cb-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="e14cb-354"><sup>2</sup> A limpeza automática de hora zero (ZAP) não está disponível no EOP autônomo (ele só funciona em caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e14cb-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="e14cb-355">Se você clicar **em Filtros,** os filtros disponíveis dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="e14cb-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e14cb-356">Para **Exibir dados por: Malware de \> Conteúdo**, você pode modificar o relatório por **Data** de Início e **Data** de Término e o **valor detecção.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="e14cb-357">Para **Exibir dados por: Substituição de Mensagens**, você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="e14cb-358">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-359">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="e14cb-359">**Override Reason**</span></span>
  - <span data-ttu-id="e14cb-360">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="e14cb-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="e14cb-361">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="e14cb-362">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e14cb-362">**Domain**</span></span>

- <span data-ttu-id="e14cb-363">Para todas as outras exibições, você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="e14cb-364">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-365">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="e14cb-365">**Detection**</span></span>
  - <span data-ttu-id="e14cb-366">**Protegido por**: **ATP** ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="e14cb-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="e14cb-367">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="e14cb-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="e14cb-368">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="e14cb-369">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e14cb-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="e14cb-370">Exibição de tabela de detalhes para o relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="e14cb-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="e14cb-371">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="e14cb-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="e14cb-372">**Exibir dados por: Visão geral**: o botão de **tabela sem exibir detalhes** está disponível.</span><span class="sxs-lookup"><span data-stu-id="e14cb-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="e14cb-373">**Exibir dados por: Conteúdo \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="e14cb-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="e14cb-374">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-374">**Date**</span></span>
  - <span data-ttu-id="e14cb-375">**Localização**</span><span class="sxs-lookup"><span data-stu-id="e14cb-375">**Location**</span></span>
  - <span data-ttu-id="e14cb-376">**Direcionado por**</span><span class="sxs-lookup"><span data-stu-id="e14cb-376">**Directed by**</span></span>
  - <span data-ttu-id="e14cb-377">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="e14cb-377">**Malware name**</span></span>

  <span data-ttu-id="e14cb-378">Se você clicar **em Filtros** neste exibição, poderá modificar o relatório por data de início e data de término **e** o **valor detecção.** </span><span class="sxs-lookup"><span data-stu-id="e14cb-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="e14cb-379">**Exibir dados por: Substituição de Mensagens**:</span><span class="sxs-lookup"><span data-stu-id="e14cb-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="e14cb-380">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-380">**Date**</span></span>
  - <span data-ttu-id="e14cb-381">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e14cb-381">**Subject**</span></span>
  - <span data-ttu-id="e14cb-382">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e14cb-382">**Sender**</span></span>
  - <span data-ttu-id="e14cb-383">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="e14cb-383">**Recipients**</span></span>
  - <span data-ttu-id="e14cb-384">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="e14cb-384">**Detected by**</span></span>
  - <span data-ttu-id="e14cb-385">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="e14cb-385">**Override Reason**</span></span>
  - <span data-ttu-id="e14cb-386">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="e14cb-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="e14cb-387">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="e14cb-387">**Tags**</span></span>

  <span data-ttu-id="e14cb-388">Se você clicar **em Filtros** neste visualização, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="e14cb-389">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-390">**Substituir Motivo**</span><span class="sxs-lookup"><span data-stu-id="e14cb-390">**Override Reason**</span></span>
  - <span data-ttu-id="e14cb-391">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="e14cb-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="e14cb-392">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="e14cb-393">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e14cb-393">**Domain**</span></span>
  - <span data-ttu-id="e14cb-394">**Destinatários** (Observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="e14cb-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="e14cb-395">Todos os outros gráficos:</span><span class="sxs-lookup"><span data-stu-id="e14cb-395">All other charts:</span></span>

  - <span data-ttu-id="e14cb-396">**Date**</span><span class="sxs-lookup"><span data-stu-id="e14cb-396">**Date**</span></span>
  - <span data-ttu-id="e14cb-397">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e14cb-397">**Subject**</span></span>
  - <span data-ttu-id="e14cb-398">**Sender**</span><span class="sxs-lookup"><span data-stu-id="e14cb-398">**Sender**</span></span>
  - <span data-ttu-id="e14cb-399">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="e14cb-399">**Recipients**</span></span>
  - <span data-ttu-id="e14cb-400">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="e14cb-400">**Detected by**</span></span>
  - <span data-ttu-id="e14cb-401">**Status da Entrega**</span><span class="sxs-lookup"><span data-stu-id="e14cb-401">**Delivery Status**</span></span>
  - <span data-ttu-id="e14cb-402">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="e14cb-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="e14cb-403">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="e14cb-403">**Tags**</span></span>

  <span data-ttu-id="e14cb-404">Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="e14cb-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="e14cb-405">**Data de início** **e data de término**</span><span class="sxs-lookup"><span data-stu-id="e14cb-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="e14cb-406">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="e14cb-406">**Detection**</span></span>
  - <span data-ttu-id="e14cb-407">**Protegido por**: **Defender para Office 365** ou **EOP**</span><span class="sxs-lookup"><span data-stu-id="e14cb-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="e14cb-408">**Marca**: filtre os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="e14cb-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="e14cb-409">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="e14cb-410">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="e14cb-410">**Domain**</span></span>
  - <span data-ttu-id="e14cb-411">**Destinatários** (Observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="e14cb-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="e14cb-412">Relatório de malware principal</span><span class="sxs-lookup"><span data-stu-id="e14cb-412">Top malware report</span></span>

<span data-ttu-id="e14cb-413">O **relatório de malware** Top mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="e14cb-414">Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de Relatórios \>  e selecione **Malware Superior.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="e14cb-415">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="e14cb-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Principal widget de malware no painel Relatórios](../../media/top-malware-report-widget.png)

<span data-ttu-id="e14cb-417">Quando você passar o mouse sobre uma cunha no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="e14cb-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Exibição de relatório de malware principal](../../media/top-malware-report-view.png)

<span data-ttu-id="e14cb-419">Se você clicar em **Exibir tabela de detalhes,** você poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="e14cb-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="e14cb-420">**Malware principal**</span><span class="sxs-lookup"><span data-stu-id="e14cb-420">**Top malware**</span></span>
- <span data-ttu-id="e14cb-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="e14cb-421">**Count**</span></span>

<span data-ttu-id="e14cb-422">Se você clicar **em Filtros** no exibição de relatório ou no exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="e14cb-423">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="e14cb-423">URL threat protection report</span></span>

<span data-ttu-id="e14cb-424">O relatório de proteção contra **ameaças de URL** está disponível no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e14cb-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e14cb-425">Para obter mais informações, consulte [RELATÓRIO de proteção contra ameaças de URL](view-reports-for-mdo.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="e14cb-425">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="e14cb-426">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="e14cb-426">User-reported messages report</span></span>

<span data-ttu-id="e14cb-427">O **relatório** de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento Mensagem de Relatório ou o [add-in](enable-the-report-message-add-in.md) Relatório [phishing](enable-the-report-phish-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="e14cb-428">Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, uma exceção de política de spam ou uma regra de fluxo de emails configurada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e14cb-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="e14cb-429">Para exibir detalhes, selecione um item na lista de relatórios do usuário e, em seguida, exibir as informações nas guias **Resumo** **e** Detalhes.</span><span class="sxs-lookup"><span data-stu-id="e14cb-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![O User-Reported mensagens mostra mensagens que os usuários rotulam como lixo eletrônico, não tentativas de lixo eletrônico ou phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="e14cb-431">Para exibir este relatório, no Centro de Conformidade & [segurança,](https://protection.office.com)faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e14cb-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="e14cb-432">Vá para **Painel de Gerenciamento de** \> **Ameaças** \> **Mensagens relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="e14cb-433">Vá para **Gerenciamento de ameaças** Revisar \> **mensagens** \> **relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="e14cb-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![No Centro de Conformidade & segurança, escolha Gerenciamento de ameaças \> Revisar \> mensagens relatadas pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="e14cb-435">Para que o relatório de mensagens relatadas pelo usuário funcione corretamente, o **log** de auditoria deve estar ligado para seu ambiente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e14cb-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="e14cb-436">Isso normalmente é feito por alguém que tem a função Logs de Auditoria atribuída no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e14cb-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="e14cb-437">Para obter mais informações, consulte Ativar ou desativar a pesquisa de log de [auditoria do Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="e14cb-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e14cb-438">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="e14cb-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e14cb-439">Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:</span><span class="sxs-lookup"><span data-stu-id="e14cb-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="e14cb-440">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="e14cb-440">**Organization Management**</span></span>
- <span data-ttu-id="e14cb-441">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="e14cb-441">**Security Administrator**</span></span>
- <span data-ttu-id="e14cb-442">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="e14cb-442">**Security Reader**</span></span>
- <span data-ttu-id="e14cb-443">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="e14cb-443">**Global Reader**</span></span>

<span data-ttu-id="e14cb-444">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="e14cb-445">**Observação**: a adição de usuários à função correspondente do Azure Active Directory no Centro de administração do  Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Conformidade & Segurança e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e14cb-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e14cb-446">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e14cb-447">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="e14cb-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e14cb-448">Se você não estiver vendo dados em seus relatórios, verifique duas vezes se suas políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="e14cb-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="e14cb-449">Para saber mais, confira [Proteger contra ameaças](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="e14cb-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e14cb-450">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e14cb-450">Related topics</span></span>

[<span data-ttu-id="e14cb-451">Proteção anti-spam e anti-malware no EOP</span><span class="sxs-lookup"><span data-stu-id="e14cb-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="e14cb-452">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="e14cb-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="e14cb-453">Exibir relatórios de fluxo de emails no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="e14cb-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="e14cb-454">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e14cb-454">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
