---
title: Configurar o Microsoft 365 Multi-Geo eDiscovery
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
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Saiba como usar o parâmetro Region para configurar a Descoberta e Para uso em locais de satélite em Microsoft 365 Multi-Geo.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923715"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a><span data-ttu-id="4a438-103">Configuração do Microsoft 365 Multi-Geo eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4a438-103">Microsoft 365 Multi-Geo eDiscovery configuration</span></span>

<span data-ttu-id="4a438-104">[Advanced eDiscovery recursos](../compliance/overview-ediscovery-20.md) permitem que um administrador de Descoberta eDiscoveria multi-geográfica pesquise todos os geos sem precisar usar um filtro de segurança "Região".</span><span class="sxs-lookup"><span data-stu-id="4a438-104">[Advanced eDiscovery capabilities](../compliance/overview-ediscovery-20.md) allow a multi-geo eDiscovery administrator to search all of the geos without needing to utilize a "Region" security filter.</span></span> <span data-ttu-id="4a438-105">Os dados são exportados para a instância do Azure da localização central do locatário multi-geo.</span><span class="sxs-lookup"><span data-stu-id="4a438-105">Data is exported to the Azure instance of the central location of the multi-geo tenant.</span></span> 

<span data-ttu-id="4a438-106">Sem recursos avançados de Descoberta e, um gerente de Descoberta e/ou administrador de um locatário multi-geo será capaz de conduzir a Descoberta eDiscovery somente no local central desse locatário.</span><span class="sxs-lookup"><span data-stu-id="4a438-106">Without advanced eDiscovery capabilities, an eDiscovery manager or administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="4a438-107">Para dar suporte à capacidade de conduzir a Descoberta Digital para locais satélite, um novo parâmetro de filtro de segurança de conformidade chamado "Região" está disponível por meio do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a438-107">To support the ability to conduct eDiscovery for satellite locations, a new compliance security filter parameter named "Region" is available via PowerShell.</span></span> <span data-ttu-id="4a438-108">Esse parâmetro pode ser usado por locatários cuja localização central está na América do Norte, Europa ou Pacífico Asiático.</span><span class="sxs-lookup"><span data-stu-id="4a438-108">This parameter can be used by tenants whose central location is in North America, Europe, or Asia Pacific.</span></span> <span data-ttu-id="4a438-109">Advanced eDiscovery é recomendado para locatários cuja localização central não está na América do Norte, Europa ou Pacífico Asiático e que precisam executar a Descoberta eDiscovery em locais geo-satélite.</span><span class="sxs-lookup"><span data-stu-id="4a438-109">Advanced eDiscovery is recommended for tenants whose central location is not in North America, Europe, or Asia Pacific and who need to perform eDiscovery across satellite geo locations.</span></span> 

<span data-ttu-id="4a438-110">O administrador global do Microsoft 365 deve atribuir permissões ao eDiscovery Manager para permitir que outras pessoas executem o eDiscovery e atribuam o parâmetro "Região" no seu Filtro de segurança de conformidade aplicável para especificar a região de execução do eDiscovery como localização do satélite; caso contrário, nenhum eDiscovery será executado na localização por satélite.</span><span class="sxs-lookup"><span data-stu-id="4a438-110">The Microsoft 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span>

<span data-ttu-id="4a438-p103">Quando a função de gerente ou administrador de Descoberta Eletrônica é definida para uma determinada localização satélite, o gerente ou o administrador só poderá realizar ações de pesquisa de Descoberta Eletrônica em sites do SharePoint e do OneDrive naquela localização satélite. Se ele tentar pesquisar sites do SharePoint ou do OneDrive fora da localização satélite especificada, nenhum resultado será apresentado. Além disso, quando o gerente ou administrador de Descoberta Eletrônica de uma localização satélite aciona uma exportação, os dados são exportados para a instância do Azure daquela região. Isso ajuda as organizações a permanecerem em conformidade, não permitindo que o conteúdo seja exportado para além de fronteiras controladas.</span><span class="sxs-lookup"><span data-stu-id="4a438-p103">When the eDiscovery Manager or Administrator role is set for a particular satellite location, the eDiscovery Manager or Administrator will only be able to perform eDiscovery search actions against the SharePoint sites and OneDrive sites located in that satellite location. If an eDiscovery Manager or Administrator attempts to search SharePoint or OneDrive sites outside the specified satellite location, no results will be returned. Also, when the eDiscovery Manager or Administrator for a satellite location triggers an export, data is exported to the Azure instance of that region. This helps organizations stay in compliance by not allowing content to be exported across controlled borders.</span></span>

> [!NOTE]
> <span data-ttu-id="4a438-115">Caso seja necessário que o gerente de Descoberta Eletrônica pesquise diversas localizações satélites no SharePoint, será necessário criar outra conta de usuário para ele, a qual especifique a localização satélite alternativa onde se encontram os sites do OneDrive ou do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a438-115">If it's necessary for an eDiscovery Manager to search across multiple SharePoint satellite locations, another user account will need to be created for the eDiscovery Manager which specifies the alternate satellite location where the OneDrive or SharePoint sites are located.</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

<span data-ttu-id="4a438-116">Para configurar o Filtro de Segurança de Conformidade para uma região:</span><span class="sxs-lookup"><span data-stu-id="4a438-116">To set the Compliance Security Filter for a Region:</span></span>

1. [<span data-ttu-id="4a438-117">Conecte-se ao Centro de conformidade e segurança do Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a438-117">Connect to Microsoft 365 Security & Compliance Center PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell)

2. <span data-ttu-id="4a438-118">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4a438-118">Use the following syntax:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   <span data-ttu-id="4a438-119">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4a438-119">For example:</span></span>

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

<span data-ttu-id="4a438-120">Confira o artigo sobre o cmdlet [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) para ver os sintaxe e parâmetros adicionais.</span><span class="sxs-lookup"><span data-stu-id="4a438-120">See the [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) article for additional parameters and syntax.</span></span>