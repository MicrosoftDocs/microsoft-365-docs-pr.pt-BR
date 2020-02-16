---
title: Aumentar a cota de Itens Recuperáveis para caixas de correio em espera
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'Habilite a caixa de correio de arquivo morto e ative o arquivamento de expansão automática para aumentar o tamanho da pasta itens recuperáveis para uma caixa de correio no Office 365. '
ms.openlocfilehash: 37d0e783f3b3a5157fe4a7a9b7d512b09c05d32c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072910"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a><span data-ttu-id="c5d93-103">Aumentar a cota de Itens Recuperáveis para caixas de correio em espera</span><span class="sxs-lookup"><span data-stu-id="c5d93-103">Increase the Recoverable Items quota for mailboxes on hold</span></span>

<span data-ttu-id="c5d93-104">A política de retenção padrão, chamada política padrão do MRM, que é aplicada automaticamente às novas caixas de correio no Exchange Online contém uma marca de retenção denominada itens recuperáveis 14 dias mover para o arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-104">The default retention policy—named Default MRM Policy—that is automatically applied to new mailboxes in Exchange Online contains a retention tag named Recoverable Items 14 days move to archive.</span></span> <span data-ttu-id="c5d93-105">Essa marca de retenção move itens da pasta itens recuperáveis na caixa de correio principal do usuário para a pasta itens recuperáveis na caixa de correio de arquivo morto do usuário depois que o período de retenção de 14 dias expira para um item.</span><span class="sxs-lookup"><span data-stu-id="c5d93-105">This retention tag moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox after the 14-day retention period expires for an item.</span></span> <span data-ttu-id="c5d93-106">Para que isso aconteça, a caixa de correio de arquivo morto do usuário deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="c5d93-106">For this to happen, the user's archive mailbox must be enabled.</span></span> <span data-ttu-id="c5d93-107">Se a caixa de correio de arquivo morto não estiver habilitada, nenhuma ação será executada, o que significa que os itens na pasta itens recuperáveis de uma caixa de correio em espera não serão movidos para a caixa de correio de arquivo morto após o período de retenção de 14 dias expirar.</span><span class="sxs-lookup"><span data-stu-id="c5d93-107">If the archive mailbox isn't enabled, no action is taken, which means that items in the Recoverable Items folder for a mailbox on hold aren't moved to the archive mailbox after the 14-day retention period expires.</span></span> <span data-ttu-id="c5d93-108">Como nada é excluído de uma caixa de correio em espera, é possível que a cota de armazenamento da pasta itens recuperáveis possa ser excedida, especialmente se a caixa de correio de arquivo morto do usuário não estiver habilitada.</span><span class="sxs-lookup"><span data-stu-id="c5d93-108">Because nothing is deleted from a mailbox on hold, it's possible that the storage quota for the Recoverable Items folder might be exceeded, especially if the user's archive mailbox isn't enabled.</span></span> 
  
<span data-ttu-id="c5d93-109">Para ajudar a reduzir a chance de exceder esse limite, a cota de armazenamento da pasta itens recuperáveis é aumentada automaticamente de 30 GB para 100 GB quando uma retenção é colocada em uma caixa de correio no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5d93-109">To help reduce the chance of exceeding this limit, the storage quota for the Recoverable Items folder is automatically increased from 30 GB to 100 GB when a hold is placed on a mailbox in Exchange Online.</span></span> <span data-ttu-id="c5d93-110">Se a caixa de correio de arquivo morto estiver habilitada, a cota de armazenamento da pasta Itens Recuperáveis na caixa de correio de arquivo morto também aumentará de 30 GB para 100 GB.</span><span class="sxs-lookup"><span data-stu-id="c5d93-110">If the archive mailbox is enabled, the storage quota for the Recoverable Items folder in the archive mailbox is also increased from 30 GB to 100 GB.</span></span> <span data-ttu-id="c5d93-111">Se o recurso de arquivamento de expansão automática no Exchange Online estiver habilitado, a cota de armazenamento da pasta itens recuperáveis no arquivo morto do usuário será ilimitada.</span><span class="sxs-lookup"><span data-stu-id="c5d93-111">If the auto-expanding archiving feature in Exchange Online is enabled, the storage quota for the Recoverable Items folder in the user's archive will be unlimited.</span></span>
  
 <span data-ttu-id="c5d93-112"> A tabela a seguir resume a cota de armazenamento da pasta Itens Recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="c5d93-112">The following table summarizes the storage quota for the Recoverable Items folder.</span></span> 
  
