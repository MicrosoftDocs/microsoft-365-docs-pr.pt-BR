---
title: Excluir um usuário da sua organização
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
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Saiba como excluir uma conta de usuário. Decida o que fazer com o email do usuário, o conteúdo do OneDrive e se deseja manter a licença do produto ou parar de pagar por ela.
ms.openlocfilehash: f54d0d4a39ff116b4bee6aceb10233344835a455
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237142"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="cde9a-104">Excluir um usuário da sua organização</span><span class="sxs-lookup"><span data-stu-id="cde9a-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="cde9a-105">**Procurando como excluir sua *própria* conta de usuário do Office 365 que você usa no trabalho ou na escola? Entre em contato com o suporte técnico em seu trabalho ou universidade para executar estas etapas.**</span><span class="sxs-lookup"><span data-stu-id="cde9a-105">**Looking for how to delete your *own* Office 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="cde9a-106">O que você precisa saber sobre a exclusão de usuários</span><span class="sxs-lookup"><span data-stu-id="cde9a-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="cde9a-107">Apenas pessoas com permissões de [administração global do Office 365](about-admin-roles.md) ou de gerenciamento de usuários para empresas ou instituições de ensino podem excluir contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="cde9a-107">Only people who have [Office 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="cde9a-108">Você tem até 30 dias para [restaurar](restore-user.md) a conta, antes que os dados do usuário sejam excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="cde9a-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="cde9a-p102">Se você quiser manter os dados do usuário do OneDrive, mova-os para um local diferente. Você ainda pode fazer isso até 30 dias após a exclusão da conta. Veja [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md). Não é necessário mover os arquivos do SharePoint; você ainda terá acesso a eles.</span><span class="sxs-lookup"><span data-stu-id="cde9a-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="cde9a-p103">Se você deseja manter o email do usuário, **ANTES** de excluir a conta, mova o email para outro local. Se você excluiu a conta há menos de 30 dias, restaure-a, mova os dados de email e exclua-a. Confira [Obter acesso e realizar backup dos dados de um usuário anterior](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="cde9a-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="cde9a-116">Se você tiver uma assinatura corporativa como o Office 365 Enterprise E3, poderá preservar os dados da caixa de correio de uma conta de usuário do Office 365 excluída, transformando-o em uma *caixa de correio inativa*.</span><span class="sxs-lookup"><span data-stu-id="cde9a-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted Office 365 user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="cde9a-117">Saiba mais em [Gerenciar as caixas de correio inativas no Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="cde9a-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="cde9a-118">Administração Global: excluir um usuário, parar de pagar por sua licença e escolher o que fazer com seus emails e conteúdo do OneDrive</span><span class="sxs-lookup"><span data-stu-id="cde9a-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="cde9a-119">Se você for um administrador global, quando excluir um usuário, também poderá conceder a outro usuário acesso ao seu email e escolher o que fazer com o conteúdo do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cde9a-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="cde9a-120">Coisas a considerar...</span><span class="sxs-lookup"><span data-stu-id="cde9a-120">Things to consider...</span></span>

