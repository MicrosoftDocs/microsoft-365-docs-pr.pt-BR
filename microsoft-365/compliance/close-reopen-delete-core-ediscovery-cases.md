---
title: Fechar, reabrir e excluir principais casos de Descoberta eDiscovery
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
description: Este artigo descreve como gerenciar os principais casos de Descoberta eDiscovery. Isso inclui fechar um caso, reabrir um caso fechado e excluir um caso.
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532441"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="68c66-104">Fechar, reabrir e excluir um caso de Descoberta Principal</span><span class="sxs-lookup"><span data-stu-id="68c66-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="68c66-105">Este artigo descreve como fechar, reabrir e excluir os principais casos de Descoberta Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68c66-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="68c66-106">Fechar um caso</span><span class="sxs-lookup"><span data-stu-id="68c66-106">Close a case</span></span>

<span data-ttu-id="68c66-107">Quando o caso legal ou a investigação com suporte de um caso core de Descoberta eDiscovery for concluído, você poderá fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="68c66-108">Veja o que acontece quando você fecha um caso:</span><span class="sxs-lookup"><span data-stu-id="68c66-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="68c66-109">Se o caso contiver qualquer ressarção de Descoberta E, eles serão desligados.</span><span class="sxs-lookup"><span data-stu-id="68c66-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="68c66-110">Depois que a espera é desligada, um período de carência de 30 dias (chamado de *atraso)* é aplicado a locais de conteúdo que estavam em espera.</span><span class="sxs-lookup"><span data-stu-id="68c66-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="68c66-111">Isso ajuda a impedir que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar e restaurar conteúdo antes que ele possa ser excluído permanentemente depois que o período de espera de atraso expirar.</span><span class="sxs-lookup"><span data-stu-id="68c66-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="68c66-112">Para obter mais informações, consulte [Removendo locais de conteúdo de uma remoção de descoberta de eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="68c66-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="68c66-113">Fechar um caso apenas desativa as retenções que estão associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="68c66-114">Se outras retenções são colocadas em um local de conteúdo (como uma Retenção de Litígio, uma política de retenção ou uma retenção de um caso de Descoberta eDiscovery Principal diferente), essas retenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="68c66-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="68c66-115">O caso ainda está listado na página Descoberta Principal da Descoberta Microsoft 365 de conformidade.</span><span class="sxs-lookup"><span data-stu-id="68c66-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="68c66-116">Os detalhes, retenções, pesquisas e membros de um caso fechado são retidos.</span><span class="sxs-lookup"><span data-stu-id="68c66-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="68c66-117">Você pode editar uma ocorrência depois que ela for fechada.</span><span class="sxs-lookup"><span data-stu-id="68c66-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="68c66-118">Por exemplo, você pode adicionar ou remover membros, criar pesquisas e exportar resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="68c66-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="68c66-119">A principal diferença entre os casos ativos e fechados é que os ressarcedores de Descoberta e São desligados quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="68c66-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="68c66-120">Para fechar um caso:</span><span class="sxs-lookup"><span data-stu-id="68c66-120">To close a case:</span></span>
  
1. <span data-ttu-id="68c66-121">No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68c66-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="68c66-122">Clique no nome do caso que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="68c66-122">Click the name of the case that you want to close.</span></span>

   ![Fechar caso na home page do caso](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="68c66-124">Na home page, em **Status**, clique **em Fechar caso**.</span><span class="sxs-lookup"><span data-stu-id="68c66-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="68c66-125">Um aviso é exibido dizendo que os ressarcições associados à ocorrência serão desligados.</span><span class="sxs-lookup"><span data-stu-id="68c66-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="68c66-126">Clique **em Sim** para fechar o caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="68c66-127">O status na home page do caso é alterado de **Ativo** para **Fechamento**.</span><span class="sxs-lookup"><span data-stu-id="68c66-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="68c66-128">Na página **Descoberta Automática Principal,** clique em **Atualizar** para atualizar o status do caso fechado.</span><span class="sxs-lookup"><span data-stu-id="68c66-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="68c66-129">Pode levar até 60 minutos para o processo de fechamento concluir.</span><span class="sxs-lookup"><span data-stu-id="68c66-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="68c66-130">Quando o processo é concluído, o status da ocorrência é alterado para **Fechado** na página **Descoberta Principal.**</span><span class="sxs-lookup"><span data-stu-id="68c66-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="68c66-131">Reabrir um caso fechado</span><span class="sxs-lookup"><span data-stu-id="68c66-131">Reopen a closed case</span></span>

<span data-ttu-id="68c66-132">Quando você reabrir um caso, qualquer Descoberta Automática que estava no local quando o caso foi fechado não será automaticamente restabelecido.</span><span class="sxs-lookup"><span data-stu-id="68c66-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="68c66-133">Depois que o caso for reaberto, você terá que ir para a página **Retém** e ativar as ressarções anteriores.</span><span class="sxs-lookup"><span data-stu-id="68c66-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="68c66-134">Para ativar uma retenção, selecione para exibir o submenu da página e depois alterne o **Status** para **Ativo**. </span><span class="sxs-lookup"><span data-stu-id="68c66-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="68c66-135">No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68c66-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="68c66-136">Clique no nome do caso que você deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="68c66-136">Click the name of the case that you want to reopen.</span></span>

   ![Reabrir um caso fechado](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="68c66-138">Na home page, em **Status**, clique em **Reabrir caso**.</span><span class="sxs-lookup"><span data-stu-id="68c66-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="68c66-139">Um aviso é exibido dizendo que as resvações associadas à ocorrência quando ela foi fechada não serão ativados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="68c66-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="68c66-140">Clique **em Sim** para reabrir o caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="68c66-141">O status na página de sobrevoo da home page de caso é alterado **de Closed** para **Active**.</span><span class="sxs-lookup"><span data-stu-id="68c66-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="68c66-142">Na página **Descoberta Principal da Descoberta Automática,** clique em **Atualizar** para atualizar o status do caso reaberto.</span><span class="sxs-lookup"><span data-stu-id="68c66-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="68c66-143">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="68c66-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="68c66-144">Quando o processo é concluído, o status da ocorrência é alterado para **Ativo** na página **Descoberta Principal.**</span><span class="sxs-lookup"><span data-stu-id="68c66-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="68c66-145">(Opcional) Para ativar quaisquer bloqueios associados ao caso  reaberto, vá para a guia Bloqueios, selecione uma responsabilidade e selecione a caixa de seleção em **Status** na página de subsuletor de espera.</span><span class="sxs-lookup"><span data-stu-id="68c66-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="68c66-146">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="68c66-146">Delete a case</span></span>

<span data-ttu-id="68c66-147">Você também pode excluir casos ativos e fechados de Descoberta eDiscovery Principal.</span><span class="sxs-lookup"><span data-stu-id="68c66-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="68c66-148">Quando você exclui um caso, todas as pesquisas e exportações no caso são excluídas, e o caso é removido da lista de casos na página Descoberta Principal de **Descoberta** e No centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68c66-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="68c66-149">Não é possível reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="68c66-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="68c66-150">Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), primeiro exclua todas as resções de *Descoberta* De eDiscovery associadas ao caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="68c66-151">Isso inclui a exclusão de retém com um status de **Off**.</span><span class="sxs-lookup"><span data-stu-id="68c66-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="68c66-152">Para excluir uma ressarção de Descoberta e:</span><span class="sxs-lookup"><span data-stu-id="68c66-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="68c66-153">Vá na **guia Retém** no caso em que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="68c66-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="68c66-154">Selecione a espera que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="68c66-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="68c66-155">Na página de sobrevoo, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="68c66-155">On the flyout page, click **Delete**.</span></span>

      ![Excluir uma responsabilidade de Descoberta De eDiscovery](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="68c66-157">Para excluir um caso:</span><span class="sxs-lookup"><span data-stu-id="68c66-157">To delete a case:</span></span>

1. <span data-ttu-id="68c66-158">No centro Microsoft 365 de conformidade, clique em **eDiscovery** Core para exibir a lista de principais casos de  >   Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="68c66-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="68c66-159">Clique no nome do caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="68c66-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="68c66-160">Na home page do caso, em **Status**, clique **em Excluir caso**.</span><span class="sxs-lookup"><span data-stu-id="68c66-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![Excluir uma ocorrência](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="68c66-162">Se o caso que você estiver tentando excluir ainda contiver retém a Descoberta E, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="68c66-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="68c66-163">Você terá que excluir todas as ressarcições associadas à ocorrência e tentar novamente excluir o caso.</span><span class="sxs-lookup"><span data-stu-id="68c66-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
