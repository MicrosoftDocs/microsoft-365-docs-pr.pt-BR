---
title: Gerenciar o acesso de convidados nos grupos do Microsoft 365
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
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753272"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="2c04e-103">Gerenciar o acesso de convidados nos grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c04e-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="2c04e-104">Por padrão, o acesso de convidados para os grupos do Microsoft 365 está ativado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c04e-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="2c04e-105">Os administradores podem controlar a possibilidade de permitir o acesso de convidados a grupos para toda a sua organização ou para grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="2c04e-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="2c04e-106">Quando ele está ativado, os membros do grupo podem convidar usuários convidados para um grupo do Microsoft 365 por meio do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="2c04e-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="2c04e-107">Os convites são enviados ao proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="2c04e-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="2c04e-108">Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="2c04e-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="2c04e-109">As redes corporativas do Yammer que estão no modo nativo ou na [Geografia da UE](https://go.microsoft.com/fwlink/?linkid=2107357) não dão suporte a convidados de rede.</span><span class="sxs-lookup"><span data-stu-id="2c04e-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="2c04e-110">Os grupos do Yammer conectados ao Microsoft 365 atualmente não dão suporte ao acesso de convidados, mas você pode criar grupos externos não conectados na sua rede do Yammer.</span><span class="sxs-lookup"><span data-stu-id="2c04e-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="2c04e-111">Veja [criar e gerenciar grupos externos no Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="2c04e-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="2c04e-112">O acesso de convidados em grupos é geralmente usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams.</span><span class="sxs-lookup"><span data-stu-id="2c04e-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="2c04e-113">Esses serviços têm suas próprias configurações de compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="2c04e-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="2c04e-114">Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e equipes, consulte:</span><span class="sxs-lookup"><span data-stu-id="2c04e-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="2c04e-115">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="2c04e-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="2c04e-116">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="2c04e-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="2c04e-117">Gerenciar o acesso de convidados a grupos</span><span class="sxs-lookup"><span data-stu-id="2c04e-117">Manage groups guest access</span></span>

<span data-ttu-id="2c04e-118">Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c04e-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="2c04e-119">No centro de administração, vá para **Mostrar todas** as \> **Settings** \> **configurações da organização** configurações e, na guia **Serviços** , selecione **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="2c04e-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="2c04e-120">Na página de **grupos do Microsoft 365** , escolha se você deseja permitir que as pessoas de fora de sua organização acessem os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas de fora da sua organização a grupos.</span><span class="sxs-lookup"><span data-stu-id="2c04e-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="2c04e-121">Adicionar convidados a um grupo do Microsoft 365 a partir do centro de administração</span><span class="sxs-lookup"><span data-stu-id="2c04e-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="2c04e-122">Se o convidado já existir no seu diretório, você poderá adicioná-lo aos seus grupos no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c04e-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="2c04e-123">No centro de administração, vá para a página grupos de **grupos**  >  **Groups** .</span><span class="sxs-lookup"><span data-stu-id="2c04e-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="2c04e-124">Clique no grupo ao qual você deseja adicionar o convidado e selecione **Exibir todos e gerenciar Membros** na guia **Membros** .</span><span class="sxs-lookup"><span data-stu-id="2c04e-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="2c04e-125">Selecione **adicionar membros**e escolha o nome do convidado que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="2c04e-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="2c04e-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2c04e-126">Select **Save**.</span></span>

<span data-ttu-id="2c04e-127">Se quiser adicionar um convidado ao diretório diretamente, você poderá [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="2c04e-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="2c04e-128">Se quiser editar as informações de um convidado, você poderá [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="2c04e-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c04e-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c04e-129">See also</span></span>

[<span data-ttu-id="2c04e-130">Bloquear usuários convidados de um grupo específico</span><span class="sxs-lookup"><span data-stu-id="2c04e-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="2c04e-131">Gerenciar a associação de grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c04e-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="2c04e-132">Revisões do acesso ao Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="2c04e-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="2c04e-133">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="2c04e-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
