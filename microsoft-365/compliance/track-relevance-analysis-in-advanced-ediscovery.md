---
title: Rastrear a análise de relevância na descoberta eletrônica avançada do Office 365
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
ms.assetid: 3ab1e2c3-28cf-4bf5-b0a8-c0222f32bdf5
description: 'Saiba como exibir e interpretar os resultados e o status de treinamento de relevância para problemas de caso na descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: 224a817e662462d0c51650e7bd364e717dbfbd62
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069468"
---
# <a name="track-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="aeba5-103">Rastrear a análise de relevância na descoberta eletrônica avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="aeba5-103">Track Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="aeba5-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="aeba5-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="aeba5-106">Na descoberta eletrônica avançada, a guia controle de relevância exibe a validade calculada do treinamento de relevância executado na guia marca e indica a próxima etapa a ser tomada em relevância do processo de treinamento iterativo.</span><span class="sxs-lookup"><span data-stu-id="aeba5-106">In Advanced eDiscovery, the Relevance Track tab displays the calculated validity of the Relevance training performed in the Tag tab and indicates the next step to take in the iterative training process in Relevance.</span></span> 
  
## <a name="tracking-relevance-training-status"></a><span data-ttu-id="aeba5-107">Status de treinamento de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="aeba5-107">Tracking Relevance training status</span></span>

