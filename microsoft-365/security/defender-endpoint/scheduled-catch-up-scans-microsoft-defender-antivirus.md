---
title: Agendar verificações rápidas e completas regulares com o Microsoft Defender Antivírus
description: Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas
keywords: verificação rápida, verificação completa, rápida versus completa, verificação de agendamento, diariamente, semanal, hora, agendada, recorrente, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689870"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="60859-104">Configurar verificações rápidas ou completas agendadas do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="60859-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="60859-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="60859-105">**Applies to:**</span></span>

- [<span data-ttu-id="60859-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="60859-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="60859-107">Por padrão, o Microsoft Defender Antivírus verifica se há uma atualização 15 minutos antes da hora de qualquer verificação agendada.</span><span class="sxs-lookup"><span data-stu-id="60859-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="60859-108">Você pode Gerenciar a agenda para quando as atualizações de proteção devem ser baixadas e [aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) para substituir esse padrão.</span><span class="sxs-lookup"><span data-stu-id="60859-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="60859-109">Além da proteção sempre em tempo [](run-scan-microsoft-defender-antivirus.md) real e verificações sob demanda, você pode configurar verificações regulares agendadas.</span><span class="sxs-lookup"><span data-stu-id="60859-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="60859-110">Você pode configurar o tipo de verificação, quando a verificação deve ocorrer e se [a](manage-protection-updates-microsoft-defender-antivirus.md) verificação deve ocorrer após uma atualização de proteção ou se o ponto de extremidade está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="60859-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="60859-111">Você também pode especificar quando verificações especiais para concluir a correção devem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="60859-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="60859-112">Este artigo descreve como configurar verificações agendadas com Política de Grupo, cmdlets do PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="60859-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="60859-113">Você também pode configurar verificações de agendamentos com [o Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) ou o Microsoft [Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="60859-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="60859-114">Para configurar as configurações da Política de Grupo descritas neste artigo</span><span class="sxs-lookup"><span data-stu-id="60859-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="60859-115">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="60859-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="60859-116">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="60859-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="60859-117">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="60859-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="60859-118">Expanda a árvore **para componentes do Windows > o Microsoft Defender Antivírus** e, em seguida, o **Local** especificado na tabela abaixo.</span><span class="sxs-lookup"><span data-stu-id="60859-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="60859-119">Clique duas vezes na **configuração de** política, conforme especificado na tabela abaixo, e de definir a opção para a configuração desejada.</span><span class="sxs-lookup"><span data-stu-id="60859-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="60859-120">Clique **em OK** e repita para quaisquer outras configurações.</span><span class="sxs-lookup"><span data-stu-id="60859-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="60859-121">Consulte também [Os tópicos Gerenciar quando](manage-protection-update-schedule-microsoft-defender-antivirus.md) as atualizações de proteção devem ser baixadas e aplicadas e Impedir ou permitir que os usuários modifiquem [localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) os tópicos das configurações de política.</span><span class="sxs-lookup"><span data-stu-id="60859-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="60859-122">Verificação rápida versus verificação completa e verificação personalizada</span><span class="sxs-lookup"><span data-stu-id="60859-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="60859-123">Ao configurar verificações agendadas, você pode configurar se a verificação deve ser completa ou rápida.</span><span class="sxs-lookup"><span data-stu-id="60859-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="60859-124">Verificações rápidas analisam todos os locais onde pode haver malware registrado para começar com o sistema, como chaves do Registro e pastas de inicialização conhecidas do Windows.</span><span class="sxs-lookup"><span data-stu-id="60859-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="60859-125">Combinado com a funcionalidade de proteção sempre em tempo [real](configure-real-time-protection-microsoft-defender-antivirus.md) - que revisa os arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta - uma verificação rápida ajuda a fornecer uma cobertura forte tanto para malware que começa com o sistema quanto o malware no nível do kernel.</span><span class="sxs-lookup"><span data-stu-id="60859-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="60859-126">Na maioria das instâncias, isso significa que uma verificação rápida é adequada para encontrar malware que não foi escolhido pela proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="60859-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="60859-127">Uma verificação completa pode ser útil em pontos de extremidade que encontraram uma ameaça de malware para identificar se há componentes inativos que exigem uma limpeza mais completa.</span><span class="sxs-lookup"><span data-stu-id="60859-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="60859-128">Nesta instância, talvez você queira usar uma verificação completa ao executar uma verificação sob [demanda.](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="60859-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="60859-129">Uma verificação personalizada permite que você especifique os arquivos e pastas a examinar, como uma unidade USB.</span><span class="sxs-lookup"><span data-stu-id="60859-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="60859-130">Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="60859-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="60859-131">Configurar verificações agendadas</span><span class="sxs-lookup"><span data-stu-id="60859-131">Set up scheduled scans</span></span>

<span data-ttu-id="60859-132">As verificações agendadas serão realizadas no dia e hora especificados.</span><span class="sxs-lookup"><span data-stu-id="60859-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="60859-133">Você pode usar a Política de Grupo, o PowerShell e o WMI para configurar verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="60859-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="60859-134">Se um computador estiver desconectado e em execução na bateria durante uma verificação completa agendada, a verificação agendada será interrompida com o evento 1002, que afirma que a verificação parou antes da conclusão.</span><span class="sxs-lookup"><span data-stu-id="60859-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="60859-135">O Microsoft Defender Antivírus executará uma verificação completa na próxima hora agendada.</span><span class="sxs-lookup"><span data-stu-id="60859-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="60859-136">Usar a Política de Grupo para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="60859-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="60859-137">Local</span><span class="sxs-lookup"><span data-stu-id="60859-137">Location</span></span> | <span data-ttu-id="60859-138">Setting</span><span class="sxs-lookup"><span data-stu-id="60859-138">Setting</span></span> | <span data-ttu-id="60859-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="60859-139">Description</span></span> | <span data-ttu-id="60859-140">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="60859-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="60859-141">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-141">Scan</span></span> | <span data-ttu-id="60859-142">Especificar o tipo de verificação a ser usado para uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="60859-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="60859-143">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="60859-143">Quick scan</span></span> |
|<span data-ttu-id="60859-144">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-144">Scan</span></span> | <span data-ttu-id="60859-145">Especificar o dia da semana para executar uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="60859-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="60859-146">Especifique o dia (ou nunca) para executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="60859-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="60859-147">Nunca</span><span class="sxs-lookup"><span data-stu-id="60859-147">Never</span></span> |
|<span data-ttu-id="60859-148">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-148">Scan</span></span> | <span data-ttu-id="60859-149">Especificar a hora do dia para executar uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="60859-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="60859-150">Especifique o número de minutos após a meia-noite (por exemplo, insira **60** para 1 da manhã).</span><span class="sxs-lookup"><span data-stu-id="60859-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="60859-151">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="60859-151">2 a.m.</span></span> |
|<span data-ttu-id="60859-152">Root</span><span class="sxs-lookup"><span data-stu-id="60859-152">Root</span></span> | <span data-ttu-id="60859-153">Randomize tempos de tarefa agendados</span><span class="sxs-lookup"><span data-stu-id="60859-153">Randomize scheduled task times</span></span> |<span data-ttu-id="60859-154">No Microsoft Defender Antivírus: randomize a hora de início da verificação para qualquer intervalo de 0 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="60859-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="60859-155">No FEP/SCEP: aleatoriamente para qualquer intervalo mais ou menos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="60859-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="60859-156">Isso pode ser útil em implantações VM ou VDI.</span><span class="sxs-lookup"><span data-stu-id="60859-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="60859-157">Habilitado</span><span class="sxs-lookup"><span data-stu-id="60859-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="60859-158">Usar cmdlets do PowerShell para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="60859-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="60859-159">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60859-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="60859-160">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="60859-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="60859-161">Usar a Instrução de Gerenciamento do Windows (WMI) para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="60859-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="60859-162">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="60859-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="60859-163">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="60859-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="60859-164">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="60859-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="60859-165">Iniciar verificações agendadas somente quando o ponto de extremidade não estiver em uso</span><span class="sxs-lookup"><span data-stu-id="60859-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="60859-166">Você pode definir a verificação agendada para ocorrer somente quando o ponto de extremidade estiver ligado, mas não estiver em uso com a Política de Grupo, o PowerShell ou o WMI.</span><span class="sxs-lookup"><span data-stu-id="60859-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="60859-167">Essas verificações não cumprirão a configuração de limitador de CPU e tirarão total proveito dos recursos disponíveis para concluir a verificação o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="60859-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="60859-168">Usar a Política de Grupo para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="60859-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="60859-169">Local</span><span class="sxs-lookup"><span data-stu-id="60859-169">Location</span></span> | <span data-ttu-id="60859-170">Setting</span><span class="sxs-lookup"><span data-stu-id="60859-170">Setting</span></span> | <span data-ttu-id="60859-171">Descrição</span><span class="sxs-lookup"><span data-stu-id="60859-171">Description</span></span> | <span data-ttu-id="60859-172">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="60859-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="60859-173">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-173">Scan</span></span> | <span data-ttu-id="60859-174">Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso</span><span class="sxs-lookup"><span data-stu-id="60859-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="60859-175">As verificações agendadas não serão executados, a menos que o computador esteja, mas não esteja em uso</span><span class="sxs-lookup"><span data-stu-id="60859-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="60859-176">Habilitado</span><span class="sxs-lookup"><span data-stu-id="60859-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="60859-177">Usar cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="60859-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="60859-178">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60859-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="60859-179">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="60859-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="60859-180">Usar a Instrução de Gerenciamento do Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="60859-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="60859-181">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="60859-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="60859-182">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="60859-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="60859-183">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="60859-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="60859-184">Configurar quando verificações completas devem ser executados para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="60859-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="60859-185">Algumas ameaças podem exigir uma verificação completa para concluir sua remoção e correção.</span><span class="sxs-lookup"><span data-stu-id="60859-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="60859-186">Você pode agendar quando essas verificações devem ocorrer com a Política de Grupo, o PowerShell ou o WMI.</span><span class="sxs-lookup"><span data-stu-id="60859-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="60859-187">Usar a Política de Grupo para agendar verificações necessárias para correção</span><span class="sxs-lookup"><span data-stu-id="60859-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="60859-188">Local</span><span class="sxs-lookup"><span data-stu-id="60859-188">Location</span></span> | <span data-ttu-id="60859-189">Setting</span><span class="sxs-lookup"><span data-stu-id="60859-189">Setting</span></span> | <span data-ttu-id="60859-190">Descrição</span><span class="sxs-lookup"><span data-stu-id="60859-190">Description</span></span> | <span data-ttu-id="60859-191">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="60859-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="60859-192">Correção</span><span class="sxs-lookup"><span data-stu-id="60859-192">Remediation</span></span> | <span data-ttu-id="60859-193">Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="60859-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="60859-194">Especifique o dia (ou nunca) para executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="60859-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="60859-195">Nunca</span><span class="sxs-lookup"><span data-stu-id="60859-195">Never</span></span> |
|<span data-ttu-id="60859-196">Correção</span><span class="sxs-lookup"><span data-stu-id="60859-196">Remediation</span></span> | <span data-ttu-id="60859-197">Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="60859-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="60859-198">Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã)</span><span class="sxs-lookup"><span data-stu-id="60859-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="60859-199">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="60859-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="60859-200">Usar cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="60859-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="60859-201">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60859-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="60859-202">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="60859-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="60859-203">Usar a Instrução de Gerenciamento do Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="60859-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="60859-204">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="60859-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="60859-205">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="60859-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="60859-206">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="60859-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="60859-207">Configurar verificações rápidas diárias</span><span class="sxs-lookup"><span data-stu-id="60859-207">Set up daily quick scans</span></span>

<span data-ttu-id="60859-208">Você pode habilitar uma verificação rápida diária que pode ser executado além de outras verificações agendadas com a Política de Grupo, o PowerShell ou o WMI.</span><span class="sxs-lookup"><span data-stu-id="60859-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="60859-209">Usar a Política de Grupo para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="60859-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="60859-210">Local</span><span class="sxs-lookup"><span data-stu-id="60859-210">Location</span></span> | <span data-ttu-id="60859-211">Setting</span><span class="sxs-lookup"><span data-stu-id="60859-211">Setting</span></span> | <span data-ttu-id="60859-212">Descrição</span><span class="sxs-lookup"><span data-stu-id="60859-212">Description</span></span> | <span data-ttu-id="60859-213">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="60859-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="60859-214">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-214">Scan</span></span> | <span data-ttu-id="60859-215">Especificar o intervalo para executar verificações rápidas por dia</span><span class="sxs-lookup"><span data-stu-id="60859-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="60859-216">Especifique quantas horas devem ser completas antes da próxima verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="60859-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="60859-217">Por exemplo, para executar a cada duas horas, insira **2**, uma vez por dia, insira **24**.</span><span class="sxs-lookup"><span data-stu-id="60859-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="60859-218">Insira **0** para nunca executar uma verificação rápida diária.</span><span class="sxs-lookup"><span data-stu-id="60859-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="60859-219">Nunca</span><span class="sxs-lookup"><span data-stu-id="60859-219">Never</span></span> |
|<span data-ttu-id="60859-220">Examinar</span><span class="sxs-lookup"><span data-stu-id="60859-220">Scan</span></span> | <span data-ttu-id="60859-221">Especifique o tempo para uma verificação rápida diária</span><span class="sxs-lookup"><span data-stu-id="60859-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="60859-222">Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã)</span><span class="sxs-lookup"><span data-stu-id="60859-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="60859-223">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="60859-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="60859-224">Usar cmdlets do PowerShell para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="60859-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="60859-225">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="60859-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="60859-226">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="60859-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="60859-227">Usar a Instrução de Gerenciamento do Windows (WMI) para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="60859-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="60859-228">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="60859-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="60859-229">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="60859-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="60859-230">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="60859-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="60859-231">Habilitar verificações após atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="60859-231">Enable scans after protection updates</span></span>

<span data-ttu-id="60859-232">Você pode forçar uma verificação a ocorrer após cada atualização [de proteção](manage-protection-updates-microsoft-defender-antivirus.md) com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="60859-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="60859-233">Usar a Política de Grupo para agendar verificações após atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="60859-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="60859-234">Local</span><span class="sxs-lookup"><span data-stu-id="60859-234">Location</span></span> | <span data-ttu-id="60859-235">Setting</span><span class="sxs-lookup"><span data-stu-id="60859-235">Setting</span></span> | <span data-ttu-id="60859-236">Descrição</span><span class="sxs-lookup"><span data-stu-id="60859-236">Description</span></span> | <span data-ttu-id="60859-237">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="60859-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="60859-238">Atualizações de assinatura</span><span class="sxs-lookup"><span data-stu-id="60859-238">Signature updates</span></span> | <span data-ttu-id="60859-239">Ativar a verificação após a atualização de Inteligência de Segurança</span><span class="sxs-lookup"><span data-stu-id="60859-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="60859-240">Uma verificação ocorrerá imediatamente depois que uma nova atualização de proteção for baixada</span><span class="sxs-lookup"><span data-stu-id="60859-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="60859-241">Habilitado</span><span class="sxs-lookup"><span data-stu-id="60859-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="60859-242">Confira também</span><span class="sxs-lookup"><span data-stu-id="60859-242">See also</span></span>
- [<span data-ttu-id="60859-243">Impedir ou permitir que os usuários modifiquem localmente as configurações de política</span><span class="sxs-lookup"><span data-stu-id="60859-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="60859-244">Configurar e executar verificações do Microsoft Defender Antivírus sob demanda</span><span class="sxs-lookup"><span data-stu-id="60859-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="60859-245">Configurar opções de verificação do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="60859-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="60859-246">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="60859-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="60859-247">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="60859-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="60859-248">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="60859-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)