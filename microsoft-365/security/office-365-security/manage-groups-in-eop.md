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
ms.openlocfilehash: fc3f3807216b269a9868e87c5ec784d75385f878
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209014"
---
# <a name="manage-groups-in-eop"></a><span data-ttu-id="4736c-103">Gerenciar grupos no EOP</span><span class="sxs-lookup"><span data-stu-id="4736c-103">Manage groups in EOP</span></span>

<span data-ttu-id="4736c-104">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode criar, modificar e remover os seguintes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="4736c-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can create, modify, and remove the following types of groups:</span></span>

- <span data-ttu-id="4736c-105">**Grupos de distribuição**: uma coleção de usuários de email ou outros grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4736c-105">**Distribution groups**: A collection of mail users or other distribution groups.</span></span> <span data-ttu-id="4736c-106">Por exemplo, equipes ou outros grupos ad hoc que precisam receber ou enviar emails em uma área comum de interesse.</span><span class="sxs-lookup"><span data-stu-id="4736c-106">For example, teams or other ad hoc groups who need to receive or send email in a common area of interest.</span></span> <span data-ttu-id="4736c-107">Os grupos de distribuição são exclusivamente para distribuir mensagens de email e não são entidades de segurança (elas não podem ter permissões atribuídas a eles).</span><span class="sxs-lookup"><span data-stu-id="4736c-107">Distribution groups are exclusively for distributing email messages, and are not security principals (they can't have permissions assigned to them).</span></span>

- <span data-ttu-id="4736c-108">**Grupos de segurança habilitados para email**: uma coleção de usuários de email e outros grupos de segurança que precisam de permissões de acesso para funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="4736c-108">**Mail-enabled security groups**: A collection of mail users and other security groups who need access permissions for admin roles.</span></span> <span data-ttu-id="4736c-109">Por exemplo, você pode querer conceder permissões de administrador de grupo específico de usuários para que eles possam definir configurações antispam e antimalware.</span><span class="sxs-lookup"><span data-stu-id="4736c-109">For example, you might want to give specific group of users admin permissions so they can configure anti-spam and anti-malware settings.</span></span>

    > [!NOTE]
    > <ul><li><span data-ttu-id="4736c-110">Por padrão, novos grupos de segurança habilitados para email rejeitam mensagens de remetentes externos (não autenticados).</span><span class="sxs-lookup"><span data-stu-id="4736c-110">By default, new mail-enabled security groups reject messages from external (unauthenticated) senders.</span></span></li><li><span data-ttu-id="4736c-111">Não adicione grupos de distribuição a grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="4736c-111">Don't add distribution groups to mail-enabled security groups.</span></span></li></ul><span data-ttu-id="4736c-112">.</span><span class="sxs-lookup"><span data-stu-id="4736c-112">.</span></span>

<span data-ttu-id="4736c-113">Você pode gerenciar grupos no centro de administração do Exchange (Eat) e no PowerShell do EOP autônomo.</span><span class="sxs-lookup"><span data-stu-id="4736c-113">You can manage groups in the Exchange admin center (EAC) and in standalone EOP PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4736c-114">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="4736c-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4736c-115">Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="4736c-115">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="4736c-116">Para se conectar ao PowerShell do EOP autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4736c-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4736c-117">Ao gerenciar grupos no EOP PowerShell autônomo, você pode encontrar limitação.</span><span class="sxs-lookup"><span data-stu-id="4736c-117">When you manage groups in standalone EOP PowerShell, you might encounter throttling.</span></span> <span data-ttu-id="4736c-118">Os procedimentos do PowerShell neste tópico usam um método de processamento em lotes que resulta em um atraso de propagação de alguns minutos antes que os resultados dos comandos fiquem visíveis.</span><span class="sxs-lookup"><span data-stu-id="4736c-118">The PowerShell procedures in this topic use a batch processing method that results in a propagation delay of a few minutes before the results of the commands are visible.</span></span>

