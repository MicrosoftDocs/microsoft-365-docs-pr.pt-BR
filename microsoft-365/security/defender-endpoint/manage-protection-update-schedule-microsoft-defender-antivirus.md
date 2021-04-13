---
title: Agendar atualizações de proteção do Microsoft Defender Antivírus
description: Agendar o dia, a hora e o intervalo para quando as atualizações de proteção devem ser baixadas
keywords: atualizações, linhas de base de segurança, agendar atualizações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689817"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="8a0ef-104">Gerenciar o cronograma para quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="8a0ef-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8a0ef-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8a0ef-105">**Applies to:**</span></span>

- [<span data-ttu-id="8a0ef-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8a0ef-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8a0ef-107">O Microsoft Defender Antivírus permite determinar quando ele deve procurar e baixar atualizações.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="8a0ef-108">Você pode agendar atualizações para seus pontos de extremidade por:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="8a0ef-109">Especificando o dia da semana para verificar se há atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="8a0ef-110">Especificando o intervalo para verificar se há atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="8a0ef-111">Especificando o tempo para verificar se há atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="8a0ef-112">Você também pode aleatoriamente as horas em que cada ponto de extremidade verifica e baixa atualizações de proteção.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="8a0ef-113">Consulte o [tópico Agendar verificações](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="8a0ef-114">Usar o Configuration Manager para agendar atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="8a0ef-115">No console do Microsoft Endpoint Manager, abra a política  antimalware que você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para Visão Geral das Políticas  >    >  **antimalware** de Proteção de Ponto de Extremidade )</span><span class="sxs-lookup"><span data-stu-id="8a0ef-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="8a0ef-116">Vá para a **seção Atualizações de inteligência de segurança.**</span><span class="sxs-lookup"><span data-stu-id="8a0ef-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="8a0ef-117">Para verificar e baixar atualizações em um determinado momento:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="8a0ef-118">Definir Verificar atualizações de inteligência de segurança da Proteção de Ponto de Extremidade **em um intervalo específico...** como **0**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="8a0ef-119">Definir Verificar atualizações de inteligência de segurança do **Endpoint Protection diariamente no momento** em que as atualizações devem ser verificadas.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="8a0ef-120">3</span><span class="sxs-lookup"><span data-stu-id="8a0ef-120">3</span></span>
4. <span data-ttu-id="8a0ef-121">Para verificar e baixar atualizações em um intervalo contínuo, Desem conjunto Verificar atualizações de inteligência de segurança da Proteção de Ponto de Extremidade em um intervalo **específico...** para o número de horas que devem ocorrer entre as atualizações.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="8a0ef-122">[Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="8a0ef-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="8a0ef-123">Usar a Política de Grupo para agendar atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a0ef-124">Por padrão, o Microsoft Defender Antivírus verificará se há uma atualização 15 minutos antes da hora de quaisquer verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="8a0ef-125">A habilitação dessas configurações substituirá esse padrão.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="8a0ef-126">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="8a0ef-127">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="8a0ef-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="8a0ef-128">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="8a0ef-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="8a0ef-129">Expanda a árvore para **componentes do Windows** Atualizações do  >  **Microsoft Defender**  >  **Antivírus Signature Intelligence** e configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="8a0ef-130">Clique duas vezes **na configuração Especificar o dia** da semana para verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8a0ef-131">Insira o dia da semana para verificar se há atualizações.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="8a0ef-132">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-132">Click **OK**.</span></span>
    2. <span data-ttu-id="8a0ef-133">Clique duas vezes na **configuração Especificar o intervalo para** verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8a0ef-134">Insira o número de horas entre as atualizações.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="8a0ef-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-135">Click **OK**.</span></span>
    3. <span data-ttu-id="8a0ef-136">Clique duas vezes na **configuração Especificar o horário para** verificar se há atualizações de inteligência de segurança e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8a0ef-137">Insira a hora em que as atualizações devem ser verificadas.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="8a0ef-138">O tempo é baseado na hora local do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="8a0ef-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="8a0ef-140">Usar cmdlets do PowerShell para agendar atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="8a0ef-141">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="8a0ef-142">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)  do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="8a0ef-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="8a0ef-143">Usar a Instrução de Gerenciamento do Windows (WMI) para agendar atualizações de proteção</span><span class="sxs-lookup"><span data-stu-id="8a0ef-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="8a0ef-144">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="8a0ef-145">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="8a0ef-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="8a0ef-146">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="8a0ef-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="8a0ef-147">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="8a0ef-147">Related articles</span></span>

- [<span data-ttu-id="8a0ef-148">Implantar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="8a0ef-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a0ef-149">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="8a0ef-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a0ef-150">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="8a0ef-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a0ef-151">Gerenciar atualizações forçadas baseadas em eventos</span><span class="sxs-lookup"><span data-stu-id="8a0ef-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a0ef-152">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="8a0ef-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8a0ef-153">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="8a0ef-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)