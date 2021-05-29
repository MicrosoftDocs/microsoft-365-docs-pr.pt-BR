---
title: Microsoft 365 Integração do Defender com o Azure Sentinel
description: Use o Azure Sentinel como SIEM para Microsoft 365 incidentes e eventos do Defender.
keywords: incidentes, alertas, investigar, analisar, responder, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707323"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Integração do Defender com o Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

O Microsoft 365 do Defender para o Azure Sentinel (visualização) envia todas as Microsoft 365 incidentes do Defender e alerta informações para o Azure Sentinel e mantém os incidentes sincronizados. 

Depois de adicionar o conector, os incidentes do Microsoft 365 Defender que incluem todos os alertas, entidades e informações relevantes associados recebidos do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade, Microsoft Defender para Office 365 e Microsoft Cloud App Security são transmitidos para o Azure Sentinel como dados de informações de segurança e gerenciamento de eventos (SIEM), fornecendo contexto para executar a triagem e a resposta a incidentes com o &mdash; &mdash; Azure Sentinel. 

Uma vez no Azure Sentinel, os incidentes permanecem sincronizados de forma bi-direcional com o Microsoft 365 Defender, permitindo que você tire proveito dos benefícios do centro de segurança do Microsoft 365 e do Azure Sentinel no portal do Azure para investigação e resposta de incidentes.

Veja como funciona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="O fluxo e o compartilhamento de dados de incidentes entre o Microsoft 365 Defender e o Azure Sentinel":::

## <a name="next-steps"></a>Próximas etapas

1. Entenda melhor a integração do [Microsoft 365 Defender com o Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Conexão dados do Microsoft 365 Defender para o Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes no Microsoft 365 Defender](incidents-overview.md)
- [Investigar incidentes com o Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
