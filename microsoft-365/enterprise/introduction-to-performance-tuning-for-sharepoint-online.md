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
description: Este artigo explica quais aspectos específicos você precisa considerar ao projetar páginas para melhorar o desempenho no SharePoint Online.
ms.openlocfilehash: d3a9dedbd5812774b81494af0f8defa5568f7dac
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687419"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="f637f-103">Introdução ao ajuste de desempenho para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="f637f-104">Este artigo explica quais aspectos específicos você precisa considerar ao projetar páginas para melhorar o desempenho no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f637f-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="f637f-105">Métricas do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-105">SharePoint Online metrics</span></span>

<span data-ttu-id="f637f-106">As seguintes métricas amplas do SharePoint Online fornecem dados reais sobre desempenho:</span><span class="sxs-lookup"><span data-stu-id="f637f-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="f637f-107">Como as páginas são carregadas rapidamente</span><span class="sxs-lookup"><span data-stu-id="f637f-107">How fast pages load</span></span>
    
- <span data-ttu-id="f637f-108">Quantas viagens de ida e volta são necessárias por página</span><span class="sxs-lookup"><span data-stu-id="f637f-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="f637f-109">Problemas com o serviço</span><span class="sxs-lookup"><span data-stu-id="f637f-109">Issues with the service</span></span>
    
- <span data-ttu-id="f637f-110">Outras coisas que causam degradação do desempenho</span><span class="sxs-lookup"><span data-stu-id="f637f-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="f637f-111">Conclusões alcançadas por causa dos dados</span><span class="sxs-lookup"><span data-stu-id="f637f-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="f637f-112">Os dados nos informam:</span><span class="sxs-lookup"><span data-stu-id="f637f-112">The data tells us:</span></span>
  
- <span data-ttu-id="f637f-113">A maioria das páginas tem um bom desempenho no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f637f-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="f637f-114">Páginas não personalizadas carregam muito rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f637f-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="f637f-115">O OneDrive for Business, os sites de equipe e as páginas do sistema, _layouts, etc., são carregados rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f637f-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="f637f-116">O 1% mais lento de páginas do SharePoint Online leva mais de 5.000 milissegundos para ser carregado.</span><span class="sxs-lookup"><span data-stu-id="f637f-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="f637f-117">Um teste de parâmetro de comparação simples que você pode usar seria medir o desempenho comparando o tempo de carregamento do seu próprio portal com o tempo de carregamento da home page do OneDrive for Business, pois ele usa poucos recursos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f637f-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="f637f-118">Essa geralmente será a primeira etapa que o Suporte solicitará que você conclua ao solucionar problemas de desempenho de rede.</span><span class="sxs-lookup"><span data-stu-id="f637f-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="f637f-119">Usar uma conta de usuário padrão ao verificar o desempenho</span><span class="sxs-lookup"><span data-stu-id="f637f-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="f637f-120">Um Administrador de Conjunto de Sites, Proprietário de Site, Editor ou Colaborador pertencem a grupos de segurança adicionais, têm permissões adicionais e, portanto, têm elementos adicionais que o SharePoint carrega em uma página.</span><span class="sxs-lookup"><span data-stu-id="f637f-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="f637f-121">Isso é aplicável ao SharePoint local e ao SharePoint Online, mas em um cenário local, as diferenças não serão notáveis tão facilmente quanto no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f637f-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="f637f-122">Para avaliar corretamente o desempenho de uma página para os usuários, você deve usar uma conta de usuário padrão para evitar carregar os controles de autoria e o tráfego adicional relacionado a grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="f637f-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="f637f-123">Categorias de conexão para ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="f637f-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="f637f-124">Você pode categorizar as conexões entre o servidor e o usuário em três componentes principais.</span><span class="sxs-lookup"><span data-stu-id="f637f-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="f637f-125">Considere-os ao projetar páginas do SharePoint Online para informações sobre tempos de carregamento.</span><span class="sxs-lookup"><span data-stu-id="f637f-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="f637f-126">**Servidor** Os servidores que a Microsoft hospeda em datacenters.</span><span class="sxs-lookup"><span data-stu-id="f637f-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="f637f-127">**Rede** A rede da Microsoft, a Internet e sua rede local entre o datacenter e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f637f-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="f637f-128">**Navegador** Onde a página é carregada.</span><span class="sxs-lookup"><span data-stu-id="f637f-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="f637f-129">Nessas três conexões, normalmente há cinco motivos que causam 95% de páginas lentas.</span><span class="sxs-lookup"><span data-stu-id="f637f-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="f637f-130">Cada um desses motivos é discutido neste artigo:</span><span class="sxs-lookup"><span data-stu-id="f637f-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="f637f-131">Problemas de navegação</span><span class="sxs-lookup"><span data-stu-id="f637f-131">Navigation issues</span></span>
    
