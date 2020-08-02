---
title: Visão geral da compreensão do documento (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenha uma visão geral da compreensão do documento no Project Cortex.
ms.openlocfilehash: 13b0aa3742c6cf1c0c1123996c683d13c6577876
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46536871"
---
# <a name="document-understanding-overview-preview"></a><span data-ttu-id="fc53e-103">Visão geral da compreensão do documento (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="fc53e-103">Document understanding overview (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="fc53e-104">O Project Cortex está atualmente em versão prévia.</span><span class="sxs-lookup"><span data-stu-id="fc53e-104">Project Cortex is currently in Preview.</span></span> <span data-ttu-id="fc53e-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="fc53e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="fc53e-106">Noções básicas sobre documentos usa modelos AI para automatizar a classificação de arquivos e extração de informações.</span><span class="sxs-lookup"><span data-stu-id="fc53e-106">Document understanding uses AI models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="fc53e-107">Ele funciona melhor com documentos não estruturados, como cartas ou contratos.</span><span class="sxs-lookup"><span data-stu-id="fc53e-107">It works best with unstructured documents, like letters or contracts.</span></span> <span data-ttu-id="fc53e-108">Os documentos devem ter texto que possa ser identificado com base em frases ou padrões.</span><span class="sxs-lookup"><span data-stu-id="fc53e-108">The documents should have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="fc53e-109">O texto identificado pode designar o tipo de arquivo (sua classificação) e o que você gostaria de extrair (seus extratores).</span><span class="sxs-lookup"><span data-stu-id="fc53e-109">The identified text can designate both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="fc53e-110">Documentos entendendo modelos são criados e gerenciados em um tipo de site do SharePoint chamado de centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fc53e-110">Document understanding models are created and managed in a type of SharePoint site called a content center.</span></span> <span data-ttu-id="fc53e-111">Quando aplicado a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que tem colunas para armazenar as informações extraídas.</span><span class="sxs-lookup"><span data-stu-id="fc53e-111">When applied to a SharePoint document library, the model is associated with a content type which has columns to store the information extracted.</span></span> <span data-ttu-id="fc53e-112">O tipo de conteúdo que você cria é armazenado na Galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fc53e-112">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="fc53e-113">Você também pode optar por usar tipos de conteúdo existentes para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="fc53e-113">You can also choose to use existing content types in order to use their schema.</span></span>

<span data-ttu-id="fc53e-114">Você pode adicionar *classificadores* e *extratores* ao seu documento entendendo modelos para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fc53e-114">You can add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="fc53e-115">Os classificadores são usados para identificar e classificar documentos que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="fc53e-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="fc53e-116">Por exemplo, um classificador pode ser "treinado" para identificar todos os documentos de *renovação de contrato* que são carregados na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="fc53e-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="fc53e-117">O tipo de conteúdo de renovação de contrato é definido por você quando você cria o classificador.</span><span class="sxs-lookup"><span data-stu-id="fc53e-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="fc53e-118">Os extratores recebem informações desses documentos.</span><span class="sxs-lookup"><span data-stu-id="fc53e-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="fc53e-119">Por exemplo, para todos os documentos de renovação de contrato identificados na sua biblioteca de documentos, as colunas serão exibidas no modo de exibição que também mostrará a *data de início* e o *cliente* para cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="fc53e-119">For example, for all contract renewal documents that are identified in your document library, columns will display in your view that will also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="fc53e-120">Você usa arquivos de exemplo para treinar e testar classificadores e extratores no modelo.</span><span class="sxs-lookup"><span data-stu-id="fc53e-120">You use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="fc53e-121">Arquivos de exemplo fornecem exemplos de modelo do que procurar ao tentar identificar e extrair dados de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fc53e-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="fc53e-122">Por exemplo, você treinaria os classificadores e os extratores de renovação de contrato com exemplos de documentos de renovação de contrato que sua empresa trabalha.</span><span class="sxs-lookup"><span data-stu-id="fc53e-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="fc53e-123">Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="fc53e-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="fc53e-124">Após publicar o modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="fc53e-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="fc53e-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="fc53e-125">See Also</span></span>
[<span data-ttu-id="fc53e-126">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="fc53e-126">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="fc53e-127">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="fc53e-127">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="fc53e-128">[Criar um centro](create-a-content-center.md) 
 de conteúdo [Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="fc53e-128">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="fc53e-129">[Aplicar um modelo](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="fc53e-129">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="fc53e-130">Diferença entre um documento entendendo e um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="fc53e-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="fc53e-131">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="fc53e-131">Form processing overview</span></span>](form-processing-overview.md)




