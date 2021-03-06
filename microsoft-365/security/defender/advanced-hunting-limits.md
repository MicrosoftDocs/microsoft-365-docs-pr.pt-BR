---
title: Cotas de busca avançadas e parâmetros de uso no Microsoft 365 Defender
description: Entenda várias cotas e parâmetros de uso (limites de serviço) que mantêm o serviço de busca avançado responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos, cota, parâmetros, alocação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7563a8299bbe7d543b065bb25eeb3bc90a854b9
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245595"
---
# <a name="advanced-hunting-quotas-and-usage-parameters"></a>Cotas de busca avançadas e parâmetros de uso

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Para manter o serviço performant e responsivo, a busca avançada define várias cotas e parâmetros de uso (também conhecidos como "limites de serviço"). Essas cotas e parâmetros se aplicam separadamente às consultas executados manualmente e às consultas que são executados usando regras [de detecção personalizadas.](custom-detection-rules.md) Os clientes que executarem várias consultas regularmente devem estar atentos a esses limites e aplicar práticas recomendadas de otimização [para](advanced-hunting-best-practices.md) minimizar interrupções.

Consulte a tabela a seguir para entender cotas e parâmetros de uso existentes.

| Cota ou parâmetro | Size | Ciclo de atualização | Descrição |
|--|--|--|--|
| Intervalo de dados | 30 dias | Cada consulta | Cada consulta pode procurar dados de até os últimos 30 dias. |
| Conjunto de resultados | 10.000 linhas | Cada consulta | Cada consulta pode retornar até 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta pode ser executado por até 10 minutos. Se ele não for concluído em 10 minutos, o serviço exibirá um erro.
| Recursos da CPU | Com base no tamanho do locatário | A cada 15 minutos | O [portal exibe um erro sempre](advanced-hunting-errors.md) que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados. As consultas serão bloqueadas se o locatário tiver atingido 100% até após o próximo ciclo de 15 minutos. |

>[!NOTE] 
>Um conjunto separado de cotas e parâmetros se aplicam a consultas de busca avançadas realizadas por meio da API. [Ler sobre APIs de busca avançada](./api-advanced-hunting.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Manipular erros avançados de busca](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)