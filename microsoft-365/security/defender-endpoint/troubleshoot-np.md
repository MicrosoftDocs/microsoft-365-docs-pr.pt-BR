---
title: Solucionar problemas com a proteção de rede
description: Recursos e código de exemplo para solucionar problemas com a proteção de rede no Microsoft Defender para Ponto de Extremidade.
keywords: solução de problemas, erro, correção, windows defender por exemplo, asr, regras, quadris, solução de problemas, auditoria, exclusão, falso positivo, quebrado, bloqueado, microsoft defender para ponto de extremidade, proteção avançada contra ameaças do Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.date: 01/26/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 165c17bc820403ebfbbe5cdfe3ca856e8416c593
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053855"
---
# <a name="troubleshoot-network-protection"></a><span data-ttu-id="58e21-104">Solucionar problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="58e21-104">Troubleshoot network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="58e21-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="58e21-105">**Applies to:**</span></span>
- [<span data-ttu-id="58e21-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="58e21-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="58e21-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58e21-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="58e21-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="58e21-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58e21-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="58e21-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="58e21-110">Ao usar a [proteção de rede,](network-protection.md) você pode encontrar problemas, como:</span><span class="sxs-lookup"><span data-stu-id="58e21-110">When you use [Network protection](network-protection.md) you may encounter issues, such as:</span></span>

- <span data-ttu-id="58e21-111">A proteção de rede bloqueia um site seguro (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="58e21-111">Network protection blocks a website that is safe (false positive)</span></span>
- <span data-ttu-id="58e21-112">A proteção de rede falha ao bloquear um site mal-intencionado suspeito ou conhecido (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="58e21-112">Network protection fails to block a suspicious or known malicious website (false negative)</span></span>

<span data-ttu-id="58e21-113">Há quatro etapas para solucionar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="58e21-113">There are four steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="58e21-114">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="58e21-114">Confirm prerequisites</span></span>
2. <span data-ttu-id="58e21-115">Usar o modo de auditoria para testar a regra</span><span class="sxs-lookup"><span data-stu-id="58e21-115">Use audit mode to test the rule</span></span>
3. <span data-ttu-id="58e21-116">Adicionar exclusões para a regra especificada (para falsos positivos)</span><span class="sxs-lookup"><span data-stu-id="58e21-116">Add exclusions for the specified rule (for false positives)</span></span>
4. <span data-ttu-id="58e21-117">Enviar logs de suporte</span><span class="sxs-lookup"><span data-stu-id="58e21-117">Submit support logs</span></span>

## <a name="confirm-prerequisites"></a><span data-ttu-id="58e21-118">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="58e21-118">Confirm prerequisites</span></span>

<span data-ttu-id="58e21-119">A proteção de rede funcionará apenas em dispositivos com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="58e21-119">Network protection will only work on devices with the following conditions:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="58e21-120">Os pontos de extremidade estão executando o Windows 10 Pro ou Enterprise edition, versão 1709 ou superior.</span><span class="sxs-lookup"><span data-stu-id="58e21-120">Endpoints are running Windows 10 Pro or Enterprise edition, version 1709 or higher.</span></span>
> - <span data-ttu-id="58e21-121">Os pontos de extremidade estão usando o Microsoft Defender Antivírus como o único aplicativo de proteção antivírus.</span><span class="sxs-lookup"><span data-stu-id="58e21-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="58e21-122">[Veja o que acontece quando você está usando uma solução antivírus que não seja da Microsoft.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="58e21-122">[See what happens when you are using a non-Microsoft antivirus solution](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>
> - <span data-ttu-id="58e21-123">[A proteção em tempo real](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="58e21-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="58e21-124">[A proteção entregue na nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="58e21-124">[Cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) is enabled.</span></span>
> - <span data-ttu-id="58e21-125">O modo de auditoria não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="58e21-125">Audit mode is not enabled.</span></span> <span data-ttu-id="58e21-126">Use [a Política de](enable-network-protection.md#group-policy) Grupo para definir a regra como **Desabilitada** (valor: **0**).</span><span class="sxs-lookup"><span data-stu-id="58e21-126">Use [Group Policy](enable-network-protection.md#group-policy) to set the rule to **Disabled** (value: **0**).</span></span>

## <a name="use-audit-mode"></a><span data-ttu-id="58e21-127">Usar o modo de auditoria</span><span class="sxs-lookup"><span data-stu-id="58e21-127">Use audit mode</span></span>

<span data-ttu-id="58e21-128">Você pode habilitar a proteção de rede no modo de auditoria e visitar um site que criamos para demonstração do recurso.</span><span class="sxs-lookup"><span data-stu-id="58e21-128">You can enable network protection in audit mode and then visit a website that we've created to demo the feature.</span></span> <span data-ttu-id="58e21-129">Todas as conexões de site serão permitidas pela proteção de rede, mas um evento será registrado para indicar qualquer conexão que tenha sido bloqueada se a proteção de rede estivesse habilitada.</span><span class="sxs-lookup"><span data-stu-id="58e21-129">All website connections will be allowed by network protection but an event will be logged to indicate any connection that would have been blocked if network protection was enabled.</span></span>

1. <span data-ttu-id="58e21-130">Definir a proteção de rede como **modo de auditoria.**</span><span class="sxs-lookup"><span data-stu-id="58e21-130">Set network protection to **Audit mode**.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection AuditMode
   ```

2. <span data-ttu-id="58e21-131">Execute a atividade de conexão que está causando um problema (por exemplo, tente visitar o site ou conecte-se ao endereço IP que você faz ou não deseja bloquear).</span><span class="sxs-lookup"><span data-stu-id="58e21-131">Perform the connection activity that is causing an issue (for example, attempt to visit the site, or connect to the IP address you do or don't want to block).</span></span>

3. <span data-ttu-id="58e21-132">[Revise os logs de eventos de](network-protection.md#review-network-protection-events-in-windows-event-viewer) proteção de rede para ver se o recurso teria bloqueado a conexão se tivesse sido definido como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="58e21-132">[Review the network protection event logs](network-protection.md#review-network-protection-events-in-windows-event-viewer) to see if the feature would have blocked the connection if it had been set to **Enabled**.</span></span>
   
   <span data-ttu-id="58e21-133">Se a proteção de rede não estiver bloqueando uma conexão que você espera que ela bloqueie, habilita o recurso.</span><span class="sxs-lookup"><span data-stu-id="58e21-133">If network protection is not blocking a connection that you are expecting it should block, enable the feature.</span></span>

   ```PowerShell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="58e21-134">Relatar um falso positivo ou falso negativo</span><span class="sxs-lookup"><span data-stu-id="58e21-134">Report a false positive or false negative</span></span>

<span data-ttu-id="58e21-135">Se você testou o recurso com o site de demonstração e com o modo de auditoria, e a proteção de rede está funcionando em cenários pré-configurados, mas não está funcionando conforme o esperado para uma conexão específica, use o formulário de envio baseado na Web do [Windows Defender Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) para relatar um falso negativo ou falso positivo para proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="58e21-135">If you've tested the feature with the demo site and with audit mode, and network protection is working on pre-configured scenarios, but is not working as expected for a specific connection, use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="58e21-136">Com uma assinatura do E5, você também pode fornecer um [link para qualquer alerta associado.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="58e21-136">With an E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

<span data-ttu-id="58e21-137">Consulte [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="58e21-137">See [Address false positives/negatives in Microsoft Defender for Endpoint](defender-endpoint-false-positives-negatives.md).</span></span>

## <a name="exclude-website-from-network-protection-scope"></a><span data-ttu-id="58e21-138">Excluir site do escopo de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="58e21-138">Exclude website from network protection scope</span></span>

<span data-ttu-id="58e21-139">Para permitir que o site que está sendo bloqueado (falso positivo), adicione sua URL à [lista de sites confiáveis](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span><span class="sxs-lookup"><span data-stu-id="58e21-139">To allow the website that is being blocked (false positive), add its URL to the [list of trusted sites](https://blogs.msdn.microsoft.com/asiatech/2014/08/19/how-to-add-web-sites-to-trusted-sites-via-gpo-from-dc-installed-ie10-or-higher-ie-version/).</span></span> <span data-ttu-id="58e21-140">Os recursos da Web desta lista ignoram a verificação de proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="58e21-140">Web resources from this list bypass the network protection check.</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="58e21-141">Coletar dados de diagnóstico para envios de arquivos</span><span class="sxs-lookup"><span data-stu-id="58e21-141">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="58e21-142">Quando você relata um problema com a proteção de rede, é solicitado a coletar e enviar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="58e21-142">When you report a problem with network protection, you are asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="58e21-143">Abra um prompt de comando elevado e altere para o Windows Defender diretório:</span><span class="sxs-lookup"><span data-stu-id="58e21-143">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd c:\program files\windows defender
   ```

2. <span data-ttu-id="58e21-144">Execute este comando para gerar os logs de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="58e21-144">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="58e21-145">Por padrão, eles são salvos em C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span><span class="sxs-lookup"><span data-stu-id="58e21-145">By default, they are saved to C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab.</span></span> <span data-ttu-id="58e21-146">Anexe o arquivo ao formulário de envio.</span><span class="sxs-lookup"><span data-stu-id="58e21-146">Attach the file to the submission form.</span></span>

## <a name="related-topics"></a><span data-ttu-id="58e21-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="58e21-147">Related topics</span></span>

- [<span data-ttu-id="58e21-148">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="58e21-148">Network protection</span></span>](network-protection.md)
- [<span data-ttu-id="58e21-149">Avaliar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="58e21-149">Evaluate network protection</span></span>](evaluate-network-protection.md)
- [<span data-ttu-id="58e21-150">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="58e21-150">Enable network protection</span></span>](enable-network-protection.md)
- [<span data-ttu-id="58e21-151">Resolver falsos positivos/negativos no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="58e21-151">Address false positives/negatives in Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
