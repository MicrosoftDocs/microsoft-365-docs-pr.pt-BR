---
title: Configurar a pesquisa do Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Saiba como configurar a pesquisa em um ambiente multi-geo. Somente alguns clientes, como OneDrive for Business, podem retornar resultados em um ambiente multi-geo.
ms.openlocfilehash: 31e0c4ae3fe73f2f6e113dbc38989726eb1ca590
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022325"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a><span data-ttu-id="ec6bf-104">Configurar a Pesquisa do Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="ec6bf-104">Configure Search for Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="ec6bf-105">Em um ambiente multigeográfico, cada localização geográfica tem seu próprio índice de pesquisa e Centro de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-105">In a multi-geo environment, each geo location has its own search index and Search Center.</span></span> <span data-ttu-id="ec6bf-106">Quando um usuário pesquisa, é realizado o fan out para todos os índices e os resultados retornados são mesclados.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-106">When a user searches, the query is fanned out to all the indexes, and the returned results are merged.</span></span>

<span data-ttu-id="ec6bf-107">Por exemplo, um usuário em uma localização geográfica pode pesquisar por um conteúdo armazenado em outra localização geográfica ou por um conteúdo em um site do SharePoint restrito a uma localização geográfica diferente.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-107">For example, a user in one geo location can search for content stored in another geo location, or for content on a SharePoint site that's restricted to a different geo location.</span></span> <span data-ttu-id="ec6bf-108">Se o usuário tiver acesso a esse conteúdo, a pesquisa mostrará o resultado.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-108">If the user has access to this content, search will show the result.</span></span>

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a><span data-ttu-id="ec6bf-109">Quais clientes de pesquisa funcionam em um ambiente multigeográfico?</span><span class="sxs-lookup"><span data-stu-id="ec6bf-109">Which search clients work in a multi-geo environment?</span></span>

<span data-ttu-id="ec6bf-110">Esses clientes podem retornar resultados de todas as localizações geográficas:</span><span class="sxs-lookup"><span data-stu-id="ec6bf-110">These clients can return results from all geo locations:</span></span>

- <span data-ttu-id="ec6bf-111">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ec6bf-111">OneDrive for Business</span></span>
- <span data-ttu-id="ec6bf-112">Delve</span><span class="sxs-lookup"><span data-stu-id="ec6bf-112">Delve</span></span>
- <span data-ttu-id="ec6bf-113">A home page do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ec6bf-113">The SharePoint home page</span></span>
- <span data-ttu-id="ec6bf-114">O Centro de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="ec6bf-114">The Search Center</span></span>
- <span data-ttu-id="ec6bf-115">Aplicativos de pesquisa personalizada que usam a API de pesquisa do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ec6bf-115">Custom search applications that use the SharePoint Search API</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="ec6bf-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="ec6bf-116">OneDrive for Business</span></span>

<span data-ttu-id="ec6bf-117">Assim que o ambiente multigeográfico for configurado, os usuários que pesquisam no OneDrive obtêm resultados de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-117">As soon as the multi-geo environment has been set up, users that search in OneDrive get results from all geo locations.</span></span>

### <a name="delve"></a><span data-ttu-id="ec6bf-118">Delve</span><span class="sxs-lookup"><span data-stu-id="ec6bf-118">Delve</span></span>

<span data-ttu-id="ec6bf-119">Assim que o ambiente multigeográfico for configurado, os usuários que pesquisam no Delve obtêm resultados de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-119">As soon as the multi-geo environment has been set up, users that search in Delve get results from all geo locations.</span></span>

<span data-ttu-id="ec6bf-p104">O feed do Delve e o cartão de perfil mostram apenas as visualizações de arquivos armazenados no local central. Para os arquivos armazenados em localizações satélites, é mostrado o ícone para o tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p104">The Delve feed and the profile card only show previews of files that are stored in the central location. For files that are stored in satellite locations, the icon for the file type is shown instead.</span></span>

