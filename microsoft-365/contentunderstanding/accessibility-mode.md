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
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="b1644-103">Modo de acessibilidade do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b1644-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="b1644-104">No [SharePoint Syntex,](index.md)os usuários podem ativar o modo de acessibilidade em todos os estágios do treinamento de modelo (rótulo, trem, teste) ao trabalhar com documentos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="b1644-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="b1644-105">O uso do modo de acessibilidade pode ajudar os usuários de baixa visão a facilitar a acessibilidade do teclado à medida que navegam e rotulam itens no visualizador de documentos.</span><span class="sxs-lookup"><span data-stu-id="b1644-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="b1644-106">Isso ajuda os usuários a usar seus teclados para navegar pelo texto no visualizador de documentos e ouvir uma narração não apenas dos valores selecionados, mas também de ações (como rotular ou remover a rotulagem do texto selecionado) ou valores de rótulo previstos à medida que você treinar o modelo com documentos de exemplo adicionais.</span><span class="sxs-lookup"><span data-stu-id="b1644-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![Modo de acessibilidade](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="b1644-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1644-108">Requirements</span></span>

<span data-ttu-id="b1644-109">Para ouvir o áudio da narração, certifique-se de ativar o aplicativo [Narrador em](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) suas Narrador no sistema Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b1644-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![Ativar Narrador](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="b1644-111">Rotulagem para usuários de teclado</span><span class="sxs-lookup"><span data-stu-id="b1644-111">Labeling for keyboard users</span></span>

<span data-ttu-id="b1644-112">Para usuários de teclado que usam o modo de acessibilidade, se você estiver rotulando texto em um documento de exemplo no visualizador, poderá usar as seguintes teclas:</span><span class="sxs-lookup"><span data-stu-id="b1644-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="b1644-113">Guia: move você para frente e seleciona a próxima palavra.</span><span class="sxs-lookup"><span data-stu-id="b1644-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="b1644-114">Guia + Turno: move você para trás e seleciona a palavra anterior.</span><span class="sxs-lookup"><span data-stu-id="b1644-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="b1644-115">Insira: rotule ou remova um rótulo da palavra selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1644-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="b1644-116">Seta à direita: move você para frente através de caracteres individuais em uma palavra selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1644-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="b1644-117">Seta à esquerda: move você para trás através de caracteres individuais em uma palavra selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1644-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="b1644-118">Se você estiver rotulando várias palavras para um único rótulo, precisará rotular cada palavra.</span><span class="sxs-lookup"><span data-stu-id="b1644-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="b1644-119">Narração</span><span class="sxs-lookup"><span data-stu-id="b1644-119">Narration</span></span>

<span data-ttu-id="b1644-120">Para Narrador usuários que usam o modo de acessibilidade, use a mesma navegação de teclado descrita para que os usuários de teclado acessem o documento de exemplo no visualizador.</span><span class="sxs-lookup"><span data-stu-id="b1644-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="b1644-121">À medida que você navega pelos documentos de exemplo e valores de cadeia de caracteres de rótulo, Narrador dará ao usuário os seguintes prompts de áudio:</span><span class="sxs-lookup"><span data-stu-id="b1644-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="b1644-122">Quando você usa o teclado para navegar pelo visualizador de documentos, Narrador áudio irá estado da cadeia de caracteres selecionada.</span><span class="sxs-lookup"><span data-stu-id="b1644-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="b1644-123">Em uma cadeia de caracteres selecionada, Narrador áudio irá estado cada caractere na cadeia de caracteres conforme você os seleciona usando as teclas de seta esquerda ou direita.</span><span class="sxs-lookup"><span data-stu-id="b1644-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="b1644-124">Se você selecionar uma cadeia de caracteres rotulada, Narrador o valor será "rotulado".</span><span class="sxs-lookup"><span data-stu-id="b1644-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="b1644-125">Por exemplo, se o valor do rótulo for "Contoso", ele irá dizer "Costoso rotulado".</span><span class="sxs-lookup"><span data-stu-id="b1644-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="b1644-126">Na guia treinamento, se você selecionar uma cadeia de caracteres no visualizador de documentos que tenha sido prevista apenas, Narrador áudio irá estado o valor e, em seguida, "previsto".</span><span class="sxs-lookup"><span data-stu-id="b1644-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="b1644-127">Isso ocorre quando o treinamento prevê um valor no arquivo que não corresponderá ao que foi rotulado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b1644-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="b1644-128">Na guia treinamento, se você selecionar uma cadeia de caracteres no visualizador de documentos que foi rotulada e prevista, Narrador áudio irá estado o valor e, em seguida, "rotulado e previsto".</span><span class="sxs-lookup"><span data-stu-id="b1644-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="b1644-129">Isso ocorre quando o treinamento é bem-sucedido e há uma combinação entre um valor previsto e o rótulo do usuário.</span><span class="sxs-lookup"><span data-stu-id="b1644-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="b1644-130">Depois que uma cadeia de caracteres for rotulada ou um rótulo tiver sido removido no visualizador, Narrador áudio avisará você para salvar suas alterações antes de sair.</span><span class="sxs-lookup"><span data-stu-id="b1644-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1644-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1644-131">See Also</span></span>

[<span data-ttu-id="b1644-132">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="b1644-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="b1644-133">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="b1644-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



