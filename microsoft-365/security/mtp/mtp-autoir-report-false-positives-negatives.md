---
title: Tratar falsos positivos ou falsos negativos no AIR no Microsoft 365 Defender
description: Algo foi perdido ou detectado incorretamente pelo AIR no Microsoft 365 Defender? Saiba como enviar falsos positivos ou falsos negativos à Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930349"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="6cc25-105">Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="6cc25-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6cc25-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6cc25-106">**Applies to:**</span></span>
- <span data-ttu-id="6cc25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cc25-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="6cc25-108">Os [recursos automatizados de investigação e resposta](mtp-autoir.md) no Microsoft 365 Defender falharam ou detectaram algo incorretamente?</span><span class="sxs-lookup"><span data-stu-id="6cc25-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="6cc25-109">Há etapas que você pode seguir para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="6cc25-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="6cc25-110">Você pode:</span><span class="sxs-lookup"><span data-stu-id="6cc25-110">You can:</span></span>

- <span data-ttu-id="6cc25-111">[Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="6cc25-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="6cc25-112">[Ajuste seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="6cc25-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="6cc25-113">[Desfazer ações de correção que foram realizadas em dispositivos.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="6cc25-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="6cc25-114">Use este artigo como guia.</span><span class="sxs-lookup"><span data-stu-id="6cc25-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="6cc25-115">Relatar um falso positivo/negativo à Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="6cc25-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="6cc25-116">Item perdido ou detectado incorretamente</span><span class="sxs-lookup"><span data-stu-id="6cc25-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="6cc25-117">Serviço</span><span class="sxs-lookup"><span data-stu-id="6cc25-117">Service</span></span>  |<span data-ttu-id="6cc25-118">O que fazer</span><span class="sxs-lookup"><span data-stu-id="6cc25-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6cc25-119">- Mensagem de email</span><span class="sxs-lookup"><span data-stu-id="6cc25-119">- Email message</span></span> <br/><span data-ttu-id="6cc25-120">- Anexo de email</span><span class="sxs-lookup"><span data-stu-id="6cc25-120">- Email attachment</span></span> <br/><span data-ttu-id="6cc25-121">- URL em uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="6cc25-121">- URL in an email message</span></span><br/><span data-ttu-id="6cc25-122">- URL em um arquivo do Office</span><span class="sxs-lookup"><span data-stu-id="6cc25-122">- URL in an Office file</span></span>      |[<span data-ttu-id="6cc25-123">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6cc25-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="6cc25-124">Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para verificação</span><span class="sxs-lookup"><span data-stu-id="6cc25-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="6cc25-125">Arquivo ou aplicativo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="6cc25-125">File or app on a device</span></span>    |[<span data-ttu-id="6cc25-126">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6cc25-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="6cc25-127">Enviar um arquivo à Microsoft para análise de malware</span><span class="sxs-lookup"><span data-stu-id="6cc25-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="6cc25-128">Ajustar um alerta para evitar que falsos positivos se repitam</span><span class="sxs-lookup"><span data-stu-id="6cc25-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="6cc25-129">Cenário</span><span class="sxs-lookup"><span data-stu-id="6cc25-129">Scenario</span></span> |<span data-ttu-id="6cc25-130">Serviço</span><span class="sxs-lookup"><span data-stu-id="6cc25-130">Service</span></span> |<span data-ttu-id="6cc25-131">O que fazer</span><span class="sxs-lookup"><span data-stu-id="6cc25-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="6cc25-132">- Um alerta é acionado por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="6cc25-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="6cc25-133">- Um alerta é impreciso</span><span class="sxs-lookup"><span data-stu-id="6cc25-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="6cc25-134">Segurança no Aplicativo da Nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6cc25-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="6cc25-135">ou</span><span class="sxs-lookup"><span data-stu-id="6cc25-135">or</span></span> <br/>[<span data-ttu-id="6cc25-136">Detecção avançada de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="6cc25-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="6cc25-137">Gerenciar alertas no portal do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6cc25-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="6cc25-138">Um arquivo, endereço IP, URL ou domínio é tratado como malware em um dispositivo, mesmo que seja seguro</span><span class="sxs-lookup"><span data-stu-id="6cc25-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="6cc25-139">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6cc25-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="6cc25-140">Criar um indicador personalizado com uma ação "Permitir"</span><span class="sxs-lookup"><span data-stu-id="6cc25-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="6cc25-141">Desfazer uma ação de correção que foi realizada em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="6cc25-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="6cc25-142">Se uma ação de correção tiver sido tomada em um dispositivo (como um dispositivo Windows 10) e o item não for realmente uma ameaça, sua equipe de operações de segurança poderá desfazer a ação de correção na Central de [ações.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="6cc25-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6cc25-143">Certifique-se de que você [tenha as permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de tentar executar a tarefa a seguir.</span><span class="sxs-lookup"><span data-stu-id="6cc25-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="6cc25-144">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="6cc25-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="6cc25-145">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="6cc25-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="6cc25-146">Na guia **Histórico,** selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="6cc25-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="6cc25-147">Isso abre um flyout.</span><span class="sxs-lookup"><span data-stu-id="6cc25-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="6cc25-148">Use filtros para restringir a lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="6cc25-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="6cc25-149">No flyout do item selecionado, selecione **a página Abrir investigação.**</span><span class="sxs-lookup"><span data-stu-id="6cc25-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="6cc25-150">Na exibição de detalhes da investigação, selecione a **guia** Ações.</span><span class="sxs-lookup"><span data-stu-id="6cc25-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="6cc25-151">Selecione um item que tenha o status **concluído** e procure um link, como **Aprovado,** na coluna **Decisões.**</span><span class="sxs-lookup"><span data-stu-id="6cc25-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="6cc25-152">Isso abre um flyout com mais detalhes sobre a ação.</span><span class="sxs-lookup"><span data-stu-id="6cc25-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="6cc25-153">Para desfazer a ação, selecione **Excluir correção.**</span><span class="sxs-lookup"><span data-stu-id="6cc25-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cc25-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="6cc25-154">See also</span></span>

- [<span data-ttu-id="6cc25-155">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="6cc25-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="6cc25-156">Busca proativa por ameaças com busca avançada no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cc25-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
