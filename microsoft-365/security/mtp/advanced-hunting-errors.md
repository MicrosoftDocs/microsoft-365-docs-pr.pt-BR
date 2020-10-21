---
title: Lidar com erros na busca avançada para a proteção contra ameaças da Microsoft
description: Entender os erros exibidos ao usar a busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, esquema, Kusto, tempo limite, recursos, erros, erro desconhecido, limites, cota, parâmetro, alocação
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
ms.openlocfilehash: 8b9c46e312d28c7a08efbfa74f96dc33b90fee0a
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636888"
---
# <a name="handle-advanced-hunting-errors"></a>Manipular erros de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


A busca avançada exibe erros para notificar erros de sintaxe e sempre que as consultas visitam [cotas predefinidas e parâmetros de uso](advanced-hunting-limits.md). Consulte a tabela abaixo para obter dicas sobre como resolver ou evitar erros.

| Tipo de erro | Causa | Resolução | Exemplos de mensagens de erro |
|--|--|--|--|
| Erros de sintaxe | A consulta contém nomes não reconhecidos, incluindo referências a operadores não existentes, colunas, funções ou tabelas. | Verifique se as referências a [operadores e funções do Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) estão corretas. Verifique [o esquema](advanced-hunting-schema-tables.md) das colunas, funções e tabelas de busca avançada corretas. Incluir cadeias de caracteres variáveis entre aspas para que sejam reconhecidas. Ao escrever suas consultas, use as sugestões de preenchimento automático do IntelliSense. | `A recognition error occurred.` |
| Erros semânticos | Enquanto a consulta usa operadores, colunas, funções ou nomes de tabela válidos, há erros em sua estrutura e lógica resultante. Em alguns casos, a busca avançada identifica o operador específico que causou o erro. | Verifique se há erros na estrutura da consulta. Consulte a [documentação do Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) para obter orientação. Ao escrever suas consultas, use as sugestões de preenchimento automático do IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tempos limite | Uma consulta pode ser executada apenas dentro de um [período limitado antes do tempo limite](advanced-hunting-limits.md). Esse erro pode ocorrer com mais frequência ao executar consultas complexas. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Limitação de CPU | As consultas no mesmo locatário excederam os [recursos de CPU](advanced-hunting-limits.md) que foram alocados com base no tamanho do locatário. | O serviço verifica o uso de recursos de CPU a cada 15 minutos e o diário e exibe avisos após o uso exceder 10% da cota alocada. Se você atingir 100% de utilização, o serviço bloqueará as consultas até após o próximo ciclo diário ou de 15 minutos. [Otimizar suas consultas para evitar o uso de cotas de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limite de tamanho do resultado excedido  | O tamanho agregado do conjunto de resultados da consulta excedeu o tamanho máximo. Este erro poderá ocorrer se o conjunto de resultados for tão grande que truncar no limite de gravação 10.000 não pode reduzi-lo para um tamanho aceitável. Resultados com várias colunas com conteúdo ajustável têm maior probabilidade de serem afetados por esse erro. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excessivo de recursos | A consulta consumiu quantidades excessivas de recursos e foi impediu de ser concluída. Em alguns casos, a caça avançada identifica o operador específico que não foi otimizado. | [Otimizar a consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Erros desconhecidos | A consulta falhou devido a um motivo desconhecido. | Tente executar a consulta novamente. Entre em contato com a Microsoft pelo portal se as consultas continuam a retornar erros desconhecidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Tópicos relacionados
- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Cotas e parâmetros de uso](advanced-hunting-limits.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Visão geral da linguagem de consulta Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
