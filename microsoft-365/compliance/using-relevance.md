---
title: Usar o módulo Relevância para analisar dados na Descoberta Eletrônico Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como o módulo relevância analisa dados em evidência com uma descrição do fluxo de trabalho de relevância e etapas de treinamento na Descoberta Avançada.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286057"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="cc3be-103">Usar o módulo Relevância para analisar dados na Descoberta Eletrônico Avançada</span><span class="sxs-lookup"><span data-stu-id="cc3be-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="cc3be-104">Na Descoberta Avançada, o módulo Relevância inclui o treinamento de relevância e a revisão de arquivos relacionados a um caso.</span><span class="sxs-lookup"><span data-stu-id="cc3be-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="cc3be-105">Para usar o fluxo de trabalho de Relevância, vá para Gerenciar conjunto de revisão dentro de um conjunto de revisão e clique em Mostrar Relevância.</span><span class="sxs-lookup"><span data-stu-id="cc3be-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="cc3be-106">Há algumas etapas que você precisa concluir antes de iniciar o fluxo de trabalho:</span><span class="sxs-lookup"><span data-stu-id="cc3be-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="cc3be-107">Processo: cada conjunto de carga adicionado ao conjunto de revisão será aparecer como um "contêiner" aqui.</span><span class="sxs-lookup"><span data-stu-id="cc3be-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="cc3be-108">Você precisa processar esses documentos antes de adicioná-los ao módulo relevância; Também é aqui que você pode marcá-los como seed ou pré-marcado para um problema específico.</span><span class="sxs-lookup"><span data-stu-id="cc3be-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="cc3be-109">Adicionar à Relevância: Em Cargas de Relevância, você pode adicionar documentos que foram processados para \> Relevância para torná-los disponíveis para treinamento.</span><span class="sxs-lookup"><span data-stu-id="cc3be-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="cc3be-110">O fluxo de trabalho relevância é mostrado e descrito da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="cc3be-110">The Relevance workflow is shown and described as follows:</span></span>
  
