---
title: Usar a Web Part de Pesquisa de Conteúdo em vez de Web Part de Consulta de Conteúdo para melhorar o desempenho no SharePoint Online
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
description: Saiba como aumentar o desempenho substituindo a Web Part de Consulta de Conteúdo pela Web Part de Pesquisa de Conteúdo no SharePoint Server 2013 e SharePoint Online.
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687519"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="764b8-103">Usar a Web Part de Pesquisa de Conteúdo em vez de Web Part de Consulta de Conteúdo para melhorar o desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="764b8-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="764b8-104">Este artigo descreve como aumentar o desempenho substituindo a Web Part de Consulta de Conteúdo pela Web Part de Pesquisa de Conteúdo no SharePoint Server 2013 e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="764b8-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="764b8-105">Um dos novos recursos mais avançados do SharePoint Server 2013 e SharePoint Online é a Web Part de Pesquisa de Conteúdo (CSWP).</span><span class="sxs-lookup"><span data-stu-id="764b8-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="764b8-106">Esta Web Part usa o índice de pesquisa para recuperar rapidamente os resultados que são mostrados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="764b8-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="764b8-107">Use a Web Part de Pesquisa de Conteúdo em vez da Web Part de Consulta de Conteúdo (CQWP) em suas páginas para melhorar o desempenho de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="764b8-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="764b8-108">Usar uma Web Part de Pesquisa de Conteúdo em uma Web Part de Consulta de Conteúdo quase sempre resultará em um desempenho de carga de página significativamente melhor no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="764b8-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="764b8-109">Há um pouco de configuração adicional para obter a consulta correta, mas as recompensas são um desempenho aprimorado e usuários mais felizes.</span><span class="sxs-lookup"><span data-stu-id="764b8-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="764b8-110">Comparando o ganho de desempenho que você obter com o uso da Web Part de Pesquisa de Conteúdo em vez de Web Part de Consulta de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="764b8-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="764b8-111">Os exemplos a seguir mostram os ganhos relativos de desempenho que você pode receber ao usar uma Web Part de Pesquisa de Conteúdo em vez de uma Web Part de Consulta de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="764b8-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="764b8-112">Os efeitos são mais óbvios com uma estrutura de site complexa e consultas de conteúdo muito amplas.</span><span class="sxs-lookup"><span data-stu-id="764b8-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="764b8-113">Este site de exemplo tem as seguintes características:</span><span class="sxs-lookup"><span data-stu-id="764b8-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="764b8-114">8 níveis de subsites.</span><span class="sxs-lookup"><span data-stu-id="764b8-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="764b8-115">Lista usando um tipo de conteúdo "frutas" personalizado.</span><span class="sxs-lookup"><span data-stu-id="764b8-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="764b8-116">Na Web Part, a consulta de conteúdo é ampla, retornando todos os itens com o tipo de conteúdo de "frutas".</span><span class="sxs-lookup"><span data-stu-id="764b8-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="764b8-117">O exemplo usa apenas 50 itens entre os 8 sites.</span><span class="sxs-lookup"><span data-stu-id="764b8-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="764b8-118">Os efeitos serão ainda mais pronunciados para sites com mais conteúdo.</span><span class="sxs-lookup"><span data-stu-id="764b8-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="764b8-119">Aqui está uma captura de tela dos resultados da Web Part de Consulta de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="764b8-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Gráfico que mostra a consulta de conteúdo da web part](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="764b8-121">No Internet Explorer, use a **guia Rede** das ferramentas de desenvolvedor F12 para ver os detalhes do header de resposta.</span><span class="sxs-lookup"><span data-stu-id="764b8-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="764b8-122">Na captura de tela a seguir, o valor do **SPRequestDuration** para esta carga de página é de 924 milissegundos.</span><span class="sxs-lookup"><span data-stu-id="764b8-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![Captura de tela mostrando a duração da solicitação de 924](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="764b8-124">**SPRequestDuration** indica a quantidade de trabalho que é feita no servidor para preparar a página.</span><span class="sxs-lookup"><span data-stu-id="764b8-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="764b8-125">Alternar conteúdo por consulta Web Parts conteúdo por pesquisa Web Parts reduz drasticamente o tempo necessário para renderizar a página.</span><span class="sxs-lookup"><span data-stu-id="764b8-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="764b8-126">Por outro lado, uma página com uma Web Part de Pesquisa de Conteúdo equivalente, retornando o mesmo número de resultados tem um **valor SPRequestDuration** de 106 milissegundos, conforme mostrado nesta captura de tela:</span><span class="sxs-lookup"><span data-stu-id="764b8-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![Captura de tela mostrando a Duração da Solicitação de 106](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="764b8-128">Adicionar uma Web Part de Pesquisa de Conteúdo no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="764b8-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="764b8-129">Adicionar uma Web Part de Pesquisa de Conteúdo é muito semelhante a uma Web Part de Consulta de Conteúdo regular.</span><span class="sxs-lookup"><span data-stu-id="764b8-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="764b8-130">Consulte a seção *"Adicionar uma Web Part de Pesquisa de Conteúdo"* em [Configurar uma Web Part](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)de Pesquisa de Conteúdo em SharePoint .</span><span class="sxs-lookup"><span data-stu-id="764b8-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="764b8-131">Criando a consulta de pesquisa correta para sua Web Part de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="764b8-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="764b8-132">Depois de adicionar uma Web Part de Pesquisa de Conteúdo, você pode refinar a pesquisa e retornar os itens que deseja.</span><span class="sxs-lookup"><span data-stu-id="764b8-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="764b8-133">Para obter instruções detalhadas sobre como fazer isso, consulte a seção "Exibir conteúdo configurando uma consulta avançada em uma Web Part de Pesquisa de *Conteúdo"* em Configure a Content [Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span><span class="sxs-lookup"><span data-stu-id="764b8-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="764b8-134">Ferramenta de teste e criação de consultas</span><span class="sxs-lookup"><span data-stu-id="764b8-134">Query building and testing tool</span></span>

<span data-ttu-id="764b8-135">Para uma ferramenta para criar e testar consultas complexas, consulte a [Ferramenta de Consulta de Pesquisa](https://sp2013searchtool.codeplex.com/) no Codeplex.</span><span class="sxs-lookup"><span data-stu-id="764b8-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

