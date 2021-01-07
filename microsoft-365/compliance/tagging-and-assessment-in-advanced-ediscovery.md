---
title: Marcação e avaliação na descoberta eletrônica avançada
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
description: Revise as etapas para executar o treinamento de avaliação, incluindo arquivos de marcação e revisar os resultados da avaliação na descoberta eletrônica avançada.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769186"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a><span data-ttu-id="0ea6a-103">Marcação e avaliação no módulo de relevância na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="0ea6a-103">Tagging and Assessment in the Relevance module in Advanced eDiscovery</span></span>
  
<span data-ttu-id="0ea6a-104">Esta seção descreve o procedimento de avaliação no módulo de relevância na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-104">This section describes the procedure for Assessment in the Relevance module in Advanced eDiscovery.</span></span>
  
## <a name="performing-assessment-training-and-analysis"></a><span data-ttu-id="0ea6a-105">Realizando treinamento e análise de avaliação</span><span class="sxs-lookup"><span data-stu-id="0ea6a-105">Performing Assessment training and analysis</span></span>

1. <span data-ttu-id="0ea6a-106">Na guia **\> controle de relevância** , clique em **avaliação** para iniciar a avaliação de caso.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-106">In the **Relevance \> Track** tab, click **Assessment** to start case assessment.</span></span>

    <span data-ttu-id="0ea6a-107">Por exemplo, neste procedimento, um conjunto de avaliação de amostra de 500 arquivos é criado e a guia **marca** é exibida, que contém o painel de marcação, o conteúdo do arquivo exibido e outras opções de marcação.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-107">For example purposes in this procedure, a sample assessment set of 500 files is created and the **Tag** tab is displayed, which contains the Tagging panel, displayed file content and other tagging options.</span></span> 

    ![Guia Marca de Relevância para Avaliação](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. <span data-ttu-id="0ea6a-109">Revise cada arquivo no exemplo, determine a relevância do arquivo para cada problema de caso e marque o arquivo usando os botões relevância (R), não relevante (NR) e pular no painel **painel de marcação** .</span><span class="sxs-lookup"><span data-stu-id="0ea6a-109">Review each file in the sample, determine the file's relevance for each case issue, and tag the file using the Relevance (R), Not relevant (NR) and Skip buttons in the **Tagging panel** pane.</span></span> 

    > [!NOTE]
    >  <span data-ttu-id="0ea6a-110">A avaliação requer arquivos marcados 500.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-110">Assessment requires 500 tagged files.</span></span> <span data-ttu-id="0ea6a-111">Se os arquivos forem "ignorados", você receberá mais arquivos para marcá-los.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-111">If files are "skipped", you will receive more files to tag.</span></span> 
  
3. <span data-ttu-id="0ea6a-112">Depois de marcar todos os arquivos no exemplo, clique em **calcular**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-112">After tagging all files in the sample, click **Calculate**.</span></span>

    <span data-ttu-id="0ea6a-113">A margem de erro atual de avaliação e a riqueza são calculadas e exibidas na guia **controle de relevância** , com detalhes expandidos por problema, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-113">The Assessment current error margin and richness are calculated and displayed in the **Relevance Track** tab, with expanded details per issue, as shown below.</span></span> <span data-ttu-id="0ea6a-114">Mais detalhes sobre esta caixa de diálogo são descritos na seção [revisando resultados da avaliação](#reviewing-assessment-results) .</span><span class="sxs-lookup"><span data-stu-id="0ea6a-114">More details about this dialog are described in the [Reviewing assessment results](#reviewing-assessment-results) section.</span></span>

    ![Controle de relevância - avaliação](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > <span data-ttu-id="0ea6a-116">Por padrão, recomendamos que você prossiga para a próxima etapa padrão quando o indicador de progresso da avaliação do problema tiver sido concluído, indicando que o exemplo de avaliação foi revisado e que os arquivos relevantes suficientes foram marcados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-116">By default, we recommend that you proceed to the default Next step when the Assessment progress indicator for the issue has completed, indicating that the assessment sample was reviewed and sufficient relevant files were tagged.</span></span> <span data-ttu-id="0ea6a-117">> caso contrário, se você quiser exibir os resultados da guia **rastrear** e controlar a margem de erro e a próxima etapa, clique em **Modificar** adjacente à **próxima etapa**, selecione **continuar avaliação** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-117">> Otherwise, if you want to view the **Track** tab results and control the margin of error and the next step, click **Modify** adjacent to **Next Step**, select **Continue assessment**, and then click **OK**.</span></span>
  
4. <span data-ttu-id="0ea6a-118">Clique em **Modificar** à direita da caixa de seleção de **avaliação** para exibir e especificar os parâmetros de avaliação por problema.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-118">Click **Modify** to the right of the **Assessment** check box to view and specify assessment parameters per issue.</span></span> <span data-ttu-id="0ea6a-119">Uma caixa de diálogo de **nível de avaliação** para cada problema é exibida, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0ea6a-119">An **Assessment level** dialog for each issue is displayed, as shown in the following example:</span></span> 

    ![Problema de caso de nível de avaliação](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    <span data-ttu-id="0ea6a-121">Os seguintes parâmetros para o problema são calculados e exibidos na caixa de diálogo **nível de avaliação** :</span><span class="sxs-lookup"><span data-stu-id="0ea6a-121">The following parameters for the issue are calculated and displayed in the **Assessment level** dialog:</span></span> 

    <span data-ttu-id="0ea6a-122">**Margem de erro de destino para estimativas de cancelamento**: com base nesse valor, o número estimado de arquivos adicionais necessários para a revisão é calculado.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-122">**Target error margin for recall estimates**: Based on this value, the estimated number of additional files necessary to review is calculated.</span></span> <span data-ttu-id="0ea6a-123">A margem usada para a recuperação é maior que 75% e com um nível de confiança 95%.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-123">The margin used for recall is greater than 75% and with a 95% confidence level.</span></span>

    <span data-ttu-id="0ea6a-124">**Arquivos de avaliação adicionais necessários**: indica o número de arquivos necessários se os requisitos da margem de erro atual não tiverem sido atendidos.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-124">**Additional assessment files required**: Indicates how many more files are necessary if the current error margin's requirements have not been met.</span></span> 

5. <span data-ttu-id="0ea6a-125">Para ajustar a margem de erro atual e ver o efeito de diferentes margens de erro (por problema):</span><span class="sxs-lookup"><span data-stu-id="0ea6a-125">To adjust the current error margin and see the effect of different error margins (per issue):</span></span>

6. <span data-ttu-id="0ea6a-126">Na lista **selecionar problema** , selecione um problema.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-126">In the **Select issue** list, select an issue.</span></span> 

7. <span data-ttu-id="0ea6a-127">Em **margem de erro de destino para estimativas de cancelamento**, insira um novo valor.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-127">In **Target error margin for recall estimates**, enter a new value.</span></span>

8. <span data-ttu-id="0ea6a-128">Clique em **atualizar valores** para ver o impacto dos ajustes.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-128">Click **Update values** to see the impact of the adjustments.</span></span> 

9. <span data-ttu-id="0ea6a-129">Clique em **avançado** na caixa de diálogo **nível de avaliação** para ver os seguintes parâmetros e detalhes adicionais:</span><span class="sxs-lookup"><span data-stu-id="0ea6a-129">Click **Advanced** in the **Assessment level** dialog to see the following additional parameters and details:</span></span> 

    ![Exibição avançada de problema de caso de nível de avaliação](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - <span data-ttu-id="0ea6a-131">**Riqueza estimada**: riqueza estimada de acordo com os resultados da avaliação atual</span><span class="sxs-lookup"><span data-stu-id="0ea6a-131">**Estimated richness**: Estimated richness according to the current assessment results</span></span>

    - <span data-ttu-id="0ea6a-132">**Para recalls presumidos**: por padrão, a margem de erro de destino se aplica à recuperação acima de 75%.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-132">**For assumed recall**: By default, the target error margin applies to recall above 75%.</span></span> <span data-ttu-id="0ea6a-133">Clique em **Editar** se quiser alterar esse parâmetro e controlar a margem de erro em um intervalo diferente de valores de recuperação.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-133">Click **Edit** if you want to change this parameter and control the margin of error on a different range of recall values.</span></span> 

    - <span data-ttu-id="0ea6a-134">**Nível de confiança**: por padrão, a margem de erro recomendada para confiança é de 95%.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-134">**Confidence level**: By default, the recommended error margin for confidence is 95%.</span></span> <span data-ttu-id="0ea6a-135">Clique em **Editar** se quiser alterar esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-135">Click **Edit** if you want to change this parameter.</span></span>

    - <span data-ttu-id="0ea6a-136">**Margem de erro de riqueza esperada**: dado os valores atualizados, esta é a margem esperada de erro da riqueza, após todos os arquivos de avaliação adicionais serem revisados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-136">**Expected richness error margin**: Given the updated values, this is the expected margin of error of the richness, after all additional assessment files are reviewed.</span></span>

    - <span data-ttu-id="0ea6a-137">**Arquivos de avaliação adicionais necessários**: dado os valores atualizados, o número de arquivos de avaliação adicionais que precisam ser revisados para chegar ao destino.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-137">**Additional assessment files required**: Given the updated values, the number of additional assessment files that need to be reviewed to reach the target.</span></span>

    - <span data-ttu-id="0ea6a-138">**Total de arquivos de avaliação necessários**: dado os valores atualizados, os arquivos de avaliação total necessários para análise.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-138">**Total assessment files required**: Given the updated values, total assessment files required for review.</span></span>

    - <span data-ttu-id="0ea6a-139">**Número esperado de arquivos relevantes na avaliação**: dado os valores atualizados, o número esperado de arquivos relevantes em toda a avaliação após todos os arquivos de avaliação adicionais serem analisados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-139">**Expected number of relevant files in assessment**: Given the updated values, the expected number of relevant files in the entire assessment after all additional assessment files are reviewed.</span></span>

10. <span data-ttu-id="0ea6a-140">Clique em **Recalcular valores**, se os parâmetros forem alterados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-140">Click **Recalculate values**, if parameters are changed.</span></span> <span data-ttu-id="0ea6a-141">Quando você terminar, se houver um problema, clique em **OK** para salvar as alterações (ou **ao avançar** quando houver vários problemas para revisar ou modificar e depois **concluir**).</span><span class="sxs-lookup"><span data-stu-id="0ea6a-141">When you're done, if there is one issue, click **OK** to save the changes (or **Next** when there are multiple issues to review or modify and then **Finish**).</span></span> 

    <span data-ttu-id="0ea6a-142">Quando há vários problemas, após todos os problemas terem sido revisados ou ajustados, um **nível de avaliação: Resumo** é exibido, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-142">When there are multiple issues, after all issues have been reviewed or adjusted, an **Assessment level: summary** dialog is displayed, as shown in the following example.</span></span> 

    ![Resumo do nível de análise](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    <span data-ttu-id="0ea6a-144">Após a conclusão bem-sucedida da avaliação, prossiga para o próximo estágio no treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-144">On successful completion of assessment, proceed to the next stage in Relevance training.</span></span>

## <a name="reviewing-assessment-results"></a><span data-ttu-id="0ea6a-145">Analisar resultados da avaliação</span><span class="sxs-lookup"><span data-stu-id="0ea6a-145">Reviewing assessment results</span></span>

<span data-ttu-id="0ea6a-146">Depois que um exemplo de avaliação é marcado, os resultados da avaliação são calculados e exibidos na guia controle de relevância.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-146">After an Assessment sample is tagged, the assessment results are calculated and displayed in the Relevance Track tab.</span></span>
  
<span data-ttu-id="0ea6a-147">Os resultados a seguir são exibidos na exibição de faixa expandida:</span><span class="sxs-lookup"><span data-stu-id="0ea6a-147">The following results are displayed in the expanded Track display:</span></span>
  
- <span data-ttu-id="0ea6a-148">Margem de erro atual de avaliação para estimativas de cancelamento</span><span class="sxs-lookup"><span data-stu-id="0ea6a-148">Assessment current error margin for recall estimates</span></span>

- <span data-ttu-id="0ea6a-149">Riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="0ea6a-149">Estimated richness</span></span>

- <span data-ttu-id="0ea6a-150">Arquivos de avaliação adicionais necessários (para revisão)</span><span class="sxs-lookup"><span data-stu-id="0ea6a-150">Additional assessment files required (for review)</span></span>

<span data-ttu-id="0ea6a-151">A margem de erro atual da avaliação é a margem de erro recomendada pela descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-151">The Assessment current error margin is the error margin recommended by Advanced eDiscovery.</span></span> <span data-ttu-id="0ea6a-152">O número exibido para os "arquivos de avaliação adicionais necessários" corresponde a essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-152">The number displayed for the "Additional assessment files required" corresponds to that recommendation.</span></span>
  
<span data-ttu-id="0ea6a-153">O indicador de progresso da avaliação mostra o nível de conclusão da avaliação, considerando a margem de erro atual.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-153">The Assessment progress indicator shows the level of completion of the assessment, given the current error margin.</span></span> <span data-ttu-id="0ea6a-154">Quando a avaliação estiver em andamento, o usuário marcará outro exemplo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-154">When assessment is underway, the user will tag another assessment sample.</span></span>
  
<span data-ttu-id="0ea6a-155">Quando o indicador de progresso da avaliação mostrar a avaliação como concluída, isso significa que a análise da amostra de avaliação foi concluída e os arquivos relevantes suficientes foram marcados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-155">When the assessment progress indicator shows assessment as complete, that means the assessment sample review was completed and sufficient relevant files were tagged.</span></span> 
  
<span data-ttu-id="0ea6a-156">A exibição de faixa expandida mostra a próxima etapa recomendada, as estatísticas de avaliação e o acesso aos resultados detalhados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-156">The expanded Track display shows the recommended next step, the assessment statistics, and access to detailed results.</span></span>
  
<span data-ttu-id="0ea6a-157">Quando a riqueza é muito baixa, o número de arquivos de avaliação adicionais necessários para atingir um número mínimo de arquivos relevantes para produzir estatísticas úteis é muito alto.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-157">When richness is very low, the number of additional assessment files needed to reach a minimal number of relevant files to produce useful statistics is very high.</span></span> <span data-ttu-id="0ea6a-158">A descoberta eletrônica avançada recomendará a migração para o treinamento.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-158">Advanced eDiscovery will then recommend moving on to training.</span></span> <span data-ttu-id="0ea6a-159">O indicador de progresso da avaliação será sombreado e nenhuma estatística estará disponível.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-159">The assessment progress indicator will be shaded, and no statistics will be available.</span></span>
  
<span data-ttu-id="0ea6a-160">Na ausência de estabilização com base Estatistica, haverá resultados com um nível inferior de precisão e nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-160">In the absence of statistically based stabilization, there will be results with a lower level of accuracy and confidence level.</span></span> <span data-ttu-id="0ea6a-161">No entanto, esses resultados podem ser usados para localizar arquivos relevantes quando você não precisa saber a porcentagem de arquivos relevantes encontrados.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-161">However, these results can be used to find relevant files when you do not need to know the percentage of relevant files found.</span></span> <span data-ttu-id="0ea6a-162">Da mesma forma, esse status pode ser usado para treinar problemas com uma riqueza inferior, em que as pontuações de relevância podem acelerar o acesso a arquivos relevantes para um problema específico.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-162">Similarly, this status can be used to train issues with low richness, where Relevance scores can accelerate access to files relevant to a specific issue.</span></span>
  
> [!TIP]
> <span data-ttu-id="0ea6a-163">Na guia **\> controle de relevância** , exibição de problema expandido, as seguintes opções de visualização estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0ea6a-163">In the **Relevance \> Track** tab, expanded issue display, the following viewing options are available:</span></span> 
> 
> <span data-ttu-id="0ea6a-164">A próxima etapa recomendada, como **próxima etapa: a marcação** pode ser ignorada (por problema) clicando no botão **Modificar** à direita e, em seguida, selecionando uma etapa diferente na **próxima etapa**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-164">The recommended next step, such as **Next step: Tagging** can be bypassed (per issue) by clicking the **Modify** button to its right, and then selecting an different step in the **Next step**.</span></span> <span data-ttu-id="0ea6a-165">Quando o indicador de progresso da avaliação não for concluído, a avaliação será a próxima opção recomendada para marcar mais arquivos de avaliação e aumentar a precisão das estatísticas.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-165">When the assessment progress indicator has not completed, assessment will be the next recommended option, to tag more assessment files and increase statistics accuracy.</span></span> 
> 
> <span data-ttu-id="0ea6a-166">Você pode alterar a margem de erro e avaliar seu impacto, clicando em **Modificar** e, na **caixa de diálogo nível de avaliação**, alterando a **margem de erro de destino para obter estimativas de cancelamento** e clicando em **atualizar valores**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-166">You can change the error margin and assess its impact, by clicking **Modify**, and in the **Assessment level dialog**, changing the **Target error margin for recall estimates**, and clicking **Update values**.</span></span> <span data-ttu-id="0ea6a-167">Além disso, nessa caixa de diálogo, você pode exibir opções avançadas clicando em **avançado**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-167">Also, in this dialog, you can view advanced options, by clicking **Advanced**.</span></span> 
> 
> <span data-ttu-id="0ea6a-168">Você pode exibir estatísticas de nível de avaliação adicionais e seu impacto clicando em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-168">You can view additional assessment level statistics and their impact by clicking **View**.</span></span> <span data-ttu-id="0ea6a-169">Na caixa de diálogo resultados detalhados exibidos, as estatísticas estão disponíveis por questão, quando há pelo menos 500 arquivos de avaliação marcados e pelo menos 18 arquivos são marcados conforme relevante para o problema.</span><span class="sxs-lookup"><span data-stu-id="0ea6a-169">In the displayed Detail results dialog, statistics are available per issue, when there are at least 500 tagged assessment files and at least 18 files are tagged as Relevant for the issue.</span></span> 
