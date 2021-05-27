---
title: Visão geral da compreensão de documentos
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Obtenha uma visão geral da compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: 7e5818a929fa0f4554a7ee4ece460b4fe0d691aa
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683818"
---
# <a name="document-understanding-overview"></a><span data-ttu-id="191ee-103">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="191ee-103">Document understanding overview</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

<span data-ttu-id="191ee-104">A compreensão de documentos usa modelos de inteligência artificial (IA) para automatizar a classificação de arquivos e a extração de informações.</span><span class="sxs-lookup"><span data-stu-id="191ee-104">Document understanding uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="191ee-105">Ele funciona melhor com documentos não estruturados, como cartas ou contratos.</span><span class="sxs-lookup"><span data-stu-id="191ee-105">It works best with unstructured documents, such as letters or contracts.</span></span> <span data-ttu-id="191ee-106">Esses documentos devem ter texto que pode ser identificado com base em frases ou padrões.</span><span class="sxs-lookup"><span data-stu-id="191ee-106">These documents must have text that can be identified based on phrases or patterns.</span></span> <span data-ttu-id="191ee-107">O texto identificado designa o tipo de arquivo (sua classificação) e o que você deseja extrair (suas extrações).</span><span class="sxs-lookup"><span data-stu-id="191ee-107">The identified text designates both the type of file it is (its classification) and what you'd like to extract (its extractors).</span></span>

> [!NOTE]
> <span data-ttu-id="191ee-108">Confira [Adoção do SharePoint Syntex: guia de introdução](./adoption-getstarted.md) para saber mais sobre os exemplos de cenários da compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="191ee-108">See the [SharePoint Syntex adoption: Get started guide](./adoption-getstarted.md) for more information about document understanding scenario examples.</span></span>

<span data-ttu-id="191ee-109">Os modelos de compreensão de documentos são criados e gerenciados em um tipo de site do SharePoint chamado *centro de conteúdo*.</span><span class="sxs-lookup"><span data-stu-id="191ee-109">Document understanding models are created and managed in a type of SharePoint site called a *content center*.</span></span> <span data-ttu-id="191ee-110">Quando aplicada a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que possui colunas para armazenar as informações que estão sendo extraídas.</span><span class="sxs-lookup"><span data-stu-id="191ee-110">When applied to a SharePoint document library, the model is associated with a content type has columns to store the information being extracted.</span></span> <span data-ttu-id="191ee-111">O tipo de conteúdo que você cria é armazenado na galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="191ee-111">The content type you create is stored in the SharePoint content type gallery.</span></span> <span data-ttu-id="191ee-112">Você também pode optar por usar os tipos de conteúdo existentes para usar o esquema.</span><span class="sxs-lookup"><span data-stu-id="191ee-112">You can also choose to use existing content types to use their schema.</span></span>

> [!NOTE]
> <span data-ttu-id="191ee-113">Os tipos de conteúdo somente leitura ou de conteúdo não podem ser atualizados, portanto, não podem ser usados em um modelo.</span><span class="sxs-lookup"><span data-stu-id="191ee-113">Read-only or sealed content types cannot be updated, so they can't be used in a model.</span></span>

<span data-ttu-id="191ee-114">Adicione se *Classificadores* e *Extratores* ao seu modelo de compreensão de documentos para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="191ee-114">Add *classifiers* and *extractors* to your document understanding models to do the following:</span></span> 

- <span data-ttu-id="191ee-115">Os classificadores são usados para identificar e classificar os documentos que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="191ee-115">Classifiers are used to identify and classify documents that are uploaded to the document library.</span></span> <span data-ttu-id="191ee-116">Por exemplo, um classificador pode ser "treinado" para identificar toda a renovação de *documentos que são carregados na biblioteca*.</span><span class="sxs-lookup"><span data-stu-id="191ee-116">For example, a classifier can be "trained" to identify all *contract renewal* documents that are uploaded to the library.</span></span> <span data-ttu-id="191ee-117">O tipo de conteúdo de renovação de contrato é definido por você quando você cria seu classificador.</span><span class="sxs-lookup"><span data-stu-id="191ee-117">The contract renewal content type is defined by you when you create your classifier.</span></span>

