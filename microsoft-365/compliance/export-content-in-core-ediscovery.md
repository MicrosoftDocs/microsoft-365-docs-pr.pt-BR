---
title: Exportar e baixar conteúdo de um caso de Descoberta Básica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Descreve como exportar e baixar conteúdo de um caso de Descoberta Principal de Descoberta Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310831"
---
# <a name="export-content-from-a-core-ediscovery-case"></a><span data-ttu-id="bcf5a-103">Exportar o conteúdo de um processo da Descoberta Eletrônica Principal</span><span class="sxs-lookup"><span data-stu-id="bcf5a-103">Export content from a Core eDiscovery case</span></span>

<span data-ttu-id="bcf5a-104">Depois que uma pesquisa associada a um caso de Descoberta Básica é executado com êxito, você pode exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-104">After a search associated with a Core eDiscovery case is successfully run, you can export the search results.</span></span> <span data-ttu-id="bcf5a-105">Quando você exporta os resultados da pesquisa, os itens de caixa de correio são baixados em arquivos PST ou como mensagens individuais.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-105">When you export search results, mailbox items are downloaded in PST files or as individual messages.</span></span> <span data-ttu-id="bcf5a-106">Quando você exporta conteúdo de sites SharePoint e OneDrive for Business, cópias de documentos nativos Office documentos e outros documentos são exportados.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-106">When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported.</span></span> <span data-ttu-id="bcf5a-107">Um Results.csv que contém informações sobre cada item exportado e um arquivo de manifesto (no formato XML) que contém informações sobre cada resultado de pesquisa também é exportado.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-107">A Results.csv file that contains information about every item that's exported and a manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
## <a name="export-search-results"></a><span data-ttu-id="bcf5a-108">Exportar resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="bcf5a-108">Export search results</span></span>

1. <span data-ttu-id="bcf5a-109">Acesse e entre usando as credenciais da conta de usuário que foram atribuídas às permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) de Descoberta eDiscoveria apropriadas.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-109">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in using the credentials for user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="bcf5a-110">No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-110">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Core**.</span></span>

3. <span data-ttu-id="bcf5a-111">Na página **Descoberta Principal da Descoberta e,** clique no nome da ocorrência em que você deseja criar a responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-111">On the **Core eDiscovery** page, click the name of the case that you want to create the hold in.</span></span>

4. <span data-ttu-id="bcf5a-112">Na **home** page do caso, clique na **guia Pesquisas.**</span><span class="sxs-lookup"><span data-stu-id="bcf5a-112">On the **Home** page for the case, click the **Searches** tab.</span></span>

5. <span data-ttu-id="bcf5a-113">No menu **Ações** na parte inferior da página de sobrevoo, clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-113">On the **Actions** menu at the bottom of the flyout page, click **Export results**.</span></span>

   ![Opção Exportar resultados no menu Ações](../media/ActionMenuExportResults.png)

   <span data-ttu-id="bcf5a-115">O fluxo de trabalho para exportar os resultados de uma pesquisa associada a um caso de Descoberta Eletrônico Principal é o mesmo que exportar os resultados da pesquisa para uma pesquisa na página de pesquisa **de** conteúdo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-115">The workflow to export the results of a search associated with a Core eDiscovery case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="bcf5a-116">Para obter instruções passo a passo, consulte [Exportar resultados de pesquisa de conteúdo](export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-116">For step-by-step instructions, see [Export content search results](export-search-results.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="bcf5a-117">Ao exportar resultados da pesquisa, você tem a opção de habilitar a de duplicação para que apenas uma cópia de uma mensagem de email seja exportada, mesmo que várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-117">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched.</span></span> <span data-ttu-id="bcf5a-118">Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="bcf5a-118">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

   <span data-ttu-id="bcf5a-119">Depois de iniciar a exportação, os resultados da pesquisa são preparados para download, o que significa que eles são transferidos para um local de Armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-119">After you start the export, the search results are prepared for downloading, which means they are transferred to a Microsoft-provided Azure Storage location in the Microsoft cloud.</span></span>
  
6. <span data-ttu-id="bcf5a-120">Clique na **guia Exportações** para exibir a lista de trabalhos de exportação.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-120">Click the **Exports** tab in the case to display the list of export jobs.</span></span>
  
   ![Exportar trabalhos na guia Exportar no caso de Descoberta Principal](../media/CoreeDiscoveryExport.png)

   <span data-ttu-id="bcf5a-122">Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação criado.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-122">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="bcf5a-123">Os trabalhos de exportação têm o mesmo nome da pesquisa correspondente **_Export** anexado ao nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-123">Export jobs have the same name as the corresponding search with **_Export** appended to the search name.</span></span>

7. <span data-ttu-id="bcf5a-124">Clique no trabalho de exportação criado para exibir informações de status na página de sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-124">Click the export job you created to display status information on the flyout page.</span></span> <span data-ttu-id="bcf5a-125">Essas informações incluem a porcentagem de itens que foram transferidos para o local de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-125">This information includes the percentage of items that have been transferred to the Azure Storage location.</span></span>

8. <span data-ttu-id="bcf5a-126">Depois que todos os itens foram transferidos, clique em **Baixar resultados** para baixar os resultados da pesquisa para o computador local.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-126">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="bcf5a-127">Para obter mais informações sobre como baixar resultados da pesquisa, consulte Etapa 2 em [Exportar resultados de pesquisa de conteúdo](export-search-results.md#step-2-download-the-search-results)</span><span class="sxs-lookup"><span data-stu-id="bcf5a-127">For more information downloading search results, see Step 2 in [Export content search results](export-search-results.md#step-2-download-the-search-results)</span></span>

### <a name="more-information-about-exporting-searches-from-a-case"></a><span data-ttu-id="bcf5a-128">Mais informações sobre a exportação de pesquisas de uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="bcf5a-128">More information about exporting searches from a case</span></span>

- <span data-ttu-id="bcf5a-129">Para obter mais informações sobre os arquivos de exportação incluídos ao exportar resultados da pesquisa, consulte [Exportar um relatório de pesquisa de conteúdo.](export-a-content-search-report.md#whats-included-in-the-report)</span><span class="sxs-lookup"><span data-stu-id="bcf5a-129">For more information about the export files that are included when you export search results, see [Export a Content search report](export-a-content-search-report.md#whats-included-in-the-report).</span></span>

- <span data-ttu-id="bcf5a-130">Se você reiniciar a exportação, quaisquer alterações nas consultas das pesquisas que comem o trabalho de exportação não afetarão os resultados da pesquisa recuperados.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-130">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that are retrieved.</span></span> <span data-ttu-id="bcf5a-131">Quando você reiniciar uma exportação, o mesmo trabalho de consulta de pesquisa combinado que foi executado quando o trabalho de exportação foi criado será executado novamente.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-131">When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>

- <span data-ttu-id="bcf5a-132">Além disso, se você reiniciar uma exportação, os resultados da pesquisa copiados para o local de Armazenamento do Azure sobrescrevem os resultados anteriores.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-132">Also, if you restart an export, the search results that are copied to the Azure Storage location overwrites the previous results.</span></span> <span data-ttu-id="bcf5a-133">Os resultados anteriores copiados não estarão disponíveis para download.</span><span class="sxs-lookup"><span data-stu-id="bcf5a-133">The previous results that were copied won't be available to be downloaded.</span></span>
