---
title: Gerenciar permissões do grupo de funções de administrador no EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Os administradores podem saber como atribuir ou remover permissões no centro de administração do Exchange (Eat) na proteção do Exchange Online.
ms.openlocfilehash: 589d979b9a2ed3f262eb8171fe08622c225548ce
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073723"
---
# <a name="manage-admin-role-group-permissions-in-eop"></a><span data-ttu-id="43417-103">Gerenciar permissões do grupo de funções de administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="43417-103">Manage admin role group permissions in EOP</span></span>
  
<span data-ttu-id="43417-p101">No Microsoft Proteção do Exchange Online (EOP), é possível usar o Centro de administração do Exchange (EAC) para tornar um usuário membro de um grupo ou de grupos de funções a fim de atribuir a ele permissões de execução de tarefas administrativas específicas. Também é possível remover um usuário de um grupo ou grupo de funções usando o EAC.</span><span class="sxs-lookup"><span data-stu-id="43417-p101">In Microsoft Exchange Online Protection (EOP), you can use the Exchange admin center (EAC) to make a user a member of a role group or groups in order to assign them permissions to perform specific administrative tasks. You can also remove a user from a role group or groups by using the EAC.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="43417-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="43417-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="43417-107">Tempo estimado para conclusão: 5 a 10 minutos</span><span class="sxs-lookup"><span data-stu-id="43417-107">Estimated time to complete: 5-10 minutes</span></span>

- <span data-ttu-id="43417-108">Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="43417-108">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="43417-p102">Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Usuários, contatos e funções de grupo" no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="43417-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Users, Contacts, and Role Groups" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="43417-111">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="43417-111">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="43417-112">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="43417-112">Having problems?</span></span> <span data-ttu-id="43417-113">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="43417-113">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>
  
## <a name="use-the-eac-to-assign-members-to-admin-role-groups"></a><span data-ttu-id="43417-114">Usar o EAC para atribuir membros a grupos de funções de administração</span><span class="sxs-lookup"><span data-stu-id="43417-114">Use the EAC to assign members to admin role groups</span></span>

1. <span data-ttu-id="43417-115">No Eat, vá para **funções de administrador**de **permissões** \> , clique no grupo de funções ao qual você deseja adicionar o usuário ou usuários e, em seguida, clique](../media/ITPro-EAC-EditIcon.gif)em **Editar** ![ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="43417-115">In the EAC, go to **Permissions** \> **Admin roles**, click the role group that you want to add the user or users to, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="43417-116">Em membros, clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif)de adição.</span><span class="sxs-lookup"><span data-stu-id="43417-116">Under Members, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="43417-117">A janela Selecionar Membros será exibida.</span><span class="sxs-lookup"><span data-stu-id="43417-117">The Select Members window will appear.</span></span>

3. <span data-ttu-id="43417-118">Procure o usuário ou usuários que você deseja adicionar ou selecione-os na lista.</span><span class="sxs-lookup"><span data-stu-id="43417-118">Search for the user or users that you wish to add, or select them from the list.</span></span>

4. <span data-ttu-id="43417-p105">Depois de selecionar o usuário ou usuários que você deseja adicionar, clique em **Adicionar** e clique em **OK**. A janela Selecionar Membros será fechada.</span><span class="sxs-lookup"><span data-stu-id="43417-p105">When you have selected the user or users that you want to add, click **Add**, and then click **OK**. The Select Members window will close.</span></span>

5. <span data-ttu-id="43417-p106">Você verá que o usuário foi adicionado ao painel **Membros**. Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="43417-p106">You will see that the user has been added to the **Members** pane. Click **Save**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="43417-123">Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="43417-123">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span> 
  
## <a name="use-the-eac-to-remove-members-from-admin-role-groups"></a><span data-ttu-id="43417-124">Usar o EAC para remover membros de grupos de funções de administração</span><span class="sxs-lookup"><span data-stu-id="43417-124">Use the EAC to remove members from admin role groups</span></span>

1. <span data-ttu-id="43417-125">No Eat, vá para **funções de administrador**de **permissões** \> , clique no grupo de funções do qual você deseja remover um usuário ou usuários e, em seguida, clique](../media/ITPro-EAC-EditIcon.gif)em **Editar** ![ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="43417-125">In the EAC, go to **Permissions** \> **Admin Roles**, click the role group that you want to remove a user or users from, and then click **Edit** ![Edit icon](../media/ITPro-EAC-EditIcon.gif).</span></span>

2. <span data-ttu-id="43417-126">Em membros, selecione o usuário ou usuários que você deseja remover e clique em **remover** ![Remover ícone](../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="43417-126">Under Members, select the user or users that you want to remove and click **Remove** ![Remove icon](../media/ITPro-EAC-RemoveIcon.gif).</span></span>

3. <span data-ttu-id="43417-p107">Clique em **Salvar** para salvar a alteração no grupo e retornar à página **Funções de Administração**. Para verificar se você removeu o usuário do grupo de funções de administrador, verifique se o membro não está mais sendo exibido em Membros no painel de detalhes do grupo de funções selecionado.</span><span class="sxs-lookup"><span data-stu-id="43417-p107">Click **Save** to save the change to the role group and return to the **Admin Roles** page. To verify that you've successfully removed the user from the administrator role group, make sure the member is no longer displayed under Members in the details pane for the selected role group.</span></span>

   > [!NOTE]
   > <span data-ttu-id="43417-129">Os usuários precisam sair e entrar novamente para ver a alteração em seus diretos administrativos após a adição ou remoção de membros do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="43417-129">Users may have to sign out and sign in again to see the change in their administrative rights after you add or remove members from the role group.</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="43417-130">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="43417-130">For more information</span></span>

[<span data-ttu-id="43417-131">Permissões de recurso no EOP</span><span class="sxs-lookup"><span data-stu-id="43417-131">Feature permissions in EOP</span></span>](feature-permissions-in-eop.md)
