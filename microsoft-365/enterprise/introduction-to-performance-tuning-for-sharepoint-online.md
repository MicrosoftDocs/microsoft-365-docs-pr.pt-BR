---
title: Introdução ao ajuste de desempenho para o SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: Este artigo explica quais aspectos específicos você precisa considerar ao criar páginas para obter um melhor desempenho no SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687419"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="cb66c-103">Introdução ao ajuste de desempenho para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="cb66c-104">Este artigo explica quais aspectos específicos você precisa considerar ao criar páginas para obter um melhor desempenho no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb66c-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="cb66c-105">Métricas do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-105">SharePoint Online metrics</span></span>

<span data-ttu-id="cb66c-106">As seguintes métricas amplas para o SharePoint Online fornecem dados reais do mundo sobre o desempenho:</span><span class="sxs-lookup"><span data-stu-id="cb66c-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="cb66c-107">Como carregar páginas rápidas</span><span class="sxs-lookup"><span data-stu-id="cb66c-107">How fast pages load</span></span>
    
- <span data-ttu-id="cb66c-108">Quantas viagens de ida e segundo são exigidas por página</span><span class="sxs-lookup"><span data-stu-id="cb66c-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="cb66c-109">Problemas com o serviço</span><span class="sxs-lookup"><span data-stu-id="cb66c-109">Issues with the service</span></span>
    
- <span data-ttu-id="cb66c-110">Outras coisas que causam degradação de desempenho</span><span class="sxs-lookup"><span data-stu-id="cb66c-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="cb66c-111">Conclusões atingidas por causa dos dados</span><span class="sxs-lookup"><span data-stu-id="cb66c-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="cb66c-112">Os dados nos dizem:</span><span class="sxs-lookup"><span data-stu-id="cb66c-112">The data tells us:</span></span>
  
- <span data-ttu-id="cb66c-113">A maioria das páginas tem um bom desempenho no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb66c-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="cb66c-114">Páginas não personalizadas carregam muito rapidamente.</span><span class="sxs-lookup"><span data-stu-id="cb66c-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="cb66c-115">O OneDrive for Business, sites de equipe e páginas de sistema, como _layouts, etc., são todos rápidos para carregar.</span><span class="sxs-lookup"><span data-stu-id="cb66c-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="cb66c-116">O 1% mais lento de páginas do SharePoint Online demora mais de 5.000 milissegundos para carregar.</span><span class="sxs-lookup"><span data-stu-id="cb66c-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="cb66c-117">Um teste de benchmark simples que você pode usar seria medir o desempenho comparando o tempo de carregamento do seu portal com o tempo de carregamento da home page do OneDrive for Business, pois usa alguns recursos personalizados.</span><span class="sxs-lookup"><span data-stu-id="cb66c-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="cb66c-118">Em geral, este será o suporte a primeira etapa solicitará a conclusão da solução de problemas de desempenho da rede.</span><span class="sxs-lookup"><span data-stu-id="cb66c-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="cb66c-119">Usar uma conta de usuário padrão ao verificar o desempenho</span><span class="sxs-lookup"><span data-stu-id="cb66c-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="cb66c-120">Um administrador do conjunto de sites, proprietário do site, editor ou colaborador pertence a grupos de segurança adicionais, têm permissões adicionais e, portanto, têm elementos adicionais que o SharePoint carrega em uma página.</span><span class="sxs-lookup"><span data-stu-id="cb66c-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="cb66c-121">Isso se aplica ao SharePoint local e ao SharePoint Online, mas em um cenário local as diferenças não serão tão facilmente percebidas quanto no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb66c-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="cb66c-122">Para avaliar corretamente como uma página será executada para os usuários, você deve usar uma conta de usuário padrão para evitar o carregamento de controles de criação e tráfego adicional relacionado a grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="cb66c-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="cb66c-123">Categorias de conexão para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="cb66c-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="cb66c-124">Você pode categorizar as conexões entre o servidor e o usuário em três componentes principais.</span><span class="sxs-lookup"><span data-stu-id="cb66c-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="cb66c-125">Considere estes ao projetar páginas do SharePoint Online para obter informações sobre o tempo de carregamento.</span><span class="sxs-lookup"><span data-stu-id="cb66c-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="cb66c-126">**Servidor do** Os servidores que a Microsoft hospeda nos data centers.</span><span class="sxs-lookup"><span data-stu-id="cb66c-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="cb66c-127">**Rede** A rede da Microsoft, a Internet e sua rede local entre o datacenter e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cb66c-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="cb66c-128">**Navegador** Onde a página é carregada.</span><span class="sxs-lookup"><span data-stu-id="cb66c-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="cb66c-129">Dentro dessas três conexões, geralmente há cinco razões que causam 95% de páginas lentas.</span><span class="sxs-lookup"><span data-stu-id="cb66c-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="cb66c-130">Cada um desses motivos é discutido neste artigo:</span><span class="sxs-lookup"><span data-stu-id="cb66c-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="cb66c-131">Problemas de navegação</span><span class="sxs-lookup"><span data-stu-id="cb66c-131">Navigation issues</span></span>
    
