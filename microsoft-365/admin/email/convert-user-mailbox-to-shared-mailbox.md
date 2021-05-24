---
title: Converter uma caixa de correio do usuário em uma caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Aprenda a converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por várias pessoas em vez de por apenas uma pessoa. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635469"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="7ee6c-103">Converter uma caixa de correio do usuário em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="7ee6c-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="7ee6c-104">Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todo o email e calendário existentes são mantidos.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="7ee6c-105">Somente agora ele está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="7ee6c-106">Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta em uma caixa de correio de usuário (privada).</span><span class="sxs-lookup"><span data-stu-id="7ee6c-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7ee6c-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7ee6c-107">Before you begin</span></span>

<span data-ttu-id="7ee6c-108">**Aqui estão algumas coisas realmente importantes que você precisa saber:**</span><span class="sxs-lookup"><span data-stu-id="7ee6c-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="7ee6c-109">A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ela antes de convertê-la em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="7ee6c-110">Caso contrário, você não verá a opção de converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="7ee6c-111">Se você tiver removido a licença, adicione-a novamente para poder converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="7ee6c-112">Depois de converter a caixa de correio em uma compartilhada, você pode remover a licença da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="7ee6c-113">As caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a elas.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="7ee6c-114">Para manter mais dados do que isso, você precisa de uma licença atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="7ee6c-115">Talvez seja necessário excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para reduzi-la para que você possa remover a licença.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="7ee6c-116">Não exclua a conta do usuário antigo.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-116">Don't delete the old user's account.</span></span> <span data-ttu-id="7ee6c-117">Isso é necessário para ancorar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-117">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="7ee6c-118">Se você já excluiu a conta de usuário, consulte Converter a caixa de [correio de um usuário excluído.](#convert-the-mailbox-of-a-deleted-user)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-118">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="7ee6c-119">As regras ficam intactas depois que a caixa de correio é convertida em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="7ee6c-120">Usar o Exchange de administração para converter uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="7ee6c-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="7ee6c-121">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="7ee6c-122">Selecione **Caixas de Correio** de \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="7ee6c-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="7ee6c-123">Selecione a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-123">Select the user mailbox.</span></span> <span data-ttu-id="7ee6c-124">Em **Converter em Caixa de Correio Compartilhada,** selecione **Converter**.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7ee6c-125">Se a caixa de correio for menor que 50 GB, você poderá remover a licença do usuário [e](../manage/remove-licenses-from-users.md)parar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="7ee6c-126">Não exclua a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-126">Don't delete the user's account.</span></span> <span data-ttu-id="7ee6c-127">A caixa de correio compartilhada precisa dela como âncora.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="7ee6c-128">Se você estiver convertendo a caixa de correio de um funcionário que está deixando sua organização, você deve tomar etapas adicionais para garantir que ele não possa mais fazer logoff.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="7ee6c-129">Confira [Remover um ex-funcionário do Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="7ee6c-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="7ee6c-130">Não é necessário redefinir a senha do usuário durante a conversão de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="7ee6c-131">No entanto, se a senha não for redefinida, o nome de usuário e a senha **originais continuarão** a funcionar depois que a conversão de caixa de correio for concluída.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="7ee6c-132">Para saber mais sobre caixas de correio compartilhadas, consulte Sobre caixas de correio [compartilhadas](about-shared-mailboxes.md) e [Criar uma caixa de correio compartilhada.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7ee6c-133">Caixas de correio compartilhadas não exigem uma licença separada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="7ee6c-134">No entanto, se você quiser habilitar o In-Place Archive ou colocar uma In-Place ou uma Responsabilidade de Litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plano 1 com Arquivamento do Exchange Online ou Exchange Online Plano 2 à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="7ee6c-135">Converter a caixa de correio de um usuário excluído</span><span class="sxs-lookup"><span data-stu-id="7ee6c-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="7ee6c-136">Digamos que você excluiu uma conta de usuário e agora deseja converter sua caixa de correio antiga em uma caixa de correio de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-136">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="7ee6c-137">Veja o que você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="7ee6c-137">Here's what you need to do:</span></span>

1. <span data-ttu-id="7ee6c-138">[Restaure a conta do usuário](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="7ee6c-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="7ee6c-139">Certifique-se de Microsoft 365 uma licença de Microsoft 365 seja atribuída a ela.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="7ee6c-140">Redefinir a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="7ee6c-141">Aguarde 20 a 30 minutos para que sua caixa de correio seja recriada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="7ee6c-142">Agora, siga as instruções nesta página para converter sua caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="7ee6c-143">Após isso, você pode remover a licença da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="7ee6c-144">Não exclua a caixa de correio antiga do usuário.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="7ee6c-145">A caixa de correio compartilhada precisa dela como âncora.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="7ee6c-146">Adicione membros à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="7ee6c-147">Converter uma caixa de correio compartilhada de volta na caixa de correio (privada) de um usuário</span><span class="sxs-lookup"><span data-stu-id="7ee6c-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="7ee6c-148">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="7ee6c-149">Selecione **Destinatários** \> **Compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="7ee6c-150">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-150">Select the shared mailbox.</span></span> <span data-ttu-id="7ee6c-151">Em **Converter em Caixa de Correio Regular,** selecione **Converter**.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="7ee6c-152">Volte para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-152">Go back to the admin center.</span></span> <span data-ttu-id="7ee6c-153">Em **Usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="7ee6c-154">Atribua uma licença à conta e redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="7ee6c-155">Levará alguns minutos para a caixa de correio ser configurada, mas, depois disso, a pessoa que vai usar essa conta está pronta para ir.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-155">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="7ee6c-156">Quando eles entrarem, verão os itens de email e calendário que costumavam estar na caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-156">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="7ee6c-157">Converter a caixa de correio de um usuário em um ambiente híbrido</span><span class="sxs-lookup"><span data-stu-id="7ee6c-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="7ee6c-158">Para obter mais informações sobre como converter uma caixa de correio de usuário em uma caixa de correio compartilhada em um ambiente Exchange híbrido, consulte:</span><span class="sxs-lookup"><span data-stu-id="7ee6c-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="7ee6c-159">Cmdlets para criar ou modificar uma caixa de correio compartilhada remota em um ambiente Exchange local</span><span class="sxs-lookup"><span data-stu-id="7ee6c-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="7ee6c-160">As caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuário após a sincronização de diretórios ser Exchange implantação híbrida</span><span class="sxs-lookup"><span data-stu-id="7ee6c-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="7ee6c-161">Se você for membro do grupo de função Gerenciamento da Organização ou Gerenciamento de Destinatários, poderá usar o Shell de Gerenciamento Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="7ee6c-162">Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="7ee6c-163">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="7ee6c-163">Related content</span></span>

<span data-ttu-id="7ee6c-164">[Sobre caixas de correio compartilhadas](about-shared-mailboxes.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="7ee6c-165">[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7ee6c-166">[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7ee6c-167">[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="7ee6c-168">[Resolver problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>