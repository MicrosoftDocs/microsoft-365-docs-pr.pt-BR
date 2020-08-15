---
title: Adicionar ou remover um administrador geográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection: SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Precisa configurar administradores separados para cada localização geográfica? Saiba como adicionar ou remover um administrador geográfico no Microsoft 365 Multi-Geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a3d916bfec2c53850f923fb5322298e9ff440ca
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687495"
---
# <a name="add-or-remove-a-geo-administrator-in-microsoft-365-multi-geo"></a><span data-ttu-id="ef31a-104">Adicionar ou remover um administrador geográfico no Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="ef31a-104">Add or remove a geo administrator in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="ef31a-105">Você pode configurar administradores separados para cada localização geográfica que há em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="ef31a-105">You can configure separate administrators for each geo location that you have in your tenant.</span></span> <span data-ttu-id="ef31a-106">Esses administradores terão acesso às configurações do SharePoint Online e do OneDrive específicas para sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="ef31a-106">These administrators will have access to the SharePoint Online and OneDrive settings that are specific to their geo location.</span></span>

<span data-ttu-id="ef31a-107">Alguns serviços, como o repositório de termos, são administrados da localização central e replicados para as localizações via satélite.</span><span class="sxs-lookup"><span data-stu-id="ef31a-107">Some services - such as the term store - are administered from the central location and replicated to satellite locations.</span></span> <span data-ttu-id="ef31a-108">O administrador geográfico da localização central tem acesso a elas, enquanto que os administradores geográficos via satélite não.</span><span class="sxs-lookup"><span data-stu-id="ef31a-108">The geo admin for the central location has access to these, whereas geo admins for satellite locations don't.</span></span>

<span data-ttu-id="ef31a-109">Os administradores globais e administradores do SharePoint Online continuam a ter acesso às configurações da localização local e das localizações via satélite.</span><span class="sxs-lookup"><span data-stu-id="ef31a-109">Global administrators and SharePoint Online administrators continue to have access to settings in the central location and all satellite locations.</span></span>

## <a name="configuring-geo-administrators"></a><span data-ttu-id="ef31a-110">Configurar os administradores geográficos</span><span class="sxs-lookup"><span data-stu-id="ef31a-110">Configuring geo administrators</span></span>

<span data-ttu-id="ef31a-111">Configurar os administradores geográficos exige o módulo PowerShell do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ef31a-111">Configuring geo admins requires SharePoint Online PowerShell module.</span></span>

<span data-ttu-id="ef31a-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) para se conectar ao centro de administração da localização geográfica onde você deseja adicionar o administrador geográfico. (Por exemplo, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span><span class="sxs-lookup"><span data-stu-id="ef31a-112">Use [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/Connect-SPOService) to connect to the admin center of the geo location where you want to add the geo admin. (For example, Connect-SPOService  https://ContosoEUR-admin.sharepoint.com.)</span></span>

<span data-ttu-id="ef31a-113">Para exibir os administradores geográficos existentes de um local, execute `Get-SPOGeoAdministrator`</span><span class="sxs-lookup"><span data-stu-id="ef31a-113">To view the existing geo admins of a location, run `Get-SPOGeoAdministrator`</span></span>

### <a name="adding-a-user-as-a-geo-admin"></a><span data-ttu-id="ef31a-114">Adicionar um usuário como um administrador geográfico</span><span class="sxs-lookup"><span data-stu-id="ef31a-114">Adding a user as a geo admin</span></span>

<span data-ttu-id="ef31a-115">Para adicionar um usuário como um administrador geográfico, execute `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="ef31a-115">To add a user as a geo admin, run `Add-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

<span data-ttu-id="ef31a-116">Para remover um usuário como um administrador geográfico de um local, execute  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span><span class="sxs-lookup"><span data-stu-id="ef31a-116">To remove a user as a Geo Admin of a location, run  `Remove-SPOGeoAdministrator -UserPrincipalName <UPN>`</span></span>

### <a name="adding-a-group-as-a-geo-admin"></a><span data-ttu-id="ef31a-117">Adicionar um grupo como um administrador geográfico</span><span class="sxs-lookup"><span data-stu-id="ef31a-117">Adding a group as a geo admin</span></span>

<span data-ttu-id="ef31a-118">Você pode adicionar um grupo de segurança ou um grupo de segurança habilitado para e-mails como administrador geográfico. (Grupos de distribuição e grupos do Microsoft 365 não são suportados.)</span><span class="sxs-lookup"><span data-stu-id="ef31a-118">You can add a security group or a mail-enabled security group as a geo admin. (Distribution groups and Microsoft 365 Groups are not supported.)</span></span>

<span data-ttu-id="ef31a-119">Para adicionar um grupo como um administrador geográfico, execute `Add-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="ef31a-119">To add a group as a geo administrator, run `Add-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="ef31a-120">Para remover um grupo como um administrador geográfico, execute `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span><span class="sxs-lookup"><span data-stu-id="ef31a-120">To remove a group as a geo administrator, run `Remove-SPOGeoAdministrator -GroupAlias <alias>`</span></span>

<span data-ttu-id="ef31a-121">Observe que nem todos os grupos de segurança têm um alias de grupo.</span><span class="sxs-lookup"><span data-stu-id="ef31a-121">Note that not all security groups have a group alias.</span></span> <span data-ttu-id="ef31a-122">Se você quiser adicionar um grupo de segurança que tenha um alias, execute [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) para recuperar uma lista de grupos, localizar o ObjectID do grupo de segurança e, em seguida, execute:</span><span class="sxs-lookup"><span data-stu-id="ef31a-122">If you want to add a security group that does not have an alias, run [Get-MsolGroup](https://docs.microsoft.com/powershell/module/msonline/get-msolgroup) to retrieve a list of groups, find your security group's ObjectID, and then run:</span></span>

`Add-SPOGeoAdministrator -ObjectID <ObjectID>`

<span data-ttu-id="ef31a-123">Para remover um grupo usando o ObjectID, execute `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span><span class="sxs-lookup"><span data-stu-id="ef31a-123">To remove a group by using the ObjectID, run `Remove-SPOGeoAdministrator -ObjectID <ObjectID>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef31a-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ef31a-124">Related topics</span></span>

[<span data-ttu-id="ef31a-125">Adicionar-SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef31a-125">Add-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/add-spogeoadministrator)

[<span data-ttu-id="ef31a-126">Obter SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef31a-126">Get-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spogeoadministrator)

[<span data-ttu-id="ef31a-127">Remover SPOGeoAdministrator</span><span class="sxs-lookup"><span data-stu-id="ef31a-127">Remove-SPOGeoAdministrator</span></span>](https://docs.microsoft.com/powershell/module/sharepoint-online/remove-spogeoadministrator)

[<span data-ttu-id="ef31a-128">Configurar um alias (MailNickName) para um grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="ef31a-128">Set an alias (MailNickName) for a security group</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup)