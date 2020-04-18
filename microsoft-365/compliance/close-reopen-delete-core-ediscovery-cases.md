---
title: Fechar, reabrir e excluir casos de descoberta eletrônica principais
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
description: Este artigo descreve como gerenciar as principais ocorrências de descoberta eletrônica. Isso inclui fechar uma ocorrência, reabrir uma ocorrência fechada e excluir uma ocorrência.
ms.openlocfilehash: 41ba622a58b0abb5ce668e6d94d89b1694a328c9
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551354"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="88a8e-104">Fechar, reabrir e excluir uma ocorrência de descoberta eletrônica principal</span><span class="sxs-lookup"><span data-stu-id="88a8e-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="88a8e-105">Este artigo descreve como fechar, reabrir e excluir casos de descoberta eletrônica principais no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a8e-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="88a8e-106">Fechar uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="88a8e-106">Close a case</span></span>

<span data-ttu-id="88a8e-107">Quando o caso ou investigação legal suportado por uma caixa de descoberta eletrônica principal é concluída, você pode fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="88a8e-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="88a8e-108">Veja o que acontece quando você fecha um caso:</span><span class="sxs-lookup"><span data-stu-id="88a8e-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="88a8e-109">Se o caso contiver qualquer local de conteúdo em retenção de descoberta eletrônica, essas isenções serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="88a8e-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="88a8e-110">Isso pode resultar na exclusão ou limpeza permanente do conteúdo, seja pelo usuário ou por um processo automatizado, como uma política de exclusão.</span><span class="sxs-lookup"><span data-stu-id="88a8e-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="88a8e-111">O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="88a8e-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="88a8e-112">Se outras isenções forem colocadas em um local de conteúdo (como uma retenção de litígio, uma política de retenção ou uma retenção de um caso de descoberta eletrônica diferente), essas isenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="88a8e-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="88a8e-113">O caso ainda está listado na página de descoberta eletrônica principal no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a8e-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="88a8e-114">Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.</span><span class="sxs-lookup"><span data-stu-id="88a8e-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="88a8e-115">Você pode editar uma ocorrência após ela ser fechada.</span><span class="sxs-lookup"><span data-stu-id="88a8e-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="88a8e-116">Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="88a8e-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="88a8e-117">A principal diferença entre casos ativos e fechados é que a descoberta eletrônica é desativada quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="88a8e-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="88a8e-118">Para fechar uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="88a8e-118">To close a case:</span></span>
  
1. <span data-ttu-id="88a8e-119">No centro de conformidade da Microsoft 365, clique em**central** de **descoberta eletrônica** > para exibir a lista de casos de descoberta eletrônica principal em sua organização.</span><span class="sxs-lookup"><span data-stu-id="88a8e-119">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="88a8e-120">Clique no nome do caso que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="88a8e-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="88a8e-121">A página **gerenciar esse** submenu de caso é exibida.</span><span class="sxs-lookup"><span data-stu-id="88a8e-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="88a8e-122">Em **gerenciar o status de caso**, clique em **fechar caso**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="88a8e-123">Um aviso é exibido dizendo que as suspensões associadas ao caso serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="88a8e-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="88a8e-124">Clique em **Sim** para fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="88a8e-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="88a8e-125">O status da página **gerenciar esse** submenu de caso é alterado de **ativo** para **encerramento**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="88a8e-126">Feche a página **gerenciar este caso** .</span><span class="sxs-lookup"><span data-stu-id="88a8e-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="88a8e-127">Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status da ocorrência fechada.</span><span class="sxs-lookup"><span data-stu-id="88a8e-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="88a8e-128">Pode levar até 60 minutos para que o processo de fechamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="88a8e-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="88a8e-129">Quando o processo estiver concluído, o status da ocorrência será alterado para **fechado** na página de **descoberta eletrônica principal** .</span><span class="sxs-lookup"><span data-stu-id="88a8e-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="88a8e-130">Clique no nome do caso novamente para exibir a página **gerenciar este caso** , que contém informações sobre quando o caso foi fechado e quem o fechou.</span><span class="sxs-lookup"><span data-stu-id="88a8e-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="88a8e-131">Reabrir uma ocorrência fechada</span><span class="sxs-lookup"><span data-stu-id="88a8e-131">Reopen a closed case</span></span>

