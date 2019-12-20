---
title: Testar a análise de relevância na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Saiba como usar a guia teste após o cálculo em lote na descoberta eletrônica avançada do Office 365 para testar, comparar e validar a qualidade geral do processamento.  '
ms.openlocfilehash: cda959c77b2d51f85f1396eb27d16d2690321bb6
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802624"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="983a1-103">Testar a análise de relevância na descoberta eletrônica avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="983a1-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="983a1-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="983a1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="983a1-106">A guia teste em descoberta eletrônica avançada permite testar, comparar e validar a qualidade geral do processamento.</span><span class="sxs-lookup"><span data-stu-id="983a1-106">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="983a1-107">Esses testes são executados após o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="983a1-107">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="983a1-108">Ao marcar os arquivos na coleção, um especialista faz o julgamento final sobre se cada arquivo marcado é realmente relevante para o caso.</span><span class="sxs-lookup"><span data-stu-id="983a1-108">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="983a1-109">Em cenários de um e vários problemas, os testes são normalmente executados por problema.</span><span class="sxs-lookup"><span data-stu-id="983a1-109">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="983a1-110">Os resultados podem ser exibidos após cada teste, e os resultados do teste podem ser retrabalhados com os arquivos de teste de amostra especificados.</span><span class="sxs-lookup"><span data-stu-id="983a1-110">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="983a1-111">Testando o restante</span><span class="sxs-lookup"><span data-stu-id="983a1-111">Testing the rest</span></span>

