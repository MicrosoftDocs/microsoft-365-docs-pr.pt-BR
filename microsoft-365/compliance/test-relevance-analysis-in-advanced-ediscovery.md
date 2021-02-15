---
title: Testar a análise de relevância na Descoberta Avançada
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
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como usar a guia Teste após o cálculo em lotes na Descoberta eDiscovery Avançada para testar, comparar e validar a qualidade geral do processamento.
ms.openlocfilehash: 3ac12c176f2e46ac0321976a7e0689fbd8893bba
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769166"
---
# <a name="test-relevance-analysis-in-advanced-ediscovery"></a><span data-ttu-id="d3f68-103">Testar a análise de relevância na Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="d3f68-103">Test Relevance analysis in Advanced eDiscovery</span></span>
  
<span data-ttu-id="d3f68-104">A guia Teste na Descoberta Avançada permite testar, comparar e validar a qualidade geral do processamento.</span><span class="sxs-lookup"><span data-stu-id="d3f68-104">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing.</span></span> <span data-ttu-id="d3f68-105">Esses testes são executados após o cálculo em lotes.</span><span class="sxs-lookup"><span data-stu-id="d3f68-105">These tests are performed after Batch calculation.</span></span> <span data-ttu-id="d3f68-106">Ao marcar os arquivos na coleção, um especialista faz o parecer final sobre se cada arquivo marcado é relevante para o caso.</span><span class="sxs-lookup"><span data-stu-id="d3f68-106">By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is relevant to the case.</span></span>
  
<span data-ttu-id="d3f68-107">Em cenários individuais e com vários problemas, os testes geralmente são executados por problema.</span><span class="sxs-lookup"><span data-stu-id="d3f68-107">In single and multiple-issue scenarios, tests are typically performed per issue.</span></span> <span data-ttu-id="d3f68-108">Os resultados podem ser exibidos após cada teste, e os resultados do teste podem ser reformulados com arquivos de teste de amostra especificados.</span><span class="sxs-lookup"><span data-stu-id="d3f68-108">Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="d3f68-109">Testando o restante</span><span class="sxs-lookup"><span data-stu-id="d3f68-109">Testing the rest</span></span>

<span data-ttu-id="d3f68-110">O teste "Testar o Restante" é usado para validar as decisões de recortar, por exemplo, para revisar somente os arquivos acima de uma pontuação de corte de relevância específica com base nos resultados finais da Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="d3f68-110">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results.</span></span> <span data-ttu-id="d3f68-111">O especialista revisa um exemplo de arquivos em uma pontuação de corte selecionada para avaliar o número de arquivos relevantes dentro desse conjunto.</span><span class="sxs-lookup"><span data-stu-id="d3f68-111">The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="d3f68-112">Este teste fornece estatísticas e uma comparação entre o conjunto de revisão e a população Test the Rest.</span><span class="sxs-lookup"><span data-stu-id="d3f68-112">This test provides statistics and a comparison between the Review set and the Test the Rest population.</span></span> <span data-ttu-id="d3f68-113">Os resultados do conjunto de revisão são aqueles calculados pela Relevância durante o Treinamento.</span><span class="sxs-lookup"><span data-stu-id="d3f68-113">The results of the review set are those calculated by Relevance during Training.</span></span> <span data-ttu-id="d3f68-114">Os resultados incluem cálculos com base em configurações e parâmetros de entrada, como:</span><span class="sxs-lookup"><span data-stu-id="d3f68-114">The results include calculations based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="d3f68-115">Teste as estatísticas de amostra do número de arquivos em uma amostra e identifique os arquivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="d3f68-115">Test sample statistics of the number of files in a sample and identified relevant files.</span></span>

- <span data-ttu-id="d3f68-116">Comparação tabular dos parâmetros Population do conjunto de Revisão e o Restante, por exemplo, o número de arquivos, o número estimado de arquivos relevantes, a riqueza estimada e o custo médio de localizar outro arquivo relevante.</span><span class="sxs-lookup"><span data-stu-id="d3f68-116">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding another relevant file.</span></span> <span data-ttu-id="d3f68-117">As configurações de parâmetro de custo podem ser definidas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="d3f68-117">Cost parameter settings can be set by the administrator.</span></span>