1. <span data-ttu-id="aeba5-108">Exibir os seguintes detalhes no controle de relevância para os problemas de caso, conforme mostrado no exemplo a seguir de uma caixa de diálogo de **nome de problema** abaixo.</span><span class="sxs-lookup"><span data-stu-id="aeba5-108">View the following details in Relevance Track for the case issues, as shown in the following example of an **Issue name** dialog below.</span></span> 
    
  - <span data-ttu-id="aeba5-109">**Avaliação**: Este indicador de progresso mostra a que grau o treinamento de relevância realizado neste ponto atingiu o alvo da avaliação em termos de margem de erro.</span><span class="sxs-lookup"><span data-stu-id="aeba5-109">**Assessment**: This progress indicator shows to what degree the Relevance training performed to this point has achieved the assessment target in terms of margin of error.</span></span> <span data-ttu-id="aeba5-110">A riqueza dos resultados de treinamento de relevância também é exibida.</span><span class="sxs-lookup"><span data-stu-id="aeba5-110">The richness of the Relevance training results is also displayed.</span></span> 
    
  - <span data-ttu-id="aeba5-111">**Treinamento**: Este indicador de progresso por cores e exibição de dica de ferramenta indica a estabilidade dos resultados de treinamento de relevância e uma escala numérica que mostra o número de amostras de treinamento de relevância marcadas para cada problema.</span><span class="sxs-lookup"><span data-stu-id="aeba5-111">**Training**: This color-coded progress indicator and tool-tip display indicates the Relevance training results stability and a numeric scale showing the number of Relevance training samples tagged for each issue.</span></span> <span data-ttu-id="aeba5-112">O especialista monitora o andamento do processo de treinamento de relevância iterativa.</span><span class="sxs-lookup"><span data-stu-id="aeba5-112">The expert monitors the progress of the iterative Relevance training process.</span></span> 
    
  - <span data-ttu-id="aeba5-113">**Cálculo em lote**: Este indicador de progresso fornece informações sobre a conclusão do cálculo em lote.</span><span class="sxs-lookup"><span data-stu-id="aeba5-113">**Batch calculation**: This progress indicator provides information about the completion of Batch calculation.</span></span>
    
  - <span data-ttu-id="aeba5-114">**Próxima etapa**: exibe a recomendação para que a próxima etapa seja executada.</span><span class="sxs-lookup"><span data-stu-id="aeba5-114">**Next step**: Displays the recommendation for the next step to be performed.</span></span> 
    
    <span data-ttu-id="aeba5-115">No exemplo, uma avaliação concluída com êxito para um problema é exibida, indicada pelo indicador de progresso de cor preenchido e pela marca de execução.</span><span class="sxs-lookup"><span data-stu-id="aeba5-115">In the example, a successfully completed Assessment for an issue is shown, indicated by the completed color progress indicator and the checkmark.</span></span> <span data-ttu-id="aeba5-116">A marcação está em andamento, mas o caso ainda é considerado instável (o status de estabilidade também é mostrado em uma dica de ferramenta).</span><span class="sxs-lookup"><span data-stu-id="aeba5-116">Tagging is underway, but the case is still considered unstable (stability status also shown in a tool-tip).</span></span> <span data-ttu-id="aeba5-117">A recomendação de próxima etapa é "treinamento".</span><span class="sxs-lookup"><span data-stu-id="aeba5-117">The next step recommendation is "Training".</span></span> 
    
    ![Etapa 1 do treinamento do Controle de Relevância](../media/a00fe607-680a-48eb-9d61-4565319f7ab6.png)
  
    <span data-ttu-id="aeba5-119">O modo de exibição expandido exibe informações e opções adicionais.</span><span class="sxs-lookup"><span data-stu-id="aeba5-119">The expanded view displays additional information and options.</span></span> <span data-ttu-id="aeba5-120">A margem de erro atual exibida é a margem de erro da recuperação no estado atual de avaliação, dado os arquivos de avaliação existentes (já marcados).</span><span class="sxs-lookup"><span data-stu-id="aeba5-120">The displayed current error margin is the error margin of the recall in the current state of assessment, given the existing (already tagged) assessment files.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="aeba5-121">O estágio de avaliação pode ser ignorado, desmarcando a caixa de seleção de **avaliação** por problema e, em seguida, para "todos os problemas".</span><span class="sxs-lookup"><span data-stu-id="aeba5-121">The Assessment stage can be bypassed by clearing the **Assessment** check box per issue and then for "all issues".</span></span> <span data-ttu-id="aeba5-122">No entanto, como resultado, não haverá estatísticas para esse problema.</span><span class="sxs-lookup"><span data-stu-id="aeba5-122">However, as a result, there will be no statistics for this issue.</span></span> <span data-ttu-id="aeba5-123">> limpar a caixa de seleção de **avaliação** só pode ser feita antes da avaliação ser realizada.</span><span class="sxs-lookup"><span data-stu-id="aeba5-123">> Clearing the **Assessment** check box can only be done before assessment is performed.</span></span> <span data-ttu-id="aeba5-124">Onde houver vários problemas em um caso, a avaliação será ignorada somente se a caixa de seleção estiver desmarcada para cada problema</span><span class="sxs-lookup"><span data-stu-id="aeba5-124">Where multiple issues exist in a case, assessment is bypassed only if the check box is cleared for each issue</span></span> 
  
    <span data-ttu-id="aeba5-125">Quando a avaliação não é concluída com o primeiro conjunto de exemplos de arquivos, a avaliação pode ser a próxima etapa para marcar mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="aeba5-125">When assessment is not completed with the first sample set of files, assessment might be the next step for tagging more files.</span></span> 
    
    <span data-ttu-id="aeba5-126">No \*\*\*\* \> **controle**de relevância, o indicador de progresso de treinamento e a dica de ferramenta indicam o número estimado de amostras adicionais necessárias para alcançar a estabilidade.</span><span class="sxs-lookup"><span data-stu-id="aeba5-126">In **Relevance** \> **Track**, the training progress indicator and tool-tip indicate the estimated number of additional samples needed to reach stability.</span></span> <span data-ttu-id="aeba5-127">Esta estimativa fornece uma diretriz para o treinamento adicional necessário.</span><span class="sxs-lookup"><span data-stu-id="aeba5-127">This estimate provides a guideline for the additional training needed.</span></span>
    
    ![Treinamento do controle de relevância](../media/98dbc3f5-5238-4d73-9f88-1aa4d77ea729.png)
  
2. <span data-ttu-id="aeba5-129">Quando tiver terminado a marcação e se precisar continuar o treinamento, clique em **treinamento**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-129">When you're done tagging and if you need to continue training, click **Training**.</span></span> <span data-ttu-id="aeba5-130">Outro conjunto de exemplos de arquivos é gerado a partir do conjunto de arquivos carregado para obter treinamento adicional.</span><span class="sxs-lookup"><span data-stu-id="aeba5-130">Another sample set of files is generated from the loaded file set for additional training.</span></span> <span data-ttu-id="aeba5-131">Em seguida, você retorna à guia marca para marcar e treinar mais arquivos.</span><span class="sxs-lookup"><span data-stu-id="aeba5-131">You are then returned to the Tag tab to tag and train more files.</span></span>
    
