---
title: Fechar ou excluir uma ocorrência
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba o que acontece quando uma investigação ou um caso jurídico suportado por um caso de descoberta eletrônica avançada é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292407"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="15551-103">Fechar ou excluir uma ocorrência de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="15551-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="15551-104">Quando o caso ou investigação legal suportado por uma ocorrência de descoberta eletrônica avançada estiver concluído, você poderá fechar ou excluir uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="15551-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="15551-105">Você também pode reabrir uma ocorrência fechada.</span><span class="sxs-lookup"><span data-stu-id="15551-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="15551-106">Fechar uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="15551-106">Close a case</span></span>

<span data-ttu-id="15551-107">Veja o que acontece quando você fecha uma caixa de descoberta eletrônica avançada:</span><span class="sxs-lookup"><span data-stu-id="15551-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="15551-108">Se o caso contiver qualquer local de conteúdo em espera, essas isenções serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="15551-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="15551-109">Isso pode resultar na exclusão ou limpeza permanente do conteúdo, seja pelo usuário ou por um processo automatizado, como uma política de exclusão.</span><span class="sxs-lookup"><span data-stu-id="15551-109">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="15551-110">O fechamento de um caso desativa apenas as suspensões que estão associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="15551-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="15551-111">Se outras isenções forem mantidas em um local de conteúdo (como uma retenção de litígio, controle de descoberta eletrônica principal ou uma retenção de uma ocorrência de descoberta eletrônica avançada diferente), elas ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="15551-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="15551-112">O caso ainda está listado na página descoberta eletrônica no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15551-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="15551-113">Os detalhes, isenções, pesquisas e membros de um caso fechado são mantidos.</span><span class="sxs-lookup"><span data-stu-id="15551-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="15551-114">Você pode editar uma ocorrência após ela ser fechada.</span><span class="sxs-lookup"><span data-stu-id="15551-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="15551-115">Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="15551-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="15551-116">A principal diferença entre casos ativos e fechados é que a retenção é desativada quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="15551-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="15551-117">Para fechar uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="15551-117">To close a case:</span></span>

1. <span data-ttu-id="15551-118">Na página **descoberta eletrônica avançada** , selecione o caso que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="15551-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="15551-119">Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="15551-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="15551-120">Clique em **fechar caso**.</span><span class="sxs-lookup"><span data-stu-id="15551-120">Click **Close case**.</span></span>

   <span data-ttu-id="15551-121">Pode levar até 60 minutos para que o processo de fechamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="15551-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="15551-122">Reabrir uma ocorrência fechada</span><span class="sxs-lookup"><span data-stu-id="15551-122">Reopen a closed case</span></span>

<span data-ttu-id="15551-123">Quando você reabre um caso de descoberta eletrônica avançada, qualquer bloqueio que estava no lugar quando o caso foi fechado não será restabelecido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="15551-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="15551-124">Depois que o caso for reaberto, você terá que ir para a guia **isenções** e ativar as isenções anteriores.</span><span class="sxs-lookup"><span data-stu-id="15551-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="15551-125">Para ativar uma retenção, selecione-a para exibir a página do submenu e, em seguida, defina o **status** de alternância como **ativado**.</span><span class="sxs-lookup"><span data-stu-id="15551-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="15551-126">Para reabrir uma ocorrência fechada:</span><span class="sxs-lookup"><span data-stu-id="15551-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="15551-127">Na página **descoberta eletrônica avançada** , selecione o caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="15551-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="15551-128">Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="15551-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="15551-129">Clique em **reabrir caso**.</span><span class="sxs-lookup"><span data-stu-id="15551-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="15551-130">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="15551-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="15551-131">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="15551-131">Delete a case</span></span>

<span data-ttu-id="15551-132">Você pode excluir casos de descoberta eletrônica avançados ativos e fechados.</span><span class="sxs-lookup"><span data-stu-id="15551-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="15551-133">Quando você exclui um caso, todos os componentes associados ao caso, como a lista de responsáveis, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos.</span><span class="sxs-lookup"><span data-stu-id="15551-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="15551-134">O caso é removido da lista de casos na página **descoberta eletrônica avançada** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15551-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="15551-135">Não é possível recuperar ou reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="15551-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="15551-136">Em cenários de derramamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir a caixa de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="15551-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="15551-137">Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="15551-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="15551-138">Antes de poder excluir uma ocorrência (se ela está ativa ou fechada), você deve primeiro excluir *todas as* isenções associadas à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="15551-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="15551-139">Isso inclui a exclusão de isenções com o status **desativado**.</span><span class="sxs-lookup"><span data-stu-id="15551-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="15551-140">Para excluir suspensões associadas a um caso:</span><span class="sxs-lookup"><span data-stu-id="15551-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="15551-141">Vá para a guia **isenções** na caixa de descoberta eletrônica avançada que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="15551-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="15551-142">Clique na isenção que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="15551-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="15551-143">Na página do menu suspenso, clique em **excluir isenção**.</span><span class="sxs-lookup"><span data-stu-id="15551-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="15551-144">Para excluir uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="15551-144">To delete a case:</span></span>

1. <span data-ttu-id="15551-145">Na página **descoberta eletrônica avançada** , selecione o caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="15551-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="15551-146">Na guia **configurações** , em **informações da ocorrência**, clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="15551-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="15551-147">Clique em **excluir caso**.</span><span class="sxs-lookup"><span data-stu-id="15551-147">Click **Delete case**.</span></span>