- <span data-ttu-id="191ee-118">Os extratores recebem informações desses documentos.</span><span class="sxs-lookup"><span data-stu-id="191ee-118">Extractors pull information from these documents.</span></span> <span data-ttu-id="191ee-119">Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *Data de início do serviço* e  *Cliente* para cada documento de renovação de contrato.</span><span class="sxs-lookup"><span data-stu-id="191ee-119">For example, for all contract renewal documents identified in your document library, columns display in your view that also show the *Service Start Date* and  *Client* for each contract renewal document.</span></span> 

<span data-ttu-id="191ee-120">Você pode usar os arquivos de exemplo para treinar e testar seus separadores e extrações em seu modelo.</span><span class="sxs-lookup"><span data-stu-id="191ee-120">You can use example files to train and test your classifiers and extractors in your model.</span></span> <span data-ttu-id="191ee-121">Os arquivos de exemplo fornecem exemplos ao seu modelo sobre o que procurar ao tentar identificar e extrair dados de arquivos.</span><span class="sxs-lookup"><span data-stu-id="191ee-121">Example files provide your model examples of what to look for when trying to identify and extract data from files.</span></span> <span data-ttu-id="191ee-122">Por exemplo, você treina os classificadores e os extratores da renovação de contrato com exemplos de documentos de renovação de contrato que a sua empresa usa.</span><span class="sxs-lookup"><span data-stu-id="191ee-122">For example, you would train your contract renewal classifiers and extractors with examples of contract renewal documents your company works with.</span></span> <span data-ttu-id="191ee-123">Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="191ee-123">You can also use example files to test the effectiveness of your model.</span></span>

<span data-ttu-id="191ee-124">Depois de publicar seu modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="191ee-124">After publishing your model, use the content center to apply it to any SharePoint document library that you have access to.</span></span>  

## <a name="file-limitations"></a><span data-ttu-id="191ee-125">Limitações de arquivo</span><span class="sxs-lookup"><span data-stu-id="191ee-125">File limitations</span></span>

<span data-ttu-id="191ee-126">Os modelos de compreensão de documentos usam a tecnologia reconhecimento óptico de caracteres (OCR) para digitalizar PDFs, imagens e arquivos TIFF, tanto quando você treina um modelo com arquivos de exemplo como quando executa o modelo em arquivos em uma biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="191ee-126">Document understanding models use Optical Character Recognition (OCR) technology to scan PDFs, images, and TIFF files, both when you train a model with example files and when you run the model against files in a document library.</span></span>

<span data-ttu-id="191ee-127">Observe as seguintes diferenças em relação a arquivos baseados em texto do Microsoft Office e arquivos verificados por OCR (PDF, imagem ou TIFF):</span><span class="sxs-lookup"><span data-stu-id="191ee-127">Note the following differences with regard to Microsoft Office text-based files and OCR-scanned files (PDF, image, or TIFF):</span></span>

- <span data-ttu-id="191ee-128">Arquivos do Office: Truncado em 64.000 caracteres (no treinamento e quando executado em arquivos em uma biblioteca de documentos).</span><span class="sxs-lookup"><span data-stu-id="191ee-128">Office files: Truncated at 64,000 characters (in training and when run against files in a document library).</span></span>

- <span data-ttu-id="191ee-129">Arquivos digitalizados com OCR: há um limite de 20 páginas.</span><span class="sxs-lookup"><span data-stu-id="191ee-129">OCR-scanned files: There's a 20-page limit.</span></span>  

### <a name="requirements"></a><span data-ttu-id="191ee-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="191ee-130">Requirements</span></span>

<span data-ttu-id="191ee-131">O processamento de OCR funciona melhor em documentos que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="191ee-131">OCR processing works best on documents that meet the following requirements:</span></span>

