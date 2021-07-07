---
title: Análise de regressão de memória
description: Como inferir regressão de memória
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: cd95c4e0eb04b05860ded256066913cf87d67e86
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322462"
---
# <a name="memory-regression-analysis"></a><span data-ttu-id="e489c-103">Análise de Regressão de Memória</span><span class="sxs-lookup"><span data-stu-id="e489c-103">Memory Regression Analysis</span></span>

<span data-ttu-id="e489c-104">A Base de Teste ajuda você a perceber com mais clareza aumentos significativos de uso de memória nas VMs de teste que executam seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e489c-104">Test Base helps you more clearly notice significant memory usage increases in the test VMs running your apps.</span></span> <span data-ttu-id="e489c-105">As métricas de desempenho, como o uso da memória, podem indicar a saúde geral do aplicativo e acreditamos que essa adição ajudará muito a manter o desempenho ideal de seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e489c-105">Performance metrics, such as memory usage, can be indicative of overall application health and we believe this addition will greatly help keep your apps performing optimally.</span></span>

<span data-ttu-id="e489c-106">Leia mais para obter mais detalhes ou assista a este vídeo para obter uma rápida explicação sobre as melhorias mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e489c-106">Read on for more details or watch this video for a quick walk through of the latest improvements.</span></span> 

<span data-ttu-id="e489c-107">Para obter mais informações sobre a base de teste para a capacidade do M365 de ajudar na análise de regressão, consulte Resultados de regressão com base na confiabilidade do processo.</span><span class="sxs-lookup"><span data-stu-id="e489c-107">For more information on Test Base for M365's ability to help with regression analysis, see Regression results based on process reliability.</span></span>

<span data-ttu-id="e489c-108"><b>Olhando mais de perto as regressões de memória</b></span><span class="sxs-lookup"><span data-stu-id="e489c-108"><b>Looking closer at memory regressions</b></span></span>

<span data-ttu-id="e489c-109">O painel base de teste do M365 mostra a memória consumida pelo aplicativo em uma nova atualização de Windows pré-lançada e a compara com a memória usada pela última atualização Windows lançada.</span><span class="sxs-lookup"><span data-stu-id="e489c-109">The Test Base for M365 dashboard shows the memory consumed by your application on a new pre-released Windows update and compares it with the memory used by the last released Windows update.</span></span> 

<span data-ttu-id="e489c-110">Com os aprimoramentos deste mês, a análise de regressão de memória agora é destaque em seus processos favoritos.</span><span class="sxs-lookup"><span data-stu-id="e489c-110">With this month’s enhancements, memory regression analysis is now featured in your favorited processes.</span></span> <span data-ttu-id="e489c-111">Os aplicativos podem conter vários processos e você pode selecionar manualmente seus processos favoritos por meio da guia Confiabilidade. Nosso serviço identificará regressões de memória nesses processos favoritos ao comparar os testes executados em diferentes Windows de atualização.</span><span class="sxs-lookup"><span data-stu-id="e489c-111">Applications can contain multiple processes and you can manually select your favorite processes through the Reliability tab. Our service will then identify memory regressions in these favorited processes while comparing test runs across different Windows update releases.</span></span> <span data-ttu-id="e489c-112">Se uma regressão for detectada, detalhes sobre a regressão estarão facilmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e489c-112">If a regression is detected, details about the regression are easily available.</span></span>

<span data-ttu-id="e489c-113">Agora vamos analisar esse recurso em detalhes e discutir como você pode solucionar problemas de regressão de memória usando o Analisador de Desempenho Windows desempenho.</span><span class="sxs-lookup"><span data-stu-id="e489c-113">Now let's look at this feature in detail and discuss how you can troubleshoot memory regressions using Windows Performance Analyzer.</span></span>

<span data-ttu-id="e489c-114">O sinal de falha causado por uma regressão de memória é mostrado no painel Base de Teste do M365 na página Resultados do teste em Utilização de Memória:</span><span class="sxs-lookup"><span data-stu-id="e489c-114">The failure signal caused by a memory regression is shown in the Test Base for M365 dashboard on the Test results page under Memory Utilization:</span></span>

![Resultados de utilização de memória](Media/01_memory-utilization-results.png)


<span data-ttu-id="e489c-116">A falha no aplicativo devido ao maior consumo de memória também será exibida como ```Fail``` na página Resumo do Teste:</span><span class="sxs-lookup"><span data-stu-id="e489c-116">Failure for the application due to higher memory consumption, will also be displayed as ```Fail``` on the Test Summary page:</span></span>

![Resultados de resumo de teste](Media/02_test-summary.png)

<span data-ttu-id="e489c-118">Ao fornecer esses sinais de falha antecipadamente, nosso objetivo é sinalizar claramente possíveis problemas que podem interromper e afetar a experiência do usuário final para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e489c-118">By providing these failure signals upfront, our goal is to clearly flag potential issues that can disrupt and impact the end user experience for your application.</span></span> 

<span data-ttu-id="e489c-119">Em seguida, você pode baixar os arquivos de log e usar o Analisador de Desempenho Windows, ou seu kit de ferramentas preferencial, para investigar mais.</span><span class="sxs-lookup"><span data-stu-id="e489c-119">You can then download the log files and use the Windows Performance Analyzer, or your preferred toolkit, to investigate further.</span></span> <span data-ttu-id="e489c-120">Você também pode trabalhar em conjunto com a equipe da Base de Teste do M365 para resolver o problema e ajudar a evitar problemas que impactam os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="e489c-120">You can also work jointly with the Test Base for M365 team on remediating the issue and help prevent issues impacting end users.</span></span>

