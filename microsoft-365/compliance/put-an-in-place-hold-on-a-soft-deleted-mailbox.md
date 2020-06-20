---
title: Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível no Exchange Online
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
description: Saiba como criar um bloqueio in-loco para uma caixa de correio excluída de forma reversível para torná-la inativa e preservar seu conteúdo.
ms.openlocfilehash: 4dcd6539519675094da9a05c7701b9f8511ce9a1
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818860"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a><span data-ttu-id="58507-103">Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58507-103">Put an In-Place Hold on a soft-deleted mailbox in Exchange Online</span></span>

<span data-ttu-id="58507-104">Saiba como criar um bloqueio in-loco para uma caixa de correio excluída de forma reversível para torná-la inativa e preservar seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="58507-104">Learn how to create an In-Place Hold for a soft-deleted mailbox to make it inactive and preserve its contents.</span></span> <span data-ttu-id="58507-105">Em seguida, você pode usar as ferramentas de descoberta eletrônica da Microsoft para pesquisar a caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="58507-105">Then you can use Microsoft eDiscovery tools to search the inactive mailbox.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58507-106">Como continuamos investindo em diferentes maneiras de preservar o conteúdo da caixa de correio, anunciamos a aposentadoria de bloqueios in-loco no centro de administração do Exchange (Eat).</span><span class="sxs-lookup"><span data-stu-id="58507-106">As we continue to invest in different ways to preserve mailbox content, we're announcing the retirement of In-Place Holds in the Exchange admin center (EAC).</span></span> <span data-ttu-id="58507-107">A partir de 1º de julho de 2020, você não poderá criar novos bloqueios in-loco no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58507-107">Starting July 1, 2020 you won't be able to create new In-Place Holds in Exchange Online.</span></span> <span data-ttu-id="58507-108">Mas você ainda poderá gerenciar bloqueios in-loco no Eat ou usando o cmdlet **Set-MailboxSearch** no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="58507-108">But you'll still be able to manage In-Place Holds in the EAC or by using the **Set-MailboxSearch** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="58507-109">No entanto, a partir de 1º de outubro de 2020, você não conseguirá gerenciar bloqueios in-loco.</span><span class="sxs-lookup"><span data-stu-id="58507-109">However, starting October 1, 2020, you won't be able to manage In-Place Holds.</span></span> <span data-ttu-id="58507-110">Você só deve removê-los no Eat ou usando o cmdlet **Remove-MailboxSearch** .</span><span class="sxs-lookup"><span data-stu-id="58507-110">You'll only be remove them in the EAC or by using the **Remove-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="58507-111">Para obter mais informações sobre a aposentadoria de bloqueios in-loco, consulte [aposentadoria of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).</span><span class="sxs-lookup"><span data-stu-id="58507-111">For more information about the retirement of In-Place Holds, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>
  
