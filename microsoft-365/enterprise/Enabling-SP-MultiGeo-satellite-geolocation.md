---
title: Ativando as funcionalidades multigeográficas do SharePoint em sua localização geográfica por satélite
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
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Este artigo fornece informações para administradores globais ou do SharePoint sobre a habilitação do SharePoint Multi-Geo em localizações geográficas por satélite.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687490"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="f581b-103">Ativando as funcionalidades multigeográficas do SharePoint em sua localização geográfica por satélite</span><span class="sxs-lookup"><span data-stu-id="f581b-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="f581b-104">Este artigo destina-se a administradores Globais ou do SharePoint que tenham criado um local de satélite multigeográfico **antes** dos recursos multigeográficos do SharePoint terem se tornado disponíveis, em 27 de março de 2019, e que não tenham habilitado as funcionalidades multigeográficas do SharePoint em suas localizações geográficas por satélite.</span><span class="sxs-lookup"><span data-stu-id="f581b-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="f581b-105">Se você adicionou uma nova localização geográfica **depois de 27 de março**, não será necessário executar estas instruções, pois sua nova localização geográfica já estará habilitada para as funcionalidades geográficas do OneDrive e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f581b-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="f581b-106">Estas instruções permitirão que você habilite o SharePoint em seu local de satélite, para que os seus usuários de satélite multigeográfico aproveitem as funcionalidades multigeográficas do OneDrive e SharePoint no O365.</span><span class="sxs-lookup"><span data-stu-id="f581b-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="f581b-107">Por favor, note que esta é uma habilitação unidirecional.</span><span class="sxs-lookup"><span data-stu-id="f581b-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="f581b-108">Depois de definir o modo SPO, você não poderá reverter seu locatário para somente o modo multigeográfico do OneDrive sem um escalonamento com suporte.</span><span class="sxs-lookup"><span data-stu-id="f581b-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="f581b-109">Para definir uma localização geográfica no modo SPO</span><span class="sxs-lookup"><span data-stu-id="f581b-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="f581b-110">Para definir uma localização geográfica no modo SPO, conecte-se à localização geográfica que você deseja definir no modo SPO:</span><span class="sxs-lookup"><span data-stu-id="f581b-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="f581b-111">Abra seu Shell de Gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f581b-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="f581b-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span><span class="sxs-lookup"><span data-stu-id="f581b-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="f581b-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="f581b-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="f581b-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="f581b-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="f581b-115">Essa operação normalmente leva cerca de uma hora enquanto executamos vários retornos de publicação no serviço e recarimbamos seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f581b-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="f581b-116">Após pelo menos 1 hora, execute um Get-SPOMultiGeoExperience.</span><span class="sxs-lookup"><span data-stu-id="f581b-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="f581b-117">Isso mostrará se esta localização geográfica está no modo SPO.</span><span class="sxs-lookup"><span data-stu-id="f581b-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="f581b-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="f581b-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="f581b-119">Certos caches no serviço são atualizados a cada 24 horas, portanto, é possível que, por um período de até 24 horas, o seu satélite geográfico possa se comportar intermitentemente como se ainda estivesse no modo ODB.</span><span class="sxs-lookup"><span data-stu-id="f581b-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="f581b-120">Isso não gera problemas técnicos.</span><span class="sxs-lookup"><span data-stu-id="f581b-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="f581b-121">Para obter informações adicionais sobre as funcionalidades multigeográficas do SharePoint, consulte [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="f581b-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


