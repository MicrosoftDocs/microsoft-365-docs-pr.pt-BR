---
title: Cotas de busca avançada e parâmetros de uso no Microsoft 365 Defender
description: Compreender várias cotas e parâmetros de uso (limites de serviço) que mantêm o serviço de busca avançada responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3d3b1055408b51e8d217f2abcb0e83ef7dd74949
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929785"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cotas de busca avançada e parâmetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Para manter o desempenho e a capacidade de resposta do serviço, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço"). Essas cotas e parâmetros se aplicam às consultas são executados manualmente e por regras [de detecção personalizadas.](custom-detection-rules.md) Os clientes que executarem várias consultas regularmente devem controlar o consumo e aplicar as práticas recomendadas de [otimização](advanced-hunting-best-practices.md) para minimizar as interrupções.

Consulte a tabela a seguir para entender as cotas e os parâmetros de uso existentes.

| Cota ou parâmetro | Size | Ciclo de atualização | Descrição |
|--|--|--|--|
| Intervalo de dados | 30 dias | Cada consulta | Cada consulta pode procurar dados de até os últimos 30 dias. |
| Conjunto de resultados | 10.000 linhas | Cada consulta | Cada consulta pode retornar até 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta pode ser executado por até 10 minutos. Se ele não for concluído dentro de 10 minutos, o serviço exibirá um erro.
| Recursos da CPU | Com base no tamanho do locatário | - Na hora e a cada 15 minutos<br>- Diariamente às 12h | O serviço impõe a cota diária e de 15 minutos separadamente. Para cada cota, o [portal exibe](advanced-hunting-errors.md) um erro sempre que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados. As consultas são bloqueadas se o locatário tiver atingido 100% até o próximo ciclo diário ou de 15 minutos. |

>[!NOTE] 
>Um conjunto separado de cotas e parâmetros se aplica a consultas de busca avançada executadas por meio da API. [Leia sobre APIs de busca avançada](https://docs.microsoft.com/microsoft-365/security/mtp/api-advanced-hunting)

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Lidar com erros de busca avançada](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)