---
title: Conheça a linguagem de consulta de busca avançada no Microsoft Threat Protection
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, aprendizado, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, Kusto, operadores, tipos de dados, download do PowerShell, exemplo de consulta
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
ms.openlocfilehash: 250d19a09d79fc5fd8c69f2ebd24abadc642fafc
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005841"
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

![Imagem da consulta de busca avançada da proteção contra ameaças da Microsoft](../../media/advanced-hunting-query-example-2.png)

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Descrever a consulta e especificar as tabelas a serem pesquisadas
Um breve comentário foi adicionado ao início da consulta para descrever o que ele é. Isso ajudará se você decidir salvar a consulta mais tarde e compartilhá-la com outras pessoas em sua organização. 

```kusto
// Finds PowerShell execution events that could involve a download
```

A consulta em si geralmente começará com um nome de tabela seguido de uma série de elementos iniciados por um pipe (`|`). Neste exemplo, começamos criando uma União de duas tabelas `DeviceProcessEvents` e `DeviceNetworkEvents` , e adicionar elementos canalizados, conforme necessário.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Definir o intervalo de tempo
O primeiro elemento canalizado é um filtro de tempo com escopo para os sete dias anteriores. Manter o intervalo de tempo tão estreito quanto possível garante que as consultas sejam executadas, retornem resultados gerenciáveis e não o tempo limite.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Verificar processos específicos
O intervalo de tempo é imediatamente seguido por uma pesquisa por nomes de arquivo de processo que representam o aplicativo PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Procurar cadeias de caracteres de comando específicas
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

### <a name="customize-result-columns-and-length"></a>Personalizar colunas e comprimento do resultado 
Agora que a consulta identifique claramente os dados que você deseja localizar, você pode adicionar elementos que definem a aparência dos resultados. `project`retorna colunas específicas e `top` limita o número de resultados. Esses operadores ajudam a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Clique **executar consulta** para ver os resultados. Selecione o ícone de expansão no canto superior direito do editor de consulta para se concentrar na consulta de busca e nos resultados. 

![Imagem do controle de expansão no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

>[!TIP]
>Você pode exibir os resultados da consulta como gráficos e ajustar rapidamente os filtros. Para obter orientação, [Leia sobre como trabalhar com os resultados da consulta](advanced-hunting-query-results.md)

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

## <a name="get-help-as-you-write-queries"></a>Obter ajuda durante a criação de consultas
Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:
- **Sugestão** automática — à medida que você escreve consultas, a busca avançada fornece sugestões do IntelliSense. 
- **Referência de esquema** — inclui a lista de tabelas e suas colunas ao lado da área de trabalho. Para saber mais, passe o mouse sobre um item. Clique duas vezes em um item para inseri-lo no editor de consultas.

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
