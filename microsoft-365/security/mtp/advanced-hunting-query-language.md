---
title: Conheça a linguagem de consulta de busca avançada no Microsoft Threat Protection
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, aprendizado, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, Kusto, operadores, tipos de dados, PowerShell baixar, exemplo de consulta
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
ms.openlocfilehash: e093bd9c5a76b44cf66591b4212f37014189186e
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928991"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conhecer a linguagem de consulta de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Você pode usar a sintaxe e os operadores Kusto para construir consultas que localizem informações no [esquema](advanced-hunting-schema-tables.md) especificamente estruturadas para a pesquisa avançada. Para entender melhor esses conceitos, execute a primeira consulta.

## <a name="try-your-first-query"></a>Experimente a primeira consulta

No centro de segurança do Microsoft 365, vá para a **busca** para executar a primeira consulta. Use o seguinte exemplo:

```kusto
// Finds PowerShell execution events that could involve a download
union DeviceProcessEvents, DeviceNetworkEvents
| where Timestamp > ago(7d)
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Esta é a aparência do aspecto da pesquisa avançada.

![Imagem da consulta de busca avançada da proteção contra ameaças da Microsoft](../../media/advanced-hunting-query-example.png)

Um breve comentário foi adicionado ao início da consulta para descrever o que ele é. Isso ajudará se você decidir salvar a consulta mais tarde e compartilhá-la com outras pessoas em sua organização. 

```kusto
// Finds PowerShell execution events that could involve a download
```

A consulta em si geralmente começará com um nome de tabela seguido de uma série de elementos iniciados por um pipe (`|`). Neste exemplo, começamos criando uma União de duas tabelas `DeviceProcessEvents` e `DeviceNetworkEvents`, e adicionar elementos canalizados, conforme necessário.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
O primeiro elemento canalizado é um filtro de tempo com escopo para os sete dias anteriores. Manter o intervalo de tempo tão estreito quanto possível garante que as consultas sejam executadas, retornem resultados gerenciáveis e não o tempo limite.

```kusto
| where Timestamp > ago(7d)
```

O intervalo de tempo é imediatamente seguido por uma pesquisa por nomes de arquivo de processo que representam o aplicativo PowerShell.

```
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

Posteriormente, a consulta procura por cadeias de caracteres em linhas de comando que normalmente são usadas para baixar arquivos usando o PowerShell.

```kusto
// Suspicious commands
| where ProcessCommandLine has_any("WebClient",
 "DownloadFile",
 "DownloadData",
 "DownloadString",
"WebRequest",
"Shellcode",
"http",
"https")
```
Agora que a consulta identifique claramente os dados que você deseja localizar, você pode adicionar elementos que definem a aparência dos resultados. `project`retorna colunas específicas e `top` limita o número de resultados, ajudando a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Clique **executar consulta** para ver os resultados. Selecione o ícone de expansão no canto superior direito do editor de consulta para se concentrar na consulta de busca e nos resultados.

![Imagem do controle de expansão no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

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
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
