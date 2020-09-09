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
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre o processamento de formulários no Project Cortex.
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405617"
---
# <a name="form-processing-overview-preview"></a><span data-ttu-id="b6ba8-103">Visão geral do processamento de formulário (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="b6ba8-103">Form Processing overview (Preview)</span></span>
> [!Note]
> <span data-ttu-id="b6ba8-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b6ba8-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b6ba8-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="b6ba8-106">O Project Cortex usa o processamento de formulário do Microsoft PowerApps [ai Builder](https://docs.microsoft.com/ai-builder/overview) para criar modelos em bibliotecas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-106">Project Cortex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>
<span data-ttu-id="b6ba8-107">Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair pares de chave-valor e dados de tabela de documentos estruturados ou semi-estruturados, como formulários e faturas.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-107">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="b6ba8-108">As empresas geralmente recebem faturas em grandes quantidades e de várias fontes, como email, fax, email ou pessoalmente.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-108">Companies often receive invoices in large quantities and from a variety of sources, such as mail, fax, email, or in person.</span></span> <span data-ttu-id="b6ba8-109">O processamento desses documentos e a inserção manual deles no banco de dados pode demorar bastante tempo.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-109">Processing these documents and manually entering them into your database can take a considerable amount of time.</span></span> <span data-ttu-id="b6ba8-110">Usando o AI para extrair o texto, os pares de chave/valor e as tabelas de seus documentos, o processamento de formulários automatizará esse processo.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-110">By using AI to extract the text, key/value pairs, and tables from your documents, form processing will automate this process.</span></span> 

<span data-ttu-id="b6ba8-111">Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de ordem de compra que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-111">For example, you can create a form processing model that will identify all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="b6ba8-112">E de cada ordem de compra, você pode extrair e exibir dados específicos que são importantes para você, como *número da OC*, *Data*ou *custo total*.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-112">And from each purchase order you can extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

<span data-ttu-id="b6ba8-113">Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="b6ba8-114">O layout do seu documento é aprendido ao treinar seu modelo.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="b6ba8-115">Você precisa apenas de cinco documentos de formulário para começar.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-115">You only need five form documents to get started.</span></span> <span data-ttu-id="b6ba8-116">O Construtor AI analisará seus arquivos de exemplo para pares de chave-valor, e você também poderá identificar manualmente aqueles que podem não ter sido detectados.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="b6ba8-117">O Construtor AI permite que você teste a precisão do seu modelo em seus arquivos de amostra.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-117">AI builder lets you test the accuracy of your model on your sample files.</span></span>

<span data-ttu-id="b6ba8-118">Depois de treinar e publicar seu modelo, use-o para criar um [fluxo automatizado de energia](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="b6ba8-118">After you train and publish your model, to use it you create a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="b6ba8-119">O fluxo é executado quando um arquivo é carregado na biblioteca de documentos do SharePoint e extrai os dados que foram identificados no modelo.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="b6ba8-120">Os dados extraídos serão exibidos em colunas no modo de exibição de biblioteca de documentos do modelo.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="b6ba8-121">Um administrador do Office 365 precisa [habilitar o processamento de formulários](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) para a biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulários](create-a-form-processing-model.md) nele.</span><span class="sxs-lookup"><span data-stu-id="b6ba8-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span>



## <a name="see-also"></a><span data-ttu-id="b6ba8-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6ba8-122">See Also</span></span>
  
[<span data-ttu-id="b6ba8-123">Documentação da automatização de energia</span><span class="sxs-lookup"><span data-stu-id="b6ba8-123">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="b6ba8-124">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="b6ba8-124">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="b6ba8-125">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="b6ba8-125">Document understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="b6ba8-126">Treinamento: aprimore o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="b6ba8-126">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




