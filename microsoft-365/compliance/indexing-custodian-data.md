---
title: Indexação de dados custodiante avançados
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
description: ''
ms.openlocfilehash: a6259d839dd9a0ca196bae37afe374d1d8f21d53
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "38684869"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="74965-102">Indexação de dados custodiante avançados</span><span class="sxs-lookup"><span data-stu-id="74965-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="74965-103">Quando um Objecté adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo no Office 365 que foi considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="74965-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="74965-104">Esse processo é chamado de *indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="74965-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="74965-105">O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.</span><span class="sxs-lookup"><span data-stu-id="74965-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="74965-106">Para saber mais sobre o processamento de suporte no Office 365 e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="74965-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="74965-107">Tipos de arquivo com suporte na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="74965-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="74965-108">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="74965-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="74965-109">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="74965-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="74965-110">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="74965-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="74965-111">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="74965-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="74965-112">Após a conclusão do processo de indexação avançada, você pode entender a eficácia da reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="74965-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="74965-113">No modo de exibição de indexação de responsáveis, o gráfico lista todos os itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="74965-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="74965-114">O índice híbrido é onde a descoberta eletrônica avançada armazena o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="74965-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="74965-115">O gráfico também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="74965-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="74965-116">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="74965-116">For more information, see:</span></span>

- [<span data-ttu-id="74965-117">Correção de erros durante o processamento de dados</span><span class="sxs-lookup"><span data-stu-id="74965-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="74965-118">Correção de erros de item único</span><span class="sxs-lookup"><span data-stu-id="74965-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="74965-119">Atualizando índices avançados para os responsáveis</span><span class="sxs-lookup"><span data-stu-id="74965-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="74965-120">Quando um responsáveis é adicionado a uma caixa de descoberta eletrônica avançada, todos os itens parcialmente indexados são reprocessados.</span><span class="sxs-lookup"><span data-stu-id="74965-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="74965-121">No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="74965-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="74965-122">Quando necessário, você pode atualizar os índices.</span><span class="sxs-lookup"><span data-stu-id="74965-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="74965-123">Atualizar os índices dos responsáveis é um processo de execução longa.</span><span class="sxs-lookup"><span data-stu-id="74965-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="74965-124">É recomendável que você não atualize os índices mais de uma vez por dia em um caso.</span><span class="sxs-lookup"><span data-stu-id="74965-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
