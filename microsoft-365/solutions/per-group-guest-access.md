---
title: Bloquear usuários convidados de um grupo específico
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
description: Bloquear usuários convidados de um grupo específico
ms.openlocfilehash: 17e5f8f9ab4107a12a0607dca3795d54b7be012c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377300"
---
# <a name="block-guest-users-from-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="4374f-103">Bloquear usuários convidados de um grupo específico do Microsoft 365 ou uma equipe do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4374f-103">Block guest users from a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="4374f-104">Se você quiser permitir o acesso de convidados à maioria dos grupos e equipes, mas tiver algumas situações em que você deseja impedir o acesso de convidados, é possível bloquear o acesso de convidados para grupos e equipes individuais.</span><span class="sxs-lookup"><span data-stu-id="4374f-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="4374f-105">(Bloquear o acesso de convidados a uma equipe é feito bloqueando o acesso de convidados ao grupo associado.)</span><span class="sxs-lookup"><span data-stu-id="4374f-105">(Blocking guest access to a team is done by blocking guest access to the associated group.)</span></span>

<span data-ttu-id="4374f-106">Se você usar rótulos de confidencialidade em sua organização, recomendamos usá-los para controlar o acesso de convidados por grupo.</span><span class="sxs-lookup"><span data-stu-id="4374f-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="4374f-107">Para obter informações sobre como fazer isso, [use rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, microsoft 365 Groups e sites do SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="4374f-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="4374f-108">Esta é a abordagem recomendada.</span><span class="sxs-lookup"><span data-stu-id="4374f-108">This is the recommended approach.</span></span>

<span data-ttu-id="4374f-109">Você também pode bloquear o acesso de convidados a grupos individuais usando o Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4374f-109">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="4374f-110">Você deve usar a versão de visualização do [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (nome do módulo **AzureADPreview**) para alterar a configuração de acesso de convidados em nível de Grupo:</span><span class="sxs-lookup"><span data-stu-id="4374f-110">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="4374f-111">Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) e siga as instruções para instalar a versão de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="4374f-111">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="4374f-112">Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.</span><span class="sxs-lookup"><span data-stu-id="4374f-112">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="4374f-113">Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.</span><span class="sxs-lookup"><span data-stu-id="4374f-113">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="4374f-114">Você deve ter direitos de administrador global para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="4374f-114">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="4374f-115">Execute o script a seguir, mudando */<GroupName/>* para o nome do grupo onde você deseja bloquear o acesso de convidados.</span><span class="sxs-lookup"><span data-stu-id="4374f-115">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="4374f-116">Para verificar suas configurações, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="4374f-116">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="4374f-117">A verificação tem a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="4374f-117">The verification looks like this:</span></span>
    
![Captura de tela da janela do PowerShell mostrando que o acesso ao grupo de convidados foi definido como false.](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="4374f-119">Permitir ou bloquear o acesso de convidados com base em seu domínio</span><span class="sxs-lookup"><span data-stu-id="4374f-119">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="4374f-120">Você pode permitir ou bloquear usuários convidados que usam um domínio específico.</span><span class="sxs-lookup"><span data-stu-id="4374f-120">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="4374f-121">Por exemplo, se sua empresa (contoso) tem uma parceria com outra empresa (Fabrikam), você pode adicionar a Fabrikam à sua lista de permissões para que os usuários possam adicionar esses convidados aos seus grupos.</span><span class="sxs-lookup"><span data-stu-id="4374f-121">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="4374f-122">Para obter mais informações, consulte [permitir ou bloquear convites para usuários B2B de organizações específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="4374f-122">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="4374f-123">Adicionar convidados à lista de endereços global</span><span class="sxs-lookup"><span data-stu-id="4374f-123">Add guests to the global address list</span></span>

<span data-ttu-id="4374f-124">Por padrão, os convidados não estão visíveis na lista de endereços global do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4374f-124">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="4374f-125">Use as etapas listadas abaixo para tornar um convidado visível na lista de endereços global.</span><span class="sxs-lookup"><span data-stu-id="4374f-125">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="4374f-126">Encontre o ObjectID do usuário convidado executando:</span><span class="sxs-lookup"><span data-stu-id="4374f-126">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="4374f-127">Em seguida, execute o seguinte usando os valores apropriados para ObjectID, excertoname, sobrenome, DisplayName e TelephoneNumber.</span><span class="sxs-lookup"><span data-stu-id="4374f-127">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="4374f-128">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4374f-128">Related articles</span></span>

[<span data-ttu-id="4374f-129">Gerenciar a associação de grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4374f-129">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="4374f-130">Revisões do acesso ao Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="4374f-130">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="4374f-131">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="4374f-131">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)