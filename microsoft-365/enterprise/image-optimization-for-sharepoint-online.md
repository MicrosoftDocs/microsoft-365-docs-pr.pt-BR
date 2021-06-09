---
title: Otimização de imagem para SharePoint sites de publicação clássicos online
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
description: Saiba como usar representações e sprites para melhorar o desempenho da imagem em seus sites de publicação SharePoint online clássicos.
ms.openlocfilehash: 0f0dd078ce28b86fc998b2f83ac19d04b1a3ab02
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907475"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Otimização de imagem para SharePoint sites de publicação clássicos online

A velocidade de carregamento de uma página da Web depende do tamanho combinado de todos os componentes necessários para renderizar a página, incluindo imagens, HTML, JavaScript e CSS. As imagens são uma ótima maneira de tornar seu site mais atraente, mas seu tamanho pode afetar o desempenho. Otimizando suas imagens com compactação e ressizing e usando sprites, você pode compensar os efeitos de imagens muito grandes. Usando SharePoint de imagens, você pode carregar uma única imagem grande e exibir seções da imagem permitindo que ela seja reutilizada em vez de recarregada.

>[!NOTE]
>Este tópico se aplica a sites de publicação SharePoint online clássicos, não aos sites de portal modernos. Para obter informações sobre otimização de imagem SharePoint sites de portal modernos online, consulte [Optimize images in SharePoint Online modern portal pages](modern-image-optimization.md).
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Usando sprites para acelerar o carregamento de imagem

|||
|:-----|:-----|
| Um sprite de imagem contém muitas imagens menores. Usando CSS, você seleciona uma parte da imagem composta para exibir em uma parte específica da página com posicionamento absoluto. Basicamente, você move uma única imagem ao redor da página em vez de carregar várias imagens e torna uma pequena parte dessa imagem visível através de uma pequena janela onde a parte necessária da imagem sprite é mostrada para o usuário final. SharePoint Online usa sprites para exibir seus vários ícones no sprite spcommon.png.  <br/>  O que é abordado aqui:  <br/>  Compactação de imagem  <br/>  Otimização de imagem  <br/>  SharePoint de imagem  <br/> |![Captura de tela do spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Isso pode aumentar o desempenho porque você baixa apenas uma imagem em vez de várias e, em seguida, armazena em cache e reutiliza essa imagem. Mesmo que a imagem não permaneça em cache, tendo uma única imagem em vez de várias imagens, esse método reduz o número total de solicitações HTTP para o servidor, o que reduzirá o tempo de carregamento da página. Isso é realmente uma forma de adlinhamento de imagem. Esta é uma técnica muito útil se as imagens não estão mudando com muita frequência, por exemplo, ícones, conforme mostrado no SharePoint exemplo fornecido acima. Você pode usar o [Web Essentials](https://vswebessentials.com/), um projeto de terceiros, de código aberto, baseado na comunidade para conseguir isso facilmente Microsoft Visual Studio. Para obter mais informações, consulte [Minification and bundling in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Usar compactação e otimização de imagem para acelerar o carregamento de página

A compactação e a otimização de imagem se trata de reduzir o tamanho do arquivo das imagens que você usa em seu site. Muitas vezes, a melhor técnica para reduzir o tamanho de uma imagem é ressizer a imagem para as dimensões máximas que serão exibidas no site. Não faz sentido ter uma imagem maior do que jamais será exibida. Garantir que as imagens sejam das dimensões corretas usando um editor de imagens é uma maneira rápida e fácil de reduzir o tamanho da sua página.
  
Depois que as imagens têm o tamanho certo, a próxima etapa é otimizar a compactação dessas imagens. Há várias ferramentas disponíveis para compactação e otimização, incluindo Galeria de Fotos e ferramentas de terceiros. A chave para compactação é reduzir o tamanho do arquivo o máximo possível sem perder qualquer qualidade perceptível para os usuários finais. Teste seus arquivos compactados em uma exibição de alta definição para garantir que eles ainda terão boa aparência.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Acelerar downloads de página usando SharePoint de imagem

As representações de imagem são um recurso no SharePoint Online que permite que você sirva diferentes versões de imagens com base em dimensões de imagem pré-definidas. Isso é especialmente importante quando há conteúdo de imagem gerado pelo usuário ou as dimensões de imagem, como largura e altura, são corrigidas pelo CSS no site. Mesmo que uma imagem seja corrigida por CSS, a imagem de resolução completa ainda será carregada. Nesse caso, o tamanho do arquivo pode ser reduzido usando representações de imagem.
  
> [!NOTE]
> As representações só estão disponíveis para SharePoint quando a publicação está habilitada. Você pode habilitar a publicação em Configurações \> Site Configurações Gerenciar recursos de site SharePoint Publicação do \> \> Servidor. A opção não aparecerá de outra forma.
  
O dimensionamento da rendição de imagem funciona com a menor dimensão definida, largura ou altura, e ressalto a imagem para que a outra dimensão seja resized automaticamente com base na taxa de proporção bloqueada. Por padrão, ela cortará a imagem do centro pelas dimensões restantes. Por exemplo, se você definir uma versão de 100px de largura e 50px de altura e sua imagem original tiver 1000px de largura e 800px de altura, ela será recortada para que a dimensão 800px agora seja 50px e a dimensão 1000px (agora 62,5px) seja cortada do centro da imagem.
  
As etapas são relativamente simples, mas para que as imagens usem as representações, as representações precisam estar no site SharePoint antes de adicionar as imagens. Além disso, você também precisa ter os recursos SharePoint Infraestrutura de Publicação do Servidor (Nível do Conjunto de Sites) e SharePoint de Publicação do Servidor (Nível do Site).
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Adicionar uma versão de imagem para acelerar o carregamento da página
  
1. Verifique se a conta de usuário que está executando esse procedimento tem, no mínimo, permissões de design para o site de nível superior do conjunto de sites e se o site está sendo publicado em uma página da Web.

2. Em um navegador da Web, vá para o site de nível superior do conjunto de sites de publicação.

3. Escolha o ícone de **configurações**.

4. Na página **Site Configurações,** na seção **Aparência,** você verá as representações de imagem integrados.

    Você pode usar as representações fora da caixa ou escolher **Representações de** Imagem para criar uma nova.

    ![Captura de tela da Rendição de Imagem](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. Na página **Representações de Imagem**, escolha **Adicionar novo item**.

    ![Captura de tela de Adicionar Novo Item](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Na página **Nova representação de imagem**, na caixa **nome**, digite um nome para a representação.

7. Nas caixas de texto **Largura** e **Altura**, digite a largura e a altura, em pixels, da representação e, em seguida, escolha **Salvar**.

    ![Captura de tela do Nome da Representação de Imagem](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Recorte personalizado com representações de imagem

Por padrão, uma representação de imagem é gerada a partir do centro da imagem. Você pode ajustar a representação de imagem para imagens individuais, cortando a parte da imagem que você deseja usar. Você pode cortar as imagens individualmente, por interpretação. O recorte das imagens acelera o carregamento da página usando o cache de blob do SharePoint para criar uma versão da imagem para cada versão. Dessa forma, a carga do servidor é reduzida porque a imagem é resized apenas uma vez e está pronta para servir aos usuários finais várias vezes. Para obter mais informações sobre como cortar uma versão de imagem, consulte [Crop an image rendition](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels).
