---
title: Excluir uma caixa de correio inativa no Office 365
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
description: Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa do Office 365, você poderá excluir permanentemente a caixa de correio inativa, removendo a isenção. Após a remoção da isenção, a caixa de correio inativa é marcada para exclusão e é excluída permanentemente após ser processada.
ms.openlocfilehash: 69628a0e3c39a0a842b2efa58c34b75c7663c728
ms.sourcegitcommit: 7646e2d742d1b2fad085a00200a2a10461dd4bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978251"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a><span data-ttu-id="ce342-104">Excluir uma caixa de correio inativa no Office 365</span><span class="sxs-lookup"><span data-stu-id="ce342-104">Delete an inactive mailbox in Office 365</span></span>

<span data-ttu-id="ce342-105">Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização.</span><span class="sxs-lookup"><span data-stu-id="ce342-105">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="ce342-106">Quando não for mais necessário preservar o conteúdo de uma caixa de correio inativa, você poderá excluir permanentemente a caixa de correio inativa, removendo a isenção.</span><span class="sxs-lookup"><span data-stu-id="ce342-106">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="ce342-107">Além disso, é possível que várias isenções possam ser colocadas em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-107">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="ce342-108">Por exemplo, uma caixa de correio inativa pode ser colocada em retenção de litígio e em uma ou mais suspensões in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-108">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="ce342-109">Além disso, uma política de retenção do Office 365 (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-109">Additionally, an Office 365 retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="ce342-110">Você deve remover todas as retenções e as políticas de retenção do Office 365 de uma caixa de correio inativa para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="ce342-110">You have to remove all holds and Office 365 retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="ce342-111">Após remover as políticas de retenção e retenção, a caixa de correio inativa é marcada para exclusão e excluída permanentemente após ser processada.</span><span class="sxs-lookup"><span data-stu-id="ce342-111">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ce342-112">Como continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce342-112">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="ce342-113">Isso significa que você deve usar as políticas de retenção de litígio e do Office 365 para criar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-113">That means you should use Litigation Holds and Office 365 retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="ce342-114">A partir de 1º de julho de 2020, você não poderá criar novos bloqueios in-loco no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ce342-114">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="ce342-115">Mas você ainda poderá alterar a duração da retenção de um bloqueio in-loco colocado em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-115">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="ce342-116">No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da retenção.</span><span class="sxs-lookup"><span data-stu-id="ce342-116">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="ce342-117">Você só poderá excluir uma caixa de correio inativa removendo o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-117">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="ce342-118">As caixas de correio inativas existentes que estão no bloqueio in-loco ainda serão preservadas até que a retenção seja removida.</span><span class="sxs-lookup"><span data-stu-id="ce342-118">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="ce342-119">Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="ce342-119">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="ce342-120">Consulte a seção [mais informações](#more-information) para obter uma descrição do que acontece depois que as retenções são removidas de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-120">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="ce342-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ce342-121">Before you begin</span></span>

- <span data-ttu-id="ce342-122">Você precisa usar o PowerShell do Exchange Online para remover uma retenção de litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-122">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="ce342-123">Você não pode usar o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="ce342-123">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="ce342-124">Para obter instruções detalhadas, consulte [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="ce342-124">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="ce342-125">Você pode usar o PowerShell do Exchange Online ou o Eat para remover um bloqueio in-loco de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-125">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="ce342-126">Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a retenção e excluir uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-126">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="ce342-127">Para obter detalhes, consulte [restaurar uma caixa de correio inativa no Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ce342-127">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ce342-128">Se você remover a política de retenção de bloqueio ou do Office 365 de uma caixa de correio inativa e o período de retenção de caixa de correio de exclusão reversível da caixa de correio tiver expirado, a caixa de correio será excluída permanentemente.</span><span class="sxs-lookup"><span data-stu-id="ce342-128">If you remove the hold or Office 365 retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="ce342-129">Depois que ele é excluído, ele não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="ce342-129">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="ce342-130">Antes de remover a retenção, certifique-se de que você não precisa mais do conteúdo na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="ce342-130">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="ce342-131">Se você quiser reativar uma caixa de correio inativa, é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="ce342-131">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="ce342-132">Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ce342-132">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ce342-133">Para obter mais informações sobre caixas de correio inativas, consulte [inativa caixas de correio no Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ce342-133">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="ce342-134">Etapa 1: identificar as isenções em uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="ce342-134">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="ce342-135">Conforme mencionado anteriormente, uma retenção de litígio, um bloqueio in-loco ou uma política de retenção do Office 365 pode ser colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-135">As previously stated, a Litigation Hold, In-Place Hold, or Office 365 retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="ce342-136">A primeira etapa é identificar as isenções em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-136">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="ce342-137">Execute o seguinte comando para exibir as informações de retenção de todas as caixas de correio inativas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ce342-137">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="ce342-138">O valor de **true** para a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="ce342-138">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="ce342-139">Se um bloqueio in-loco for colocado em uma caixa de correio inativa, o GUID da retenção será exibido como o valor da propriedade **InPlaceHolds** .</span><span class="sxs-lookup"><span data-stu-id="ce342-139">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="ce342-140">Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma retenção de litígio é colocada em Ana Beebe e que duas isenções in-loco são colocadas na Pilar Fernandes.</span><span class="sxs-lookup"><span data-stu-id="ce342-140">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="ce342-141">Se uma grande quantidade de bloqueios in-loco for colocada em uma caixa de correio inativa, nem todos os GUIDs de bloqueio in-loco serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="ce342-141">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="ce342-142">Você pode executar o seguinte comando para exibir todos os GUIDs de bloqueio in-loco:`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="ce342-142">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="ce342-143">Etapa 2: remover uma retenção de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="ce342-143">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="ce342-144">Depois de identificar o tipo de retenção que é colocado na caixa de correio inativa (e se há várias isenções), a próxima etapa é remover as isenções da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="ce342-144">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="ce342-145">Conforme mencionado anteriormente, você deve remover todas as isenções para excluir permanentemente uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-145">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="ce342-146">Remover uma retenção de litígio</span><span class="sxs-lookup"><span data-stu-id="ce342-146">Remove a Litigation Hold</span></span>

<span data-ttu-id="ce342-147">Conforme mencionado anteriormente, você precisa usar o Windows PowerShell para remover uma retenção de litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-147">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="ce342-148">Você não pode usar o Eat.</span><span class="sxs-lookup"><span data-stu-id="ce342-148">You can't use the EAC.</span></span> <span data-ttu-id="ce342-149">Execute o comando a seguir para remover uma retenção de litígio.</span><span class="sxs-lookup"><span data-stu-id="ce342-149">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="ce342-150">A melhor maneira de identificar uma caixa de correio inativa é usando seu nome distinto ou valor de GUID do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ce342-150">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="ce342-151">O uso de um desses valores ajuda a evitar a especificação acidental da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="ce342-151">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="ce342-152">Remover bloqueios in-loco</span><span class="sxs-lookup"><span data-stu-id="ce342-152">Remove In-Place Holds</span></span>

 <span data-ttu-id="ce342-153">Há duas maneiras de remover um bloqueio in-loco de uma caixa de correio inativa:</span><span class="sxs-lookup"><span data-stu-id="ce342-153">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="ce342-154">**Excluir o objeto bloqueio in-loco** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem de um bloqueio in-loco, você pode simplesmente excluir o objeto de bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-154">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="ce342-155">Você precisa desabilitar a retenção antes de excluir um objeto de bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-155">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="ce342-156">Se você tentar excluir um objeto de bloqueio in-loco com a retenção habilitada, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="ce342-156">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="ce342-157">**Remover a caixa de correio inativa como uma caixa de correio de origem de um bloqueio in-loco** Se quiser reter outras caixas de correio de origem para um bloqueio in-loco, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-157">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="ce342-158">Use o Eat para excluir um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="ce342-158">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ce342-159">Se você souber o nome do bloqueio in-loco que deseja excluir, poderá ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ce342-159">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="ce342-160">Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco que é colocado na caixa de correio inativa que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="ce342-160">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="ce342-161">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ce342-161">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="ce342-162">No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.</span><span class="sxs-lookup"><span data-stu-id="ce342-162">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ce342-163">Selecione o bloqueio in-loco que você deseja excluir e, em seguida **Edit** ![, clique em](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)editar ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="ce342-163">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ce342-164">Na página Propriedades **de retenção de &amp; descoberta eletrônica in-loco** , clique **em bloqueio in-loco**, desmarque a caixa **fazer o conteúdo que corresponde à consulta de pesquisa em caixas de correio selecionadas em retenção** e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce342-164">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="ce342-165">Na página **bloqueio de descoberta eletrônica &amp; in-loco** , selecione o bloqueio in-loco novamente e clique em **excluir**![excluir ícone](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span><span class="sxs-lookup"><span data-stu-id="ce342-165">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="ce342-166">No aviso, clique em **Sim** para excluir o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-166">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="ce342-167">Usar o PowerShell do Exchange Online para excluir um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="ce342-167">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="ce342-168">Crie uma variável que contenha as propriedades do bloqueio in-loco que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ce342-168">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="ce342-169">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ce342-169">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="ce342-170">Desabilite o bloqueio no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-170">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="ce342-171">Exclua o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-171">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ce342-172">Use o Eat para remover uma caixa de correio inativa de um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="ce342-172">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="ce342-173">Se você souber o nome do bloqueio in-loco colocado na caixa de correio inativa, poderá ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ce342-173">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="ce342-174">Caso contrário, execute o seguinte comando para obter o nome do bloqueio in-loco colocado na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="ce342-174">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="ce342-175">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ce342-175">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="ce342-176">No Eat, vá para **Gerenciamento** \> **de conformidade e descoberta eletrônica &amp; in-loco**.</span><span class="sxs-lookup"><span data-stu-id="ce342-176">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="ce342-177">Selecione o bloqueio in-loco que é colocado na caixa de correio inativa e, em **Edit** ![seguida, clique](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)em Editar ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="ce342-177">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="ce342-178">Na página Propriedades **de retenção de &amp; descoberta eletrônica in-loco** , clique em **fontes**.</span><span class="sxs-lookup"><span data-stu-id="ce342-178">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="ce342-179">Na lista de caixas de correio de origem, clique no nome da caixa de correio inativa que você deseja remover e clique em **remover**![remover](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span><span class="sxs-lookup"><span data-stu-id="ce342-179">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="ce342-180">Clique em **Salvar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="ce342-180">Click **Save** to save the change.</span></span> <span data-ttu-id="ce342-181">Uma mensagem é exibida dizendo que a operação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="ce342-181">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="ce342-182">Repita as etapas 1 a 6 para remover outros bloqueios in-loco colocados na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-182">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="ce342-183">Usar o PowerShell do Exchange Online para remover uma caixa de correio inativa de um bloqueio in-loco</span><span class="sxs-lookup"><span data-stu-id="ce342-183">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="ce342-184">Se o bloqueio in-loco contiver um grande número de caixas de correio de origem, é possível que a caixa de correio inativa não seja listada na página **fontes** no Eat.</span><span class="sxs-lookup"><span data-stu-id="ce342-184">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="ce342-185">Até 3.000 caixas de correio são exibidas na página **fontes** quando você edita um bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-185">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="ce342-186">Se uma caixa de correio inativa não estiver listada na página **fontes** , você poderá usar o PowerShell do Exchange Online para removê-lo do bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-186">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="ce342-187">Criar uma variável que contém as propriedades do bloqueio in-loco colocado na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-187">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="ce342-188">Use o GUID de bloqueio in-loco obtido na [etapa 1: identificar as isenções em uma caixa de correio inativa](#step-1-identify-the-holds-on-an-inactive-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ce342-188">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="ce342-189">Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-189">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="ce342-190">**Observação:** A propriedade *sources* do bloqueio in-loco identifica as caixas de correio de origem por suas propriedades *legacyExchangeDN* .</span><span class="sxs-lookup"><span data-stu-id="ce342-190">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="ce342-191">Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *sources* do bloqueio in-loco ajuda a evitar a remoção da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="ce342-191">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="ce342-192">Isso também ajuda a evitar problemas se duas caixas de correio tiverem o mesmo alias ou endereço SMTP.</span><span class="sxs-lookup"><span data-stu-id="ce342-192">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="ce342-193">Remova a caixa de correio inativa da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="ce342-193">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="ce342-194">Certifique-se de usar o **legacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="ce342-194">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="ce342-195">Por exemplo, o comando a seguir remove a caixa de correio inativa de pilar Fernandes.</span><span class="sxs-lookup"><span data-stu-id="ce342-195">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="ce342-196">Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="ce342-196">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="ce342-197">Modificar o bloqueio in-loco com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-197">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="ce342-198">Verifique se a caixa de correio inativa é removida da lista de caixas de correio de origem para o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="ce342-198">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="ce342-199">Mais informações</span><span class="sxs-lookup"><span data-stu-id="ce342-199">More information</span></span>

- <span data-ttu-id="ce342-200">**Uma caixa de correio inativa é um tipo de caixa de correio excluída por software.**</span><span class="sxs-lookup"><span data-stu-id="ce342-200">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="ce342-201">No Exchange Online, uma caixa de correio excluída por software é uma caixa de correio excluída, mas pode ser recuperada dentro de um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="ce342-201">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="ce342-202">O período de retenção de caixa de correio excluída de forma reversível no Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ce342-202">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="ce342-203">Isso significa que a caixa de correio pode ser recuperada em até 30 dias após a exclusão reversível.</span><span class="sxs-lookup"><span data-stu-id="ce342-203">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="ce342-204">Após 30 dias, uma caixa de correio excluída por software é marcada para exclusão permanente e não pode ser recuperada.</span><span class="sxs-lookup"><span data-stu-id="ce342-204">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="ce342-205">**O que acontece depois que você remove o bloqueio em uma caixa de correio inativa?**</span><span class="sxs-lookup"><span data-stu-id="ce342-205">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="ce342-206">A caixa de correio é tratada como outras caixas de correio excluídas por software e é marcada para exclusão permanente após o período de retenção de caixa de correio de exclusão reversível de 30 dias expirar.</span><span class="sxs-lookup"><span data-stu-id="ce342-206">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="ce342-207">Esse período de retenção é iniciado na data em que a caixa de correio foi feita pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ce342-207">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="ce342-208">Essa data é conhecida como a data de exclusão reversível, que é a data em que a conta de usuário do Office 365 correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="ce342-208">This date is known as the soft-deleted date, which is the date the corresponding Office 365 user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="ce342-209">A data de exclusão reversível não é a data na qual você remove a retenção.</span><span class="sxs-lookup"><span data-stu-id="ce342-209">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="ce342-210">**A caixa de correio inativa é permanentemente excluída imediatamente após a removida?**</span><span class="sxs-lookup"><span data-stu-id="ce342-210">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="ce342-211">Se a data de exclusão reversível de uma caixa de correio inativa for mais antiga que 30 dias, a caixa de correio não será excluída permanentemente assim que você remover a retenção.</span><span class="sxs-lookup"><span data-stu-id="ce342-211">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="ce342-212">A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez em que for processada.</span><span class="sxs-lookup"><span data-stu-id="ce342-212">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="ce342-213">**Como o período de retenção de caixa de correio de exclusão reversível afeta caixas de correio inativas?**</span><span class="sxs-lookup"><span data-stu-id="ce342-213">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="ce342-214">Se a data de exclusão reversível de uma caixa de correio inativa for superior a 30 dias antes da data em que o bloqueio foi removido, a caixa de correio será marcada para exclusão permanente.</span><span class="sxs-lookup"><span data-stu-id="ce342-214">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="ce342-215">Mas, se uma caixa de correio inativa tiver uma data de exclusão reversível nos últimos 30 dias e você remover a retenção, você poderá recuperar a caixa de correio até que o período de retenção de caixa de correio de exclusão reversível expire.</span><span class="sxs-lookup"><span data-stu-id="ce342-215">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="ce342-216">Para obter detalhes, consulte [excluir ou restaurar caixas de correio do usuário no Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span><span class="sxs-lookup"><span data-stu-id="ce342-216">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="ce342-217">Depois que o período de retenção de caixa de correio excluída por software expirar, você seguirá os procedimentos para recuperar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="ce342-217">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="ce342-218">Para obter detalhes, consulte [recuperar uma caixa de correio inativa no Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="ce342-218">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="ce342-219">**Como exibir informações sobre uma caixa de correio inativa depois que a retenção for removida?**</span><span class="sxs-lookup"><span data-stu-id="ce342-219">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="ce342-220">Depois que uma retenção for removida e a caixa de correio inativa for revertida para uma caixa de correio excluída por software, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox** .</span><span class="sxs-lookup"><span data-stu-id="ce342-220">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="ce342-221">Mas você pode exibir informações sobre a caixa de correio usando o comando **Get-Mailbox-SoftDeletedMailbox** .</span><span class="sxs-lookup"><span data-stu-id="ce342-221">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="ce342-222">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="ce342-222">For example:</span></span> 
    
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

  <span data-ttu-id="ce342-223">No exemplo acima, a propriedade *WhenSoftDeleted* identifica a data de exclusão reversível, que neste exemplo é 30 de outubro de 2014.</span><span class="sxs-lookup"><span data-stu-id="ce342-223">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="ce342-224">Se esta caixa de correio excluída por software anteriormente era uma caixa de correio inativa para a qual a retenção foi removida, ela será excluída permanentemente 30 dias após o valor da propriedade *WhenSoftDeleted* .</span><span class="sxs-lookup"><span data-stu-id="ce342-224">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="ce342-225">Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.</span><span class="sxs-lookup"><span data-stu-id="ce342-225">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

