---
title: Conheça a linguagem de consulta de busca avançada no Microsoft Threat Protection
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, aprendizado, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, Kusto, operadores, tipos de dados
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: eda9b893057afd54a644f0091bf4e1b421bd5439
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234690"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conhecer a linguagem de consulta de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Você pode usar a sintaxe e os operadores Kusto para construir consultas que localizem informações no [esquema](advanced-hunting-schema-tables.md) especificamente estruturadas para a pesquisa avançada. Para entender melhor esses conceitos, execute a primeira consulta.

## <a name="try-your-first-query"></a>Experimente a primeira consulta

na central de segurança do Microsoft 365, vá para **procurando** executar a primeira consulta. Use o seguinte exemplo:

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents 
| where Timestamp > ago(7d)
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE") 
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Esta é a aparência do aspecto da pesquisa avançada.

![Imagem da consulta caça avançada do Microsoft defender ATP](../../media/advanced-hunting-query-example.png)

A consulta começa com um pequeno comentário descrevendo o que é para isso. Isso ajudará se você decidir salvar sua consulta mais tarde e compartilhá-la com outras pessoas em sua organização.

```kusto
// Finds PowerShell execution events that could involve a download.
DeviceProcessEvents
```

A consulta em si geralmente começará com um nome de tabela seguido de uma série de elementos iniciados por um pipe (`|`). Neste exemplo, começamos adicionando com o nome da tabela `DeviceProcessEvents` e adicionar elementos de pipe conforme necessário.

O primeiro elemento canalizado é um filtro de tempo delimitado dentro dos últimos sete dias. Manter o intervalo de tempo tão estreito quanto possível garante que as consultas sejam executadas, retornem resultados gerenciáveis e não o tempo limite.

```kusto
| where Timestamp > ago(7d)
```

O intervalo de tempo é imediatamente seguido por uma pesquisa de arquivos que representam o aplicativo PowerShell.

```kusto
| where FileName in ("powershell.exe", "POWERSHELL.EXE", "powershell_ise.exe", "POWERSHELL_ISE.EXE")
```

Em seguida, a consulta procura linhas de comando que normalmente são usadas com o PowerShell para baixar arquivos.

```kusto
| where ProcessCommandLine has "Net.WebClient"
        or ProcessCommandLine has "DownloadFile"
        or ProcessCommandLine has "Invoke-WebRequest"
        or ProcessCommandLine has "Invoke-Shellcode"
        or ProcessCommandLine contains "http:"
```

Agora que a consulta identifique claramente os dados que você deseja localizar, você pode adicionar elementos que definem a aparência dos resultados. `project` retorna colunas específicas e `top` limita o número de resultados, tornando os resultados bem formatados e razoavelmente grandes e fáceis de processar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, FileName, ProcessCommandLine
| top 100 by Timestamp
```

Clique **executar consulta** para ver os resultados. Você pode expandir o modo de exibição de tela para poder se concentrar em sua consulta de busca e nos resultados.

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Conheça operadores de consulta comuns para a caça avançada

Agora que você executou a primeira consulta e tem uma ideia geral dos seus componentes, chegou a hora de recapitular um pouco e aprender algumas noções básicas. A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.

| Operador | Descrição e uso |
|--|--|
| `where` | Filtre uma tabela no subconjunto de linhas que atendem a um predicado. |
| `summarize` | Produza uma tabela que agrega o conteúdo da tabela de entrada. |
| `join` | Mescle as linhas de duas tabelas para formar uma nova tabela, correspondendo valores das colunas especificadas de cada tabela. |
| `count` | Retorne o número de registros no conjunto de registros de entrada. |
| `top` | Retorne os primeiros registros N classificados pelas colunas especificadas. |
| `limit` | Retornar para o número especificado de linhas. |
| `project` | Selecione as colunas a serem incluídas, renomear ou descartar e inserir novas colunas computadas. |
| `extend` | Crie colunas calculadas e as acrescente ao conjunto de resultados. |
| `makeset` |  Retornar uma matriz dinâmica (JSON) do conjunto de valores distintos que Expr assume no grupo. |
| `find` | Localizar linhas que correspondam a um predicado em um conjunto de tabelas. |

Para ver um exemplo instantâneo desses operadores, execute-os na seção **começar**, na caça avançada.

## <a name="understand-data-types-and-their-query-syntax-implications"></a>Compreenda os tipos de dados e suas implicações de sintaxe de consulta

Os dados em tabelas de caça avançada geralmente são classificados nos seguintes tipos de dados.

| Tipo de dados | Implicações de descrição e de consulta |
|--|--|
| `datetime` | As informações de dados e hora geralmente representam os carimbos de data/hora |
| `string` | Conjunto de caracteres |
| `bool` | Verdadeiro ou falso |
| `int` | valor numérico de bits de 32  |
| `long` | valor numérico de bits de 64 |

## <a name="use-sample-queries"></a>Use consultas de amostra

A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência. Tente executar essas consultas e faça pequenas modificações nelas.

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças. Explore as consultas compartilhadas, no lado esquerdo da página ou no repositório de consultas do GitHub.

## <a name="access-query-language-documentation"></a>Documentação da linguagem de consulta do Access

Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