|<span data-ttu-id="c5d93-113">**Local da pasta Itens Recuperáveis**</span><span class="sxs-lookup"><span data-stu-id="c5d93-113">**Location of Recoverable Items folder**</span></span>|<span data-ttu-id="c5d93-114">**Caixas de correio não em espera**</span><span class="sxs-lookup"><span data-stu-id="c5d93-114">**Mailboxes not on hold**</span></span>|<span data-ttu-id="c5d93-115">**Caixas de correio em espera**</span><span class="sxs-lookup"><span data-stu-id="c5d93-115">**Mailboxes on hold**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c5d93-116">Caixa de correio principal</span><span class="sxs-lookup"><span data-stu-id="c5d93-116">Primary mailbox</span></span>  <br/> |<span data-ttu-id="c5d93-117">30 GB</span><span class="sxs-lookup"><span data-stu-id="c5d93-117">30 GB</span></span>  <br/> |<span data-ttu-id="c5d93-118">100 GB</span><span class="sxs-lookup"><span data-stu-id="c5d93-118">100 GB</span></span>  <br/> |
|<span data-ttu-id="c5d93-119">Caixa de correio de arquivo morto<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c5d93-119">Archive mailbox<sup>\*</sup></span></span> <br/> |<span data-ttu-id="c5d93-120">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="c5d93-120">Unlimited</span></span>  <br/> |<span data-ttu-id="c5d93-121">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="c5d93-121">Unlimited</span></span>  <br/> |
|<span data-ttu-id="c5d93-122">**Cota de armazenamento total para a pasta Itens Recuperáveis**</span><span class="sxs-lookup"><span data-stu-id="c5d93-122">**Total storage quota for the Recoverable Items folder**</span></span> <br/> |<span data-ttu-id="c5d93-123">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="c5d93-123">Unlimited</span></span>  <br/> |<span data-ttu-id="c5d93-124">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="c5d93-124">Unlimited</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="c5d93-125"><sup>\*</sup>A cota de armazenamento inicial da caixa de correio de arquivo morto é de 100 GB para os usuários com uma licença do Exchange Online (plano 2).</span><span class="sxs-lookup"><span data-stu-id="c5d93-125"><sup>\*</sup> The initial storage quota for the archive mailbox is 100 GB for users with an Exchange Online (Plan 2) license.</span></span> <span data-ttu-id="c5d93-126">No entanto, quando o arquivamento de expansão automática está ativado para caixas de correio em espera, a cota de armazenamento para a caixa de correio de arquivo morto e a pasta itens recuperáveis é aumentada para 110 GB.</span><span class="sxs-lookup"><span data-stu-id="c5d93-126">However, when auto-expanding archiving is turned on for mailboxes on hold, the storage quota for both the archive mailbox and the Recoverable Items folder is increased to 110 GB.</span></span> <span data-ttu-id="c5d93-127">Espaço de armazenamento adicional de arquivo morto será provisionado quando necessário, o que resulta em uma quantidade ilimitada de armazenamento de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-127">Additional archive storage space will be provisioned when necessary which results in an unlimited amount of archive storage.</span></span> <span data-ttu-id="c5d93-128">Para obter mais informações sobre o arquivamento de expansão automática, consulte [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c5d93-128">For more information about auto-expanding archiving, see [Overview of unlimited archiving in Office 365](unlimited-archiving.md).</span></span> 
  
<span data-ttu-id="c5d93-129">Quando a cota de armazenamento da pasta Itens Recuperáveis na caixa de correio principal de uma caixa de correio em espera está quase atingindo o limite, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c5d93-129">When the storage quota for the Recoverable Items folder in the primary mailbox of a mailbox on hold is close to reaching its limit, you can do the following things:</span></span>
  
