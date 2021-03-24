---
title: Visão geral sobre novos usuários encaminhando email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender como usar o novo usuário encaminhando informações de email no Centro de Conformidade e Segurança & para investigar quando os usuários em sua organização estão encaminhando mensagens para novos domínios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053140"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="8bcfa-103">Novos usuários encaminhando informações de email no Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="8bcfa-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8bcfa-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-104">**Applies to**</span></span>
- [<span data-ttu-id="8bcfa-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8bcfa-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="8bcfa-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8bcfa-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="8bcfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bcfa-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="8bcfa-108">É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-108">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="8bcfa-109">Os **novos domínio & s** que [](https://protection.office.com) estão sendo encaminhados no Centro de Conformidade e Segurança notificam você quando usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-109">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="8bcfa-110">Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar os novos usuários.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-110">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="8bcfa-111">Se você suspeitar que as contas foram comprometidas, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="8bcfa-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="8bcfa-112">Esse insight aparece somente quando o problema é detectado e aparece na página [Relatório de](view-mail-flow-reports.md#forwarding-report) Encaminhamento.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-112">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="8bcfa-114">Quando você clica no widget, um sobremenu aparece onde você pode encontrar mais [](#forwarding-modifications-report) detalhes sobre as mensagens encaminhadas, incluindo um link para o relatório de modificações de encaminhamento conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-114">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Detalhes sobre o sobrevoo que aparece após clicar no insight De encaminhamento de email novos usuários](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="8bcfa-116">Você também pode acessar **essa** página de detalhes  quando selecionar o insight depois de clicar em Exibir tudo na área Principais & recomendações em (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="8bcfa-116">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="8bcfa-117">Você pode clicar no link Ver relatório associado  **ao** insight para acessar o relatório de modificações de encaminhamento conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-117">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="8bcfa-118">Relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="8bcfa-118">Forwarding modifications report</span></span>

<span data-ttu-id="8bcfa-119">O **relatório de modificações de encaminhamento** mostra detalhes sobre mensagens que estão sendo encaminhadas automaticamente de senders em sua organização:</span><span class="sxs-lookup"><span data-stu-id="8bcfa-119">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="8bcfa-120">Contas recém-criadas que estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-120">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="8bcfa-121">Contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas por outros senders em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-121">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="8bcfa-122">Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-122">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="8bcfa-123">O relatório contém dados de até 90 dias.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-123">The report contains data for up to 90 days.</span></span> <span data-ttu-id="8bcfa-124">Por padrão, o relatório mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-124">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="8bcfa-125">Este relatório não está disponível [](mail-flow-insights-v2.md) diretamente no painel de fluxo de emails ou no painel [Relatórios.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="8bcfa-125">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="8bcfa-126">Além de clicar no link **Ver relatório associado** ao insight no insight Novos usuários encaminhando informações de **email,** você pode acessar o relatório por:</span><span class="sxs-lookup"><span data-stu-id="8bcfa-126">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="8bcfa-127">Clicando no **link Relatório de notificações** de encaminhamento nos detalhes dos novos domínios que estão sendo [encaminhados informações de email.](mfi-new-domains-being-forwarded-email.md)</span><span class="sxs-lookup"><span data-stu-id="8bcfa-127">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="8bcfa-128">Abrindo <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="8bcfa-128">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8bcfa-129">Exibição de relatório para o relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="8bcfa-129">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="8bcfa-130">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="8bcfa-130">The following charts are available in the report view:</span></span>

- <span data-ttu-id="8bcfa-131">**Mostrar dados para: Novos usuários de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-131">**Show data for: New forwarding users**:</span></span>

  ![Nova exibição de usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="8bcfa-133">**Mostrar dados para: Novos domínios de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-133">**Show data for: New forwarding domains**:</span></span>

  ![Nova exibição de domínios encaminhados no relatório de modificações de encaminhamento](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="8bcfa-135">Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-135">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="8bcfa-136">Exibição de tabela de detalhes para o relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="8bcfa-136">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="8bcfa-137">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="8bcfa-137">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="8bcfa-138">**Mostrar dados para: Novos usuários de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-138">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="8bcfa-139">**Nome**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-139">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="8bcfa-140">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-140">**Forwarding type**</span></span>
  - <span data-ttu-id="8bcfa-141">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-141">**Recipient address**</span></span>
  - <span data-ttu-id="8bcfa-142">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-142">**Details**</span></span>
  - <span data-ttu-id="8bcfa-143">**Count**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-143">**Count**</span></span>
  - <span data-ttu-id="8bcfa-144">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-144">**First forward date**</span></span>

- <span data-ttu-id="8bcfa-145">**Mostrar dados para: Novos domínios de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-145">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="8bcfa-146">**Nome**: O domínio de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-146">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="8bcfa-147">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-147">**Forwarding type**</span></span>
  - <span data-ttu-id="8bcfa-148">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-148">**Recipient address**</span></span>
  - <span data-ttu-id="8bcfa-149">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-149">**Details**</span></span>
  - <span data-ttu-id="8bcfa-150">**Count**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-150">**Count**</span></span>
  - <span data-ttu-id="8bcfa-151">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-151">**First forward date**</span></span>

<span data-ttu-id="8bcfa-152">Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-152">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="8bcfa-153">Se você selecionar uma linha da tabela, um **sobremenu de Detalhes** aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8bcfa-153">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="8bcfa-154">**Nome**: Este é o endereço de email do remetente (de Mostrar dados **para:** nova exibição de usuários de encaminhamento) ou o domínio de email do remetente (de Mostrar dados para: Novo exibição de **domínios** de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="8bcfa-154">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="8bcfa-155">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-155">**Forwarding type**</span></span>
- <span data-ttu-id="8bcfa-156">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-156">**Recipient**</span></span>
- <span data-ttu-id="8bcfa-157">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-157">**Details**</span></span>
- <span data-ttu-id="8bcfa-158">**Count**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-158">**Count**</span></span>
- <span data-ttu-id="8bcfa-159">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="8bcfa-159">**Start date**</span></span>
- <span data-ttu-id="8bcfa-160">**Recomendação**: a partir daqui, você pode clicar no link para gerenciar o usuário no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-160">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Detalhes do sobrevoo da tabela de detalhes da exibição Novos usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="8bcfa-162">Para voltar à exibição de relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="8bcfa-162">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bcfa-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8bcfa-163">Related topics</span></span>

<span data-ttu-id="8bcfa-164">Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="8bcfa-164">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
