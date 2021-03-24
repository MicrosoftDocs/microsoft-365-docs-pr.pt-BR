---
title: Limites avançados de busca no Microsoft Defender ATP
description: Compreender vários limites de serviço que mantêm o serviço de busca avançado responsivo
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, wdatp, pesquisa, consulta, telemetria, esquema, kusto, limite de CPU, limite de consulta, recursos, resultados máximos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 127ebc8c0eaba433710bc272a2cf602e7c9a9730
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054331"
---
# <a name="advanced-hunting-service-limits"></a>Limites avançados do serviço de busca

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Para manter o serviço performant e responsivo, a busca avançada define vários limites para consultas executados manualmente e por regras [de detecção personalizadas.](custom-detection-rules.md) Consulte a tabela a seguir para entender esses limites.

| Limite | Size | Ciclo de atualização | Descrição |
|--|--|--|--|
| Intervalo de dados | 30 dias | Cada consulta | Cada consulta pode procurar dados de até os últimos 30 dias. |
| Conjunto de resultados | 10.000 linhas | Cada consulta | Cada consulta pode retornar até 10.000 registros. |
| Timeout | 10 minutos | Cada consulta | Cada consulta pode ser executado por até 10 minutos. Se ele não for concluído em 10 minutos, o serviço exibirá um erro.
| Recursos da CPU | Com base no tamanho do locatário | - Na hora e, em seguida, a cada 15 minutos<br>- Diariamente à meia-noite | O serviço impõe o limite diário e de 15 minutos separadamente. Para cada limite, o [portal exibe](advanced-hunting-errors.md) um erro sempre que uma consulta é executado e o locatário consumiu mais de 10% dos recursos alocados. As consultas serão bloqueadas se o locatário tiver atingido 100% até após o próximo ciclo diário ou de 15 minutos. |

>[!NOTE] 
>Um conjunto separado de limites se aplica a consultas de busca avançadas realizadas por meio da API. [Ler sobre APIs de busca avançada](run-advanced-query-api.md)

Os clientes que executarem várias consultas [](advanced-hunting-best-practices.md) regularmente devem controlar o consumo e aplicar práticas recomendadas de otimização para minimizar a interrupção resultante de exceder esses limites.

## <a name="related-topics"></a>Tópicos relacionados

- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Manipular erros avançados de busca](advanced-hunting-errors.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Regras de detecções personalizadas](custom-detection-rules.md)
