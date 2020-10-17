---
title: Visão geral do processamento de formulário
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Saiba mais sobre o processamento de formulário no SharePoint Syntex
ms.openlocfilehash: 7340e0c78db71fbb0acc05c2985b60f6bafbba80
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48493668"
---
# <a name="form-processing-overview"></a><span data-ttu-id="fd720-103">Visão geral do processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="fd720-103">Form processing overview</span></span>

 ![Construtor AI](../media/content-understanding/ai-builder.png)</br>

<span data-ttu-id="fd720-105">O Microsoft SharePoint Syntex usa o processamento de formulário do [Construtor AI](https://docs.microsoft.com/ai-builder/overview) do Microsoft PowerApps para criar modelos nas bibliotecas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd720-105">Microsoft SharePoint Syntex uses Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) form processing to create models within SharePoint document libraries.</span></span>

<span data-ttu-id="fd720-106">Você pode usar o processamento de formulário do Construtor AI para criar modelos AI que usam a tecnologia de aprendizado de máquina para identificar e extrair os pares de chave/valor e os dados da tabela de documentos estruturados e semiestruturados, como formulários e faturas.</span><span class="sxs-lookup"><span data-stu-id="fd720-106">You can use AI Builder form processing to create AI models that use machine learning technology to identify and extract key-value pairs and table data from structured or semi-structured  documents, like forms and invoices.</span></span>

<span data-ttu-id="fd720-107">As organizações geralmente recebem faturas em grandes quantidades de diversas fontes, como correio, fax, email, etc. Processar esses documentos e inseri-los manualmente em um banco de dados pode demorar um período de tempo considerável.</span><span class="sxs-lookup"><span data-stu-id="fd720-107">Organizations often receive invoices in large quantities from a variety of sources, such as mail, fax, email, etc. Processing these documents and manually entering them into a database can take a considerable amount of time.</span></span> <span data-ttu-id="fd720-108">Ao usar AI para extrair o texto, os pares de chave/valor e tabelas dos seus documentos, o processamento de formulário automatiza esse processo.</span><span class="sxs-lookup"><span data-stu-id="fd720-108">By using AI to extract the text, key/value pairs, and tables from your documents, form processing automates this process.</span></span> 

> [!NOTE]
> <span data-ttu-id="fd720-109">Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para saber mais sobre os exemplos de cenários de processamento de formulário.</span><span class="sxs-lookup"><span data-stu-id="fd720-109">See the [SharePoint Syntex adoption: Get started guide](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) for more information about form processing scenario examples.</span></span>

<span data-ttu-id="fd720-110">Por exemplo, você pode criar um modelo de processamento de formulário que identifique todos os documentos de pedido de compra carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="fd720-110">For example, you can create a form processing model that identifies all purchase order documents that are uploaded to the document library.</span></span> <span data-ttu-id="fd720-111">De cada pedido de compra, você pode extrair e exibir dados específicos que são importantes para você, como *Número do PC*, *Data* ou *Custo Total*.</span><span class="sxs-lookup"><span data-stu-id="fd720-111">From each purchase order you can then extract and display specific data that is important to you, such as *PO Number*, *Date*, or *Total Cost*.</span></span>

![Modo de exibição da biblioteca de documentos](../media/content-understanding/doc-lib-done.png)</br>  

<span data-ttu-id="fd720-113">Você usa arquivos de exemplo para treinar seu modelo e definir as informações a serem extraídas do seu formulário.</span><span class="sxs-lookup"><span data-stu-id="fd720-113">You use example files to train your model and define the information to be extracted from your form.</span></span> <span data-ttu-id="fd720-114">O layout do seu documento é aprendido treinando o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="fd720-114">The layout of your document is learned by training your model.</span></span> <span data-ttu-id="fd720-115">Você só precisa de cinco documentos de formulário para começar.</span><span class="sxs-lookup"><span data-stu-id="fd720-115">You only need five form documents to get started.</span></span> <span data-ttu-id="fd720-116">O Construtor AI analisará seus arquivos de exemplo para pares de chave/valor e você também pode identificar manualmente os que podem não ter sido detectados.</span><span class="sxs-lookup"><span data-stu-id="fd720-116">AI Builder will analyze your example files for key-value pairs, and you can also manually identify ones that may not have been detected.</span></span>  <span data-ttu-id="fd720-117">O Construtor AI permite testar a precisão do modelo em seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd720-117">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="fd720-118">Você precisa de no mínimo cinco documentos de formulário para começar.</span><span class="sxs-lookup"><span data-stu-id="fd720-118">You need a minimum of five form documents to get started.</span></span> <span data-ttu-id="fd720-119">A construção de AI analisa os arquivos de exemplo para pares de chave/valor e identifica manualmente aqueles que podem não ter sido detectados.</span><span class="sxs-lookup"><span data-stu-id="fd720-119">AI building analyzes your example files for key-value pairs, and then manually identifies the ones that may not have been detected.</span></span>  <span data-ttu-id="fd720-120">O Construtor AI permite testar a precisão do modelo em seus arquivos de exemplo.</span><span class="sxs-lookup"><span data-stu-id="fd720-120">AI builder lets you test the accuracy of your model on your example files.</span></span>

<span data-ttu-id="fd720-121">Depois de treinar e publicar seu modelo, ele cria um [Fluxo do Power Automate](https://docs.microsoft.com/power-automate/getting-started).</span><span class="sxs-lookup"><span data-stu-id="fd720-121">After you train and publish your model, your model creates a [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started).</span></span> <span data-ttu-id="fd720-122">O fluxo será executado quando um arquivo for carregado na biblioteca de documentos do SharePoint e extrairá os dados identificados no modelo.</span><span class="sxs-lookup"><span data-stu-id="fd720-122">The flow runs when a file is uploaded to the SharePoint document library and will extract data that has been identified in the model.</span></span> <span data-ttu-id="fd720-123">Os dados extraídos serão exibidos em colunas no modo de exibição da biblioteca de documentos do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="fd720-123">The extracted data will display in columns in your model's document library view.</span></span>

<span data-ttu-id="fd720-124">Um administrador do Office 365 precisa [habilitar o processamento de formulário](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) da biblioteca de documentos do SharePoint para que os usuários possam [criar um modelo de processamento de formulário](create-a-form-processing-model.md) nele.</span><span class="sxs-lookup"><span data-stu-id="fd720-124">An Office 365 admin needs to [enable Form processing](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) for the SharePoint document library for users to be able to [create a form processing model](create-a-form-processing-model.md) in it.</span></span> <span data-ttu-id="fd720-125">Você pode selecionar os sites durante a instalação ou após a instalação das suas configurações de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="fd720-125">You can select the sites during setup, or after setup in your management settings.</span></span>



## <a name="see-also"></a><span data-ttu-id="fd720-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="fd720-126">See Also</span></span>
  
[<span data-ttu-id="fd720-127">Documentação do Power Automate</span><span class="sxs-lookup"><span data-stu-id="fd720-127">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="fd720-128">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="fd720-128">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="fd720-129">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="fd720-129">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="fd720-130">Treinamento: melhorar o desempenho de negócios com o Construtor AI</span><span class="sxs-lookup"><span data-stu-id="fd720-130">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