- <span data-ttu-id="191ee-132">Nos formatos JPG, PNG ou PDF (texto ou digitalizado).</span><span class="sxs-lookup"><span data-stu-id="191ee-132">JPG, PNG, or PDF format (text or scanned).</span></span> <span data-ttu-id="191ee-133">PDFs inseridos por texto são melhores, pois não haverá erros na extração de caracteres e no local.</span><span class="sxs-lookup"><span data-stu-id="191ee-133">Text-embedded PDFs are better, because there won't be any errors in character extraction and location.</span></span>

- <span data-ttu-id="191ee-134">Se seus PDFs estão bloqueados por senha, você deve remover o bloqueio antes de enviar a eles.</span><span class="sxs-lookup"><span data-stu-id="191ee-134">If your PDFs are password-locked, you must remove the lock before submitting them.</span></span>

- <span data-ttu-id="191ee-135">O tamanho de arquivo combinado dos documentos usados para treinamento por coleção não deve exceder 50 MB, e documentos PDF não devem ter mais de 500 páginas.</span><span class="sxs-lookup"><span data-stu-id="191ee-135">The combined file size of the documents used for training per collection must not exceed 50 MB, and PDF documents shouldn't have more than 500 pages.</span></span>

- <span data-ttu-id="191ee-136">Para imagens, as dimensões devem estar entre 50 × 50 e 10.000 × 10.000 pixels.</span><span class="sxs-lookup"><span data-stu-id="191ee-136">For images, dimensions must be between 50 × 50 and 10,000 × 10,000 pixels.</span></span>
   > [!NOTE]
   > <span data-ttu-id="191ee-137">Imagens muito largas ou com dimensões ímpares (por exemplo, plantas terrárias) podem ficar truncadas no processo de OCR e perder precisão.</span><span class="sxs-lookup"><span data-stu-id="191ee-137">Images that are very wide or have odd dimensions (for example, floor plans) might get truncated in the OCR process and lose accuracy.</span></span>
 
- <span data-ttu-id="191ee-138">Para arquivos PDF, as dimensões devem ser de no máximo 17 x 17 polegadas, correspondentes aos tamanhos de papel Legal ou A3 e menores.</span><span class="sxs-lookup"><span data-stu-id="191ee-138">For PDF files, dimensions must be at most 17 x 17 inches, corresponding to Legal or A3 paper sizes and smaller.</span></span>

- <span data-ttu-id="191ee-139">Se digitalizados de documentos de papel, as digitalizações deverão ser imagens de alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="191ee-139">If scanned from paper documents, scans should be high-quality images.</span></span>

- <span data-ttu-id="191ee-140">Deve usar o alfabeto latino (caracteres em inglês).</span><span class="sxs-lookup"><span data-stu-id="191ee-140">Must use the Latin alphabet (English characters).</span></span>

> [!NOTE]
> <span data-ttu-id="191ee-141">No momento, o AI Builder não dá suporte aos seguintes tipos de dados de entrada de formulário:</span><span class="sxs-lookup"><span data-stu-id="191ee-141">AI Builder doesn't currently support the following types of form processing input data:</span></span><br><span data-ttu-id="191ee-142">- Caixas de seleção ou botões de rádio</span><span class="sxs-lookup"><span data-stu-id="191ee-142">- Check boxes or radio buttons</span></span><br><span data-ttu-id="191ee-143">– Assinaturas</span><span class="sxs-lookup"><span data-stu-id="191ee-143">- Signatures</span></span><br><span data-ttu-id="191ee-144">– PDFs preenchíveis</span><span class="sxs-lookup"><span data-stu-id="191ee-144">- Fillable PDFs</span></span>

### <a name="supported-file-types"></a><span data-ttu-id="191ee-145">Tipos de arquivo compatíveis</span><span class="sxs-lookup"><span data-stu-id="191ee-145">Supported file types</span></span>

<span data-ttu-id="191ee-146">Os modelos de compreensão de documentos são compatíveis com os seguintes tipos de arquivo:</span><span class="sxs-lookup"><span data-stu-id="191ee-146">Document understanding models support the following file types:</span></span>

