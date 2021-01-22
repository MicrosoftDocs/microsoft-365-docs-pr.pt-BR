---
title: Ações de correção no Microsoft 365 Defender
description: Obter uma visão geral das ações de correção que seguem investigações automatizadas no Microsoft 365 Defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932845"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="01f8e-104">Ações de correção no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01f8e-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="01f8e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="01f8e-105">**Applies to:**</span></span>
- <span data-ttu-id="01f8e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01f8e-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="01f8e-107">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="01f8e-107">Remediation actions</span></span>

<span data-ttu-id="01f8e-108">Durante e após uma investigação automatizada no Microsoft 365 Defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="01f8e-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="01f8e-109">Alguns tipos de ações de correção são realizadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="01f8e-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="01f8e-110">Outras ações de correção são realizadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="01f8e-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="01f8e-111">Investigações automatizadas são concluídas após ações de correção, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="01f8e-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01f8e-112">Se as ações de correção são realizadas automaticamente ou somente mediante aprovação depende de determinadas configurações, como a forma como os níveis de automação.</span><span class="sxs-lookup"><span data-stu-id="01f8e-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="01f8e-113">Para saber mais, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="01f8e-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="01f8e-114">Configurar seus recursos automatizados de investigação e resposta no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01f8e-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="01f8e-115">Como as ameaças são remediadas em dispositivos</span><span class="sxs-lookup"><span data-stu-id="01f8e-115">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [<span data-ttu-id="01f8e-116">Ameaças e ações de correção no conteúdo de colaboração & email</span><span class="sxs-lookup"><span data-stu-id="01f8e-116">Threats and remediation actions on email & collaboration content</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