- <span data-ttu-id="4736c-119">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="4736c-119">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="4736c-120">Especificamente, você precisa da função grupos de distribuição, que é atribuída aos grupos de função gerenciamento (administradores globais) e RecipientManagement por padrão.</span><span class="sxs-lookup"><span data-stu-id="4736c-120">Specifically, you need the Distribution Groups role, which is assigned to the OrganizationManagement (global admins) and RecipientManagement role groups by default.</span></span> <span data-ttu-id="4736c-121">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="4736c-121">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="4736c-122">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4736c-122">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="4736c-123">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="4736c-123">Having problems?</span></span> <span data-ttu-id="4736c-124">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="4736c-124">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a><span data-ttu-id="4736c-125">Usar o centro de administração do Exchange para gerenciar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="4736c-125">Use the Exchange admin center to manage distribution groups</span></span>

### <a name="use-the-eac-to-create-groups"></a><span data-ttu-id="4736c-126">Usar o Eat para criar grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-126">Use the EAC to create groups</span></span>

1. <span data-ttu-id="4736c-127">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="4736c-127">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="4736c-128">Clique em **novo** ![ ícone novo ](../../media/ITPro-EAC-AddIcon.png) e selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4736c-128">Click **New** ![New icon](../../media/ITPro-EAC-AddIcon.png), and then select one of the following options:</span></span>

   - <span data-ttu-id="4736c-129">**Grupo de distribuição**</span><span class="sxs-lookup"><span data-stu-id="4736c-129">**Distribution group**</span></span>

   - <span data-ttu-id="4736c-130">**Grupo de segurança habilitado para email**</span><span class="sxs-lookup"><span data-stu-id="4736c-130">**Mail-enabled security group**</span></span>

3. <span data-ttu-id="4736c-131">Na página novo grupo que é aberta, defina as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="4736c-131">In the new group page that opens, configure the following settings.</span></span> <span data-ttu-id="4736c-132">As configurações marcadas com um <sup>\*</sup> são obrigatórias.</span><span class="sxs-lookup"><span data-stu-id="4736c-132">Settings marked with an <sup>\*</sup> are required.</span></span>

   - <span data-ttu-id="4736c-133"><sup>\*</sup>**Nome para exibição**: esse nome é exibido no catálogo de endereços da sua organização, na linha para: quando o email é enviado a esse grupo e na lista de **grupos** no Eat.</span><span class="sxs-lookup"><span data-stu-id="4736c-133"><sup>\*</sup>**Display name**: This name appears in your organization's address book, on the To: line when email is sent to this group, and in the **Groups** list in the EAC.</span></span> <span data-ttu-id="4736c-134">O nome para exibição é necessário, deve ser exclusivo e ser intuitivo para o usuário, para que as pessoas reconheçam o que é.</span><span class="sxs-lookup"><span data-stu-id="4736c-134">The display name is required, must be unique, and should be user-friendly so people recognize what it is.</span></span>

   - <span data-ttu-id="4736c-135"><sup>\*</sup>**Alias**: Use esta caixa para digitar o nome do alias do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-135"><sup>\*</sup>**Alias**: Use this box to type the name of the alias for the group.</span></span> <span data-ttu-id="4736c-136">O alias não pode exceder 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4736c-136">The alias can't exceed 64 characters and must be unique.</span></span> <span data-ttu-id="4736c-137">Quando um usuário digita o alias na linha para de uma mensagem de email, ele é resolvido como o nome de exibição do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-137">When a user types the alias in the To line of an email message, it resolves to the group's display name.</span></span>

   - <span data-ttu-id="4736c-138"><sup>\*</sup>**Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="4736c-138"><sup>\*</sup>**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="4736c-139">Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="4736c-139">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="4736c-140">Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4736c-140">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

   - <span data-ttu-id="4736c-141">**Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.</span><span class="sxs-lookup"><span data-stu-id="4736c-141">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

   - <span data-ttu-id="4736c-142"><sup>\*</sup>**Proprietários**: um proprietário de grupo pode gerenciar A Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-142"><sup>\*</sup>**Owners**: A group owner can manage group membership.</span></span> <span data-ttu-id="4736c-143">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="4736c-143">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="4736c-144">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="4736c-144">All groups must have at least one owner.</span></span>

     <span data-ttu-id="4736c-145">Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4736c-145">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4736c-146">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="4736c-146">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="4736c-147">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="4736c-147">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4736c-148">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4736c-148">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="4736c-149">Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4736c-149">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

   - <span data-ttu-id="4736c-150">**Membros**: Adicionar e remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-150">**Members**: Add and remove group members.</span></span>

     <span data-ttu-id="4736c-151">Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4736c-151">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4736c-152">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="4736c-152">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="4736c-153">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="4736c-153">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4736c-154">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4736c-154">When you're finished, click **OK**.</span></span>

     <span data-ttu-id="4736c-155">Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4736c-155">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

