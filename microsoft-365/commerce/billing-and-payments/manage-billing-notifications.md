---
title: Gerenciar notificações de cobrança e anexos de fatura
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Saiba como gerenciar quem recebe emails de notificação de cobrança e anexos de fatura.
ms.openlocfilehash: f0811c5d027d042b5114c9e05c698dab1e08763b
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515215"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="33016-103">Gerenciar notificações de cobrança e anexos de fatura</span><span class="sxs-lookup"><span data-stu-id="33016-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="33016-104">A **página Notificações de** cobrança permite gerenciar quem recebe emails de notificação de cobrança para sua organização.</span><span class="sxs-lookup"><span data-stu-id="33016-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="33016-105">A página também oferece a opção de receber as faturas da sua organização [como anexos de email.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="33016-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="33016-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="33016-106">Before you begin</span></span>

<span data-ttu-id="33016-107">Você deve ser um administrador global para fazer as etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="33016-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="33016-108">Os administradores de cobrança podem fazer algumas dessas alterações, conforme o que se pode ver nas seções abaixo.</span><span class="sxs-lookup"><span data-stu-id="33016-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="33016-109">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="33016-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="33016-110">Alterar o idioma em que você recebe emails</span><span class="sxs-lookup"><span data-stu-id="33016-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="33016-111">Os administradores de cobrança também podem fazer as etapas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="33016-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="33016-112">Os emails de notificação de cobrança são enviados no idioma preferencial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="33016-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="33016-113">Para alterar o idioma preferencial, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="33016-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="33016-114">No Centro de administração do Microsoft 365, vá para a página **Notificações** de  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank"></a> cobrança.</span><span class="sxs-lookup"><span data-stu-id="33016-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-115">Na seção **Configurações de notificação de cobrança,** selecione **Editar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="33016-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="33016-116">No painel **Configurações de notificação de** cobrança, em **Idioma** preferencial, selecione o idioma que você deseja usar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33016-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="33016-117">Alterar quem recebe notificações de cobrança</span><span class="sxs-lookup"><span data-stu-id="33016-117">Change who receives billing notifications</span></span>

<span data-ttu-id="33016-118">As notificações de cobrança da sua organização são enviadas para o endereço de email principal e alternativo de cada administrador Global e cobrança. Para alterar quais usuários têm a função de administrador Global ou Cobrança, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="33016-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="33016-119">Atribuir funções de administrador usando a página Notificações de Cobrança</span><span class="sxs-lookup"><span data-stu-id="33016-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="33016-120">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="33016-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-121">Na seção **Administradores que recebem notificações de cobrança,** selecione o link Administrador **de Cobrança** ou **Administrador Global** no texto de descrição.</span><span class="sxs-lookup"><span data-stu-id="33016-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="33016-122">No painel direito, na guia **Administradores Atribuídos,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="33016-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="33016-123">No painel **Adicionar administradores,** digite o nome de exibição ou nome de usuário do usuário e selecione o usuário na lista de sugestões.</span><span class="sxs-lookup"><span data-stu-id="33016-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="33016-124">Adicione vários usuários até terminar.</span><span class="sxs-lookup"><span data-stu-id="33016-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="33016-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33016-125">Select **Save**.</span></span> <span data-ttu-id="33016-126">O usuário é adicionado à lista de administradores atribuídos.</span><span class="sxs-lookup"><span data-stu-id="33016-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="33016-127">Remover funções de administrador usando a página Notificações de cobrança</span><span class="sxs-lookup"><span data-stu-id="33016-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="33016-128">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="33016-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-129">Na seção **Administradores que recebem notificações de cobrança,** selecione o link Administrador **de Cobrança** ou **Administrador Global** no texto de descrição.</span><span class="sxs-lookup"><span data-stu-id="33016-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="33016-130">No painel direito, na guia Administradores **Atribuídos,** selecione os usuários a remover da função e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="33016-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="33016-131">Na caixa de confirmação, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="33016-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="33016-132">O usuário é removido da lista de administradores atribuídos.</span><span class="sxs-lookup"><span data-stu-id="33016-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="33016-133">Alterar os endereços de email para administradores</span><span class="sxs-lookup"><span data-stu-id="33016-133">Change the email addresses for admins</span></span>

<span data-ttu-id="33016-134">Para alterar o endereço de email principal e alternativo de outros administradores em sua organização, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="33016-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="33016-135">Os administradores de cobrança podem alterar seus próprios endereços de email primários e alternativos, mas não para outros administradores.</span><span class="sxs-lookup"><span data-stu-id="33016-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="33016-136">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="33016-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-137">Na seção **Administradores que recebem notificações de cobrança,** selecione um nome.</span><span class="sxs-lookup"><span data-stu-id="33016-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="33016-138">No painel direito, adicione ou atualize o endereço de email principal e alternativo conforme necessário e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33016-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="33016-139">Alterar o email de contato da sua organização</span><span class="sxs-lookup"><span data-stu-id="33016-139">Change your organization's contact email</span></span>

