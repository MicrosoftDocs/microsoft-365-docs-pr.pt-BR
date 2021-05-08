---
title: Investigar entidades em dispositivos que usam a resposta ao vivo no Microsoft Defender para Ponto de Extremidade
description: Acesse um dispositivo usando uma conexão de shell remoto seguro para fazer um trabalho de investigação e tomar ações de resposta imediatas em um dispositivo em tempo real.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fc1c1e0d3f68016651c04521e04ce348e5ab9a65
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246460"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="a656f-104">Investigar entidades em dispositivos usando a resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="a656f-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a656f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a656f-105">**Applies to:**</span></span>
- [<span data-ttu-id="a656f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a656f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a656f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a656f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="a656f-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a656f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a656f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a656f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="a656f-110">A resposta ao vivo dá às equipes de operações de segurança acesso instantâneo a um dispositivo (também chamado de máquina) usando uma conexão de shell remoto.</span><span class="sxs-lookup"><span data-stu-id="a656f-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="a656f-111">Isso permite que você faça um trabalho de investigação aprofundado e tome ações de resposta imediatas para conter prontamente ameaças identificadas em tempo real.</span><span class="sxs-lookup"><span data-stu-id="a656f-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="a656f-112">A resposta ao vivo foi projetada para aprimorar as investigações, permitindo que sua equipe de operações de segurança colete dados forenses, execute scripts, envie entidades suspeitas para análise, correção de ameaças e busca proativamente por ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="a656f-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="a656f-113">Com a resposta ao vivo, os analistas podem realizar todas as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="a656f-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="a656f-114">Execute comandos básicos e avançados para fazer um trabalho de investigação em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="a656f-115">Baixe arquivos como exemplos de malware e resultados de scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a656f-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="a656f-116">Baixar arquivos em segundo plano (novo!).</span><span class="sxs-lookup"><span data-stu-id="a656f-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="a656f-117">Upload um script do PowerShell ou executável para a biblioteca e executá-lo em um dispositivo de um nível de locatário.</span><span class="sxs-lookup"><span data-stu-id="a656f-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="a656f-118">Realizar ou desfazer ações de correção.</span><span class="sxs-lookup"><span data-stu-id="a656f-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a656f-119">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a656f-119">Before you begin</span></span>

<span data-ttu-id="a656f-120">Antes de iniciar uma sessão em um dispositivo, certifique-se de atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a656f-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="a656f-121">**Verifique se você está executando uma versão com suporte do Windows**.</span><span class="sxs-lookup"><span data-stu-id="a656f-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="a656f-122">Os dispositivos devem estar executando uma das seguintes versões do Windows</span><span class="sxs-lookup"><span data-stu-id="a656f-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="a656f-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="a656f-123">**Windows 10**</span></span>
    - <span data-ttu-id="a656f-124">[Versão 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) ou posterior</span><span class="sxs-lookup"><span data-stu-id="a656f-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="a656f-125">[Versão 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) com [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="a656f-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="a656f-126">[Versão 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) com [KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="a656f-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="a656f-127">[Versão 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) com [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="a656f-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="a656f-128">[Versão 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) com [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="a656f-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="a656f-129">**Windows Server 2019 - Somente aplicável para visualização pública**</span><span class="sxs-lookup"><span data-stu-id="a656f-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="a656f-130">Versão 1903 ou (com [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) posteriormente</span><span class="sxs-lookup"><span data-stu-id="a656f-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="a656f-131">Versão 1809 (com [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="a656f-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="a656f-132">**Habilitar a resposta ao vivo na página configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="a656f-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="a656f-133">Você precisará habilitar o recurso de resposta ao vivo na página [Configurações de recursos](advanced-features.md) avançados.</span><span class="sxs-lookup"><span data-stu-id="a656f-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="a656f-134">Somente usuários com funções de administrador global ou de segurança podem editar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="a656f-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="a656f-135">**Habilita a resposta ao vivo para servidores a partir da página de configurações avançadas** (recomendada).</span><span class="sxs-lookup"><span data-stu-id="a656f-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="a656f-136">Somente usuários com funções de administrador global ou de segurança podem editar essas configurações.</span><span class="sxs-lookup"><span data-stu-id="a656f-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="a656f-137">**Verifique se o dispositivo tem um nível de Correção de Automação** atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="a656f-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="a656f-138">Você precisará habilitar, pelo menos, o Nível mínimo de Correção para um determinado Grupo de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a656f-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="a656f-139">Caso contrário, você não poderá estabelecer uma sessão de Resposta Ao Vivo para um membro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="a656f-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="a656f-140">Você receberá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="a656f-140">You'll receive the following error:</span></span>

    ![Imagem da mensagem de erro](images/live-response-error.png)

- <span data-ttu-id="a656f-142">**Habilitar a execução de script de resposta ao** vivo sem assinatura (opcional).</span><span class="sxs-lookup"><span data-stu-id="a656f-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="a656f-143">Permitir o uso de scripts não assinados pode aumentar sua exposição a ameaças.</span><span class="sxs-lookup"><span data-stu-id="a656f-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="a656f-144">A execução de scripts não assinados não é recomendada, pois pode aumentar sua exposição a ameaças.</span><span class="sxs-lookup"><span data-stu-id="a656f-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="a656f-145">No entanto, se você precisar usá-los, será necessário habilitar a configuração na [página Configurações de recursos](advanced-features.md) avançados.</span><span class="sxs-lookup"><span data-stu-id="a656f-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="a656f-146">**Verifique se você tem as permissões apropriadas**.</span><span class="sxs-lookup"><span data-stu-id="a656f-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="a656f-147">Somente usuários que foram provisionados com as permissões apropriadas podem iniciar uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a656f-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="a656f-148">Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a656f-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="a656f-149">A opção de carregar um arquivo na biblioteca só está disponível para aqueles com as permissões RBAC apropriadas.</span><span class="sxs-lookup"><span data-stu-id="a656f-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="a656f-150">O botão está acinzentado para usuários com apenas permissões delegadas.</span><span class="sxs-lookup"><span data-stu-id="a656f-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="a656f-151">Dependendo da função que foi concedida a você, você pode executar comandos básicos ou avançados de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a656f-152">As permissões dos usuários são controladas pela função personalizada do RBAC.</span><span class="sxs-lookup"><span data-stu-id="a656f-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="a656f-153">Visão geral do painel de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="a656f-153">Live response dashboard overview</span></span>
<span data-ttu-id="a656f-154">Quando você inicia uma sessão de resposta ao vivo em um dispositivo, um painel é aberto.</span><span class="sxs-lookup"><span data-stu-id="a656f-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="a656f-155">O painel fornece informações sobre a sessão, como o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a656f-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="a656f-156">Who a sessão</span><span class="sxs-lookup"><span data-stu-id="a656f-156">Who created the session</span></span>
- <span data-ttu-id="a656f-157">Quando a sessão foi iniciada</span><span class="sxs-lookup"><span data-stu-id="a656f-157">When the session started</span></span>
- <span data-ttu-id="a656f-158">A duração da sessão</span><span class="sxs-lookup"><span data-stu-id="a656f-158">The duration of the session</span></span>

<span data-ttu-id="a656f-159">O painel também oferece acesso a:</span><span class="sxs-lookup"><span data-stu-id="a656f-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="a656f-160">Desconectar sessão</span><span class="sxs-lookup"><span data-stu-id="a656f-160">Disconnect session</span></span>
- <span data-ttu-id="a656f-161">Upload arquivos para a biblioteca</span><span class="sxs-lookup"><span data-stu-id="a656f-161">Upload files to the library</span></span> 
- <span data-ttu-id="a656f-162">Console de comando</span><span class="sxs-lookup"><span data-stu-id="a656f-162">Command console</span></span>
- <span data-ttu-id="a656f-163">Log de comando</span><span class="sxs-lookup"><span data-stu-id="a656f-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="a656f-164">Iniciar uma sessão de resposta ao vivo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="a656f-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="a656f-165">Entre no Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a656f-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="a656f-166">Navegue até a página de lista de dispositivos e selecione um dispositivo para investigar.</span><span class="sxs-lookup"><span data-stu-id="a656f-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="a656f-167">A página dispositivos é aberta.</span><span class="sxs-lookup"><span data-stu-id="a656f-167">The devices page opens.</span></span>

3. <span data-ttu-id="a656f-168">Inicie a sessão de resposta ao vivo selecionando **Iniciar sessão de resposta ao vivo**.</span><span class="sxs-lookup"><span data-stu-id="a656f-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="a656f-169">Um console de comando é exibido.</span><span class="sxs-lookup"><span data-stu-id="a656f-169">A command console is displayed.</span></span> <span data-ttu-id="a656f-170">Aguarde enquanto a sessão se conecta ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="a656f-171">Use os comandos integrados para fazer um trabalho de investigação.</span><span class="sxs-lookup"><span data-stu-id="a656f-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="a656f-172">Para obter mais informações, consulte [Comandos de resposta ao vivo](#live-response-commands).</span><span class="sxs-lookup"><span data-stu-id="a656f-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="a656f-173">Após concluir sua investigação, selecione **Desconectar sessão** e, em seguida, **selecione Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a656f-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="a656f-174">Comandos de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="a656f-174">Live response commands</span></span>

<span data-ttu-id="a656f-175">Dependendo da função que foi concedida a você, você pode executar comandos básicos ou avançados de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="a656f-176">As permissões do usuário são controladas por funções personalizadas do RBAC.</span><span class="sxs-lookup"><span data-stu-id="a656f-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="a656f-177">Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a656f-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="a656f-178">A resposta ao vivo é um shell interativo baseado em nuvem, dessa forma, a experiência de comando específica pode variar no tempo de resposta, dependendo da qualidade da rede e da carga do sistema entre o usuário final e o dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="a656f-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="a656f-179">Comandos básicos</span><span class="sxs-lookup"><span data-stu-id="a656f-179">Basic commands</span></span>

<span data-ttu-id="a656f-180">Os comandos a seguir estão disponíveis para funções de usuário que têm a capacidade de executar comandos **básicos** de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="a656f-181">Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a656f-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a656f-182">Comando</span><span class="sxs-lookup"><span data-stu-id="a656f-182">Command</span></span> | <span data-ttu-id="a656f-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="a656f-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="a656f-184">Altera o diretório atual.</span><span class="sxs-lookup"><span data-stu-id="a656f-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="a656f-185">Limpa a tela do console.</span><span class="sxs-lookup"><span data-stu-id="a656f-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="a656f-186">Inicia uma sessão de resposta ao vivo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="a656f-187">Mostra todas as conexões ativas.</span><span class="sxs-lookup"><span data-stu-id="a656f-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="a656f-188">Mostra uma lista de arquivos e subdireários em um diretório.</span><span class="sxs-lookup"><span data-stu-id="a656f-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`drivers` |  <span data-ttu-id="a656f-189">Mostra todos os drivers instalados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-189">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="a656f-190">Coloque o trabalho especificado em primeiro plano em primeiro plano, tornando-o o trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="a656f-190">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="a656f-191">OBSERVAÇÃO: fg tem uma "ID de comando" disponível nos trabalhos, não em um PID</span><span class="sxs-lookup"><span data-stu-id="a656f-191">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="a656f-192">Obter informações sobre um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-192">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="a656f-193">Localiza arquivos por um determinado nome no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-193">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="a656f-194">Baixa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-194">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="a656f-195">Fornece informações de ajuda para comandos de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-195">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="a656f-196">Mostra trabalhos em execução no momento, sua ID e status.</span><span class="sxs-lookup"><span data-stu-id="a656f-196">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="a656f-197">Mostra todos os métodos de persistência conhecidos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-197">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="a656f-198">Mostra todos os processos em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-198">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="a656f-199">Mostra valores do Registro.</span><span class="sxs-lookup"><span data-stu-id="a656f-199">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="a656f-200">Mostra todas as tarefas agendadas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-200">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="a656f-201">Mostra todos os serviços no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-201">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="a656f-202">Define o modo de registro em log do terminal como depuração.</span><span class="sxs-lookup"><span data-stu-id="a656f-202">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="a656f-203">Comandos avançados</span><span class="sxs-lookup"><span data-stu-id="a656f-203">Advanced commands</span></span>
<span data-ttu-id="a656f-204">Os comandos a seguir estão disponíveis para funções de usuário que têm a capacidade de executar **comandos** avançados de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-204">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="a656f-205">Para obter mais informações sobre atribuições de função, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a656f-205">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="a656f-206">Comando</span><span class="sxs-lookup"><span data-stu-id="a656f-206">Command</span></span> | <span data-ttu-id="a656f-207">Descrição</span><span class="sxs-lookup"><span data-stu-id="a656f-207">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="a656f-208">Analisa a entidade com vários mecanismos de rebaixamento para chegar a um veredito.</span><span class="sxs-lookup"><span data-stu-id="a656f-208">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="a656f-209">Executa um script do PowerShell da biblioteca no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-209">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="a656f-210">Lista arquivos que foram carregados na biblioteca de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-210">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="a656f-211">Coloca um arquivo da biblioteca no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-211">Puts a file from the library to the device.</span></span> <span data-ttu-id="a656f-212">Os arquivos são salvos em uma pasta de trabalho e são excluídos quando o dispositivo é reiniciado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a656f-212">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="a656f-213">Correção de uma entidade no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-213">Remediates an entity on the device.</span></span> <span data-ttu-id="a656f-214">A ação de correção variará dependendo do tipo de entidade:</span><span class="sxs-lookup"><span data-stu-id="a656f-214">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="a656f-215">- Arquivo: excluir</span><span class="sxs-lookup"><span data-stu-id="a656f-215">- File: delete</span></span><br><span data-ttu-id="a656f-216">- Processo: parar, excluir arquivo de imagem</span><span class="sxs-lookup"><span data-stu-id="a656f-216">- Process: stop, delete image file</span></span><br><span data-ttu-id="a656f-217">- Serviço: parar, excluir arquivo de imagem</span><span class="sxs-lookup"><span data-stu-id="a656f-217">- Service: stop, delete image file</span></span><br><span data-ttu-id="a656f-218">- Entrada do Registro: excluir</span><span class="sxs-lookup"><span data-stu-id="a656f-218">- Registry entry: delete</span></span><br><span data-ttu-id="a656f-219">- Tarefa agendada: remover</span><span class="sxs-lookup"><span data-stu-id="a656f-219">- Scheduled task: remove</span></span><br><span data-ttu-id="a656f-220">- Item de pasta de inicialização: excluir arquivo</span><span class="sxs-lookup"><span data-stu-id="a656f-220">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="a656f-221">OBSERVAÇÃO: Este comando tem um comando de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="a656f-221">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="a656f-222">Você pode usar `-auto` o comando em conjunto com para executar `remediate` automaticamente o comando de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="a656f-222">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="a656f-223">Restaura uma entidade que foi remediada.</span><span class="sxs-lookup"><span data-stu-id="a656f-223">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="a656f-224">Usar comandos de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="a656f-224">Use live response commands</span></span>

<span data-ttu-id="a656f-225">Os comandos que você pode usar no console seguem princípios semelhantes aos [Windows Comandos](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span><span class="sxs-lookup"><span data-stu-id="a656f-225">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="a656f-226">Os comandos avançados oferecem um conjunto mais robusto de ações que permitem que você tome ações mais poderosas, como baixar e carregar um arquivo, executar scripts no dispositivo e executar ações de correção em uma entidade.</span><span class="sxs-lookup"><span data-stu-id="a656f-226">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="a656f-227">Obter um arquivo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="a656f-227">Get a file from the device</span></span>

<span data-ttu-id="a656f-228">Para cenários em que você gostaria de obter um arquivo de um dispositivo que está investigando, você pode usar o `getfile` comando.</span><span class="sxs-lookup"><span data-stu-id="a656f-228">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="a656f-229">Isso permite que você salve o arquivo do dispositivo para investigação posterior.</span><span class="sxs-lookup"><span data-stu-id="a656f-229">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="a656f-230">Os seguintes limites de tamanho de arquivo se aplicam:</span><span class="sxs-lookup"><span data-stu-id="a656f-230">The following file size limits apply:</span></span>
>- <span data-ttu-id="a656f-231">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="a656f-231">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="a656f-232">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="a656f-232">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="a656f-233">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="a656f-233">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="a656f-234">Baixar um arquivo em segundo plano</span><span class="sxs-lookup"><span data-stu-id="a656f-234">Download a file in the background</span></span>

<span data-ttu-id="a656f-235">Para permitir que sua equipe de operações de segurança continue investigando um dispositivo afetado, os arquivos agora podem ser baixados em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a656f-235">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="a656f-236">Para baixar um arquivo em segundo plano, no console de comando de resposta ao vivo, digite `download <file_path> &` .</span><span class="sxs-lookup"><span data-stu-id="a656f-236">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="a656f-237">Se você estiver esperando um arquivo ser baixado, poderá movê-lo para o segundo plano usando Ctrl + Z.</span><span class="sxs-lookup"><span data-stu-id="a656f-237">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="a656f-238">Para trazer um download de arquivo para o primeiro plano, no console de comando de resposta ao vivo, digite `fg <command_id>` .</span><span class="sxs-lookup"><span data-stu-id="a656f-238">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="a656f-239">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="a656f-239">Here are some examples:</span></span>


|<span data-ttu-id="a656f-240">Comando</span><span class="sxs-lookup"><span data-stu-id="a656f-240">Command</span></span>  |<span data-ttu-id="a656f-241">Função</span><span class="sxs-lookup"><span data-stu-id="a656f-241">What it does</span></span>  |
|---------|---------|
|`getfile "C:\windows\some_file.exe" &`     |<span data-ttu-id="a656f-242">Inicia o download de um arquivo *chamadosome_file.exe* em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a656f-242">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="a656f-243">Retorna um download com a ID do comando *1234* em primeiro plano.</span><span class="sxs-lookup"><span data-stu-id="a656f-243">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="a656f-244">Colocar um arquivo na biblioteca</span><span class="sxs-lookup"><span data-stu-id="a656f-244">Put a file in the library</span></span>

<span data-ttu-id="a656f-245">A resposta ao vivo tem uma biblioteca na qual você pode colocar arquivos.</span><span class="sxs-lookup"><span data-stu-id="a656f-245">Live response has a library where you can put files into.</span></span> <span data-ttu-id="a656f-246">A biblioteca armazena arquivos (como scripts) que podem ser executados em uma sessão de resposta ao vivo no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="a656f-246">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="a656f-247">A resposta ao vivo permite que os scripts do PowerShell seja executados, no entanto, você deve primeiro colocar os arquivos na biblioteca antes de poder executar eles.</span><span class="sxs-lookup"><span data-stu-id="a656f-247">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="a656f-248">Você pode ter uma coleção de scripts do PowerShell que podem ser executados em dispositivos com os que você inicia sessões de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-248">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="a656f-249">Para carregar um arquivo na biblioteca</span><span class="sxs-lookup"><span data-stu-id="a656f-249">To upload a file in the library</span></span>

1. <span data-ttu-id="a656f-250">Clique **Upload arquivo para biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="a656f-250">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="a656f-251">Clique **em Procurar** e selecione o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-251">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="a656f-252">Forneça uma breve descrição.</span><span class="sxs-lookup"><span data-stu-id="a656f-252">Provide a brief description.</span></span>

4. <span data-ttu-id="a656f-253">Especifique se você gostaria de substituir um arquivo com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="a656f-253">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="a656f-254">Se você quiser, saiba quais parâmetros são necessários para o script, marque a caixa de seleção parâmetros de script.</span><span class="sxs-lookup"><span data-stu-id="a656f-254">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="a656f-255">No campo de texto, insira um exemplo e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="a656f-255">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="a656f-256">Clique **em Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a656f-256">Click **Confirm**.</span></span> 

7. <span data-ttu-id="a656f-257">(Opcional) Para verificar se o arquivo foi carregado na biblioteca, execute o `library` comando.</span><span class="sxs-lookup"><span data-stu-id="a656f-257">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="a656f-258">Cancelar um comando</span><span class="sxs-lookup"><span data-stu-id="a656f-258">Cancel a command</span></span>
<span data-ttu-id="a656f-259">A qualquer momento durante uma sessão, você pode cancelar um comando pressionando CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="a656f-259">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="a656f-260">O uso desse atalho não interromperá o comando no lado do agente.</span><span class="sxs-lookup"><span data-stu-id="a656f-260">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="a656f-261">Ele só cancelará o comando no portal.</span><span class="sxs-lookup"><span data-stu-id="a656f-261">It will only cancel the command in the portal.</span></span> <span data-ttu-id="a656f-262">Portanto, a alteração de operações como "correção" pode continuar, enquanto o comando é cancelado.</span><span class="sxs-lookup"><span data-stu-id="a656f-262">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

## <a name="run-a-powershell-script"></a><span data-ttu-id="a656f-263">Executar um script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a656f-263">Run a PowerShell script</span></span> 

<span data-ttu-id="a656f-264">Antes de executar um script do PowerShell, você deve primeiro carregar na biblioteca.</span><span class="sxs-lookup"><span data-stu-id="a656f-264">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="a656f-265">Depois de carregar o script na biblioteca, use o `run` comando para executar o script.</span><span class="sxs-lookup"><span data-stu-id="a656f-265">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="a656f-266">Se você planeja usar um script não assinado na sessão, será necessário habilitar a configuração na [página Configurações de](advanced-features.md) recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="a656f-266">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="a656f-267">Permitir o uso de scripts não assinados pode aumentar sua exposição a ameaças.</span><span class="sxs-lookup"><span data-stu-id="a656f-267">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="a656f-268">Aplicar parâmetros de comando</span><span class="sxs-lookup"><span data-stu-id="a656f-268">Apply command parameters</span></span>

- <span data-ttu-id="a656f-269">Exibir a ajuda do console para saber mais sobre parâmetros de comando.</span><span class="sxs-lookup"><span data-stu-id="a656f-269">View the console help to learn about command parameters.</span></span> <span data-ttu-id="a656f-270">Para saber mais sobre um comando individual, execute:</span><span class="sxs-lookup"><span data-stu-id="a656f-270">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="a656f-271">Ao aplicar parâmetros aos comandos, observe que os parâmetros são manipulados com base em uma ordem fixa:</span><span class="sxs-lookup"><span data-stu-id="a656f-271">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="a656f-272">Ao especificar parâmetros fora da ordem fixa, especifique o nome do parâmetro com um hífen antes de fornecer o valor:</span><span class="sxs-lookup"><span data-stu-id="a656f-272">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="a656f-273">Ao usar comandos com comandos de pré-requisito, você pode usar sinalizadores:</span><span class="sxs-lookup"><span data-stu-id="a656f-273">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="a656f-274">`<command name> -type file -id <file path> - auto` ou `remediate file <file path> - auto`.</span><span class="sxs-lookup"><span data-stu-id="a656f-274">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="a656f-275">Tipos de saída com suporte</span><span class="sxs-lookup"><span data-stu-id="a656f-275">Supported output types</span></span>

<span data-ttu-id="a656f-276">A resposta ao vivo dá suporte a tipos de saída de tabela e formato JSON.</span><span class="sxs-lookup"><span data-stu-id="a656f-276">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="a656f-277">Para cada comando, há um comportamento de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="a656f-277">For each command, there's a default output behavior.</span></span> <span data-ttu-id="a656f-278">Você pode modificar a saída no formato de saída preferencial usando os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="a656f-278">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="a656f-279">Menos campos são mostrados no formato de tabela devido ao espaço limitado.</span><span class="sxs-lookup"><span data-stu-id="a656f-279">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="a656f-280">Para ver mais detalhes na saída, você pode usar o comando de saída JSON para que mais detalhes sejam mostrados.</span><span class="sxs-lookup"><span data-stu-id="a656f-280">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="a656f-281">Pipes de saída com suporte</span><span class="sxs-lookup"><span data-stu-id="a656f-281">Supported output pipes</span></span>

<span data-ttu-id="a656f-282">A resposta ao vivo dá suporte à canalização de saída para CLI e arquivo.</span><span class="sxs-lookup"><span data-stu-id="a656f-282">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="a656f-283">CLI é o comportamento de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="a656f-283">CLI is the default output behavior.</span></span> <span data-ttu-id="a656f-284">Você pode canalar a saída para um arquivo usando o seguinte comando: [comando] > [nomedo arquivo].txt.</span><span class="sxs-lookup"><span data-stu-id="a656f-284">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="a656f-285">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="a656f-285">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="a656f-286">Exibir o log de comandos</span><span class="sxs-lookup"><span data-stu-id="a656f-286">View the command log</span></span>

<span data-ttu-id="a656f-287">Selecione a **guia Log de** comando para ver os comandos usados no dispositivo durante uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a656f-287">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="a656f-288">Cada comando é rastreado com detalhes completos, como:</span><span class="sxs-lookup"><span data-stu-id="a656f-288">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="a656f-289">ID</span><span class="sxs-lookup"><span data-stu-id="a656f-289">ID</span></span>
- <span data-ttu-id="a656f-290">Linha de comando</span><span class="sxs-lookup"><span data-stu-id="a656f-290">Command line</span></span>
- <span data-ttu-id="a656f-291">Duration</span><span class="sxs-lookup"><span data-stu-id="a656f-291">Duration</span></span>
- <span data-ttu-id="a656f-292">Status e barra lateral de entrada ou saída</span><span class="sxs-lookup"><span data-stu-id="a656f-292">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="a656f-293">Limitações</span><span class="sxs-lookup"><span data-stu-id="a656f-293">Limitations</span></span>

- <span data-ttu-id="a656f-294">As sessões de resposta ao vivo são limitadas a 25 sessões de resposta ao vivo por vez.</span><span class="sxs-lookup"><span data-stu-id="a656f-294">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="a656f-295">O valor de tempo de tempo de inatividade da sessão de resposta ao vivo é de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="a656f-295">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="a656f-296">Um usuário pode iniciar até 10 sessões simultâneas.</span><span class="sxs-lookup"><span data-stu-id="a656f-296">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="a656f-297">Um dispositivo só pode estar em uma sessão por vez.</span><span class="sxs-lookup"><span data-stu-id="a656f-297">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="a656f-298">Os seguintes limites de tamanho de arquivo se aplicam:</span><span class="sxs-lookup"><span data-stu-id="a656f-298">The following file size limits apply:</span></span>
   - <span data-ttu-id="a656f-299">`getfile` limite: 3 GB</span><span class="sxs-lookup"><span data-stu-id="a656f-299">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="a656f-300">`fileinfo` limite: 10 GB</span><span class="sxs-lookup"><span data-stu-id="a656f-300">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="a656f-301">`library` limite: 250 MB</span><span class="sxs-lookup"><span data-stu-id="a656f-301">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="a656f-302">Artigo relacionado</span><span class="sxs-lookup"><span data-stu-id="a656f-302">Related article</span></span>
- [<span data-ttu-id="a656f-303">Exemplos de comando de Resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="a656f-303">Live response command examples</span></span>](live-response-command-examples.md)
