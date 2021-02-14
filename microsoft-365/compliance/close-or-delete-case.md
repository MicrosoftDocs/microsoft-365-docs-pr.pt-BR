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
description: Saiba o que acontece quando uma investigação ou um caso jurídico suportado por um caso de Descoberta Avançada é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419057"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="0c2ad-103">Fechar ou excluir uma ocorrência de Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="0c2ad-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="0c2ad-104">Quando o caso jurídico ou a investigação suportado por um caso de Descoberta Avançada for concluído, você poderá fechar ou excluir uma ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="0c2ad-105">Você também pode reabrir um caso fechado.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="0c2ad-106">Fechar uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="0c2ad-106">Close a case</span></span>

<span data-ttu-id="0c2ad-107">Veja o que acontece quando você fecha um caso de Descoberta Avançada:</span><span class="sxs-lookup"><span data-stu-id="0c2ad-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="0c2ad-108">Se o caso contiver qualquer local de conteúdo em espera, essas regiões serão desligadas.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="0c2ad-109">Depois que a espera é desligada, um período de carência de 30 dias (chamado de espera de *atraso)* é aplicado a locais de conteúdo que estavam em espera.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="0c2ad-110">Isso ajuda a evitar que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar ou recuperar conteúdo que será excluído permanentemente após o período de espera de atraso expirar.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="0c2ad-111">Para obter mais informações, [consulte Removendo locais de conteúdo de um eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="0c2ad-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="0c2ad-112">Fechar uma ocorrência só desliga as retém associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="0c2ad-113">Se outras retenções ocorrerem em um local de conteúdo (como uma Responsabilidade de Litígio, Uma Espera principal de Descoberta eDiscovery ou uma responsabilidade de um caso de Descoberta eDiscovery Avançada diferente), essas retenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="0c2ad-114">A ocorrência ainda está listada na página de Descobertas EDiscovery no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0c2ad-115">Os detalhes, retidos, pesquisas e membros de um caso fechado são mantidos.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="0c2ad-116">Você pode editar uma ocorrência depois que ela for fechada.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="0c2ad-117">Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise na Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="0c2ad-118">A principal diferença entre os casos ativos e fechados é que as retém são desligadas quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="0c2ad-119">Para fechar um caso:</span><span class="sxs-lookup"><span data-stu-id="0c2ad-119">To close a case:</span></span>

1. <span data-ttu-id="0c2ad-120">Na página **Descobertas Avançadas,** selecione a ocorrência que você deseja fechar.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="0c2ad-121">Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0c2ad-122">Clique **em Fechar caso.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-122">Click **Close case**.</span></span>

   <span data-ttu-id="0c2ad-123">Pode levar até 60 minutos para que o processo de fechamento seja concluído.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="0c2ad-124">Reabrir um caso fechado</span><span class="sxs-lookup"><span data-stu-id="0c2ad-124">Reopen a closed case</span></span>

<span data-ttu-id="0c2ad-125">Quando você reabrir um caso de Descoberta Automática Avançada, todas as resuspensão que estavam no local quando o caso foi fechado não serão automaticamente restabelecimento.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="0c2ad-126">Depois que o caso for reaberto, você terá que ir para a guia **Isões** e ativar as retém anteriores.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="0c2ad-127">Para ativar uma espera, selecione-a para exibir a página do flyout e, em seguida, de definir a **alternância de Status** para **Ativar.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="0c2ad-128">Para reabrir um caso fechado:</span><span class="sxs-lookup"><span data-stu-id="0c2ad-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="0c2ad-129">Na página **Descoberta Avançada,** selecione a ocorrência que você deseja reabrir.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="0c2ad-130">Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0c2ad-131">Clique **em Caso de Reabertura.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="0c2ad-132">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="0c2ad-133">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="0c2ad-133">Delete a case</span></span>

<span data-ttu-id="0c2ad-134">Você pode excluir ocorrências de Descobertas Avançadas ativas e fechadas.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="0c2ad-135">Quando você exclui uma ocorrência, todos os componentes associados à ocorrência, como a lista de custodiantes, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="0c2ad-136">O caso é removido da lista de casos na **página Descobertas Avançadas** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0c2ad-137">Não é possível recuperar ou reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="0c2ad-138">Em cenários de vazamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir o caso de Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="0c2ad-139">Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="0c2ad-140">Antes de excluir uma ocorrência (se ela está ativa  ou fechada), primeiro você deve excluir todas as retém associadas à ocorrência.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="0c2ad-141">Isso inclui a exclusão de retém com um status **de Desligado**.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="0c2ad-142">Para excluir retém associadas a uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="0c2ad-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="0c2ad-143">Vá para **a** guia Retém no caso de Descoberta eDiscovery Avançada que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="0c2ad-144">Clique na espera que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="0c2ad-145">Na página do flyout, clique em **Excluir bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="0c2ad-146">Para excluir uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="0c2ad-146">To delete a case:</span></span>

1. <span data-ttu-id="0c2ad-147">Na página **Descobertas Avançadas,** selecione a ocorrência que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="0c2ad-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="0c2ad-148">Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="0c2ad-149">Clique **em Excluir caso.**</span><span class="sxs-lookup"><span data-stu-id="0c2ad-149">Click **Delete case**.</span></span>
