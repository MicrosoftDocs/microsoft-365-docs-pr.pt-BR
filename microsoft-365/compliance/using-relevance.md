---
title: Usar o módulo de relevância para analisar dados na descoberta eletrônica avançada
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
description: Saiba como o módulo de relevância analisa dados em evidência com uma descrição do fluxo de trabalho de relevância e as etapas de treinamento na descoberta eletrônica avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4babb0aa7693bc1107cc7594da967bca2d307228
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034463"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="50711-103">Usar o módulo de relevância para analisar dados na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="50711-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="50711-104">Na descoberta eletrônica avançada, o módulo de relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="50711-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="50711-105">Para usar o fluxo de trabalho de relevância, vá para gerenciar análise definida em um conjunto de análise e clique em mostrar relevância.</span><span class="sxs-lookup"><span data-stu-id="50711-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="50711-106">Há algumas etapas que precisam ser concluídas para que você possa iniciar o fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="50711-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="50711-107">Processo: cada conjunto de carga adicionado ao conjunto de revisão será exibido como um "contêiner" aqui.</span><span class="sxs-lookup"><span data-stu-id="50711-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="50711-108">Você precisa processar esses documentos para poder adicioná-los ao módulo de relevância; Isso também é onde você pode marcá-los como semente ou pré-selecionado para um problema específico.</span><span class="sxs-lookup"><span data-stu-id="50711-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="50711-109">Adicionar à relevância: em cargas \> de relevância, você pode adicionar documentos que foram processados à relevância para torná-los disponíveis para treinamento.</span><span class="sxs-lookup"><span data-stu-id="50711-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="50711-110">O fluxo de trabalho de relevância é mostrado e descrito da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="50711-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Fluxo de trabalho de relevância](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="50711-112">**Ciclos de avaliação e controle**:</span><span class="sxs-lookup"><span data-stu-id="50711-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="50711-113">**Avaliação**: habilita a avaliação prévia com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação de previsão.</span><span class="sxs-lookup"><span data-stu-id="50711-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="50711-114">**Track**: calcular e exibir resultados provisórios da avaliação e monitorar a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="50711-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="50711-115">**Ciclos de treinamento e acompanhamento**</span><span class="sxs-lookup"><span data-stu-id="50711-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="50711-116">**Marca**: a descoberta eletrônica avançada aprende critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.</span><span class="sxs-lookup"><span data-stu-id="50711-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="50711-117">**Track**: calcular e exibir resultados provisórios do treinamento de relevância e monitorar a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="50711-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="50711-118">**Cálculo de lote**: os critérios de relevância acumulados e aprendidos são aplicados a todo o conjunto de arquivos e uma pontuação de relevância é gerada para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="50711-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="50711-119">**Decide**@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ Os resultados da análise aplicada ao caso inteiro são exibidos após o cálculo de lote, e os dados usados para fazer decisões de revisão</span><span class="sxs-lookup"><span data-stu-id="50711-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="50711-120">**Test**: os resultados podem ser testados para verificar a validade e a eficácia do processamento avançado de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="50711-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="50711-121">**Pesquisa**: depois que o fluxo de trabalho de relevância estiver concluído, você poderá usar a saída como ler percentil de um documento para o seu problema ao executar uma consulta no conjunto de análise.</span><span class="sxs-lookup"><span data-stu-id="50711-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="50711-122">Diretrizes para treinamento e análise de relevância</span><span class="sxs-lookup"><span data-stu-id="50711-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="50711-123">Veja a seguir uma visão geral das diretrizes de treinamento e análise de relevância:</span><span class="sxs-lookup"><span data-stu-id="50711-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="50711-124">**Erros e inconsistências**: se forem feitos erros de marcação durante o treinamento, retorne a amostras de arquivos anteriores para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="50711-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="50711-125">Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou problema, os critérios de relevância deverão ser redefinidos pelo administrador e o treinamento de relevância reiniciado.</span><span class="sxs-lookup"><span data-stu-id="50711-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="50711-126">**Marcação e treinamento**:</span><span class="sxs-lookup"><span data-stu-id="50711-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="50711-127">Os arquivos devem ser marcados com base apenas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="50711-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="50711-128">Não considere metadados, como os responsáveis, a data ou o caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="50711-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="50711-129">Não considere indicações de intervalo de datas no texto ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="50711-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="50711-130">Não considere imagens gráficas incorporadas ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="50711-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="50711-131">Ignorar o texto aplicado à relevância será removido no conteúdo do arquivo exibido no modo de exibição de texto de relevância.</span><span class="sxs-lookup"><span data-stu-id="50711-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="50711-132">Se os valores para ignorar texto tiverem sido definidos após o treinamento de relevância já ter sido iniciado, o novo texto ignorado será aplicado a arquivos de exemplo criados a partir do ponto em que foi definido.</span><span class="sxs-lookup"><span data-stu-id="50711-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="50711-133">O recurso Ignorar texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos</span><span class="sxs-lookup"><span data-stu-id="50711-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="50711-134">Use a opção **ignorar marcação** apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="50711-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="50711-135">A descoberta eletrônica avançada não treina com base em arquivos ignorados.</span><span class="sxs-lookup"><span data-stu-id="50711-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="50711-136">Em avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como relevante (R) ou não relevante (NR) sempre que possível, em vez de selecionar **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="50711-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="50711-137">Quando a descoberta eletrônica avançada avaliar o treinamento, ela poderá ser vista como esses tipos de arquivos foram processados.</span><span class="sxs-lookup"><span data-stu-id="50711-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="50711-138">Até mesmo arquivos com uma quantidade muito pequena de texto extraído deve ser marcado em treinamento como R/NR, e não como "ignorar", quando possível.</span><span class="sxs-lookup"><span data-stu-id="50711-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="50711-139">A marcação pode impactar o classificador, desde que o arquivo seja legível e possa ser marcado como R/NR.</span><span class="sxs-lookup"><span data-stu-id="50711-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="50711-140">O número de sequência de arquivo na lista de arquivos de amostra exibidos na guia **marca** permite que o usuário retorne à ordem de exibição original dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="50711-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="50711-141">Você pode retornar a qualquer amostra e alterar a marcação dos arquivos de avaliação e de conjunto de treinamento.</span><span class="sxs-lookup"><span data-stu-id="50711-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="50711-142">As alterações serão aplicadas durante a criação do próximo exemplo.</span><span class="sxs-lookup"><span data-stu-id="50711-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="50711-143">Os arquivos do Excel digitalizados no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="50711-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="50711-144">Quando estiver em dúvida sobre a marcação de relevância de um arquivo, consulte um especialista.</span><span class="sxs-lookup"><span data-stu-id="50711-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="50711-145">Marcações incorretas durante o treinamento de relevância podem causar perda de tempo mais tarde no processo e também podem ter um impacto negativo sobre a qualidade dos resultados gerais.</span><span class="sxs-lookup"><span data-stu-id="50711-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="50711-146">As palavras-chave que foram definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.</span><span class="sxs-lookup"><span data-stu-id="50711-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="50711-147">**Cálculo em lotes**: os arquivos que foram marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100.</span><span class="sxs-lookup"><span data-stu-id="50711-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="50711-148">Isso se aplica à marcação feita antes do cálculo em lote.</span><span class="sxs-lookup"><span data-stu-id="50711-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="50711-149">Se o especialista tiver alternado o problema para ficar inativo após o cálculo de lote e a marcação contínua desse problema, as pontuações recentemente marcadas não serão 100/0, mas sim a pontuação original.</span><span class="sxs-lookup"><span data-stu-id="50711-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="50711-150">**Modo de problemas e de amostragem**: problemas geralmente estão desativados quando o trabalho deles é concluído (o treinamento de relevância é estabilizado e o cálculo do lote foi realizado), quando os problemas são cancelados ou quando outro usuário está trabalhando com os problemas.</span><span class="sxs-lookup"><span data-stu-id="50711-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="50711-151">Etapas no treinamento de relevância</span><span class="sxs-lookup"><span data-stu-id="50711-151">Steps in Relevance training</span></span>

