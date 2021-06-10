---
title: Executar e personalizar verificações sob demanda em Microsoft Defender Antivírus
description: Executar e configurar verificações sob demanda usando o PowerShell, Windows Instrumentação de Gerenciamento ou individualmente nos pontos de extremidade com o aplicativo Segurança do Windows de gerenciamento
keywords: verificação, sob demanda, dos, intune, verificação instantânea
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
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789166"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="3608d-104">Configurar e executar verificações do Microsoft Defender Antivírus sob demanda</span><span class="sxs-lookup"><span data-stu-id="3608d-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="3608d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3608d-105">**Applies to:**</span></span>

- [<span data-ttu-id="3608d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3608d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3608d-107">Você pode executar uma verificação sob demanda em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="3608d-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="3608d-108">Essas verificações serão iniciais imediatamente e você pode definir parâmetros para a verificação, como o local ou o tipo.</span><span class="sxs-lookup"><span data-stu-id="3608d-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="3608d-109">Verificação rápida versus verificação completa</span><span class="sxs-lookup"><span data-stu-id="3608d-109">Quick scan versus full scan</span></span>

<span data-ttu-id="3608d-110">A verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves do Registro e pastas de inicialização Windows conhecidas.</span><span class="sxs-lookup"><span data-stu-id="3608d-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3608d-111">Microsoft Defender Antivírus é executado no contexto da conta [LocalSystem](/windows/win32/services/localsystem-account) ao executar uma verificação local.</span><span class="sxs-lookup"><span data-stu-id="3608d-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="3608d-112">Para verificações de rede, ele usa o contexto da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3608d-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="3608d-113">Se a conta do dispositivo de domínio não tiver permissões apropriadas para acessar o compartilhamento, a verificação não funcionará.</span><span class="sxs-lookup"><span data-stu-id="3608d-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="3608d-114">Verifique se o dispositivo tem permissões para o compartilhamento de rede de acesso.</span><span class="sxs-lookup"><span data-stu-id="3608d-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="3608d-115">Combinado com a funcionalidade de proteção sempre em [tempo real,](configure-real-time-protection-microsoft-defender-antivirus.md)uma verificação rápida ajuda a fornecer uma cobertura forte para malware que começa com o sistema e malware no nível do kernel.</span><span class="sxs-lookup"><span data-stu-id="3608d-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="3608d-116">A proteção sempre em tempo real revisa arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta.</span><span class="sxs-lookup"><span data-stu-id="3608d-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="3608d-117">Por padrão, verificações rápidas são executados em dispositivos removíveis montados, como unidades USB.</span><span class="sxs-lookup"><span data-stu-id="3608d-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="3608d-118">Na maioria dos casos, uma verificação rápida é adequada para encontrar malware que não foi escolhido pela proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="3608d-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="3608d-119">Uma verificação completa pode ser útil quando uma ameaça de malware é relatada em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3608d-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="3608d-120">A verificação pode identificar se há componentes inativos que exigem uma limpeza mais completa.</span><span class="sxs-lookup"><span data-stu-id="3608d-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="3608d-121">No entanto, a Microsoft geralmente recomenda usar verificações rápidas em vez de verificações completas.</span><span class="sxs-lookup"><span data-stu-id="3608d-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="3608d-122">Uma verificação completa pode levar algumas horas ou dias para ser concluída, dependendo da quantidade e do tipo de dados que precisam ser verificados.</span><span class="sxs-lookup"><span data-stu-id="3608d-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="3608d-123">Para saber mais sobre as diferenças entre verificações rápidas e completas, consulte Verificação rápida versus verificação [completa e verificação personalizada.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="3608d-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="3608d-124">Usar Microsoft Endpoint Manager para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="3608d-125">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="3608d-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="3608d-126">Escolha **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="3608d-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="3608d-127">Na lista de guias, selecione Windows 10 pontos de extremidade **não salubres**.</span><span class="sxs-lookup"><span data-stu-id="3608d-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="3608d-128">Na lista de ações fornecidas, selecione **Verificação Rápida** ou **Verificação Completa**.</span><span class="sxs-lookup"><span data-stu-id="3608d-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="3608d-129">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3608d-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="3608d-130">Para obter mais informações sobre como Microsoft Endpoint Manager executar uma verificação, consulte [Tarefas de antimalware](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)e firewall: como executar uma verificação sob demanda.</span><span class="sxs-lookup"><span data-stu-id="3608d-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="3608d-131">Use o mpcmdrun.exe de linha de comando para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="3608d-132">Use o seguinte `-scan` parâmetro:</span><span class="sxs-lookup"><span data-stu-id="3608d-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="3608d-133">Para obter mais informações sobre como usar a ferramenta e parâmetros adicionais, incluindo iniciar uma verificação completa ou definir caminhos, consulte [Usar a](command-line-arguments-microsoft-defender-antivirus.md)ferramenta de linha de comando mpcmdrun.exe para configurar e gerenciar Microsoft Defender Antivírus .</span><span class="sxs-lookup"><span data-stu-id="3608d-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="3608d-134">Usar Microsoft Intune para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="3608d-135">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="3608d-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="3608d-136">Na barra lateral, selecione **Dispositivos > Todos os** Dispositivos e escolha o dispositivo que você deseja examinar.</span><span class="sxs-lookup"><span data-stu-id="3608d-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="3608d-137">Selecione **... Mais**.</span><span class="sxs-lookup"><span data-stu-id="3608d-137">Select **...More**.</span></span> <span data-ttu-id="3608d-138">Nas opções, selecione **Verificação Rápida** ou **Verificação Completa.**</span><span class="sxs-lookup"><span data-stu-id="3608d-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="3608d-139">Usar o Segurança do Windows para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="3608d-140">Consulte [Executar uma verificação no aplicativo Segurança do Windows para](microsoft-defender-security-center-antivirus.md) obter instruções sobre como executar uma verificação em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="3608d-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="3608d-141">Usar cmdlets do PowerShell para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="3608d-142">Use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3608d-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="3608d-143">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.</span><span class="sxs-lookup"><span data-stu-id="3608d-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="3608d-144">Use Windows Instrução de Gerenciamento (WMI) para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="3608d-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="3608d-145">Use o [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) da **classe MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="3608d-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="3608d-146">Para obter mais informações sobre quais parâmetros são permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="3608d-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="3608d-147">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="3608d-147">Related articles</span></span>

- [<span data-ttu-id="3608d-148">Configurar opções de verificação do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="3608d-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3608d-149">Configurar verificações Microsoft Defender Antivírus agendadas</span><span class="sxs-lookup"><span data-stu-id="3608d-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3608d-150">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="3608d-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)