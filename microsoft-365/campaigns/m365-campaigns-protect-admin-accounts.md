---
title: Proteger suas contas de administrador
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Saiba como configurar e proteger suas contas de administrador.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044483"
---
# <a name="protect-your-administrator-accounts"></a><span data-ttu-id="723d2-103">Proteger suas contas de administrador</span><span class="sxs-lookup"><span data-stu-id="723d2-103">Protect your administrator accounts</span></span>

<span data-ttu-id="723d2-104">Como as contas de administrador vêm com privilégios elevados, elas são alvos valiosos para hackers e ciberataques.</span><span class="sxs-lookup"><span data-stu-id="723d2-104">Because admin accounts come with elevated privileges, they're valuable targets for hackers and cyber criminals.</span></span> <span data-ttu-id="723d2-105">Este artigo descreve:</span><span class="sxs-lookup"><span data-stu-id="723d2-105">This article describes:</span></span>

- <span data-ttu-id="723d2-106">Como configurar uma conta de administrador adicional para emergências.</span><span class="sxs-lookup"><span data-stu-id="723d2-106">How to set up an additional administrator account for emergencies.</span></span>
- <span data-ttu-id="723d2-107">Como proteger essas contas.</span><span class="sxs-lookup"><span data-stu-id="723d2-107">How to protect these accounts.</span></span>

<span data-ttu-id="723d2-108">Ao se inscrever no Microsoft 365 e inserir suas informações, você se tornará automaticamente o administrador global. Um administrador global tem o controle total de contas de usuário e todas as outras configurações no centro de administração da Microsoft, mas há muitos tipos diferentes de contas de administrador com graus variáveis de acesso.</span><span class="sxs-lookup"><span data-stu-id="723d2-108">When you sign up for Microsoft 365 and enter your information, you automatically become the global admin. A global admin has the ultimate control of user accounts and all the other settings in the Microsoft admin center, but there are many different kinds of admin accounts with varying degrees of access.</span></span> <span data-ttu-id="723d2-109">Consulte [as funções de administrador](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) para obter informações sobre os diferentes níveis de acesso para cada tipo de função de administrador.</span><span class="sxs-lookup"><span data-stu-id="723d2-109">See [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) for information about the different access levels for each kind of admin role.</span></span>

## <a name="create-additional-admin-accounts"></a><span data-ttu-id="723d2-110">Criar contas de administrador adicionais</span><span class="sxs-lookup"><span data-stu-id="723d2-110">Create additional admin accounts</span></span>

<span data-ttu-id="723d2-111">Use contas de administrador somente para administração.</span><span class="sxs-lookup"><span data-stu-id="723d2-111">Use admin accounts only for administration.</span></span> <span data-ttu-id="723d2-112">Os administradores devem ter uma conta de usuário separada para uso regular de aplicativos do Office e usar sua conta administrativa somente quando necessário para gerenciar contas e dispositivos e enquanto trabalham em outras funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="723d2-112">Admins should have a separate user account for regular use of Office apps and only use their administrative account when necessary to manage accounts and devices, and while working on other admin functions.</span></span> <span data-ttu-id="723d2-113">Também é uma boa ideia remover a licença do Microsoft 365 das contas de administrador para que você não tenha que pagar por elas.</span><span class="sxs-lookup"><span data-stu-id="723d2-113">It's also a good idea to remove the Microsoft 365 license from the admin accounts so you don't have to pay for them.</span></span>

