---
title: Marcação e avaliação no Advanced eDiscovery
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
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Revise as etapas para executar o treinamento de Avaliação, incluindo arquivos de marcação e revisão dos resultados da avaliação Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769186"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="13928-103">Marcação e Avaliação no módulo De relevância no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="13928-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="13928-104">Esta seção descreve o procedimento para Avaliação no módulo De relevância no Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="13928-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="13928-105">Realizar treinamento e análise de Avaliação</span><span class="sxs-lookup"><span data-stu-id="13928-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="13928-106">Na guia **Faixa de \> Relevância,** clique em **Avaliação** para iniciar a avaliação de caso.</span><span class="sxs-lookup"><span data-stu-id="13928-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="13928-107">Para fins de exemplo neste procedimento, um conjunto de avaliação de exemplo de 500 arquivos é criado e a guia **Marca** é exibida, que contém o painel De marcação, conteúdo de arquivo exibido e outras opções de marcação.</span><span class="sxs-lookup"><span data-stu-id="13928-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Guia Marca de Relevância para Avaliação](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="13928-109">Revise cada arquivo no exemplo, determine a relevância do arquivo para cada problema de caso e marque o arquivo usando os  botões Relevância (R), Não Relevante (NR) e Ignorar no painel Painel de Marcação.</span><span class="sxs-lookup"><span data-stu-id="13928-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="13928-110">A avaliação requer 500 arquivos marcados.</span><span class="sxs-lookup"><span data-stu-id="13928-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="13928-111">Se os arquivos são "ignorados", você receberá mais arquivos para marcar.</span><span class="sxs-lookup"><span data-stu-id="13928-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="13928-112">Depois de marcar todos os arquivos no exemplo, clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="13928-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="13928-113">A margem de erro e a riqueza atuais  de Avaliação são calculadas e exibidas na guia Faixa de Relevância, com detalhes expandidos por problema, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="13928-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="13928-114">Mais detalhes sobre essa caixa de diálogo são descritos na seção [Revisão dos resultados da avaliação.](#reviewing-assessment-results)</span><span class="sxs-lookup"><span data-stu-id="13928-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Controle de relevância - avaliação](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="13928-116">Por padrão, recomendamos que você prossiga para a próxima etapa padrão quando o indicador de progresso da Avaliação para o problema tiver sido concluído, indicando que o exemplo de avaliação foi revisado e arquivos relevantes suficientes foram marcados.</span><span class="sxs-lookup"><span data-stu-id="13928-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="13928-117">> Caso contrário, se você quiser  exibir os resultados da guia Controlar e  controlar a margem de erro e a próxima etapa, clique em Modificar adjacente à Próxima **Etapa,** selecione **Continuar** avaliação e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13928-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="13928-118">Clique **em Modificar** à direita da caixa de seleção **Avaliação** para exibir e especificar parâmetros de avaliação por problema.</span><span class="sxs-lookup"><span data-stu-id="13928-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="13928-119">Uma **caixa de diálogo Nível** de Avaliação para cada problema é exibida, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="13928-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Problema de caso de nível de avaliação](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="13928-121">Os seguintes parâmetros para o problema são calculados e exibidos na caixa de diálogo **Nível de Avaliação:**</span><span class="sxs-lookup"><span data-stu-id="13928-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="13928-122">**Margem de erro de** destino para estimativas de recall : Com base nesse valor, o número estimado de arquivos adicionais necessários para revisão é calculado.</span><span class="sxs-lookup"><span data-stu-id="13928-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="13928-123">A margem usada para recall é maior do que 75% e com um nível de confiança de 95%.</span><span class="sxs-lookup"><span data-stu-id="13928-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="13928-124">**Arquivos de avaliação adicionais** necessários: indica quantos arquivos mais são necessários se os requisitos atuais da margem de erro não foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="13928-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="13928-125">Para ajustar a margem de erro atual e ver o efeito de diferentes margens de erro (por problema):</span><span class="sxs-lookup"><span data-stu-id="13928-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="13928-126">Na lista **Selecionar problema,** selecione um problema.</span><span class="sxs-lookup"><span data-stu-id="13928-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="13928-127">Em **Margem de erro de destino para estimativas de** recall, insira um novo valor.</span><span class="sxs-lookup"><span data-stu-id="13928-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="13928-128">Clique **em Atualizar valores** para ver o impacto dos ajustes.</span><span class="sxs-lookup"><span data-stu-id="13928-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="13928-129">Clique **em Avançado** na caixa de diálogo Nível de **Avaliação** para ver os seguintes parâmetros e detalhes adicionais:</span><span class="sxs-lookup"><span data-stu-id="13928-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Exibição avançada de problema de caso de nível de avaliação](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="13928-131">**Riqueza estimada**: Riqueza estimada de acordo com os resultados atuais da avaliação</span><span class="sxs-lookup"><span data-stu-id="13928-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="13928-132">**Para recall presumido**: Por padrão, a margem de erro de destino se aplica ao recall acima de 75%.</span><span class="sxs-lookup"><span data-stu-id="13928-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="13928-133">Clique **em Editar** se quiser alterar esse parâmetro e controlar a margem de erro em um intervalo diferente de valores de recall.</span><span class="sxs-lookup"><span data-stu-id="13928-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="13928-134">**Nível de** confiança : Por padrão, a margem de erro recomendada para confiança é de 95%.</span><span class="sxs-lookup"><span data-stu-id="13928-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="13928-135">Clique **em Editar** se quiser alterar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="13928-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="13928-136">**Margem de erro** de riqueza esperada : Considerando os valores atualizados, essa é a margem de erro esperada da riqueza, depois que todos os arquivos de avaliação adicionais são revisados.</span><span class="sxs-lookup"><span data-stu-id="13928-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="13928-137">**Arquivos de avaliação adicionais necessários:** dados os valores atualizados, o número de arquivos de avaliação adicionais que precisam ser revisados para alcançar o destino.</span><span class="sxs-lookup"><span data-stu-id="13928-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="13928-138">**Total de arquivos de avaliação necessários**: Dados os valores atualizados, total de arquivos de avaliação necessários para revisão.</span><span class="sxs-lookup"><span data-stu-id="13928-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="13928-139">**Número esperado de arquivos relevantes** na avaliação : Dado os valores atualizados, o número esperado de arquivos relevantes em toda a avaliação depois que todos os arquivos de avaliação adicionais são revisados.</span><span class="sxs-lookup"><span data-stu-id="13928-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="13928-140">Clique **em Recalcular valores**, se os parâmetros são alterados.</span><span class="sxs-lookup"><span data-stu-id="13928-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="13928-141">Quando terminar, se houver um problema, clique em **OK** para salvar as alterações (ou **Next** quando houver vários problemas para revisar ou modificar e, em seguida, **Concluir**).</span><span class="sxs-lookup"><span data-stu-id="13928-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="13928-142">Quando há vários problemas, depois que todos os problemas foram revisados ou ajustados, um nível de **Avaliação:** a caixa de diálogo resumo é exibida, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="13928-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Resumo do nível de análise](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="13928-144">Após a conclusão bem-sucedida da avaliação, prossiga para o próximo estágio no treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="13928-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="13928-145">Revisão dos resultados da avaliação</span><span class="sxs-lookup"><span data-stu-id="13928-145">Reviewing assessment results</span></span>

<span data-ttu-id="13928-146">Depois que um exemplo de Avaliação é marcado, os resultados da avaliação são calculados e exibidos na guia Faixa de Relevância.</span><span class="sxs-lookup"><span data-stu-id="13928-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="13928-147">Os seguintes resultados são exibidos na exibição Faixa expandida:</span><span class="sxs-lookup"><span data-stu-id="13928-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="13928-148">Margem de erro atual de avaliação para estimativas de recall</span><span class="sxs-lookup"><span data-stu-id="13928-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="13928-149">Riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="13928-149">Estimated richness</span></span>

- <span data-ttu-id="13928-150">Arquivos de avaliação adicionais necessários (para revisão)</span><span class="sxs-lookup"><span data-stu-id="13928-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="13928-151">A margem de erro de Avaliação atual é a margem de erro recomendada por Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="13928-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="13928-152">O número exibido para os "Arquivos de avaliação adicionais necessários" corresponde a essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="13928-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="13928-153">O indicador de progresso da Avaliação mostra o nível de conclusão da avaliação, considerando a margem de erro atual.</span><span class="sxs-lookup"><span data-stu-id="13928-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="13928-154">Quando a avaliação estiver em andamento, o usuário marcará outro exemplo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="13928-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="13928-155">Quando o indicador de progresso da avaliação mostra a avaliação como concluída, isso significa que a revisão de exemplo de avaliação foi concluída e arquivos relevantes suficientes foram marcados.</span><span class="sxs-lookup"><span data-stu-id="13928-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="13928-156">A exibição faixa expandida mostra a próxima etapa recomendada, as estatísticas de avaliação e o acesso a resultados detalhados.</span><span class="sxs-lookup"><span data-stu-id="13928-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="13928-157">Quando a riqueza é muito baixa, o número de arquivos de avaliação adicionais necessários para alcançar um número mínimo de arquivos relevantes para produzir estatísticas úteis é muito alto.</span><span class="sxs-lookup"><span data-stu-id="13928-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="13928-158">Advanced eDiscovery, em seguida, recomendamos passar para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="13928-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="13928-159">O indicador de progresso da avaliação será sombreado e nenhuma estatística estará disponível.</span><span class="sxs-lookup"><span data-stu-id="13928-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="13928-160">Na ausência de estabilização baseada em estatísticas, haverá resultados com um nível mais baixo de precisão e nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="13928-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="13928-161">No entanto, esses resultados podem ser usados para encontrar arquivos relevantes quando você não precisa saber a porcentagem de arquivos relevantes encontrados.</span><span class="sxs-lookup"><span data-stu-id="13928-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="13928-162">Da mesma forma, esse status pode ser usado para treinar problemas com baixa riqueza, onde as pontuações de Relevância podem acelerar o acesso a arquivos relevantes a um problema específico.</span><span class="sxs-lookup"><span data-stu-id="13928-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="13928-163">Na guia **Faixa de \> Relevância,** exibição de problemas expandidos, as seguintes opções de exibição estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="13928-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="13928-164">A próxima etapa recomendada, como Próxima **etapa:** a marcação pode ser  ignorada (por problema) clicando no botão Modificar à direita e selecionando uma etapa diferente na **próxima etapa**.</span><span class="sxs-lookup"><span data-stu-id="13928-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="13928-165">Quando o indicador de progresso da avaliação não for concluído, a avaliação será a próxima opção recomendada, para marcar mais arquivos de avaliação e aumentar a precisão de estatísticas.</span><span class="sxs-lookup"><span data-stu-id="13928-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="13928-166">Você pode alterar a margem de erro e avaliar seu impacto, clicando em **Modificar** e na caixa de diálogo Nível de Avaliação, alterando a margem de erro de destino para **estimativas** de recall e clicando em Atualizar **valores**.</span><span class="sxs-lookup"><span data-stu-id="13928-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="13928-167">Além disso, nesta caixa de diálogo, você pode exibir opções avançadas clicando em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="13928-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="13928-168">Você pode exibir estatísticas adicionais de nível de avaliação e seu impacto clicando em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="13928-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="13928-169">Na caixa de diálogo Resultados de detalhes exibidos, as estatísticas estão disponíveis por problema, quando há pelo menos 500 arquivos de avaliação marcados e pelo menos 18 arquivos são marcados como Relevantes para o problema.</span><span class="sxs-lookup"><span data-stu-id="13928-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
