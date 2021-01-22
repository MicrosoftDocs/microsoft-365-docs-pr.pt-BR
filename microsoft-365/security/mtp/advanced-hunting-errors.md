---
title: Tratar erros na busca avançada pelo Microsoft 365 Defender
description: Entender os erros exibidos ao usar a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, esquema, kusto, tempo limite, recursos, erros, erro desconhecido, limites, cota, parâmetro, alocação
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
ms.openlocfilehash: 645e78de9d7a8a779be8741a7471e9c1a88ba538
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929641"
---
# <a name="handle-advanced-hunting-errors"></a>Lidar com erros de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


A busca avançada exibe erros para notificar erros de sintaxe e sempre que as consultas atingem [cotas e parâmetros de uso predefinidos.](advanced-hunting-limits.md) Consulte a tabela abaixo para ver dicas sobre como resolver ou evitar erros.

| Tipo de erro | Causa | Resolução | Exemplos de mensagem de erro |
|--|--|--|--|
| Erros de sintaxe | A consulta contém nomes não conhecidos, incluindo referências a operadores, colunas, funções ou tabelas inexistentes. | Certifique-se de que as referências [a operadores e funções kusto estão corretas.](https://docs.microsoft.com/azure/data-explorer/kusto/query/) Verifique [o esquema das](advanced-hunting-schema-tables.md) colunas, funções e tabelas de busca avançada corretas. Coloque as cadeias de caracteres variáveis entre aspas para que sejam reconhecidas. Ao escrever suas consultas, use as sugestões de preenchimento automático do IntelliSense. | `A recognition error occurred.` |
| Erros semânticos | Embora a consulta use nomes válidos de operador, coluna, função ou tabela, há erros em sua estrutura e lógica resultante. Em alguns casos, a busca avançada identifica o operador específico que causou o erro. | Verifique se há erros na estrutura da consulta. Consulte a [documentação do Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/) para obter orientação. Ao escrever suas consultas, use as sugestões de preenchimento automático do IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Tempos-e-tempos | Uma consulta só pode ser executado dentro de um [período limitado antes do tempo limite.](advanced-hunting-limits.md) Esse erro pode acontecer com mais frequência ao executar consultas complexas. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Throttling de CPU | As consultas no mesmo locatário excederam os recursos [da CPU](advanced-hunting-limits.md) que foram alocados com base no tamanho do locatário. | O serviço verifica o uso de recursos da CPU a cada 15 minutos e diariamente e exibe avisos depois que o uso excede 10% da cota alocada. Se você alcançar 100% de utilização, o serviço bloqueará as consultas até o próximo ciclo diário ou de 15 minutos. [Otimize suas consultas para evitar atingir cotas de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limite de tamanho dos resultados excedido  | O tamanho agregado do conjunto de resultados para a consulta excedeu o tamanho máximo. Esse erro poderá ocorrer se o conjunto de resultados for tão grande que o truncamento no limite de 10.000 registros não poderá reduzi-lo a um tamanho aceitável. Os resultados com várias colunas com conteúdoizável têm maior probabilidade de serem afetados por esse erro. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excessivo de recursos | A consulta consumiu quantidades excessivas de recursos e foi impedida de concluir. Em alguns casos, a busca avançada identifica o operador específico que não foi otimizado. | [Otimizar a consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Erros desconhecidos | A consulta falhou devido a um motivo desconhecido. | Tente executar a consulta novamente. Entre em contato com a Microsoft por meio do portal se as consultas continuarem a retornar erros desconhecidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Tópicos relacionados
- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Cotas e parâmetros de uso](advanced-hunting-limits.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Visão geral da linguagem de consulta Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/)
