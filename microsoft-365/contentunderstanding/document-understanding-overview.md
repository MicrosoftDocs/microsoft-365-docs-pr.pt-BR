---
title: Visão geral da compreensão do documento
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenha uma visão geral da compreensão do documento no Microsoft SharePoint Syntex.
ms.openlocfilehash: dd8731759d8f1cbea57d171fa7a803ffc4f1baa7
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294755"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="bdd2f-103">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="bdd2f-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="bdd2f-104">O documento entende o uso de modelos de inteligência artificial (AI) para automatizar a classificação de arquivos e a extração de informações.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="bdd2f-105">Ele funciona melhor com documentos não estruturados, como cartas ou contratos.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="bdd2f-106">Esses documentos devem ter texto que possa ser identificado com base em frases ou padrões.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="bdd2f-107">O texto identificado designa o tipo de arquivo que ele é (sua classificação) e o que você gostaria de extrair (seus extratores).</span><span class="sxs-lookup"><span data-stu-id="bdd2f-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

<span data-ttu-id="bdd2f-108">Documentos entendendo modelos são criados e gerenciados em um tipo de site do SharePoint chamado de *centro de conteúdo*.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-108">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="bdd2f-109">Quando aplicado a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo tem colunas para armazenar as informações extraídas.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-109">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="bdd2f-110">O tipo de conteúdo que você cria é armazenado na Galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-110">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="bdd2f-111">Você também pode optar por usar tipos de conteúdo existentes para usar seu esquema.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-111">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="bdd2f-112">Adicione *classificadores* e *extratores* ao seu documento entendendo os modelos para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bdd2f-112">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="bdd2f-113">Os classificadores são usados para identificar e classificar documentos que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-113">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="bdd2f-114">Por exemplo, um classificador pode ser "treinado" para identificar todos os documentos de *renovação de contrato* que são carregados na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-114">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="bdd2f-115">O tipo de conteúdo de renovação de contrato é definido por você quando você cria o classificador.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-115">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="bdd2f-116">Os extratores recebem informações desses documentos.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-116">Extractors pull information from these documents.</span></span> <span data-ttu-id="bdd2f-117">Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *data de início do serviço* e o  *cliente* para cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-117">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="bdd2f-118">Você pode usar arquivos de exemplo para treinar e testar seus classificadores e extratores no modelo.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-118">You can use sample files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="bdd2f-119">Arquivos de exemplo fornecem exemplos de modelo do que procurar ao tentar identificar e extrair dados de arquivos.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-119">Sample files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="bdd2f-120">Por exemplo, você treinaria os classificadores e os extratores de renovação de contrato com exemplos de documentos de renovação de contrato que sua empresa trabalha.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-120">For example, you would train your contract renewal classifiers and extractors with samples of contract renewal documents your company works with.</span></span> <span data-ttu-id="bdd2f-121">Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-121">You can also use sample files to test the effectiveness of your model.</span></span>

<span data-ttu-id="bdd2f-122">Após publicar o modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="bdd2f-122">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  


## <a name="see-also"></a><span data-ttu-id="bdd2f-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="bdd2f-123">See Also</span></span>
[<span data-ttu-id="bdd2f-124">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="bdd2f-124">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="bdd2f-125">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="bdd2f-125">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="bdd2f-126">[Criar um centro](create-a-content-center.md) 
 de conteúdo [Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</span><span class="sxs-lookup"><span data-stu-id="bdd2f-126">[Create a content center](create-a-content-center.md)
[Create a form processing model](create-a-form-processing-model.md)</span></span></br>
<span data-ttu-id="bdd2f-127">[Aplicar um modelo](apply-a-model.md) </span><span class="sxs-lookup"><span data-stu-id="bdd2f-127">[Apply a model](apply-a-model.md) </span></span>  
[<span data-ttu-id="bdd2f-128">Diferença entre um documento entendendo e um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="bdd2f-128">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)  
[<span data-ttu-id="bdd2f-129">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="bdd2f-129">Form processing overview</span></span>](form-processing-overview.md)
