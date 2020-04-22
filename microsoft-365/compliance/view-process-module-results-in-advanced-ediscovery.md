---
title: Exibir resultados do módulo de processo na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: 'Saiba mais sobre como localizar os resultados de um módulo de processo executado na descoberta eletrônica avançada, incluindo o status da tarefa e o resumo do processo.  '
ms.openlocfilehash: b7b88ed291236330c87c96d24fa6f1c22fb3d773
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626307"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="3dc61-103">Exibir resultados do módulo de processo na descoberta eletrônica avançada (clássico)</span><span class="sxs-lookup"><span data-stu-id="3dc61-103">View Process module results in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="3dc61-104">Depois que o **processo** de **preparação** \> é iniciado, você pode exibir o progresso e os resultados.</span><span class="sxs-lookup"><span data-stu-id="3dc61-104">After **Prepare** \> **Process** is initiated, you can view progress and results.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3dc61-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="3dc61-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="process-task-status"></a><span data-ttu-id="3dc61-107">Status da tarefa de processo</span><span class="sxs-lookup"><span data-stu-id="3dc61-107">Process task status</span></span>

<span data-ttu-id="3dc61-108">Nos **resultados**do **processo** \> de **preparação** \> , a página mostra o status atual (se o processo estiver em execução no momento) ou o status da tarefa de status do último processo, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3dc61-108">In **Prepare** \> **Process** \> **Results**, the page shows the current status (if Process is currently running) or the last Process status task status as shown in the following example.</span></span>
  