- <span data-ttu-id="cb66c-132">Distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="cb66c-132">Content roll up</span></span>
    
- <span data-ttu-id="cb66c-133">Arquivos grandes</span><span class="sxs-lookup"><span data-stu-id="cb66c-133">Large files</span></span>
    
- <span data-ttu-id="cb66c-134">Muitas solicitações para o servidor</span><span class="sxs-lookup"><span data-stu-id="cb66c-134">Many requests to the server</span></span>
    
- <span data-ttu-id="cb66c-135">Processamento de Web Part</span><span class="sxs-lookup"><span data-stu-id="cb66c-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="cb66c-136">Conexão do servidor</span><span class="sxs-lookup"><span data-stu-id="cb66c-136">Server connection</span></span>

<span data-ttu-id="cb66c-137">Muitos dos problemas que afetam o desempenho com o SharePoint local também se aplicam ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb66c-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="cb66c-138">Como esperado, você tem muito mais controle sobre como os servidores são executados com o SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="cb66c-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="cb66c-139">Com o SharePoint Online, as coisas são um pouco diferentes.</span><span class="sxs-lookup"><span data-stu-id="cb66c-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="cb66c-140">Quanto mais trabalho fizer um servidor, mais demorará para renderizar uma página.</span><span class="sxs-lookup"><span data-stu-id="cb66c-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="cb66c-141">Com o SharePoint, o maior culpado nesse respeito é páginas complexas com várias Web Parts.</span><span class="sxs-lookup"><span data-stu-id="cb66c-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="cb66c-142">SharePoint Server local</span><span class="sxs-lookup"><span data-stu-id="cb66c-142">SharePoint Server on-premises</span></span>
  
