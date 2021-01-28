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
description: Os administradores podem aprender a usar os novos usuários que encaminham informações de & email no Centro de Conformidade e Segurança para investigar quando os usuários em sua organização estão encaminhando mensagens para novos domínios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: af991cb0af20a0f48bc5283d4e4fb26ea75d6ba6
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029865"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="b6b30-103">Novos usuários encaminhando informações de email no Centro de Conformidade e & Segurança</span><span class="sxs-lookup"><span data-stu-id="b6b30-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b6b30-104">É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="b6b30-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="b6b30-105">Os **novos domínios** que estão sendo encaminhado [& s](https://protection.office.com) no Centro de Conformidade e Segurança notifica você quando usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="b6b30-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="b6b30-106">Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar novos usuários.</span><span class="sxs-lookup"><span data-stu-id="b6b30-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="b6b30-107">Se você suspeitar que as contas foram comprometidas, confira [Responder a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="b6b30-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="b6b30-108">Esse insight só aparece quando o problema é detectado e aparece na página [de relatório de encaminhamento.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="b6b30-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="b6b30-110">Quando você clica no widget, um flyout é exibido, onde você pode encontrar [](#forwarding-modifications-report) mais detalhes sobre as mensagens encaminhadas, incluindo um link para o relatório de modificações de encaminhamento, conforme descrito mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="b6b30-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Detalhes do flyout que aparece depois de clicar no insight de novos usuários que encaminham emails](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="b6b30-112">Você também pode acessar **essa** página de detalhes  ao selecionar as informações depois de clicar em Exibir tudo na área De informações principais & recomendações (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="b6b30-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="b6b30-113">Você pode clicar no link **Ver relatório associado ao** insight para ir para o relatório de modificações de encaminhamento conforme descrito na próxima seção. </span><span class="sxs-lookup"><span data-stu-id="b6b30-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="b6b30-114">Relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="b6b30-114">Forwarding modifications report</span></span>

<span data-ttu-id="b6b30-115">O **relatório de modificações de encaminhamento** mostra detalhes sobre as mensagens que estão sendo encaminhadas automaticamente dos envios em sua organização:</span><span class="sxs-lookup"><span data-stu-id="b6b30-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="b6b30-116">Contas recém-criadas que estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="b6b30-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="b6b30-117">Contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas por outros senders em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b6b30-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="b6b30-118">Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="b6b30-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="b6b30-119">O relatório contém dados por até 90 dias.</span><span class="sxs-lookup"><span data-stu-id="b6b30-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="b6b30-120">Por padrão, o relatório mostra dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="b6b30-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="b6b30-121">Esse relatório não está diretamente disponível no painel de fluxo de [emails](mail-flow-insights-v2.md) ou no painel [Relatórios.](view-mail-flow-reports.md)</span><span class="sxs-lookup"><span data-stu-id="b6b30-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="b6b30-122">Além de clicar no link Ver **relatório associado** ao insight no insight de novos usuários que encaminham informações de **email,** você pode acessar o relatório ao:</span><span class="sxs-lookup"><span data-stu-id="b6b30-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="b6b30-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="b6b30-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="b6b30-124">Abertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="b6b30-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="b6b30-125">Exibição de relatório para o relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="b6b30-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="b6b30-126">Os gráficos a seguir estão disponíveis na exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="b6b30-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="b6b30-127">**Mostrar dados para: Novos usuários de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="b6b30-127">**Show data for: New forwarding users**:</span></span>

  ![New forwarding users view in the Forwarding modifications report](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="b6b30-129">**Mostrar dados para: Novos domínios de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="b6b30-129">**Show data for: New forwarding domains**:</span></span>

  ![New forwarded domains view in the Forwarding modifications report](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="b6b30-131">Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="b6b30-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="b6b30-132">Visão de tabela de detalhes para o relatório de modificações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="b6b30-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="b6b30-133">Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:</span><span class="sxs-lookup"><span data-stu-id="b6b30-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="b6b30-134">**Mostrar dados para: Novos usuários de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="b6b30-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="b6b30-135">**Nome**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="b6b30-136">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="b6b30-136">**Forwarding type**</span></span>
  - <span data-ttu-id="b6b30-137">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="b6b30-137">**Recipient address**</span></span>
  - <span data-ttu-id="b6b30-138">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b6b30-138">**Details**</span></span>
  - <span data-ttu-id="b6b30-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="b6b30-139">**Count**</span></span>
  - <span data-ttu-id="b6b30-140">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="b6b30-140">**First forward date**</span></span>

- <span data-ttu-id="b6b30-141">**Mostrar dados para: Novos domínios de encaminhamento:**</span><span class="sxs-lookup"><span data-stu-id="b6b30-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="b6b30-142">**Nome**: o domínio de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="b6b30-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="b6b30-143">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="b6b30-143">**Forwarding type**</span></span>
  - <span data-ttu-id="b6b30-144">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="b6b30-144">**Recipient address**</span></span>
  - <span data-ttu-id="b6b30-145">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b6b30-145">**Details**</span></span>
  - <span data-ttu-id="b6b30-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="b6b30-146">**Count**</span></span>
  - <span data-ttu-id="b6b30-147">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="b6b30-147">**First forward date**</span></span>

<span data-ttu-id="b6b30-148">Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**</span><span class="sxs-lookup"><span data-stu-id="b6b30-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="b6b30-149">Se você selecionar uma linha da tabela, um flyout **Detalhes** aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b6b30-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="b6b30-150">**Nome:** este é o endereço de email do remetente (de Mostrar dados **para:** exibição novos usuários de encaminhamento) ou o domínio de email do remetente (de Mostrar dados para: exibição de novos **domínios** de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="b6b30-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="b6b30-151">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="b6b30-151">**Forwarding type**</span></span>
- <span data-ttu-id="b6b30-152">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="b6b30-152">**Recipient**</span></span>
- <span data-ttu-id="b6b30-153">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="b6b30-153">**Details**</span></span>
- <span data-ttu-id="b6b30-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="b6b30-154">**Count**</span></span>
- <span data-ttu-id="b6b30-155">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="b6b30-155">**Start date**</span></span>
- <span data-ttu-id="b6b30-156">**Recomendação:** a partir daqui, você pode clicar no link para gerenciar o usuário no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6b30-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Detalhes do flyout da tabela de detalhes da exibição Novos usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="b6b30-158">Para voltar para a exibição de relatórios, clique em **Exibir relatório.**</span><span class="sxs-lookup"><span data-stu-id="b6b30-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b6b30-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b6b30-159">Related topics</span></span>

<span data-ttu-id="b6b30-160">Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b6b30-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
