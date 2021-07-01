---
title: Integração do Microsoft 365 Defender com o Azure Sentinel
description: Use o Azure Sentinel como SIEM para Microsoft 365 Defender incidentes e eventos.
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
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229906"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Integração do Microsoft 365 Defender com o Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

O Microsoft 365 Defender conector do Azure Sentinel (visualização) envia todas as informações Microsoft 365 Defender incidentes e alertas para o Azure Sentinel e mantém os incidentes sincronizados. 

Depois de adicionar o conector, Microsoft 365 Defender incidentes que incluem todos os alertas, entidades e informações relevantes associados recebidos do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade, Microsoft Defender para Office 365 e Microsoft Cloud App Security são transmitidos para o Azure Sentinel como dados de informações de segurança e gerenciamento de eventos (SIEM), fornecendo contexto para executar a triagem e a resposta a incidentes com o &mdash; &mdash; Azure Sentinel. 

Uma vez no Azure Sentinel, os incidentes permanecem sincronizados bi-direcionalmente com o Microsoft 365 Defender, permitindo que você tire proveito dos benefícios do centro de segurança do Microsoft 365 e do Azure Sentinel no portal do Azure para investigação e resposta de incidentes.

Assista a esta breve visão geral da integração do Azure Sentinel com Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Veja como funciona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="O fluxo e o compartilhamento de dados de incidentes entre o Microsoft 365 Defender e o Azure Sentinel":::

## <a name="next-steps"></a>Próximas etapas

1. Obter uma compreensão mais profunda sobre [Microsoft 365 Defender integração com o Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Conexão dados do Microsoft 365 Defender para o Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes Microsoft 365 Defender](incidents-overview.md)
- [Investigar incidentes com o Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
