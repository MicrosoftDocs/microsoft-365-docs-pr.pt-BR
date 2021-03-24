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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fa73756aa9f350793c00a7e4a960c215627b712f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053512"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a><span data-ttu-id="0ea6b-104">Ações de correção no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ea6b-104">Remediation actions in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0ea6b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0ea6b-105">**Applies to:**</span></span>
- <span data-ttu-id="0ea6b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ea6b-106">Microsoft 365 Defender</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="0ea6b-107">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="0ea6b-107">Remediation actions</span></span>

<span data-ttu-id="0ea6b-108">Durante e após uma investigação automatizada no Microsoft 365 Defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-108">During and after an automated investigation in Microsoft 365 Defender, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="0ea6b-109">Alguns tipos de ações de correção são tomadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="0ea6b-110">Outras ações de correção são tomadas no conteúdo de email.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="0ea6b-111">Investigações automatizadas concluídas após ações de correção são tomadas, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ea6b-112">Se as ações de correção são tomadas automaticamente ou somente após aprovação depende de determinadas configurações, como os níveis de automação.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-112">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as how automation levels.</span></span> <span data-ttu-id="0ea6b-113">Para saber mais, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="0ea6b-113">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="0ea6b-114">Configurar seus recursos automatizados de investigação e resposta no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ea6b-114">Configure your automated investigation and response capabilities in Microsoft 365 Defender</span></span>](m365d-configure-auto-investigation-response.md)
> - [<span data-ttu-id="0ea6b-115">Como as ameaças são remediadas em dispositivos</span><span class="sxs-lookup"><span data-stu-id="0ea6b-115">How threats are remediated on devices</span></span>](../defender-endpoint/automated-investigations.md)
> - [<span data-ttu-id="0ea6b-116">Ações de ameaças e correção no email & conteúdo de colaboração</span><span class="sxs-lookup"><span data-stu-id="0ea6b-116">Threats and remediation actions on email & collaboration content</span></span>](../defender-365-security/air-remediation-actions.md#threats-and-remediation-actions)

<span data-ttu-id="0ea6b-117">A tabela a seguir resume as ações de correção com suporte no Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="0ea6b-117">The following table summarizes remediation actions that are currently supported in Microsoft 365 Defender:</span></span> 

|<span data-ttu-id="0ea6b-118">Ações de correção de dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-118">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="0ea6b-119">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="0ea6b-119">Email remediation actions</span></span>  |
|:---------|:---------|
|<span data-ttu-id="0ea6b-120">- Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="0ea6b-120">- Collect investigation package</span></span> <br/><span data-ttu-id="0ea6b-121">- Isolar dispositivo (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-121">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="0ea6b-122">- Máquina de offboard</span><span class="sxs-lookup"><span data-stu-id="0ea6b-122">- Offboard machine</span></span> <br/><span data-ttu-id="0ea6b-123">- Execução de código de versão</span><span class="sxs-lookup"><span data-stu-id="0ea6b-123">- Release code execution</span></span> <br/><span data-ttu-id="0ea6b-124">- Liberação da quarentena</span><span class="sxs-lookup"><span data-stu-id="0ea6b-124">- Release from quarantine</span></span> <br/><span data-ttu-id="0ea6b-125">- Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="0ea6b-125">- Request sample</span></span> <br/><span data-ttu-id="0ea6b-126">- Restringir a execução de código (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-126">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="0ea6b-127">- Executar a verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="0ea6b-127">- Run antivirus scan</span></span> <br/><span data-ttu-id="0ea6b-128">- Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="0ea6b-128">- Stop and quarantine</span></span>      |<span data-ttu-id="0ea6b-129">- Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-129">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="0ea6b-130">- Excluir mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="0ea6b-130">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="0ea6b-131">- Email de quarentena</span><span class="sxs-lookup"><span data-stu-id="0ea6b-131">- Quarantine email</span></span><br/><span data-ttu-id="0ea6b-132">- Colocar em quarentena um anexo de email</span><span class="sxs-lookup"><span data-stu-id="0ea6b-132">- Quarantine an email attachment</span></span><br/><span data-ttu-id="0ea6b-133">- Desativar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="0ea6b-133">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="0ea6b-134">As ações de correção, sejam aprovações pendentes ou já concluídas, podem ser exibidas no [Centro de Ações](m365d-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="0ea6b-134">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](m365d-action-center.md).</span></span>

## <a name="remediation-actions-that-follow-automated-investigations"></a><span data-ttu-id="0ea6b-135">Ações de correção que seguem investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="0ea6b-135">Remediation actions that follow automated investigations</span></span>

<span data-ttu-id="0ea6b-136">Quando uma investigação automatizada é concluída, um veredito é atingido para cada prova envolvida.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-136">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="0ea6b-137">Dependendo do veredito, as ações de correção são identificadas.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-137">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="0ea6b-138">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-138">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="0ea6b-139">Tudo depende de como [a investigação e a resposta automatizadas são configuradas.](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-139">It all depends on how [automated investigation and response is configured](m365d-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="0ea6b-140">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="0ea6b-140">The following table lists possible verdicts and outcomes:</span></span>

| <span data-ttu-id="0ea6b-141">Verdito</span><span class="sxs-lookup"><span data-stu-id="0ea6b-141">Verdict</span></span>    | <span data-ttu-id="0ea6b-142">Área</span><span class="sxs-lookup"><span data-stu-id="0ea6b-142">Area</span></span>    | <span data-ttu-id="0ea6b-143">Resultados</span><span class="sxs-lookup"><span data-stu-id="0ea6b-143">Outcomes</span></span>|
|------|------|------|
| <span data-ttu-id="0ea6b-144">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="0ea6b-144">Malicious</span></span>    | <span data-ttu-id="0ea6b-145">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-145">Devices (endpoints)</span></span>    | <span data-ttu-id="0ea6b-146">As ações de correção são tomadas [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) automaticamente (supondo que os grupos de dispositivos da sua organização sejam definidos como **Full - correção de ameaças automaticamente**)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-146">Remediation actions are taken automatically (assuming your organization's [device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
| <span data-ttu-id="0ea6b-147">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="0ea6b-147">Malicious</span></span>    | <span data-ttu-id="0ea6b-148">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="0ea6b-148">Email content (URLs or attachments)</span></span> | <span data-ttu-id="0ea6b-149">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="0ea6b-149">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="0ea6b-150">Suspeito</span><span class="sxs-lookup"><span data-stu-id="0ea6b-150">Suspicious</span></span>    | <span data-ttu-id="0ea6b-151">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="0ea6b-151">Devices or email content</span></span> | <span data-ttu-id="0ea6b-152">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="0ea6b-152">Recommended remediation actions are pending approval</span></span>|
| <span data-ttu-id="0ea6b-153">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="0ea6b-153">No threats found</span></span>    | <span data-ttu-id="0ea6b-154">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="0ea6b-154">Devices or email content</span></span>    | <span data-ttu-id="0ea6b-155">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="0ea6b-155">No remediation actions are needed</span></span>|


## <a name="remediation-actions-that-are-taken-manually"></a><span data-ttu-id="0ea6b-156">Ações de correção realizadas manualmente</span><span class="sxs-lookup"><span data-stu-id="0ea6b-156">Remediation actions that are taken manually</span></span>

<span data-ttu-id="0ea6b-157">Além das ações de correção que seguem investigações automatizadas, sua equipe de operações de segurança pode realizar determinadas ações de correção manualmente.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-157">In addition to remediation actions that follow automated investigations, your security operations team can take certain remediation actions manually.</span></span> <span data-ttu-id="0ea6b-158">Elas incluem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="0ea6b-158">These include the following actions:</span></span>

- <span data-ttu-id="0ea6b-159">Ação de dispositivo manual, como isolamento de dispositivo ou quarentena de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-159">Manual device action, such as device isolation or file quarantine.</span></span>
- <span data-ttu-id="0ea6b-160">Ação de email manual, como a exclusão suave de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-160">Manual email action, such as soft-deleting email messages.</span></span> 
- <span data-ttu-id="0ea6b-161">[Ação de busca](../defender-endpoint/advanced-hunting-overview.md) avançada em dispositivos ou emails.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-161">[Advanced hunting](../defender-endpoint/advanced-hunting-overview.md) action on devices or email.</span></span>
- <span data-ttu-id="0ea6b-162">[Ação](../defender-365-security/threat-explorer.md) do Explorer no conteúdo de email, como a movimentação de emails para lixo eletrônico, a exclusão de emails ou a exclusão de emails.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-162">[Explorer](../defender-365-security/threat-explorer.md) action on email content, such as moving email to junk, soft-deleting email, or hard-deleting email.</span></span>
- <span data-ttu-id="0ea6b-163">Ação [de resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) manual, como excluir um arquivo, interromper um processo e remover uma tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-163">Manual [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) action, such as deleting a file, stopping a process, and removing a scheduled task.</span></span>
- <span data-ttu-id="0ea6b-164">Ação de resposta ao vivo com [APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis)do Microsoft Defender para Ponto de Extremidade , como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ea6b-164">Live response action with [Microsoft Defender for Endpoint APIs](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="0ea6b-165">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0ea6b-165">Next steps</span></span>

- [<span data-ttu-id="0ea6b-166">Visite a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="0ea6b-166">Visit the Action center</span></span>](m365d-action-center.md)
- [<span data-ttu-id="0ea6b-167">Exibir e gerenciar ações de correção</span><span class="sxs-lookup"><span data-stu-id="0ea6b-167">View and manage remediation actions</span></span>]( m365d-autoir-actions.md)
- [<span data-ttu-id="0ea6b-168">Manipular falsos positivos/negativos em recursos automatizados de investigação e resposta</span><span class="sxs-lookup"><span data-stu-id="0ea6b-168">Handle false positives/negatives in automated investigation and response capabilities</span></span>](m365d-autoir-report-false-positives-negatives.md)
