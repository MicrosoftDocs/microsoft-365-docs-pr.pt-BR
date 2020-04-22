---
title: Lidar com falsos positivos ou falsos negativos no ar no Microsoft Threat Protection
description: Algo estava perdido ou foi detectado incorretamente pelo ar na proteção contra ameaças da Microsoft? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 4030469b54d9a3a9c6f2eaceae384d39ea7f3e20
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637075"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="3ae7b-105">Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="3ae7b-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="3ae7b-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3ae7b-106">**Applies to:**</span></span>
- <span data-ttu-id="3ae7b-107">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ae7b-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="3ae7b-108">Os [recursos de investigação e resposta automatizados](mtp-autoir.md) na proteção contra ameaças da Microsoft perdem ou detectam incorretamente algo?</span><span class="sxs-lookup"><span data-stu-id="3ae7b-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="3ae7b-109">Há etapas que você pode executar para corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="3ae7b-110">Você pode:</span><span class="sxs-lookup"><span data-stu-id="3ae7b-110">You can:</span></span>

- <span data-ttu-id="3ae7b-111">[Relatar um falso positivo/negativo para a Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="3ae7b-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="3ae7b-112">[Ajustar seus alertas](#adjust-an-alert-to-prevent-false-positives-from-recurring) (se necessário); e</span><span class="sxs-lookup"><span data-stu-id="3ae7b-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="3ae7b-113">[Desfazer ações de correção que foram tomadas nos dispositivos](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="3ae7b-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="3ae7b-114">Use este artigo como uma guia.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="3ae7b-115">Relatar um falso positivo/negativo para a Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="3ae7b-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="3ae7b-116">Item perdido ou detectado incorretamente</span><span class="sxs-lookup"><span data-stu-id="3ae7b-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="3ae7b-117">Serviço</span><span class="sxs-lookup"><span data-stu-id="3ae7b-117">Service</span></span>  |<span data-ttu-id="3ae7b-118">O que fazer</span><span class="sxs-lookup"><span data-stu-id="3ae7b-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="3ae7b-119">-Mensagem de email</span><span class="sxs-lookup"><span data-stu-id="3ae7b-119">- Email message</span></span> <br/><span data-ttu-id="3ae7b-120">-Anexo de email</span><span class="sxs-lookup"><span data-stu-id="3ae7b-120">- Email attachment</span></span> <br/><span data-ttu-id="3ae7b-121">-URL em uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="3ae7b-121">- URL in an email message</span></span><br/><span data-ttu-id="3ae7b-122">-URL em um arquivo do Office</span><span class="sxs-lookup"><span data-stu-id="3ae7b-122">- URL in an Office file</span></span>      |[<span data-ttu-id="3ae7b-123">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="3ae7b-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="3ae7b-124">Enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft para verificação</span><span class="sxs-lookup"><span data-stu-id="3ae7b-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="3ae7b-125">Arquivo ou aplicativo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="3ae7b-125">File or app on a device</span></span>    |[<span data-ttu-id="3ae7b-126">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ae7b-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="3ae7b-127">Enviar um arquivo para a Microsoft para análise de malware</span><span class="sxs-lookup"><span data-stu-id="3ae7b-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="3ae7b-128">Ajustar um alerta para impedir que falsos positivos sejam recorrentes</span><span class="sxs-lookup"><span data-stu-id="3ae7b-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="3ae7b-129">Cenário</span><span class="sxs-lookup"><span data-stu-id="3ae7b-129">Scenario</span></span> |<span data-ttu-id="3ae7b-130">Serviço</span><span class="sxs-lookup"><span data-stu-id="3ae7b-130">Service</span></span> |<span data-ttu-id="3ae7b-131">O que fazer</span><span class="sxs-lookup"><span data-stu-id="3ae7b-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="3ae7b-132">-Um alerta é disparado por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="3ae7b-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="3ae7b-133">-Um alerta é impreciso</span><span class="sxs-lookup"><span data-stu-id="3ae7b-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="3ae7b-134">Segurança no Aplicativo da Nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ae7b-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="3ae7b-135">ou</span><span class="sxs-lookup"><span data-stu-id="3ae7b-135">or</span></span> <br/>[<span data-ttu-id="3ae7b-136">Detecção avançada de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="3ae7b-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="3ae7b-137">Gerenciar alertas no portal do Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="3ae7b-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="3ae7b-138">Um arquivo, um endereço IP, uma URL ou um domínio é tratado como um malware em um dispositivo, mesmo que seja seguro</span><span class="sxs-lookup"><span data-stu-id="3ae7b-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="3ae7b-139">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="3ae7b-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="3ae7b-140">Criar um indicador personalizado com uma ação "permitir"</span><span class="sxs-lookup"><span data-stu-id="3ae7b-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="3ae7b-141">Desfazer uma ação de correção executada em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="3ae7b-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="3ae7b-142">Se uma ação de correção foi realizada em um dispositivo (como um dispositivo Windows 10) e o item não for uma ameaça, a equipe de operações de segurança poderá desfazer a ação de correção na [central de ações](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="3ae7b-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ae7b-143">Verifique se você tem as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks) antes de tentar executar a tarefa a seguir.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="3ae7b-144">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="3ae7b-145">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="3ae7b-146">Na guia **histórico** , selecione uma ação que você deseja desfazer.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="3ae7b-147">Isso abre um submenu.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="3ae7b-148">Use filtros para restringir a lista de resultados.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="3ae7b-149">No submenu do item selecionado, selecione **página de investigação aberta**.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="3ae7b-150">No modo de exibição detalhes da investigação, selecione a guia **ações** .</span><span class="sxs-lookup"><span data-stu-id="3ae7b-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="3ae7b-151">Selecione um item com status **concluído**e procure um link, como **aprovado**, na coluna **decisões** .</span><span class="sxs-lookup"><span data-stu-id="3ae7b-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="3ae7b-152">Isso abre um submenu com mais detalhes sobre a ação.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="3ae7b-153">Para desfazer a ação, selecione **excluir correção**.</span><span class="sxs-lookup"><span data-stu-id="3ae7b-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3ae7b-154">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="3ae7b-154">Related articles</span></span>

- [<span data-ttu-id="3ae7b-155">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="3ae7b-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="3ae7b-156">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="3ae7b-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="3ae7b-157">Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ae7b-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
