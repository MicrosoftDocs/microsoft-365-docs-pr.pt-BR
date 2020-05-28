---
title: Criar e usar um modelo para adicionar usuários
f1.keywords:
- NOCSH
ms.author: v-sharos
author: shars
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
- MET150
- MOE150
description: Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários.
ms.openlocfilehash: 3173d28f27acdf1a084137d36cd71894e94e9547
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387220"
---
# <a name="create-and-use-a-template-to-add-users"></a><span data-ttu-id="33292-103">Criar e usar um modelo para adicionar usuários</span><span class="sxs-lookup"><span data-stu-id="33292-103">Create and use a template to add users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="33292-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="33292-104">The admin center is changing.</span></span> <span data-ttu-id="33292-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="33292-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="33292-106">Você pode criar e usar um modelo para economizar tempo e padronizar as configurações ao adicionar vários usuários.</span><span class="sxs-lookup"><span data-stu-id="33292-106">You can create and use a template to save time and standardize settings when you are adding multiple users.</span></span> <span data-ttu-id="33292-107">Os modelos são particularmente úteis se você tiver usuários que compartilham muitas propriedades comuns, como aqueles que têm a mesma função e funcionam no mesmo local e aqueles que exigem o mesmo software.</span><span class="sxs-lookup"><span data-stu-id="33292-107">Templates are particularly useful if you have users who share many common properties, like those who have the same role and work at the same location and those who require the same software.</span></span> <span data-ttu-id="33292-108">Por exemplo, você pode ter uma equipe de engenheiros de suporte que trabalham no mesmo escritório.</span><span class="sxs-lookup"><span data-stu-id="33292-108">For example, you might have a team of support engineers who work in the same office.</span></span>  

## <a name="create-a-template"></a><span data-ttu-id="33292-109">Criar um modelo</span><span class="sxs-lookup"><span data-stu-id="33292-109">Create a template</span></span>

<span data-ttu-id="33292-110">Os modelos são fáceis de criar &mdash; é possível selecionar **os**  >  **Active users**  >  **modelos de usuário**ativos dos usuários e, em seguida, selecionar **Adicionar um modelo** na lista suspensa ou adicionar um novo usuário e quando terminar, você terá a opção de salvar a entrada como um modelo.</span><span class="sxs-lookup"><span data-stu-id="33292-110">Templates are easy to create&mdash;you can select **Users** > **Active users** > **User templates**, and then select **Add a template** from the drop-down list, or you can add a new user and when you are finished, you will have the option of saving the entry as a template.</span></span>

<span data-ttu-id="33292-111">Quando você cria um modelo após adicionar um usuário, os valores escolhidos para as seguintes configurações são salvos no modelo:</span><span class="sxs-lookup"><span data-stu-id="33292-111">When you create a template after adding a user, the values you choose for the following settings are saved in the template:</span></span>

- <span data-ttu-id="33292-112">Nome de domínio</span><span class="sxs-lookup"><span data-stu-id="33292-112">Domain name</span></span>
- <span data-ttu-id="33292-113">Opção de configurações de senha: você pode optar por criar senhas ou fazer com que elas sejam geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="33292-113">Password settings choice: you can choose to create passwords or have them auto-generated</span></span>
- <span data-ttu-id="33292-114">Opção de senha de uso único: você pode exigir que o usuário crie uma nova senha após a primeira entrada</span><span class="sxs-lookup"><span data-stu-id="33292-114">One-time password choice: you can require the user to create a new password after first sign in</span></span>
- <span data-ttu-id="33292-115">Local da licença</span><span class="sxs-lookup"><span data-stu-id="33292-115">License location</span></span>
- <span data-ttu-id="33292-116">Opções de licença</span><span class="sxs-lookup"><span data-stu-id="33292-116">License choices</span></span>
- <span data-ttu-id="33292-117">Opções de aplicativo</span><span class="sxs-lookup"><span data-stu-id="33292-117">Application choices</span></span>
- <span data-ttu-id="33292-118">Role</span><span class="sxs-lookup"><span data-stu-id="33292-118">Role</span></span>
- <span data-ttu-id="33292-119">A maioria das informações de perfil, como **perfil de trabalho**, **Departamento**, **escritório**, **telefone comercial**e **endereço**</span><span class="sxs-lookup"><span data-stu-id="33292-119">Most profile information, such as **Job profile**, **Department**, **Office**, **Office phone**, and **Street address**</span></span> 

