---
title: Indexação de dados custodiante avançados
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
description: Quando um custodiante é adicionado a um caso de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911205"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="14da6-103">Indexação de dados custodiante avançados</span><span class="sxs-lookup"><span data-stu-id="14da6-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="14da6-104">Quando um custodiante é adicionado a um caso de Descoberta Avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="14da6-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="14da6-105">Esse processo é chamado *de indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="14da6-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="14da6-106">O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivo sem suporte ou quando os limites de tamanho do arquivo de indexação são encontrados.</span><span class="sxs-lookup"><span data-stu-id="14da6-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="14da6-107">Para saber mais sobre o suporte ao processamento e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="14da6-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="14da6-108">Tipos de arquivo com suporte na Descoberta Avançada da Descoberta</span><span class="sxs-lookup"><span data-stu-id="14da6-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="14da6-109">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="14da6-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="14da6-110">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="14da6-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="14da6-111">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="14da6-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="14da6-112">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="14da6-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="14da6-113">Depois que o processo de indexação avançada for concluído, você poderá obter uma compreensão da eficácia do reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="14da6-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="14da6-114">No modo de exibição De resultados de indexação avançada na guia **Processamento** de uma ocorrência, o gráfico lista o número de itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="14da6-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="14da6-115">O índice híbrido é onde a Descoberta Virtual Avançada armazena o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="14da6-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="14da6-116">Essa exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="14da6-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="14da6-117">Para mais informações, confira:</span><span class="sxs-lookup"><span data-stu-id="14da6-117">For more information, see:</span></span>

- [<span data-ttu-id="14da6-118">Correção de erros durante o processamento de dados</span><span class="sxs-lookup"><span data-stu-id="14da6-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="14da6-119">Correção de erros de item único</span><span class="sxs-lookup"><span data-stu-id="14da6-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="14da6-120">Atualizando o índice avançado para custodiantes</span><span class="sxs-lookup"><span data-stu-id="14da6-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="14da6-121">Quando um custodiante é adicionado a um caso de Descoberta Avançada, todos os itens parcialmente indexados são reprocessados.</span><span class="sxs-lookup"><span data-stu-id="14da6-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="14da6-122">No entanto, com o passar do tempo, itens indexados mais parcialmente podem ser adicionados à caixa de correio de um usuário ou à conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="14da6-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="14da6-123">Se necessário, você pode atualizar o índice para o custodiante específico.</span><span class="sxs-lookup"><span data-stu-id="14da6-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="14da6-124">Para obter mais informações, consulte [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="14da6-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="14da6-125">Você também pode atualizar o índice para todos os custodiantes em um caso clicando no índice **Atualizar** na guia **Processamento.**</span><span class="sxs-lookup"><span data-stu-id="14da6-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="14da6-126">A atualização dos índices de custodiante é um processo em execução longa.</span><span class="sxs-lookup"><span data-stu-id="14da6-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="14da6-127">É recomendável que você não atualize índices mais de uma vez por dia em um caso.</span><span class="sxs-lookup"><span data-stu-id="14da6-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>