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
ms.openlocfilehash: fa8e37b5e924f1b38755a953f40d8b70011213d0
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698274"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="dfe1a-103">Converter uma caixa de correio do usuário em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="dfe1a-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="dfe1a-104">Quando você converte a caixa de correio de um usuário em uma caixa de correio compartilhada, todos os emails e calendários existentes são mantidos.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="dfe1a-105">Agora, ela está em uma caixa de correio compartilhada onde várias pessoas poderão acessá-la, em vez de uma pessoa.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="dfe1a-106">Em uma data posterior, você pode converter uma caixa de correio compartilhada de volta para uma caixa de correio de usuário (privada).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="dfe1a-107">**Veja algumas coisas realmente importantes que você precisa saber:**</span><span class="sxs-lookup"><span data-stu-id="dfe1a-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="dfe1a-108">A caixa de correio do usuário que você está convertendo precisa de uma licença atribuída a ele antes de convertê-lo em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="dfe1a-109">Caso contrário, você não verá a opção de converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="dfe1a-110">Se você tiver removido a licença, adicione-a de volta para que possa converter a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="dfe1a-111">Após converter a caixa de correio para uma compartilhada, você pode remover a licença da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="dfe1a-112">Caixas de correio compartilhadas podem ter até 50 GB de dados sem uma licença atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="dfe1a-113">Para armazenar mais dados do que isso, você precisa de uma licença atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="dfe1a-114">Você pode precisar excluir um monte de emails grandes (digamos, aqueles com anexos) da caixa de correio compartilhada para diminuí-lo para que você possa remover a licença.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="dfe1a-115">Não exclua a conta do usuário antigo.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-115">Don't delete the old user's account.</span></span> <span data-ttu-id="dfe1a-116">Isso é necessário para ancorar a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-116">That's required to anchor the shared mailbox.</span></span> <span data-ttu-id="dfe1a-117">Se você já tiver excluído a conta de usuário, consulte [converter a caixa de correio de um usuário excluído](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-117">If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="dfe1a-118">As regras ficam intactas após a conversão da caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="dfe1a-119">Usar o centro de administração do Exchange para converter uma caixa de correio</span><span class="sxs-lookup"><span data-stu-id="dfe1a-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="dfe1a-120">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="dfe1a-121">Selecionar  \> **caixas de correio** de destinatários.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="dfe1a-122">Selecione a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-122">Select the user mailbox.</span></span> <span data-ttu-id="dfe1a-123">Em **converter em caixa de correio compartilhada**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="dfe1a-124">Se a caixa de correio for menor do que 50 GB, você poderá remover a [licença do usuário](../manage/remove-licenses-from-users.md)e deixar de pagar por ela.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="dfe1a-125">Não exclua a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-125">Don't delete the user's account.</span></span> <span data-ttu-id="dfe1a-126">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="dfe1a-127">Se estiver convertendo a caixa de correio de um funcionário que está saindo da sua organização, você deve executar etapas adicionais para garantir que eles não consigam mais fazer logon.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="dfe1a-128">Confira [remover um antigo funcionário da Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="dfe1a-129">Não é necessário redefinir a senha do usuário durante a conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="dfe1a-130">No entanto, se a senha não for redefinida, **o nome de usuário e a senha originais continuarão funcionando** após a conclusão da conversão da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="dfe1a-131">Para tudo o que você precisa saber sobre caixas de correio compartilhadas, consulte [sobre caixas de correio](about-shared-mailboxes.md) compartilhadas e [criar uma caixa de correio compartilhada](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dfe1a-132">Caixas de correio compartilhadas não exigem uma licença separada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="dfe1a-133">No entanto, se você deseja habilitar o arquivo de In-Place ou colocar uma In-Place isenção ou uma retenção de litígio em uma caixa de correio compartilhada, você deve atribuir uma licença do Exchange Online Plan 1 com o arquivamento do Exchange Online ou do Exchange Online Plan 2 à caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="dfe1a-134">Converter a caixa de correio de um usuário excluído</span><span class="sxs-lookup"><span data-stu-id="dfe1a-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="dfe1a-135">Digamos que você tenha excluído uma conta de usuário e agora deseja converter sua caixa de correio antiga para uma caixa de correio de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-135">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox.</span></span> <span data-ttu-id="dfe1a-136">Veja o que você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="dfe1a-136">Here's what you need to do:</span></span>

