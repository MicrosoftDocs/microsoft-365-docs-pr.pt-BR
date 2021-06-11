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
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878797"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="8c922-104">Configurar e executar verificações do Microsoft Defender Antivírus sob demanda</span><span class="sxs-lookup"><span data-stu-id="8c922-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="8c922-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c922-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c922-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8c922-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8c922-107">Você pode executar uma verificação sob demanda em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="8c922-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="8c922-108">Essas verificações serão iniciais imediatamente e você pode definir parâmetros para a verificação, como o local ou o tipo.</span><span class="sxs-lookup"><span data-stu-id="8c922-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="8c922-109">Ao executar uma verificação, você pode escolher entre três tipos: verificação rápida, verificação completa e verificação personalizada.</span><span class="sxs-lookup"><span data-stu-id="8c922-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="8c922-110">Na maioria dos casos, use uma verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="8c922-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="8c922-111">Uma verificação rápida analisa todos os locais onde pode haver malware registrado para começar com o sistema, como chaves de registro e pastas de inicialização Windows conhecidas.</span><span class="sxs-lookup"><span data-stu-id="8c922-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="8c922-112">Combinado com a proteção sempre em tempo real, que revisa arquivos quando eles são abertos e fechados e sempre que um usuário navega para uma pasta, uma verificação rápida ajuda a fornecer uma proteção forte contra malware que começa com o sistema e malware no nível do kernel.</span><span class="sxs-lookup"><span data-stu-id="8c922-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="8c922-113">Na maioria dos casos, uma verificação rápida é suficiente e é a opção recomendada para verificações agendadas ou sob demanda.</span><span class="sxs-lookup"><span data-stu-id="8c922-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="8c922-114">[Saiba mais sobre tipos de verificação](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span><span class="sxs-lookup"><span data-stu-id="8c922-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c922-115">Microsoft Defender Antivírus é executado no contexto da conta [LocalSystem](/windows/win32/services/localsystem-account) ao executar uma verificação local.</span><span class="sxs-lookup"><span data-stu-id="8c922-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="8c922-116">Para verificações de rede, ele usa o contexto da conta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8c922-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="8c922-117">Se a conta do dispositivo de domínio não tiver permissões apropriadas para acessar o compartilhamento, a verificação não funcionará.</span><span class="sxs-lookup"><span data-stu-id="8c922-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="8c922-118">Verifique se o dispositivo tem permissões para o compartilhamento de rede de acesso.</span><span class="sxs-lookup"><span data-stu-id="8c922-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="8c922-119">Usar Microsoft Endpoint Manager para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="8c922-120">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="8c922-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="8c922-121">Escolha **Endpoint security**  >  **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="8c922-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="8c922-122">Na lista de guias, selecione Windows 10 pontos de extremidade **não salubres**.</span><span class="sxs-lookup"><span data-stu-id="8c922-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="8c922-123">Na lista de ações fornecidas, selecione **Verificação Rápida** (recomendado) ou **Verificação Completa.**</span><span class="sxs-lookup"><span data-stu-id="8c922-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="8c922-124">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="8c922-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="8c922-125">Para obter mais informações sobre como Microsoft Endpoint Manager executar uma verificação, consulte [Tarefas de antimalware](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)e firewall: como executar uma verificação sob demanda.</span><span class="sxs-lookup"><span data-stu-id="8c922-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="8c922-126">Use o mpcmdrun.exe de linha de comando para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="8c922-127">Use o seguinte `-scan` parâmetro:</span><span class="sxs-lookup"><span data-stu-id="8c922-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="8c922-128">Para obter mais informações sobre como usar a ferramenta e parâmetros adicionais, incluindo iniciar uma verificação completa ou definir caminhos, consulte [Usar a](command-line-arguments-microsoft-defender-antivirus.md)ferramenta de linha de comando mpcmdrun.exe para configurar e gerenciar Microsoft Defender Antivírus .</span><span class="sxs-lookup"><span data-stu-id="8c922-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="8c922-129">Usar Microsoft Intune para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="8c922-130">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e faça logoff.</span><span class="sxs-lookup"><span data-stu-id="8c922-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="8c922-131">Na barra lateral, selecione **Dispositivos**  >  **Todos os Dispositivos** e escolha o dispositivo que você deseja examinar.</span><span class="sxs-lookup"><span data-stu-id="8c922-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="8c922-132">Selecione **... Mais**.</span><span class="sxs-lookup"><span data-stu-id="8c922-132">Select **...More**.</span></span> <span data-ttu-id="8c922-133">Nas opções, selecione **Verificação Rápida** (recomendado) ou **Verificação Completa**.</span><span class="sxs-lookup"><span data-stu-id="8c922-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="8c922-134">Usar o Segurança do Windows para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="8c922-135">Consulte [Executar uma verificação no aplicativo Segurança do Windows para](microsoft-defender-security-center-antivirus.md) obter instruções sobre como executar uma verificação em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="8c922-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="8c922-136">Usar cmdlets do PowerShell para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="8c922-137">Use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8c922-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="8c922-138">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender/)Microsoft Defender Antivírus e Defender.</span><span class="sxs-lookup"><span data-stu-id="8c922-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="8c922-139">Use Windows Instrução de Gerenciamento (WMI) para executar uma verificação</span><span class="sxs-lookup"><span data-stu-id="8c922-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="8c922-140">Use o [ **método Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) da **classe MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="8c922-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="8c922-141">Para obter mais informações sobre quais parâmetros são permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="8c922-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

