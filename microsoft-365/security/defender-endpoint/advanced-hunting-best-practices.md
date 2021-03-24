---
title: Práticas recomendadas de consulta para busca avançada
description: Aprenda a criar consultas de busca de ameaças rápidas, eficientes e sem erros ao usar a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, evitar tempo de espera, linhas de comando, id de processo
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
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6259ac1c5804b244c825a1bb54401640fdefaf34
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053432"
---
# <a name="advanced-hunting-query-best-practices"></a>Práticas recomendadas de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-abovefoldlink)

## <a name="optimize-query-performance"></a>Obter o melhor resultado possível numa consulta

Aplique essas recomendações para obter resultados mais rápidos e evitar tempo de execução de consultas complexas.

- Ao experimentar novas consultas, use sempre `limit` para evitar conjuntos de resultados grandes demais. Você também pode avaliar inicialmente o tamanho do conjunto de resultados usando `count`.
- Use primeiro os filtros de tempo. O ideal é limitar suas consultas a sete dias.
- Coloque os filtros passíveis de remover a maior parte dos dados no início da consulta, imediatamente após o filtro de tempo.
- Use o operador `has` sobre `contains` ao procurar tokens completos.
- Examine uma coluna específica, em vez de executar pesquisas de texto completo em todas as colunas.
- Ao adicionar tabelas, especifique primeiro a tabela com menos linhas.
- `project` somente as colunas necessárias das tabelas que adicionou.

>[!TIP]
>Para obter mais informações sobre como melhorar o desempenho da consulta, leia [ práticas recomendadas de consulta no Kusto](https://docs.microsoft.com/azure/kusto/query/best-practices).

## <a name="query-tips-and-pitfalls"></a>Dicas de consulta e armadilhas

### <a name="queries-with-process-ids"></a>Consultas com IDs de processo

As IDs de processo (PIDs) são recicladas no Windows e reutilizadas para novos processos. Por si só, eles não servem como identificadores exclusivos para processos específicos. Para obter um identificador exclusivo para um processo em um dispositivo específico, use a ID do processo juntamente com o tempo de criação do processo. Ao ingressar ou resumir dados em torno de processos, inclua colunas para o identificador de dispositivo (ou ), a ID do processo ( ou ) e o tempo de criação do processo `DeviceId` `DeviceName` ( ou `ProcessId` `InitiatingProcessId` `ProcessCreationTime` `InitiatingProcessCreationTime` ).

O exemplo de consulta a seguir localiza processos que acessam mais de 10 endereços IP na porta 445 (SMB), possivelmente procurando por compartilhamentos de arquivos.

```kusto
DeviceNetworkEvents
| where RemotePort == 445 and Timestamp > ago(12h) and InitiatingProcessId !in (0, 4)
| summarize RemoteIPCount=dcount(RemoteIP) by DeviceName, InitiatingProcessId, InitiatingProcessCreationTime, InitiatingProcessFileName
| where RemoteIPCount > 10
```

A consulta é resumida por tanto `InitiatingProcessId` quanto`InitiatingProcessCreationTime` para que ela examine um único processo, sem misturar vários processos com a mesma ID de processo.

### <a name="queries-with-command-lines"></a>Consultas com linhas de comando

As linhas de comando podem variar. Quando aplicável, filtre os nomes dos arquivos e realize correspondência difusa.

Há várias maneiras de criar uma linha de comando para executar uma tarefa. Por exemplo, um invasor pode fazer referência a um arquivo de imagem com ou sem um caminho, sem uma extensão de arquivo, usando variáveis de ambiente ou com aspas. Além disso, o invasor também pode alterar a ordem dos parâmetros ou adicionar várias aspas e espaços.

Para criar consultas mais duráveis usando linhas de comando, aplique as seguintes práticas:

- Identifique os processos conhecidos ( tais como *net. exe* ou *PsExec. exe*) pela correspondência com os campos nome de arquivo, em vez de usar um filtro no campo de linha de comando.
- Ao consultar argumentos de linha de comando, não procure uma correspondência exata com vários argumentos não relacionados em uma determinada ordem. Em vez disso, use expressões regulares ou use vários operadores Contém separados.
- Correspondências que não diferenciam letras maiúsculas de minúsculas. Por exemplo, use `=~` , `in~` e, `contains` em vez de `==` , `in` e `contains_cs`
- Para atenuar os efeitos das técnicas de ofuscação de linha de comando do DOS, considere remover aspas, substituir vírgulas por espaços e substituir vários espaços consecutivos por um único espaço. Observe que há técnicas de ofuscação de DOS mais complexas que exigem outras abordagens, mas estas técnicas acima citadas podem ajudar a resolver os problemas mais comuns.

Os exemplos a seguir mostram várias maneiras de criar uma consulta que procura o arquivo *net. exe* para deter o serviço do Windows Defender firewall:

```kusto
// Non-durable query - do not use
DeviceProcessEvents
| where ProcessCommandLine == "net stop MpsSvc"
| limit 10

// Better query - filters on filename, does case-insensitive matches
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe") and ProcessCommandLine contains "stop" and ProcessCommandLine contains "MpsSvc" 

// Best query also ignores quotes
DeviceProcessEvents
| where Timestamp > ago(7d) and FileName in~ ("net.exe", "net1.exe")
| extend CanonicalCommandLine=replace("\"", "", ProcessCommandLine)
| where CanonicalCommandLine contains "stop" and CanonicalCommandLine contains "MpsSvc" 
```

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-bestpractices-belowfoldlink)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
