---
title: Personalizar o tema do Office 365 da sua organização
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 8275da91-7a48-4591-94ab-3123a3f79530
description: 'Saiba como alterar o tema padrão do Office 365 e personalizá-lo para corresponder ao logotipo ou à cor da empresa. '
ms.openlocfilehash: 9d83abb919cfb9f6ea3c804d9c5d934614f35285
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42360632"
---
# <a name="customize-the-office-365-theme-for-your-organization"></a>Personalizar o tema do Office 365 da sua organização

Saiba como personalizar seu tema no centro de administração do Microsoft 365. Como administrador da sua assinatura do Office 365 para empresas, você pode alterar o tema padrão que aparece na barra de navegação superior para todos na organização. Você pode adicionar o logotipo da empresa e alterar as cores para que correspondam ao restante da marca. Você pode até mesmo adicionar um link de destino para que os usuários naveguem quando selecionam o logotipo. Você pode ver aqui o tema padrão e o resultado do tema personalizado no Office 365.
  
![Tema padrão do Office 365 e tema personalizado do Office 365](../../media/e2cbc922-b424-4683-8c5c-fdbcbd0ce844.png)
  
## <a name="customize-your-theme-in-the-admin-center"></a>Personalizar seu tema no centro de administração

1. No centro de administração, vá para as **** \> **configurações**de configurações e, em seguida, escolha a guia **perfil da organização** .

2. Na guia **perfil da organização** , escolha **temas personalizados**.

3. No painel **temas alfandegários** , altere os elementos de tema desejados para sua organização:
    
  - **Usar uma imagem de logotipo personalizada**: escolha se deseja usar uma imagem de uma URL ou carregar uma imagem. Se você usar uma URL, certifique-se de que a URL usa HTTPS e tenha 200 x 30 pixels de qualquer formato de qualquer tamanho. Você pode carregar um logotipo abaixo de 10 KB 200 x 30 pixels no formato JPG, PNG, GIF ou SVG.

    > [!NOTE]
    > Para que o logotipo apareça no aplicativo móvel do SharePoint, use somente imagens SVG. As imagens carregadas em qualquer outro formato não são exibidas no aplicativo. Os logotipos não são clicados no aplicativo móvel do SharePoint.
    
  - **Tornar o logotipo clicado**: você pode usar o logotipo na barra de navegação como um link para qualquer recurso da empresa. Você pode digitar a URL para o logotipo aqui, começando com http://ou https://. Isso é opcional.
    
  - **Selecionar imagem de plano de fundo**: selecione a imagem e carregue seu próprio jpg, png ou GIF com uma resolução de 1366 x 50 pixels, não maior que 15 KB. Esta imagem de tela de fundo aparece na barra de navegação superior em cada página.
    
    > [!NOTE]
    > As imagens que contêm texto podem não ser exibidas como esperado. Os elementos internos que são exibidos à direita e à esquerda da barra de navegação podem variar entre os serviços e seu texto pode ficar escondido por esses elementos. Devido à natureza dinâmica da barra de navegação, no momento não é possível fornecer orientações sobre enchimento de imagem, o que resulta em uma experiência inconsistente. 
    
  - **Cor da barra de navegação**: selecione uma cor a ser usada para o plano de fundo da barra de navegação. Ela é exibida na parte superior de cada página.
    
  - **Texto e ícones**: Selecione uma cor para usar para o texto e ícones na barra de navegação superior.
    
  - **Cor de ênfase**: selecione uma cor a ser usada para o botão da barra de navegação cor e destaques da página, como botões e texto em determinados aplicativos.

   - **Impedir que os usuários substituam o tema**: inverter esta opção para impedir que os usuários escolham seu próprio tema da nossa seleção de temas. Isso não impede que os usuários sejam capazes de definir um tema de alto contraste.
      
  - **Mostrar o nome de usuário**: escolha se deseja mostrar o nome completo de um usuário no ponto de entrada para o gerente de contas no canto superior direito da página quando o usuário está conectado. Por padrão, os usuários verão sua foto ou suas iniciais se uma foto ainda não tiver sido carregada.
    
4. Selecione **Salvar alterações**.
    
Você verá seu novo tema no centro de administração imediatamente e após um pequeno atraso, verá-o em todo o Office 365, incluindo as páginas do Outlook e do SharePoint. É possível remover as cores ou o ícone personalizado a qualquer momento. Basta retornar à página do tema e selecionar **remover temas personalizados**.
  
## <a name="best-practices"></a>Práticas Recomendadas

Ao escolher uma **imagem de logotipo**, recomendamos o uso de um tipo de arquivo SVG, sempre que possível, para que o logotipo tenha uma aparência de alta resolução em todas as telas e em todos os níveis de zoom.

Ao escolher cores personalizadas, escolha uma **cor de plano de fundo da barra de navegação** que tenha uma taxa de contraste alto com a imagem de **logotipo** que você selecionou. Escolha também uma cor de **texto e ícones** com uma taxa de contraste alto para a **cor de plano de fundo da barra de navegação** para garantir que todos os textos e ícones sejam facilmente visíveis.

Ao escolher cores personalizadas, escolha uma **cor de ênfase** que aparece bem em um plano de fundo branco ou claro. A **cor de destaque** é usada para colorir alguns links e botões que aparecem em um plano de fundo branco ou claro. Por exemplo, a **cor de destaque** é usada para colorir elementos na caixa de entrada de um usuário e em sua página do portal do Office.com. 
  
A taxa de contraste recomendada entre a cor de plano de fundo, o ícone ou o texto é 4,5:1.

Veja a seguir um gráfico de fluxo simples para ajudá-lo a se configurar rapidamente com um tema 365 personalizado visualmente atraente para sua organização:
  - Eu gostaria de usar uma versão colorida do nosso logotipo.
    - Recomendamos as seguintes configurações:
      - **Imagem do logotipo**: o logotipo colorido da sua organização.
      - **Cor da barra de navegação**: uma cor neutra. Recomendamos #FAF9F7 para uma cor clara e #252423 para uma cor escura.
      - **Cor de texto e ícone**: uma cor para comparar a **cor da barra de navegação**. Recomendamos #FAF9F7 para uma cor clara e #252423 para uma cor escura.
      - **Cor de ênfase**: uma cor de marca escura. Com determinados aplicativos, essa cor deve estar visível em um plano de fundo claro.
  - Eu gostaria de usar uma versão neutra do nosso logotipo e representar a cor na barra de navegação.
    - Recomendamos as seguintes configurações:
      - **Imagem do logotipo**: o logotipo neutro da sua organização.
      - **Cor da barra de navegação**: uma cor de marca que contrasta com o logotipo.
      - **Cor de texto e ícone**: escolha uma cor que contraste contra a cor da marca escolhida para a **cor da barra de navegação**. Recomendamos #252423 para uma cor escura e #FAF9F7 para uma cor clara.
      - **Cor de ênfase**: uma cor de marca escura. Com determinados aplicativos, essa cor deve estar visível em um plano de fundo claro.
  
## <a name="related-articles"></a>Artigos relacionados

[Adicionar blocos personalizados à página "Meus aplicativos" e ao inicializador de aplicativos](../manage/customize-the-app-launcher.md)
  
  

