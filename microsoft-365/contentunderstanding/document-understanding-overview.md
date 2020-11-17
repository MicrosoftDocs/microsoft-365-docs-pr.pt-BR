---
title: Visão geral da compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Obtenha uma visão geral da compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: b26ed9a9ed9b8d1f332ccf14377660e634349b3d
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087362"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="141dd-103">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="141dd-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="141dd-104">A compreensão de documentos usa modelos de inteligência artificial (IA) para automatizar a classificação de arquivos e a extração de informações.</span><span class="sxs-lookup"><span data-stu-id="141dd-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="141dd-105">Ele funciona melhor com documentos não estruturados, como cartas ou contratos.</span><span class="sxs-lookup"><span data-stu-id="141dd-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="141dd-106">Esses documentos devem ter texto que pode ser identificado com base em frases ou padrões.</span><span class="sxs-lookup"><span data-stu-id="141dd-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="141dd-107">O texto identificado designa o tipo de arquivo (sua classificação) e o que você deseja extrair (suas extrações).</span><span class="sxs-lookup"><span data-stu-id="141dd-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="141dd-108">Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) para saber mais sobre os exemplos de cenários da compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="141dd-108">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="141dd-109">Os modelos de compreensão de documentos são criados e gerenciados em um tipo de site do SharePoint chamado *centro de conteúdo*.</span><span class="sxs-lookup"><span data-stu-id="141dd-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="141dd-110">Quando aplicada a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que possui colunas para armazenar as informações que estão sendo extraídas.</span><span class="sxs-lookup"><span data-stu-id="141dd-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="141dd-111">O tipo de conteúdo que você cria é armazenado na galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="141dd-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="141dd-112">Você também pode optar por usar os tipos de conteúdo existentes para usar o esquema.</span><span class="sxs-lookup"><span data-stu-id="141dd-112">You can also choose to use existing content types to use their schema.</span></span>

<span data-ttu-id="141dd-113">Adicione se *Classificadores* e *Extratores* ao seu modelo de compreensão de documentos para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="141dd-113">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="141dd-114">Os classificadores são usados para identificar e classificar os documentos que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="141dd-114">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="141dd-115">Por exemplo, um classificador pode ser "treinado" para identificar toda a renovação de *documentos que são carregados na biblioteca*.</span><span class="sxs-lookup"><span data-stu-id="141dd-115">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="141dd-116">O tipo de conteúdo de renovação de contrato é definido por você quando você cria seu classificador.</span><span class="sxs-lookup"><span data-stu-id="141dd-116">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="141dd-117">Os extratores recebem informações desses documentos.</span><span class="sxs-lookup"><span data-stu-id="141dd-117">Extractors pull information from these documents.</span></span> <span data-ttu-id="141dd-118">Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *Data de início do serviço* e  *Cliente* para cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="141dd-118">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="141dd-119">Você pode usar os arquivos de exemplo para treinar e testar seus separadores e extrações em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="141dd-119">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="141dd-120">Os arquivos de exemplo fornecem exemplos ao seu modelo sobre o que procurar ao tentar identificar e extrair dados de arquivos.</span><span class="sxs-lookup"><span data-stu-id="141dd-120">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="141dd-121">Por exemplo, você treina os classificadores e os extratores da renovação de contrato com exemplos de documentos de renovação de contrato que a sua empresa usa.</span><span class="sxs-lookup"><span data-stu-id="141dd-121">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="141dd-122">Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="141dd-122">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="141dd-123">Depois de publicar seu modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="141dd-123">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  



## <a name="see-also"></a><span data-ttu-id="141dd-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="141dd-124">See Also</span></span>
[<span data-ttu-id="141dd-125">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="141dd-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="141dd-126">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="141dd-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="141dd-127">Criar um centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="141dd-127">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="141dd-128">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="141dd-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="141dd-129">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="141dd-129">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="141dd-130">Diferença entre um modelo de compreensão de documentos e um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="141dd-130">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="141dd-131">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="141dd-131">Form processing overview</span></span>](form-processing-overview.md)
