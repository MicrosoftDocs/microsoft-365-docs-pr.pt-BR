---
title: Visão geral do processamento de formulário
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
description: Saiba mais sobre o processamento de formulário no SharePoint Syntex
ms.openlocfilehash: 1dba8828a158a5163017ee5f37735f44e974274c
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515155"
---
# <a name="form-processing-overview"></a><span data-ttu-id="164c5-103">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="164c5-103">Form processing overview</span></span>

 ![Construtor AI](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="164c5-105">O Microsoft SharePoint Syntex usa o processamento de formulário do [Construtor AI](https://docs.microsoft.com/ai-builder/overview) do Microsoft PowerApps para criar modelos nas bibliotecas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="164c5-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="164c5-106">Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair os pares de chave/valor e os dados da tabela de documentos estruturados e semiestruturados, como formulários e faturas.</span><span class="sxs-lookup"><span data-stu-id="164c5-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="164c5-107">As organizações geralmente recebem faturas em grandes quantidades de diversas fontes, como correio, fax, email, etc. Processar esses documentos e inseri-los manualmente em um banco de dados pode demorar um período de tempo considerável.</span><span class="sxs-lookup"><span data-stu-id="164c5-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="164c5-108">Ao usar AI para extrair o texto, os pares de chave/valor e tabelas dos seus documentos, o processamento de formulário automatiza esse processo.</span><span class="sxs-lookup"><span data-stu-id="164c5-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="164c5-109">Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para saber mais sobre os exemplos de cenários de processamento de formulário.</span><span class="sxs-lookup"><span data-stu-id="164c5-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="164c5-110">Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de pedido de compra carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="164c5-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="164c5-111">De cada pedido de compra, você pode extrair e exibir dados específicos que são importantes para você, como *Número do PC*, *Data* ou *Custo Total*.</span><span class="sxs-lookup"><span data-stu-id="164c5-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Modo de exibição da biblioteca de documentos](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="164c5-113">Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário.</span><span class="sxs-lookup"><span data-stu-id="164c5-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="164c5-114">O layout do seu documento é aprendido treinando o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="164c5-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="164c5-115">Você só precisa de cinco documentos de formulário para começar.</span><span class="sxs-lookup"><span data-stu-id="164c5-115">You only need five form documents to get started.</span></span> <span data-ttu-id="164c5-116">O Construtor AI analisará seus arquivos de exemplo para pares de chave/valor e você também pode identificar manualmente os que podem não ter sido detectados.</span><span class="sxs-lookup"><span data-stu-id="164c5-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="164c5-117">O Construtor AI permite testar a precisão do modelo em seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="164c5-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="164c5-118">Depois de treinar e publicar seu modelo, ele cria um [Fluxo do Power Automate](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="164c5-118">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="164c5-119">O fluxo será executado quando um arquivo for carregado na biblioteca de documentos do SharePoint e extrairá os dados identificados no modelo.</span><span class="sxs-lookup"><span data-stu-id="164c5-119">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="164c5-120">Os dados extraídos serão exibidos em colunas no modo de exibição da biblioteca de documentos do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="164c5-120">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="164c5-121">Um administrador do Office 365 precisa [habilitar o processamento de formulário](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) da biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulário](create-a-form-processing-model.md) nele.</span><span class="sxs-lookup"><span data-stu-id="164c5-121">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="164c5-122">Você pode selecionar os sites durante a instalação ou após a instalação das suas configurações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="164c5-122">You can select the sites during setup, or after setup in your management settings.</span></span>

### <a name="file-limitations"></a><span data-ttu-id="164c5-123">Limitações do arquivo</span><span class="sxs-lookup"><span data-stu-id="164c5-123">File limitations</span></span>

<span data-ttu-id="164c5-124">Ao utilizar modelos de processamento de formulários, certifique-se de observar os [requisitos e limitações para o uso de arquivos](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span><span class="sxs-lookup"><span data-stu-id="164c5-124">When using form processing models, make sure to note the [requirements and limitations for file usage](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span>

### <a name="multi-geo-environments"></a><span data-ttu-id="164c5-125">Ambientes Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="164c5-125">Multi-Geo environments</span></span>

<span data-ttu-id="164c5-126">Ao configurar o SharePoint Syntex em um [Ambiente Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo), você só pode configurá-lo para usar o processamento de formulário no local central.</span><span class="sxs-lookup"><span data-stu-id="164c5-126">When setting up SharePoint Syntex in a [Microsoft 365 Multi-Geo environment](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo), you can only configure it to use form processing in the central location.</span></span> <span data-ttu-id="164c5-127">Se você deseja usar o processamento de formulário em um local satélite, entre em contato com o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="164c5-127">If you want to use form processing in a satellite location, contact Microsoft support.</span></span>






## <a name="see-also"></a><span data-ttu-id="164c5-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="164c5-128">See Also</span></span>
  
[<span data-ttu-id="164c5-129">Documentação do Power Automate</span><span class="sxs-lookup"><span data-stu-id="164c5-129">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="164c5-130">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="164c5-130">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="164c5-131">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="164c5-131">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="164c5-132">Treinamento: melhorar o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="164c5-132">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