### <a name="reaching-stable-training-levels"></a><span data-ttu-id="aeba5-132">Atingir níveis de treinamento estáveis</span><span class="sxs-lookup"><span data-stu-id="aeba5-132">Reaching stable training levels</span></span>

<span data-ttu-id="aeba5-133">Após os arquivos de avaliação terem alcançado um nível estável de treinamento, a descoberta eletrônica avançada estará pronta para o cálculo em lote.</span><span class="sxs-lookup"><span data-stu-id="aeba5-133">After the assessment files have attained a stable level of training, Advanced eDiscovery is ready for Batch calculation.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aeba5-134">Normalmente, após três amostras de treinamento estáveis, a próxima etapa é "cálculo em lote".</span><span class="sxs-lookup"><span data-stu-id="aeba5-134">Usually, after three stable training samples, the next step is "Batch calculation".</span></span> <span data-ttu-id="aeba5-135">Podem haver exceções, por exemplo, quando houve alterações na marcação de arquivos de exemplos anteriores ou quando os arquivos semente foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="aeba5-135">There may be exceptions, for example, when there were changes to the tagging of files from earlier samples or when seed files were added.</span></span> 
  
### <a name="performing-batch-calculation"></a><span data-ttu-id="aeba5-136">Executando cálculo em lote</span><span class="sxs-lookup"><span data-stu-id="aeba5-136">Performing Batch calculation</span></span>

<span data-ttu-id="aeba5-137">O cálculo de lote é executado como a próxima etapa após o treinamento ter sido concluído com êxito (quando um status de treinamento estável é mostrado pela barra de progresso, uma marca de e o status de estável na ferramenta dica.) O cálculo de lote aplica o conhecimento adquirido durante o treinamento de relevância a todo o preenchimento de arquivo, para avaliar a relevância dos arquivos e para atribuir pontuações de relevância.</span><span class="sxs-lookup"><span data-stu-id="aeba5-137">Batch calculation is executed as the next step after training is successfully completed (when a stable training status is shown by the progress bar, a checkmark and stable status in the tool-tip.) Batch calculation applies the knowledge acquired during the Relevance training to the entire file population, to assess the files' relevance and to assign Relevance scores.</span></span>
  
<span data-ttu-id="aeba5-138">Quando há mais de um problema, o cálculo do lote é feito por questão.</span><span class="sxs-lookup"><span data-stu-id="aeba5-138">When there is more than one issue, Batch calculation is done per issue.</span></span> <span data-ttu-id="aeba5-139">Durante o cálculo do lote, o andamento é monitorado durante o processamento de todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="aeba5-139">During Batch calculation, progress is monitored while processing all of the files.</span></span> 
  
<span data-ttu-id="aeba5-140">Aqui, a próxima etapa recomendada é "nenhum", que indica que nenhum treinamento adicional de relevância iterativa é necessário neste ponto.</span><span class="sxs-lookup"><span data-stu-id="aeba5-140">Here, the recommended next step is "None", which indicates that no additional iterative Relevance training is required at this point.</span></span> <span data-ttu-id="aeba5-141">A fase seguinte é a **de \> relevância-decisão** .</span><span class="sxs-lookup"><span data-stu-id="aeba5-141">The next phase is the **Relevance \> Decide** tab.</span></span> 
  
<span data-ttu-id="aeba5-142">Se você deseja importar novos arquivos após o cálculo de lote, o administrador pode adicionar os arquivos importados a uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="aeba5-142">If you want to import new files after Batch calculation, the administrator can add the imported files to a new load.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aeba5-143">Se você clicar em **Cancelar** durante o cálculo do lote, o processo salvará o que já foi executado.</span><span class="sxs-lookup"><span data-stu-id="aeba5-143">If you click **Cancel** during Batch calculation, the process saves what was already executed.</span></span> <span data-ttu-id="aeba5-144">Se você executar o cálculo em lotes novamente, o processo continuará a partir do último ponto executado.</span><span class="sxs-lookup"><span data-stu-id="aeba5-144">If you run Batch calculation again, the process will continue from the last executed point.</span></span> 
  
