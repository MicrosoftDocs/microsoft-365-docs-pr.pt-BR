---
title: Atraso no carregamento de imagens e JavaScript no SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: Admin
ms.topic: troubleshooting
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
- SPO160
- MET150
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: Saiba como diminuir o tempo de carregamento das páginas do SharePoint Online usando JavaScript para atrasar o carregamento de imagens e JavaScript não essencial.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687289"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="9b7b9-103">Atraso no carregamento de imagens e JavaScript no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9b7b9-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="9b7b9-104">Este artigo descreve como você pode diminuir o tempo de carregamento das páginas do SharePoint Online usando JavaScript para atrasar o carregamento de imagens e também aguardando para carregar JavaScript não essencial até que a página seja carregada.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="9b7b9-105">As imagens podem afetar negativamente as velocidades de carregamento da página no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="9b7b9-106">Por padrão, os navegadores da Internet mais modernos pré-buscam imagens ao carregar uma página HTML.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="9b7b9-107">Isso pode fazer com que a página seja desnecessariamente lenta para carregar se as imagens não estão visíveis na tela até que o usuário role para baixo.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="9b7b9-108">As imagens podem impedir o navegador de carregar a parte visível da página.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="9b7b9-109">Para resolver esse problema, você pode usar o JavaScript para ignorar o carregamento das imagens primeiro.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="9b7b9-110">Além disso, carregar JavaScript não essencial também pode reduzir os tempos de download em suas páginas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="9b7b9-111">Este tópico descreve alguns métodos que você pode usar para melhorar o tempo de carregamento da página com JavaScript no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="9b7b9-112">Melhorar o tempo de carregamento de página atrasando o carregamento de imagem em páginas do SharePoint Online usando JavaScript</span><span class="sxs-lookup"><span data-stu-id="9b7b9-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="9b7b9-113">Você pode usar o JavaScript para impedir que um navegador da Web pré-busque imagens.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="9b7b9-114">Isso acelera a renderização geral do documento.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="9b7b9-115">Para fazer isso, remova o valor do atributo src da marca e substitua-o pelo caminho para um arquivo em um atributo de dados \<img\> como: data-src.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="9b7b9-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b7b9-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="9b7b9-117">Usando esse método, o navegador não baixa as imagens imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="9b7b9-118">Se a imagem já estiver no viewport, o JavaScript pedirá ao navegador para recuperar a URL do atributo de dados e inseri-la como o valor do atributo src.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="9b7b9-119">A imagem só é carregada conforme o usuário rola e entra em exibição.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="9b7b9-120">Para fazer tudo isso acontecer, você precisará usar JavaScript.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="9b7b9-121">Em um arquivo de texto, defina a função **isElementInViewport()** para verificar se um elemento está ou não na parte do navegador que é visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

<span data-ttu-id="9b7b9-122">Em seguida, use **isElementInViewport()** na **função loadItemsInView().**</span><span class="sxs-lookup"><span data-stu-id="9b7b9-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="9b7b9-123">A **função loadItemsInView()** carregará todas as imagens que tenham um valor para o atributo data-src se elas estão na parte do navegador visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="9b7b9-124">Adicione a seguinte função ao arquivo de texto:</span><span class="sxs-lookup"><span data-stu-id="9b7b9-124">Add the following function to the text file:</span></span>
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

<span data-ttu-id="9b7b9-125">Por fim, **chame loadItemsInView()** de **dentro de window.onscroll()** conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="9b7b9-126">Isso garante que todas as imagens que estão no viewport sejam carregadas conforme o usuário precisa delas, mas não antes.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="9b7b9-127">Adicione o seguinte ao arquivo de texto:</span><span class="sxs-lookup"><span data-stu-id="9b7b9-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="9b7b9-128">Para o SharePoint Online, você precisa anexar a função a seguir ao evento de rolagem na marca #s4 de espaço de \<div\> trabalho.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="9b7b9-129">Isso ocorre porque os eventos de janela são substituídos para garantir que a faixa de opções permaneça anexada à parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="9b7b9-130">Salve o arquivo de texto como um arquivo JavaScript com a extensão .js, por exemplo, delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="9b7b9-131">Depois de terminar de escrever delayLoadImages.js, você pode adicionar o conteúdo do arquivo a uma página mestra no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="9b7b9-132">Você pode fazer isso adicionando um link de script ao título na página mestra.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="9b7b9-133">Quando ele está em uma página mestra, o JavaScript será aplicado a todas as páginas em seu site do SharePoint Online que usam esse layout de página mestra.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="9b7b9-134">Como alternativa, se você pretende usar isso apenas em uma página do seu site, use a Web Part do editor de scripts para inserir o JavaScript na página.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="9b7b9-135">Consulte estes tópicos para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="9b7b9-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="9b7b9-136">Como: aplicar uma página mestra a um site no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9b7b9-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [<span data-ttu-id="9b7b9-137">Tutorial: criar um layout de página no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9b7b9-137">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="9b7b9-138">Exemplo: Referenciando o arquivo javascript delayLoadImages.js de uma página mestra no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9b7b9-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="9b7b9-139">Para que isso funcione, você também precisa fazer referência a jQuery na página mestra.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="9b7b9-140">No exemplo a seguir, você pode ver no carregamento inicial da página que há apenas uma imagem carregada, mas há várias mais na página.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Captura de tela mostrando uma imagem carregada na página](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="9b7b9-142">A captura de tela a seguir mostra o restante das imagens que são baixadas depois que elas rolam para a exibição.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Captura de tela mostrando várias imagens carregadas na página](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="9b7b9-144">Atrasar o carregamento de imagens usando JavaScript pode ser uma técnica eficaz para aumentar o desempenho; No entanto, se a técnica for aplicada em um site público, os mecanismos de pesquisa não poderão rastrear as imagens da mesma forma que rastreariam uma imagem formada regularmente.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="9b7b9-145">Isso pode afetar as classificações nos mecanismos de pesquisa porque os metadados na imagem em si não estão realmente lá até que a página seja carregada.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="9b7b9-146">Os rastreadores do mecanismo de pesquisa apenas leem o HTML e, portanto, não verão as imagens como conteúdo na página.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="9b7b9-147">As imagens são um dos fatores usados para classificar páginas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="9b7b9-148">Uma maneira de resolver isso é usar texto introdutório para suas imagens.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="9b7b9-149">Exemplo de código do GitHub: injetar JavaScript para melhorar o desempenho</span><span class="sxs-lookup"><span data-stu-id="9b7b9-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="9b7b9-150">Não perca o artigo e o exemplo de código sobre a [injeção de JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) fornecido no GitHub.</span><span class="sxs-lookup"><span data-stu-id="9b7b9-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b7b9-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="9b7b9-151">See also</span></span>

[<span data-ttu-id="9b7b9-152">Navegadores com suporte no Office 2013 e no Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="9b7b9-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="9b7b9-153">Como: aplicar uma página mestra a um site no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9b7b9-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[<span data-ttu-id="9b7b9-154">Tutorial: criar um layout de página no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9b7b9-154">How to: Create a page layout in SharePoint 2013</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=525628)