![Captura de tela do servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="cb66c-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-144">SharePoint Online</span></span>
  
![Captura de tela do servidor online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="cb66c-146">Com o SharePoint Online, determinadas solicitações de página podem realmente acabar chamando vários servidores.</span><span class="sxs-lookup"><span data-stu-id="cb66c-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="cb66c-147">Você pode acabar com uma matriz de solicitações entre servidores para uma solicitação individual.</span><span class="sxs-lookup"><span data-stu-id="cb66c-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="cb66c-148">Essas interações são caras de uma perspectiva de carregamento de página e tornarão as coisas lentas.</span><span class="sxs-lookup"><span data-stu-id="cb66c-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="cb66c-149">Os exemplos dessas interações de servidor para servidor são:</span><span class="sxs-lookup"><span data-stu-id="cb66c-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="cb66c-150">Web para SQL Servers</span><span class="sxs-lookup"><span data-stu-id="cb66c-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="cb66c-151">Servidores da Web para aplicativos</span><span class="sxs-lookup"><span data-stu-id="cb66c-151">Web to application servers</span></span>
    
<span data-ttu-id="cb66c-152">A outra coisa que pode reduzir as interações com o servidor é erros de cache.</span><span class="sxs-lookup"><span data-stu-id="cb66c-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="cb66c-153">Ao contrário do SharePoint local, há uma chance muito leve de que você acesse o mesmo servidor para uma página que visitou anteriormente; Isso torna o cache do objeto obsoleto.</span><span class="sxs-lookup"><span data-stu-id="cb66c-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="cb66c-154">Conexão de rede</span><span class="sxs-lookup"><span data-stu-id="cb66c-154">Network connection</span></span>

<span data-ttu-id="cb66c-155">Com o SharePoint local que não faz uso de uma WAN, você pode usar uma conexão de alta velocidade entre o datacenter e os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="cb66c-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="cb66c-156">Geralmente, as coisas são fáceis de gerenciar a partir de uma perspectiva de rede.</span><span class="sxs-lookup"><span data-stu-id="cb66c-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="cb66c-157">Com o SharePoint Online, há alguns fatores que devem ser considerados; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="cb66c-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="cb66c-158">A rede da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cb66c-158">The Microsoft network</span></span>
    
- <span data-ttu-id="cb66c-159">A Internet</span><span class="sxs-lookup"><span data-stu-id="cb66c-159">The Internet</span></span>
    
- <span data-ttu-id="cb66c-160">O ISP</span><span class="sxs-lookup"><span data-stu-id="cb66c-160">The ISP</span></span>
    
<span data-ttu-id="cb66c-161">Independentemente da versão do SharePoint (e da rede) que você está usando, as coisas que normalmente farão com que a rede estejam ocupadas incluem:</span><span class="sxs-lookup"><span data-stu-id="cb66c-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="cb66c-162">Carga grande</span><span class="sxs-lookup"><span data-stu-id="cb66c-162">Large payload</span></span>
    
- <span data-ttu-id="cb66c-163">Muitos arquivos</span><span class="sxs-lookup"><span data-stu-id="cb66c-163">Many files</span></span>
    
- <span data-ttu-id="cb66c-164">Grande distância física para o servidor</span><span class="sxs-lookup"><span data-stu-id="cb66c-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="cb66c-165">Um recurso que você pode aproveitar no SharePoint Online é a CDN da Microsoft (rede de distribuição de conteúdo).</span><span class="sxs-lookup"><span data-stu-id="cb66c-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="cb66c-166">Uma CDN é basicamente uma coleção distribuída de servidores implantados em vários datacenters.</span><span class="sxs-lookup"><span data-stu-id="cb66c-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="cb66c-167">Com uma CDN, o conteúdo nas páginas pode ser hospedado em um servidor próximo ao cliente, mesmo que o cliente esteja longe do servidor do SharePoint de origem.</span><span class="sxs-lookup"><span data-stu-id="cb66c-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="cb66c-168">A Microsoft usará isso mais no futuro para armazenar instâncias locais de páginas que não podem ser personalizadas, por exemplo, a Home Page de administração do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="cb66c-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="cb66c-169">Para obter mais informações sobre o CDNs, consulte [redes de distribuição de conteúdo](content-delivery-networks.md).</span><span class="sxs-lookup"><span data-stu-id="cb66c-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="cb66c-170">Algo que você precisa saber, mas talvez não seja possível fazer muito sobre a velocidade de conexão do seu provedor de Internet.</span><span class="sxs-lookup"><span data-stu-id="cb66c-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="cb66c-171">Uma ferramenta de teste de velocidade simples informará a velocidade da conexão.</span><span class="sxs-lookup"><span data-stu-id="cb66c-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="cb66c-172">Conexão do navegador</span><span class="sxs-lookup"><span data-stu-id="cb66c-172">Browser connection</span></span>

<span data-ttu-id="cb66c-173">Há alguns fatores que devem ser considerados nos navegadores da Web a partir de uma perspectiva de desempenho.</span><span class="sxs-lookup"><span data-stu-id="cb66c-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="cb66c-174">A visita a páginas complexas afetará o desempenho.</span><span class="sxs-lookup"><span data-stu-id="cb66c-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="cb66c-175">A maioria dos navegadores tem um pequeno cache (em torno de 90MB), enquanto a página da Web média é geralmente cerca de 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="cb66c-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="cb66c-176">Isso não demora muito para ser usado.</span><span class="sxs-lookup"><span data-stu-id="cb66c-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="cb66c-177">A largura de banda também pode ser um problema.</span><span class="sxs-lookup"><span data-stu-id="cb66c-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="cb66c-178">Por exemplo, se um usuário estiver assistindo a vídeos em outra sessão, isso afetará o desempenho da página do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cb66c-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="cb66c-179">Embora não seja possível impedir que os usuários enviem mídias, você pode controlar a forma como uma página será carregada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="cb66c-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="cb66c-180">Confira os seguintes artigos para diferentes técnicas de personalização de páginas do SharePoint Online e outras práticas recomendadas para ajudá-lo a obter o desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="cb66c-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="cb66c-181">Opções de navegação para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-182">Usar a ferramenta diagnóstico de página para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="cb66c-183">Otimização de imagem para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-184">Atraso no carregamento de imagens e JavaScript no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-185">Minificação e agrupamento no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-186">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="cb66c-187">Usando a Web Part de pesquisa de conteúdo em vez da Web Part de consulta de conteúdo para melhorar o desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="cb66c-188">Planejamento de capacidade e teste de carregamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-189">Diagnóstico de problemas de desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-190">Usando o cache de objetos com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="cb66c-191">Como evitar ficar limitado ou bloqueado no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cb66c-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

