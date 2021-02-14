---
title: Usando o cache de objetos com o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
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
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: Este artigo explica a diferença entre usar o cache de objetos no SharePoint Server 2013 local e no SharePoint Online.
ms.openlocfilehash: 279d156a941aad6fbe7adbcf052c57f5b58c652f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695385"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a><span data-ttu-id="beb6e-103">Usando o cache de objetos com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="beb6e-103">Using the object cache with SharePoint Online</span></span>

<span data-ttu-id="beb6e-104">Este artigo explica a diferença entre usar o cache de objetos no SharePoint Server 2013 local e no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="beb6e-104">This article explains the difference between using the object cache in SharePoint Server 2013 on-premises and SharePoint Online.</span></span>
  
<span data-ttu-id="beb6e-105">Há um impacto negativo significativo da confiança no cache de objetos na implantação do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="beb6e-105">There is significant negative impact of relying on the object cache in SharePoint Online deployment.</span></span> <span data-ttu-id="beb6e-106">Qualquer dependência no cache de objetos no SharePoint Online reduzirá a confiabilidade da sua página.</span><span class="sxs-lookup"><span data-stu-id="beb6e-106">Any dependency on object cache in SharePoint Online will reduce the reliability of your page.</span></span> 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a><span data-ttu-id="beb6e-107">Como funciona o cache de objetos do SharePoint Online e do SharePoint Server 2013</span><span class="sxs-lookup"><span data-stu-id="beb6e-107">How the SharePoint Online and SharePoint Server 2013 object cache works</span></span>

<span data-ttu-id="beb6e-108">Quando o SharePoint Server 2013 é hospedado no local, o cliente tem servidores Web front-end privados que hospedam o cache de objetos.</span><span class="sxs-lookup"><span data-stu-id="beb6e-108">When SharePoint Server 2013 is hosted on-premises, the customer has private front-end web servers that host the object cache.</span></span> <span data-ttu-id="beb6e-109">Isso significa que o cache é dedicado a um cliente e é limitado apenas pela quantidade de memória disponível e alocada ao cache de objetos.</span><span class="sxs-lookup"><span data-stu-id="beb6e-109">This means the cache is dedicated to one customer and is only limited by how much memory is available and allocated to the object cache.</span></span> <span data-ttu-id="beb6e-110">Como apenas um cliente é atendido no cenário local, os servidores web front-end normalmente têm usuários fazendo solicitações para os mesmos sites constantemente.</span><span class="sxs-lookup"><span data-stu-id="beb6e-110">Because only one customer is served in the on-premises scenario the front-end web servers typically have users making requests to the same sites over and over.</span></span> <span data-ttu-id="beb6e-111">Isso significa que o cache fica cheio rapidamente e permanece cheio dos resultados da consulta de lista e dos objetos do SharePoint que os usuários estão solicitando regularmente.</span><span class="sxs-lookup"><span data-stu-id="beb6e-111">This means that the cache gets full quickly and remains full of the list query results and SharePoint objects that your users are requesting on a regular basis.</span></span>
  