<span data-ttu-id="983a1-112">O teste "Test The Rest" é usado para validar decisões de remoção, por exemplo, para revisar apenas arquivos acima de uma pontuação específica de corte de relevância com base nos resultados finais avançados da descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="983a1-112">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="983a1-113">O especialista revisa uma amostra de arquivos sob uma pontuação de corte selecionada para avaliar o número de arquivos relevantes dentro desse conjunto.</span><span class="sxs-lookup"><span data-stu-id="983a1-113">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="983a1-114">Esse teste fornece estatísticas e uma comparação entre o conjunto de revisão e o teste da população REST.</span><span class="sxs-lookup"><span data-stu-id="983a1-114">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="983a1-115">Os resultados do conjunto de revisão são aqueles calculados por relevância durante o treinamento.</span><span class="sxs-lookup"><span data-stu-id="983a1-115">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="983a1-116">Os resultados incluem cálculos, com base em configurações e parâmetros de entrada, como:</span><span class="sxs-lookup"><span data-stu-id="983a1-116">The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="983a1-117">Teste as estatísticas de exemplo do número de arquivos em uma amostra e identificado arquivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="983a1-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="983a1-118">Comparação de tabulação dos parâmetros de população do conjunto de análise e do restante, por exemplo, o número de arquivos, o número estimado de arquivos relevantes, a riqueza estimada e o custo médio de localizar um arquivo relevante adicional.</span><span class="sxs-lookup"><span data-stu-id="983a1-118">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file.</span></span> <span data-ttu-id="983a1-119">As configurações de parâmetros de custo podem ser definidas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="983a1-119">Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="983a1-120">Abra a **guia \> teste de relevância** .</span><span class="sxs-lookup"><span data-stu-id="983a1-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="983a1-121">Na guia **teste** , clique em **novo teste**.</span><span class="sxs-lookup"><span data-stu-id="983a1-121">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="983a1-122">A caixa de diálogo **criar teste** é exibida, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="983a1-122">The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Resultados de “Test the Rest” de relevância](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="983a1-124">Em **nome do teste**e **Descrição**, digite o nome e a descrição.</span><span class="sxs-lookup"><span data-stu-id="983a1-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="983a1-125">Na lista **tipo de teste** , selecione **testar o restante**</span><span class="sxs-lookup"><span data-stu-id="983a1-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="983a1-126">Na lista **problema/categoria** , selecione o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="983a1-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="983a1-127">Na lista **carregar** , selecione carregar.</span><span class="sxs-lookup"><span data-stu-id="983a1-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="983a1-128">Em **leitura%**, aceite o valor padrão ou selecione um valor para a pontuação de relevância de corte.</span><span class="sxs-lookup"><span data-stu-id="983a1-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="983a1-129">Em **tamanho do conjunto**, ou aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="983a1-129">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="983a1-130">Observe que os ícones de restauração restaurarão os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="983a1-130">Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="983a1-131">Clique em **Iniciar marcação**.</span><span class="sxs-lookup"><span data-stu-id="983a1-131">Click **Start tagging**.</span></span> <span data-ttu-id="983a1-132">Um exemplo de teste é gerado.</span><span class="sxs-lookup"><span data-stu-id="983a1-132">A test sample is generated.</span></span>
    
10. <span data-ttu-id="983a1-133">Revise e marque cada um dos arquivos na **guia \> marca de relevância** e, quando terminar, clique em **calcular**.</span><span class="sxs-lookup"><span data-stu-id="983a1-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="983a1-134">Na guia teste, você pode clicar em **exibir resultados** para ver os resultados do teste.</span><span class="sxs-lookup"><span data-stu-id="983a1-134">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="983a1-135">Um exemplo é mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="983a1-135">An example is shown in the following figure.</span></span> 
    
    ![Resultados do “Test the rest”](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="983a1-137">Na figura acima, a seção **parâmetros de exemplo** da tabela contém detalhes sobre o número de arquivos no exemplo marcado pelo especialista e o número de arquivos relevantes encontrados nesse exemplo.</span><span class="sxs-lookup"><span data-stu-id="983a1-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="983a1-138">A seção **parâmetros de população** da tabela contém os resultados do teste, incluindo a população de análise definida de arquivos com uma pontuação abaixo do corte selecionado e o preenchimento "o restante" dos arquivos com uma pontuação acima do corte selecionado.</span><span class="sxs-lookup"><span data-stu-id="983a1-138">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="983a1-139">Para cada população, os seguintes resultados são exibidos:</span><span class="sxs-lookup"><span data-stu-id="983a1-139">For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="983a1-140">Inclui arquivos com corte de leitura%-declarado</span><span class="sxs-lookup"><span data-stu-id="983a1-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="983a1-141">O número total de arquivos</span><span class="sxs-lookup"><span data-stu-id="983a1-141">The total number of files</span></span> 
    
- <span data-ttu-id="983a1-142">O número estimado de arquivos relevantes</span><span class="sxs-lookup"><span data-stu-id="983a1-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="983a1-143">A riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="983a1-143">The estimated richness</span></span> 
    
- <span data-ttu-id="983a1-144">O custo de análise média de localizar outro arquivo relevante</span><span class="sxs-lookup"><span data-stu-id="983a1-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="983a1-145">Testando a fatia</span><span class="sxs-lookup"><span data-stu-id="983a1-145">Testing the slice</span></span>

<span data-ttu-id="983a1-146">O teste "testar a fatia" executa testes semelhantes ao teste "testar o REST", mas para um segmento do conjunto de arquivos conforme especificado por relevância Read%.</span><span class="sxs-lookup"><span data-stu-id="983a1-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="983a1-147">Abra a **guia \> teste de relevância** .</span><span class="sxs-lookup"><span data-stu-id="983a1-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="983a1-148">Na guia **teste** , clique em **novo teste**.</span><span class="sxs-lookup"><span data-stu-id="983a1-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="983a1-149">A caixa de diálogo **criar teste** é exibida.</span><span class="sxs-lookup"><span data-stu-id="983a1-149">The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="983a1-150">Em **nome do teste** e **Descrição**, digite as informações.</span><span class="sxs-lookup"><span data-stu-id="983a1-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="983a1-151">Na lista **tipo de teste** , selecione **testar a fatia**.</span><span class="sxs-lookup"><span data-stu-id="983a1-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="983a1-152">Na lista **problema** , selecione o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="983a1-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="983a1-153">Na lista **carregar** , selecione carregar.</span><span class="sxs-lookup"><span data-stu-id="983a1-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="983a1-154">Em **% de leitura**, aceite os valores de intervalo baixo e alto padrão ou selecione valores para as pontuações de relevância de corte.</span><span class="sxs-lookup"><span data-stu-id="983a1-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="983a1-155">Em **tamanho do conjunto**, selecione um valor ou aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="983a1-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="983a1-156">Os ícones de restauração restaurarão o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="983a1-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="983a1-157">Clique em **Iniciar marcação**.</span><span class="sxs-lookup"><span data-stu-id="983a1-157">Click **Start tagging**.</span></span> <span data-ttu-id="983a1-158">Um exemplo de teste é gerado.</span><span class="sxs-lookup"><span data-stu-id="983a1-158">A test sample is generated.</span></span>
    
10. <span data-ttu-id="983a1-159">Revise e marque cada um dos arquivos na **guia \> marca de relevância** e, quando terminar, clique em **calcular**.</span><span class="sxs-lookup"><span data-stu-id="983a1-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="983a1-160">Na guia teste, você pode clicar em **exibir resultados** para ver os resultados do teste.</span><span class="sxs-lookup"><span data-stu-id="983a1-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="983a1-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="983a1-161">See also</span></span>

[<span data-ttu-id="983a1-162">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="983a1-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="983a1-163">Noções básicas sobre avaliação em relevância</span><span class="sxs-lookup"><span data-stu-id="983a1-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="983a1-164">Marcação e avaliação</span><span class="sxs-lookup"><span data-stu-id="983a1-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="983a1-165">Treinamento de marcação e relevância</span><span class="sxs-lookup"><span data-stu-id="983a1-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="983a1-166">Análise de relevância de rastreamento</span><span class="sxs-lookup"><span data-stu-id="983a1-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="983a1-167">Decidindo com base nos resultados</span><span class="sxs-lookup"><span data-stu-id="983a1-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

