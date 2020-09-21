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
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 205809bac14cc82e850ea1cbc0349256432bfe68
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962580"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a><span data-ttu-id="e3268-104">Ações de correção após as investigações automatizadas no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e3268-104">Remediation actions following automated investigations in Microsoft Threat Protection</span></span>

<span data-ttu-id="e3268-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e3268-105">**Applies to:**</span></span>
- <span data-ttu-id="e3268-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e3268-106">Microsoft Threat Protection</span></span>


## <a name="remediation-actions"></a><span data-ttu-id="e3268-107">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="e3268-107">Remediation actions</span></span>

<span data-ttu-id="e3268-108">Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos.</span><span class="sxs-lookup"><span data-stu-id="e3268-108">During and after an automated investigation in Microsoft Threat Protection, remediation actions are identified for malicious or suspicious items.</span></span> <span data-ttu-id="e3268-109">Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e3268-109">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="e3268-110">Outras ações de correção são executadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="e3268-110">Other remediation actions are taken on email content.</span></span> <span data-ttu-id="e3268-111">Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.</span><span class="sxs-lookup"><span data-stu-id="e3268-111">Automated investigations complete after remediation actions are taken, approved, or rejected.</span></span>

<span data-ttu-id="e3268-112">A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e3268-112">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="e3268-113">Ações de correção de dispositivo (ponto de extremidade)</span><span class="sxs-lookup"><span data-stu-id="e3268-113">Device (endpoint) remediation actions</span></span>  |<span data-ttu-id="e3268-114">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="e3268-114">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="e3268-115">– Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="e3268-115">- Collect investigation package</span></span> <br/><span data-ttu-id="e3268-116">-Isolar dispositivo (esta ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="e3268-116">- Isolate device (this action can be undone)</span></span><br/><span data-ttu-id="e3268-117">-Máquina externamente</span><span class="sxs-lookup"><span data-stu-id="e3268-117">- Offboard machine</span></span> <br/><span data-ttu-id="e3268-118">-Liberar execução de código</span><span class="sxs-lookup"><span data-stu-id="e3268-118">- Release code execution</span></span> <br/><span data-ttu-id="e3268-119">– Liberar da quarentena</span><span class="sxs-lookup"><span data-stu-id="e3268-119">- Release from quarantine</span></span> <br/><span data-ttu-id="e3268-120">– Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="e3268-120">- Request sample</span></span> <br/><span data-ttu-id="e3268-121">– Restringir a execução de código (essa ação pode ser desfeita)</span><span class="sxs-lookup"><span data-stu-id="e3268-121">- Restrict code execution (this action can be undone)</span></span> <br/><span data-ttu-id="e3268-122">– Executar verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="e3268-122">- Run antivirus scan</span></span> <br/><span data-ttu-id="e3268-123">– Parar e colocar em quarentena</span><span class="sxs-lookup"><span data-stu-id="e3268-123">- Stop and quarantine</span></span>      |<span data-ttu-id="e3268-124">-Bloquear URL (tempo de clique)</span><span class="sxs-lookup"><span data-stu-id="e3268-124">- Block URL (time-of-click)</span></span><br/><span data-ttu-id="e3268-125">– Excluir mensagens de email ou clusters</span><span class="sxs-lookup"><span data-stu-id="e3268-125">- Soft delete email messages or clusters</span></span><br/><span data-ttu-id="e3268-126">– Email de quarentena</span><span class="sxs-lookup"><span data-stu-id="e3268-126">- Quarantine email</span></span><br/><span data-ttu-id="e3268-127">-Colocar um anexo de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="e3268-127">- Quarantine an email attachment</span></span><br/><span data-ttu-id="e3268-128">– Desativar o encaminhamento de email externo</span><span class="sxs-lookup"><span data-stu-id="e3268-128">- Turn off external mail forwarding</span></span>          |

<span data-ttu-id="e3268-129">Ações de correção, se a aprovação pendente ou já concluída, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="e3268-129">Remediation actions, whether pending approval or already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="remediation-actions-follow-automated-investigations"></a><span data-ttu-id="e3268-130">As ações de correção seguem investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="e3268-130">Remediation actions follow automated investigations</span></span>

