---
title: API REST do modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Visão geral da API REST de compreensão de documentos do Microsoft Office SharePoint Online Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908084"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a><span data-ttu-id="0144e-103">API REST do modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex</span><span class="sxs-lookup"><span data-stu-id="0144e-103">SharePoint Syntex document understanding model REST API</span></span>

<span data-ttu-id="0144e-104">Você pode usar a interface REST do Microsoft Office SharePoint Online para criar um modelo de compreensão de documento, aplicar ou remover o modelo em uma ou mais bibliotecas e obter ou atualizar informações sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="0144e-104">You can use the SharePoint REST interface to create a document understanding model, apply or remove the model to one or more libraries, and obtain or update information about the model.</span></span> 

<span data-ttu-id="0144e-105">O serviço REST do SharePoint Online (e o SharePoint 2016 e posterior no local) dá suporte à combinação de várias solicitações em uma única chamada para o serviço, usando a opção de consulta $batch do OData.</span><span class="sxs-lookup"><span data-stu-id="0144e-105">The SharePoint Online (and SharePoint 2016 and later on-premises) REST service supports combining multiple requests into a single call to the service by using the OData $batch query option.</span></span> 

<span data-ttu-id="0144e-106">Para obter detalhes e links de amostras de código, confira [Fazer solicitações em lote com APIs REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span><span class="sxs-lookup"><span data-stu-id="0144e-106">For details and links to code samples, see [Make batch requests with the REST APIs](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0144e-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0144e-107">Prerequisites</span></span>

<span data-ttu-id="0144e-108">Antes de começar, verifique se está familiarizado com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0144e-108">Before you get started, make sure that you're familiar with the following:</span></span>

- [<span data-ttu-id="0144e-109">Conheça o serviço REST do SharePoint</span><span class="sxs-lookup"><span data-stu-id="0144e-109">Get to know the SharePoint REST service</span></span>](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [<span data-ttu-id="0144e-110">Realizar operações básicas usando os pontos de extremidade REST do SharePoint</span><span class="sxs-lookup"><span data-stu-id="0144e-110">Complete basic operations using SharePoint REST endpoints</span></span>](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a><span data-ttu-id="0144e-111">Comandos REST</span><span class="sxs-lookup"><span data-stu-id="0144e-111">REST commands</span></span>

<span data-ttu-id="0144e-112">Os seguintes comandos REST estão disponíveis para trabalhar com modelos de compreensão de documentos da Syntex:</span><span class="sxs-lookup"><span data-stu-id="0144e-112">The following REST commands are available for working with Syntex document understanding models:</span></span>

- <span data-ttu-id="0144e-113">[Criar modelo](rest-createmodel-method.md) – Cria um modelo e seu tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="0144e-113">[Create model](rest-createmodel-method.md) – Creates a model and its associated content type.</span></span>
- <span data-ttu-id="0144e-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Obtém ou atualiza informações sobre um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex.</span><span class="sxs-lookup"><span data-stu-id="0144e-114">[GetByUniqueId](rest-getbyuniqueid-method.md) – Gets or updates information about a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="0144e-115">[GetByTitle](rest-getbytitle-method.md) – Obtém ou atualiza informações sobre um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex usando o título do modelo.</span><span class="sxs-lookup"><span data-stu-id="0144e-115">[GetByTitle](rest-getbytitle-method.md) – Gets or updates information about a SharePoint Syntex document understanding model using the model title.</span></span>
- <span data-ttu-id="0144e-116">[Aplicar modelo](rest-applymodel-method.md) – Aplica (ou sincroniza) um modelo treinado de compreensão de documento a uma ou mais bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0144e-116">[Apply model](rest-applymodel-method.md) – Applies (or syncs) a trained document understanding model to one or more libraries.</span></span>
- <span data-ttu-id="0144e-117">[Obter informações sobre modelos e bibliotecas](rest-getmodelandlibraryinfo.md) – Obtém informações sobre um modelo e a biblioteca na qual ele foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="0144e-117">[Get model and library information](rest-getmodelandlibraryinfo.md) – Gets information about a model and the library where it has been applied.</span></span>
- <span data-ttu-id="0144e-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Atualiza as configurações de modelos disponíveis (descrição de modelo e rótulo de retenção associado) para um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex.</span><span class="sxs-lookup"><span data-stu-id="0144e-118">[UpdateModelSettings](rest-updatemodelsettings-method.md) – Updates available models settings (associated retention label and model description) for a SharePoint Syntex document understanding model.</span></span>
- <span data-ttu-id="0144e-119">[BatchDelete](rest-batchdelete-method.md) – Remove um modelo de compreensão de documento aplicado de uma ou mais bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0144e-119">[BatchDelete](rest-batchdelete-method.md) – Removes an applied document understanding model from one or more libraries.</span></span>
- <span data-ttu-id="0144e-120">[Criar solicitação de classificação](rest-createclassificationrequest.md) – Cria uma solicitação para classificar um arquivo ou arquivos especificados usando o modelo aplicado.</span><span class="sxs-lookup"><span data-stu-id="0144e-120">[Create classification request](rest-createclassificationrequest.md) – Creates a request to classify a specified file or files using the applied model.</span></span>

## <a name="scenarios"></a><span data-ttu-id="0144e-121">Cenários</span><span class="sxs-lookup"><span data-stu-id="0144e-121">Scenarios</span></span>

<span data-ttu-id="0144e-122">Observe os seguintes exemplos de cenário que não são intuitivos com base no nome do método.</span><span class="sxs-lookup"><span data-stu-id="0144e-122">Note the following scenario examples that aren't intuitive from the method name.</span></span> <span data-ttu-id="0144e-123">Para obter mais informações, consulte cada artigo.</span><span class="sxs-lookup"><span data-stu-id="0144e-123">For more information, see each article.</span></span>

<span data-ttu-id="0144e-124">O método criar modelo apenas cria o objeto de modelo e seu tipo de conteúdo associado.</span><span class="sxs-lookup"><span data-stu-id="0144e-124">The create model method only creates the model object and its associated content type.</span></span> <span data-ttu-id="0144e-125">Será preciso primeiro treinar o modelo no centro de conteúdo antes que ele possa ser aplicado a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="0144e-125">You'll need to first train the model in the content center before it can be applied to a library.</span></span>

<span data-ttu-id="0144e-126">O método de modelo de aplicação é usado para configurar o modelo na biblioteca de destino para classificar documentos e, opcionalmente, extrair informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="0144e-126">The apply model method is used to configure the model on the target library to classify documents and optionally extract additional information.</span></span> <span data-ttu-id="0144e-127">Essa API também dá suporte à aplicação em lote do modelo a várias bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="0144e-127">This API also supports batch applying the model to multiple libraries.</span></span>

<span data-ttu-id="0144e-128">O método de remover modelo simplesmente remove o modelo de uma ou mais bibliotecas onde ele foi aplicado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0144e-128">The remove model method just removes the model from one or more libraries where it was previously applied.</span></span> <span data-ttu-id="0144e-129">Se você quiser excluir o modelo, ele deverá primeiro ser removido de todas as bibliotecas onde ele foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="0144e-129">If you want to delete the model, it must first be removed from all the libraries where it was applied.</span></span>


## <a name="see-also"></a><span data-ttu-id="0144e-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="0144e-130">See also</span></span>

[<span data-ttu-id="0144e-131">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="0144e-131">Document understanding overview</span></span>](../document-understanding-overview.md)

