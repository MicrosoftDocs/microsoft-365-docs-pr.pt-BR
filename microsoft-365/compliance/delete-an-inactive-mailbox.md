---
title: Excluir uma caixa de correio inativa
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
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Quando você não precisa mais preservar o conteúdo de uma caixa de correio inativa do Microsoft 365, você pode excluir permanentemente a caixa de correio inativa.
ms.openlocfilehash: 94a20bee1ca3d11a193a25efeb6d73f356e1d58d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909921"
---
# <a name="delete-an-inactive-mailbox"></a><span data-ttu-id="5a813-103">Excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="5a813-103">Delete an inactive mailbox</span></span>

<span data-ttu-id="5a813-104">Uma caixa de correio inativa é usada para preservar o email de um ex-funcionário após sair da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5a813-104">An inactive mailbox is used to preserve a former employee's email after they leave your organization.</span></span> <span data-ttu-id="5a813-105">Quando você não precisa mais preservar o conteúdo de uma caixa de correio inativa, você pode excluir permanentemente a caixa de correio inativa removendo a espera.</span><span class="sxs-lookup"><span data-stu-id="5a813-105">When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold.</span></span> <span data-ttu-id="5a813-106">Além disso, é possível que vários retém possam ser colocados em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-106">Also, it's possible that multiple holds might be placed on an inactive mailbox.</span></span> <span data-ttu-id="5a813-107">Por exemplo, uma caixa de correio inativa pode ser colocada em Contencioso e em um ou mais In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="5a813-107">For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds.</span></span> <span data-ttu-id="5a813-108">Além disso, uma política de retenção (criada no centro de segurança e conformidade no Office 365 ou no Microsoft 365) pode ser aplicada à caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-108">Additionally, a retention policy (created in the security and compliance center in Office 365 or Microsoft 365) might be applied to the inactive mailbox.</span></span> <span data-ttu-id="5a813-109">Você precisa remover todas as políticas de retenção e retenção de uma caixa de correio inativa para excluí-la.</span><span class="sxs-lookup"><span data-stu-id="5a813-109">You have to remove all holds and retention policies from an inactive mailbox to delete it.</span></span> <span data-ttu-id="5a813-110">Depois de remover as políticas de retenção e retenção, a caixa de correio inativa será marcada para exclusão e será excluída permanentemente depois de processada.</span><span class="sxs-lookup"><span data-stu-id="5a813-110">After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5a813-111">À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ress contração de In-Place no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5a813-111">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center.</span></span> <span data-ttu-id="5a813-112">Isso significa que você deve usar as Políticas de Retenção e Retenção de Litígio para criar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-112">That means you should use Litigation Holds and retention policies to create an inactive mailbox.</span></span> <span data-ttu-id="5a813-113">A partir de 1º de julho de 2020, você não poderá criar novos In-Place no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5a813-113">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="5a813-114">Mas você ainda poderá alterar a duração de espera de uma In-Place de espera colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-114">But you'll still be able to change the hold duration of an In-Place Hold placed on an inactive mailbox.</span></span> <span data-ttu-id="5a813-115">No entanto, a partir de 1º de outubro de 2020, você não poderá alterar a duração da espera.</span><span class="sxs-lookup"><span data-stu-id="5a813-115">However, starting October 1, 2020, you won't be able to change the hold duration.</span></span> <span data-ttu-id="5a813-116">Você só poderá excluir uma caixa de correio inativa removendo o In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-116">You'll only be able to delete an inactive mailbox by removing the In-Place Hold.</span></span> <span data-ttu-id="5a813-117">As caixas de correio inativas existentes que estão em In-Place de espera ainda serão preservadas até que a espera seja removida.</span><span class="sxs-lookup"><span data-stu-id="5a813-117">Existing inactive mailboxes that are on In-Place Hold will still be preserved until the hold is removed.</span></span> <span data-ttu-id="5a813-118">Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="5a813-118">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="5a813-119">Consulte a [seção Mais informações](#more-information) para obter uma descrição do que acontece após a remoção de retém de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-119">See the [More information](#more-information) section for a description of what happens after holds are removed from an inactive mailbox.</span></span>
  
## <a name="before-you-delete-an-inactive-mailbox"></a><span data-ttu-id="5a813-120">Antes de excluir uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="5a813-120">Before you delete an inactive mailbox</span></span>

- <span data-ttu-id="5a813-121">Você precisa usar o PowerShell do Exchange Online para remover uma Moção de Litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-121">You have to use Exchange Online PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="5a813-122">Você não pode usar o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="5a813-122">You can't use the Exchange admin center (EAC).</span></span> <span data-ttu-id="5a813-123">Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5a813-123">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5a813-124">Você pode copiar o conteúdo de uma caixa de correio inativa para outra caixa de correio antes de remover a espera e excluir uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-124">You can copy the contents of an inactive mailbox to another mailbox before you remove the hold and delete an inactive mailbox.</span></span> <span data-ttu-id="5a813-125">Para obter detalhes, [consulte Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="5a813-125">For details, see [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="5a813-126">Se você remover a política de retenção ou retenção de uma caixa de correio inativa e o período de retenção de caixa de correio excluída pela caixa de correio tiver expirado, a caixa de correio será excluída permanentemente.</span><span class="sxs-lookup"><span data-stu-id="5a813-126">If you remove the hold or retention policy from an inactive mailbox and the soft-deleted mailbox retention period for the mailbox has expired, the mailbox will be permanently deleted.</span></span> <span data-ttu-id="5a813-127">Depois que ele é excluído, ele não pode ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="5a813-127">After it's deleted, it can't be recovered.</span></span> <span data-ttu-id="5a813-128">Antes de remover a espera, certifique-se de não precisar mais do conteúdo na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="5a813-128">Before you remove the hold, be sure that you no longer need the contents in the mailbox.</span></span> <span data-ttu-id="5a813-129">Se você quiser reativar uma caixa de correio inativa, poderá recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="5a813-129">If you want to reactivate an inactive mailbox, you can recover it.</span></span> <span data-ttu-id="5a813-130">Para obter detalhes, [consulte Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="5a813-130">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="5a813-131">Para obter mais informações sobre caixas de correio inativas, consulte Caixas de correio [inativas no Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="5a813-131">For more information about inactive mailboxes, see [Inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a><span data-ttu-id="5a813-132">Etapa 1: identificar os retém em uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="5a813-132">Step 1: Identify the holds on an inactive mailbox</span></span>

<span data-ttu-id="5a813-133">Como mencionado anteriormente, uma retenção de litígio, In-Place retenção ou política de retenção pode ser colocada em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-133">As previously stated, a Litigation Hold, In-Place Hold, or retention policy might be placed on an inactive mailbox.</span></span> <span data-ttu-id="5a813-134">A primeira etapa é identificar os retém em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-134">The first step is to identify the holds on an inactive mailbox.</span></span>
  
<span data-ttu-id="5a813-135">Execute o seguinte comando para exibir as informações de espera de todas as caixas de correio inativas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5a813-135">Run the following command to display the hold information for all inactive mailboxes in your organization.</span></span>
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

<span data-ttu-id="5a813-136">O valor **true para** a propriedade **LitigationHoldEnabled** indica que a caixa de correio inativa está em Contencioso.</span><span class="sxs-lookup"><span data-stu-id="5a813-136">The value of **True** for the **LitigationHoldEnabled** property indicates that the inactive mailbox is on Litigation Hold.</span></span> <span data-ttu-id="5a813-137">Se um In-Place de espera for colocado em uma caixa de correio inativa, o GUID da responsabilidade será exibido como o valor da **propriedade InPlaceHolds.**</span><span class="sxs-lookup"><span data-stu-id="5a813-137">If an In-Place Hold is placed on an inactive mailbox, the GUID for the hold is displayed as the value for the **InPlaceHolds** property.</span></span> <span data-ttu-id="5a813-138">Por exemplo, os resultados a seguir para duas caixas de correio inativas mostram que uma Retenção de Litígio é colocada em Ann Beebe e que uma política de retenção e retenção de In-Place é colocada em Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="5a813-138">For example, the following results for two inactive mailboxes show that a Litigation Hold is placed on Ann Beebe and that an In-Place Hold and retention policy are placed on Pilar Pinilla.</span></span>
  
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
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, mbxba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> <span data-ttu-id="5a813-139">Se muitas In-Place de retenção ou retenção são colocadas em uma caixa de correio inativa, nem todos os GUIDs de retenção In-Place serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="5a813-139">If a lot of In-Place Holds or retention policies are placed on an inactive mailbox, not all of the In-Place Hold GUIDs will be displayed.</span></span> <span data-ttu-id="5a813-140">Você pode executar o seguinte comando para exibir todos os GUIDs na propriedade InPlaceHolds:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span><span class="sxs-lookup"><span data-stu-id="5a813-140">You can run the following command to display all the GUIDs in the InPlaceHolds property:  `Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`</span></span>
  
<span data-ttu-id="5a813-141">Para obter mais informações sobre como identificar retém, consulte Como identificar o tipo [de espera colocada em uma caixa de correio](identify-a-hold-on-an-exchange-online-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="5a813-141">For more information about identify holds, see [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md).</span></span>

## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a><span data-ttu-id="5a813-142">Etapa 2: Remover uma espera de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="5a813-142">Step 2: Remove a hold from an inactive mailbox</span></span>

<span data-ttu-id="5a813-143">Depois de identificar qual tipo de espera é colocada na caixa de correio inativa (e se há várias restituições), a próxima etapa é remover as resituções na caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="5a813-143">After you identify what type of hold is placed on the inactive mailbox (and whether there are multiple holds), the next step is to remove the holds on the mailbox.</span></span> <span data-ttu-id="5a813-144">Conforme mencionado anteriormente, você precisa remover todas as resvases para excluir permanentemente uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-144">As previously stated, you have to remove all holds to permanently delete an inactive mailbox.</span></span>
  
### <a name="remove-a-litigation-hold"></a><span data-ttu-id="5a813-145">Remover uma moção de litígio</span><span class="sxs-lookup"><span data-stu-id="5a813-145">Remove a Litigation Hold</span></span>

<span data-ttu-id="5a813-146">Como mencionado anteriormente, você precisa usar Windows PowerShell remover uma Moção de Litígio de uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-146">As previously stated, you have to use Windows PowerShell to remove a Litigation Hold from an inactive mailbox.</span></span> <span data-ttu-id="5a813-147">Não é possível usar o EAC.</span><span class="sxs-lookup"><span data-stu-id="5a813-147">You can't use the EAC.</span></span> <span data-ttu-id="5a813-148">Execute o seguinte comando para remover uma Moção de Litígio.</span><span class="sxs-lookup"><span data-stu-id="5a813-148">Run the following command to remove a Litigation Hold.</span></span>
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> <span data-ttu-id="5a813-149">A melhor maneira de identificar uma caixa de correio inativa é usando seu valor Distinguished Name ou GUID do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5a813-149">The best way to identify an inactive mailbox is by using its Distinguished Name or Exchange GUID value.</span></span> <span data-ttu-id="5a813-150">Usar um desses valores ajuda a evitar a especificação acidental da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="5a813-150">Using one of these values helps prevent accidentally specifying the wrong mailbox.</span></span> 
  
### <a name="remove-an-inactive-mailbox-from-a-retention-policy"></a><span data-ttu-id="5a813-151">Remover uma caixa de correio inativa de uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="5a813-151">Remove an inactive mailbox from a retention policy</span></span>

<span data-ttu-id="5a813-152">O procedimento para remover uma caixa de correio inativa de uma política de retenção do Microsoft 365 depende se a política de retenção atribuída à caixa de correio inativa é de toda a organização ou explícita.</span><span class="sxs-lookup"><span data-stu-id="5a813-152">The procedure to remove an inactive mailbox from a Microsoft 365 retention policy depends whether the retention policy assigned to the inactive mailbox is organization-wide or explicit.</span></span> <span data-ttu-id="5a813-153">no tipo de política de retenção atribuída à caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-153">on the type of retention policy that's assigned to the inactive mailbox.</span></span>

- <span data-ttu-id="5a813-154">Políticas de retenção em toda a organização atribuídas a todas as caixas de correio na organização.</span><span class="sxs-lookup"><span data-stu-id="5a813-154">Organization-wide retention policies assigned to all mailboxes in the organization.</span></span> <span data-ttu-id="5a813-155">Use o cmdlet **Get-OrganizationConfig** no PowerShell do Exchange Online para obter informações sobre políticas de retenção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="5a813-155">Use the **Get-OrganizationConfig** cmdlet in Exchange Online PowerShell to get information about organization-wide retention policies.</span></span>

- <span data-ttu-id="5a813-156">Políticas de retenção de localização específicas atribuídas a caixas de correio específicas.</span><span class="sxs-lookup"><span data-stu-id="5a813-156">Specific location retention policies assigned to specific mailboxes.</span></span> <span data-ttu-id="5a813-157">São políticas atribuídas aos locais de conteúdo de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="5a813-157">These are policies that are assigned to the content locations of specific users.</span></span> <span data-ttu-id="5a813-158">Use o cmdlet **Get-Mailbox -IncludeInactiveMailbox** no PowerShell do Exchange Online para obter informações sobre políticas de retenção atribuídas a caixas de correio inativas específicas.</span><span class="sxs-lookup"><span data-stu-id="5a813-158">Use the **Get-Mailbox -IncludeInactiveMailbox** cmdlet in Exchange Online PowerShell to get information about retention policies assigned to specific inactive mailboxes.</span></span>

#### <a name="remove-an-inactive-mailbox-from-an-organization-wide-retention-policy"></a><span data-ttu-id="5a813-159">Remover uma caixa de correio inativa de uma política de retenção em toda a organização</span><span class="sxs-lookup"><span data-stu-id="5a813-159">Remove an inactive mailbox from an organization-wide retention policy</span></span>

<span data-ttu-id="5a813-160">Execute o seguinte comando no PowerShell do Exchange Online para excluir uma caixa de correio inativa de uma política de retenção em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="5a813-160">Run the following command in Exchange Online PowerShell to exclude an inactive mailbox from an organization-wide retention policy.</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromOrgHolds <retention policy GUID without prefix or suffix>
```

<span data-ttu-id="5a813-161">Para obter mais informações que identifiquem políticas de retenção em toda a organização aplicadas a uma caixa de correio inativa e obtenham o GUID de uma política de retenção, consulte [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig)seção "Get-OrganizationConfig" em Como identificar o tipo de retenção colocado em uma caixa de correio .</span><span class="sxs-lookup"><span data-stu-id="5a813-161">For more information identifying organization-wide retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-OrganizationConfig" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-organizationconfig).</span></span>

<span data-ttu-id="5a813-162">Como alternativa, você pode executar o seguinte comando para remover a caixa de correio inativa de todas as políticas de toda a organização:</span><span class="sxs-lookup"><span data-stu-id="5a813-162">Alternatively, you can run the following command to remove the inactive mailbox from all organization-wide policies:</span></span>

```powershell
Set-Mailbox <identity of inactive mailbox> -ExcludeFromAllOrgHolds
```

#### <a name="remove-an-inactive-mailbox-from-a-specific-location-retention-policy"></a><span data-ttu-id="5a813-163">Remover uma caixa de correio inativa de uma política de retenção de local específica</span><span class="sxs-lookup"><span data-stu-id="5a813-163">Remove an inactive mailbox from a specific location retention policy</span></span>

<span data-ttu-id="5a813-164">Execute o seguinte comando no Centro de Conformidade & Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) para remover uma caixa de correio inativa de uma política de retenção explícita.</span><span class="sxs-lookup"><span data-stu-id="5a813-164">Run the following command in [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) to remove an inactive mailbox from an explicit retention policy.</span></span>

```powershell
Set-RetentionCompliancePolicy -Identity <retention policy GUID without prefix or suffix> -AddExchangeLocationException <identity of inactive mailbox>
```

<span data-ttu-id="5a813-165">Para obter mais informações sobre como identificar políticas de retenção de local específicas aplicadas a uma caixa de correio inativa e obter o GUID de uma política de retenção, consulte [a](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox)seção "Get-Mailbox" em Como identificar o tipo de retenção colocada em uma caixa de correio .</span><span class="sxs-lookup"><span data-stu-id="5a813-165">For more information identifying specific location retention policies applied to an inactive mailbox and obtaining the GUID for a retention policy, see the "Get-Mailbox" section in [How to identify the type of hold placed on a mailbox](identify-a-hold-on-an-exchange-online-mailbox.md#get-mailbox).</span></span>

### <a name="remove-in-place-holds"></a><span data-ttu-id="5a813-166">Remover Retenções Locais</span><span class="sxs-lookup"><span data-stu-id="5a813-166">Remove In-Place Holds</span></span>

 <span data-ttu-id="5a813-167">Há duas maneiras de remover um In-Place de uma caixa de correio inativa:</span><span class="sxs-lookup"><span data-stu-id="5a813-167">There are two ways to remove an In-Place Hold from an inactive mailbox:</span></span> 
  
- <span data-ttu-id="5a813-168">**Exclua o In-Place objeto Hold**.</span><span class="sxs-lookup"><span data-stu-id="5a813-168">**Delete the In-Place Hold object**.</span></span> <span data-ttu-id="5a813-169">Se a caixa de correio inativa que você deseja excluir permanentemente for a única caixa de correio de origem para um In-Place de espera, você pode apenas excluir o objeto In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-169">If the inactive mailbox that you want to permanently delete is the only source mailbox for an In-Place Hold, you can just delete the In-Place Hold object.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5a813-170">Você precisa desabilitar a espera antes de poder excluir um objeto In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-170">You have to disable the hold before you can delete an In-Place Hold object.</span></span> <span data-ttu-id="5a813-171">Se você tentar excluir um objeto In-Place Hold que tenha a espera habilitada, receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="5a813-171">If you try to delete an In-Place Hold object that has the hold enabled, you'll receive an error message.</span></span> 
  
- <span data-ttu-id="5a813-172">**Remova a caixa de correio inativa como uma caixa de** correio de origem de um In-Place Hold .</span><span class="sxs-lookup"><span data-stu-id="5a813-172">**Remove the inactive mailbox as a source mailbox of an In-Place Hold**.</span></span> <span data-ttu-id="5a813-173">Se você quiser reter outras caixas de correio de origem para um In-Place, você pode remover a caixa de correio inativa da lista de caixas de correio de origem e manter o objeto In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-173">If you want to retain other source mailboxes for an In-Place Hold, you can remove the inactive mailbox from the list of source mailboxes and keep the In-Place Hold object.</span></span>

#### <a name="delete-an-in-place-hold"></a><span data-ttu-id="5a813-174">Excluir um In-Place de espera</span><span class="sxs-lookup"><span data-stu-id="5a813-174">Delete an In-Place Hold</span></span>

1. <span data-ttu-id="5a813-175">Crie uma variável que contenha as propriedades do In-Place que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="5a813-175">Create a variable that contains the properties of the In-Place Hold that you want to delete.</span></span> <span data-ttu-id="5a813-176">Use o GUID In-Place de espera que você obteve na [Etapa 1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identificar os retém em uma caixa de correio inativa .</span><span class="sxs-lookup"><span data-stu-id="5a813-176">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. <span data-ttu-id="5a813-177">Desabilite a espera no In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-177">Disable the hold on the In-Place Hold.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. <span data-ttu-id="5a813-178">Exclua o In-Place de espera.</span><span class="sxs-lookup"><span data-stu-id="5a813-178">Delete the In-Place Hold.</span></span>

   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="remove-an-inactive-mailbox-from-an-in-place-hold"></a><span data-ttu-id="5a813-179">Remover uma caixa de correio inativa de um In-Place Hold</span><span class="sxs-lookup"><span data-stu-id="5a813-179">Remove an inactive mailbox from an In-Place Hold</span></span>

<span data-ttu-id="5a813-180">Se o In-Place hold contiver um grande número de caixas de correio de origem,  é possível que a caixa de correio inativa não seja listada na página Fontes no EAC.</span><span class="sxs-lookup"><span data-stu-id="5a813-180">If the In-Place Hold contains a large number of source mailboxes, it's possible the inactive mailbox won't be listed on the **Sources** page in the EAC.</span></span> <span data-ttu-id="5a813-181">Até 3.000 caixas de correio  são exibidas na página Fontes quando você edita um In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-181">Up to 3,000 mailboxes are displayed on the **Sources** page when you edit an In-Place Hold.</span></span> <span data-ttu-id="5a813-182">Se uma caixa de correio inativa  não estiver listada na página Fontes, você poderá usar o PowerShell do Exchange Online para removê-la do In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-182">If an inactive mailbox isn't listed on the **Sources** page, you can use Exchange Online PowerShell to remove it from the In-Place Hold.</span></span> 
  
1. <span data-ttu-id="5a813-183">Crie uma variável que contenha as propriedades do In-Place hold colocado na caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-183">Create a variable that contains the properties of the In-Place Hold placed on the inactive mailbox.</span></span> <span data-ttu-id="5a813-184">Use o GUID In-Place de espera que você obteve na [Etapa 1:](#step-1-identify-the-holds-on-an-inactive-mailbox)Identificar os retém em uma caixa de correio inativa .</span><span class="sxs-lookup"><span data-stu-id="5a813-184">Use the In-Place Hold GUID that you obtained in [Step 1: Identify the holds on an inactive mailbox](#step-1-identify-the-holds-on-an-inactive-mailbox).</span></span>

    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. <span data-ttu-id="5a813-185">Verifique se a caixa de correio inativa está listada como uma caixa de correio de origem para o In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-185">Verify that the inactive mailbox is listed as a source mailbox for the In-Place Hold.</span></span> 

   ```powershell
   $InPlaceHold.Sources
   ```

   > [!NOTE]
   > <span data-ttu-id="5a813-186">A *propriedade Sources* do In-Place Hold identifica as caixas de correio de origem por suas propriedades *LegacyExchangeDN.*</span><span class="sxs-lookup"><span data-stu-id="5a813-186">The *Sources* property of the In-Place Hold identifies the source mailboxes by their *LegacyExchangeDN* properties.</span></span> <span data-ttu-id="5a813-187">Como essa propriedade identifica exclusivamente caixas de correio inativas, o uso da propriedade *Sources* do In-Place Hold ajuda a evitar a remoção da caixa de correio errada.</span><span class="sxs-lookup"><span data-stu-id="5a813-187">Because this property uniquely identifies inactive mailboxes, using the *Sources* property from the In-Place Hold helps prevent removing the wrong mailbox.</span></span> <span data-ttu-id="5a813-188">Isso também ajuda a evitar problemas se duas caixas de correio têm o mesmo alias ou endereço SMTP.</span><span class="sxs-lookup"><span data-stu-id="5a813-188">This also helps to avoid issues if two mailboxes have the same alias or SMTP address.</span></span> 

3. <span data-ttu-id="5a813-189">Remova a caixa de correio inativa da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="5a813-189">Remove the inactive mailbox from the list of source mailboxes in the variable.</span></span> <span data-ttu-id="5a813-190">Use o **LegacyExchangeDN** da caixa de correio inativa retornada pelo comando na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="5a813-190">Be sure to use the **LegacyExchangeDN** of the inactive mailbox that's returned by the command in the previous step.</span></span> 

    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    <span data-ttu-id="5a813-191">Por exemplo, o comando a seguir remove a caixa de correio inativa de Pilar Pinilla.</span><span class="sxs-lookup"><span data-stu-id="5a813-191">For example, the following command removes the inactive mailbox for Pilar Pinilla.</span></span>

    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. <span data-ttu-id="5a813-192">Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem na variável.</span><span class="sxs-lookup"><span data-stu-id="5a813-192">Verify that the inactive mailbox is removed from the list of source mailboxes in the variable.</span></span>

   ```powershell
   $InPlaceHold.Sources
   ```

5. <span data-ttu-id="5a813-193">Modifique o In-Place com a lista atualizada de caixas de correio de origem, que não inclui a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-193">Modify the In-Place Hold with the updated list of source mailboxes, which doesn't include the inactive mailbox.</span></span>

   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. <span data-ttu-id="5a813-194">Verifique se a caixa de correio inativa foi removida da lista de caixas de correio de origem do In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="5a813-194">Verify that the inactive mailbox is removed from the list of source mailboxes for the In-Place Hold.</span></span>

   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a><span data-ttu-id="5a813-195">Mais informações</span><span class="sxs-lookup"><span data-stu-id="5a813-195">More information</span></span>

- <span data-ttu-id="5a813-196">**Uma caixa de correio inativa é um tipo de caixa de correio excluída de forma suave.**</span><span class="sxs-lookup"><span data-stu-id="5a813-196">**An inactive mailbox is a type of soft-deleted mailbox.**</span></span> <span data-ttu-id="5a813-197">No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada em um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="5a813-197">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="5a813-198">O período de retenção de caixa de correio excluído no Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="5a813-198">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="5a813-199">Isso significa que a caixa de correio pode ser recuperada dentro de 30 dias após a exclusão suave.</span><span class="sxs-lookup"><span data-stu-id="5a813-199">This means that the mailbox can be recovered within 30 days of being soft-deleted.</span></span> <span data-ttu-id="5a813-200">Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada.</span><span class="sxs-lookup"><span data-stu-id="5a813-200">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered.</span></span>

- <span data-ttu-id="5a813-201">**O que acontece depois de remover a espera em uma caixa de correio inativa?**</span><span class="sxs-lookup"><span data-stu-id="5a813-201">**What happens after you remove the hold on an inactive mailbox?**</span></span> <span data-ttu-id="5a813-202">A caixa de correio é tratada como outras caixas de correio excluídas de forma suave e é marcada para exclusão permanente após o período de retenção de caixa de correio excluído por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="5a813-202">The mailbox is treated like other soft-deleted mailboxes and is marked for permanent deletion after the 30-day soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="5a813-203">Esse período de retenção começa na data em que a caixa de correio foi inativa pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="5a813-203">This retention period starts on the date when the mailbox was first made inactive.</span></span> <span data-ttu-id="5a813-204">Essa data é conhecida como a data excluída de forma suave, que é a data em que a conta de usuário correspondente foi excluída ou quando a caixa de correio do Exchange Online foi excluída com o cmdlet **Remove-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="5a813-204">This date is known as the soft-deleted date, which is the date the corresponding user account was deleted or when the Exchange Online mailbox was deleted with the **Remove-Mailbox** cmdlet.</span></span> <span data-ttu-id="5a813-205">A data excluída de forma suave não é a data em que você remove a espera.</span><span class="sxs-lookup"><span data-stu-id="5a813-205">The soft-deleted date isn't the date on which you remove the hold.</span></span>

- <span data-ttu-id="5a813-206">**Uma caixa de correio inativa será excluída permanentemente imediatamente após a remoção da moção?**</span><span class="sxs-lookup"><span data-stu-id="5a813-206">**Is an inactive mailbox permanently deleted immediately after the hold is removed?**</span></span> <span data-ttu-id="5a813-207">Se a data de exclusão suave de uma caixa de correio inativa tiver mais de 30 dias, a caixa de correio não será excluída permanentemente assim que você remover a responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="5a813-207">If the soft-deleted date for an inactive mailbox is older than 30 days, the mailbox won't be permanently deleted as soon as you remove the hold.</span></span> <span data-ttu-id="5a813-208">A caixa de correio será marcada para exclusão permanente e será excluída na próxima vez que for processada.</span><span class="sxs-lookup"><span data-stu-id="5a813-208">The mailbox will be marked for permanent deletion and is deleted the next time it's processed.</span></span>

- <span data-ttu-id="5a813-209">**Como o período de retenção de caixa de correio excluído suave afeta caixas de correio inativas?**</span><span class="sxs-lookup"><span data-stu-id="5a813-209">**How does the soft-deleted mailbox retention period affect inactive mailboxes?**</span></span> <span data-ttu-id="5a813-210">Se a data de exclusão suave de uma caixa de correio inativa for superior a 30 dias antes da data em que a remoção foi removida, a caixa de correio será marcada para exclusão permanente.</span><span class="sxs-lookup"><span data-stu-id="5a813-210">If the soft-deleted date for an inactive mailbox is more than 30 days before the date the hold was removed, the mailbox is marked for permanent deletion.</span></span> <span data-ttu-id="5a813-211">Porém, se uma caixa de correio inativa tiver uma data excluída nos últimos 30 dias e você remover a retenção, poderá recuperar a caixa de correio até que o período de retenção de caixa de correio excluído de forma suave expire.</span><span class="sxs-lookup"><span data-stu-id="5a813-211">But if an inactive mailbox has a soft-deleted date within the last 30 days and you remove the hold, you can recover the mailbox up until the soft-deleted mailbox retention period expires.</span></span> <span data-ttu-id="5a813-212">Para obter detalhes, consulte [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span><span class="sxs-lookup"><span data-stu-id="5a813-212">For details, see [Delete or restore user mailboxes in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes).</span></span> <span data-ttu-id="5a813-213">Depois que o período de retenção de caixa de correio excluídos de forma suave expirar, você deve seguir os procedimentos para recuperar uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="5a813-213">After the soft-deleted mailbox retention period expires, you have to follow the procedures for recovering an inactive mailbox.</span></span> <span data-ttu-id="5a813-214">Para obter detalhes, [consulte Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="5a813-214">For details, see [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).</span></span>

- <span data-ttu-id="5a813-215">**Como você exibe informações sobre uma caixa de correio inativa após a remoção da moção?**</span><span class="sxs-lookup"><span data-stu-id="5a813-215">**How do you display information about an inactive mailbox after the hold is removed?**</span></span> <span data-ttu-id="5a813-216">Depois que uma espera é removida e a caixa de correio inativa é revertida de volta para uma caixa de correio excluída de forma suave, ela não será retornada usando o parâmetro *InactiveMailboxOnly* com o cmdlet **Get-Mailbox.**</span><span class="sxs-lookup"><span data-stu-id="5a813-216">After a hold is removed and the inactive mailbox is reverted back to a soft-deleted mailbox, it won't be returned by using the  *InactiveMailboxOnly*  parameter with the **Get-Mailbox** cmdlet.</span></span> <span data-ttu-id="5a813-217">Mas você pode exibir informações sobre a caixa de correio usando o **comando Get-Mailbox -SoftDeletedMailbox.**</span><span class="sxs-lookup"><span data-stu-id="5a813-217">But you can display information about the mailbox by using the **Get-Mailbox -SoftDeletedMailbox** command.</span></span> <span data-ttu-id="5a813-218">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a813-218">For example:</span></span>

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

  <span data-ttu-id="5a813-219">No exemplo acima, a *propriedade WhenSoftDeleted* identifica a data excluída de forma suave, que neste exemplo é 30 de outubro de 2014.</span><span class="sxs-lookup"><span data-stu-id="5a813-219">In the above example, the *WhenSoftDeleted* property identifies the soft-deleted date, which in this example is October 30, 2014.</span></span> <span data-ttu-id="5a813-220">Se essa caixa de correio excluída suave anteriormente fosse uma caixa de correio inativa para a qual a responsabilidade foi removida, ela será excluída permanentemente 30 dias após o valor da *propriedade WhenSoftDeleted.*</span><span class="sxs-lookup"><span data-stu-id="5a813-220">If this soft-deleted mailbox was previously an inactive mailbox for which the hold was removed, it will be permanently deleted 30 days after the value of the *WhenSoftDeleted* property.</span></span> <span data-ttu-id="5a813-221">Nesse caso, a caixa de correio é excluída permanentemente após 30 de novembro de 2014.</span><span class="sxs-lookup"><span data-stu-id="5a813-221">In this case, the mailbox is permanently deleted after November 30, 2014.</span></span>