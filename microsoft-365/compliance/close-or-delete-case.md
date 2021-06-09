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
description: Saiba o que acontece quando uma investigação ou um caso legal suportado por Advanced eDiscovery caso é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657628"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="06273-103">Fechar ou excluir uma Advanced eDiscovery caso</span><span class="sxs-lookup"><span data-stu-id="06273-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="06273-104">Quando o caso legal ou a investigação suportado por um caso Advanced eDiscovery for concluído, você poderá fechar ou excluir um caso.</span><span class="sxs-lookup"><span data-stu-id="06273-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="06273-105">Você também pode reabrir um caso fechado.</span><span class="sxs-lookup"><span data-stu-id="06273-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="06273-106">Fechar um caso</span><span class="sxs-lookup"><span data-stu-id="06273-106">Close a case</span></span>

<span data-ttu-id="06273-107">Veja o que acontece quando você fecha um Advanced eDiscovery caso:</span><span class="sxs-lookup"><span data-stu-id="06273-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="06273-108">Se o caso possui qualquer local de conteúdo em retenção, essas retenções serão desativadas.</span><span class="sxs-lookup"><span data-stu-id="06273-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="06273-109">Depois que a espera é desligada, um período de carência de 30 dias (chamado de *atraso)* é aplicado a locais de conteúdo que estavam em espera.</span><span class="sxs-lookup"><span data-stu-id="06273-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="06273-110">Isso ajuda a impedir que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar ou recuperar conteúdo que será excluído permanentemente depois que o período de espera de atraso expirar.</span><span class="sxs-lookup"><span data-stu-id="06273-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="06273-111">Para obter mais informações, consulte [Removendo locais de conteúdo de uma remoção de descoberta de eDiscovery](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span><span class="sxs-lookup"><span data-stu-id="06273-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="06273-112">Fechar um caso apenas fecha as retenções que estão associadas a esse caso.</span><span class="sxs-lookup"><span data-stu-id="06273-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="06273-113">Se outras retenções ocorrerem em um local de conteúdo (como uma responsabilidade por litígio, uma retenção de Descoberta Principal ou uma retenção de um caso Advanced eDiscovery caso diferente), essas retenções ainda serão mantidas.</span><span class="sxs-lookup"><span data-stu-id="06273-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="06273-114">O caso ainda está listado na página Descoberta e-descoberta no centro Microsoft 365 conformidade.</span><span class="sxs-lookup"><span data-stu-id="06273-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="06273-115">Os detalhes, retenções, pesquisas e membros de um caso fechado são retidos.</span><span class="sxs-lookup"><span data-stu-id="06273-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="06273-116">Você pode editar uma ocorrência depois que ela for fechada.</span><span class="sxs-lookup"><span data-stu-id="06273-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="06273-117">Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise em Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="06273-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="06273-118">A principal diferença entre caso ativo ou fechado é que as retenções são desativadas quando um caso é fechado.</span><span class="sxs-lookup"><span data-stu-id="06273-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="06273-119">Para fechar um caso:</span><span class="sxs-lookup"><span data-stu-id="06273-119">To close a case:</span></span>

1. <span data-ttu-id="06273-120">Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser fechado.</span><span class="sxs-lookup"><span data-stu-id="06273-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="06273-121">Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="06273-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="06273-122">Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Fechar caso**.</span><span class="sxs-lookup"><span data-stu-id="06273-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![Opção no menu Mais opções para fechar um Advanced eDiscovery caso](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="06273-124">Pode levar até 60 minutos para o processo de fechamento concluir.</span><span class="sxs-lookup"><span data-stu-id="06273-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="06273-125">Reabrir um caso fechado</span><span class="sxs-lookup"><span data-stu-id="06273-125">Reopen a closed case</span></span>

<span data-ttu-id="06273-126">Quando você reabrir Advanced eDiscovery caso, quaisquer ressarcimentos que estavam no local quando o caso foi fechado não serão automaticamente reinstalados.</span><span class="sxs-lookup"><span data-stu-id="06273-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="06273-127">Depois que o caso for reaberto, você terá que ir até a guia **Retém** e ativar as resvasões anteriores.</span><span class="sxs-lookup"><span data-stu-id="06273-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="06273-128">Para ativar uma retenção, selecione para exibir o submenu da página e depois alterne o **Status** para **Ativo**. </span><span class="sxs-lookup"><span data-stu-id="06273-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="06273-129">Para reabrir um caso fechado:</span><span class="sxs-lookup"><span data-stu-id="06273-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="06273-130">Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser reaberto.</span><span class="sxs-lookup"><span data-stu-id="06273-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="06273-131">Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="06273-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="06273-132">Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Reabrir caso**.</span><span class="sxs-lookup"><span data-stu-id="06273-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![Opção no menu Mais opções para reabrir uma Advanced eDiscovery caso](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="06273-134">Pode levar até 60 minutos para que o processo de reabertura seja concluído.</span><span class="sxs-lookup"><span data-stu-id="06273-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="06273-135">Excluir uma ocorrência</span><span class="sxs-lookup"><span data-stu-id="06273-135">Delete a case</span></span>

<span data-ttu-id="06273-136">Você pode excluir os casos ativos e Advanced eDiscovery fechados.</span><span class="sxs-lookup"><span data-stu-id="06273-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="06273-137">Quando você exclui um caso, todos os componentes associados a ele, como lista de custodiantes, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos.</span><span class="sxs-lookup"><span data-stu-id="06273-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="06273-138">O caso é removido da lista de casos na **página** Advanced eDiscovery no centro Microsoft 365 conformidade.</span><span class="sxs-lookup"><span data-stu-id="06273-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="06273-139">Não é possível recuperar ou reabrir um caso excluído.</span><span class="sxs-lookup"><span data-stu-id="06273-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="06273-140">Em cenários de vazamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir o Advanced eDiscovery caso.</span><span class="sxs-lookup"><span data-stu-id="06273-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="06273-141">Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="06273-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="06273-142">Antes de poder excluir uma ocorrência (se ela está  ativa ou fechada), primeiro exclua todas as resções associadas ao caso.</span><span class="sxs-lookup"><span data-stu-id="06273-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="06273-143">Isso inclui a exclusão de retém com um status de **Off**.</span><span class="sxs-lookup"><span data-stu-id="06273-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="06273-144">Para excluir ressarcições associadas a uma ocorrência:</span><span class="sxs-lookup"><span data-stu-id="06273-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="06273-145">Vá na **guia Retém** no Advanced eDiscovery caso que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="06273-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="06273-146">Clique na espera que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="06273-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="06273-147">Na página sobrevoo, clique em **Excluir bloqueio**.</span><span class="sxs-lookup"><span data-stu-id="06273-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="06273-148">Para excluir um caso:</span><span class="sxs-lookup"><span data-stu-id="06273-148">To delete a case:</span></span>

1. <span data-ttu-id="06273-149">Na página **Descoberta Eletrônica Avançada**, selecione o caso para ser excluído.</span><span class="sxs-lookup"><span data-stu-id="06273-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="06273-150">Na guia **Configurações**, em **Informações de caso**, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="06273-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="06273-151">Na parte inferior da página informações **de** caso, clique em (**...**) **Mais opções** e clique em **Excluir caso**.</span><span class="sxs-lookup"><span data-stu-id="06273-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![Opção no menu Mais opções para excluir um Advanced eDiscovery caso](..\Media\DeleteAdvancedeDiscoveryCase.png)
