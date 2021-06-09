---
title: Solucionar problemas de desempenho
description: Solucionar problemas de alto uso de CPU relacionados ao serviço de proteção em tempo real no Microsoft Defender para Ponto de Extremidade.
keywords: solução de problemas, desempenho, alta utilização da CPU, alto uso da CPU, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: normal
manager: dansimp
ms.date: 04/14/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 1a969b6430914eb2dd667a906dc071d3cd49be8b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625324"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a><span data-ttu-id="27b86-104">Solucionar problemas de desempenho relacionados à proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="27b86-104">Troubleshoot performance issues related to real-time protection</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="27b86-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="27b86-105">**Applies to:**</span></span>

- [<span data-ttu-id="27b86-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="27b86-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
 
<span data-ttu-id="27b86-107">Se o seu sistema estiver tendo altos problemas de uso ou desempenho da CPU relacionados ao serviço de proteção em tempo real no Microsoft Defender para Ponto de Extremidade, você pode enviar um tíquete para o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27b86-107">If your system is having high CPU usage or performance issues related to the real-time protection service in Microsoft Defender for Endpoint, you can submit a ticket to Microsoft support.</span></span> <span data-ttu-id="27b86-108">Siga as etapas em [Coletar Microsoft Defender Antivírus dados de diagnóstico](collect-diagnostic-data.md).</span><span class="sxs-lookup"><span data-stu-id="27b86-108">Follow the steps in [Collect Microsoft Defender Antivirus diagnostic data](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="27b86-109">Como administrador, você também pode solucionar esses problemas por conta própria.</span><span class="sxs-lookup"><span data-stu-id="27b86-109">As an admin, you can also troubleshoot these issues on your own.</span></span> 

<span data-ttu-id="27b86-110">Primeiro, talvez você queira verificar se o problema está sendo causado por outro software.</span><span class="sxs-lookup"><span data-stu-id="27b86-110">First, you might want to check if the issue is being caused by another software.</span></span> <span data-ttu-id="27b86-111">Leia [Verificar com o fornecedor sobre exclusões de antivírus.](#check-with-vendor-for-antivirus-exclusions)</span><span class="sxs-lookup"><span data-stu-id="27b86-111">Read [Check with vendor for antivirus exclusions](#check-with-vendor-for-antivirus-exclusions).</span></span>

<span data-ttu-id="27b86-112">Caso contrário, você pode identificar qual software está relacionado ao problema de desempenho identificado seguindo as etapas em [Analisar o Log de Proteção da Microsoft.](#analyze-the-microsoft-protection-log)</span><span class="sxs-lookup"><span data-stu-id="27b86-112">Otherwise, you can identify which software is related to the identified performance issue by following the steps in [Analyze the Microsoft Protection Log](#analyze-the-microsoft-protection-log).</span></span> 

<span data-ttu-id="27b86-113">Você também pode fornecer logs adicionais para o seu envio para o suporte da Microsoft seguindo as etapas em:</span><span class="sxs-lookup"><span data-stu-id="27b86-113">You can also provide additional logs to your submission to Microsoft support by following the steps in:</span></span>
- [<span data-ttu-id="27b86-114">Capturar logs de processo usando o Monitor de Processo</span><span class="sxs-lookup"><span data-stu-id="27b86-114">Capture process logs using Process Monitor</span></span>](#capture-process-logs-using-process-monitor)
- [<span data-ttu-id="27b86-115">Capturar logs de desempenho usando Windows Gravador de Desempenho</span><span class="sxs-lookup"><span data-stu-id="27b86-115">Capture performance logs using Windows Performance Recorder</span></span>](#capture-performance-logs-using-windows-performance-recorder) 

## <a name="check-with-vendor-for-antivirus-exclusions"></a><span data-ttu-id="27b86-116">Verificar com o fornecedor sobre exclusões de antivírus</span><span class="sxs-lookup"><span data-stu-id="27b86-116">Check with vendor for antivirus exclusions</span></span>

<span data-ttu-id="27b86-117">Se você puder identificar prontamente o software que afeta o desempenho do sistema, vá para a base de dados de conhecimento ou centro de suporte do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="27b86-117">If you can readily identify the software affecting system performance, go to the software vendor's knowledge base or support center.</span></span> <span data-ttu-id="27b86-118">Pesquise se eles têm recomendações sobre exclusões de antivírus.</span><span class="sxs-lookup"><span data-stu-id="27b86-118">Search if they have recommendations about antivirus exclusions.</span></span> <span data-ttu-id="27b86-119">Se o site do fornecedor não os tiver, você poderá abrir um tíquete de suporte com eles e pedir que eles publiquem um.</span><span class="sxs-lookup"><span data-stu-id="27b86-119">If the vendor's website does not have them, you can open a support ticket with them and ask them to publish one.</span></span> 

<span data-ttu-id="27b86-120">Recomendamos que os fornecedores de software sigam as várias diretrizes em Parceria com o setor para [minimizar falsos positivos.](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)</span><span class="sxs-lookup"><span data-stu-id="27b86-120">We recommend that software vendors follow the various guidelines in [Partnering with the industry to minimize false positives](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/).</span></span> <span data-ttu-id="27b86-121">O fornecedor pode enviar seu software por meio do portal de Inteligência de Segurança [do Microsoft Defender (MDSI).](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)</span><span class="sxs-lookup"><span data-stu-id="27b86-121">The vendor can submit their software through the [Microsoft Defender Security Intelligence portal (MDSI)](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).</span></span>


## <a name="analyze-the-microsoft-protection-log"></a><span data-ttu-id="27b86-122">Analisar o Log de Proteção da Microsoft</span><span class="sxs-lookup"><span data-stu-id="27b86-122">Analyze the Microsoft Protection Log</span></span>

<span data-ttu-id="27b86-123">Em **MPLog-xxxxxxxx-xxxxxx.log,** você pode encontrar as informações de impacto de desempenho estimadas do software em execução *como EstimatedImpact*:</span><span class="sxs-lookup"><span data-stu-id="27b86-123">In **MPLog-xxxxxxxx-xxxxxx.log**, you can find the estimated performance impact information of running software as *EstimatedImpact*:</span></span>
    
`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

| <span data-ttu-id="27b86-124">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="27b86-124">Field name</span></span> | <span data-ttu-id="27b86-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="27b86-125">Description</span></span> |
|---|---|
|<span data-ttu-id="27b86-126">ProcessImageName</span><span class="sxs-lookup"><span data-stu-id="27b86-126">ProcessImageName</span></span> | <span data-ttu-id="27b86-127">Processar nome da imagem</span><span class="sxs-lookup"><span data-stu-id="27b86-127">Process image name</span></span> |
| <span data-ttu-id="27b86-128">TotalTime</span><span class="sxs-lookup"><span data-stu-id="27b86-128">TotalTime</span></span> | <span data-ttu-id="27b86-129">A duração cumulativa em milissegundos gastos em verificações de arquivos acessados por esse processo</span><span class="sxs-lookup"><span data-stu-id="27b86-129">The cumulative duration in milliseconds spent in scans of files accessed by this process</span></span> |
|<span data-ttu-id="27b86-130">Contagem</span><span class="sxs-lookup"><span data-stu-id="27b86-130">Count</span></span> | <span data-ttu-id="27b86-131">O número de arquivos verificados acessados por esse processo</span><span class="sxs-lookup"><span data-stu-id="27b86-131">The number of scanned files accessed by this process</span></span> |
|<span data-ttu-id="27b86-132">MaxTime</span><span class="sxs-lookup"><span data-stu-id="27b86-132">MaxTime</span></span> |  <span data-ttu-id="27b86-133">A duração em milissegundos na verificação única mais longa de um arquivo acessado por esse processo</span><span class="sxs-lookup"><span data-stu-id="27b86-133">The duration in milliseconds in the longest single scan of a file accessed by this process</span></span> |
| <span data-ttu-id="27b86-134">MaxTimeFile</span><span class="sxs-lookup"><span data-stu-id="27b86-134">MaxTimeFile</span></span> | <span data-ttu-id="27b86-135">O caminho do arquivo acessado por esse processo para o qual a verificação mais longa de duração `MaxTime` foi registrada</span><span class="sxs-lookup"><span data-stu-id="27b86-135">The path of the file accessed by this process for which the longest scan of `MaxTime` duration was recorded</span></span> |
| <span data-ttu-id="27b86-136">EstimatedImpact</span><span class="sxs-lookup"><span data-stu-id="27b86-136">EstimatedImpact</span></span> | <span data-ttu-id="27b86-137">A porcentagem de tempo gasto em verificações de arquivos acessados por esse processo fora do período em que esse processo experimentou a atividade de verificação</span><span class="sxs-lookup"><span data-stu-id="27b86-137">The percentage of time spent in scans for files accessed by this process out of the period in which this process experienced scan activity</span></span> |

<span data-ttu-id="27b86-138">Se o impacto no desempenho for alto, tente adicionar o processo às exclusões de Caminho/Processo seguindo as etapas em Configurar e validar exclusões para Microsoft Defender Antivírus [verificações](collect-diagnostic-data.md).</span><span class="sxs-lookup"><span data-stu-id="27b86-138">If the performance impact is high, try adding the process to the Path/Process exclusions by following the steps in [Configure and validate exclusions for Microsoft Defender Antivirus scans](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="27b86-139">Se a etapa anterior não resolver o problema, você poderá coletar mais informações por meio do [Monitor](#capture-process-logs-using-process-monitor) de Processo ou do Windows [De](#capture-performance-logs-using-windows-performance-recorder) desempenho nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="27b86-139">If the previous step doesn't solve the problem, you can collect more information through the [Process Monitor](#capture-process-logs-using-process-monitor) or the [Windows Performance Recorder](#capture-performance-logs-using-windows-performance-recorder) in the following sections.</span></span>
     
## <a name="capture-process-logs-using-process-monitor"></a><span data-ttu-id="27b86-140">Capturar logs de processo usando o Monitor de Processo</span><span class="sxs-lookup"><span data-stu-id="27b86-140">Capture process logs using Process Monitor</span></span>

<span data-ttu-id="27b86-141">O Monitor de Processos (ProcMon) é uma ferramenta de monitoramento avançada que pode mostrar processos em tempo real.</span><span class="sxs-lookup"><span data-stu-id="27b86-141">Process Monitor (ProcMon) is an advanced monitoring tool that can show real-time processes.</span></span> <span data-ttu-id="27b86-142">Você pode usar isso para capturar o problema de desempenho enquanto ele está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="27b86-142">You can use this to capture the performance issue as it is occurring.</span></span>

1. <span data-ttu-id="27b86-143">Baixe [o Monitor de Processo v3.60](/sysinternals/downloads/procmon) para uma pasta como `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="27b86-143">Download [Process Monitor v3.60](/sysinternals/downloads/procmon) to a folder like `C:\temp`.</span></span>

2. <span data-ttu-id="27b86-144">Para remover a marca do arquivo da Web:</span><span class="sxs-lookup"><span data-stu-id="27b86-144">To remove the file's mark of the web:</span></span>
    1. <span data-ttu-id="27b86-145">Clique com o botão **direito doProcessMonitor.zip** e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="27b86-145">Right-click **ProcessMonitor.zip** and select **Properties**.</span></span>
    1. <span data-ttu-id="27b86-146">Na guia *Geral,* procure *Segurança*.</span><span class="sxs-lookup"><span data-stu-id="27b86-146">Under the *General* tab, look for *Security*.</span></span>
    1. <span data-ttu-id="27b86-147">Marque a caixa ao lado **de Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="27b86-147">Check the box beside **Unblock**.</span></span>
    1. <span data-ttu-id="27b86-148">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="27b86-148">Select **Apply**.</span></span>
    
    ![Remover o MOTW](images/procmon-motw.png) 

3. <span data-ttu-id="27b86-150">Descomplem o arquivo `C:\temp` para que o caminho da pasta seja `C:\temp\ProcessMonitor` .</span><span class="sxs-lookup"><span data-stu-id="27b86-150">Unzip the file in `C:\temp` so that the folder path will be `C:\temp\ProcessMonitor`.</span></span> 

4. <span data-ttu-id="27b86-151">Copie **ProcMon.exe** para o cliente Windows ou Windows servidor que você está solucionando.</span><span class="sxs-lookup"><span data-stu-id="27b86-151">Copy **ProcMon.exe**  to the Windows client or Windows server you're troubleshooting.</span></span>  

5. <span data-ttu-id="27b86-152">Antes de executar ProcMon, certifique-se de que todos os outros aplicativos não relacionados ao alto problema de uso da CPU sejam fechados.</span><span class="sxs-lookup"><span data-stu-id="27b86-152">Before running ProcMon, make sure all other applications not related to the high CPU usage issue are closed.</span></span> <span data-ttu-id="27b86-153">Isso minimizará o número de processos a verificar.</span><span class="sxs-lookup"><span data-stu-id="27b86-153">Doing this will minimize the number of processes to check.</span></span>

6. <span data-ttu-id="27b86-154">Você pode iniciar ProcMon de duas maneiras.</span><span class="sxs-lookup"><span data-stu-id="27b86-154">You can launch ProcMon in two ways.</span></span>
    1. <span data-ttu-id="27b86-155">Clique com o **ProcMon.exe** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="27b86-155">Right-click **ProcMon.exe** and select **Run as administrator**.</span></span> 
    

        <span data-ttu-id="27b86-156">Como o registro em log é iniciado automaticamente, selecione o ícone de lupa para interromper a captura atual ou usar o atalho de teclado **Ctrl+E**.</span><span class="sxs-lookup"><span data-stu-id="27b86-156">Since logging starts automatically, select the magnifying glass icon  to stop the current capture or use the keyboard shortcut **Ctrl+E**.</span></span>
 
        ![ícone de lupa](images/procmon-magglass.png)

        <span data-ttu-id="27b86-158">Para verificar se você interrompeu a captura, verifique se o ícone da lupa agora aparece com um X vermelho.</span><span class="sxs-lookup"><span data-stu-id="27b86-158">To verify that you have stopped the capture, check if the magnifying glass icon now appears with a red X.</span></span>

        ![barra vermelha](images/procmon-magglass-stop.png)         

        <span data-ttu-id="27b86-160">Em seguida, para limpar a captura anterior, selecione o ícone borracha.</span><span class="sxs-lookup"><span data-stu-id="27b86-160">Next, to clear the earlier capture, select the eraser icon.</span></span>

        ![ícone clear](images/procmon-eraser-clear.png)

        <span data-ttu-id="27b86-162">Ou use o atalho do teclado **Ctrl+X**.</span><span class="sxs-lookup"><span data-stu-id="27b86-162">Or use the keyboard shortcut **Ctrl+X**.</span></span>

    2. <span data-ttu-id="27b86-163">A segunda maneira é executar a linha **de comando** como administrador e, em seguida, a partir do caminho do Monitor de Processo, execute:</span><span class="sxs-lookup"><span data-stu-id="27b86-163">The second way is to run the **command line** as admin, then from the Process Monitor path, run:</span></span>

        ![cmd procmon](images/cmd-procmon.png)
 
        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```
        
        >[!TIP] 
        ><span data-ttu-id="27b86-165">Faça com que a janela ProcMon seja o menor possível ao capturar dados para que você possa iniciar e interromper facilmente o rastreamento.</span><span class="sxs-lookup"><span data-stu-id="27b86-165">Make the ProcMon window as small as possible when capturing data so you can easily start and stop the trace.</span></span>
        > 
        >![Minimizar Procmon](images/procmon-minimize.png)
    
7. <span data-ttu-id="27b86-167">Depois de seguir um dos procedimentos na etapa 6, você verá em seguida uma opção para definir filtros.</span><span class="sxs-lookup"><span data-stu-id="27b86-167">After following one of the procedures in step 6, you'll next see an option to set filters.</span></span> <span data-ttu-id="27b86-168">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="27b86-168">Select **OK**.</span></span> <span data-ttu-id="27b86-169">Você sempre pode filtrar os resultados depois que a captura for concluída.</span><span class="sxs-lookup"><span data-stu-id="27b86-169">You can always filter the results after the capture is completed.</span></span>
 
    ![Filtrar Nome do Processo é Exclusão do Sistema](images/procmon-filter-options.png) 

8. <span data-ttu-id="27b86-171">Para iniciar a captura, selecione o ícone de lupa novamente.</span><span class="sxs-lookup"><span data-stu-id="27b86-171">To start the capture, select the magnifying glass icon again.</span></span>
     
9. <span data-ttu-id="27b86-172">Reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="27b86-172">Reproduce the problem.</span></span>
 
    >[!TIP] 
    ><span data-ttu-id="27b86-173">Aguarde até que o problema seja totalmente reproduzido e, em seguida, anote o data/hora quando o rastreamento foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="27b86-173">Wait for the problem to be fully reproduced, then take note of the timestamp when the trace started.</span></span>

10. <span data-ttu-id="27b86-174">Depois de ter de dois a quatro minutos de atividade de processo durante a condição de alto uso da CPU, pare a captura selecionando o ícone de lupa.</span><span class="sxs-lookup"><span data-stu-id="27b86-174">Once you have two to four minutes of process activity during the high CPU usage condition, stop the capture by selecting the magnifying glass icon.</span></span>

11. <span data-ttu-id="27b86-175">Para salvar a captura com um nome exclusivo e com o formato .pml, selecione **Arquivo** e selecione **Salvar...**. Certifique-se de selecionar os botões de opção **Todos os eventos** e Formato de Monitor de Processo Nativo **(PML).**</span><span class="sxs-lookup"><span data-stu-id="27b86-175">To save the capture with a unique name and with the .pml format, select **File** then select **Save...**. Make sure to select the radio buttons **All events** and **Native Process Monitor Format (PML)**.</span></span>

    ![salvar configurações](images/procmon-savesettings1.png)

12. <span data-ttu-id="27b86-177">Para melhor controle, altere o caminho padrão `C:\temp\ProcessMonitor\LogFile.PML` de para `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` onde:</span><span class="sxs-lookup"><span data-stu-id="27b86-177">For better tracking, change the default path from `C:\temp\ProcessMonitor\LogFile.PML` to `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` where:</span></span>
    - <span data-ttu-id="27b86-178">`%ComputerName%` é o nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="27b86-178">`%ComputerName%` is the device name</span></span>
    - <span data-ttu-id="27b86-179">`MMDDYEAR` é o mês, dia e ano</span><span class="sxs-lookup"><span data-stu-id="27b86-179">`MMDDYEAR` is the month, day, and year</span></span>
    -  <span data-ttu-id="27b86-180">`Repro_of_issue` é o nome do problema que você está tentando reproduzir</span><span class="sxs-lookup"><span data-stu-id="27b86-180">`Repro_of_issue` is the name of the issue you're trying to reproduce</span></span>

    >[!TIP] 
    > <span data-ttu-id="27b86-181">Se você tiver um sistema de trabalho, talvez queira obter um log de exemplo para comparar.</span><span class="sxs-lookup"><span data-stu-id="27b86-181">If you have a working system, you might want to get a sample log to compare.</span></span>

13. <span data-ttu-id="27b86-182">Feche o arquivo .pml e envie-o para o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27b86-182">Zip the .pml file and submit it to Microsoft support.</span></span>


## <a name="capture-performance-logs-using-windows-performance-recorder"></a><span data-ttu-id="27b86-183">Capturar logs de desempenho usando Windows Gravador de Desempenho</span><span class="sxs-lookup"><span data-stu-id="27b86-183">Capture performance logs using Windows Performance Recorder</span></span>

<span data-ttu-id="27b86-184">Você pode usar Windows WPR (Gravador de Desempenho) para incluir informações adicionais no envio ao suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27b86-184">You can use Windows Performance Recorder (WPR) to include additional information in your submission to Microsoft support.</span></span> <span data-ttu-id="27b86-185">WPR é uma ferramenta de gravação poderosa que cria Rastreamento de Eventos para Windows gravações.</span><span class="sxs-lookup"><span data-stu-id="27b86-185">WPR is a powerful recording tool that creates Event Tracing for Windows recordings.</span></span> 

<span data-ttu-id="27b86-186">WPR faz parte do Windows Kit de Avaliação e Implantação (Windows ADK) e pode ser baixado do Download e instalar o [Windows ADK](/windows-hardware/get-started/adk-install).</span><span class="sxs-lookup"><span data-stu-id="27b86-186">WPR is part of the Windows Assessment and Deployment Kit (Windows ADK) and can be downloaded from [Download and install the Windows ADK](/windows-hardware/get-started/adk-install).</span></span> <span data-ttu-id="27b86-187">Você também pode baixá-lo como parte do Windows 10 Software Development Kit [em Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).</span><span class="sxs-lookup"><span data-stu-id="27b86-187">You can also download it as part of the Windows 10 Software Development Kit at [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).</span></span>

<span data-ttu-id="27b86-188">Você pode usar a interface do usuário WPR seguindo as etapas em Capturar logs de desempenho usando a interface do usuário [WPR](#capture-performance-logs-using-the-wpr-ui).</span><span class="sxs-lookup"><span data-stu-id="27b86-188">You can use the WPR user interface by following the steps in [Capture performance logs using the WPR UI](#capture-performance-logs-using-the-wpr-ui).</span></span> 

<span data-ttu-id="27b86-189">Como alternativa, você também pode usar a ferramenta de linha de comando *wpr.exe*, que está disponível no Windows 8 e versões posteriores seguindo as etapas em Capturar logs de desempenho usando a [CLI WPR](#capture-performance-logs-using-the-wpr-cli).</span><span class="sxs-lookup"><span data-stu-id="27b86-189">Alternatively, you can also use the command-line tool *wpr.exe*, which is available in Windows 8 and later versions  by following the steps in [Capture performance logs using the WPR CLI](#capture-performance-logs-using-the-wpr-cli).</span></span>


### <a name="capture-performance-logs-using-the-wpr-ui"></a><span data-ttu-id="27b86-190">Capturar logs de desempenho usando a interface do usuário WPR</span><span class="sxs-lookup"><span data-stu-id="27b86-190">Capture performance logs using the WPR UI</span></span>

>[!TIP]
><span data-ttu-id="27b86-191">Se você tiver vários dispositivos em que o problema está ocorrendo, use o que tem a maior quantidade de RAM.</span><span class="sxs-lookup"><span data-stu-id="27b86-191">If you have multiple devices where the issue is occurring, use the one which has the most amount of RAM.</span></span>

1. <span data-ttu-id="27b86-192">Baixe e instale o WPR.</span><span class="sxs-lookup"><span data-stu-id="27b86-192">Download and install WPR.</span></span>

2. <span data-ttu-id="27b86-193">Em *Windows Kits,* clique com o botão direito do **mouse Windows Performance Recorder**.</span><span class="sxs-lookup"><span data-stu-id="27b86-193">Under *Windows Kits*, right-click **Windows Performance Recorder**.</span></span> 

    ![Menu Iniciar](images/wpr-01.png)

    <span data-ttu-id="27b86-195">Selecione **Mais**.</span><span class="sxs-lookup"><span data-stu-id="27b86-195">Select **More**.</span></span> <span data-ttu-id="27b86-196">Selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="27b86-196">Select **Run as administrator**.</span></span>

3. <span data-ttu-id="27b86-197">Quando a caixa de diálogo Controle de Conta de Usuário for exibida, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="27b86-197">When the User Account Control dialog box appears, select **Yes**.</span></span>

    ![UAC](images/wpt-yes.png)

4. <span data-ttu-id="27b86-199">Em seguida, baixe o perfil de análise do [Microsoft Defender para Ponto](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) de Extremidade e salve uma pasta como `MDAV.wprp` `C:\temp` .</span><span class="sxs-lookup"><span data-stu-id="27b86-199">Next, download the [Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) profile and save as `MDAV.wprp` to a folder like `C:\temp`.</span></span> 
     
5. <span data-ttu-id="27b86-200">Na caixa de diálogo WPR, selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="27b86-200">On the WPR dialog box, select **More options**.</span></span>

    ![Selecionar mais opções](images/wpr-03.png)

6. <span data-ttu-id="27b86-202">Selecione **Adicionar Perfis...** e navegue até o caminho do `MDAV.wprp` arquivo.</span><span class="sxs-lookup"><span data-stu-id="27b86-202">Select **Add Profiles...** and browse to the path of the `MDAV.wprp` file.</span></span>

7. <span data-ttu-id="27b86-203">Depois disso, você deverá ver um novo conjunto de perfis em *Medidas personalizadas* chamadas *Microsoft Defender para Análise* do Ponto de Extremidade abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="27b86-203">After that, you should see a new profile set under *Custom measurements* named *Microsoft Defender for Endpoint analysis* underneath it.</span></span>

    ![in-file](images/wpr-infile.png)

    >[!WARNING]
    ><span data-ttu-id="27b86-205">Se o Windows Server tiver 64 GB de RAM ou mais, use a medida personalizada `Microsoft Defender for Endpoint analysis for large servers` em vez de `Microsoft Defender for Endpoint analysis` .</span><span class="sxs-lookup"><span data-stu-id="27b86-205">If your Windows Server has 64 GB of RAM or more, use the custom measurement `Microsoft Defender for Endpoint analysis for large servers` instead of `Microsoft Defender for Endpoint analysis`.</span></span> <span data-ttu-id="27b86-206">Caso contrário, seu sistema poderia consumir uma grande quantidade de memória de pool não páginada ou buffers que podem levar à instabilidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="27b86-206">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span> <span data-ttu-id="27b86-207">Você pode escolher quais perfis adicionar expandindo **a Análise de Recursos**.</span><span class="sxs-lookup"><span data-stu-id="27b86-207">You can choose which profiles to add by expanding **Resource Analysis**.</span></span> <span data-ttu-id="27b86-208">Esse perfil personalizado fornece o contexto necessário para análise detalhada de desempenho.</span><span class="sxs-lookup"><span data-stu-id="27b86-208">This custom profile provides the necessary context for in-depth performance analysis.</span></span>
 
8. <span data-ttu-id="27b86-209">Para usar o perfil de análise detalhado da medida personalizada do Microsoft Defender for Endpoint na interface do usuário WPR:</span><span class="sxs-lookup"><span data-stu-id="27b86-209">To use the custom measurement Microsoft Defender for Endpoint verbose analysis profile in the WPR UI:</span></span>

    1. <span data-ttu-id="27b86-210">Verifique se nenhum perfil está selecionado nos grupos *Triagem* de primeiro nível, Análise *de Recursos* e Análise *de Cenário.*</span><span class="sxs-lookup"><span data-stu-id="27b86-210">Ensure no profiles are selected under the *First-level triage*, *Resource Analysis* and *Scenario Analysis* groups.</span></span>
    2. <span data-ttu-id="27b86-211">Selecione **Medidas personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="27b86-211">Select **Custom measurements**.</span></span>
    3. <span data-ttu-id="27b86-212">Selecione **Microsoft Defender para análise de ponto de extremidade**.</span><span class="sxs-lookup"><span data-stu-id="27b86-212">Select **Microsoft Defender for Endpoint analysis**.</span></span>
    4. <span data-ttu-id="27b86-213">Selecione **Verbose** em *Nível de* detalhes.</span><span class="sxs-lookup"><span data-stu-id="27b86-213">Select **Verbose** under *Detail* level.</span></span>
    1. <span data-ttu-id="27b86-214">Selecione **Arquivo ou** Memória **no** modo Log.</span><span class="sxs-lookup"><span data-stu-id="27b86-214">Select **File** or **Memory** under Logging mode.</span></span> 

    >[!important]
    ><span data-ttu-id="27b86-215">Você deve selecionar *Arquivo para* usar o modo de registro em log de arquivos se o problema de desempenho puder ser reproduzido diretamente pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="27b86-215">You should select *File* to use the file logging mode if the performance issue can be reproduced directly by the user.</span></span> <span data-ttu-id="27b86-216">A maioria dos problemas se enquadra nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="27b86-216">Most issues fall under this category.</span></span> <span data-ttu-id="27b86-217">No entanto, se o usuário não puder reproduzir diretamente o problema, mas puder notá-lo facilmente depois que o problema ocorrer, o usuário deverá selecionar *Memória* para usar o modo de registro em log de memória.</span><span class="sxs-lookup"><span data-stu-id="27b86-217">However, if the user cannot directly reproduce the issue but can easily notice it once the issue occurs, the user should select *Memory* to use the memory logging mode.</span></span> <span data-ttu-id="27b86-218">Isso garante que o log de rastreamento não seja inflado excessivamente devido ao tempo de longo prazo.</span><span class="sxs-lookup"><span data-stu-id="27b86-218">This ensures that the trace log will not inflate excessively due to the long run time.</span></span>

9. <span data-ttu-id="27b86-219">Agora você está pronto para coletar dados.</span><span class="sxs-lookup"><span data-stu-id="27b86-219">Now you're ready to collect data.</span></span> <span data-ttu-id="27b86-220">Saia de todos os aplicativos que não são relevantes para reproduzir o problema de desempenho.</span><span class="sxs-lookup"><span data-stu-id="27b86-220">Exit all the applications that are not relevant to reproducing the performance issue.</span></span> <span data-ttu-id="27b86-221">Você pode selecionar **Ocultar opções** para manter o espaço ocupado pela janela WPR pequena.</span><span class="sxs-lookup"><span data-stu-id="27b86-221">You can select **Hide options** to keep the space occupied by the WPR window small.</span></span>

    ![Opções de hipe](images/wpr-08.png)

    >[!TIP]
    ><span data-ttu-id="27b86-223">Tente iniciar o rastreamento em segundos inteiros.</span><span class="sxs-lookup"><span data-stu-id="27b86-223">Try starting the trace at whole number seconds.</span></span> <span data-ttu-id="27b86-224">Por exemplo, 01:30:00.</span><span class="sxs-lookup"><span data-stu-id="27b86-224">For instance, 01:30:00.</span></span> <span data-ttu-id="27b86-225">Isso facilitará a análise dos dados.</span><span class="sxs-lookup"><span data-stu-id="27b86-225">This will make it easier to analyze the data.</span></span> <span data-ttu-id="27b86-226">Tente também manter o controle do data/hora exato de quando o problema é reproduzido.</span><span class="sxs-lookup"><span data-stu-id="27b86-226">Also try to keep track of the timestamp of exactly when the issue is reproduced.</span></span>

10. <span data-ttu-id="27b86-227">Selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="27b86-227">Select **Start**.</span></span>

    ![Selecionar início do rastreamento](images/wpr-09.png)

11. <span data-ttu-id="27b86-229">Reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="27b86-229">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="27b86-230">Mantenha a coleção de dados em até cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="27b86-230">Keep the data collection to no more than five minutes.</span></span> <span data-ttu-id="27b86-231">Dois a três minutos é um bom intervalo, pois muitos dados estão sendo coletados.</span><span class="sxs-lookup"><span data-stu-id="27b86-231">Two to three minutes is a good range since a lot of data is being collected.</span></span>

12. <span data-ttu-id="27b86-232">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27b86-232">Select **Save**.</span></span>

    ![Selecionar salvar](images/wpr-10.png)

13. <span data-ttu-id="27b86-234">Preencha **Digite uma descrição detalhada do problema:** com informações sobre o problema e como você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="27b86-234">Fill up **Type in a detailed description of the problem:** with information about the problem and how you reproduced the issue.</span></span>

    ![Preencher detalhes](images/wpr-12.png)

    1. <span data-ttu-id="27b86-236">Selecione **Nome do Arquivo:** para determinar onde o arquivo de rastreamento será salvo.</span><span class="sxs-lookup"><span data-stu-id="27b86-236">Select **File Name:** to determine where your trace file will be saved.</span></span> <span data-ttu-id="27b86-237">Por padrão, ele 1.is salvo em `%user%\Documents\WPR Files\` .</span><span class="sxs-lookup"><span data-stu-id="27b86-237">By default, it 1.is saved to `%user%\Documents\WPR Files\`.</span></span>
    1. <span data-ttu-id="27b86-238">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="27b86-238">Select **Save**.</span></span>

14. <span data-ttu-id="27b86-239">Aguarde enquanto o rastreamento está sendo mesclado.</span><span class="sxs-lookup"><span data-stu-id="27b86-239">Wait while the trace is being merged.</span></span>

    ![Rastreamento geral de coleta de WPR](images/wpr-13.png)

15. <span data-ttu-id="27b86-241">Depois que o rastreamento for salvo, selecione **Abrir pasta**.</span><span class="sxs-lookup"><span data-stu-id="27b86-241">Once the trace is saved, select **Open folder**.</span></span>

    ![Rastreamento WPR salvo](images/wpr-14.png)

    <span data-ttu-id="27b86-243">Inclua o arquivo e a pasta no seu envio para o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27b86-243">Include both the file and the folder in your submission to Microsoft support.</span></span>

    ![Arquivo e pasta](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a><span data-ttu-id="27b86-245">Capturar logs de desempenho usando a CLI WPR</span><span class="sxs-lookup"><span data-stu-id="27b86-245">Capture performance logs using the WPR CLI</span></span>

<span data-ttu-id="27b86-246">A ferramenta de linha *de comandowpr.exe* faz parte do sistema operacional a partir do Windows 8.</span><span class="sxs-lookup"><span data-stu-id="27b86-246">The command-line tool *wpr.exe* is part of the operating system starting with Windows 8.</span></span> <span data-ttu-id="27b86-247">Para coletar um rastreamento WPR usando a ferramenta de linha de comando wpr.exe:</span><span class="sxs-lookup"><span data-stu-id="27b86-247">To collect a WPR trace using the command-line tool wpr.exe:</span></span>

1. <span data-ttu-id="27b86-248">Baixe o perfil de análise **[do Microsoft Defender para Ponto](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** de Extremidade para rastreamentos de desempenho para um arquivo nomeado em um diretório local como `MDAV.wprp` `C:\traces` .</span><span class="sxs-lookup"><span data-stu-id="27b86-248">Download **[Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** profile for performance traces to a file named `MDAV.wprp` in a local directory such as `C:\traces`.</span></span>

3. <span data-ttu-id="27b86-249">Clique com o botão direito do mouse no **ícone menu** Iniciar e selecione **Windows PowerShell (Administrador)** ou Prompt de **Comando (Administrador)** para abrir uma janela de prompt de comando de administrador.</span><span class="sxs-lookup"><span data-stu-id="27b86-249">Right-click the **Start Menu** icon and select **Windows PowerShell (Admin)** or **Command Prompt (Admin)** to open an Admin command prompt window.</span></span>

4. <span data-ttu-id="27b86-250">Quando a caixa de diálogo Controle de Conta de Usuário for exibida, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="27b86-250">When the User Account Control dialog box appears, select **Yes**.</span></span>

5. <span data-ttu-id="27b86-251">No prompt elevado, execute o seguinte comando para iniciar um rastreamento de desempenho do Microsoft Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="27b86-251">At the elevated prompt, run the following command to start a Microsoft Defender for Endpoint performance trace:</span></span>

    ```console
    wpr.exe -start C:\traces\MDAV.wprp!WD.Verbose -filemode
    ```
    
    >[!WARNING]
    ><span data-ttu-id="27b86-252">Se seu Windows Server tiver 64 GB ou RAM ou mais, use perfis e, em vez de `WDForLargeServers.Light` `WDForLargeServers.Verbose` perfis `WD.Light` e , `WD.Verbose` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="27b86-252">If your Windows Server has 64 GB or RAM or more, use profiles `WDForLargeServers.Light` and `WDForLargeServers.Verbose` instead of profiles `WD.Light` and `WD.Verbose`, respectively.</span></span> <span data-ttu-id="27b86-253">Caso contrário, seu sistema poderia consumir uma grande quantidade de memória de pool não páginada ou buffers que podem levar à instabilidade do sistema.</span><span class="sxs-lookup"><span data-stu-id="27b86-253">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span>

6. <span data-ttu-id="27b86-254">Reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="27b86-254">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="27b86-255">Mantenha a coleção de dados não para mais de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="27b86-255">Keep the data collection no to more than five minutes.</span></span>  <span data-ttu-id="27b86-256">Dependendo do cenário, dois a três minutos é um bom intervalo, pois muitos dados estão sendo coletados.</span><span class="sxs-lookup"><span data-stu-id="27b86-256">Depending on the scenario, two to three minutes is a good range since a lot of data is being collected.</span></span>

7. <span data-ttu-id="27b86-257">No prompt elevado, execute o seguinte comando para interromper o rastreamento de desempenho, fornecendo informações sobre o problema e como você reproduziu o problema:</span><span class="sxs-lookup"><span data-stu-id="27b86-257">At the elevated prompt, run the following command to stop the performance trace, making sure to provide information about the problem and how you reproduced the issue:</span></span>

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

8. <span data-ttu-id="27b86-258">Aguarde até que o rastreamento seja mesclado.</span><span class="sxs-lookup"><span data-stu-id="27b86-258">Wait until the trace is merged.</span></span> 

9. <span data-ttu-id="27b86-259">Inclua o arquivo e a pasta no seu envio para o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27b86-259">Include both the file and the folder in your submission to Microsoft support.</span></span>

## <a name="see-also"></a><span data-ttu-id="27b86-260">Confira também</span><span class="sxs-lookup"><span data-stu-id="27b86-260">See also</span></span>

- [<span data-ttu-id="27b86-261">Coletar Microsoft Defender Antivírus dados de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="27b86-261">Collect Microsoft Defender Antivirus diagnostic data</span></span>](collect-diagnostic-data.md)
- [<span data-ttu-id="27b86-262">Configurar e validar exclusões para Microsoft Defender Antivírus verificações</span><span class="sxs-lookup"><span data-stu-id="27b86-262">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