- <span data-ttu-id="c5d93-130">**Habilitar a caixa de correio de arquivo morto e ativar o arquivamento de expansão automática** -você pode habilitar uma capacidade de armazenamento ilimitada para a pasta itens recuperáveis, simplesmente habilitando a caixa de correio de arquivo morto e, em seguida, ativando o recurso de arquivamento de expansão automática no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c5d93-130">**Enable the archive mailbox and turn on auto-expanding archiving** - You can enable an unlimited storage capacity for the Recoverable Items folder simply by enabling the archive mailbox and then turning on the auto-expanding archiving feature in Exchange Online.</span></span> <span data-ttu-id="c5d93-131">Isso resulta em 110 GB para a pasta itens recuperáveis na caixa de correio principal e uma quantidade ilimitada de capacidade de armazenamento para a pasta itens recuperáveis no arquivo morto do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5d93-131">This results in 110 GB for the Recoverable Items folder in the primary mailbox and an unlimited amount of storage capacity for the Recoverable Items folder in the user's archive.</span></span> <span data-ttu-id="c5d93-132">Confira como: [habilitar caixas de correio de arquivo morto no centro de conformidade de & de segurança](enable-archive-mailboxes.md) e [habilitar o arquivamento ilimitado no Office 365](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="c5d93-132">See how: [Enable archive mailboxes in the Security & Compliance Center](enable-archive-mailboxes.md) and [Enable unlimited archiving in Office 365](enable-unlimited-archiving.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c5d93-133">Após habilitar o arquivamento para uma caixa de correio que está prestes a exceder a cota de armazenamento da pasta Itens Recuperáveis, convém executar o Assistente de Pasta Gerenciada para disparar manualmente o assistente para processar a caixa de correio, de modo que os itens expirados sejam movidos para a pasta Itens Recuperáveis na caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-133">After you enable the archive for a mailbox that's close to exceeding the storage quota for the Recoverable Items folder, you might want to run the Managed Folder Assistant to manually trigger the assistant to process the mailbox so that expired items are moved the Recoverable Items folder in the archive mailbox.</span></span> <span data-ttu-id="c5d93-134">Confira as instruções na [Etapa 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings).</span><span class="sxs-lookup"><span data-stu-id="c5d93-134">See [Step 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings) for instructions.</span></span> <span data-ttu-id="c5d93-135">Os demais itens na caixa de correio do usuário podem ser movidos para a nova caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-135">Note that other items in the user's mailbox might be moved to the new archive mailbox.</span></span> <span data-ttu-id="c5d93-136">Considere a possibilidade de informar ao usuário que isso pode acontecer depois que você habilitar a caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-136">Consider telling the user that this may happen after you enable the archive mailbox.</span></span> 
  
- <span data-ttu-id="c5d93-137">**Criar uma política de retenção personalizada para caixas de correio em retenção** , além de habilitar a caixa de correio de arquivo morto e o arquivamento de expansão automática para caixas de correio em retenção de litígio ou bloqueio in-loco, você também pode querer criar uma política de retenção personalizada para caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="c5d93-137">**Create a custom retention policy for mailboxes on hold** - In addition to enabling the archive mailbox and auto-expanding archiving for mailboxes on Litigation Hold or In-Place Hold, you might also want to create a custom retention policy for mailboxes on hold.</span></span> <span data-ttu-id="c5d93-138">Isso permite aplicar uma política de retenção para caixas de correio em espera diferente da Política de MRM Padrão que é aplicada às caixas de correio que não estão em espera.</span><span class="sxs-lookup"><span data-stu-id="c5d93-138">This let's you apply a retention policy to mailboxes on hold that's different from the Default MRM Policy that's applied to mailboxes that aren't on hold.</span></span> <span data-ttu-id="c5d93-139">Isso permite aplicar marcas de retenção projetadas especificamente para caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="c5d93-139">This lets you to apply retention tags that are specifically designed for mailboxes on hold.</span></span> <span data-ttu-id="c5d93-140">Isso inclui a criação de uma nova marca de retenção para a pasta Itens Recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="c5d93-140">This includes creating a new retention tag for the Recoverable Items folder.</span></span> 
    
<span data-ttu-id="c5d93-141">O restante deste tópico descreve os procedimentos passo a passo para criar uma política de retenção personalizada para caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="c5d93-141">The remainder of this topic describes the step-by-step procedures to create a custom retention policy for mailboxes on hold.</span></span>
  
