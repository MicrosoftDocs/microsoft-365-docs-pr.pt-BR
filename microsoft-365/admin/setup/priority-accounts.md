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
description: Monitorar mensagens enviadas por email com falha e atraso enviadas para ou de contas com alto impacto comercial.
ms.openlocfilehash: f67b9c6f0eaa229b650026670cf1b2adf88ab3c0
ms.sourcegitcommit: 58fbcfd6437bfb08966b79954ca09556e636ff4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51632175"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="4c10f-103">Gerenciar e monitorar contas prioritárias</span><span class="sxs-lookup"><span data-stu-id="4c10f-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="4c10f-104">Em cada organização do Microsoft 365, há pessoas essenciais, como executivos, líderes, gerentes ou outros usuários que têm acesso a informações confidenciais, proprietárias ou de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="4c10f-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="4c10f-105">Para ajudar sua organização a proteger essas contas, agora você pode designar usuários específicos como contas prioritárias e aproveitar recursos específicos do aplicativo que oferecem a eles proteção extra.</span><span class="sxs-lookup"><span data-stu-id="4c10f-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="4c10f-106">No futuro, mais aplicativos e recursos darão suporte a contas de prioridade e, para começar, anunciamos dois **recursos:** proteção de conta de prioridade e monitoramento de fluxo de **emails premium.**</span><span class="sxs-lookup"><span data-stu-id="4c10f-106">In the future, more apps and features will support priority accounts, and to start with, we've announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="4c10f-107">Proteção de conta de prioridade **–** o Microsoft Defender para Office 365 (anteriormente a Proteção Avançada contra Ameaças do Office 365) dá suporte a contas prioritárias como marcas que podem ser usadas em filtros em alertas, relatórios e investigações.</span><span class="sxs-lookup"><span data-stu-id="4c10f-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="4c10f-108">Para obter mais informações, confira [Marcas de usuário no Microsoft Defender para Office 365](../../security/office-365-security/user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="4c10f-108">For more information, check out [User tags in Microsoft Defender for Office 365](../../security/office-365-security/user-tags.md).</span></span>

  <span data-ttu-id="4c10f-109">Uma pergunta natural é: "Todos os usuários não são uma prioridade?</span><span class="sxs-lookup"><span data-stu-id="4c10f-109">A natural question is, "Aren't all users a priority?</span></span> <span data-ttu-id="4c10f-110">Por que não designar todos os usuários como contas prioritárias?"</span><span class="sxs-lookup"><span data-stu-id="4c10f-110">Why not designate all users as priority accounts?"</span></span> <span data-ttu-id="4c10f-111">Sim, todos os usuários são uma prioridade, mas a proteção da conta de prioridade oferece os seguintes benefícios adicionais:</span><span class="sxs-lookup"><span data-stu-id="4c10f-111">Yes, all users are a priority, but priority account protection offers the following additional benefits:</span></span>

  - <span data-ttu-id="4c10f-112">**Heurística adicional**: Nossa análise do fluxo de emails nos datacenters da Microsoft indica que os padrões de fluxo de emails para executivos da empresa são diferentes dos funcionários médios.</span><span class="sxs-lookup"><span data-stu-id="4c10f-112">**Additional heuristics**: Our analysis of mail flow in the Microsoft datacenters indicates that mail flow patterns for company executives are different than the average employee.</span></span> <span data-ttu-id="4c10f-113">A proteção de conta de prioridade oferece heurísticas adicionais especificamente adaptadas aos executivos da empresa que não beneficiaria um funcionário normal.</span><span class="sxs-lookup"><span data-stu-id="4c10f-113">Priority account protection offers additional heuristics that are specifically tailored to company executives that wouldn't benefit a regular employee.</span></span>
  - <span data-ttu-id="4c10f-114">**Visibilidade adicional no relatório**: Na verdade, as informações para todos os usuários (ou todos os usuários afetados) já estão disponíveis em alertas, relatórios e investigações.</span><span class="sxs-lookup"><span data-stu-id="4c10f-114">**Additional visibility in reporting**: In effect, information for all users (or all affected users) is already available in alerts, reports, and investigations.</span></span> <span data-ttu-id="4c10f-115">A marca de contas de prioridade como filtro permite direcionar especificamente suas investigações.</span><span class="sxs-lookup"><span data-stu-id="4c10f-115">The priority accounts tag as a filter allows you to specifically target your investigations.</span></span>

