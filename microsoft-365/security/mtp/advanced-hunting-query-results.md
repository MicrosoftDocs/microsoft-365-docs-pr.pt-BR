---
title: Trabalhar com resultados de consulta de busca avançada na proteção contra ameaças da Microsoft
description: Aproveitar ao máximo os resultados da consulta retornados por busca avançada na proteção contra ameaças da Microsoft
keywords: caça avançada, busca de ameaças, caça de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft, visualização, gráfico, filtros Drill-down
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
ms.openlocfilehash: f9838908ca0dbfb498601c3509b920b064a2eb22
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929067"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabalhar com resultados de consulta de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Embora você possa construir suas consultas de [busca avançada](advanced-hunting-overview.md) para retornar informações muito precisas, você também pode trabalhar com os resultados da consulta para obter mais percepção e investigar atividades e indicadores específicos. Você pode executar as seguintes ações nos resultados de consulta:

- Exibir resultados como uma tabela ou um gráfico
- Exportar tabelas e gráficos
- Aprofundar nas informações detalhadas da entidade
- Ajustar suas consultas diretamente dos resultados ou aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Exibir resultados de consulta como uma tabela ou um gráfico
Por padrão, a busca avançada exibe resultados de consulta como dados tabulares. Você também pode exibir os mesmos dados de um gráfico. A busca avançada é compatível com os seguintes modos de exibição:

| Tipo de modo de exibição | Descrição |
| -- | -- |
| **Table** | Exibe os resultados da consulta no formato de tabela |
| **Gráfico de colunas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais cujas alturas representam valores numéricos de outro campo |
| **Gráfico de colunas empilhadas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais empilhadas cujas alturas representam valores numéricos de um ou mais campos |
| **Gráfico de pizza** | Renderiza tortas de seção que representam itens exclusivos. O tamanho de cada pizza representa valores numéricos de outro campo. |
| **Gráfico de rosca** | Renderiza arcos de seção que representam itens exclusivos. O comprimento de cada arco representa valores numéricos de outro campo. |
| **Gráfico de linhas** | Plota valores numéricos para uma série de itens exclusivos e conecta os valores plotados |
| **Gráfico de dispersão** | Plota valores numéricos para uma série de itens exclusivos |
| **Gráfico de área** | Plota valores numéricos para uma série de itens exclusivos e preenche as seções abaixo dos valores plotados |

### <a name="construct-queries-for-effective-charts"></a>Construir consultas para gráficos efetivos
Ao renderizar gráficos, a busca avançada identifica automaticamente as colunas de interesse e os valores numéricos a serem agregados. Para obter gráficos significativos, construa suas consultas para retornar os valores específicos que você deseja ver visualizados. Veja algumas consultas de exemplo e os gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por severidade
Use o `summarize` operador para obter uma contagem numérica dos valores que você deseja para o gráfico. A consulta abaixo usa o `summarize` operador para obter o número de alertas por severidade.

```kusto
AlertInfo
| summarize Total = count() by Severity
```
Ao renderizar os resultados, um gráfico de colunas exibe cada valor de severidade como uma coluna separada:

![Imagem dos resultados da consulta de busca avançada exibidos como um](../../media/advanced-hunting-column-chart.jpg)
gráfico de colunas*resultados de consulta para alertas por severidade exibido como gráfico de colunas*

#### <a name="alert-severity-by-operating-system"></a>Severidade de alerta por sistema operacional
Você também pode usar o `summarize` operador para preparar resultados para valores de gráfico de vários campos. Por exemplo, talvez você queira entender como as severidades de alerta são distribuídas entre OS sistemas operacionais (SO). 

A consulta a seguir usa `join` um operador para extrair informações de so da `DeviceInfo` tabela e, em seguida `summarize` , usa para contar valores em `OSPlatform` ambas `Severity` as colunas:

```kusto
AlertInfo
| join AlertEvidence on AlertId
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity 
```
Esses resultados são mais visualizados usando um gráfico de colunas empilhadas:

![Imagem dos resultados da consulta de busca avançada exibidos como um gráfico](../../media/advanced-hunting-stacked-chart.jpg)
empilhado*resultados de consulta para alertas por sistema operacional e severidade exibidos como um gráfico empilhado*

#### <a name="phishing-emails-across-top-ten-sender-domains"></a>Emails de phishing nos dez principais domínios de remetente
Se você estiver lidando com uma lista de valores que não é finito, você pode usar `Top` o operador para apenas o gráfico os valores com a maioria das instâncias. Por exemplo, para obter os dez principais domínios de remetente com a maioria dos emails de phishing, use a consulta abaixo:

```kusto
EmailEvents
| where PhishFilterVerdict == "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count
```
Use o modo de exibição gráfico de pizza para mostrar efetivamente a distribuição nos principais domínios:

![Imagem dos resultados da consulta de busca avançada exibidos como gráfico](../../media/advanced-hunting-pie-chart.jpg)
de pizza de gráfico de pizza*mostrando distribuição de emails de phishing nos principais domínios de remetente*

#### <a name="file-activities-over-time"></a>Atividades de arquivo ao longo do tempo
Usando o `summarize` operador com a `bin()` função, você pode verificar se há eventos que envolvem um indicador específico ao longo do tempo. A consulta abaixo conta os eventos que envolvem o arquivo `invoice.doc` em intervalos de 30 minutos para mostrar picos de atividade relacionadas a esse arquivo:

```kusto
AppFileEvents
| union DeviceFileEvents
| where FileName == "invoice.doc"
| summarize FileCount = count() by bin(Timestamp, 30m)
```
O gráfico de linhas abaixo realça claramente os períodos de tempo com `invoice.doc`mais atividade envolvendo: 

![Imagem dos resultados da consulta de busca avançada exibidos como um](../../media/advanced-hunting-line-chart.jpg)
gráfico de linha de gráfico de linhas*mostrando o número de eventos que envolvem um arquivo ao longo do tempo*


## <a name="export-tables-and-charts"></a>Exportar tabelas e gráficos
Após executar uma consulta, selecione **Exportar** para salvar os resultados no arquivo local. O modo de exibição escolhido determina como os resultados são exportados:

- **Modo de exibição de tabela** : os resultados da consulta são exportados no formato tabular como uma pasta de trabalho do Microsoft Excel
- **Qualquer gráfico** — os resultados da consulta são exportados como uma imagem JPEG do gráfico renderizado

## <a name="drill-down-from-query-results"></a>Aprofundar a partir de resultados de consulta
Para ver em seus resultados de consulta mais informações sobre entidades, como máquinas, arquivos, usuários, endereços IP e URLs, simplesmente clique no identificador de entidade. Isso abre uma página de perfil detalhada para a entidade selecionada no Central de Segurança do Microsoft Defender.

## <a name="tweak-your-queries-from-the-results"></a>Ajustar consultas a partir dos resultados
Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta. Você pode usar as opções para:

- Procurar explicitamente pelo valor selecionado (`==`)
- Excluir o valor selecionado da consulta (`!=`)
- Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with` 

![Imagem de conjunto de resultados de busca avançada](../../media/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar os resultados da consulta
Os filtros exibidos à direita fornecem um resumo do conjunto de resultados. Cada coluna tem sua própria seção, que lista os valores distintos encontrados para essa coluna e o número de instâncias.

Refine sua consulta selecionando os `+` botões `-` ou nos valores que você deseja incluir ou excluir e selecionar **Executar consulta**.

![Imagem do filtro de busca avançada](../../media/advanced-hunting-filter.png)

Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
