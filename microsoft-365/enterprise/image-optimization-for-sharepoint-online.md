---
title: Otimização de imagem para sites de publicação clássicos do SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
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
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: Saiba como usar representações e sprites para melhorar o desempenho da imagem em seus sites de publicação clássicos do SharePoint Online.
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687159"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Otimização de imagem para sites de publicação clássicos do SharePoint Online

A velocidade de carregamento de uma página da Web depende do tamanho combinado de todos os componentes necessários para renderizar a página, incluindo imagens, HTML, JavaScript e CSS. As imagens são uma ótima maneira de tornar seu site mais atraente, mas seu tamanho pode afetar o desempenho. Ao otimizar suas imagens com compactação e re tamanho, e usando sprites, você pode desloca os efeitos de imagens muito grandes. Usando as representações de imagem do SharePoint, você pode carregar uma única imagem grande e exibir seções da imagem permitindo que ela seja reutilizada em vez de recarregada.

>[!NOTE]
>Este tópico se aplica aos sites de publicação clássicos do SharePoint Online, não a sites de portal modernos. Para saber mais sobre a otimização de imagens nos sites de portal modernos do SharePoint Online, confira Otimizar imagens nas páginas do portal moderno do [SharePoint Online.](modern-image-optimization.md)
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Usar sprites para acelerar o carregamento de imagens

|||
|:-----|:-----|
| Um sprite de imagem contém muitas imagens menores. Usando o CSS, você seleciona uma parte da imagem composta para exibir em uma parte específica da página com posicionamento absoluto. Basicamente, você move uma única imagem ao redor da página em vez de carregar várias imagens e torna uma pequena parte dessa imagem visível por meio de uma pequena janela em que a parte necessária da imagem de sprite é mostrada para o usuário final. O SharePoint Online usa sprites para exibir seus vários ícones no sprite spcommon.png.  <br/>  O que é abordado aqui:  <br/>  Compactação de imagem  <br/>  Otimização de imagem  <br/>  Representações de imagem do SharePoint  <br/> |![Captura de tela do spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Isso pode aumentar o desempenho porque você baixa apenas uma imagem em vez de várias e depois armazena em cache e reutiliza essa imagem. Mesmo que a imagem não permaneça em cache, tendo uma única imagem em vez de várias imagens, esse método reduz o número total de solicitações HTTP para o servidor, o que reduzirá o tempo de carregamento da página. Isso é realmente uma forma de reaqueamento de imagens. Essa é uma técnica muito útil se as imagens não estão mudando com muita frequência, por exemplo, ícones, conforme mostrado no exemplo do SharePoint fornecido acima. Você pode usar o [Web Essentials](https://vswebessentials.com/), um projeto de terceiros baseado em comunidade, de código aberto, para conseguir isso facilmente no Microsoft Visual Studio. Para obter mais informações, consulte [Minification e bundling no SharePoint Online.](https://go.microsoft.com/fwlink/?LinkId=708698)
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Usar a compactação e a otimização de imagem para acelerar o carregamento de páginas

A compactação e a otimização da imagem são sobre a redução do tamanho do arquivo das imagens que você usa no seu site. Muitas vezes, a melhor técnica para reduzir o tamanho de uma imagem é re dimensionar a imagem para as dimensões máximas que ela será exibida no site. Não faz sentido ter uma imagem maior do que nunca será exibida. Garantir que as imagens sejam das dimensões corretas usando um editor de imagens é uma maneira rápida e fácil de reduzir o tamanho da sua página.
  
Depois que as imagens têm o tamanho correto, a próxima etapa é otimizar a compactação dessas imagens. Há várias ferramentas disponíveis para usar para compactação e otimização, incluindo Galeria de Fotos e ferramentas de terceiros. A chave para compactação é reduzir o tamanho do arquivo o máximo possível sem perder qualquer qualidade perceptível para os usuários finais. Certifique-se de testar seus arquivos compactados em uma exibição de alta definição para garantir que eles ainda terão uma boa aparência.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Acelerar os downloads de página usando a reprodução de imagens do SharePoint

As representações de imagem são um recurso no SharePoint Online que permite atender a diferentes versões de imagens com base em dimensões de imagem pré-definidas. Isso é especialmente importante quando há conteúdo de imagem gerado pelo usuário ou as dimensões da imagem, como largura e altura, são corrigidas pelo CSS no site. Mesmo que uma imagem seja corrigida por CSS, a imagem de resolução total ainda será carregada. Nesse caso, o tamanho do arquivo pode ser reduzido usando representações de imagem.
  
> [!NOTE]
> As representações só estarão disponíveis para o SharePoint quando a publicação estiver habilitada. Você pode habilitar a publicação em Configurações \> do Site Gerenciar recursos de site de Publicação do \> \> SharePoint Server. A opção não será exibida de outra forma.
  
O re dimensionamento da rendição de imagem funciona aproveitando a menor dimensão definida, largura ou altura, e re dimensionando a imagem para que a outra dimensão seja automaticamente relizada com base na taxa de proporção bloqueada. Por padrão, ele cortará a imagem do centro pelas dimensões restantes. Por exemplo, se você definir uma rendição de 100px de largura e 50px de altura e sua imagem original tiver 1000px de largura e 800px de altura, ela será relizada para que a dimensão de 800px agora seja 50px e a dimensão de 1000px (agora 62,5px) seja cortada do centro da imagem.
  
As etapas são relativamente simples, mas para que as imagens usem as representações, as representações precisam estar no site do SharePoint antes de adicionar as imagens. Além disso, você também precisa ter os recursos Infraestrutura de Publicação do SharePoint Server (Nível do Conjunto de Sites) e Publicação do SharePoint Server (Nível de Site) ativos.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Adicionar uma reprodução de imagem para acelerar o carregamento de página
  
1. Verifique se a conta de usuário que está executando esse procedimento tem, no mínimo, permissões de Design para o site de nível superior do conjunto de sites e se o site está sendo publicado em uma página da Web.

2. Em um navegador da Web, vá para o site de nível superior do conjunto de sites de publicação.

3. Escolha o ícone de **configurações**.

4. Na página **Configurações do Site,** na **seção Aparência,** você verá as representações de imagem.

    Você pode usar as representações fora da caixa ou escolher representações **de** imagem para criar uma nova.

    ![Captura de tela da apresentação de imagem](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. Na página **Representações de Imagem**, escolha **Adicionar novo item**.

    ![Captura de tela de Adicionar Novo Item](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Na página **Nova representação de imagem**, na caixa **nome**, digite um nome para a representação.

7. Nas caixas de texto **Largura** e **Altura**, digite a largura e a altura, em pixels, da representação e, em seguida, escolha **Salvar**.

    ![Captura de tela do Nome da Representação de Imagem](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Corte personalizado com representações de imagem

Por padrão, uma representação de imagem é gerada a partir do centro da imagem. Você pode ajustar a representação de imagem para imagens individuais, cortando a parte da imagem que você deseja usar. Você pode cortar as imagens individualmente, por apresentação. O corte das imagens acelera o carregamento de página usando o cache de blob do SharePoint para criar uma versão da imagem para cada apresentação. Dessa forma, a carga do servidor é reduzida porque a imagem só é re tamanhoada uma vez e então está pronta para servir aos usuários finais várias vezes. For more information on how to crop an image rendition, see [Crop an image rendition](https://go.microsoft.com/fwlink/p/?LinkId=525626).
  

