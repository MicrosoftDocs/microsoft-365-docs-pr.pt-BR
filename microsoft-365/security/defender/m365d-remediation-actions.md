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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 80546d44bc1ba222c736b397a272f9f1f1a01d4a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269463"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="002c2-104">Ações de correção no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="002c2-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="002c2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="002c2-105">**Applies to:**</span></span>
- <span data-ttu-id="002c2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="002c2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="002c2-107">Durante e após uma investigação automatizada no Microsoft 365 Defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="002c2-107">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="002c2-108">Alguns tipos de ações de correção são tomadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="002c2-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="002c2-109">Outras ações de correção são tomadas no conteúdo de email.</span><span class="sxs-lookup"><span data-stu-id="002c2-109">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="002c2-110">Investigações automatizadas concluídas após ações de correção são tomadas, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="002c2-110">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="002c2-111">Se as ações de correção são tomadas automaticamente ou somente após aprovação depende de determinadas configurações, como os níveis de automação.</span><span class="sxs-lookup"><span data-stu-id="002c2-111">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="002c2-112">Para saber mais, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="002c2-112">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="002c2-113">Configurar seus recursos automatizados de investigação e resposta no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="002c2-113">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="002c2-114">Como as ameaças são remediadas em dispositivos</span><span class="sxs-lookup"><span data-stu-id="002c2-114">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="002c2-115">Ações de ameaças e correção no email & conteúdo de colaboração</span><span class="sxs-lookup"><span data-stu-id="002c2-115">Threats and remediation actions on email & collaboration content</span></span>](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="002c2-116">A tabela a seguir resume as ações de correção atualmente suportadas no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="002c2-116">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender.</span></span> 