<span data-ttu-id="88a8e-132">Quando você reabrir um caso, qualquer bloqueio de descoberta eletrônica que estava no lugar quando o caso foi fechado não será restabelecido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88a8e-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="88a8e-133">Depois que o caso for reaberto, você terá que ir para a página de **isenções** e ativar as isenções anteriores.</span><span class="sxs-lookup"><span data-stu-id="88a8e-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="88a8e-134">Para ativar uma retenção, selecione-a para exibir a página do submenu e, em seguida, defina o **status** de alternância como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="88a8e-135">No centro de conformidade da Microsoft 365, clique em**central** de **descoberta eletrônica** > para exibir a lista de casos de descoberta eletrônica principal em sua organização.</span><span class="sxs-lookup"><span data-stu-id="88a8e-135">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="88a8e-136">Clique no nome do caso que você deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="88a8e-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="88a8e-137">A página **gerenciar esse** submenu de caso é exibida.</span><span class="sxs-lookup"><span data-stu-id="88a8e-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="88a8e-138">Em **gerenciar o status de caso**, clique em **reabrir caso**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="88a8e-139">Um aviso é exibido dizendo que as suspensões que estavam associadas ao caso em que foram fechadas não serão ativadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88a8e-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="88a8e-140">Clique em **Sim** para reabrir a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="88a8e-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="88a8e-141">O status da página **gerenciar esse** submenu de caso é alterado de **fechado** para **ativo**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="88a8e-142">Feche a página **gerenciar este caso** .</span><span class="sxs-lookup"><span data-stu-id="88a8e-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="88a8e-143">Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status do caso reaberto.</span><span class="sxs-lookup"><span data-stu-id="88a8e-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="88a8e-144">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="88a8e-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="88a8e-145">Quando o processo estiver concluído, o status da ocorrência será alterado para **ativo** na página de **descoberta eletrônica principal** .</span><span class="sxs-lookup"><span data-stu-id="88a8e-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="88a8e-146">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="88a8e-146">Delete a case</span></span>

<span data-ttu-id="88a8e-147">Você também pode excluir casos de descoberta eletrônica ativos e fechados.</span><span class="sxs-lookup"><span data-stu-id="88a8e-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="88a8e-148">Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas e o caso é removido da lista de casos na página de **descoberta eletrônica principal** do centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a8e-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="88a8e-149">Não é possível reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="88a8e-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="88a8e-150">Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* retenções de descoberta eletrônica associadas à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="88a8e-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="88a8e-151">Isso inclui a exclusão de isenções com o status **desativado**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="88a8e-152">Para excluir uma retenção de descoberta eletrônica:</span><span class="sxs-lookup"><span data-stu-id="88a8e-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="88a8e-153">Vá para a guia **isenções** , caso você queira excluir.</span><span class="sxs-lookup"><span data-stu-id="88a8e-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="88a8e-154">Clique na isenção que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="88a8e-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="88a8e-155">Na página do menu suspenso, clique em **excluir isenção**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="88a8e-156">Para excluir uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="88a8e-156">To delete a case:</span></span>

1. <span data-ttu-id="88a8e-157">No centro de conformidade da Microsoft 365, clique em**central** de **descoberta eletrônica** > para exibir a lista de casos de descoberta eletrônica principal em sua organização.</span><span class="sxs-lookup"><span data-stu-id="88a8e-157">In the Microsoft 365 compliance enter, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="88a8e-158">Clique no nome do caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="88a8e-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="88a8e-159">Em **gerenciar status de caso** na página de submenu, clique em **excluir caso**.</span><span class="sxs-lookup"><span data-stu-id="88a8e-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="88a8e-160">Se o caso que você está tentando excluir ainda contiver bloqueios de descoberta eletrônica, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="88a8e-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="88a8e-161">Você terá que excluir todas as suspensões associadas à ocorrência e, em seguida, tentar excluir a ocorrência novamente.</span><span class="sxs-lookup"><span data-stu-id="88a8e-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
