---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Utilize a taxonomia de repositório de termos ao criar um extrator em seu modelo de compreensão de documento no Microsoft SharePoint Syntex.
ms.openlocfilehash: aff2df6a96fdfee7380651f68e647019e9485658
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975734"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="c1064-103">Aproveitar a taxonomia do repositório de termos ao criar um extrator</span><span class="sxs-lookup"><span data-stu-id="c1064-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="c1064-104">Ao criar um extrator em seu modelo de compreensão de documento usando o SharePoint Syntex, você pode aproveitar os conjuntos de termos globais no [repositório de termos](https://docs.microsoft.com/sharepoint/managed-metadata) para exibir os termos preferenciais para os dados extraídos.</span><span class="sxs-lookup"><span data-stu-id="c1064-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](https://docs.microsoft.com/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="c1064-105">Por exemplo, o modelo identifica e classifica todos os documentos de **Contrato** que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="c1064-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="c1064-106">Além disso, o modelo também extrai um valor de **Serviços contratados** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c1064-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="c1064-107">Entre os vários valores dos Serviços contratados nos contratos, há vários valores mais antigos que a sua empresa não usa mais e foi renomeado.</span><span class="sxs-lookup"><span data-stu-id="c1064-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="c1064-108">Por exemplo, todas as referências aos termos de serviços contratados *Design*, *Gráficos* ou *Topografia* devem agora ser chamados *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="c1064-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="c1064-109">Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você quer que ele exiba o termo atual - Criativo - no modo de exibição da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c1064-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="c1064-110">No exemplo a seguir, enquanto treina o modelo, vemos que um documento de exemplo contém o termo desatualizado *Design*.</span><span class="sxs-lookup"><span data-stu-id="c1064-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Repositório de termos](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="c1064-112">Usar uma coluna de metadados gerenciados no extrator</span><span class="sxs-lookup"><span data-stu-id="c1064-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="c1064-113">Os conjuntos de termos são configurados no repositório de termos de serviços de Metadados Gerenciados (MMS) no Centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c1064-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="c1064-114">No exemplo abaixo, o *Contrato de Serviços* [conjunto de termos](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) está configurado para incluir vários termos, incluindo o *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="c1064-114">In the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include several terms, including *Creative*.</span></span>  <span data-ttu-id="c1064-115">Os detalhes mostram que o termo tem três sinônimos (*Design*, *Gráficos* e *Topografia*) e os sinônimos devem ser traduzidos para *Criativo*.</span><span class="sxs-lookup"><span data-stu-id="c1064-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="c1064-117">Pode haver muitos motivos pelos quais você pode querer usar um sinônimo em seu conjunto de termos.</span><span class="sxs-lookup"><span data-stu-id="c1064-117">There could be many reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="c1064-118">Por exemplo, pode haver termos desatualizados, termos renomeados ou variações de nome entre seus departamentos de organizações.</span><span class="sxs-lookup"><span data-stu-id="c1064-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="c1064-119">Para disponibilizar o campo de metadados gerenciados para seleção ao criar seu extrator em seu modelo, você precisa [adicioná-lo como uma coluna de site de metadados gerenciados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="c1064-119">To make the managed metadata field available to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="c1064-120">Depois de adicionar a coluna do site, você pode selecioná-la ao criar o extrator para o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="c1064-120">After you add the site column, you can select it when you create the extractor for your model.</span></span>

   ![Serviços contratados](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="c1064-122">Depois de aplicar seu modelo à biblioteca de documentos, quando os documentos forem carregados na biblioteca, a coluna de *Serviços criativos* exibirá o termo preferido (*Criativo*) quando o extrator encontrar qualquer um dos valores de sinônimos (*Design*, *Gráficos* e *Topografia*).</span><span class="sxs-lookup"><span data-stu-id="c1064-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Coluna de serviços contratados](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="c1064-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1064-124">See Also</span></span>
[<span data-ttu-id="c1064-125">Introdução a Metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="c1064-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="c1064-126">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="c1064-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c1064-127">Criar uma coluna de metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="c1064-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





