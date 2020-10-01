---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Use a taxonomia do repositório de termos ao criar um extrator no seu modelo de compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: 457cab51f8dd19e95707801f793cdf2aa267d18f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321284"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="6c3c9-103">Aproveitar a taxonomia do repositório de termos ao criar um extrator</span><span class="sxs-lookup"><span data-stu-id="6c3c9-103">Leverage term store taxonomy when creating an extractor</span></span>

<span data-ttu-id="6c3c9-104">Ao criar um extrator no modelo de compreensão de documentos no SharePoint Syntex, você pode aproveitar a taxonomia do repositório de termos dos [serviços de metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para exibir os termos preferenciais para os dados que você extrai.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="6c3c9-105">Por exemplo, o modelo identifica e classifica todos os documentos de **Contrato** que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="6c3c9-106">Além disso, o modelo também extrai um valor de **Serviços contratados** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="6c3c9-107">Entre os vários valores dos Serviços contratados nos contratos, há vários valores mais antigos que a sua empresa não usa mais e foi renomeado.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="6c3c9-108">Por exemplo, todas as referências aos termos de serviços contratados *Design*, *Gráficos*ou *Topografia* devem agora ser chamados *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="6c3c9-109">Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você quer que ele exiba o termo atual - Criativo - no modo de exibição da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="6c3c9-110">No exemplo a seguir, enquanto treina o modelo, vemos que um documento de exemplo contém o termo desatualizado *Design*.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Repositório de termos](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="6c3c9-112">Usar uma coluna de metadados gerenciados no extrator</span><span class="sxs-lookup"><span data-stu-id="6c3c9-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="6c3c9-113">Os conjuntos de termos são configurados no repositório de termos serviços de metadados gerenciados no Centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="6c3c9-114">No exemplo a seguir, o *conjunto de termos* dos [Serviços contratados](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) é configurado para incluir um número de termos, incluindo *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="6c3c9-115">Os detalhes mostram que o termo tem três sinônimos (*Design*, *Gráficos* e *Topografia*) e os sinônimos devem ser traduzidos para *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="6c3c9-117">Pode haver vários motivos pelos quais você pode querer usar um sinônimo em seu conjunto de termos.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-117">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="6c3c9-118">Por exemplo, pode haver termos desatualizados, termos renomeados ou variações de nome entre seus departamentos de organizações.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="6c3c9-119">Para disponibilizar o campo de metadados gerenciados para seleção quando você cria o seu extrador em seu modelo, é necessário [adicioná-lo como uma coluna de site de metadados gerenciados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="6c3c9-119">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="6c3c9-120">Depois que você adicionar a coluna de site, ela estará disponível para você selecionar quando criar o extrator para o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="6c3c9-120">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![Serviços contratados](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="6c3c9-122">Depois de aplicar seu modelo à biblioteca de documentos, quando os documentos forem carregados na biblioteca, a coluna de *Serviços criativos* exibirá o termo preferido (*Criativo*) quando o extrator encontrar qualquer um dos valores de sinônimos (*Design*, *Gráficos*e *Topografia*).</span><span class="sxs-lookup"><span data-stu-id="6c3c9-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Coluna de serviços contratados](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="6c3c9-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="6c3c9-124">See Also</span></span>
[<span data-ttu-id="6c3c9-125">Introdução a Metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="6c3c9-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="6c3c9-126">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="6c3c9-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="6c3c9-127">Criar uma coluna de metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="6c3c9-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