4. <span data-ttu-id="4736c-156">Quando tiver terminado, clique em **salvar** para criar o grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4736c-156">When you're finished, click **Save** to create the distribution group.</span></span>

### <a name="use-the-eac-to-modify-distribution-groups"></a><span data-ttu-id="4736c-157">Usar o Eat para modificar grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="4736c-157">Use the EAC to modify distribution groups</span></span>

1. <span data-ttu-id="4736c-158">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="4736c-158">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="4736c-159">Na lista de grupos, selecione o grupo de distribuição ou grupo de segurança habilitado para email que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4736c-159">In the list of groups, select the distribution group or mail-enabled security group that you want to modify, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png).</span></span>

3. <span data-ttu-id="4736c-160">Na página de propriedades do grupo de distribuição que é aberta, clique em uma das guias a seguir para exibir ou alterar propriedades.</span><span class="sxs-lookup"><span data-stu-id="4736c-160">On the distribution group properties page that opens, click one of the following tabs to view or change properties.</span></span>

   <span data-ttu-id="4736c-161">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4736c-161">When you're finished, click **Save**.</span></span>

#### <a name="general"></a><span data-ttu-id="4736c-162">Geral</span><span class="sxs-lookup"><span data-stu-id="4736c-162">General</span></span>

<span data-ttu-id="4736c-163">Use essa guia para exibir ou alterar as informações básicas sobre o grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-163">Use this tab to view or change basic information about the group.</span></span>

- <span data-ttu-id="4736c-164">**Nome para exibição**: esse nome é exibido no catálogo de endereços, na linha para quando o email é enviado a esse grupo e na **lista de grupos**.</span><span class="sxs-lookup"><span data-stu-id="4736c-164">**Display name**: This name appears in the address book, on the To line when email is sent to this group, and in the **Groups list**.</span></span> <span data-ttu-id="4736c-165">O nome para exibição é necessário e deve ser amigável para que as pessoas o reconheçam.</span><span class="sxs-lookup"><span data-stu-id="4736c-165">The display name is required and should be user-friendly so people recognize what it is.</span></span> <span data-ttu-id="4736c-166">Ele também deve ser exclusivo em seu domínio.</span><span class="sxs-lookup"><span data-stu-id="4736c-166">It also has to be unique in your domain.</span></span>

  <span data-ttu-id="4736c-167">Se você implementou uma política de nomeação de grupo, o nome para exibição terá que estar em conformidade com o formato de nomeação definido pela política.</span><span class="sxs-lookup"><span data-stu-id="4736c-167">If you've implemented a group naming policy, the display name has to conform to the naming format defined by the policy.</span></span>

- <span data-ttu-id="4736c-168">**Alias**: esta é a parte do endereço de email que aparece à esquerda do símbolo de arroba (@).</span><span class="sxs-lookup"><span data-stu-id="4736c-168">**Alias**: This is the portion of the email address that appears to the left of the at (@) symbol.</span></span> <span data-ttu-id="4736c-169">Se você alterar o alias, o endereço SMTP principal do grupo também será alterado e conterá o novo alias.</span><span class="sxs-lookup"><span data-stu-id="4736c-169">If you change the alias, the primary SMTP address for the group will also be changed, and contain the new alias.</span></span> <span data-ttu-id="4736c-170">Além disso, o endereço de email com o alias anterior será mantido como um endereço proxy para o grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-170">Also, the email address with the previous alias will be kept as a proxy address for the group.</span></span>

