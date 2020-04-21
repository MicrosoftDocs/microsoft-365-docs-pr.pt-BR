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
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628910"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="47873-103">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="47873-103">Configure email forwarding</span></span>
  
<span data-ttu-id="47873-104">Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de emails para a caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="47873-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="47873-105">O encaminhamento de email permite que você encaminhe mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="47873-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="47873-106">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="47873-106">Configure email forwarding</span></span>

 <span data-ttu-id="47873-107">Antes de configurar o encaminhamento de email, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="47873-107">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="47873-108">Após configurar o encaminhamento de email **, somente os** emails enviados para a caixa *de* correio serão fowarded.</span><span class="sxs-lookup"><span data-stu-id="47873-108">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be fowarded.</span></span> 
    
- <span data-ttu-id="47873-109">O encaminhamento de email exige que a conta *de* tenha uma licença.</span><span class="sxs-lookup"><span data-stu-id="47873-109">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="47873-110">Se você estiver configurando o encaminhamento de emails porque o usuário deixou sua organização, outra opção é [converter a caixa de correio em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="47873-110">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="47873-111">Dessa forma, várias pessoas podem acessá-la.</span><span class="sxs-lookup"><span data-stu-id="47873-111">This way several people can access it.</span></span> <span data-ttu-id="47873-112">No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.</span><span class="sxs-lookup"><span data-stu-id="47873-112">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="47873-113">Você deve ser um administrador do Exchange ou administrador global no Microsoft 365 para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="47873-113">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="47873-114">Para obter mais informações, consulte o tópico [sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="47873-114">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="47873-115">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="47873-115">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="47873-116">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="47873-116">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="47873-117">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="47873-117">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="47873-118">Na guia **email** , selecione **gerenciar encaminhamento de email**.</span><span class="sxs-lookup"><span data-stu-id="47873-118">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="47873-119">Na página encaminhamento de email, selecione **encaminhar todos os emails enviados para esta caixa de correio**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="47873-119">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="47873-120">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="47873-120">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="47873-121">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="47873-121">Select **Save changes**.</span></span>
    
    <span data-ttu-id="47873-122">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="47873-122">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="47873-123">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="47873-123">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="47873-124">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="47873-124">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="47873-125">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="47873-125">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="47873-126">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="47873-126">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="47873-127">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="47873-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="47873-128">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="47873-128">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="47873-129">Expanda **configurações de email**e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47873-129">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="47873-130">Na página encaminhamento de email, **defina a opção Ativar, digite**o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="47873-130">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="47873-131">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="47873-131">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="47873-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="47873-132">Select **Save**.</span></span>
    
    <span data-ttu-id="47873-133">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="47873-133">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="47873-134">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="47873-134">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="47873-135">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="47873-135">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="47873-136">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="47873-136">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="47873-137">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="47873-137">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="47873-138">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="47873-138">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="47873-139">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="47873-139">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="47873-140">Expanda **configurações de email**e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="47873-140">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="47873-141">Na página encaminhamento de email, **defina a opção Ativar, digite**o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="47873-141">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="47873-142">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="47873-142">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="47873-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="47873-143">Select **Save**.</span></span>
    
    <span data-ttu-id="47873-144">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="47873-144">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="47873-145">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="47873-145">To learn more, see [Use rules to automatically forward messages](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="47873-146">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="47873-146">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="47873-147">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="47873-147">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="47873-148">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="47873-148">If you do, email forwarding will stop.</span></span> 

::: moniker-end 
