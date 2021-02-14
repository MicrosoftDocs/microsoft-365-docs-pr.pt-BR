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
description: Quando não precisar mais preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, você poderá excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817890"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="f8741-103">Excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="f8741-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="f8741-104">Uma caixa de correio inativa é usada para preservar emails de um ex-funcionário depois que ele deixa sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8741-104">An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="f8741-105">Quando você não precisar mais preservar o conteúdo de uma caixa de correio inativa, poderá excluir permanentemente a caixa de correio inativa removendo a espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="f8741-106">Além disso, é possível que várias retém sejam colocadas em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8741-107">Por exemplo, uma caixa de correio inativa pode ser colocada em Litígio e em um ou mais In-Place Retém.</span><span class="sxs-lookup"><span data-stu-id="f8741-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="f8741-108">Além disso, uma política de retenção (criada no centro de conformidade e segurança no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="f8741-109">Você precisa remover todas as retenções e políticas de retenção de uma caixa de correio inativa para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="f8741-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="f8741-110">Depois de remover as retenções e as políticas de retenção, a caixa de correio inativa é marcada para exclusão e é excluída permanentemente depois de processada.</span><span class="sxs-lookup"><span data-stu-id="f8741-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f8741-111">À medida que continuamos investindo em maneiras diferentes de preservar o conteúdo da caixa de correio, anunciamos a ressarção do In-Place retém no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8741-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="f8741-112">Isso significa que você deve usar Retenções de Litígio e políticas de retenção para criar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="f8741-113">A partir de 1º de julho de 2020, você não poderá criar novos In-Place retém no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f8741-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="f8741-114">Mas você ainda poderá alterar a duração da espera de uma In-Place colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="f8741-115">No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="f8741-116">Você só poderá excluir uma caixa de correio inativa removendo o In-Place Remoção.</span><span class="sxs-lookup"><span data-stu-id="f8741-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="f8741-117">Caixas de correio inativas existentes que estão In-Place remoção ainda serão preservadas até que a iseção seja removida.</span><span class="sxs-lookup"><span data-stu-id="f8741-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="f8741-118">Para obter mais informações sobre a baixa In-Place, consulte a Baixa das ferramentas de [Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="f8741-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="f8741-119">Consulte a [seção Mais informações](#more-information) para obter uma descrição do que acontece após remoção de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="f8741-120">Antes de excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="f8741-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="f8741-121">Você precisa usar o PowerShell do Exchange Online para remover uma Moção de Litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8741-122">Você não pode usar o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="f8741-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="f8741-123">Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="f8741-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554).</span></span> <span data-ttu-id="f8741-124">Você pode usar o PowerShell do Exchange Online ou o EAC para remover um In-Place de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-124">You can use Exchange Online PowerShell or the EAC to remove an In-Place Hold from an inactive mailbox.</span></span> 
    
- <span data-ttu-id="f8741-125">Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a espera e excluir uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-125">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="f8741-126">Para obter detalhes, [consulte Restaurar uma caixa de correio inativa no Office 365.](restore-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f8741-126">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8741-127">Se você remover a política de retenção ou retenção de uma caixa de correio inativa e o período de retenção de caixa de correio excluída de forma flexível da caixa de correio tiver expirado, a caixa de correio será excluída permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f8741-127">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="f8741-128">Depois que ele é excluído, ele não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="f8741-128">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="f8741-129">Antes de remover a espera, certifique-se de não precisar mais do conteúdo na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="f8741-129">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="f8741-130">Se você quiser reativar uma caixa de correio inativa, poderá recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="f8741-130">If you want to re-activate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="f8741-131">Para obter detalhes, [consulte Recuperar uma caixa de correio inativa no Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f8741-131">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8741-132">Para saber mais sobre caixas de correio inativas, confira Caixas de correio [inativas no Office 365.](inactive-mailboxes-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="f8741-132">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="f8741-133">Etapa 1: Identificar os retém em uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="f8741-133">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="f8741-134">Conforme mencionado anteriormente, uma retenção de litígio, In-Place retenção ou política de retenção pode ser colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-134">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="f8741-135">A primeira etapa é identificar os retém em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-135">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="f8741-136">Execute o seguinte comando para exibir as informações de espera para todas as caixas de correio inativas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8741-136">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="f8741-137">O valor True **para** a **propriedade LitigationHoldEnabled** indica que a caixa de correio inativa está em Litígio.</span><span class="sxs-lookup"><span data-stu-id="f8741-137">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="f8741-138">Se um In-Place De espera for colocado em uma caixa de correio inativa, o GUID da iseção será exibido como o valor da **propriedade InPlaceHolds.**</span><span class="sxs-lookup"><span data-stu-id="f8741-138">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="f8741-139">Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma Responsabilidade de Litígio é colocada em Ann Beebe e que dois In-Place Reter são colocados em Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="f8741-139">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that two In-Place Holds are placed on Pilar Pinilla.</span></span> 
  
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
> <span data-ttu-id="f8741-140">Se muitos In-Place retém são colocados em uma caixa de correio inativa, nem todos os GUIDs de In-Place de espera serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="f8741-140">If a lot of In-Place Holds are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="f8741-141">Você pode executar o seguinte comando para exibir todos os GUIDs de In-Place de espera:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="f8741-141">You can run the following command to display all the In-Place Hold GUIDs:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="f8741-142">Etapa 2: Remover uma espera de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="f8741-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="f8741-143">Depois de identificar que tipo de espera é colocada na caixa de correio inativa (e se há várias retém), a próxima etapa é remover os retém na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="f8741-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="f8741-144">Conforme mencionado anteriormente, você precisa remover todas as retém para excluir permanentemente uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span> 
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="f8741-145">Remover uma moção de litígio</span><span class="sxs-lookup"><span data-stu-id="f8741-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="f8741-146">Conforme mencionado anteriormente, você precisa usar o Windows PowerShell para remover uma Moção de Litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="f8741-147">Você não pode usar o EAC.</span><span class="sxs-lookup"><span data-stu-id="f8741-147">You can't use the EAC.</span></span> <span data-ttu-id="f8741-148">Execute o seguinte comando para remover uma Moção de Litígio.</span><span class="sxs-lookup"><span data-stu-id="f8741-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="f8741-149">A melhor maneira de identificar uma caixa de correio inativa é usando o nome diferenciado ou o valor guid do Exchange.</span><span class="sxs-lookup"><span data-stu-id="f8741-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="f8741-150">Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="f8741-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-in-place-holds"></a><span data-ttu-id="f8741-151">Remover Retenções Locais</span><span class="sxs-lookup"><span data-stu-id="f8741-151">Remove In-Place Holds</span></span>

 <span data-ttu-id="f8741-152">Há duas maneiras de remover um In-Place de uma caixa de correio inativa:</span><span class="sxs-lookup"><span data-stu-id="f8741-152">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="f8741-153">**Excluir o In-Place objeto Hold** Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem para um In-Place, você pode apenas excluir o objeto In-Place De espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-153">**Delete the In-Place Hold object** If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="f8741-154">Você precisa desabilitar a espera antes de excluir um objeto In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="f8741-154">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="f8741-155">Se você tentar excluir um objeto In-Place Hold que tenha a espera habilitada, você receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f8741-155">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="f8741-156">**Remover a caixa de correio inativa como uma caixa de correio de origem de um In-Place Espera** Se quiser reter outras caixas de correio de origem para um In-Place, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto In-Place Retenção.</span><span class="sxs-lookup"><span data-stu-id="f8741-156">**Remove the inactive mailbox as a source mailbox of an In-Place Hold** If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span> 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a><span data-ttu-id="f8741-157">Usar o EAC para excluir uma In-Place Segura</span><span class="sxs-lookup"><span data-stu-id="f8741-157">Use the EAC to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8741-158">Se você sabe o nome do In-Place que deseja excluir, vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="f8741-158">If you know the name of the In-Place Hold that you want to delete, you can go to the next step.</span></span> <span data-ttu-id="f8741-159">Caso contrário, execute o seguinte comando para obter o nome do In-Place Que é colocado na caixa de correio inativa que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f8741-159">Otherwise, run the following command to get the name of the In-Place Hold that is placed on the inactive mailbox that you want to permanently delete.</span></span> <span data-ttu-id="f8741-160">Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f8741-160">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="f8741-161">No EAC, vá para **Gerenciamento de Conformidade** \> **eDiscovery Hold in-loco. &amp;**</span><span class="sxs-lookup"><span data-stu-id="f8741-161">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8741-162">Selecione o In-Place que você deseja excluir e clique em **Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ícone.</span><span class="sxs-lookup"><span data-stu-id="f8741-162">Select the In-Place Hold you want to delete, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8741-163">Na página de propriedades do **In-Place eDiscovery &amp; Hold,**  clique em **In-Place Hold**, desmarque o conteúdo Local correspondente à consulta de pesquisa em caixas de correio selecionadas em espera e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f8741-163">On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.</span></span>
    
5. <span data-ttu-id="f8741-164">Na página **In-Place eDiscovery &amp; Hold,** selecione o In-Place Recluso e clique em **Excluir** ![ ](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="f8741-164">On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>
    
6. <span data-ttu-id="f8741-165">No aviso, clique em **Sim** para excluir a In-Place Segura.</span><span class="sxs-lookup"><span data-stu-id="f8741-165">On the warning, click **Yes** to delete the In-Place Hold.</span></span> 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a><span data-ttu-id="f8741-166">Usar o PowerShell do Exchange Online para excluir uma In-Place Segura</span><span class="sxs-lookup"><span data-stu-id="f8741-166">Use Exchange Online PowerShell to delete an In-Place Hold</span></span>

1. <span data-ttu-id="f8741-167">Crie uma variável que contenha as propriedades do In-Place Hold que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="f8741-167">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="f8741-168">Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f8741-168">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="f8741-169">Desabilite a espera no In-Place Desem espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-169">Disable the hold on the In-Place Hold.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="f8741-170">Exclua a In-Place Segura.</span><span class="sxs-lookup"><span data-stu-id="f8741-170">Delete the In-Place Hold.</span></span>
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8741-171">Usar o EAC para remover uma caixa de correio inativa de um In-Place Espera</span><span class="sxs-lookup"><span data-stu-id="f8741-171">Use the EAC to remove an inactive mailbox from an In-Place Hold</span></span>

1. <span data-ttu-id="f8741-172">Se você sabe o nome do In-Place que é colocado na caixa de correio inativa, você pode ir para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="f8741-172">If you know the name of the In-Place Hold that's placed on the inactive mailbox, you can go to the next step.</span></span> <span data-ttu-id="f8741-173">Caso contrário, execute o seguinte comando para obter o nome do In-Place De espera colocado na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="f8741-173">Otherwise, run the following command to get the name of the In-Place Hold placed on the mailbox.</span></span> <span data-ttu-id="f8741-174">Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f8741-174">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. <span data-ttu-id="f8741-175">No EAC, vá para **Gerenciamento de Conformidade** \> **eDiscovery Hold in-loco. &amp;**</span><span class="sxs-lookup"><span data-stu-id="f8741-175">In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.</span></span>
    
3. <span data-ttu-id="f8741-176">Selecione o In-Place Que é colocado na caixa de correio inativa e clique em **Editar** ![ ícone ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .</span><span class="sxs-lookup"><span data-stu-id="f8741-176">Select the In-Place Hold that is placed on the inactive mailbox, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
4. <span data-ttu-id="f8741-177">Na página **de propriedades do In-Place eDiscovery &amp; Hold,** clique em **Fontes**.</span><span class="sxs-lookup"><span data-stu-id="f8741-177">On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.</span></span>
    
5. <span data-ttu-id="f8741-178">Na lista de caixas de correio de origem, clique no nome da caixa de correio inativa que você deseja remover e clique no ícone ![ Remover. ](../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="f8741-178">In the list of source mailboxes, click the name of the inactive mailbox that you want to remove, and then click **Remove**![Remove icon](../media/adf01106-cc79-475c-8673-065371c1897b.gif).</span></span>
    
6. <span data-ttu-id="f8741-179">Clique em **Salvar** para salvar a alteração.</span><span class="sxs-lookup"><span data-stu-id="f8741-179">Click **Save** to save the change.</span></span> <span data-ttu-id="f8741-180">Uma mensagem é exibida dizendo que a operação foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="f8741-180">A message is displayed saying the operation was successfully completed.</span></span> 
    
7. <span data-ttu-id="f8741-181">Repita as etapas 1 a 6 para remover In-Place Retém colocadas na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-181">Repeat steps 1 through 6 to remove other In-Place Holds placed on the inactive mailbox.</span></span>
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="f8741-182">Usar o PowerShell do Exchange Online para remover uma caixa de correio inativa de um In-Place Espera</span><span class="sxs-lookup"><span data-stu-id="f8741-182">Use Exchange Online PowerShell to remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="f8741-183">Se o In-Place de correio contiver um grande número de caixas de correio de origem, é possível que a caixa de correio inativa não seja listada na página Fontes do EAC. </span><span class="sxs-lookup"><span data-stu-id="f8741-183">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="f8741-184">Até 3.000 caixas de correio  são exibidas na página Fontes quando você edita um In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-184">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="f8741-185">Se uma caixa de correio inativa  não estiver listada na página Fontes, você poderá usar o PowerShell do Exchange Online para removê-la do In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-185">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="f8741-186">Crie uma variável que contenha as propriedades do In-Place colocado na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-186">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="f8741-187">Use a In-Place GUID de espera obtida na Etapa 1: identificar os retém em uma [caixa de correio inativa.](#step-1-identify-the-holds-on-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="f8741-187">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="f8741-188">Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-188">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   <span data-ttu-id="f8741-189">**Observação:** A *propriedade Sources* do In-Place Hold identifica as caixas de correio de origem por suas propriedades *LegacyExchangeDN.*</span><span class="sxs-lookup"><span data-stu-id="f8741-189">**Note:** The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="f8741-190">Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *Sources* do In-Place Hold ajuda a evitar a remoção da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="f8741-190">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="f8741-191">Isso também ajuda a evitar problemas se duas caixas de correio têm o mesmo alias ou endereço SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8741-191">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 
   
3. <span data-ttu-id="f8741-192">Remova a caixa de correio inativa da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="f8741-192">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="f8741-193">Certifique-se de usar **o LegacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="f8741-193">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="f8741-194">Por exemplo, o comando a seguir remove a caixa de correio inativa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="f8741-194">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="f8741-195">Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="f8741-195">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="f8741-196">Modifique o In-Place Com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-196">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="f8741-197">Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem do In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-197">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="f8741-198">Mais informações</span><span class="sxs-lookup"><span data-stu-id="f8741-198">More information</span></span>

- <span data-ttu-id="f8741-199">**Uma caixa de correio inativa é um tipo de caixa de correio excluída de forma flexível.**</span><span class="sxs-lookup"><span data-stu-id="f8741-199">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="f8741-200">No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada dentro de um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="f8741-200">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="f8741-201">O período de retenção de caixa de correio excluída de forma suave no Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="f8741-201">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="f8741-202">Isso significa que a caixa de correio pode ser recuperada dentro de 30 dias após a exclusão suave.</span><span class="sxs-lookup"><span data-stu-id="f8741-202">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="f8741-203">Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada.</span><span class="sxs-lookup"><span data-stu-id="f8741-203">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span> 
    
- <span data-ttu-id="f8741-204">**O que acontece depois que você remove a espera em uma caixa de correio inativa?**</span><span class="sxs-lookup"><span data-stu-id="f8741-204">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="f8741-205">A caixa de correio é tratada como outras caixas de correio excluídas de forma suave e é marcada para exclusão permanente após o período de retenção de caixa de correio excluída por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="f8741-205">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8741-206">Esse período de retenção começa na data em que a caixa de correio foi inativa pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f8741-206">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="f8741-207">Essa data é conhecida como a data de exclusão suave, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="f8741-207">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8741-208">A data de exclusão suave não é a data em que você remove a espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-208">The soft-deleted date isn't the date on which you remove the hold.</span></span> 
    
- <span data-ttu-id="f8741-209">**Uma caixa de correio inativa é excluída permanentemente imediatamente após a remoção da espera?**</span><span class="sxs-lookup"><span data-stu-id="f8741-209">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="f8741-210">Se a data de exclusão flexível de uma caixa de correio inativa tiver mais de 30 dias, ela não será excluída permanentemente assim que você remover a espera.</span><span class="sxs-lookup"><span data-stu-id="f8741-210">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="f8741-211">A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez que for processada.</span><span class="sxs-lookup"><span data-stu-id="f8741-211">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span> 
    
- <span data-ttu-id="f8741-212">**Como o período de retenção de caixa de correio excluída de forma flexível afeta as caixas de correio inativas?**</span><span class="sxs-lookup"><span data-stu-id="f8741-212">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="f8741-213">Se a data de exclusão flexível de uma caixa de correio inativa for superior a 30 dias antes da data em que o espera foi removido, a caixa de correio será marcada para exclusão permanente.</span><span class="sxs-lookup"><span data-stu-id="f8741-213">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="f8741-214">Mas se uma caixa de correio inativa tiver uma data de exclusão flexível nos últimos 30 dias e você remover a retenção, poderá recuperar a caixa de correio até que o período de retenção da caixa de correio excluída de forma flexível expire.</span><span class="sxs-lookup"><span data-stu-id="f8741-214">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="f8741-215">Para obter detalhes, consulte [Excluir ou restaurar caixas de correio do usuário no Exchange Online.](https://go.microsoft.com/fwlink/?linkid=856835)</span><span class="sxs-lookup"><span data-stu-id="f8741-215">For details, see [Delete or restore user mailboxes in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856835).</span></span> <span data-ttu-id="f8741-216">Depois que o período de retenção de caixa de correio excluída de forma flexível expirar, você seguirá os procedimentos para recuperar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="f8741-216">After the soft-deleted mailbox retention period expires, you have follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="f8741-217">Para obter detalhes, [consulte Recuperar uma caixa de correio inativa no Office 365.](recover-an-inactive-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="f8741-217">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>
    
- <span data-ttu-id="f8741-218">**Como exibir informações sobre uma caixa de correio inativa após a remoção da espera?**</span><span class="sxs-lookup"><span data-stu-id="f8741-218">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="f8741-219">Depois que uma espera é removida e a caixa de correio inativa é revertida de volta para uma caixa de correio excluída de forma reversida, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="f8741-219">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="f8741-220">Mas você pode exibir informações sobre a caixa de correio usando o **comando Get-Mailbox -SoftDeletedMailbox.**</span><span class="sxs-lookup"><span data-stu-id="f8741-220">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="f8741-221">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f8741-221">For example:</span></span> 
    
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

  <span data-ttu-id="f8741-222">No exemplo acima, a propriedade *WhenSoftDeleted* identifica a data de exclusão suave, que neste exemplo é 30 de outubro de 2014.</span><span class="sxs-lookup"><span data-stu-id="f8741-222">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="f8741-223">Se essa caixa de correio excluída por software anteriormente era uma caixa de correio inativa para a qual a espera foi removida, ela será excluída permanentemente 30 dias após o valor da propriedade *WhenSoftDeleted.*</span><span class="sxs-lookup"><span data-stu-id="f8741-223">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="f8741-224">Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.</span><span class="sxs-lookup"><span data-stu-id="f8741-224">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>

