---
title: Painel de descoberta eletrônica avançado para conjuntos de análise
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 65a0e6dc2857a51b10d1fa3b6674ccf24dbc4799
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080058"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a><span data-ttu-id="7f15a-102">Painel de descoberta eletrônica avançado para conjuntos de revisão (visualização)</span><span class="sxs-lookup"><span data-stu-id="7f15a-102">Advanced eDiscovery dashboard for review sets (preview)</span></span>

<span data-ttu-id="7f15a-103">Para alguns casos na descoberta eletrônica avançada, você pode ter um grande volume de documentos e mensagens de email que precisam ser revisados.</span><span class="sxs-lookup"><span data-stu-id="7f15a-103">For some cases in Advanced eDiscovery, you may have a large volume of documents and email messages that need to be reviewed.</span></span> <span data-ttu-id="7f15a-104">Antes de iniciar o processo de revisão, talvez você queira analisar rapidamente seu corpus para identificar tendências ou estatísticas importantes que ajudarão você a desenvolver sua estratégia de análise.</span><span class="sxs-lookup"><span data-stu-id="7f15a-104">Before you start the review process, you may want to quickly analyze your corpus to identify trends or key statistics that will help you develop your review strategy.</span></span> <span data-ttu-id="7f15a-105">Para fazer isso, você pode usar o painel de descoberta eletrônica avançado para conjuntos de revisão para analisar rapidamente seus corpus.</span><span class="sxs-lookup"><span data-stu-id="7f15a-105">To do this, you can use the Advanced eDiscovery dashboard for review sets to quickly analyze your corpus.</span></span>

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a><span data-ttu-id="7f15a-106">Etapa 1: criar um widget no painel de análise de revisão</span><span class="sxs-lookup"><span data-stu-id="7f15a-106">Step 1: Create a widget on the review set dashboard</span></span>

1. <span data-ttu-id="7f15a-107">No centro de conformidade de & de segurança, acesse **descoberta eletrônica avançada > eDiscovery** para exibir a lista de casos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f15a-107">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>
  
2. <span data-ttu-id="7f15a-108">Selecione um caso existente.</span><span class="sxs-lookup"><span data-stu-id="7f15a-108">Select an existing case.</span></span>
  
3. <span data-ttu-id="7f15a-109">Clique na guia **conjunto de revisão** e selecione um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7f15a-109">Click the **Review Set** tab, and then select a review set.</span></span>
  
4. <span data-ttu-id="7f15a-110">Na lista suspensa de **resultados individuais** , clique em **modo de exibição de perfil de pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="7f15a-110">In the **Individual results** dropdown list, click **Search profile view**.</span></span> 

   ![DashbordPivot](../media/dashboardpivot.png)

   <span data-ttu-id="7f15a-112">A página de **exibição do perfil de pesquisa** é exibida; na primeira vez que você exibir esta página, três widgets padrão serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="7f15a-112">The **Search profile view** page is displayed; the first time you display this page, three default widgets are displayed.</span></span>

   ![Painel](../media/dashboardonly.png)
  
5. <span data-ttu-id="7f15a-114">Clique no **widget novo** e selecione um dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="7f15a-114">Click the **New  widget** and then select one of the following items:</span></span>

   ![Nova lista suspensa de widget](../media/NewWidgetDropdownBox.png)

   - <span data-ttu-id="7f15a-116">**Escolha na biblioteca:** Exibe uma biblioteca de widgets padrão.</span><span class="sxs-lookup"><span data-stu-id="7f15a-116">**Choose from library:** Displays a default library of widgets.</span></span> <span data-ttu-id="7f15a-117">Você clica em um widget e, em seguida, clica em **Adicionar** para adicioná-lo aos widgets na página de **exibição do perfil de pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="7f15a-117">You click a widget and then click **Add** to add it to the widgets on the **Search profile view** page.</span></span>
  
   - <span data-ttu-id="7f15a-118">**Criar widget personalizado:** Exibe uma página de submenu que você pode usar para configurar um widget personalizado.</span><span class="sxs-lookup"><span data-stu-id="7f15a-118">**Create custom widget:** Displays a flyout page that you can use to set up a custom widget.</span></span> 

