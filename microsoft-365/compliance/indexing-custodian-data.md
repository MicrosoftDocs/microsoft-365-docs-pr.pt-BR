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
description: ''
ms.openlocfilehash: 5ab54e84de7434a16bdf7eb7d04fad7b9af05440
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600628"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="910a1-102">Indexação de dados custodiante avançados</span><span class="sxs-lookup"><span data-stu-id="910a1-102">Advanced indexing of custodian data</span></span>

<span data-ttu-id="910a1-103">Quando um Objecté adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo no Office 365 que foi considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="910a1-103">When a custodian is added to an Advanced eDiscovery case, any content in Office 365 that was deemed as partially indexed is re-processed to make it fully searchable.</span></span>  <span data-ttu-id="910a1-104">Esse processo é chamado de *indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="910a1-104">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="910a1-105">O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.</span><span class="sxs-lookup"><span data-stu-id="910a1-105">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="910a1-106">Para saber mais sobre o processamento de suporte no Office 365 e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="910a1-106">To learn more about processing support in Office 365 and partially indexed items, see:</span></span>

- [<span data-ttu-id="910a1-107">Tipos de arquivo com suporte na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="910a1-107">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)
- [<span data-ttu-id="910a1-108">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="910a1-108">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)
- [<span data-ttu-id="910a1-109">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="910a1-109">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [<span data-ttu-id="910a1-110">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="910a1-110">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="910a1-111">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="910a1-111">Viewing Advanced indexing results</span></span>

<span data-ttu-id="910a1-112">Após a conclusão do processo de indexação avançada, você pode entender a eficácia da reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="910a1-112">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of re-processing.</span></span>  <span data-ttu-id="910a1-113">No modo de exibição de indexação de responsáveis, o gráfico lista todos os itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="910a1-113">In the Custodian Indexing view, the graph lists all items added to the *hybrid index*.</span></span>  <span data-ttu-id="910a1-114">O índice híbrido é onde a descoberta eletrônica avançada armazena o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="910a1-114">The hybrid index is where Advanced eDiscovery stores the re-processed content.</span></span>

<span data-ttu-id="910a1-115">O gráfico também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="910a1-115">The graph also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="910a1-116">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="910a1-116">For more information, see:</span></span>

- [<span data-ttu-id="910a1-117">Correção de erros durante o processamento de dados</span><span class="sxs-lookup"><span data-stu-id="910a1-117">Error remediation when processing data</span></span>](error-remediation.md)
- [<span data-ttu-id="910a1-118">Correção de erros de item único</span><span class="sxs-lookup"><span data-stu-id="910a1-118">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a><span data-ttu-id="910a1-119">Atualizando índices avançados para os responsáveis</span><span class="sxs-lookup"><span data-stu-id="910a1-119">Updating Advanced indexes for custodians</span></span>

<span data-ttu-id="910a1-120">Quando um responsáveis é adicionado a uma caixa de descoberta eletrônica avançada, todos os itens parcialmente indexados são reprocessados.</span><span class="sxs-lookup"><span data-stu-id="910a1-120">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are re-processed.</span></span> <span data-ttu-id="910a1-121">No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="910a1-121">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="910a1-122">Quando necessário, você pode atualizar os índices.</span><span class="sxs-lookup"><span data-stu-id="910a1-122">When needed, you can update the indexes.</span></span>

> [!NOTE]
> <span data-ttu-id="910a1-123">Atualizar os índices dos responsáveis é um processo de execução longa.</span><span class="sxs-lookup"><span data-stu-id="910a1-123">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="910a1-124">É recomendável que você não atualize os índices mais de uma vez por dia em um caso.</span><span class="sxs-lookup"><span data-stu-id="910a1-124">It's recommended that you don't update indexes more than once per day in a case.</span></span>
