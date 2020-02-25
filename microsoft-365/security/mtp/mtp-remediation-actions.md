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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266047"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="b33d2-104">Ações de correção após as investigações automatizadas no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b33d2-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="b33d2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b33d2-105">**Applies to:**</span></span>
- <span data-ttu-id="b33d2-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b33d2-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="b33d2-107">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="b33d2-107">Remediation actions</span></span>

<span data-ttu-id="b33d2-108">Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="b33d2-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="b33d2-109">Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b33d2-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="b33d2-110">Outras ações de correção são executadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="b33d2-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="b33d2-111">Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="b33d2-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="b33d2-112">A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b33d2-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="b33d2-113">Ações de correção de dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="b33d2-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="b33d2-114">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="b33d2-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="b33d2-115">Arquivo de quarentena</span><span class="sxs-lookup"><span data-stu-id="b33d2-115">Quarantine file</span></span><br/><span data-ttu-id="b33d2-116">Remover chave do registro</span><span class="sxs-lookup"><span data-stu-id="b33d2-116">Remove registry key</span></span><br/><span data-ttu-id="b33d2-117">Finalizar processo</span><span class="sxs-lookup"><span data-stu-id="b33d2-117">Kill process</span></span> <br/><span data-ttu-id="b33d2-118">Parar serviço</span><span class="sxs-lookup"><span data-stu-id="b33d2-118">Stop service</span></span> <br/><span data-ttu-id="b33d2-119">Desabilitar o driver</span><span class="sxs-lookup"><span data-stu-id="b33d2-119">Disable driver</span></span> <br/><span data-ttu-id="b33d2-120">Remover tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="b33d2-120">Remove scheduled task</span></span>      |<span data-ttu-id="b33d2-121">Exclusão reversível de mensagens de emails ou clusters</span><span class="sxs-lookup"><span data-stu-id="b33d2-121">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="b33d2-122">Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="b33d2-122">Block URL (time-of-click)</span></span><br/><span data-ttu-id="b33d2-123">Desativar o encaminhamento de emails externo</span><span class="sxs-lookup"><span data-stu-id="b33d2-123">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="b33d2-124">Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="b33d2-124">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="verdicts-and-outcomes-following-automated-investigations"></a><span data-ttu-id="b33d2-125">Verdicts e resultados após investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="b33d2-125">Verdicts and outcomes following automated investigations</span></span>

<span data-ttu-id="b33d2-126">Quando uma investigação automatizada for concluída, um veredito será feito para cada evidência envolvida, e as ações de correção serão identificadas.</span><span class="sxs-lookup"><span data-stu-id="b33d2-126">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="b33d2-127">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="b33d2-127">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="b33d2-128">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="b33d2-128">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="b33d2-129">Verdito</span><span class="sxs-lookup"><span data-stu-id="b33d2-129">Verdict</span></span>    |<span data-ttu-id="b33d2-130">Área</span><span class="sxs-lookup"><span data-stu-id="b33d2-130">Area</span></span>   |<span data-ttu-id="b33d2-131">Resultados</span><span class="sxs-lookup"><span data-stu-id="b33d2-131">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="b33d2-132">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="b33d2-132">Malicious</span></span>  |<span data-ttu-id="b33d2-133">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="b33d2-133">Devices (endpoints)</span></span>    |<span data-ttu-id="b33d2-134">As ações de correção são tomadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="b33d2-134">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="b33d2-135">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="b33d2-135">Malicious</span></span>  |<span data-ttu-id="b33d2-136">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="b33d2-136">Email content (URLs or attachments)</span></span> | <span data-ttu-id="b33d2-137">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="b33d2-137">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="b33d2-138">Suspeito</span><span class="sxs-lookup"><span data-stu-id="b33d2-138">Suspicious</span></span> |<span data-ttu-id="b33d2-139">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="b33d2-139">Devices or email content</span></span> |<span data-ttu-id="b33d2-140">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="b33d2-140">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="b33d2-141">Limpar</span><span class="sxs-lookup"><span data-stu-id="b33d2-141">Clean</span></span>  |<span data-ttu-id="b33d2-142">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="b33d2-142">Devices or email content</span></span>   |<span data-ttu-id="b33d2-143">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="b33d2-143">No remediation actions are needed</span></span>|

[<span data-ttu-id="b33d2-144">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="b33d2-144">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="b33d2-145">Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar!</span><span class="sxs-lookup"><span data-stu-id="b33d2-145">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="b33d2-146">[Relatar falsos positivos/negativos](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="b33d2-146">[Report false positives/negatives](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b33d2-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b33d2-147">Next steps</span></span>

- [<span data-ttu-id="b33d2-148">Aprovar ou rejeitar ações</span><span class="sxs-lookup"><span data-stu-id="b33d2-148">Approve or reject actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [<span data-ttu-id="b33d2-149">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="b33d2-149">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
