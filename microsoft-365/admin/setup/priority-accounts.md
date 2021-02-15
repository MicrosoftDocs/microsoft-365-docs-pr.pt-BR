---
title: Gerenciar e monitorar contas prioritárias
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Monitore mensagens de email com falha e atraso enviadas para ou de contas que têm alto impacto nos negócios.
ms.openlocfilehash: dbdd692a41d341564376960788054e70623daf5a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233357"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="ad41f-103">Gerenciar e monitorar contas prioritárias</span><span class="sxs-lookup"><span data-stu-id="ad41f-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="ad41f-104">Em cada organização do Microsoft 365, há pessoas essenciais, como executivos, líderes, gerentes ou outros usuários que têm acesso a informações confidenciais, proprietárias ou de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="ad41f-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="ad41f-105">Para ajudar sua organização a proteger essas contas, agora você pode designar usuários específicos como contas prioritárias e aproveitar os recursos específicos do aplicativo que fornecem proteção extra a eles.</span><span class="sxs-lookup"><span data-stu-id="ad41f-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="ad41f-106">No futuro, mais aplicativos e recursos darão suporte a contas de prioridade e, para começar, anunciamos dois **recursos:** proteção de conta de prioridade e monitoramento de fluxo de emails **premium.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="ad41f-107">Proteção de conta de prioridade **-** O Microsoft Defender para Office 365 (antigo Office 365 Advanced Threat Protection) dá suporte a contas prioritárias como marcas que podem ser usadas em filtros em alertas, relatórios e investigações.</span><span class="sxs-lookup"><span data-stu-id="ad41f-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="ad41f-108">Para saber mais, confira as [marcas de usuário no Microsoft Defender para Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags)</span><span class="sxs-lookup"><span data-stu-id="ad41f-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags).</span></span>
- <span data-ttu-id="ad41f-109">**Monitoramento de Fluxo de** Emails Premium - O fluxo de emails ínteio pode ser fundamental para o sucesso dos negócios, e atrasos ou falhas na entrega podem ter um impacto negativo sobre os negócios.</span><span class="sxs-lookup"><span data-stu-id="ad41f-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="ad41f-110">Você pode escolher um limite para emails com falha ou atraso, receber alertas quando esse limite for excedido e exibir um relatório de problemas de email para contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="ad41f-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="ad41f-111">Para obter mais informações, confira [Problemas de email para o relatório de contas prioritárias no EAC moderno](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="ad41f-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="ad41f-112">Para práticas recomendadas de segurança para contas prioritárias, consulte [Recomendações de segurança para contas prioritárias.](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts)</span><span class="sxs-lookup"><span data-stu-id="ad41f-112">For security best practices for priority accounts, see [Security recommendations for priority accounts](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-recommendations-for-priority-accounts).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ad41f-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ad41f-113">Before you begin</span></span>

<span data-ttu-id="ad41f-114">O **recurso de proteção de** conta de prioridade descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="ad41f-114">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="ad41f-115">Microsoft Defender para Office 365 Plano 2, incluindo aqueles com Office 365 E3, Office 365 E5, Microsoft 365 E5 ou Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="ad41f-115">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="ad41f-116">O **recurso Monitoramento de Fluxo de** Emails Premium descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="ad41f-116">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="ad41f-117">Sua organização precisa ter uma contagem de licenças de pelo menos 10.000, de um ou uma combinação dos seguintes produtos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ad41f-117">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="ad41f-118">Por exemplo, sua organização pode ter 3000 licenças do Office 365 E3 e 8500 Microsoft 365 E5, para um total de 11.500 licenças dos produtos qualificados.</span><span class="sxs-lookup"><span data-stu-id="ad41f-118">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="ad41f-119">A organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ad41f-119">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="ad41f-120">Você pode monitorar até 250 contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="ad41f-120">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="ad41f-121">Adicionar contas de prioridade da página De instalação</span><span class="sxs-lookup"><span data-stu-id="ad41f-121">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="ad41f-122">Adicione contas de prioridade da página **De instalação.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-122">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="ad41f-123">Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="ad41f-123">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ad41f-124">Vá para **Configurar o**  >  **conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-124">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="ad41f-125">Selecione **Iniciar ou** **Gerenciar.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-125">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="ad41f-126">Na página **Adicionar Contas de** Prioridade, no campo de pesquisa, digite o nome ou endereço de email da pessoa que você deseja adicionar à lista de contas prioritárias.</span><span class="sxs-lookup"><span data-stu-id="ad41f-126">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="ad41f-127">Você também pode definir o limite de email para emails com falha ou atraso e obter um relatório semanal de problemas para contas prioritárias.</span><span class="sxs-lookup"><span data-stu-id="ad41f-127">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="ad41f-128">Selecione o usuário e escolha **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-128">Select the user and choose **Save**.</span></span>

<span data-ttu-id="ad41f-129">Você também pode adicionar contas prioritárias da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="ad41f-129">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="ad41f-130">Adicionar contas de prioridade da página Usuários ativos</span><span class="sxs-lookup"><span data-stu-id="ad41f-130">Add priority accounts from Active users page</span></span>

<span data-ttu-id="ad41f-131">Adicione contas de prioridade da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="ad41f-131">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="ad41f-132">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="ad41f-132">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ad41f-133">Vá até **Usuários**  >  **Ativos e** escolha **...** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="ad41f-133">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="ad41f-134">Selecione **Gerenciar contas de prioridade.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-134">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="ad41f-135">Selecione **Adicionar contas** e, na página Adicionar Contas de Prioridade, no campo de pesquisa, digite o nome da pessoa que você deseja adicionar à lista de contas prioritárias. </span><span class="sxs-lookup"><span data-stu-id="ad41f-135">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="ad41f-136">Selecione o usuário e escolha **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-136">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="ad41f-137">Remover um usuário da lista de contas prioritárias</span><span class="sxs-lookup"><span data-stu-id="ad41f-137">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="ad41f-138">Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="ad41f-138">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="ad41f-139">Vá para **Configurar o**  >  **conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-139">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="ad41f-140">Na página **Monitorar a maioria das contas,** escolha Contas de **prioridade** em Gerenciar **esse recurso.**</span><span class="sxs-lookup"><span data-stu-id="ad41f-140">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="ad41f-141">Na página **Contas de prioridade,** selecione o usuário ou usuários que você deseja remover da lista e escolha, **Remover contas**.</span><span class="sxs-lookup"><span data-stu-id="ad41f-141">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad41f-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ad41f-142">Related topics</span></span>

[<span data-ttu-id="ad41f-143">Usando contas de prioridade no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ad41f-143">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)