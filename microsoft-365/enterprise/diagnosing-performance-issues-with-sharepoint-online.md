---
title: Diagnosticando problemas de desempenho no SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: Este artigo mostra como você pode diagnosticar problemas comuns com seu site do SharePoint online usando as ferramentas de desenvolvedor do Internet Explorer.
ms.openlocfilehash: a8a79afd860006a16874370b1124696550dab029
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687148"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnosticando problemas de desempenho no SharePoint Online

Este artigo mostra como você pode diagnosticar problemas comuns com seu site do SharePoint online usando as ferramentas de desenvolvedor do Internet Explorer.
  
Há três maneiras diferentes que você pode identificar que uma página em um site do SharePoint Online tem um problema de desempenho com as personalizações.
  
- O monitor de rede da barra de ferramentas F12

- Comparação com uma linha de base não personalizada

- Métricas de cabeçalho de resposta do SharePoint Online

Este tópico descreve como usar cada um desses métodos para diagnosticar problemas de desempenho. Depois de descobrir a causa do problema, você pode trabalhar em direção a uma solução usando os artigos sobre como melhorar o desempenho do SharePoint que você pode encontrar https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Usando a barra de ferramentas F12 para diagnosticar o desempenho no SharePoint Online
<a name="F12ToolInfo"> </a>

Neste artigo, utilizamos o Internet Explorer 11. As versões das ferramentas de desenvolvedor F12 em outros navegadores têm recursos semelhantes, embora possam parecer um pouco diferentes. Para obter informações sobre as ferramentas de desenvolvedor F12, consulte:
  
- [O que há de novo nas Ferramentas F12](https://go.microsoft.com/fwlink/p/?LinkId=522545)

- [Usando as ferramentas de desenvolvedor F12](https://go.microsoft.com/fwlink/p/?LinkId=522546)

Para exibir as ferramentas de desenvolvedor, pressione **F12** e clique no ícone de Wi-Fi:
  
![Captura de tela de ícone de Wi-Fi de ferramentas de desenvolvedor F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Na guia **rede** , pressione o botão de execução verde para carregar uma página. A ferramenta retorna todos os arquivos que o navegador solicita para obter a página que você solicitou. A captura de tela a seguir mostra uma lista.
  
![Captura de tela da lista de arquivos retornados com uma solicitação de página.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
Você também pode ver os tempos de download dos arquivos no lado direito, conforme mostrado na captura de tela.
  
![Diagrama mostrando o tempo de carregamento das páginas solicitadas do SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Isso dá a você uma representação visual de quanto tempo o arquivo levou para carregar. A linha verde representa quando a página está pronta para ser renderizada pelo navegador. Isso pode dar a você uma visão rápida dos diferentes arquivos que podem estar causando cargas de página lentas no site.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Configurando uma linha de base não personalizada para o SharePoint Online
<a name="F12ToolInfo"> </a>

A melhor maneira de determinar o desempenho do seu site pontos fracos é configurar um conjunto de sites totalmente pronto no SharePoint Online. Dessa forma, você pode comparar todos os vários aspectos do seu site com o que você obteria sem nenhuma personalização na página. A home page do OneDrive for Business é um bom exemplo de um conjunto de sites separado que provavelmente não terá qualquer personalização.
  
## <a name="viewing-sharepoint-response-header-information"></a>Exibindo informações de cabeçalho de resposta do SharePoint
<a name="F12ToolInfo"> </a>

No SharePoint Online, você pode acessar as informações enviadas de volta ao navegador no cabeçalho de resposta de cada arquivo. O valor mais útil para diagnosticar problemas de desempenho é o **SPRequestDuration**, que exibe a quantidade de tempo que a solicitação levou no servidor para ser processada. Isso pode ajudar a determinar se a solicitação é muito pesada e intensiva em recursos. Esta é a melhor informação que você tem em quanto trabalho o servidor está fazendo para atender à página.

### <a name="to-view-sharepoint-response-header-information"></a>Para exibir informações de cabeçalho de resposta do SharePoint
  
1. Verifique se você tem as ferramentas F12 instaladas. Para obter mais informações sobre como baixar e instalar essas ferramentas, consulte [What ' s New in F12 Tools](https://go.microsoft.com/fwlink/p/?LinkId=522545).

2. Nas Ferramentas F12, na guia **rede** , pressione o botão de execução verde para carregar uma página.

3. Clique em um dos arquivos. aspx retornados pela ferramenta e, em seguida, clique em **detalhes**.

    ![Mostra detalhes do cabeçalho de resposta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Clique em **cabeçalhos de resposta**.

    ![Diagrama mostrando a URL do cabeçalho de resposta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>O que está causando problemas de desempenho no SharePoint Online?
<a name="F12ToolInfo"> </a>

O artigo [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md) mostra um exemplo de uso do valor SPRequestDuration para determinar que a navegação estrutural complicada estava fazendo com que a página demore muito tempo para ser processada no servidor. Ao pegar um valor para um site de linha de base (sem personalização), é possível determinar se um determinado arquivo está demorando muito para ser carregado. O exemplo usado nas [Opções de navegação para o SharePoint Online](navigation-options-for-sharepoint-online.md) é o arquivo Main. aspx. Esse arquivo contém a maior parte do código ASP.NET que é executado para o carregamento da página. Dependendo do modelo de site que você usa, pode ser Start. aspx, Home. aspx, Default. aspx ou outro nome se você personalizar a Home Page. Se esse número for consideravelmente maior do que o site da linha de base, é uma boa indicação de que há algo complexo em sua página que está causando problemas de desempenho.
  
Depois de identificar um problema específico para o seu site, a maneira recomendada de descobrir o que está causando um desempenho ruim é eliminar todas as causas possíveis, como personalizações de página e adicioná-las de volta ao site um por um. Depois de remover as personalizações suficientes que a página está executando bem, você poderá adicionar personalizações específicas uma a uma.
  
Por exemplo, se você tiver uma navegação muito complexa, tente alterar a navegação para não mostrar os subsites e, em seguida, verifique as ferramentas de desenvolvedor para ver se isso faz diferença. Ou se você tiver uma grande quantidade de registros de conteúdo, tente removê-los da sua página e veja se isso melhora as coisas. Se você eliminar todas as causas possíveis e adicioná-las novamente de uma por vez, poderá identificar facilmente quais recursos são o maior problema e, em seguida, trabalhar em direção a uma solução.
