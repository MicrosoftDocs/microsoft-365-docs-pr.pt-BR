---
title: Migrações de locatário para locatário do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Saiba como migrar locatários do Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447138"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="b1964-103">Migrações de locatário para locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1964-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="b1964-104">Há várias abordagens de arquitetura para fusões, aquisições, divestitures e outros cenários que podem levar você a migrar um Microsoft 365 locatário existente para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="b1964-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="b1964-105">A maioria dos clientes trabalha com os serviços de consultoria da Microsoft ou um parceiro da Microsoft para migrar locatários, incluindo o uso de ferramentas de terceiros para migrar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b1964-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="b1964-106">Use o [modelo de arquitetura de migração de locatário para locatário](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) para entender como planejar as migrações de locatário para locatário do Microsoft 365 e as etapas de uma migração.</span><span class="sxs-lookup"><span data-stu-id="b1964-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="b1964-107">[![Modelo de migração de locatário para locatário](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="b1964-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="b1964-108">Você também pode baixar esse modelo em formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) e imprimi-lo em papel de tamanho carta, ofício ou tablóide (279 x 432 mm).</span><span class="sxs-lookup"><span data-stu-id="b1964-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="b1964-109">Este modelo fornece orientações e um ponto de partida para o planejamento com seções sobre:</span><span class="sxs-lookup"><span data-stu-id="b1964-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="b1964-110">Mapeamento de cenários de negócios para abordagens de arquitetura</span><span class="sxs-lookup"><span data-stu-id="b1964-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="b1964-111">Considerações de design</span><span class="sxs-lookup"><span data-stu-id="b1964-111">Design considerations</span></span>

<span data-ttu-id="b1964-112">Este modelo também contém exemplos detalhados de:</span><span class="sxs-lookup"><span data-stu-id="b1964-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="b1964-113">Um único fluxo de migração de eventos</span><span class="sxs-lookup"><span data-stu-id="b1964-113">A single event migration flow</span></span>
- <span data-ttu-id="b1964-114">Um fluxo de migração em fases</span><span class="sxs-lookup"><span data-stu-id="b1964-114">A phased migration flow</span></span>
- <span data-ttu-id="b1964-115">Um fluxo de movimentação ou divisão de locatário</span><span class="sxs-lookup"><span data-stu-id="b1964-115">A tenant move or split flow</span></span>