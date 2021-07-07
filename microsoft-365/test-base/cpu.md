---
title: Análise de regressão de CPU
description: Noções básicas sobre resultados e métricas de regressão para consumo de CPU
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
ms.openlocfilehash: bc28c128902ae353fb35c3b6010856ade934a436
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322442"
---
# <a name="intelligent-cpu-regression-analysis"></a><span data-ttu-id="3d31e-103">Análise de regressão de CPU inteligente</span><span class="sxs-lookup"><span data-stu-id="3d31e-103">Intelligent CPU regression analysis</span></span>

<span data-ttu-id="3d31e-104">A utilização da CPU pode indicar se um aplicativo é afetado por uma atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3d31e-104">CPU utilization can indicate whether an application is affected by an operating system update.</span></span> 

<span data-ttu-id="3d31e-105">A Base de Teste para Microsoft 365 fornece aos desenvolvedores de software uma visão das regressões de desempenho da CPU que ocorrem quando seu aplicativo está sendo executado em diferentes versões de uma atualização futura do sistema operacional (sistema operacional) Windows futuro.</span><span class="sxs-lookup"><span data-stu-id="3d31e-105">Test Base for Microsoft 365 provides software developers with an insight into CPU performance regressions which occur when their application is running on different versions of an upcoming Windows Operating System (OS) update.</span></span> 

<span data-ttu-id="3d31e-106">Essas regressões de CPU permitem que os desenvolvedores detectem e resolvam problemas de aplicativo (e possíveis falhas) antes que a atualização do sistema operacional seja implantada amplamente, impedindo assim uma experiência ruim para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="3d31e-106">These CPU regressions enable developers to detect and resolve application issues (and potential failures) before the OS update is deployed broadly, thus preventing a bad experience for the end user.</span></span>


### <a name="how-cpu-regression-analysis-works"></a><span data-ttu-id="3d31e-107">Como funciona a análise de regressão da CPU</span><span class="sxs-lookup"><span data-stu-id="3d31e-107">How CPU regression analysis works</span></span> ###

<span data-ttu-id="3d31e-108">Como um usuário da Base de Teste, você pode carregar os binários do aplicativo (em um único arquivo .zip), juntamente com scripts de teste associados e selecionar a versão do sistema operacional Windows na qual você gostaria de testar seu aplicativo no portal base de teste no Azure.</span><span class="sxs-lookup"><span data-stu-id="3d31e-108">As a Test Base user, you can upload your application's binaries (in a single .zip file), along with associated test scripts and select the Windows OS version against which you would like to test your application on the Test Base portal on Azure.</span></span> 

<span data-ttu-id="3d31e-109">Em seguida, o serviço Base de Teste executa os scripts de teste e executa a Análise **de Regressão da CPU.**</span><span class="sxs-lookup"><span data-stu-id="3d31e-109">The Test Base service then runs the test scripts and performs the **CPU Regression Analysis**.</span></span> 

<span data-ttu-id="3d31e-110">O serviço verifica se a utilização da CPU para o aplicativo na versão de pré-lançamento da atualização do sistema operacional de destino está em linha com a utilização da CPU para a versão lançada do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3d31e-110">The service checks if the CPU utilization for the application on the pre-release version of the update for the target OS is in line with the CPU utilization for the released version of the OS.</span></span> 

<span data-ttu-id="3d31e-111">A utilização da CPU não é uma comparação 100% like-for-like porque os processos em execução nas duas versões do sistema operacional podem ou não ser uma combinação exata devido a versões diferentes do sistema operacional; no entanto, a análise realizada pela Base de Teste pode mostrar se a utilização da CPU para seu aplicativo é impactada por uma atualização futura do sistema operacional e especificamente quais processos foram regredidos de testes anteriores.</span><span class="sxs-lookup"><span data-stu-id="3d31e-111">CPU utilization is not a 100% like-for-like comparison because the processes running on the two versions of the OS may or may not be an exact match due to differing OS versions; however, the analysis performed by Test Base can show you whether CPU utilization for your application is impacted by an upcoming OS update and specifically which processes have regressed from previous test runs.</span></span>

<span data-ttu-id="3d31e-112">No instantâneo abaixo, há duas versões do sistema operacional em relação às quais as utilizações da CPU são comparadas para o mesmo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-112">In the snapshot below, there are two OS releases against which the CPU utilizations are compared for the same application.</span></span> 
-   <span data-ttu-id="3d31e-113">A guia utilização da CPU mostra os limites superiores e inferiores de utilização para ambas as versões em percentis 90 e 10, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3d31e-113">The CPU utilization tab shows the upper and lower bounds of utilization for both releases at 90th and 10th percentiles respectively.</span></span> 
-   <span data-ttu-id="3d31e-114">Os gráficos mostram a série de tempo de utilização da CPU juntamente com a utilização média.</span><span class="sxs-lookup"><span data-stu-id="3d31e-114">The graphs show the time series of CPU utilization along with the average utilization.</span></span> 

