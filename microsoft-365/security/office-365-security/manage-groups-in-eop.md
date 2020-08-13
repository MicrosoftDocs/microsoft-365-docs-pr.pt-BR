---
title: Gerenciar grupos no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administradores no proteção autônoma do Exchange Online (EOP) as organizações podem aprender a criar, modificar e remover grupos de distribuição e grupos de segurança habilitados para email no centro de administração do Exchange (Eat) e no PowerShell autônomo do Exchange Online Protection (EOP).
ms.openlocfilehash: 813735d4024c3b8424a6bbac51ebef7b4c53e590
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653648"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="73848-103">Gerenciar grupos no EOP</span><span class="sxs-lookup"><span data-stu-id="73848-103">Manage groups in EOP</span></span>

<span data-ttu-id="73848-104">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode criar, modificar e remover os seguintes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="73848-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="73848-105">**Grupos de distribuição**: uma coleção de usuários de email ou outros grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="73848-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="73848-106">Por exemplo, equipes ou outros grupos ad hoc que precisam receber ou enviar emails em uma área comum de interesse.</span><span class="sxs-lookup"><span data-stu-id="73848-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="73848-107">Os grupos de distribuição são exclusivamente para distribuir mensagens de email e não são entidades de segurança (elas não podem ter permissões atribuídas a eles).</span><span class="sxs-lookup"><span data-stu-id="73848-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="73848-108">**Grupos de segurança habilitados para email**: uma coleção de usuários de email e outros grupos de segurança que precisam de permissões de acesso para funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="73848-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="73848-109">Por exemplo, você pode querer conceder permissões de administrador de grupo específico de usuários para que eles possam definir configurações antispam e antimalware.</span><span class="sxs-lookup"><span data-stu-id="73848-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    >
    > - <span data-ttu-id="73848-110">Por padrão, novos grupos de segurança habilitados para email rejeitam mensagens de remetentes externos (não autenticados).</span><span class="sxs-lookup"><span data-stu-id="73848-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span>
    >
    > - <span data-ttu-id="73848-111">Não adicione grupos de distribuição a grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="73848-111">Don't add distribution groups to mail-enabled security groups.</span></span>

<span data-ttu-id="73848-112">Você pode gerenciar grupos no centro de administração do Exchange (Eat) e no PowerShell do EOP autônomo.</span><span class="sxs-lookup"><span data-stu-id="73848-112">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73848-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="73848-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73848-114">Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="73848-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="73848-115">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="73848-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="73848-116">Ao gerenciar grupos no EOP PowerShell autônomo, você pode encontrar limitação.</span><span class="sxs-lookup"><span data-stu-id="73848-116">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="73848-117">Os procedimentos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="73848-117">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="73848-118">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="73848-118">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="73848-119">Especificamente, você precisa da função grupos de distribuição, que é atribuída aos grupos de função gerenciamento (administradores globais) e RecipientManagement por padrão.</span><span class="sxs-lookup"><span data-stu-id="73848-119">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="73848-120">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="73848-120">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="73848-121">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="73848-121">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="73848-122">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="73848-122">Having problems?</span></span> <span data-ttu-id="73848-123">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="73848-123">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="73848-124">Usar o centro de administração do Exchange para gerenciar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="73848-124">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="73848-125">Usar o Eat para criar grupos</span><span class="sxs-lookup"><span data-stu-id="73848-125">Use the EAC to create groups</span></span>