[<span data-ttu-id="c5d93-142">Etapa 1: criar uma marca de retenção personalizada para a pasta Itens Recuperáveis</span><span class="sxs-lookup"><span data-stu-id="c5d93-142">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

<span data-ttu-id="c5d93-143">[[Etapa 2: criar uma nova política de retenção para caixas de correio em espera](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span><span class="sxs-lookup"><span data-stu-id="c5d93-143">[[Step 2: Create a new retention policy for mailboxes on hold](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)</span></span>

[<span data-ttu-id="c5d93-144">Etapa 3: aplicar a nova política de retenção a caixas de correio em espera</span><span class="sxs-lookup"><span data-stu-id="c5d93-144">Step 3: Apply the new retention policy to mailboxes on hold</span></span>](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[<span data-ttu-id="c5d93-145">(Opcional) Etapa 4: executar o Assistente de Pasta Gerenciada para aplicar as novas configurações de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-145">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a><span data-ttu-id="c5d93-146">Etapa 1: Criar uma marca de retenção personalizada para a pasta Itens Recuperáveis</span><span class="sxs-lookup"><span data-stu-id="c5d93-146">Step 1: Create a custom retention tag for the Recoverable Items folder</span></span>

<span data-ttu-id="c5d93-147">A primeira etapa é criar uma marca de retenção personalizada (chamada de marca de política de retenção ou RPT) para a pasta Itens Recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="c5d93-147">The first step is to create a custom retention tag (called a retention policy tag or RPT) for the Recoverable Items folder.</span></span> <span data-ttu-id="c5d93-148">Como explicado anteriormente, essa RPT move itens da pasta Itens Recuperáveis na caixa de correio principal do usuário para a pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5d93-148">As previously explained, this RPT moves items from the Recoverable Items folder in the user's primary mailbox to the Recoverable Items folder in the user's archive mailbox.</span></span> <span data-ttu-id="c5d93-149">Você precisa usar o PowerShell para criar um relatório para a pasta itens recuperáveis.</span><span class="sxs-lookup"><span data-stu-id="c5d93-149">You have to use PowerShell to create an RPT for the Recoverable Items folder.</span></span> <span data-ttu-id="c5d93-150">Você não pode usar o Centro de Administração do Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="c5d93-150">You can't use the Exchange admin center (EAC).</span></span> 
  
1. [<span data-ttu-id="c5d93-151">Conectar-se ao Exchange Online usando o PowerShell Remoto</span><span class="sxs-lookup"><span data-stu-id="c5d93-151">Connect to Exchange Online using remote PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. <span data-ttu-id="c5d93-152">Execute o seguinte comando para criar um novo relatório para a pasta Itens Recuperáveis: </span><span class="sxs-lookup"><span data-stu-id="c5d93-152">Run the following command to create a new RPT for the Recoverable Items folder:</span></span> 
    
    ```powershell
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    <span data-ttu-id="c5d93-p108">Por exemplo, o comando a seguir cria um relatório para a pasta Itens Recuperáveis denominado "Itens Recuperáveis para caixas de correio em retenção: 30 dias", com um período de retenção de 30 dias. Isso significa que depois que um item estiver na pasta Itens Recuperáveis por 30 dias, ele será movido para a pasta Itens Recuperáveis na caixa de correio de arquivo morto do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5d93-p108">For example, the following command creates a RPT for the Recoverable Items folder named "Recoverable Items 30 days for mailboxes on hold", with a retention period of 30 days. This means that after an item has been in the Recoverable Items folder for 30 days, it will be moved to the Recoverable Items folder in the user's archive mailbox.</span></span>
    
    ```powershell
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > <span data-ttu-id="c5d93-155">Recomendamos que o período de retenção (definido pelo parâmetro _AgeLimitForRetention_ ) para os itens recuperáveis RPT seja o mesmo que o período de retenção de itens excluídos para as caixas de correio às quais o RPT será aplicado.</span><span class="sxs-lookup"><span data-stu-id="c5d93-155">We recommend that the retention period (defined by the  _AgeLimitForRetention_ parameter) for the Recoverable Items RPT is the same as the deleted item retention period for the mailboxes that the RPT will be applied to.</span></span> <span data-ttu-id="c5d93-156">Isso proporciona a um usuário todo o período de retenção de itens excluídos para recuperar itens excluídos antes que eles sejam movidos para a caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-156">This allows a user the entire deleted item retention period to recover deleted items before they are moved to the archive mailbox.</span></span> <span data-ttu-id="c5d93-157">No exemplo anterior, o período de retenção foi configurado para 30 dias com base na suposição de que o período de retenção de itens excluídos para caixas de correio também é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c5d93-157">In the previous example, the retention period was set to 30 days based on the assumption that the deleted item retention period for mailboxes is also 30 days.</span></span> <span data-ttu-id="c5d93-158">Uma caixa de correio do Exchange Online é configurada, por padrão, para manter itens excluídos por 14 dias.</span><span class="sxs-lookup"><span data-stu-id="c5d93-158">An Exchange Online mailbox is configured to retain deleted items for 14 days, by default.</span></span> <span data-ttu-id="c5d93-159">Porém, você pode alterar essa configuração para até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c5d93-159">But you can change this setting to a maximum of 30 days.</span></span> <span data-ttu-id="c5d93-160">Para obter mais informações, consulte [alterar o período de retenção de itens excluídos para uma caixa de correio no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span><span class="sxs-lookup"><span data-stu-id="c5d93-160">For more information, see [Change the deleted item retention period for a mailbox in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286940).</span></span> 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a><span data-ttu-id="c5d93-161">Etapa 2: Criar uma nova política de retenção para caixas de correio em espera</span><span class="sxs-lookup"><span data-stu-id="c5d93-161">Step 2: Create a new retention policy for mailboxes on hold</span></span>

<span data-ttu-id="c5d93-p110">A próxima etapa é criar uma nova política de retenção e adicionar marcas de retenção a ela, inclusive o RPT de Itens Recuperáveis que você criou na Etapa 1. Essa nova política será aplicada às caixas de correio em espera na próxima etapa. </span><span class="sxs-lookup"><span data-stu-id="c5d93-p110">The next step is to create a new retention policy and add retention tags to it, including the Recoverable Items RPT that you created in Step 1. This new policy will be applied to mailboxes on hold in the next step.</span></span> 
  
<span data-ttu-id="c5d93-p111">Antes de criar a nova política de retenção, determine as marcas de retenção adicionais que você deseja adicionar. Confira a lista das marcas de retenção adicionadas à política MRM Padrão e informações sobre como criar novas marcas de retenção em:</span><span class="sxs-lookup"><span data-stu-id="c5d93-p111">Before you create the new retention policy, determine the additional retention tags that you want to add. For a list of the retention tags that are added to the Default MRM Policy and for information about creating new retention tags, see the following:</span></span>
  
- [<span data-ttu-id="c5d93-166">Política de Retenção Padrão no Exchange Online </span><span class="sxs-lookup"><span data-stu-id="c5d93-166">Default Retention Policy in Exchange Online </span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [<span data-ttu-id="c5d93-167">Pastas padrão que suportam marcas de política de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-167">Default folders that support Retention Policy Tags</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- <span data-ttu-id="c5d93-168">A seção "criar uma marca de retenção" no tópico [criar uma política de retenção](https://go.microsoft.com/fwlink/p/?LinkId=404422) .</span><span class="sxs-lookup"><span data-stu-id="c5d93-168">The "Create a retention tag" section in the [Create a Retention Policy](https://go.microsoft.com/fwlink/p/?LinkId=404422) topic.</span></span>
    
<span data-ttu-id="c5d93-169">Você pode usar o Eat ou o PowerShell do Exchange Online para criar uma política de retenção.</span><span class="sxs-lookup"><span data-stu-id="c5d93-169">You can use the EAC or Exchange Online PowerShell to create a retention policy.</span></span>
  
### <a name="use-the-eac-to-create-a-retention-policy"></a><span data-ttu-id="c5d93-170">Usar o EAC para criar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-170">Use the EAC to create a retention policy</span></span>
  
1. <span data-ttu-id="c5d93-171">No Eat, vá para **políticas de retenção**de **Gerenciamento** \> de conformidade e clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif)de adição.</span><span class="sxs-lookup"><span data-stu-id="c5d93-171">In the EAC, go to **Compliance management** \> **Retention policies**, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
2. <span data-ttu-id="c5d93-172">Na página **Nova política de retenção**, em **Nome**, digite um nome que descreva o propósito da política de retenção, por exemplo, **MRM Policy for Mailboxes on Hold**. </span><span class="sxs-lookup"><span data-stu-id="c5d93-172">On the **New retention policy** page, under **Name**, type a name that describes the purpose of the retention policy; for example, **MRM Policy for Mailboxes on Hold**.</span></span> 
    
3. <span data-ttu-id="c5d93-173">Em **marcas de retenção**, \*\*\*\* ![clique em Adicionar](../media/ITPro-EAC-AddIcon.gif)ícone de adição.</span><span class="sxs-lookup"><span data-stu-id="c5d93-173">Under **Retention tags**, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="c5d93-174">Na lista de marcas de retenção, selecione o relatório de itens recuperáveis que você criou na Etapa 1 e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-174">In the list of retention tags, select the Recoverable Items RPT that you created in Step 1, and then click **Add**.</span></span>
    
    ![Selecione a marca de retenção personalizada Itens Recuperáveis](../media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. <span data-ttu-id="c5d93-p112">Selecione marcas de retenção adicionais para adicionar à política de retenção. Por exemplo, convém adicionar as mesmas marcas que são incluídas na Política de MRM Padrão.</span><span class="sxs-lookup"><span data-stu-id="c5d93-p112">Select additional retention tags to add to the retention policy. For example, you might want to add the same tags that are included in the Default MRM Policy.</span></span>
    
6. <span data-ttu-id="c5d93-178">Quando terminar de adicionar marcas de retenção, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-178">When you're finished adding retention tags, click **OK**.</span></span>
    
7. <span data-ttu-id="c5d93-179">Clique em **Salvar** para criar a nova política de retenção. </span><span class="sxs-lookup"><span data-stu-id="c5d93-179">Click **Save** to create the new retention policy.</span></span> 
    
    <span data-ttu-id="c5d93-180">Observe que as marcas de retenção vinculadas à política de retenção são exibidas no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="c5d93-180">Notice that the retention tags linked to the retention policy are displayed in the details pane.</span></span>
    
    ![Marcas de retenção vinculadas à política de retenção são exibidas no painel de detalhes](../media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a><span data-ttu-id="c5d93-182">Usar o PowerShell do Exchange Online para criar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-182">Use Exchange Online PowerShell to create a retention policy</span></span>
  
<span data-ttu-id="c5d93-183">Execute o comando a seguir para criar a nova política de retenção para caixas de correio em espera. </span><span class="sxs-lookup"><span data-stu-id="c5d93-183">Run the following command to create new retention policy for mailboxes on hold.</span></span> 
  
```powershell
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

<span data-ttu-id="c5d93-184">Por exemplo, o comando a seguir cria a política de retenção e as marcas de retenção vinculadas que são exibidas na ilustração anterior.</span><span class="sxs-lookup"><span data-stu-id="c5d93-184">For example, the following command creates the retention policy and linked retention tags that is displayed in the previous illustration.</span></span>
  
```powershell
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```

## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a><span data-ttu-id="c5d93-185">Etapa 3: Aplicar a nova política de retenção a caixas de correio em espera</span><span class="sxs-lookup"><span data-stu-id="c5d93-185">Step 3: Apply the new retention policy to mailboxes on hold</span></span>

<span data-ttu-id="c5d93-186">A última etapa é aplicar a nova política de retenção que você criou na Etapa 2 a caixas de correio em espera na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c5d93-186">The last step is to apply the new retention policy that you created in Step 2 to mailboxes on hold in your organization.</span></span> <span data-ttu-id="c5d93-187">Você pode usar o Eat ou o PowerShell do Exchange Online para aplicar a política de retenção a uma única caixa de correio ou a várias caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-187">You can use the EAC or Exchange Online PowerShell to apply the retention policy to a single mailbox or to multiple mailboxes.</span></span> 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a><span data-ttu-id="c5d93-188">Usar o EAC para aplicar a nova política de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-188">Use the EAC to apply the new retention policy</span></span>
  
1. <span data-ttu-id="c5d93-189">Acesse **Destinatários** \> **Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-189">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="c5d93-190">No modo de exibição de lista, selecione a caixa de correio à qual você deseja aplicar a política de \*\*\*\* ![retenção e clique](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)em Editar ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="c5d93-190">In the list view, select the mailbox you want to apply the retention policy to, and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif).</span></span>
    
3. <span data-ttu-id="c5d93-191">Na página **Caixa de Correio do Usuário**, clique em **Recursos de caixa de correio**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-191">On the **User Mailbox** page, click **Mailbox features**.</span></span>
    
4. <span data-ttu-id="c5d93-192">Em **Política de retenção**, selecione a política de retenção que você criou na Etapa 2 e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-192">Under **Retention policy**, select the retention policy that you created in Step 2, and then click **Save**.</span></span>
    
<span data-ttu-id="c5d93-193">Você também pode usar o EAC para aplicar a política de retenção a várias caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-193">You can also use the EAC to apply the retention policy to multiple mailboxes.</span></span>
  
1. <span data-ttu-id="c5d93-194">Acesse **Destinatários** \> **Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-194">Go to **Recipients** \> **Mailboxes**.</span></span>
    
2. <span data-ttu-id="c5d93-195">No modo de exibição de lista, use as teclas Shift ou Ctrl, para selecionar várias caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-195">In the list view, use the Shift or Ctrl keys to select multiple mailboxes.</span></span>
    
3. <span data-ttu-id="c5d93-196">No painel de detalhes, clique em **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-196">In the details pane, click **More options**.</span></span>
    
4. <span data-ttu-id="c5d93-197">Em **Política de Retenção**, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="c5d93-197">Under **Retention Policy**, click **Update**.</span></span>
    
5. <span data-ttu-id="c5d93-198">Na página **Atribuir em massa uma política de retenção**, selecione a política de retenção que você criou na Etapa 2 e clique em **Salvar**. </span><span class="sxs-lookup"><span data-stu-id="c5d93-198">On the **Bulk assign retention policy** page, select the retention policy that you created in Step 2, and then click **Save**.</span></span> 
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a><span data-ttu-id="c5d93-199">Usar o PowerShell do Exchange Online para aplicar a nova política de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-199">Use Exchange Online PowerShell to apply the new retention policy</span></span>
  
<span data-ttu-id="c5d93-200">Você pode usar o PowerShell do Exchange Online para aplicar uma nova política de retenção a uma única caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-200">You can use Exchange Online PowerShell to apply a new retention policy to a single mailbox.</span></span> <span data-ttu-id="c5d93-201">Mas o poder real do PowerShell é que você pode usá-lo para identificar rapidamente todas as caixas de correio em sua organização que estão em retenção de litígio ou bloqueio in-loco e, em seguida, aplicar a nova política de retenção a todas as caixas de correio em espera em um único comando.</span><span class="sxs-lookup"><span data-stu-id="c5d93-201">But the real power of PowerShell is that you can use it to quickly identify all the mailboxes in your organization that are on either Litigation Hold or In-Place Hold, and then apply the new retention policy to all mailboxes on hold in a single command.</span></span> <span data-ttu-id="c5d93-202">Aqui estão alguns exemplos de como usar o Exchange PowerShell para aplicar uma política de retenção a uma ou mais caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-202">Here are some examples of using Exchange PowerShell to apply a retention policy to one or more mailboxes.</span></span> <span data-ttu-id="c5d93-203">Todos os exemplos aplicam a política de retenção que foi criada na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c5d93-203">All of the examples apply the retention policy that was created in Step 2.</span></span>
  
<span data-ttu-id="c5d93-204">Este exemplo aplica a nova política de retenção à caixa de correio de Clara Barbosa.</span><span class="sxs-lookup"><span data-stu-id="c5d93-204">This example applies the new retention policy to Pilar Pinilla's mailbox.</span></span>
  
```powershell
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="c5d93-205">Este exemplo aplica a nova política de retenção a todas as caixas de correio na organização que estão em Retenção de Litígio.</span><span class="sxs-lookup"><span data-stu-id="c5d93-205">This example applies the new retention policy to all mailboxes in the organization that are on Litigation Hold.</span></span>
  
```powershell
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```powershell
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="c5d93-206">Este exemplo aplica a nova política de retenção a todas as caixas de correio na organização que estão em Bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="c5d93-206">This example applies the new retention policy to all mailboxes in the organization that are on In-Place Hold.</span></span>
  
```powershell
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```powershell
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

<span data-ttu-id="c5d93-207">Você pode usar o cmdlet **Get-Mailbox** para verificar se a nova política de retenção foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="c5d93-207">You can use the **Get-Mailbox** cmdlet to verify that the new retention policy was applied.</span></span> 
  
<span data-ttu-id="c5d93-208">Aqui estão alguns exemplos para verificar se os comandos nos exemplos anteriores aplicaram a "Política MRM a caixas de correio em espera" em caixas de correio em Retenção de Litígio e caixas de correio em Bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="c5d93-208">Here are some examples to verify that the commands in the previous examples applied the "MRM Policy for Mailboxes on Hold" retention policy to mailboxes on Litigation Hold and mailboxes on In-Place Hold.</span></span>
  
```powershell
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```powershell
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```

## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a><span data-ttu-id="c5d93-209">(Opcional) Etapa 4: Executar o Assistente de Pasta Gerenciada para aplicar as novas configurações de retenção</span><span class="sxs-lookup"><span data-stu-id="c5d93-209">(Optional) Step 4: Run the Managed Folder Assistant to apply the new retention settings</span></span>

<span data-ttu-id="c5d93-210">Depois de aplicar a nova política de retenção às caixas de correio em espera, pode levar até 7 dias no Exchange Online para que o assistente de pasta gerenciada processe essas caixas de correio usando as configurações da nova política de retenção.</span><span class="sxs-lookup"><span data-stu-id="c5d93-210">After you apply the new retention policy to mailboxes on hold, it can take up to 7 days in Exchange Online for the Managed Folder Assistant to process these mailboxes using the settings in the new retention policy.</span></span> <span data-ttu-id="c5d93-211">Em vez de esperar pela execução do Assistente de Pasta Gerenciada, você pode usar o cmdlet **Start-ManagedFolderAssistant** para disparar manualmente o assistente para processar as caixas de correio às quais você aplicou a nova política de retenção.</span><span class="sxs-lookup"><span data-stu-id="c5d93-211">Instead of waiting for the Managed Folder Assistant to run, you can use the **Start-ManagedFolderAssistant** cmdlet to manually trigger the assistant to process the mailboxes that you applied the new retention policy to.</span></span> 
  
<span data-ttu-id="c5d93-212">Execute o comando a seguir para iniciar o Assistente de Pasta Gerenciada para caixa de correio de Clara Barbosa.</span><span class="sxs-lookup"><span data-stu-id="c5d93-212">Run the following command to start the Managed Folder Assistant for Pilar Pinilla's mailbox.</span></span>
  
```powershell
Start-ManagedFolderAssistant "Pilar Pinilla"
```

<span data-ttu-id="c5d93-213">Execute os comandos a seguir para iniciar o Assistente de Pasta Gerenciada para todas as caixas de correio em espera.</span><span class="sxs-lookup"><span data-stu-id="c5d93-213">Run the following commands to start the Managed Folder Assistant for all mailboxes on hold.</span></span>
  
```powershell
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```powershell
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a><span data-ttu-id="c5d93-214">Mais informações</span><span class="sxs-lookup"><span data-stu-id="c5d93-214">More information</span></span>

- <span data-ttu-id="c5d93-215">Após habilitar a caixa de correio de arquivo morto de um usuário, considere informar ao usuário que outros itens da sua caixa de correio (não apenas itens na pasta Itens Recuperáveis) podem ser movidos para a caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-215">After you enable a user's archive mailbox, consider telling the user that other items in their mailbox (not just items in the Recoverable Items folder) might be moved to the archive mailbox.</span></span> <span data-ttu-id="c5d93-216">Isso ocorre porque a política padrão do MRM atribuída às caixas de correio do Exchange Online contém uma marca de retenção (chamada padrão de dois anos mover para o arquivo morto) que move itens para a caixa de correio de arquivo morto dois anos após a data em que o item foi entregue à caixa de correio ou criado pelo utilizador.</span><span class="sxs-lookup"><span data-stu-id="c5d93-216">This is because the Default MRM Policy that's assigned to Exchange Online mailboxes contains a retention tag (named Default 2 years move to archive) that moves items to the archive mailbox two years after the date the item was delivered to the mailbox or created by the user.</span></span> <span data-ttu-id="c5d93-217">Para obter mais informações, consulte [Default Retention Policy in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span><span class="sxs-lookup"><span data-stu-id="c5d93-217">For more information, see [Default Retention Policy in Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkId=746954)</span></span>
    
- <span data-ttu-id="c5d93-218">Após habilitar a caixa de correio de arquivo morto de um usuário, você também pode informar ao usuário que ele pode recuperar itens excluídos na pasta Itens Recuperáveis na caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="c5d93-218">After you enable a user's archive mailbox, you might also tell the user that they can recover deleted items in the Recoverable Items folder in their archive mailbox.</span></span> <span data-ttu-id="c5d93-219">Eles podem fazer isso no Outlook selecionando a pasta **itens excluídos** na caixa de correio de arquivo morto e, em seguida, clicando em **recuperar itens excluídos do servidor** na guia **página inicial** . Para obter mais informações sobre a recuperação de itens excluídos, consulte [recuperar itens excluídos no Outlook para Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span><span class="sxs-lookup"><span data-stu-id="c5d93-219">They can do this in Outlook by selecting the **Deleted Items** folder in the archive mailbox, and then clicking **Recover Deleted Items from Server** on the **Home** tab. For more information about recovering deleted items, see [Recover deleted items in Outlook for Windows](https://go.microsoft.com/fwlink/p/?LinkId=624829).</span></span> 
