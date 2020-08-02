---
title: Visão geral do processamento de formulário (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre o processamento de formulários no Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540053"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="231b1-103">Visão geral do processamento de formulário (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="231b1-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="231b1-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="231b1-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="231b1-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="231b1-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="231b1-106">O Project Cortex usa o processamento de formulário do Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) para criar modelos em bibliotecas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="231b1-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="231b1-107">Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair pares de chave-valor e dados de tabela de documentos estruturados ou semi-estruturados, como formulário e faturas.</span><span class="sxs-lookup"><span data-stu-id="231b1-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like form and invoices.</span></span>

<span data-ttu-id="231b1-108">As empresas geralmente recebem faturas em grandes quantidades e de várias fontes, como email, fax, email ou pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="231b1-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="231b1-109">O processamento desses documentos e a inserção manual deles no banco de dados pode demorar bastante tempo.</span><span class="sxs-lookup"><span data-stu-id="231b1-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="231b1-110">Usando o AI para extrair o texto, os pares de chave/valor e as tabelas de seus documentos, o processamento de formulários automatizará esse processo.</span><span class="sxs-lookup"><span data-stu-id="231b1-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="231b1-111">Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de ordem de compra que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="231b1-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="231b1-112">E de cada ordem de compra, você pode extrair e exibir dados específicos que são importantes para você, como *número da OC*, *Data*ou *custo total*.</span><span class="sxs-lookup"><span data-stu-id="231b1-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="231b1-113">Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário.</span><span class="sxs-lookup"><span data-stu-id="231b1-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="231b1-114">O layout do seu documento é aprendido ao treinar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="231b1-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="231b1-115">Você precisa apenas de cinco documentos de formulário para começar.</span><span class="sxs-lookup"><span data-stu-id="231b1-115">You only need five form documents to get started.</span></span> <span data-ttu-id="231b1-116">A compilação do AI analisará seus arquivos de exemplo para pares de chave-valor, e você também poderá identificar manualmente aqueles que podem não ter sido detectados.</span><span class="sxs-lookup"><span data-stu-id="231b1-116">AI building will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="231b1-117">O Construtor AI permite que você teste a precisão do seu modelo em seus arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="231b1-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="231b1-118">Depois de treinar e publicar seu modelo, use-o para criar um [fluxo automatizado de energia](https://docs.microsoft.com/power-automate/getting-started) que será executado quando um arquivo for carregado na biblioteca de documentos do SharePoint e extrairá os dados que foram identificados no modelo.</span><span class="sxs-lookup"><span data-stu-id="231b1-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) that will run when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="231b1-119">Os dados extraídos serão exibidos em colunas no modo de exibição de biblioteca de documentos do modelo.</span><span class="sxs-lookup"><span data-stu-id="231b1-119">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="231b1-120">Um administrador do Office 365 precisa [habilitar o processamento de formulários](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) para a biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulários](create-a-form-processing-model.md) nele.</span><span class="sxs-lookup"><span data-stu-id="231b1-120">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="231b1-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="231b1-121">See Also</span></span>
  
[<span data-ttu-id="231b1-122">Documentação da automatização de energia</span><span class="sxs-lookup"><span data-stu-id="231b1-122">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="231b1-123">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="231b1-123">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="231b1-124">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="231b1-124">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="231b1-125">Treinamento: aprimore o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="231b1-125">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




