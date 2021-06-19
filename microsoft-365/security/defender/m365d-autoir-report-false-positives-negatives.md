---
title: Resolver falsos positivos ou falsos negativos em Microsoft 365 Defender
description: Algo falhou ou errou ao ser detectado pelo AIR Microsoft 365 Defender? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022529"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="911d1-105">Resolver falsos positivos ou falsos negativos em Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="911d1-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="911d1-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="911d1-106">**Applies to:**</span></span>
- <span data-ttu-id="911d1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="911d1-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="911d1-108">Falsos positivos ou negativos podem ocorrer ocasionalmente com qualquer solução de proteção contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="911d1-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="911d1-109">Se [os recursos automatizados de investigação](m365d-autoir.md) e resposta Microsoft 365 Defender algo perdido ou detectado incorretamente, há etapas que sua equipe de operações de segurança pode seguir:</span><span class="sxs-lookup"><span data-stu-id="911d1-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="911d1-110">Relatar um falso positivo/negativo para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="911d1-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="911d1-111">[Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário)</span><span class="sxs-lookup"><span data-stu-id="911d1-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="911d1-112">Desfazer ações de correção que foram tomadas em dispositivos</span><span class="sxs-lookup"><span data-stu-id="911d1-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="911d1-113">As seções a seguir descrevem como executar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="911d1-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="911d1-114">Relatar um falso positivo/negativo à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="911d1-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="911d1-115">Item perdido ou detectado incorretamente</span><span class="sxs-lookup"><span data-stu-id="911d1-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="911d1-116">Serviço</span><span class="sxs-lookup"><span data-stu-id="911d1-116">Service</span></span>  |<span data-ttu-id="911d1-117">O que fazer</span><span class="sxs-lookup"><span data-stu-id="911d1-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="911d1-118">- Mensagem de email</span><span class="sxs-lookup"><span data-stu-id="911d1-118">- Email message</span></span> <br/><span data-ttu-id="911d1-119">- Anexo de email</span><span class="sxs-lookup"><span data-stu-id="911d1-119">- Email attachment</span></span> <br/><span data-ttu-id="911d1-120">- URL em uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="911d1-120">- URL in an email message</span></span><br/><span data-ttu-id="911d1-121">- URL em um arquivo Office de dados</span><span class="sxs-lookup"><span data-stu-id="911d1-121">- URL in an Office file</span></span>      |[<span data-ttu-id="911d1-122">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="911d1-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="911d1-123">Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para verificação</span><span class="sxs-lookup"><span data-stu-id="911d1-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="911d1-124">Arquivo ou aplicativo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="911d1-124">File or app on a device</span></span>    |[<span data-ttu-id="911d1-125">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="911d1-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="911d1-126">Enviar um arquivo à Microsoft para análise de malware</span><span class="sxs-lookup"><span data-stu-id="911d1-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="911d1-127">Ajustar um alerta para evitar que falsos positivos se repitam</span><span class="sxs-lookup"><span data-stu-id="911d1-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="911d1-128">Cenário</span><span class="sxs-lookup"><span data-stu-id="911d1-128">Scenario</span></span> |<span data-ttu-id="911d1-129">Serviço</span><span class="sxs-lookup"><span data-stu-id="911d1-129">Service</span></span> |<span data-ttu-id="911d1-130">O que fazer</span><span class="sxs-lookup"><span data-stu-id="911d1-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="911d1-131">- Um alerta é disparado por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="911d1-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="911d1-132">- Um alerta é impreciso</span><span class="sxs-lookup"><span data-stu-id="911d1-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="911d1-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="911d1-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="911d1-134">ou</span><span class="sxs-lookup"><span data-stu-id="911d1-134">or</span></span> <br/>[<span data-ttu-id="911d1-135">Proteção contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="911d1-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="911d1-136">Gerenciar alertas no Cloud App Security portal</span><span class="sxs-lookup"><span data-stu-id="911d1-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="911d1-137">Um arquivo, endereço IP, URL ou domínio é tratado como malware em um dispositivo, mesmo que seja seguro</span><span class="sxs-lookup"><span data-stu-id="911d1-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="911d1-138">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="911d1-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="911d1-139">Criar um indicador personalizado com uma ação "Permitir"</span><span class="sxs-lookup"><span data-stu-id="911d1-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="911d1-140">Desfazer uma ação de correção que foi tomada em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="911d1-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="911d1-141">Se uma ação de correção tiver sido tomada em uma entidade (como um dispositivo ou uma mensagem de email) e a entidade afetada não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção no Centro de Ações [.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="911d1-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="911d1-142">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="911d1-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="911d1-143">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="911d1-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="911d1-144">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="911d1-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="911d1-145">Seu painel de sobrevoo é aberto.</span><span class="sxs-lookup"><span data-stu-id="911d1-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="911d1-146">No painel de sobrevoos, selecione **Desfazer**.</span><span class="sxs-lookup"><span data-stu-id="911d1-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="911d1-147">Consulte [Desfazer ações concluídas](m365d-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="911d1-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="911d1-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="911d1-148">See also</span></span>

- [<span data-ttu-id="911d1-149">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="911d1-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="911d1-150">Busca proativamente por ameaças com busca avançada em Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="911d1-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
