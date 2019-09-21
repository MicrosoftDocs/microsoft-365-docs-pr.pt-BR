---
title: Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam receber permissões no centro de conformidade & segurança do Office 365 antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.openlocfilehash: c64991fa4ad847381cb00e38473aefc848015ff0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072461"
---
# <a name="give-users-access-to-the-office-365-security--compliance-center"></a><span data-ttu-id="a3a04-103">Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="a3a04-103">Give users access to the Office 365 Security & Compliance Center</span></span>

<span data-ttu-id="a3a04-104">Os usuários precisam receber permissões no centro de conformidade & segurança do Office 365 antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade.</span><span class="sxs-lookup"><span data-stu-id="a3a04-104">Users need to be assigned permissions in the Office 365 Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="a3a04-105">Como um administrador global do Office 365 ou membro do grupo de função gerenciamento no centro de conformidade & segurança, você pode conceder essas permissões aos usuários.</span><span class="sxs-lookup"><span data-stu-id="a3a04-105">As an Office 365 global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="a3a04-106">Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="a3a04-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span> 
  
<span data-ttu-id="a3a04-107">Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no centro de conformidade & segurança, confira [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a3a04-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3a04-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a3a04-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3a04-109">Você precisa ser um administrador global do Office 365 ou um membro do grupo de função gerenciamento no centro de conformidade & segurança, para concluir as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a3a04-109">You need to be an Office 365 global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="a3a04-110">Grupos de função para o centro de conformidade & segurança podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="a3a04-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="a3a04-111">As associações do grupo de funções não são compartilhadas entre o Exchange Online e o centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="a3a04-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="a3a04-112">Permissão de acesso delegado (DAP) parceiros com permissões de administração em nome de (AOBO) não podem acessar o centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="a3a04-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="a3a04-113">Usar o centro de administração para conceder acesso a outro usuário ao centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="a3a04-113">Use the admin center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="a3a04-114">[Entre no Office 365 e vá para o centro de administração](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span><span class="sxs-lookup"><span data-stu-id="a3a04-114">[Sign in to Office 365 and go to the Admin center](https://go.microsoft.com/fwlink/p/?LinkId=525275).</span></span>

2. <span data-ttu-id="a3a04-115">No centro de administração do Microsoft 365, abra **centros de administração** e clique em **segurança & conformidade**.</span><span class="sxs-lookup"><span data-stu-id="a3a04-115">In the Microsoft 365 admin center, open **Admin centers** and then click **Security & Compliance**.</span></span>

3. <span data-ttu-id="a3a04-116">No centro de conformidade & segurança, acesse **permissões**.</span><span class="sxs-lookup"><span data-stu-id="a3a04-116">In the Security & Compliance Center, go to **Permissions**.</span></span>

4. <span data-ttu-id="a3a04-117">Na lista, escolha o grupo de funções ao qual você deseja adicionar o usuário e clique em **Editar** ![ícone](../media/O365-MDM-CreatePolicy-EditIcon.gif)de edição.</span><span class="sxs-lookup"><span data-stu-id="a3a04-117">From the list, choose the role group that you want to add the user to and click **Edit** ![Edit icon](../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

5. <span data-ttu-id="a3a04-118">Na página de propriedades do grupo de funções, em **Membros**, clique em](../media/ITPro-EAC-AddIcon.gif) **Adicionar**![ícone de adição e selecione o nome do usuário (ou usuários) que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a3a04-118">In the role group's properties page under **Members**, click **Add**![Add Icon](../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

6. <span data-ttu-id="a3a04-119">Depois de selecionar todos os usuários que você deseja adicionar ao grupo de funções, clique em \*\*Adicionar\> \*\* e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3a04-119">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

7. <span data-ttu-id="a3a04-120">Clique em **Salvar** para salvar as alterações feitas no grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="a3a04-120">Click **Save** to save the changes to the role group.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a3a04-121">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a3a04-121">How do you know this worked?</span></span>

1. <span data-ttu-id="a3a04-122">No centro de conformidade & segurança, acesse **permissões**.</span><span class="sxs-lookup"><span data-stu-id="a3a04-122">In the Security & Compliance Center, go to **Permissions**.</span></span>

2. <span data-ttu-id="a3a04-123">Na lista, selecione o grupo de funções para exibir os membros.</span><span class="sxs-lookup"><span data-stu-id="a3a04-123">From the list, select the role group to view the members.</span></span>

3. <span data-ttu-id="a3a04-124">No lado direito, nos detalhes do grupo de função, você pode exibir os membros do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="a3a04-124">On the right, in the role group details, you can view the members of the role group.</span></span>

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="a3a04-125">Usar o PowerShell para conceder a outro usuário acesso ao centro de conformidade de & de segurança</span><span class="sxs-lookup"><span data-stu-id="a3a04-125">Use PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="a3a04-126">[Conecte-se ao PowerShell do centro de conformidade & segurança do Office 365](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="a3a04-126">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="a3a04-127">Use o comando **Add-RoleGroupMember** para adicionar um usuário à função de Gerenciamento de Organização, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3a04-127">Use the **Add-RoleGroupMember** command to add a user to the Organization Management Role, as shown in the following example.</span></span>

   ```
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   <span data-ttu-id="a3a04-128">**Parâmetros**:</span><span class="sxs-lookup"><span data-stu-id="a3a04-128">**Parameters**:</span></span>
  
   - <span data-ttu-id="a3a04-129">_Identity_ é o grupo de funções ao qual adicionar um membro.</span><span class="sxs-lookup"><span data-stu-id="a3a04-129">_Identity_ is the role group to add a member to.</span></span>

   - <span data-ttu-id="a3a04-130">_Member_ é a caixa de correio, grupo de segurança universal (USG) ou computador a ser adicionado ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="a3a04-130">_Member_ is the mailbox, universal security group (USG), or computer to add to the role group.</span></span> <span data-ttu-id="a3a04-131">Você só pode especificar um membro por vez.</span><span class="sxs-lookup"><span data-stu-id="a3a04-131">You can specify only one member at a time.</span></span>

<span data-ttu-id="a3a04-132">Para obter informações detalhadas sobre sintaxe e parâmetros, consulte [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span><span class="sxs-lookup"><span data-stu-id="a3a04-132">For detailed information on syntax and parameters, see [Add-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510859).</span></span>
  
### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a3a04-133">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a3a04-133">How do you know this worked?</span></span>

<span data-ttu-id="a3a04-134">Para verificar se você concedeu aos usuários acesso ao centro de conformidade de & de segurança, use o cmdlet **Get-RoleGroupMember** para exibir os membros no grupo de função gerenciamento da organização, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="a3a04-134">To verify that you've given users access to the Security & Compliance Center, use the **Get-RoleGroupMember** cmdlet to view the members in the Organization Management role group, as shown in the following example.</span></span>
  
```
Get-RoleGroupMember -Identity "Organization Management"
```

<span data-ttu-id="a3a04-135">Para obter informações detalhadas sobre sintaxe e parâmetros, consulte [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span><span class="sxs-lookup"><span data-stu-id="a3a04-135">For detailed information on syntax and parameters, see [Get-RoleGroupMember](https://go.microsoft.com/fwlink/p/?LinkId=510860).</span></span>
