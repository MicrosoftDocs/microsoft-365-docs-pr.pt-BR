---
title: Visão geral sobre novos usuários encaminhando email
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos usuários que estão encaminhando informações de email no centro de conformidade de & de segurança para investigar quando os usuários de sua organização estão encaminhando mensagens para novos domínios.
ms.openlocfilehash: cf1852169279e19ac00e5e29dd1c26e155936039
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660012"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="26362-103">Novos usuários encaminhando informações de email no centro de conformidade e segurança &</span><span class="sxs-lookup"><span data-stu-id="26362-103">New users forwarding email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="26362-104">É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos de repente.</span><span class="sxs-lookup"><span data-stu-id="26362-104">It's suspicious when new user accounts in your organization suddenly start forwarding email messages to external domains.</span></span>

<span data-ttu-id="26362-105">Os **novos domínios que estão sendo encaminhados** informações de email no [centro de conformidade e segurança &](https://protection.office.com) notifica você quando os usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="26362-105">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when newly-created users in your organization are forwarding messages to external domains.</span></span> <span data-ttu-id="26362-106">Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar novos usuários.</span><span class="sxs-lookup"><span data-stu-id="26362-106">This condition could indicate compromised admin accounts were used to create the new users.</span></span> <span data-ttu-id="26362-107">Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="26362-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="26362-108">Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="26362-108">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

<span data-ttu-id="26362-110">Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link para o [relatório de alterações de encaminhamento](#forwarding-modifications-report) , conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="26362-110">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link to the [Forwarding modifications report](#forwarding-modifications-report) as described later in this article.</span></span>

![Submenu de detalhes que aparece depois de clicar nos novos usuários encaminhando informações sobre o envio de email](../../media/mfi-new-users-forwarding-email-details.png)

<span data-ttu-id="26362-112">Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de **relatórios** \>  ou <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="26362-112">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="26362-113">Você pode clicar no link **Confira o relatório associado com a percepção** para acessar o **relatório de alterações de encaminhamento** conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="26362-113">You can click the **See report associated with insight** link to go to the **Forwarding modifications report** as described in the next section.</span></span>

## <a name="forwarding-modifications-report"></a><span data-ttu-id="26362-114">Relatório de reencaminhamento de modificações</span><span class="sxs-lookup"><span data-stu-id="26362-114">Forwarding modifications report</span></span>

<span data-ttu-id="26362-115">O **relatório de alterações de encaminhamento** mostra detalhes sobre as mensagens que estão sendo encaminhadas automaticamente de remetentes em sua organização:</span><span class="sxs-lookup"><span data-stu-id="26362-115">The **Forwarding modifications report** shows details about messages that are being automatically forwarded from senders in your organization:</span></span>

- <span data-ttu-id="26362-116">Contas recém-criadas que estão encaminhando mensagens para domínios externos.</span><span class="sxs-lookup"><span data-stu-id="26362-116">Newly-created accounts that are forwarding messages to external domains.</span></span>
- <span data-ttu-id="26362-117">As contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para outros remetentes em sua organização.</span><span class="sxs-lookup"><span data-stu-id="26362-117">Accounts that are forwarding messages to external domains that have never been forwarded to by other senders in your organization.</span></span>

<span data-ttu-id="26362-118">Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="26362-118">These types of forwarded messages can pose a security or compliance risk, and might indicate compromised accounts.</span></span>

<span data-ttu-id="26362-119">O relatório contém dados de até 90 dias.</span><span class="sxs-lookup"><span data-stu-id="26362-119">The report contains data for up to 90 days.</span></span> <span data-ttu-id="26362-120">Por padrão, o relatório mostra os dados dos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="26362-120">By default, the report shows data for the last 7 days.</span></span>

<span data-ttu-id="26362-121">Este relatório não está disponível diretamente no [painel de fluxo de emails](mail-flow-insights-v2.md) ou no [painel relatórios](view-mail-flow-reports.md).</span><span class="sxs-lookup"><span data-stu-id="26362-121">This report isn't directly available in the [Mail flow dashboard](mail-flow-insights-v2.md) or in the [Reports dashboard](view-mail-flow-reports.md).</span></span> <span data-ttu-id="26362-122">Além de clicar no link **Ver relatório associado com a percepção** no **envio de emails de encaminhamento de novos usuários** , você recebe o relatório por:</span><span class="sxs-lookup"><span data-stu-id="26362-122">In addition to clicking the **See report associated with insight** link in the **New users forwarding email** insight, you get to the report by:</span></span>

- <span data-ttu-id="26362-123">Clicando no link de **relatório de notificações de encaminhamento** , nos detalhes dos [novos domínios que estão sendo encaminhados informações de email](mfi-new-domains-being-forwarded-email.md).</span><span class="sxs-lookup"><span data-stu-id="26362-123">Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).</span></span>
- <span data-ttu-id="26362-124">Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .</span><span class="sxs-lookup"><span data-stu-id="26362-124">Opening <https://protection.office.com/reportv2?id=MailFlowNewForwarding>.</span></span>

### <a name="report-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="26362-125">Exibição de relatório para o relatório de alterações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="26362-125">Report view for the Forwarding modifications report</span></span>

<span data-ttu-id="26362-126">Os gráficos a seguir estão disponíveis no modo de exibição de relatório:</span><span class="sxs-lookup"><span data-stu-id="26362-126">The following charts are available in the report view:</span></span>

- <span data-ttu-id="26362-127">**Mostrar dados de: novos usuários de encaminhamento**:</span><span class="sxs-lookup"><span data-stu-id="26362-127">**Show data for: New forwarding users**:</span></span>

  ![Novo modo de exibição de usuários de encaminhamento no relatório de alterações de encaminhamento](../../media/forwarding-modifications-report-new-forwarding-users.png)

- <span data-ttu-id="26362-129">**Mostrar dados para: novos domínios de encaminhamento**:</span><span class="sxs-lookup"><span data-stu-id="26362-129">**Show data for: New forwarding domains**:</span></span>

  ![Exibição de novos domínios encaminhados no relatório de alterações de encaminhamento](../../media/forwarding-modifications-report-new-forwarded-domains.png)

<span data-ttu-id="26362-131">Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="26362-131">If you click **Filters** in a report view, you can specify a date range with **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-forwarding-modifications-report"></a><span data-ttu-id="26362-132">Exibição da tabela de detalhes para o relatório de alterações de encaminhamento</span><span class="sxs-lookup"><span data-stu-id="26362-132">Details table view for the Forwarding modifications report</span></span>

<span data-ttu-id="26362-133">Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:</span><span class="sxs-lookup"><span data-stu-id="26362-133">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="26362-134">**Mostrar dados de: novos usuários de encaminhamento**:</span><span class="sxs-lookup"><span data-stu-id="26362-134">**Show data for: New forwarding users**:</span></span>

  - <span data-ttu-id="26362-135">**Name**: o endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="26362-135">**Name**: The email address of the sender.</span></span>
  - <span data-ttu-id="26362-136">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="26362-136">**Forwarding type**</span></span>
  - <span data-ttu-id="26362-137">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="26362-137">**Recipient address**</span></span>
  - <span data-ttu-id="26362-138">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="26362-138">**Details**</span></span>
  - <span data-ttu-id="26362-139">**Count**</span><span class="sxs-lookup"><span data-stu-id="26362-139">**Count**</span></span>
  - <span data-ttu-id="26362-140">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="26362-140">**First forward date**</span></span>

- <span data-ttu-id="26362-141">**Mostrar dados para: novos domínios de encaminhamento**:</span><span class="sxs-lookup"><span data-stu-id="26362-141">**Show data for: New forwarding domains**:</span></span>

  - <span data-ttu-id="26362-142">**Name**: o domínio de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="26362-142">**Name**: The email domain of the sender.</span></span>
  - <span data-ttu-id="26362-143">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="26362-143">**Forwarding type**</span></span>
  - <span data-ttu-id="26362-144">**Endereço do destinatário**</span><span class="sxs-lookup"><span data-stu-id="26362-144">**Recipient address**</span></span>
  - <span data-ttu-id="26362-145">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="26362-145">**Details**</span></span>
  - <span data-ttu-id="26362-146">**Count**</span><span class="sxs-lookup"><span data-stu-id="26362-146">**Count**</span></span>
  - <span data-ttu-id="26362-147">**Primeira data de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="26362-147">**First forward date**</span></span>

<span data-ttu-id="26362-148">Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.</span><span class="sxs-lookup"><span data-stu-id="26362-148">If you click **Filters** in a details table view, you can specify a date range with **Start date** and **End date**.</span></span>

<span data-ttu-id="26362-149">Se você selecionar uma linha da tabela, um submenu de **detalhes** aparecerá com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="26362-149">If you select a row from the table, a **Details** flyout appears with the following information:</span></span>

- <span data-ttu-id="26362-150">**Nome**: Este é o endereço de email do remetente (da exibição **Mostrar dados para: novos usuários de encaminhamento** ) ou o domínio de email do remetente (do **Mostrar dados para: novo** modo de exibição de domínios de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="26362-150">**Name**: This is either the sender's email address (from **Show data for: New forwarding users** view) or the sender's email domain (from **Show data for: New forwarding domains** view).</span></span>
- <span data-ttu-id="26362-151">**Tipo de encaminhamento**</span><span class="sxs-lookup"><span data-stu-id="26362-151">**Forwarding type**</span></span>
- <span data-ttu-id="26362-152">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="26362-152">**Recipient**</span></span>
- <span data-ttu-id="26362-153">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="26362-153">**Details**</span></span>
- <span data-ttu-id="26362-154">**Count**</span><span class="sxs-lookup"><span data-stu-id="26362-154">**Count**</span></span>
- <span data-ttu-id="26362-155">**Data de início**</span><span class="sxs-lookup"><span data-stu-id="26362-155">**Start date**</span></span>
- <span data-ttu-id="26362-156">**Recomendação**: aqui, você pode clicar no link para gerenciar o usuário no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26362-156">**Recommendation**: From here, you can click the link to manage the user in the Microsoft 365 admin center.</span></span>

![Submenu de detalhes da tabela detalhes do novo modo de exibição de usuários de encaminhamento no relatório de alterações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

<span data-ttu-id="26362-158">Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="26362-158">To go back to the reports view, click **View report**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="26362-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="26362-159">Related topics</span></span>

<span data-ttu-id="26362-160">Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="26362-160">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
