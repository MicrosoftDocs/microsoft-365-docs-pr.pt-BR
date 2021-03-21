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
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919159"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Atraso no carregamento de imagens e JavaScript no SharePoint Online

Este artigo descreve como você pode diminuir o tempo de carga para páginas do SharePoint Online usando JavaScript para atrasar o carregamento de imagens e também aguardando para carregar JavaScript não essencial até depois que a página for carregada.
  
As imagens podem afetar negativamente as velocidades de carga da página no SharePoint Online. Por padrão, a maioria dos navegadores modernos da Internet pré-busca imagens ao carregar uma página HTML. Isso pode fazer com que a página seja desnecessariamente lenta para carregar se as imagens não estão visíveis na tela até que o usuário role para baixo. As imagens podem impedir o navegador de carregar a parte visível da página. Para resolver esse problema, você pode usar JavaScript para ignorar o carregamento das imagens primeiro. Além disso, carregar JavaScript não essencial também pode diminuir o tempo de download em suas páginas do SharePoint. Este tópico descreve alguns métodos que você pode usar para melhorar os tempos de carregamento de página com JavaScript no SharePoint Online.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Melhorar os tempos de carregamento de página atrasando o carregamento de imagem em páginas do SharePoint Online usando JavaScript

Você pode usar o JavaScript para impedir que um navegador da Web pre-busque imagens. Isso acelera a renderização geral do documento. Para fazer isso, remova o valor do atributo src da marca e substitua-o pelo caminho para um arquivo em um atributo de dados, \<img\> como: data-src. Por exemplo:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Usando esse método, o navegador não baixa as imagens imediatamente. Se a imagem já estiver no viewport, JavaScript pedirá ao navegador para recuperar a URL do atributo de dados e inseri-la como o valor do atributo src. A imagem só é carregada à medida que o usuário rola e ela entra em exibição.
  
Para fazer tudo isso acontecer, você precisará usar JavaScript.
  
Em um arquivo de texto, defina a função **isElementInViewport()** para verificar se um elemento está ou não na parte do navegador visível para o usuário.
  
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

Em seguida, **use isElementInViewport()** na **função loadItemsInView().** A **função loadItemsInView()** carregará todas as imagens que tenham um valor para o atributo data-src se elas estão na parte do navegador visível para o usuário. Adicione a seguinte função ao arquivo de texto:
  
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

Por fim, **chame loadItemsInView()** de **dentro de window.onscroll()** conforme mostrado no exemplo a seguir. Isso garante que todas as imagens que estão no viewport sejam carregadas conforme o usuário precisa delas, mas não antes. Adicione o seguinte ao arquivo de texto:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Para o SharePoint Online, você precisa anexar a seguinte função ao evento de rolagem na marca \<div\> #s4-workspace. Isso ocorre porque os eventos da janela são substituídos para garantir que a faixa de opções permaneça anexada à parte superior da página.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Salve o arquivo de texto como um arquivo JavaScript com a extensão .js, por exemplo, delayLoadImages.js.
  
Depois de terminar de escrever delayLoadImages.js, você pode adicionar o conteúdo do arquivo a uma página mestra no SharePoint Online. Você faz isso adicionando um link de script ao header na página mestra. Depois de estar em uma página mestra, o JavaScript será aplicado a todas as páginas em seu site do SharePoint Online que usam esse layout de página mestra. Como alternativa, se você pretende usar isso apenas em uma página do seu site, use a Web Part do editor de scripts para inserir o JavaScript na página. Confira estes tópicos para obter mais informações:
  
- [Como: aplicar uma página mestra a um site no SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [Tutorial: criar um layout de página no SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Exemplo: fazendo referência ao arquivo delayLoadImages.js JavaScript de uma página mestra no SharePoint Online
  
Para que isso funcione, você também precisa fazer referência a jQuery na página mestra. No exemplo a seguir, você pode ver na carga inicial da página que há apenas uma imagem carregada, mas há várias outras na página.
  
![Captura de tela mostrando uma imagem carregada na página](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
A captura de tela a seguir mostra o restante das imagens que são baixadas após rolarem para o exibição.
  
![Captura de tela mostrando várias imagens carregadas na página](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Atrasar o carregamento de imagem usando JavaScript pode ser uma técnica eficaz para aumentar o desempenho; no entanto, se a técnica for aplicada em um site público, os mecanismos de pesquisa não poderão rastrear as imagens da mesma maneira que rastreariam uma imagem formada regularmente. Isso pode afetar as classificações nos mecanismos de pesquisa porque os metadados na imagem em si não estão realmente lá até que a página seja carregada. Os rastreadores do mecanismo de pesquisa só leem o HTML e, portanto, não verão as imagens como conteúdo na página. As imagens são um dos fatores usados para classificar páginas nos resultados da pesquisa. Uma maneira de resolver isso é usar texto introdutório para suas imagens.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>Exemplo de código do GitHub: Injetar JavaScript para melhorar o desempenho

Não perca o artigo e o exemplo de código sobre a injeção [JavaScript](https://go.microsoft.com/fwlink/p/?LinkId=524759) fornecida no GitHub.
  
## <a name="see-also"></a>Confira também

[Navegadores com suporte no Office 2013 e no Microsoft 365 Apps para empresas](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Como: aplicar uma página mestra a um site no SharePoint 2013](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[Tutorial: criar um layout de página no SharePoint 2013](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)