- <span data-ttu-id="f637f-132">Roll up de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f637f-132">Content roll up</span></span>
    
- <span data-ttu-id="f637f-133">Arquivos grandes</span><span class="sxs-lookup"><span data-stu-id="f637f-133">Large files</span></span>
    
- <span data-ttu-id="f637f-134">Muitas solicitações para o servidor</span><span class="sxs-lookup"><span data-stu-id="f637f-134">Many requests to the server</span></span>
    
- <span data-ttu-id="f637f-135">Processamento de Web Part</span><span class="sxs-lookup"><span data-stu-id="f637f-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="f637f-136">Conexão do servidor</span><span class="sxs-lookup"><span data-stu-id="f637f-136">Server connection</span></span>

<span data-ttu-id="f637f-137">Muitos dos problemas que afetam o desempenho com o SharePoint local também se aplicam ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f637f-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="f637f-138">Como esperado, você tem muito mais controle sobre o desempenho dos servidores com o SharePoint local.</span><span class="sxs-lookup"><span data-stu-id="f637f-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="f637f-139">Com o SharePoint Online, as coisas são um pouco diferentes.</span><span class="sxs-lookup"><span data-stu-id="f637f-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="f637f-140">Quanto mais trabalho você faz um servidor, mais tempo leva para renderizar uma página.</span><span class="sxs-lookup"><span data-stu-id="f637f-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="f637f-141">Com o SharePoint, o maior responsável por esse aspecto são as páginas complexas com várias Web Parts.</span><span class="sxs-lookup"><span data-stu-id="f637f-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="f637f-142">SharePoint Server local</span><span class="sxs-lookup"><span data-stu-id="f637f-142">SharePoint Server on-premises</span></span>
  
