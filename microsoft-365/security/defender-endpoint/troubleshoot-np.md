---
title: Solucionar problemas com a proteção de rede
description: Recursos e código de exemplo para solucionar problemas com a proteção de rede no Microsoft Defender para Ponto de Extremidade.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 481a8f15d6a41bda8dc866ce40d98c4f3717223d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844047"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="9253b-104">Solucionar problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="9253b-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9253b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9253b-105">**Applies to:**</span></span>
- [<span data-ttu-id="9253b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9253b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9253b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9253b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="9253b-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9253b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9253b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9253b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="9253b-110">Ao usar a [proteção de rede,](network-protection.md) você pode encontrar problemas, como:</span><span class="sxs-lookup"><span data-stu-id="9253b-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="9253b-111">A proteção de rede bloqueia um site seguro (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="9253b-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="9253b-112">A proteção de rede falha ao bloquear um site mal-intencionado suspeito ou conhecido (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="9253b-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="9253b-113">Há quatro etapas para solucionar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="9253b-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="9253b-114">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9253b-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="9253b-115">Usar o modo de auditoria para testar a regra</span><span class="sxs-lookup"><span data-stu-id="9253b-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="9253b-116">Adicionar exclusões para a regra especificada (para falsos positivos)</span><span class="sxs-lookup"><span data-stu-id="9253b-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="9253b-117">Enviar logs de suporte</span><span class="sxs-lookup"><span data-stu-id="9253b-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="9253b-118">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9253b-118">Confirm prerequisites</span></span>

<span data-ttu-id="9253b-119">A proteção de rede funcionará apenas em dispositivos com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="9253b-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="9253b-120">Os pontos de extremidade estão executando Windows 10 Pro ou Enterprise edição, versão 1709 ou superior.</span><span class="sxs-lookup"><span data-stu-id="9253b-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="9253b-121">Os pontos de extremidade estão usando Microsoft Defender Antivírus como o único aplicativo de proteção antivírus.</span><span class="sxs-lookup"><span data-stu-id="9253b-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="9253b-122">[Veja o que acontece quando você está usando uma solução antivírus que não seja da Microsoft.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="9253b-122">[See what happens when you are using a non-Microsoft antivirus solution](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="9253b-123">[A proteção em tempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9253b-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="9253b-124">[A proteção entregue na nuvem](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9253b-124">[Cloud-delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="9253b-125">O modo de auditoria não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="9253b-125">Audit mode is not enabled.</span></span> <span data-ttu-id="9253b-126">Use [a Política de](enable-network-protection.md#group-policy) Grupo para definir a regra como **Desabilitada** (valor: **0**).</span><span class="sxs-lookup"><span data-stu-id="9253b-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="9253b-127">Usar o modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="9253b-127">Use audit mode</span></span>

<span data-ttu-id="9253b-128">Você pode habilitar a proteção de rede no modo de auditoria e visitar um site que criamos para demonstração do recurso.</span><span class="sxs-lookup"><span data-stu-id="9253b-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="9253b-129">Todas as conexões de site serão permitidas pela proteção de rede, mas um evento será registrado para indicar qualquer conexão que tenha sido bloqueada se a proteção de rede estivesse habilitada.</span><span class="sxs-lookup"><span data-stu-id="9253b-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="9253b-130">Definir a proteção de rede como **modo de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="9253b-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="9253b-131">Execute a atividade de conexão que está causando um problema (por exemplo, tente visitar o site ou conecte-se ao endereço IP que você faz ou não deseja bloquear).</span><span class="sxs-lookup"><span data-stu-id="9253b-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="9253b-132">[Revise os logs de eventos de](network-protection.md#review-network-protection-events-in-windows-event-viewer) proteção de rede para ver se o recurso teria bloqueado a conexão se tivesse sido definido como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="9253b-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="9253b-133">Se a proteção de rede não estiver bloqueando uma conexão que você espera que ela bloqueie, habilita o recurso.</span><span class="sxs-lookup"><span data-stu-id="9253b-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="9253b-134">Relatar um falso positivo ou falso negativo</span><span class="sxs-lookup"><span data-stu-id="9253b-134">Report a false positive or false negative</span></span>

<span data-ttu-id="9253b-135">Se você testou o recurso com o site de demonstração e com o modo de auditoria, e a proteção de rede está funcionando em cenários pré-configurados, mas não está funcionando conforme o esperado para uma conexão específica, use o formulário de envio baseado na Web do [Windows Defender Security Intelligence para](https://www.microsoft.com/wdsi/filesubmission) relatar um falso negativo ou falso positivo para proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="9253b-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="9253b-136">Com uma assinatura do E5, você também pode fornecer um [link para qualquer alerta associado.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="9253b-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="9253b-137">Consulte [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="9253b-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="9253b-138">Excluir site do escopo de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="9253b-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="9253b-139">Para permitir que o site que está sendo bloqueado (falso positivo), adicione sua URL à [lista de sites confiáveis](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span><span class="sxs-lookup"><span data-stu-id="9253b-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="9253b-140">Os recursos da Web desta lista ignoram a verificação de proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="9253b-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="9253b-141">Coletar dados de diagnóstico para envios de arquivos</span><span class="sxs-lookup"><span data-stu-id="9253b-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="9253b-142">Quando você relata um problema com a proteção de rede, é solicitado a coletar e enviar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="9253b-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="9253b-143">Abra um prompt de comando elevado e altere para o Windows Defender diretório:</span><span class="sxs-lookup"><span data-stu-id="9253b-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="9253b-144">Execute este comando para gerar os logs de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="9253b-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="9253b-145">Anexe o arquivo ao formulário de envio.</span><span class="sxs-lookup"><span data-stu-id="9253b-145">Attach the file to the submission form.</span></span> <span data-ttu-id="9253b-146">Por padrão, os logs de diagnóstico são salvos em `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="9253b-146">By default, diagnostic logs are saved at `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> 

## <a name="resolve-connectivity-issues-with-network-protection-for-e5-customers"></a><span data-ttu-id="9253b-147">Resolver problemas de conectividade com a proteção de rede (para clientes E5)</span><span class="sxs-lookup"><span data-stu-id="9253b-147">Resolve connectivity issues with network protection (for E5 customers)</span></span>

<span data-ttu-id="9253b-148">Devido ao ambiente em que a proteção de rede é executado, a Microsoft não consegue ver as configurações de proxy do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9253b-148">Due to the environment where network protection runs, Microsoft is unable to see your operating system proxy settings.</span></span> <span data-ttu-id="9253b-149">Em alguns casos, os clientes de proteção de rede não conseguem alcançar o serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="9253b-149">In some cases, network protection clients are unable to reach the cloud service.</span></span> <span data-ttu-id="9253b-150">Para resolver problemas de conectividade com a proteção de rede, configure uma das seguintes chaves do Registro para que a proteção de rede fique ciente da configuração de proxy:</span><span class="sxs-lookup"><span data-stu-id="9253b-150">To resolve connectivity issues with network protection, configure one of the following registry keys so that network protection becomes aware of the proxy configuration:</span></span>

```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
```

<span data-ttu-id="9253b-151">---OR---</span><span class="sxs-lookup"><span data-stu-id="9253b-151">---OR---</span></span>


```powershell
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f
```

<span data-ttu-id="9253b-152">Você pode configurar a chave do Registro usando o PowerShell, Microsoft Endpoint Manager ou Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="9253b-152">You can configure the registry key by using PowerShell, Microsoft Endpoint Manager, or Group Policy.</span></span> <span data-ttu-id="9253b-153">Aqui estão alguns recursos para ajudar:</span><span class="sxs-lookup"><span data-stu-id="9253b-153">Here are some resources to help:</span></span>
- [<span data-ttu-id="9253b-154">Trabalhando com chaves do Registro</span><span class="sxs-lookup"><span data-stu-id="9253b-154">Working with Registry Keys</span></span>](/powershell/scripting/samples/working-with-registry-keys)
- [<span data-ttu-id="9253b-155">Configurar configurações de cliente personalizadas para Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="9253b-155">Configure custom client settings for Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-configure-client)
- [<span data-ttu-id="9253b-156">Use as configurações da Política de Grupo para gerenciar Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="9253b-156">Use Group Policy settings to manage Endpoint Protection</span></span>](/mem/configmgr/protect/deploy-use/endpoint-protection-group-policies)

## <a name="see-also"></a><span data-ttu-id="9253b-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="9253b-157">See also</span></span>

- [<span data-ttu-id="9253b-158">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="9253b-158">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="9253b-159">Avaliar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="9253b-159">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="9253b-160">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="9253b-160">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="9253b-161">Resolver falsos positivos/negativos no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9253b-161">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
