---
title: Gerenciar o acesso de hóspedes em grupos Microsoft 365
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
description: Aprenda a adicionar hóspedes a um grupo de Microsoft 365, visualize os usuários convidados e use o PowerShell para controlar o acesso dos hóspedes.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571932"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="aed79-103">Gerenciar o acesso de hóspedes em grupos Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aed79-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="aed79-104">Por padrão, o acesso de hóspedes para grupos Microsoft 365 é ligado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="aed79-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="aed79-105">Os administradores podem controlar se permitem o acesso dos hóspedes a grupos para toda a sua organização ou para grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="aed79-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="aed79-106">Quando ele está ligado, os membros do grupo podem convidar os usuários convidados para um grupo Microsoft 365 através de Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="aed79-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="aed79-107">Os convites são enviados ao dono do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="aed79-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="aed79-108">Uma vez aprovado, o usuário convidado é adicionado ao diretório e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="aed79-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="aed79-109">Yammer Enterprise redes que estão no Modo Nativo ou no [Geo da UE](/yammer/manage-security-and-compliance/manage-data-compliance) não suportam hóspedes da rede.</span><span class="sxs-lookup"><span data-stu-id="aed79-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="aed79-110">Microsoft 365 Os grupos de Yammer conectados não suportam atualmente o acesso aos hóspedes, mas você pode criar grupos externos não conectados em sua rede Yammer.</span><span class="sxs-lookup"><span data-stu-id="aed79-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="aed79-111">Consulte [Criar e gerenciar grupos externos em Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="aed79-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="aed79-112">O acesso de hóspedes em grupos é frequentemente usado como parte de um cenário mais amplo que inclui SharePoint ou Teams.</span><span class="sxs-lookup"><span data-stu-id="aed79-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="aed79-113">Esses serviços têm suas próprias configurações de compartilhamento de hóspedes.</span><span class="sxs-lookup"><span data-stu-id="aed79-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="aed79-114">Para obter instruções completas para configurar o compartilhamento de hóspedes entre grupos, SharePoint e Teams, consulte:</span><span class="sxs-lookup"><span data-stu-id="aed79-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="aed79-115">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="aed79-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="aed79-116">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="aed79-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="aed79-117">Gerenciar grupos de acesso a hóspedes</span><span class="sxs-lookup"><span data-stu-id="aed79-117">Manage groups guest access</span></span>

<span data-ttu-id="aed79-118">Se você quiser ativar ou desativar o acesso de hóspedes em grupos, você pode fazê-lo no centro administrativo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aed79-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="aed79-119">No centro administrativo, vá para **Mostrar todas as** \> configurações **Configurações** Org e na guia \> **Serviços,** selecione **Microsoft 365 grupos**. </span><span class="sxs-lookup"><span data-stu-id="aed79-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="aed79-120">Na página **Microsoft 365 Grupos,** escolha se você quer deixar as pessoas fora da sua organização acessar os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas fora de sua organização a grupos.</span><span class="sxs-lookup"><span data-stu-id="aed79-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="aed79-121">Adicione os hóspedes a um grupo de Microsoft 365 do centro administrativo</span><span class="sxs-lookup"><span data-stu-id="aed79-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="aed79-122">Se o convidado já existir em seu diretório, você pode adicioná-los aos seus grupos do centro administrativo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aed79-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="aed79-123">(Grupos com membros dinâmicos devem ser [gerenciados em Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span><span class="sxs-lookup"><span data-stu-id="aed79-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="aed79-124">No centro administrativo, acesse a página **Grupos**  >  **grupos.**</span><span class="sxs-lookup"><span data-stu-id="aed79-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="aed79-125">Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos e gerenciar membros** na guia **Membros.**</span><span class="sxs-lookup"><span data-stu-id="aed79-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="aed79-126">Selecione **Adicionar membros** e escolha o nome do convidado que deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="aed79-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="aed79-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="aed79-127">Select **Save**.</span></span>

<span data-ttu-id="aed79-128">Se você quiser adicionar um convidado ao diretório diretamente, você pode [adicionar Azure Active Directory usuários de colaboração B2B no portal Azure](/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="aed79-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="aed79-129">Se você quiser editar qualquer uma das informações de um convidado, você pode [adicionar ou atualizar as informações do perfil de um usuário usando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="aed79-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="aed79-130">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="aed79-130">Related content</span></span>

<span data-ttu-id="aed79-131">[Bloqueie os usuários convidados de um grupo específico](../../solutions/per-group-guest-access.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="aed79-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="aed79-132">[Gerenciar a adesão do grupo no centro administrativo Microsoft 365](add-or-remove-members-from-groups.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="aed79-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="aed79-133">[Azure Active Directory comentários de acesso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artigo)</span><span class="sxs-lookup"><span data-stu-id="aed79-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="aed79-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artigo)</span><span class="sxs-lookup"><span data-stu-id="aed79-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>