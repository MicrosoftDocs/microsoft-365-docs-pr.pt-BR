---
title: Gerenciar e monitorar contas de prioridade
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
description: Monitorar mensagens de email com e atrasadas enviadas para ou de contas com alto impacto nos negócios.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477608"
---
# <a name="manage-and-monitor-priority-accounts"></a><span data-ttu-id="1ba85-103">Gerenciar e monitorar contas de prioridade</span><span class="sxs-lookup"><span data-stu-id="1ba85-103">Manage and monitor priority accounts</span></span>

<span data-ttu-id="1ba85-104">Em todas as organizações da Microsoft 365, há pessoas essenciais, como executivos, líderes, gerentes ou outros usuários que têm acesso a informações confidenciais, proprietárias ou de alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-104">In every Microsoft 365 organization, there are people that are essential, like executives, leaders, managers, or other users who have access to sensitive, proprietary, or high priority information.</span></span>

<span data-ttu-id="1ba85-105">Para ajudar sua organização a proteger essas contas, agora você pode designar usuários específicos como contas de prioridade e aproveitar recursos específicos de aplicativos que oferecem proteção extra.</span><span class="sxs-lookup"><span data-stu-id="1ba85-105">To help your organization protect these accounts, you can now designate specific users as priority accounts and leverage app-specific features that provide them with extra protection.</span></span> <span data-ttu-id="1ba85-106">No futuro, mais aplicativos e recursos oferecerão suporte a contas de prioridade e, para começar, anunciamos dois recursos: **prioridade de proteção de conta** e **monitoramento de fluxo de emails Premium**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-106">In the future, more apps and features will support priority accounts, and to start with, we’ve announced two capabilities: **priority account protection** and **premium mail flow monitoring**.</span></span>

