---
title: Agendar verificações rápidas e completas regulares com Microsoft Defender Antivírus
description: Configurar verificações recorrentes (agendadas), incluindo quando devem ser executados e se são executados como verificações completas ou rápidas
keywords: verificação rápida, verificação completa, rápida versus completa, verificação de agendamento, diariamente, semanal, hora, agendada, recorrente, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789263"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="870cb-104">Configurar verificações rápidas ou completas do Microsoft Defender Antivírus agendadas</span><span class="sxs-lookup"><span data-stu-id="870cb-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="870cb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="870cb-105">**Applies to:**</span></span>

- [<span data-ttu-id="870cb-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="870cb-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="870cb-107">Por padrão, Microsoft Defender Antivírus verifica se há uma atualização 15 minutos antes da hora de quaisquer verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="870cb-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="870cb-108">Você pode Gerenciar a agenda para quando as atualizações de proteção devem ser baixadas e [aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) para substituir esse padrão.</span><span class="sxs-lookup"><span data-stu-id="870cb-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="870cb-109">Além da proteção sempre em tempo [](run-scan-microsoft-defender-antivirus.md) real e verificações sob demanda, você pode configurar verificações regulares agendadas.</span><span class="sxs-lookup"><span data-stu-id="870cb-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="870cb-110">Você pode configurar o tipo de verificação, quando a verificação deve ocorrer e se [a](manage-protection-updates-microsoft-defender-antivirus.md) verificação deve ocorrer após uma atualização de proteção ou se o ponto de extremidade está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="870cb-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="870cb-111">Você também pode especificar quando verificações especiais para concluir a correção devem ocorrer.</span><span class="sxs-lookup"><span data-stu-id="870cb-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="870cb-112">Este artigo descreve como configurar verificações agendadas com Política de Grupo, cmdlets do PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="870cb-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="870cb-113">Você também pode configurar verificações de agendamentos [com Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) ou [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span><span class="sxs-lookup"><span data-stu-id="870cb-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="870cb-114">Para configurar as configurações da Política de Grupo descritas neste artigo</span><span class="sxs-lookup"><span data-stu-id="870cb-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="870cb-115">Em sua máquina de gerenciamento de Política de Grupo, no Editor de Política de Grupo, acesse Configuração do computador Modelos administrativos Windows  >    >  **Componentes**  >  **Microsoft Defender Antivírus**  >  **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="870cb-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="870cb-116">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="870cb-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="870cb-117">Especifique as configurações do Objeto de Política de Grupo e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="870cb-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="870cb-118">Repita as etapas 1 a 4 para cada configuração que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="870cb-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="870cb-119">Implante seu Objeto de Política de Grupo como você normalmente faz.</span><span class="sxs-lookup"><span data-stu-id="870cb-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="870cb-120">Se você precisar de ajuda com objetos de política de grupo, consulte [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span><span class="sxs-lookup"><span data-stu-id="870cb-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="870cb-121">Consulte também [Os tópicos Gerenciar quando](manage-protection-update-schedule-microsoft-defender-antivirus.md) as atualizações de proteção devem ser baixadas e aplicadas e Impedir ou permitir que os usuários modifiquem [localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) os tópicos das configurações de política.</span><span class="sxs-lookup"><span data-stu-id="870cb-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="870cb-122">Verificação rápida versus verificação completa e verificação personalizada</span><span class="sxs-lookup"><span data-stu-id="870cb-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="870cb-123">Ao configurar verificações agendadas, você pode configurar se a verificação deve ser completa ou rápida.</span><span class="sxs-lookup"><span data-stu-id="870cb-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="870cb-124">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="870cb-124">Quick scan</span></span>  |<span data-ttu-id="870cb-125">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="870cb-125">Full scan</span></span>  | <span data-ttu-id="870cb-126">Verificação personalizada</span><span class="sxs-lookup"><span data-stu-id="870cb-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="870cb-127">Uma verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves de registro e pastas de inicialização Windows conhecidas.</span><span class="sxs-lookup"><span data-stu-id="870cb-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="870cb-128">Na maioria dos casos, uma verificação rápida é suficiente e é recomendada para verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="870cb-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="870cb-129">Uma verificação completa é iniciada executando uma verificação rápida e, em seguida, continua com uma verificação de arquivo sequencial de todos os discos fixos montados e unidades removíveis/de rede (se a verificação completa estiver configurada para fazer isso).</span><span class="sxs-lookup"><span data-stu-id="870cb-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="870cb-130">Uma verificação completa pode levar algumas horas ou dias para ser concluída, dependendo da quantidade e do tipo de dados que precisam ser verificados.</span><span class="sxs-lookup"><span data-stu-id="870cb-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="870cb-131">Quando a verificação completa for concluída, a nova inteligência de segurança estará disponível e uma nova verificação será necessária para garantir que nenhuma outra ameaça seja detectada com a nova inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="870cb-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="870cb-132">Uma verificação personalizada é uma verificação rápida que é executado nos arquivos e pastas que você especificar.</span><span class="sxs-lookup"><span data-stu-id="870cb-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="870cb-133">Por exemplo, você pode optar por examinar uma unidade USB ou uma pasta específica na unidade local do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="870cb-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="870cb-134">Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="870cb-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="870cb-135">Como saber qual tipo de verificação escolher?</span><span class="sxs-lookup"><span data-stu-id="870cb-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="870cb-136">Use a tabela a seguir para escolher um tipo de verificação.</span><span class="sxs-lookup"><span data-stu-id="870cb-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="870cb-137">Cenário</span><span class="sxs-lookup"><span data-stu-id="870cb-137">Scenario</span></span>  |<span data-ttu-id="870cb-138">Tipo de verificação recomendado</span><span class="sxs-lookup"><span data-stu-id="870cb-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="870cb-139">Você deseja configurar verificações regulares agendadas</span><span class="sxs-lookup"><span data-stu-id="870cb-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="870cb-140">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="870cb-140">Quick scan</span></span> <p><span data-ttu-id="870cb-141">Uma verificação rápida verifica os processos, memória, perfis e determinados locais no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="870cb-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="870cb-142">Combinado com [a proteção sempre em tempo real,](configure-real-time-protection-microsoft-defender-antivirus.md)uma verificação rápida ajuda a fornecer uma cobertura forte para malware que começa com o sistema e malware no nível do kernel.</span><span class="sxs-lookup"><span data-stu-id="870cb-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="870cb-143">A proteção em tempo real revisa arquivos quando são abertos e fechados e sempre que um usuário navega para uma pasta.</span><span class="sxs-lookup"><span data-stu-id="870cb-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="870cb-144">Ameaças, como malware, são detectadas em um dispositivo individual</span><span class="sxs-lookup"><span data-stu-id="870cb-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="870cb-145">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="870cb-145">Quick scan</span></span> <p><span data-ttu-id="870cb-146">Na maioria dos casos, uma verificação rápida detectará e limpará o malware detectado.</span><span class="sxs-lookup"><span data-stu-id="870cb-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="870cb-147">Você deseja executar uma verificação [sob demanda](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="870cb-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="870cb-148">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="870cb-148">Quick scan</span></span>       |
| <span data-ttu-id="870cb-149">Você deseja garantir que um dispositivo portátil, como uma unidade USB, não contenha malware</span><span class="sxs-lookup"><span data-stu-id="870cb-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="870cb-150">Verificação personalizada</span><span class="sxs-lookup"><span data-stu-id="870cb-150">Custom scan</span></span> <p><span data-ttu-id="870cb-151">Uma verificação personalizada permite selecionar locais, pastas ou arquivos específicos e executa uma verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="870cb-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="870cb-152">O que mais preciso saber sobre verificações rápidas e completas?</span><span class="sxs-lookup"><span data-stu-id="870cb-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="870cb-153">Arquivos mal-intencionados podem ser armazenados em locais que não estão incluídos em uma verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="870cb-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="870cb-154">No entanto, a proteção sempre em tempo real revisa todos os arquivos abertos e fechados e todos os arquivos que estão em pastas acessadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="870cb-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="870cb-155">A combinação de proteção em tempo real e uma verificação rápida ajuda a fornecer uma proteção forte contra malware.</span><span class="sxs-lookup"><span data-stu-id="870cb-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="870cb-156">A proteção ao acessar [com](cloud-protection-microsoft-defender-antivirus.md) a proteção entregue na nuvem ajuda a garantir que todos os arquivos acessados no sistema estão sendo verificados com os modelos de aprendizado de máquina de nuvem e inteligência de segurança mais recentes.</span><span class="sxs-lookup"><span data-stu-id="870cb-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="870cb-157">Quando a proteção em tempo real detecta malware e a extensão dos arquivos afetados não é determinada inicialmente, Microsoft Defender Antivírus inicia uma verificação completa como parte do processo de correção.</span><span class="sxs-lookup"><span data-stu-id="870cb-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="870cb-158">Uma verificação completa pode detectar arquivos mal-intencionados que não foram detectados por outras verificações, como uma verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="870cb-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="870cb-159">No entanto, uma verificação completa pode demorar um pouco e usar recursos valiosos do sistema para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="870cb-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="870cb-160">Se um dispositivo estiver offline por um longo período de tempo, uma verificação completa poderá levar mais tempo para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="870cb-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="870cb-161">Configurar verificações agendadas</span><span class="sxs-lookup"><span data-stu-id="870cb-161">Set up scheduled scans</span></span>

<span data-ttu-id="870cb-162">Verificações agendadas são realizadas no dia e hora especificados.</span><span class="sxs-lookup"><span data-stu-id="870cb-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="870cb-163">Você pode usar a Política de Grupo, o PowerShell e o WMI para configurar verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="870cb-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="870cb-164">Se um dispositivo for desconectado e estiver sendo executado na bateria durante uma verificação completa agendada, a verificação agendada será interrompida com o evento 1002, que afirma que a verificação parou antes da conclusão.</span><span class="sxs-lookup"><span data-stu-id="870cb-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="870cb-165">Microsoft Defender Antivírus executará uma verificação completa na próxima hora agendada.</span><span class="sxs-lookup"><span data-stu-id="870cb-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="870cb-166">Usar a Política de Grupo para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="870cb-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="870cb-167">Localização</span><span class="sxs-lookup"><span data-stu-id="870cb-167">Location</span></span> | <span data-ttu-id="870cb-168">Configuração</span><span class="sxs-lookup"><span data-stu-id="870cb-168">Setting</span></span> | <span data-ttu-id="870cb-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="870cb-169">Description</span></span> | <span data-ttu-id="870cb-170">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="870cb-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="870cb-171">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-171">Scan</span></span> | <span data-ttu-id="870cb-172">Especificar o tipo de verificação a ser usado para uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="870cb-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="870cb-173">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="870cb-173">Quick scan</span></span> |
|<span data-ttu-id="870cb-174">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-174">Scan</span></span> | <span data-ttu-id="870cb-175">Especificar o dia da semana para executar uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="870cb-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="870cb-176">Especifique o dia (ou nunca) para executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="870cb-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="870cb-177">Nunca</span><span class="sxs-lookup"><span data-stu-id="870cb-177">Never</span></span> |
|<span data-ttu-id="870cb-178">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-178">Scan</span></span> | <span data-ttu-id="870cb-179">Especificar a hora do dia para executar uma verificação agendada</span><span class="sxs-lookup"><span data-stu-id="870cb-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="870cb-180">Especifique o número de minutos após a meia-noite (por exemplo, insira **60** para 1 da manhã).</span><span class="sxs-lookup"><span data-stu-id="870cb-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="870cb-181">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="870cb-181">2 a.m.</span></span> |
|<span data-ttu-id="870cb-182">Root</span><span class="sxs-lookup"><span data-stu-id="870cb-182">Root</span></span> | <span data-ttu-id="870cb-183">Randomize tempos de tarefa agendados</span><span class="sxs-lookup"><span data-stu-id="870cb-183">Randomize scheduled task times</span></span> |<span data-ttu-id="870cb-184">Em Microsoft Defender Antivírus, randomize o horário de início da verificação para qualquer intervalo de 0 a 4 horas.</span><span class="sxs-lookup"><span data-stu-id="870cb-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="870cb-185">Em [SCEP,](/mem/intune/protect/certificates-scep-configure)randomize verifica para qualquer intervalo mais ou menos 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="870cb-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="870cb-186">Isso pode ser útil em máquinas virtuais ou implantações VDI.</span><span class="sxs-lookup"><span data-stu-id="870cb-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="870cb-187">Habilitado</span><span class="sxs-lookup"><span data-stu-id="870cb-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="870cb-188">Usar cmdlets do PowerShell para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="870cb-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="870cb-189">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="870cb-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="870cb-190">Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="870cb-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="870cb-191">Use Windows Instrução de Gerenciamento (WMI) para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="870cb-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="870cb-192">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="870cb-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="870cb-193">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="870cb-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="870cb-194">Iniciar verificações agendadas somente quando o ponto de extremidade não estiver em uso</span><span class="sxs-lookup"><span data-stu-id="870cb-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="870cb-195">Você pode definir a verificação agendada para ocorrer somente quando o ponto de extremidade estiver ligado, mas não estiver em uso com a Política de Grupo, o PowerShell ou o WMI.</span><span class="sxs-lookup"><span data-stu-id="870cb-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="870cb-196">Essas verificações não cumprirão a configuração de limitador de CPU e tirarão total proveito dos recursos disponíveis para concluir a verificação o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="870cb-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="870cb-197">Usar a Política de Grupo para agendar verificações</span><span class="sxs-lookup"><span data-stu-id="870cb-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="870cb-198">Localização</span><span class="sxs-lookup"><span data-stu-id="870cb-198">Location</span></span> | <span data-ttu-id="870cb-199">Configuração</span><span class="sxs-lookup"><span data-stu-id="870cb-199">Setting</span></span> | <span data-ttu-id="870cb-200">Descrição</span><span class="sxs-lookup"><span data-stu-id="870cb-200">Description</span></span> | <span data-ttu-id="870cb-201">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="870cb-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="870cb-202">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-202">Scan</span></span> | <span data-ttu-id="870cb-203">Iniciar a verificação agendada somente quando o computador estiver em uso, mas não estiver em uso</span><span class="sxs-lookup"><span data-stu-id="870cb-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="870cb-204">As verificações agendadas não serão executados, a menos que o computador esteja, mas não esteja em uso</span><span class="sxs-lookup"><span data-stu-id="870cb-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="870cb-205">Habilitado</span><span class="sxs-lookup"><span data-stu-id="870cb-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="870cb-206">Usar cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="870cb-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="870cb-207">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="870cb-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="870cb-208">Para obter mais informações, confira [Usar cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [cmdlets do Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="870cb-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="870cb-209">Usar Windows Instrução de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="870cb-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="870cb-210">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="870cb-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="870cb-211">Para obter mais informações sobre APIs e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="870cb-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="870cb-212">Configurar quando verificações completas devem ser executados para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="870cb-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="870cb-213">Algumas ameaças podem exigir uma verificação completa para concluir sua remoção e correção.</span><span class="sxs-lookup"><span data-stu-id="870cb-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="870cb-214">Você pode especificar quando essas verificações devem ocorrer com Política de Grupo, PowerShell ou WMI.</span><span class="sxs-lookup"><span data-stu-id="870cb-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="870cb-215">Usar a Política de Grupo para agendar verificações necessárias para correção</span><span class="sxs-lookup"><span data-stu-id="870cb-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="870cb-216">Localização</span><span class="sxs-lookup"><span data-stu-id="870cb-216">Location</span></span> | <span data-ttu-id="870cb-217">Configuração</span><span class="sxs-lookup"><span data-stu-id="870cb-217">Setting</span></span> | <span data-ttu-id="870cb-218">Descrição</span><span class="sxs-lookup"><span data-stu-id="870cb-218">Description</span></span> | <span data-ttu-id="870cb-219">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="870cb-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="870cb-220">Correção</span><span class="sxs-lookup"><span data-stu-id="870cb-220">Remediation</span></span> | <span data-ttu-id="870cb-221">Especificar o dia da semana para executar uma verificação completa agendada para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="870cb-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="870cb-222">Especifique o dia (ou nunca) para executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="870cb-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="870cb-223">Nunca</span><span class="sxs-lookup"><span data-stu-id="870cb-223">Never</span></span> |
|<span data-ttu-id="870cb-224">Correção</span><span class="sxs-lookup"><span data-stu-id="870cb-224">Remediation</span></span> | <span data-ttu-id="870cb-225">Especificar a hora do dia para executar uma verificação completa agendada para concluir a correção</span><span class="sxs-lookup"><span data-stu-id="870cb-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="870cb-226">Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã)</span><span class="sxs-lookup"><span data-stu-id="870cb-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="870cb-227">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="870cb-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="870cb-228">Usar cmdlets do PowerShell</span><span class="sxs-lookup"><span data-stu-id="870cb-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="870cb-229">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="870cb-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="870cb-230">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="870cb-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="870cb-231">Usar Windows Instrução de Gerenciamento (WMI)</span><span class="sxs-lookup"><span data-stu-id="870cb-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="870cb-232">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="870cb-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="870cb-233">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="870cb-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="870cb-234">Configurar verificações rápidas diárias</span><span class="sxs-lookup"><span data-stu-id="870cb-234">Set up daily quick scans</span></span>

<span data-ttu-id="870cb-235">Você pode habilitar uma verificação rápida diária que pode ser executado além de outras verificações agendadas com a Política de Grupo, o PowerShell ou o WMI.</span><span class="sxs-lookup"><span data-stu-id="870cb-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="870cb-236">Usar a Política de Grupo para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="870cb-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="870cb-237">Localização</span><span class="sxs-lookup"><span data-stu-id="870cb-237">Location</span></span> | <span data-ttu-id="870cb-238">Configuração</span><span class="sxs-lookup"><span data-stu-id="870cb-238">Setting</span></span> | <span data-ttu-id="870cb-239">Descrição</span><span class="sxs-lookup"><span data-stu-id="870cb-239">Description</span></span> | <span data-ttu-id="870cb-240">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="870cb-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="870cb-241">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-241">Scan</span></span> | <span data-ttu-id="870cb-242">Especificar o intervalo para executar verificações rápidas por dia</span><span class="sxs-lookup"><span data-stu-id="870cb-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="870cb-243">Especifique quantas horas devem ser completas antes da próxima verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="870cb-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="870cb-244">Por exemplo, para executar a cada duas horas, insira **2**, uma vez por dia, insira **24**.</span><span class="sxs-lookup"><span data-stu-id="870cb-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="870cb-245">Insira **0** para nunca executar uma verificação rápida diária.</span><span class="sxs-lookup"><span data-stu-id="870cb-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="870cb-246">Nunca</span><span class="sxs-lookup"><span data-stu-id="870cb-246">Never</span></span> |
|<span data-ttu-id="870cb-247">Examinar</span><span class="sxs-lookup"><span data-stu-id="870cb-247">Scan</span></span> | <span data-ttu-id="870cb-248">Especifique o tempo para uma verificação rápida diária</span><span class="sxs-lookup"><span data-stu-id="870cb-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="870cb-249">Especifique o número de minutos após a meia-noite (por exemplo, **insira 60** para 1 da manhã)</span><span class="sxs-lookup"><span data-stu-id="870cb-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="870cb-250">2 da manhã.</span><span class="sxs-lookup"><span data-stu-id="870cb-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="870cb-251">Usar cmdlets do PowerShell para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="870cb-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="870cb-252">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="870cb-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="870cb-253">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.</span><span class="sxs-lookup"><span data-stu-id="870cb-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="870cb-254">Use Windows Instrução de Gerenciamento (WMI) para agendar verificações diárias</span><span class="sxs-lookup"><span data-stu-id="870cb-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="870cb-255">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="870cb-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="870cb-256">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="870cb-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="870cb-257">Habilitar verificações após atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="870cb-257">Enable scans after protection updates</span></span>

<span data-ttu-id="870cb-258">Você pode forçar uma verificação a ocorrer após cada atualização [de proteção](manage-protection-updates-microsoft-defender-antivirus.md) com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="870cb-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="870cb-259">Usar a Política de Grupo para agendar verificações após atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="870cb-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="870cb-260">Localização</span><span class="sxs-lookup"><span data-stu-id="870cb-260">Location</span></span> | <span data-ttu-id="870cb-261">Configuração</span><span class="sxs-lookup"><span data-stu-id="870cb-261">Setting</span></span> | <span data-ttu-id="870cb-262">Descrição</span><span class="sxs-lookup"><span data-stu-id="870cb-262">Description</span></span> | <span data-ttu-id="870cb-263">Configuração padrão (se não estiver configurada)</span><span class="sxs-lookup"><span data-stu-id="870cb-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="870cb-264">Atualizações de assinatura</span><span class="sxs-lookup"><span data-stu-id="870cb-264">Signature updates</span></span> | <span data-ttu-id="870cb-265">Ativar a verificação após a atualização de Inteligência de Segurança</span><span class="sxs-lookup"><span data-stu-id="870cb-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="870cb-266">Uma verificação ocorrerá imediatamente depois que uma nova atualização de proteção for baixada</span><span class="sxs-lookup"><span data-stu-id="870cb-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="870cb-267">Habilitado</span><span class="sxs-lookup"><span data-stu-id="870cb-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="870cb-268">Confira também</span><span class="sxs-lookup"><span data-stu-id="870cb-268">See also</span></span>

- [<span data-ttu-id="870cb-269">Impedir ou permitir que os usuários modifiquem localmente as configurações de política</span><span class="sxs-lookup"><span data-stu-id="870cb-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="870cb-270">Configurar e executar verificações do Microsoft Defender Antivírus sob demanda</span><span class="sxs-lookup"><span data-stu-id="870cb-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="870cb-271">Configurar opções de verificação do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="870cb-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="870cb-272">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="870cb-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="870cb-273">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="870cb-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="870cb-274">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="870cb-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)