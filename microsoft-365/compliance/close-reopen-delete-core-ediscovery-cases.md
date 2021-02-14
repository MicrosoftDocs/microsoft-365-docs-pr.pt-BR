---
title: Fechar, reabrir e excluir ocorrências de Descobertas Principais
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como gerenciar casos principais de Descobertas eDiscovery. Isso inclui fechar uma ocorrência, reabrir uma ocorrência fechada e excluir uma ocorrência.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412790"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="2819c-104">Fechar, reabrir e excluir um caso principal de Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2819c-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="2819c-105">Este artigo descreve como fechar, reabrir e excluir ocorrências de Descobertas Principais no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2819c-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="2819c-106">Fechar uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="2819c-106">Close a case</span></span>

<span data-ttu-id="2819c-107">Quando o caso jurídico ou a investigação com suporte em um caso de Descoberta e Principal for concluído, você poderá fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="2819c-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="2819c-108">Veja o que acontece quando você fecha um caso:</span><span class="sxs-lookup"><span data-stu-id="2819c-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="2819c-109">Se a ocorrência contiver qualquer local de conteúdo em espera de Descoberta eDiscovery, essas regiões serão desligadas.</span><span class="sxs-lookup"><span data-stu-id="2819c-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="2819c-110">Depois que a espera é desligada, um período de carência de 30 dias (chamado de espera de *atraso)* é aplicado a locais de conteúdo que estavam em espera.</span><span class="sxs-lookup"><span data-stu-id="2819c-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="2819c-111">Isso ajuda a evitar que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar e restaurar conteúdo antes que ele possa ser excluído permanentemente após o período de espera de atraso expirar.</span><span class="sxs-lookup"><span data-stu-id="2819c-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="2819c-112">Para obter mais informações, [consulte Removendo locais de conteúdo de um eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="2819c-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="2819c-113">Fechar uma ocorrência só desliga as retém associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="2819c-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="2819c-114">Se outras retenções são colocadas em um local de conteúdo (como uma Retenção de Litígio, uma política de retenção ou uma retenção de um caso de Descoberta eDiscovery Principal diferente), essas retenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="2819c-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="2819c-115">O caso ainda está listado na página Descoberta e Principal no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2819c-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2819c-116">Os detalhes, retidos, pesquisas e membros de um caso fechado são mantidos.</span><span class="sxs-lookup"><span data-stu-id="2819c-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="2819c-117">Você pode editar uma ocorrência depois que ela for fechada.</span><span class="sxs-lookup"><span data-stu-id="2819c-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="2819c-118">Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2819c-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="2819c-119">A principal diferença entre os casos ativos e fechados é que as isenções de Descoberta eDiscovery são desligadas quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="2819c-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="2819c-120">Para fechar um caso:</span><span class="sxs-lookup"><span data-stu-id="2819c-120">To close a case:</span></span>
  
1. <span data-ttu-id="2819c-121">No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2819c-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2819c-122">Clique no nome da ocorrência que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="2819c-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="2819c-123">A **página Gerenciar esse caso** é exibida.</span><span class="sxs-lookup"><span data-stu-id="2819c-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="2819c-124">Em **Gerenciar status da ocorrência,** clique em Fechar **caso.**</span><span class="sxs-lookup"><span data-stu-id="2819c-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="2819c-125">Um aviso é exibido dizendo que as iseções associadas à ocorrência serão desligadas.</span><span class="sxs-lookup"><span data-stu-id="2819c-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="2819c-126">Clique **em Sim** para fechar a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2819c-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="2819c-127">O status na página **Gerenciar este caso** do flyout é alterado de **Ativo** para **Fechamento.**</span><span class="sxs-lookup"><span data-stu-id="2819c-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="2819c-128">Feche a **página Gerenciar este caso.**</span><span class="sxs-lookup"><span data-stu-id="2819c-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="2819c-129">Na página **Descoberta Automática Principal,** clique em Atualizar para atualizar o status do caso fechado. </span><span class="sxs-lookup"><span data-stu-id="2819c-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="2819c-130">Pode levar até 60 minutos para que o processo de fechamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="2819c-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="2819c-131">Quando o processo é concluído, o status da ocorrência é alterado para **Fechado** na página **Descoberta Principal.**</span><span class="sxs-lookup"><span data-stu-id="2819c-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="2819c-132">Clique no nome da ocorrência  novamente para exibir a página gerenciar esse caso do flyout, que contém informações sobre quando o caso foi fechado e quem o fechou.</span><span class="sxs-lookup"><span data-stu-id="2819c-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="2819c-133">Reabrir um caso fechado</span><span class="sxs-lookup"><span data-stu-id="2819c-133">Reopen a closed case</span></span>

