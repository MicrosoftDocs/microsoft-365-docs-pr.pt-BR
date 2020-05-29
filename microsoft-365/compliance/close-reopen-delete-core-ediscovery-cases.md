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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412790"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="3eafa-104">Fechar, reabrir e excluir uma ocorrência de descoberta eletrônica principal</span><span class="sxs-lookup"><span data-stu-id="3eafa-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="3eafa-105">Este artigo descreve como fechar, reabrir e excluir casos de descoberta eletrônica principais no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3eafa-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="3eafa-106">Fechar uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="3eafa-106">Close a case</span></span>

<span data-ttu-id="3eafa-107">Quando o caso ou investigação legal suportado por uma caixa de descoberta eletrônica principal é concluída, você pode fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="3eafa-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="3eafa-108">Veja o que acontece quando você fecha um caso:</span><span class="sxs-lookup"><span data-stu-id="3eafa-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="3eafa-109">Se o caso contiver qualquer local de conteúdo em retenção de descoberta eletrônica, essas isenções serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="3eafa-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="3eafa-110">Depois que a retenção é desativada, um período de cortesia de 30 dias (chamado de *espera de atraso*) é aplicado aos locais de conteúdo que estavam em espera.</span><span class="sxs-lookup"><span data-stu-id="3eafa-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="3eafa-111">Isso ajuda a evitar que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de Pesquisar e restaurar o conteúdo antes que ele possa ser excluído permanentemente após o período de espera de atraso expirar.</span><span class="sxs-lookup"><span data-stu-id="3eafa-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="3eafa-112">Para obter mais informações, consulte [removendo locais de conteúdo de um controle de descoberta eletrônica](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="3eafa-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="3eafa-113">O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="3eafa-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="3eafa-114">Se outras isenções forem colocadas em um local de conteúdo (como uma retenção de litígio, uma política de retenção ou uma retenção de um caso de descoberta eletrônica diferente), essas isenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="3eafa-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="3eafa-115">O caso ainda está listado na página de descoberta eletrônica principal no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3eafa-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3eafa-116">Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.</span><span class="sxs-lookup"><span data-stu-id="3eafa-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="3eafa-117">Você pode editar uma ocorrência após ela ser fechada.</span><span class="sxs-lookup"><span data-stu-id="3eafa-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="3eafa-118">Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3eafa-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="3eafa-119">A principal diferença entre casos ativos e fechados é que a descoberta eletrônica é desativada quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="3eafa-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="3eafa-120">Para fechar uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="3eafa-120">To close a case:</span></span>
  
1. <span data-ttu-id="3eafa-121">No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3eafa-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3eafa-122">Clique no nome do caso que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="3eafa-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="3eafa-123">A página **gerenciar esse** submenu de caso é exibida.</span><span class="sxs-lookup"><span data-stu-id="3eafa-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="3eafa-124">Em **gerenciar o status de caso**, clique em **fechar caso**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="3eafa-125">Um aviso é exibido dizendo que as suspensões associadas ao caso serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="3eafa-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="3eafa-126">Clique em **Sim** para fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="3eafa-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="3eafa-127">O status da página **gerenciar esse** submenu de caso é alterado de **ativo** para **encerramento**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="3eafa-128">Feche a página **gerenciar este caso** .</span><span class="sxs-lookup"><span data-stu-id="3eafa-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="3eafa-129">Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status da ocorrência fechada.</span><span class="sxs-lookup"><span data-stu-id="3eafa-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="3eafa-130">Pode levar até 60 minutos para que o processo de fechamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="3eafa-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="3eafa-131">Quando o processo estiver concluído, o status da ocorrência será alterado para **fechado** na página de **descoberta eletrônica principal** .</span><span class="sxs-lookup"><span data-stu-id="3eafa-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="3eafa-132">Clique no nome do caso novamente para exibir a página **gerenciar este caso** , que contém informações sobre quando o caso foi fechado e quem o fechou.</span><span class="sxs-lookup"><span data-stu-id="3eafa-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="3eafa-133">Reabrir uma ocorrência fechada</span><span class="sxs-lookup"><span data-stu-id="3eafa-133">Reopen a closed case</span></span>

