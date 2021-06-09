---
title: Adicionar fontes de dados não custodiais a um Advanced eDiscovery caso
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
description: Você pode adicionar fontes de dados não custodiais a uma Advanced eDiscovery caso e colocar uma espera na fonte de dados. Fontes de dados não custodiais são reindexadas, portanto, qualquer conteúdo marcado como parcialmente indexado é reprocessado para torná-lo pesquisável de forma completa e rápida.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740348"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="deaf5-104">Adicionar fontes de dados não custodiais a um Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="deaf5-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="deaf5-105">Em Advanced eDiscovery, nem sempre ele atendem às suas necessidades para associar uma fonte Microsoft 365 de dados a um custodiante no caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="deaf5-106">Mas você ainda pode precisar associar esses dados a um caso para poder pesquisá-los, adicioná-los a um conjunto de revisão e analisá-los e revisá-los.</span><span class="sxs-lookup"><span data-stu-id="deaf5-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="deaf5-107">O recurso no Advanced eDiscovery é  chamado de fontes de dados não custodiais e permite adicionar dados a uma ocorrência sem precisar associá-los a um custodiante.</span><span class="sxs-lookup"><span data-stu-id="deaf5-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="deaf5-108">Ele também aplica a mesma Advanced eDiscovery a dados não custodiais que estão disponíveis para dados associados ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="deaf5-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="deaf5-109">Duas das coisas mais úteis que você pode aplicar a dados não custodiais é colocá-los em espera e processá-los usando [indexação avançada](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="deaf5-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="deaf5-110">Adicionar uma fonte de dados não custodiada</span><span class="sxs-lookup"><span data-stu-id="deaf5-110">Add a non-custodial data source</span></span>

<span data-ttu-id="deaf5-111">Siga estas etapas para adicionar e gerenciar fontes de dados não custodiais em um Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="deaf5-112">Na home **page Advanced eDiscovery,** clique no caso ao que deseja adicionar os dados.</span><span class="sxs-lookup"><span data-stu-id="deaf5-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="deaf5-113">Clique na **guia Fontes de** dados e clique em Adicionar fonte de **dados** Adicionar locais  >  **de dados**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="deaf5-114">Na página **Sub-subsisão** Novos locais de dados não custodiados, escolha as fontes de dados que você deseja adicionar ao caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="deaf5-115">Você pode adicionar várias caixas de correio e sites expandindo as seções **SharePoint** ou **Exchange** e clicando em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Adicionar SharePoint sites e Exchange caixas de correio como fontes de dados não custodiais](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="deaf5-117">**SharePoint** - Clique **em Editar** para adicionar sites.</span><span class="sxs-lookup"><span data-stu-id="deaf5-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="deaf5-118">Selecione um site na lista ou você pode pesquisar um site digitando a URL do site na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="deaf5-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="deaf5-119">Selecione os sites que você deseja adicionar como fontes de dados não custodiadas e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="deaf5-120">**Exchange** - Clique em **Editar** para adicionar caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="deaf5-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="deaf5-121">Digite um nome ou alias (no mínimo três caracteres) na caixa de pesquisa para caixas de correio ou grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="deaf5-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="deaf5-122">Selecione as caixas de correio que você deseja adicionar como fontes de dados não custodiadas e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="deaf5-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="deaf5-123">Você pode usar as seções **SharePoint** e **Exchange** para adicionar sites e caixas de correio associadas a uma equipe ou grupo Yammer como fontes de dados não custodiais.</span><span class="sxs-lookup"><span data-stu-id="deaf5-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="deaf5-124">Você precisa adicionar separadamente a caixa de correio e o site associados a uma equipe ou Yammer grupo.</span><span class="sxs-lookup"><span data-stu-id="deaf5-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="deaf5-125">Depois de adicionar fontes de dados não custodiais, você tem a opção de colocar esses locais em espera ou não.</span><span class="sxs-lookup"><span data-stu-id="deaf5-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="deaf5-126">Selecione ou desmarque a caixa de seleção **De** espera ao lado da fonte de dados para mantê-la em espera.</span><span class="sxs-lookup"><span data-stu-id="deaf5-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="deaf5-127">Clique **em Adicionar** na parte inferior da página **sub-subsisão** Novos locais de dados não custodiados para adicionar as fontes de dados ao caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="deaf5-128">Cada fonte de dados não custodiada adicionada está listada na página **Fontes de** dados.</span><span class="sxs-lookup"><span data-stu-id="deaf5-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="deaf5-129">Fontes de dados não custodiais são identificadas pelo valor **de local** de dados na coluna **Tipo de** origem.</span><span class="sxs-lookup"><span data-stu-id="deaf5-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Fontes de dados não custodiais na guia Fontes de dados](../media/NonCustodialDataSources2.png)

<span data-ttu-id="deaf5-131">Depois de adicionar fontes de dados não custodiais ao caso, um trabalho chamado *Reindexando* dados não custodiais é criado e exibido na guia **Trabalhos** do caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="deaf5-132">Após a criação do trabalho, o processo de indexação avançada é iniciado e as fontes de dados são reindexadas.</span><span class="sxs-lookup"><span data-stu-id="deaf5-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="deaf5-133">Gerenciar a responsabilidade para fontes de dados não custodiais</span><span class="sxs-lookup"><span data-stu-id="deaf5-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="deaf5-134">Depois de colocar uma suspensão em uma fonte de dados não custodial, uma política de suspensão que contém as fontes de dados não custodiadas para o caso é criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="deaf5-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="deaf5-135">Quando você coloca outras fontes de dados não custodiais em espera, elas são adicionadas a essa política de ressaltou.</span><span class="sxs-lookup"><span data-stu-id="deaf5-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="deaf5-136">Abra a Advanced eDiscovery e selecione a **guia** Segurar.</span><span class="sxs-lookup"><span data-stu-id="deaf5-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="deaf5-137">Clique **em NCDSHold- \<GUID\>**, onde o valor GUID é exclusivo da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="deaf5-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="deaf5-138">A página do sub-uso exibe informações e estatísticas sobre as fontes de dados não custodiadas em espera.</span><span class="sxs-lookup"><span data-stu-id="deaf5-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![A página de sub-sub-subsão para fontes de dados não custodiadas exibe estatísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="deaf5-140">Clique **em Editar espera** para exibir as fontes de dados não custodiais colocadas em espera e executar as seguintes tarefas de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="deaf5-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="deaf5-141">Na página **Locais,** você pode liberar uma fonte de dados não custodiada removendo-a da espera.</span><span class="sxs-lookup"><span data-stu-id="deaf5-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="deaf5-142">Liberar uma fonte de dados não remove a fonte de dados não custodiada do caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="deaf5-143">Ele remove apenas a espera que foi colocada na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="deaf5-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="deaf5-144">Na página **Consulta,** você pode editar a isenção para criar uma isenção baseada em consulta aplicada a todas as fontes de dados não custodiais no caso.</span><span class="sxs-lookup"><span data-stu-id="deaf5-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