![Fluxo de trabalho de relevância](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="cc3be-112">**Ciclos de avaliação e rastreamento:**</span><span class="sxs-lookup"><span data-stu-id="cc3be-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="cc3be-113">**Avaliação:** permite a avaliação antecipada com base em uma amostra aleatória de arquivos e usa essa avaliação para aplicar decisões para determinar o desempenho do processo de codificação preditiva.</span><span class="sxs-lookup"><span data-stu-id="cc3be-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="cc3be-114">**Controle:** calcule e exibe os resultados provisórios da avaliação enquanto monitora a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cc3be-115">**Ciclos de treinamento e rastreamento**</span><span class="sxs-lookup"><span data-stu-id="cc3be-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="cc3be-116">**Marca**: a Descoberta Avançada aprende os critérios de relevância específicos para cada problema com base na revisão iterativa do especialista e na marcação de arquivos individuais.</span><span class="sxs-lookup"><span data-stu-id="cc3be-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="cc3be-117">**Controle:** calcule e exibe os resultados provisórios do treinamento de relevância enquanto monitora a validade estatística do processo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="cc3be-118">**Cálculo em** lotes : Os critérios de relevância acumulados e aprendidas são aplicados a todo o conjunto de arquivos, e uma pontuação de Relevância é gerada para cada arquivo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="cc3be-119">**Decidir:** os resultados da análise aplicados a todo o caso são exibidos após o cálculo em lotes, e os dados usados para tomar decisões de revisão de documentos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="cc3be-120">**Teste:** os resultados podem ser testados para verificar a validade e a eficácia do processamento de Descobertas Públicas Avançada.</span><span class="sxs-lookup"><span data-stu-id="cc3be-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="cc3be-121">**Pesquisa:** depois que o fluxo de trabalho de Relevância for concluído, você poderá usar a saída, como o percentil de leitura de um documento, para o problema ao executar uma consulta no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="cc3be-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="cc3be-122">Diretrizes para treinamento e revisão de relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="cc3be-123">A seguir está uma visão geral das diretrizes de treinamento e revisão de relevância:</span><span class="sxs-lookup"><span data-stu-id="cc3be-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="cc3be-124">**Erros e inconsistências:** se erros de marcação são feitos durante o treinamento, retorne aos exemplos de arquivo anteriores para corrigi-los.</span><span class="sxs-lookup"><span data-stu-id="cc3be-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="cc3be-125">Se houver muitos erros para corrigir ou se houver uma nova perspectiva do caso ou do problema, os critérios de relevância deverão ser redefinidos pelo Administrador e o treinamento de Relevância será reiniciado.</span><span class="sxs-lookup"><span data-stu-id="cc3be-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="cc3be-126">**Marcação e treinamento:**</span><span class="sxs-lookup"><span data-stu-id="cc3be-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="cc3be-127">Os arquivos devem ser marcados com base apenas no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="cc3be-128">Não considere metadados, como custodiante, data ou caminho do arquivo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="cc3be-129">Não considere indicações de intervalo de datas no texto ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="cc3be-130">Não considere imagens gráficas incorporadas ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="cc3be-131">Ignorar o texto aplicado à relevância será removido do conteúdo do arquivo exibido no ponto de vista de texto em Relevância.</span><span class="sxs-lookup"><span data-stu-id="cc3be-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="cc3be-132">Se os valores para Ignorar texto foram definidos após o treinamento de relevância já iniciado, o novo texto ignorado será aplicado aos arquivos de exemplo criados a partir do ponto em que foi definido.</span><span class="sxs-lookup"><span data-stu-id="cc3be-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="cc3be-133">O recurso Ignorar Texto deve ser usado com cautela, pois seu uso pode reduzir o desempenho da análise de arquivos</span><span class="sxs-lookup"><span data-stu-id="cc3be-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="cc3be-134">Use a **opção de marcação** Ignorar somente quando necessário.</span><span class="sxs-lookup"><span data-stu-id="cc3be-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="cc3be-135">A Descoberta Avançada não treinará com base em arquivos ignorados.</span><span class="sxs-lookup"><span data-stu-id="cc3be-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="cc3be-136">Na avaliação, se for difícil dizer se um arquivo é relevante, é melhor marcar como Relevante (R) ou Não Relevante (NR) sempre que possível, em vez de selecionar **Skip**.</span><span class="sxs-lookup"><span data-stu-id="cc3be-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="cc3be-137">Quando a Descoberta Avançada avalia o treinamento, pode-se ver o quão bem esses tipos de arquivos foram processados.</span><span class="sxs-lookup"><span data-stu-id="cc3be-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="cc3be-138">Mesmo arquivos com uma quantidade muito pequena de texto extraído devem ser marcados no treinamento como R/NR, em vez de "Ignorar", quando possível.</span><span class="sxs-lookup"><span data-stu-id="cc3be-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="cc3be-139">A marcação pode afetar o classificador, desde que o arquivo seja acessível e possa ser marcado como R/NR.</span><span class="sxs-lookup"><span data-stu-id="cc3be-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="cc3be-140">O número da sequência de arquivos na lista de arquivos de exemplo exibido na guia **Marca** permite que o usuário retorne à ordem original exibida dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="cc3be-141">Você pode voltar a qualquer exemplo e alterar a marcação dos arquivos do conjunto de avaliação e treinamento.</span><span class="sxs-lookup"><span data-stu-id="cc3be-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="cc3be-142">As alterações serão aplicadas ao criar o próximo exemplo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="cc3be-143">Os arquivos verificados do Excel no formato PDF devem ser tratados da mesma forma que os arquivos nativos do Excel ao marcar arquivos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="cc3be-144">Quando estiver em dúvida sobre a marcação de Relevância de um arquivo, consulte um especialista.</span><span class="sxs-lookup"><span data-stu-id="cc3be-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="cc3be-145">A marcação incorreta durante o treinamento de relevância pode levar a perda de tempo mais tarde no processo e também pode ter um impacto negativo sobre a qualidade dos resultados gerais.</span><span class="sxs-lookup"><span data-stu-id="cc3be-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="cc3be-146">Palavras-chave definidas nas listas de palavras-chave serão exibidas em cores para ajudar o usuário a identificar arquivos relevantes durante a marcação.</span><span class="sxs-lookup"><span data-stu-id="cc3be-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="cc3be-147">**Cálculo em** lote: os arquivos marcados como R/NR pelo especialista receberão uma pontuação de 0 ou 100.</span><span class="sxs-lookup"><span data-stu-id="cc3be-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="cc3be-148">Isso se aplica à marcação feita antes do cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="cc3be-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="cc3be-149">Se o especialista alternou o problema para Ocioso após o Cálculo em Lote e continua marcando esse problema, as pontuações recém-marcadas não serão 100/0, mas sim a pontuação original.</span><span class="sxs-lookup"><span data-stu-id="cc3be-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="cc3be-150">Issues **and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span><span class="sxs-lookup"><span data-stu-id="cc3be-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="cc3be-151">Etapas do treinamento em relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-151">Steps in Relevance training</span></span>

<span data-ttu-id="cc3be-152">Na guia **Controle de \> Relevância,** a Descoberta Avançada fornece recomendações sobre como prosseguir no processamento, com as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="cc3be-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="cc3be-153">As implicações são descritas abaixo quando cada uma das etapas a seguir é recomendada no processo de treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="cc3be-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="cc3be-154">Marcação/ Continuar marcação: Revisão de arquivo e marcação de relevância executadas por um especialista para cada arquivo e problema em um exemplo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="cc3be-155">Implicação: um exemplo existente precisa ser marcado.</span><span class="sxs-lookup"><span data-stu-id="cc3be-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="cc3be-156">Avaliação/continuar avaliação: permite a validação antecipada da relevância do problema de caso e uma visão preliminar da relevância da população de arquivos importada para o caso atual.</span><span class="sxs-lookup"><span data-stu-id="cc3be-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="cc3be-157">Implicação: mais avaliação é necessária ou recomendada.</span><span class="sxs-lookup"><span data-stu-id="cc3be-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="cc3be-158">Treinamento/Continuar treinamento: processo durante o qual a Descoberta Avançada do eDiscovery aprende com o especialista que está marcando os exemplos de arquivo e adquire a capacidade de identificar critérios de relevância pertinentes a cada problema no contexto de cada caso.</span><span class="sxs-lookup"><span data-stu-id="cc3be-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="cc3be-159">Implicação: o problema precisa de mais treinamento; o próximo exemplo deve ser criado e marcado.</span><span class="sxs-lookup"><span data-stu-id="cc3be-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="cc3be-160">Cálculo em lotes: processo de relevância no qual a Descoberta Eletrônico Avançada pega o conhecimento adquirido durante o estágio de treinamento e o aplica a toda a população de arquivos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="cc3be-161">Todos os arquivos no grupo de arquivos pertinentes são avaliados para relevância e atribuídos com uma pontuação de relevância.</span><span class="sxs-lookup"><span data-stu-id="cc3be-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="cc3be-162">Implicação: o problema está estabilizado, e o cálculo em lote pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="cc3be-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="cc3be-163">Catch-up: A relevância indica quando um especialista revisa e marca um exemplo de arquivos selecionados de uma carga de arquivo adicional durante um cenário de Rolagem de Cargas.</span><span class="sxs-lookup"><span data-stu-id="cc3be-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="cc3be-164">Implicação: uma nova carga foi adicionada, e o catch-up é necessário para continuar funcionando.</span><span class="sxs-lookup"><span data-stu-id="cc3be-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="cc3be-165">Inconsistências de marca: o processo identifica, por meio de um algoritmo de Descoberta Avançada, inconsistências no processo de marcação de arquivo que podem afetar negativamente a análise.</span><span class="sxs-lookup"><span data-stu-id="cc3be-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="cc3be-166">Implicação: o próximo exemplo incluirá arquivos que foram marcados em exemplos anteriores, e sua marcação deve ser refeita.</span><span class="sxs-lookup"><span data-stu-id="cc3be-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="cc3be-167">Classificador de atualização: permite que o usuário aplique alterações de marcação ou de complicação.</span><span class="sxs-lookup"><span data-stu-id="cc3be-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="cc3be-168">Implicação: as alterações de marcação e de complicação podem ser aplicadas sem a necessidade de executar manualmente outro exemplo de Relevância.</span><span class="sxs-lookup"><span data-stu-id="cc3be-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="cc3be-169">Em espera: O processo de treinamento de relevância foi concluído.</span><span class="sxs-lookup"><span data-stu-id="cc3be-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="cc3be-170">Implicação: nenhum treinamento de relevância é necessário neste momento.</span><span class="sxs-lookup"><span data-stu-id="cc3be-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="cc3be-171">Embora a Descoberta Avançada o guie pelo processo, com as próximas etapas recomendadas em diferentes estágios, ela também permite navegar entre guias e páginas e fazer escolhas para abordar situações que podem ser pertinentes ao seu processo individual de caso, problema ou revisão de documentos.</span><span class="sxs-lookup"><span data-stu-id="cc3be-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="cc3be-172">É possível aceitar ou substituir as opções de processamento da Próxima etapa da Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="cc3be-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="cc3be-173">Se você deseja executar uma etapa diferente da  próxima etapa recomendada, clique na próxima etapa  listada na exibição do problema expandido na caixa de diálogo, clique no botão Modificar ao lado da próxima etapa e selecione outra opção próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="cc3be-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cc3be-174">Algumas opções podem permanecer desabilitadas após o desbloqueio, pois não há suporte para uso nesse momento no processo.</span><span class="sxs-lookup"><span data-stu-id="cc3be-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="cc3be-175">Mais informações</span><span class="sxs-lookup"><span data-stu-id="cc3be-175">More information</span></span>

[<span data-ttu-id="cc3be-176">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cc3be-177">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="cc3be-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cc3be-178">Treinamento de marcação e relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cc3be-179">Rastreando a análise de relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cc3be-180">Decidir com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="cc3be-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="cc3be-181">Testando a análise de relevância</span><span class="sxs-lookup"><span data-stu-id="cc3be-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="cc3be-182">Consultar os dados em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="cc3be-182">Query the data in a review set</span></span>](review-set-search.md)
