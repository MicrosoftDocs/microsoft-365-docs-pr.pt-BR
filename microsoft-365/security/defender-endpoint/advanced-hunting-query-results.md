---
title: Trabalhar com resultados avançados de consulta de busca no Microsoft Defender ATP
description: Fazer o máximo dos resultados da consulta retornados pela busca avançada no Microsoft Defender ATP
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, visualização, gráfico, filtros, detalhamento
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
ms.openlocfilehash: 8876eea8f8b1111a2039328296fbd7c2d50022cb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054208"
---
# <a name="work-with-advanced-hunting-query-results"></a>Trabalhar com resultados avançados de consulta de busca

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

Embora você possa construir [suas](advanced-hunting-overview.md) consultas de busca avançadas para retornar informações muito precisas, você também pode trabalhar com os resultados da consulta para obter mais informações e investigar atividades e indicadores específicos. Você pode tomar as seguintes ações em seus resultados de consulta:

- Exibir resultados como tabela ou gráfico
- Exportar tabelas e gráficos
- Detalhar as informações detalhadas da entidade
- Ajustar suas consultas diretamente dos resultados ou aplicar filtros

## <a name="view-query-results-as-a-table-or-chart"></a>Exibir resultados da consulta como uma tabela ou gráfico
Por padrão, a busca avançada exibe os resultados da consulta como dados tabular. Você também pode exibir os mesmos dados de um gráfico. A busca avançada dá suporte às seguintes exibições:

| Tipo de modo de exibição | Descrição |
| -- | -- |
| **Table** | Exibe os resultados da consulta no formato tabular |
| **Gráfico de colunas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais cujas alturas representam valores numéricos de outro campo |
| **Gráfico de colunas empilhadas** | Renderiza uma série de itens exclusivos no eixo x como barras verticais empilhadas cujas alturas representam valores numéricos de um ou mais outros campos |
| **Gráfico de pizza** | Renderiza as pizzas desaversais que representam itens exclusivos. O tamanho de cada pizza representa valores numéricos de outro campo. |
| **Gráfico de rosca** | Renderiza arcos seccionais que representam itens exclusivos. O comprimento de cada arco representa valores numéricos de outro campo. |
| **Gráfico de linhas** | Plota valores numéricos para uma série de itens exclusivos e conecta os valores plotados |
| **Gráfico de dispersão** | Plota valores numéricos para uma série de itens exclusivos |
| **Gráfico de área** | Plota valores numéricos para uma série de itens exclusivos e preenche as seções abaixo dos valores plotados |

### <a name="construct-queries-for-effective-charts"></a>Criar consultas para gráficos efetivos
Ao renderizar gráficos, a busca avançada identifica automaticamente colunas de interesse e os valores numéricos a agregar. Para obter gráficos significativos, construa suas consultas para retornar os valores específicos que você deseja ver visualizados. Aqui estão algumas consultas de exemplo e os gráficos resultantes.

#### <a name="alerts-by-severity"></a>Alertas por gravidade
Use o `summarize` operador para obter uma contagem numérica dos valores que você deseja fazer gráfico. A consulta abaixo usa o `summarize` operador para obter o número de alertas por gravidade.

```kusto
DeviceAlertEvents
| summarize Total = count() by Severity
```
Ao renderizar os resultados, um gráfico de coluna exibe cada valor de severidade como uma coluna separada:

![Imagem dos resultados avançados da consulta de busca exibida como um gráfico de colunas Resultados de consulta para alertas por gravidade ](images/advanced-hunting-column-chart.jpg)
 *exibidos como um gráfico de colunas*

#### <a name="alert-severity-by-operating-system"></a>Gravidade do alerta pelo sistema operacional
Você também pode usar o `summarize` operador para preparar resultados para o gráfico de valores de vários campos. Por exemplo, talvez você queira entender como as gravidades do alerta são distribuídas entre os sistemas operacionais (SO). 

