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
description: Este artigo mostra como diagnosticar problemas comuns com seu site do SharePoint Online usando ferramentas de desenvolvedor do Internet Explorer.
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927607"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="ac1f3-103">Diagnosticando problemas de desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ac1f3-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="ac1f3-104">Este artigo mostra como diagnosticar problemas comuns com seu site do SharePoint Online usando ferramentas de desenvolvedor do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="ac1f3-105">Há três maneiras diferentes de identificar que uma página em um site do SharePoint Online tem um problema de desempenho com as personalizações.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="ac1f3-106">O monitor de rede da barra de ferramentas F12</span><span class="sxs-lookup"><span data-stu-id="ac1f3-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="ac1f3-107">Comparação com uma linha de base não personalizada</span><span class="sxs-lookup"><span data-stu-id="ac1f3-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="ac1f3-108">Métricas de header de resposta do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ac1f3-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="ac1f3-109">Este tópico descreve como usar cada um desses métodos para diagnosticar problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="ac1f3-110">Depois de descobrir a causa do problema, você pode trabalhar em direção a uma solução usando os artigos sobre como melhorar o desempenho do SharePoint que você pode encontrar em https://aka.ms/tune .</span><span class="sxs-lookup"><span data-stu-id="ac1f3-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="ac1f3-111">Usar a barra de ferramentas F12 para diagnosticar o desempenho no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ac1f3-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="ac1f3-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ac1f3-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ac1f3-113">Neste artigo, usamos o Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="ac1f3-114">As versões das ferramentas de desenvolvedor F12 em outros navegadores têm recursos semelhantes, embora possam parecer um pouco diferentes.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="ac1f3-115">Para obter informações sobre as ferramentas de desenvolvedor F12, consulte:</span><span class="sxs-lookup"><span data-stu-id="ac1f3-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="ac1f3-116">[Novidades nas Ferramentas F12](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ac1f3-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="ac1f3-117">[Usando as ferramentas de desenvolvedor F12](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ac1f3-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="ac1f3-118">Para levantar as ferramentas de desenvolvedor, pressione **F12** e clique no ícone Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="ac1f3-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![Captura de tela de ícone de Wi-Fi de ferramentas de desenvolvedor F12](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="ac1f3-120">Na guia **Rede,** pressione o botão de reprodução verde para carregar uma página.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="ac1f3-121">A ferramenta retorna todos os arquivos que o navegador solicita para obter a página que você solicitou.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="ac1f3-122">A captura de tela a seguir mostra uma lista dessas.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-122">The following screen shot shows one such list.</span></span>
  
![Captura de tela da lista de arquivos retornados com uma solicitação de página.](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="ac1f3-124">Você também pode ver os horários de download dos arquivos no lado direito, conforme mostrado nesta captura de tela.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![Diagrama mostrando o tempo de carregamento das páginas solicitadas do SharePoint](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="ac1f3-126">Isso oferece uma representação visual de quanto tempo o arquivo levou para carregar.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="ac1f3-127">A linha verde representa quando a página está pronta para ser renderizada pelo navegador.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="ac1f3-128">Isso pode lhe dar uma visão rápida dos diferentes arquivos que podem estar causando cargas lentas de página em seu site.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="ac1f3-129">Configurando uma linha de base não personalizada para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ac1f3-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="ac1f3-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ac1f3-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ac1f3-131">A melhor maneira de determinar os pontos fracos de desempenho do seu site é configurar um conjunto de sites totalmente pronto para uso no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="ac1f3-132">Dessa forma, você pode comparar todos os vários aspectos do seu site com o que você obteria sem personalização na página.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="ac1f3-133">A home page do OneDrive for Business é um bom exemplo de um conjunto de sites separado que é improvável ter qualquer personalização.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="ac1f3-134">Exibindo informações do header de resposta do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ac1f3-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="ac1f3-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ac1f3-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ac1f3-136">No SharePoint Online, você pode acessar as informações enviadas de volta ao navegador no header de resposta para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="ac1f3-137">O valor mais útil para diagnosticar problemas de desempenho é **SPRequestDuration**, que exibe o tempo que a solicitação levou no servidor a ser processado.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="ac1f3-138">Isso pode ajudar a determinar se a solicitação é muito pesada e o recurso é intenso.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="ac1f3-139">Essa é a melhor dica que você tem sobre quanto trabalho o servidor está fazendo para atender à página.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="ac1f3-140">Para exibir informações do header de resposta do SharePoint</span><span class="sxs-lookup"><span data-stu-id="ac1f3-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="ac1f3-141">Verifique se você tem as ferramentas F12 instaladas.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="ac1f3-142">Para obter mais informações sobre como baixar e instalar essas ferramentas, consulte [Novidades nas ferramentas F12.](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="ac1f3-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="ac1f3-143">Nas ferramentas F12, na **guia** Rede, pressione o botão de reprodução verde para carregar uma página.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="ac1f3-144">Clique em um dos arquivos .aspx retornados pela ferramenta e clique em **DETALHES.**</span><span class="sxs-lookup"><span data-stu-id="ac1f3-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![Mostra detalhes do cabeçalho de resposta](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="ac1f3-146">Clique **em Headers de resposta**.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-146">Click **Response headers**.</span></span>

    ![Diagrama mostrando a URL do cabeçalho de resposta](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="ac1f3-148">O que está causando problemas de desempenho no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="ac1f3-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="ac1f3-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="ac1f3-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="ac1f3-150">O artigo Opções de navegação para [SharePoint Online](navigation-options-for-sharepoint-online.md) mostra um exemplo de uso do valor SPRequestDuration para determinar que a navegação estrutural complicada estava fazendo com que a página demorava muito para ser processada no servidor.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="ac1f3-151">Ao tirar um valor para um site de linha de base (sem personalização), é possível determinar se um determinado arquivo está demorando muito para ser carregado.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="ac1f3-152">O exemplo usado nas [opções de navegação do SharePoint Online](navigation-options-for-sharepoint-online.md) é o arquivo .aspx principal.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="ac1f3-153">Esse arquivo contém a maior parte do código ASP.NET que é executado para a carga da página.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="ac1f3-154">Dependendo do modelo de site usado, pode ser start.aspx, home.aspx, default.aspx ou outro nome se você personalizar a home page.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="ac1f3-155">Se esse número for consideravelmente maior do que seu site de linha de base, é uma boa indicação de que há algo complexo acontecendo em sua página que está causando problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="ac1f3-156">Depois de identificar que um problema específico do seu site é identificado, a maneira recomendada de descobrir o que está causando um desempenho ruim é eliminar todas as causas possíveis, como personalizações de página, e, em seguida, adicioná-los de volta ao site um por um.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="ac1f3-157">Depois de remover personalizações suficientes para que a página tenha um bom desempenho, você poderá adicionar de volta personalizações específicas uma a uma.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="ac1f3-158">Por exemplo, se você tiver uma navegação muito complexa tente alterar a navegação para não mostrar subs sites, verifique as ferramentas de desenvolvedor para ver se isso faz diferença.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="ac1f3-159">Ou se você tiver uma grande quantidade de roll-ups de conteúdo tente removê-los de sua página e veja se isso melhora as coisas.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="ac1f3-160">Se você eliminar todas as causas possíveis e adicioná-las novamente em uma de cada vez, poderá identificar facilmente quais recursos são o maior problema e, em seguida, trabalhar em direção a uma solução.</span><span class="sxs-lookup"><span data-stu-id="ac1f3-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>