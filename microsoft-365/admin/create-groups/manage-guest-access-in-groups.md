---
title: Gerenciar o acesso de convidados nos grupos do Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.date: 12/18/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Saiba como adicionar convidados a um grupo do Office 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: 02a951b1fbf43c22f12a89663a0aee279b191088
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352612"
---
# <a name="manage-guest-access-in-office-365-groups"></a><span data-ttu-id="ddb45-103">Gerenciar o acesso de convidados nos grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="ddb45-103">Manage guest access in Office 365 Groups</span></span>

<span data-ttu-id="ddb45-104">Por padrão, o acesso de convidados para grupos do Office 365 está ativado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ddb45-104">By default, guest access for Office 365 groups is turned on for your organization.</span></span> <span data-ttu-id="ddb45-105">Os administradores podem controlar a possibilidade de permitir o acesso de convidados a grupos para toda a sua organização ou para grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="ddb45-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="ddb45-106">Quando ele está ativado, os membros do grupo podem convidar usuários convidados para um grupo do Office 365 por meio do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="ddb45-106">When it's turned on, group members can invite guest users to an Office 365 group through Outlook on Web.</span></span> <span data-ttu-id="ddb45-107">Os convites são enviados ao proprietário do grupo para aprovação.</span><span class="sxs-lookup"><span data-stu-id="ddb45-107">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="ddb45-108">As redes corporativas do Yammer que estão no modo nativo ou na [Geografia da UE](https://go.microsoft.com/fwlink/?linkid=2107357) não dão suporte a convidados de rede.</span><span class="sxs-lookup"><span data-stu-id="ddb45-108">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="ddb45-109">Os grupos do Yammer conectados ao Office 365 atualmente não dão suporte ao acesso de convidados, mas você pode criar grupos externos não conectados na sua rede do Yammer.</span><span class="sxs-lookup"><span data-stu-id="ddb45-109">Office 365 Connected Yammer Groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="ddb45-110">Veja [criar e gerenciar grupos externos no Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ddb45-110">See [Create and manage external groups in Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a.aspx) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="ddb45-111">Editar informações de convidados</span><span class="sxs-lookup"><span data-stu-id="ddb45-111">Edit guest information</span></span>