1. <span data-ttu-id="73848-126">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="73848-126">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="73848-127">Clique em **novo** ![ ícone novo ](../../media/ITPro-EAC-AddIcon.png) e selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="73848-127">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="73848-128">**Grupo de distribuição**</span><span class="sxs-lookup"><span data-stu-id="73848-128">**Distribution group**</span></span>

   - <span data-ttu-id="73848-129">**Grupo de segurança habilitado para email**</span><span class="sxs-lookup"><span data-stu-id="73848-129">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="73848-130">Na página novo grupo que é aberta, defina as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="73848-130">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="73848-131">As configurações marcadas com um <sup>\*</sup> são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="73848-131">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="73848-132"><sup>\*</sup>**Nome para exibição**: esse nome é exibido no catálogo de endereços da sua organização, na linha para: quando o email é enviado a esse grupo e na lista de **grupos** no Eat.</span><span class="sxs-lookup"><span data-stu-id="73848-132"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="73848-133">O nome para exibição é necessário, deve ser exclusivo e ser intuitivo para o usuário, para que as pessoas reconheçam o que é.</span><span class="sxs-lookup"><span data-stu-id="73848-133">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="73848-134"><sup>\*</sup>**Alias**: Use esta caixa para digitar o nome do alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-134"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="73848-135">O alias não pode exceder 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="73848-135">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="73848-136">Quando um usuário digita o alias na linha para de uma mensagem de email, ele é resolvido como o nome de exibição do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-136">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="73848-137"><sup>\*</sup>**Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="73848-137"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="73848-138">Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="73848-138">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="73848-139">Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.</span><span class="sxs-lookup"><span data-stu-id="73848-139">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="73848-140">**Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.</span><span class="sxs-lookup"><span data-stu-id="73848-140">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="73848-141"><sup>\*</sup>**Proprietários**: um proprietário de grupo pode gerenciar A Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-141"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="73848-142">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="73848-142">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="73848-143">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="73848-143">All groups must have at least one owner.</span></span>

     <span data-ttu-id="73848-144">Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73848-144">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="73848-145">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="73848-145">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="73848-146">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="73848-146">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="73848-147">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73848-147">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="73848-148">Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="73848-148">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="73848-149">**Membros**: Adicionar e remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-149">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="73848-150">Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73848-150">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="73848-151">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="73848-151">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="73848-152">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="73848-152">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="73848-153">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73848-153">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="73848-154">Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="73848-154">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="73848-155">Quando tiver terminado, clique em **salvar** para criar o grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="73848-155">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="73848-156">Usar o Eat para modificar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="73848-156">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="73848-157">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="73848-157">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="73848-158">Na lista de grupos, selecione o grupo de distribuição ou grupo de segurança habilitado para email que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73848-158">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="73848-159">Na página de propriedades do grupo de distribuição que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.</span><span class="sxs-lookup"><span data-stu-id="73848-159">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="73848-160">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73848-160">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="73848-161">Geral</span><span class="sxs-lookup"><span data-stu-id="73848-161">General</span></span>

<span data-ttu-id="73848-162">Use essa guia para exibir ou alterar as informações básicas sobre o grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-162">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="73848-163">**Nome para exibição**: esse nome é exibido no catálogo de endereços, na linha para quando o email é enviado a esse grupo e na **lista de grupos**.</span><span class="sxs-lookup"><span data-stu-id="73848-163">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="73848-164">O nome para exibição é necessário e deve ser amigável para que as pessoas o reconheçam.</span><span class="sxs-lookup"><span data-stu-id="73848-164">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="73848-165">Ele também deve ser exclusivo em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="73848-165">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="73848-166">Se você implementou uma política de nomeação de grupo, o nome para exibição terá que estar em conformidade com o formato de nomeação definido pela política.</span><span class="sxs-lookup"><span data-stu-id="73848-166">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="73848-167">**Alias**: esta é a parte do endereço de email que aparece à esquerda do símbolo de arroba (@).</span><span class="sxs-lookup"><span data-stu-id="73848-167">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="73848-168">Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias.</span><span class="sxs-lookup"><span data-stu-id="73848-168">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="73848-169">Além disso, o endereço de email com o alias anterior será mantido como um endereço proxy para o grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-169">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="73848-170">**Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="73848-170">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="73848-171">Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="73848-171">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="73848-172">Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.</span><span class="sxs-lookup"><span data-stu-id="73848-172">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="73848-173">**Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.</span><span class="sxs-lookup"><span data-stu-id="73848-173">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="73848-174">Propriedade</span><span class="sxs-lookup"><span data-stu-id="73848-174">Ownership</span></span>

<span data-ttu-id="73848-175">Use esta guia para atribuir proprietários de grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-175">Use this tab to assign group owners.</span></span> <span data-ttu-id="73848-176">Um proprietário de grupo pode gerenciar A Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-176">A group owner can manage group membership.</span></span> <span data-ttu-id="73848-177">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="73848-177">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="73848-178">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="73848-178">All groups must have at least one owner.</span></span>

<span data-ttu-id="73848-179">Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73848-179">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="73848-180">Na caixa de diálogo exibida, localize e selecione um destinatário e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="73848-180">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="73848-181">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="73848-181">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="73848-182">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73848-182">When you're finished, click **OK**.</span></span>

<span data-ttu-id="73848-183">Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="73848-183">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="73848-184">Associação</span><span class="sxs-lookup"><span data-stu-id="73848-184">Membership</span></span>

