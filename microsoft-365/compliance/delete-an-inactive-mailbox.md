---
title: Excluir uma caixa de correio inativa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, você poderá excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817890"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="668da-103">Excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="668da-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="668da-104">Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização.</span><span class="sxs-lookup"><span data-stu-id="668da-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="668da-105">Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa, você poderá excluir permanentemente a caixa de correio inativa, removendo a isenção.</span><span class="sxs-lookup"><span data-stu-id="668da-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="668da-106">Além disso, é possível que várias isenções possam ser colocadas em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="668da-107">Por exemplo, uma caixa de correio inativa pode ser colocada em retenção de litígio e em uma ou mais suspensões in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="668da-108">Além disso, uma política de retenção (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="668da-109">Você deve remover todas as políticas de retenção e retenção de uma caixa de correio inativa para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="668da-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="668da-110">Após remover as políticas de retenção e retenção, a caixa de correio inativa é marcada para exclusão e excluída permanentemente após ser processada.</span><span class="sxs-lookup"><span data-stu-id="668da-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="668da-111">Como continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="668da-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="668da-112">Isso significa que você deve usar as políticas de retenção e retenção de litígio para criar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="668da-113">A partir de 1º de julho de 2020, você não poderá criar novos bloqueios in-loco no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="668da-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="668da-114">Mas você ainda poderá alterar a duração da retenção de um bloqueio in-loco colocado em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="668da-115">No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="668da-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="668da-116">Você só poderá excluir uma caixa de correio inativa removendo o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="668da-117">As caixas de correio inativas existentes que estão no bloqueio in-loco ainda serão preservadas até que a retenção seja removida.</span><span class="sxs-lookup"><span data-stu-id="668da-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="668da-118">Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="668da-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="668da-119">Consulte a seção [mais informações](#more-information) para obter uma descrição do que acontece depois que as retenções são removidas de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="668da-120">Antes de excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="668da-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="668da-121">Você precisa usar o PowerShell do Exchange Online para remover uma retenção de litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="668da-122">Você não pode usar o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="668da-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="668da-123">Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="668da-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="668da-124">Você pode usar o PowerShell do Exchange Online ou o Eat para remover um bloqueio in-loco de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="668da-125">Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a retenção e excluir uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="668da-126">Para obter detalhes, consulte [restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="668da-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="668da-127">Se você remover a política de retenção ou isenção de uma caixa de correio inativa e o período de retenção de caixa de correio de exclusão reversível da caixa de correio tiver expirado, a caixa de correio será excluída permanentemente.</span><span class="sxs-lookup"><span data-stu-id="668da-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="668da-128">Depois que ele é excluído, ele não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="668da-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="668da-129">Antes de remover a retenção, certifique-se de que você não precisa mais do conteúdo na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="668da-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="668da-130">Se você quiser reativar uma caixa de correio inativa, é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="668da-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="668da-131">Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="668da-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="668da-132">Para obter mais informações sobre caixas de correio inativas, consulte [inativa caixas de correio no Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="668da-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="668da-133">Etapa 1: identificar as isenções em uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="668da-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="668da-134">Conforme mencionado anteriormente, uma retenção de litígio, um bloqueio in-loco ou uma política de retenção pode ser colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="668da-135">A primeira etapa é identificar as isenções em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="668da-136">Execute o seguinte comando para exibir as informações de retenção de todas as caixas de correio inativas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="668da-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="668da-137">O valor de **true** para a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="668da-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="668da-138">Se um bloqueio in-loco for colocado em uma caixa de correio inativa, o GUID da retenção será exibido como o valor da propriedade **InPlaceHolds** .</span><span class="sxs-lookup"><span data-stu-id="668da-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="668da-139">Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma retenção de litígio é colocada em Ana Beebe e que duas isenções in-loco são colocadas na Pilar Fernandes.</span><span class="sxs-lookup"><span data-stu-id="668da-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="668da-140">Se uma grande quantidade de bloqueios in-loco for colocada em uma caixa de correio inativa, nem todos os GUIDs de bloqueio in-loco serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="668da-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="668da-141">Você pode executar o seguinte comando para exibir todos os GUIDs de bloqueio in-loco:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="668da-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="668da-142">Etapa 2: remover uma retenção de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="668da-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="668da-143">Depois de identificar o tipo de retenção que é colocado na caixa de correio inativa (e se há várias isenções), a próxima etapa é remover as isenções da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="668da-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="668da-144">Conforme mencionado anteriormente, você deve remover todas as isenções para excluir permanentemente uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="668da-145">Remover uma retenção de litígio</span><span class="sxs-lookup"><span data-stu-id="668da-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="668da-146">Conforme mencionado anteriormente, você precisa usar o Windows PowerShell para remover uma retenção de litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="668da-147">Você não pode usar o Eat.</span><span class="sxs-lookup"><span data-stu-id="668da-147">You can't use the EAC.</span></span> <span data-ttu-id="668da-148">Execute o comando a seguir para remover uma retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="668da-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="668da-149">A melhor maneira de identificar uma caixa de correio inativa é usando seu nome distinto ou valor de GUID do Exchange.</span><span class="sxs-lookup"><span data-stu-id="668da-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="668da-150">O uso de um desses valores ajuda a evitar a especificação acidental da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="668da-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="668da-151">Remover bloqueios in-loco</span><span class="sxs-lookup"><span data-stu-id="668da-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="668da-152">Há duas maneiras de remover um bloqueio in-loco de uma caixa de correio inativa:</span><span class="sxs-lookup"><span data-stu-id="668da-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="668da-153">**Excluir o objeto bloqueio in-loco** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem de um bloqueio in-loco, você pode simplesmente excluir o objeto de bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="668da-154">Você precisa desabilitar a retenção antes de excluir um objeto de bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="668da-155">Se você tentar excluir um objeto de bloqueio in-loco com a retenção habilitada, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="668da-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="668da-156">**Remover a caixa de correio inativa como uma caixa de correio de origem de um bloqueio in-loco** Se quiser reter outras caixas de correio de origem para um bloqueio in-loco, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="668da-157">Use o Eat para excluir um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="668da-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="668da-158">Se você souber o nome do bloqueio in-loco que deseja excluir, poderá ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="668da-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="668da-159">Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco que é colocado na caixa de correio inativa que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="668da-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="668da-160">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="668da-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="668da-161">No Eat, vá para **Gerenciamento de conformidade** e \> **descoberta eletrônica in &amp; -loco**.</span><span class="sxs-lookup"><span data-stu-id="668da-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="668da-162">Selecione o bloqueio in-loco que você deseja excluir e, em seguida, clique em **Editar** ![ ícone de edição ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="668da-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="668da-163">Na página Propriedades **de &amp; retenção de descoberta eletrônica in-loco** , clique **em bloqueio in-loco**, desmarque a caixa **fazer o conteúdo que corresponde à consulta de pesquisa em caixas de correio selecionadas em retenção** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="668da-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="668da-164">Na página \*\* &amp; bloqueio de descoberta eletrônica in-loco\*\* , selecione o bloqueio in-loco novamente e clique em **excluir** ![ excluir ícone ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="668da-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="668da-165">No aviso, clique em **Sim** para excluir o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="668da-166">Usar o PowerShell do Exchange Online para excluir um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="668da-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="668da-167">Crie uma variável que contenha as propriedades do bloqueio in-loco que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="668da-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="668da-168">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="668da-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="668da-169">Desabilite o bloqueio no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="668da-170">Exclua o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="668da-171">Use o Eat para remover uma caixa de correio inativa de um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="668da-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="668da-172">Se você souber o nome do bloqueio in-loco colocado na caixa de correio inativa, poderá ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="668da-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="668da-173">Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco colocado na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="668da-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="668da-174">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="668da-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="668da-175">No Eat, vá para **Gerenciamento de conformidade** e \> **descoberta eletrônica in &amp; -loco**.</span><span class="sxs-lookup"><span data-stu-id="668da-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="668da-176">Selecione o bloqueio in-loco que é colocado na caixa de correio inativa e, em seguida, clique em **Editar** ![ ícone de edição ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="668da-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="668da-177">Na página Propriedades **de &amp; retenção de descoberta eletrônica in-loco** , clique em **fontes**.</span><span class="sxs-lookup"><span data-stu-id="668da-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="668da-178">Na lista de caixas de correio de origem, clique no nome da caixa de correio inativa que você deseja remover e clique em **remover** ![ Remover ](../media/adf01106-cc79-475c-8673-065371c1897b.gif) .</span><span class="sxs-lookup"><span data-stu-id="668da-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="668da-179">Clique em **Salvar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="668da-179">Click **Save** to save the change.</span></span> <span data-ttu-id="668da-180">Uma mensagem é exibida dizendo que a operação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="668da-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="668da-181">Repita as etapas 1 a 6 para remover outros bloqueios in-loco colocados na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="668da-182">Usar o PowerShell do Exchange Online para remover uma caixa de correio inativa de um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="668da-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="668da-183">Se o bloqueio in-loco contiver um grande número de caixas de correio de origem, é possível que a caixa de correio inativa não seja listada na página **fontes** no Eat.</span><span class="sxs-lookup"><span data-stu-id="668da-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="668da-184">Até 3.000 caixas de correio são exibidas na página **fontes** quando você edita um bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="668da-185">Se uma caixa de correio inativa não estiver listada na página **fontes** , você poderá usar o PowerShell do Exchange Online para removê-lo do bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="668da-186">Criar uma variável que contém as propriedades do bloqueio in-loco colocado na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="668da-187">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="668da-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="668da-188">Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="668da-189">**Observação:** A propriedade *sources* do bloqueio in-loco identifica as caixas de correio de origem por suas propriedades *legacyExchangeDN* .</span><span class="sxs-lookup"><span data-stu-id="668da-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="668da-190">Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *sources* do bloqueio in-loco ajuda a evitar a remoção da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="668da-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="668da-191">Isso também ajuda a evitar problemas se duas caixas de correio tiverem o mesmo alias ou endereço SMTP.</span><span class="sxs-lookup"><span data-stu-id="668da-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="668da-192">Remova a caixa de correio inativa da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="668da-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="668da-193">Certifique-se de usar o **legacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="668da-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="668da-194">Por exemplo, o comando a seguir remove a caixa de correio inativa de pilar Fernandes.</span><span class="sxs-lookup"><span data-stu-id="668da-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="668da-195">Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="668da-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="668da-196">Modificar o bloqueio in-loco com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="668da-197">Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem para o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="668da-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="668da-198">Mais informações</span><span class="sxs-lookup"><span data-stu-id="668da-198">More information</span></span>

- <span data-ttu-id="668da-199">**Uma caixa de correio inativa é um tipo de caixa de correio excluída por software.**</span><span class="sxs-lookup"><span data-stu-id="668da-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="668da-200">No Exchange Online, uma caixa de correio excluída por software é uma caixa de correio excluída, mas pode ser recuperada dentro de um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="668da-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="668da-201">O período de retenção de caixa de correio excluída de forma reversível no Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="668da-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="668da-202">Isso significa que a caixa de correio pode ser recuperada em até 30 dias após a exclusão reversível.</span><span class="sxs-lookup"><span data-stu-id="668da-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="668da-203">Após 30 dias, uma caixa de correio excluída por software é marcada para exclusão permanente e não pode ser recuperada.</span><span class="sxs-lookup"><span data-stu-id="668da-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="668da-204">**O que acontece depois que você remove o bloqueio em uma caixa de correio inativa?**</span><span class="sxs-lookup"><span data-stu-id="668da-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="668da-205">A caixa de correio é tratada como outras caixas de correio excluídas por software e é marcada para exclusão permanente após o período de retenção de caixa de correio de exclusão reversível de 30 dias expirar.</span><span class="sxs-lookup"><span data-stu-id="668da-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="668da-206">Esse período de retenção é iniciado na data em que a caixa de correio foi feita pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="668da-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="668da-207">Essa data é conhecida como a data de exclusão reversível, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="668da-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="668da-208">A data de exclusão reversível não é a data na qual você remove a retenção.</span><span class="sxs-lookup"><span data-stu-id="668da-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="668da-209">**A caixa de correio inativa é permanentemente excluída imediatamente após a removida?**</span><span class="sxs-lookup"><span data-stu-id="668da-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="668da-210">Se a data de exclusão reversível de uma caixa de correio inativa for mais antiga que 30 dias, a caixa de correio não será excluída permanentemente assim que você remover a retenção.</span><span class="sxs-lookup"><span data-stu-id="668da-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="668da-211">A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez em que for processada.</span><span class="sxs-lookup"><span data-stu-id="668da-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="668da-212">**Como o período de retenção de caixa de correio de exclusão reversível afeta caixas de correio inativas?**</span><span class="sxs-lookup"><span data-stu-id="668da-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="668da-213">Se a data de exclusão reversível de uma caixa de correio inativa for superior a 30 dias antes da data em que o bloqueio foi removido, a caixa de correio será marcada para exclusão permanente.</span><span class="sxs-lookup"><span data-stu-id="668da-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="668da-214">Mas, se uma caixa de correio inativa tiver uma data de exclusão reversível nos últimos 30 dias e você remover a retenção, você poderá recuperar a caixa de correio até que o período de retenção de caixa de correio de exclusão reversível expire.</span><span class="sxs-lookup"><span data-stu-id="668da-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="668da-215">Para obter detalhes, consulte [excluir ou restaurar caixas de correio do usuário no Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="668da-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="668da-216">Depois que o período de retenção de caixa de correio excluída por software expirar, você seguirá os procedimentos para recuperar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="668da-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="668da-217">Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="668da-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="668da-218">**Como exibir informações sobre uma caixa de correio inativa depois que a retenção for removida?**</span><span class="sxs-lookup"><span data-stu-id="668da-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="668da-219">Depois que uma retenção for removida e a caixa de correio inativa for revertida para uma caixa de correio excluída por software, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="668da-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="668da-220">Mas você pode exibir informações sobre a caixa de correio usando o comando **Get-Mailbox-SoftDeletedMailbox** .</span><span class="sxs-lookup"><span data-stu-id="668da-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="668da-221">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="668da-221">For example:</span></span> 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  <span data-ttu-id="668da-222">No exemplo acima, a propriedade *WhenSoftDeleted* identifica a data de exclusão reversível, que neste exemplo é 30 de outubro de 2014.</span><span class="sxs-lookup"><span data-stu-id="668da-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="668da-223">Se esta caixa de correio excluída por software anteriormente era uma caixa de correio inativa para a qual a retenção foi removida, ela será excluída permanentemente 30 dias após o valor da propriedade *WhenSoftDeleted* .</span><span class="sxs-lookup"><span data-stu-id="668da-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="668da-224">Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.</span><span class="sxs-lookup"><span data-stu-id="668da-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

