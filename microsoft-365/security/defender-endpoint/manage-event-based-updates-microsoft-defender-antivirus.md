---
title: Aplicar atualizações do Microsoft Defender Antivírus após determinados eventos
description: Gerencie como o Microsoft Defender Antivírus aplica atualizações de inteligência de segurança após a inicialização ou recebimento de relatórios de detecção entregues na nuvem.
keywords: atualizações, proteção, atualizações de força, eventos, inicialização, verificar se há mais recentes, notificações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b9f09878c645d54aadca21fe01749a0e73939c5f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689820"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="3af73-104">Gerenciar atualizações forçadas baseadas em eventos</span><span class="sxs-lookup"><span data-stu-id="3af73-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3af73-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3af73-105">**Applies to:**</span></span>

- [<span data-ttu-id="3af73-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3af73-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3af73-107">O Microsoft Defender Antivírus permite determinar se as atualizações devem (ou não) ocorrer após determinados eventos, como na inicialização ou depois de receber relatórios específicos do serviço de proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3af73-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="3af73-108">Verifique se há atualizações de proteção antes de executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3af73-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="3af73-109">Você pode usar o Microsoft Endpoint Configuration Manager, a Política de Grupo, os cmdlets do PowerShell e o WMI para forçar o Microsoft Defender Antivírus a verificar e baixar atualizações de proteção antes de executar uma verificação agendada.</span><span class="sxs-lookup"><span data-stu-id="3af73-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="3af73-110">Use o Configuration Manager para verificar se há atualizações de proteção antes de executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3af73-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="3af73-111">No console do Microsoft Endpoint Manager, abra a política  antimalware que você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para Visão Geral das Políticas  >    >  **antimalware** de Proteção de Ponto de Extremidade )</span><span class="sxs-lookup"><span data-stu-id="3af73-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="3af73-112">Vá para a seção **Verificações** agendadas e **desem conjunto Verificar as** atualizações mais recentes de inteligência de segurança antes de executar uma verificação como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="3af73-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="3af73-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-113">Click **OK**.</span></span>

4. <span data-ttu-id="3af73-114">[Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="3af73-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="3af73-115">Use a Política de Grupo para verificar se há atualizações de proteção antes de executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3af73-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="3af73-116">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3af73-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3af73-117">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="3af73-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3af73-118">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="3af73-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="3af73-119">Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Scan**.</span><span class="sxs-lookup"><span data-stu-id="3af73-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="3af73-120">Clique duas **vezes em Verificar as definições mais** recentes de vírus e spyware antes de executar uma verificação agendada e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3af73-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="3af73-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="3af73-122">Use cmdlets do PowerShell para verificar se há atualizações de proteção antes de executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3af73-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="3af73-123">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3af73-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="3af73-124">Para obter mais informações, [consulte Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar os [cmdlets](/powershell/module/defender/index)do Microsoft Defender Antivírus e do Defender.</span><span class="sxs-lookup"><span data-stu-id="3af73-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="3af73-125">Use a Instrução de Gerenciamento do Windows (WMI) para verificar se há atualizações de proteção antes de executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3af73-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="3af73-126">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="3af73-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="3af73-127">Para obter mais informações, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="3af73-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="3af73-128">Verificar se há atualizações de proteção na inicialização</span><span class="sxs-lookup"><span data-stu-id="3af73-128">Check for protection updates on startup</span></span>

<span data-ttu-id="3af73-129">Você pode usar a Política de Grupo para forçar o Microsoft Defender Antivírus a verificar e baixar atualizações de proteção quando o computador for iniciado.</span><span class="sxs-lookup"><span data-stu-id="3af73-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="3af73-130">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3af73-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3af73-131">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="3af73-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3af73-132">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="3af73-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="3af73-133">Expanda a árvore para **componentes do Windows** Atualizações de Inteligência de Segurança do Microsoft Defender  >    >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="3af73-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="3af73-134">Clique duas **vezes em Verificar as definições mais** recentes de vírus e spyware na inicialização e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3af73-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="3af73-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-135">Click **OK**.</span></span>

<span data-ttu-id="3af73-136">Você também pode usar a Política de Grupo, o PowerShell ou o WMI para configurar o Microsoft Defender Antivírus para verificar se há atualizações na inicialização, mesmo quando ela não está em execução.</span><span class="sxs-lookup"><span data-stu-id="3af73-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="3af73-137">Usar a Política de Grupo para baixar atualizações quando o Microsoft Defender Antivírus não estiver presente</span><span class="sxs-lookup"><span data-stu-id="3af73-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="3af73-138">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3af73-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3af73-139">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador**.</span><span class="sxs-lookup"><span data-stu-id="3af73-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3af73-140">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="3af73-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="3af73-141">Expanda a árvore para **componentes do Windows** Atualizações de Inteligência de Segurança do Microsoft Defender  >    >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="3af73-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="3af73-142">Clique duas vezes em **Iniciar atualização de inteligência de segurança na inicialização** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3af73-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="3af73-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="3af73-144">Usar cmdlets do PowerShell para baixar atualizações quando o Microsoft Defender Antivírus não estiver presente</span><span class="sxs-lookup"><span data-stu-id="3af73-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="3af73-145">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="3af73-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="3af73-146">Para obter mais informações, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para gerenciar os [cmdlets](/powershell/module/defender/index) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="3af73-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="3af73-147">Use a Instrução de Gerenciamento do Windows (WMI) para baixar atualizações quando o Microsoft Defender Antivírus não estiver presente</span><span class="sxs-lookup"><span data-stu-id="3af73-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="3af73-148">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="3af73-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="3af73-149">Para obter mais informações, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="3af73-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="3af73-150">Permitir alterações ad hoc na proteção com base na proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="3af73-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="3af73-151">O Microsoft Defender AV pode fazer alterações em sua proteção com base na proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3af73-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="3af73-152">Essas alterações podem ocorrer fora das atualizações de proteção normais ou agendadas.</span><span class="sxs-lookup"><span data-stu-id="3af73-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="3af73-153">Se você habilitar a proteção entregue na nuvem, o Microsoft Defender AV enviará arquivos suspeitos para a Windows Defender nuvem.</span><span class="sxs-lookup"><span data-stu-id="3af73-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="3af73-154">Se o serviço de nuvem relata que o arquivo é mal-intencionado e o arquivo é detectado em uma atualização de proteção recente, você pode usar a Política de Grupo para configurar o Microsoft Defender AV para receber automaticamente essa atualização de proteção.</span><span class="sxs-lookup"><span data-stu-id="3af73-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="3af73-155">Outras atualizações de proteção importantes também podem ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3af73-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="3af73-156">Usar a Política de Grupo para baixar automaticamente atualizações recentes com base na proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="3af73-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="3af73-157">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3af73-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="3af73-158">Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="3af73-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="3af73-159">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="3af73-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="3af73-160">Expanda a árvore para **componentes do Windows** Atualizações de Inteligência de Segurança do Microsoft Defender  >    >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="3af73-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="3af73-161">Clique duas vezes **em Permitir atualizações de** inteligência de segurança em tempo real com base em relatórios para o Microsoft MAPS e de definir a opção **como Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="3af73-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="3af73-162">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-162">Then click **OK**.</span></span>

6. <span data-ttu-id="3af73-163">**Permitir notificações para desabilitar relatórios baseados** em definições para o Microsoft MAPS e definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3af73-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="3af73-164">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3af73-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3af73-165">**Permitir notificações para desabilitar relatórios baseados** em definições permite que o Microsoft MAPS desabilite essas definições conhecidas por causar relatórios falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="3af73-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="3af73-166">Você deve configurar seu computador para ingressar no Microsoft MAPS para que essa função funcione.</span><span class="sxs-lookup"><span data-stu-id="3af73-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="3af73-167">Confira também</span><span class="sxs-lookup"><span data-stu-id="3af73-167">See also</span></span>

- [<span data-ttu-id="3af73-168">Implantar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="3af73-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3af73-169">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="3af73-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3af73-170">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="3af73-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3af73-171">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="3af73-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3af73-172">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="3af73-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3af73-173">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="3af73-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)