<span data-ttu-id="73848-185">Use esta guia para adicionar ou remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-185">Use this tab to add or remove group members.</span></span> <span data-ttu-id="73848-186">Os proprietários do grupo não precisam ser membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-186">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="73848-187">Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="73848-187">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="73848-188">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="73848-188">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="73848-189">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="73848-189">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="73848-190">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73848-190">When you're finished, click **OK**.</span></span>

<span data-ttu-id="73848-191">Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="73848-191">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="73848-192">Usar o Eat para remover grupos</span><span class="sxs-lookup"><span data-stu-id="73848-192">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="73848-193">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="73848-193">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="73848-194">Na lista de grupos, selecione o grupo de distribuição que você deseja remover e clique em **remover** ![ ícone de remoção ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="73848-194">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="73848-195">Usar o PowerShell para gerenciar grupos</span><span class="sxs-lookup"><span data-stu-id="73848-195">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="73848-196">Usar o EOP PowerShell autônomo para exibir grupos</span><span class="sxs-lookup"><span data-stu-id="73848-196">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="73848-197">Para retornar uma lista resumida de todos os grupos de distribuição e grupos de segurança habilitados para email no PowerShell autônomo do EOP, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="73848-197">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="73848-198">Para retornar a lista de membros do grupo, substitua-o \<GroupIdentity\> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="73848-198">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="73848-199">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="73848-199">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="73848-200">Usar o EOP PowerShell autônomo para criar grupos</span><span class="sxs-lookup"><span data-stu-id="73848-200">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="73848-201">Para criar grupos de distribuição ou grupos de segurança habilitados para email no PowerShell autônomo do EOP, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="73848-201">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="73848-202">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="73848-202">**Notes**:</span></span>

- <span data-ttu-id="73848-203">O parâmetro _Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="73848-203">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="73848-204">Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="73848-204">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="73848-205">Se você não usar o parâmetro _alias_ , o parâmetro _Name_ será usado para o valor do alias.</span><span class="sxs-lookup"><span data-stu-id="73848-205">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="73848-206">Os espaços são removidos e os caracteres não suportados são convertidos em pontos de interrogação (?).</span><span class="sxs-lookup"><span data-stu-id="73848-206">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="73848-207">Se você não usar o parâmetro _PrimarySmtpAddress_ , o valor do alias será usado no parâmetro _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="73848-207">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="73848-208">Se você não usar o parâmetro _Type_ , o valor padrão será Distribution.</span><span class="sxs-lookup"><span data-stu-id="73848-208">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="73848-209">Este exemplo cria um grupo de distribuição chamado administradores de ti com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="73848-209">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="73848-210">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="73848-210">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="73848-211">Usar o EOP PowerShell autônomo para modificar grupos</span><span class="sxs-lookup"><span data-stu-id="73848-211">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="73848-212">Para modificar grupos no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="73848-212">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="73848-213">Este exemplo usa as alterações do endereço SMTP principal (também chamado de endereço de resposta) do grupo de Seattle Employees para sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="73848-213">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="73848-214">Este exemplo substitui os membros atuais do grupo equipe de segurança por Kitty Petersen e Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="73848-214">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="73848-215">Este exemplo adiciona um novo usuário chamado Tyson Fawcett ao grupo chamado equipe de segurança enquanto preserva os membros atuais do grupo.</span><span class="sxs-lookup"><span data-stu-id="73848-215">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="73848-216">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="73848-216">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="73848-217">Remover um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="73848-217">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="73848-218">Este exemplo usa remove o grupo de distribuição chamado administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="73848-218">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="73848-219">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="73848-219">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="73848-220">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="73848-220">How do you know these procedures worked?</span></span>

<span data-ttu-id="73848-221">Para verificar se você criou, modificou ou removeu com êxito um grupo de distribuição ou um grupo de segurança habilitado para email, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="73848-221">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="73848-222">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="73848-222">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="73848-223">Verifique se o grupo está listado (ou não listado) e verifique o valor do **tipo de grupo** .</span><span class="sxs-lookup"><span data-stu-id="73848-223">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="73848-224">Selecione o grupo e visualize as informações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) para exibir as configurações.</span><span class="sxs-lookup"><span data-stu-id="73848-224">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="73848-225">Em EOP autônomo do PowerShell, execute o seguinte comando para verificar se o grupo está listado (ou não está listado):</span><span class="sxs-lookup"><span data-stu-id="73848-225">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="73848-226">Substitua \<GroupIdentity\> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="73848-226">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="73848-227">Para exibir os membros do grupo, substitua o \<GroupIdentity\> nome, o alias ou o endereço de email do grupo e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="73848-227">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
