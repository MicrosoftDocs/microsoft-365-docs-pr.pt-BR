---
title: Configurar encaminhamento de email
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar o encaminhamento de emails para uma ou mais contas de email usando o office365.
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560787"
---
# <a name="configure-email-forwarding"></a><span data-ttu-id="82ea1-103">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="82ea1-103">Configure email forwarding</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="82ea1-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="82ea1-104">The admin center is changing.</span></span> <span data-ttu-id="82ea1-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="82ea1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
<span data-ttu-id="82ea1-106">Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de emails para a caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="82ea1-106">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="82ea1-107">O encaminhamento de email permite que você encaminhe mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="82ea1-107">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="82ea1-108">Você pode usar as políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="82ea1-108">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="82ea1-109">Para obter mais informações, consulte [controlar o encaminhamento de email externo automático no Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="82ea1-109">For more information, see [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

  
## <a name="configure-email-forwarding"></a><span data-ttu-id="82ea1-110">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="82ea1-110">Configure email forwarding</span></span>

 <span data-ttu-id="82ea1-111">Antes de configurar o encaminhamento de email, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="82ea1-111">Before you set up email forwarding, note the following:</span></span> 

- <span data-ttu-id="82ea1-112">Após configurar o encaminhamento de email **, somente os** emails enviados para a caixa  *de*  correio serão encaminhados.</span><span class="sxs-lookup"><span data-stu-id="82ea1-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span> 
    
- <span data-ttu-id="82ea1-113">O encaminhamento de email exige que a conta  *de*  tenha uma licença.</span><span class="sxs-lookup"><span data-stu-id="82ea1-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="82ea1-114">Se você estiver configurando o encaminhamento de emails porque o usuário deixou sua organização, outra opção é [converter a caixa de correio em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="82ea1-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="82ea1-115">Dessa forma, várias pessoas podem acessá-la.</span><span class="sxs-lookup"><span data-stu-id="82ea1-115">This way several people can access it.</span></span> <span data-ttu-id="82ea1-116">No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.</span><span class="sxs-lookup"><span data-stu-id="82ea1-116">However, a shared mailbox cannot exceed 50GB.</span></span> 
    
<span data-ttu-id="82ea1-117">Você deve ser um administrador do Exchange ou administrador global no Microsoft 365 para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="82ea1-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="82ea1-118">Para obter mais informações, consulte o tópico [sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="82ea1-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="82ea1-119">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="82ea1-119">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="82ea1-120">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="82ea1-120">Select the name of the user whose email you want to forward to open the properties page.</span></span> 
 
3. <span data-ttu-id="82ea1-121">Na guia **email** , selecione **gerenciar encaminhamento de email**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-121">On the **Mail** tab, select **Manage email forwarding**.</span></span> 
  
4. <span data-ttu-id="82ea1-122">Na página encaminhamento de email, selecione **encaminhar todos os emails enviados para esta caixa de correio**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="82ea1-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="82ea1-123">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="82ea1-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="82ea1-124">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-124">Select **Save changes**.</span></span>
    
    <span data-ttu-id="82ea1-125">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="82ea1-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="82ea1-126">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="82ea1-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="82ea1-127">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="82ea1-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="82ea1-128">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="82ea1-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="82ea1-129">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="82ea1-129">If you do, email forwarding will stop.</span></span> 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   <span data-ttu-id="82ea1-130">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="82ea1-130">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="82ea1-131">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="82ea1-131">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="82ea1-132">Expanda **configurações de email** e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="82ea1-133">Na página encaminhamento de email, **defina a opção Ativar, digite** o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="82ea1-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="82ea1-134">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="82ea1-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="82ea1-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-135">Select **Save**.</span></span>
    
    <span data-ttu-id="82ea1-136">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="82ea1-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="82ea1-137">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="82ea1-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="82ea1-138">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="82ea1-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="82ea1-139">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="82ea1-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="82ea1-140">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="82ea1-140">If you do, email forwarding will stop.</span></span>    

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="82ea1-141">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="82ea1-141">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 
    
2. <span data-ttu-id="82ea1-142">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="82ea1-142">Select the name of the user whose email you want to forward to open the properties page.</span></span> 

3. <span data-ttu-id="82ea1-143">Expanda **configurações de email** e, na seção **encaminhamento de email** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="82ea1-144">Na página encaminhamento de email, **defina a opção Ativar, digite** o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="82ea1-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="82ea1-145">Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="82ea1-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="82ea1-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82ea1-146">Select **Save**.</span></span>
    
    <span data-ttu-id="82ea1-147">**Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="82ea1-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="82ea1-148">Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="82ea1-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span> 
    
     <span data-ttu-id="82ea1-149">Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="82ea1-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>
    
5. <span data-ttu-id="82ea1-150">Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="82ea1-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="82ea1-151">Se fizer isso, o encaminhamento de emails será interrompido.</span><span class="sxs-lookup"><span data-stu-id="82ea1-151">If you do, email forwarding will stop.</span></span> 


::: moniker-end 