<span data-ttu-id="2819c-134">Quando você reabrir um caso, qualquer resuspensão de Descoberta Automática que estava no local quando o caso foi fechado não será automaticamente restabelecimento.</span><span class="sxs-lookup"><span data-stu-id="2819c-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="2819c-135">Depois que o caso for reaberto, você terá que ir para a página **Isões** e ativar as retém anteriores.</span><span class="sxs-lookup"><span data-stu-id="2819c-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="2819c-136">Para ativar uma espera, selecione-a para exibir a página do flyout e, em seguida, de definir a **alternância de Status** para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="2819c-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="2819c-137">No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2819c-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2819c-138">Clique no nome do caso que você deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="2819c-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="2819c-139">A **página Gerenciar esse caso** é exibida.</span><span class="sxs-lookup"><span data-stu-id="2819c-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="2819c-140">Em **Gerenciar status do caso,** clique em **Reabrir caso.**</span><span class="sxs-lookup"><span data-stu-id="2819c-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="2819c-141">Um aviso é exibido dizendo que as resuspensão que estavam associadas à ocorrência quando ele foi fechado não serão ativados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2819c-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="2819c-142">Clique **em Sim** para reabrir o caso.</span><span class="sxs-lookup"><span data-stu-id="2819c-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="2819c-143">O status na página **Gerenciar este caso** do flyout é alterado de **Fechado** para **Ativo.**</span><span class="sxs-lookup"><span data-stu-id="2819c-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="2819c-144">Feche a **página Gerenciar este caso.**</span><span class="sxs-lookup"><span data-stu-id="2819c-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="2819c-145">Na página **Descoberta Automática** Principal,  clique em Atualizar para atualizar o status do caso reaberto.</span><span class="sxs-lookup"><span data-stu-id="2819c-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="2819c-146">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="2819c-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="2819c-147">Quando o processo é concluído, o status da ocorrência é alterado para **Ativo** na página **Descoberta Principal.**</span><span class="sxs-lookup"><span data-stu-id="2819c-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="2819c-148">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="2819c-148">Delete a case</span></span>

<span data-ttu-id="2819c-149">Você também pode excluir ocorrências de Descobertas Principais ativas e fechadas.</span><span class="sxs-lookup"><span data-stu-id="2819c-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="2819c-150">Quando você exclui uma ocorrência, todas as pesquisas e exportações no caso são excluídas, e o caso é removido da lista de ocorrências na página **Descoberta** Principal do Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2819c-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2819c-151">Não é possível reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="2819c-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="2819c-152">Antes de excluir uma ocorrência (se ela está ativa  ou fechada), primeiro você deve excluir todas as retém de Descobertas De eDiscovery associadas à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2819c-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="2819c-153">Isso inclui a exclusão de retém com um status **de Desligado**.</span><span class="sxs-lookup"><span data-stu-id="2819c-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="2819c-154">Para excluir um eDiscovery hold:</span><span class="sxs-lookup"><span data-stu-id="2819c-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="2819c-155">Vá para **a guia** Retém no caso em que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="2819c-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="2819c-156">Clique na espera que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="2819c-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="2819c-157">Na página do flyout, clique em **Excluir bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="2819c-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="2819c-158">Para excluir uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="2819c-158">To delete a case:</span></span>

1. <span data-ttu-id="2819c-159">No centro de conformidade do Microsoft 365, clique em **eDiscovery** Core para exibir a lista de principais ocorrências de Descoberta  >   eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2819c-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="2819c-160">Clique no nome da ocorrência que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="2819c-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="2819c-161">Em **Gerenciar status da ocorrência** na página do sub-sub-piloto, clique em Excluir **caso.**</span><span class="sxs-lookup"><span data-stu-id="2819c-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="2819c-162">Se o caso que você estiver tentando excluir ainda contiver rescuções de Descoberta eDiscovery, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="2819c-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="2819c-163">Você terá que excluir todas as retém associadas à ocorrência e, em seguida, tentar novamente excluir a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2819c-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
