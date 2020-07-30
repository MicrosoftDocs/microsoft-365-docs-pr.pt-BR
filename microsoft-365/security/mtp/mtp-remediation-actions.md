---
title: Ações de correção após as investigações automatizadas no Microsoft Threat Protection
description: Obter uma visão geral das ações de correção que seguem as investigações automatizadas no Microsoft Threat Protection
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502932"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="b7d67-104">Ações de correção após as investigações automatizadas no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b7d67-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="b7d67-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b7d67-105">**Applies to:**</span></span>
- <span data-ttu-id="b7d67-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b7d67-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="b7d67-107">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="b7d67-107">Remediation actions</span></span>

<span data-ttu-id="b7d67-108">Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="b7d67-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="b7d67-109">Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7d67-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="b7d67-110">Outras ações de correção são executadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="b7d67-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="b7d67-111">Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="b7d67-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="b7d67-112">A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b7d67-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="b7d67-113">Ações de correção de dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="b7d67-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="b7d67-114">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="b7d67-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="b7d67-115">– Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="b7d67-115">- Collect investigation package</span></span> <br/><span data-ttu-id="b7d67-116">-Isolar dispositivo (esta ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="b7d67-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="b7d67-117">-Máquina externamente</span><span class="sxs-lookup"><span data-stu-id="b7d67-117">- Offboard machine</span></span> <br/><span data-ttu-id="b7d67-118">-Liberar execução de código</span><span class="sxs-lookup"><span data-stu-id="b7d67-118">- Release code execution</span></span> <br/><span data-ttu-id="b7d67-119">– Liberar da quarentena</span><span class="sxs-lookup"><span data-stu-id="b7d67-119">- Release from quarantine</span></span> <br/><span data-ttu-id="b7d67-120">– Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="b7d67-120">- Request sample</span></span> <br/><span data-ttu-id="b7d67-121">– Restringir a execução de código (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="b7d67-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="b7d67-122">– Executar verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="b7d67-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="b7d67-123">– Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="b7d67-123">- Stop and quarantine</span></span>      |<span data-ttu-id="b7d67-124">-Bloquear URL (tempo de clique)</span><span class="sxs-lookup"><span data-stu-id="b7d67-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="b7d67-125">– Excluir mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="b7d67-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="b7d67-126">– Email de quarentena</span><span class="sxs-lookup"><span data-stu-id="b7d67-126">- Quarantine email</span></span><br/><span data-ttu-id="b7d67-127">-Colocar um anexo de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="b7d67-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="b7d67-128">– Desativar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="b7d67-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="b7d67-129">Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="b7d67-129">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="b7d67-130">As ações de correção seguem investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="b7d67-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="b7d67-131">Quando uma investigação automatizada for concluída, um veredito será feito para cada evidência envolvida, e as ações de correção serão identificadas.</span><span class="sxs-lookup"><span data-stu-id="b7d67-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="b7d67-132">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="b7d67-132">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="b7d67-133">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="b7d67-133">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="b7d67-134">Verdito</span><span class="sxs-lookup"><span data-stu-id="b7d67-134">Verdict</span></span>    |<span data-ttu-id="b7d67-135">Área</span><span class="sxs-lookup"><span data-stu-id="b7d67-135">Area</span></span>    |<span data-ttu-id="b7d67-136">Resultados</span><span class="sxs-lookup"><span data-stu-id="b7d67-136">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="b7d67-137">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="b7d67-137">Malicious</span></span>    |<span data-ttu-id="b7d67-138">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="b7d67-138">Devices (endpoints)</span></span>    |<span data-ttu-id="b7d67-139">As ações de correção são tomadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="b7d67-139">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="b7d67-140">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="b7d67-140">Malicious</span></span>    |<span data-ttu-id="b7d67-141">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="b7d67-141">Email content (URLs or attachments)</span></span> | <span data-ttu-id="b7d67-142">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="b7d67-142">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="b7d67-143">Suspeito</span><span class="sxs-lookup"><span data-stu-id="b7d67-143">Suspicious</span></span>    |<span data-ttu-id="b7d67-144">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="b7d67-144">Devices or email content</span></span> |<span data-ttu-id="b7d67-145">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="b7d67-145">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="b7d67-146">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="b7d67-146">No threats found</span></span>    |<span data-ttu-id="b7d67-147">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="b7d67-147">Devices or email content</span></span>    |<span data-ttu-id="b7d67-148">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="b7d67-148">No remediation actions are needed</span></span>|

[<span data-ttu-id="b7d67-149">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="b7d67-149">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="b7d67-150">Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar!</span><span class="sxs-lookup"><span data-stu-id="b7d67-150">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="b7d67-151">[Relatar falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="b7d67-151">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7d67-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b7d67-152">Next steps</span></span>

- [<span data-ttu-id="b7d67-153">Aprovar ou rejeitar ações</span><span class="sxs-lookup"><span data-stu-id="b7d67-153">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="b7d67-154">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="b7d67-154">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