<span data-ttu-id="58507-112">Você pode ter uma situação em que uma pessoa deixou sua organização e a conta de usuário correspondente e caixa de correio foram excluídas.</span><span class="sxs-lookup"><span data-stu-id="58507-112">You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted.</span></span> <span data-ttu-id="58507-113">Posteriormente, você perceberá que há informações na caixa de correio que precisam ser preservadas.</span><span class="sxs-lookup"><span data-stu-id="58507-113">Afterwards, you realize there's information in the mailbox that needs to be preserved.</span></span> <span data-ttu-id="58507-114">O que você pode fazer?</span><span class="sxs-lookup"><span data-stu-id="58507-114">What can you do?</span></span> <span data-ttu-id="58507-115">Se o período de retenção de caixa de correio excluída ainda não tiver expirado, você pode colocar um bloqueio in-loco na caixa de correio excluída (chamada de caixa de correio excluída por software) e torná-la uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="58507-115">If the deleted mailbox retention period hasn't expired, you can put an In-Place Hold on the deleted mailbox (called a  soft-deleted mailbox ) and make it an inactive mailbox.</span></span> <span data-ttu-id="58507-116">Uma *caixa de correio inativa* é usada para preservar o email de um funcionário anterior, depois que ele deixa sua organização.</span><span class="sxs-lookup"><span data-stu-id="58507-116">An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization.</span></span> <span data-ttu-id="58507-117">O conteúdo de uma caixa de correio inativa é preservado para a duração do bloqueio in-loco que foi colocado na caixa de correio excluída por software quando ele foi tornado inativo.</span><span class="sxs-lookup"><span data-stu-id="58507-117">The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive.</span></span> <span data-ttu-id="58507-118">Após a caixa de correio ser desativada, você pode pesquisar a caixa de correio usando a descoberta eletrônica in-loco no Exchange Online, pesquisa de conteúdo no centro de conformidade de & de segurança ou no centro de descoberta eletrônica no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58507-118">After the mailbox is made inactive, you can search the mailbox by using In-Place eDiscovery in Exchange Online, Content Search in the Security & Compliance Center, or the eDiscovery Center in SharePoint Online.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58507-119">No Exchange Online, uma caixa de correio excluída por software é uma caixa de correio excluída, mas pode ser recuperada dentro de um período de retenção específico.</span><span class="sxs-lookup"><span data-stu-id="58507-119">In Exchange Online, a soft-deleted mailbox is a mailbox that's been deleted but can be recovered within a specific retention period.</span></span> <span data-ttu-id="58507-120">O período de retenção de caixa de correio excluída de forma reversível no Exchange Online é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="58507-120">The soft-deleted mailbox retention period in Exchange Online is 30 days.</span></span> <span data-ttu-id="58507-121">Isso significa que a caixa de correio pode ser recuperada (ou criada em uma caixa de correio inativa) em 30 dias após a exclusão.</span><span class="sxs-lookup"><span data-stu-id="58507-121">This means that the mailbox can be recovered (or made an inactive mailbox) within 30 days of being deleted.</span></span> <span data-ttu-id="58507-122">Após 30 dias, uma caixa de correio excluída por software é marcada para exclusão permanente e não pode ser recuperada ou desativada.</span><span class="sxs-lookup"><span data-stu-id="58507-122">After 30 days, a soft-deleted mailbox is marked for permanent deletion and can't be recovered or made inactive.</span></span> 
  
## <a name="requirements-for-in-place-holds"></a><span data-ttu-id="58507-123">Requisitos para bloqueios in-loco</span><span class="sxs-lookup"><span data-stu-id="58507-123">Requirements for In-Place Holds</span></span>

- <span data-ttu-id="58507-124">Você precisa usar o cmdlet **New-MailboxSearch** no Windows PowerShell para colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível.</span><span class="sxs-lookup"><span data-stu-id="58507-124">You have to use the **New-MailboxSearch** cmdlet in Windows PowerShell to put an In-Place Hold on a soft-deleted mailbox.</span></span> <span data-ttu-id="58507-125">Você não pode usar o centro de administração do Exchange (Eat) ou o centro de descoberta eletrônica no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58507-125">You can't use the Exchange admin center (EAC) or the eDiscovery Center in SharePoint Online.</span></span> 

- <span data-ttu-id="58507-126">Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="58507-126">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

