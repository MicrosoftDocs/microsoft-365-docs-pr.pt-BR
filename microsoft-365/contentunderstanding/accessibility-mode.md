---
title: 'Modo de acessibilidade do SharePoint Syntex '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Saiba como usar o modo de acessibilidade ao treinar um modelo em SharePoint Syntex.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515143"
---
# <a name="sharepoint-syntex-accessibility-mode"></a>Modo de acessibilidade do SharePoint Syntex

No [SharePoint Syntex,](index.md)os usuários podem ativar o modo de acessibilidade em todos os estágios do treinamento de modelo (rótulo, trem, teste) ao trabalhar com documentos de exemplo. O uso do modo de acessibilidade pode ajudar os usuários de baixa visão a facilitar a acessibilidade do teclado à medida que navegam e rotulam itens no visualizador de documentos.

Isso ajuda os usuários a usar seus teclados para navegar pelo texto no visualizador de documentos e ouvir uma narração não apenas dos valores selecionados, mas também de ações (como rotular ou remover a rotulagem do texto selecionado) ou valores de rótulo previstos à medida que você treinar o modelo com documentos de exemplo adicionais. 


![Modo de acessibilidade](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a>Requisitos

Para ouvir o áudio da narração, certifique-se de ativar o aplicativo [Narrador em](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) suas Narrador no sistema Windows 10.

![Ativar Narrador](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a>Rotulagem para usuários de teclado

Para usuários de teclado que usam o modo de acessibilidade, se você estiver rotulando texto em um documento de exemplo no visualizador, poderá usar as seguintes teclas:

- Guia: move você para frente e seleciona a próxima palavra.
- Guia + Turno: move você para trás e seleciona a palavra anterior.
- Insira: rotule ou remova um rótulo da palavra selecionada.
- Seta à direita: move você para frente através de caracteres individuais em uma palavra selecionada.
- Seta à esquerda: move você para trás através de caracteres individuais em uma palavra selecionada.

> [!NOTE]
> Se você estiver rotulando várias palavras para um único rótulo, precisará rotular cada palavra.


## <a name="narration"></a>Narração

Para Narrador usuários que usam o modo de acessibilidade, use a mesma navegação de teclado descrita para que os usuários de teclado acessem o documento de exemplo no visualizador.

À medida que você navega pelos documentos de exemplo e valores de cadeia de caracteres de rótulo, Narrador dará ao usuário os seguintes prompts de áudio:

- Quando você usa o teclado para navegar pelo visualizador de documentos, Narrador áudio irá estado da cadeia de caracteres selecionada.
- Em uma cadeia de caracteres selecionada, Narrador áudio irá estado cada caractere na cadeia de caracteres conforme você os seleciona usando as teclas de seta esquerda ou direita.
- Se você selecionar uma cadeia de caracteres rotulada, Narrador o valor será "rotulado".  Por exemplo, se o valor do rótulo for "Contoso", ele irá dizer "Costoso rotulado". 
- Na guia treinamento, se você selecionar uma cadeia de caracteres no visualizador de documentos que tenha sido prevista apenas, Narrador áudio irá estado o valor e, em seguida, "previsto". Isso ocorre quando o treinamento prevê um valor no arquivo que não corresponderá ao que foi rotulado pelo usuário.
- Na guia treinamento, se você selecionar uma cadeia de caracteres no visualizador de documentos que foi rotulada e prevista, Narrador áudio irá estado o valor e, em seguida, "rotulado e previsto". Isso ocorre quando o treinamento é bem-sucedido e há uma combinação entre um valor previsto e o rótulo do usuário.



Depois que uma cadeia de caracteres for rotulada ou um rótulo tiver sido removido no visualizador, Narrador áudio avisará você para salvar suas alterações antes de sair.

## <a name="see-also"></a>Confira também

[Criar um extrator](create-an-extractor.md)</br>

[Criar um classificador](create-a-classifier.md)</br>










 


  
  