- <span data-ttu-id="4736c-171">**Endereço de email**: o endereço de email consiste no alias no lado esquerdo do símbolo de arroba (@) e em um domínio no lado direito.</span><span class="sxs-lookup"><span data-stu-id="4736c-171">**Email address**: The email address consists of the alias on the left side of the at (@) symbol, and a domain on the right side.</span></span> <span data-ttu-id="4736c-172">Por padrão, o valor de **alias** é usado para o valor do alias, mas você pode alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="4736c-172">By default, the value of **Alias** is used for the alias value, but you can change it.</span></span> <span data-ttu-id="4736c-173">Para o valor de domínio, clique no menu suspenso e selecione o domínio aceito em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4736c-173">For the domain value, click the drop down and select and accepted domain in your organization.</span></span>

- <span data-ttu-id="4736c-174">**Descrição**: esta descrição aparece no catálogo de endereços e no painel de detalhes no Eat.</span><span class="sxs-lookup"><span data-stu-id="4736c-174">**Description**: This description appears in the address book and in the Details pane in the EAC.</span></span>

#### <a name="ownership"></a><span data-ttu-id="4736c-175">Propriedade</span><span class="sxs-lookup"><span data-stu-id="4736c-175">Ownership</span></span>

<span data-ttu-id="4736c-176">Use esta guia para atribuir proprietários de grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-176">Use this tab to assign group owners.</span></span> <span data-ttu-id="4736c-177">Um proprietário de grupo pode gerenciar A Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-177">A group owner can manage group membership.</span></span> <span data-ttu-id="4736c-178">Por padrão, a pessoa que cria um grupo é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="4736c-178">By default, the person who creates a group is the owner.</span></span> <span data-ttu-id="4736c-179">Todos os grupos devem ter no mínimo um proprietário.</span><span class="sxs-lookup"><span data-stu-id="4736c-179">All groups must have at least one owner.</span></span>

<span data-ttu-id="4736c-180">Para adicionar proprietários, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4736c-180">To add owners, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4736c-181">Na caixa de diálogo exibida, localize e selecione um destinatário e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="4736c-181">In the dialog that appears, find and select a recipient, and then click **add ->**.</span></span> <span data-ttu-id="4736c-182">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="4736c-182">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4736c-183">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4736c-183">When you're finished, click **OK**.</span></span>

<span data-ttu-id="4736c-184">Para remover um proprietário, selecione o proprietário e, em seguida, clique em **remover** ![ Remover ícone ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4736c-184">To remove an owner, select the owner, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

#### <a name="membership"></a><span data-ttu-id="4736c-185">Associação</span><span class="sxs-lookup"><span data-stu-id="4736c-185">Membership</span></span>

<span data-ttu-id="4736c-186">Use esta guia para adicionar ou remover membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-186">Use this tab to add or remove group members.</span></span> <span data-ttu-id="4736c-187">Os proprietários do grupo não precisam ser membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-187">Group owners don't need to be members of the group.</span></span>

<span data-ttu-id="4736c-188">Para adicionar membros, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="4736c-188">To add members, click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png).</span></span> <span data-ttu-id="4736c-189">Na caixa de diálogo exibida, localize e selecione um destinatário ou grupo e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="4736c-189">In the dialog that appears, find and select a recipient or group, and then click **add ->**.</span></span> <span data-ttu-id="4736c-190">Repita essa etapa quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="4736c-190">Repeat this step as many times as necessary.</span></span> <span data-ttu-id="4736c-191">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4736c-191">When you're finished, click **OK**.</span></span>

<span data-ttu-id="4736c-192">Para remover um membro, selecione-o e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4736c-192">To remove a member, select the member, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

### <a name="use-the-eac-to-remove-groups"></a><span data-ttu-id="4736c-193">Usar o Eat para remover grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-193">Use the EAC to remove groups</span></span>

1. <span data-ttu-id="4736c-194">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="4736c-194">In the EAC, go to **Recipients** \> **Groups**.</span></span>