<span data-ttu-id="3d31e-115">Os clientes agora podem usar a funcionalidade para determinar se a utilização da CPU do aplicativo é impactada pelas atualizações do sistema operacional e especificamente quais processos foram regredidos da execução anterior.</span><span class="sxs-lookup"><span data-stu-id="3d31e-115">Customers can now use the functionality to determine if their application's CPU utilization is impacted by OS updates and specifically which processes have regressed from their previous execution.</span></span>


![Análise de regressão de CPU](Media/cpu-regression-analysis.jpg)

### <a name="relevant-process-identification"></a><span data-ttu-id="3d31e-117">Identificação de processo relevante</span><span class="sxs-lookup"><span data-stu-id="3d31e-117">Relevant Process Identification</span></span> ###

<span data-ttu-id="3d31e-118">Aqui, abordamos como identificar processos regredidos no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-118">Here, we discuss how to identify regressed processes in the application.</span></span> 

<span data-ttu-id="3d31e-119">Analisar a regressão de desempenho requer o acompanhamento de diferentes tipos de contadores de desempenho para cada processo em execução em uma máquina virtual durante a execução do teste.</span><span class="sxs-lookup"><span data-stu-id="3d31e-119">Analyzing performance regression requires tracking different kinds of performance counters for every process running on a virtual machine during the test run.</span></span> 

<span data-ttu-id="3d31e-120">Essa análise captura muitas variáveis para muitos processos para um determinado aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-120">Such analysis captures a lot of variables for a lot of processes for a given application.</span></span> <span data-ttu-id="3d31e-121">Nem todos os processos estão associados a uma executar ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-121">Not all processes are associated with a run or application.</span></span> <span data-ttu-id="3d31e-122">Para resolver esse desafio, um algoritmo de classificação de informações mútuo usando probabilidade e a teoria da informação é aplicado para descobrir quais processos são mais relevantes para um determinado aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-122">To work around this challenge, a mutual information ranking algorithm using probability and information theory is applied to figure out which processes are most relevant for a given application.</span></span> 

<span data-ttu-id="3d31e-123">Um aplicativo pode ser considerado um tipo de variável aleatória discreta enquanto um processo é considerado outro tipo de variável aleatória discreta.</span><span class="sxs-lookup"><span data-stu-id="3d31e-123">An application can be considered one type of discrete random variable while a process is considered another kind of discrete random variable.</span></span> <span data-ttu-id="3d31e-124">A associação das duas variáveis aleatórias é medida usando probabilidades condicionais para relevância.</span><span class="sxs-lookup"><span data-stu-id="3d31e-124">The association of the two random variables is measured using conditional probabilities for relevance.</span></span> 

<span data-ttu-id="3d31e-125">Em seguida, os processos são exibidos na ordem de sua relevância para cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3d31e-125">Processes are then displayed in the order of their relevance for each application.</span></span> <span data-ttu-id="3d31e-126">Você também pode favorito de um subconjunto de processos que podem ser monitorados, por padrão, juntamente com processos relevantes para análise de regressão de CPU.</span><span class="sxs-lookup"><span data-stu-id="3d31e-126">You can also favorite a subset of processes that can be monitored, by default, along with relevant processes for CPU regression analysis.</span></span> <span data-ttu-id="3d31e-127">Depois que uma regressão é detectada, você pode baixar o kit de ferramentas do Analisador de Desempenho Windows e analisar os motivos das regressões de desempenho da CPU.</span><span class="sxs-lookup"><span data-stu-id="3d31e-127">Once a regression is detected, you can download the Windows Performance Analyzer toolkit and analyze reasons for CPU performance regressions.</span></span> 

<span data-ttu-id="3d31e-128">O Windows de desempenho assume o log de rastreamento de eventos (ETL) como entradas e esses arquivos .etl estão disponíveis nos arquivos de log baixáveis para execução de teste no portal.</span><span class="sxs-lookup"><span data-stu-id="3d31e-128">The Windows Performance Analyzer takes event trace log (ETL) as inputs and these .etl files are available in the log files downloadable for test runs on the portal.</span></span> <span data-ttu-id="3d31e-129">Se você quiser saber mais sobre a depuração do desempenho da CPU, consulte a documentação Windows Analisador de Desempenho.</span><span class="sxs-lookup"><span data-stu-id="3d31e-129">If you would like to know more about debugging CPU performance, see the Windows Performance Analyzer documentation.</span></span>

