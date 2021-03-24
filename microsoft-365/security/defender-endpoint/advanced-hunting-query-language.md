---
title: Conhecer a linguagem de consulta de busca avançada
description: Crie sua primeira consulta de busca de ameaças e saiba mais sobre os operadores comuns e outros aspectos da linguagem de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, idioma, aprender, primeira consulta, telemetria, eventos, telemetria, detecções personalizadas, esquema, kusto, operadores, tipos de dados
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
ms.openlocfilehash: 21cea1f661de294aea41ea2c4db21b1aca8a0eec
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053626"
---
# <a name="learn-the-advanced-hunting-query-language"></a>Conhecer a linguagem de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

A caça avançada baseia-se na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/). Você pode usar operadores e instruções kusto para construir consultas que localizem informações em um [esquema especializado.](advanced-hunting-schema-reference.md) Para entender melhor esses conceitos, execute a primeira consulta.

## <a name="try-your-first-query"></a>Experimente a primeira consulta

No Centro de Segurança do Microsoft Defender, vá para **Busca Avançada** para executar sua primeira consulta. Use o seguinte exemplo:

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
**[Executar essa consulta em busca avançada](https://securitycenter.windows.com/hunting?query=H4sIAAAAAAAEAI2TT0vDQBDF5yz4HUJPFcTqyZsXqyCIBFvxKNGWtpo_NVlbC8XP7m8mado0K5Zls8nkzdu3b2Z70pNAbmUmqYyk4D2UTJYyllwGMmWNGQHrN_NNvsSBzUBrbMFMiWieAx3xDEBl4GL4AuNd8B0bNgARENcdUmIZ3yM5liPwac3bN-YZPGPU5ET1rWDc7Ox4uod8YDp4MzI-GkjlX4Ne2nly0zEkKzFWh4ZE5sSuTN8Ehq5couvEMnvmUAhez-HsRBMipVa_W_OG6vEfGtT12JRHpqV064e1Kx04NsxFzXxW1aFjp_djXmDRPbfY3XMMcLogTz2bWZ2KqmIJI6q6wKe2WYnrRsa9KVeU9kCBBo2v7BzPxF_Bx2DKiqh63SGoRoc6Njti48z_yL71XHQAcgAur6rXRpcqH3l-4knZF23Utsbq2MircEqmw-G__xR1TdZ1r7zb7XLezmx3etkvGr-ze6NdGdW92azUfpcdluWvr-aqbh_nofnqcWI3aYyOsBV7giduRUO7187LMKTT5rxvHHX80_t8IeeMgLquvL7-Ak3q-kz8BAAA&runQuery=true&timeRangeId=week)**

### <a name="describe-the-query-and-specify-the-tables-to-search"></a>Descrever a consulta e especificar as tabelas a ser pesquisadas
Um breve comentário foi adicionado ao início da consulta para descrever para que ela é. Este comentário ajuda se você decidir mais tarde salvar a consulta e compartilhá-la com outras pessoas em sua organização.

```kusto
// Finds PowerShell execution events that could involve a download
```
A consulta em si normalmente iniciará com um nome de tabela seguido por vários elementos que começam com um pipe ( `|` ). Neste exemplo, começamos criando uma união de duas tabelas e , e adicionamos elementos  `DeviceProcessEvents` `DeviceNetworkEvents` canalados conforme necessário.

```kusto
union DeviceProcessEvents, DeviceNetworkEvents
```
### <a name="set-the-time-range"></a>Definir o intervalo de tempo
O primeiro elemento canalado é um filtro de tempo com escopo para os sete dias anteriores. Limitar o intervalo de tempo ajuda a garantir que as consultas executem bem, retornem resultados gerenciáveis e não se limitem.

```kusto
| where Timestamp > ago(7d)
```

### <a name="check-specific-processes"></a>Verificar processos específicos
O intervalo de tempo é imediatamente seguido por uma pesquisa de nomes de arquivo de processo que representam o aplicativo PowerShell.

```kusto
// Pivoting on PowerShell processes
| where FileName in~ ("powershell.exe", "powershell_ise.exe")
```

### <a name="search-for-specific-command-strings"></a>Pesquisar cadeias de caracteres de comando específicas
Posteriormente, a consulta procura cadeias de caracteres em linhas de comando que normalmente são usadas para baixar arquivos usando o PowerShell.

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

### <a name="customize-result-columns-and-length"></a>Personalizar colunas de resultados e comprimento 
Agora que sua consulta identifica claramente os dados que você deseja localizar, você pode definir a aparência dos resultados. `project` retorna colunas específicas e `top` limita o número de resultados. Esses operadores ajudam a garantir que os resultados sejam bem formatados e razoavelmente grandes e fáceis de processar.

```kusto
| project Timestamp, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, 
FileName, ProcessCommandLine, RemoteIP, RemoteUrl, RemotePort, RemoteIPType
| top 100 by Timestamp
```

Selecione **Executar consulta para** ver os resultados. Use o ícone de expansão na parte superior direita do editor de consulta para se concentrar na consulta de busca e nos resultados. 

![Imagem do controle Expandir no editor de consulta de busca avançada](images/advanced-hunting-expand.png)

>[!TIP]
>Você pode exibir os resultados da consulta como gráficos e ajustar filtros rapidamente. Para obter orientações, [leia sobre como trabalhar com resultados de consulta](advanced-hunting-query-results.md)

## <a name="learn-common-query-operators-for-advanced-hunting"></a>Conheça operadores de consulta comuns para a caça avançada

Você acabou de executar sua primeira consulta e ter uma ideia geral de seus componentes. É hora de voltar um pouco e aprender alguns conceitos básicos. A linguagem de consulta Kusto usada por caça avançada oferece suporte a vários operadores, incluindo os seguintes.

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

Para ver um exemplo ao vivo desses operadores, execute-os na seção **Iniciar** da página de busca avançada.

## <a name="understand-data-types"></a>Compreender tipos de dados

A busca avançada dá suporte a tipos de dados Kusto, incluindo os seguintes tipos comuns:

| Tipo de dados | Implicações de descrição e de consulta |
|--|--|
| `datetime` | As informações de dados e de hora geralmente representam os datas-hora do evento. [Consulte formatos de data/hora suportados](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/datetime) |
| `string` | Cadeia de caracteres em UTF-8 entre aspas simples ( `'` ) ou aspas duplas ( `"` ). [Leia mais sobre cadeias de caracteres](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/string) |
| `bool` | Esse tipo de dados dá suporte `true` ou `false` estados. [Consulte literais e operadores com suporte](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/bool) |
| `int` | Inteiro de 32 bits  |
| `long` | Inteiro de 64 bits |

Para saber mais sobre esses tipos de dados, leia sobre tipos de dados [escalares do Kusto.](https://docs.microsoft.com/azure/data-explorer/kusto/query/scalar-data-types/)

## <a name="get-help-as-you-write-queries"></a>Obter ajuda durante a criação de consultas
Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:

- **Autosuggest**— à medida que você escreve consultas, a busca avançada fornece sugestões de IntelliSense.
- **Árvore de esquema**— uma representação de esquema que inclui a lista de tabelas e suas colunas é fornecida ao lado da sua área de trabalho. Para saber mais, passe o mouse sobre um item. Clique duas vezes em um item para inseri-lo no editor de consultas.
- **[Referência de esquema](advanced-hunting-schema-reference.md#get-schema-information-in-the-security-center)**— referência no portal com descrições de tabela e coluna, bem como tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo

## <a name="work-with-multiple-queries-in-the-editor"></a>Trabalhar com várias consultas no editor
Você pode usar o editor de consulta para experimentar várias consultas. Para usar várias consultas:

- Separe cada consulta com uma linha vazia.
- Coloque o cursor em qualquer parte de uma consulta para selecionar essa consulta antes de ser executado. Isso executará apenas a consulta selecionada. Para executar outra consulta, mova o cursor de acordo e selecione **Executar consulta**.

![Imagem do editor de consulta de busca avançada com o editor de consulta de várias ](images/ah-multi-query.png)
 _consultas com várias consultas_

## <a name="use-sample-queries"></a>Use consultas de amostra

A seção **introdução** fornece algumas consultas simples usando operadores usados com frequência. Tente executar essas consultas e faça pequenas modificações nelas.

![Imagem da guia de início da busca avançada](images/atp-advanced-hunting.png)

> [!NOTE]
> Além das amostras básicas de consulta, você também pode acessar [consultas compartilhadas](advanced-hunting-shared-queries.md) para cenários específicos de busca de ameaças. Explore as consultas compartilhadas no lado esquerdo da página ou no [repositório de consulta do GitHub.](https://aka.ms/hunting-queries)

## <a name="access-comprehensive-query-language-reference"></a>Acessar referência abrangente do idioma de consulta

Para obter informações detalhadas sobre o idioma de consulta, consulte a documentação do idioma de consulta [kusto.](https://docs.microsoft.com/azure/kusto/query/)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-reference.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
