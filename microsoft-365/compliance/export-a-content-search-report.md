---
title: Exportar um relatório de Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Em vez de exportar os resultados reais de uma Pesquisa de Conteúdo no Centro de Conformidade & segurança no Office 365, você pode exportar um relatório de resultados de pesquisa. O relatório contém um resumo dos resultados da pesquisa e um documento com informações detalhadas sobre cada item que seria exportado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fec6e441458ad7429067a1314a7aec3824aff11a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760149"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="b873e-104">Exportar um relatório de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="b873e-104">Export a Content Search report</span></span>

<span data-ttu-id="b873e-105">Em vez de exportar o conjunto completo de resultados de pesquisa de uma Pesquisa de Conteúdo no Centro de Conformidade de Segurança & (e de uma Pesquisa de Conteúdo associada a um caso de Descoberta Digital), você pode exportar os mesmos relatórios gerados quando você exporta resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="b873e-106">Quando você exporta um relatório, ele é baixado para uma pasta que tem o mesmo nome que a Pesquisa de Conteúdo, mas que é anexado ao _ReportsOnly *.*</span><span class="sxs-lookup"><span data-stu-id="b873e-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="b873e-107">Por exemplo, se a Pesquisa de Conteúdo for chamada  *ContosoCase0815*, o relatório será baixado para uma pasta chamada *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="b873e-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="b873e-108">Para uma lista de documentos incluídos no relatório, consulte [O que está incluído no relatório](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="b873e-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="assign-roles-and-check-system-requirements"></a><span data-ttu-id="b873e-109">Atribuir funções e verificar requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="b873e-109">Assign roles and check system requirements</span></span>

- <span data-ttu-id="b873e-110">Para exportar um relatório de Pesquisa de Conteúdo, você precisa ter a função de gerenciamento de Pesquisa de Conformidade no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="b873e-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="b873e-111">Essa função é atribuída por padrão aos grupos de função de Gerenciamento de Descoberta e Gerenciamento de Organização integrados.</span><span class="sxs-lookup"><span data-stu-id="b873e-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="b873e-112">Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b873e-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="b873e-113">Quando você exporta um relatório, os dados são temporariamente armazenados em uma área exclusiva do Azure Armazenamento na nuvem da Microsoft antes que eles são baixados para o computador local.</span><span class="sxs-lookup"><span data-stu-id="b873e-113">When you export a report, the data is temporarily stored in a unique Azure Storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="b873e-114">Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é **\* .blob.core.windows.net** (o caractere curinga representa um identificador exclusivo para sua exportação).</span><span class="sxs-lookup"><span data-stu-id="b873e-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="b873e-115">Os dados de resultados da pesquisa são excluídos da área de Armazenamento do Azure duas semanas após a criação.</span><span class="sxs-lookup"><span data-stu-id="b873e-115">The search results data is deleted from the Azure Storage area two weeks after it's created.</span></span>

- <span data-ttu-id="b873e-116">O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:</span><span class="sxs-lookup"><span data-stu-id="b873e-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="b873e-117">Versão mais recente do Windows (32 bits ou 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b873e-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="b873e-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="b873e-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="b873e-119">Você precisa usar um dos seguintes navegadores com suporte para executar a Ferramenta de Exportação de Descoberta e<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="b873e-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="b873e-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b873e-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="b873e-121">OU</span><span class="sxs-lookup"><span data-stu-id="b873e-121">OR</span></span>

  - <span data-ttu-id="b873e-122">Internet Explorer 10 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="b873e-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="b873e-123"><sup>1</sup> A Microsoft não fabrica extensões ou complementos de terceiros para ClickOnce aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b873e-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="b873e-124">Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b873e-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="b873e-125"><sup>2</sup> Como resultado de alterações recentes no Microsoft Edge, ClickOnce suporte não está mais habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b873e-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="b873e-126">Para obter instruções sobre como habil ClickOnce suporte no Edge, [consulte Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="b873e-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="b873e-127">Se o tamanho total estimado dos resultados retornados por uma Pesquisa de Conteúdo exceder 2 TB, a exportação do relatório falhará.</span><span class="sxs-lookup"><span data-stu-id="b873e-127">If the estimated total size of the results returned by a Content Search exceeds 2 TB, exporting the report fails.</span></span> <span data-ttu-id="b873e-128">Para exportar o relatório com êxito, tente restringir o escopo e reprisar a pesquisa para que o tamanho estimado dos resultados seja menor que 2 TB.</span><span class="sxs-lookup"><span data-stu-id="b873e-128">To successfully export the report, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="b873e-129">A exportação de relatórios de Pesquisa de Conteúdo conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar.</span><span class="sxs-lookup"><span data-stu-id="b873e-129">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="b873e-130">Para obter mais informações sobre limites de exportação, consulte [Exportar resultados da Pesquisa de Conteúdo](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="b873e-130">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="b873e-131">Gerar e baixar um relatório de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="b873e-131">Generate and download a Content Search report</span></span>

<span data-ttu-id="b873e-132">As etapas para gerar e baixar um relatório de Pesquisa de Conteúdo são semelhantes à exportação de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-132">The steps to generate and download a Content Search report are similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="b873e-133">Etapa 1: Gerar o relatório para exportação</span><span class="sxs-lookup"><span data-stu-id="b873e-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="b873e-134">A primeira etapa é preparar o relatório para download no computador que está sendo exportado.</span><span class="sxs-lookup"><span data-stu-id="b873e-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="b873e-135">Quando você faz o relatório, os documentos do relatório são carregados em uma área de Armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b873e-135">When you the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="b873e-136">Acesse [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="b873e-136">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="b873e-137">Entre usando sua conta de trabalho ou da escola.</span><span class="sxs-lookup"><span data-stu-id="b873e-137">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="b873e-138">No painel esquerdo do Centro de Conformidade & Segurança, clique em **Pesquisar** \> **Conteúdo de Pesquisa.**</span><span class="sxs-lookup"><span data-stu-id="b873e-138">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="b873e-139">Na página **Pesquisa de** conteúdo, selecione uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-139">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="b873e-140">No painel de detalhes, em **Relatório de exportação para um computador,** clique em Gerar **relatório**.</span><span class="sxs-lookup"><span data-stu-id="b873e-140">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b873e-141">Se os resultados de uma pesquisa tiverem mais de 7 dias, você precisará atualizá-los.</span><span class="sxs-lookup"><span data-stu-id="b873e-141">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="b873e-142">Se isso acontecer, cancele  a exportação, clique em Atualizar resultados da pesquisa no painel de detalhes da pesquisa selecionada e, em seguida, inicie a exportação de relatório novamente depois que os resultados forem atualizados.</span><span class="sxs-lookup"><span data-stu-id="b873e-142">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="b873e-143">Na página **Exportar um relatório,** em Incluir esses itens da **pesquisa,** escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b873e-143">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="b873e-144">Exportar somente itens indexados</span><span class="sxs-lookup"><span data-stu-id="b873e-144">Export only indexed items</span></span>
    
    - <span data-ttu-id="b873e-145">Exportar itens indexados e não indexados</span><span class="sxs-lookup"><span data-stu-id="b873e-145">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="b873e-146">Exportar somente itens não indexados</span><span class="sxs-lookup"><span data-stu-id="b873e-146">Export only unindexed items</span></span>
    
    <span data-ttu-id="b873e-147">Para obter mais informações sobre itens não indexados, consulte [Itens parcialmente indexados na Pesquisa de Conteúdo](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="b873e-147">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="b873e-148">Escolha incluir estatísticas de pesquisa para todas as versões de SharePoint documentos.</span><span class="sxs-lookup"><span data-stu-id="b873e-148">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="b873e-149">Essa opção será exibida somente se as fontes de conteúdo da pesquisa incluirem SharePoint ou OneDrive for Business sites.</span><span class="sxs-lookup"><span data-stu-id="b873e-149">This option appears only if the content sources of the search include SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="b873e-150">Clique **em Gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="b873e-150">Click **Generate report**.</span></span>
    
    <span data-ttu-id="b873e-151">O relatório de resultados da pesquisa está preparado para download, o que significa que os documentos do relatório serão carregados para a área de Armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b873e-151">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure Storage area in the Microsoft cloud.</span></span> <span data-ttu-id="b873e-152">Quando o relatório estiver pronto para download, o link **Baixar** relatório será exibido em Relatório de **Exportação para** um computador no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="b873e-152">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b873e-153">Você também pode exportar um relatório para uma Pesquisa de Conteúdo associada a um caso de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="b873e-153">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="b873e-154">Para fazer isso, vá para **Descoberta EDiscovery** \> **eDiscovery,** selecione uma ocorrência e clique em **Editar** ![ ícone editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="b873e-154">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="b873e-155">Na página **Pesquisas,** selecione uma pesquisa e clique em **Exportar** ícone Exportar resultados da pesquisa ![ Exportar um ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **relatório**.</span><span class="sxs-lookup"><span data-stu-id="b873e-155">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="b873e-156">Etapa 2: Baixar o relatório</span><span class="sxs-lookup"><span data-stu-id="b873e-156">Step 2: Download the report</span></span>

<span data-ttu-id="b873e-157">A próxima etapa é baixar o relatório da área de Armazenamento do Azure para o computador local.</span><span class="sxs-lookup"><span data-stu-id="b873e-157">The next step is to download the report from the Azure Storage area to your local computer.</span></span>
  
1. <span data-ttu-id="b873e-158">No painel de detalhes da pesquisa para a que você gerou o relatório, em **Exportar relatório para um** computador, clique em Baixar **relatório**.</span><span class="sxs-lookup"><span data-stu-id="b873e-158">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="b873e-159">A **página Baixar relatório** é exibida e contém as seguintes informações sobre o relatório baixado para seu computador.</span><span class="sxs-lookup"><span data-stu-id="b873e-159">The **Download report** page is displayed and contains the following information about the report that's downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="b873e-160">O número de itens que serão baixados.</span><span class="sxs-lookup"><span data-stu-id="b873e-160">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="b873e-161">O tamanho total estimado dos itens que serão baixados.</span><span class="sxs-lookup"><span data-stu-id="b873e-161">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="b873e-162">Se serão exportados itens indexados ou não indexados.</span><span class="sxs-lookup"><span data-stu-id="b873e-162">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="b873e-163">Itens não indexados são itens que têm um formato reconhecido, são criptografados ou não foram indexados por outros motivos.</span><span class="sxs-lookup"><span data-stu-id="b873e-163">Unindexed items are items that have a recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="b873e-164">Se as versões SharePoint documentos serão baixadas.</span><span class="sxs-lookup"><span data-stu-id="b873e-164">Whether versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="b873e-165">O status do processo de exportação de relatório.</span><span class="sxs-lookup"><span data-stu-id="b873e-165">The status of the report export process.</span></span> <span data-ttu-id="b873e-166">Você pode começar a baixar o relatório mesmo que a preparação do relatório não seja concluída.</span><span class="sxs-lookup"><span data-stu-id="b873e-166">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="b873e-167">Em **Chave de exportação**, clique em **Copiar para a área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="b873e-167">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="b873e-168">Use essa chave na etapa 5 para baixar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b873e-168">You use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b873e-169">Como qualquer pessoa pode instalar e iniciar a ferramenta De Exportação de Descoberta Digital e, em seguida, usar essa chave para baixar o relatório de pesquisa, certifique-se de tomar precauções para proteger essa chave da mesma forma que você protegeria senhas ou outras informações relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="b873e-169">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="b873e-170">Clique **em Baixar relatório**.</span><span class="sxs-lookup"><span data-stu-id="b873e-170">Click **Download report**.</span></span>
    
4. <span data-ttu-id="b873e-171">Se você for solicitado a instalar a Ferramenta de Exportação **de Descoberta Digital,** clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b873e-171">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="b873e-172">Na **Ferramenta de Exportação de Descoberta Eletrônica**, cole a chave de exportação que você copiou na etapa 2 na caixa apropriada.</span><span class="sxs-lookup"><span data-stu-id="b873e-172">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="b873e-173">Clique **em Procurar** para especificar o local onde você deseja baixar o relatório.</span><span class="sxs-lookup"><span data-stu-id="b873e-173">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="b873e-174">Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.</span><span class="sxs-lookup"><span data-stu-id="b873e-174">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="b873e-175">A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="b873e-175">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="b873e-176">Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde eles foram baixados.</span><span class="sxs-lookup"><span data-stu-id="b873e-176">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="b873e-177">Você pode baixar o relatório de uma Pesquisa de Conteúdo associada a um caso de Descoberta E.</span><span class="sxs-lookup"><span data-stu-id="b873e-177">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="b873e-178">Para fazer isso, vá para **Descoberta EDiscovery** \> **eDiscovery,** selecione uma ocorrência e clique em **Editar** ![ ícone editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="b873e-178">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="b873e-179">Na página **Exportações,** selecione uma exportação de relatório e clique em **Baixar relatório** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="b873e-179">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="b873e-180">O que está incluído no relatório</span><span class="sxs-lookup"><span data-stu-id="b873e-180">What's included in the report</span></span>

<span data-ttu-id="b873e-181">Quando você gera e exporta um relatório sobre os resultados de uma Pesquisa de Conteúdo, os seguintes documentos são baixados:</span><span class="sxs-lookup"><span data-stu-id="b873e-181">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="b873e-182">**Resumo de Exportação:** Um Excel que contém um resumo da exportação.</span><span class="sxs-lookup"><span data-stu-id="b873e-182">**Export Summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="b873e-183">Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que seriam exportados e o tamanho estimado e real dos itens que seriam exportados.</span><span class="sxs-lookup"><span data-stu-id="b873e-183">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="b873e-184">Se você incluir itens não índicedos ao exportar o relatório, o número de itens não indexados será incluído no número total de resultados de pesquisa estimados e no número total de resultados de pesquisa baixados (se você fosse exportar os resultados da pesquisa) listados no relatório Resumo de Exportação.</span><span class="sxs-lookup"><span data-stu-id="b873e-184">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="b873e-185">Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não índicedos.</span><span class="sxs-lookup"><span data-stu-id="b873e-185">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="b873e-186">**Manifesto:** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-186">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="b873e-187">**Resultados:** Um Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-187">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="b873e-188">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b873e-188">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="b873e-189">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="b873e-189">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="b873e-190">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="b873e-190">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="b873e-191">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b873e-191">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="b873e-192">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b873e-192">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="b873e-193">Para documentos de SharePoint sites OneDrive for Business, o log De resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b873e-193">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="b873e-194">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="b873e-194">The URL for the document.</span></span>
    
  - <span data-ttu-id="b873e-195">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="b873e-195">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="b873e-196">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="b873e-196">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="b873e-197">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="b873e-197">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b873e-198">O número de linhas  no relatório Resultados deve ser igual ao número total de resultados da pesquisa menos o número total de itens listados no relatório Itens Não **Índicedos.**</span><span class="sxs-lookup"><span data-stu-id="b873e-198">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="b873e-199">**Itens nãoindexados:** Um Excel que contém informações sobre todos os itens não indexados incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b873e-199">**Unindexed Items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="b873e-200">Se você não incluir itens não índicedos ao gerar o relatório de resultados da pesquisa, esse relatório ainda será baixado, mas estará vazio.</span><span class="sxs-lookup"><span data-stu-id="b873e-200">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
