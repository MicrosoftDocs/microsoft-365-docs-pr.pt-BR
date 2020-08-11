---
title: Diferença entre modelos de processamento de formulários e compreensão de documentos (visualização)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Descreve a principal diferença entre modelos de processamento de formulários e compreensão de documentos.
ms.openlocfilehash: 7c480b91c1ddd75016b4bd35faa3d5692cacd103
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612733"
---
# <a name="difference-between-document-understanding-and-form-processing-models-preview"></a><span data-ttu-id="ae90e-103">Diferença entre modelos de processamento de formulários e compreensão de documentos (visualização)</span><span class="sxs-lookup"><span data-stu-id="ae90e-103">Difference between document understanding and form processing models (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="ae90e-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="ae90e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="ae90e-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="ae90e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="ae90e-106">Compreensão do conteúdo no Project Cortex permite que você identifique e Classifique documentos que são carregados em bibliotecas de documentos do SharePoint, bem como extraia informações relevantes de cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="ae90e-106">Content understanding in Project Cortex allows you to identify and classify documents that are uploaded to SharePoint document libraries, as well as extracting relevant information from each file.</span></span>  <span data-ttu-id="ae90e-107">Por exemplo, à medida que os arquivos são carregados para uma biblioteca de documentos do SharePoint, todos os arquivos identificados como *ordens de compra* são classificados como tal e exibidos em um modo de exibição de biblioteca de documentos personalizado no qual são exibidos.</span><span class="sxs-lookup"><span data-stu-id="ae90e-107">For example, as files are uploaded to a SharePoint document library, all files that are identified as *Purchase Orders* are classified as such and displayed in a custom document library view in which they are displayed.</span></span> <span data-ttu-id="ae90e-108">Além disso, você pode extrair informações específicas de cada arquivo (por exemplo, *número de OC* e *total*) e exibi-las em uma coluna no modo de exibição de biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ae90e-108">Additionally, you can pull specific information from each file (for example, *PO Number* and *Total*) and display it in a column in your document library view.</span></span> 


<span data-ttu-id="ae90e-109">A compreensão do conteúdo permite que você crie *modelos* para identificar e extrair as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="ae90e-109">Content understanding lets you create *models* to identify and extract the information you need.</span></span>  <span data-ttu-id="ae90e-110">Há dois tipos de modelos que podem ser usados:</span><span class="sxs-lookup"><span data-stu-id="ae90e-110">There are two types of models that can be used:</span></span>

- [<span data-ttu-id="ae90e-111">Modelos de compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="ae90e-111">Document understanding models</span></span>](document-understanding-overview.md)
- [<span data-ttu-id="ae90e-112">Modelos de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="ae90e-112">Form processing models</span></span>](form-processing-overview.md)

<span data-ttu-id="ae90e-113">Embora ambos os modelos sejam usados para o mesmo objetivo, há diferenças importantes que afetarão o que você pode escolher usar.</span><span class="sxs-lookup"><span data-stu-id="ae90e-113">While both models are used for generally the same purpose, there are key differences that will affect which ones you may choose to use.</span></span>


## <a name="structured-versus-unstructured-and-semi-structured-content"></a><span data-ttu-id="ae90e-114">Conteúdo estruturado versus não estruturado e semi-estruturados</span><span class="sxs-lookup"><span data-stu-id="ae90e-114">Structured versus unstructured and semi-structured content</span></span>

<span data-ttu-id="ae90e-115">Use documentos entendendo modelos para identificar e extrair dados de documentos não estruturados, como cartas ou contratos, onde as entidades de texto que você deseja extrair residem em frases ou regiões específicas do documento.</span><span class="sxs-lookup"><span data-stu-id="ae90e-115">Use document understanding models to identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> <span data-ttu-id="ae90e-116">Por exemplo, um documento não estruturado pode ser uma carta de renovação de contrato que pode ser escrita de diferentes maneiras.</span><span class="sxs-lookup"><span data-stu-id="ae90e-116">For example, an unstructured document could be a contract renewal letter that can be written in different ways.</span></span> <span data-ttu-id="ae90e-117">No entanto, há informações que são consistentemente no corpo de cada documento de renovação de contrato, como a cadeia de caracteres de texto "data de início do serviço" seguida de uma data real.</span><span class="sxs-lookup"><span data-stu-id="ae90e-117">However, there is information that is consistently in the body of each contract renewal document, such as the text string "Service start date of" followed by an actual date.</span></span>   

<span data-ttu-id="ae90e-118">Use modelos de processamento de formulário para identificar arquivos e extrair dados de documentos estruturados ou semi-estruturados, como formulários ou faturas, onde você tem pares de chave-valor claro (por exemplo, *Date: 10/1/2020*) \* ou Table Data.</span><span class="sxs-lookup"><span data-stu-id="ae90e-118">Use form processing models to identify files and extract data from structured or semi-structured documents, such as forms or invoices, where you have clear key-value pairs (for example, *Date: 10/1/2020*)\* or table data.</span></span> <span data-ttu-id="ae90e-119">Por exemplo, um bom candidato para processamento de formulários seria o formulário de solicitação de pedido de uma empresa em que os clientes precisam fornecer suas informações para campos específicos que estão localizados na mesma área do layout do documento, como *nome*, *número de telefone*, *custo total*, etc.  Um formulário de impostos é um bom exemplo de um documento estruturado.</span><span class="sxs-lookup"><span data-stu-id="ae90e-119">As an example, a good candidate for form processing would be a company's order request form in which clients need to provide their information for specific fields which are located in the same area of the document layout, such as *Name*, *Phone Number*, *Total Cost*, etc.  A tax form is a good example of a structured document.</span></span> 