A consulta abaixo usa um operador para obter informações do sistema operacional da tabela e usa para contar valores nas `join` `DeviceInfo` `summarize` `OSPlatform` `Severity` colunas e:

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by OSPlatform, Severity
```
Esses resultados são melhor visualizados usando um gráfico de colunas empilhados:

![Imagem dos resultados avançados da consulta de busca exibida como um gráfico empilhado Resultados de consulta para alertas pelo sistema operacional e gravidade ](images/advanced-hunting-stacked-chart.jpg)
 *exibidos como um gráfico empilhado*

#### <a name="top-ten-device-groups-with-alerts"></a>Os dez principais grupos de dispositivos com alertas
Se você estiver lidando com uma lista de valores que não são finitos, você pode usar o operador para gráfico somente os valores com a maioria `Top` das instâncias. Por exemplo, para obter os dez principais grupos de dispositivos com a maioria dos alertas, use a consulta abaixo:

```kusto
DeviceAlertEvents
| join DeviceInfo on DeviceId
| summarize Count = count() by MachineGroup
| top 10 by Count
```
Use o modo de exibição do gráfico de pizza para mostrar efetivamente a distribuição entre os principais grupos:

![Imagem dos resultados avançados da consulta de busca exibida como um gráfico de pizza gráfico de pizza mostrando a distribuição ](images/advanced-hunting-pie-chart.jpg)
 *de alertas entre grupos de dispositivos*

#### <a name="malware-detections-over-time"></a>Detecções de malware ao longo do tempo
Usando o `summarize` operador com `bin()` a função, você pode verificar se há eventos envolvendo um indicador específico ao longo do tempo. A consulta abaixo conta detecções de um arquivo de teste EICAR em intervalos de 30 minutos para mostrar picos nas detecções desse arquivo:

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| where SHA1 == "3395856ce81f2b7382dee72602f798b642f14140"
| summarize Detections = count() by bin(Timestamp, 30m)
```
O gráfico de linha abaixo realça claramente os períodos de tempo com mais detecções do malware de teste: 

![Imagem de resultados de consulta de busca avançada exibidos como um gráfico de linha gráfico De linha mostrando o número de ](images/advanced-hunting-line-chart.jpg)
 *detecções* de um malware de teste ao longo do tempo


## <a name="export-tables-and-charts"></a>Exportar tabelas e gráficos
Depois de executar uma consulta, selecione **Exportar** para salvar os resultados no arquivo local. Sua exibição escolhida determina como os resultados são exportados:

- **Exibição de** tabela — os resultados da consulta são exportados no formato tabular como uma planilha do Microsoft Excel
- **Qualquer gráfico** — os resultados da consulta são exportados como uma imagem JPEG do gráfico renderizado

## <a name="drill-down-from-query-results"></a>Detalhar a partir dos resultados da consulta
Para exibir mais informações sobre entidades, como dispositivos, arquivos, usuários, endereços IP e URLs, nos resultados da consulta, basta clicar no identificador da entidade. Isso abre uma página de perfil detalhada para a entidade selecionada.

Para inspecionar rapidamente um registro nos resultados da consulta, selecione a linha correspondente para abrir o painel Inspecionar registro. O painel fornece as seguintes informações com base no registro selecionado:

- **Ativos** — Uma exibição resumida dos principais ativos (caixas de correio, dispositivos e usuários) encontrados no registro, enriquecidos com informações disponíveis, como níveis de risco e exposição
- **Árvore de** processos — um gráfico gerado para registros com informações de processo e enriquecido usando informações contextuais disponíveis; em geral, consultas que retornam mais colunas podem resultar em árvores de processo mais ricas.
- **Todos os detalhes** — lista todos os valores das colunas no registro

## <a name="tweak-your-queries-from-the-results"></a>Ajustar consultas a partir dos resultados
Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta. Você pode usar as opções para:

- Procurar explicitamente pelo valor selecionado (`==`)
- Excluir o valor selecionado da consulta (`!=`)
- Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with` 

![Imagem do conjunto de resultados de busca avançada](images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar os resultados da consulta
Os filtros exibidos no painel direito fornecem um resumo do conjunto de resultados. Cada coluna tem sua própria seção no painel, cada uma lista os valores encontrados nessa coluna e o número de instâncias.

Refine sua consulta selecionando os botões ou nos valores `+` que você deseja incluir ou `-` excluir. Em **seguida, selecione Executar consulta**.

![Imagem do filtro de busca avançada](images/advanced-hunting-filter.png)

Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-reference.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
