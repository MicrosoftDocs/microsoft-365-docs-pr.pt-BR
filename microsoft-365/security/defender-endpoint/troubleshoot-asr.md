---
title: Solucionar problemas com regras de redução de superfície de ataque
description: Recursos e código de exemplo para solucionar problemas com regras de redução de superfície de ataque no Microsoft Defender para Ponto de Extremidade.
keywords: troubleshoot, error, fix, windows defender eg, asr, rules, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c5c76553ff3f0b32def5fbafbf2c8f010e49eeb2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845411"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="ed2f3-104">Solucionar problemas de regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ed2f3-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ed2f3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ed2f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="ed2f3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ed2f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ed2f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ed2f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ed2f3-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ed2f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ed2f3-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="ed2f3-110">Quando você usa regras [de redução de superfície de](attack-surface-reduction.md) ataque, você pode ter problemas, como:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="ed2f3-111">Uma regra bloqueia um arquivo, um processo ou executa alguma outra ação que não deve (falso positivo)</span><span class="sxs-lookup"><span data-stu-id="ed2f3-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="ed2f3-112">Uma regra não funciona conforme descrito ou não bloqueia um arquivo ou processo que deve (falso negativo)</span><span class="sxs-lookup"><span data-stu-id="ed2f3-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="ed2f3-113">Há quatro etapas para solucionar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="ed2f3-114">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ed2f3-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="ed2f3-115">Usar o modo de auditoria para testar a regra</span><span class="sxs-lookup"><span data-stu-id="ed2f3-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="ed2f3-116">[Adicionar exclusões para a regra especificada](#add-exclusions-for-a-false-positive) (para falsos positivos)</span><span class="sxs-lookup"><span data-stu-id="ed2f3-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="ed2f3-117">Enviar logs de suporte</span><span class="sxs-lookup"><span data-stu-id="ed2f3-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="ed2f3-118">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ed2f3-118">Confirm prerequisites</span></span>

