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
ms.openlocfilehash: dc7d73c233aa48b88e9dce32fad613ccc5e19333
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035057"
---
# <a name="advanced-indexing-of-data-for-an-investigation"></a><span data-ttu-id="2d19e-103">Indexação avançada de dados para uma investigação</span><span class="sxs-lookup"><span data-stu-id="2d19e-103">Advanced indexing of data for an investigation</span></span>

<span data-ttu-id="2d19e-104">O conteúdo no sistema ativo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.</span><span class="sxs-lookup"><span data-stu-id="2d19e-104">Content in the live system can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span> <span data-ttu-id="2d19e-105">Ao lidar com o despejo de dados de alto risco, você deseja garantir que sua pesquisa tenha capturado todos os dados que você deseja investigar.</span><span class="sxs-lookup"><span data-stu-id="2d19e-105">When you are dealing with high risk data spill, you want to make sure that your search captured all data that you want to investigate.</span></span> <span data-ttu-id="2d19e-106">Quando uma pessoa de interesse é adicionada a uma investigação de dados, qualquer conteúdo considerado parcialmente indexado é processado novamente para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="2d19e-106">When a person of interest is added to a Data investigation, any content that was deemed as partially indexed is re-processed to make it fully searchable.</span></span> <span data-ttu-id="2d19e-107">Esse processo é chamado de *indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="2d19e-107">This process is called *Advanced indexing*.</span></span> 

<span data-ttu-id="2d19e-108">Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="2d19e-108">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="2d19e-109">Tipos de arquivo com suporte em investigações de dados</span><span class="sxs-lookup"><span data-stu-id="2d19e-109">Supported file types in Data Investigations</span></span>](supported-filetypes-datainvestigations.md)

- [<span data-ttu-id="2d19e-110">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="2d19e-110">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="2d19e-111">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="2d19e-111">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="2d19e-112">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="2d19e-112">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="2d19e-113">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="2d19e-113">Viewing Advanced indexing results</span></span>

<span data-ttu-id="2d19e-114">Após a conclusão do processo de indexação avançada, você pode entender a eficácia da reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="2d19e-114">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="2d19e-115">Na exibição de indexação de pessoas de interesse, o gráfico lista todos os itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="2d19e-115">In the People of interest indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="2d19e-116">O índice híbrido é onde as investigações de dados (prévia) armazenam o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="2d19e-116">The hybrid index is where Data Investigations (Preview) stores the re-processed content.</span></span>

<span data-ttu-id="2d19e-117">O gráfico também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2d19e-117">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="2d19e-118">Para obter mais informações, consulte [Error remediation When Processing data](error-remediation.md).</span><span class="sxs-lookup"><span data-stu-id="2d19e-118">For more information, see [Error remediation when processing data](error-remediation.md).</span></span>

## <a name="updating-advanced-indexes-for-people-of-interest"></a><span data-ttu-id="2d19e-119">Atualizando índices avançados para pessoas de interesse</span><span class="sxs-lookup"><span data-stu-id="2d19e-119">Updating Advanced indexes for people of interest</span></span>

<span data-ttu-id="2d19e-120">Quando uma pessoa de interesse é adicionada a uma investigação de dados, todos os itens parcialmente indexados são processados novamente.</span><span class="sxs-lookup"><span data-stu-id="2d19e-120">When a person of interest is added to a data investigation, all partially indexed items are re-processed.</span></span> <span data-ttu-id="2d19e-121">No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2d19e-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="2d19e-122">Quando necessário, você pode atualizar os índices.</span><span class="sxs-lookup"><span data-stu-id="2d19e-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="2d19e-123">A atualização de pessoas de índices de interesse é um processo de execução demorada.</span><span class="sxs-lookup"><span data-stu-id="2d19e-123">Updating people of interest indexes is a long running process.</span></span> <span data-ttu-id="2d19e-124">É recomendável que você não atualize os índices mais de uma vez por dia em uma investigação.</span><span class="sxs-lookup"><span data-stu-id="2d19e-124">It's recommended that you don't update indexes more than once per day in an investigation.</span></span>