- <span data-ttu-id="191ee-147">doc</span><span class="sxs-lookup"><span data-stu-id="191ee-147">doc</span></span>
- <span data-ttu-id="191ee-148">docx</span><span class="sxs-lookup"><span data-stu-id="191ee-148">docx</span></span>
- <span data-ttu-id="191ee-149">eml</span><span class="sxs-lookup"><span data-stu-id="191ee-149">eml</span></span>
- <span data-ttu-id="191ee-150">HEIC</span><span class="sxs-lookup"><span data-stu-id="191ee-150">heic</span></span>
- <span data-ttu-id="191ee-151">HEIF</span><span class="sxs-lookup"><span data-stu-id="191ee-151">heif</span></span>
- <span data-ttu-id="191ee-152">htm</span><span class="sxs-lookup"><span data-stu-id="191ee-152">htm</span></span>
- <span data-ttu-id="191ee-153">HTML</span><span class="sxs-lookup"><span data-stu-id="191ee-153">html</span></span>
- <span data-ttu-id="191ee-154">JPEG</span><span class="sxs-lookup"><span data-stu-id="191ee-154">jpeg</span></span>
- <span data-ttu-id="191ee-155">jpg</span><span class="sxs-lookup"><span data-stu-id="191ee-155">jpg</span></span>
- <span data-ttu-id="191ee-156">Markdown</span><span class="sxs-lookup"><span data-stu-id="191ee-156">markdown</span></span>
- <span data-ttu-id="191ee-157">md</span><span class="sxs-lookup"><span data-stu-id="191ee-157">md</span></span>
- <span data-ttu-id="191ee-158">msg</span><span class="sxs-lookup"><span data-stu-id="191ee-158">msg</span></span>
- <span data-ttu-id="191ee-159">pdf</span><span class="sxs-lookup"><span data-stu-id="191ee-159">pdf</span></span>
- <span data-ttu-id="191ee-160">PNG</span><span class="sxs-lookup"><span data-stu-id="191ee-160">png</span></span>
- <span data-ttu-id="191ee-161">ppt</span><span class="sxs-lookup"><span data-stu-id="191ee-161">ppt</span></span>
- <span data-ttu-id="191ee-162">pptx</span><span class="sxs-lookup"><span data-stu-id="191ee-162">pptx</span></span>
- <span data-ttu-id="191ee-163">rtf</span><span class="sxs-lookup"><span data-stu-id="191ee-163">rtf</span></span>
- <span data-ttu-id="191ee-164">tif</span><span class="sxs-lookup"><span data-stu-id="191ee-164">tif</span></span>
- <span data-ttu-id="191ee-165">tiff</span><span class="sxs-lookup"><span data-stu-id="191ee-165">tiff</span></span>
- <span data-ttu-id="191ee-166">txt</span><span class="sxs-lookup"><span data-stu-id="191ee-166">txt</span></span>
- <span data-ttu-id="191ee-167">xls</span><span class="sxs-lookup"><span data-stu-id="191ee-167">xls</span></span>
- <span data-ttu-id="191ee-168">xlsx</span><span class="sxs-lookup"><span data-stu-id="191ee-168">xlsx</span></span>



## <a name="see-also"></a><span data-ttu-id="191ee-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="191ee-169">See Also</span></span>
[<span data-ttu-id="191ee-170">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="191ee-170">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="191ee-171">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="191ee-171">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="191ee-172">Criar um centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="191ee-172">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="191ee-173">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="191ee-173">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="191ee-174">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="191ee-174">Apply a model</span></span>](apply-a-model.md)   

[<span data-ttu-id="191ee-175">Diferença entre um modelo de compreensão de documentos e um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="191ee-175">Difference between a document understanding and a form processing model</span></span>](difference-between-document-understanding-and-form-processing-model.md)
  
[<span data-ttu-id="191ee-176">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="191ee-176">Form processing overview</span></span>](form-processing-overview.md)

[<span data-ttu-id="191ee-177">Modo de acessibilidade do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="191ee-177">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)