<span data-ttu-id="01f8e-117">A tabela a seguir resume as ações de correção com suporte no momento no Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="01f8e-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="01f8e-118">Ações de correção do dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="01f8e-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="01f8e-119">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="01f8e-119">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="01f8e-120">- Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="01f8e-120">- Collect investigation package</span></span> <br/><span data-ttu-id="01f8e-121">- Isolar dispositivo (esta ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="01f8e-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="01f8e-122">- Computador de redação</span><span class="sxs-lookup"><span data-stu-id="01f8e-122">- Offboard machine</span></span> <br/><span data-ttu-id="01f8e-123">- Liberar execução de código</span><span class="sxs-lookup"><span data-stu-id="01f8e-123">- Release code execution</span></span> <br/><span data-ttu-id="01f8e-124">- Liberar da quarentena</span><span class="sxs-lookup"><span data-stu-id="01f8e-124">- Release from quarantine</span></span> <br/><span data-ttu-id="01f8e-125">- Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="01f8e-125">- Request sample</span></span> <br/><span data-ttu-id="01f8e-126">- Restringir a execução de código (esta ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="01f8e-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="01f8e-127">- Executar a verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="01f8e-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="01f8e-128">- Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="01f8e-128">- Stop and quarantine</span></span>      |<span data-ttu-id="01f8e-129">- Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="01f8e-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="01f8e-130">- Excluir mensagens de email ou clusters de forma suave</span><span class="sxs-lookup"><span data-stu-id="01f8e-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="01f8e-131">- Colocar o email em quarentena</span><span class="sxs-lookup"><span data-stu-id="01f8e-131">- Quarantine email</span></span><br/><span data-ttu-id="01f8e-132">- Colocar em quarentena um anexo de email</span><span class="sxs-lookup"><span data-stu-id="01f8e-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="01f8e-133">- Desativar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="01f8e-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="01f8e-134">Ações de correção, se a aprovação pendente ou já concluída, podem ser exibidas na Central [de Ações.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)</span><span class="sxs-lookup"><span data-stu-id="01f8e-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="01f8e-135">Ações de correção que seguem investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="01f8e-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="01f8e-136">Quando uma investigação automatizada é concluída, um veredito é atingido para cada evidência envolvida.</span><span class="sxs-lookup"><span data-stu-id="01f8e-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="01f8e-137">Dependendo do veredito, as ações de correção são identificadas.</span><span class="sxs-lookup"><span data-stu-id="01f8e-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="01f8e-138">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="01f8e-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="01f8e-139">Tudo depende de como [a investigação e resposta automatizadas são configuradas.](mtp-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="01f8e-139">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="01f8e-140">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="01f8e-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="01f8e-141">Verdito</span><span class="sxs-lookup"><span data-stu-id="01f8e-141">Verdict</span></span>    | <span data-ttu-id="01f8e-142">Área</span><span class="sxs-lookup"><span data-stu-id="01f8e-142">Area</span></span>    | <span data-ttu-id="01f8e-143">Resultados</span><span class="sxs-lookup"><span data-stu-id="01f8e-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="01f8e-144">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="01f8e-144">Malicious</span></span>    | <span data-ttu-id="01f8e-145">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="01f8e-145">Devices (endpoints)</span></span>    | <span data-ttu-id="01f8e-146">As ações de correção são realizadas [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) automaticamente (supondo que os grupos de dispositivos da sua organização estão definidos como **Completo - correção de ameaças automaticamente**)</span><span class="sxs-lookup"><span data-stu-id="01f8e-146">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="01f8e-147">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="01f8e-147">Malicious</span></span>    | <span data-ttu-id="01f8e-148">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="01f8e-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="01f8e-149">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="01f8e-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="01f8e-150">Suspeito</span><span class="sxs-lookup"><span data-stu-id="01f8e-150">Suspicious</span></span>    | <span data-ttu-id="01f8e-151">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="01f8e-151">Devices or email content</span></span> | <span data-ttu-id="01f8e-152">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="01f8e-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="01f8e-153">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="01f8e-153">No threats found</span></span>    | <span data-ttu-id="01f8e-154">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="01f8e-154">Devices or email content</span></span>    | <span data-ttu-id="01f8e-155">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="01f8e-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="01f8e-156">Ações de correção que são realizadas manualmente</span><span class="sxs-lookup"><span data-stu-id="01f8e-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="01f8e-157">Além das ações de correção que seguem investigações automatizadas, sua equipe de operações de segurança pode realizar determinadas ações de correção manualmente.</span><span class="sxs-lookup"><span data-stu-id="01f8e-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="01f8e-158">Elas incluem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="01f8e-158">These include the following actions:</span></span>

- <span data-ttu-id="01f8e-159">Ação manual do dispositivo, como isolamento de dispositivo ou quarentena de arquivo.</span><span class="sxs-lookup"><span data-stu-id="01f8e-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="01f8e-160">Ação manual de email, como exclusão suave de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="01f8e-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="01f8e-161">[Ação de busca](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avançada em dispositivos ou emails.</span><span class="sxs-lookup"><span data-stu-id="01f8e-161">[Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) action on devices or email.</span></span>
- <span data-ttu-id="01f8e-162">[Ação](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) do Explorer no conteúdo de email, como mover emails para lixo eletrônico, excluir emails de forma fácil ou excluir emails ilegíveis.</span><span class="sxs-lookup"><span data-stu-id="01f8e-162">[Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="01f8e-163">Ação [manual de resposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) ao vivo, como excluir um arquivo, interromper um processo e remover uma tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="01f8e-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="01f8e-164">Ação de resposta ao vivo com o Microsoft Defender para [APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)de ponto de extremidade, como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo.</span><span class="sxs-lookup"><span data-stu-id="01f8e-164">Live response action with [Microsoft Defender for Endpoint APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="01f8e-165">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="01f8e-165">Next steps</span></span>

- [<span data-ttu-id="01f8e-166">Visite a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="01f8e-166">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="01f8e-167">Aprovar ou rejeitar ações pendentes</span><span class="sxs-lookup"><span data-stu-id="01f8e-167">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="01f8e-168">Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="01f8e-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