![Status da tarefa do módulo de processamento](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
<span data-ttu-id="3dc61-110">As tarefas exibidas podem variar dependendo das opções de processo selecionadas.</span><span class="sxs-lookup"><span data-stu-id="3dc61-110">The displayed tasks may vary depending on the Process options selected.</span></span> 
  
- <span data-ttu-id="3dc61-111">**Inventory**: a descoberta eletrônica avançada repete todos os arquivos selecionados para o processo e executa uma coleção de dados básica.</span><span class="sxs-lookup"><span data-stu-id="3dc61-111">**Inventory**: Advanced eDiscovery iterates through all files selected for Process and performs basic data collection.</span></span>
    
- <span data-ttu-id="3dc61-112">**Calculate Signatures**: calcula as assinaturas digitais MD5.</span><span class="sxs-lookup"><span data-stu-id="3dc61-112">**Calculate signatures**: Calculates the MD5 digital signatures.</span></span>
    
- <span data-ttu-id="3dc61-113">**Extração de compostos**: extrai arquivos internos ou contidos recursivamente de arquivos compostos (por exemplo, PST, zip, msg).</span><span class="sxs-lookup"><span data-stu-id="3dc61-113">**Compounds extraction**: Extracts inner or contained files recursively from compound files (for example, PST, ZIP, MSG).</span></span> <span data-ttu-id="3dc61-114">Os arquivos extraídos são armazenados na pasta de casos do caso.</span><span class="sxs-lookup"><span data-stu-id="3dc61-114">Extracted files are stored in the case folder of the case.</span></span>
    
- <span data-ttu-id="3dc61-115">**Sincronizando banco de dados**: processo de banco de dados interno.</span><span class="sxs-lookup"><span data-stu-id="3dc61-115">**Synchronizing database**: Internal database process.</span></span>
    
- <span data-ttu-id="3dc61-116">**Cópia de arquivo**: copia arquivos de processo.</span><span class="sxs-lookup"><span data-stu-id="3dc61-116">**File copy**: Copies Process files.</span></span> <span data-ttu-id="3dc61-117">Essa tarefa sempre é exibida, mesmo quando a opção de cópia avançada de arquivos está selecionada.</span><span class="sxs-lookup"><span data-stu-id="3dc61-117">This task is always displayed, even when the advanced Copy files option is selected.</span></span>
    
- <span data-ttu-id="3dc61-118">**Extração de texto**: quando há arquivos nativos, a descoberta eletrônica avançada extrai o texto desses arquivos usando o DTSearch.</span><span class="sxs-lookup"><span data-stu-id="3dc61-118">**Text extraction**: When there are native files, Advanced eDiscovery extracts text from these files using DTSearch.</span></span> <span data-ttu-id="3dc61-119">O texto extraído desses arquivos é armazenado como arquivos de texto na pasta de caso.</span><span class="sxs-lookup"><span data-stu-id="3dc61-119">The extracted text of these files is stored as text files in the case folder.</span></span>
    
- <span data-ttu-id="3dc61-120">**Atualizando metadados**: processa os metadados carregados.</span><span class="sxs-lookup"><span data-stu-id="3dc61-120">**Updating metadata**: Processes the loaded metadata.</span></span> 
    
- <span data-ttu-id="3dc61-121">**Finalizando**: o processamento interno que finaliza os dados de arquivos de caso carregados (por exemplo, identificar arquivos de erro e de êxito).</span><span class="sxs-lookup"><span data-stu-id="3dc61-121">**Finalizing**: Internal processing that finalizes data of loaded case files (for example, identify error and success files).</span></span> 
    
<span data-ttu-id="3dc61-122">Status da tarefa: exibido após a conclusão da tarefa.</span><span class="sxs-lookup"><span data-stu-id="3dc61-122">Task status: Displayed after task completion.</span></span> <span data-ttu-id="3dc61-123">Enquanto as tarefas estão em execução, a duração da execução é exibida.</span><span class="sxs-lookup"><span data-stu-id="3dc61-123">While tasks are running, run duration is displayed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3dc61-124">As tarefas concluídas também podem incluir totais de arquivos que concluiram o processamento ou arquivos com erros.</span><span class="sxs-lookup"><span data-stu-id="3dc61-124">Completed tasks may also include totals for files that completed processing or files with errors.</span></span> 
  
> [!TIP]
> <span data-ttu-id="3dc61-125">"Cancelar" oferece uma opção de reversão para interromper a execução do processo e reverter para o preenchimento de dados anterior ou os dados processados salvos.</span><span class="sxs-lookup"><span data-stu-id="3dc61-125">"Cancel" provides a rollback option to stop Process execution and then roll back to the previous data population or saved processed data.</span></span> <span data-ttu-id="3dc61-126">Rollback limpa todos os dados processados.</span><span class="sxs-lookup"><span data-stu-id="3dc61-126">Rollback clears all processed data.</span></span> <span data-ttu-id="3dc61-127">Se você não quiser que os dados processados sejam perdidos (por exemplo, você planeja recarregar esses arquivos), selecione a opção "Cancelar" nesta janela para escolher não reverter.</span><span class="sxs-lookup"><span data-stu-id="3dc61-127">If you do not want the processed data to be lost (for example, you plan to reload these files), select the "Cancel" option in this window to choose not to roll back.</span></span> 
  
## <a name="process-summary"></a><span data-ttu-id="3dc61-128">Resumo do processo</span><span class="sxs-lookup"><span data-stu-id="3dc61-128">Process summary</span></span>

<span data-ttu-id="3dc61-129">No resumo \> do \> processo \> de preparação dos resultados do processo, uma divisão dos resultados do arquivo carregado é exibida de acordo com o processamento de arquivos bem-sucedido e resultados de erros.</span><span class="sxs-lookup"><span data-stu-id="3dc61-129">In Prepare \> Process \> Results \> Process summary, a breakdown of loaded file results is displayed according to successful file processing and error results.</span></span>
  
<span data-ttu-id="3dc61-130">Os painéis apresentam uma exibição gráfica das estatísticas de arquivo importadas, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3dc61-130">The panes present a graphical display of imported file statistics, as follows:</span></span>
  
- <span data-ttu-id="3dc61-131">**Resumo do processo acumula**d: todos os arquivos no caso.</span><span class="sxs-lookup"><span data-stu-id="3dc61-131">**Process summary accumulate**d: All files in the case.</span></span>
    
- <span data-ttu-id="3dc61-132">**Resumo do processo por último**: arquivos carregados da última sessão ou ação.</span><span class="sxs-lookup"><span data-stu-id="3dc61-132">**Process summary last**: Files loaded from the last session or action.</span></span> 
    
- <span data-ttu-id="3dc61-133">**Famílias por último**: informações da família no caso (se houver).</span><span class="sxs-lookup"><span data-stu-id="3dc61-133">**Families last**: Family information in the case (if any).</span></span>
    
- <span data-ttu-id="3dc61-134">Se os arquivos **semente** foram adicionados, o número de arquivos semente é listado por problema definido para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="3dc61-134">If **Seed** files were added, the number of seed files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="3dc61-135">Se a marcação de arquivos de **propagação** falhar, isso também será observado.</span><span class="sxs-lookup"><span data-stu-id="3dc61-135">If the marking of **Seed** files failed, that is also noted.</span></span> 
    
- <span data-ttu-id="3dc61-136">Se forem adicionados arquivos **previamente marcados** , o número de arquivos previamente marcados será listado por problema definido para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="3dc61-136">If **Pre-tagged** files were added, the number of pre-tagged files is listed per issue that was defined for the files.</span></span> 
    
    <span data-ttu-id="3dc61-137">Se a marcação de arquivos **previamente marcados** falhou, isso também é observado.</span><span class="sxs-lookup"><span data-stu-id="3dc61-137">If the marking of **Pre-tagged** files failed, that is also noted.</span></span> 
    
![Resumo do módulo de processamento](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a><span data-ttu-id="3dc61-139">Resumo do processo acumulado e últimos gráficos</span><span class="sxs-lookup"><span data-stu-id="3dc61-139">Process summary accumulated and last charts</span></span>

<span data-ttu-id="3dc61-140">A barra esquerda inclui arquivos de origem + extraídos: que são todos os arquivos encontrados.</span><span class="sxs-lookup"><span data-stu-id="3dc61-140">The left bar includes Source + extracted files: which is all files found.</span></span> 
  
<span data-ttu-id="3dc61-141">A barra direita, processada, inclui:</span><span class="sxs-lookup"><span data-stu-id="3dc61-141">The right bar, Processed, includes:</span></span>
  
- <span data-ttu-id="3dc61-142">Arquivos com erros de carregamento</span><span class="sxs-lookup"><span data-stu-id="3dc61-142">Files with load errors</span></span>
    
- <span data-ttu-id="3dc61-143">Arquivos carregados com êxito, que podem incluir:</span><span class="sxs-lookup"><span data-stu-id="3dc61-143">Successfully loaded files, which may include:</span></span> 
    
  - <span data-ttu-id="3dc61-144">**Existentes**: arquivos que foram carregados antes e agora são carregados novamente (incluindo duplicatas).</span><span class="sxs-lookup"><span data-stu-id="3dc61-144">**Existing**: Files that were loaded before and are now loaded again (including duplicates).</span></span>
    
  - <span data-ttu-id="3dc61-145">**Text**: arquivos exclusivos com texto.</span><span class="sxs-lookup"><span data-stu-id="3dc61-145">**Text**: Unique files with text.</span></span>
    
  - <span data-ttu-id="3dc61-146">**Não texto**: Arquivos de texto vazios, arquivos de texto nativo vazios, arquivos de não-texto nativo.</span><span class="sxs-lookup"><span data-stu-id="3dc61-146">**Non-text**: Empty text files, empty native text files, native non-text files.</span></span> 
    
  - <span data-ttu-id="3dc61-147">**Duplicar**s: duplicar arquivos com texto.</span><span class="sxs-lookup"><span data-stu-id="3dc61-147">**Duplicate**s: Duplicate files with text.</span></span>
    
## <a name="last-process-errors"></a><span data-ttu-id="3dc61-148">Erros do último processo</span><span class="sxs-lookup"><span data-stu-id="3dc61-148">Last process errors</span></span>

<span data-ttu-id="3dc61-149">Em preparar \> resultados \> \> do processo últimos erros de processo, os detalhes dos erros na última sessão ou ação executada são exibidos.</span><span class="sxs-lookup"><span data-stu-id="3dc61-149">In Prepare \> Process \> Results \> Last process errors, details of the errors in the last session or action performed are displayed.</span></span>
  
![Erros do módulo de processamento](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a><span data-ttu-id="3dc61-151">Também consulte</span><span class="sxs-lookup"><span data-stu-id="3dc61-151">See also</span></span>

[<span data-ttu-id="3dc61-152">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="3dc61-152">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="3dc61-153">Executando o módulo de processo e carregando dados</span><span class="sxs-lookup"><span data-stu-id="3dc61-153">Running the Process module and loading data</span></span>](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