## <a name="where-they-are-created"></a><span data-ttu-id="ae90e-120">Onde são criados</span><span class="sxs-lookup"><span data-stu-id="ae90e-120">Where they are created</span></span>

<span data-ttu-id="ae90e-121">Documentos entendendo modelos são criados e gerenciados em um site do centro de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae90e-121">Document understanding models are created and managed in a SharePoint content center site.</span></span> <span data-ttu-id="ae90e-122">Você deve ter acesso a um site de centro de conteúdo para criar um documento que compreenda o modelo ou aplicar um a uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae90e-122">You must have access to a content center site to create a document understanding model or to apply one to a SharePoint document library.</span></span> 

<span data-ttu-id="ae90e-123">Ao criar um documento que compreenda o modelo, você cria um novo [tipo de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que é salvo na Galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae90e-123">When you create a document understanding model, you create a new [SharePoint content type](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) that is saved to the SharePoint Content Types gallery.</span></span> <span data-ttu-id="ae90e-124">Opcionalmente, você pode usar tipos de conteúdo existentes para definir seu modelo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ae90e-124">You can optionally use existing content types to define your model if needed.</span></span>

<span data-ttu-id="ae90e-125">Modelos de processamento de formulário são criados no [Construtor de ai](https://docs.microsoft.com/ai-builder/overview)do PowerApps, mas a criação é iniciada diretamente de uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae90e-125">Form processing models are created in PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview), but the creation is initiated directly from a SharePoint Document library.</span></span> <span data-ttu-id="ae90e-126">A criação do modelo de processamento de formulários precisa estar habilitada na biblioteca de documentos para que um usuário possa criar um modelo de processamento de formulário para ele, e um administrador pode fazer isso no conteúdo entendendo as configurações de administração.</span><span class="sxs-lookup"><span data-stu-id="ae90e-126">Form processing model creation needs to be enabled on your document library in order for a user to create a form processing model for it, and an admin can do this in the content understanding admin settings.</span></span> <span data-ttu-id="ae90e-127">Os modelos de processamento de formulários usam fluxos PowerAutomate para processar arquivos quando são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="ae90e-127">Form processing models use PowerAutomate flows to process files when they are uploaded to the document library.</span></span>

<span data-ttu-id="ae90e-128">Os modelos de processamento de formulários também criam novos [tipos de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), que também são armazenados na Galeria de tipos de conteúdo do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ae90e-128">Form processing models also create new [SharePoint content types](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978), which are also stored in the SharePoint Content Types gallery.</span></span>

## <a name="where-they-can-be-applied"></a><span data-ttu-id="ae90e-129">Onde podem ser aplicados</span><span class="sxs-lookup"><span data-stu-id="ae90e-129">Where they can be applied</span></span>

<span data-ttu-id="ae90e-130">Documentos entendendo modelos podem ser aplicados a diferentes bibliotecas de documentos do SharePoint às quais você tem acesso.</span><span class="sxs-lookup"><span data-stu-id="ae90e-130">Document understanding models can be applied to different SharePoint document libraries that you have access to.</span></span> <span data-ttu-id="ae90e-131">Você pode usar o centro de conteúdo para não apenas criar um documento que compreenda o modelo, mas também aplicá-lo a diferentes bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="ae90e-131">You can use the content center to not only create a document understanding model, but also to apply it to different document libraries.</span></span> <span data-ttu-id="ae90e-132">O centro de conteúdo oferece um controle mais centralizado de como o documento entendendo modelos são usados e onde eles são aplicados, pois essas informações devem ser acumuladas em um centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ae90e-132">The content center gives a more central control of how document understanding models are used and where they are applied, since this information must roll up to a content center.</span></span>

<span data-ttu-id="ae90e-133">No momento, os modelos de processamento de formulário só podem ser aplicados à biblioteca de documentos do SharePoint a partir da qual foram criados.</span><span class="sxs-lookup"><span data-stu-id="ae90e-133">Form processing models can currently only be applied to the SharePoint document library from which they were created.</span></span> <span data-ttu-id="ae90e-134">Isso permite que qualquer usuário licenciado que tenha acesso ao site crie um modelo de processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="ae90e-134">This allows any licensed user who has access to the site to create a form processing model.</span></span>




 ## <a name="see-also"></a><span data-ttu-id="ae90e-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="ae90e-135">See Also</span></span>
[<span data-ttu-id="ae90e-136">Treinamento: aprimore o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="ae90e-136">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[<span data-ttu-id="ae90e-137">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="ae90e-137">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="ae90e-138">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="ae90e-138">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="ae90e-139">Aplicar um documento entendendo o modelo</span><span class="sxs-lookup"><span data-stu-id="ae90e-139">Apply a document understanding model</span></span>](apply-a-model.md)</br>
[<span data-ttu-id="ae90e-140">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="ae90e-140">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>



  
  



