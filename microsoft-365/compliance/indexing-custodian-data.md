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
description: Quando um qualificador é adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750752"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="d7262-103">Indexação de dados custodiante avançados</span><span class="sxs-lookup"><span data-stu-id="d7262-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="d7262-104">Quando um qualificador é adicionado a um caso de descoberta eletrônica avançada, qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-lo totalmente pesquisável.</span><span class="sxs-lookup"><span data-stu-id="d7262-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="d7262-105">Esse processo é chamado de *indexação avançada*.</span><span class="sxs-lookup"><span data-stu-id="d7262-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="d7262-106">O conteúdo pode ser parcialmente indexado por vários motivos, incluindo a existência de imagens, tipos de arquivos não suportados ou quando são encontrados limites de tamanho de arquivo de indexação.</span><span class="sxs-lookup"><span data-stu-id="d7262-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="d7262-107">Para saber mais sobre o processamento de suporte e itens parcialmente indexados, consulte:</span><span class="sxs-lookup"><span data-stu-id="d7262-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="d7262-108">Tipos de arquivo com suporte na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="d7262-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="d7262-109">Itens parcialmente indexados na Pesquisa de Conteúdo do Office 365</span><span class="sxs-lookup"><span data-stu-id="d7262-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="d7262-110">Formatos de arquivo indexados pela pesquisa do Exchange</span><span class="sxs-lookup"><span data-stu-id="d7262-110">File formats indexed by Exchange Search</span></span>](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="d7262-111">Extensões de nome de arquivo rastreado padrão e tipos de arquivos analisados no SharePoint Server Server</span><span class="sxs-lookup"><span data-stu-id="d7262-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="d7262-112">Exibindo resultados avançados de indexação</span><span class="sxs-lookup"><span data-stu-id="d7262-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="d7262-113">Após a conclusão do processo de indexação avançada, você pode entender a eficácia do reprocessamento.</span><span class="sxs-lookup"><span data-stu-id="d7262-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="d7262-114">No modo de exibição de resultados de indexação avançados na guia **processamento** para um caso, o gráfico lista o número de itens adicionados ao *índice híbrido*.</span><span class="sxs-lookup"><span data-stu-id="d7262-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="d7262-115">O índice híbrido é onde a descoberta eletrônica avançada armazena o conteúdo reprocessado.</span><span class="sxs-lookup"><span data-stu-id="d7262-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="d7262-116">Este modo de exibição também inclui o número de itens que exigem correção e outro gráfico de erros por tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d7262-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="d7262-117">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="d7262-117">For more information, see:</span></span>

- [<span data-ttu-id="d7262-118">Correção de erros durante o processamento de dados</span><span class="sxs-lookup"><span data-stu-id="d7262-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="d7262-119">Correção de erros de item único</span><span class="sxs-lookup"><span data-stu-id="d7262-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="d7262-120">Atualizando o índice avançado para os responsáveis</span><span class="sxs-lookup"><span data-stu-id="d7262-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="d7262-121">Quando um responsáveis é adicionado a uma caixa de descoberta eletrônica avançada, todos os itens parcialmente indexados são reprocessados.</span><span class="sxs-lookup"><span data-stu-id="d7262-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="d7262-122">No entanto, à medida que o tempo passa, os itens mais parcialmente indexados podem ser adicionados à caixa de correio de um usuário ou a uma conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="d7262-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="d7262-123">Se necessário, você pode atualizar o índice para os responsáveis específicos.</span><span class="sxs-lookup"><span data-stu-id="d7262-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="d7262-124">Para obter mais informações, consulte [Manage responsáveis em uma caixa de descoberta eletrônica avançada](manage-new-custodians.md#re-index-custodian-data).</span><span class="sxs-lookup"><span data-stu-id="d7262-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="d7262-125">Você também pode atualizar o índice para todos os responsáveis em um caso clicando no **índice de atualização** na guia **processamento** .</span><span class="sxs-lookup"><span data-stu-id="d7262-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="d7262-126">Atualizar os índices dos responsáveis é um processo de execução longa.</span><span class="sxs-lookup"><span data-stu-id="d7262-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="d7262-127">É recomendável que você não atualize os índices mais de uma vez por dia em um caso.</span><span class="sxs-lookup"><span data-stu-id="d7262-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>
