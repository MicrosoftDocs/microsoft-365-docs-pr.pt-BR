---
title: Detalhes e resultados de uma investigação automatizada
description: Durante e após uma investigação automática, você pode exibir os resultados e as principais descobertas
keywords: automatização, investigação, resultados, análise, detalhes, correção, autoair
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
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 62d33c57606aad81607164b1f068c6f6d91063c2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962294"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="61503-104">Detalhes e resultados de uma investigação automatizada</span><span class="sxs-lookup"><span data-stu-id="61503-104">Details and results of an automated investigation</span></span>

<span data-ttu-id="61503-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="61503-105">**Applies to:**</span></span>
- <span data-ttu-id="61503-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="61503-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="61503-107">Quando uma investigação automatizada ocorrer na Proteção Contra Ameaças da Microsoft, os detalhes dessa investigação estarão disponíveis durante e após o processo de investigação automática.</span><span class="sxs-lookup"><span data-stu-id="61503-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="61503-108">Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá exibir esses detalhes na exibição de detalhes da investigação.</span><span class="sxs-lookup"><span data-stu-id="61503-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="61503-109">A exibição de detalhes da investigação fornece o status atualizado e a capacidade de aprovar as ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="61503-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="61503-111">Abrir a exibição de detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="61503-111">Open the investigation details view</span></span>

<span data-ttu-id="61503-112">Você pode abrir a exibição de detalhes da investigação usando um destes métodos:</span><span class="sxs-lookup"><span data-stu-id="61503-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="61503-113">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="61503-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="61503-114">Selecionar uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="61503-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="61503-115">Selecionar um item na central de Ações</span><span class="sxs-lookup"><span data-stu-id="61503-115">Select an item in the Action center</span></span>

<span data-ttu-id="61503-116">Use a central de ações para exibir as ações que estão pendentes (na guia **Pendente**) ou que já foram aprovadas (na guia **Histórico**).</span><span class="sxs-lookup"><span data-stu-id="61503-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="61503-117">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="61503-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="61503-118">No painel de navegação, escolha **Central de ações**.</span><span class="sxs-lookup"><span data-stu-id="61503-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="61503-119">Na guia **Pendente**ou **Histórico**, selecione um item.</span><span class="sxs-lookup"><span data-stu-id="61503-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="61503-120">Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá aprovar (ou rejeitar) ações pendentes.</span><span class="sxs-lookup"><span data-stu-id="61503-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="61503-121">Abrir uma investigação em uma página de detalhes do incidente</span><span class="sxs-lookup"><span data-stu-id="61503-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="61503-122">Use uma página de detalhes do incidente para exibir informações detalhadas sobre um incidente, incluindo os alertas que foram disparados com informações sobre os dispositivos afetados, contas de usuários ou caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="61503-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="61503-123">Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="61503-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="61503-124">No painel de navegação, escolha **Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="61503-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="61503-125">Selecione um item na lista para abrir a exibição de detalhes do incidente.</span><span class="sxs-lookup"><span data-stu-id="61503-125">Select an item in the list to open the incident details view.</span></span><br/>![Detalhes do incidente](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="61503-127">Na guia **Investigações**, selecione uma investigação na lista.</span><span class="sxs-lookup"><span data-stu-id="61503-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="61503-128">Detalhes da investigação</span><span class="sxs-lookup"><span data-stu-id="61503-128">Investigation details</span></span>

<span data-ttu-id="61503-129">Use o modo de exibição de detalhes da investigação para ver as atividades antigas, atuais e pendentes referentes a uma investigação.</span><span class="sxs-lookup"><span data-stu-id="61503-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="61503-130">A exibição de detalhes de investigação se parece com a seguinte imagem:</span><span class="sxs-lookup"><span data-stu-id="61503-130">The investigation details view resembles the following image:</span></span>

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

<span data-ttu-id="61503-132">Na exibição de detalhes da investigação, você pode ver as informações nas guias **Gráfico de Investigação**, **Alertas**, **Dispositivos**, **Identidades**, **Principais descobertas**, **Entidades**,**Log** e **Ações pendentes**, descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="61503-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="61503-133">Guia</span><span class="sxs-lookup"><span data-stu-id="61503-133">Tab</span></span>    |<span data-ttu-id="61503-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="61503-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="61503-135">Gráficos de investigação</span><span class="sxs-lookup"><span data-stu-id="61503-135">Investigation graph</span></span>    |<span data-ttu-id="61503-136">Oferece uma representação visual da investigação.</span><span class="sxs-lookup"><span data-stu-id="61503-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="61503-137">Descreve entidades e lista as ameaças encontradas, juntamente com os alertas, e se as ações estão aguardando aprovação.</span><span class="sxs-lookup"><span data-stu-id="61503-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="61503-138">Você pode clicar em um item no gráfico para exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="61503-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="61503-139">Por exemplo, clicar no ícone **Ameaças encontradas** o levará para a guia **Principais conclusões**.</span><span class="sxs-lookup"><span data-stu-id="61503-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="61503-140">Alertas</span><span class="sxs-lookup"><span data-stu-id="61503-140">Alerts</span></span> |<span data-ttu-id="61503-141">Lista os alertas associados à investigação.</span><span class="sxs-lookup"><span data-stu-id="61503-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="61503-142">Os alertas podem ser de recursos de proteção contra ameaças no computador de um usuário, em aplicativos do Office, Cloud app Security e outros recursos de Proteção Contra Ameaças da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61503-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="61503-143">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="61503-143">Devices</span></span>|<span data-ttu-id="61503-144">Lista os computadores incluídos na investigação, juntamente com o nível de correção.</span><span class="sxs-lookup"><span data-stu-id="61503-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="61503-145">Conclusões principais</span><span class="sxs-lookup"><span data-stu-id="61503-145">Key findings</span></span>   |<span data-ttu-id="61503-146">Lista os resultados da investigação, juntamente com o status e as ações realizadas ou pendentes.</span><span class="sxs-lookup"><span data-stu-id="61503-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="61503-147">Você pode aprovar as ações pendentes para dispositivos e identidades na guia.</span><span class="sxs-lookup"><span data-stu-id="61503-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="61503-148">Entidades</span><span class="sxs-lookup"><span data-stu-id="61503-148">Entities</span></span>   |<span data-ttu-id="61503-149">Lista as atividades do usuário, os arquivos, os processos, os serviços, os endereços IP, drivers, e os métodos de persistência associados à investigação, juntamente com o status e as ações realizadas.</span><span class="sxs-lookup"><span data-stu-id="61503-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="61503-150">Log</span><span class="sxs-lookup"><span data-stu-id="61503-150">Log</span></span>    |<span data-ttu-id="61503-151">Fornece uma exibição detalhada de todas as etapas realizadas durante a investigação, juntamente com o status.</span><span class="sxs-lookup"><span data-stu-id="61503-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="61503-152">Ações pendentes</span><span class="sxs-lookup"><span data-stu-id="61503-152">Pending actions</span></span>    |<span data-ttu-id="61503-153">Lista os itens que exigem aprovação para prosseguir.</span><span class="sxs-lookup"><span data-stu-id="61503-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="61503-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="61503-154">Next steps</span></span>

- [<span data-ttu-id="61503-155">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="61503-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