<span data-ttu-id="50711-152">Na guia **controle \> de relevância** , a descoberta eletrônica avançada fornece recomendações sobre como proceder no processamento, com as próximas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="50711-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="50711-153">As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="50711-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="50711-154">Marcação/continuação de marcação: marcação de arquivo e classificação de relevância executada por um especialista para cada arquivo e problema em um exemplo.</span><span class="sxs-lookup"><span data-stu-id="50711-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="50711-155">Implicação: um exemplo existente precisa ser marcado.</span><span class="sxs-lookup"><span data-stu-id="50711-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="50711-156">Avaliação/continuação da avaliação: habilita a validação antecipada da relevância do problema de caso e uma exibição preliminar da relevância da população de arquivo importada para o caso atual.</span><span class="sxs-lookup"><span data-stu-id="50711-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="50711-157">Implicação: mais avaliação obrigatória ou recomendada.</span><span class="sxs-lookup"><span data-stu-id="50711-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="50711-158">Treinamento de treinamento/continuação: processo durante o qual a descoberta eletrônica avançada aprende do especialista que está marcando os exemplos de arquivo e obtém a capacidade de identificar critérios de relevância pertinentes a cada problema dentro do contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="50711-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="50711-159">Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado.</span><span class="sxs-lookup"><span data-stu-id="50711-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="50711-160">Cálculo em lote: processo de relevância no qual a descoberta eletrônica avançada Obtém o conhecimento adquirido durante o estágio de treinamento e a aplica à população de arquivo inteiro.</span><span class="sxs-lookup"><span data-stu-id="50711-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="50711-161">Todos os arquivos no grupo de arquivos pertinente são avaliados por relevância e recebem uma pontuação de relevância.</span><span class="sxs-lookup"><span data-stu-id="50711-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="50711-162">Implicação: o problema foi estabilizado e o cálculo de lote pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="50711-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="50711-163">Atualização: relevância indica quando um especialista revisa e marca uma amostra de arquivos selecionados a partir de uma carga de arquivos adicional durante um cenário de cargas sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="50711-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="50711-164">Implicação: uma nova carga foi adicionada e a atualização é necessária para continuar trabalhando.</span><span class="sxs-lookup"><span data-stu-id="50711-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="50711-165">Inconsistências de marca: o processo identifica, por meio de um algoritmo de descoberta eletrônica avançado, inconsistências no processo de marcação de arquivos que podem afetar negativamente a análise.</span><span class="sxs-lookup"><span data-stu-id="50711-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="50711-166">Implicação: o exemplo a seguir inclui arquivos que foram marcados em exemplos anteriores e sua marcação deve ser refeita.</span><span class="sxs-lookup"><span data-stu-id="50711-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="50711-167">Classificador de atualização: permite que o usuário Aplique alterações de marcação ou propagação.</span><span class="sxs-lookup"><span data-stu-id="50711-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="50711-168">Implicação: as alterações de marcação e propagação podem ser aplicadas sem a necessidade de executar outra amostra de relevância manualmente.</span><span class="sxs-lookup"><span data-stu-id="50711-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="50711-169">Em retenção: o processo de treinamento de relevância foi concluído.</span><span class="sxs-lookup"><span data-stu-id="50711-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="50711-170">Implicação: nenhum treinamento de relevância é necessário neste ponto.</span><span class="sxs-lookup"><span data-stu-id="50711-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="50711-171">Embora a descoberta eletrônica avançada orienta você durante o processo, com as próximas etapas recomendadas em estágios diferentes, ela também permite que você navegue entre guias e páginas e faça escolhas para lidar com situações que possam ser pertinentes a seu processo de análise de caso, de problema ou de documento individual.</span><span class="sxs-lookup"><span data-stu-id="50711-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="50711-172">É possível aceitar ou substituir as opções de processamento de próxima etapa de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="50711-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="50711-173">Se você deseja executar uma etapa diferente da próxima etapa recomendada, clique na **próxima etapa** listada na exibição de problema expandida na caixa de diálogo, clique no botão **Modificar** ao lado da próxima etapa e selecione outra opção de próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="50711-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="50711-174">Algumas opções podem permanecer desabilitadas após a desbloqueio, pois elas não são suportadas para uso nesse ponto no processo.</span><span class="sxs-lookup"><span data-stu-id="50711-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="50711-175">Mais informações</span><span class="sxs-lookup"><span data-stu-id="50711-175">More information</span></span>

[<span data-ttu-id="50711-176">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="50711-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="50711-177">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="50711-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="50711-178">Treinamento de marcação e relevância</span><span class="sxs-lookup"><span data-stu-id="50711-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="50711-179">Análise de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="50711-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="50711-180">Decidindo com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="50711-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="50711-181">Testando análise de relevância</span><span class="sxs-lookup"><span data-stu-id="50711-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="50711-182">Consultar os dados em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="50711-182">Query the data in a review set</span></span>](review-set-search.md)
