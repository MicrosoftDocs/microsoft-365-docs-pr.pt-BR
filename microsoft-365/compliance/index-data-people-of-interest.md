---
title: Indexação avançada de dados para uma investigação
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
description: Saiba como usar a indexação avançada para garantir que sua pesquisa Capture todos os dados que você deseja investigar.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b0bb1a757ac70466fb43f2385485ce6da1dc741
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285957"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="f078f-103">Indexação avançada de dados para uma investigação</span><span class="sxs-lookup"><span data-stu-id="f078f-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="f078f-104">O conteúdo no sistema ativo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.</span><span class="sxs-lookup"><span data-stu-id="f078f-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="f078f-105">Ao lidar com o despejo de dados de alto risco, você deseja garantir que sua pesquisa tenha capturado todos os dados que você deseja investigar.</span><span class="sxs-lookup"><span data-stu-id="f078f-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="f078f-106">Quando uma pessoa de interesse é adicionada a uma investigação de dados, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="f078f-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span> <span data-ttu-id="f078f-107">Esse processo é chamado de *indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="f078f-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="f078f-108">Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="f078f-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="f078f-109">Tipos de arquivo com suporte em investigações de dados</span><span class="sxs-lookup"><span data-stu-id="f078f-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="f078f-110">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="f078f-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="f078f-111">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="f078f-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="f078f-112">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="f078f-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="f078f-113">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="f078f-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="f078f-114">Após a conclusão do processo de indexação avançada, você pode entender a eficácia do reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="f078f-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="f078f-115">Na exibição de indexação de pessoas de interesse, o gráfico lista todos os itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="f078f-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="f078f-116">O índice híbrido é onde as investigações de dados (prévia) armazenam o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="f078f-116">The hybrid index is where Data Investigations (preview) stores the reprocessed content.</span></span>

<span data-ttu-id="f078f-117">O gráfico também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="f078f-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="f078f-118">Para obter mais informações, consulte [Error remediation When Processing data](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="f078f-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="f078f-119">Atualizando índices avançados para pessoas de interesse</span><span class="sxs-lookup"><span data-stu-id="f078f-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="f078f-120">Quando uma pessoa de interesse é adicionada a uma investigação de dados, todos os itens parcialmente indexados são reprocessados.</span><span class="sxs-lookup"><span data-stu-id="f078f-120">When a person of interest is added to a data investigation, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="f078f-121">No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="f078f-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="f078f-122">Quando necessário, você pode atualizar os índices.</span><span class="sxs-lookup"><span data-stu-id="f078f-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="f078f-123">A atualização de pessoas de índices de interesse é um processo de execução demorada.</span><span class="sxs-lookup"><span data-stu-id="f078f-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="f078f-124">É recomendável que você não atualize os índices mais de uma vez por dia em uma investigação.</span><span class="sxs-lookup"><span data-stu-id="f078f-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
