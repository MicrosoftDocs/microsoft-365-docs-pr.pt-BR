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
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290794"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="148a8-104">Exibir relatórios de segurança de email no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="148a8-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="148a8-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="148a8-105">**Applies to**</span></span>
- [<span data-ttu-id="148a8-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="148a8-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="148a8-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="148a8-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="148a8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="148a8-108">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="148a8-109">Vários relatórios estão disponíveis no Centro de Conformidade e Segurança para ajudá-lo [& a](https://protection.office.com) ver como os recursos de segurança de email, como anti-spam, anti-malware e criptografia no Microsoft 365, estão protegendo sua organização.</span><span class="sxs-lookup"><span data-stu-id="148a8-109">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="148a8-110">Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports)&, poderá exibir esses relatórios no Centro de Conformidade e Segurança indo para o Painel **de** \> **Relatórios.**</span><span class="sxs-lookup"><span data-stu-id="148a8-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="148a8-111">Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="148a8-111">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Painel relatórios no Centro de Conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="148a8-113">Relatório de usuários comprometidos</span><span class="sxs-lookup"><span data-stu-id="148a8-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="148a8-114">Esse relatório está disponível em organizações do Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="148a8-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="148a8-115">Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="148a8-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="148a8-116">O **relatório De usuários** comprometidos mostra o  número de contas de usuário que foram marcadas como **Suspeitas** ou Restritas nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="148a8-117">As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas.</span><span class="sxs-lookup"><span data-stu-id="148a8-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="148a8-118">Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="148a8-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="148a8-119">Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget de usuários comprometidos no painel Relatórios](../../media/compromised-users-report-widget.png)

<span data-ttu-id="148a8-121">A exibição agregada mostra os dados dos últimos 90 dias e a exibição detalhada mostra os dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="148a8-122">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione Usuários  \>  **comprometidos.**</span><span class="sxs-lookup"><span data-stu-id="148a8-122">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="148a8-123">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="148a8-123">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="148a8-124">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="148a8-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="148a8-125">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="148a8-126">**Suspeito:** a conta de usuário enviou emails suspeitos e corre o risco de ser restringida de enviar emails.</span><span class="sxs-lookup"><span data-stu-id="148a8-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="148a8-127">**Restrito:** a conta de usuário foi restringida de enviar emails devido a padrões altamente suspeitos.</span><span class="sxs-lookup"><span data-stu-id="148a8-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Exibição de relatório no relatório De usuários comprometidos](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="148a8-129">Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="148a8-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="148a8-130">**Hora de criação**</span><span class="sxs-lookup"><span data-stu-id="148a8-130">**Creation time**</span></span>
- <span data-ttu-id="148a8-131">**ID de usuário**</span><span class="sxs-lookup"><span data-stu-id="148a8-131">**User ID**</span></span>
- <span data-ttu-id="148a8-132">**Ação**</span><span class="sxs-lookup"><span data-stu-id="148a8-132">**Action**</span></span>

<span data-ttu-id="148a8-133">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="148a8-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="148a8-134">Relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-134">Encryption report</span></span>

<span data-ttu-id="148a8-135">O **relatório de criptografia** está disponível no EOP (assinaturas com caixas de correio no Exchange Online ou no EOP autônomo sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="148a8-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="148a8-136">A equipe de segurança da sua organização pode usar as informações nesse relatório para identificar padrões e aplicar ou ajustar proativamente políticas para mensagens de email confidenciais.</span><span class="sxs-lookup"><span data-stu-id="148a8-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="148a8-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="148a8-137">For example:</span></span>

- <span data-ttu-id="148a8-138">Se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso.</span><span class="sxs-lookup"><span data-stu-id="148a8-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="148a8-139">Para saber mais, confira [Definir regras de fluxo de emails para criptografar mensagens de email no Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="148a8-140">Se você tiver vários modelos de criptografia disponíveis, mas ninguém os estiver usando, poderá explorar se os usuários precisam de treinamento de recursos.</span><span class="sxs-lookup"><span data-stu-id="148a8-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="148a8-141">A exibição agregada permite a filtragem dos últimos 90 dias, enquanto a exibição de detalhes permite a filtragem por 10 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="148a8-142">Para exibir o relatório, abra o [Centro de Conformidade & Segurança,](https://protection.office.com)vá para o Painel de Relatórios e selecione Relatório de  \>  **criptografia.**</span><span class="sxs-lookup"><span data-stu-id="148a8-142">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="148a8-143">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="148a8-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="148a8-144">Para saber mais sobre criptografia, confira [Criptografia de email no Microsoft 365.](../../compliance/email-encryption.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="148a8-145">Exibição de relatório para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-145">Report view for the Encryption report</span></span>

<span data-ttu-id="148a8-146">Você pode usar os seguintes filtros no gráfico:</span><span class="sxs-lookup"><span data-stu-id="148a8-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="148a8-147">**Exibir dados por: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span><span class="sxs-lookup"><span data-stu-id="148a8-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="148a8-148">**Criptografia por usuário**</span><span class="sxs-lookup"><span data-stu-id="148a8-148">**Encryption by user**</span></span>
  - <span data-ttu-id="148a8-149">**Criptografia por política**</span><span class="sxs-lookup"><span data-stu-id="148a8-149">**Encryption by policy**</span></span>

  <span data-ttu-id="148a8-150">Se você clicar **em Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="148a8-151">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-152">Método de criptografia.</span><span class="sxs-lookup"><span data-stu-id="148a8-152">Encryption method.</span></span>
  - <span data-ttu-id="148a8-153">Modelo de criptografia.</span><span class="sxs-lookup"><span data-stu-id="148a8-153">Encryption template.</span></span>

- <span data-ttu-id="148a8-154">**Exibir dados por: Relatório de criptografia de** mensagens e **métrica por:** modelo de criptografia: os seguintes métodos de criptografia estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="148a8-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="148a8-155">**Não encaminhar**</span><span class="sxs-lookup"><span data-stu-id="148a8-155">**Do not forward**</span></span>
  - <span data-ttu-id="148a8-156">**Somente criptografar**</span><span class="sxs-lookup"><span data-stu-id="148a8-156">**Encrypt only**</span></span>
  - <span data-ttu-id="148a8-157">**OME anterior**</span><span class="sxs-lookup"><span data-stu-id="148a8-157">**OME previous**</span></span>
  - <span data-ttu-id="148a8-158">**Personalizados**</span><span class="sxs-lookup"><span data-stu-id="148a8-158">**Custom**</span></span>

  <span data-ttu-id="148a8-159">Se você clicar **em Filtros,** poderá modificar o gráfico com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="148a8-160">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-161">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-161">Encryption method</span></span>
  - <span data-ttu-id="148a8-162">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-162">Encryption template</span></span>

- <span data-ttu-id="148a8-163">**Exibir dados por: 5** principais domínios de destinatários: esta exibição mostra um gráfico de pizza com contagens de mensagens enviadas para os 5 principais domínios de destinatários.</span><span class="sxs-lookup"><span data-stu-id="148a8-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="148a8-164">Se você clicar em **Filtros,** poderá selecionar a data **de início** e a **data de término.**</span><span class="sxs-lookup"><span data-stu-id="148a8-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="148a8-165">Exibição de tabela de detalhes para o relatório de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="148a8-166">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="148a8-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="148a8-167">**Quebra por: método de criptografia** **ou quebra por: modelo de criptografia**: as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="148a8-168">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-168">**Date**</span></span>
  - <span data-ttu-id="148a8-169">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="148a8-169">**Sender address**</span></span>
  - <span data-ttu-id="148a8-170">**Modelo de criptografia**</span><span class="sxs-lookup"><span data-stu-id="148a8-170">**Encryption template**</span></span>
  - <span data-ttu-id="148a8-171">**Método de criptografia**</span><span class="sxs-lookup"><span data-stu-id="148a8-171">**Encryption method**</span></span>
  - <span data-ttu-id="148a8-172">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="148a8-172">**Recipient address**</span></span>
  - <span data-ttu-id="148a8-173">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="148a8-173">**Subject**</span></span>

- <span data-ttu-id="148a8-174">**Exibir dados por: 5 domínios de destinatário principais:**</span><span class="sxs-lookup"><span data-stu-id="148a8-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="148a8-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-175">**Date**</span></span>
  - <span data-ttu-id="148a8-176">**Domínio do destinatário**</span><span class="sxs-lookup"><span data-stu-id="148a8-176">**Recipient domain**</span></span>
  - <span data-ttu-id="148a8-177">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="148a8-177">**Message count**</span></span>

<span data-ttu-id="148a8-178">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="148a8-179">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="148a8-180">Método de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-180">Encryption method</span></span>
- <span data-ttu-id="148a8-181">Modelo de criptografia</span><span class="sxs-lookup"><span data-stu-id="148a8-181">Encryption template</span></span>

<span data-ttu-id="148a8-182">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="148a8-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="148a8-183">Relatório de status do fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="148a8-183">Mailflow status report</span></span>

<span data-ttu-id="148a8-184">O **relatório de status do fluxo de mensagens** contém informações sobre malware, spam, phishing e mensagens bloqueadas por borda.</span><span class="sxs-lookup"><span data-stu-id="148a8-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="148a8-185">Para obter mais detalhes, consulte [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="148a8-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="148a8-186">Detecções de malware no relatório de email</span><span class="sxs-lookup"><span data-stu-id="148a8-186">Malware detections in email report</span></span>

<span data-ttu-id="148a8-187">O **relatório de detecções de malware** no email mostra informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado pela Proteção do Exchange Online ou EOP).</span><span class="sxs-lookup"><span data-stu-id="148a8-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="148a8-188">Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="148a8-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="148a8-189">O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite 10 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="148a8-190">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione detecções de malware no  \>  **email.**</span><span class="sxs-lookup"><span data-stu-id="148a8-190">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="148a8-191">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="148a8-191">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Detecções de malware no widget de email no painel Relatórios](../../media/malware-detections-widget.png)

<span data-ttu-id="148a8-193">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando:</span><span class="sxs-lookup"><span data-stu-id="148a8-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="148a8-194">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="148a8-195">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="148a8-195">**Inbound**</span></span>
- <span data-ttu-id="148a8-196">**Saída**</span><span class="sxs-lookup"><span data-stu-id="148a8-196">**Outbound**</span></span>

![Exibição de relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

<span data-ttu-id="148a8-198">Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="148a8-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="148a8-199">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-199">**Date**</span></span>
- <span data-ttu-id="148a8-200">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="148a8-200">**Sender address**</span></span>
- <span data-ttu-id="148a8-201">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="148a8-201">**Recipient address**</span></span>
- <span data-ttu-id="148a8-202">**ID da** mensagem: disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="148a8-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="148a8-203">Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).</span><span class="sxs-lookup"><span data-stu-id="148a8-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="148a8-204">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="148a8-204">**Subject**</span></span>
- <span data-ttu-id="148a8-205">**Filename**</span><span class="sxs-lookup"><span data-stu-id="148a8-205">**Filename**</span></span>
- <span data-ttu-id="148a8-206">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="148a8-206">**Malware name**</span></span>

<span data-ttu-id="148a8-207">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="148a8-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="148a8-208">Relatório de latência de email</span><span class="sxs-lookup"><span data-stu-id="148a8-208">Mail latency report</span></span>

<span data-ttu-id="148a8-209">O **relatório de latência de email** contém informações sobre a entrega de email e a latência de detonação experimentado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="148a8-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="148a8-210">Para obter mais informações, consulte [Relatório de latência de email.](view-reports-for-atp.md#mail-latency-report)</span><span class="sxs-lookup"><span data-stu-id="148a8-210">For more information, see [Mail latency report](view-reports-for-atp.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="148a8-211">Relatório de emails enviados e recebidos</span><span class="sxs-lookup"><span data-stu-id="148a8-211">Sent and received email report</span></span>

<span data-ttu-id="148a8-212">O **relatório de emails** enviados e recebidos contém informações sobre malware, spam, regras de fluxo de emails (também conhecidas como regras de transporte) e detecções avançadas de malware depois que o email entra no serviço.</span><span class="sxs-lookup"><span data-stu-id="148a8-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="148a8-213">Para obter mais informações, consulte [Relatório de emails enviados e recebidos.](view-mail-flow-reports.md#sent-and-received-email-report)</span><span class="sxs-lookup"><span data-stu-id="148a8-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="148a8-214">Relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="148a8-214">Spam detections report</span></span>

<span data-ttu-id="148a8-215">O **relatório de detecções de** spam mostra mensagens de email de spam bloqueadas pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="148a8-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="148a8-216">As mensagens são contadas individualmente, não por destinatário.</span><span class="sxs-lookup"><span data-stu-id="148a8-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="148a8-217">Por exemplo, se a mesma mensagem de spam foi enviada para 100 destinatários em sua organização, ela conta como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="148a8-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="148a8-218">A exibição agregada permite a filtragem por 90 dias, enquanto a tabela de detalhes permite a filtragem de 10 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="148a8-219">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione  \>  **detecções de spam.**</span><span class="sxs-lookup"><span data-stu-id="148a8-219">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="148a8-220">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="148a8-220">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget de detecções de spam no painel Relatórios](../../media/spam-detections-report-widget.png)

<span data-ttu-id="148a8-222">Para obter mais informações sobre proteção anti-spam, consulte [Proteção anti-spam no EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="148a8-223">Exibição de relatório para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="148a8-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="148a8-224">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="148a8-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="148a8-225">**Abaixo por: Ação:** os seguintes tipos de evento são mostrados:</span><span class="sxs-lookup"><span data-stu-id="148a8-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="148a8-226">**Conteúdo de spam filtrado**</span><span class="sxs-lookup"><span data-stu-id="148a8-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="148a8-227">**Bloqueio de IP de spam**</span><span class="sxs-lookup"><span data-stu-id="148a8-227">**Spam IP block**</span></span>
  - <span data-ttu-id="148a8-228">**Bloqueio de envelope de spam**</span><span class="sxs-lookup"><span data-stu-id="148a8-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="148a8-229">**Filtro DBEB de spam:** bloqueio de borda baseado em diretório (DBEB)</span><span class="sxs-lookup"><span data-stu-id="148a8-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="148a8-230">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantos itens foram bloqueados naquele dia, bem como como esses itens são categorizados.</span><span class="sxs-lookup"><span data-stu-id="148a8-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Exibição de ação no relatório de detecções de spam](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="148a8-232">**Down by: Direction**: The following directions are shown:</span><span class="sxs-lookup"><span data-stu-id="148a8-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="148a8-233">**Entrada**</span><span class="sxs-lookup"><span data-stu-id="148a8-233">**Inbound**</span></span>
  - <span data-ttu-id="148a8-234">**Saída**</span><span class="sxs-lookup"><span data-stu-id="148a8-234">**Outbound**</span></span>

  ![Exibição de direção no relatório de detecções de spam](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="148a8-236">Se você clicar **em Filtros** em uma exibição de relatório, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="148a8-237">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="148a8-238">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="148a8-238">Direction values</span></span>
- <span data-ttu-id="148a8-239">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="148a8-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="148a8-240">Exibição de tabela de detalhes para o relatório de detecções de spam</span><span class="sxs-lookup"><span data-stu-id="148a8-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="148a8-241">Se você clicar em **Exibir tabela de detalhes** em qualquer exibição de relatório, as seguintes informações serão mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="148a8-242">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-242">**Date**</span></span>
- <span data-ttu-id="148a8-243">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="148a8-243">**Sender address**</span></span>
- <span data-ttu-id="148a8-244">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="148a8-244">**Recipient address**</span></span>
- <span data-ttu-id="148a8-245">**Tipo de evento**</span><span class="sxs-lookup"><span data-stu-id="148a8-245">**Event type**</span></span>
- <span data-ttu-id="148a8-246">**Ação**</span><span class="sxs-lookup"><span data-stu-id="148a8-246">**Action**</span></span>
- <span data-ttu-id="148a8-247">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="148a8-247">**Subject**</span></span>

<span data-ttu-id="148a8-248">Se você clicar **em Filtros** em uma tabela de detalhes, poderá modificar os resultados com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="148a8-249">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="148a8-250">Valores de direção</span><span class="sxs-lookup"><span data-stu-id="148a8-250">Direction values</span></span>
- <span data-ttu-id="148a8-251">Valores de tipo de evento</span><span class="sxs-lookup"><span data-stu-id="148a8-251">Event type values</span></span>

<span data-ttu-id="148a8-252">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="148a8-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="148a8-253">Relatório de detecções de spoof</span><span class="sxs-lookup"><span data-stu-id="148a8-253">Spoof detections report</span></span>

<span data-ttu-id="148a8-254">O relatório de detecções de Spoof mostra quantas mensagens de email falsas foram detectadas e quais foram consideradas "boas" (emails de **spoof** feitos por motivos comerciais legítimos).</span><span class="sxs-lookup"><span data-stu-id="148a8-254">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="148a8-255">Para obter mais informações sobre a spoofing, consulte [Proteção anti-spoofing no EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="148a8-255">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="148a8-256">A exibição agregada do relatório permite 90 dias de filtragem, enquanto a exibição de detalhes só permite dez dias de filtragem.</span><span class="sxs-lookup"><span data-stu-id="148a8-256">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="148a8-257">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione  \>  **detecções de Spoof**.</span><span class="sxs-lookup"><span data-stu-id="148a8-257">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="148a8-258">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="148a8-258">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widget de detecções de spoof no painel Relatórios](../../media/spoof-detections-widget.png)

<span data-ttu-id="148a8-260">Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens de email falsas passaram.</span><span class="sxs-lookup"><span data-stu-id="148a8-260">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="148a8-261">Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="148a8-261">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="148a8-262">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-262">**Start date** and **End date**</span></span>

- <span data-ttu-id="148a8-263">**Email bom**</span><span class="sxs-lookup"><span data-stu-id="148a8-263">**Good mail**</span></span>

- <span data-ttu-id="148a8-264">**Capturado como spam**</span><span class="sxs-lookup"><span data-stu-id="148a8-264">**Caught as spam**</span></span>

![Exibição de relatório no relatório de detecções de Spoof](../../media/spoof-detections-report-view.png)

<span data-ttu-id="148a8-266">Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="148a8-266">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="148a8-267">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-267">**Date**</span></span>
- <span data-ttu-id="148a8-268">**Remetente spoofed**</span><span class="sxs-lookup"><span data-stu-id="148a8-268">**Spoofed sender**</span></span>
- <span data-ttu-id="148a8-269">**Remetente verdadeiro**</span><span class="sxs-lookup"><span data-stu-id="148a8-269">**True sender**</span></span>
- <span data-ttu-id="148a8-270">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="148a8-270">**Sender IP**</span></span>
- <span data-ttu-id="148a8-271">**Ação**</span><span class="sxs-lookup"><span data-stu-id="148a8-271">**Action**</span></span>
- <span data-ttu-id="148a8-272">**Contagem de mensagem**</span><span class="sxs-lookup"><span data-stu-id="148a8-272">**Message count**</span></span>

<span data-ttu-id="148a8-273">Para voltar para a exibição de relatório, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="148a8-273">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="148a8-274">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="148a8-274">Threat protection status report</span></span>

<span data-ttu-id="148a8-275">O **relatório de status de** proteção contra ameaças está disponível no EOP e no Microsoft Defender para Office 365; no entanto, os relatórios contêm dados diferentes.</span><span class="sxs-lookup"><span data-stu-id="148a8-275">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="148a8-276">Por exemplo, os clientes do EOP podem exibir informações sobre malware detectado no email, mas não informações sobre arquivos mal-intencionados detectados por Anexos seguros para [o SharePoint, o OneDrive](atp-for-spo-odb-and-teams.md)e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="148a8-276">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="148a8-277">O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) que foram bloqueados pelo mecanismo anti-malware, zap [(limpeza automática zero hora)](zero-hour-auto-purge.md)e recursos do Defender para Office 365, como links [seguros,](atp-safe-links.md) [anexos](atp-safe-attachments.md)seguros e [anti-phishing.](set-up-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-277">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="148a8-278">Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajuste.</span><span class="sxs-lookup"><span data-stu-id="148a8-278">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="148a8-279">**Observação:** é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes, e não como uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="148a8-279">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="148a8-280">Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione o status de proteção contra  \>  **ameaças.**</span><span class="sxs-lookup"><span data-stu-id="148a8-280">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="148a8-281">Para ir diretamente para o relatório, abra uma das seguintes URLs:</span><span class="sxs-lookup"><span data-stu-id="148a8-281">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="148a8-282">Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="148a8-282">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="148a8-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="148a8-283">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget de status de proteção contra ameaças no painel Relatórios](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="148a8-285">Por padrão, o gráfico mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-285">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="148a8-286">Se você clicar **em Filtros,** poderá selecionar um intervalo de datas de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias).</span><span class="sxs-lookup"><span data-stu-id="148a8-286">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="148a8-287">A exibição de tabela de detalhes permite a filtragem por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="148a8-287">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="148a8-288">Exibição de relatório para o relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="148a8-288">Report view for the Threat protection status report</span></span>

<span data-ttu-id="148a8-289">Os seguintes exibições estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="148a8-289">The following views are available:</span></span>

- <span data-ttu-id="148a8-290">**Exibir dados por: Visão geral:** as seguintes informações de detecção são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-290">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="148a8-291">**Malware de email**</span><span class="sxs-lookup"><span data-stu-id="148a8-291">**Email malware**</span></span>
  - <span data-ttu-id="148a8-292">**Phishing de email**</span><span class="sxs-lookup"><span data-stu-id="148a8-292">**Email phish**</span></span>
  - <span data-ttu-id="148a8-293">**Malware de conteúdo**</span><span class="sxs-lookup"><span data-stu-id="148a8-293">**Content malware**</span></span>

  ![Visão geral no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="148a8-295">**Exibir dados por: Conteúdo \> Malware**<sup>1</sup>: as seguintes informações são mostradas para organizações do Microsoft Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="148a8-295">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="148a8-296">**Mecanismo anti-malware:** arquivos mal-intencionados detectados no Sharepoint, no OneDrive e no Microsoft Teams pela detecção de vírus interna no [Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-296">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="148a8-297">**Detonação** de arquivo: arquivos mal-intencionados detectados pelos Anexos Seguros [para o SharePoint, o OneDrive e o Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-297">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

  ![Exibição de malware de conteúdo no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="148a8-299">**Exibir dados por: Substituição de Mensagem:** as informações do motivo da substituição a seguir são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-299">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="148a8-300">**Ignorar no local**</span><span class="sxs-lookup"><span data-stu-id="148a8-300">**On-premises skip**</span></span>
  - <span data-ttu-id="148a8-301">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="148a8-301">**IP Allow**</span></span>
  - <span data-ttu-id="148a8-302">**Regra de fluxo de emails**</span><span class="sxs-lookup"><span data-stu-id="148a8-302">**Mail flow rule**</span></span>
  - <span data-ttu-id="148a8-303">**Permitir remetente**</span><span class="sxs-lookup"><span data-stu-id="148a8-303">**Sender allow**</span></span>
  - <span data-ttu-id="148a8-304">**Permitir domínio**</span><span class="sxs-lookup"><span data-stu-id="148a8-304">**Domain allow**</span></span>
  - <span data-ttu-id="148a8-305">**ZAP não habilitado**</span><span class="sxs-lookup"><span data-stu-id="148a8-305">**ZAP not enabled**</span></span>
  - <span data-ttu-id="148a8-306">**Pasta Lixo Eletrônico não habilitada**</span><span class="sxs-lookup"><span data-stu-id="148a8-306">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="148a8-307">**Remetente Seguro do Usuário**</span><span class="sxs-lookup"><span data-stu-id="148a8-307">**User Safe Sender**</span></span>
  - <span data-ttu-id="148a8-308">**Domínio seguro do usuário**</span><span class="sxs-lookup"><span data-stu-id="148a8-308">**User Safe Domain**</span></span>

  ![Exibição de substituição de mensagem no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="148a8-310">**Confira abaixo: Tecnologia de detecção e** exibir dados **por: \> Phishing** de email: as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-310">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="148a8-311">**Reputação de URL** gerada pela ATP <sup>1:</sup>reputação de URL mal-intencionada gerada pelo Defender para ataques do Office 365 em outros clientes do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="148a8-311">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="148a8-312">**Filtro de phishing** avançado: sinais de phishing com base no aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="148a8-312">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="148a8-313">**Anti-spoof - Falha do DMARC:** falha de autenticação do DMARC em mensagens.</span><span class="sxs-lookup"><span data-stu-id="148a8-313">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="148a8-314">**Anti-spoof - dentro da organização**: o remetente está tentando fazer spoof do domínio do destinatário.</span><span class="sxs-lookup"><span data-stu-id="148a8-314">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="148a8-315">**Anti-spoof - domínio externo**: o remetente está tentando fazer spoof de algum outro domínio.</span><span class="sxs-lookup"><span data-stu-id="148a8-315">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="148a8-316">**Representação de marca**: representação de marcas conhecidas com base em senders.</span><span class="sxs-lookup"><span data-stu-id="148a8-316">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="148a8-317">**Representação de domínio**<sup>1:</sup>Representação de domínios que o cliente possui ou define.</span><span class="sxs-lookup"><span data-stu-id="148a8-317">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="148a8-318">**Reputação da URL do EOP:** reputação de URL mal-intencionada.</span><span class="sxs-lookup"><span data-stu-id="148a8-318">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="148a8-319">**Filtro de phishing** geral: sinais de phishing com base em regras de analista.</span><span class="sxs-lookup"><span data-stu-id="148a8-319">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="148a8-320">**Outros**</span><span class="sxs-lookup"><span data-stu-id="148a8-320">**Others**</span></span>
  - <span data-ttu-id="148a8-321">**ZAP de phishing**<sup>2:</sup>limpeza automática zero hora de mensagens de phishing.</span><span class="sxs-lookup"><span data-stu-id="148a8-321">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="148a8-322">**Detonação de URL**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="148a8-322">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="148a8-323">**Representação de usuário**<sup>1:</sup>Representação de usuários definida pelo administrador ou aprendida por meio da inteligência de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="148a8-323">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Exibição de tecnologia de detecção para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="148a8-325">**Confira: Tecnologia de detecção e** exibir dados **por: Malware \> de email:** as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-325">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="148a8-326">**Reputação de arquivo gerada pela ATP**<sup>1:</sup>toda a reputação de arquivo mal-intencionado gerada pelo Defender para ataques do Office 365.</span><span class="sxs-lookup"><span data-stu-id="148a8-326">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="148a8-327">**Mecanismo anti-malware**<sup>1:</sup>detecção de mecanismos anti-malware.</span><span class="sxs-lookup"><span data-stu-id="148a8-327">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="148a8-328">**Bloqueio de tipo de arquivo de política anti-malware:** são mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.</span><span class="sxs-lookup"><span data-stu-id="148a8-328">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="148a8-329">**Detonação**<sup>de arquivo 1:</sup>detecção por anexos seguros.</span><span class="sxs-lookup"><span data-stu-id="148a8-329">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="148a8-330">**Reputação de arquivos mal-intencionados**</span><span class="sxs-lookup"><span data-stu-id="148a8-330">**Malicious file reputation**</span></span>
  - <span data-ttu-id="148a8-331">**ZAP**<sup>2 de</sup> malware</span><span class="sxs-lookup"><span data-stu-id="148a8-331">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="148a8-332">**Outros**</span><span class="sxs-lookup"><span data-stu-id="148a8-332">**Others**</span></span>

  ![Exibição de tecnologia de detecção para malware no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="148a8-334">**Intervalo por: Tipo de** política e Exibir dados **por: Email \> Phish** or **Exibir dados por: Malware \>** de Email : As seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-334">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="148a8-335">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="148a8-335">**Anti-malware**</span></span>
  - <span data-ttu-id="148a8-336">**Anexos seguros**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="148a8-336">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="148a8-337">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="148a8-337">**Anti-phish**</span></span>
  - <span data-ttu-id="148a8-338">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="148a8-338">**Anti-spam**</span></span>
  - <span data-ttu-id="148a8-339">**Regra de fluxo de** emails (também conhecida como regra de transporte)</span><span class="sxs-lookup"><span data-stu-id="148a8-339">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="148a8-340">**Outros**</span><span class="sxs-lookup"><span data-stu-id="148a8-340">**Others**</span></span>

  ![Exibição de tipo de política para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="148a8-342">**Intervalo por: Status de entrega** e Exibir dados **por: \> Phishing** de email ou exibir dados **por: \> Malware** de email: as seguintes informações são mostradas:</span><span class="sxs-lookup"><span data-stu-id="148a8-342">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="148a8-343">**Falha na entrega**</span><span class="sxs-lookup"><span data-stu-id="148a8-343">**Delivery failed**</span></span>
  - <span data-ttu-id="148a8-344">**Dropped**</span><span class="sxs-lookup"><span data-stu-id="148a8-344">**Dropped**</span></span>
  - <span data-ttu-id="148a8-345">**Encaminhado**</span><span class="sxs-lookup"><span data-stu-id="148a8-345">**Forwarded**</span></span>
  - <span data-ttu-id="148a8-346">**Caixa de correio hospedada: pasta personalizada**</span><span class="sxs-lookup"><span data-stu-id="148a8-346">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="148a8-347">**Caixa de correio hospedada: Itens excluídos**</span><span class="sxs-lookup"><span data-stu-id="148a8-347">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="148a8-348">**Caixa de correio hospedada: Caixa de Entrada**</span><span class="sxs-lookup"><span data-stu-id="148a8-348">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="148a8-349">**Caixa de correio hospedada: Lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="148a8-349">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="148a8-350">**Servidor local: Entregue**</span><span class="sxs-lookup"><span data-stu-id="148a8-350">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="148a8-351">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="148a8-351">**Quarantine**</span></span>

  ![Exibição de status de entrega para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="148a8-353"><sup>1</sup> Defender para Office 365 somente</span><span class="sxs-lookup"><span data-stu-id="148a8-353"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="148a8-354"><sup>A</sup> ZAP (Limpeza Automática Zero Hora) não está disponível no EOP autônomo (funciona apenas em caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="148a8-354"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="148a8-355">Se você clicar **em Filtros,** os filtros disponíveis dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="148a8-355">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="148a8-356">Para **exibir dados por: \> Malware** de conteúdo, você pode modificar o relatório **por** data de início e **data** de término e o valor **de** detecção.</span><span class="sxs-lookup"><span data-stu-id="148a8-356">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="148a8-357">Para **exibir dados por: Substituição de Mensagem,** você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-357">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="148a8-358">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-358">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-359">**Motivo da substituição**</span><span class="sxs-lookup"><span data-stu-id="148a8-359">**Override Reason**</span></span>
  - <span data-ttu-id="148a8-360">**Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="148a8-360">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="148a8-361">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-361">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="148a8-362">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="148a8-362">**Domain**</span></span>

- <span data-ttu-id="148a8-363">Para todos os outros, você pode modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-363">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="148a8-364">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-364">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-365">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="148a8-365">**Detection**</span></span>
  - <span data-ttu-id="148a8-366">**Protegido por:** **ATP** **ou EOP**</span><span class="sxs-lookup"><span data-stu-id="148a8-366">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="148a8-367">**Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="148a8-367">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="148a8-368">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-368">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="148a8-369">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="148a8-369">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="148a8-370">Visão de tabela de detalhes do relatório de status de Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="148a8-370">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="148a8-371">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="148a8-371">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="148a8-372">**Exibir dados por: Visão geral:** o botão **Tabela de detalhes** Sem Exibição está disponível.</span><span class="sxs-lookup"><span data-stu-id="148a8-372">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="148a8-373">**Exibir dados por: Conteúdo \> Malware**:</span><span class="sxs-lookup"><span data-stu-id="148a8-373">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="148a8-374">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-374">**Date**</span></span>
  - <span data-ttu-id="148a8-375">**Location**</span><span class="sxs-lookup"><span data-stu-id="148a8-375">**Location**</span></span>
  - <span data-ttu-id="148a8-376">**Direcionado por**</span><span class="sxs-lookup"><span data-stu-id="148a8-376">**Directed by**</span></span>
  - <span data-ttu-id="148a8-377">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="148a8-377">**Malware name**</span></span>

  <span data-ttu-id="148a8-378">Se você clicar **em Filtros** nesta exibição, poderá modificar o relatório por data de início e **data** de término e o **valor de** detecção. </span><span class="sxs-lookup"><span data-stu-id="148a8-378">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="148a8-379">**Exibir dados por: Substituição de Mensagem:**</span><span class="sxs-lookup"><span data-stu-id="148a8-379">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="148a8-380">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-380">**Date**</span></span>
  - <span data-ttu-id="148a8-381">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="148a8-381">**Subject**</span></span>
  - <span data-ttu-id="148a8-382">**Sender**</span><span class="sxs-lookup"><span data-stu-id="148a8-382">**Sender**</span></span>
  - <span data-ttu-id="148a8-383">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="148a8-383">**Recipients**</span></span>
  - <span data-ttu-id="148a8-384">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="148a8-384">**Detected by**</span></span>
  - <span data-ttu-id="148a8-385">**Motivo da substituição**</span><span class="sxs-lookup"><span data-stu-id="148a8-385">**Override Reason**</span></span>
  - <span data-ttu-id="148a8-386">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="148a8-386">**Source of Compromise**</span></span>
  - <span data-ttu-id="148a8-387">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="148a8-387">**Tags**</span></span>

  <span data-ttu-id="148a8-388">Se você clicar **em Filtros** nesta exibição, poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-388">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="148a8-389">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-389">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-390">**Motivo da substituição**</span><span class="sxs-lookup"><span data-stu-id="148a8-390">**Override Reason**</span></span>
  - <span data-ttu-id="148a8-391">**Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="148a8-391">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="148a8-392">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-392">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="148a8-393">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="148a8-393">**Domain**</span></span>
  - <span data-ttu-id="148a8-394">**Destinatários** (observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="148a8-394">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="148a8-395">Todos os outros gráficos:</span><span class="sxs-lookup"><span data-stu-id="148a8-395">All other charts:</span></span>

  - <span data-ttu-id="148a8-396">**Date**</span><span class="sxs-lookup"><span data-stu-id="148a8-396">**Date**</span></span>
  - <span data-ttu-id="148a8-397">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="148a8-397">**Subject**</span></span>
  - <span data-ttu-id="148a8-398">**Sender**</span><span class="sxs-lookup"><span data-stu-id="148a8-398">**Sender**</span></span>
  - <span data-ttu-id="148a8-399">**Destinatários**</span><span class="sxs-lookup"><span data-stu-id="148a8-399">**Recipients**</span></span>
  - <span data-ttu-id="148a8-400">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="148a8-400">**Detected by**</span></span>
  - <span data-ttu-id="148a8-401">**Status de Entrega**</span><span class="sxs-lookup"><span data-stu-id="148a8-401">**Delivery Status**</span></span>
  - <span data-ttu-id="148a8-402">**Fonte de comprometimento**</span><span class="sxs-lookup"><span data-stu-id="148a8-402">**Source of Compromise**</span></span>
  - <span data-ttu-id="148a8-403">**Marcas**</span><span class="sxs-lookup"><span data-stu-id="148a8-403">**Tags**</span></span>

  <span data-ttu-id="148a8-404">Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="148a8-404">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="148a8-405">**Data de início** e **data de término**</span><span class="sxs-lookup"><span data-stu-id="148a8-405">**Start date** and **End date**</span></span>
  - <span data-ttu-id="148a8-406">**Detecção**</span><span class="sxs-lookup"><span data-stu-id="148a8-406">**Detection**</span></span>
  - <span data-ttu-id="148a8-407">**Protegido por:** **Defender para Office 365** **ou EOP**</span><span class="sxs-lookup"><span data-stu-id="148a8-407">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="148a8-408">**Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias).</span><span class="sxs-lookup"><span data-stu-id="148a8-408">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="148a8-409">Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-409">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="148a8-410">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="148a8-410">**Domain**</span></span>
  - <span data-ttu-id="148a8-411">**Destinatários** (observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)</span><span class="sxs-lookup"><span data-stu-id="148a8-411">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="148a8-412">Relatório de malware principal</span><span class="sxs-lookup"><span data-stu-id="148a8-412">Top malware report</span></span>

<span data-ttu-id="148a8-413">O **relatório de malware** principal mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-413">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="148a8-414">Para exibir o relatório, abra o [Centro de Conformidade e Segurança &,](https://protection.office.com)vá para o Painel de Relatórios e selecione Malware  \>  **principal.**</span><span class="sxs-lookup"><span data-stu-id="148a8-414">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="148a8-415">Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="148a8-415">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Principal widget de malware no painel Relatórios](../../media/top-malware-report-widget.png)

<span data-ttu-id="148a8-417">Quando você passar o mouse sobre um 100o no gráfico de pizza, poderá ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.</span><span class="sxs-lookup"><span data-stu-id="148a8-417">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Exibição do relatório de malware principal](../../media/top-malware-report-view.png)

<span data-ttu-id="148a8-419">Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="148a8-419">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="148a8-420">**Principais malwares**</span><span class="sxs-lookup"><span data-stu-id="148a8-420">**Top malware**</span></span>
- <span data-ttu-id="148a8-421">**Count**</span><span class="sxs-lookup"><span data-stu-id="148a8-421">**Count**</span></span>

<span data-ttu-id="148a8-422">Se você clicar em **Filtros** na exibição de relatório ou na exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="148a8-422">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="148a8-423">Relatório de proteção contra ameaças de URL</span><span class="sxs-lookup"><span data-stu-id="148a8-423">URL threat protection report</span></span>

<span data-ttu-id="148a8-424">O **relatório de proteção contra ameaças de URL** está disponível no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="148a8-424">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="148a8-425">Para obter mais informações, consulte o [relatório de proteção contra ameaças de URL.](view-reports-for-atp.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="148a8-425">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="148a8-426">Relatório de mensagens relatadas pelo usuário</span><span class="sxs-lookup"><span data-stu-id="148a8-426">User-reported messages report</span></span>

<span data-ttu-id="148a8-427">O  relatório de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que [](enable-the-report-message-add-in.md) os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento Mensagem de Relatório ou o complemento Phishing de [Relatório.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-427">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="148a8-428">Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, como uma exceção de política de spam ou uma regra de fluxo de emails configurada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="148a8-428">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="148a8-429">Para exibir detalhes, selecione um item na lista de relatórios  do usuário e, em seguida, veja as informações nas **guias** Resumo e Detalhes.</span><span class="sxs-lookup"><span data-stu-id="148a8-429">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![O User-Reported mensagens mostra mensagens rotuladas como lixo eletrônico, não tentativas de lixo eletrônico ou phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="148a8-431">Para exibir esse relatório, no Centro [de Conformidade & segurança,](https://protection.office.com)faça um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="148a8-431">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="148a8-432">Vá para **o Painel de Gerenciamento** de \> **Ameaças** Mensagens \> **relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="148a8-432">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="148a8-433">Vá para **Análise de gerenciamento de** ameaças \> **Mensagens** \> **relatadas pelo usuário.**</span><span class="sxs-lookup"><span data-stu-id="148a8-433">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![No Centro de Conformidade & segurança, escolha Revisar ameaças Mensagens relatadas \> \> pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="148a8-435">Para que o relatório de mensagens relatadas  pelo usuário funcione corretamente, o log de auditoria deve estar ligado para seu ambiente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="148a8-435">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="148a8-436">Isso geralmente é feito por alguém que tem a função Logs de Auditoria atribuída no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="148a8-436">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="148a8-437">Para saber mais, confira Ativar ou desativar a pesquisa de log de [auditoria do Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-437">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="148a8-438">Quais permissões são necessárias para exibir esses relatórios?</span><span class="sxs-lookup"><span data-stu-id="148a8-438">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="148a8-439">Para exibir e usar os relatórios descritos neste artigo &, você precisa ser membro de um dos seguintes grupos de função no Centro de Conformidade e Segurança:</span><span class="sxs-lookup"><span data-stu-id="148a8-439">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Security & Compliance Center:</span></span>

- <span data-ttu-id="148a8-440">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="148a8-440">**Organization Management**</span></span>
- <span data-ttu-id="148a8-441">**Administrador de Segurança**</span><span class="sxs-lookup"><span data-stu-id="148a8-441">**Security Administrator**</span></span>
- <span data-ttu-id="148a8-442">**Leitor de Segurança**</span><span class="sxs-lookup"><span data-stu-id="148a8-442">**Security Reader**</span></span>
- <span data-ttu-id="148a8-443">**Leitor Global**</span><span class="sxs-lookup"><span data-stu-id="148a8-443">**Global Reader**</span></span>

<span data-ttu-id="148a8-444">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="148a8-444">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="148a8-445">**Observação:** a adição de usuários à função do Azure Active Directory correspondente no Centro de administração do  Microsoft 365 oferece aos usuários as permissões necessárias no Centro de Conformidade e Segurança & e permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="148a8-445">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="148a8-446">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="148a8-446">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="148a8-447">E se os relatórios não mostrarem dados?</span><span class="sxs-lookup"><span data-stu-id="148a8-447">What if the reports aren't showing data?</span></span>

<span data-ttu-id="148a8-448">Se você não estiver vendo dados em seus relatórios, verifique se as políticas estão configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="148a8-448">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="148a8-449">Para saber mais, confira [Proteger contra ameaças.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="148a8-449">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="148a8-450">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="148a8-450">Related topics</span></span>

[<span data-ttu-id="148a8-451">Proteção anti-spam e anti-malware no EOP</span><span class="sxs-lookup"><span data-stu-id="148a8-451">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="148a8-452">Relatórios inteligentes e insights no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="148a8-452">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="148a8-453">Exibir relatórios de fluxo de emails no Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="148a8-453">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="148a8-454">Exibir relatórios do Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="148a8-454">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)