<span data-ttu-id="e489c-121">Os sinais de memória são capturados na guia Utilização de Memória no serviço Base de Teste para M365 para todas as executações de teste.</span><span class="sxs-lookup"><span data-stu-id="e489c-121">Memory signals are captured in the Memory Utilization tab in the Test Base for M365 service for all test runs.</span></span> <span data-ttu-id="e489c-122">O exemplo a seguir mostra um teste recente executado com o aplicativo onboarded "Stress de memória de teste de fumaça" na atualização de segurança de agosto de 2020.</span><span class="sxs-lookup"><span data-stu-id="e489c-122">The example below shows a recent test run with the onboarded application “Smoke Test Memory Stress” against the pre-release August 2020 security update.</span></span> <span data-ttu-id="e489c-123">(Este aplicativo foi escrito por nossa equipe para ilustrar regressões de memória.)</span><span class="sxs-lookup"><span data-stu-id="e489c-123">(This application was written by our team to illustrate memory regressions.)</span></span>

![Resultados de regressão de memória](Media/03_memory-regression%20comparison.png)

<span data-ttu-id="e489c-125">Neste exemplo, o processo favorito "USLTestMemoryStress.exe" consumiu uma média de aproximadamente 100 MB na atualização de agosto de pré-lançamento em comparação com a atualização lançada em julho, portanto, a Base de Teste para M365 identificou uma regressão.</span><span class="sxs-lookup"><span data-stu-id="e489c-125">In this example, the favorite process “USLTestMemoryStress.exe” process consumed an average of approximately 100 MB on the pre-release August update compared to the released July update, hence the Test Base for M365 identified a regression.</span></span> 

<span data-ttu-id="e489c-126">Os outros processos , mostrados aqui como "USLTestMemoryStress_Aux1.exe" e "USLTestMemoryStress_Aux2.exe", também pertencem ao mesmo aplicativo, mas consumiram aproximadamente a mesma quantidade de memória para as duas versões para que "passaram" e foram considerados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e489c-126">The other processes—shown here as “USLTestMemoryStress_Aux1.exe” and “USLTestMemoryStress_Aux2.exe”—also belong to the same application, but consumed approximately the same amount of memory for the two releases so they "passed" and were considered healthy.</span></span>

<span data-ttu-id="e489c-127">A regressão no processo principal foi determinada como "significativamente significativa" para que o serviço se comunicava e realçava essa diferença para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e489c-127">The regression on the main process was determined to be “statistically significant” so the service communicated and highlighted this difference to the user.</span></span> <span data-ttu-id="e489c-128">Se a comparação não tiver sido significativa, ela não será realçada.</span><span class="sxs-lookup"><span data-stu-id="e489c-128">If the comparison was not statistically significant, it would not be highlighted.</span></span> <span data-ttu-id="e489c-129">A utilização de memória pode ser barulhento, portanto, usamos modelos estatísticos para distinguir, entre versões e versões, diferenças significativas de diferenças inconsequentes.</span><span class="sxs-lookup"><span data-stu-id="e489c-129">Memory utilization can be noisy, so we use statistical models to distinguish, across builds and releases, meaningful differences from inconsequential differences.</span></span> 

<span data-ttu-id="e489c-130">Uma comparação raramente pode ser sinalizada quando não há diferença verdadeira (um falso positivo), mas essa é uma troca necessária para melhorar a probabilidade de identificar corretamente as regressões (ou verdadeiros positivos).)</span><span class="sxs-lookup"><span data-stu-id="e489c-130">A comparison may rarely be flagged when there is no true difference (a false positive), but this is a necessary tradeoff to improve the likelihood of correctly identifying regressions (or true positives.)</span></span>

<span data-ttu-id="e489c-131">A próxima etapa é entender o que causou a regressão de memória.</span><span class="sxs-lookup"><span data-stu-id="e489c-131">The next step is to understand what caused the memory regression.</span></span> <span data-ttu-id="e489c-132">Você pode baixar os arquivos zip para ambas as execuções na opção Baixar arquivos de log, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="e489c-132">You can download the zip files for both executions from the Download log files option, as shown below.</span></span> 

<span data-ttu-id="e489c-133">Esses arquivos zip contêm os resultados de sua execução de teste, incluindo resultados de script e dados de desempenho de memória e CPU incluídos no arquivo ETL.</span><span class="sxs-lookup"><span data-stu-id="e489c-133">These zip files contain the results of your test run, including script results and memory and CPU performance data which is included in the ETL file.</span></span>

![Arquivos de teste de regressão de memória](Media/04_memory-regression-test-files.png)

<span data-ttu-id="e489c-135">Você pode baixar e descompoar os logs das duas versões de teste e localizar o arquivo ETL em cada pasta e renomeá-los como target.etl (para o teste executado na atualização de pré-lançamento) e baseline.etl (para o teste executado na última atualização lançada) para simplificar a exploração e a navegação.</span><span class="sxs-lookup"><span data-stu-id="e489c-135">You can download and unzip the logs for the two test runs, then locate the ETL file within each folder and rename them as target.etl (for the test run on the pre-release update) and baseline.etl (for the test run on last released update) to simplify exploration and navigation.</span></span>
 
## <a name="next-steps"></a><span data-ttu-id="e489c-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e489c-136">Next steps</span></span>

<span data-ttu-id="e489c-137">Avance para o próximo artigo para começar a entender a análise inteligente de regressão da CPU.</span><span class="sxs-lookup"><span data-stu-id="e489c-137">Advance to the next article to get started with understanding intelligent CPU regression analysis.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="e489c-138">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e489c-138">Next step</span></span>](cpu.md)

<!---
Add button for next page
-->
