---
title: Adicionar fontes de dados não custodial a um caso de Descoberta Avançada
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
description: Você pode adicionar fontes de dados não custodial a um caso de Descoberta eDiscovery Avançada e colocar em espera a fonte de dados. Fontes de dados não custodial são reindexadas, portanto, qualquer conteúdo marcado como parcialmente indexado é reprocessado para torná-lo completamente e rapidamente pesquisável.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740348"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="279bd-104">Adicionar fontes de dados não custodial a um caso de Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="279bd-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="279bd-105">Em casos de Descoberta Avançada, nem sempre ela atenderá às suas necessidades de associar uma fonte de dados do Microsoft 365 a um custodiante no caso.</span><span class="sxs-lookup"><span data-stu-id="279bd-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="279bd-106">Mas talvez ainda seja necessário associar esses dados a uma ocorrência para que você possa pesquisá-los, adicioná-los a um conjunto de revisão e analisá-los e revisá-los.</span><span class="sxs-lookup"><span data-stu-id="279bd-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="279bd-107">O recurso na Descoberta Avançada  é chamado de fontes de dados não custodial e permite adicionar dados a uma ocorrência sem precisar associá-los a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="279bd-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="279bd-108">Também se aplica a mesma funcionalidade de Descoberta Avançada a dados não custodial que estão disponíveis para dados associados ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="279bd-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="279bd-109">Duas das coisas mais úteis que você pode aplicar a dados não custodial é colocá-los em espera e processá-los usando [indexação avançada.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="279bd-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="279bd-110">Adicionar uma fonte de dados não custodial</span><span class="sxs-lookup"><span data-stu-id="279bd-110">Add a non-custodial data source</span></span>

<span data-ttu-id="279bd-111">Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em um caso de Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="279bd-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="279bd-112">Na home page **Da Descoberta Avançada,** clique na ocorrência à que você deseja adicionar os dados.</span><span class="sxs-lookup"><span data-stu-id="279bd-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="279bd-113">Clique na **guia Fontes de dados** e clique em Adicionar fonte de **dados** Adicionar locais  >  **de dados.**</span><span class="sxs-lookup"><span data-stu-id="279bd-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="279bd-114">Na página do sub-subconsiência Novos locais de dados sem custodiante, escolha as fontes de dados que você deseja adicionar à ocorrência. </span><span class="sxs-lookup"><span data-stu-id="279bd-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="279bd-115">Você pode adicionar várias caixas de correio e sites expandindo as seções **do SharePoint** ou **do Exchange** e clicando em **Editar.**</span><span class="sxs-lookup"><span data-stu-id="279bd-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Adicionar sites do SharePoint e caixas de correio do Exchange como fontes de dados não custodial](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="279bd-117">**SharePoint** - Clique **em Editar** para adicionar sites.</span><span class="sxs-lookup"><span data-stu-id="279bd-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="279bd-118">Selecione um site na lista ou pesquise um site digitando a URL do site na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="279bd-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="279bd-119">Selecione os sites que você deseja adicionar como fontes de dados não custodiante e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="279bd-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="279bd-120">**Exchange** - Clique **em Editar** para adicionar caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="279bd-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="279bd-121">Digite um nome ou alias (no mínimo três caracteres) na caixa de pesquisa para caixas de correio ou grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="279bd-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="279bd-122">Selecione as caixas de correio que você deseja adicionar como fontes de dados não custodiante e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="279bd-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="279bd-123">Você pode usar as seções do **SharePoint** e do **Exchange** para adicionar sites e caixas de correio associadas a uma equipe ou grupo do Yammer como fontes de dados não custodial.</span><span class="sxs-lookup"><span data-stu-id="279bd-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="279bd-124">Você precisa adicionar separadamente a caixa de correio e o site associados a uma equipe ou grupo do Yammer.</span><span class="sxs-lookup"><span data-stu-id="279bd-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="279bd-125">Depois de adicionar fontes de dados não custodial, você tem a opção de colocar esses locais em espera ou não.</span><span class="sxs-lookup"><span data-stu-id="279bd-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="279bd-126">Marque ou desmarque a **caixa de** seleção De espera ao lado da fonte de dados para mantê-la em espera.</span><span class="sxs-lookup"><span data-stu-id="279bd-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="279bd-127">Clique **em Adicionar** na parte inferior da página **do** sub-menu Novos locais de dados sem custodiante para adicionar as fontes de dados à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="279bd-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="279bd-128">Cada fonte de dados não custodial que você adicionou está listada na **página Fontes de** dados.</span><span class="sxs-lookup"><span data-stu-id="279bd-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="279bd-129">As fontes de dados não custodial são identificadas pelo valor **do** local dos dados na coluna **Tipo de** origem.</span><span class="sxs-lookup"><span data-stu-id="279bd-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Fontes de dados não custodial na guia Fontes de dados](../media/NonCustodialDataSources2.png)

<span data-ttu-id="279bd-131">Depois de adicionar fontes de dados não custodial ao caso, um trabalho chamado *Reindexação* de dados não custodial é criado e exibido na guia Trabalhos do caso. </span><span class="sxs-lookup"><span data-stu-id="279bd-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="279bd-132">Depois que o trabalho é criado, o processo de indexação Avançada é iniciado e as fontes de dados são reindexadas.</span><span class="sxs-lookup"><span data-stu-id="279bd-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="279bd-133">Gerenciar a responsabilidade por fontes de dados não custodial</span><span class="sxs-lookup"><span data-stu-id="279bd-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="279bd-134">Depois de colocar em espera uma fonte de dados não custodial, uma política de suspensão que contém as fontes de dados não custodial para o caso é criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="279bd-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="279bd-135">Quando você coloca outras fontes de dados não custodial em espera, elas são adicionadas a essa política de espera.</span><span class="sxs-lookup"><span data-stu-id="279bd-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="279bd-136">Abra a ocorrência de Descoberta Avançada e selecione **a** guia Espera.</span><span class="sxs-lookup"><span data-stu-id="279bd-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="279bd-137">Clique **em NCDSHold- \<GUID\>**, onde o valor de GUID é exclusivo para a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="279bd-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="279bd-138">A página de subconsiência exibe informações e estatísticas sobre as fontes de dados não custodial em espera.</span><span class="sxs-lookup"><span data-stu-id="279bd-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![A página de subconsiência para fontes de dados não custodial em espera exibe estatísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="279bd-140">Clique **em Editar espera** para exibir as fontes de dados não custodial colocadas em espera e executar as seguintes tarefas de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="279bd-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="279bd-141">Na página **Locais,** você pode liberar uma fonte de dados não custodial removendo-a da espera.</span><span class="sxs-lookup"><span data-stu-id="279bd-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="279bd-142">Liberar uma fonte de dados não remove a fonte de dados não custodial do caso.</span><span class="sxs-lookup"><span data-stu-id="279bd-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="279bd-143">Ela apenas remove a espera que foi colocada na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="279bd-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="279bd-144">Na página **Consulta,** você pode editar a isenção para criar uma isenção baseada em consulta que é aplicada a todas as fontes de dados não custodial no caso.</span><span class="sxs-lookup"><span data-stu-id="279bd-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
