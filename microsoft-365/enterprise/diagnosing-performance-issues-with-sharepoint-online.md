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
description: Este artigo mostra como diagnosticar problemas comuns com seu site SharePoint Online usando ferramentas de desenvolvedor do Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927607"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>Diagnosticando problemas de desempenho no SharePoint Online

Este artigo mostra como diagnosticar problemas comuns com seu site SharePoint Online usando ferramentas de desenvolvedor do Internet Explorer.
  
Há três maneiras diferentes de identificar que uma página em um site SharePoint Online tem um problema de desempenho com as personalizações.
  
- O monitor de rede da barra de ferramentas F12

- Comparação com uma linha de base não personalizada

- SharePoint Métricas de header de resposta online

Este tópico descreve como usar cada um desses métodos para diagnosticar problemas de desempenho. Depois de descobrir a causa do problema, você pode trabalhar em direção a uma solução usando os artigos sobre como melhorar SharePoint desempenho que você pode encontrar em https://aka.ms/tune .
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>Usar a barra de ferramentas F12 para diagnosticar o desempenho no SharePoint Online
<a name="F12ToolInfo"> </a>

Neste artigo, usamos o Internet Explorer 11. As versões das ferramentas de desenvolvedor F12 em outros navegadores têm recursos semelhantes, embora possam parecer um pouco diferentes. Para obter informações sobre as ferramentas de desenvolvedor F12, consulte:
  
- [Novidades nas Ferramentas F12](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [Usando as ferramentas de desenvolvedor F12](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

Para levantar as ferramentas de desenvolvedor, pressione **F12** e clique no ícone Wi-Fi:
  
![Captura de tela de ícone de Wi-Fi de ferramentas de desenvolvedor F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
Na guia **Rede,** pressione o botão de reprodução verde para carregar uma página. A ferramenta retorna todos os arquivos que o navegador solicita para obter a página que você solicitou. A captura de tela a seguir mostra uma lista dessas.
  
![Captura de tela da lista de arquivos retornados com uma solicitação de página.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
Você também pode ver os horários de download dos arquivos no lado direito, conforme mostrado nesta captura de tela.
  
![Diagrama mostrando o tempo de carregamento das páginas solicitadas do SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
Isso oferece uma representação visual de quanto tempo o arquivo levou para carregar. A linha verde representa quando a página está pronta para ser renderizada pelo navegador. Isso pode lhe dar uma visão rápida dos diferentes arquivos que podem estar causando cargas lentas de página em seu site.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>Configurando uma linha de base não personalizada para SharePoint Online
<a name="F12ToolInfo"> </a>

A melhor maneira de determinar os pontos fracos de desempenho do seu site é configurar um conjunto de sites totalmente pronto para uso no SharePoint Online. Dessa forma, você pode comparar todos os vários aspectos do seu site com o que você obteria sem personalização na página. A OneDrive for Business página inicial é um bom exemplo de um conjunto de sites separado que é improvável ter qualquer personalização.
  
## <a name="viewing-sharepoint-response-header-information"></a>Exibindo SharePoint de header de resposta
<a name="F12ToolInfo"> </a>

No SharePoint Online, você pode acessar as informações enviadas de volta ao navegador no header de resposta para cada arquivo. O valor mais útil para diagnosticar problemas de desempenho é **SPRequestDuration**, que exibe o tempo que a solicitação levou no servidor a ser processado. Isso pode ajudar a determinar se a solicitação é muito pesada e o recurso é intenso. Essa é a melhor dica que você tem sobre quanto trabalho o servidor está fazendo para atender à página.

### <a name="to-view-sharepoint-response-header-information"></a>Para exibir SharePoint informações do header de resposta
  
1. Verifique se você tem as ferramentas F12 instaladas. Para obter mais informações sobre como baixar e instalar essas ferramentas, consulte [Novidades nas ferramentas F12.](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

2. Nas ferramentas F12, na **guia** Rede, pressione o botão de reprodução verde para carregar uma página.

3. Clique em um dos arquivos .aspx retornados pela ferramenta e clique em **DETALHES.**

    ![Mostra detalhes do cabeçalho de resposta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. Clique **em Headers de resposta**.

    ![Diagrama mostrando a URL do cabeçalho de resposta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>O que está causando problemas de desempenho no SharePoint Online?
<a name="F12ToolInfo"> </a>

O artigo Opções de navegação para [SharePoint Online](navigation-options-for-sharepoint-online.md) mostra um exemplo de uso do valor SPRequestDuration para determinar que a navegação estrutural complicada estava fazendo com que a página demorava muito para ser processada no servidor. Ao tirar um valor para um site de linha de base (sem personalização), é possível determinar se um determinado arquivo está demorando muito para ser carregado. O exemplo usado nas [opções de navegação para SharePoint Online](navigation-options-for-sharepoint-online.md) é o arquivo .aspx principal. Esse arquivo contém a maior parte do código ASP.NET que é executado para a carga da página. Dependendo do modelo de site usado, pode ser start.aspx, home.aspx, default.aspx ou outro nome se você personalizar a home page. Se esse número for consideravelmente maior do que seu site de linha de base, é uma boa indicação de que há algo complexo acontecendo em sua página que está causando problemas de desempenho.
  
Depois de identificar que um problema específico do seu site é identificado, a maneira recomendada de descobrir o que está causando um desempenho ruim é eliminar todas as causas possíveis, como personalizações de página, e, em seguida, adicioná-los de volta ao site um por um. Depois de remover personalizações suficientes para que a página tenha um bom desempenho, você poderá adicionar de volta personalizações específicas uma a uma.
  
Por exemplo, se você tiver uma navegação muito complexa tente alterar a navegação para não mostrar subs sites, verifique as ferramentas de desenvolvedor para ver se isso faz diferença. Ou se você tiver uma grande quantidade de roll-ups de conteúdo tente removê-los de sua página e veja se isso melhora as coisas. Se você eliminar todas as causas possíveis e adicioná-las novamente em uma de cada vez, poderá identificar facilmente quais recursos são o maior problema e, em seguida, trabalhar em direção a uma solução.