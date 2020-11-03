---
title: Cotas de busca avançada e parâmetros de uso no Microsoft 365 defender
description: Entenda vários parâmetros de uso e cotas (limites de serviço) que mantêm o serviço de busca avançada responsivo
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Search, Query, telemetria, Schema, Kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: bab63d9e5939f87f6a1edbf62d256b82552e4fe9
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847363"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cotas de busca avançada e parâmetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

Para manter o serviço em desempenho e resposta, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço"). Essas cotas e parâmetros se aplicam às consultas executadas manualmente e por [regras de detecção personalizadas](custom-detection-rules.md). Os clientes que executam várias consultas regularmente acompanham o consumo e [aplicam práticas recomendadas de otimização](advanced-hunting-best-practices.md) para minimizar as interrupções.

Consulte a tabela a seguir para entender as cotas e os parâmetros de uso existentes.

| Cota ou parâmetro | Size | Ciclo de atualização | Descrição |
|--|--|--|--|
| Intervalo de dados | 30 dias | Cada consulta | Cada consulta pode pesquisar dados dos últimos 30 dias. |
| Conjunto de resultados | 10.000 linhas | Cada consulta | Cada consulta pode retornar até 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta pode ser executada por até 10 minutos. Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.
| Recursos de CPU | Com base no tamanho do locatário | -Na hora e, em seguida, a cada 15 minutos<br>– Diariamente às 12 da meia-noite | O serviço impõe a cota diária e de 15 minutos separadamente. Para cada cota, o [portal exibe um erro](advanced-hunting-errors.md) sempre que uma consulta é executada e o locatário consome mais de 10% dos recursos alocados. As consultas são bloqueadas se o locatário tiver alcançado 100% até o ciclo seguinte ou de 15 minutos. |

>[!NOTE] 
>Um conjunto separado de cotas e parâmetros se aplica a consultas de busca avançada realizadas por meio da API. [Leia sobre APIs de busca avançada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Manipular erros de busca avançada](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)