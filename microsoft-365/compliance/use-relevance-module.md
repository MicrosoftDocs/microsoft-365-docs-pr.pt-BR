---
title: Usar o módulo de relevância para analisar dados em evidência
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
ms.openlocfilehash: cf69f76fd461c718bccb560f91bf31c2e30aea39
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601288"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="a9b25-102">Usar o módulo de relevância para analisar dados em evidência</span><span class="sxs-lookup"><span data-stu-id="a9b25-102">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="a9b25-103">Em investigações de dados (prévia), o módulo de relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a uma investigação.</span><span class="sxs-lookup"><span data-stu-id="a9b25-103">In Data Investigations (Preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="a9b25-104">O fluxo de trabalho de relevância é mostrado e descrito da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="a9b25-104">The Relevance workflow is shown and described as follows:</span></span>
  
![Fluxo de trabalho de relevância](media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="a9b25-106">**Ciclos de avaliação e controle**:</span><span class="sxs-lookup"><span data-stu-id="a9b25-106">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="a9b25-107">**Avaliação**: habilita a avaliação prévia com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação de previsão.</span><span class="sxs-lookup"><span data-stu-id="a9b25-107">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="a9b25-108">**Track**: calcular e exibir resultados provisórios da avaliação e monitorar a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-108">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="a9b25-109">**Ciclos de treinamento e acompanhamento**</span><span class="sxs-lookup"><span data-stu-id="a9b25-109">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="a9b25-110">**Marca**: as investigações de dados (visualização) aprende critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.</span><span class="sxs-lookup"><span data-stu-id="a9b25-110">**Tag**: Data Investigations (Preview) learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="a9b25-111">**Track**: calcular e exibir resultados provisórios do treinamento de relevância e monitorar a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-111">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="a9b25-112">**Cálculo de lote**: os critérios de relevância acumulados e aprendidos são aplicados a todo o conjunto de arquivos e uma pontuação de relevância é gerada para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-112">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="a9b25-113">\*\*\*\*@ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ Os resultados da análise aplicada ao caso inteiro são exibidos após o cálculo de lote, e os dados usados para fazer decisões de revisão</span><span class="sxs-lookup"><span data-stu-id="a9b25-113">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="a9b25-114">**Test**: os resultados podem ser testados para verificar a validade e a eficácia do processamento de investigações de dados (visualização).</span><span class="sxs-lookup"><span data-stu-id="a9b25-114">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (Preview) processing.</span></span>

- <span data-ttu-id="a9b25-115">**Pesquisa**: depois que o fluxo de trabalho de relevância estiver concluído, você poderá usar a saída como ler percentil de um documento para o seu problema ao executar uma consulta dentro do seu conjunto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a9b25-115">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="a9b25-116">Diretrizes para treinamento e análise de relevância</span><span class="sxs-lookup"><span data-stu-id="a9b25-116">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="a9b25-117">Veja a seguir uma visão geral das diretrizes de treinamento e análise de relevância:</span><span class="sxs-lookup"><span data-stu-id="a9b25-117">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="a9b25-118">**Erros e inconsistências**: se forem feitos erros de marcação durante o treinamento, retorne a amostras de arquivos anteriores para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="a9b25-118">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="a9b25-119">Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou problema, os critérios de relevância deverão ser redefinidos pelo administrador e o treinamento de relevância reiniciado.</span><span class="sxs-lookup"><span data-stu-id="a9b25-119">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="a9b25-120">**Marcação e treinamento**:</span><span class="sxs-lookup"><span data-stu-id="a9b25-120">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="a9b25-121">Os arquivos devem ser marcados com base apenas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-121">Files should be tagged based on content only.</span></span> <span data-ttu-id="a9b25-122">Não considere metadados, como os responsáveis, a data ou o caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-122">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="a9b25-123">Não considere indicações de intervalo de datas no texto ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="a9b25-123">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="a9b25-124">Não considere imagens gráficas incorporadas ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="a9b25-124">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="a9b25-125">Ignorar o texto aplicado à relevância será removido no conteúdo do arquivo exibido no modo de exibição de texto de relevância.</span><span class="sxs-lookup"><span data-stu-id="a9b25-125">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="a9b25-126">Se os valores para ignorar texto tiverem sido definidos após o treinamento de relevância já ter sido iniciado, o novo texto ignorado será aplicado a arquivos de exemplo criados a partir do ponto em que foi definido.</span><span class="sxs-lookup"><span data-stu-id="a9b25-126">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="a9b25-127">O recurso Ignorar texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos</span><span class="sxs-lookup"><span data-stu-id="a9b25-127">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="a9b25-128">Use a opção **ignorar marcação** apenas quando necessário.</span><span class="sxs-lookup"><span data-stu-id="a9b25-128">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="a9b25-129">As investigações de dados (prévia) não são treinadas com base em arquivos ignorados.</span><span class="sxs-lookup"><span data-stu-id="a9b25-129">Data Investigations (Preview) does not train based on skipped files.</span></span> <span data-ttu-id="a9b25-130">Em avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como relevante (R) ou não relevante (NR) sempre que possível, em vez de selecionar **ignorar**.</span><span class="sxs-lookup"><span data-stu-id="a9b25-130">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="a9b25-131">Quando a investigação de dados (prévia) avalia o treinamento, ela pode ser vista como esses tipos de arquivos foram processados.</span><span class="sxs-lookup"><span data-stu-id="a9b25-131">When Data Investigations (Preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="a9b25-132">Até mesmo arquivos com uma quantidade muito pequena de texto extraído deve ser marcado em treinamento como R/NR, e não como "ignorar", quando possível.</span><span class="sxs-lookup"><span data-stu-id="a9b25-132">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="a9b25-133">A marcação pode impactar o classificador, desde que o arquivo seja legível e possa ser marcado como R/NR.</span><span class="sxs-lookup"><span data-stu-id="a9b25-133">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="a9b25-134">O número de sequência de arquivo na lista de arquivos de amostra exibidos na guia **marca** permite que o usuário retorne à ordem de exibição original dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="a9b25-134">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="a9b25-135">Você pode retornar a qualquer amostra e alterar a marcação dos arquivos de avaliação e de conjunto de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a9b25-135">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="a9b25-136">As alterações serão aplicadas durante a criação do próximo exemplo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-136">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="a9b25-137">Os arquivos do Excel digitalizados no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="a9b25-137">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="a9b25-138">Quando estiver em dúvida sobre a marcação de relevância de um arquivo, consulte um especialista.</span><span class="sxs-lookup"><span data-stu-id="a9b25-138">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="a9b25-139">Marcações incorretas durante o treinamento de relevância podem causar perda de tempo mais tarde no processo e também podem ter um impacto negativo sobre a qualidade dos resultados gerais.</span><span class="sxs-lookup"><span data-stu-id="a9b25-139">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="a9b25-140">As palavras-chave que foram definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.</span><span class="sxs-lookup"><span data-stu-id="a9b25-140">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="a9b25-141">**Cálculo em lotes**: os arquivos que foram marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100.</span><span class="sxs-lookup"><span data-stu-id="a9b25-141">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="a9b25-142">Isso se aplica à marcação feita antes do cálculo em lote.</span><span class="sxs-lookup"><span data-stu-id="a9b25-142">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="a9b25-143">Se o especialista tiver alternado o problema para ficar inativo após o cálculo de lote e a marcação contínua desse problema, as pontuações recentemente marcadas não serão 100/0, mas sim a pontuação original.</span><span class="sxs-lookup"><span data-stu-id="a9b25-143">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="a9b25-144">**Modo de problemas e de amostragem**: problemas geralmente estão desativados quando o trabalho deles é concluído (o treinamento de relevância é estabilizado e o cálculo do lote foi realizado), quando os problemas são cancelados ou quando outro usuário está trabalhando com os problemas.</span><span class="sxs-lookup"><span data-stu-id="a9b25-144">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="a9b25-145">Etapas no treinamento de relevância</span><span class="sxs-lookup"><span data-stu-id="a9b25-145">Steps in Relevance training</span></span>

<span data-ttu-id="a9b25-146">Na guia **controle \> de relevância** , as investigações de dados fornecem recomendações sobre como proceder no processamento, seguindo as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="a9b25-146">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="a9b25-147">As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="a9b25-147">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="a9b25-148">Marcação/continuação de marcação: marcação de arquivo e classificação de relevância executada por um especialista para cada arquivo e problema em um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-148">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="a9b25-149">Implicação: um exemplo existente precisa ser marcado.</span><span class="sxs-lookup"><span data-stu-id="a9b25-149">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="a9b25-150">Avaliação/continuação da avaliação: habilita a validação antecipada da relevância do problema de caso e uma exibição preliminar da relevância da população de arquivo importada para o caso atual.</span><span class="sxs-lookup"><span data-stu-id="a9b25-150">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="a9b25-151">Implicação: mais avaliação obrigatória ou recomendada.</span><span class="sxs-lookup"><span data-stu-id="a9b25-151">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="a9b25-152">Treinamento de treinamento/continuação: processo durante o qual as investigações de dados aprendem do especialista, que está marcando os exemplos de arquivos e obtém a capacidade de identificar critérios de relevância pertinentes a cada problema dentro do contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="a9b25-152">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="a9b25-153">Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado.</span><span class="sxs-lookup"><span data-stu-id="a9b25-153">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="a9b25-154">Cálculo em lote: o processo de relevância no qual as investigações de dados leva o conhecimento adquirido durante o estágio de treinamento e o aplica à população de arquivo inteiro.</span><span class="sxs-lookup"><span data-stu-id="a9b25-154">Batch calculation: Relevance process in which Data investigations takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="a9b25-155">Todos os arquivos no grupo de arquivos pertinente são avaliados por relevância e recebem uma pontuação de relevância.</span><span class="sxs-lookup"><span data-stu-id="a9b25-155">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="a9b25-156">Implicação: o problema foi estabilizado e o cálculo de lote pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="a9b25-156">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="a9b25-157">Atualização: relevância indica quando um especialista revisa e marca uma amostra de arquivos selecionados a partir de uma carga de arquivos adicional durante um cenário de cargas sem interrupção.</span><span class="sxs-lookup"><span data-stu-id="a9b25-157">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="a9b25-158">Implicação: uma nova carga foi adicionada e a atualização é necessária para continuar trabalhando.</span><span class="sxs-lookup"><span data-stu-id="a9b25-158">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="a9b25-159">Inconsistências de marca: o processo identifica, por meio de um algoritmo de investigações de dados, inconsistências no processo de marcação de arquivos que podem afetar negativamente a análise.</span><span class="sxs-lookup"><span data-stu-id="a9b25-159">Tag inconsistencies: Process identifies, via an Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="a9b25-160">Implicação: o exemplo a seguir inclui arquivos que foram marcados em exemplos anteriores e sua marcação deve ser refeita.</span><span class="sxs-lookup"><span data-stu-id="a9b25-160">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="a9b25-161">Classificador de atualização: permite que o usuário Aplique alterações de marcação ou propagação.</span><span class="sxs-lookup"><span data-stu-id="a9b25-161">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="a9b25-162">Implicação: as alterações de marcação e propagação podem ser aplicadas sem a necessidade de executar outra amostra de relevância manualmente.</span><span class="sxs-lookup"><span data-stu-id="a9b25-162">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="a9b25-163">Em retenção: o processo de treinamento de relevância foi concluído.</span><span class="sxs-lookup"><span data-stu-id="a9b25-163">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="a9b25-164">Implicação: nenhum treinamento de relevância é necessário neste ponto.</span><span class="sxs-lookup"><span data-stu-id="a9b25-164">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="a9b25-165">Embora as investigações de dados orientam você durante o processo, com as próximas etapas recomendadas em estágios diferentes, também permite navegar entre guias e páginas e fazer escolhas para lidar com situações que possam ser pertinentes a seu caso, problema ou processo de revisão de documento.</span><span class="sxs-lookup"><span data-stu-id="a9b25-165">Although Data investigations guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="a9b25-166">É possível aceitar ou substituir as investigações de dados as opções de processamento da próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="a9b25-166">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="a9b25-167">Se você deseja executar uma etapa diferente da próxima etapa recomendada, clique na **próxima etapa** listada na exibição de problema expandida na caixa de diálogo, clique no botão **Modificar** ao lado da próxima etapa e selecione outra opção de próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="a9b25-167">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a9b25-168">Algumas opções podem permanecer desabilitadas após a desbloqueio, pois elas não são suportadas para uso nesse ponto no processo.</span><span class="sxs-lookup"><span data-stu-id="a9b25-168">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="a9b25-169">Mais informações</span><span class="sxs-lookup"><span data-stu-id="a9b25-169">More information</span></span>

[<span data-ttu-id="a9b25-170">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="a9b25-170">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a9b25-171">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="a9b25-171">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a9b25-172">Treinamento de marcação e relevância</span><span class="sxs-lookup"><span data-stu-id="a9b25-172">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a9b25-173">Análise de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="a9b25-173">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a9b25-174">Decidindo com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="a9b25-174">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a9b25-175">Testando análise de relevância</span><span class="sxs-lookup"><span data-stu-id="a9b25-175">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="a9b25-176">Consultar os dados em evidência</span><span class="sxs-lookup"><span data-stu-id="a9b25-176">Query the data in evidence</span></span>](evidence-query.md)
