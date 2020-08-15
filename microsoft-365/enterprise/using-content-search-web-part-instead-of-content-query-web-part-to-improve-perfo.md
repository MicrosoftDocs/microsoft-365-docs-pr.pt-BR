---
title: Usando a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo para melhorar o desempenho no SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: Saiba como aumentar o desempenho substituindo a Web Part de consulta de conteúdo pela Web Part de pesquisa de conteúdo no SharePoint Server 2013 e no SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687519"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a>Usando a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo para melhorar o desempenho no SharePoint Online

Este artigo descreve como aumentar o desempenho substituindo a Web Part de consulta de conteúdo pela Web Part de pesquisa de conteúdo no SharePoint Server 2013 e no SharePoint Online.
  
Um dos novos recursos mais poderosos do SharePoint Server 2013 e do SharePoint Online é a Web Part de pesquisa de conteúdo (CSWP). Esta Web Part usa o índice de pesquisa para recuperar rapidamente os resultados mostrados para o usuário. Use a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo (CQWP) em suas páginas para melhorar o desempenho de seus usuários.
  
Usar uma Web Part de pesquisa de conteúdo em uma Web Part de consulta de conteúdo quase sempre resultará em um desempenho de carregamento de página significativamente melhor no SharePoint Online. Há uma pequena configuração adicional para obter a consulta certa, mas os prêmios têm desempenho aprimorado e mais feliz usuários.
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a>Comparando o ganho de desempenho obtido usando a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo

Os exemplos a seguir mostram os ganhos de desempenho relativos que você pode receber ao usar uma Web Part de pesquisa de conteúdo em vez de uma Web Part de consulta de conteúdo. Os efeitos são mais óbvios com uma estrutura de site complexa e consultas de conteúdo muito abrangentes.
  
Este exemplo de site tem as seguintes características:
  
- 8 níveis de subsites.
    
- Listas que usam um tipo de conteúdo "fruta" personalizado.
    
- Na Web Part, a consulta de conteúdo é ampla, retornando todos os itens com o tipo de conteúdo "fruta".
    
- O exemplo usa apenas 50 itens nos 8 sites. Os efeitos serão ainda mais pronunciados para sites com mais conteúdo.
    
Veja a seguir uma captura de tela dos resultados da Web Part de consulta de conteúdo.
  
![Gráfico que mostra a consulta de conteúdo da web part](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
No Internet Explorer, use a guia **rede** das ferramentas de desenvolvedor F12 para examinar os detalhes do cabeçalho da resposta. Na captura de tela a seguir, o valor de **SPRequestDuration** para esta carga de página é de 924 milissegundos. 
  
![Captura de tela mostrando a duração da solicitação de 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 **SPRequestDuration** indica a quantidade de trabalho feito no servidor para preparar a página. Alternar conteúdo por Web Parts de consulta com conteúdo por Web Parts de pesquisa reduz drasticamente o tempo que leva para renderizar a página. Por outro lado, uma página com uma Web Part de pesquisa de conteúdo equivalente, retornando o mesmo número de resultados tem um valor de **SPRequestDuration** de 106 milissegundos, conforme mostrado nesta captura de tela: 
  
![Captura de tela mostrando a Duração da Solicitação de 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a>Adicionando uma Web Part de pesquisa de conteúdo no SharePoint Online

A adição de uma Web Part de pesquisa de conteúdo é muito semelhante a uma Web Part de consulta de conteúdo normal. Consulte a seção  *"adicionar uma Web Part de pesquisa de conteúdo"*  em [Configurar uma Web Part de pesquisa de conteúdo no SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a>Criando a consulta de pesquisa certa para a Web Part de pesquisa de conteúdo

Depois de adicionar uma Web Part de pesquisa de conteúdo, você pode refinar a pesquisa e retornar os itens desejados. Para obter instruções detalhadas sobre como fazer isso, confira a seção  *"exibir conteúdo Configurando uma consulta avançada em uma Web Part de pesquisa de conteúdo"*  em [Configurar uma Web Part de pesquisa de conteúdo no SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).
  
## <a name="query-building-and-testing-tool"></a>Ferramenta de criação e teste de consulta

Para uma ferramenta para compilar e testar consultas complexas, consulte a [ferramenta de consulta de pesquisa](https://sp2013searchtool.codeplex.com/) no CodePlex. 
  