<span data-ttu-id="cde9a-121">Antes de começar, pense no que você deseja fazer com o conteúdo do usuário e do OneDrive, e se você deseja manter a licença ou parar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="cde9a-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cde9a-122">Licenças de produto</span><span class="sxs-lookup"><span data-stu-id="cde9a-122">Product licenses</span></span>  <br/> |<span data-ttu-id="cde9a-123">Você pode remover a licença do usuário e removê-la das assinaturas para parar de pagar pela licença.</span><span class="sxs-lookup"><span data-stu-id="cde9a-123">You can remove the license from the user and remove it from your subscriptions to stop paying for that license.</span></span> <span data-ttu-id="cde9a-124">Se você selecionar essa opção, a licença será removida automaticamente de suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="cde9a-124">If you select this option, the license will be removed automatically from your subscriptions.</span></span>  <br/><br/> <span data-ttu-id="cde9a-125">**Você não pode remover a licença** se a comprou por meio de um parceiro ou de um licenciamento por volume.</span><span class="sxs-lookup"><span data-stu-id="cde9a-125">**You can't remove the license** if you bought it through a Partner or volume licensing.</span></span> <span data-ttu-id="cde9a-126">Se você estiver pagando um plano anual ou se estiver no meio de um ciclo de cobrança, não será possível remover a licença da sua assinatura até que o compromisso seja concluído.</span><span class="sxs-lookup"><span data-stu-id="cde9a-126">If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.</span></span>  <br/> |
|<span data-ttu-id="cde9a-127">Conteúdo do OneDrive</span><span class="sxs-lookup"><span data-stu-id="cde9a-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="cde9a-128">Se o usuário salvou seus arquivos no OneDrive, você pode dar a outro usuário acesso a esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="cde9a-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="cde9a-129">Você precisará mover os arquivos que deseja manter dentro do período de retenção definido para arquivos do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cde9a-129">You'll need to move the files you want to keep within the retention period that is set for OneDrive files.</span></span> <span data-ttu-id="cde9a-130">**Por padrão, o período de retenção é de 30 dias.**</span><span class="sxs-lookup"><span data-stu-id="cde9a-130">**By default, the retention period is 30 days.**</span></span> <span data-ttu-id="cde9a-131">Se você não mover os arquivos dentro do período de retenção após excluir o usuário, o conteúdo do OneDrive será excluído permanentemente.</span><span class="sxs-lookup"><span data-stu-id="cde9a-131">If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted.</span></span> <span data-ttu-id="cde9a-132">Para aumentar o número de dias que você retém arquivos do OneDrive para contas excluídas, consulte [set the onedrive Retention for Deleted Users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span><span class="sxs-lookup"><span data-stu-id="cde9a-132">To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).</span></span>  <br/><br/> <span data-ttu-id="cde9a-133">**Importante!**</span><span class="sxs-lookup"><span data-stu-id="cde9a-133">**Important!**</span></span> <span data-ttu-id="cde9a-134">Se o usuário excluído utilizou um computador pessoal para baixar arquivos do SharePoint e do OneDrive, não há como apagar os arquivos armazenados no computador.</span><span class="sxs-lookup"><span data-stu-id="cde9a-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="cde9a-135">Eles continuarão a ter acesso a todos os arquivos que foram sincronizados a partir do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="cde9a-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="cde9a-136">Email</span><span class="sxs-lookup"><span data-stu-id="cde9a-136">Email</span></span>  <br/> | <span data-ttu-id="cde9a-137">Conceder a outro usuário acesso ao email do usuário excluído converterá a caixa de correio do usuário excluído em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="cde9a-137">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="cde9a-138">O novo proprietário da caixa de correio pode acessar a caixa de correio e monitorar novos emails.</span><span class="sxs-lookup"><span data-stu-id="cde9a-138">The new mailbox owner can then access the mailbox and monitor for new email.</span></span> <span data-ttu-id="cde9a-139">Você também terá as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="cde9a-139">You'll also have the following options:</span></span>  <br/>  <br/><span data-ttu-id="cde9a-140">Alterar o nome para exibição-recomendamos alterar o nome de exibição para que seja fácil identificar a caixa de correio compartilhada na lista de usuários ativos.</span><span class="sxs-lookup"><span data-stu-id="cde9a-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="cde9a-141">Ativar respostas automáticas – já escrevemos uma resposta de educador automática para você.</span><span class="sxs-lookup"><span data-stu-id="cde9a-141">Turn on automatic replies - We've already written a polite automatic reply for you.</span></span> <span data-ttu-id="cde9a-142">Você pode enviar respostas automáticas diferentes para pessoas dentro da sua organização e pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="cde9a-142">You can send a different automatic replies to people within your organization and people from outside your organization.</span></span>  <br/> <br/> <span data-ttu-id="cde9a-143">Limpar aliases-os aliases são endereços de email adicionais para os usuários.</span><span class="sxs-lookup"><span data-stu-id="cde9a-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="cde9a-144">Algumas organizações não as usam, portanto, se você não tiver nenhum, não será necessário fazer nada mais aqui.</span><span class="sxs-lookup"><span data-stu-id="cde9a-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="cde9a-145">Se o usuário tiver aliases, recomendamos removê-los para que você possa reutilizar esses endereços de email.</span><span class="sxs-lookup"><span data-stu-id="cde9a-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="cde9a-146">Caso contrário, você não poderá usar novamente esses endereços de email até que o período de retenção de caixas de correio excluídas tenha passado.</span><span class="sxs-lookup"><span data-stu-id="cde9a-146">Otherwise, you can’t re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="cde9a-147">Por padrão, uma caixa de correio excluída é recuperável por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="cde9a-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="cde9a-148">Para obter mais informações, consulte [excluir ou restaurar caixas de correio do usuário no Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="cde9a-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="cde9a-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="cde9a-149">Active Directory</span></span>  <br/> |<span data-ttu-id="cde9a-150">Se a sua empresa usa o **Active Directory** sincronizado com o Azure AD, é necessário excluir a conta de usuário do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cde9a-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="cde9a-151">Não é possível fazê-lo no Office 365.</span><span class="sxs-lookup"><span data-stu-id="cde9a-151">You can't do it through Office 365.</span></span> <span data-ttu-id="cde9a-152">Para obter instruções, consulte [excluir uma conta de usuário](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="cde9a-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="cde9a-153">Introdução</span><span class="sxs-lookup"><span data-stu-id="cde9a-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="cde9a-154">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="cde9a-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="cde9a-155">Como a experiência orientada percorre as etapas para excluir um usuário, veja aqui como começar.</span><span class="sxs-lookup"><span data-stu-id="cde9a-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="cde9a-156">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cde9a-157">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cde9a-158">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="cde9a-159">Selecione o usuário que você deseja excluir e, em seguida, selecione **excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="cde9a-160">Administração de gerenciamento de usuários: excluir um ou mais usuários do Office 365</span><span class="sxs-lookup"><span data-stu-id="cde9a-160">User management admin: Delete one or more users from Office 365</span></span>


 <span data-ttu-id="cde9a-p113">**IMPORTANTE**: Não exclua a conta de um usuário se você tiver [convertido a conta em uma caixa de correio compartilhada](../email/convert-user-mailbox-to-shared-mailbox.md) ou se tiver configurado um encaminhamento de email na conta. Essas funções precisam da conta. Se as tiver convertido em uma caixa de correio compartilhada, você poderá [Parar de pagar pela licença](#stop-paying-for-the-license) e deixar de pagar por ela. Se você configurar o encaminhamento de email, não poderá remover a licença. Isso interromperá o encaminhamento de email e desativará a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cde9a-p113">**IMPORTANT**: Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions need the account there. If you've converted it to a shared mailbox, you can [Stop paying for the license](#stop-paying-for-the-license) from it so you aren't paying for it. If you set up email forwarding, you cannot remove the license. Doing so will stop the email forwarding and inactivate the mailbox.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="cde9a-166">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="cde9a-167">Selecione os nomes dos usuários que você deseja excluir, selecione **mais opções** (**...**) e, em seguida, escolha **excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-167">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="cde9a-168">Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-168">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="cde9a-169">Consulte o procedimento a seguir para interromper o pagamento da licença.</span><span class="sxs-lookup"><span data-stu-id="cde9a-169">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="cde9a-170">Ou você pode atribuir a licença a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="cde9a-170">Or, you can assign the license to another user.</span></span> <span data-ttu-id="cde9a-171">Ele não será atribuído a alguém automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cde9a-171">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cde9a-172">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-172">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cde9a-173">Selecione os nomes dos usuários que você deseja excluir e, no painel **ações em massa** , escolha **excluir usuários**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-173">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="cde9a-174">Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-174">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="cde9a-175">Consulte o procedimento a seguir para interromper o pagamento da licença.</span><span class="sxs-lookup"><span data-stu-id="cde9a-175">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="cde9a-176">Ou você pode atribuir a licença a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="cde9a-176">Or, you can assign the license to another user.</span></span> <span data-ttu-id="cde9a-177">Ele não será atribuído a alguém automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cde9a-177">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cde9a-178">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-178">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="cde9a-179">Selecione os nomes dos usuários que você deseja excluir e, no painel **ações em massa** , escolha **excluir usuários**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-179">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="cde9a-180">Embora você tenha excluído a conta do usuário, **ainda está pagando pela licença**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-180">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="cde9a-181">Consulte o procedimento a seguir para interromper o pagamento da licença.</span><span class="sxs-lookup"><span data-stu-id="cde9a-181">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="cde9a-182">Ou você pode atribuir a licença a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="cde9a-182">Or, you can assign the license to another user.</span></span> <span data-ttu-id="cde9a-183">Ele não será atribuído a alguém automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cde9a-183">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="cde9a-184">Parar de pagar pela licença</span><span class="sxs-lookup"><span data-stu-id="cde9a-184">Stop paying for the license</span></span>

<span data-ttu-id="cde9a-185">Reduzir o número de licenças é uma etapa separada que só pode ser realizada pelo administrador global ou administrador de cobrança.</span><span class="sxs-lookup"><span data-stu-id="cde9a-185">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="cde9a-186">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produtos e serviços</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-186">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="cde9a-187">Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-187">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="cde9a-188">Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-188">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="cde9a-189">Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!</span><span class="sxs-lookup"><span data-stu-id="cde9a-189">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="cde9a-190">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-190">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="cde9a-191">Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-191">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="cde9a-192">Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-192">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="cde9a-193">Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!</span><span class="sxs-lookup"><span data-stu-id="cde9a-193">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="cde9a-194">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.</span><span class="sxs-lookup"><span data-stu-id="cde9a-194">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="cde9a-195">Se você não vir essa opção, você não é um administrador global ou de cobrança e não pode executar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-195">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="cde9a-196">Selecione a assinatura (se você tiver mais de uma) e, em seguida, selecione **Adicionar/remover licenças** para excluir a licença para não pagar por ela até contratar outra pessoa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-196">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="cde9a-197">Mais tarde, quando você passar pelas etapas para adicionar outra pessoa à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!</span><span class="sxs-lookup"><span data-stu-id="cde9a-197">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="cde9a-198">Excluir muitos usuários ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="cde9a-198">Delete many users at the same time</span></span>

<span data-ttu-id="cde9a-199">Consulte o cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cde9a-199">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="cde9a-200">Corrigir problemas na exclusão de um usuário</span><span class="sxs-lookup"><span data-stu-id="cde9a-200">Fix issues with deleting a user</span></span>

<span data-ttu-id="cde9a-201">Aqui estão os problemas mais comuns que as pessoas encontram ao excluir um usuário:</span><span class="sxs-lookup"><span data-stu-id="cde9a-201">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="cde9a-202">**Você recebe uma mensagem de erro ao longo das linhas de "o usuário não pode ser excluído. Tente novamente mais tarde. "**</span><span class="sxs-lookup"><span data-stu-id="cde9a-202">**You get an error message along the lines of "User cannot be deleted. Please try again later."**</span></span> <span data-ttu-id="cde9a-203">Verifique se a conta do encaminhamento de emails foi configurada ou se foi convertida em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="cde9a-203">Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox.</span></span> <span data-ttu-id="cde9a-204">Ambos causarão esse erro.</span><span class="sxs-lookup"><span data-stu-id="cde9a-204">Both of these will cause that error.</span></span> <span data-ttu-id="cde9a-205">Não exclua a conta se tiver encaminhamento de email ou se ele tiver sido convertido em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="cde9a-205">Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="cde9a-206">**Você não tem as permissões adequadas para excluir um usuário**.</span><span class="sxs-lookup"><span data-stu-id="cde9a-206">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="cde9a-207">Somente as pessoas que são [administradores globais ou administradores de gerenciamento de usuários do Office 365](about-admin-roles.md) podem excluir usuários.</span><span class="sxs-lookup"><span data-stu-id="cde9a-207">Only people who are [Office 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="cde9a-208">Normalmente, esse é o suporte técnico disponível em sua escola ou empresa.</span><span class="sxs-lookup"><span data-stu-id="cde9a-208">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="cde9a-p122">**Você exclui o usuário, mas o nome dele continua aparecendo no catálogo de endereços global**. Isso acontece quando uma empresa está usando o Active Directory. Você precisa excluir a conta de usuário do Active Directory. Confira as instruções neste artigo do TechNet: [Excluir uma conta de usuário.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="cde9a-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="cde9a-213">**Você deseja excluir o Office 365 do computador? Vá para a opção [Cancelar sua assinatura](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="cde9a-213">**Do you want to delete Office 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="cde9a-214">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="cde9a-214">Related articles</span></span>

[<span data-ttu-id="cde9a-215">Restaurar um usuário</span><span class="sxs-lookup"><span data-stu-id="cde9a-215">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="cde9a-216">Excluir permanentemente uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="cde9a-216">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="cde9a-217">Remover um ex-funcionário do Office 365</span><span class="sxs-lookup"><span data-stu-id="cde9a-217">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="cde9a-218">Adicionar um novo funcionário ao Office 365</span><span class="sxs-lookup"><span data-stu-id="cde9a-218">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="cde9a-219">[Excluir uma conta de usuário](https://go.microsoft.com/fwlink/p/?linkid=841808): Use estas instruções se a sua empresa usa o **Active Directory** que está sincronizando com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cde9a-219">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="cde9a-220">Não é possível fazê-lo no Office 365.</span><span class="sxs-lookup"><span data-stu-id="cde9a-220">You can't do it through Office 365.</span></span>