---
title: Adicionar usuários individualmente ou em massa
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Saiba como adicionar usuários ao Microsoft 365, um de cada vez ou vários usuários ao mesmo tempo a partir de um arquivo CSV.
ms.openlocfilehash: 78e5cf2c3c0148a91d48355881c3aec331213fd5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43618855"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="27672-103">Adicionar usuários individualmente ou em massa</span><span class="sxs-lookup"><span data-stu-id="27672-103">Add users individually or in bulk</span></span>

<span data-ttu-id="27672-104">As pessoas da sua equipe precisam de uma conta de usuário antes de entrarem e acessar [o Microsoft 365 for Business](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="27672-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="27672-105">A maneira mais fácil de adicionar contas de usuário é adicionar uma de cada vez no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27672-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="27672-106">Após executar esta etapa, seus usuários terão licenças do Microsoft 365, credenciais de entrada e caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27672-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="27672-107">Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.</span><span class="sxs-lookup"><span data-stu-id="27672-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="27672-108">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="27672-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="27672-109">Vá para **Users** > **usuários ativos**do usuários e selecione **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="27672-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="27672-110">No painel **Configurar o básico** , preencha as seguintes informações e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27672-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="27672-111">**Nome** Preencha o primeiro, o último, o nome para exibição e o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="27672-112">**Domínio** Por exemplo, se o nome de usuário do usuário for Jakob, e seu domínio for contoso.com, ele entrará na digitação de jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27672-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="27672-113">**Configurações de senha** Escolha a senha gerada automaticamente ou crie sua própria senha forte para o usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="27672-114">Os usuários devem alterar as respectivas senhas após 90 dias.</span><span class="sxs-lookup"><span data-stu-id="27672-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="27672-115">Ou você pode optar por **exigir que esse usuário altere a senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="27672-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="27672-116">Escolha se você deseja enviar a senha no email quando o usuário tiver sido adicionado.</span><span class="sxs-lookup"><span data-stu-id="27672-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="27672-117">No painel **atribuir licenças de produtos** , selecione o local e a licença apropriada para o usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="27672-118">Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="27672-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="27672-119">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27672-119">Select **Next**.</span></span>

5. <span data-ttu-id="27672-120">Na página **configurações opcionais** , expanda **funções** se quiser tornar esse usuário um administrador e expanda **informações de perfil** se quiser adicionar mais informações sobre o usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="27672-121">Selecione **Avançar**, revise as configurações do novo usuário, faça as alterações desejadas e selecione **concluir adição**.</span><span class="sxs-lookup"><span data-stu-id="27672-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="27672-122">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="27672-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="27672-123">Vá para **Users** > **usuários ativos**do usuários e selecione **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="27672-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="27672-124">No painel **novo usuário** , preencha as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="27672-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="27672-125">Selecione **Adicionar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="27672-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="27672-126">**Nome** Preencha o nome, o sobrenome, o nome para exibição e o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="27672-127">**Domínio** Por exemplo, se o nome de usuário do usuário for Jakob, e seu domínio for contoso.com, ele entrará na digitação de jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27672-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="27672-128">**Informações de contato** Expanda para preencher um número de telefone celular, endereço e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="27672-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="27672-129">**Senha** Use a senha gerada automaticamente ou expanda para especificar uma senha forte para o usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="27672-p105">Os usuários devem alterar as respectivas senhas após 90 dias. Além disso, você pode optar por **Permitir que esse usuário altere a senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="27672-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="27672-132">**Funções** Expanda, caso precise tornar esse usuário um administrador.</span><span class="sxs-lookup"><span data-stu-id="27672-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="27672-p106">**Licenças de produto** Expanda esta seção e escolha a licença apropriada. Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="27672-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="27672-135">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="27672-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="27672-136">Vá para **Users** > **usuários ativos**do usuários e selecione **Adicionar um usuário**.</span><span class="sxs-lookup"><span data-stu-id="27672-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="27672-137">No painel **novo usuário** , preencha as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="27672-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="27672-138">Selecione **Adicionar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="27672-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="27672-139">**Nome** Preencha o nome, o sobrenome, o nome para exibição e o nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="27672-140">**Domínio** Por exemplo, se o nome de usuário do usuário for Jakob, e seu domínio for contoso.com, ele entrará na digitação de jakob@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="27672-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="27672-141">**Informações de contato** Expanda para preencher um número de telefone celular, endereço e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="27672-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="27672-142">**Senha** Use a senha gerada automaticamente ou expanda para especificar uma senha forte para o usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="27672-p108">Os usuários devem alterar as respectivas senhas após 90 dias. Além disso, você pode optar por **Permitir que esse usuário altere a senha quando entrar pela primeira vez**.</span><span class="sxs-lookup"><span data-stu-id="27672-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="27672-145">**Funções** Expanda, caso precise tornar esse usuário um administrador.</span><span class="sxs-lookup"><span data-stu-id="27672-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="27672-p109">**Licenças de produto** Expanda esta seção e escolha a licença apropriada. Caso não haja licenças disponíveis, você pode comprar mais licenças e adicionar usuários.</span><span class="sxs-lookup"><span data-stu-id="27672-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="27672-148">Depois de adicionar usuários, você receberá uma notificação por email da equipe do Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="27672-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="27672-149">O email conterá a ID de usuário e a senha da pessoa para que eles possam entrar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27672-149">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="27672-150">Você precisa informar ao novo usuário sobre suas informações de entrada do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27672-150">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="27672-151">Use seu processo normal para comunicar as novas senhas.</span><span class="sxs-lookup"><span data-stu-id="27672-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="27672-152">Se você criar usuários migrando caixas de correio, será necessário ativar as contas de usuário atribuindo licenças.</span><span class="sxs-lookup"><span data-stu-id="27672-152">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="27672-153">Se você não atribuir uma licença a um usuário, a caixa de correio será desabilitada após um período de carência de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="27672-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="27672-154">Confira como [atribuir licenças aos usuários](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) usando o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="27672-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="27672-155">Vídeo: Adicionar e gerenciar usuários no centro de administração</span><span class="sxs-lookup"><span data-stu-id="27672-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="27672-156">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="27672-156">Next steps</span></span>

<span data-ttu-id="27672-157">Compartilhe o [Guia de início rápido do funcionário](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) com seus novos usuários para definir alguns pontos, como o [Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) e os [Aplicativos móveis do Office](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="27672-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="27672-158">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="27672-158">Need help?</span></span>

<span data-ttu-id="27672-159">[Entre em contato com o suporte da Microsoft 365 para empresas](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="27672-159">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="27672-160">Você tem centenas ou milhares de usuários para adicionar?</span><span class="sxs-lookup"><span data-stu-id="27672-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="27672-161">Para adicionar vários usuários ao mesmo tempo, siga essas etapas:</span><span class="sxs-lookup"><span data-stu-id="27672-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="27672-162">**Usar uma planilha para adicionar pessoas em massa.**</span><span class="sxs-lookup"><span data-stu-id="27672-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="27672-163">Confira [adicionar vários usuários ao mesmo tempo](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="27672-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="27672-164">**Automatize a adição de contas e a atribuição de licenças.**</span><span class="sxs-lookup"><span data-stu-id="27672-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="27672-165">Confira [criar contas de usuário com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="27672-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="27672-166">Escolha este método se já estiver familiarizado com o uso dos cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27672-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="27672-167">**Usando o ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="27672-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="27672-168">[Configurar a sincronização de diretório para o Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="27672-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="27672-169">Use a ferramenta Azure AD Connect para replicar as contas de usuário do Active Directory (e outros objetos do Active Directory) no Office 365.</span><span class="sxs-lookup"><span data-stu-id="27672-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="27672-170">A sincronização só adiciona as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="27672-171">Você precisará atribuir licenças aos usuários sincronizados antes que eles possam usar o email e outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="27672-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="27672-172">**Migrar do Exchange?**</span><span class="sxs-lookup"><span data-stu-id="27672-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="27672-173">[Maneiras de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="27672-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="27672-174">Ao migrar várias caixas de correio para o Microsoft 365 usando a substituição, a transferência ou um método híbrido do Exchange, você adicionará usuários automaticamente como parte da migração.</span><span class="sxs-lookup"><span data-stu-id="27672-174">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="27672-175">A migração somente adiciona as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="27672-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="27672-176">Você precisará atribuir licenças aos usuários para que eles possam usar emails e outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="27672-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="27672-177">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="27672-177">Related articles</span></span>

[<span data-ttu-id="27672-178">Adicionar um novo funcionário ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27672-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="27672-179">Excluir um usuário da sua organização</span><span class="sxs-lookup"><span data-stu-id="27672-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="27672-180">Restaurar um usuário no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27672-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="27672-181">Adicionar vários usuários ao mesmo tempo para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="27672-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

