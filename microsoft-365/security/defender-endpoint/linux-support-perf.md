---
title: Solucionar problemas de desempenho do Microsoft Defender ATP para Linux
description: Solucionar problemas de desempenho no Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8865da0c8080213f6a2b82f78a6b31983c50409
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688616"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="48350-104">Solucionar problemas de desempenho do Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="48350-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48350-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="48350-105">**Applies to:**</span></span>
- [<span data-ttu-id="48350-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="48350-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48350-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48350-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="48350-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="48350-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="48350-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="48350-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="48350-110">Este artigo fornece algumas etapas gerais que podem ser usadas para reduzir os problemas de desempenho relacionados ao Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="48350-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="48350-111">A proteção em tempo real (RTP) é um recurso do Defender for Endpoint para Linux que monitora e protege continuamente seu dispositivo contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="48350-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="48350-112">Ele consiste no monitoramento de arquivos e processos e outras heurísticas.</span><span class="sxs-lookup"><span data-stu-id="48350-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="48350-113">Dependendo dos aplicativos que você está executando e das características do dispositivo, você pode ter um desempenho suboptimal ao executar o Defender para o Ponto de Extremidade para Linux.</span><span class="sxs-lookup"><span data-stu-id="48350-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="48350-114">Em particular, aplicativos ou processos do sistema que acessam muitos recursos em um curto período de tempo podem levar a problemas de desempenho no Defender para Ponto de Extremidade para Linux.</span><span class="sxs-lookup"><span data-stu-id="48350-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="48350-115">Antes de iniciar, **verifique se outros produtos de segurança não estão sendo executados no dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="48350-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="48350-116">Vários produtos de segurança podem conflitar e afetar o desempenho do host.</span><span class="sxs-lookup"><span data-stu-id="48350-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="48350-117">As etapas a seguir podem ser usadas para solucionar problemas e atenuar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="48350-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="48350-118">Desabilite a proteção em tempo real usando um dos métodos a seguir e observe se o desempenho melhora.</span><span class="sxs-lookup"><span data-stu-id="48350-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="48350-119">Essa abordagem ajuda a restringir se o Defender for Endpoint para Linux está contribuindo para os problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="48350-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="48350-120">Se o dispositivo não for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="48350-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="48350-121">Se seu dispositivo for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada pelo administrador usando as instruções em Definir [preferências](linux-preferences.md)para Defender para Ponto de Extremidade para Linux .</span><span class="sxs-lookup"><span data-stu-id="48350-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="48350-122">Se o problema de desempenho persistir enquanto a proteção em tempo real estiver desligada, a origem do problema poderá ser o componente de detecção e resposta do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="48350-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="48350-123">Nesse caso, entre em contato com o suporte do cliente para obter mais instruções e mitigação.</span><span class="sxs-lookup"><span data-stu-id="48350-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="48350-124">Para encontrar os aplicativos que estão disparando a maioria das verificações, você pode usar estatísticas em tempo real coletadas pelo Defender para Endpoint para Linux.</span><span class="sxs-lookup"><span data-stu-id="48350-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48350-125">Esse recurso está disponível na versão 100.90.70 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="48350-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="48350-126">Esse recurso é habilitado por padrão nos `Dogfood` canais `InsiderFast` e.</span><span class="sxs-lookup"><span data-stu-id="48350-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="48350-127">Se você estiver usando um canal de atualização diferente, esse recurso poderá ser habilitado a partir da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="48350-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="48350-128">Esse recurso requer proteção em tempo real para ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="48350-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="48350-129">Para verificar o status da proteção em tempo real, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="48350-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="48350-130">Verifique se a `real_time_protection_enabled` entrada é `true` .</span><span class="sxs-lookup"><span data-stu-id="48350-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="48350-131">Caso contrário, execute o seguinte comando para habilita-lo:</span><span class="sxs-lookup"><span data-stu-id="48350-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="48350-132">Para coletar estatísticas atuais, execute:</span><span class="sxs-lookup"><span data-stu-id="48350-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="48350-133">O ```--output json``` uso (observe o traço duplo) garante que o formato de saída esteja pronto para análise.</span><span class="sxs-lookup"><span data-stu-id="48350-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="48350-134">A saída desse comando mostrará todos os processos e suas atividades de verificação associadas.</span><span class="sxs-lookup"><span data-stu-id="48350-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="48350-135">Em seu sistema Linux, baixe o analisador Python de **exemplo high_cpu_parser.py** usando o comando:</span><span class="sxs-lookup"><span data-stu-id="48350-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="48350-136">A saída deste comando deve ser semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="48350-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="48350-137">Em seguida, digite os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="48350-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="48350-138">A saída do acima é uma lista dos principais colaboradores para problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="48350-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="48350-139">A primeira coluna é o identificador de processo (PID), a segunda coluna é o nome do processo e a última coluna é o número de arquivos verificados, classificação por impacto.</span><span class="sxs-lookup"><span data-stu-id="48350-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="48350-140">Por exemplo, a saída do comando será algo como o abaixo:</span><span class="sxs-lookup"><span data-stu-id="48350-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
    ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
    27432 None 76703
    73467 actool     1249
    73914 xcodebuild 1081
    73873 bash 1050
    27475 None 836
    1    launchd    407
    73468 ibtool     344
    549  telemetryd_v1   325
    4764 None 228
    125  CrashPlanService 164
    ```

    <span data-ttu-id="48350-141">Para melhorar o desempenho do Defender para Ponto de Extremidade para Linux, localize o que tem o número mais alto sob a linha e `Total files scanned` adicione uma exclusão para ele.</span><span class="sxs-lookup"><span data-stu-id="48350-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="48350-142">Para obter mais informações, [consulte Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="48350-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="48350-143">O aplicativo armazena estatísticas na memória e só mantém o controle da atividade do arquivo desde que foi iniciado e a proteção em tempo real foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="48350-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="48350-144">Os processos que foram lançados antes ou durante períodos em que a proteção em tempo real estava desligada não são contados.</span><span class="sxs-lookup"><span data-stu-id="48350-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="48350-145">Além disso, somente os eventos que dispararam verificações são contados.</span><span class="sxs-lookup"><span data-stu-id="48350-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="48350-146">Configure o Microsoft Defender ATP para Linux com exclusões para os processos ou locais de disco que contribuem para os problemas de desempenho e rehabilitam a proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="48350-146">Configure Microsoft Defender ATP for Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="48350-147">Para obter mais informações, [consulte Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span><span class="sxs-lookup"><span data-stu-id="48350-147">For more information, see [Configure and validate exclusions for Microsoft Defender ATP for Linux](linux-exclusions.md).</span></span>