|<span data-ttu-id="002c2-117">Ações de correção de dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="002c2-117">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="002c2-118">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="002c2-118">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="002c2-119">- Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="002c2-119">- Collect investigation package</span></span> <br/><span data-ttu-id="002c2-120">- Isolar dispositivo (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="002c2-120">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="002c2-121">- Máquina de offboard</span><span class="sxs-lookup"><span data-stu-id="002c2-121">- Offboard machine</span></span> <br/><span data-ttu-id="002c2-122">- Execução de código de versão</span><span class="sxs-lookup"><span data-stu-id="002c2-122">- Release code execution</span></span> <br/><span data-ttu-id="002c2-123">- Liberação da quarentena</span><span class="sxs-lookup"><span data-stu-id="002c2-123">- Release from quarantine</span></span> <br/><span data-ttu-id="002c2-124">- Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="002c2-124">- Request sample</span></span> <br/><span data-ttu-id="002c2-125">- Restringir a execução de código (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="002c2-125">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="002c2-126">- Executar a verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="002c2-126">- Run antivirus scan</span></span> <br/><span data-ttu-id="002c2-127">- Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="002c2-127">- Stop and quarantine</span></span>      |<span data-ttu-id="002c2-128">- Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="002c2-128">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="002c2-129">- Excluir mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="002c2-129">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="002c2-130">- Email de quarentena</span><span class="sxs-lookup"><span data-stu-id="002c2-130">- Quarantine email</span></span><br/><span data-ttu-id="002c2-131">- Colocar em quarentena um anexo de email</span><span class="sxs-lookup"><span data-stu-id="002c2-131">- Quarantine an email attachment</span></span><br/><span data-ttu-id="002c2-132">- Desativar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="002c2-132">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="002c2-133">As ações de correção, sejam aprovações pendentes ou já concluídas, podem ser exibidas no [Centro de Ações](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="002c2-133">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="002c2-134">Ações de correção que seguem investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="002c2-134">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="002c2-135">Quando uma investigação automatizada é concluída, um veredito é atingido para cada prova envolvida.</span><span class="sxs-lookup"><span data-stu-id="002c2-135">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="002c2-136">Dependendo do veredito, as ações de correção são identificadas.</span><span class="sxs-lookup"><span data-stu-id="002c2-136">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="002c2-137">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="002c2-137">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="002c2-138">Tudo depende de como [a investigação e a resposta automatizadas são configuradas.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="002c2-138">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="002c2-139">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="002c2-139">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="002c2-140">Verdito</span><span class="sxs-lookup"><span data-stu-id="002c2-140">Verdict</span></span>    | <span data-ttu-id="002c2-141">Entidades afetadas</span><span class="sxs-lookup"><span data-stu-id="002c2-141">Affected entities</span></span>    | <span data-ttu-id="002c2-142">Resultados</span><span class="sxs-lookup"><span data-stu-id="002c2-142">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="002c2-143">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="002c2-143">Malicious</span></span>    | <span data-ttu-id="002c2-144">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="002c2-144">Devices (endpoints)</span></span>    | <span data-ttu-id="002c2-145">As ações de correção são tomadas [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) automaticamente (supondo que os grupos de dispositivos da sua organização sejam definidos como **Full - correção de ameaças automaticamente**)</span><span class="sxs-lookup"><span data-stu-id="002c2-145">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="002c2-146">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="002c2-146">Malicious</span></span>    | <span data-ttu-id="002c2-147">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="002c2-147">Email content (URLs or attachments)</span></span> | <span data-ttu-id="002c2-148">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="002c2-148">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="002c2-149">Suspeito</span><span class="sxs-lookup"><span data-stu-id="002c2-149">Suspicious</span></span>    | <span data-ttu-id="002c2-150">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="002c2-150">Devices or email content</span></span> | <span data-ttu-id="002c2-151">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="002c2-151">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="002c2-152">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="002c2-152">No threats found</span></span>    | <span data-ttu-id="002c2-153">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="002c2-153">Devices or email content</span></span>    | <span data-ttu-id="002c2-154">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="002c2-154">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="002c2-155">Ações de correção realizadas manualmente</span><span class="sxs-lookup"><span data-stu-id="002c2-155">Remediation actions that are taken manually</span></span>

<span data-ttu-id="002c2-156">Além das ações de correção que seguem investigações automatizadas, sua equipe de operações de segurança pode realizar determinadas ações de correção manualmente.</span><span class="sxs-lookup"><span data-stu-id="002c2-156">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="002c2-157">Elas incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="002c2-157">These include the following:</span></span>

- <span data-ttu-id="002c2-158">Ação manual do dispositivo, como isolamento de dispositivo ou quarentena de arquivo</span><span class="sxs-lookup"><span data-stu-id="002c2-158">Manual device action, such as device isolation or file quarantine</span></span>
- <span data-ttu-id="002c2-159">Ação de email manual, como a exclusão suave de mensagens de email</span><span class="sxs-lookup"><span data-stu-id="002c2-159">Manual email action, such as soft-deleting email messages</span></span> 
- <span data-ttu-id="002c2-160">[Ação de busca](../defender-endpoint/advanced-hunting-overview.md) avançada em dispositivos ou email</span><span class="sxs-lookup"><span data-stu-id="002c2-160">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email</span></span>
- <span data-ttu-id="002c2-161">[Ação](../office-365-security/threat-explorer.md) do Explorer no conteúdo de email, como a movimentação de emails para lixo eletrônico, a exclusão de emails ou a exclusão direta de emails</span><span class="sxs-lookup"><span data-stu-id="002c2-161">[Explorer](../office-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email</span></span>
- <span data-ttu-id="002c2-162">Ação [de resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como excluir um arquivo, interromper um processo e remover uma tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="002c2-162">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task</span></span>
- <span data-ttu-id="002c2-163">Ação de resposta ao vivo com [o Microsoft Defender para APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)de ponto de extremidade , como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo</span><span class="sxs-lookup"><span data-stu-id="002c2-163">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file</span></span>

## <a name="next-steps"></a><span data-ttu-id="002c2-164">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="002c2-164">Next steps</span></span>

- [<span data-ttu-id="002c2-165">Visite a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="002c2-165">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="002c2-166">Exibir e gerenciar ações de correção</span><span class="sxs-lookup"><span data-stu-id="002c2-166">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="002c2-167">Resolver falsos positivos ou falsos negativos</span><span class="sxs-lookup"><span data-stu-id="002c2-167">Address false positives or false negatives</span></span>](m365d-autoir-report-false-positives-negatives.md)
