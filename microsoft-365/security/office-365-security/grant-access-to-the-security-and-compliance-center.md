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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Os usuários precisam ter permissões no Centro de Conformidade e Segurança do Microsoft 36 & 5 para poder gerenciar qualquer um dos seus recursos de segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a619b184c575e3750b2499adc661627b4d27d6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289872"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="3989f-103">Conceder aos usuários acesso ao Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="3989f-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3989f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3989f-104">**Applies to**</span></span>
- [<span data-ttu-id="3989f-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3989f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3989f-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3989f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="3989f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3989f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="3989f-108">Os usuários precisam ter permissões no Centro de Conformidade e Segurança & para poder gerenciar qualquer um dos seus recursos de segurança ou conformidade.</span><span class="sxs-lookup"><span data-stu-id="3989f-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="3989f-109">Como administrador global ou membro do grupo de função OrganizationManage & ment no Centro de Conformidade e Segurança, você pode dar essas permissões aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3989f-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="3989f-110">Os usuários só podem gerenciar os recursos de segurança ou de conformidade para os quais você conceder acesso.</span><span class="sxs-lookup"><span data-stu-id="3989f-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="3989f-111">Para obter mais informações sobre as diferentes permissões que você pode dar aos usuários no Centro de Conformidade e Segurança &, confira Permissões no Centro de Conformidade e & [Segurança.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="3989f-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3989f-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3989f-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3989f-113">Você precisa ser um administrador global ou um membro do grupo de função OrganizationManage & ment no Centro de Conformidade e Segurança, para concluir as etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3989f-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="3989f-114">Grupos de função para o Centro de Conformidade e Segurança & podem ter nomes semelhantes aos grupos de função no Exchange Online, mas eles não são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="3989f-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="3989f-115">As associações do grupo de funções não são compartilhadas entre o Exchange Online e o Centro de Conformidade & segurança.</span><span class="sxs-lookup"><span data-stu-id="3989f-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="3989f-116">Parceiros com permissões de acesso delegado (DAP) com permissões Administrar em nome de (AOBO) não podem acessar o Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="3989f-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="3989f-117">Usar o Centro de Conformidade & segurança para dar a outro usuário acesso ao Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="3989f-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="3989f-118">Abra o Centro de Conformidade & segurança <https://protection.office.com> e vá para **Permissões.**</span><span class="sxs-lookup"><span data-stu-id="3989f-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="3989f-119">Para ir diretamente para a **guia Permissões,** abra <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="3989f-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="3989f-120">Na lista de grupos de função, escolha o grupo de função e clique em **Editar** ![ ícone ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="3989f-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="3989f-121">Na página de propriedades do grupo de funções em **Membros,** clique em Adicionar Ícone e selecione o nome do usuário ![ ](../../media/ITPro-EAC-AddIcon.gif) (ou usuários) que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="3989f-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="3989f-122">Quando você selecionar todos os usuários que deseja adicionar ao grupo de funções, clique em **adicionar \> e,** em seguida, **OK.**</span><span class="sxs-lookup"><span data-stu-id="3989f-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="3989f-123">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3989f-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="3989f-124">Usar o & PowerShell do Centro de Conformidade e Segurança para dar a outro usuário acesso ao Centro de Conformidade & Segurança</span><span class="sxs-lookup"><span data-stu-id="3989f-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="3989f-125">[Conectar-se ao Windows PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="3989f-125">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="3989f-126">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3989f-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="3989f-127">Para problemas detalhados de sintaxes e de parâmetros, consulte [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="3989f-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3989f-128">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="3989f-128">How do you know this worked?</span></span>

<span data-ttu-id="3989f-129">Para verificar se você concedeu com êxito o acesso ao Centro de Conformidade & segurança, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3989f-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="3989f-130">No Centro de Conformidade & segurança, vá para **Permissões** e selecione o grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="3989f-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="3989f-131">No flyout de detalhes que é aberto, verifique os membros do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="3989f-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="3989f-132">No PowerShell & Centro de Conformidade e Segurança, substitua pelo nome do grupo de função \<RoleGroupName\> e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3989f-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="3989f-133">Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="3989f-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
