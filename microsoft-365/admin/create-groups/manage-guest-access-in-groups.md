---
title: Gerenciar o acesso de convidados Microsoft 365 grupos
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
description: Saiba como adicionar convidados a um grupo Microsoft 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571932"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="ef45a-103">Gerenciar o acesso de convidados Microsoft 365 grupos</span><span class="sxs-lookup"><span data-stu-id="ef45a-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="ef45a-104">Por padrão, o acesso de convidados Microsoft 365 grupos está ligado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ef45a-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="ef45a-105">Os administradores podem controlar se é possível permitir o acesso de convidados a grupos para toda a organização ou para grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="ef45a-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="ef45a-106">Quando ele está ligado, os membros do grupo podem convidar usuários convidados para um grupo Microsoft 365 por meio Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="ef45a-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="ef45a-107">Os convites são enviados ao proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ef45a-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="ef45a-108">Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="ef45a-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="ef45a-109">Yammer Enterprise redes que estão no Modo Nativo ou na [UE Geo](/yammer/manage-security-and-compliance/manage-data-compliance) não suportam convidados de rede.</span><span class="sxs-lookup"><span data-stu-id="ef45a-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="ef45a-110">Microsoft 365 Os grupos Yammer conectados atualmente não suportam o acesso de convidados, mas você pode criar grupos externos não conectados em sua Yammer rede.</span><span class="sxs-lookup"><span data-stu-id="ef45a-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="ef45a-111">Consulte [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ef45a-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="ef45a-112">O acesso de convidados em grupos geralmente é usado como parte de um cenário mais amplo que inclui SharePoint ou Teams.</span><span class="sxs-lookup"><span data-stu-id="ef45a-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="ef45a-113">Esses serviços têm suas próprias configurações de compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="ef45a-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="ef45a-114">Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e Teams, consulte:</span><span class="sxs-lookup"><span data-stu-id="ef45a-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="ef45a-115">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="ef45a-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="ef45a-116">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="ef45a-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="ef45a-117">Gerenciar o acesso de convidados de grupos</span><span class="sxs-lookup"><span data-stu-id="ef45a-117">Manage groups guest access</span></span>

<span data-ttu-id="ef45a-118">Se você quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração Microsoft 365 local.</span><span class="sxs-lookup"><span data-stu-id="ef45a-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="ef45a-119">No centro de administração, vá para **Mostrar todas** as configurações Configurações Org e, na guia \>  \>  **Serviços,** selecione **Microsoft 365 grupos**.</span><span class="sxs-lookup"><span data-stu-id="ef45a-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="ef45a-120">Na página **Microsoft 365 Grupos,** escolha se deseja permitir que pessoas de fora da sua organização acessem recursos de grupo ou permitir que os proprietários do grupo adicionem pessoas de fora da sua organização a grupos.</span><span class="sxs-lookup"><span data-stu-id="ef45a-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="ef45a-121">Adicionar convidados a um grupo Microsoft 365 do centro de administração</span><span class="sxs-lookup"><span data-stu-id="ef45a-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="ef45a-122">Se o convidado já existir em seu diretório, você poderá adicioná-los aos seus grupos Microsoft 365 centro de administração.</span><span class="sxs-lookup"><span data-stu-id="ef45a-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="ef45a-123">(Grupos com associação dinâmica devem ser [gerenciados Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="ef45a-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="ef45a-124">No centro de administração, vá para a página **Grupos**  >  **grupos.**</span><span class="sxs-lookup"><span data-stu-id="ef45a-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="ef45a-125">Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos** e gerenciar membros na **guia** Membros.</span><span class="sxs-lookup"><span data-stu-id="ef45a-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="ef45a-126">Selecione **Adicionar membros** e escolha o nome do convidado que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef45a-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="ef45a-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef45a-127">Select **Save**.</span></span>

<span data-ttu-id="ef45a-128">Se você quiser adicionar um convidado ao diretório diretamente, você pode adicionar Azure Active Directory usuários de colaboração [B2B no portal do Azure](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="ef45a-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="ef45a-129">Se você quiser editar qualquer uma das informações de um convidado, poderá [adicionar](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ou atualizar as informações de perfil de um usuário usando Azure Active Directory .</span><span class="sxs-lookup"><span data-stu-id="ef45a-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="ef45a-130">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ef45a-130">Related content</span></span>

<span data-ttu-id="ef45a-131">[Bloquear usuários convidados de um grupo específico](../../solutions/per-group-guest-access.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef45a-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="ef45a-132">[Gerenciar a associação de grupo no Microsoft 365 de administração](add-or-remove-members-from-groups.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef45a-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="ef45a-133">[Azure Active Directory de acesso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef45a-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="ef45a-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ef45a-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>