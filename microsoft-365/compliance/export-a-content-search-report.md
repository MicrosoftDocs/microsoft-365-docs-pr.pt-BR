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
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311563"
---
# <a name="export-a-content-search-report"></a><span data-ttu-id="001f1-104">Exportar um relatório de Pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="001f1-104">Export a Content search report</span></span>

<span data-ttu-id="001f1-105">Em vez de exportar o conjunto completo de resultados de pesquisa de uma pesquisa de conteúdo no Centro de conformidade do Microsoft 365 (ou de uma pesquisa associada a um caso de Descoberta Básica), você pode exportar os mesmos relatórios gerados ao exportar os resultados reais da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-105">Instead of exporting the full set of search results from a Content search in the Microsoft 365 compliance Center (or from a search that's associated with a Core eDiscovery case), you can export the same reports that are generated when you export the actual search results.</span></span>
  
<span data-ttu-id="001f1-106">Quando você exporta um relatório, os arquivos de relatório são baixados para uma pasta em seu computador local que tem o mesmo nome da Pesquisa de Conteúdo, mas isso é anexado ao _ReportsOnly *.*</span><span class="sxs-lookup"><span data-stu-id="001f1-106">When you export a report, the report files are downloaded to a folder on your local computer that has the same name as the Content Search, but that's appended with *_ReportsOnly*.</span></span> <span data-ttu-id="001f1-107">Por exemplo, se a Pesquisa de Conteúdo for chamada  *ContosoCase0815*, o relatório será baixado para uma pasta chamada *ContosoCase0815_ReportsOnly*.</span><span class="sxs-lookup"><span data-stu-id="001f1-107">For example, if the Content Search is named  *ContosoCase0815*, then the report is downloaded to a folder named *ContosoCase0815_ReportsOnly*.</span></span> <span data-ttu-id="001f1-108">Para uma lista de documentos incluídos no relatório, consulte [O que está incluído no relatório](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="001f1-108">For a list of documents that are included in the report, see [What's included in the report](#whats-included-in-the-report).</span></span>

## <a name="before-you-export-a-search-report"></a><span data-ttu-id="001f1-109">Antes de exportar um relatório de pesquisa</span><span class="sxs-lookup"><span data-stu-id="001f1-109">Before you export a search report</span></span>

- <span data-ttu-id="001f1-110">Para exportar um relatório de pesquisa, você precisa ter a função de gerenciamento de Pesquisa de Conformidade no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="001f1-110">To export a search report, you have to be assigned the Compliance Search management role in Security & Compliance Center.</span></span> <span data-ttu-id="001f1-111">Essa função é atribuída por padrão aos grupos de função de Gerenciamento de Descoberta e Gerenciamento de Organização integrados.</span><span class="sxs-lookup"><span data-stu-id="001f1-111">This role is assigned by default to the built-in eDiscovery Manager and Organization Management role groups.</span></span> <span data-ttu-id="001f1-112">Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="001f1-112">For more information, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="001f1-113">Quando você exporta um relatório, os dados são temporariamente armazenados em um local Armazenamento do Azure na nuvem da Microsoft antes de ser baixado para o computador local.</span><span class="sxs-lookup"><span data-stu-id="001f1-113">When you export a report, the data is temporarily stored in an Azure Storage location in the Microsoft cloud before it's downloaded to your local computer.</span></span> <span data-ttu-id="001f1-114">Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é **\* .blob.core.windows.net** (o caractere curinga representa um identificador exclusivo para sua exportação).</span><span class="sxs-lookup"><span data-stu-id="001f1-114">Be sure that your organization can connect to the endpoint in Azure, which is **\*.blob.core.windows.net** (the wildcard represents a unique identifier for your export).</span></span> <span data-ttu-id="001f1-115">Os dados de resultados da pesquisa são excluídos do local de Armazenamento do Azure duas semanas após a criação.</span><span class="sxs-lookup"><span data-stu-id="001f1-115">The search results data is deleted from the Azure Storage location two weeks after it's created.</span></span>

- <span data-ttu-id="001f1-116">O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:</span><span class="sxs-lookup"><span data-stu-id="001f1-116">The computer you use to export the search results has to meet the following system requirements:</span></span>

  - <span data-ttu-id="001f1-117">Versão mais recente do Windows (32 bits ou 64 bits)</span><span class="sxs-lookup"><span data-stu-id="001f1-117">Latest version of Windows (32-bit or 64-bit)</span></span>

  - <span data-ttu-id="001f1-118">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="001f1-118">Microsoft .NET Framework 4.7</span></span>

- <span data-ttu-id="001f1-119">Você precisa usar um dos seguintes navegadores com suporte para executar a Ferramenta de Exportação de Descoberta e<sup>1</sup>:</span><span class="sxs-lookup"><span data-stu-id="001f1-119">You have to use one of the following supported browsers to run the eDiscovery Export Tool<sup>1</sup>:</span></span>

  - <span data-ttu-id="001f1-120">Microsoft Edge <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="001f1-120">Microsoft Edge <sup>2</sup></span></span>

    <span data-ttu-id="001f1-121">OU</span><span class="sxs-lookup"><span data-stu-id="001f1-121">OR</span></span>

  - <span data-ttu-id="001f1-122">Internet Explorer 10 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="001f1-122">Microsoft Internet Explorer 10 and later versions</span></span>

  > [!NOTE]
  > <span data-ttu-id="001f1-123"><sup>1</sup> A Microsoft não fabrica extensões ou complementos de terceiros para ClickOnce aplicativos.</span><span class="sxs-lookup"><span data-stu-id="001f1-123"><sup>1</sup> Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications.</span></span> <span data-ttu-id="001f1-124">Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="001f1-124">Exporting search results using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span><br/>
  > <span data-ttu-id="001f1-125"><sup>2</sup> Como resultado de alterações recentes no Microsoft Edge, ClickOnce suporte não está mais habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="001f1-125"><sup>2</sup> As a result of recent changes to Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="001f1-126">Para obter instruções sobre como habil ClickOnce suporte no Edge, [consulte Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="001f1-126">For instructions on enabling ClickOnce support in Edge, see [Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).</span></span>

- <span data-ttu-id="001f1-127">Se o tamanho total estimado dos resultados retornados pela pesquisa exceder 2 TB, a exportação dos relatórios falhará.</span><span class="sxs-lookup"><span data-stu-id="001f1-127">If the estimated total size of the results returned by search exceeds 2 TB, exporting the reports fails.</span></span> <span data-ttu-id="001f1-128">Para exportar os relatórios com êxito, tente restringir o escopo e reprisar a pesquisa para que o tamanho estimado dos resultados seja menor que 2 TB.</span><span class="sxs-lookup"><span data-stu-id="001f1-128">To successfully export the reports, try to narrow the scope and rerun the search so the estimated size of the results is less than 2 TB.</span></span>

- <span data-ttu-id="001f1-129">Se os resultados de uma pesquisa são mais antigos do que 7 dias e você envia um trabalho de relatório de exportação, uma mensagem de erro é exibida solicitando que você reprise a pesquisa para atualizar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-129">If the results of a search are older than 7 days and you submit an export report job, an error message is displayed prompting you to rerun the search to update the search results.</span></span> <span data-ttu-id="001f1-130">Se isso acontecer, cancele a exportação, reprise a pesquisa e inicie a exportação novamente.</span><span class="sxs-lookup"><span data-stu-id="001f1-130">If this happens, cancel the export, rerun the search, and then start the export again.</span></span>

- <span data-ttu-id="001f1-131">A exportação de relatórios de pesquisa conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar.</span><span class="sxs-lookup"><span data-stu-id="001f1-131">Exporting search reports counts against the maximum number of exports running at the same time and the maximum number of exports that a single user can run.</span></span> <span data-ttu-id="001f1-132">Para obter mais informações sobre limites de exportação, consulte [Exportar resultados da pesquisa de conteúdo.](export-search-results.md#export-limits)</span><span class="sxs-lookup"><span data-stu-id="001f1-132">For more information about export limits, see [Export Content search results](export-search-results.md#export-limits).</span></span>
  
## <a name="step-1-generate-the-report-for-export"></a><span data-ttu-id="001f1-133">Etapa 1: Gerar o relatório para exportação</span><span class="sxs-lookup"><span data-stu-id="001f1-133">Step 1: Generate the report for export</span></span>

<span data-ttu-id="001f1-134">A primeira etapa é preparar o relatório para download no computador que está sendo exportado.</span><span class="sxs-lookup"><span data-stu-id="001f1-134">The first step is to prepare the report for downloading to your computer exporting.</span></span> <span data-ttu-id="001f1-135">Quando você exporta o relatório, os documentos do relatório são carregados em uma área Armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="001f1-135">When you export the report, the report documents are uploaded to an Azure Storage area in the Microsoft cloud.</span></span>
  
1. <span data-ttu-id="001f1-136">No centro Microsoft 365 de conformidade, selecione a pesquisa de conteúdo da onde você deseja exportar o relatório.</span><span class="sxs-lookup"><span data-stu-id="001f1-136">In the Microsoft 365 compliance center, select the Content search that you want to export the report from.</span></span>
  
2. <span data-ttu-id="001f1-137">No menu **Ações** na parte inferior da página de sobrevoo de pesquisa, clique **em Exportar relatório**.</span><span class="sxs-lookup"><span data-stu-id="001f1-137">On the **Actions** menu at the bottom of the search flyout page, click **Export report**.</span></span>

   ![Opção Exportar relatório no menu Ações](../media/ActionMenuExportReport.png)

   <span data-ttu-id="001f1-139">A **página de sobrevoo** Exportar relatório é exibida.</span><span class="sxs-lookup"><span data-stu-id="001f1-139">The **Export report** flyout page is displayed.</span></span> <span data-ttu-id="001f1-140">As opções de relatório de exportação disponíveis para exportar informações sobre a pesquisa dependem se os resultados da pesquisa estão localizados em caixas de correio ou sites ou uma combinação de ambos.</span><span class="sxs-lookup"><span data-stu-id="001f1-140">The export report options available to export information about the search depend on whether search results are located in mailboxes or sites or a combination of both.</span></span>
  
3. <span data-ttu-id="001f1-141">Em **Opções de saída,** escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="001f1-141">Under **Output options**, choose one of the following options:</span></span>
  
   ![Exportar opções de saída](../media/ExportOutputOptions.png)

    - <span data-ttu-id="001f1-143">**Todos os itens, excluindo aqueles** que têm formato não reconhecedo, são criptografados ou não indexados por outros motivos.</span><span class="sxs-lookup"><span data-stu-id="001f1-143">**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="001f1-144">Essa opção exporta apenas informações sobre itens indexados.</span><span class="sxs-lookup"><span data-stu-id="001f1-144">This option only exports information about indexed items.</span></span>
  
    - <span data-ttu-id="001f1-145">Todos os itens, incluindo aqueles que não têm formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.**</span><span class="sxs-lookup"><span data-stu-id="001f1-145">**All items, including ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="001f1-146">Essa opção exporta informações sobre itens indexados e não indexados.</span><span class="sxs-lookup"><span data-stu-id="001f1-146">This option exports information about indexed and unindexed items.</span></span>
  
    - <span data-ttu-id="001f1-147">Somente os itens que têm um formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.**</span><span class="sxs-lookup"><span data-stu-id="001f1-147">**Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**.</span></span> <span data-ttu-id="001f1-148">Essa opção exporta apenas informações sobre itens não índicedos.</span><span class="sxs-lookup"><span data-stu-id="001f1-148">This option only exports information about unindexed items.</span></span>

4. <span data-ttu-id="001f1-149">Configure a **opção Habilitar a duplicação para Exchange conteúdo.**</span><span class="sxs-lookup"><span data-stu-id="001f1-149">Configure the **Enable de-duplication for Exchange content** option.</span></span>
  
   - <span data-ttu-id="001f1-150">Se você selecionar essa opção, a contagem de mensagens duplicadas (antes da des duplicação e após a duplicação) será incluída no relatório de resumo de exportação.</span><span class="sxs-lookup"><span data-stu-id="001f1-150">If you select this option, the count of duplicate messages (before de-duplication and after de-duplication) is included in the export summary report.</span></span> <span data-ttu-id="001f1-151">Além disso, apenas uma cópia de uma mensagem será incluída no arquivo manifest.xml.</span><span class="sxs-lookup"><span data-stu-id="001f1-151">Also, only one copy of a message will be included in the manifest.xml file.</span></span> <span data-ttu-id="001f1-152">Mas o relatório de resultados de exportação conterá uma linha para cada cópia de uma mensagem duplicada para que você possa identificar as caixas de correio que contêm uma cópia da mensagem duplicada.</span><span class="sxs-lookup"><span data-stu-id="001f1-152">But the export results report will contain a row for every copy of a duplicate message so that you can identify the mailboxes that contain a copy of the duplicate message.</span></span> <span data-ttu-id="001f1-153">Para obter mais informações sobre os relatórios exportados, consulte [O que está incluído no relatório](#whats-included-in-the-report).</span><span class="sxs-lookup"><span data-stu-id="001f1-153">For more information about the exported reports, see [What's included in the report](#whats-included-in-the-report).</span></span>

   - <span data-ttu-id="001f1-154">Se você não selecionar essa opção, os relatórios de exportação conterão informações sobre todas as mensagens retornadas pela pesquisa, incluindo duplicatas.</span><span class="sxs-lookup"><span data-stu-id="001f1-154">If you don't select this option, the export reports will contain information about all messages returned by the search, including duplicates.</span></span>

     <span data-ttu-id="001f1-155">Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span><span class="sxs-lookup"><span data-stu-id="001f1-155">For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span>

5. <span data-ttu-id="001f1-156">Clique **em Gerar relatório**.</span><span class="sxs-lookup"><span data-stu-id="001f1-156">Click **Generate report**.</span></span>

   <span data-ttu-id="001f1-157">Os relatórios de pesquisa estão preparados para download, o que significa que os documentos do relatório são carregados em um local Armazenamento do Azure na nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="001f1-157">The search reports are prepared for downloading, which means the report documents are uploaded to an Azure Storage location in the Microsoft cloud.</span></span> <span data-ttu-id="001f1-158">Isso pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="001f1-158">This may take several minutes.</span></span>

<span data-ttu-id="001f1-159">Consulte a próxima seção para obter instruções para baixar os relatórios de pesquisa exportados.</span><span class="sxs-lookup"><span data-stu-id="001f1-159">See the next section for instructions to download the exported search reports.</span></span>
  
## <a name="step-2-download-the-report"></a><span data-ttu-id="001f1-160">Etapa 2: Baixar o relatório</span><span class="sxs-lookup"><span data-stu-id="001f1-160">Step 2: Download the report</span></span>

<span data-ttu-id="001f1-161">A próxima etapa é baixar o relatório da área de Armazenamento do Azure para o computador local.</span><span class="sxs-lookup"><span data-stu-id="001f1-161">The next step is to download the report from the Azure Storage area to your local computer.</span></span>

1. <span data-ttu-id="001f1-162">Na página **Pesquisa de** conteúdo no centro de conformidade Microsoft 365, selecione a **guia Exportações**</span><span class="sxs-lookup"><span data-stu-id="001f1-162">On the **Content search** page in the Microsoft 365 compliance center, select the **Exports** tab</span></span>
  
   <span data-ttu-id="001f1-163">Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação criado.</span><span class="sxs-lookup"><span data-stu-id="001f1-163">You may have to click **Refresh** to update the list of export jobs so that it shows the export job you created.</span></span> <span data-ttu-id="001f1-164">Os trabalhos de relatório de exportação têm o mesmo nome que a pesquisa correspondente **_ReportsOnly** anexado ao nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-164">Export report jobs have the same name as the corresponding search with **_ReportsOnly** appended to the search name.</span></span>
  
2. <span data-ttu-id="001f1-165">Selecione o trabalho de exportação que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="001f1-165">Select the export job that you created in Step 1.</span></span>

3. <span data-ttu-id="001f1-166">Na página **Sobrevoo** Exportar relatório em **Tecla Exportar,** clique **em Copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="001f1-166">On the **Export report** flyout page under **Export key**, click **Copy to clipboard**.</span></span> <span data-ttu-id="001f1-167">Use essa chave na etapa 6 para baixar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-167">You use this key in step 6 to download the search results.</span></span>
  
   > [!IMPORTANT]
   > <span data-ttu-id="001f1-168">Como qualquer pessoa pode instalar e iniciar a ferramenta De Exportação de Descoberta Digital e, em seguida, usar essa chave para baixar o relatório de pesquisa, certifique-se de tomar precauções para proteger essa chave da mesma forma que você protegeria senhas ou outras informações relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="001f1-168">Because anyone can install and start the eDiscovery Export tool, and then use this key to download the search report, be sure to take precautions to protect this key just like you would protect passwords or other security-related information.</span></span>

4. <span data-ttu-id="001f1-169">Na parte superior da página de sobrevoo, clique **em Baixar resultados**.</span><span class="sxs-lookup"><span data-stu-id="001f1-169">At the top of the flyout page, click **Download results**.</span></span>

5. <span data-ttu-id="001f1-170">Se você for solicitado a instalar a Ferramenta de Exportação **de Descoberta Digital,** clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="001f1-170">If you're prompted to install the **eDiscovery Export Tool**, click **Install**.</span></span>

6. <span data-ttu-id="001f1-171">Na Ferramenta de Exportação de Descoberta **e**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="001f1-171">In the **eDiscovery Export Tool**, do the following:</span></span>

   ![Ferramenta de Exportação de Descoberta Digital](../media/eDiscoveryExportTool.png)

   1. <span data-ttu-id="001f1-173">Colar a chave de exportação que você copiou na etapa 3 na caixa apropriada.</span><span class="sxs-lookup"><span data-stu-id="001f1-173">Paste the export key that you copied in step 3 in the appropriate box.</span></span>
  
   2. <span data-ttu-id="001f1-174">Clique **em Procurar** para especificar o local onde você deseja baixar os arquivos de relatório de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-174">Click **Browse** to specify the location where you want to download the search report files.</span></span>

7. <span data-ttu-id="001f1-175">Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.</span><span class="sxs-lookup"><span data-stu-id="001f1-175">Click **Start** to download the search results to your computer.</span></span>
  
    <span data-ttu-id="001f1-176">A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados.</span><span class="sxs-lookup"><span data-stu-id="001f1-176">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded.</span></span> <span data-ttu-id="001f1-177">Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde eles foram baixados.</span><span class="sxs-lookup"><span data-stu-id="001f1-177">When the export process is complete, you can access the files in the location where they were downloaded.</span></span>
  
## <a name="whats-included-in-the-report"></a><span data-ttu-id="001f1-178">O que está incluído no relatório</span><span class="sxs-lookup"><span data-stu-id="001f1-178">What's included in the report</span></span>

<span data-ttu-id="001f1-179">Quando você gera e exporta um relatório sobre os resultados de uma pesquisa de conteúdo, os seguintes documentos são baixados:</span><span class="sxs-lookup"><span data-stu-id="001f1-179">When you generate and export a report about the results of a Content search, the following documents are downloaded:</span></span>
  
- <span data-ttu-id="001f1-180">**Resumo de exportação:** Um Excel que contém um resumo da exportação.</span><span class="sxs-lookup"><span data-stu-id="001f1-180">**Export summary:** An Excel document that contains a summary of the export.</span></span> <span data-ttu-id="001f1-181">Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que seriam exportados e o tamanho estimado e real dos itens que seriam exportados.</span><span class="sxs-lookup"><span data-stu-id="001f1-181">This includes information such as the number of content sources that were searched, the number of search results from each content location, the estimated number of items, the actual number of items that would be exported, and the estimated and actual size of items that would be exported.</span></span>

   <span data-ttu-id="001f1-182">Se você incluir itens não índicedos ao exportar o relatório, o número de itens não índicedos será incluído no número total de resultados estimados da pesquisa e no número total de resultados de pesquisa baixados (se você fosse exportar os resultados da pesquisa) listados no relatório de resumo de exportação.</span><span class="sxs-lookup"><span data-stu-id="001f1-182">If you include unindexed items when exporting the report, the number of unindexed items are included in the total number of estimated search results and in the total number of downloaded search results (if you were to export the search results) that are listed in the export summary report.</span></span> <span data-ttu-id="001f1-183">Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não índicedos.</span><span class="sxs-lookup"><span data-stu-id="001f1-183">In other words, the total number of items that would be downloaded is equal to the total number of estimated results and the total number of unindexed items.</span></span>
  
- <span data-ttu-id="001f1-184">**Manifesto:** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-184">**Manifest:** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="001f1-185">Se você habilitar a opção de des duplicação, a mensagem duplicada não será incluída no arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="001f1-185">If you enabled the de-duplication option, duplicate message are not included in the manifest file.</span></span>

- <span data-ttu-id="001f1-186">**Resultados:** Um Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-186">**Results:** An Excel document that contains a row with information about each indexed item that would be exported with the search results.</span></span> <span data-ttu-id="001f1-187">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="001f1-187">For email, the result log contains information about each message, including:</span></span> 

  - <span data-ttu-id="001f1-188">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="001f1-188">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>

  - <span data-ttu-id="001f1-189">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="001f1-189">The date the message was sent or received.</span></span>

  - <span data-ttu-id="001f1-190">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="001f1-190">The Subject line from the message.</span></span>

  - <span data-ttu-id="001f1-191">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="001f1-191">The sender and recipients of the message.</span></span>

  <span data-ttu-id="001f1-192">Para documentos de SharePoint sites OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="001f1-192">For documents from SharePoint and OneDrive for Business sites, the results log contains information about each document, including:</span></span>

  - <span data-ttu-id="001f1-193">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="001f1-193">The URL for the document.</span></span>

  - <span data-ttu-id="001f1-194">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="001f1-194">The URL for the site collection where the document is located.</span></span>

  - <span data-ttu-id="001f1-195">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="001f1-195">The date that the document was last modified.</span></span>

  - <span data-ttu-id="001f1-196">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="001f1-196">The name of the document (which is located in the Subject column in the result log).</span></span>

  > [!NOTE]
  > <span data-ttu-id="001f1-197">O número de linhas  no relatório Resultados deve ser igual ao número total de resultados da pesquisa menos o número total de itens listados no relatório Itens Não **Índicedos.**</span><span class="sxs-lookup"><span data-stu-id="001f1-197">The number of rows in the **Results** report should be equal to the total number of search results minus the total number of items listed in the **Unindexed Items** report.</span></span>
  
- <span data-ttu-id="001f1-198">**Trace.log**: um log de rastreamento que contém informações detalhadas sobre o processo de exportação e pode ajudar a descobrir problemas durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="001f1-198">**Trace.log**: A trace log that contains detailed logging information about the export process and can help uncover issues during export.</span></span> <span data-ttu-id="001f1-199">Se você abrir um tíquete com o Suporte da Microsoft sobre um problema relacionado à exportação de relatórios de pesquisa, talvez seja solicitado a fornecer esse log de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="001f1-199">If you open a ticket with Microsoft Support about an issue related to exporting search reports, you may be asked to provide this trace log.</span></span>

- <span data-ttu-id="001f1-200">**Itens não índicedos:** Um Excel que contém informações sobre todos os itens não indexados incluídos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="001f1-200">**Unindexed items:** An Excel document that contains information about any unindexed items included in the search results.</span></span> <span data-ttu-id="001f1-201">Se você não incluir itens não índicedos ao gerar o relatório de resultados da pesquisa, esse relatório ainda será baixado, mas estará vazio.</span><span class="sxs-lookup"><span data-stu-id="001f1-201">If you don't include unindexed items when you generate the search results report, this report will still be downloaded, but will be empty.</span></span>