<span data-ttu-id="e3268-131">Quando uma investigação automatizada é concluída, um veredicto é alcançado para cada evidência envolvida.</span><span class="sxs-lookup"><span data-stu-id="e3268-131">When an automated investigation completes, a verdict is reached for every piece of evidence involved.</span></span> <span data-ttu-id="e3268-132">Dependendo do veredicto, as ações de correção serão identificadas.</span><span class="sxs-lookup"><span data-stu-id="e3268-132">Depending on the verdict, remediation actions are identified.</span></span> <span data-ttu-id="e3268-133">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="e3268-133">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="e3268-134">Tudo isso depende de como a [investigação e a resposta automáticas são configuradas](mtp-configure-auto-investigation-response.md).</span><span class="sxs-lookup"><span data-stu-id="e3268-134">It all depends on how [automated investigation and response is configured](mtp-configure-auto-investigation-response.md).</span></span>

<span data-ttu-id="e3268-135">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="e3268-135">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="e3268-136">Verdito</span><span class="sxs-lookup"><span data-stu-id="e3268-136">Verdict</span></span>    |<span data-ttu-id="e3268-137">Área</span><span class="sxs-lookup"><span data-stu-id="e3268-137">Area</span></span>    |<span data-ttu-id="e3268-138">Resultados</span><span class="sxs-lookup"><span data-stu-id="e3268-138">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="e3268-139">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="e3268-139">Malicious</span></span>    |<span data-ttu-id="e3268-140">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="e3268-140">Devices (endpoints)</span></span>    |<span data-ttu-id="e3268-141">As ações de correção são realizadas automaticamente (supondo que os [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) da sua organização estejam definidos para **corrigir ameaças automaticamente**)</span><span class="sxs-lookup"><span data-stu-id="e3268-141">Remediation actions are taken automatically (assuming your organization's [device groups](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) are set to **Full - remediate threats automatically**)</span></span>|
|<span data-ttu-id="e3268-142">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="e3268-142">Malicious</span></span>    |<span data-ttu-id="e3268-143">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="e3268-143">Email content (URLs or attachments)</span></span> | <span data-ttu-id="e3268-144">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="e3268-144">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="e3268-145">Suspeito</span><span class="sxs-lookup"><span data-stu-id="e3268-145">Suspicious</span></span>    |<span data-ttu-id="e3268-146">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="e3268-146">Devices or email content</span></span> |<span data-ttu-id="e3268-147">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="e3268-147">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="e3268-148">Nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="e3268-148">No threats found</span></span>    |<span data-ttu-id="e3268-149">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="e3268-149">Devices or email content</span></span>    |<span data-ttu-id="e3268-150">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="e3268-150">No remediation actions are needed</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="e3268-151">Se as ações de correção serão realizadas automaticamente ou apenas após a aprovação dependerá de determinadas configurações, como as políticas de grupo de dispositivos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e3268-151">Whether remediation actions are taken automatically or only upon approval depends on certain settings, such as your organization's device group policies.</span></span> <span data-ttu-id="e3268-152">Para saber mais, confira os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="e3268-152">To learn more, see the following articles:</span></span>
> - [<span data-ttu-id="e3268-153">Configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e3268-153">Configure automated investigation and response capabilities in Microsoft Threat Protection</span></span>](mtp-configure-auto-investigation-response.md)
> - [<span data-ttu-id="e3268-154">Como as ameaças são corrigidas nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="e3268-154">How threats are remediated on devices</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a><span data-ttu-id="e3268-155">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e3268-155">Next steps</span></span>

- [<span data-ttu-id="e3268-156">Visite a central de ações</span><span class="sxs-lookup"><span data-stu-id="e3268-156">Visit the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [<span data-ttu-id="e3268-157">Aprovar ou rejeitar ações pendentes</span><span class="sxs-lookup"><span data-stu-id="e3268-157">Approve or reject pending actions</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="e3268-158">Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="e3268-158">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
