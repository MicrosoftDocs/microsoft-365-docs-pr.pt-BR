---
title: Gerenciar grupos no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Os administradores em organizações autônomas do Exchange Online Protection (EOP) podem aprender a criar, modificar e remover grupos de distribuição e grupos de segurança habilitados para email no Centro de administração do Exchange (EAC) e no PowerShell do Exchange Online Protection (EOP) autônomo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d03b8a5129eb3b070f30de46b9b9c7bcc8e9898d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286796"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="1698c-103">Gerenciar grupos no EOP</span><span class="sxs-lookup"><span data-stu-id="1698c-103">Manage groups in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1698c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="1698c-104">**Applies to**</span></span>
-  [<span data-ttu-id="1698c-105">Proteção do Exchange Online autônoma</span><span class="sxs-lookup"><span data-stu-id="1698c-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="1698c-106">Em organizações autônomas do Proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, você pode criar, modificar e remover os seguintes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="1698c-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="1698c-107">**Grupos de distribuição:** uma coleção de usuários de email ou outros grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="1698c-107">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="1698c-108">Por exemplo, equipes ou outros grupos ad hoc que precisam receber ou enviar emails em uma área comum de interesse.</span><span class="sxs-lookup"><span data-stu-id="1698c-108">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="1698c-109">Os grupos de distribuição são exclusivamente para distribuir mensagens de email e não são entidades de segurança (eles não podem ter permissões atribuídas a eles).</span><span class="sxs-lookup"><span data-stu-id="1698c-109">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="1698c-110">**Grupos de segurança habilitados para email:** uma coleção de usuários de email e outros grupos de segurança que precisam de permissões de acesso para funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="1698c-110">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="1698c-111">Por exemplo, talvez você queira dar permissões de administrador a um grupo específico de usuários para que eles possam definir configurações anti-spam e anti-malware.</span><span class="sxs-lookup"><span data-stu-id="1698c-111">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="1698c-112">Por padrão, novos grupos de segurança habilitados para email rejeitam mensagens de envios externos (não autenticados).</span><span class="sxs-lookup"><span data-stu-id="1698c-112">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="1698c-113">Não adicione grupos de distribuição a grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="1698c-113">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="1698c-114">Você pode gerenciar grupos no Centro de administração do Exchange (EAC) e no EOP PowerShell autônomo.</span><span class="sxs-lookup"><span data-stu-id="1698c-114">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1698c-115">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="1698c-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1698c-116">Para abrir o Centro de administração do Exchange, confira o Centro de administração [do Exchange no EOP autônomo.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="1698c-116">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="1698c-117">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="1698c-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="1698c-118">Ao gerenciar grupos no PowerShell do EOP autônomo, você pode encontrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="1698c-118">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="1698c-119">Os procedimentos do PowerShell neste artigo usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos sejam visíveis.</span><span class="sxs-lookup"><span data-stu-id="1698c-119">The PowerShell procedures in this article use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="1698c-120">Para fazer os procedimentos deste artigo, você precisa ter permissões no Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="1698c-120">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="1698c-121">Especificamente, você precisa da função **Grupos de**  Distribuição,  que é atribuída aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão.</span><span class="sxs-lookup"><span data-stu-id="1698c-121">Specifically, you need the **Distribution Groups** role, which is assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="1698c-122">Para obter mais informações, [consulte Permissões no EOP](feature-permissions-in-eop.md) autônomo e use o EAC modificar a lista de [membros em grupos de função.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="1698c-122">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="1698c-123">Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o Centro de administração do Exchange no Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="1698c-123">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="1698c-124">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="1698c-124">Having problems?</span></span> <span data-ttu-id="1698c-125">Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="1698c-125">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="1698c-126">Usar o Centro de administração do Exchange para gerenciar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="1698c-126">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="1698c-127">Usar o EAC para criar grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-127">Use the EAC to create groups</span></span>

1. <span data-ttu-id="1698c-128">No EAC, vá para Grupos **de** \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="1698c-128">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1698c-129">Clique **em** ![ Novo ícone Novo e selecione uma das seguintes ](../../media/ITPro-EAC-AddIcon.png) opções:</span><span class="sxs-lookup"><span data-stu-id="1698c-129">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="1698c-130">**Grupo de distribuição**</span><span class="sxs-lookup"><span data-stu-id="1698c-130">**Distribution group**</span></span>

   - <span data-ttu-id="1698c-131">**Grupo de segurança habilitado para email**</span><span class="sxs-lookup"><span data-stu-id="1698c-131">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="1698c-132">Na nova página de grupo que é aberta, de configure as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="1698c-132">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="1698c-133">As configurações marcadas com <sup>\*</sup> um são necessárias.</span><span class="sxs-lookup"><span data-stu-id="1698c-133">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="1698c-134"><sup>\*</sup>**Nome para** exibição: esse nome aparece no livro de endereços da sua organização,  na linha Para: quando o email é enviado para esse grupo e na lista Grupos no EAC.</span><span class="sxs-lookup"><span data-stu-id="1698c-134"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="1698c-135">O nome de exibição é obrigatório, deve ser exclusivo e deve ser amigável para que as pessoas reconheçam o que é.</span><span class="sxs-lookup"><span data-stu-id="1698c-135">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="1698c-136"><sup>\*</sup>**Alias:** Use essa caixa para digitar o nome do alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-136"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="1698c-137">O alias não pode exceder 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1698c-137">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="1698c-138">Quando um usuário digita o alias na linha Para de uma mensagem de email, ele é resolvido para o nome de exibição do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-138">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="1698c-139"><sup>\*</sup>**Endereço de** email : O endereço de email consiste no alias à esquerda do símbolo de aa (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="1698c-139"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="1698c-140">Por padrão, o valor de **Alias** é usado para o valor de alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="1698c-140">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="1698c-141">Para o valor do domínio, clique no drop down e selecione e aceite o domínio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1698c-141">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="1698c-142">**Descrição:** essa descrição aparece no livro de endereços e no painel Detalhes do EAC.</span><span class="sxs-lookup"><span data-stu-id="1698c-142">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="1698c-143"><sup>\*</sup>**Proprietários:** um proprietário de grupo pode gerenciar a associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-143"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="1698c-144">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="1698c-144">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="1698c-145">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="1698c-145">All groups must have at least one owner.</span></span>

     <span data-ttu-id="1698c-146">Para adicionar proprietários, clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1698c-146">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1698c-147">Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique em **add ->**.</span><span class="sxs-lookup"><span data-stu-id="1698c-147">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1698c-148">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="1698c-148">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1698c-149">Quando terminar, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="1698c-149">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="1698c-150">Para remover um proprietário, selecione o  proprietário e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="1698c-150">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="1698c-151">**Membros:** Adicionar e remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-151">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="1698c-152">Para adicionar membros, clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1698c-152">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1698c-153">Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique em **add ->**.</span><span class="sxs-lookup"><span data-stu-id="1698c-153">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1698c-154">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="1698c-154">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1698c-155">Quando terminar, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="1698c-155">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="1698c-156">Para remover um membro, selecione o  membro e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="1698c-156">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="1698c-157">Quando terminar, clique em **Salvar para** criar o grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="1698c-157">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="1698c-158">Usar o EAC para modificar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="1698c-158">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="1698c-159">No EAC, vá para Grupos **de** \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="1698c-159">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1698c-160">Na lista de grupos, selecione o grupo de distribuição ou grupo de segurança habilitado para email que você deseja modificar e clique em **Editar** ![ ](../../media/ITPro-EAC-AddIcon.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="1698c-160">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="1698c-161">Na página de propriedades do grupo de distribuição que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.</span><span class="sxs-lookup"><span data-stu-id="1698c-161">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="1698c-162">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1698c-162">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="1698c-163">Geral</span><span class="sxs-lookup"><span data-stu-id="1698c-163">General</span></span>

<span data-ttu-id="1698c-164">Use esta guia para exibir ou alterar informações básicas sobre o grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-164">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="1698c-165">**Nome para** exibição: esse nome aparece no livro de endereços, na linha Para quando o email é enviado a esse grupo e na lista **Grupos.**</span><span class="sxs-lookup"><span data-stu-id="1698c-165">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="1698c-166">O nome para exibição é necessário e deve ser amigável para que as pessoas o reconheçam.</span><span class="sxs-lookup"><span data-stu-id="1698c-166">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="1698c-167">Ele também deve ser exclusivo em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="1698c-167">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="1698c-168">Se você implementou uma política de nomeação de grupo, o nome para exibição terá que estar em conformidade com o formato de nomeação definido pela política.</span><span class="sxs-lookup"><span data-stu-id="1698c-168">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="1698c-169">**Alias:** esta é a parte do endereço de email que aparece à esquerda do símbolo de aa (@).</span><span class="sxs-lookup"><span data-stu-id="1698c-169">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="1698c-170">Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias.</span><span class="sxs-lookup"><span data-stu-id="1698c-170">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="1698c-171">Além disso, o endereço de email com o alias anterior será mantido como um endereço proxy para o grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-171">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="1698c-172">**Endereço de** email : O endereço de email consiste no alias à esquerda do símbolo de aa (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="1698c-172">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="1698c-173">Por padrão, o valor de **Alias** é usado para o valor de alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="1698c-173">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="1698c-174">Para o valor do domínio, clique no drop down e selecione e aceite o domínio em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1698c-174">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="1698c-175">**Descrição:** essa descrição aparece no livro de endereços e no painel Detalhes do EAC.</span><span class="sxs-lookup"><span data-stu-id="1698c-175">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="1698c-176">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1698c-176">Ownership</span></span>

<span data-ttu-id="1698c-177">Use esta guia para atribuir proprietários do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-177">Use this tab to assign group owners.</span></span> <span data-ttu-id="1698c-178">Um proprietário de grupo pode gerenciar a associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-178">A group owner can manage group membership.</span></span> <span data-ttu-id="1698c-179">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="1698c-179">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="1698c-180">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="1698c-180">All groups must have at least one owner.</span></span>

<span data-ttu-id="1698c-181">Para adicionar proprietários, clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1698c-181">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1698c-182">Na caixa de diálogo exibida, encontre e selecione um destinatário e clique **em add ->**.</span><span class="sxs-lookup"><span data-stu-id="1698c-182">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="1698c-183">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="1698c-183">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1698c-184">Quando terminar, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="1698c-184">When you're finished, click **OK**.</span></span>

<span data-ttu-id="1698c-185">Para remover um proprietário, selecione o  proprietário e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="1698c-185">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="1698c-186">Associação</span><span class="sxs-lookup"><span data-stu-id="1698c-186">Membership</span></span>

<span data-ttu-id="1698c-187">Use esta guia para adicionar ou remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-187">Use this tab to add or remove group members.</span></span> <span data-ttu-id="1698c-188">Os proprietários do grupo não precisam ser membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-188">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="1698c-189">Para adicionar membros, clique **no ícone** ![ ](../../media/ITPro-EAC-AddIcon.png) Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1698c-189">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="1698c-190">Na caixa de diálogo exibida, encontre e selecione um destinatário ou grupo e clique em **add ->**.</span><span class="sxs-lookup"><span data-stu-id="1698c-190">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="1698c-191">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="1698c-191">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="1698c-192">Quando terminar, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="1698c-192">When you're finished, click **OK**.</span></span>

<span data-ttu-id="1698c-193">Para remover um membro, selecione o  membro e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="1698c-193">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="1698c-194">Usar o EAC para remover grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-194">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="1698c-195">No EAC, vá para Grupos **de** \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="1698c-195">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="1698c-196">Na lista de grupos, selecione o grupo de distribuição  que você deseja remover e clique no ícone ![ ](../../media/ITPro-EAC-RemoveIcon.gif) Remover.</span><span class="sxs-lookup"><span data-stu-id="1698c-196">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="1698c-197">Usar o PowerShell para gerenciar grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-197">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="1698c-198">Usar o EOP PowerShell autônomo para exibir grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-198">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="1698c-199">Para retornar uma lista resumida de todos os grupos de distribuição e grupos de segurança habilitados para email no EOP PowerShell autônomo, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1698c-199">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="1698c-200">Para retornar a lista de membros do grupo, substitua pelo nome, alias ou endereço de email do grupo e \<GroupIdentity\> execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1698c-200">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="1698c-201">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="1698c-201">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="1698c-202">Usar o EOP PowerShell autônomo para criar grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-202">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="1698c-203">Para criar grupos de distribuição ou grupos de segurança habilitados para email no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1698c-203">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="1698c-204">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="1698c-204">**Notes**:</span></span>

- <span data-ttu-id="1698c-205">O _parâmetro Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1698c-205">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="1698c-206">Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="1698c-206">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="1698c-207">Se você não usar o parâmetro _Alias,_ o parâmetro _Name_ será usado para o valor de alias.</span><span class="sxs-lookup"><span data-stu-id="1698c-207">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="1698c-208">Os espaços são removidos e os caracteres sem suporte são convertidos em pontos de interrogação (?).</span><span class="sxs-lookup"><span data-stu-id="1698c-208">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="1698c-209">Se você não usar o _parâmetro PrimarySmtpAddress,_ o valor do alias será usado no _parâmetro PrimarySmtpAddress._</span><span class="sxs-lookup"><span data-stu-id="1698c-209">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="1698c-210">Se você não usar o parâmetro _Type,_ o valor padrão será Distribution.</span><span class="sxs-lookup"><span data-stu-id="1698c-210">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="1698c-211">Este exemplo cria um grupo de distribuição chamado Administradores de IT com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="1698c-211">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="1698c-212">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="1698c-212">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="1698c-213">Usar o EOP PowerShell autônomo para modificar grupos</span><span class="sxs-lookup"><span data-stu-id="1698c-213">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="1698c-214">Para modificar grupos no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="1698c-214">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="1698c-215">Este exemplo usa alterações no endereço SMTP principal (também chamado de endereço de resposta) para o grupo Funcionários de Seattle sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1698c-215">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

<span data-ttu-id="1698c-216">Este exemplo substitui os membros atuais do grupo Equipe de Segurança por Kitty Petersen e Peter Fawcett.</span><span class="sxs-lookup"><span data-stu-id="1698c-216">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="1698c-217">Este exemplo adiciona um novo usuário chamado Faba Fawcett ao grupo chamado Equipe de Segurança, preservando os membros atuais do grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-217">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="1698c-218">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="1698c-218">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="1698c-219">Remover um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="1698c-219">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="1698c-220">Este exemplo usa o grupo de distribuição chamado Administradores de IT.</span><span class="sxs-lookup"><span data-stu-id="1698c-220">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="1698c-221">Para informações detalhadas de sintaxes e de parâmetros, [consulte Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="1698c-221">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="1698c-222">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="1698c-222">How do you know these procedures worked?</span></span>

<span data-ttu-id="1698c-223">Para verificar se você criou, modificou ou removeu com êxito um grupo de distribuição ou um grupo de segurança habilitado para email, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="1698c-223">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="1698c-224">No EAC, vá para Grupos **de** \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="1698c-224">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="1698c-225">Verifique se o grupo está listado (ou não listado) e verifique o valor **de Tipo de** Grupo.</span><span class="sxs-lookup"><span data-stu-id="1698c-225">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="1698c-226">Selecione o grupo e veja as informações no  painel Detalhes ou clique no ícone ![ Editar para exibir as ](../../media/ITPro-EAC-AddIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="1698c-226">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="1698c-227">No EOP PowerShell autônomo, execute o seguinte comando para verificar se o grupo está listado (ou não está listado):</span><span class="sxs-lookup"><span data-stu-id="1698c-227">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="1698c-228">Substitua pelo nome, alias ou endereço de email do grupo e \<GroupIdentity\> execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="1698c-228">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="1698c-229">Para exibir os membros do grupo, substitua pelo nome, alias ou endereço de email do grupo \<GroupIdentity\> e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1698c-229">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