<span data-ttu-id="ddb45-112">Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="ddb45-112">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="ddb45-113">O acesso de convidados em grupos é geralmente usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams.</span><span class="sxs-lookup"><span data-stu-id="ddb45-113">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="ddb45-114">Esses serviços têm suas próprias configurações de compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="ddb45-114">These services have their own guest sharing settings.</span></span> <span data-ttu-id="ddb45-115">Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e equipes, consulte:</span><span class="sxs-lookup"><span data-stu-id="ddb45-115">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="ddb45-116">Colaborar com convidados em um site</span><span class="sxs-lookup"><span data-stu-id="ddb45-116">Collaborate with guests in a site</span></span>](https://docs.microsoft.com/Office365/Enterprise/collaborate-in-a-site)
- [<span data-ttu-id="ddb45-117">Colaborar com convidados em uma equipe</span><span class="sxs-lookup"><span data-stu-id="ddb45-117">Collaborate with guests in a team</span></span>](https://docs.microsoft.com/Office365/Enterprise/collaborate-as-a-team)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="ddb45-118">Gerenciar o acesso de convidados a grupos</span><span class="sxs-lookup"><span data-stu-id="ddb45-118">Manage groups guest access</span></span>

<span data-ttu-id="ddb45-119">Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddb45-119">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="ddb45-120">No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">&</a> de suplementos.</span><span class="sxs-lookup"><span data-stu-id="ddb45-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">Services & add-ins</a> page.</span></span>

2. <span data-ttu-id="ddb45-121">Selecione **grupos do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="ddb45-121">Select **Office 365 Groups**.</span></span>
  
3. <span data-ttu-id="ddb45-122">Na página **grupos do Office 365** , escolha se você deseja permitir que pessoas de fora da sua organização acessem os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas de fora da sua organização a grupos.</span><span class="sxs-lookup"><span data-stu-id="ddb45-122">On the **Office 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-an-office-365-group-from-the-admin-center"></a><span data-ttu-id="ddb45-123">Adicionar convidados a um grupo do Office 365 a partir do centro de administração</span><span class="sxs-lookup"><span data-stu-id="ddb45-123">Add guests to an Office 365 group from the admin center</span></span>

<span data-ttu-id="ddb45-124">Se o convidado já existir no seu diretório, você poderá adicioná-lo aos seus grupos no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ddb45-124">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="ddb45-125">No centro de administração, vá para**a página grupos** de **grupos** > .</span><span class="sxs-lookup"><span data-stu-id="ddb45-125">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="ddb45-126">Selecione o grupo ao qual você deseja adicionar o convidado e selecione **Exibir todos e gerenciar Membros** na guia **Membros** .</span><span class="sxs-lookup"><span data-stu-id="ddb45-126">Select the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="ddb45-127">Selecione **adicionar membros**e escolha o nome do convidado que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ddb45-127">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="ddb45-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ddb45-128">Select **Save**.</span></span>

<span data-ttu-id="ddb45-129">Se quiser adicionar um convidado ao diretório diretamente, você poderá [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="ddb45-129">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="ddb45-130">Se quiser editar as informações de um convidado, você poderá [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="ddb45-130">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="ddb45-131">Bloquear usuários convidados de um grupo específico</span><span class="sxs-lookup"><span data-stu-id="ddb45-131">Block guest users from a specific group</span></span>

<span data-ttu-id="ddb45-132">Se você quiser permitir o acesso de convidados à maioria dos grupos, mas tiver algumas situações em que você deseja impedir o acesso de convidados, poderá bloquear o acesso de convidados para grupos individuais usando o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ddb45-132">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="ddb45-133">Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:</span><span class="sxs-lookup"><span data-stu-id="ddb45-133">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="ddb45-134">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="ddb45-134">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="ddb45-135">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="ddb45-135">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="ddb45-136">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="ddb45-136">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="ddb45-137">Você deve ter direitos de administrador global para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="ddb45-137">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="ddb45-138">Execute o script a seguir, \* / \* mudando para o nome do grupo onde você deseja bloquear o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="ddb45-138">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="ddb45-139">Para verificar suas configurações, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="ddb45-139">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="ddb45-140">A verificação tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="ddb45-140">The verification looks like this:</span></span>
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="ddb45-142">Permitir ou bloquear o acesso de convidados com base em seu domínio</span><span class="sxs-lookup"><span data-stu-id="ddb45-142">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="ddb45-143">Você pode permitir ou bloquear usuários convidados que usam um domínio específico.</span><span class="sxs-lookup"><span data-stu-id="ddb45-143">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="ddb45-144">Por exemplo, se sua empresa (contoso) tem uma parceria com outra empresa (Fabrikam), você pode adicionar a Fabrikam à sua lista de permissões para que os usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="ddb45-144">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="ddb45-145">Para obter mais informações, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="ddb45-145">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="ddb45-146">Adicionar convidados à lista de endereços global</span><span class="sxs-lookup"><span data-stu-id="ddb45-146">Add guests to the global address list</span></span>

<span data-ttu-id="ddb45-147">Por padrão, os convidados não estão visíveis na lista de endereços global do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ddb45-147">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="ddb45-148">Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="ddb45-148">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="ddb45-149">Encontre o ObjectID do usuário convidado executando:</span><span class="sxs-lookup"><span data-stu-id="ddb45-149">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="ddb45-150">Em seguida, execute o seguinte usando os valores apropriados para ObjectID, excertoname, sobrenome, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="ddb45-150">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="ddb45-151">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="ddb45-151">Related articles</span></span>

[<span data-ttu-id="ddb45-152">Gerenciar a associação de grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ddb45-152">Manage Group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="ddb45-153">Revisões do acesso ao Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="ddb45-153">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="ddb45-154">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="ddb45-154">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