<span data-ttu-id="d3f68-118">Para executar o teste "Testar o Restante":</span><span class="sxs-lookup"><span data-stu-id="d3f68-118">To run the "Test the Rest" test:</span></span>

1. <span data-ttu-id="d3f68-119">Abra a **guia Teste \> de Relevância.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-119">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="d3f68-120">Na guia **Teste,** clique em **Novo teste.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-120">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="d3f68-121">A **caixa de** diálogo Criar teste é exibida, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3f68-121">The **Create test** dialog is displayed, as shown in the following example.</span></span>

    ![Resultados de “Test the Rest” de relevância](../media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="d3f68-123">Em **Nome do teste** e **descrição,** digite o nome e a descrição.</span><span class="sxs-lookup"><span data-stu-id="d3f68-123">In **Test name**, and **Description**, type the name and description.</span></span>

4. <span data-ttu-id="d3f68-124">Na lista **de tipos de** teste, selecione Testar o **Restante**</span><span class="sxs-lookup"><span data-stu-id="d3f68-124">In the **Test type** list, select **Test the Rest**</span></span>

5. <span data-ttu-id="d3f68-125">Na lista **Problema/Categoria,** selecione o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="d3f68-125">In the **Issue / Category** list, select the issue name.</span></span>

6. <span data-ttu-id="d3f68-126">Na lista **Carregar,** selecione o carregamento.</span><span class="sxs-lookup"><span data-stu-id="d3f68-126">In the **Load** list, select the load.</span></span> 

7. <span data-ttu-id="d3f68-127">Em **% de** leitura, aceite o valor padrão ou selecione um valor para a pontuação de relevância de corte.</span><span class="sxs-lookup"><span data-stu-id="d3f68-127">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 

8. <span data-ttu-id="d3f68-128">Em **Definir tamanho,** ou aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="d3f68-128">In **Set size**, or accept the default value.</span></span> <span data-ttu-id="d3f68-129">Os ícones de restauração restaurarão os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="d3f68-129">The restore icons will restore the default values.</span></span>

9. <span data-ttu-id="d3f68-130">Clique **na marcação Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-130">Click **Start tagging**.</span></span> <span data-ttu-id="d3f68-131">Um exemplo de teste é gerado.</span><span class="sxs-lookup"><span data-stu-id="d3f68-131">A test sample is generated.</span></span>

10. <span data-ttu-id="d3f68-132">Revise e marque cada um dos arquivos na **guia \>** Marca de Relevância e, quando terminar, clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="d3f68-132">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="d3f68-133">Na guia Teste, você pode clicar em Exibir **resultados** para ver os resultados do teste.</span><span class="sxs-lookup"><span data-stu-id="d3f68-133">In the Test tab, you can click **View results** to see the test results.</span></span> <span data-ttu-id="d3f68-134">Um exemplo é mostrado na captura de tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3f68-134">An example is shown in the following screenshot.</span></span>

    ![Resultados do “Test the rest”](../media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="d3f68-136">Na captura de tela anterior, a seção Exemplos de parâmetros da tabela contém detalhes sobre o número de arquivos na amostra marcados pelo especialista e o número de arquivos **relevantes** encontrados nesse exemplo.</span><span class="sxs-lookup"><span data-stu-id="d3f68-136">In the previous screenshot, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span>
  
<span data-ttu-id="d3f68-137">A **seção Parâmetros** População da tabela contém os resultados do teste, incluindo a população de conjunto de revisão de arquivos com uma pontuação abaixo da pontuação selecionada e a população de arquivos "O Restante" com uma pontuação acima do corte selecionado.</span><span class="sxs-lookup"><span data-stu-id="d3f68-137">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff.</span></span> <span data-ttu-id="d3f68-138">Para cada população, os seguintes resultados são exibidos:</span><span class="sxs-lookup"><span data-stu-id="d3f68-138">For each population, the following results are displayed:</span></span>
  
- <span data-ttu-id="d3f68-139">Inclui arquivos com % de leitura - Corte declarado</span><span class="sxs-lookup"><span data-stu-id="d3f68-139">Includes files with read % - Stated cutoff</span></span>

- <span data-ttu-id="d3f68-140">O número total de arquivos</span><span class="sxs-lookup"><span data-stu-id="d3f68-140">The total number of files</span></span>

- <span data-ttu-id="d3f68-141">O número estimado de arquivos relevantes</span><span class="sxs-lookup"><span data-stu-id="d3f68-141">The estimated number of relevant files</span></span>

- <span data-ttu-id="d3f68-142">A riqueza estimada</span><span class="sxs-lookup"><span data-stu-id="d3f68-142">The estimated richness</span></span>

- <span data-ttu-id="d3f68-143">O custo médio de revisão para localizar outro arquivo relevante</span><span class="sxs-lookup"><span data-stu-id="d3f68-143">The average review cost of finding another relevant file</span></span>

## <a name="testing-the-slice"></a><span data-ttu-id="d3f68-144">Testando a fatia</span><span class="sxs-lookup"><span data-stu-id="d3f68-144">Testing the slice</span></span>

<span data-ttu-id="d3f68-145">O teste "Testar a Fatia" realiza testes semelhantes ao teste "Testar o Restante", mas a um segmento do conjunto de arquivos, conforme especificado pelo %de Leitura de Relevância.</span><span class="sxs-lookup"><span data-stu-id="d3f68-145">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>

<span data-ttu-id="d3f68-146">Para executar o teste "Testar a fatia":</span><span class="sxs-lookup"><span data-stu-id="d3f68-146">To run the "Test the Slice" test:</span></span>
  
1. <span data-ttu-id="d3f68-147">Abra a **guia Teste \> de Relevância.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-147">Open the **Relevance \> Test** tab.</span></span>

2. <span data-ttu-id="d3f68-148">Na guia **Teste,** clique em **Novo teste.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-148">In the **Test** tab, click **New test**.</span></span> <span data-ttu-id="d3f68-149">A **caixa de diálogo** Criar teste é exibida.</span><span class="sxs-lookup"><span data-stu-id="d3f68-149">The **Create test** dialog is displayed.</span></span>

3. <span data-ttu-id="d3f68-150">Em **Nome do teste** e **descrição,** digite as informações.</span><span class="sxs-lookup"><span data-stu-id="d3f68-150">In **Test name** and **Description**, type the information.</span></span>

4. <span data-ttu-id="d3f68-151">Na lista **De tipo de** teste, selecione Testar a **fatia**.</span><span class="sxs-lookup"><span data-stu-id="d3f68-151">In the **Test type** list, select **Test the Slice**.</span></span>

5. <span data-ttu-id="d3f68-152">Na lista **Problema,** selecione o nome do problema.</span><span class="sxs-lookup"><span data-stu-id="d3f68-152">In the **Issue** list, select the issue name.</span></span>

6. <span data-ttu-id="d3f68-153">Na lista **Carregar,** selecione o carregamento.</span><span class="sxs-lookup"><span data-stu-id="d3f68-153">In the **Load** list, select the load.</span></span>

7. <span data-ttu-id="d3f68-154">Em **% de leitura entre**, aceite os valores padrão de intervalo baixo e alto ou selecione valores para as pontuações de relevância de corte.</span><span class="sxs-lookup"><span data-stu-id="d3f68-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span>

8. <span data-ttu-id="d3f68-155">Em **Definir tamanho,** selecione um valor ou aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="d3f68-155">In **Set size**, select a value or accept the default value.</span></span>

    <span data-ttu-id="d3f68-156">Os ícones de restauração restaurarão o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="d3f68-156">The restore icons will restore the default value.</span></span>

9. <span data-ttu-id="d3f68-157">Clique **na marcação Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="d3f68-157">Click **Start tagging**.</span></span> <span data-ttu-id="d3f68-158">Um exemplo de teste é gerado.</span><span class="sxs-lookup"><span data-stu-id="d3f68-158">A test sample is generated.</span></span>

10. <span data-ttu-id="d3f68-159">Revise e marque cada um dos arquivos na **guia \>** Marca de Relevância e, quando terminar, clique em **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="d3f68-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>

11. <span data-ttu-id="d3f68-160">Na guia Teste, você pode clicar em Exibir **resultados** para ver os resultados do teste.</span><span class="sxs-lookup"><span data-stu-id="d3f68-160">In the Test tab, you can click **View results** to see the test results.</span></span>