![Mostra o tráfego e a carga para servidores front-end da Web locais](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
<span data-ttu-id="beb6e-113">Como resultado, na segunda vez que um usuário visita uma página, o tempo de carregamento da página melhora.</span><span class="sxs-lookup"><span data-stu-id="beb6e-113">As a result, the second time a user visits a page, the page load time improves.</span></span> <span data-ttu-id="beb6e-114">Após um mínimo de quatro cargas da mesma página, a página é armazenada em cache em todos os servidores web front-end.</span><span class="sxs-lookup"><span data-stu-id="beb6e-114">After a minimum of four loads of the same page, the page is cached on all of the front-end web servers.</span></span>
  
<span data-ttu-id="beb6e-115">Por outro lado, no SharePoint Online há muito mais servidores, mas também muitos outros sites.</span><span class="sxs-lookup"><span data-stu-id="beb6e-115">In contrast, in SharePoint Online there are many more servers but also many more sites.</span></span> <span data-ttu-id="beb6e-116">Cada usuário pode se conectar a um servidor Web front-end diferente que não tenha o cache preenchido.</span><span class="sxs-lookup"><span data-stu-id="beb6e-116">Each user may connect to a different front-end web server that doesn't have the cache populated.</span></span> <span data-ttu-id="beb6e-117">Ou talvez o cache seja preenchido para um servidor, mas o próximo usuário desse servidor Web front-end solicita uma página de um site diferente.</span><span class="sxs-lookup"><span data-stu-id="beb6e-117">Or, perhaps the cache does get populated for a server, but the next user to that front-end web server requests a page from a different site.</span></span> <span data-ttu-id="beb6e-118">Ou, mesmo se o próximo usuário solicitar a mesma página da visita anterior, ele terá uma carga balanceada para um servidor Web front-end diferente que não tenha essa página em seu cache.</span><span class="sxs-lookup"><span data-stu-id="beb6e-118">Or, even if the next user requests the same page as on their previous visit, they are load-balanced to a different front-end web server that doesn't have that page in its cache.</span></span> <span data-ttu-id="beb6e-119">Nesse último caso, o armazenamento em cache não ajuda os usuários.</span><span class="sxs-lookup"><span data-stu-id="beb6e-119">In this last case, caching doesn't help the users at all.</span></span>
  
<span data-ttu-id="beb6e-120">Na figura a seguir, cada ponto representa uma página que um usuário está solicitando e onde ela foi armazenada em cache.</span><span class="sxs-lookup"><span data-stu-id="beb6e-120">In the following figure, each dot represents a page that a user is requesting and where it cached.</span></span> <span data-ttu-id="beb6e-121">Cores diferentes representam diferentes clientes que fazem uso compartilhado da infraestrutura SaaS.</span><span class="sxs-lookup"><span data-stu-id="beb6e-121">Different colors represent different customers making shared use of the SaaS infrastructure.</span></span>
  
![Mostra os resultados do cache de objeto no SharePoint Online](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
<span data-ttu-id="beb6e-123">Como você pode ver no diagrama, as chances de qualquer usuário chegar a um servidor com a versão em cache de sua página são grandes.</span><span class="sxs-lookup"><span data-stu-id="beb6e-123">As you can see from the diagram, the chances of any given user hitting a server with the cached version of their page are slim.</span></span> <span data-ttu-id="beb6e-124">Além disso, devido à grande produtividade e ao fato de que os servidores são compartilhados entre muitos sites, o cache não dura muito, pois há apenas muito espaço disponível para armazenamento em cache.</span><span class="sxs-lookup"><span data-stu-id="beb6e-124">Also, due to the large throughput and fact that the servers are shared between many sites, the cache doesn't last long since there is only so much space for caching available.</span></span>
  
<span data-ttu-id="beb6e-125">Por todos esses motivos, confiar nos usuários que estão recebendo objetos armazenados em cache não é uma maneira eficaz de garantir uma experiência de usuário de qualidade e tempos de carregamento de página no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="beb6e-125">For all of these reasons, relying on users getting cached objects is not an effective way to ensure a quality user experience and page load times in SharePoint Online.</span></span>
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a><span data-ttu-id="beb6e-126">Se não dependermos do cache de objetos para melhorar o desempenho no SharePoint Online, o que usamos em vez disso?</span><span class="sxs-lookup"><span data-stu-id="beb6e-126">If we can't rely on the object cache to improve performance in SharePoint Online, what do we use instead?</span></span>

<span data-ttu-id="beb6e-127">Como você não deve confiar no cache no SharePoint Online, você deve avaliar abordagens de design alternativas para personalizações do SharePoint que usam o cache de objetos.</span><span class="sxs-lookup"><span data-stu-id="beb6e-127">Since you shouldn't rely on caching in SharePoint Online, you should evaluate alternative design approaches for SharePoint customizations that use the object cache.</span></span> <span data-ttu-id="beb6e-128">Isso significa usar abordagens para problemas de desempenho que não dependem do cache de objetos para produzir bons resultados para os usuários.</span><span class="sxs-lookup"><span data-stu-id="beb6e-128">This means using approaches for performance issues which do not rely on the object caching in order to produce good results for users.</span></span> <span data-ttu-id="beb6e-129">Isso é descrito em alguns dos outros artigos desta série e incluem:</span><span class="sxs-lookup"><span data-stu-id="beb6e-129">This is described in some of the other articles in this series and include:</span></span>
  
- [<span data-ttu-id="beb6e-130">Opções de navegação para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="beb6e-130">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="beb6e-131">Minificação e agrupamento no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="beb6e-131">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="beb6e-132">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="beb6e-132">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="beb6e-133">Atraso no carregamento de imagens e JavaScript no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="beb6e-133">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

