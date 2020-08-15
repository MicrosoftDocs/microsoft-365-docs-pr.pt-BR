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
description: Saiba como usar as técnicas de agrupamento e minificação com o Web Essentials para reduzir as solicitações HTTP e o tempo necessário para carregar páginas no SharePoint Online.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686957"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minificação e agrupamento no SharePoint Online

Este artigo descreve como usar as técnicas de agrupamento e minificação com o Web Essentials para reduzir o número de solicitações HTTP e reduzir o tempo que leva para carregar páginas no SharePoint Online.
  
Ao personalizar seu site, você pode acabar adicionando um grande número de arquivos extras ao servidor para dar suporte à personalização. Adicionar JavaScript, CSS e imagens extras aumenta o número de solicitações HTTP para o servidor que, por sua vez, aumenta o tempo necessário para exibir uma página da Web. Se você tiver vários arquivos do mesmo tipo, pode incluir esses arquivos para fazer o download desses arquivos com mais rapidez.
  
Para arquivos JavaScript e CSS, você também pode usar uma abordagem chamada minificação, onde você reduz o tamanho total de arquivos removendo espaços em branco e outros caracteres que não são necessários.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minificação e agrupamento de arquivos JavaScript e CSS com o Web Essentials

Você pode usar software de terceiros, como o Web Essentials, para agrupar arquivos CSS e JavaScript.
  
> [!IMPORTANT]
> O Web Essentials é um projeto de terceiros, de código aberto, baseado na Comunidade. O software é uma extensão do Visual Studio 2012 e do Visual Studio 2013 e não tem suporte da Microsoft. Para baixar o Web Essentials, visite o site em [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
O Web Essentials oferece duas formas de agrupamento:
  
- . Bundle: para arquivos CSS e JavaScript
    
- . Sprite: para imagens (disponível somente no Visual Studio 2013)
    
Você pode usar o Web Essentials se tiver um recurso existente com alguns elementos de identidade visual que são referenciados dentro de uma página mestra personalizada, como:
  
![Captura de tela do elemento de marca na página mestra personalizada](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Para criar um TE000127218 e um pacote CSS no Web Essentials**
  
1. No Visual Studio, no Gerenciador de soluções, selecione os arquivos que você deseja incluir no pacote.
    
2. Clique com o botão direito do mouse nos arquivos selecionados e selecione **Web Essentials** \> **criar arquivo de pacote JavaScript** no menu de contexto. Por exemplo: 
    
    ![Captura de tela mostrando as opções do menu Web Essentials](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Exibindo os resultados do agrupamento de arquivos JavaScript e CSS

Quando você cria um pacote JavaScript e CSS, o Web Essentials cria um arquivo XML chamado arquivo de receita que identifica os arquivos JavaScript e CSS, bem como outras informações de configuração: 
  
![Captura de tela de arquivo de receita JavaScript e CSS](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Além disso, se o sinalizador reduza estiver definido como true na receita de agrupamento, os arquivos serão reduzidos em tamanho e agrupados. Isso significa que novas versões do empacotar minimizadas dos arquivos JavaScript foram criadas, que você pode fazer referência à sua página mestra.
  
![Captura de tela do sinalizador minify definido como verdadeiro](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Ao carregar uma página do seu site, você pode usar as ferramentas de desenvolvedor do navegador da Web, como o Internet Explorer 11, para ver o número de solicitações enviadas ao servidor e por quanto tempo cada arquivo levou para carregar.
  
A figura a seguir é o resultado do carregamento dos arquivos JavaScript e CSS antes do minificação.
  
![Captura de tela mostrando 80 itens sendo baixados](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Após agrupar os arquivos CSS e JavaScript juntos, o número de solicitações descartadas para 74 e cada arquivo demorou apenas um pouco mais do que os arquivos originais a serem baixados individualmente:
  
![Captura de tela mostrando 74 itens sendo baixados](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Após o agrupamento, o arquivo de pacote JavaScript é reduzido significativamente de 815KB para 365KB:
  
![Captura de tela mostrando tamanho do download reduzido](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Empacotando imagens criando uma imagem Sprite

Semelhante à forma como você agrupa arquivos JavaScript e CSS, é possível combinar vários ícones pequenos e outras imagens comuns em uma folha de Sprite maior e, em seguida, usar CSS para revelar as imagens individuais. Em vez de baixar cada imagem individual, o navegador da Web do usuário baixa a folha de Sprite e, em seguida, o armazena no computador local. Isso melhora o desempenho do carregamento da página, reduzindo o número de downloads e viagens de ida e segundo para o servidor Web.
  
 **Para criar uma imagem Sprite no Web Essentials**
  
1. No Visual Studio, no Gerenciador de soluções, selecione os arquivos que você deseja incluir no pacote.
    
2. Clique com o botão direito do mouse nos arquivos selecionados e, em seguida, selecione o **Web Essentials** \> **criar a imagem Sprite** no menu de contexto. Por exemplo: 
    
    ![Captura de tela mostrando como criar uma entidade gráfica de imagem](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Escolha um local para salvar o arquivo Sprite. O arquivo. Sprite é um arquivo XML que descreve as configurações e os arquivos no Sprite. As figuras a seguir mostram um exemplo de um arquivo PNG Sprite e seu arquivo XML. Sprite correspondente.
    
    ![Captura de tela de um arquivo de entidade gráfica](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Captura de tela de arquivo XML de entidade gráfica](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

