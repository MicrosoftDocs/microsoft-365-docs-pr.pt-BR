---
title: Exibir os detalhes e resultados de uma investigação automatizada
description: Durante e após uma investigação automática, você pode exibir os resultados e as principais descobertas
keywords: automatização, investigação, resultados, análise, detalhes, correção, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e70fa5f226b25df72514f75bb20873665d9021f6
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256547"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="eec2c-104">Exibir os detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="eec2c-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="eec2c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="eec2c-105">**Applies to:**</span></span>
- <span data-ttu-id="eec2c-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="eec2c-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="eec2c-107">Quando uma investigação automatizada ocorrer na Proteção Contra Ameaças da Microsoft, os detalhes dessa investigação estarão disponíveis durante e após o processo de investigação automática.</span><span class="sxs-lookup"><span data-stu-id="eec2c-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="eec2c-108">Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá exibir esses detalhes na exibição de detalhes da investigação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="eec2c-109">A exibição de detalhes da investigação fornece o status atualizado e a capacidade de aprovar as ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="eec2c-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detalhes da investigação](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="eec2c-111">Abrir a exibição de detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="eec2c-111">Open the investigation details view</span></span>

<span data-ttu-id="eec2c-112">Você pode abrir a exibição de detalhes da investigação usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="eec2c-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="eec2c-113">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="eec2c-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="eec2c-114">Selecionar uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="eec2c-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="eec2c-115">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="eec2c-115">Select an item in the Action center</span></span>

<span data-ttu-id="eec2c-116">Use a central de ações para exibir as ações que estão pendentes (na guia **Pendente**) ou que já foram aprovadas (na guia **Histórico**).</span><span class="sxs-lookup"><span data-stu-id="eec2c-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="eec2c-117">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="eec2c-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="eec2c-118">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="eec2c-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="eec2c-119">Na guia **Pendente**ou **Histórico**, selecione um item.</span><span class="sxs-lookup"><span data-stu-id="eec2c-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="eec2c-120">Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá aprovar (ou rejeitar) ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="eec2c-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="eec2c-121">Abrir uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="eec2c-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="eec2c-122">Use uma página de detalhes do incidente para exibir informações detalhadas sobre um incidente, incluindo os alertas que foram disparados com informações sobre os dispositivos afetados, contas de usuários ou caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="eec2c-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="eec2c-123">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="eec2c-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="eec2c-124">No painel de navegação, escolha **Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="eec2c-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="eec2c-125">Selecione um item na lista para abrir a exibição de detalhes do incidente.</span><span class="sxs-lookup"><span data-stu-id="eec2c-125">Select an item in the list to open the incident details view.</span></span><br/>![Detalhes do incidente](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="eec2c-127">Na guia **Investigações**, selecione uma investigação na lista.</span><span class="sxs-lookup"><span data-stu-id="eec2c-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="eec2c-128">Detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="eec2c-128">Investigation details</span></span>

<span data-ttu-id="eec2c-129">Use o modo de exibição de detalhes da investigação para ver as atividades antigas, atuais e pendentes referentes a uma investigação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="eec2c-130">A exibição de detalhes de investigação se parece com a seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="eec2c-130">The investigation details view resembles the following image:</span></span>

![Detalhes da investigação](../images/mtp-air-investdetails.png)

<span data-ttu-id="eec2c-132">Na exibição de detalhes da investigação, você pode ver as informações nas guias **Gráfico de Investigação**, **Alertas**, **Dispositivos**, **Identidades**, **Principais descobertas**, **Entidades**,**Log** e **Ações pendentes**, descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="eec2c-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="eec2c-133">Guia</span><span class="sxs-lookup"><span data-stu-id="eec2c-133">Tab</span></span>    |<span data-ttu-id="eec2c-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="eec2c-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="eec2c-135">Gráficos de investigação</span><span class="sxs-lookup"><span data-stu-id="eec2c-135">Investigation graph</span></span>    |<span data-ttu-id="eec2c-136">Oferece uma representação visual da investigação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="eec2c-137">Descreve entidades e lista as ameaças encontradas, juntamente com os alertas, e se as ações estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="eec2c-138">Você pode clicar em um item no gráfico para exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="eec2c-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="eec2c-139">Por exemplo, clicar no ícone **Ameaças encontradas** o levará para a guia **Principais conclusões**.</span><span class="sxs-lookup"><span data-stu-id="eec2c-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="eec2c-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="eec2c-140">Alerts</span></span> |<span data-ttu-id="eec2c-141">Lista os alertas associados à investigação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="eec2c-142">Os alertas podem ser de recursos de proteção contra ameaças no computador de um usuário, em aplicativos do Office, Cloud app Security e outros recursos de Proteção Contra Ameaças da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eec2c-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="eec2c-143">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="eec2c-143">Devices</span></span>|<span data-ttu-id="eec2c-144">Lista os computadores incluídos na investigação, juntamente com o nível de correção.</span><span class="sxs-lookup"><span data-stu-id="eec2c-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="eec2c-145">Conclusões principais</span><span class="sxs-lookup"><span data-stu-id="eec2c-145">Key findings</span></span>   |<span data-ttu-id="eec2c-146">Lista os resultados da investigação, juntamente com o status e as ações realizadas ou pendentes.</span><span class="sxs-lookup"><span data-stu-id="eec2c-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="eec2c-147">Você pode aprovar as ações pendentes para dispositivos e identidades na guia.</span><span class="sxs-lookup"><span data-stu-id="eec2c-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="eec2c-148">Entidades</span><span class="sxs-lookup"><span data-stu-id="eec2c-148">Entities</span></span>   |<span data-ttu-id="eec2c-149">Lista as atividades do usuário, os arquivos, os processos, os serviços, os endereços IP, drivers, e os métodos de persistência associados à investigação, juntamente com o status e as ações realizadas.</span><span class="sxs-lookup"><span data-stu-id="eec2c-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="eec2c-150">Log</span><span class="sxs-lookup"><span data-stu-id="eec2c-150">Log</span></span>    |<span data-ttu-id="eec2c-151">Fornece uma exibição detalhada de todas as etapas realizadas durante a investigação, juntamente com o status.</span><span class="sxs-lookup"><span data-stu-id="eec2c-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="eec2c-152">Ações pendentes</span><span class="sxs-lookup"><span data-stu-id="eec2c-152">Pending actions</span></span>    |<span data-ttu-id="eec2c-153">Lista os itens que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="eec2c-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="eec2c-154">Ações de correção após a investigação automática</span><span class="sxs-lookup"><span data-stu-id="eec2c-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="eec2c-155">Quando uma investigação automatizada for concluída, um veredito será feito para cada evidência envolvida, e as ações de correção serão identificadas.</span><span class="sxs-lookup"><span data-stu-id="eec2c-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="eec2c-156">Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação.</span><span class="sxs-lookup"><span data-stu-id="eec2c-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="eec2c-157">A tabela a seguir lista os possíveis verditos e resultados:</span><span class="sxs-lookup"><span data-stu-id="eec2c-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="eec2c-158">Verdito</span><span class="sxs-lookup"><span data-stu-id="eec2c-158">Verdict</span></span>    |<span data-ttu-id="eec2c-159">Área</span><span class="sxs-lookup"><span data-stu-id="eec2c-159">Area</span></span>   |<span data-ttu-id="eec2c-160">Resultados</span><span class="sxs-lookup"><span data-stu-id="eec2c-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="eec2c-161">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="eec2c-161">Malicious</span></span>  |<span data-ttu-id="eec2c-162">Dispositivos (pontos de extremidade)</span><span class="sxs-lookup"><span data-stu-id="eec2c-162">Devices (endpoints)</span></span>    |<span data-ttu-id="eec2c-163">As ações de correção são tomadas automaticamente</span><span class="sxs-lookup"><span data-stu-id="eec2c-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="eec2c-164">Mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="eec2c-164">Malicious</span></span>  |<span data-ttu-id="eec2c-165">Conteúdo do email (URLs ou anexos)</span><span class="sxs-lookup"><span data-stu-id="eec2c-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="eec2c-166">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="eec2c-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="eec2c-167">Suspeito</span><span class="sxs-lookup"><span data-stu-id="eec2c-167">Suspicious</span></span> |<span data-ttu-id="eec2c-168">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="eec2c-168">Devices or email content</span></span> |<span data-ttu-id="eec2c-169">As ações de correção recomendadas estão aguardando aprovação</span><span class="sxs-lookup"><span data-stu-id="eec2c-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="eec2c-170">Limpar</span><span class="sxs-lookup"><span data-stu-id="eec2c-170">Clean</span></span>  |<span data-ttu-id="eec2c-171">Conteúdo de dispositivos ou emails</span><span class="sxs-lookup"><span data-stu-id="eec2c-171">Devices or email content</span></span>   |<span data-ttu-id="eec2c-172">Nenhuma ação de correção é necessária</span><span class="sxs-lookup"><span data-stu-id="eec2c-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="eec2c-173">Revisar uma ação pendente na Central de Ações</span><span class="sxs-lookup"><span data-stu-id="eec2c-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="eec2c-174">Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar!</span><span class="sxs-lookup"><span data-stu-id="eec2c-174">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="eec2c-175">Veja [como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados (Air) no Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="eec2c-175">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="eec2c-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eec2c-176">Next steps</span></span>

- [<span data-ttu-id="eec2c-177">Obter uma visão geral das permissões da central de Ações</span><span class="sxs-lookup"><span data-stu-id="eec2c-177">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="eec2c-178">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="eec2c-178">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

