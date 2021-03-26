---
title: Visão geral da compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenha uma visão geral da compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: 73e217e458fb9e1ccad8b64ffc81a6c9522a04f4
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222750"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="267ba-103">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="267ba-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="267ba-104">A compreensão de documentos usa modelos de inteligência artificial (IA) para automatizar a classificação de arquivos e a extração de informações.</span><span class="sxs-lookup"><span data-stu-id="267ba-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="267ba-105">Ele funciona melhor com documentos não estruturados, como cartas ou contratos.</span><span class="sxs-lookup"><span data-stu-id="267ba-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="267ba-106">Esses documentos devem ter texto que pode ser identificado com base em frases ou padrões.</span><span class="sxs-lookup"><span data-stu-id="267ba-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="267ba-107">O texto identificado designa o tipo de arquivo (sua classificação) e o que você deseja extrair (suas extrações).</span><span class="sxs-lookup"><span data-stu-id="267ba-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="267ba-108">Confira [Adoção do SharePoint Syntex: guia de introdução](./adoption-getstarted.md) para saber mais sobre os exemplos de cenários da compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="267ba-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="267ba-109">Os modelos de compreensão de documentos são criados e gerenciados em um tipo de site do SharePoint chamado *centro de conteúdo*.</span><span class="sxs-lookup"><span data-stu-id="267ba-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="267ba-110">Quando aplicada a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que possui colunas para armazenar as informações que estão sendo extraídas.</span><span class="sxs-lookup"><span data-stu-id="267ba-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="267ba-111">O tipo de conteúdo que você cria é armazenado na galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="267ba-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="267ba-112">Você também pode optar por usar os tipos de conteúdo existentes para usar o esquema.</span><span class="sxs-lookup"><span data-stu-id="267ba-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="267ba-113">Tipos de conteúdo selados ou somente leitura não podem ser atualizados e, assim, não podem ser usados em um modelo.</span><span class="sxs-lookup"><span data-stu-id="267ba-113">Read-only or sealed content types cannot be updated, so they cannot be used in a model.</span></span>

<span data-ttu-id="267ba-114">Adicione se *Classificadores* e *Extratores* ao seu modelo de compreensão de documentos para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="267ba-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="267ba-115">Os classificadores são usados para identificar e classificar os documentos que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="267ba-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="267ba-116">Por exemplo, um classificador pode ser "treinado" para identificar toda a renovação de *documentos que são carregados na biblioteca*.</span><span class="sxs-lookup"><span data-stu-id="267ba-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="267ba-117">O tipo de conteúdo de renovação de contrato é definido por você quando você cria seu classificador.</span><span class="sxs-lookup"><span data-stu-id="267ba-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="267ba-118">Os extratores recebem informações desses documentos.</span><span class="sxs-lookup"><span data-stu-id="267ba-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="267ba-119">Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *Data de início do serviço* e  *Cliente* para cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="267ba-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="267ba-120">Você pode usar os arquivos de exemplo para treinar e testar seus separadores e extrações em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="267ba-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="267ba-121">Os arquivos de exemplo fornecem exemplos ao seu modelo sobre o que procurar ao tentar identificar e extrair dados de arquivos.</span><span class="sxs-lookup"><span data-stu-id="267ba-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="267ba-122">Por exemplo, você treina os classificadores e os extratores da renovação de contrato com exemplos de documentos de renovação de contrato que a sua empresa usa.</span><span class="sxs-lookup"><span data-stu-id="267ba-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="267ba-123">Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="267ba-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="267ba-124">Depois de publicar seu modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="267ba-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

### <a name="file-limitations"></a><span data-ttu-id="267ba-125">Limitações de arquivo</span><span class="sxs-lookup"><span data-stu-id="267ba-125">File limitations</span></span>

<span data-ttu-id="267ba-126">Os modelos de compreensão de documentos usam a tecnologia reconhecimento óptico de caracteres (OCR) para digitalizar PDFs, imagens e arquivos TIFF, tanto quando você treina um modelo com arquivos de exemplo como quando executa o modelo em arquivos em uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="267ba-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="267ba-127">Observe as seguintes diferenças em relação aos arquivos baseados em texto do Microsoft Office e arquivos digitalizados por OCR (PDF, imagem ou TIFF):</span><span class="sxs-lookup"><span data-stu-id="267ba-127">Note the following differences in regards to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="267ba-128">Arquivos do Office: truncamos em 64000 caracteres (no treinamento e quando executado em arquivos em uma biblioteca de documentos).</span><span class="sxs-lookup"><span data-stu-id="267ba-128">Office files: We truncate at 64K characters (in training and when run against files in a document library).</span></span>
- <span data-ttu-id="267ba-129">Arquivos digitalizados por OCR: há um limite de 20 páginas.</span><span class="sxs-lookup"><span data-stu-id="267ba-129">OCR-scanned files: There is a 20 page limit.</span></span>  

