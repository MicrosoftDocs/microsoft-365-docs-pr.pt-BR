---
title: Minificação e agrupamento no SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
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
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Saiba como usar técnicas de diminuição e de emulação com o Web Essentials para reduzir solicitações HTTP e o tempo necessário para carregar páginas no SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686957"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="0ba71-103">Minificação e agrupamento no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0ba71-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="0ba71-104">Este artigo descreve como usar técnicas de diminuição e de numeração com o Web Essentials para reduzir o número de solicitações HTTP e reduzir o tempo necessário para carregar páginas no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0ba71-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="0ba71-105">Ao personalizar seu site, você pode acabar adicionando um grande número de arquivos extras ao servidor para dar suporte à personalização.</span><span class="sxs-lookup"><span data-stu-id="0ba71-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="0ba71-106">Adicionar JavaScript, CSS e imagens extras aumenta o número de solicitações HTTP para o servidor, o que, por sua vez, aumenta o tempo necessário para exibir uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="0ba71-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="0ba71-107">Se você tiver vários arquivos do mesmo tipo, poderá agrupar esses arquivos para tornar o download desses arquivos mais rápido.</span><span class="sxs-lookup"><span data-stu-id="0ba71-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="0ba71-108">Para arquivos JavaScript e CSS, você também pode usar uma abordagem chamada redução, onde você reduz o tamanho total de arquivos removendo espaços em branco e outros caracteres que não são necessários.</span><span class="sxs-lookup"><span data-stu-id="0ba71-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="0ba71-109">Replicação e a replicação de arquivos CSS e JavaScript com o Web Essentials</span><span class="sxs-lookup"><span data-stu-id="0ba71-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="0ba71-110">Você pode usar softwares de terceiros, como o Web Essentials, para agrupar arquivos CSS e JavaScript.</span><span class="sxs-lookup"><span data-stu-id="0ba71-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ba71-111">O Web Essentials é um projeto de terceiros baseado em comunidade, de código aberto.</span><span class="sxs-lookup"><span data-stu-id="0ba71-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="0ba71-112">O software é uma extensão do Visual Studio 2012 e do Visual Studio 2013 e não é suportado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0ba71-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="0ba71-113">Para baixar o Web Essentials, visite o site em [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="0ba71-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="0ba71-114">O Web Essentials oferece duas formas de aplicação:</span><span class="sxs-lookup"><span data-stu-id="0ba71-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="0ba71-115">.bundle: para arquivos CSS e JavaScript</span><span class="sxs-lookup"><span data-stu-id="0ba71-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="0ba71-116">.sprite: para imagens (disponível somente no Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="0ba71-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="0ba71-117">Você pode usar o Web Essentials se tiver um recurso existente com alguns elementos de identidade visual referenciados dentro de uma página mestra personalizada, como:</span><span class="sxs-lookup"><span data-stu-id="0ba71-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Captura de tela do elemento de marca na página mestra personalizada](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="0ba71-119">**Para criar um pacote TE000127218 e CSS no Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="0ba71-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="0ba71-120">No Visual Studio, no Solution Explorer, selecione os arquivos que você deseja incluir no pacote.</span><span class="sxs-lookup"><span data-stu-id="0ba71-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="0ba71-121">Clique com o botão direito do mouse nos arquivos selecionados e selecione **Web Essentials** Criar arquivo de pacote \> **JavaScript** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="0ba71-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="0ba71-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0ba71-122">For example:</span></span> 
    
    ![Captura de tela mostrando as opções do menu Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="0ba71-124">Exibindo os resultados do bundling de arquivos JAVAScript e CSS</span><span class="sxs-lookup"><span data-stu-id="0ba71-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="0ba71-125">Quando você cria um pacote JavaScript e CSS, o Web Essentials cria um arquivo XML chamado um arquivo de receita que identifica os arquivos JavaScript e CSS, bem como algumas outras informações de configuração:</span><span class="sxs-lookup"><span data-stu-id="0ba71-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Captura de tela de arquivo de receita JavaScript e CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="0ba71-127">Além disso, se o sinalizador de diminuição estiver definido como verdadeiro na receita de empacotamento, os arquivos serão reduzidos em tamanho e agrupados.</span><span class="sxs-lookup"><span data-stu-id="0ba71-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="0ba71-128">Isso significa que foram criadas versões novas e minificadas dos arquivos JavaScript que você pode referenciar em sua página mestra.</span><span class="sxs-lookup"><span data-stu-id="0ba71-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Captura de tela do sinalizador minify definido como verdadeiro](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="0ba71-130">Ao carregar uma página do seu site, você pode usar as ferramentas de desenvolvedor do navegador da Web, como o Internet Explorer 11, para ver o número de solicitações enviadas ao servidor e quanto tempo cada arquivo levou para carregar.</span><span class="sxs-lookup"><span data-stu-id="0ba71-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="0ba71-131">A figura a seguir é o resultado do carregamento dos arquivos JavaScript e CSS antes da ulação.</span><span class="sxs-lookup"><span data-stu-id="0ba71-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Captura de tela mostrando 80 itens sendo baixados](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="0ba71-133">Depois de unir os arquivos CSS e JavaScript, o número de solicitações passou para 74 e cada arquivo levou apenas um pouco mais do que os arquivos originais para baixar individualmente:</span><span class="sxs-lookup"><span data-stu-id="0ba71-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Captura de tela mostrando 74 itens sendo baixados](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="0ba71-135">Após o empacotamento, o arquivo de pacote JavaScript é reduzido significativamente de 815KB para 365KB:</span><span class="sxs-lookup"><span data-stu-id="0ba71-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Captura de tela mostrando tamanho do download reduzido](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="0ba71-137">Como criar um sprite de imagem para criar imagens</span><span class="sxs-lookup"><span data-stu-id="0ba71-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="0ba71-138">Semelhante a como agrupar arquivos JavaScript e CSS, você pode combinar muitos ícones pequenos e outras imagens comuns em uma folha de sprite maior e, em seguida, usar CSS para revelar as imagens individuais.</span><span class="sxs-lookup"><span data-stu-id="0ba71-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="0ba71-139">Em vez de baixar cada imagem individual, o navegador da Web do usuário baixa a folha de sprite uma vez e a armazena em cache no computador local.</span><span class="sxs-lookup"><span data-stu-id="0ba71-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="0ba71-140">Isso melhora o desempenho da carga da página reduzindo o número de downloads e viagens de ida e volta ao servidor Web.</span><span class="sxs-lookup"><span data-stu-id="0ba71-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="0ba71-141">**Para criar um sprite de imagem no Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="0ba71-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="0ba71-142">No Visual Studio, no Solution Explorer, selecione os arquivos que você deseja incluir no pacote.</span><span class="sxs-lookup"><span data-stu-id="0ba71-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="0ba71-143">Clique com o botão direito do mouse nos arquivos selecionados e selecione **Web Essentials** \> **Create image sprite** no menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="0ba71-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="0ba71-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0ba71-144">For example:</span></span> 
    
    ![Captura de tela mostrando como criar uma entidade gráfica de imagem](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="0ba71-146">Escolha um local para salvar o arquivo sprite.</span><span class="sxs-lookup"><span data-stu-id="0ba71-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="0ba71-147">O arquivo .sprite é um arquivo XML que descreve as configurações e os arquivos no sprite.</span><span class="sxs-lookup"><span data-stu-id="0ba71-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="0ba71-148">As figuras a seguir mostram um exemplo de um arquivo PNG de sprite e seu arquivo XML .sprite correspondente.</span><span class="sxs-lookup"><span data-stu-id="0ba71-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Captura de tela de um arquivo de entidade gráfica](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Captura de tela de arquivo XML de entidade gráfica](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