### <a name="assessing-tagging-consistency"></a><span data-ttu-id="aeba5-145">Avaliando a consistência de marcação</span><span class="sxs-lookup"><span data-stu-id="aeba5-145">Assessing tagging consistency</span></span>

<span data-ttu-id="aeba5-146">Se houver inconsistências na marcação de arquivos, ela poderá afetar a análise.</span><span class="sxs-lookup"><span data-stu-id="aeba5-146">If there are inconsistencies in file tagging, it can affect the analysis.</span></span> <span data-ttu-id="aeba5-147">O processo de consistência de marcação de descoberta eletrônica avançada pode ser usado quando os resultados não são ideais ou a consistência está em dúvida.</span><span class="sxs-lookup"><span data-stu-id="aeba5-147">The Advanced eDiscovery tagging consistency process can be used when results are not optimal or consistency is in doubt.</span></span> <span data-ttu-id="aeba5-148">Uma lista de possíveis arquivos marcados inconsistentes é retornada, e eles podem ser revisados e remarcados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="aeba5-148">A list of possible inconsistently tagged files is returned, and they can be reviewed and re-tagged, as necessary.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aeba5-149">Após sete ou mais rodadas de treinamento após a avaliação, a consistência de marcação pode ser visualizada no **andamento do treinamento**de **resultados** \> detalhados do **problema** \> de **controle** \> de **relevância** \> .</span><span class="sxs-lookup"><span data-stu-id="aeba5-149">After seven or more training rounds following assessment, tagging consistency can be viewed in **Relevance** \> **Track** \> **Issue** \> **Detailed results** \> **Training progress**.</span></span> <span data-ttu-id="aeba5-150">Essa análise é feita para um problema de cada vez.</span><span class="sxs-lookup"><span data-stu-id="aeba5-150">This review is done for one issue at a time.</span></span> 
  
1. <span data-ttu-id="aeba5-151">No **controle \> de relevância**, expanda a linha de um problema.</span><span class="sxs-lookup"><span data-stu-id="aeba5-151">In **Relevance \> Track**, expand an issue's row.</span></span>
    
2. <span data-ttu-id="aeba5-152">À direita da **próxima etapa**, clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-152">To the right of **Next step**, click **Modify**.</span></span>
    
3. <span data-ttu-id="aeba5-153">Selecione **inconsistências de marca** como a opção **próxima etapa** , após sete amostras de treinamento e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-153">Select **Tag inconsistencies** as the **Next step** option, after seven training samples and click **OK**.</span></span>
    
4. <span data-ttu-id="aeba5-154">Selecione **inconsistências de marca**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-154">Select **Tag inconsistencies**.</span></span> <span data-ttu-id="aeba5-155">A guia **marca** é aberta exibindo uma lista das inconsistências a serem marcadas novamente, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="aeba5-155">The **Tag** tab opens displaying a list of the inconsistencies to re-tag as necessary.</span></span> 
    
5. <span data-ttu-id="aeba5-156">Clique em **calcular** para enviar as alterações.</span><span class="sxs-lookup"><span data-stu-id="aeba5-156">Click **Calculate** to submit the changes.</span></span> <span data-ttu-id="aeba5-157">A próxima etapa após a marcação de inconsistências é "treinamento".</span><span class="sxs-lookup"><span data-stu-id="aeba5-157">The next step after tagging inconsistencies is "Training".</span></span> 
    
## <a name="viewing-and-using-relevance-results"></a><span data-ttu-id="aeba5-158">Exibindo e usando resultados de relevância</span><span class="sxs-lookup"><span data-stu-id="aeba5-158">Viewing and using Relevance results</span></span>

<span data-ttu-id="aeba5-159">Na guia **controle \> de relevância** , expanda a linha de um problema e ao lado de **resultados detalhados**, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-159">In the **Relevance \> Track** tab, expand an issue's row, and next to **Detailed results**, click **View**.</span></span> <span data-ttu-id="aeba5-160">Os painéis de resultados detalhados são exibidos, conforme mostrado e descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="aeba5-160">The Detailed results panes are displayed, as shown and described below.</span></span>
  
![Resultados detalhado do treinamento de relevância](../media/495c04a9-ed1e-4355-8cab-c14270ca2bbb.png)
  
