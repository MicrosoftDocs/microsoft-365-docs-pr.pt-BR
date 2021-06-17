---
title: Informações adicionais para provedores de soluções na nuvem
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: Informações adicionais para Provedores de Soluções na Nuvem relevantes para a migração do Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984911"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="7fa81-103">Informações adicionais para provedores de soluções na nuvem</span><span class="sxs-lookup"><span data-stu-id="7fa81-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="7fa81-104">Os CSPs (Provedores de Soluções na Nuvem) que suportam os clientes precisam tomar etapas adicionais durante a migração do Microsoft Cloud Deutschland para a nova região do datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="7fa81-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="7fa81-105">Migração de locatários de parceiros</span><span class="sxs-lookup"><span data-stu-id="7fa81-105">Partner tenant migration</span></span>

<span data-ttu-id="7fa81-106">Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados.</span><span class="sxs-lookup"><span data-stu-id="7fa81-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="7fa81-107">Em vez disso, um novo locatário de Office 365 serviços será criado para cada Microsoft Partner na nova região do datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="7fa81-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="7fa81-108">Os locatários de clientes CSP serão migrados para a nova região do datacenter alemão e serão vinculados ao novo locatário de serviços Office 365 do mesmo parceiro.</span><span class="sxs-lookup"><span data-stu-id="7fa81-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="7fa81-109">Após a transição do cliente, o parceiro pode gerenciar o cliente usando o novo locatário de serviços Office 365 na região do datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="7fa81-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="7fa81-110">Assinaturas ausentes no Azure</span><span class="sxs-lookup"><span data-stu-id="7fa81-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="7fa81-111">Depois que a transição de assinatura e licença [(fase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) tiver sido concluída, os Provedores de Soluções na Nuvem não terão mais acesso à assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="7fa81-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="7fa81-112">Para recuperar o acesso, siga estas etapas para elevar o acesso para [gerenciar todas as assinaturas e grupos de gerenciamento do Azure.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="7fa81-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
