---
title: Microsoft 365 migrações de locatário para locatário
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
description: Saiba como migrar Microsoft 365 locatários.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819709"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="2d2e1-103">Microsoft 365 migrações de locatário para locatário</span><span class="sxs-lookup"><span data-stu-id="2d2e1-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="2d2e1-104">Há várias abordagens de arquitetura para fusões, aquisições, desinvestres e outros cenários que podem levar você a migrar um locatário Microsoft 365 existente para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="2d2e1-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="2d2e1-105">A maioria dos clientes trabalha com o Microsoft Consulting Services ou com um parceiro da Microsoft para migrar locatários, incluindo o uso de ferramentas de terceiros para migrar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2d2e1-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="2d2e1-106">Use o [modelo de](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) arquitetura de migração locatário para locatário para entender como planejar Microsoft 365 migrações de locatário para locatário e as etapas de uma migração.</span><span class="sxs-lookup"><span data-stu-id="2d2e1-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="2d2e1-107">[![Modelo de migração de locatário para locatário](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="2d2e1-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="2d2e1-108">Baixe esse modelo no [formato PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) e imprima-o em papel de carta, legal ou tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="2d2e1-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="2d2e1-109">Este modelo fornece orientações e um ponto de partida para planejamento com seções em:</span><span class="sxs-lookup"><span data-stu-id="2d2e1-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="2d2e1-110">Mapeamento de cenários de negócios para abordagens de arquitetura</span><span class="sxs-lookup"><span data-stu-id="2d2e1-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="2d2e1-111">Considerações de design</span><span class="sxs-lookup"><span data-stu-id="2d2e1-111">Design considerations</span></span>

<span data-ttu-id="2d2e1-112">Este modelo também contém exemplos detalhados de:</span><span class="sxs-lookup"><span data-stu-id="2d2e1-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="2d2e1-113">Um único fluxo de migração de eventos</span><span class="sxs-lookup"><span data-stu-id="2d2e1-113">A single event migration flow</span></span>
- <span data-ttu-id="2d2e1-114">Um fluxo de migração em fases</span><span class="sxs-lookup"><span data-stu-id="2d2e1-114">A phased migration flow</span></span>
- <span data-ttu-id="2d2e1-115">Uma movimentação de locatário ou fluxo dividido</span><span class="sxs-lookup"><span data-stu-id="2d2e1-115">A tenant move or split flow</span></span>
