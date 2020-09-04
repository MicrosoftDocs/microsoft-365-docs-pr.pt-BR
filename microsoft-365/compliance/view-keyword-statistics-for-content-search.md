---
title: Exibir as estatísticas de palavras-chave para resultados da Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/30/2017
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 9701a024-c52e-43f0-b545-9a53478aec04
description: Saiba como usar o recurso estatísticas de pesquisa para exibir e comparar as estatísticas de várias pesquisas de conteúdo no centro de conformidade e segurança &.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f9f6b77a7a557ca363b2a7d56b96ea3d6ccc287
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358459"
---
# <a name="view-keyword-statistics-for-content-search-results"></a>Exibir as estatísticas de palavras-chave para resultados da Pesquisa de Conteúdo

Depois de criar e executar uma pesquisa de conteúdo, você pode exibir estatísticas sobre os resultados estimados da pesquisa. Isso inclui um resumo dos resultados da pesquisa (semelhante ao resumo dos resultados de pesquisa estimados exibidos no painel de detalhes), as estatísticas de consulta, como o número de locais de conteúdo com itens que correspondem à consulta de pesquisa e o nome dos locais de conteúdo que têm os itens mais coincidentes. Você poderá exibir as estatísticas de uma ou mais pesquisas de conteúdo. Isso permite que você compare rapidamente os resultados de várias pesquisas e tome decisões sobre a eficácia de suas consultas de pesquisa.
  
Além disso, você pode configurar as pesquisas novas e existentes para retornar as estatísticas de cada palavra-chave em uma consulta de pesquisa. Isso permite que você compare o número de resultados para cada palavra-chave em uma consulta e compare as estatísticas de palavra-chave de várias pesquisas.
  
Você também poderá baixar as estatísticas da pesquisa e as estatísticas da palavra-chave para um arquivo CSV. Isso permite usar os recursos de filtragem e classificação no Excel para comparar resultados e preparar relatórios para os resultados da pesquisa.
  
## <a name="get-statistics-for-content-searches"></a>Obter estatísticas para pesquisas de conteúdo

Para exibir estatísticas para pesquisas de conteúdo:
  
1. No centro de conformidade & segurança, vá para **Search** \> **pesquisa de conteúdo**de pesquisa.
    
2. Na lista de pesquisas, selecione uma ou mais pesquisas e, em seguida, clique em Pesquisar estatísticas da pesquisa de **estatísticas** ![ ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) .
    
    ![Selecionar várias pesquisas e clicar em estatísticas de pesquisa](../media/1195c6c3-2e00-469d-8c29-85c1c7ebe6c7.png)
  
