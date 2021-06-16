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
ms.openlocfilehash: 7a7c377d8e0b72a0179ff28a93018f88d22a5325
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52931041"
---
# <a name="additional-information-for-cloud-solution-providers"></a>Informações adicionais para provedores de soluções na nuvem

Os CSPs (Provedores de Soluções na Nuvem) que suportam os clientes precisam tomar etapas adicionais durante a migração do Microsoft Cloud Deutschland para a nova região do datacenter alemão.

## <a name="partner-tenant-migration"></a>Migração de locatários de parceiros

Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados. Em vez disso, um novo locatário de Office 365 serviços será criado para cada Microsoft Partner na nova região do datacenter alemão.

Os locatários de clientes CSP serão migrados para a nova região do datacenter alemão e serão vinculados ao novo locatário de serviços Office 365 do mesmo parceiro. Após a transição do cliente, o parceiro pode gerenciar o cliente usando o novo locatário de serviços Office 365 na região do datacenter alemão.

## <a name="missing-subscriptions-in-azure"></a>Assinaturas ausentes no Azure

Depois que a transição de assinatura e licença [(fase 3)](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) tiver sido concluída, os Provedores de Soluções na Nuvem não terão mais acesso à assinatura do Azure.

Para recuperar o acesso, siga estas etapas para elevar o acesso para [gerenciar todas as assinaturas e grupos de gerenciamento do Azure.](/azure/role-based-access-control/elevate-access-global-admin)