<span data-ttu-id="723d2-114">Você vai querer configurar pelo menos uma conta de administrador global adicional para dar acesso de administrador a outro funcionário confiável.</span><span class="sxs-lookup"><span data-stu-id="723d2-114">You'll want to set up at least one additional global admin account to give admin access to another trusted employee.</span></span> <span data-ttu-id="723d2-115">Você também pode criar contas de administrador separadas para gerenciamento de usuários (essa função é chamada **de Administrador de gerenciamento de usuários).**</span><span class="sxs-lookup"><span data-stu-id="723d2-115">You can also create separate admin accounts for user management (this role is called **User management administrator**).</span></span> <span data-ttu-id="723d2-116">Para obter mais informações, consulte [as funções de administrador.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="723d2-116">For more information, see [about admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="723d2-117">Para criar contas de administrador adicionais:</span><span class="sxs-lookup"><span data-stu-id="723d2-117">To create additional admin accounts:</span></span>

 1. <span data-ttu-id="723d2-118">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Ativos na** entrada esquerda.</span><span class="sxs-lookup"><span data-stu-id="723d2-118">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. <span data-ttu-id="723d2-120">Na página **Usuários ativos,** selecione Adicionar um usuário na  parte superior da página e, no painel Novo usuário, insira o nome e outras informações. </span><span class="sxs-lookup"><span data-stu-id="723d2-120">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
 3. <span data-ttu-id="723d2-121">Expanda **a seção** Funções e escolha Administrador **global** para dar a esse usuário acesso de administrador global.</span><span class="sxs-lookup"><span data-stu-id="723d2-121">Expand the **Roles** section, and choose **Global administrator** to give this user global admin access.</span></span> <span data-ttu-id="723d2-122">Você também pode escolher **Administrador personalizado** e escolher qualquer uma das funções exibidas.</span><span class="sxs-lookup"><span data-stu-id="723d2-122">You can also choose **Customized administrator** and choose any of the roles that are displayed.</span></span>

    <span data-ttu-id="723d2-123">Insira um email alternativo na caixa **de texto Endereço de email** alternativo.</span><span class="sxs-lookup"><span data-stu-id="723d2-123">Enter an alternate email in the **Alternative email address** text box.</span></span> <span data-ttu-id="723d2-124">Você pode usar esse endereço para recuperar suas informações de senha se for bloqueado. Para administradores globais, um extrato de cobrança também será enviado para esse endereço.</span><span class="sxs-lookup"><span data-stu-id="723d2-124">You can use this address to recover your password information if you get locked out. For global admins, a billing statement will also be sent to this address.</span></span>

    ![Escolher a função de administrador](../media/adminroles.png)

 4. <span data-ttu-id="723d2-126">Na seção **Licenças de produto,** mova o seletor  do **Microsoft 365 Business** para Desligado e o usuário Criar sem licença de produto **para** **On**.</span><span class="sxs-lookup"><span data-stu-id="723d2-126">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **Off** and the **Create user without product license** to **On**.</span></span>

    ![Escolher a licença do produto](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a><span data-ttu-id="723d2-128">Criar uma conta de administrador de emergência</span><span class="sxs-lookup"><span data-stu-id="723d2-128">Create an emergency admin account</span></span>

<span data-ttu-id="723d2-129">Você também deve criar uma conta de backup que não esteja configurada com a autenticação multifatória (MFA) para que você não se bloqueie acidentalmente (por exemplo, se você perder o telefone que está usando como uma segunda forma de verificação).</span><span class="sxs-lookup"><span data-stu-id="723d2-129">You should also create a backup account that isn't set up with multi-factor authentication (MFA) so you don't accidentally lock yourself out (for example if you lose your phone that you're using as a second form of verification).</span></span> <span data-ttu-id="723d2-130">Certifique-se de que a senha dessa conta seja uma frase ou pelo menos 16 caracteres.</span><span class="sxs-lookup"><span data-stu-id="723d2-130">Make sure that the password for this account is a phrase or at least 16 characters long.</span></span> <span data-ttu-id="723d2-131">Isso geralmente é conhecido como uma "conta de vidro de vidro".</span><span class="sxs-lookup"><span data-stu-id="723d2-131">This is often referred to as a "break-glass account."</span></span>

## <a name="create-a-user-account-for-yourself"></a><span data-ttu-id="723d2-132">Criar uma conta de usuário para si mesmo</span><span class="sxs-lookup"><span data-stu-id="723d2-132">Create a user account for yourself</span></span>

<span data-ttu-id="723d2-133">Use sua conta de usuário para participar da colaboração com sua organização, incluindo a verificação de emails.</span><span class="sxs-lookup"><span data-stu-id="723d2-133">Use your user account to participate in collaboration with your organization, including checking mail.</span></span> <span data-ttu-id="723d2-134">Isso significa que suas credenciais de administrador podem ser semelhantes a  *Alice.Contoso.org <span></span> e* sua conta de usuário normal pode ser semelhante a *Alice <span></span> @Contoso.com*.</span><span class="sxs-lookup"><span data-stu-id="723d2-134">This means your admin credentials might be similar to  *Alice.Chavez <span></span>@Contoso.org* and your regular user account might be similar to *Alice<span></span>@Contoso.com*.</span></span>

<span data-ttu-id="723d2-135">Para criar uma nova conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="723d2-135">To create a new user account:</span></span>

1. <span data-ttu-id="723d2-136">Vá para o <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">centro de administração</a> e escolha **Usuários** \> **Ativos na** entrada esquerda.</span><span class="sxs-lookup"><span data-stu-id="723d2-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">admin center</a> and then choose **Users** \> **Active users** in the left nav.</span></span>
2. <span data-ttu-id="723d2-137">Na página **Usuários ativos,** selecione Adicionar um usuário na  parte superior da página e, no painel Novo usuário, insira o nome e outras informações. </span><span class="sxs-lookup"><span data-stu-id="723d2-137">On the **Active users** page, select **Add a user** at the top of the page, and on the **New user** panel, enter the name and other information.</span></span>
3. <span data-ttu-id="723d2-138">Expanda **a seção** Funções e escolha Usuário **(sem acesso administrativo).**</span><span class="sxs-lookup"><span data-stu-id="723d2-138">Expand the **Roles** section, and choose **User (no administrative access)**.</span></span>
4. <span data-ttu-id="723d2-139">Na seção **Licenças de produto,** mova o seletor do **Microsoft 365 Business** para **On.**</span><span class="sxs-lookup"><span data-stu-id="723d2-139">In the **Product licenses** section, move the selector for **Microsoft 365 Business** to **On**.</span></span>

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a><span data-ttu-id="723d2-140">Registre cada uma dessas contas para autenticação multifa factor</span><span class="sxs-lookup"><span data-stu-id="723d2-140">Register each of these accounts for multi-factor authentication</span></span>

<span data-ttu-id="723d2-141">Certifique-se de que essas contas estão usando [a autenticação multifator.](m365-campaigns-multifactor-authenication.md)</span><span class="sxs-lookup"><span data-stu-id="723d2-141">Make sure these accounts are using [multifactor authentication](m365-campaigns-multifactor-authenication.md).</span></span>

## <a name="additional-recommendations"></a><span data-ttu-id="723d2-142">Recomendações adicionais</span><span class="sxs-lookup"><span data-stu-id="723d2-142">Additional recommendations</span></span>

- <span data-ttu-id="723d2-143">Certifique-se de que as contas de administrador também estão configuradas para autenticação multifa factor.</span><span class="sxs-lookup"><span data-stu-id="723d2-143">Be sure that admin accounts are also set up for multi-factor authentication.</span></span> <span data-ttu-id="723d2-144">Mostraremos como fazer isso em Configurar políticas de [acesso condicional.](m365-campaigns-conditional-access.md)</span><span class="sxs-lookup"><span data-stu-id="723d2-144">We'll show you how to do this in [Configure conditional access policies](m365-campaigns-conditional-access.md).</span></span>
- <span data-ttu-id="723d2-145">Antes de usar contas de administrador, feche todas as sessões de navegador e aplicativos não relacionados, incluindo contas de email pessoais.</span><span class="sxs-lookup"><span data-stu-id="723d2-145">Before using admin accounts, close out all unrelated browser sessions and apps, including personal email accounts.</span></span> <span data-ttu-id="723d2-146">Você também pode usar em janelas privadas ou anônimas do navegador.</span><span class="sxs-lookup"><span data-stu-id="723d2-146">You can also use in private, or incognito browser windows.</span></span>
- <span data-ttu-id="723d2-147">Depois de concluir as tarefas de administrador, saia da sessão do navegador.</span><span class="sxs-lookup"><span data-stu-id="723d2-147">After completing admin tasks, be sure to sign out of the browser session.</span></span>
