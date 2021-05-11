---
title: Exibir estatísticas para resultados de pesquisa de Descobertas EDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.search: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: Saiba como usar o recurso de estatísticas de pesquisa para exibir estatísticas para pesquisas e pesquisas de conteúdo associadas a um caso de Descoberta Principal de Descoberta Microsoft 365 de conformidade.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0e543c89b91560520a4e4bf31feb8471c91da4a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311083"
---
# <a name="view-statistics-for-ediscovery-search-results"></a>Exibir estatísticas para resultados de pesquisa de Descobertas EDiscovery

Depois de criar e executar uma pesquisa de Conteúdo ou uma pesquisa associada a um caso de Descoberta Principal de Descoberta e, você pode exibir estatísticas sobre os resultados estimados da pesquisa. Isso inclui um resumo dos resultados da pesquisa (semelhante ao resumo dos resultados estimados da pesquisa exibidos na página de sobrevoo de pesquisa), as estatísticas de consulta, como o número de locais de conteúdo com itens que coincidem com a consulta de pesquisa, e a identidade dos locais de conteúdo que têm os itens mais correspondentes.
  
Além disso, você pode usar a lista de palavras-chave para configurar uma pesquisa para retornar estatísticas de cada palavra-chave em uma consulta de pesquisa. Isso permite comparar o número de resultados retornados por cada palavra-chave em uma consulta.
  
Você também pode baixar estatísticas de pesquisa para um arquivo CSV. Isso permite usar os recursos de filtragem e classificação no Excel para comparar resultados e preparar relatórios para os resultados da pesquisa.
  
## <a name="get-statistics-for-searches"></a>Obter estatísticas para pesquisas

Para exibir estatísticas de uma pesquisa de conteúdo ou uma pesquisa associada a um caso de Descoberta eDiscoveria Principal.:
  
1. No Microsoft 365 de conformidade, clique em **Mostrar tudo** e, em seguida, faça um dos seguintes:

   - Clique **em Pesquisa de** conteúdo e selecione uma pesquisa para exibir a página de sobrevoo.

     OU

   - Clique **em EDiscovery** Core, selecione uma ocorrência e selecione uma pesquisa na guia Pesquisas para exibir a página  >  de sobrevoo. 

2. Na página de sobrevoo da pesquisa selecionada, clique na **guia Estatísticas de** pesquisa.
  
   ![A guia Estatísticas de Pesquisa](../media/SearchStatistics1.png)

A **guia Estatísticas de Pesquisa** contém seções a seguir que contêm diferentes tipos de estatísticas sobre a pesquisa.

### <a name="search-content"></a>Conteúdo de pesquisa

Esta seção exibe um resumo gráfico dos itens estimados retornados pela pesquisa. Isso indica o número de itens que corresponderem aos critérios de pesquisa. Essas informações dão uma ideia do número estimado de itens retornados pela pesquisa.

![Estimativas de pesquisa para uma pesquisa](../media/SearchContentReport.png)

- **Itens estimados por locais**: O número total de itens estimados retornados pela pesquisa. O número específico de itens localizados em caixas de correio e localizados em sites também é exibido.

- **Locais estimados com visitas**: O número total de locais de conteúdo que contêm itens retornados pela pesquisa. O número específico de caixas de correio e locais de site também é exibido.

- **Volume de dados por local (em MB)**: o tamanho total de todos os itens estimados retornados pela pesquisa. O tamanho específico de itens de caixa de correio e itens de site também é exibido.

### <a name="condition-report"></a>Relatório de condição

Esta seção exibe estatísticas sobre a consulta de pesquisa e o número de itens estimados que corresponderam a diferentes partes da consulta de pesquisa. Você pode usar essas estatísticas para analisar o número de itens que corresponderem a cada componente da consulta de pesquisa. Isso pode ajudá-lo a refinar os critérios de pesquisa e, se necessário, restringir o escopo do escopo. Você também pode baixar uma cópia desse relatório no formato CSV.

![Relatório de condição](../media/SearchContentReportNoKeywordList.png)

- **Tipo de** local : o tipo de local de conteúdo ao qual as estatísticas de consulta são aplicáveis. O valor de **Exchange** indica um local de caixa de correio; um valor de **SharePoint** indica um local do site.