#### <a name="supported-file-types"></a><span data-ttu-id="267ba-130">Tipos de arquivo compatíveis</span><span class="sxs-lookup"><span data-stu-id="267ba-130">Supported file types</span></span>

<span data-ttu-id="267ba-131">Os modelos de compreensão de documentos são compatíveis com os seguintes tipos de arquivo:</span><span class="sxs-lookup"><span data-stu-id="267ba-131">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="267ba-132">doc</span><span class="sxs-lookup"><span data-stu-id="267ba-132">doc</span></span>
- <span data-ttu-id="267ba-133">docx</span><span class="sxs-lookup"><span data-stu-id="267ba-133">docx</span></span>
- <span data-ttu-id="267ba-134">eml</span><span class="sxs-lookup"><span data-stu-id="267ba-134">eml</span></span>
- <span data-ttu-id="267ba-135">HEIC</span><span class="sxs-lookup"><span data-stu-id="267ba-135">heic</span></span>
- <span data-ttu-id="267ba-136">HEIF</span><span class="sxs-lookup"><span data-stu-id="267ba-136">heif</span></span>
- <span data-ttu-id="267ba-137">htm</span><span class="sxs-lookup"><span data-stu-id="267ba-137">htm</span></span>
- <span data-ttu-id="267ba-138">HTML</span><span class="sxs-lookup"><span data-stu-id="267ba-138">html</span></span>
- <span data-ttu-id="267ba-139">JPEG</span><span class="sxs-lookup"><span data-stu-id="267ba-139">jpeg</span></span>
- <span data-ttu-id="267ba-140">jpg</span><span class="sxs-lookup"><span data-stu-id="267ba-140">jpg</span></span>
- <span data-ttu-id="267ba-141">Markdown</span><span class="sxs-lookup"><span data-stu-id="267ba-141">markdown</span></span>
- <span data-ttu-id="267ba-142">md</span><span class="sxs-lookup"><span data-stu-id="267ba-142">md</span></span>
- <span data-ttu-id="267ba-143">msg</span><span class="sxs-lookup"><span data-stu-id="267ba-143">msg</span></span>
- <span data-ttu-id="267ba-144">pdf</span><span class="sxs-lookup"><span data-stu-id="267ba-144">pdf</span></span>
- <span data-ttu-id="267ba-145">PNG</span><span class="sxs-lookup"><span data-stu-id="267ba-145">png</span></span>
- <span data-ttu-id="267ba-146">ppt</span><span class="sxs-lookup"><span data-stu-id="267ba-146">ppt</span></span>
- <span data-ttu-id="267ba-147">pptx</span><span class="sxs-lookup"><span data-stu-id="267ba-147">pptx</span></span>
- <span data-ttu-id="267ba-148">rtf</span><span class="sxs-lookup"><span data-stu-id="267ba-148">rtf</span></span>
- <span data-ttu-id="267ba-149">tif</span><span class="sxs-lookup"><span data-stu-id="267ba-149">tif</span></span>
- <span data-ttu-id="267ba-150">tiff</span><span class="sxs-lookup"><span data-stu-id="267ba-150">tiff</span></span>
- <span data-ttu-id="267ba-151">txt</span><span class="sxs-lookup"><span data-stu-id="267ba-151">txt</span></span>
- <span data-ttu-id="267ba-152">xls</span><span class="sxs-lookup"><span data-stu-id="267ba-152">xls</span></span>
- <span data-ttu-id="267ba-153">xlsx</span><span class="sxs-lookup"><span data-stu-id="267ba-153">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="267ba-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="267ba-154">See Also</span></span>
[<span data-ttu-id="267ba-155">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="267ba-155">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="267ba-156">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="267ba-156">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="267ba-157">Criar um centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="267ba-157">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="267ba-158">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="267ba-158">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="267ba-159">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="267ba-159">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="267ba-160">Diferença entre um modelo de compreensão de documentos e um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="267ba-160">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="267ba-161">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="267ba-161">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="267ba-162">Modo de acessibilidade do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="267ba-162">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)