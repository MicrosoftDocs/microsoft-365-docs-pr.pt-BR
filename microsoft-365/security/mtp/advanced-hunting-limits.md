---
title: Limites de busca avançada na proteção contra ameaças da Microsoft
description: Entender vários limites de serviço que mantêm o serviço de busca avançada responsivo
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, esquema, Kusto, limite de CPU, limite de consulta, recursos, resultados máximos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ad21b4241d7cbbcc85639a0a10b47971e5fcebcb
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412689"
---
# <a name="advanced-hunting-service-limits"></a>Limites de serviço de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Para manter o serviço em execução e responsivo, a busca avançada define vários limites para consultas executadas manualmente e por [regras de detecção personalizadas](custom-detection-rules.md). Consulte a tabela a seguir para entender esses limites.

| Limite | Size | Ciclo de atualização | Descrição |
|--|--|--|--|
| Intervalo de dados | 30 dias | Cada consulta | Cada consulta pode pesquisar dados dos últimos 30 dias. |
| Conjunto de resultados | 10.000 linhas | Cada consulta | Cada consulta pode retornar até 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta pode ser executada por até 10 minutos. Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.
| Recursos de CPU | Com base no tamanho do locatário | -Na hora e, em seguida, a cada 15 minutos<br>– Diariamente às 12 da meia-noite | O serviço impõe o limite diário e de 15 minutos separadamente. Para cada limite, o [portal exibe um erro](advanced-hunting-errors.md) sempre que uma consulta é executada e o locatário consome mais de 10% dos recursos alocados. As consultas são bloqueadas se o locatário tiver alcançado 100% até o ciclo seguinte ou de 15 minutos. |

>[!NOTE] 
>Um conjunto separado de limites se aplica a consultas de busca avançada realizadas por meio da API. [Leia sobre APIs de busca avançada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

Os clientes que executam várias consultas regularmente acompanham o consumo e [aplicam as práticas recomendadas de otimização](advanced-hunting-best-practices.md) para minimizar a interrupção resultante da excedeção desses limites.

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Manipular erros de busca avançada](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
