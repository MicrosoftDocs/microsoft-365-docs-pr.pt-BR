---
title: Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada
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
description: Você pode adicionar fontes de dados não-custodial a um caso de descoberta eletrônica avançada e colocar uma retenção na fonte de dados. As fontes de dados que não são do custodial são reindexada, de forma que qualquer conteúdo que foi marcado como parcialmente indexado é reprocessado para torná-la totalmente e rapidamente pesquisável.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740348"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="bdb1d-104">Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="bdb1d-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="bdb1d-105">Em casos de descoberta eletrônica avançada, nem sempre atende às suas necessidades para associar uma fonte de dados do Microsoft 365 a um funcionário no caso.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="bdb1d-106">Mas talvez você ainda precise associar esses dados a um caso para que possa procurá-los, adicioná-los a um conjunto de análise e analisá-los e examiná-los.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="bdb1d-107">O recurso na descoberta eletrônica avançada é chamado de *fontes de dados não-custodial* e permite que você adicione dados a um caso sem precisar associá-lo a um funcionário.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="bdb1d-108">Ele também aplica a mesma funcionalidade de descoberta eletrônica avançada a dados não-custodial que estão disponíveis para dados associados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="bdb1d-109">Duas das coisas mais úteis que você pode aplicar a dados não-custodial estão colocando-o em espera e processando-o usando [indexação avançada](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="bdb1d-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="bdb1d-110">Adicionar uma fonte de dados não custodial</span><span class="sxs-lookup"><span data-stu-id="bdb1d-110">Add a non-custodial data source</span></span>

<span data-ttu-id="bdb1d-111">Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em uma ocorrência de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="bdb1d-112">Na home page de **descoberta eletrônica avançada** , clique na ocorrência à qual você deseja adicionar os dados.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="bdb1d-113">Clique na guia **fontes de dados** e, em seguida, clique em **Adicionar fonte de dados**  >  **Adicionar locais de dados**.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="bdb1d-114">Na página novo submenu de **locais de dados não custodial** , escolha as fontes de dados que você deseja adicionar ao caso.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="bdb1d-115">Você pode adicionar várias caixas de correio e sites expandindo as seções do **SharePoint** ou do **Exchange** e clicando em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Adicionar sites do SharePoint e caixas de correio do Exchange como fontes de dados não custodial](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="bdb1d-117">**SharePoint** – clique em **Editar** para adicionar sites.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="bdb1d-118">Selecione um site na lista ou você pode pesquisar um site digitando a URL do site na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="bdb1d-119">Selecione os sites que você deseja adicionar como fontes de dados não responsáveis e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="bdb1d-120">**Exchange** -clique em **Editar** para adicionar caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="bdb1d-121">Digite um nome ou alias (no mínimo três caracteres) na caixa de pesquisa para caixas de correio ou grupos de distribuição.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="bdb1d-122">Selecione as caixas de correio que você deseja adicionar como fontes de dados não responsáveis e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bdb1d-123">Você pode usar as seções do **SharePoint** e do **Exchange** para adicionar sites e caixas de correio associadas a uma equipe ou a um grupo do Yammer como fontes de dados não custodial.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="bdb1d-124">Você precisa adicionar separadamente a caixa de correio e o site associados a uma equipe ou a um grupo do Yammer.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="bdb1d-125">Após adicionar fontes de dados não-custodial, você tem a opção de colocar esses locais em espera ou não.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="bdb1d-126">Marque ou desmarque a caixa de seleção **reter** ao lado da fonte de dados para colocá-la em espera.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="bdb1d-127">Clique em **Adicionar** na parte inferior da página do submenu **novo locais de dados não-custodial** para adicionar as fontes de dados ao caso.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="bdb1d-128">Cada fonte de dados não-custodial adicionada é listada na página **fontes de dados** .</span><span class="sxs-lookup"><span data-stu-id="bdb1d-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="bdb1d-129">Fontes de dados não custodial são identificadas pelo valor de **local dos dados** na coluna **tipo de fonte** .</span><span class="sxs-lookup"><span data-stu-id="bdb1d-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Fontes de dados não custodial na guia fontes de dados](../media/NonCustodialDataSources2.png)

<span data-ttu-id="bdb1d-131">Após adicionar fontes de dados não-custodial ao caso, um trabalho chamado *reindexação de dados não-custodial* é criado e exibido na guia **trabalhos** da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="bdb1d-132">Depois que o trabalho é criado, o processo de indexação avançada em iniciado e as fontes de dados são reindexados.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="bdb1d-133">Gerenciar a retenção de fontes de dados não custodial</span><span class="sxs-lookup"><span data-stu-id="bdb1d-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="bdb1d-134">Depois de colocar uma retenção em uma fonte de dados não custodial, uma política de retenção que contém as fontes de dados não custodial para o caso é criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="bdb1d-135">Quando você coloca outras fontes de dados não-custodial em espera, elas são adicionadas a essa política de retenção.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="bdb1d-136">Abra o caso de descoberta eletrônica avançada e selecione a guia **reter** .</span><span class="sxs-lookup"><span data-stu-id="bdb1d-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="bdb1d-137">Clique em **NCDSHold \<GUID\> -**, onde o valor de GUID é exclusivo do caso.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="bdb1d-138">A página de submenu exibe informações e estatísticas sobre as fontes de dados não custodial em espera.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![A página de submenu de fontes de dados não custodial exibe as estatísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="bdb1d-140">Clique em **Editar retenção** para exibir as fontes de dados não custodial colocadas em espera e execute as seguintes tarefas de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="bdb1d-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="bdb1d-141">Na página **locais** , você pode liberar uma fonte de dados não custodial removendo-a da isenção.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="bdb1d-142">Liberar uma fonte de dados não remove a fonte de dados não custodial da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="bdb1d-143">Ela apenas remove a retenção que foi colocada na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="bdb1d-144">Na página **consulta** , você pode editar a isenção para criar uma retenção baseada em consulta que é aplicada a todas as fontes de dados não-custodial do tha no caso.</span><span class="sxs-lookup"><span data-stu-id="bdb1d-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
