---
title: Rastrear análise de relevância no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como exibir e interpretar o status e os resultados do treinamento de relevância para problemas de caso Advanced eDiscovery.
ms.openlocfilehash: 224337969b5e662d45c5b804fa5a0ee045f4fb84
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769176"
---
# <a name="track-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="b7a22-103">Rastrear análise de relevância no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="b7a22-103">Track Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="b7a22-104">No Advanced eDiscovery, a guia Faixa de Relevância exibe a validade calculada do treinamento de relevância executado na guia Marca e indica a próxima etapa a ser seguida no processo de treinamento iterativo em Relevância.</span><span class="sxs-lookup"><span data-stu-id="b7a22-104">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="b7a22-105">Status do treinamento de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="b7a22-105">Tracking Relevance training status</span></span>

1. <span data-ttu-id="b7a22-106">Veja os detalhes a seguir em Faixa de Relevância para os problemas de caso, conforme mostrado no exemplo a seguir de uma caixa de diálogo **Nome de** problema abaixo.</span><span class="sxs-lookup"><span data-stu-id="b7a22-106">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span>

   - <span data-ttu-id="b7a22-107">**Avaliação**: esse indicador de progresso mostra até que ponto o treinamento de relevância executado até esse ponto atingiu a meta de avaliação em termos de margem de erro.</span><span class="sxs-lookup"><span data-stu-id="b7a22-107">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="b7a22-108">A riqueza dos resultados do treinamento de relevância também é exibida.</span><span class="sxs-lookup"><span data-stu-id="b7a22-108">The richness of the Relevance training results is also displayed.</span></span>

   - <span data-ttu-id="b7a22-109">**Treinamento**: este indicador de progresso codificado por cores e dica de ferramenta indica a estabilidade dos resultados do treinamento de relevância e uma escala numérica mostrando o número de amostras de treinamento de relevância marcadas para cada problema.</span><span class="sxs-lookup"><span data-stu-id="b7a22-109">**Training**: This color-coded progress indicator and tool-tip indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="b7a22-110">O especialista monitora o andamento do processo de treinamento de relevância iterativa.</span><span class="sxs-lookup"><span data-stu-id="b7a22-110">The expert monitors the progress of the iterative Relevance training process.</span></span> 
  
   - <span data-ttu-id="b7a22-111">**Cálculo em lotes**: Este indicador de progresso fornece informações sobre a conclusão do cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="b7a22-111">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
  
   - <span data-ttu-id="b7a22-112">**Próxima etapa**: Exibe a recomendação para a próxima etapa a ser executada.</span><span class="sxs-lookup"><span data-stu-id="b7a22-112">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
  
    <span data-ttu-id="b7a22-113">No exemplo, uma Avaliação concluída com êxito para um problema é mostrada, indicada pelo indicador de progresso de cores concluído e pela marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="b7a22-113">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="b7a22-114">A marcação está em andamento, mas o caso ainda é considerado instável (status de estabilidade também mostrado em uma dica de ferramenta).</span><span class="sxs-lookup"><span data-stu-id="b7a22-114">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="b7a22-115">A recomendação da próxima etapa é "Treinamento".</span><span class="sxs-lookup"><span data-stu-id="b7a22-115">The next step recommendation is "Training".</span></span> 
  
    ![Etapa 1 do treinamento do Controle de Relevância](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="b7a22-117">O visor expandido exibe informações e opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="b7a22-117">The expanded view displays additional information and options.</span></span> <span data-ttu-id="b7a22-118">A margem de erro atual exibida é a margem de erro do recall no estado atual da avaliação, considerando os arquivos de avaliação existentes (já marcados).</span><span class="sxs-lookup"><span data-stu-id="b7a22-118">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="b7a22-119">O estágio de Avaliação pode ser ignorado limpando a caixa de seleção **Avaliação** por problema e, em seguida, para "todos os problemas".</span><span class="sxs-lookup"><span data-stu-id="b7a22-119">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="b7a22-120">No entanto, como resultado, não haverá estatísticas para esse problema.</span><span class="sxs-lookup"><span data-stu-id="b7a22-120">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="b7a22-121">> a caixa de seleção **Limpar** a Avaliação só pode ser feita antes que a avaliação seja realizada.</span><span class="sxs-lookup"><span data-stu-id="b7a22-121">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="b7a22-122">Onde existem vários problemas em um caso, a avaliação é ignorada somente se a caixa de seleção for desapurada para cada problema</span><span class="sxs-lookup"><span data-stu-id="b7a22-122">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="b7a22-123">Quando a avaliação não é concluída com o primeiro conjunto de exemplos de arquivos, a avaliação pode ser a próxima etapa para marcar mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="b7a22-123">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span>
  
    <span data-ttu-id="b7a22-124">Em **Faixa de Relevância** , o indicador de progresso de treinamento e a dica de ferramenta indicam o número estimado de amostras adicionais \> necessárias para alcançar a estabilidade.</span><span class="sxs-lookup"><span data-stu-id="b7a22-124">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="b7a22-125">Essa estimativa fornece uma diretriz para o treinamento adicional necessário.</span><span class="sxs-lookup"><span data-stu-id="b7a22-125">This estimate provides a guideline for the additional training needed.</span></span>
  
    ![Treinamento do controle de relevância](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="b7a22-127">Quando terminar a marcação e se precisar continuar o treinamento, clique em **Treinamento**.</span><span class="sxs-lookup"><span data-stu-id="b7a22-127">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="b7a22-128">Outro conjunto de exemplos de arquivos é gerado a partir do conjunto de arquivos carregados para treinamento adicional.</span><span class="sxs-lookup"><span data-stu-id="b7a22-128">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="b7a22-129">Em seguida, você é retornado para a guia Marca para marcar e treinar mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="b7a22-129">You are then returned to the Tag tab to tag and train more files.</span></span>

### <a name="reaching-stable-training-levels"></a><span data-ttu-id="b7a22-130">Atingir níveis de treinamento estáveis</span><span class="sxs-lookup"><span data-stu-id="b7a22-130">Reaching stable training levels</span></span>

<span data-ttu-id="b7a22-131">Depois que os arquivos de avaliação atingirem um nível estável de treinamento, Advanced eDiscovery estará pronto para cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="b7a22-131">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7a22-132">Normalmente, após três exemplos de treinamento estáveis, a próxima etapa é "Cálculo em lotes".</span><span class="sxs-lookup"><span data-stu-id="b7a22-132">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="b7a22-133">Pode haver exceções, por exemplo, quando houve alterações na marcação de arquivos de exemplos anteriores ou quando arquivos de semente foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="b7a22-133">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="b7a22-134">Executando cálculo em lotes</span><span class="sxs-lookup"><span data-stu-id="b7a22-134">Performing Batch calculation</span></span>

<span data-ttu-id="b7a22-135">O cálculo em lotes é executado como a próxima etapa após a conclusão do treinamento com êxito (quando um status de treinamento estável é mostrado pela barra de progresso, uma marca de seleção e um status estável na dica de ferramenta.) O cálculo em lotes aplica o conhecimento adquirido durante o treinamento de relevância para toda a população de arquivos, para avaliar a relevância dos arquivos e atribuir pontuações de relevância.</span><span class="sxs-lookup"><span data-stu-id="b7a22-135">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="b7a22-136">Quando há mais de um problema, o cálculo em lotes é feito por problema.</span><span class="sxs-lookup"><span data-stu-id="b7a22-136">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="b7a22-137">Durante o cálculo em lote, o andamento é monitorado durante o processamento de todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="b7a22-137">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="b7a22-138">Aqui, a próxima etapa recomendada é "None", que indica que nenhum treinamento adicional de Relevância Iterativa é necessário neste ponto.</span><span class="sxs-lookup"><span data-stu-id="b7a22-138">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="b7a22-139">A próxima fase é **a guia Decidir \> relevância.**</span><span class="sxs-lookup"><span data-stu-id="b7a22-139">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="b7a22-140">Se você quiser importar novos arquivos após o cálculo em lotes, o administrador poderá adicionar os arquivos importados a uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="b7a22-140">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7a22-141">Se você clicar em **Cancelar** durante o cálculo em lote, o processo salvará o que já foi executado.</span><span class="sxs-lookup"><span data-stu-id="b7a22-141">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="b7a22-142">Se você executar o cálculo em lote novamente, o processo continuará a partir do último ponto executado.</span><span class="sxs-lookup"><span data-stu-id="b7a22-142">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="b7a22-143">Avaliando a consistência de marcação</span><span class="sxs-lookup"><span data-stu-id="b7a22-143">Assessing tagging consistency</span></span>

<span data-ttu-id="b7a22-144">Se houver inconsistências na marcação de arquivo, isso pode afetar a análise.</span><span class="sxs-lookup"><span data-stu-id="b7a22-144">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="b7a22-145">O Advanced eDiscovery de consistência de marcação pode ser usado quando os resultados não são ideais ou a consistência está em dúvida.</span><span class="sxs-lookup"><span data-stu-id="b7a22-145">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="b7a22-146">Uma lista de possíveis arquivos marcados de forma inconsistente é retornada e eles podem ser revisados e retomados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b7a22-146">A list of possible inconsistently tagged files is returned, and they can be reviewed and retagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7a22-147">Após sete ou mais rodadas de treinamento após a avaliação, a consistência de marcação pode ser exibida em **Problemas** de Faixa de Relevância \>  \>  \> **Resultados detalhados** \> **Andamento do treinamento.**</span><span class="sxs-lookup"><span data-stu-id="b7a22-147">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="b7a22-148">Esta revisão é feita para um problema de cada vez.</span><span class="sxs-lookup"><span data-stu-id="b7a22-148">This review is done for one issue at a time.</span></span>
  
1. <span data-ttu-id="b7a22-149">Em **Faixa de \> Relevância,** expanda a linha de um problema.</span><span class="sxs-lookup"><span data-stu-id="b7a22-149">In **Relevance \> Track**, expand an issue's row.</span></span>
  
2. <span data-ttu-id="b7a22-150">À direita da **próxima etapa,** clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="b7a22-150">To the right of **Next step**, click **Modify**.</span></span>
  
3. <span data-ttu-id="b7a22-151">Selecione **Marca inconsistências** como **a opção Próxima etapa,** após sete exemplos de treinamento e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7a22-151">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
  
4. <span data-ttu-id="b7a22-152">Selecione **Inconsistências de marca**.</span><span class="sxs-lookup"><span data-stu-id="b7a22-152">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="b7a22-153">A **guia Marca** é aberta exibindo uma lista das inconsistências a ser retag, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b7a22-153">The **Tag** tab opens displaying a list of the inconsistencies to retag as necessary.</span></span>
  
5. <span data-ttu-id="b7a22-154">Clique **em Calcular** para enviar as alterações.</span><span class="sxs-lookup"><span data-stu-id="b7a22-154">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="b7a22-155">A próxima etapa após a marcação de inconsistências é "Treinamento".</span><span class="sxs-lookup"><span data-stu-id="b7a22-155">The next step after tagging inconsistencies is "Training".</span></span> 
  
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="b7a22-156">Exibindo e usando resultados de relevância</span><span class="sxs-lookup"><span data-stu-id="b7a22-156">Viewing and using Relevance results</span></span>

<span data-ttu-id="b7a22-157">Na guia **Faixa de \> Relevância,** expanda a linha de um problema e, ao lado de **Resultados** detalhados, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b7a22-157">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="b7a22-158">Os painéis de resultados detalhados são exibidos, conforme mostrado e descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="b7a22-158">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Resultados detalhado do treinamento de relevância](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="b7a22-160">Resumo de marcação</span><span class="sxs-lookup"><span data-stu-id="b7a22-160">Tagging summary</span></span>

 <span data-ttu-id="b7a22-161">No exemplo mostrado abaixo, o resumo **de Marcação** exibe totais para cada um dos processos de marcação de arquivo de Avaliação, Treinamento e Captura.</span><span class="sxs-lookup"><span data-stu-id="b7a22-161">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span>
  
![Resumo de marcação de controle de relevância](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="b7a22-163">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="b7a22-163">Keywords</span></span>

<span data-ttu-id="b7a22-164">Uma palavra-chave é uma cadeia de caracteres, palavra, frase ou sequência exclusiva de palavras em um arquivo identificado Advanced eDiscovery como um indicador significativo de se um arquivo é relevante.</span><span class="sxs-lookup"><span data-stu-id="b7a22-164">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="b7a22-165">As colunas "Incluir" listam palavras-chave e pesos em arquivos marcados como Relevantes, e as colunas "Excluir" listam palavras-chave e pesos em arquivos marcados como Não relevantes.</span><span class="sxs-lookup"><span data-stu-id="b7a22-165">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="b7a22-166">Advanced eDiscovery atribui valores de peso de palavra-chave negativos ou positivos.</span><span class="sxs-lookup"><span data-stu-id="b7a22-166">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="b7a22-167">Quanto maior o peso, maior será a probabilidade de que um arquivo no qual a palavra-chave apareça tenha uma pontuação de Relevância mais alta durante o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="b7a22-167">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span>
  
<span data-ttu-id="b7a22-168">A Advanced eDiscovery de palavras-chave pode ser usada para complementar uma lista criada por um especialista ou como uma verificação de sanidade indireta em qualquer ponto do processo de revisão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7a22-168">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="b7a22-169">Progresso do treinamento</span><span class="sxs-lookup"><span data-stu-id="b7a22-169">Training progress</span></span>

<span data-ttu-id="b7a22-170">O **painel Progresso do** Treinamento inclui um gráfico de progresso de treinamento e uma exibição de indicador de qualidade, conforme mostrado no exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="b7a22-170">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span>
  
![Progresso do treinamento do Controle de Relevância](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
<span data-ttu-id="b7a22-172">**Indicador de qualidade de** treinamento : exibe a classificação da consistência de marcação da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b7a22-172">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="b7a22-173">**Bom:** os arquivos são marcados de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="b7a22-173">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="b7a22-174">(Luz verde exibida)</span><span class="sxs-lookup"><span data-stu-id="b7a22-174">(Green light displayed)</span></span>
  
- <span data-ttu-id="b7a22-175">**Médio**: Alguns arquivos podem ser marcados inconsistentemente.</span><span class="sxs-lookup"><span data-stu-id="b7a22-175">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="b7a22-176">(Luz amarela exibida)</span><span class="sxs-lookup"><span data-stu-id="b7a22-176">(Yellow light displayed)</span></span>

- <span data-ttu-id="b7a22-177">**Aviso:** muitos arquivos podem ser marcados de forma inconsistente.</span><span class="sxs-lookup"><span data-stu-id="b7a22-177">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="b7a22-178">(Luz vermelha exibida)</span><span class="sxs-lookup"><span data-stu-id="b7a22-178">(Red light displayed)</span></span>

<span data-ttu-id="b7a22-179">**Gráfico de progresso do** treinamento : mostra o grau de estabilidade do treinamento de relevância após muitos ciclos de treinamento de relevância em comparação com o valor da medida F.</span><span class="sxs-lookup"><span data-stu-id="b7a22-179">**Training progress graph**: Shows the degree of Relevance training stability after many Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="b7a22-180">À medida que movemos da esquerda para a direita no gráfico, o intervalo de confiança estreita e é usado, juntamente com a medida F, pela relevância Advanced eDiscovery para determinar a estabilidade quando os resultados do treinamento de relevância são otimizados.</span><span class="sxs-lookup"><span data-stu-id="b7a22-180">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7a22-181">A relevância usa F2, uma métrica de medida F em que Recall recebe duas vezes mais peso que Precision.</span><span class="sxs-lookup"><span data-stu-id="b7a22-181">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="b7a22-182">Para casos com alta riqueza (mais de 25%), a Relevância usa F1 (taxa de 1:1).</span><span class="sxs-lookup"><span data-stu-id="b7a22-182">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="b7a22-183">A taxa de medida F pode ser configurada em **Configurações avançadas** de configuração \> **de relevância.**</span><span class="sxs-lookup"><span data-stu-id="b7a22-183">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span>
  
### <a name="batch-calculation-results"></a><span data-ttu-id="b7a22-184">Resultados do cálculo em lotes</span><span class="sxs-lookup"><span data-stu-id="b7a22-184">Batch calculation results</span></span>

<span data-ttu-id="b7a22-185">O **painel de resultados de** cálculo em lotes inclui o número de arquivos que foram marcados para Relevância, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b7a22-185">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="b7a22-186">**Success**</span><span class="sxs-lookup"><span data-stu-id="b7a22-186">**Success**</span></span>
  
- <span data-ttu-id="b7a22-187">**Vazio**: não contém texto, por exemplo, somente espaços/guias</span><span class="sxs-lookup"><span data-stu-id="b7a22-187">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
  
- <span data-ttu-id="b7a22-188">**Falha**: devido ao tamanho excessivo ou não pôde ser lido</span><span class="sxs-lookup"><span data-stu-id="b7a22-188">**Failed**: Due to excessive size or could not be read</span></span>
  
- <span data-ttu-id="b7a22-189">**Ignorado :** devido ao tamanho excessivo</span><span class="sxs-lookup"><span data-stu-id="b7a22-189">**Ignored**: Due to excessive size</span></span>
  
- <span data-ttu-id="b7a22-190">**Nebulous**: contém texto sem sentido ou nenhum recursos relevantes para o problema</span><span class="sxs-lookup"><span data-stu-id="b7a22-190">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7a22-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span><span class="sxs-lookup"><span data-stu-id="b7a22-191">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span>
  
### <a name="training-statistics"></a><span data-ttu-id="b7a22-192">Estatísticas de treinamento</span><span class="sxs-lookup"><span data-stu-id="b7a22-192">Training statistics</span></span>

<span data-ttu-id="b7a22-193">O **painel Estatísticas de** treinamento exibe estatísticas e gráficos com base nos resultados Advanced eDiscovery treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="b7a22-193">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Estatística do treinamento do controle de relevância](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="b7a22-195">Esta exibição mostra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7a22-195">This view shows the following:</span></span>
  
- <span data-ttu-id="b7a22-196">**Taxa de reavaliação-recall**: comparação de resultados de acordo com as pontuações de relevância em uma revisão hipoteticamente linear.</span><span class="sxs-lookup"><span data-stu-id="b7a22-196">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="b7a22-197">O recall é estimado devido ao conjunto de tamanhos do conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="b7a22-197">Recall is estimated given the review set size set.</span></span>
  
- <span data-ttu-id="b7a22-198">**Parâmetros**: Estatísticas calculadas cumulativas referentes ao conjunto de revisão em relação à população de arquivos para todo o caso.</span><span class="sxs-lookup"><span data-stu-id="b7a22-198">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
  
- <span data-ttu-id="b7a22-199">**Revisão**: Porcentagem de arquivos a analisar com base nesse recorte.</span><span class="sxs-lookup"><span data-stu-id="b7a22-199">**Review**: Percentage of files to review based on this cutoff.</span></span>
  
- <span data-ttu-id="b7a22-200">**Recall**: Porcentagem de arquivos relevantes no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="b7a22-200">**Recall**: Percentage of Relevant files in the review set.</span></span> 
  
- <span data-ttu-id="b7a22-201">**Distribuição por pontuação de relevância:** Os arquivos na exibição cinza escuro à esquerda estão abaixo da pontuação de recorte.</span><span class="sxs-lookup"><span data-stu-id="b7a22-201">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="b7a22-202">Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b7a22-202">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