<span data-ttu-id="33016-140">Além dos administradores global e de cobrança, enviamos notificações de cobrança para o endereço de email de contato da sua organização.</span><span class="sxs-lookup"><span data-stu-id="33016-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="33016-141">Para alterar o endereço de email, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="33016-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="33016-142">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="33016-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-143">Em **Contato da organização recebendo notificações de cobrança,** selecione o contato da organização.</span><span class="sxs-lookup"><span data-stu-id="33016-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="33016-144">No painel direito, digite o endereço de email que você deseja usar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33016-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="33016-145">Receber as faturas da sua organização como anexos de email</span><span class="sxs-lookup"><span data-stu-id="33016-145">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="33016-146">Os administradores de cobrança também podem fazer as etapas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="33016-146">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="33016-147">Você pode ter uma cópia da fatura da sua organização anexada como um arquivo PDF para faturar emails de notificação quando uma nova fatura estiver pronta.</span><span class="sxs-lookup"><span data-stu-id="33016-147">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="33016-148">Use as etapas a seguir para receber faturas como anexos.</span><span class="sxs-lookup"><span data-stu-id="33016-148">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="33016-149">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="33016-149">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="33016-150">Em **Configurações de notificação de cobrança,** selecione **Editar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="33016-150">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="33016-151">No painel **Configurações de** notificação de cobrança, em **Anexar** um PDF aos emails da fatura, marque a caixa de seleção e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="33016-151">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="33016-152">Para parar de receber o anexo da fatura a qualquer momento, siga as etapas acima e desempure a caixa de seleção Anexar um **PDF** à caixa de seleção emails de fatura na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="33016-152">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="33016-153">E se eu tiver um perfil de cobrança?</span><span class="sxs-lookup"><span data-stu-id="33016-153">What if I have a billing profile?</span></span>

<span data-ttu-id="33016-154">Se você tiver um perfil de cobrança, algumas das etapas descritas neste artigo podem ser ligeiramente diferentes para algumas de suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="33016-154">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="33016-155">Esta seção descreve essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="33016-155">This section describes those differences.</span></span> [<span data-ttu-id="33016-156">Como saber se tenho um perfil de cobrança?</span><span class="sxs-lookup"><span data-stu-id="33016-156">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="33016-157">Quem recebe notificações de cobrança?</span><span class="sxs-lookup"><span data-stu-id="33016-157">Who receives Billing notifications?</span></span>

<span data-ttu-id="33016-158">Os emails de notificação de cobrança são enviados para os endereços de email principais e alternativos para usuários que têm uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="33016-158">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="33016-159">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="33016-159">Billing profile owner</span></span>
- <span data-ttu-id="33016-160">Colaborador de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="33016-160">Billing profile contributor</span></span>
- <span data-ttu-id="33016-161">Gerenciador de faturas</span><span class="sxs-lookup"><span data-stu-id="33016-161">Invoice manager</span></span>

<span data-ttu-id="33016-162">Para saber mais sobre funções de perfil de cobrança e como gerenciá-las, consulte Compreender funções administrativas do Contrato de Cliente da [Microsoft no Azure](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles).</span><span class="sxs-lookup"><span data-stu-id="33016-162">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](https://docs.microsoft.com/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="33016-163">Para alterar quem recebe as notificações de cobrança da sua organização, use as etapas a seguir para alterar as funções atribuídas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="33016-163">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="33016-164">No centro de administração, vá para a página **Contas de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamentos.</a></span><span class="sxs-lookup"><span data-stu-id="33016-164">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="33016-165">Na guia **Perfil de Cobrança,** selecione um perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="33016-165">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="33016-166">Na seção **Funções de perfil de** cobrança, atribua ou remova funções para o proprietário do perfil de Cobrança, colaborador de perfil de cobrança ou Gerente de **Fatura.**  </span><span class="sxs-lookup"><span data-stu-id="33016-166">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="33016-167">Receber faturas como anexos de email</span><span class="sxs-lookup"><span data-stu-id="33016-167">Receive invoices as email attachments</span></span>

<span data-ttu-id="33016-168">Para receber suas faturas como anexos às notificações de fatura, use as etapas a seguir para ativar essa configuração para um perfil de cobrança específico.</span><span class="sxs-lookup"><span data-stu-id="33016-168">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="33016-169">No centro de administração, vá para a página **Contas de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamentos.</a></span><span class="sxs-lookup"><span data-stu-id="33016-169">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="33016-170">Selecione a **guia Perfis de** Cobrança e selecione um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="33016-170">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="33016-171">Na página detalhes do perfil de cobrança, em **Obter faturas** em anexos de email, alterne a alternância para **On**.</span><span class="sxs-lookup"><span data-stu-id="33016-171">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="33016-172">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="33016-172">Related content</span></span>

<span data-ttu-id="33016-173">[Exibir sua fatura ou fatura](view-your-bill-or-invoice.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="33016-173">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="33016-174">[Entenda sua fatura ou fatura do Microsoft 365 for business](understand-your-invoice2.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="33016-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="33016-175">[Adicionar usuários e atribuir licenças ao mesmo tempo](../../admin/add-users/add-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="33016-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>