---
title: Trabalhar com resultados de consulta de busca avançada no Microsoft 365 Defender
description: Make the most of the query results returned by advanced hunting in Microsoft 365 Defender
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, microsoft 365, Proteção contra Ameaças da Microsoft, visualização, gráfico, filtros, buscas
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
ms.openlocfilehash: 462ba35f584b45bbfeb0d8a3de3b118ba1c9e17c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932299"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabalhar com resultados de consulta de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Embora você possa [](advanced-hunting-overview.md) construir suas consultas de busca avançada para retornar informações muito precisas, você também pode trabalhar com os resultados da consulta para obter mais informações e investigar atividades e indicadores específicos. Você pode tomar as seguintes ações nos resultados da consulta:

- Exibir resultados como uma tabela ou gráfico
- Exportar tabelas e gráficos
- Drill down to detailed entity information
- Ajustar suas consultas diretamente dos resultados ou aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Exibir resultados de consulta como uma tabela ou gráfico
Por padrão, a busca avançada exibe os resultados da consulta como dados tabular. Você também pode exibir os mesmos dados que um gráfico. A busca avançada dá suporte às seguintes exibições:

| Tipo de modo de exibição | Descrição |
| -- | -- |
| **Table** | Exibe os resultados da consulta no formato tabular |
| **Gráfico de colunas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais cujas alturas representam valores numéricos de outro campo |
| **Gráfico de colunas empilhadas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais empilhadas cujas alturas representam valores numéricos de um ou mais campos |
| **Gráfico de pizza** | Renderiza pizzas em forma de pizza que representam itens exclusivos. O tamanho de cada pizza representa valores numéricos de outro campo. |
| **Gráfico Desdoo** | Renderiza arcos de renderização que representam itens exclusivos. O comprimento de cada arco representa valores numéricos de outro campo. |
| **Gráfico de linhas** | Plota valores numéricos para uma série de itens exclusivos e conecta os valores plotados |
| **Gráfico de dispersão** | Plota valores numéricos para uma série de itens exclusivos |
| **Gráfico de área** | Plota valores numéricos para uma série de itens exclusivos e preenche as seções abaixo dos valores plotados |

### <a name="construct-queries-for-effective-charts"></a>Construir consultas para gráficos efetivos
Ao renderizar gráficos, a busca avançada identifica automaticamente colunas de interesse e os valores numéricos a agregar. Para obter gráficos significativos, construa suas consultas para retornar os valores específicos que você deseja visualizar. Aqui estão algumas consultas de exemplo e os gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravidade
Use o `summarize` operador para obter uma contagem numérica dos valores que você deseja gráfico. A consulta abaixo usa o `summarize` operador para obter o número de alertas por gravidade.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Ao renderizar os resultados, um gráfico de coluna exibe cada valor de severidade como uma coluna separada:

![Imagem de resultados de consulta de busca avançada exibida como um gráfico de colunas Resultados de consulta para alertas por gravidade ](../../media/advanced-hunting-column-chart.jpg)
 *exibidos como um gráfico de colunas*

#### <a name="alert-severity-by-operating-system"></a>Gravidade do alerta pelo sistema operacional
Você também pode usar o operador `summarize` para preparar resultados para gráficos de valores de vários campos. Por exemplo, talvez você queira entender como as gravidades de alerta são distribuídas entre sistemas operacionais (SO). 

A consulta abaixo usa um operador para obter informações do sistema operacional da tabela e, em seguida, usa para contar valores nas `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` colunas e na coluna:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Esses resultados são melhor visualizados usando um gráfico de colunas empilhadas:

![Imagem de resultados de consulta de busca avançada exibida como um gráfico empilhado Resultados de consulta para alertas por sistema operacional e gravidade exibidos como ](../../media/advanced-hunting-stacked-chart.jpg)
 *um gráfico empilhado*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Phishing de emails nos dez principais domínios de remetente
Se você estiver lidando com uma lista de valores que não são finitos, você pode usar o operador para gráfico apenas os valores com a maioria `Top` das instâncias. Por exemplo, para obter os dez principais domínios de remetente com mais emails de phishing, use a consulta abaixo:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Use o modo de exibição gráfico de pizza para mostrar efetivamente a distribuição entre os principais domínios:

![Imagem dos resultados da consulta de busca avançada exibida como um gráfico de pizza do gráfico de pizza mostrando a distribuição de emails de phishing entre os ](../../media/advanced-hunting-pie-chart.jpg)
 *principais domínios de remetentes*

#### <a name="file-activities-over-time"></a>Atividades de arquivo ao longo do tempo
Usando o `summarize` operador com `bin()` a função, você pode verificar se há eventos envolvendo um indicador específico ao longo do tempo. A consulta abaixo conta os eventos envolvendo o arquivo em intervalos de 30 minutos para mostrar picos de atividade `invoice.doc` relacionados a esse arquivo:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
O gráfico de linhas abaixo destaca claramente os períodos de tempo com mais atividades `invoice.doc` envolvendo: 

![Imagem dos resultados da consulta de busca avançada exibida como um gráfico de linhas de linhas mostrando o número de eventos ](../../media/advanced-hunting-line-chart.jpg)
 *envolvendo um arquivo ao longo do tempo*


## <a name="export-tables-and-charts"></a>Exportar tabelas e gráficos
Depois de executar uma consulta, selecione **Exportar** para salvar os resultados no arquivo local. A exibição escolhida determina como os resultados são exportados:

- **Exibição de** tabela — os resultados da consulta são exportados em formato tabular como uma planilha do Microsoft Excel
- **Qualquer gráfico** — os resultados da consulta são exportados como uma imagem JPEG do gráfico renderizado

## <a name="drill-down-from-query-results"></a>Drill down from query results
Para inspecionar rapidamente um registro nos resultados da consulta, selecione a linha correspondente para abrir o painel **Inspecionar registro.** O painel fornece as seguintes informações com base no registro selecionado:

- **Ativos** — exibição resumida dos principais ativos (caixas de correio, dispositivos e usuários) encontrados no registro, enriquecidos com informações disponíveis, como níveis de risco e exposição
- **Árvore de processos** — gerada para registros com informações de processo e enriquecida usando informações contextuais disponíveis; em geral, consultas que retornam mais colunas podem resultar em árvores de processo mais rica.
- **Todos os** detalhes — todos os valores das colunas no registro  

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/inspect-record.png)

Para exibir mais informações sobre uma entidade específica nos resultados da consulta, como um computador, arquivo, usuário, endereço IP ou URL, selecione o identificador de entidade para abrir uma página de perfil detalhada para essa entidade.

## <a name="tweak-your-queries-from-the-results"></a>Ajustar consultas a partir dos resultados
Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta. Você pode usar as opções para:

- Procurar explicitamente pelo valor selecionado (`==`)
- Excluir o valor selecionado da consulta (`!=`)
- Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with` 

![Imagem do conjunto de resultados de busca avançada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar os resultados da consulta
Os filtros exibidos à direita fornecem um resumo do conjunto de resultados. Cada coluna tem sua própria seção, que lista os valores distintos encontrados para essa coluna e o número de instâncias.

Refine sua consulta selecionando os ou os botões nos valores que você deseja incluir ou excluir e, em `+` `-` seguida, selecionando **Executar consulta**.

![Imagem do filtro de busca avançada](../../media/advanced-hunting-filter.png)

Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
