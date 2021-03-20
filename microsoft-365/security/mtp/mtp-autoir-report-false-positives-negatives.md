---
title: Manipular falsos positivos ou falsos negativos no AIR no Microsoft 365 Defender
description: Algo falhou ou errou ao ser detectado pelo AIR no Microsoft 365 Defender? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: ccfb2c8d9395d3f64b20980b156ed51545967101
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917065"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="2c5ae-105">Manipular falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="2c5ae-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2c5ae-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2c5ae-106">**Applies to:**</span></span>
- <span data-ttu-id="2c5ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c5ae-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="2c5ae-108">Falsos positivos/negativos podem ocorrer ocasionalmente com qualquer solução de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="2c5ae-109">Se [os recursos automatizados](mtp-autoir.md) de investigação e resposta no Microsoft 365 Defender não foram detectados ou detectaram algo incorretamente, há etapas que sua equipe de operações de segurança pode seguir:</span><span class="sxs-lookup"><span data-stu-id="2c5ae-109">If [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="2c5ae-110">[Relatar um falso positivo/negativo para a Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="2c5ae-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="2c5ae-111">[Ajuste seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="2c5ae-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="2c5ae-112">[Desfazer ações de correção que foram tomadas em dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="2c5ae-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="2c5ae-113">As seções a seguir descrevem como executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="2c5ae-114">Relatar um falso positivo/negativo à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="2c5ae-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="2c5ae-115">Item perdido ou detectado incorretamente</span><span class="sxs-lookup"><span data-stu-id="2c5ae-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="2c5ae-116">Serviço</span><span class="sxs-lookup"><span data-stu-id="2c5ae-116">Service</span></span>  |<span data-ttu-id="2c5ae-117">O que fazer</span><span class="sxs-lookup"><span data-stu-id="2c5ae-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2c5ae-118">- Mensagem de email</span><span class="sxs-lookup"><span data-stu-id="2c5ae-118">- Email message</span></span> <br/><span data-ttu-id="2c5ae-119">- Anexo de email</span><span class="sxs-lookup"><span data-stu-id="2c5ae-119">- Email attachment</span></span> <br/><span data-ttu-id="2c5ae-120">- URL em uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="2c5ae-120">- URL in an email message</span></span><br/><span data-ttu-id="2c5ae-121">- URL em um arquivo do Office</span><span class="sxs-lookup"><span data-stu-id="2c5ae-121">- URL in an Office file</span></span>      |[<span data-ttu-id="2c5ae-122">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="2c5ae-122">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)        |[<span data-ttu-id="2c5ae-123">Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para verificação</span><span class="sxs-lookup"><span data-stu-id="2c5ae-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="2c5ae-124">Arquivo ou aplicativo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="2c5ae-124">File or app on a device</span></span>    |[<span data-ttu-id="2c5ae-125">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c5ae-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="2c5ae-126">Enviar um arquivo à Microsoft para análise de malware</span><span class="sxs-lookup"><span data-stu-id="2c5ae-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="2c5ae-127">Ajustar um alerta para evitar que falsos positivos se repitam</span><span class="sxs-lookup"><span data-stu-id="2c5ae-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="2c5ae-128">Cenário</span><span class="sxs-lookup"><span data-stu-id="2c5ae-128">Scenario</span></span> |<span data-ttu-id="2c5ae-129">Serviço</span><span class="sxs-lookup"><span data-stu-id="2c5ae-129">Service</span></span> |<span data-ttu-id="2c5ae-130">O que fazer</span><span class="sxs-lookup"><span data-stu-id="2c5ae-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="2c5ae-131">- Um alerta é disparado por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="2c5ae-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="2c5ae-132">- Um alerta é impreciso</span><span class="sxs-lookup"><span data-stu-id="2c5ae-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="2c5ae-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2c5ae-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="2c5ae-134">ou</span><span class="sxs-lookup"><span data-stu-id="2c5ae-134">or</span></span> <br/>[<span data-ttu-id="2c5ae-135">Detecção avançada de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="2c5ae-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="2c5ae-136">Gerenciar alertas no portal de Segurança do Aplicativo na Nuvem</span><span class="sxs-lookup"><span data-stu-id="2c5ae-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="2c5ae-137">Um arquivo, endereço IP, URL ou domínio é tratado como malware em um dispositivo, mesmo que seja seguro</span><span class="sxs-lookup"><span data-stu-id="2c5ae-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="2c5ae-138">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c5ae-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="2c5ae-139">Criar um indicador personalizado com uma ação "Permitir"</span><span class="sxs-lookup"><span data-stu-id="2c5ae-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="2c5ae-140">Desfazer uma ação de correção que foi tomada em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="2c5ae-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="2c5ae-141">Se uma ação de correção tiver sido tomada em uma entidade (como um dispositivo ou uma mensagem de email) e a entidade afetada não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção no Centro de Ações [.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="2c5ae-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

1. <span data-ttu-id="2c5ae-142">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="2c5ae-143">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="2c5ae-144">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="2c5ae-145">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="2c5ae-146">No painel de sobrevoos, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="2c5ae-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="2c5ae-147">Consulte [Desfazer ações concluídas](mtp-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="2c5ae-147">See [Undo completed actions](mtp-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="2c5ae-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c5ae-148">See also</span></span>

- [<span data-ttu-id="2c5ae-149">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="2c5ae-149">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="2c5ae-150">Busca proativamente por ameaças com busca avançada no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c5ae-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2c5ae-151">Resolver falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c5ae-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)