<span data-ttu-id="3eafa-134">Quando você reabrir um caso, qualquer bloqueio de descoberta eletrônica que estava no lugar quando o caso foi fechado não será restabelecido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3eafa-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="3eafa-135">Depois que o caso for reaberto, você terá que ir para a página de **isenções** e ativar as isenções anteriores.</span><span class="sxs-lookup"><span data-stu-id="3eafa-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="3eafa-136">Para ativar uma retenção, selecione-a para exibir a página do submenu e, em seguida, defina o **status** de alternância como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="3eafa-137">No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3eafa-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3eafa-138">Clique no nome do caso que você deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="3eafa-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="3eafa-139">A página **gerenciar esse** submenu de caso é exibida.</span><span class="sxs-lookup"><span data-stu-id="3eafa-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="3eafa-140">Em **gerenciar o status de caso**, clique em **reabrir caso**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="3eafa-141">Um aviso é exibido dizendo que as suspensões que estavam associadas ao caso em que foram fechadas não serão ativadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3eafa-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="3eafa-142">Clique em **Sim** para reabrir a ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3eafa-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="3eafa-143">O status da página **gerenciar esse** submenu de caso é alterado de **fechado** para **ativo**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="3eafa-144">Feche a página **gerenciar este caso** .</span><span class="sxs-lookup"><span data-stu-id="3eafa-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="3eafa-145">Na página **descoberta eletrônica principal** , clique em **Atualizar** para atualizar o status do caso reaberto.</span><span class="sxs-lookup"><span data-stu-id="3eafa-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="3eafa-146">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="3eafa-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="3eafa-147">Quando o processo estiver concluído, o status da ocorrência será alterado para **ativo** na página de **descoberta eletrônica principal** .</span><span class="sxs-lookup"><span data-stu-id="3eafa-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="3eafa-148">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="3eafa-148">Delete a case</span></span>

<span data-ttu-id="3eafa-149">Você também pode excluir casos de descoberta eletrônica ativos e fechados.</span><span class="sxs-lookup"><span data-stu-id="3eafa-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="3eafa-150">Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas e o caso é removido da lista de casos na página de **descoberta eletrônica principal** do centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3eafa-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="3eafa-151">Não é possível reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="3eafa-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="3eafa-152">Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* retenções de descoberta eletrônica associadas à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="3eafa-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="3eafa-153">Isso inclui a exclusão de isenções com o status **desativado**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="3eafa-154">Para excluir uma retenção de descoberta eletrônica:</span><span class="sxs-lookup"><span data-stu-id="3eafa-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="3eafa-155">Vá para a guia **isenções** , caso você queira excluir.</span><span class="sxs-lookup"><span data-stu-id="3eafa-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="3eafa-156">Clique na isenção que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="3eafa-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="3eafa-157">Na página do menu suspenso, clique em **excluir isenção**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="3eafa-158">Para excluir uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="3eafa-158">To delete a case:</span></span>

1. <span data-ttu-id="3eafa-159">No centro de conformidade da Microsoft 365, clique em Central de **descoberta eletrônica**  >  **Core** para exibir a lista de principais casos de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3eafa-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="3eafa-160">Clique no nome do caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="3eafa-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="3eafa-161">Em **gerenciar status de caso** na página de submenu, clique em **excluir caso**.</span><span class="sxs-lookup"><span data-stu-id="3eafa-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="3eafa-162">Se o caso que você está tentando excluir ainda contiver bloqueios de descoberta eletrônica, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="3eafa-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="3eafa-163">Você terá que excluir todas as suspensões associadas à ocorrência e, em seguida, tentar excluir a ocorrência novamente.</span><span class="sxs-lookup"><span data-stu-id="3eafa-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