![Captura de tela do servidor local](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="f637f-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-144">SharePoint Online</span></span>
  
![Captura de tela do servidor online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="f637f-146">Com o SharePoint Online, determinadas solicitações de página podem acabar chamando vários servidores.</span><span class="sxs-lookup"><span data-stu-id="f637f-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="f637f-147">Você pode acabar com uma matriz de solicitações entre servidores para uma solicitação individual.</span><span class="sxs-lookup"><span data-stu-id="f637f-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="f637f-148">Essas interações são caras de uma perspectiva de carregamento de página e tornarão as coisas lentas.</span><span class="sxs-lookup"><span data-stu-id="f637f-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="f637f-149">Exemplos dessas interações de servidor para servidor são:</span><span class="sxs-lookup"><span data-stu-id="f637f-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="f637f-150">Web para SQL Servers</span><span class="sxs-lookup"><span data-stu-id="f637f-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="f637f-151">Web para servidores de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f637f-151">Web to application servers</span></span>
    
<span data-ttu-id="f637f-152">A outra coisa que pode diminuir a velocidade das interações do servidor são erros de cache.</span><span class="sxs-lookup"><span data-stu-id="f637f-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="f637f-153">Ao contrário do SharePoint local, há uma chance muito grande de você atingir o mesmo servidor para uma página que você tenha visitado anteriormente; Isso torna o cache de objetos obsoleto.</span><span class="sxs-lookup"><span data-stu-id="f637f-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="f637f-154">Conexão de rede</span><span class="sxs-lookup"><span data-stu-id="f637f-154">Network connection</span></span>

<span data-ttu-id="f637f-155">Com o SharePoint local que não usa uma WAN, você pode usar uma conexão de alta velocidade entre o datacenter e os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f637f-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="f637f-156">Geralmente, as coisas são fáceis de gerenciar a partir de uma perspectiva de rede.</span><span class="sxs-lookup"><span data-stu-id="f637f-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="f637f-157">Com o SharePoint Online, há mais alguns fatores a considerar; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f637f-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="f637f-158">A rede da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f637f-158">The Microsoft network</span></span>
    
- <span data-ttu-id="f637f-159">A Internet</span><span class="sxs-lookup"><span data-stu-id="f637f-159">The Internet</span></span>
    
- <span data-ttu-id="f637f-160">O ISP</span><span class="sxs-lookup"><span data-stu-id="f637f-160">The ISP</span></span>
    
<span data-ttu-id="f637f-161">Independentemente da versão do SharePoint (e de qual rede) você está usando, as coisas que normalmente fazem a rede estar ocupada incluem:</span><span class="sxs-lookup"><span data-stu-id="f637f-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="f637f-162">Carga grande</span><span class="sxs-lookup"><span data-stu-id="f637f-162">Large payload</span></span>
    
- <span data-ttu-id="f637f-163">Muitos arquivos</span><span class="sxs-lookup"><span data-stu-id="f637f-163">Many files</span></span>
    
- <span data-ttu-id="f637f-164">Distância física grande até o servidor</span><span class="sxs-lookup"><span data-stu-id="f637f-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="f637f-165">Um recurso que você pode aproveitar no SharePoint Online é a CDN da Microsoft (Rede de Distribuição de Conteúdo).</span><span class="sxs-lookup"><span data-stu-id="f637f-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="f637f-166">Uma CDN é basicamente uma coleção distribuída de servidores implantados em vários datacenters.</span><span class="sxs-lookup"><span data-stu-id="f637f-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="f637f-167">Com uma CDN, o conteúdo nas páginas pode ser hospedado em um servidor próximo ao cliente mesmo se o cliente estiver longe do SharePoint Server originado.</span><span class="sxs-lookup"><span data-stu-id="f637f-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="f637f-168">A Microsoft estará usando isso mais no futuro para armazenar instâncias locais de páginas que não podem ser personalizadas, por exemplo, a home page do administrador do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f637f-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="f637f-169">Para obter mais informações sobre CDNs, consulte [Redes de distribuição de conteúdo.](content-delivery-networks.md)</span><span class="sxs-lookup"><span data-stu-id="f637f-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="f637f-170">Algo que você precisa estar ciente, mas pode não ser capaz de fazer muito sobre a velocidade de conexão do seu ISP.</span><span class="sxs-lookup"><span data-stu-id="f637f-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="f637f-171">Uma ferramenta de teste de velocidade simples dirá a velocidade da conexão.</span><span class="sxs-lookup"><span data-stu-id="f637f-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="f637f-172">Conexão do navegador</span><span class="sxs-lookup"><span data-stu-id="f637f-172">Browser connection</span></span>

<span data-ttu-id="f637f-173">Há alguns fatores a considerar com os navegadores da Web de uma perspectiva de desempenho.</span><span class="sxs-lookup"><span data-stu-id="f637f-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="f637f-174">A visita a páginas complexas afetará o desempenho.</span><span class="sxs-lookup"><span data-stu-id="f637f-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="f637f-175">A maioria dos navegadores tem apenas um pequeno cache (cerca de 90 MB), enquanto a página da Web média é geralmente de cerca de 1,6 MB.</span><span class="sxs-lookup"><span data-stu-id="f637f-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="f637f-176">Isso não leva muito tempo para ser usado.</span><span class="sxs-lookup"><span data-stu-id="f637f-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="f637f-177">A largura de banda também pode ser um problema.</span><span class="sxs-lookup"><span data-stu-id="f637f-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="f637f-178">Por exemplo, se um usuário estiver assistindo a vídeos em outra sessão, isso afetará o desempenho da sua página do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f637f-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="f637f-179">Embora você não possa impedir que os usuários streaming de mídia, você pode controlar a maneira como uma página será carregada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="f637f-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="f637f-180">Confira os artigos a seguir para obter diferentes técnicas de personalização de página do SharePoint Online e outras práticas recomendadas para ajudá-lo a obter o desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="f637f-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="f637f-181">Opções de navegação para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-182">Usar a ferramenta Diagnóstico de Página para SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="f637f-183">Otimização de imagem para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-184">Atraso no carregamento de imagens e JavaScript no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-185">Minificação e agrupamento no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-186">Usar a Rede de Distribuição de Conteúdo (CDN) do Office 365 com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="f637f-187">Usar a Web Part de Pesquisa de Conteúdo em vez de Web Part de Consulta de Conteúdo para melhorar o desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="f637f-188">Planejamento de capacidade e teste de carregamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-189">Diagnóstico de problemas de desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-190">Usando o cache de objetos com o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="f637f-191">Como evitar ficar limitado ou bloqueado no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f637f-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](https://msdn.microsoft.com/library/office/dn889829.aspx)
    

