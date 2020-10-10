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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: ffa5e6abf7fb1cb0f93fe1c233ef7e3f0b023faf
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412617"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conhecer a linguagem de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Você pode usar a sintaxe e os operadores do Kusto para construir consultas que localizem informações em um [esquema](advanced-hunting-schema-tables.md)especializado. Para entender melhor esses conceitos, execute a primeira consulta.

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

**[Executar esta consulta em busca avançada](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2TW0sCURSF93PQfxh8Moisp956yYIgQtLoMaYczJpbzkkTpN_et_dcdPQkcpjbmrXXWftyetKTQG5lKqmMpeB9IJksJJKZDOWdZ8wKeP5wvcm3OLgZbMXmXCmIxjnYIfcAVgYvRi8w3TnfsXEDGAG47pCCZXyP5ViO4KeNbt-Up-hEuJmB6lvButnY8XSL-cDl0M2I-GwxVX8Fe2H5zMzHiKjEVB0eEsnBrszfBIWuXOLrxCJ7VqEBfM3DWUYTkNKrv1p5y3X0jwetemzOQ_NSVuuXZ1c6aNTKRaN8VvWhY9n7OS-o6J5r7mYeQypdEKc1m1qfiqpjCSuspsDntt2J61bEvTlXls5AgQfFl5bHM_gr_BhO2RF1rztoBv2tWahrso_TtzkL93KGMGZVr2pe7eWR-xeZl91f_113UOsx3nDR4Y9j5R6kaCq8ajr_YWfFeedsd27L7it-Z6dAZyxsJq1d9-2ZOSzK3y2NVd8-zUPjtZaJnYsIH4Md7AmdeAcd2Cl1XoURc5PzXlfU8U9P54WcswL6t_TW9Q__qX-xygQAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Descrever a consulta e especificar as tabelas a serem pesquisadas
Um breve comentário foi adicionado ao início da consulta para descrever o que ele é. Este comentário ajuda se você decidir salvar a consulta mais tarde e compartilhá-la com outras pessoas em sua organização. 

```kusto
// Finds PowerShell execution events that could involve a download
```

Em geral, a consulta é iniciada com um nome de tabela seguido por vários elementos que começam com um pipe ( `|` ). Neste exemplo, começamos criando uma União de duas tabelas  `DeviceProcessEvents` e `DeviceNetworkEvents` , e adicionar elementos canalizados, conforme necessário.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Definir o intervalo de tempo
O primeiro elemento canalizado é um filtro de tempo com escopo para os sete dias anteriores. Limitar o intervalo de tempo ajuda a garantir que as consultas tenham um bom desempenho, retornem resultados gerenciáveis e não o tempo limite.

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
Agora que a consulta identifica claramente os dados que você deseja localizar, você pode definir a aparência dos resultados. `project` retorna colunas específicas e `top` limita o número de resultados. Esses operadores ajudam a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selecione **Executar consulta** para ver os resultados. Use o ícone de expansão no canto superior direito do editor de consulta para se concentrar na consulta de busca e nos resultados. 

![Imagem do controle de expansão no editor de consulta de busca avançada](../../media/advanced-hunting-expand.png)

>[!TIP]
>Você pode exibir os resultados da consulta como gráficos e ajustar rapidamente os filtros. Para obter orientação, [Leia sobre como trabalhar com os resultados da consulta](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators"></a>Aprender operadores de consulta comuns

Você acabou de executar a primeira consulta e ter uma ideia geral de seus componentes. É hora de desfocar levemente e aprender algumas noções básicas. A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.

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

## <a name="understand-data-types"></a>Entender tipos de dados

A busca avançada oferece suporte a tipos de dados do Kusto, incluindo os seguintes tipos comuns:

| Tipo de dados | Implicações de descrição e de consulta |
|--|--|
| `datetime` | Informações de dados e tempo geralmente representam carimbos de data/hora. [Consulte formatos de DateTime suportados](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadeia de caracteres em UTF-8 entre aspas simples ( `'` ) ou aspas duplas ( `"` ). [Ler mais sobre cadeias de caracteres](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Esse tipo de dados oferece suporte `true` ou `false` Estados. [Consulte literais e operadores suportados](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | inteiro de 32 bits  |
| `long` | inteiro de 64 bits |

Para saber mais sobre esses tipos de dados, [Leia sobre os tipos de dados escalares Kusto](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/).

## <a name="get-help-as-you-write-queries"></a>Obter ajuda durante a criação de consultas
Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:
- **Sugestão**automática — à medida que você escreve consultas, a busca avançada fornece sugestões do IntelliSense. 
- **Árvore de esquema**— uma representação de esquema que inclui a lista de tabelas e suas colunas é fornecida ao lado da área de trabalho. Para saber mais, passe o mouse sobre um item. Clique duas vezes em um item para inseri-lo no editor de consultas.
- **[Referência de esquema](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**: referência no portal com descrições de tabela e coluna, bem como tipos de eventos suportados ( `ActionType` valores) e consultas de exemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabalhar com várias consultas no editor
Você pode usar o editor de consultas para experimentar várias consultas. Para usar várias consultas:

- Separe cada consulta com uma linha vazia.
- Coloque o cursor em qualquer parte de uma consulta para selecionar a consulta antes de executá-la. A consulta selecionada será executada apenas. Para executar outra consulta, mova o cursor de acordo e selecione **Executar consulta**.

![Imagem do editor de consultas com várias consultas](../../media/mtp-ah/ah-multi-query.png)

## <a name="use-sample-queries"></a>Use consultas de amostra

A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência. Tente executar essas consultas e faça pequenas modificações nelas.

![Imagem da janela de caça avançada](../../media/advanced-hunting-get-started.png)

>[!NOTE]
>Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças. Explore as consultas compartilhadas no lado esquerdo da página ou no [repositório de consultas do GitHub](https://aka.ms/hunting-queries).

## <a name="access-query-language-documentation"></a>Documentação da linguagem de consulta do Access

Para obter mais informações sobre a linguagem de consulta Kusto e os operadores com suporte, confira [documentação da linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/).

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