### <a name="tagging-summary"></a><span data-ttu-id="aeba5-162">Resumo de marcação</span><span class="sxs-lookup"><span data-stu-id="aeba5-162">Tagging summary</span></span>

 <span data-ttu-id="aeba5-163">No exemplo mostrado abaixo, o **Resumo de marcação** exibe os totais para cada um dos processos de marcação de avaliação, treinamento e arquivo de verificação.</span><span class="sxs-lookup"><span data-stu-id="aeba5-163">In the example shown below, the **Tagging summary** displays totals for each of Assessment, Training, and Catch-up file tagging processes.</span></span> 
  
![Resumo de marcação de controle de relevância](../media/0ec906fc-bc84-4245-a964-fb3ca37891db.png)
  
### <a name="keywords"></a><span data-ttu-id="aeba5-165">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="aeba5-165">Keywords</span></span>

<span data-ttu-id="aeba5-166">Uma palavra-chave é uma cadeia de caracteres exclusiva, palavra, frase ou sequência de palavras em um arquivo identificado por uma descoberta eletrônica avançada como um indicador significativo do fato de um arquivo ser relevante.</span><span class="sxs-lookup"><span data-stu-id="aeba5-166">A keyword is a unique string, word, phrase, or sequence of words in a file identified by Advanced eDiscovery as a significant indicator of whether a file is relevant.</span></span> <span data-ttu-id="aeba5-167">A palavra-chave "include" da lista de colunas e os pesos em arquivos marcados como relevantes e as colunas "exclude" lista palavras-chave e pesos em arquivos marcados como não relevantes.</span><span class="sxs-lookup"><span data-stu-id="aeba5-167">The "Include" columns list keyword and weights in files tagged as Relevant, and the "Exclude" columns lists keywords and weights in files tagged as Not relevant.</span></span>
  
<span data-ttu-id="aeba5-168">A descoberta eletrônica avançada atribui valores de peso de palavra-chave negativas ou positivos.</span><span class="sxs-lookup"><span data-stu-id="aeba5-168">Advanced eDiscovery assigns negative or positive keyword weight values.</span></span> <span data-ttu-id="aeba5-169">Quanto maior o peso, maior a probabilidade de um arquivo em que a palavra-chave seja exibida é atribuída uma pontuação de relevância maior durante o cálculo do lote.</span><span class="sxs-lookup"><span data-stu-id="aeba5-169">The higher the weight, the higher the likelihood that a file in which the keyword appears is assigned a higher Relevance score during Batch calculation.</span></span> 
  
<span data-ttu-id="aeba5-170">A lista de descoberta eletrônica avançada de palavras-chave pode ser usada para complementar uma lista criada por um especialista ou como uma verificação de sanidade indireta em qualquer ponto do processo de revisão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="aeba5-170">The Advanced eDiscovery list of keywords can be used to supplement a list built by an expert or as an indirect sanity check at any point in the file review process.</span></span>
  
### <a name="training-progress"></a><span data-ttu-id="aeba5-171">Progresso do treinamento</span><span class="sxs-lookup"><span data-stu-id="aeba5-171">Training progress</span></span>

<span data-ttu-id="aeba5-172">O painel **andamento do treinamento** inclui um gráfico de progresso de treinamento e um indicador de qualidade, conforme mostrado no exemplo abaixo.</span><span class="sxs-lookup"><span data-stu-id="aeba5-172">The **Training Progress** pane includes a training progress graph and quality indicator display, as shown in the example below.</span></span> 
  
![Progresso do treinamento do Controle de Relevância](../media/8a5089f5-a162-4246-ae09-bc1921859860.png)
  
 <span data-ttu-id="aeba5-174">**Indicador de qualidade de treinamento**: exibe a classificação da consistência de marcação da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aeba5-174">**Training quality indicator**: Displays the rating of the tagging consistency as follows:</span></span>
  
- <span data-ttu-id="aeba5-175">**Boa**: os arquivos são marcados de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="aeba5-175">**Good**: Files are tagged consistently.</span></span> <span data-ttu-id="aeba5-176">(Luz verde exibida)</span><span class="sxs-lookup"><span data-stu-id="aeba5-176">(Green light displayed)</span></span>
    