3. Na página **Estatísticas de pesquisa** , clique em um dos seguintes links para exibir estatísticas sobre as pesquisas selecionadas. 
    
    **Resumo**
    
    Esta página exibe estatísticas semelhantes às exibidas no painel de detalhes na página de **pesquisa de conteúdo** . As estatísticas de todas as pesquisas selecionadas são exibidas. Observe que você também pode executar novamente as pesquisas selecionadas nesta página para atualizar as estatísticas. 
    
    ![Resumo das estatísticas das pesquisas selecionadas](../media/abb663eb-b3d6-4f4c-a99f-55d20b0848af.png)
  
    a.  O nome da pesquisa de conteúdo. Conforme mencionado anteriormente, você pode exibir e comparar as estatísticas de várias pesquisas.
    
    b. O tipo de local de conteúdo que foi pesquisado. Cada linha exibe as estatísticas de caixas de correio, sites e pastas públicas da pesquisa especificada.
    
    c. O número de locais de conteúdo que contêm itens que correspondem à consulta de pesquisa. Para caixas de correio, essa estatística também inclui o número de caixas de correio de arquivo morto que contêm itens que correspondem à consulta de pesquisa.
    
    d. O número total de itens de todos os locais de conteúdo especificados que correspondem à consulta de pesquisa. Exemplos de tipos de item incluem mensagens de email, itens de calendário e documentos. Se um item contiver várias instâncias de uma palavra-chave que está sendo pesquisada, ela só será contada uma vez no número total de itens. Por exemplo, se você estiver pesquisando palavras "stock" ou "disfraude" e uma mensagem de email contiver três instâncias da palavra "stock", ela só será contada uma vez na coluna **itens** . 
    
    e. O tamanho total de todos os itens que foram encontrados no local de conteúdo especificado que corresponde à consulta de pesquisa. 
    
    **Queries**
    
    Esta página exibe estatísticas sobre a consulta de pesquisa.
    
    ![Estatísticas de consulta de pesquisa para as pesquisas selecionadas](../media/dc817526-dfb9-43d3-a14c-4c58077eb7bb.png)
  
    a. O nome da pesquisa de conteúdo para a qual a linha contém as estatísticas de consulta.
    
    b. O tipo de local de conteúdo ao qual as estatísticas de consulta se aplicam.
    
    c. Essa coluna indica a qual parte da consulta de pesquisa as estatísticas são aplicáveis. **Primary** indica a consulta de pesquisa inteira. Se você usar uma lista de palavras-chave ao criar ou editar uma consulta de pesquisa, as estatísticas de cada componente da consulta serão incluídas nessa tabela. Consulte a seção [obter estatísticas de palavra-chave para pesquisas de conteúdo](#get-keyword-statistics-for-content-searches) neste artigo para obter mais informações. 
    
    d. Esta coluna contém a consulta de pesquisa real que é executada pela ferramenta de pesquisa de conteúdo. Observe que a ferramenta adiciona automaticamente alguns componentes adicionais à consulta que você criou. 

    - Quando você procura todo o conteúdo nas caixas de correio (não especificando nenhuma palavra-chave), a consulta de palavras-chave real é  `size>=0` para que todos os itens sejam retornados. 
    
     - Quando você pesquisa sites do SharePoint Online e do OneDrive for Business, os dois componentes a seguir são adicionados:
    
          **Não IsExternalContent: 1** -exclui qualquer conteúdo de uma organização local do SharePoint. 
    
          **Não IsOneNotePage: 1** -exclui todos os arquivos do OneNote porque eles seriam duplicatas de qualquer documento que corresponda à consulta de pesquisa. 

    
    e. O número de locais de conteúdo (especificado pela coluna * * tipo de local * *) que contêm itens que correspondem à consulta de pesquisa listada na coluna **consulta** . 
    
    f. O número de itens (do local de conteúdo especificado) que correspondem à consulta de pesquisa listada na coluna **consulta** . Conforme explicado anteriormente, se um item contiver várias instâncias de uma palavra-chave que está sendo pesquisada, ela só será contada uma vez na coluna this. 
    
    g. O tamanho total de todos os itens que foram encontrados (no local de conteúdo especificado) que correspondem à consulta de pesquisa na coluna de **consulta** . 
    
    **Principais locais**
    
    Esta página exibe estatísticas sobre o número de itens que correspondem à consulta de pesquisa em cada local de conteúdo pesquisado. Os primeiros 1.000 locais são exibidos. Se você exibir estatísticas para várias pesquisas, os principais locais de 1.000 para cada pesquisa são exibidos. Observe que um local de conteúdo não está incluído nesta página se ela não contiver nenhum item correspondente à consulta de pesquisa.
    
    ![Estatísticas sobre o número de itens encontrados nos locais de conteúdo que foram pesquisados](../media/35a820b0-85d9-45d1-9a0c-c74bec803e67.png)
  
    a. O nome do local do conteúdo.
    
    b. O tipo de local de conteúdo ao qual as estatísticas de local se aplicam.
    
    c. Há colunas para cada pesquisa para a qual você está exibindo as estatísticas. Esta coluna mostra o número (e o tamanho total) dos itens que correspondem à consulta de pesquisa em cada local de conteúdo. Observe que, quando você estiver exibindo as estatísticas de várias pesquisas, a "na" nesta coluna indica que o local do conteúdo não foi incluído nessa pesquisa. 

## <a name="get-keyword-statistics-for-content-searches"></a>Obter estatísticas de palavra-chave para pesquisas de conteúdo

Como explicado anteriormente, a página **consultas** mostra a consulta de pesquisa e o número (e o tamanho) dos itens que correspondem à consulta. Se você usar uma lista de palavras-chave ao criar ou editar uma consulta de pesquisa, poderá obter estatísticas aprimoradas que mostrem quantos itens correspondem a cada palavra-chave ou frase de palavra-chave. Isso pode ajudá-lo a identificar rapidamente quais partes da consulta são as mais (e menos) eficientes. Por exemplo, se uma palavra-chave retornar um grande número de itens, você pode optar por refinar a consulta de palavra-chave para restringir os resultados da pesquisa. Você pode configurar uma lista de palavras-chave ao criar ou editar uma pesquisa de conteúdo. 


Para criar uma lista de palavras-chave e exibir estatísticas de palavras-chave para uma pesquisa de conteúdo:
  
1. No centro de conformidade & segurança, vá para **Search** \> **pesquisa de conteúdo**de pesquisa.
    
2. Na lista de pesquisas de conteúdo, clique em uma pesquisa e, em seguida, clique em **Editar** ![ ícone de edição ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .
    
3. Clique em **consulta** e faça o seguinte: 
    
    ![Clique na caixa de seleção Mostrar lista de palavras-chave e digite uma palavra-chave em cada linha](../media/73ef46dd-3d5c-415d-b5e7-c3559caaafe2.png)
  
    a. Clique na caixa de seleção **Mostrar lista de palavras-chave** . 
    
    b. Digite uma palavra-chave ou fase de palavra-chave em uma linha na tabela Keywords. Por exemplo, digite **orçamento** na primeira linha e, em seguida, digite **segurança** na segunda linha. 
    
4. Após adicionar as palavras-chave que você deseja pesquisar e obter as estatísticas, clique em **Pesquisar** para executar a pesquisa revisada. 
    
5. Quando a pesquisa estiver concluída, selecione-a na lista de pesquisas e, em seguida, clique no botão Pesquisar estatísticas da pesquisa de **estatísticas** ![ ](../media/9bf56d43-25bf-4f53-a4be-f4d55102310c.png) . Você também pode exibir e comparar as estatísticas de palavras-chave para várias pesquisas.
    
6. Na página **Estatísticas de pesquisa** , clique em **consulta** para exibir as estatísticas de palavra-chave das pesquisas selecionadas. 
    
    ![As estatísticas de cada palavra-chave para as pesquisas selecionadas são exibidas](../media/e7910fa9-af93-4df9-92d0-e1e3e089e14f.png)
  
    Conforme mostrado na captura de tela anterior, as estatísticas de cada palavra-chave são exibidas; Isso inclui: 
    
    - As estatísticas de palavra-chave para cada tipo de local de conteúdo incluído na pesquisa.
    
    - A consulta de pesquisa real para cada palavra-chave, que inclui quaisquer condições da consulta de pesquisa. 
    
    - A consulta de pesquisa completa (identificada como **primária** na coluna **parte** ) e as estatísticas da consulta completa. Observe que essas são as mesmas estatísticas exibidas na página de **Resumo** . 

> [!NOTE]
> Para ajudar a reduzir os problemas causados por listas de palavras-chave grandes, agora você está limitado a um máximo de 20 linhas na lista de palavras-chave de uma consulta de pesquisa.