- <span data-ttu-id="4c10f-116">**Monitoramento de Fluxo de Email Premium** - O fluxo de emails saudável pode ser fundamental para o sucesso dos negócios, e atrasos ou falhas de entrega podem ter um impacto negativo sobre a empresa.</span><span class="sxs-lookup"><span data-stu-id="4c10f-116">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="4c10f-117">Você pode escolher um limite para emails com falha ou atraso, receber alertas quando esse limite for excedido e exibir um relatório de problemas de email para contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="4c10f-117">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="4c10f-118">Para obter mais informações, confira Problemas de email para o relatório de contas [de prioridade no EAC moderno](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span><span class="sxs-lookup"><span data-stu-id="4c10f-118">For more information, check out [Email issues for priority accounts report in the modern EAC](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)</span></span>

<span data-ttu-id="4c10f-119">Para práticas recomendadas de segurança para contas prioritárias, consulte [Recomendações de segurança para contas prioritárias.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="4c10f-119">For security best practices for priority accounts, see [Security recommendations for priority accounts](../../security/office-365-security/security-recommendations-for-priority-accounts.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="4c10f-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4c10f-120">Before you begin</span></span>

<span data-ttu-id="4c10f-121">O **recurso de proteção** de conta de prioridade descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="4c10f-121">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="4c10f-122">Microsoft Defender para Office 365 Plano 2, incluindo aqueles com Office 365 E3, Office 365 E5, Microsoft 365 E5 ou Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="4c10f-122">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="4c10f-123">O recurso Monitoramento de **Fluxo de** Email Premium descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="4c10f-123">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="4c10f-124">Sua organização precisa ter uma contagem de licenças de pelo menos 10.000, de um ou uma combinação dos seguintes produtos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4c10f-124">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="4c10f-125">Por exemplo, sua organização pode ter 3.000 licenças do Office 365 E3 e 8500 Microsoft 365 E5, para um total de 11.500 licenças dos produtos qualificados.</span><span class="sxs-lookup"><span data-stu-id="4c10f-125">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="4c10f-126">A organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c10f-126">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="4c10f-127">Você pode monitorar até 250 contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="4c10f-127">You can monitor up to 250 priority accounts.</span></span>

<span data-ttu-id="4c10f-128">Ao aplicar a proteção de conta de prioridade a uma caixa de correio, você também deve aplicar a proteção de conta de prioridade aos usuários que têm acesso à caixa de correio (por exemplo, o CEO e o assistente executivo do CEO que gerencia o calendário do CEO).</span><span class="sxs-lookup"><span data-stu-id="4c10f-128">When you apply priority account protection to a mailbox, you should also apply priority account protection to users who have access to the mailbox (for example, the CEO and the CEO's executive assistant who manages the CEO's calendar).</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="4c10f-129">Adicionar contas de prioridade da página De instalação</span><span class="sxs-lookup"><span data-stu-id="4c10f-129">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="4c10f-130">Adicione contas de prioridade da página **De instalação**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-130">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="4c10f-131">Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="4c10f-131">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4c10f-132">Vá para **Configurar**  >  **Conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**</span><span class="sxs-lookup"><span data-stu-id="4c10f-132">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="4c10f-133">Selecione **Iniciar ou** **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-133">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="4c10f-134">Na página **Adicionar contas de** prioridade, no campo de pesquisa, digite o nome ou o endereço de email da pessoa que você deseja adicionar à lista de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="4c10f-134">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="4c10f-135">Você também pode definir o limite de email para emails com falha ou atraso e obter um relatório semanal de problemas para contas prioritárias.</span><span class="sxs-lookup"><span data-stu-id="4c10f-135">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="4c10f-136">Selecione o usuário e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-136">Select the user and choose **Save**.</span></span>

<span data-ttu-id="4c10f-137">Você também pode adicionar contas de prioridade da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="4c10f-137">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="4c10f-138">Adicionar contas de prioridade da página Usuários ativos</span><span class="sxs-lookup"><span data-stu-id="4c10f-138">Add priority accounts from Active users page</span></span>

<span data-ttu-id="4c10f-139">Adicione contas de prioridade da página Usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="4c10f-139">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="4c10f-140">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="4c10f-140">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4c10f-141">Vá para **Usuários**  >  **Usuários ativos** e escolha **...** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="4c10f-141">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="4c10f-142">Selecione **Gerenciar contas de prioridade**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-142">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="4c10f-143">Selecione **Adicionar contas** e, na página Adicionar contas **de** prioridade, no campo de pesquisa, digite o nome da pessoa que você deseja adicionar à lista de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="4c10f-143">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="4c10f-144">Selecione o usuário e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-144">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="4c10f-145">Remover um usuário da lista de contas de prioridade</span><span class="sxs-lookup"><span data-stu-id="4c10f-145">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="4c10f-146">Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="4c10f-146">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="4c10f-147">Vá para **Configurar**  >  **Conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**</span><span class="sxs-lookup"><span data-stu-id="4c10f-147">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="4c10f-148">Na página **Monitorar a maioria das contas,** escolha Contas de **prioridade** em Gerenciar **esse recurso**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-148">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="4c10f-149">Na página **Contas de prioridade,** selecione o usuário ou os usuários que você deseja remover da lista e escolha, **Remover contas**.</span><span class="sxs-lookup"><span data-stu-id="4c10f-149">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c10f-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4c10f-150">Related topics</span></span>

[<span data-ttu-id="4c10f-151">Usando contas prioritárias no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c10f-151">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
