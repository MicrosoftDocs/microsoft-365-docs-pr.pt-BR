---
title: Gerenciar o acesso de convidados em grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Saiba como adicionar convidados a um grupo do Microsoft 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453652"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="9024c-103">Gerenciar o acesso de convidados em grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9024c-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="9024c-104">Por padrão, o acesso de convidados para grupos do Microsoft 365 está ligado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9024c-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="9024c-105">Os administradores podem controlar se é possível permitir o acesso de convidados a grupos para toda a organização ou para grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="9024c-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="9024c-106">Quando ele está ligado, os membros do grupo podem convidar usuários convidados para um grupo do Microsoft 365 por meio do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="9024c-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="9024c-107">Os convites são enviados ao proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="9024c-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="9024c-108">Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="9024c-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="9024c-109">As redes do Yammer Enterprise que estão no Modo Nativo ou na [UE Geo](https://go.microsoft.com/fwlink/?linkid=2107357) não suportam convidados de rede.</span><span class="sxs-lookup"><span data-stu-id="9024c-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="9024c-110">Os grupos do Microsoft 365 Connected Yammer atualmente não suportam o acesso de convidados, mas você pode criar grupos externos não conectados em sua rede do Yammer.</span><span class="sxs-lookup"><span data-stu-id="9024c-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="9024c-111">Consulte [Criar e gerenciar grupos externos no Yammer para](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) obter instruções.</span><span class="sxs-lookup"><span data-stu-id="9024c-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="9024c-112">O acesso de convidados em grupos geralmente é usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams.</span><span class="sxs-lookup"><span data-stu-id="9024c-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="9024c-113">Esses serviços têm suas próprias configurações de compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="9024c-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="9024c-114">Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e Teams, consulte:</span><span class="sxs-lookup"><span data-stu-id="9024c-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="9024c-115">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="9024c-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="9024c-116">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="9024c-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="9024c-117">Gerenciar o acesso de convidados de grupos</span><span class="sxs-lookup"><span data-stu-id="9024c-117">Manage groups guest access</span></span>

<span data-ttu-id="9024c-118">Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9024c-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="9024c-119">No centro de administração, vá para **Mostrar todas as** configurações da Organização de Configurações e, na guia Serviços, selecione Grupos do Microsoft \>  \>  **365**. </span><span class="sxs-lookup"><span data-stu-id="9024c-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="9024c-120">Na página Grupos do **Microsoft 365,** escolha se deseja permitir que pessoas de fora da sua organização acessem recursos de grupo ou permitir que os proprietários do grupo adicionem pessoas de fora da sua organização a grupos.</span><span class="sxs-lookup"><span data-stu-id="9024c-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="9024c-121">Adicionar convidados a um grupo do Microsoft 365 do centro de administração</span><span class="sxs-lookup"><span data-stu-id="9024c-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="9024c-122">Se o convidado já existir em seu diretório, você poderá adicioná-los aos seus grupos do Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9024c-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="9024c-123">(Grupos com associação dinâmica devem ser [gerenciados no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="9024c-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="9024c-124">No centro de administração, vá para a página **Grupos**  >  **grupos.**</span><span class="sxs-lookup"><span data-stu-id="9024c-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="9024c-125">Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos** e gerenciar membros na **guia** Membros.</span><span class="sxs-lookup"><span data-stu-id="9024c-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="9024c-126">Selecione **Adicionar membros** e escolha o nome do convidado que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="9024c-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="9024c-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9024c-127">Select **Save**.</span></span>

<span data-ttu-id="9024c-128">Se quiser adicionar um convidado ao diretório diretamente, você pode adicionar usuários de colaboração [B2B do Azure Active Directory no portal do Azure.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="9024c-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="9024c-129">Se você quiser editar qualquer uma das informações de um convidado, poderá adicionar ou atualizar as informações de perfil de um usuário usando o [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9024c-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="9024c-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="9024c-130">See also</span></span>

[<span data-ttu-id="9024c-131">Bloquear usuários convidados de um grupo específico</span><span class="sxs-lookup"><span data-stu-id="9024c-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="9024c-132">Gerenciar associação de grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9024c-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="9024c-133">Avaliações de acesso do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9024c-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="9024c-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="9024c-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