6. <span data-ttu-id="7f15a-119">Para criar um widget personalizado, faça o seguinte na página **Adicionar** submenu do widget:</span><span class="sxs-lookup"><span data-stu-id="7f15a-119">To create a custom widget, do the following on the **Add widget** flyout page:</span></span>

   ![Criar widget](../media/addwidget.png)

    <span data-ttu-id="7f15a-121">a.</span><span class="sxs-lookup"><span data-stu-id="7f15a-121">a.</span></span> <span data-ttu-id="7f15a-122">Digite um nome para o widget, que é exibido na barra de título do widget.</span><span class="sxs-lookup"><span data-stu-id="7f15a-122">Type a name for the widget, which is displayed in the widget title bar.</span></span> <span data-ttu-id="7f15a-123">É necessário nomear um widget, mas é útil identificar os dados do widget.</span><span class="sxs-lookup"><span data-stu-id="7f15a-123">Naming a widget is required, but it's helpful to identify the widget data.</span></span>

    <span data-ttu-id="7f15a-124">b.</span><span class="sxs-lookup"><span data-stu-id="7f15a-124">b.</span></span> <span data-ttu-id="7f15a-125">Selecione uma propriedade na lista suspensa **Escolher tabela** suspensa que será usada para os dados do widget.</span><span class="sxs-lookup"><span data-stu-id="7f15a-125">Select a property in the **Choose pivot** dropdown list that will be used for the widget data.</span></span> <span data-ttu-id="7f15a-126">Os itens nesta lista são as propriedades pesquisáveis para os itens no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="7f15a-126">The items in this list are the searchable properties for the items in the review set.</span></span> <span data-ttu-id="7f15a-127">Para obter uma descrição dessas propriedades, confira [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md).</span><span class="sxs-lookup"><span data-stu-id="7f15a-127">For a description of these properties, see [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).</span></span> <span data-ttu-id="7f15a-128">As opções de tabela dinâmica do widget estão listadas na coluna **nome do campo pesquisável** neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7f15a-128">The pivot options for the widget are listed in the **Searchable field name** column in this topic.</span></span>

    <span data-ttu-id="7f15a-129">c.</span><span class="sxs-lookup"><span data-stu-id="7f15a-129">c.</span></span> <span data-ttu-id="7f15a-130">Selecione um tipo de gráfico para exibir os dados da propriedade dinâmica selecionada.</span><span class="sxs-lookup"><span data-stu-id="7f15a-130">Select a chart type to display the data from the selected pivot property.</span></span>

  6. <span data-ttu-id="7f15a-131">Clique em **Adicionar** para criar o widget personalizado e exibi-lo na página **Exibir Perfil de pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="7f15a-131">Click **Add** to create the custom widget and display it on the **Search profile view** page.</span></span>

## <a name="step-2-create-a-review-set-search-query"></a><span data-ttu-id="7f15a-132">Etapa 2: criar uma consulta de pesquisa do conjunto de análise</span><span class="sxs-lookup"><span data-stu-id="7f15a-132">Step 2: Create a review set search query</span></span>

1. <span data-ttu-id="7f15a-133">Clique em **...** na barra de título do widget e, em seguida, clique em **aplicar condição**.</span><span class="sxs-lookup"><span data-stu-id="7f15a-133">Click **...** in the widget title bar, and then click **Apply condition**.</span></span>

   ![Painel](../media/searchprofilehome.png)

2. <span data-ttu-id="7f15a-135">Na página do menu suspenso, clique em um elemento na chave do widget ou no gráfico de widget para criar um filtro.</span><span class="sxs-lookup"><span data-stu-id="7f15a-135">On the flyout page, click an element on the widget key or widget chart to create a filter.</span></span>

   ![Createfilter](../media/applyconditionfilter.png)

3. <span data-ttu-id="7f15a-137">Repita as etapas 1-2 para outros widgets vários widgets.</span><span class="sxs-lookup"><span data-stu-id="7f15a-137">Repeat steps 1-2 for other widgets multiple widgets.</span></span> 

4. <span data-ttu-id="7f15a-138">Quando tiver concluído, clique em **salvar como consulta** para salvar suas condições como uma nova consulta de pesquisa para o conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="7f15a-138">When you're done, click **Save as query** to save your conditions as a new search query for the review set.</span></span>

   ![Consulta](../media/savequery.png)

5. <span data-ttu-id="7f15a-140">Feche o **modo de exibição perfil de pesquisa** para retornar ao modo de exibição resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7f15a-140">Close the **Search profile view** to return to the search results view.</span></span>

   <span data-ttu-id="7f15a-141">Se você tiver criado filtros visuais, a consulta resultante será aplicada aos resultados da pesquisa exibidos, e a consulta de pesquisa salva na etapa 4 será exibida em **consultas salvas**.</span><span class="sxs-lookup"><span data-stu-id="7f15a-141">If you have created any visual filters, the resulting query is applied to the search results that are displayed, and the search query that you saved in step 4 is displayed under **Saved queries**.</span></span> <span data-ttu-id="7f15a-142">Para obter mais informações sobre as consultas de análise de revisão, consulte [consultar os dados em um conjunto de revisão](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="7f15a-142">For more information about review set queries, see [Query the data in a review set](review-set-search.md).</span></span>
