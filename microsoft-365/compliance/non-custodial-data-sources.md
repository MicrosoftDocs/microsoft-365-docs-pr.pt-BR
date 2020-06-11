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
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode adicionar fontes de dados não-custodial a um caso de descoberta eletrônica avançada e colocar uma retenção na fonte de dados. As fontes de dados não custodial são indexadas novamente, de forma que qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-la totalmente e rapidamente pesquisável.
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695493"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="2f5e6-104">Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="2f5e6-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="2f5e6-105">Em casos de descoberta eletrônica avançada, nem sempre atende às suas necessidades para associar uma fonte de dados do Microsoft 365 a um funcionário no caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="2f5e6-106">Mas talvez ainda seja necessário associar esses dados a um caso para que você pesquise, adicione-o ao conjunto de revisão e revise-o.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-106">But you may still need to associate that data with a case so that you search it, add it to review set, and review it.</span></span> <span data-ttu-id="2f5e6-107">O novo recurso chamado de *fontes de dados não-custodial* permite que você adicione dados a um caso sem precisar associar os dados a um funcionário.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-107">The new feature called *non-custodial data sources* lets you add data to a case without having to associate the data to a custodian.</span></span> <span data-ttu-id="2f5e6-108">Ele também aplica a mesma funcionalidade de descoberta eletrônica avançada a dados não-custodial que estão disponíveis para dados associados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="2f5e6-109">Dois dos recursos mais úteis que você pode aplicar a dados não custodial estão colocando-o em espera e processando-o usando [indexação avançada](indexing-custodian-data.md).</span><span class="sxs-lookup"><span data-stu-id="2f5e6-109">Two of the most useful features that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="2f5e6-110">Adicionar uma fonte de dados não custodial</span><span class="sxs-lookup"><span data-stu-id="2f5e6-110">Add a non-custodial data source</span></span>

<span data-ttu-id="2f5e6-111">Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em uma ocorrência de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="2f5e6-112">Na home page de **descoberta eletrônica avançada** , clique na ocorrência à qual você deseja adicionar os dados.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="2f5e6-113">Na página **fontes** , clique na guia **locais dos dados** e, em seguida, clique em **Adicionar local de dados**.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-113">On the **Sources** page, click the **Data locations** tab, and then click **Add data location**.</span></span>

3. <span data-ttu-id="2f5e6-114">Clique em **Adicionar local de dados** e escolha as fontes de dados que você deseja adicionar ao caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-114">Click **Add data location** and choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="2f5e6-115">Você pode adicionar várias caixas de correio e sites.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-115">You can add multiple mailboxes and sites.</span></span>

4. <span data-ttu-id="2f5e6-116">Na página **escolher locais** no assistente, adicione caixas de correio ou sites (ou ambos) como fontes de dados não-custodial ao caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-116">On the **Choose locations** page in the wizard, add mailboxes or sites (or both) as non-custodial data sources to the case.</span></span>

5. <span data-ttu-id="2f5e6-117">Após adicionar as fontes de dados, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-117">After adding the data sources, click **Next**.</span></span>

6. <span data-ttu-id="2f5e6-118">Na página **local** , escolha as fontes de dados que você deseja colocar em espera marcando ou desmarcando a caixa de seleção associada.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-118">On the **Place holds** page, choose which data sources you want to place on hold by selecting or unselecting the associated checkbox.</span></span>

7. <span data-ttu-id="2f5e6-119">Verifique as seleções de retenção e clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-119">Verify the hold selections and then click **Submit**.</span></span>

   <span data-ttu-id="2f5e6-120">Cada fonte de dados não-custodial adicionada é listada na página **fontes de dados** .</span><span class="sxs-lookup"><span data-stu-id="2f5e6-120">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span>

   <span data-ttu-id="2f5e6-121">Além disso, um trabalho chamado *reindexação de dados não-custodial* é criado e exibido na guia **trabalhos** do caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-121">Also, a job named *Re-indexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="2f5e6-122">Depois que o trabalho é criado, o processo de indexação avançada em iniciado e as fontes de dados são re-indexado.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-122">After the job is created, the Advanced indexing process in initiated and the data sources are re-indexed.</span></span>

## <a name="managing-the-hold-on-non-custodial-data-sources"></a><span data-ttu-id="2f5e6-123">Gerenciando a espera em fontes de dados não-custodial</span><span class="sxs-lookup"><span data-stu-id="2f5e6-123">Managing the hold on non-custodial data sources</span></span>

<span data-ttu-id="2f5e6-124">Depois que você coloca uma retenção em uma fonte de dados não custodial, uma política de retenção que contém todas as fontes de dados não custodial para o caso é criada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-124">After you place a hold on a non-custodial data source, a hold policy that contains all non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="2f5e6-125">Quando você coloca outras fontes de dados não-custodial em espera, elas são adicionadas a essa política de retenção.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-125">When you place additional non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="2f5e6-126">Na **Home** Page do caso, clique na guia **isenções** .</span><span class="sxs-lookup"><span data-stu-id="2f5e6-126">On the **Home** page of the case, click the **Holds** tab.</span></span>

2. <span data-ttu-id="2f5e6-127">Na página **isenções** , clique em \*\*NCDSHold- \<GUID\> \*\*, onde o valor de GUID é exclusivo do caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-127">On the **Holds** page, and click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

3. <span data-ttu-id="2f5e6-128">Na página do menu suspenso, clique em **Editar retenção** para exibir todas as fontes de dados não custodial que são colocadas em espera.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-128">On the flyout page, click **Edit hold** to view all the non-custodial data sources that are placed on hold.</span></span>

<span data-ttu-id="2f5e6-129">Você pode executar a seguinte tarefa de gerenciamento em fontes de dados não-custodial:</span><span class="sxs-lookup"><span data-stu-id="2f5e6-129">You can perform the following management task on non-custodial data sources:</span></span>

- <span data-ttu-id="2f5e6-130">Você pode editar a isenção para criar uma retenção baseada em consulta que é aplicada a todas as fontes de dados não-custodial no caso.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-130">You can edit the hold to create a query-based hold that is applied to all non-custodial data sources in the case.</span></span>

- <span data-ttu-id="2f5e6-131">Você pode liberar uma fonte de dados não custodial da isenção.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-131">You can release a non-custodial data source from the hold.</span></span> <span data-ttu-id="2f5e6-132">Liberar uma fonte de dados não remove a fonte de dados não custodial da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-132">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="2f5e6-133">Ela apenas remove a retenção que foi colocada na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2f5e6-133">It only removes the hold that was placed on the data source.</span></span>