- <span data-ttu-id="1ba85-107">**Proteção de conta de prioridade** -o Microsoft defender para Office 365 (anteriormente chamado de proteção avançada contra ameaças do Office 365) oferece suporte a contas de prioridade como marcas que podem ser usadas em filtros em alertas, relatórios e investigações.</span><span class="sxs-lookup"><span data-stu-id="1ba85-107">**Priority account protection** - Microsoft Defender for Office 365 (formerly Office 365 Advanced Threat Protection) supports priority accounts as tags that can be used in filters in alerts, reports, and investigations.</span></span> <span data-ttu-id="1ba85-108">Para obter mais informações, confira [marcas de usuário no Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="1ba85-108">For more information, check out [User tags in Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).</span></span>
- <span data-ttu-id="1ba85-109">**Monitoramento de fluxo de mensagens Premium** -o fluxo de emails íntegros pode ser fundamental para o sucesso dos negócios, e atrasos de entregas ou falhas podem ter um impacto negativo sobre a empresa.</span><span class="sxs-lookup"><span data-stu-id="1ba85-109">**Premium Mail Flow Monitoring** - Healthy mail flow can be critical to business success, and delivery delays or failures can have a negative impact on the business.</span></span> <span data-ttu-id="1ba85-110">Você pode escolher um limite para emails com falha ou atraso, receber alertas quando esse limite for excedido e exibir um relatório de problemas de email para contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-110">You can choose a threshold for failed or delayed emails, receive alerts when that threshold is exceeded, and view a report of email issues for priority accounts.</span></span> <span data-ttu-id="1ba85-111">Para obter mais informações, confira [o relatório de problemas de email para contas de prioridade no Eat moderno](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span><span class="sxs-lookup"><span data-stu-id="1ba85-111">For more information, check out [Email issues for priority accounts report in the modern EAC](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1ba85-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1ba85-112">Before you begin</span></span>

<span data-ttu-id="1ba85-113">O recurso de **proteção de conta de prioridade** descrito neste tópico está disponível somente para as organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="1ba85-113">The **Priority account protection** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1ba85-114">Microsoft defender para Office 365 plano 2, incluindo aqueles com o Office 365 E3, o Office 365 e5, o Microsoft 365 E5 ou o Microsoft 365 E5 Security.</span><span class="sxs-lookup"><span data-stu-id="1ba85-114">Microsoft Defender for Office 365 Plan 2, including those with Office 365 E3, Office 365 E5, Microsoft 365 E5, or Microsoft 365 E5 Security.</span></span>

<span data-ttu-id="1ba85-115">O recurso de **monitoramento de fluxo de email Premium** descrito neste tópico está disponível somente para as organizações que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="1ba85-115">The **Premium Mail Flow Monitoring** feature that's described in this topic is available only to organizations that meet the following requirements:</span></span>

- <span data-ttu-id="1ba85-116">Sua organização precisa ter uma contagem de licenças de pelo menos 10.000, de um ou de uma combinação dos seguintes produtos: Office 365 E3, Microsoft 365 E3, Office 365 e5, Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="1ba85-116">Your organization needs to have a license count of at least 10,000, from either one of, or a combination of the following products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> <span data-ttu-id="1ba85-117">Por exemplo, sua organização pode ter 3000 Office 365 E3 licenças e 8500 Microsoft 365 e5, para um total de licenças de 11.500 dos produtos qualificados.</span><span class="sxs-lookup"><span data-stu-id="1ba85-117">For example, your organization can have 3000 Office 365 E3 licenses and 8500 Microsoft 365 E5, for a total of 11,500 licenses from the qualifying products.</span></span>
- <span data-ttu-id="1ba85-118">Sua organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ba85-118">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

> [!NOTE]
> <span data-ttu-id="1ba85-119">Você pode monitorar até 250 contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-119">You can monitor up to 250 priority accounts.</span></span>

### <a name="add-priority-accounts-from-the-setup-page"></a><span data-ttu-id="1ba85-120">Adicionar contas de prioridade da página de configuração</span><span class="sxs-lookup"><span data-stu-id="1ba85-120">Add priority accounts from the Setup page</span></span>

<span data-ttu-id="1ba85-121">Adicione contas de prioridade da **página de configuração**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-121">Add priority accounts from the **Setup page**.</span></span>

1. <span data-ttu-id="1ba85-122">Vá para o centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="1ba85-122">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1ba85-123">Vá para **Configurar**  >  **conhecimento organizacional** e escolha **Exibir** em **monitorar suas contas mais importantes**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-123">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1ba85-124">Selecione **introdução** ou **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-124">Select **Get Started** or **Manage**.</span></span>

4. <span data-ttu-id="1ba85-125">Na página **Adicionar contas de prioridade** , no campo de pesquisa, digite o nome ou o endereço de email da pessoa que você deseja adicionar à lista contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-125">On the **Add Priority accounts** page, in the search field, type the name or email address of the person you want to add to the priority accounts list.</span></span> <span data-ttu-id="1ba85-126">Você também pode definir seu limite de email para emails com falha ou atraso e obter um relatório semanal de problemas de contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-126">You can also set your email threshold for failed or delayed emails and get a weekly report of issues for priority accounts.</span></span>

5. <span data-ttu-id="1ba85-127">Selecione o usuário e escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-127">Select the user and choose **Save**.</span></span>

<span data-ttu-id="1ba85-128">Você também pode adicionar contas de prioridade da página usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="1ba85-128">You can also add priority accounts from the Active users page.</span></span>

### <a name="add-priority-accounts-from-active-users-page"></a><span data-ttu-id="1ba85-129">Adicionar contas de prioridade da página de usuários ativos</span><span class="sxs-lookup"><span data-stu-id="1ba85-129">Add priority accounts from Active users page</span></span>

<span data-ttu-id="1ba85-130">Adicionar contas de prioridade da página usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="1ba85-130">Add priority accounts from the Active users page.</span></span>

1. <span data-ttu-id="1ba85-131">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="1ba85-131">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1ba85-132">Vá para **Users** usuários  >  **ativos** do usuário e escolha **..** . na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="1ba85-132">Go to **Users** > **Active users** and choose **...** at the top of the page.</span></span> <span data-ttu-id="1ba85-133">Selecione **gerenciar contas de prioridade**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-133">Select **Manage priority accounts**.</span></span>

3. <span data-ttu-id="1ba85-134">Selecione **Adicionar contas** e, na página **Adicionar contas de prioridade** , no campo de pesquisa, digite o nome da pessoa que você deseja adicionar à lista contas de prioridade.</span><span class="sxs-lookup"><span data-stu-id="1ba85-134">Select **Add accounts**, and on the **Add Priority accounts** page, in the search field, type the name of the person you want to add to the priority accounts list.</span></span>

4. <span data-ttu-id="1ba85-135">Selecione o usuário e escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-135">Select the user and choose **Save**.</span></span>

## <a name="remove-a-user-from-the-priority-accounts-list"></a><span data-ttu-id="1ba85-136">Remover um usuário da lista contas de prioridade</span><span class="sxs-lookup"><span data-stu-id="1ba85-136">Remove a user from the priority accounts list</span></span>

1. <span data-ttu-id="1ba85-137">Vá para o centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="1ba85-137">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="1ba85-138">Vá para **Configurar**  >  **conhecimento organizacional** e escolha **Exibir** em **monitorar suas contas mais importantes**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-138">Go to **Setup** > **Organizational knowledge**, and choose **View** under **Monitor your most important accounts**.</span></span>

3. <span data-ttu-id="1ba85-139">Na página **monitorar a maioria das contas** , escolha **contas de prioridade** em **gerenciar este recurso**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-139">On the **Monitor your most accounts** page, choose **Priority accounts** under **Manage this feature**.</span></span>

4. <span data-ttu-id="1ba85-140">Na página **contas de prioridade** , selecione o usuário ou os usuários que você deseja remover da lista e escolha, **remover contas**.</span><span class="sxs-lookup"><span data-stu-id="1ba85-140">On the **Priority accounts** page, select the user or users you want to remove from the list and choose, **Remove accounts**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1ba85-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ba85-141">Related topics</span></span>

[<span data-ttu-id="1ba85-142">Usando contas de prioridade no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1ba85-142">Using Priority Accounts in Microsoft 365</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)