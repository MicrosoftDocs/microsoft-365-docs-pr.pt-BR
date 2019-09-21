---
title: Exportar um relatório de Pesquisa de Conteúdo
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: Em vez de exportar os resultados reais de uma pesquisa de conteúdo no centro de conformidade & segurança no Office 365, você pode apenas exportar um relatório de resultados de pesquisa. O relatório contém um resumo dos resultados da pesquisa e um documento com informações detalhadas sobre cada item que seria exportado.
ms.openlocfilehash: 8e33a7ba236e0890fc5985aa9a00cba904a40793
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072644"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="0f9b7-104">Exportar um relatório de Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="0f9b7-104">Export a Content Search report</span></span>

<span data-ttu-id="0f9b7-105">Em vez de exportar o conjunto completo de resultados de pesquisa de uma pesquisa de conteúdo no centro de conformidade de & de segurança (e de uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica), você pode apenas exportar os mesmos relatórios gerados ao exportar os resultados da pesquisa .</span><span class="sxs-lookup"><span data-stu-id="0f9b7-105">Instead of exporting the full set of search results from a Content Search in the Security & Compliance Center (and from a Content Search that's associated with an eDiscovery case), you can just export the same reports that are generated when you export search results.</span></span>
  
<span data-ttu-id="0f9b7-106">Quando um relatório é exportado, ele é baixado para uma pasta que tenha o mesmo nome da pesquisa de conteúdo, mas que é acrescentado com *_ReportsOnly* .</span><span class="sxs-lookup"><span data-stu-id="0f9b7-106">When you export a report, it's downloaded to a folder that has the same name as the Content Search, but that's appended with  *_ReportsOnly*  .</span></span> <span data-ttu-id="0f9b7-107">Por exemplo, se a pesquisa de conteúdo for chamada de *ContosoCase0815* , o relatório será baixado para uma pasta denominada *ContosoCase0815_ReportsOnly* .</span><span class="sxs-lookup"><span data-stu-id="0f9b7-107">For example, if the Content Search is named  *ContosoCase0815*  , then the report is downloaded to a folder named  *ContosoCase0815_ReportsOnly*  .</span></span> <span data-ttu-id="0f9b7-108">Para obter uma lista de documentos incluídos no relatório, confira o [que está incluído no relatório](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0f9b7-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="0f9b7-109">Before you begin</span></span>

- <span data-ttu-id="0f9b7-110">Para exportar um relatório de pesquisa de conteúdo, você precisa ter a função de gerenciamento de pesquisa de conformidade no centro de conformidade de segurança &.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-110">To export a Content Search report, you have to be assigned the Compliance Search management role in the Security & Compliance Center.</span></span> <span data-ttu-id="0f9b7-111">Essa função é atribuída ao Gerenciador de descoberta eletrônica interno e aos grupos de função de gerenciamento da organização.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-111">This role is assigned to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="0f9b7-112">Ela não é atribuída por padrão ao grupo de funções Gerenciamento da Organização.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-112">It isn't assigned by default to the Organization Management role group.</span></span> <span data-ttu-id="0f9b7-113">Para obter mais informações, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-113">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="0f9b7-114">Quando um relatório é exportado, os dados são temporariamente armazenados em uma área de armazenamento exclusiva do Windows Azure na nuvem da Microsoft antes de ele ser baixado para o computador local.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-114">When you export a report, the data is temporarily stored in a unique Windows Azure storage area in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="0f9b7-115">Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é \*\* \*. blob.Core.Windows.net\*\* (o caractere curinga representa um identificador exclusivo para sua exportação).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-115">Be sure your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="0f9b7-116">Os dados dos resultados da pesquisa são excluídos da área de armazenamento do Azure duas semanas após sua criação.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-116">The search results data is deleted from the Azure storage area two weeks after it's created.</span></span> 
    
- <span data-ttu-id="0f9b7-117">O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-117">The computer you use to export the search results has to meet the following system requirements:</span></span>
    
  - <span data-ttu-id="0f9b7-118">Versões de 32 e 64 bits do Windows 7 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="0f9b7-118">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
  - <span data-ttu-id="0f9b7-119">Microsoft .NET Framework 4,7</span><span class="sxs-lookup"><span data-stu-id="0f9b7-119">Microsoft .NET Framework 4.7</span></span>
    
  - <span data-ttu-id="0f9b7-120">Um navegador com suporte:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-120">A supported browser:</span></span>
    
    - <span data-ttu-id="0f9b7-121">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0f9b7-121">Microsoft Edge</span></span>
    
      <span data-ttu-id="0f9b7-122">ou</span><span class="sxs-lookup"><span data-stu-id="0f9b7-122">or</span></span>
    
    - <span data-ttu-id="0f9b7-123">Microsoft Internet Explorer 10 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="0f9b7-123">Microsoft Internet Explorer 10 and later versions</span></span>
    
    <span data-ttu-id="0f9b7-124">**Observação:** A Microsoft não fabrica extensões ou complementos de terceiros para aplicativos ClickOnce.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-124">**Note:** Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="0f9b7-125">Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-125">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 

- <span data-ttu-id="0f9b7-126">Se o tamanho total estimado dos resultados retornados por uma pesquisa de conteúdo exceder 20&nbsp;TB, a exportação do relatório falhará.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-126">If the estimated total size of the results returned by a Content Search exceeds 20&nbsp;TB, exporting the report will fail.</span></span> <span data-ttu-id="0f9b7-127">Para exportar o relatório com êxito, tente restringir o escopo e executar novamente a pesquisa para que o tamanho estimado dos resultados seja menor que 20&nbsp;TB.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-127">To successfully export the report, try to narrow the scope and re-run the search so the estimated size of the results is less than 20&nbsp;TB.</span></span>

- <span data-ttu-id="0f9b7-128">A exportação de relatórios de pesquisa de conteúdo conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-128">Exporting Content Search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="0f9b7-129">Para obter mais informações sobre limites de exportação, consulte [Exportar resultados de pesquisa de conteúdo](export-search-results.md#export-limits).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-129">For more information about export limits, see [Export Content Search results](export-search-results.md#export-limits).</span></span>

## <a name="generate-and-download-a-content-search-report"></a><span data-ttu-id="0f9b7-130">Gerar e baixar um relatório de pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="0f9b7-130">Generate and download a Content Search report</span></span>

<span data-ttu-id="0f9b7-131">As etapas para gerar e baixar um relatório de pesquisa de conteúdo são muito parecidas de exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-131">The steps to generate and download a Content Search report are very similar to actually exporting search results.</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="0f9b7-132">Etapa 1: gerar o relatório para exportação</span><span class="sxs-lookup"><span data-stu-id="0f9b7-132">Step 1: Generate the report for export</span></span>

<span data-ttu-id="0f9b7-133">A primeira etapa é preparar o relatório para download para a exportação do seu computador.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-133">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="0f9b7-134">Quando você o relatório, os documentos do relatório são carregados em uma área de armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-134">When you the report, the report documents are uploaded to an Azure storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="0f9b7-135">Acesse [https://protection.office.com](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-135">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="0f9b7-136">Entre no Office 365 usando a sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-136">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="0f9b7-137">No painel esquerdo do centro de conformidade & segurança, clique em \*\*\*\* \> **pesquisa de conteúdo**de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-137">In the left pane of the Security & Compliance Center, click **Search** \> **Content search**.</span></span>
    
4. <span data-ttu-id="0f9b7-138">Na página **pesquisa de conteúdo** , selecione uma pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-138">On the **Content search** page, select a search.</span></span> 
    
5. <span data-ttu-id="0f9b7-139">No painel de detalhes, em **Exportar relatório para um computador**, clique em **gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-139">In the details pane, under **Export report to a computer**, click **Generate report**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f9b7-140">Se os resultados de uma pesquisa tiverem mais de 7 dias, você precisará atualizá-los.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-140">If the results for a search are older than 7 days, you are prompted to update the search results.</span></span> <span data-ttu-id="0f9b7-141">Se isso acontecer, cancele a exportação, clique em **Atualizar resultados da pesquisa** no painel de detalhes da pesquisa selecionada e, em seguida, inicie a exportação novamente após os resultados serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-141">If this happens, cancel the export, click **Update search results** in the details pane for the selected search, and then start the report export again after the results are updated.</span></span> 
  
6. <span data-ttu-id="0f9b7-142">Na página **exportar um relatório** , em **incluir estes itens da pesquisa**, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-142">On the **Export a report** page, under **Include these items from the search**, choose one of the following options:</span></span>
    
    - <span data-ttu-id="0f9b7-143">Exportar somente itens indexados</span><span class="sxs-lookup"><span data-stu-id="0f9b7-143">Export only indexed items</span></span>
    
    - <span data-ttu-id="0f9b7-144">Exportar itens indexados e não indexados</span><span class="sxs-lookup"><span data-stu-id="0f9b7-144">Export indexed and unindexed items</span></span>
    
    - <span data-ttu-id="0f9b7-145">Exportar somente itens não indexados</span><span class="sxs-lookup"><span data-stu-id="0f9b7-145">Export only unindexed items</span></span>
    
    <span data-ttu-id="0f9b7-146">Para obter mais informações sobre itens não indexados, consulte [itens parcialmente indexados na pesquisa de conteúdo](partially-indexed-items-in-content-search.md).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-146">For more information about unindexed items, see [Partially indexed items in Content Search](partially-indexed-items-in-content-search.md).</span></span>
    
7. <span data-ttu-id="0f9b7-147">Escolha incluir estatísticas de pesquisa para todas as versões dos documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-147">Choose to include search statistics for all versions of SharePoint documents.</span></span> <span data-ttu-id="0f9b7-148">Essa opção será exibida somente se as fontes de conteúdo da pesquisa incluirem sites do SharePoint ou do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-148">This option appears only if the content sources of the search includes SharePoint or OneDrive for Business sites.</span></span>
    
8. <span data-ttu-id="0f9b7-149">Clique em **gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-149">Click **Generate report**.</span></span>
    
    <span data-ttu-id="0f9b7-150">O relatório de resultados de pesquisa está preparado para download, o que significa que os documentos de relatório serão carregados para a área de armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-150">The search results report is prepared for downloading, which means the report documents will be uploaded to the Azure storage area in the Microsoft cloud.</span></span> <span data-ttu-id="0f9b7-151">Quando o relatório estiver pronto para download, o link de **relatório de download** será exibido em **Exportar relatório para um computador** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-151">When the report is ready for download, the **Download report** link is displayed under **Export report to a computer** in the details pane.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0f9b7-152">Você também pode exportar um relatório para uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-152">You can also export a report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0f9b7-153">Para fazer isso, **vá para** \> **descoberta eletrônica**eletrônica, selecione um caso e clique em **Editar** ![ícone](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edição.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-153">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0f9b7-154">Na página **pesquisas** , selecione uma pesquisa e clique em **Exportar** ![o ícone](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> resultados da pesquisa exportar **um relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-154">On the **Searches** page, select a search, and then click **Export** ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **Export a report**.</span></span> 
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="0f9b7-155">Etapa 2: baixar o relatório</span><span class="sxs-lookup"><span data-stu-id="0f9b7-155">Step 2: Download the report</span></span>

<span data-ttu-id="0f9b7-156">A próxima etapa é baixar o relatório da área de armazenamento do Azure para seu computador local.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-156">The next step is to download the report from the Azure storage area to your local computer.</span></span>
  
1. <span data-ttu-id="0f9b7-157">No painel de detalhes da pesquisa para a qual você gerou o relatório, em **Exportar relatório para um computador**, clique em **baixar relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-157">In the details pane for the search that you generated the report for, under **Export report to a computer**, click **Download report**.</span></span>
    
    <span data-ttu-id="0f9b7-158">A página de **relatório de download** é exibida e contém as seguintes informações sobre o relatório, na qual será feito o download para o seu computador.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-158">The **Download report** page is displayed and contains the following information about the report till be downloaded to your computer.</span></span> 
    
    - <span data-ttu-id="0f9b7-159">O número de itens que serão baixados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-159">The number of items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0f9b7-160">O tamanho total estimado dos itens que serão baixados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-160">The estimated total size of the items that will be downloaded.</span></span>
    
    - <span data-ttu-id="0f9b7-161">Se serão exportados itens indexados ou não indexados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-161">Whether indexed or unindexed will be exported.</span></span> <span data-ttu-id="0f9b7-162">Os itens não indexados são itens que têm um formato reconhecido, estão criptografados ou não foram indexados por outros motivos.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-162">Unindexed items are items that have an recognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="0f9b7-163">Se serão baixadas ou não versões dos documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-163">Whether or not versions of SharePoint documents will be downloaded.</span></span>
    
    - <span data-ttu-id="0f9b7-164">O status do processo de exportação de relatórios.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-164">The status of the report export process.</span></span> <span data-ttu-id="0f9b7-165">Você pode começar a baixar o relatório mesmo se a preparação do relatório não estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-165">You can start downloading the report even if the preparation of the report isn't complete.</span></span>
    
2. <span data-ttu-id="0f9b7-166">Em **Exportar chave**, clique em **Copiar para a área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-166">Under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="0f9b7-167">Você usará essa chave na etapa 5 para baixar o relatório.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-167">You will use this key in step 5 to download the report.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0f9b7-168">Como qualquer pessoa pode instalar e iniciar a ferramenta de exportação de descoberta eletrônica e, em seguida, usar essa chave para baixar o relatório de pesquisa, tome precauções para proteger essa chave da mesma forma que você protegeria senhas ou outras informações relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span> 
  
3. <span data-ttu-id="0f9b7-169">Clique em **baixar relatório**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-169">Click **Download report**.</span></span>
    
4. <span data-ttu-id="0f9b7-170">Se você for solicitado a instalar a **ferramenta de exportação de descoberta eletrônica do MicrosoftOffice 365**, clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-170">If you're prompted to install the **MicrosoftOffice 365 eDiscovery Export Tool**, click **Install**.</span></span>
    
5. <span data-ttu-id="0f9b7-171">Na **Ferramenta de Exportação de Descoberta Eletrônica**, cole a chave de exportação que você copiou na etapa 2 na caixa apropriada.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-171">In the **eDiscovery Export Tool**, paste the export key that you copied in step 2 in the appropriate box.</span></span>
    
6. <span data-ttu-id="0f9b7-172">Clique em **procurar** para especificar o local onde você deseja baixar o relatório.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-172">Click **Browse** to specify the location where you want to download the report.</span></span> 
    
7. <span data-ttu-id="0f9b7-173">Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-173">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="0f9b7-174">A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-174">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="0f9b7-175">Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde foram baixados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-175">When the export process is complete, you can access the files in the location where they were downloaded.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0f9b7-176">Você pode baixar o relatório para uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-176">You can download the report for a Content Search that's associated with an eDiscovery case.</span></span> <span data-ttu-id="0f9b7-177">Para fazer isso, **vá para** \> **descoberta eletrônica**eletrônica, selecione um caso e clique em **Editar** ![ícone](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edição.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-177">To do this, go to **eDiscovery** \> **eDiscovery**, select a case, and click **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span> <span data-ttu-id="0f9b7-178">Na página **Exportar** , selecione uma exportação de relatório e clique em **baixar relatório** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-178">On the **Exports** page, select an report export, and then click **Download report** in the details pane.</span></span> 
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="0f9b7-179">O que está incluído no relatório</span><span class="sxs-lookup"><span data-stu-id="0f9b7-179">What's included in the report</span></span>

<span data-ttu-id="0f9b7-180">Quando você gera e exporta um relatório sobre os resultados de uma pesquisa de conteúdo, os seguintes documentos são baixados:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-180">When you generate and export a report about the results of a Content Search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="0f9b7-181">**Resumo de exportação** : um documento do Excel que contém um resumo da exportação.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-181">**Export Summary** - An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="0f9b7-182">Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que serão exportados e o tamanho estimado e real dos itens Isso seria exportado.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-182">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="0f9b7-183">Se você incluir itens não indexados ao exportar o relatório, o número de itens não indexados será incluído no número total de resultados de pesquisa estimados e no número total de resultados de pesquisa baixados (se você tiver que exportar os resultados da pesquisa) listados na Relatório de Resumo de exportação.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-183">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the Export Summary report.</span></span> <span data-ttu-id="0f9b7-184">Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não indexados.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-184">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span> 
  
- <span data-ttu-id="0f9b7-185">**Manifest** -um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-185">**Manifest** - A manifest file (in XML format) that contains information about each item included in the search results.</span></span> 
    
- <span data-ttu-id="0f9b7-186">**Resultados** -um documento do Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-186">**Results** - An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="0f9b7-187">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-187">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="0f9b7-188">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="0f9b7-189">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-189">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="0f9b7-190">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-190">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="0f9b7-191">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-191">The sender and recipients of the message.</span></span>
    
    <span data-ttu-id="0f9b7-192">Para documentos de sites do SharePoint e do OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0f9b7-192">For documents from SharePoint and OneDrive for Business sites, the Results log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="0f9b7-193">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-193">The URL for the document.</span></span>
    
  - <span data-ttu-id="0f9b7-194">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-194">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="0f9b7-195">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-195">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="0f9b7-196">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="0f9b7-196">The name of the document (which is located in the Subject column in the result log).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0f9b7-197">O número de linhas no relatório de **resultados** deve ser igual ao número total de resultados de pesquisa que serão baixados menos o número total de itens listados no relatório de **itens não indexados** .</span><span class="sxs-lookup"><span data-stu-id="0f9b7-197">The number of rows in the **Results** report should be equal to the total number of search results that would be downloaded minus the total number of items listed in the **Unindexed Items** report.</span></span> 
  
- <span data-ttu-id="0f9b7-198">**Itens não indexados** -um documento do Excel que contém informações sobre itens não indexados que seriam incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-198">**Unindexed Items** - An Excel document that contains information about any unindexed items that would be included in the search results.</span></span> <span data-ttu-id="0f9b7-199">Se você não incluir itens não indexados ao gerar o relatório de resultados de pesquisa, esse relatório ainda será baixado, mas estará vazio.</span><span class="sxs-lookup"><span data-stu-id="0f9b7-199">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
