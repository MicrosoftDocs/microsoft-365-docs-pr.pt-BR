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
description: 'Saiba como converter uma caixa de correio privada em uma caixa de correio compartilhada que pode ser acessada por vários usuários. '
ms.openlocfilehash: bc867c9b43656e40149eb7cd7a7e5ce186c10798
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445682"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="27dba-103">Converter uma caixa de correio do usuário em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="27dba-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="27dba-104">Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todos os emails e calendários existentes são mantidos.</span><span class="sxs-lookup"><span data-stu-id="27dba-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="27dba-105">Agora, ela está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la, em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="27dba-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="27dba-106">Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada).</span><span class="sxs-lookup"><span data-stu-id="27dba-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="27dba-107">**Veja algumas coisas realmente importantes que você precisa saber:**</span><span class="sxs-lookup"><span data-stu-id="27dba-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="27dba-108">A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ele antes de convertê-lo em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="27dba-109">Caso contrário, você não verá a opção de converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="27dba-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="27dba-110">Se você tiver removido a licença, adicione-a de volta para que possa converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="27dba-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="27dba-111">Após converter a caixa de correio para uma compartilhada, você pode remover a licença da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="27dba-112">Caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="27dba-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="27dba-113">Para armazenar mais dados do que isso, você precisa de uma licença atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="27dba-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="27dba-114">Você pode precisar excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para diminuí-lo para que você possa remover a licença.</span><span class="sxs-lookup"><span data-stu-id="27dba-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="27dba-115">Não exclua a conta do usuário antigo.</span><span class="sxs-lookup"><span data-stu-id="27dba-115">Don't delete the old user's account.</span></span> <span data-ttu-id="27dba-116">Isso é necessário para ancorar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="27dba-117">Se você já tiver excluído a conta de usuário, consulte [converter a caixa de correio de um usuário excluído](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="27dba-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="27dba-118">As regras ficam intactas após a conversão da caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="27dba-119">Usar o centro de administração do Exchange para converter uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="27dba-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="27dba-120">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="27dba-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="27dba-121">Selecionar **Recipients** \> **caixas de correio**de destinatários.</span><span class="sxs-lookup"><span data-stu-id="27dba-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="27dba-122">Selecione a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-122">Select the user mailbox.</span></span> <span data-ttu-id="27dba-123">Em **converter em caixa de correio compartilhada**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="27dba-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="27dba-124">Se a caixa de correio for menor do que 50 GB, você poderá remover a [licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="27dba-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="27dba-125">Não exclua a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-125">Don't delete the user's account.</span></span> <span data-ttu-id="27dba-126">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="27dba-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="27dba-127">Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon.</span><span class="sxs-lookup"><span data-stu-id="27dba-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="27dba-128">Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="27dba-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="27dba-129">Não é necessário redefinir a senha do usuário durante a conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="27dba-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="27dba-130">No entanto, se a senha não for redefinida, **o nome de usuário e a senha originais continuarão funcionando** após a conclusão da conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="27dba-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="27dba-131">Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="27dba-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="27dba-132">Caixas de correio compartilhadas não exigem uma licença separada.</span><span class="sxs-lookup"><span data-stu-id="27dba-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="27dba-133">No entanto, se você deseja habilitar o arquivo de In-Place ou colocar uma In-Place isenção ou uma retenção de litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plan 1 com o arquivamento do Exchange Online ou do Exchange Online Plan 2 à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="27dba-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="27dba-134">Converter a caixa de correio de um usuário excluído</span><span class="sxs-lookup"><span data-stu-id="27dba-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="27dba-135">Digamos que você tenha excluído uma conta de usuário e agora deseja converter sua caixa de correio antiga para uma caixa de correio de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="27dba-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="27dba-136">Veja o que você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="27dba-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="27dba-137">[Restaure a conta do usuário](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="27dba-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="27dba-138">Verifique se uma licença da Microsoft 365 está atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="27dba-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="27dba-139">Redefinir a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="27dba-140">Aguarde 20-30 minutos para que a caixa de correio seja recriada.</span><span class="sxs-lookup"><span data-stu-id="27dba-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="27dba-141">Agora siga as instruções nesta página para converter a caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="27dba-142">Depois disso, você pode remover a licença da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="27dba-143">Não exclua a caixa de correio antiga do usuário.</span><span class="sxs-lookup"><span data-stu-id="27dba-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="27dba-144">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="27dba-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="27dba-145">Adicionar membros à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="27dba-146">Converter uma caixa de correio compartilhada de volta para a caixa de correio de um usuário (privado)</span><span class="sxs-lookup"><span data-stu-id="27dba-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="27dba-147">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="27dba-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="27dba-148">Selecione **destinatários** \> **compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="27dba-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="27dba-149">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-149">Select the shared mailbox.</span></span> <span data-ttu-id="27dba-150">Em **converter em caixa de correio normal**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="27dba-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="27dba-151">Volte para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="27dba-151">Go back to the admin center.</span></span> <span data-ttu-id="27dba-152">Em **usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga.</span><span class="sxs-lookup"><span data-stu-id="27dba-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="27dba-153">Atribua uma licença à conta e redefina a senha.</span><span class="sxs-lookup"><span data-stu-id="27dba-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="27dba-154">Levará alguns minutos para que a caixa de correio seja configurada, mas depois dela, a pessoa que usará a conta está pronta para começar.</span><span class="sxs-lookup"><span data-stu-id="27dba-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="27dba-155">Quando eles entrarem, eles verão os itens de email e calendário que usaram a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="27dba-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="27dba-156">Converter a caixa de correio de um usuário em um ambiente híbrido</span><span class="sxs-lookup"><span data-stu-id="27dba-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="27dba-157">Se essa caixa de correio compartilhada estiver em um ambiente híbrido, **recomendamos enfaticamente** (quase exigir!) que você mova a caixa de correio do usuário de volta para o local, converta a caixa de correio do usuário em uma caixa de correio compartilhada e, em seguida, mova a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="27dba-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="27dba-158">Veja por quê: se você converter a caixa de correio na nuvem, ela poderá ser convertida, mas o local ainda acha que a caixa de correio é a caixa de correio do usuário, porque a nova realidade não é sincronizada para o local.</span><span class="sxs-lookup"><span data-stu-id="27dba-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="27dba-159">Normalmente, isso não é um problema, mas há alguns cenários em que os atributos locais (que acreditam que a caixa de correio é a caixa de correio do usuário) podem substituir as novas versões de nuvem desses atributos e, como resultado, a caixa de correio pode ser convertida novamente.</span><span class="sxs-lookup"><span data-stu-id="27dba-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="27dba-160">Isso é um problema porque as caixas de correio do usuário exigem licenças **ou são excluídas de forma reversível após 30 dias**!</span><span class="sxs-lookup"><span data-stu-id="27dba-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="27dba-161">Abordamos a maioria dos motivos pelos quais isso acontece, mas ele ainda pode acontecer, embora com frequência.</span><span class="sxs-lookup"><span data-stu-id="27dba-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="27dba-162">É melhor ser seguro e mover a caixa de correio de volta para o local, convertê-la e, em seguida, mover a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="27dba-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="27dba-163">Essa solução recomendada não está violando o contrato de licenciamento para ambientes híbridos porque a existência da caixa de correio de usuário local é apenas temporária.</span><span class="sxs-lookup"><span data-stu-id="27dba-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="27dba-164">Você estaria violando sua licença se manteve a caixa de correio do usuário ou a caixa de correio compartilhada em sua organização local e não a moveu de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="27dba-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="27dba-165">Se você é membro do grupo de funções Gerenciamento da organização ou gerenciamento de destinatários, você pode usar o Shell de gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local.</span><span class="sxs-lookup"><span data-stu-id="27dba-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="27dba-166">Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="27dba-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="27dba-167">Consulte a solução alternativa nesta solução de suporte para instâncias quando [caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuários](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="27dba-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="27dba-168">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="27dba-168">Related articles</span></span>

[<span data-ttu-id="27dba-169">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="27dba-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="27dba-170">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="27dba-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="27dba-171">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="27dba-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="27dba-172">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="27dba-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="27dba-173">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="27dba-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