2. <span data-ttu-id="4736c-195">Na lista de grupos, selecione o grupo de distribuição que você deseja remover e clique em **remover** ![ ícone de remoção ](../../media/ITPro-EAC-RemoveIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="4736c-195">In the list of groups, select the distribution group that you want to remove, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span>

## <a name="use-powershell-to-manage-groups"></a><span data-ttu-id="4736c-196">Usar o PowerShell para gerenciar grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-196">Use PowerShell to manage groups</span></span>

### <a name="use-standalone-eop-powershell-to-view-groups"></a><span data-ttu-id="4736c-197">Usar o EOP PowerShell autônomo para exibir grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-197">Use standalone EOP PowerShell to view groups</span></span>

<span data-ttu-id="4736c-198">Para retornar uma lista resumida de todos os grupos de distribuição e grupos de segurança habilitados para email no PowerShell autônomo do EOP, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4736c-198">To return a summary list of all distribution groups and mail-enabled security groups in standalone EOP PowerShell, run the following command:</span></span>

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

<span data-ttu-id="4736c-199">Para retornar a lista de membros do grupo, substitua \< GroupIdentity \> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4736c-199">To return the list of group members, replace \<GroupIdentity\> with the name, alias, or email address of the group, and run the following command:</span></span>

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

<span data-ttu-id="4736c-200">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) e [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="4736c-200">For detailed syntax and parameter information, see [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-recipient) and [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).</span></span>

### <a name="use-standalone-eop-powershell-to-create-groups"></a><span data-ttu-id="4736c-201">Usar o EOP PowerShell autônomo para criar grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-201">Use standalone EOP PowerShell to create groups</span></span>

<span data-ttu-id="4736c-202">Para criar grupos de distribuição ou grupos de segurança habilitados para email no PowerShell autônomo do EOP, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4736c-202">To create distribution groups or mail-enabled security groups in standalone EOP PowerShell, use the following syntax:</span></span>

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

<span data-ttu-id="4736c-203">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="4736c-203">**Notes**:</span></span>

- <span data-ttu-id="4736c-204">O parâmetro _Name_ é obrigatório, tem um comprimento máximo de 64 caracteres e deve ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="4736c-204">The _Name_ parameter is required, has a maximum length of 64 characters, and must be unique.</span></span> <span data-ttu-id="4736c-205">Se você não usa o parâmetro _DisplayName_, o valor do parâmetro _Name_ é usado para o nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="4736c-205">If you don't use the _DisplayName_ parameter, the value of the _Name_ parameter is used for the display name.</span></span>

- <span data-ttu-id="4736c-206">Se você não usar o parâmetro _alias_ , o parâmetro _Name_ será usado para o valor do alias.</span><span class="sxs-lookup"><span data-stu-id="4736c-206">If you don't use the _Alias_ parameter, the _Name_ parameter is used for the alias value.</span></span> <span data-ttu-id="4736c-207">Os espaços são removidos e os caracteres não suportados são convertidos em pontos de interrogação (?).</span><span class="sxs-lookup"><span data-stu-id="4736c-207">Spaces are removed and unsupported characters are converted to question marks (?).</span></span>

- <span data-ttu-id="4736c-208">Se você não usar o parâmetro _PrimarySmtpAddress_ , o valor do alias será usado no parâmetro _PrimarySmtpAddress_ .</span><span class="sxs-lookup"><span data-stu-id="4736c-208">If you don't use the _PrimarySmtpAddress_ parameter, the alias value is used in the _PrimarySmtpAddress_ parameter.</span></span>

- <span data-ttu-id="4736c-209">Se você não usar o parâmetro _Type_ , o valor padrão será Distribution.</span><span class="sxs-lookup"><span data-stu-id="4736c-209">If you don't use the _Type_ parameter, the default value is Distribution.</span></span>

<span data-ttu-id="4736c-210">Este exemplo cria um grupo de distribuição chamado administradores de ti com as propriedades especificadas.</span><span class="sxs-lookup"><span data-stu-id="4736c-210">This example creates a distribution group named IT Administrators with the specified properties.</span></span>

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

<span data-ttu-id="4736c-211">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span><span class="sxs-lookup"><span data-stu-id="4736c-211">For detailed syntax and parameter information, see [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup).</span></span>

### <a name="use-standalone-eop-powershell-to-modify-groups"></a><span data-ttu-id="4736c-212">Usar o EOP PowerShell autônomo para modificar grupos</span><span class="sxs-lookup"><span data-stu-id="4736c-212">Use standalone EOP PowerShell to modify groups</span></span>

<span data-ttu-id="4736c-213">Para modificar grupos no EOP PowerShell autônomo, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4736c-213">To modify groups in standalone EOP PowerShell, use the following syntax:</span></span>

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

<span data-ttu-id="4736c-214">Este exemplo usa as alterações do endereço SMTP principal (também chamado de endereço de resposta) do grupo de Seattle Employees para sea.employees@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="4736c-214">This example uses changes the primary SMTP address (also called the reply address) for the Seattle Employees group to sea.employees@contoso.com.</span></span>

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

<span data-ttu-id="4736c-215">Este exemplo substitui os membros atuais do grupo equipe de segurança por Kitty Petersen e Tyson Fawcett.</span><span class="sxs-lookup"><span data-stu-id="4736c-215">This example replaces the current members of the Security Team group with Kitty Petersen and Tyson Fawcett.</span></span>

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

<span data-ttu-id="4736c-216">Este exemplo adiciona um novo usuário chamado Tyson Fawcett ao grupo chamado equipe de segurança enquanto preserva os membros atuais do grupo.</span><span class="sxs-lookup"><span data-stu-id="4736c-216">This example adds a new user named Tyson Fawcett to the group named Security Team while preserving the current members of the group.</span></span>

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

<span data-ttu-id="4736c-217">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) e [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span><span class="sxs-lookup"><span data-stu-id="4736c-217">For detailed syntax and parameter information, see [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).</span></span>

### <a name="remove-a-group-using-remote-windows-powershell"></a><span data-ttu-id="4736c-218">Remover um grupo usando o Windows PowerShell remoto</span><span class="sxs-lookup"><span data-stu-id="4736c-218">Remove a group using remote Windows PowerShell</span></span>

<span data-ttu-id="4736c-219">Este exemplo usa remove o grupo de distribuição chamado administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="4736c-219">This example uses removes the distribution group named IT Administrators.</span></span>

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

<span data-ttu-id="4736c-220">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span><span class="sxs-lookup"><span data-stu-id="4736c-220">For detailed syntax and parameter information, see [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="4736c-221">Como saber se esses procedimentos funcionaram?</span><span class="sxs-lookup"><span data-stu-id="4736c-221">How do you know these procedures worked?</span></span>

<span data-ttu-id="4736c-222">Para verificar se você criou, modificou ou removeu com êxito um grupo de distribuição ou um grupo de segurança habilitado para email, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4736c-222">To verify that you've successfully created, modified, or removed a distribution group or a mail-enabled security group, do any of the following steps:</span></span>

- <span data-ttu-id="4736c-223">No Eat, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="4736c-223">In the EAC, go to **Recipients** \> **Groups**.</span></span> <span data-ttu-id="4736c-224">Verifique se o grupo está listado (ou não listado) e verifique o valor do **tipo de grupo** .</span><span class="sxs-lookup"><span data-stu-id="4736c-224">Verify that the group is listed (or not listed), and verify the **Group Type** value.</span></span> <span data-ttu-id="4736c-225">Selecione o grupo e visualize as informações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-AddIcon.png) para exibir as configurações.</span><span class="sxs-lookup"><span data-stu-id="4736c-225">Select the group and view the information in the Details pane, or click **Edit** ![Edit icon](../../media/ITPro-EAC-AddIcon.png) to view the settings.</span></span>

- <span data-ttu-id="4736c-226">Em EOP autônomo do PowerShell, execute o seguinte comando para verificar se o grupo está listado (ou não está listado):</span><span class="sxs-lookup"><span data-stu-id="4736c-226">In standalone EOP PowerShell, run the following command to verify the group is listed (or isn't listed):</span></span>

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- <span data-ttu-id="4736c-227">Substitua \< GroupIdentity \> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="4736c-227">Replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- <span data-ttu-id="4736c-228">Para exibir os membros do grupo, substitua \< GroupIdentity \> pelo nome, alias ou endereço de email do grupo e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4736c-228">To view the group members, replace \<GroupIdentity\> with the name, alias, or email address of the group and run the following command:</span></span>

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
