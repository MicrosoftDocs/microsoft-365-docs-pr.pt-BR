---
title: Restringir o conteúdo do site do SharePoint a um local geográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Neste artigo, saiba como restringir SharePoint sites a uma localização geográfica especificada em um ambiente multi-geo.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927259"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a><span data-ttu-id="4dec1-103">Restringir o conteúdo do site do SharePoint a um local geográfico</span><span class="sxs-lookup"><span data-stu-id="4dec1-103">Restrict SharePoint site content to a geo location</span></span>

<span data-ttu-id="4dec1-104">Em algumas circunstâncias você pode optar por impor que um site e o conteúdo do arquivo permaneça na localização geográfica onde o site foi criado, impedindo que o site movido ou impedindo o cache de conteúdo do arquivo do site em outro local geográfico.</span><span class="sxs-lookup"><span data-stu-id="4dec1-104">Under some circumstances you may choose to enforce a site and its file content to remain in the geo location where the site was created, either by preventing the site from being moved or by preventing the caching of the site's file content in another geo location.</span></span>

<span data-ttu-id="4dec1-105">Você pode fazer isso usando o cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) com o parâmetro **RestrictedToGeo**.</span><span class="sxs-lookup"><span data-stu-id="4dec1-105">You can do this by using the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet with the **RestrictedToGeo** parameter.</span></span> <span data-ttu-id="4dec1-106">Esse parâmetro possui um valor padrão de NULO, mas você pode alterá-lo para um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4dec1-106">This parameter has a default value of NULL, but you can change it to one of the following:</span></span>

|<span data-ttu-id="4dec1-107">Restrição</span><span class="sxs-lookup"><span data-stu-id="4dec1-107">Restriction</span></span>|<span data-ttu-id="4dec1-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="4dec1-108">Description</span></span>|
|:----------|:----------|
|<span data-ttu-id="4dec1-109">NoRestriction</span><span class="sxs-lookup"><span data-stu-id="4dec1-109">NoRestriction</span></span>|<span data-ttu-id="4dec1-110">O site pode ser movido para outro local geográfico.</span><span class="sxs-lookup"><span data-stu-id="4dec1-110">The site can be moved to another geo location.</span></span>|
|<span data-ttu-id="4dec1-111">BlockMoveOnly</span><span class="sxs-lookup"><span data-stu-id="4dec1-111">BlockMoveOnly</span></span>|<span data-ttu-id="4dec1-112">O site não pode ser movido para outro local geográfico, mas o conteúdo do site pode ser armazenada em cache em outros locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="4dec1-112">Site cannot be moved to another geo location, but site content can be cached in other geo locations.</span></span>|
|<span data-ttu-id="4dec1-113">BlockFull</span><span class="sxs-lookup"><span data-stu-id="4dec1-113">BlockFull</span></span>|<span data-ttu-id="4dec1-114">Site não pode ser movido para outro local geográfico e o conteúdo do arquivo completo não está armazenado em cache em outros locais geográficos.</span><span class="sxs-lookup"><span data-stu-id="4dec1-114">Site cannot be moved to another geo location, and full file content is not cached in other geo locations.</span></span> <span data-ttu-id="4dec1-115">O título dos arquivos (colhidos do conteúdo), o nome do arquivo e outras propriedades do arquivo ainda podem ser armazenados em cache em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4dec1-115">Files' title (harvested from the content), file name, and other properties of the file can still be cached in other geo-locations.</span></span><br><span data-ttu-id="4dec1-116">O conteúdo armazenado no site antes de ser configurado para o BlockFull, pode continuar a ser armazenado em cache em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4dec1-116">Content stored in the site before it was configured to BlockFull, may continue to be cached in other geo locations.</span></span>|

<span data-ttu-id="4dec1-117">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4dec1-117">Use the following syntax:</span></span>

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

<span data-ttu-id="4dec1-118">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4dec1-118">For example:</span></span>

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`