- **Parte**: A parte da consulta de pesquisa à que as estatísticas são aplicáveis. **O** primário indica toda a consulta de pesquisa. **A** palavra-chave indica que as estatísticas na linha são para uma palavra-chave específica. Se você usar uma lista de palavras-chave para consulta de pesquisa, as estatísticas de cada componente da consulta serão incluídas nesta tabela. Para obter mais informações, consulte [Obter estatísticas de palavra-chave para pesquisas](#get-keyword-statistics-for-searches).

- **Condição**: o componente real (palavra-chave ou condição) da consulta de pesquisa que retornou as estatísticas exibidas na linha correspondente.

- **Locais com hits**: o número dos locais  de conteúdo (especificados pela coluna Tipo de local) que contêm itens que corresponderem à consulta primária ou de palavra-chave listada na **coluna** Condição.

- **Itens**: o número de itens (do local de conteúdo especificado) que combinam com a consulta listada na **coluna Condição.** Conforme explicado anteriormente, se um item contiver várias instâncias de uma palavra-chave que está sendo pesquisada, ele só será contado uma vez nesta coluna.

- **Tamanho (MB)**: o tamanho total de todos os itens encontrados (no local de conteúdo especificado) que corresponderem à consulta de pesquisa na **coluna** Condição.

### <a name="top-locations"></a>Principais locais

Esta seção exibe estatísticas sobre os locais de conteúdo específicos com a maioria dos itens retornados pela pesquisa. Os primeiros 1.000 locais são exibidos. Você também pode baixar uma cópia desse relatório no formato CSV.

- O nome do nome do local (o endereço de email das caixas de correio e a URL para sites).

- Tipo de local (uma caixa de correio ou site).

- Número estimado de itens no local de conteúdo retornado pela pesquisa.

- O tamanho total dos itens estimados em cada local de conteúdo.

## <a name="get-keyword-statistics-for-searches"></a>Obter estatísticas de palavra-chave para pesquisas

Como explicado anteriormente, a seção **Relatório de** condição mostra a consulta de pesquisa e o número (e tamanho) de itens que corresponderem à consulta. Se você usar uma lista de palavras-chave ao criar ou editar uma consulta de pesquisa, poderá obter estatísticas avançadas que mostram quantos itens corresponderem a cada palavra-chave ou frase de palavra-chave. Isso pode ajudá-lo a identificar rapidamente quais partes da consulta são mais (e menos) eficazes. Por exemplo, se uma palavra-chave retornar um grande número de itens, você pode optar por refinar a consulta de palavra-chave para restringir os resultados da pesquisa.

Para criar uma lista de palavras-chave e exibir estatísticas de palavra-chave para uma pesquisa:
  
1. No centro Microsoft 365 de conformidade, crie uma nova pesquisa de conteúdo ou uma pesquisa associada a um caso de Descoberta Principal de Descoberta e.

2. Na página **Condições** do assistente de pesquisa. selecione a **caixa de seleção Mostrar lista de palavras-chave.**

   ![Caixa de seleção Mostrar lista de palavras-chave](../media/SearchKeywordsList1.png)

3. Digite uma palavra-chave ou uma fase de palavra-chave em uma linha na tabela de palavras-chave. Por exemplo, digite **orçamento** na primeira linha, digite **segurança** na segunda linha e digite **FY2021** na terceira linha.

   ![Digite até 20 palavras-chave ou frases de palavra-chave na lista](../media/SearchKeywordsList2.png)

   > [!NOTE]
   > Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, você está limitado a no máximo 20 linhas na lista de palavras-chave de uma consulta de pesquisa.

4. Depois de adicionar as palavras-chave à lista que você deseja pesquisar e obter estatísticas, execute a pesquisa.

5. Quando a pesquisa for concluída, selecione-a para exibir a página de sobrevoo.

6. Na guia **Estatísticas de Pesquisa,** clique no relatório **Condição** para exibir as estatísticas de palavra-chave da pesquisa.

    ![As estatísticas de cada palavra-chave são exibidas](../media/SearchKeywordsList3.png)
  
    Conforme mostrado na captura de tela anterior, as estatísticas de cada palavra-chave são exibidas; isso inclui:

    - As estatísticas de palavra-chave para cada tipo de local de conteúdo incluído na pesquisa.

    - O número de itens de caixa de correio não índicedos.

    - A consulta de pesquisa real e os resultados  de cada palavra-chave (identificado como **Palavra-chave** na coluna Parte), que inclui quaisquer condições da consulta de pesquisa.

    - A consulta de pesquisa completa (identificada como **Primária** na coluna Parte) e as estatísticas da consulta completa para cada tipo de local.  Observe que estas são as mesmas estatísticas exibidas na **guia Resumo.**