### <a name="the-sharepoint-home-page"></a><span data-ttu-id="ec6bf-122">A home page do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ec6bf-122">The SharePoint home page</span></span>

<span data-ttu-id="ec6bf-p105">Assim que o ambiente multigeográfico for configurado, os usuários verão notícias, sites recentes e seguidos a partir de várias localizações geográficas na home page do SharePoint. Se eles usarem a caixa de pesquisa na home page do SharePoint, receberão resultados mesclados de várias localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p105">As soon as the multi-geo environment has been set up, users will see news, recent and followed sites from multiple geo locations on their SharePoint home page. If they use the search box on the SharePoint home page, they'll get merged results from multiple geo locations.</span></span>

### <a name="the-search-center"></a><span data-ttu-id="ec6bf-125">O Centro de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="ec6bf-125">The Search Center</span></span>

<span data-ttu-id="ec6bf-p106">Após a configuração do ambiente multigeográfico, cada Centro de Pesquisa continua mostrando apenas os resultados da própria localização geográfica. Os administradores devem [alterar as configurações de cada Centro de Pesquisa](#_Set_up_a_1) para obter resultados de todas as localizações geográficas. Posteriormente, os usuários que pesquisarem no Centro de Pesquisa obterão resultados de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p106">After the multi-geo environment has been set up, each Search Center continues to only show results from their own geo location. Admins must [change the settings of each Search Center](#_Set_up_a_1) to get results from all geo locations. Afterwards, users that search in the Search Center get results from all geo locations.</span></span>

### <a name="custom-search-applications"></a><span data-ttu-id="ec6bf-129">Aplicativos de pesquisa personalizada</span><span class="sxs-lookup"><span data-stu-id="ec6bf-129">Custom search applications</span></span>

<span data-ttu-id="ec6bf-p107">Como de costume, os aplicativos de pesquisa personalizada interagem com os índices de pesquisa usando as APIs REST existentes da Pesquisa do SharePoint. Para obter resultados de todas ou de algumas localizações geográficas, o aplicativo deve [ligar para a API e incluir os novos parâmetros de consulta multigeográfica](#_Get_custom_search) na solicitação. Isso dispara um fan-out da consulta para todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p107">As usual, custom search applications interact with the search indexes by using the existing SharePoint Search REST APIs. To get results from all, or some geo locations, the application must [call the API and include the new Multi-Geo query parameters](#_Get_custom_search) in the request. This triggers a fan out of the query to all geo locations.</span></span>

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a><span data-ttu-id="ec6bf-133">O que a pesquisa em um ambiente multigeográfico tem de diferente?</span><span class="sxs-lookup"><span data-stu-id="ec6bf-133">What's different about search in a multi-geo environment?</span></span>

<span data-ttu-id="ec6bf-134">Alguns recursos de pesquisa que talvez você conheça funcionam diferente em um ambiente multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-134">Some search features you might be familiar with, work differently in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec6bf-135"><strong>Recurso</strong></span><span class="sxs-lookup"><span data-stu-id="ec6bf-135"><strong>Feature</strong></span></span></th>
<th align="left"><span data-ttu-id="ec6bf-136"><strong>Como funciona</strong></span><span class="sxs-lookup"><span data-stu-id="ec6bf-136"><strong>How it works</strong></span></span></th>
<th align="left"><span data-ttu-id="ec6bf-137"><strong>Solução alternativa</strong></span><span class="sxs-lookup"><span data-stu-id="ec6bf-137"><strong>Workaround</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-138">Resultados promovidos</span><span class="sxs-lookup"><span data-stu-id="ec6bf-138">Promoted results</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-139">Você pode criar regras de consulta com nos resultados promovidos em diferentes níveis: do locatário inteiro, um conjunto de sites ou um site.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-139">You can create query rules with promoted results at different levels: for the whole tenant, for a site collection, or for a site.</span></span> <span data-ttu-id="ec6bf-140">Em um ambiente multigeográfico, definir resultados promovidos no nível do locatário para promover os resultados para os Centros de Pesquisa em todos as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-140">In a multi-geo environment, define promoted results at the tenant level to promote the results to the Search Centers in all geo locations.</span></span> <span data-ttu-id="ec6bf-141">Se você deseja promover resultados no Centro de pesquisa que está na localização geográfica do conjunto de sites ou site, defina os resultados promovidos no nível do site ou conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-141">If you only want to promote results in the Search Center that's in the geo location of the site collection or site, define the promoted results at the site collection or site level.</span></span> <span data-ttu-id="ec6bf-142">Esses resultados não são promovidos em outras localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-142">These results are not promoted in other geo locations.</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-143">Se você não precisar de diferentes resultados promovidos por localização geográfica, como diferentes regras de viagens, recomendamos definir resultados promovidos no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-143">If you don't need different promoted results per geo location, for example different rules for traveling, we recommend defining promoted results at the tenant level.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-144">Refinadores de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ec6bf-144">Search refiners</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-p109">A pesquisa retorna refinadores de todas as localizações geográficas de um locatário e os agrega. A agregação é um esforço dentro do melhor possível, quer dizer, as contagens de refinador podem não estar 100% corretas. Para a maioria dos cenários orientados por pesquisa, esse nível e precisão é suficiente. </span><span class="sxs-lookup"><span data-stu-id="ec6bf-p109">Search returns refiners from all the geo locations of a tenant and then aggregates them. The aggregation is a best effort, meaning that the refiner counts might not be 100% accurate. For most search-driven scenarios, this accuracy is sufficient. </span></span></td>
<td align="left"><span data-ttu-id="ec6bf-148">Para os aplicativos orientados por pesquisa que dependem da integridade do refinador, consulte cada localização geográfica individualmente.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-148">For search-driven applications that depend on refiner completeness, query each geo location independently.</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><span data-ttu-id="ec6bf-149">A pesquisa multigeográfica não dá suporte a bucketing dinâmico para refinadores numéricos.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-149">Multi-geo search doesn't support dynamic bucketing for numerical refiners.</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-150">Use o <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">parâmetro "Discretize"</a> para refinadores numéricos.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-150">Use the <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">"Discretize" parameter</a> for numerical refiners.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-151">IDs do documento</span><span class="sxs-lookup"><span data-stu-id="ec6bf-151">Document IDs</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-152">Se você estiver desenvolvendo um aplicativo orientado por pesquisa que depende de IDs de documento, observe que as IDs de documento em um ambiente multigeográfico não são exclusivas entre localizações geográficas, elas são exclusivas por localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-152">If you're developing a search-driven application that depends on document IDs, note that document IDs in a multi-geo environment aren't unique across geo locations, they are unique per geo location.</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-153">Adicionar uma coluna que identifique a localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-153">We've added a column that identifies the geo location.</span></span> <span data-ttu-id="ec6bf-154">Use essa coluna para ter exclusividade.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-154">Use this column to achieve uniqueness.</span></span> <span data-ttu-id="ec6bf-155">Esta coluna é chamada "GeoLocationSource".</span><span class="sxs-lookup"><span data-stu-id="ec6bf-155">This column is named "GeoLocationSource".</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-156">Número de resultados</span><span class="sxs-lookup"><span data-stu-id="ec6bf-156">Number of results</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-157">A página de resultados de pesquisa mostra os resultados combinados das localizações geográficas, mas não é possível paginar mais de 500 resultados.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-157">The search results page shows combined results from the geo locations, but it's not possible to page beyond 500 results.</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-158">Pesquisa híbrida</span><span class="sxs-lookup"><span data-stu-id="ec6bf-158">Hybrid search</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-159">Em um ambiente do SharePoint híbrido com <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">pesquisa híbrida de nuvem</a>, o conteúdo local é adicionado ao índice do Microsoft 365 da localização central.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-159">In a hybrid SharePoint environment with <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">cloud hybrid search</a>,  on-premises content is added to the Microsoft 365 index of the central location.</span></span></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a><span data-ttu-id="ec6bf-160">O que a pesquisa em um ambiente multigeográfico não suporta?</span><span class="sxs-lookup"><span data-stu-id="ec6bf-160">What's not supported for search in a multi-geo environment?</span></span>

<span data-ttu-id="ec6bf-161">Alguns dos recursos de pesquisa que talvez você conheça não são suportados em um ambiente multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-161">Some of the search features you might be familiar with, aren't supported in a multi-geo environment.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec6bf-162"><strong>Recurso de pesquisa</strong></span><span class="sxs-lookup"><span data-stu-id="ec6bf-162"><strong>Search feature</strong></span></span></th>
<th align="left"><span data-ttu-id="ec6bf-163"><strong>Observação</strong></span><span class="sxs-lookup"><span data-stu-id="ec6bf-163"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-164">Autenticação somente aplicativo</span><span class="sxs-lookup"><span data-stu-id="ec6bf-164">App-only authentication</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-165">A autenticação somente de aplicativos (acesso privilegiado dos serviços) não tem suporte na pesquisa multigeográfica.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-165">App-only authentication (privileged access from services) isn't supported in multi-geo search.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-166">Usuários convidados</span><span class="sxs-lookup"><span data-stu-id="ec6bf-166">Guest users</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-167">Os usuários convidados só obtêm resultados da localização geográfica da qual estão pesquisando.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-167">Guest users only get results from the geo location that they're searching from.</span></span></td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a><span data-ttu-id="ec6bf-168">Como a pesquisa funciona em um ambiente multigeográfico?</span><span class="sxs-lookup"><span data-stu-id="ec6bf-168">How does search work in a multi-geo environment?</span></span>

<span data-ttu-id="ec6bf-169">Todos os clientes de pesquisa usam as APIs REST de Pesquisa existentes do SharePoint para interagir com os índices de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-169">All the search clients use the existing SharePoint Search REST APIs to interact with the search indexes.</span></span>

![Diagrama mostrando como SharePoint APIs REST de Pesquisa interagem com os índices de pesquisa](../media/configure-search-for-multi-geo-image1-1.png)

1. <span data-ttu-id="ec6bf-171">Um cliente pesquisa chama o ponto de extremidade da API REST com a propriedade de consulta EnableMultiGeoSearch= true.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-171">A search client calls the Search REST endpoint with the query property EnableMultiGeoSearch= true.</span></span>
2. <span data-ttu-id="ec6bf-172">A consulta é enviada a todas as localizações geográficas no locatário.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-172">The query is sent to all geo locations in the tenant.</span></span>
3. <span data-ttu-id="ec6bf-173">Os resultados de pesquisa de cada localização geográfica são mesclados e classificados.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-173">Search results from each geo location are merged and ranked.</span></span>
4. <span data-ttu-id="ec6bf-174">O cliente obtém resultados de pesquisa unificados.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-174">The client gets unified search results.</span></span>

<span data-ttu-id="ec6bf-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Observe que não mesclamos os resultados da pesquisa até recebemos resultados de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-175"><span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Notice that we don't merge the search results until we've received results from all the geo locations.</span></span> <span data-ttu-id="ec6bf-176">Isso significa que pesquisas multigeográficas têm latência adicional comparadas com pesquisas em um ambiente com localização geográfica única.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-176">This means that multi-geo searches have additional latency compared to searches in an environment with only one geo location.</span></span>

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a><span data-ttu-id="ec6bf-177">Obter um centro de pesquisa para mostrar resultados de todas as localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-177">Get a Search Center to show results from all geo locations</span></span>

<span data-ttu-id="ec6bf-178">Cada centro de pesquisa tem vários verticais e você precisará configurar cada vertical individualmente.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-178">Each Search Center has several verticals and you have to set up each vertical individually.</span></span>

1. <span data-ttu-id="ec6bf-179">Certifique-se de executar essas etapas com uma conta que tenha permissão para editar a página de resultados de pesquisa e a Web Part de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-179">Ensure that you perform these steps with an account that has permission to edit the search results page and the Search Result Web Part.</span></span>

2. <span data-ttu-id="ec6bf-180">Navegue até a página de resultados de pesquisa (confira a [lista](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) das páginas de resultados de pesquisa)</span><span class="sxs-lookup"><span data-stu-id="ec6bf-180">Navigate to the search results page (see the [list](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) of search results pages)</span></span>

3. <span data-ttu-id="ec6bf-p112">Selecione o eixo vertical a configurar, clique no ícone de engrenagem **Configurações** no canto superior direito e, em seguida, clique em **Editar página**. A página de resultados de pesquisa abre no modo de edição.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p112">Select the vertical to set up, click **Settings** gear icon in the upper, right corner, and then click **Edit Page**. The search results page opens in Edit mode.</span></span>

   ![Editar seleção de página em Configurações](../media/configure-search-for-multi-geo-image2.png)

4. <span data-ttu-id="ec6bf-184">Na Web Part de Resultados de Pesquisa, mova o ponteiro para o canto superior direito da web part, clique na seta e, em seguida, clique em **Editar Web Part** no menu.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-184">In the Search Results Web Part, move the pointer to the upper, right corner of the web part, click the arrow, and then click **Edit Web Part** on the menu.</span></span> <span data-ttu-id="ec6bf-185">O painel de ferramentas da Web Part de Resultados de Pesquisa é aberto na faixa de opções no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-185">The Search Results Web Part tool pane opens under the ribbon in the top right of the page.</span></span>

   ![Editar seleção de Web Part](../media/configure-search-for-multi-geo-image3.png)

5. <span data-ttu-id="ec6bf-187">No painel de ferramentas da Web Part, na seção **Configurações**, em **Configurações de controle de resultados**, marque **Mostrar resultados multigeográficos** para obter a Web Part de resultados de pesquisa para mostrar resultados de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-187">In the Web Part tool pane, in the **Settings** section, under **Results control settings**, select **Show Multi-Geo results** to get the Search Results Web Part to show results from all geo locations.</span></span>

6. <span data-ttu-id="ec6bf-188">Clique em **OK** para salvar as alterações e fechar o painel de ferramentas da Web Part.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-188">Click **OK** to save your change and close the Web Part tool pane.</span></span>

7. <span data-ttu-id="ec6bf-189">Verifique as suas alterações na Web Part de resultados da pesquisa clicando em **Check-In** na guia Página do menu principal.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-189">Check your changes to the Search Results Web Part by clicking **Check-In** on the Page tab of the main menu.</span></span>

8. <span data-ttu-id="ec6bf-190">Publique as alterações usando o link fornecido na observação na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-190">Publish the changes by using the link provided in the note at the top of the page.</span></span>

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a><span data-ttu-id="ec6bf-191">Obter aplicativos de pesquisa personalizada para mostrar resultados de todas ou algumas localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-191">Get custom search applications to show results from all or some geo locations</span></span>

<span data-ttu-id="ec6bf-p114">Os aplicativos de pesquisa personalizada obtêm resultados de todas ou algumas localizações geográficas, especificando-se os parâmetros de consulta com a solicitação para a API REST de pesquisa do SharePoint. Dependendo dos parâmetros de consulta, realiza-se fan-out da consulta para todas ou algumas localizações geográficas. Por exemplo, se você apenas precisar consultar um subconjunto de localizações geográficas para encontrar informações relevantes, você pode controlar o fan-out apenas de acordo com elas. Se a solicitação for concluída, a API REST de pesquisa do SharePoint retorna dados de resposta.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p114">Custom search applications get results from all, or some, geo locations by specifying query parameters with the request to the SharePoint Search REST API. Depending on the query parameters, the query is fanned out to all geo locations, or to some geo locations. For example, if you only need to query a subset of geo locations to find relevant information, you can control the fan out to only these. If the request succeeds, the SharePoint Search REST API returns response data.</span></span>

### <a name="requirement"></a><span data-ttu-id="ec6bf-196">Requisito</span><span class="sxs-lookup"><span data-stu-id="ec6bf-196">Requirement</span></span>

<span data-ttu-id="ec6bf-p115">Para cada local geográfico, certifique-se de que todos os usuários na organização tiverem o nível de permissão **ler** do site raiz (por exemplo, contoso **APAC**.sharepoint.com/ e a contoso **EU**.sharepoint.com/). [Saiba mais sobre permissões](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p115">For each geo location, you must ensure that all users in the organization have been granted the **Read** permission level for the root website (for example contoso **APAC**.sharepoint.com/ and contoso **EU**.sharepoint.com/). [Learn about permissions](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).</span></span>

### <a name="query-parameters"></a><span data-ttu-id="ec6bf-199">Parâmetros de consulta</span><span class="sxs-lookup"><span data-stu-id="ec6bf-199">Query parameters</span></span>

<span data-ttu-id="ec6bf-200">EnableMultiGeoSearch, isso é um valor Booleano que especifica se o fan ou deve ser realizado para os índices das outras localizações geográficas do locatário multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-200">EnableMultiGeoSearch - This is a Boolean value that specifies whether the query shall be fanned out to the indexes of other geo locations of the multi-geo tenant.</span></span> <span data-ttu-id="ec6bf-201">Definido como **verdadeiro** para realizar o fan out da consulta. **falso** para não realizar o fan out da consulta.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-201">Set it to **true** to fan out the query; **false** to not fan out the query.</span></span> <span data-ttu-id="ec6bf-202">Se você não incluir esse parâmetro, o valor padrão será **falso**, exceto ao fazer uma chamada da API REST em um site que use o modelo do Centro de Pesquisa Corporativo; nesse caso, o valor padrão será **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-202">If you don't include this parameter, the default value is **false**, except when making a REST API call against a site which uses the Enterprise Search Center template, in this case the default value is **true**.</span></span> <span data-ttu-id="ec6bf-203">Se você usa o parâmetro em um ambiente que não é multigeográfico, o parâmetro será ignorado.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-203">If you use the parameter in an environment that isn't multi-geo, the parameter is ignored.</span></span>

<span data-ttu-id="ec6bf-204">ClientType - Isso é uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-204">ClientType - This is a string.</span></span> <span data-ttu-id="ec6bf-205">Insira um nome exclusivo do cliente para cada aplicativo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-205">Enter a unique client name for each search application.</span></span> <span data-ttu-id="ec6bf-206">Se esse parâmetro não for incluído, o fan out da consulta não é feito em outra localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-206">If you don't include this parameter, the query is not fanned out to other geo locations.</span></span>

<span data-ttu-id="ec6bf-207">MultiGeoSearchConfiguration - Isso é uma lista opcional de localizações geográficas filiais em um locatário multigeográfico para realizar o fan out da consulta quando **EnableMultiGeoSearch** for **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-207">MultiGeoSearchConfiguration - This is an optional list of which geo locations in the multi-geo tenant to fan the query out to when **EnableMultiGeoSearch** is **true**.</span></span> <span data-ttu-id="ec6bf-208">Se você não incluir este parâmetro ou deixar em branco, o fan out da consulta é feito para todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-208">If you don't include this parameter, or leave it blank, the query is fanned out to all geo locations.</span></span> <span data-ttu-id="ec6bf-209">Para cada localização geográfica, insira os seguintes itens no formato JSON:</span><span class="sxs-lookup"><span data-stu-id="ec6bf-209">For each geo location, enter the following items, in JSON format:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec6bf-210">Item</span><span class="sxs-lookup"><span data-stu-id="ec6bf-210">Item</span></span></th>
<th align="left"><span data-ttu-id="ec6bf-211">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec6bf-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-212">DataLocation</span><span class="sxs-lookup"><span data-stu-id="ec6bf-212">DataLocation</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-213">Localização geográfica, por exemplo, NAM.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-213">The geo location, for example NAM.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-214">EndPoint</span><span class="sxs-lookup"><span data-stu-id="ec6bf-214">EndPoint</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-215">O ponto de extremidade ao qual se conectar, por exemplo, https://contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="ec6bf-215">The endpoint to connect to, for example https://contoso.sharepoint.com</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-216">SourceId</span><span class="sxs-lookup"><span data-stu-id="ec6bf-216">SourceId</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-217">O GUID da fonte de resultados, por exemplo, B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-217">The GUID of the result source, for example B81EAB55-3140-4312-B0F4-9459D1B4FFEE.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="ec6bf-p119">Se você omitir DataLocation ou EndPoint ou se um DataLocation estiver duplicado, a solicitação falhará. [Você pode obter informações sobre o ponto de extremidade das localizações geográficas de um locatário usando o Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p119">If you omit DataLocation or EndPoint, or if a DataLocation is duplicated, the request fails. [You can get information about the endpoint of a tenant's geo locations by using Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery).</span></span>

### <a name="response-data"></a><span data-ttu-id="ec6bf-220">Dado de resposta</span><span class="sxs-lookup"><span data-stu-id="ec6bf-220">Response data</span></span>

<span data-ttu-id="ec6bf-p120">MultiGeoSearchStatus – Isso é uma propriedade que a API de pesquisa do SharePoint retorna em resposta a uma solicitação. O valor da propriedade é uma cadeia de caracteres e fornece as seguintes informações sobre os resultados que a API de pesquisa do SharePoint retorna:</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p120">MultiGeoSearchStatus – This is a property that the SharePoint Search API returns in response to a request. The value of the property is a string and gives the following information about the results that the SharePoint Search API returns:</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec6bf-223">Valor</span><span class="sxs-lookup"><span data-stu-id="ec6bf-223">Value</span></span></th>
<th align="left"><span data-ttu-id="ec6bf-224">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec6bf-224">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-225">Completo</span><span class="sxs-lookup"><span data-stu-id="ec6bf-225">Full</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-226">Total de resultados de <strong>todas</strong> as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-226">Full results from <strong>all</strong> the geo locations.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="ec6bf-227">Parcial</span><span class="sxs-lookup"><span data-stu-id="ec6bf-227">Partial</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-p121">Os resultados parciais de uma ou mais localizações geográficas. Os resultados são incompletos devido a um erro transitório.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p121">Partial results from one or more geo locations. The results are incomplete due to a transient error.</span></span></td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a><span data-ttu-id="ec6bf-230">Consulta usando o serviço REST</span><span class="sxs-lookup"><span data-stu-id="ec6bf-230">Query using the REST service</span></span>

<span data-ttu-id="ec6bf-p122">Com uma solicitação GET, você especifica os parâmetros da consulta na URL. Com uma solicitação POST, você passa os parâmetros de consulta no corpo no formato JavaScript Object Notation (JSON).</span><span class="sxs-lookup"><span data-stu-id="ec6bf-p122">With a GET request, you specify the query parameters in the URL. With a POST request, you pass the query parameters in the body in JavaScript Object Notation (JSON) format.</span></span>

#### <a name="request-headers"></a><span data-ttu-id="ec6bf-233">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ec6bf-233">Request headers</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ec6bf-234">Nome</span><span class="sxs-lookup"><span data-stu-id="ec6bf-234">Name</span></span></th>
<th align="left"><span data-ttu-id="ec6bf-235">Valor</span><span class="sxs-lookup"><span data-stu-id="ec6bf-235">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="ec6bf-236">Content-Type</span><span class="sxs-lookup"><span data-stu-id="ec6bf-236">Content-Type</span></span></td>
<td align="left"><span data-ttu-id="ec6bf-237">application/json;odata=verbose</span><span class="sxs-lookup"><span data-stu-id="ec6bf-237">application/json;odata=verbose</span></span></td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="ec6bf-238">Exemplo de solicitação GET da qual se realiza fan-out para **todas** as localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-238">Sample GET request that's fanned out to **all** geo locations</span></span>

<span data-ttu-id="ec6bf-239"> https:// \<tenant\> / \_ api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my \_ \_ client id'</span><span class="sxs-lookup"><span data-stu-id="ec6bf-239">https:// \<tenant\>/\_api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my\_client\_id'</span></span>

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a><span data-ttu-id="ec6bf-240">Exemplo de solicitação GET da qual realizar fan-out para **algumas** localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-240">Sample GET request to fan out to **some** geo locations</span></span>

<span data-ttu-id="ec6bf-241"> https:// \<tenant\> / \_ api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation \\ :"NAM" \\ ,Endpoint \\ :"https \\ ://contosoNAM.sharepoint.com" \\ ,SourceId \\ :"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ ,{DataLocation \\ :"CAN" \\ ,Endpoint \\ :"https \\ ://contosoCAN.sharepoint-df.com"}]'</span><span class="sxs-lookup"><span data-stu-id="ec6bf-241">https:// \<tenant\>/\_api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation\\:"NAM"\\,Endpoint\\:"https\\://contosoNAM.sharepoint.com"\\,SourceId\\:"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"}\\,{DataLocation\\:"CAN"\\,Endpoint\\:"https\\://contosoCAN.sharepoint-df.com"}]'</span></span>

> [!NOTE]
> <span data-ttu-id="ec6bf-242">Vírgulas e dois-pontos na lista de localizações geográficas para a propriedade MultiGeoSearchConfiguration são precedidas pelo caractere **barra invertida**.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-242">Commas and colons in the list of geo locations for the MultiGeoSearchConfiguration property are preceded by the **backslash** character.</span></span> <span data-ttu-id="ec6bf-243">Isso ocorre porque solicitações GET usam dois-pontos para separar propriedades e vírgulas para separar os argumentos das propriedades.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-243">This is because GET requests use colons to separate properties and commas to separate arguments of properties.</span></span> <span data-ttu-id="ec6bf-244">Sem uma barra invertida como um caractere de escape, a propriedade MultiGeoSearchConfiguration será interpretada incorretamente.</span><span class="sxs-lookup"><span data-stu-id="ec6bf-244">Without the backslash as an escape character, the MultiGeoSearchConfiguration property is interpreted wrongly.</span></span>

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a><span data-ttu-id="ec6bf-245">Exemplo de solicitação POST da qual se realiza fan-out para **todas** as localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-245">Sample POST request that's fanned out to **all** geo locations</span></span>

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a><span data-ttu-id="ec6bf-246">Exemplo de solicitação POST da qual se realiza fan-out para **algumas** localizações geográficas</span><span class="sxs-lookup"><span data-stu-id="ec6bf-246">Sample POST request that's fanned out to **some** geo locations</span></span>

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a><span data-ttu-id="ec6bf-247">Consulta usando o CSOM</span><span class="sxs-lookup"><span data-stu-id="ec6bf-247">Query using CSOM</span></span>

<span data-ttu-id="ec6bf-248">Vejamos um exemplo de consulta CSOM da qual se faz fan-out para **todas** as localizações geográficas:</span><span class="sxs-lookup"><span data-stu-id="ec6bf-248">Here's a sample CSOM query that's fanned out to **all** geo locations:</span></span>

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery.Properties["EnableMultiGeoSearch"] = true;
```
