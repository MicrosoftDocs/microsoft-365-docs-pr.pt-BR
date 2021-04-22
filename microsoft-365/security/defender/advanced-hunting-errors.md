---
title: Manipular erros na busca avançada do Microsoft 365 Defender
description: Compreender erros exibidos ao usar a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, esquema, kusto, tempo limite, recursos, erros, erro desconhecido, limites, cota, parâmetro, alocação
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
ms.openlocfilehash: d8d165f39c45bd235800dc951d50934b47dd7ff5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935444"
---
# <a name="handle-advanced-hunting-errors"></a>Manipular erros avançados de busca

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


A busca avançada exibe erros para notificar erros de sintaxe e sempre que as consultas atingem [cotas e parâmetros de uso predefinidos.](advanced-hunting-limits.md) Consulte a tabela abaixo para saber mais sobre como resolver ou evitar erros.

| Tipo de erro | Causa | Resolução | Exemplos de mensagem de erro |
|--|--|--|--|
| Erros de sintaxe | A consulta contém nomes não conhecidos, incluindo referências a operadores, colunas, funções ou tabelas inexistentes. | Verifique se as referências [aos operadores e funções kusto estão corretas.](/azure/data-explorer/kusto/query/) Verifique [o esquema das](advanced-hunting-schema-tables.md) colunas, funções e tabelas de busca avançadas corretas. Coloque cadeias de caracteres variáveis entre aspas para que elas sejam reconhecidas. Ao escrever suas consultas, use as sugestões de preenchimento automático de IntelliSense. | `A recognition error occurred.` |
| Erros semânticos | Embora a consulta use nomes de operador, coluna, função ou tabela válidos, há erros em sua estrutura e lógica resultante. Em alguns casos, a busca avançada identifica o operador específico que causou o erro. | Verifique se há erros na estrutura da consulta. Consulte a [documentação do Kusto](/azure/data-explorer/kusto/query/) para obter orientações. Ao escrever suas consultas, use as sugestões de preenchimento automático de IntelliSense. |  `'project' operator: Failed to resolve scalar expression named 'x'`|
| Timeouts | Uma consulta só pode ser executado dentro de um [período limitado antes do tempo limite](advanced-hunting-limits.md). Esse erro pode acontecer com mais frequência ao executar consultas complexas. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Query exceeded the timeout period.` |
| Throttling da CPU | As consultas no mesmo locatário excederam os recursos [da CPU](advanced-hunting-limits.md) alocados com base no tamanho do locatário. | O serviço verifica o uso de recursos da CPU a cada 15 minutos e diariamente e exibe avisos após o uso exceder 10% da cota alocada. Se você atingir 100% de utilização, o serviço bloqueará as consultas até após o próximo ciclo diário ou de 15 minutos. [Otimizar suas consultas para evitar atingir cotas de CPU](advanced-hunting-best-practices.md) | - `This query used X% of your organization's allocated resources for the current 15 minutes.`<br>- `You have exceeded processing resources allocated to this tenant. You can run queries again in <duration>.` |
| Limite de tamanho do resultado excedido  | O tamanho agregado do conjunto de resultados da consulta excedeu o tamanho máximo. Esse erro pode ocorrer se o conjunto de resultados for tão grande que a truncamento no limite de 10.000 registros não poderá reduzi-lo a um tamanho aceitável. Os resultados que têm várias colunas com conteúdo considerável são mais prováveis de serem afetados por esse erro. | [Otimizar a consulta](advanced-hunting-best-practices.md) | `Result size limit exceeded. Use "summarize" to aggregate results, "project" to drop uninteresting columns, or "take" to truncate results.` |
| Consumo excessivo de recursos | A consulta consumiu quantidades excessivas de recursos e foi impedida de concluir. Em alguns casos, a busca avançada identifica o operador específico que não foi otimizado. | [Otimizar a consulta](advanced-hunting-best-practices.md) | -`Query stopped due to excessive resource consumption.`<br>-`Query stopped. Adjust use of the <operator name> operator to avoid excessive resource consumption.` |
| Erros desconhecidos | A consulta falhou devido a um motivo desconhecido. | Tente executar a consulta novamente. Contate a Microsoft por meio do portal se as consultas continuarem a retornar erros desconhecidos. | `An unexpected error occurred during query execution. Please try again in a few minutes.`

## <a name="related-topics"></a>Tópicos relacionados
- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Cotas e parâmetros de uso](advanced-hunting-limits.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Visão geral do Idioma de Consulta do Kusto](/azure/data-explorer/kusto/query/)