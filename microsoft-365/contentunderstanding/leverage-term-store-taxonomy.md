---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Aproveitar a taxonomia do repositório de termos ao criar um extrator em seu documento entendendo o modelo no Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295712"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="10ee5-103">Aproveitar a taxonomia do repositório de termos ao criar um extrator</span><span class="sxs-lookup"><span data-stu-id="10ee5-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="10ee5-104">Ao criar um extrator em seu documento entendendo o modelo no SharePoint Syntex, você pode aproveitar a taxonomia do repositório de termos [dos serviços de metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata#terms) para exibir os termos preferenciais dos dados extraídos.</span><span class="sxs-lookup"><span data-stu-id="10ee5-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="10ee5-105">Por exemplo, o modelo identifica e classifica todos os documentos de **contrato** que são carregados na biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="10ee5-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="10ee5-106">Além disso, o modelo também extrai um valor de **serviço de contrato** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="10ee5-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="10ee5-107">Entre os vários valores de serviços de contrato nos contratos, há vários valores mais antigos que sua empresa não usa mais e foi renomeado.</span><span class="sxs-lookup"><span data-stu-id="10ee5-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="10ee5-108">Por exemplo, todas as referências aos termos *design*, *elementos gráficos*ou serviços de contrato *topografia* agora devem ser chamadas de *criativo*.</span><span class="sxs-lookup"><span data-stu-id="10ee5-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="10ee5-109">Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você deseja que ele exiba o termo atual-criativo-no modo de exibição de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="10ee5-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="10ee5-110">No exemplo abaixo, ao treinar o modelo, vemos que um documento de exemplo contém o termo de *design*desatualizado.</span><span class="sxs-lookup"><span data-stu-id="10ee5-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Repositório de termos](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="10ee5-112">Sinônimos de conjunto de termos</span><span class="sxs-lookup"><span data-stu-id="10ee5-112">Term set synonyms</span></span> 

<span data-ttu-id="10ee5-113">Os conjuntos de termos são configurados no repositório de termos de serviços de metadados gerenciados no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="10ee5-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="10ee5-114">No exemplo abaixo, o [conjunto de termos](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *dos serviços de contrato* é configurado para incluir vários termos, incluindo *criativo*.</span><span class="sxs-lookup"><span data-stu-id="10ee5-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="10ee5-115">Os detalhes de ti mostram que o termo tem três sinônimos (*design*, *elementos gráficos*e *topografia*) e que os sinônimos devem ser traduzidos para *criativo*.</span><span class="sxs-lookup"><span data-stu-id="10ee5-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="10ee5-117"><Mike, aqui está onde não tenho certeza sobre como descrever isso.</span><span class="sxs-lookup"><span data-stu-id="10ee5-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="10ee5-118">Qual ação diz ao modelo que quando crio um extrator para extrair e exibir uma coluna de serviços de contrato, como essa coluna "marcada" para usar o conjunto de termos de metadados gerenciados para serviços de criação? ></span><span class="sxs-lookup"><span data-stu-id="10ee5-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="10ee5-119">Configurar a coluna de site de biblioteca de documentos para um campo de metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="10ee5-119">Configure your document library site column for a managed metadata field</span></span>


   ![Criar metadados gerenciados](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="10ee5-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="10ee5-121">See Also</span></span>
[<span data-ttu-id="10ee5-122">Introdução aos metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="10ee5-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="10ee5-123">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="10ee5-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="10ee5-124">Criar uma coluna de metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="10ee5-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