<span data-ttu-id="33292-120">As informações a seguir são específicas do usuário e não são salvas no modelo:</span><span class="sxs-lookup"><span data-stu-id="33292-120">The following information is user-specific and isn't saved in the template:</span></span>

- <span data-ttu-id="33292-121">Nome e sobrenome</span><span class="sxs-lookup"><span data-stu-id="33292-121">First and last name</span></span>
- <span data-ttu-id="33292-122">Nome diferenciado (DN)</span><span class="sxs-lookup"><span data-stu-id="33292-122">Display name</span></span>
- <span data-ttu-id="33292-123">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="33292-123">User name</span></span>
- <span data-ttu-id="33292-124">Escolha para enviar a senha por email e para quem o email de senha é enviado</span><span class="sxs-lookup"><span data-stu-id="33292-124">Choice to send the password in email and who the password email is sent to</span></span>
- <span data-ttu-id="33292-125">Número de telefone celular</span><span class="sxs-lookup"><span data-stu-id="33292-125">Mobile phone number</span></span>

<span data-ttu-id="33292-126">Se você optar por não inserir informações para uma configuração dentro de uma seção, esse valor ficará em branco e essa configuração não será exibida no modelo.</span><span class="sxs-lookup"><span data-stu-id="33292-126">If you choose not to enter information for a setting within a section, that value will be blank and that setting will not display in the template.</span></span> <span data-ttu-id="33292-127">Por exemplo, se você deixar o **título do trabalho** em branco, quando você revisar seu modelo e quando você usa o modelo, o **cargo** não aparecerá.</span><span class="sxs-lookup"><span data-stu-id="33292-127">For example, if you leave **Job title** blank, when you review your template and when you use your template, **Job title** will not appear at all.</span></span> <span data-ttu-id="33292-128">Se você deixar todas as configurações da seção de **perfil** em branco, a seção de **perfil** exibirá **nenhuma fornecida** no modelo final.</span><span class="sxs-lookup"><span data-stu-id="33292-128">If you leave all the **Profile** section settings blank, the **Profile** section will display **None provided** in your final template.</span></span>

<span data-ttu-id="33292-129">Ao criar um modelo selecionando a opção **Adicionar um modelo** , você pode escolher quais valores serão concluídos.</span><span class="sxs-lookup"><span data-stu-id="33292-129">When you create a template by selecting the **Add a template** option, you can choose which values to complete.</span></span> <span data-ttu-id="33292-130">Tudo o que for deixado em branco aparecerá como **nenhum fornecido** no modelo.</span><span class="sxs-lookup"><span data-stu-id="33292-130">Anything that is left blank will appear as **None provided** in the template.</span></span>

## <a name="use-a-template-to-add-a-user"></a><span data-ttu-id="33292-131">Usar um modelo para adicionar um usuário</span><span class="sxs-lookup"><span data-stu-id="33292-131">Use a template to add a user</span></span>

<span data-ttu-id="33292-132">Para usar um modelo existente para adicionar um usuário:</span><span class="sxs-lookup"><span data-stu-id="33292-132">To use an existing template to add a user:</span></span>