<span data-ttu-id="ed2f3-119">As regras de redução de superfície de ataque funcionarão apenas em dispositivos com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="ed2f3-120">Os pontos de extremidade estão executando Windows 10 Enterprise versão 1709 (também conhecida como Atualização de Criadores de Fall).</span><span class="sxs-lookup"><span data-stu-id="ed2f3-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="ed2f3-121">Os pontos de extremidade estão usando Microsoft Defender Antivírus como o único aplicativo de proteção antivírus.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="ed2f3-122">[O uso de qualquer outro aplicativo antivírus fará com que o Microsoft Defender AV se desabilite](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span><span class="sxs-lookup"><span data-stu-id="ed2f3-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="ed2f3-123">[A proteção em tempo real](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) está habilitada.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-123">[Real-time protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="ed2f3-124">O modo de auditoria não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="ed2f3-125">Use a Política de Grupo para definir a regra como **Desabilitada** (valor: **0**) conforme descrito em [Habilitar regras de](enable-attack-surface-reduction.md)redução de superfície de ataque .</span><span class="sxs-lookup"><span data-stu-id="ed2f3-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="ed2f3-126">Se todos esses pré-requisitos foram atendidos, prossiga para a próxima etapa para testar a regra no modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="ed2f3-127">Usar o modo de auditoria para testar a regra</span><span class="sxs-lookup"><span data-stu-id="ed2f3-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="ed2f3-128">Você pode visitar o site de campo de teste do Windows Defender no [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que as regras de redução de superfície de ataque geralmente estão funcionando para cenários e processos pré-configurados em um dispositivo, ou você pode usar o modo de auditoria, que permite regras apenas para relatórios.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="ed2f3-129">Siga estas instruções em [Usar a ferramenta de demonstração](evaluate-attack-surface-reduction.md) para ver como funcionam as regras de redução de superfície de ataque para testar a regra específica com a qual você está encontrando problemas.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="ed2f3-130">Habilitar o modo de auditoria para a regra específica que você deseja testar.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="ed2f3-131">Use a Política de Grupo para definir a regra como **Modo de** Auditoria (valor: **2**) conforme descrito em [Habilitar regras de](enable-attack-surface-reduction.md)redução de superfície de ataque .</span><span class="sxs-lookup"><span data-stu-id="ed2f3-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="ed2f3-132">O modo de auditoria permite que a regra reporte o arquivo ou o processo, mas ainda permitirá que ele seja executado.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="ed2f3-133">Execute a atividade que está causando um problema (por exemplo, abra ou execute o arquivo ou processo que deve ser bloqueado, mas está sendo permitido).</span><span class="sxs-lookup"><span data-stu-id="ed2f3-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="ed2f3-134">[Revise os logs de](attack-surface-reduction.md) eventos de regra de redução de superfície de ataque para ver se a regra teria bloqueado o arquivo ou o processo se a regra tivesse sido definida como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="ed2f3-135">Se uma regra não estiver bloqueando um arquivo ou processo que você espera que ele bloqueie, primeiro verifique se o modo de auditoria está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="ed2f3-136">O modo de auditoria pode ter sido habilitado para testar outro recurso ou por um script do PowerShell automatizado e pode não ter sido desabilitado após a conclusão dos testes.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="ed2f3-137">Se você testou a regra com a ferramenta de demonstração e com o modo de auditoria, e as regras de redução de superfície de ataque estão funcionando em cenários pré-configurados, mas a regra não está funcionando conforme esperado, prossiga para uma das seções a seguir com base em sua situação:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="ed2f3-138">Se a regra de redução de superfície de ataque estiver bloqueando algo que não deve ser bloqueado (também conhecido como falso positivo), primeiro você poderá adicionar uma exclusão de regra de redução de superfície [de ataque.](#add-exclusions-for-a-false-positive)</span><span class="sxs-lookup"><span data-stu-id="ed2f3-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="ed2f3-139">Se a regra de redução de superfície de ataque não estiver bloqueando algo que ela deve bloquear (também conhecido como falso negativo), você poderá prosseguir imediatamente para a última etapa, coletando dados de diagnóstico e enviando o problema para [nós](#collect-diagnostic-data-for-file-submissions).</span><span class="sxs-lookup"><span data-stu-id="ed2f3-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="ed2f3-140">Adicionar exclusões para um falso positivo</span><span class="sxs-lookup"><span data-stu-id="ed2f3-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="ed2f3-141">Se a regra de redução de superfície de ataque estiver bloqueando algo que não deve ser bloqueado (também conhecido como falso positivo), você poderá adicionar exclusões para impedir que as regras de redução de superfície de ataque avaliam os arquivos ou pastas excluídos.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="ed2f3-142">Para adicionar uma exclusão, consulte [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="ed2f3-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="ed2f3-143">Você pode especificar arquivos e pastas individuais a serem excluídos, mas não pode especificar regras individuais.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="ed2f3-144">Isso significa que todos os arquivos ou pastas excluídos serão excluídos de todas as regras ASR.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="ed2f3-145">Relatar um falso positivo ou falso negativo</span><span class="sxs-lookup"><span data-stu-id="ed2f3-145">Report a false positive or false negative</span></span>

<span data-ttu-id="ed2f3-146">Use o Windows Defender de envio baseado na Web do [Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) para relatar um falso negativo ou falso positivo para proteção de rede.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="ed2f3-147">Com uma assinatura Windows E5, você também pode fornecer um [link para qualquer alerta associado.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="ed2f3-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="ed2f3-148">Coletar dados de diagnóstico para envios de arquivos</span><span class="sxs-lookup"><span data-stu-id="ed2f3-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="ed2f3-149">Quando você relata um problema com regras de redução de superfície de ataque, é solicitado a coletar e enviar dados de diagnóstico que podem ser usados pelo suporte da Microsoft e equipes de engenharia para ajudar a solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="ed2f3-150">Abra um prompt de comando elevado e altere para o Windows Defender diretório:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="ed2f3-151">Execute este comando para gerar os logs de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ed2f3-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="ed2f3-152">Por padrão, eles são salvos em `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="ed2f3-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="ed2f3-153">Anexe o arquivo ao formulário de envio.</span><span class="sxs-lookup"><span data-stu-id="ed2f3-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ed2f3-154">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="ed2f3-154">Related articles</span></span>

- [<span data-ttu-id="ed2f3-155">Regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ed2f3-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="ed2f3-156">Habilitar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ed2f3-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="ed2f3-157">Avaliar as regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="ed2f3-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
