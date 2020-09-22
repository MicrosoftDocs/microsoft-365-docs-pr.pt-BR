---
title: Conceder aos usuários acesso ao Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam receber permissões no centro de conformidade & segurança da Microsoft 365 antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202802"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="54249-103">Conceder aos usuários acesso ao Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="54249-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="54249-104">Os usuários precisam receber permissões no centro de conformidade e segurança & antes de poderem gerenciar qualquer um dos seus recursos de segurança ou conformidade.</span><span class="sxs-lookup"><span data-stu-id="54249-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="54249-105">Como um administrador global ou membro do grupo de função gerenciamento no centro de conformidade & segurança, você pode conceder essas permissões aos usuários.</span><span class="sxs-lookup"><span data-stu-id="54249-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="54249-106">Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="54249-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="54249-107">Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no centro de conformidade & segurança, confira [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="54249-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="54249-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="54249-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="54249-109">Você precisa ser um administrador global ou um membro do grupo de função gerenciamento no centro de conformidade & segurança, para concluir as etapas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="54249-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="54249-110">Grupos de função para o centro de conformidade & segurança podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="54249-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="54249-111">As associações do grupo de funções não são compartilhadas entre o Exchange Online e o centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="54249-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="54249-112">Permissão de acesso delegado (DAP) parceiros com permissões de administração em nome de (AOBO) não podem acessar o centro de conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="54249-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="54249-113">Usar o centro de conformidade de & de segurança para conceder acesso de outro usuário ao centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="54249-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="54249-114">Abra o centro de conformidade & segurança em <https://protection.office.com> e vá até **permissões**.</span><span class="sxs-lookup"><span data-stu-id="54249-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="54249-115">Para ir diretamente para a guia **permissões** , abra <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="54249-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="54249-116">Na lista de grupos de função, escolha o grupo de função e, em seguida, clique em **Editar** ![ ícone de edição ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="54249-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="54249-117">Na página de propriedades do grupo de funções, em **Membros**, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.gif) de adição e selecione o nome do usuário (ou usuários) que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="54249-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="54249-118">Depois de selecionar todos os usuários que você deseja adicionar ao grupo de funções, clique em \*\*Adicionar \> \*\* e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="54249-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="54249-119">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="54249-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="54249-120">Usar o PowerShell do centro de conformidade & a segurança para conceder acesso a outro usuário ao centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="54249-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="54249-121">[Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="54249-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="54249-122">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="54249-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="54249-123">Para problemas detalhados de sintaxe e parâmetro, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="54249-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="54249-124">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="54249-124">How do you know this worked?</span></span>

<span data-ttu-id="54249-125">Para verificar se você obteve com êxito o acesso ao centro de conformidade de & de segurança, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="54249-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="54249-126">No centro de conformidade & segurança, acesse **permissões** e selecione o grupo de função.</span><span class="sxs-lookup"><span data-stu-id="54249-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="54249-127">No submenu de detalhes que é aberto, verifique os membros do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="54249-127">In the details flyout that opens, verify the members of the role group.</span></span> 

- <span data-ttu-id="54249-128">Em segurança & o PowerShell do centro de conformidade, substitua \<RoleGroupName\> o nome do grupo de função e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="54249-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="54249-129">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="54249-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