1. <span data-ttu-id="33292-133">No centro de administração, selecione usuários ativos do **usuário**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="33292-133">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="33292-134">Selecione **modelos de usuário**e, em seguida, selecione um modelo na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="33292-134">Select **User templates**, and then select a template from the drop-down list.</span></span> <span data-ttu-id="33292-135">(A lista conterá apenas os modelos criados, e não os criados por outros administradores.)</span><span class="sxs-lookup"><span data-stu-id="33292-135">(The list will contain only the templates that you created, not those created by other admins.)</span></span>

 > [!NOTE]
 > <span data-ttu-id="33292-136">Você também pode usar um modelo para adicionar um usuário selecionando **modelos de usuário**  >  **gerenciar modelos**, selecionando um modelo e, em seguida, selecionando **usar modelo**.</span><span class="sxs-lookup"><span data-stu-id="33292-136">You can also use a template to add a user by selecting **User templates** > **Manage templates**, selecting a template, and then selecting **Use template**.</span></span>

3. <span data-ttu-id="33292-137">Siga as etapas para criar um usuário a partir do modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="33292-137">Follow the steps to create a user from the template you selected.</span></span>

> [!NOTE]
> <span data-ttu-id="33292-138">Se você tiver licenças insuficientes disponíveis para um usuário que você adicionar e suas informações de pagamento estiverem disponíveis, tentaremos comprar outra licença usando suas informações de pagamento existentes.</span><span class="sxs-lookup"><span data-stu-id="33292-138">If you have insufficient licenses available for a user that you add, and your payment information is available, we will attempt to purchase another license using your existing payment information.</span></span> <span data-ttu-id="33292-139">Se suas informações de pagamento não estiverem disponíveis, o usuário será criado como um usuário não licenciado.</span><span class="sxs-lookup"><span data-stu-id="33292-139">If your payment information is unavailable, the user will be created as an unlicensed user.</span></span>

## <a name="manage-templates"></a><span data-ttu-id="33292-140">Gerenciar modelos</span><span class="sxs-lookup"><span data-stu-id="33292-140">Manage templates</span></span>

<span data-ttu-id="33292-141">Você pode excluir facilmente modelos que não são mais necessários e adicionar novos.</span><span class="sxs-lookup"><span data-stu-id="33292-141">You can easily delete templates you no longer need and add new ones.</span></span> <span data-ttu-id="33292-142">Para excluir um modelo:</span><span class="sxs-lookup"><span data-stu-id="33292-142">To delete a template:</span></span>

1. <span data-ttu-id="33292-143">No centro de administração, selecione usuários ativos do **usuário**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="33292-143">In the admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="33292-144">Selecione **modelos**e, em seguida, selecione **gerenciar modelos** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="33292-144">Select **Templates**, and then select **Manage templates** from the drop-down list.</span></span>

3. <span data-ttu-id="33292-145">Uma lista de modelos será exibida.</span><span class="sxs-lookup"><span data-stu-id="33292-145">A list of templates will appear.</span></span> <span data-ttu-id="33292-146">Você pode excluir um modelo executando qualquer um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="33292-146">You can delete a template by doing any of the following:</span></span>
    - <span data-ttu-id="33292-147">Selecione um ou mais modelos e, em seguida, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="33292-147">Select one or more templates, and then select **Delete**.</span></span> 
    - <span data-ttu-id="33292-148">Selecione os três pontos à direita do nome do modelo e, em seguida, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="33292-148">Select the three dots to the right of the template name, and then select **Delete**.</span></span>
    - <span data-ttu-id="33292-149">Selecione o nome do modelo.</span><span class="sxs-lookup"><span data-stu-id="33292-149">Select the template name.</span></span> <span data-ttu-id="33292-150">Quando os detalhes do modelo aparecem no lado direito da tela, selecione **excluir modelo**.</span><span class="sxs-lookup"><span data-stu-id="33292-150">When the template details appear on the right side of your screen, select **Delete template**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="33292-151">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="33292-151">Related articles</span></span>

[<span data-ttu-id="33292-152">Adicionar usuários individualmente ou em massa ao Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33292-152">Add users individually or in bulk to Microsoft 365</span></span>](add-users.md)

[<span data-ttu-id="33292-153">Remover um antigo funcionário da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33292-153">Remove a former employee from Microsoft 365</span></span>](remove-former-employee.md)
  