- <span data-ttu-id="aeba5-177">**Médio**: alguns arquivos podem ser marcados de forma inconsistente.</span><span class="sxs-lookup"><span data-stu-id="aeba5-177">**Medium**: Some files may be tagged inconsistently.</span></span> <span data-ttu-id="aeba5-178">(Luz amarela exibida)</span><span class="sxs-lookup"><span data-stu-id="aeba5-178">(Yellow light displayed)</span></span>
    
- <span data-ttu-id="aeba5-179">**Aviso**: muitos arquivos podem ser marcados de forma inconsistente.</span><span class="sxs-lookup"><span data-stu-id="aeba5-179">**Warning**: Many files may be tagged inconsistently.</span></span> <span data-ttu-id="aeba5-180">(Luz vermelha exibida)</span><span class="sxs-lookup"><span data-stu-id="aeba5-180">(Red light displayed)</span></span>
    
 <span data-ttu-id="aeba5-181">**Gráfico de progresso do treinamento**: mostra o grau de estabilidade de treinamento de relevância após vários ciclos de treinamento de relevância em comparação ao valor de medida F.</span><span class="sxs-lookup"><span data-stu-id="aeba5-181">**Training progress graph**: Shows the degree of Relevance training stability after a number of Relevance training cycles in comparison to the F-measure value.</span></span> <span data-ttu-id="aeba5-182">À medida que mudamos da esquerda para a direita no gráfico, o intervalo de confiança diminui e é usado, juntamente com a medida F, por uma relevância avançada de descoberta eletrônica para determinar a estabilidade quando os resultados de treinamento de relevância são otimizados.</span><span class="sxs-lookup"><span data-stu-id="aeba5-182">As we move from the left to the right across the graph, the confidence interval narrows and is used, along with the F-measure, by Advanced eDiscovery Relevance to determine stability when the Relevance training results are optimized.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aeba5-183">A relevância usa F2, uma métrica de c-Measure onde a recuperação recebe duas vezes mais peso que a precisão.</span><span class="sxs-lookup"><span data-stu-id="aeba5-183">Relevance uses F2, an F-measure metric where Recall receives twice as much weight as Precision.</span></span> <span data-ttu-id="aeba5-184">Para casos com grande riqueza (mais de 25%), a relevância usa F1 (taxa de 1:1).</span><span class="sxs-lookup"><span data-stu-id="aeba5-184">For cases with high richness (over 25%), Relevance uses F1 (1:1 ratio).</span></span> <span data-ttu-id="aeba5-185">A taxa de medida de F pode ser configurada em **Configurações avançadas**de **configuração** \> de relevância.</span><span class="sxs-lookup"><span data-stu-id="aeba5-185">The F-measure ratio can be configured in **Relevance setup** \> **Advanced settings**.</span></span> 
  
### <a name="batch-calculation-results"></a><span data-ttu-id="aeba5-186">Resultados do cálculo em lote</span><span class="sxs-lookup"><span data-stu-id="aeba5-186">Batch calculation results</span></span>

<span data-ttu-id="aeba5-187">O painel **resultados do cálculo em lotes** inclui o número de arquivos que foram pontuados para fins de relevância da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="aeba5-187">The **Batch calculation results** pane includes the number of files that were scored for Relevance, as follows:</span></span> 
  
- <span data-ttu-id="aeba5-188">**Success**</span><span class="sxs-lookup"><span data-stu-id="aeba5-188">**Success**</span></span>
    
- <span data-ttu-id="aeba5-189">**Vazio**: não contém texto, por exemplo, somente espaços/abas</span><span class="sxs-lookup"><span data-stu-id="aeba5-189">**Empty**: Contains no text, for example, only spaces/tabs</span></span>
    
- <span data-ttu-id="aeba5-190">**Falha**: devido a tamanho excessivo ou não pôde ser lido</span><span class="sxs-lookup"><span data-stu-id="aeba5-190">**Failed**: Due to excessive size or could not be read</span></span>
    
- <span data-ttu-id="aeba5-191">**Ignorado**: devido ao tamanho excessivo</span><span class="sxs-lookup"><span data-stu-id="aeba5-191">**Ignored**: Due to excessive size</span></span>
    
