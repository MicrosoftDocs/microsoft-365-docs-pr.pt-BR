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
# <a name="additional-information-for-cloud-solution-providers"></a>Informações adicionais para provedores de soluções na nuvem

Os CSPs (Provedores de Soluções na Nuvem) que suportam os clientes precisam tomar etapas adicionais durante a migração do Microsoft Cloud Deutschland para a nova região do datacenter alemão.

## <a name="partner-tenant-migration"></a>Migração de locatários de parceiros

Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados. Em vez disso, um novo locatário de Office 365 serviços será criado para cada Microsoft Partner na nova região do datacenter alemão.

Os locatários de clientes CSP serão migrados para a nova região do datacenter alemão e serão vinculados ao novo locatário de serviços Office 365 do mesmo parceiro. Após a transição do cliente, o parceiro pode gerenciar o cliente usando o novo locatário de serviços Office 365 na região do datacenter alemão.

## <a name="missing-subscriptions-in-azure"></a>Assinaturas ausentes no Azure

Depois que a transição de assinatura e licença [(fase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) tiver sido concluída, os Provedores de Soluções na Nuvem não terão mais acesso à assinatura do Azure.

Para recuperar o acesso, siga estas etapas para elevar o acesso para [gerenciar todas as assinaturas e grupos de gerenciamento do Azure.](/azure/role-based-access-control/elevate-access-global-admin)