- <span data-ttu-id="58507-127">Execute o seguinte comando para obter informações de identidade sobre as caixas de correio excluídas por software em sua organização.</span><span class="sxs-lookup"><span data-stu-id="58507-127">Run the following command to get identity information about the soft-deleted mailboxes in your organization.</span></span> 

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- <span data-ttu-id="58507-128">Para obter mais informações sobre caixas de correio inativas, consulte [visão geral das caixas de correio inativas no Office 365](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="58507-128">For more information about inactive mailboxes, see [Overview of inactive mailboxes in Office 365](inactive-mailboxes-in-office-365.md).</span></span>

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a><span data-ttu-id="58507-129">Colocar um bloqueio in-loco em uma caixa de correio excluída de forma reversível para torná-la uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="58507-129">Put an In-Place Hold on a soft-deleted mailbox to make it an inactive mailbox</span></span>

<span data-ttu-id="58507-130">Use o cmdlet **New-MailboxSearch** para tornar uma caixa de correio de exclusão flexível uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="58507-130">Use the **New-MailboxSearch** cmdlet to make a soft-deleted mailbox an inactive mailbox.</span></span> <span data-ttu-id="58507-131">Para obter mais informações, consulte [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span><span class="sxs-lookup"><span data-stu-id="58507-131">For more information, see [New-MailboxSearch](https://technet.microsoft.com/library/74303b47-bb49-407c-a43b-590356eae35c.aspx).</span></span>
  
1. <span data-ttu-id="58507-132">Criar uma variável que contém as propriedades da caixa de correio excluída de forma reversível.</span><span class="sxs-lookup"><span data-stu-id="58507-132">Create a variable that contains the properties of the soft-deleted mailbox.</span></span>

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="58507-133">No comando anterior, use o valor da propriedade **distinguishedName** ou **ExchangeGuid** para identificar a caixa de correio excluída de forma reversível.</span><span class="sxs-lookup"><span data-stu-id="58507-133">In the previous command, use the value of the **DistinguishedName** or **ExchangeGuid** property to identify the soft-deleted mailbox.</span></span> <span data-ttu-id="58507-134">Essas propriedades são exclusivas para cada caixa de correio em sua organização, enquanto é possível que uma caixa de correio ativa e uma caixa de correio excluída de forma reversível possam ter o mesmo endereço SMTP principal.</span><span class="sxs-lookup"><span data-stu-id="58507-134">These properties are unique for each mailbox in your organization, whereas it's possible that an active mailbox and a soft-deleted mailbox might have the same primary SMTP address.</span></span> 
  
2. <span data-ttu-id="58507-135">Crie um bloqueio in-loco e coloque-o na caixa de correio excluída de forma reversível.</span><span class="sxs-lookup"><span data-stu-id="58507-135">Create an In-Place Hold and place it on the soft-deleted mailbox.</span></span> <span data-ttu-id="58507-136">Neste exemplo, não é especificada nenhuma duração de retenção.</span><span class="sxs-lookup"><span data-stu-id="58507-136">In this example, no hold duration is specified.</span></span> <span data-ttu-id="58507-137">Isso significa que os itens serão mantidos indefinidamente ou até que a retenção seja removida da caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="58507-137">This means items will be held indefinitely or until the hold is removed from the inactive mailbox.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   <span data-ttu-id="58507-138">Você também pode especificar uma duração de retenção ao criar o bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="58507-138">You can also specify a hold duration when you create the In-Place Hold.</span></span> <span data-ttu-id="58507-139">Este exemplo mantém itens na caixa de correio inativa por aproximadamente 7 anos.</span><span class="sxs-lookup"><span data-stu-id="58507-139">This example holds items in the inactive mailbox for approximately 7 years.</span></span>

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. <span data-ttu-id="58507-140">Após alguns momentos, execute um dos seguintes comandos para verificar se a caixa de correio excluída por software é uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="58507-140">After a few moments, run one of the following commands to verify that the soft-deleted mailbox is an inactive mailbox.</span></span>

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    <span data-ttu-id="58507-141">Ou</span><span class="sxs-lookup"><span data-stu-id="58507-141">Or</span></span>
    
   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a><span data-ttu-id="58507-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="58507-142">More information</span></span>

<span data-ttu-id="58507-143">Após tornar uma caixa de correio inativa excluída por software, há várias maneiras de gerenciar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="58507-143">After you make a soft-deleted mailbox an inactive mailbox, there are a number of ways you can manage the mailbox.</span></span> <span data-ttu-id="58507-144">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="58507-144">For more information, see:</span></span>
  
- [<span data-ttu-id="58507-145">Alterar a duração de retenção de uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="58507-145">Change the hold duration for an inactive mailbox</span></span>](change-the-hold-duration-for-an-inactive-mailbox.md)

- [<span data-ttu-id="58507-146">Recuperar uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="58507-146">Recover an inactive mailbox</span></span>](recover-an-inactive-mailbox.md)

- [<span data-ttu-id="58507-147">Restaurar uma caixa de correio inativa</span><span class="sxs-lookup"><span data-stu-id="58507-147">Restore an inactive mailbox</span></span>](restore-an-inactive-mailbox.md)

- <span data-ttu-id="58507-148">[Excluir uma caixa de correio inativa](delete-an-inactive-mailbox.md) (removendo a isenção)</span><span class="sxs-lookup"><span data-stu-id="58507-148">[Delete an inactive mailbox](delete-an-inactive-mailbox.md) (by removing the hold)</span></span>