1. <span data-ttu-id="dfe1a-137">[Restaure a conta do usuário](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="dfe1a-138">Verifique se uma licença da Microsoft 365 está atribuída a ele.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="dfe1a-139">Redefinir a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="dfe1a-140">Aguarde 20-30 minutos para que a caixa de correio seja recriada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="dfe1a-141">Agora siga as instruções nesta página para converter a caixa de correio em uma caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="dfe1a-142">Depois disso, você pode remover a licença da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="dfe1a-143">Não exclua a caixa de correio antiga do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="dfe1a-144">A caixa de correio compartilhada precisa dela como uma âncora.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="dfe1a-145">Adicionar membros à caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="dfe1a-146">Converter uma caixa de correio compartilhada de volta para a caixa de correio de um usuário (privado)</span><span class="sxs-lookup"><span data-stu-id="dfe1a-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="dfe1a-147">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="dfe1a-148">Selecione **destinatários** \> **compartilhados**.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="dfe1a-149">Selecione a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-149">Select the shared mailbox.</span></span> <span data-ttu-id="dfe1a-150">Em **converter em caixa de correio normal**, selecione **converter**.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="dfe1a-151">Volte para o centro de administração.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-151">Go back to the admin center.</span></span> <span data-ttu-id="dfe1a-152">Em **usuários**, escolha a conta de usuário associada à caixa de correio compartilhada antiga.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="dfe1a-153">Atribua uma licença à conta e redefina a senha.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="dfe1a-154">Levará alguns minutos para que a caixa de correio seja configurada, mas depois dela, a pessoa que usará a conta está pronta para começar.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-154">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go.</span></span> <span data-ttu-id="dfe1a-155">Quando eles entrarem, eles verão os itens de email e calendário que usaram a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-155">When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="dfe1a-156">Converter a caixa de correio de um usuário em um ambiente híbrido</span><span class="sxs-lookup"><span data-stu-id="dfe1a-156">Convert a user's mailbox in a hybrid environment</span></span>

> [!NOTE] 
> <span data-ttu-id="dfe1a-157">A partir de outubro de 11, 2018, a implantação híbrida do Exchange suporta a criação de caixas de correio compartilhadas remotas começando na atualização cumulativa 21 para o Exchange Server 2013 e a atualização cumulativa 10 para o Exchange Server 2016 em um ambiente local do Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-157">Starting October 11th, 2018, Exchange hybrid deployment supports the creation of remote shared mailboxes starting in Cumulative Update 21 for Exchange Server 2013 and Cumulative Update 10 for Exchange Server 2016 in an on-premises Exchange Server environment.</span></span> <span data-ttu-id="dfe1a-158">Você pode criar ou modificar diretamente uma caixa de correio compartilhada remota usando o parâmetro New _-Shared_ .</span><span class="sxs-lookup"><span data-stu-id="dfe1a-158">You can directly create or modify a remote shared mailbox by using the new _-shared_ parameter.</span></span> <span data-ttu-id="dfe1a-159">Para obter mais informações, visite [cmdlets para criar ou modificar uma caixa de correio compartilhada remota em um ambiente do Exchange local](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-159">For more information, visit [Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment](https://support.microsoft.com/help/4133605/cmdlets-to-create-modify-remote-shared-mailbox-in-on-premises-exchange).</span></span>

<span data-ttu-id="dfe1a-160">Se essa caixa de correio compartilhada estiver em um ambiente híbrido e não se enquadrar no cenário acima, **recomendamos enfaticamente** que você mova a caixa de correio do usuário de volta para o local, converta a caixa de correio do usuário em uma caixa de correio compartilhada e mova a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-160">If this shared mailbox is in a hybrid environment and not falling under the above scenario, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="dfe1a-161">Veja por quê: se você converter a caixa de correio na nuvem, ela poderá ser convertida, mas o local ainda acha que a caixa de correio é a caixa de correio do usuário, porque a nova realidade não é sincronizada para o local.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-161">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="dfe1a-162">Normalmente, isso não é um problema, mas há alguns cenários em que os atributos locais (que acreditam que a caixa de correio é a caixa de correio do usuário) podem substituir as novas versões de nuvem desses atributos e, como resultado, a caixa de correio pode ser convertida novamente.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-162">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="dfe1a-163">Isso é um problema porque as caixas de correio do usuário exigem licenças **ou são excluídas de forma reversível após 30 dias**!</span><span class="sxs-lookup"><span data-stu-id="dfe1a-163">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="dfe1a-164">Abordamos a maioria dos motivos pelos quais isso acontece, mas ele ainda pode acontecer, embora com frequência.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-164">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="dfe1a-165">É melhor ser seguro e mover a caixa de correio de volta para o local, convertê-la e, em seguida, mover a caixa de correio compartilhada de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-165">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="dfe1a-166">Essa solução recomendada não está violando o contrato de licenciamento para ambientes híbridos porque a existência da caixa de correio de usuário local é apenas temporária.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-166">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="dfe1a-167">Você estaria violando sua licença se manteve a caixa de correio do usuário ou a caixa de correio compartilhada em sua organização local e não a moveu de volta para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-167">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>


> [!NOTE]
> <span data-ttu-id="dfe1a-168">Se você é membro do grupo de funções Gerenciamento da organização ou gerenciamento de destinatários, você pode usar o Shell de gerenciamento do Exchange para alterar uma caixa de correio de usuário para uma caixa de correio compartilhada no local.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-168">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="dfe1a-169">Por exemplo, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="dfe1a-169">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="dfe1a-170">Consulte a solução alternativa nesta solução de suporte para instâncias quando [caixas de correio compartilhadas são convertidas inesperadamente em caixas de correio de usuários](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="dfe1a-170">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="dfe1a-171">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="dfe1a-171">Related articles</span></span>

[<span data-ttu-id="dfe1a-172">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="dfe1a-172">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="dfe1a-173">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="dfe1a-173">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="dfe1a-174">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="dfe1a-174">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="dfe1a-175">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="dfe1a-175">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="dfe1a-176">Solucionar problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="dfe1a-176">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
