---
title: Configurar encaminhamento de email
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar o encaminhamento de emails para uma ou mais contas de email usando o office365.
ms.openlocfilehash: 8cd86bcab4d73719e527f9942cd41a3174966c2d
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140448"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="abd26-103">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="abd26-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="abd26-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="abd26-104">The admin center is changing.</span></span> <span data-ttu-id="abd26-105">Se sua experiência não corresponder aos detalhes apresentados aqui, consulte [sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="abd26-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="abd26-106">Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de emails para a caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="abd26-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="abd26-107">O encaminhamento de email permite que você encaminhe mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="abd26-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="abd26-108">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="abd26-108">Configure email forwarding</span></span>

 <span data-ttu-id="abd26-109">Antes de configurar o encaminhamento de email, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="abd26-109">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="abd26-110">Após configurar o encaminhamento de email **, somente os** emails enviados para a caixa *de* correio serão fowarded.</span><span class="sxs-lookup"><span data-stu-id="abd26-110">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="abd26-111">O encaminhamento de email exige que a conta *de* tenha uma licença.</span><span class="sxs-lookup"><span data-stu-id="abd26-111">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="abd26-112">Se você estiver configurando o encaminhamento de emails porque o usuário deixou sua organização, outra opção é [converter a caixa de correio em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="abd26-112">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="abd26-113">Dessa forma, várias pessoas podem acessá-la.</span><span class="sxs-lookup"><span data-stu-id="abd26-113">This way several people can access it.</span></span> <span data-ttu-id="abd26-114">No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.</span><span class="sxs-lookup"><span data-stu-id="abd26-114">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="abd26-115">Você deve ser um administrador do Exchange ou administrador global no Microsoft 365 para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="abd26-115">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="abd26-116">Para obter mais informações, consulte o tópico [sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="abd26-116">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="abd26-117">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="abd26-117">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="abd26-118">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="abd26-118">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="abd26-119">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="abd26-119">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="abd26-120">Na guia **email** , selecione **gerenciar encaminhamento de email**.</span><span class="sxs-lookup"><span data-stu-id="abd26-120">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="abd26-121">Na página encaminhamento de email, selecione **encaminhar todos os emails enviados para esta caixa de correio**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="abd26-121">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="abd26-122">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="abd26-122">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="abd26-123">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="abd26-123">Select **Save changes**.</span></span>
    
    <span data-ttu-id="abd26-124">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="abd26-124">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="abd26-125">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="abd26-125">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="abd26-126">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="abd26-126">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="abd26-127">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="abd26-127">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="abd26-128">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="abd26-128">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="abd26-129">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="abd26-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="abd26-130">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="abd26-130">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="abd26-131">Expanda **configurações de email**e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="abd26-131">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="abd26-132">Na página encaminhamento de email, **defina a opção Ativar, digite**o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="abd26-132">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="abd26-133">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="abd26-133">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="abd26-134">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="abd26-134">Select **Save**.</span></span>
    
    <span data-ttu-id="abd26-135">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="abd26-135">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="abd26-136">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="abd26-136">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="abd26-137">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="abd26-137">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="abd26-138">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="abd26-138">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="abd26-139">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="abd26-139">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="abd26-140">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="abd26-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="abd26-141">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="abd26-141">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="abd26-142">Expanda **configurações de email**e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="abd26-142">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="abd26-143">Na página encaminhamento de email, **defina a opção Ativar, digite**o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="abd26-143">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="abd26-144">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="abd26-144">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="abd26-145">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="abd26-145">Select **Save**.</span></span>
    
    <span data-ttu-id="abd26-146">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="abd26-146">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="abd26-147">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="abd26-147">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="abd26-148">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="abd26-148">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="abd26-149">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="abd26-149">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="abd26-150">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="abd26-150">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
