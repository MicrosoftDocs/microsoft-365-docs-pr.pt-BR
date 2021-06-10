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
description: Saiba como diminuir o tempo de carregamento para páginas SharePoint Online usando JavaScript para atrasar o carregamento de imagens e JavaScript não essencial.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919159"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="e4516-103">Atraso no carregamento de imagens e JavaScript no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e4516-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="e4516-104">Este artigo descreve como você pode diminuir o tempo de carga para páginas do SharePoint Online usando JavaScript para atrasar o carregamento de imagens e também aguardando para carregar JavaScript não essencial até que a página seja carregada.</span><span class="sxs-lookup"><span data-stu-id="e4516-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="e4516-105">As imagens podem afetar negativamente as velocidades de carga da página SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4516-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="e4516-106">Por padrão, a maioria dos navegadores modernos da Internet pré-busca imagens ao carregar uma página HTML.</span><span class="sxs-lookup"><span data-stu-id="e4516-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="e4516-107">Isso pode fazer com que a página seja desnecessariamente lenta para carregar se as imagens não estão visíveis na tela até que o usuário role para baixo.</span><span class="sxs-lookup"><span data-stu-id="e4516-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="e4516-108">As imagens podem impedir o navegador de carregar a parte visível da página.</span><span class="sxs-lookup"><span data-stu-id="e4516-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="e4516-109">Para resolver esse problema, você pode usar JavaScript para ignorar o carregamento das imagens primeiro.</span><span class="sxs-lookup"><span data-stu-id="e4516-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="e4516-110">Além disso, carregar JavaScript não essencial também pode diminuir o tempo de download em SharePoint páginas.</span><span class="sxs-lookup"><span data-stu-id="e4516-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="e4516-111">Este tópico descreve alguns métodos que você pode usar para melhorar os tempos de carregamento de página com JavaScript no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4516-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="e4516-112">Melhorar os tempos de carregamento de página atrasando o carregamento de imagem em SharePoint online usando JavaScript</span><span class="sxs-lookup"><span data-stu-id="e4516-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="e4516-113">Você pode usar o JavaScript para impedir que um navegador da Web pre-busque imagens.</span><span class="sxs-lookup"><span data-stu-id="e4516-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="e4516-114">Isso acelera a renderização geral do documento.</span><span class="sxs-lookup"><span data-stu-id="e4516-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="e4516-115">Para fazer isso, remova o valor do atributo src da marca e substitua-o pelo caminho para um arquivo em um atributo de dados, \<img\> como: data-src.</span><span class="sxs-lookup"><span data-stu-id="e4516-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="e4516-116">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e4516-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="e4516-117">Usando esse método, o navegador não baixa as imagens imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e4516-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="e4516-118">Se a imagem já estiver no viewport, JavaScript pedirá ao navegador para recuperar a URL do atributo de dados e inseri-la como o valor do atributo src.</span><span class="sxs-lookup"><span data-stu-id="e4516-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="e4516-119">A imagem só é carregada à medida que o usuário rola e ela entra em exibição.</span><span class="sxs-lookup"><span data-stu-id="e4516-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="e4516-120">Para fazer tudo isso acontecer, você precisará usar JavaScript.</span><span class="sxs-lookup"><span data-stu-id="e4516-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="e4516-121">Em um arquivo de texto, defina a função **isElementInViewport()** para verificar se um elemento está ou não na parte do navegador visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e4516-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="e4516-122">Em seguida, **use isElementInViewport()** na **função loadItemsInView().**</span><span class="sxs-lookup"><span data-stu-id="e4516-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="e4516-123">A **função loadItemsInView()** carregará todas as imagens que tenham um valor para o atributo data-src se elas estão na parte do navegador visível para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e4516-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="e4516-124">Adicione a seguinte função ao arquivo de texto:</span><span class="sxs-lookup"><span data-stu-id="e4516-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="e4516-125">Por fim, **chame loadItemsInView()** de **dentro de window.onscroll()** conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e4516-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="e4516-126">Isso garante que todas as imagens que estão no viewport sejam carregadas conforme o usuário precisa delas, mas não antes.</span><span class="sxs-lookup"><span data-stu-id="e4516-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="e4516-127">Adicione o seguinte ao arquivo de texto:</span><span class="sxs-lookup"><span data-stu-id="e4516-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="e4516-128">Para SharePoint Online, você precisa anexar a seguinte função ao evento de rolagem na marca \<div\> #s4-workspace.</span><span class="sxs-lookup"><span data-stu-id="e4516-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="e4516-129">Isso ocorre porque os eventos da janela são substituídos para garantir que a faixa de opções permaneça anexada à parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="e4516-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="e4516-130">Salve o arquivo de texto como um arquivo JavaScript com a extensão .js, por exemplo, delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="e4516-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="e4516-131">Depois de terminar de escrever delayLoadImages.js, você pode adicionar o conteúdo do arquivo a uma página mestra no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e4516-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="e4516-132">Você faz isso adicionando um link de script ao header na página mestra.</span><span class="sxs-lookup"><span data-stu-id="e4516-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="e4516-133">Depois de estar em uma página mestra, o JavaScript será aplicado a todas as páginas em seu site SharePoint Online que usam esse layout de página mestra.</span><span class="sxs-lookup"><span data-stu-id="e4516-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="e4516-134">Como alternativa, se você pretende usar isso apenas em uma página do seu site, use a Web Part do editor de scripts para inserir o JavaScript na página.</span><span class="sxs-lookup"><span data-stu-id="e4516-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="e4516-135">Confira estes tópicos para obter mais informações:</span><span class="sxs-lookup"><span data-stu-id="e4516-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="e4516-136">Como: aplicar uma página mestra a um site no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e4516-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="e4516-137">Tutorial: criar um layout de página no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e4516-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="e4516-138">Exemplo: fazendo referência ao arquivo javaScript delayLoadImages.js de uma página mestra no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e4516-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="e4516-139">Para que isso funcione, você também precisa fazer referência a jQuery na página mestra.</span><span class="sxs-lookup"><span data-stu-id="e4516-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="e4516-140">No exemplo a seguir, você pode ver na carga inicial da página que há apenas uma imagem carregada, mas há várias outras na página.</span><span class="sxs-lookup"><span data-stu-id="e4516-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Captura de tela mostrando uma imagem carregada na página](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="e4516-142">A captura de tela a seguir mostra o restante das imagens que são baixadas após rolarem para o exibição.</span><span class="sxs-lookup"><span data-stu-id="e4516-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Captura de tela mostrando várias imagens carregadas na página](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="e4516-144">Atrasar o carregamento de imagem usando JavaScript pode ser uma técnica eficaz para aumentar o desempenho; no entanto, se a técnica for aplicada em um site público, os mecanismos de pesquisa não poderão rastrear as imagens da mesma maneira que rastreariam uma imagem formada regularmente.</span><span class="sxs-lookup"><span data-stu-id="e4516-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="e4516-145">Isso pode afetar as classificações nos mecanismos de pesquisa porque os metadados na imagem em si não estão realmente lá até que a página seja carregada.</span><span class="sxs-lookup"><span data-stu-id="e4516-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="e4516-146">Os rastreadores do mecanismo de pesquisa só leem o HTML e, portanto, não verão as imagens como conteúdo na página.</span><span class="sxs-lookup"><span data-stu-id="e4516-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="e4516-147">As imagens são um dos fatores usados para classificar páginas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e4516-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="e4516-148">Uma maneira de resolver isso é usar texto introdutório para suas imagens.</span><span class="sxs-lookup"><span data-stu-id="e4516-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="e4516-149">GitHub de código: Injetar JavaScript para melhorar o desempenho</span><span class="sxs-lookup"><span data-stu-id="e4516-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="e4516-150">Não perca o artigo e o exemplo de código sobre a injeção [javaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) fornecida GitHub.</span><span class="sxs-lookup"><span data-stu-id="e4516-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e4516-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4516-151">See also</span></span>

[<span data-ttu-id="e4516-152">Navegadores com suporte no Office 2013 e Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="e4516-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="e4516-153">Como: aplicar uma página mestra a um site no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e4516-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="e4516-154">Tutorial: criar um layout de página no SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="e4516-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)