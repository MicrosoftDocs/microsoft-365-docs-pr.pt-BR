---
title: Aplicar atualizações de proteção do Microsoft Defender AV a pontos de extremidade des date
description: Defina quando e como as atualizações devem ser aplicadas para pontos de extremidade que não foram atualizados há algum tempo.
keywords: atualizações, proteção, desatualizados, desatualizados, antigos, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275055"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="df496-104">Gerenciar atualizações do Microsoft Defender Antivírus e verifica se há pontos de extremidade que estão desatualizados</span><span class="sxs-lookup"><span data-stu-id="df496-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="df496-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="df496-105">**Applies to:**</span></span>

- [<span data-ttu-id="df496-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="df496-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="df496-107">Microsoft Defender Antivírus permite definir por quanto tempo um ponto de extremidade pode evitar uma atualização ou quantas verificações ele pode falhar antes de ser necessário atualizar e verificar a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="df496-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="df496-108">Isso é especialmente útil em ambientes onde os dispositivos não estão frequentemente conectados a uma rede corporativa ou externa ou dispositivos que não são usados diariamente.</span><span class="sxs-lookup"><span data-stu-id="df496-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="df496-109">Por exemplo, um funcionário que usa um computador específico está em pausa por três dias e não faz logoff no computador durante esse tempo.</span><span class="sxs-lookup"><span data-stu-id="df496-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="df496-110">Quando o usuário retorna ao trabalho e faz logo em seu computador, o Microsoft Defender Antivírus verificará imediatamente e baixará as atualizações de proteção mais recentes e executará uma verificação.</span><span class="sxs-lookup"><span data-stu-id="df496-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="df496-111">Configurar atualizações de proteção de catch-up para pontos de extremidade que não são atualizados há algum tempo</span><span class="sxs-lookup"><span data-stu-id="df496-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="df496-112">Se Microsoft Defender Antivírus as atualizações de proteção não foram baixadas por um período especificado, você pode defini-la para verificar e baixar automaticamente a atualização mais recente no próximo logoff.</span><span class="sxs-lookup"><span data-stu-id="df496-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="df496-113">Isso será útil se você [tiver desabilitado globalmente](manage-event-based-updates-microsoft-defender-antivirus.md)os downloads de atualização automática na inicialização .</span><span class="sxs-lookup"><span data-stu-id="df496-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="df496-114">Usar o Configuration Manager para configurar atualizações de proteção de atualização</span><span class="sxs-lookup"><span data-stu-id="df496-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="df496-115">Em seu console Microsoft Endpoint Manager, abra a política antimalware que  você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para **Visão** geral  >  **Endpoint Protection**  >  **Políticas antimalware**)</span><span class="sxs-lookup"><span data-stu-id="df496-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="df496-116">Vá para a seção **Atualizações de Inteligência de** Segurança e configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="df496-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="df496-117">Definir Forçar uma atualização de inteligência de segurança se o computador cliente estiver offline para mais de duas atualizações **agendadas consecutivas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="df496-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="df496-118">Para o Gerenciador de Configurações if é usado como uma fonte para atualizações de inteligência de  **segurança...**, especifique as horas antes das quais as atualizações de proteção entregues pelo Configuration Manager devem ser consideradas des date.</span><span class="sxs-lookup"><span data-stu-id="df496-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="df496-119">Isso fará com que o próximo local de atualização seja usado, com base na ordem de origem [de fallback definida.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="df496-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="df496-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-120">Click **OK**.</span></span>

4.  <span data-ttu-id="df496-121">[Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="df496-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="df496-122">Usar a Política de Grupo para habilitar e configurar o recurso de atualização de atualização de catch-up</span><span class="sxs-lookup"><span data-stu-id="df496-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="df496-123">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="df496-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="df496-124">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="df496-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="df496-125">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="df496-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="df496-126">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Atualizações de Assinatura.**</span><span class="sxs-lookup"><span data-stu-id="df496-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="df496-127">Clique duas vezes na **configuração Definir** o número de dias após os quais uma atualização de inteligência de segurança de atualização é necessária e defina a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="df496-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="df496-128">Insira o número de dias após os quais você deseja que o Microsoft Defender AV verifique e baixe a atualização de proteção mais recente.</span><span class="sxs-lookup"><span data-stu-id="df496-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="df496-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="df496-130">Usar cmdlets do PowerShell para configurar atualizações de proteção de atualização</span><span class="sxs-lookup"><span data-stu-id="df496-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="df496-131">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="df496-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="df496-132">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="df496-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="df496-133">Use Windows Instrução de Gerenciamento (WMI) para configurar atualizações de proteção de atualização</span><span class="sxs-lookup"><span data-stu-id="df496-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="df496-134">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="df496-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="df496-135">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="df496-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="df496-136">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="df496-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="df496-137">Definir o número de dias antes que a proteção seja relatada como des date</span><span class="sxs-lookup"><span data-stu-id="df496-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="df496-138">Você também pode especificar o número de dias após os quais Microsoft Defender Antivírus proteção é considerada antiga ou desa data.</span><span class="sxs-lookup"><span data-stu-id="df496-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="df496-139">Após o número especificado de dias, o cliente se reportará como desa datado e mostrará um erro para o usuário do computador.</span><span class="sxs-lookup"><span data-stu-id="df496-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="df496-140">Também pode fazer com que Microsoft Defender Antivírus tente baixar uma atualização de outras fontes (com base na ordem de origem de [fallback](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)definida ), como ao usar o MMPC como uma fonte secundária após definir o WSUS ou o Microsoft Update como a primeira fonte.</span><span class="sxs-lookup"><span data-stu-id="df496-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="df496-141">Use a Política de Grupo para especificar o número de dias antes que a proteção seja considerada desa atual</span><span class="sxs-lookup"><span data-stu-id="df496-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="df496-142">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="df496-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="df496-143">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="df496-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="df496-144">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="df496-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="df496-145">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Atualizações** de Assinatura e configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="df496-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="df496-146">Clique duas vezes em Definir o número de dias antes que as definições de spyware sejam **consideradas** desa data e defina a opção **como Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="df496-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="df496-147">Insira o número de dias após os quais você deseja que o Microsoft Defender AV considere o spyware Security intelligence desagregado.</span><span class="sxs-lookup"><span data-stu-id="df496-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="df496-148">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="df496-149">Clique duas vezes em Definir o número de dias antes que as definições de vírus sejam **consideradas** desa data e defina a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="df496-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="df496-150">Insira o número de dias após os quais você deseja que o Microsoft Defender AV considere a inteligência de segurança de vírus desagregada.</span><span class="sxs-lookup"><span data-stu-id="df496-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="df496-151">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="df496-152">Configurar verificações de catch-up para pontos de extremidade que não foram verificados por um tempo</span><span class="sxs-lookup"><span data-stu-id="df496-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="df496-153">Você pode definir o número de verificações agendadas consecutivas que podem ser perdidas antes Microsoft Defender Antivírus forçar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="df496-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="df496-154">O processo para habilitação desse recurso é:</span><span class="sxs-lookup"><span data-stu-id="df496-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="df496-155">Configurar pelo menos uma verificação agendada (consulte o [tópico Agendar verificações).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="df496-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="df496-156">Habilita o recurso de verificação de captura.</span><span class="sxs-lookup"><span data-stu-id="df496-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="df496-157">Defina o número de verificações que podem ser ignoradas antes que ocorra uma verificação de captura.</span><span class="sxs-lookup"><span data-stu-id="df496-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="df496-158">Esse recurso pode ser habilitado para verificações completas e rápidas.</span><span class="sxs-lookup"><span data-stu-id="df496-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="df496-159">Usar a Política de Grupo para habilitar e configurar o recurso de verificação de captura</span><span class="sxs-lookup"><span data-stu-id="df496-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="df496-160">Verifique se você definiu pelo menos uma verificação agendada.</span><span class="sxs-lookup"><span data-stu-id="df496-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="df496-161">Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="df496-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="df496-162">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="df496-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="df496-163">Clique **em Políticas** e modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="df496-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="df496-164">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Verificar** e configurar as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="df496-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="df496-165">Se você tiver definido as verificações  rápidas agendadas, clique duas vezes na configuração Ativar a verificação rápida de captura e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="df496-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="df496-166">Se você tiver definido as verificações  completas agendadas, clique duas vezes na configuração Ativar a verificação completa de captura e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="df496-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="df496-167">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-167">Click **OK**.</span></span>
    3. <span data-ttu-id="df496-168">Clique duas vezes na **configuração Definir** o número de dias após os quais uma verificação de captura é forçada e defina a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="df496-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="df496-169">Insira o número de verificações que podem ser perdidas antes que uma verificação seja automaticamente executado quando o próximo usuário faz logor no computador.</span><span class="sxs-lookup"><span data-stu-id="df496-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="df496-170">O tipo de verificação que é executado é determinado pelo tipo Especificar o tipo de verificação a ser usado para uma verificação **agendada** (consulte o tópico [Agendar verificações).](scheduled-catch-up-scans-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="df496-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="df496-171">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="df496-172">O título de configuração da Política de Grupo refere-se ao número de dias.</span><span class="sxs-lookup"><span data-stu-id="df496-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="df496-173">A configuração, no entanto, é aplicada ao número de verificações (não dias) antes que a verificação de captura seja executado.</span><span class="sxs-lookup"><span data-stu-id="df496-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="df496-174">Usar cmdlets do PowerShell para configurar verificações de captura</span><span class="sxs-lookup"><span data-stu-id="df496-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="df496-175">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="df496-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="df496-176">Consulte [Usar cmdlets do PowerShell para gerenciar cmdlets Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md) e [Defender](/powershell/module/defender/) para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="df496-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="df496-177">Use Windows Instrução de Gerenciamento (WMI) para configurar verificações de captura</span><span class="sxs-lookup"><span data-stu-id="df496-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="df496-178">Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="df496-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="df496-179">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="df496-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="df496-180">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="df496-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="df496-181">Usar o Configuration Manager para configurar verificações de captura</span><span class="sxs-lookup"><span data-stu-id="df496-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="df496-182">Em seu console Microsoft Endpoint Manager, abra a política antimalware que  você deseja alterar (clique em Ativos e Conformidade no painel de navegação à esquerda e expanda a árvore para **Visão** geral  >  **Endpoint Protection**  >  **Políticas antimalware**)</span><span class="sxs-lookup"><span data-stu-id="df496-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="df496-183">Vá para a seção **Verificações** Agendadas e Force uma verificação do tipo de verificação selecionado se o computador cliente **estiver offline...** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="df496-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="df496-184">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="df496-184">Click **OK**.</span></span>

4.  <span data-ttu-id="df496-185">[Implantar a política atualizada como de costume](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span><span class="sxs-lookup"><span data-stu-id="df496-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="df496-186">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="df496-186">Related articles</span></span>

- [<span data-ttu-id="df496-187">Implantar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="df496-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df496-188">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="df496-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df496-189">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="df496-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df496-190">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="df496-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df496-191">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="df496-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="df496-192">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="df496-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)