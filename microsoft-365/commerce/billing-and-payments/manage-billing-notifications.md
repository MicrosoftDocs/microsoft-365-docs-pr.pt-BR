---
title: Gerenciar notificações de faturamento e anexos de fatura
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
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
- commerce_billing
search.appverid:
- MET150
description: Saiba como gerenciar quem recebe emails de notificação de cobrança e anexos de fatura.
ms.date: 03/17/2021
ms.openlocfilehash: a49598cd1b361a85af8455b0aff19e11fcf96526
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203239"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="ef0ed-103">Gerenciar notificações de faturamento e anexos de fatura</span><span class="sxs-lookup"><span data-stu-id="ef0ed-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="ef0ed-104">A **página Notificações de** cobrança permite gerenciar quem recebe emails de notificação de cobrança para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="ef0ed-105">A página também oferece a opção de receber as faturas da sua organização [como anexos de email.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="ef0ed-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ef0ed-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ef0ed-106">Before you begin</span></span>

<span data-ttu-id="ef0ed-107">Você deve ser um administrador global para fazer as etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="ef0ed-108">Os administradores de cobrança podem fazer algumas dessas alterações, conforme o que se pode ver nas seções abaixo.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="ef0ed-109">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ef0ed-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="ef0ed-110">Alterar o idioma em que você recebe emails</span><span class="sxs-lookup"><span data-stu-id="ef0ed-110">Change the language you receive email in</span></span>

<span data-ttu-id="ef0ed-111">Os emails de notificação de cobrança são enviados no idioma preferencial da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-111">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="ef0ed-112">Para alterar o idioma preferencial, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-112">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="ef0ed-113">Na Centro de administração do Microsoft 365, vá para a página **Notificações** de  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank"></a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-113">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-114">Na seção **Configurações de notificação de cobrança,** selecione **Editar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-114">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="ef0ed-115">No painel **Configurações de notificação de** cobrança, em **Idioma** preferencial, selecione o idioma que você deseja usar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-115">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="ef0ed-116">Alterar quem recebe notificações de cobrança</span><span class="sxs-lookup"><span data-stu-id="ef0ed-116">Change who receives billing notifications</span></span>

<span data-ttu-id="ef0ed-117">As notificações de cobrança da sua organização são enviadas para o endereço de email principal e alternativo de cada administrador Global e cobrança. Para alterar quais usuários têm a função de administrador Global ou Cobrança, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-117">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="ef0ed-118">Atribuir funções de administrador usando a página Notificações de Cobrança</span><span class="sxs-lookup"><span data-stu-id="ef0ed-118">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="ef0ed-119">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-120">Na seção **Administradores que recebem notificações de cobrança,** selecione o link Administrador **de Cobrança** ou **Administrador Global** no texto de descrição.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-120">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="ef0ed-121">No painel direito, na guia **Administradores Atribuídos,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-121">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="ef0ed-122">No painel **Adicionar administradores,** digite o nome de exibição ou nome de usuário do usuário e selecione o usuário na lista de sugestões.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-122">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="ef0ed-123">Adicione vários usuários até terminar.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-123">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="ef0ed-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-124">Select **Save**.</span></span> <span data-ttu-id="ef0ed-125">O usuário é adicionado à lista de administradores atribuídos.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-125">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="ef0ed-126">Remover funções de administrador usando a página Notificações de cobrança</span><span class="sxs-lookup"><span data-stu-id="ef0ed-126">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="ef0ed-127">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-128">Na seção **Administradores que recebem notificações de cobrança,** selecione o link Administrador **de Cobrança** ou **Administrador Global** no texto de descrição.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-128">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="ef0ed-129">No painel direito, na guia Administradores **Atribuídos,** selecione os usuários a remover da função e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-129">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="ef0ed-130">Na caixa de confirmação, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-130">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="ef0ed-131">O usuário é removido da lista de administradores atribuídos.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-131">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="ef0ed-132">Alterar os endereços de email para administradores</span><span class="sxs-lookup"><span data-stu-id="ef0ed-132">Change the email addresses for admins</span></span>

<span data-ttu-id="ef0ed-133">Para alterar o endereço de email principal e alternativo de outros administradores em sua organização, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-133">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="ef0ed-134">Os administradores de cobrança podem alterar seus próprios endereços de email primários e alternativos, mas não para outros administradores.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-134">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="ef0ed-135">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-135">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-136">Na seção **Administradores que recebem notificações de cobrança,** selecione um nome.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-136">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="ef0ed-137">No painel direito, adicione ou atualize o endereço de email principal e alternativo conforme necessário e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-137">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="ef0ed-138">Alterar o email de contato da sua organização</span><span class="sxs-lookup"><span data-stu-id="ef0ed-138">Change your organization's contact email</span></span>

<span data-ttu-id="ef0ed-139">Além dos administradores global e de cobrança, enviamos notificações de cobrança para o endereço de email de contato da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-139">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="ef0ed-140">Para alterar o endereço de email, use as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-140">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="ef0ed-141">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-141">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-142">Em **Contato da organização recebendo notificações de cobrança,** selecione o contato da organização.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-142">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="ef0ed-143">No painel direito, digite o endereço de email que você deseja usar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-143">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="ef0ed-144">Receber as faturas da sua organização como anexos de email</span><span class="sxs-lookup"><span data-stu-id="ef0ed-144">Receive your organization's invoices as email attachments</span></span>

> [!NOTE]
> <span data-ttu-id="ef0ed-145">Os administradores de cobrança também podem fazer as etapas nesta seção.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-145">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="ef0ed-146">Você pode ter uma cópia da fatura da sua organização anexada como um arquivo PDF para faturar emails de notificação quando uma nova fatura estiver pronta.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="ef0ed-147">Use as etapas a seguir para receber faturas como anexos.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="ef0ed-148">No centro de administração, vá para a página **Fatura** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Notificações de fatura</a>.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="ef0ed-149">Em **Configurações de notificação de cobrança,** selecione **Editar configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="ef0ed-150">No painel **Configurações de** notificação de cobrança, em **Anexar** um PDF aos emails da fatura, marque a caixa de seleção e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="ef0ed-151">Para parar de receber o anexo da fatura a qualquer momento, siga as etapas acima e desempure a caixa de seleção Anexar um **PDF** à caixa de seleção emails de fatura na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="ef0ed-152">E se eu tiver um perfil de cobrança?</span><span class="sxs-lookup"><span data-stu-id="ef0ed-152">What if I have a billing profile?</span></span>

<span data-ttu-id="ef0ed-153">Se você tiver um perfil de cobrança, algumas das etapas descritas neste artigo podem ser ligeiramente diferentes para algumas de suas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="ef0ed-154">Esta seção descreve essas diferenças.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-154">This section describes those differences.</span></span> [<span data-ttu-id="ef0ed-155">Como saber se tenho um perfil de cobrança?</span><span class="sxs-lookup"><span data-stu-id="ef0ed-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="ef0ed-156">Who recebe notificações de cobrança?</span><span class="sxs-lookup"><span data-stu-id="ef0ed-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="ef0ed-157">Os emails de notificação de cobrança são enviados para os endereços de email principais e alternativos para usuários que têm uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="ef0ed-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="ef0ed-158">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="ef0ed-158">Billing profile owner</span></span>
- <span data-ttu-id="ef0ed-159">Colaborador de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="ef0ed-159">Billing profile contributor</span></span>
- <span data-ttu-id="ef0ed-160">Gerenciador de faturas</span><span class="sxs-lookup"><span data-stu-id="ef0ed-160">Invoice manager</span></span>

<span data-ttu-id="ef0ed-161">Para saber mais sobre funções de perfil de cobrança e como gerenciá-las, consulte Compreender funções administrativas do Contrato de Cliente da [Microsoft no Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span><span class="sxs-lookup"><span data-stu-id="ef0ed-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="ef0ed-162">Para alterar quem recebe as notificações de cobrança da sua organização, use as etapas a seguir para alterar as funções atribuídas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="ef0ed-163">No centro de administração, vá para a página **Contas de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamentos.</a></span><span class="sxs-lookup"><span data-stu-id="ef0ed-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="ef0ed-164">Na guia **Perfil de Cobrança,** selecione um perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="ef0ed-165">Na seção **Funções de perfil de** cobrança, atribua ou remova funções para o proprietário do perfil de Cobrança, colaborador de perfil de cobrança ou Gerente de **Fatura.**  </span><span class="sxs-lookup"><span data-stu-id="ef0ed-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="ef0ed-166">Receber faturas como anexos de email</span><span class="sxs-lookup"><span data-stu-id="ef0ed-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="ef0ed-167">Para receber suas faturas como anexos às notificações de fatura, use as etapas a seguir para ativar essa configuração para um perfil de cobrança específico.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="ef0ed-168">No centro de administração, vá para a página **Contas de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamentos.</a></span><span class="sxs-lookup"><span data-stu-id="ef0ed-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="ef0ed-169">Selecione a **guia Perfis de** Cobrança e selecione um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="ef0ed-170">Na página detalhes do perfil de cobrança, em **Obter faturas** em anexos de email, alterne a alternância para **On**.</span><span class="sxs-lookup"><span data-stu-id="ef0ed-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="ef0ed-171">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ef0ed-171">Related content</span></span>

<span data-ttu-id="ef0ed-172">[Ver sua conta ou fatura](view-your-bill-or-invoice.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef0ed-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="ef0ed-173">[Informações de faturamento do Microsoft 365 para empresas no México](mexico-billing-info.md) (artigo) </span><span class="sxs-lookup"><span data-stu-id="ef0ed-173">[Billing information for Microsoft 365 for business in Mexico](mexico-billing-info.md) (article) </span></span>\
<span data-ttu-id="ef0ed-174">[Entenda sua fatura ou fatura para Microsoft 365 para empresas](understand-your-invoice2.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef0ed-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="ef0ed-175">[Adicionar usuários e atribuir licenças ao mesmo tempo](../../admin/add-users/add-users.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef0ed-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
