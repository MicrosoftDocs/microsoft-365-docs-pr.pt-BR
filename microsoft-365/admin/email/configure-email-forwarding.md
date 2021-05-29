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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: O encaminhamento de email permite encaminhar mensagens de email enviadas para uma caixa de correio de usuário Microsoft 365 para outra caixa de correio dentro ou fora da sua organização.
ms.openlocfilehash: 1d16a44749b51b582b7198cb331edf7faf3cf1f8
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698911"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a><span data-ttu-id="477b8-103">Configurar o encaminhamento de email em Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="477b8-103">Configure email forwarding in Microsoft 365</span></span>

<span data-ttu-id="477b8-104">Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de email para a caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="477b8-104">As the admin of an organization, you might have company requirements to set up email forwarding for a user's mailbox.</span></span> <span data-ttu-id="477b8-105">O encaminhamento de email permite encaminhar mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="477b8-105">Email forwarding lets you forward email messages sent to a user's mailbox to another user's mailbox inside or outside of your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="477b8-106">Você pode usar políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos.</span><span class="sxs-lookup"><span data-stu-id="477b8-106">You can use outbound spam filter policies to control automatic forwarding to external recipients.</span></span> <span data-ttu-id="477b8-107">Para obter mais informações, consulte [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span><span class="sxs-lookup"><span data-stu-id="477b8-107">For more information, see [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).</span></span>

## <a name="configure-email-forwarding"></a><span data-ttu-id="477b8-108">Configurar encaminhamento de email</span><span class="sxs-lookup"><span data-stu-id="477b8-108">Configure email forwarding</span></span>

<span data-ttu-id="477b8-109">Antes de configurar o encaminhamento de email, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="477b8-109">Before you set up email forwarding, note the following:</span></span>

- <span data-ttu-id="477b8-110">Permitir que mensagens encaminhadas automaticamente sejam enviadas para pessoas no domínio remoto.</span><span class="sxs-lookup"><span data-stu-id="477b8-110">Allow automatically forwarded messages to be sent to people on the remote domain.</span></span> <span data-ttu-id="477b8-111">Consulte [Gerenciar domínios remotos](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="477b8-111">See [Manage remote domains](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) for details.</span></span>

- <span data-ttu-id="477b8-112">Depois de configurar o encaminhamento de email, somente **os** novos emails enviados para a caixa  *de*  correio da caixa de correio serão encaminhados.</span><span class="sxs-lookup"><span data-stu-id="477b8-112">Once you set up email forwarding, only **new** emails sent to the  *from*  mailbox will be forwarded.</span></span>

- <span data-ttu-id="477b8-113">O encaminhamento de email exige que  *a conta de*  a partir tenha uma licença.</span><span class="sxs-lookup"><span data-stu-id="477b8-113">Email forwarding requires that the  *from*  account has a license.</span></span> <span data-ttu-id="477b8-114">Se você estiver configurando o encaminhamento de email porque o usuário deixou sua organização, outra opção é converter sua caixa de correio [em uma caixa de correio compartilhada.](convert-user-mailbox-to-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="477b8-114">If you're setting up email forwarding because the user has left your organization, another option is to [convert their mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md).</span></span> <span data-ttu-id="477b8-115">Dessa forma, várias pessoas podem acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="477b8-115">This way several people can access it.</span></span> <span data-ttu-id="477b8-116">No entanto, uma caixa de correio compartilhada não pode exceder 50 GB.</span><span class="sxs-lookup"><span data-stu-id="477b8-116">However, a shared mailbox cannot exceed 50GB.</span></span>

<span data-ttu-id="477b8-117">Você deve ser um administrador Exchange ou administrador global no Microsoft 365 para fazer essas etapas.</span><span class="sxs-lookup"><span data-stu-id="477b8-117">You must be an Exchange administrator or Global administrator in Microsoft 365 to do these steps.</span></span> <span data-ttu-id="477b8-118">Para obter mais informações, consulte o tópico [Sobre funções de administrador](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="477b8-118">For more information, see the topic [About admin roles](../add-users/about-admin-roles.md).</span></span>

1. <span data-ttu-id="477b8-119">No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=834822)**</span><span class="sxs-lookup"><span data-stu-id="477b8-119">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=834822)** page.</span></span>

2. <span data-ttu-id="477b8-120">Selecione o nome do usuário cujo email você deseja encaminhar e abra a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="477b8-120">Select the name of the user whose email you want to forward, then open the properties page.</span></span>

3. <span data-ttu-id="477b8-121">Na guia **Email,** selecione **Gerenciar encaminhamento de email**.</span><span class="sxs-lookup"><span data-stu-id="477b8-121">On the **Mail** tab, select **Manage email forwarding**.</span></span>

4. <span data-ttu-id="477b8-122">Na página de encaminhamento de email, selecione Encaminhar todos os **emails** enviados para essa caixa de correio, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="477b8-122">On the email forwarding page, select **Forward all emails sent to this mailbox**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="477b8-123">Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="477b8-123">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="477b8-124">Selecione **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="477b8-124">Select **Save changes**.</span></span>

    <span data-ttu-id="477b8-125">**Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="477b8-125">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="477b8-126">Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="477b8-126">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

     <span data-ttu-id="477b8-127">Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="477b8-127">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="477b8-128">Não exclua a conta do usuário que está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="477b8-128">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="477b8-129">Se você fizer isso, o encaminhamento de email será parado.</span><span class="sxs-lookup"><span data-stu-id="477b8-129">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="477b8-130">No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=847686)**</span><span class="sxs-lookup"><span data-stu-id="477b8-130">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=847686)** page.</span></span>