- <span data-ttu-id="aeba5-192">**Nebulous**: contém texto sem sentido ou nenhum recurso relevante para o problema</span><span class="sxs-lookup"><span data-stu-id="aeba5-192">**Nebulous**: Contains meaningless text or no features relevant to the issue</span></span>
    
> [!NOTE]
> <span data-ttu-id="aeba5-193">Empty, Failed, ignored ou nebulous receberá uma pontuação de relevância de-1.</span><span class="sxs-lookup"><span data-stu-id="aeba5-193">Empty, Failed, Ignored, or Nebulous will receive a Relevance score of -1.</span></span> 
  
### <a name="training-statistics"></a><span data-ttu-id="aeba5-194">Estatísticas de treinamento</span><span class="sxs-lookup"><span data-stu-id="aeba5-194">Training statistics</span></span>

<span data-ttu-id="aeba5-195">O painel **Estatísticas de treinamento** exibe as estatísticas e os gráficos com base nos resultados do treinamento de relevância de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="aeba5-195">The **Training statistics** pane displays statistics and graphs based on results from Advanced eDiscovery Relevance training.</span></span> 
  
![Estatística do treinamento do controle de relevância](../media/9a07740e-20d3-49fb-b9b9-84265e0a1836.png)
  
<span data-ttu-id="aeba5-197">Este modo de exibição mostra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aeba5-197">This view shows the following:</span></span>
  
- <span data-ttu-id="aeba5-198">**Taxa de recuperação de revisão**: comparação de resultados de acordo com as pontuações de relevância em uma revisão hipotéticamente linear.</span><span class="sxs-lookup"><span data-stu-id="aeba5-198">**Review-recall ratio**: Comparison of results according to Relevance scores in a hypothetically linear review.</span></span> <span data-ttu-id="aeba5-199">A rechamada é estimada de acordo com o tamanho do conjunto de revisão definido.</span><span class="sxs-lookup"><span data-stu-id="aeba5-199">Recall is estimated given the review set size set.</span></span>
    
- <span data-ttu-id="aeba5-200">**Parâmetros**: estatísticas calculadas cumulativas pertencentes ao conjunto de revisão em relação à população de arquivo para o caso inteiro.</span><span class="sxs-lookup"><span data-stu-id="aeba5-200">**Parameters**: Cumulative calculated statistics pertaining to the review set in relation to the file population for the entire case.</span></span>
    
- <span data-ttu-id="aeba5-201">**Revisão**: porcentagem de arquivos a serem revisados com base nesse corte.</span><span class="sxs-lookup"><span data-stu-id="aeba5-201">**Review**: Percentage of files to review based on this cutoff.</span></span>
    
- <span data-ttu-id="aeba5-202">**Recall**: porcentagem de arquivos relevantes no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="aeba5-202">**Recall**: Percentage of Relevant files in the review set.</span></span> 
    
- <span data-ttu-id="aeba5-203">**Distribuição por Pontuação de relevância**: os arquivos na exibição cinza escuro à esquerda estão abaixo da Pontuação de corte.</span><span class="sxs-lookup"><span data-stu-id="aeba5-203">**Distribution by relevance score**: Files in the dark gray display to the left are below the cutoff score.</span></span> <span data-ttu-id="aeba5-204">Uma dica de ferramenta exibe a pontuação de relevância e a porcentagem relacionada de arquivos no conjunto de arquivos de revisão em relação ao total de arquivos.</span><span class="sxs-lookup"><span data-stu-id="aeba5-204">A tool-tip displays the Relevance score and the related percentage of files in the review file set in relation to the total files.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aeba5-205">Confira também</span><span class="sxs-lookup"><span data-stu-id="aeba5-205">See also</span></span>

[<span data-ttu-id="aeba5-206">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="aeba5-206">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="aeba5-207">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="aeba5-207">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="aeba5-208">Realizando e revisando a avaliação</span><span class="sxs-lookup"><span data-stu-id="aeba5-208">Performing and reviewing Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="aeba5-209">Realizando treinamento de relevância</span><span class="sxs-lookup"><span data-stu-id="aeba5-209">Performing Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="aeba5-210">Tomada de decisões com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="aeba5-210">Making decisions based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="aeba5-211">Testando análise de relevância</span><span class="sxs-lookup"><span data-stu-id="aeba5-211">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

