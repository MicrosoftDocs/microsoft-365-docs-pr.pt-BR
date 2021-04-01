---
title: Duplicar um modelo no Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda como e por que duplicar um modelo no Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445931"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="77c77-103">Duplicar um modelo no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="77c77-103">Duplicate a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="77c77-104">A duplicação de um modelo de compreensão de documento pode economizar tempo e esforço se você precisar criar um novo modelo e saber que um modelo existente é muito semelhante ao que você precisa.</span><span class="sxs-lookup"><span data-stu-id="77c77-104">Duplicating a document understanding model can save you time and effort if you need to create a new model, and know that an existing model is very similar to what you need.</span></span>

<span data-ttu-id="77c77-105">Por exemplo, um modelo existente denominado “Contratos” classifica os mesmos arquivos com os quais você precisa trabalhar.</span><span class="sxs-lookup"><span data-stu-id="77c77-105">For example, an existing model named “Contracts” classifies the same files you need to work with.</span></span> <span data-ttu-id="77c77-106">Seu novo modelo extrairá alguns dos dados existentes, mas precisará ser atualizado para extrair alguns dados adicionais.</span><span class="sxs-lookup"><span data-stu-id="77c77-106">Your new model will extract some of the existing data, but will need to be updated to extract some additional data.</span></span> <span data-ttu-id="77c77-107">Em vez de criar e treinar um novo modelo do zero, você pode usar o recurso de modelo duplicado para fazer uma cópia do modelo de Contratos, que também copiará todos os itens de treinamento associados, como arquivos de exemplo e extratores de entidade.</span><span class="sxs-lookup"><span data-stu-id="77c77-107">Instead of creating and training a new model from scratch, you can use the duplicate model feature to make a copy of the Contracts model, which will also copy all associated training items, such as example files and entity extractors.</span></span>

<span data-ttu-id="77c77-108">Ao duplicar o modelo, depois de renomeá-lo (por exemplo, para “Renovações de contrato”), você pode fazer atualizações nele.</span><span class="sxs-lookup"><span data-stu-id="77c77-108">When you duplicate the model, after you rename it (for example, to “Contract Renewals”), you can then make updates to it.</span></span> <span data-ttu-id="77c77-109">Por exemplo, você pode escolher remover alguns dos campos extraídos existentes que você não precisa e, em seguida, treinar o modelo para extrair um novo (por exemplo, "Data de renovação").</span><span class="sxs-lookup"><span data-stu-id="77c77-109">For example, you can choose to remove some of the existing extracted fields that you don’t need, and then train the model to extract a new one (for example, “Renewal date”).</span></span>

## <a name="duplicate-a-model"></a><span data-ttu-id="77c77-110">Duplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="77c77-110">Duplicate a model</span></span>

<span data-ttu-id="77c77-111">Siga estas etapas para duplicar um modelo de compreensão de documento.</span><span class="sxs-lookup"><span data-stu-id="77c77-111">Follow these steps to duplicate a document understanding model.</span></span>

1. <span data-ttu-id="77c77-112">No centro de conteúdo, selecione **Modelos** para ver sua lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="77c77-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="77c77-113">Na página **Modelos**, selecione o modelo que deseja duplicar.</span><span class="sxs-lookup"><span data-stu-id="77c77-113">On the **Models** page, select the model you want to duplicate.</span></span>

3. <span data-ttu-id="77c77-114">Usando a faixa de opções ou o botão **Mostrar ações** (próxima ao nome do modelo), selecione **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="77c77-114">By using either the ribbon or the **Show actions** button (next to the model name), select **Duplicate**.</span></span></br>

    ![Captura de tela da página Modelos mostrando um modelo selecionado com as opções Duplicar destacadas.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. <span data-ttu-id="77c77-116">No painel **Modelo duplicado**:</span><span class="sxs-lookup"><span data-stu-id="77c77-116">On the **Duplicate model** panel:</span></span>

   <span data-ttu-id="77c77-117">a.</span><span class="sxs-lookup"><span data-stu-id="77c77-117">a.</span></span> <span data-ttu-id="77c77-118">Em **Nome**, insira o novo nome do modelo que deseja duplicar.</span><span class="sxs-lookup"><span data-stu-id="77c77-118">Under **Name**, enter the new name of the model that you want to duplicate.</span></span></br>

    ![Captura de tela mostrando o painel do modelo duplicado.](../media/content-understanding/duplicate-model-panel.png) </br>

   <span data-ttu-id="77c77-120">b.</span><span class="sxs-lookup"><span data-stu-id="77c77-120">b.</span></span> <span data-ttu-id="77c77-121">Em **Descrição**, adicione uma descrição de seu novo modelo.</span><span class="sxs-lookup"><span data-stu-id="77c77-121">Under **Description**, add a description of your new model.</span></span>

   <span data-ttu-id="77c77-122">c.</span><span class="sxs-lookup"><span data-stu-id="77c77-122">c.</span></span> <span data-ttu-id="77c77-123">(Opcional) Em **Configurações avançadas**, selecione se deseja associar um tipo de [conteúdo existente](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span><span class="sxs-lookup"><span data-stu-id="77c77-123">(Optional) Under **Advanced settings**, select whether you want to associate an existing [content type](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).</span></span>

5. <span data-ttu-id="77c77-124">Selecione **Duplicar**.</span><span class="sxs-lookup"><span data-stu-id="77c77-124">Select **Duplicate**.</span></span>

## <a name="see-also"></a><span data-ttu-id="77c77-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="77c77-125">See Also</span></span>
[<span data-ttu-id="77c77-126">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="77c77-126">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="77c77-127">Renomear um modelo</span><span class="sxs-lookup"><span data-stu-id="77c77-127">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="77c77-128">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="77c77-128">Create an extractor</span></span>](create-an-extractor.md)

<span data-ttu-id="77c77-129">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="77c77-129">[Document Understanding overview](document-understanding-overview.md)</span></span>

[<span data-ttu-id="77c77-130">Tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="77c77-130">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="77c77-131">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="77c77-131">Apply a model</span></span>](apply-a-model.md) 

[<span data-ttu-id="77c77-132">Modo de Acessibilidade do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="77c77-132">SharePoint Syntex Accessibility Mode</span></span>](accessibility-mode.md)