2. <span data-ttu-id="477b8-131">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="477b8-131">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="477b8-132">Expanda **configurações de** email e, em seguida, na seção **Encaminhamento de email,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="477b8-132">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="477b8-133">Na página de encaminhamento de email, de definir a alternância como **On**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="477b8-133">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="477b8-134">Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="477b8-134">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="477b8-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="477b8-135">Select **Save**.</span></span>

   <span data-ttu-id="477b8-136">**Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="477b8-136">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="477b8-137">Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="477b8-137">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="477b8-138">Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="477b8-138">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="477b8-139">Não exclua a conta do usuário que está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="477b8-139">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span>  <span data-ttu-id="477b8-140">Se você fizer isso, o encaminhamento de email será parado.</span><span class="sxs-lookup"><span data-stu-id="477b8-140">If you do, email forwarding will stop.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="477b8-141">No centro de administração, vá para a página **Usuários** \> **[Usuários ativos.](https://go.microsoft.com/fwlink/p/?linkid=850628)**</span><span class="sxs-lookup"><span data-stu-id="477b8-141">In the admin center, go to the **Users** \> **[Active users](https://go.microsoft.com/fwlink/p/?linkid=850628)** page.</span></span>

2. <span data-ttu-id="477b8-142">Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades.</span><span class="sxs-lookup"><span data-stu-id="477b8-142">Select the name of the user whose email you want to forward to open the properties page.</span></span>

3. <span data-ttu-id="477b8-143">Expanda **configurações de** email e, em seguida, na seção **Encaminhamento de email,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="477b8-143">Expand **Mail settings**, and then in the **Email forwarding** section, select **Edit**.</span></span>

4. <span data-ttu-id="477b8-144">Na página de encaminhamento de email, de definir a alternância como **On**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados.</span><span class="sxs-lookup"><span data-stu-id="477b8-144">On the email forwarding page, set the toggle to **On**, enter the forwarding address, and choose whether you want to keep a copy of forwarded emails.</span></span> <span data-ttu-id="477b8-145">Se você não vir essa opção, certifique-se de que uma licença seja atribuída à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="477b8-145">If you don't see this option, make sure a license is assigned to the user account.</span></span> <span data-ttu-id="477b8-146">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="477b8-146">Select **Save**.</span></span>

   <span data-ttu-id="477b8-147">**Para encaminhar para vários endereços de email,** você pode pedir ao usuário para configurar uma regra Outlook encaminhar para os endereços.</span><span class="sxs-lookup"><span data-stu-id="477b8-147">**To forward to multiple email addresses**, you can ask the user to set up a rule in Outlook to forward to the addresses.</span></span> <span data-ttu-id="477b8-148">Para saber mais, confira [Usar regras para encaminhar automaticamente mensagens](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span><span class="sxs-lookup"><span data-stu-id="477b8-148">To learn more, see [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).</span></span>

   <span data-ttu-id="477b8-149">Ou, no centro de administração, crie um grupo de [distribuição,](add-user-or-contact-to-distribution-list.md)adicione os endereços a ele e, em seguida, defina o encaminhamento para apontar para [a](../setup/create-distribution-lists.md)DL usando as instruções neste artigo.</span><span class="sxs-lookup"><span data-stu-id="477b8-149">Or, in the admin center, [create a distribution group](../setup/create-distribution-lists.md), [add the addresses to it](add-user-or-contact-to-distribution-list.md), and then set up forwarding to point to the DL using the instructions in this article.</span></span>

5. <span data-ttu-id="477b8-150">Não exclua a conta do usuário que está encaminhando ou remova sua licença!</span><span class="sxs-lookup"><span data-stu-id="477b8-150">Don't delete the account of the user who's email you're forwarding or remove their license!</span></span> <span data-ttu-id="477b8-151">Se você fizer isso, o encaminhamento de email será parado.</span><span class="sxs-lookup"><span data-stu-id="477b8-151">If you do, email forwarding will stop.</span></span>

::: moniker-end

## <a name="related-content"></a><span data-ttu-id="477b8-152">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="477b8-152">Related content</span></span> 

<span data-ttu-id="477b8-153">[Criar uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="477b8-153">[Create a shared mailbox](../email/create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="477b8-154">[Enviar email de um endereço](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) diferente (artigo)</span><span class="sxs-lookup"><span data-stu-id="477b8-154">[Send email from a different address](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)</span></span>\
<span data-ttu-id="477b8-155">[Alterar um nome de usuário e um endereço de email](../add-users/change-a-user-name-and-email-address.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="477b8-155">[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)</span></span>
