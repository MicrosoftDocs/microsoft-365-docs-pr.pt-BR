---
title: Impedir que convidados são adicionados a um grupo específico
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba como impedir que os convidados são adicionados a um grupo específico
ms.openlocfilehash: 572746a666586920ad85dafddbd78997940490d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907935"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="1791f-103">Impedir que os convidados seja adicionado a um grupo específico do Microsoft 365 ou à equipe do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1791f-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="1791f-104">Se você deseja permitir o acesso de convidados à maioria dos grupos e equipes, mas tem alguns onde deseja impedir o acesso de convidados, você pode bloquear o acesso de convidados para grupos e equipes individuais.</span><span class="sxs-lookup"><span data-stu-id="1791f-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="1791f-105">(O bloqueio do acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.) Isso impede que novos convidados sejam adicionados, mas não remove os convidados que já estão no grupo ou na equipe.</span><span class="sxs-lookup"><span data-stu-id="1791f-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="1791f-106">Se você usar rótulos de sensibilidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo.</span><span class="sxs-lookup"><span data-stu-id="1791f-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="1791f-107">Para obter informações sobre como fazer isso, use rótulos de sensibilidade para proteger o conteúdo no Microsoft Teams, nos grupos do [Microsoft 365 e nos sites do SharePoint.](../compliance/sensitivity-labels-teams-groups-sites.md)</span><span class="sxs-lookup"><span data-stu-id="1791f-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="1791f-108">Esta é a abordagem recomendada.</span><span class="sxs-lookup"><span data-stu-id="1791f-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="1791f-109">Alterar configurações de grupo usando o Microsoft PowerShell</span><span class="sxs-lookup"><span data-stu-id="1791f-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="1791f-110">Você também pode impedir a adição de novos convidados a grupos individuais usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1791f-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="1791f-111">(Lembre-se de que o site do SharePoint associado da equipe tem controles de compartilhamento de [convidados separados](/sharepoint/change-external-sharing-site).)</span><span class="sxs-lookup"><span data-stu-id="1791f-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="1791f-112">Você deve usar a versão de visualização do [Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidado no nível de grupo:</span><span class="sxs-lookup"><span data-stu-id="1791f-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="1791f-113">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="1791f-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="1791f-114">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="1791f-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="1791f-115">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="1791f-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="1791f-116">Você deve ter direitos de administrador global para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="1791f-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="1791f-117">Execute o script a seguir, alterando para o nome do */<GroupName/>* grupo onde você deseja bloquear o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="1791f-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="1791f-118">Para verificar suas configurações, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="1791f-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="1791f-119">A verificação tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="1791f-119">The verification looks like this:</span></span>
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="1791f-121">Permitir ou bloquear o acesso de convidados com base em seu domínio</span><span class="sxs-lookup"><span data-stu-id="1791f-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="1791f-122">Você pode permitir ou bloquear convidados que estão usando um domínio específico.</span><span class="sxs-lookup"><span data-stu-id="1791f-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="1791f-123">Por exemplo, se sua empresa (Contoso) tiver uma parceria com outra empresa (Fabrikam), você poderá adicionar Fabrikam à sua lista Permitir para que os usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="1791f-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="1791f-124">Para obter mais informações, consulte [Permitir ou bloquear convites para usuários B2B de organizações específicas.](/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="1791f-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="1791f-125">Adicionar convidados à lista de endereços global</span><span class="sxs-lookup"><span data-stu-id="1791f-125">Add guests to the global address list</span></span>

<span data-ttu-id="1791f-126">Por padrão, os convidados não estão visíveis na Lista de Endereços Globais do Exchange.</span><span class="sxs-lookup"><span data-stu-id="1791f-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="1791f-127">Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="1791f-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="1791f-128">Encontre ObjectID do convidado executando:</span><span class="sxs-lookup"><span data-stu-id="1791f-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="1791f-129">Em seguida, execute o seguinte usando os valores apropriados para ObjectID, GivenName, Surname, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="1791f-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="1791f-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1791f-130">Related topics</span></span>

[<span data-ttu-id="1791f-131">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="1791f-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="1791f-132">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="1791f-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="1791f-133">Gerenciar associação ao grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1791f-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="1791f-134">Avaliações de acesso do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1791f-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="1791f-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="1791f-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)