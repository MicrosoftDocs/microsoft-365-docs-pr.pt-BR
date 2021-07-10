---
title: Funcionalidades multigeográficas no OneDrive e no SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Expanda sua presença no Microsoft 365 para várias regiões geográficas com recursos multigeográficos no OneDrive Online.
ms.openlocfilehash: 405f876317a6cec6defdf3f1a49b0dc32ac0add2
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362277"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="a9540-103">Funcionalidades multigeográficas no OneDrive e no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="a9540-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="a9540-104">Recursos multi-geo no OneDrive e no SharePoint Online permitem o controle de recursos compartilhados, como sites de equipe SharePoint e caixas de correio Microsoft 365 Group armazenadas em repouso em uma localização geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="a9540-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a specified geo location.</span></span>

<span data-ttu-id="a9540-105">Cada usuário, caixa de correio do Grupo e site do SharePoint possui uma Localização Preferencial do Dados (PDL) que indica a localização geográfica onde os dados relacionados devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="a9540-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="a9540-106">Os dados pessoais do usuário (caixa de correio do Exchange e do OneDrive), juntamente com os grupos do Microsoft 365 ou sites do SharePoint criados por eles, podem ser armazenados em uma localização geográfica especificada para atender aos requisitos de residência dos dados.</span><span class="sxs-lookup"><span data-stu-id="a9540-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="a9540-107">Você pode [especificar administradores diferentes para cada localização geográfica](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="a9540-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="a9540-108">Os usuários têm uma experiência perfeita ao usar os serviços do Microsoft 365, incluindo os aplicativos do Office, OneDrive e Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a9540-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="a9540-109">Para obter mais detalhes, confira [Experiência do usuário em um ambiente Multi-Geo](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="a9540-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="a9540-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="a9540-110">OneDrive</span></span>

<span data-ttu-id="a9540-111">Cada usuário do OneDrive pode ser provisionado ou [movido por um administrador](move-onedrive-between-geo-locations.md) em um localização por satélite de acordo com PDL do usuário.</span><span class="sxs-lookup"><span data-stu-id="a9540-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="a9540-112">Os arquivos pessoais são mantidos nessa localização geográfica, embora eles possam ser compartilhados com usuários em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="a9540-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="a9540-113">Sites e Grupos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="a9540-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="a9540-114">O gerenciamento de recursos multigeográficos está disponível por meio do Centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a9540-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="a9540-115">Informações detalhadas podem ser encontradas em [postagem de blog correspondentes](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="a9540-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="a9540-116">Quando um usuário cria um site conectado a um grupo do SharePoint no ambiente multigeográfico, o PDL é usado para determinar a localização geográfica onde o site e sua caixa de correio de Grupo associada foram criados.</span><span class="sxs-lookup"><span data-stu-id="a9540-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="a9540-117">(Se o valor PDL do usuário ainda não foi definida ou foi definida em uma localização geográfica que ainda não foi configurada como uma localização por satélite, os sites e as caixas de correio são criados em uma localização central.)</span><span class="sxs-lookup"><span data-stu-id="a9540-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="a9540-118">Microsoft 365 que não sejam Exchange, OneDrive, SharePoint e Teams não são Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="a9540-118">Microsoft 365 services other than Exchange, OneDrive, SharePoint, and Teams are not Multi-Geo.</span></span> <span data-ttu-id="a9540-119">No entanto, Microsoft 365 grupos criados por esses serviços serão configurados com o PDL do criador e sua caixa de correio Exchange Group, SharePoint site é provisionado no geo correspondente.</span><span class="sxs-lookup"><span data-stu-id="a9540-119">However, Microsoft 365 Groups that are created by these services will be configured with the PDL of the creator and their Exchange Group mailbox, SharePoint site are provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="a9540-120">Gerenciar o ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="a9540-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="a9540-121">A configuração e o gerenciamento do ambiente multigeográfico são feitos pelo centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a9540-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Captura de tela da página de localizações geográficas do centro de administração SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="a9540-123">(Algumas ações, como mover um site do SharePoint ou um site do OneDrive necessitam do Microsoft PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="a9540-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="a9540-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="a9540-124">See also</span></span>

[<span data-ttu-id="a9540-125">Várias regiões nos grupos do SharePoint e do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9540-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="a9540-126">Administrar um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="a9540-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="a9540-127">Cotas de armazenamento do SharePoint em ambientes multigeográficos</span><span class="sxs-lookup"><span data-stu-id="a9540-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="a9540-128">Administrar caixas de correio do Exchange Online em um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="a9540-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
