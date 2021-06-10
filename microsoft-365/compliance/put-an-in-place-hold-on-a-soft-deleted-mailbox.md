---
title: Colocar uma In-Place em uma caixa de correio excluída de forma Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
description: Saiba como criar um In-Place para uma caixa de correio excluída de forma suave para torná-la inativa e preservar seu conteúdo.
ms.openlocfilehash: 4cca34ab2ca3a946245f34a9b0d898a07537a722
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925517"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="6623d-103">Colocar uma In-Place em uma caixa de correio excluída de forma Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6623d-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="6623d-104">Saiba como criar um In-Place para uma caixa de correio excluída de forma suave para torná-la inativa e preservar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6623d-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="6623d-105">Em seguida, você pode usar as ferramentas de Descoberta Eletrônico da Microsoft para pesquisar a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6623d-106">À medida que continuamos a investir em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a ressarção do In-Place Holds no centro de administração Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="6623d-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="6623d-107">A partir de 1º de julho de 2020, você não poderá criar novos In-Place de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6623d-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="6623d-108">Mas você ainda poderá gerenciar os In-Place no EAC ou usando o cmdlet **Set-MailboxSearch** no Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6623d-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="6623d-109">No entanto, a partir de 1º de outubro de 2020, você não poderá gerenciar In-Place Holds.</span><span class="sxs-lookup"><span data-stu-id="6623d-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="6623d-110">Você só os removerá no EAC ou usando o cmdlet **Remove-MailboxSearch.**</span><span class="sxs-lookup"><span data-stu-id="6623d-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="6623d-111">Para obter mais informações sobre a aposentadoria de In-Place Detém, consulte A aposentadoria de ferramentas [de Descoberta eDiscovery herdado.](legacy-ediscovery-retirement.md)</span><span class="sxs-lookup"><span data-stu-id="6623d-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="6623d-112">Você pode ter uma situação em que uma pessoa tenha deixado sua organização e sua conta de usuário e caixa de correio correspondentes tenham sido excluídas.</span><span class="sxs-lookup"><span data-stu-id="6623d-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="6623d-113">Depois, você percebe que há informações na caixa de correio que precisam ser preservadas.</span><span class="sxs-lookup"><span data-stu-id="6623d-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="6623d-114">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="6623d-114">What can you do?</span></span> <span data-ttu-id="6623d-115">Se o período de retenção de caixa de correio excluído não tiver expirado, você poderá colocar uma retenção de In-Place na caixa de correio excluída (chamada de caixa de correio excluída de forma suave) e torná-la uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="6623d-116">Uma  *caixa de correio inativa*  é usada para preservar o email de um ex-funcionário depois que ele sai da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6623d-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="6623d-117">O conteúdo de uma caixa de correio inativa é preservado durante a duração do In-Place Que foi colocado na caixa de correio excluída quando ela foi inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="6623d-118">Depois que a caixa de correio for inativa, você poderá pesquisar a caixa de correio usando In-Place Descoberta eDiscovery no Exchange Online, Pesquisa de Conteúdo no Centro de Conformidade de Segurança & ou no Centro de Descoberta Eletrônico no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6623d-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6623d-119">No Exchange Online, uma caixa de correio excluída de forma suave é uma caixa de correio que foi excluída, mas pode ser recuperada em um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="6623d-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="6623d-120">O período de retenção de caixa de correio excluídos de forma Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="6623d-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="6623d-121">Isso significa que a caixa de correio pode ser recuperada (ou feita uma caixa de correio inativa) dentro de 30 dias após a exclusão.</span><span class="sxs-lookup"><span data-stu-id="6623d-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="6623d-122">Após 30 dias, uma caixa de correio excluída de forma suave é marcada para exclusão permanente e não pode ser recuperada ou inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="6623d-123">Requisitos para In-Place Detém</span><span class="sxs-lookup"><span data-stu-id="6623d-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="6623d-124">Você precisa usar o cmdlet **New-MailboxSearch** no Windows PowerShell para colocar um In-Place em uma caixa de correio excluída de forma suave.</span><span class="sxs-lookup"><span data-stu-id="6623d-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="6623d-125">Não é possível usar o centro de administração Exchange (EAC) ou o Centro de Descoberta SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6623d-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="6623d-126">Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6623d-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="6623d-127">Execute o seguinte comando para obter informações de identidade sobre as caixas de correio excluídas de forma suave em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6623d-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="6623d-128">Para obter mais informações sobre caixas de correio inativas, consulte [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6623d-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="6623d-129">Colocar uma In-Place em uma caixa de correio excluída de forma suave para torná-la uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="6623d-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="6623d-130">Use o cmdlet **New-MailboxSearch** para tornar uma caixa de correio excluída de forma suave uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="6623d-131">Para obter mais informações, consulte [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span><span class="sxs-lookup"><span data-stu-id="6623d-131">For more information, see [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch).</span></span>
  
1. <span data-ttu-id="6623d-132">Crie uma variável que contenha as propriedades da caixa de correio excluída de forma suave.</span><span class="sxs-lookup"><span data-stu-id="6623d-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="6623d-133">No comando anterior, use o valor da propriedade **DistinguishedName** ou **ExchangeGuid** para identificar a caixa de correio excluída de forma suave.</span><span class="sxs-lookup"><span data-stu-id="6623d-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="6623d-134">Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e uma caixa de correio excluída de forma suave tenham o mesmo endereço SMTP principal.</span><span class="sxs-lookup"><span data-stu-id="6623d-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="6623d-135">Crie uma In-Place e coloque-a na caixa de correio excluída.</span><span class="sxs-lookup"><span data-stu-id="6623d-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="6623d-136">Neste exemplo, nenhuma duração de espera é especificada.</span><span class="sxs-lookup"><span data-stu-id="6623d-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="6623d-137">Isso significa que os itens serão mantidos indefinidamente ou até que a espera seja removida da caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="6623d-138">Você também pode especificar uma duração de espera ao criar o In-Place Hold.</span><span class="sxs-lookup"><span data-stu-id="6623d-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="6623d-139">Este exemplo mantém itens na caixa de correio inativa por aproximadamente 7 anos.</span><span class="sxs-lookup"><span data-stu-id="6623d-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="6623d-140">Depois de alguns instantes, execute um dos seguintes comandos para verificar se a caixa de correio excluída de forma suave é uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="6623d-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="6623d-141">Ou</span><span class="sxs-lookup"><span data-stu-id="6623d-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="6623d-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="6623d-142">More information</span></span>

<span data-ttu-id="6623d-143">Depois de tornar uma caixa de correio excluída de forma suave uma caixa de correio inativa, há várias maneiras de gerenciar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="6623d-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="6623d-144">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="6623d-144">For more information, see:</span></span>
  
- [<span data-ttu-id="6623d-145">Alterar a duração de retenção de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="6623d-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="6623d-146">Recuperar uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="6623d-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="6623d-147">Restaurar uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="6623d-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="6623d-148">[Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md) (removendo a espera)</span><span class="sxs-lookup"><span data-stu-id="6623d-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>