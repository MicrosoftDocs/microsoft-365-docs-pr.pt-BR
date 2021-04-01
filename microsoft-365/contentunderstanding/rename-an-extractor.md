---
title: Renomear um extrator no Microsoft SharePoint Syntex
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
description: 'Aprenda como e por que renomear um extrator no Microsoft SharePoint Syntex. '
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445922"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a3d5d-103">Renomear um extrator no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="a3d5d-103">Rename an extractor in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="a3d5d-104">Em algum ponto, você pode precisar renomear um extrator se quiser se referir a um campo de dados extraído com um nome diferente.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-104">At some point, you might need to rename an extractor if you want to refer to an extracted data field by a different name.</span></span> <span data-ttu-id="a3d5d-105">Por exemplo, sua organização decide fazer alterações em seus documentos de contrato e se refere a “consumidor” como “clientes” em seus documentos.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-105">For example, your organization decides to make changes to their contract documents, and refers to “customers” as “clients” in their documents.</span></span> <span data-ttu-id="a3d5d-106">Se você estava extraindo um campo "Consumidor" em seu modelo, pode escolher renomeá-lo para "Cliente".</span><span class="sxs-lookup"><span data-stu-id="a3d5d-106">If you were extracting a “Customer” field in your model, you can choose to rename it to “Client.”</span></span>

<span data-ttu-id="a3d5d-107">Ao sincronizar o modelo atualizado com a biblioteca de documentos do Microsoft Office SharePoint Online, você verá uma nova coluna “Cliente” na exibição da biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-107">When you sync your updated model to your SharePoint document library, you will see a new “Client” column in your document library view.</span></span> <span data-ttu-id="a3d5d-108">Sua exibição manterá a coluna “Consumidor” para atividades anteriores, mas atualizará a nova coluna “Cliente” para todos os novos documentos que são processados por seu modelo.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-108">Your view will retain the “Customer” column for past activity, but will update the new “Client” column for all new documents that are processed by your model.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="a3d5d-109">Certifique-se de sincronizar seu modelo atualizado com as bibliotecas de documentos onde você o aplicou anteriormente para que o novo nome da coluna seja exibido.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-109">Make sure to sync your updated model to the document libraries where you had previously applied it for the new column name to display.</span></span> 

## <a name="rename-an-extractor"></a><span data-ttu-id="a3d5d-110">Renomear um extrator</span><span class="sxs-lookup"><span data-stu-id="a3d5d-110">Rename an extractor</span></span>

<span data-ttu-id="a3d5d-111">Siga estas etapas para renomear um extrator de entidade.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-111">Follow these steps to rename an entity extractor.</span></span>

1. <span data-ttu-id="a3d5d-112">No centro de conteúdo, selecione **Modelos** para ver a lista de modelos.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-112">From the content center, select **Models** to see your models list.</span></span>

2. <span data-ttu-id="a3d5d-113">Na página **Modelos**, na coluna **Nome**, selecione o modelo para o qual deseja renomear um extrator.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-113">On the **Models** page, in the **Name** column, select the model for which you want to rename an extractor.</span></span>

3. <span data-ttu-id="a3d5d-114">Em **Extratores de entidades**, selecione o nome do extrator que deseja renomear e, a seguir, selecione **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-114">Under **Entity extractors**, select the name of the extractor you want to rename, and then select **Rename**.</span></span></br>

    ![Captura de tela da seção Extratores de entidade mostrando um extrator selecionado com a opção Renomear destacada.](../media/content-understanding/entity-extractor-rename.png) </br>

4. <span data-ttu-id="a3d5d-116">No painel **Renomear extrator de entidade**:</span><span class="sxs-lookup"><span data-stu-id="a3d5d-116">On the **Rename entity extractor** panel:</span></span>

   <span data-ttu-id="a3d5d-117">a.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-117">a.</span></span> <span data-ttu-id="a3d5d-118">Em **Novo nome**, insira o novo nome do extrator.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-118">Under **New name**, enter the new name of the extractor.</span></span></br>

    ![Captura de tela mostrando o painel do Extrator de entidade.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   <span data-ttu-id="a3d5d-120">b.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-120">b.</span></span> <span data-ttu-id="a3d5d-121">(Opcional) Em **Configurações avançadas**, selecione se deseja associar uma coluna de site existente.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-121">(Optional) Under **Advanced settings**, select whether you want to associate an existing site column.</span></span>

5. <span data-ttu-id="a3d5d-122">Selecione **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="a3d5d-122">Select **Rename**.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3d5d-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="a3d5d-123">See Also</span></span>
[<span data-ttu-id="a3d5d-124">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="a3d5d-124">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="a3d5d-125">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="a3d5d-125">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="a3d5d-126">Renomear um modelo</span><span class="sxs-lookup"><span data-stu-id="a3d5d-126">Rename a model</span></span>](rename-a-model.md)

[<span data-ttu-id="a3d5d-127">Tipos de explicação</span><span class="sxs-lookup"><span data-stu-id="a3d5d-127">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="a3d5d-128">Aproveitar a taxonomia do repositório de termos ao criar um extrator</span><span class="sxs-lookup"><span data-stu-id="a3d5d-128">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

<span data-ttu-id="a3d5d-129">[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a3d5d-129">[Document Understanding overview](document-understanding-overview.md)</span></span>

[<span data-ttu-id="a3d5d-130">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="a3d5d-130">Apply a model</span></span>](apply-a-model.md) 
