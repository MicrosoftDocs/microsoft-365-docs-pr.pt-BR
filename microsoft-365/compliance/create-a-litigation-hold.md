---
title: Criar uma Retenção de Litígio
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Saiba como colocar uma caixa de correio em Retenção de Litígio, mantendo todo o conteúdo da caixa de correio durante uma investigação.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 81d3bf7bba0aadbcd2d52b5f7707caeea96e26c1
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750055"
---
# <a name="create-a-litigation-hold"></a><span data-ttu-id="7f2cd-103">Criar uma Retenção de Litígio</span><span class="sxs-lookup"><span data-stu-id="7f2cd-103">Create a Litigation Hold</span></span>

<span data-ttu-id="7f2cd-104">Você pode colocar uma caixa de correio em Retenção de Litígio para reter todo o conteúdo da caixa de correio, incluindo itens excluídos e as versões originais de itens modificados.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-104">You can place a mailbox on Litigation Hold to retain all mailbox content, including deleted items and the original versions of modified items.</span></span> <span data-ttu-id="7f2cd-105">Quando você coloca uma caixa de correio de usuário em Contencioso, o conteúdo na caixa de correio de arquivo morto do usuário (se estiver habilitada) também será mantido.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-105">When you place a user mailbox on Litigation Hold, content in the user's archive mailbox (if it's enabled) is also retained.</span></span> <span data-ttu-id="7f2cd-106">Ao criar uma espera, você pode especificar uma duração de espera (também chamada de espera baseada em *tempo)* para que os itens excluídos e modificados sejam mantidos por um período especificado e excluídos permanentemente da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-106">When you create a hold, you can specify a hold duration (also called a *time-based hold*) so that deleted and modified items are retained for a specified period and then permanently deleted from the mailbox.</span></span> <span data-ttu-id="7f2cd-107">Ou você pode manter o conteúdo indefinidamente (chamado de retenção infinita *)* ou até que a Retenção de Litígio seja removida.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-107">Or you can just retain content indefinitely (called an *infinite hold*) or until the Litigation Hold is removed.</span></span> <span data-ttu-id="7f2cd-108">Se você especificar um período de duração de espera, ele será calculado a partir da data em que uma mensagem é recebida ou um item de caixa de correio é criado.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-108">If you do specify a hold duration period, it's calculated from the date a message is received or a mailbox item is created.</span></span> 
  
<span data-ttu-id="7f2cd-109">Veja o que acontece quando você cria um Litígio.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-109">Here's what happens when you create a Litigation Hold.</span></span>
  
- <span data-ttu-id="7f2cd-110">Os itens excluídos permanentemente pelo usuário são mantidos na pasta Itens Recuperáveis na caixa de correio do usuário durante a espera.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-110">Items that are permanently deleted by the user are retained in the Recoverable Items folder in the user's mailbox for the duration of the hold.</span></span>

- <span data-ttu-id="7f2cd-111">Os itens que são limpos da pasta Itens Recuperáveis pelo usuário são mantidos durante a espera.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-111">Items that are purged from the Recoverable Items folder by the user are retained for the duration of the hold.</span></span>

- <span data-ttu-id="7f2cd-112">A cota de armazenamento para a pasta Itens Recuperáveis é aumentada de 30 GB para 110 GB.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-112">The storage quota for the Recoverable Items folder is increased from 30 GB to 110 GB.</span></span>

- <span data-ttu-id="7f2cd-113">Os itens nas caixas de correio primárias e de arquivo morto do usuário são mantidos</span><span class="sxs-lookup"><span data-stu-id="7f2cd-113">Items in the user's primary and the archive mailboxes are retained</span></span>

## <a name="assign-an-exchange-online-plan-2-license"></a><span data-ttu-id="7f2cd-114">Atribuir uma licença Exchange Online Plano 2</span><span class="sxs-lookup"><span data-stu-id="7f2cd-114">Assign an Exchange Online Plan 2 license</span></span>

<span data-ttu-id="7f2cd-115">Para colocar uma caixa de correio Exchange Online de litígio em Contencioso, ela deve receber uma licença Exchange Online Plano 2.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-115">To place an Exchange Online mailbox on Litigation Hold, it must be assigned an Exchange Online Plan 2 license.</span></span> <span data-ttu-id="7f2cd-116">Se uma caixa de correio receber uma licença Exchange Online Plano 1, você terá que atribuí-la uma licença de Arquivamento do Exchange Online separada para mantê-la em espera.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-116">If a mailbox is assigned an Exchange Online Plan 1 license, you would have to assign it a separate Exchange Online Archiving license to place it on hold.</span></span>

> [!NOTE]
> <span data-ttu-id="7f2cd-117">Para Office 365 Education organizações, a responsabilidade por litígio é suportada em assinaturas Office 365 A1, que incluem uma licença Exchange Online Plano 1 com recursos complementares.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-117">For Office 365 Education organizations, Litigation Hold is supported in Office 365 A1 subscriptions, which include an Exchange Online Plan 1 license with supplemental features.</span></span> <span data-ttu-id="7f2cd-118">Para obter mais informações, consulte a seção "Exchange Online recursos" na descrição [Office 365 Education serviço.](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features)</span><span class="sxs-lookup"><span data-stu-id="7f2cd-118">For more information, see the "Exchange Online features" section in the [Office 365 Education service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-education#exchange-online-features).</span></span>

## <a name="place-a-mailbox-on-litigation-hold"></a><span data-ttu-id="7f2cd-119">Colocar uma caixa de correio em Retenção de Litígio</span><span class="sxs-lookup"><span data-stu-id="7f2cd-119">Place a mailbox on Litigation Hold</span></span>

<span data-ttu-id="7f2cd-120">Aqui estão as etapas para colocar uma caixa de correio em Responsabilidade de Litígio usando o Exchange de administração.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-120">Here are the steps to place a mailbox on Litigation Hold using the Exchange admin center.</span></span>

1. <span data-ttu-id="7f2cd-121">Acesse e [https://outlook.office.com/ecp](https://outlook.office.com/ecp) entre usando sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-121">Go to [https://outlook.office.com/ecp](https://outlook.office.com/ecp) and sign in using your global administrator account.</span></span>

2. <span data-ttu-id="7f2cd-122">Clique **em Destinatários > Caixas de** Correio no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-122">Click **Recipients > Mailboxes** in the left navigation pane.</span></span>

3. <span data-ttu-id="7f2cd-123">Selecione a caixa de correio que você deseja colocar em Contencioso e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-123">Select the mailbox that you want to place on Litigation Hold, and then click **Edit**.</span></span>

4. <span data-ttu-id="7f2cd-124">Na página de propriedades da caixa de correio, clique em **Recursos da Caixa de Correio**.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-124">On the mailbox properties page, click **Mailbox features**.</span></span>
    
5. <span data-ttu-id="7f2cd-125">Em **Retenção de Litígio: Desativado**, clique em **Habilitar** para colocar a caixa de correio em Retenção de Litígio.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-125">Under **Litigation hold: Disabled**, click **Enable** to place the mailbox on Litigation Hold.</span></span>
    
6. <span data-ttu-id="7f2cd-126">Na página **De espera de** litígio, insira as seguintes informações opcionais:</span><span class="sxs-lookup"><span data-stu-id="7f2cd-126">On the **Litigation hold** page, enter the following optional information:</span></span> 
    
    - <span data-ttu-id="7f2cd-127">**Duração de espera de litígio (dias)** - Use essa caixa para criar uma hold baseada em tempo e especificar por quanto tempo os itens de caixa de correio são mantidos quando a caixa de correio é colocada em Contencioso.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-127">**Litigation hold duration (days)** - Use this box to create a time-based hold and specify how long mailbox items are held when the mailbox is placed on Litigation Hold.</span></span> <span data-ttu-id="7f2cd-128">A duração é calculada a partir da data em que um item de caixa de correio é recebido ou criado.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-128">The duration is calculated from the date a mailbox item is received or created.</span></span> <span data-ttu-id="7f2cd-129">Quando a duração da espera expirar para um item específico, esse item não será mais preservado.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-129">When the hold duration expires for a specific item, that item will no longer be preserved.</span></span> <span data-ttu-id="7f2cd-130">Se você deixar essa caixa em branco, os itens serão preservados indefinidamente ou até que a espera seja removida.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-130">If you leave this box blank, items are preserved indefinitely or until the hold is removed.</span></span> <span data-ttu-id="7f2cd-131">Use dias para especificar a duração.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-131">Use days to specify the duration.</span></span>
    
    - <span data-ttu-id="7f2cd-132">**Observação** - Use esta caixa para informar ao usuário que sua caixa de correio está em Contencioso.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-132">**Note** - Use this box to inform the user their mailbox is on Litigation Hold.</span></span> <span data-ttu-id="7f2cd-133">A observação aparecerá na página Informações da Conta na caixa de correio do usuário se estiver usando Outlook 2010 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-133">The note will appear on the Account Information page in the user's mailbox if they're using Outlook 2010 or later.</span></span> <span data-ttu-id="7f2cd-134">Para acessar esta página, os usuários podem clicar **em Arquivo** em Outlook.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-134">To access this page, users can click **File** in Outlook.</span></span>
    
    - <span data-ttu-id="7f2cd-135">**URL** - Use essa caixa para direcionar o usuário para um site para obter mais informações sobre a responsabilidade por litígio.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-135">**URL** - Use this box to direct the user to a website for more information about Litigation Hold.</span></span> <span data-ttu-id="7f2cd-136">Essa URL será exibida na página Informações da Conta na caixa de correio do usuário se estiver usando Outlook 2010 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-136">This URL appears on the Account Information page in the user's mailbox if they are using Outlook 2010 or later.</span></span> <span data-ttu-id="7f2cd-137">Para acessar esta página, os usuários podem clicar **em Arquivo** em Outlook..</span><span class="sxs-lookup"><span data-stu-id="7f2cd-137">To access this page, users can click **File** in Outlook..</span></span>

7. <span data-ttu-id="7f2cd-138">Clique **em Salvar** na página De espera **de** litígio e clique em **Salvar** na página propriedades da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-138">Click **Save** on the **Litigation hold** page, and then click **Save** on the mailbox properties page.</span></span>

### <a name="create-a-litigation-hold-using-powershell"></a><span data-ttu-id="7f2cd-139">Criar uma hold de litígio usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="7f2cd-139">Create a Litigation Hold using PowerShell</span></span>

<span data-ttu-id="7f2cd-140">Você também pode criar uma Hold de Litígio executando o seguinte comando [em Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="7f2cd-140">You can also create a Litigation Hold by running the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

<span data-ttu-id="7f2cd-141">O comando anterior preserva os itens indefinidamente porque a duração da espera não é especificada.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-141">The previous command preserves items indefinitely because the hold duration isn't specified.</span></span> <span data-ttu-id="7f2cd-142">Para criar uma espera baseada em tempo, usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7f2cd-142">To create a time-based hold, using the following command:</span></span>

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

<span data-ttu-id="7f2cd-143">Para obter mais informações, consulte [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="7f2cd-143">For more information, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

## <a name="how-does-litigation-hold-work"></a><span data-ttu-id="7f2cd-144">Como funciona a retenção de litígio?</span><span class="sxs-lookup"><span data-stu-id="7f2cd-144">How does Litigation Hold work?</span></span>

<span data-ttu-id="7f2cd-145">No fluxo de trabalho normal de item excluído, um item de caixa de correio é movido para a subpasta Exclusões na pasta Itens recuperáveis quando um usuário o excluir permanentemente (Shift + Delete) ou o excluir da pasta Itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-145">In the normal deleted item workflow, a mailbox item is moved to the Deletions subfolder in the Recoverable Items folder when a user permanently deletes it (Shift + Delete) or deletes it from the Deleted Items folder.</span></span> <span data-ttu-id="7f2cd-146">Uma política de exclusão (que é uma marca de retenção configurada com uma ação de retenção de exclusão) também move itens para a subpasta Exclusões quando o período de retenção expira.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-146">A deletion policy (which is a retention tag configured with a Delete retention action) also moves items to the Deletions subfolder when the retention period expires.</span></span> <span data-ttu-id="7f2cd-147">Quando um usuário descarta um item da pasta Itens recuperáveis ou quando o período de retenção do item excluído expira para um item, ele é movido para a subpasta Exclusões na pasta Itens recuperáveis e marcado para exclusão permanente.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-147">When a user purges an item in the Recoverable Items folder or when the deleted item retention period expires for an item, it's moved to the Purges subfolder in the Recoverable Items folder and marked for permanent deletion.</span></span> <span data-ttu-id="7f2cd-148">Ele será excluído do Exchange na próxima vez em que a caixa de correio for processada pelo Assistente de Pasta Gerenciada (MFA).</span><span class="sxs-lookup"><span data-stu-id="7f2cd-148">It will be purged from Exchange the next time the mailbox is processed by the Managed Folder Assistant (MFA).</span></span>

<span data-ttu-id="7f2cd-p109">Quando uma caixa de correio é colocada em retenção de litígio, os itens na subpasta Exclusões são preservados durante o período especificado pela retenção de litígio. A duração da retenção é calculada a partir da data original em que um item foi recebido ou criado e define por quanto tempo os itens na subpasta Exclusões são retidos. Quando expira o período de retenção de um item na subpasta Exclusões, o item é marcado para exclusão permanente e é excluído da Exchange na próxima vez em que a caixa de correio for processada pelo MFA. Se uma caixa de correio for colocada em retenção indefinida, os itens nunca serão excluídos da subpasta Exclusões.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-p109">When a mailbox is placed on Litigation Hold, items in the Purges subfolder are preserved for the hold duration specified by the Litigation Hold. The hold duration is calculated from the original date an item was received or created, and defines how long items in the Purges subfolder are held. When the hold duration expires for an item in the Purges subfolder, the item is marked for permanent deletion and will be purged from Exchange the next time the mailbox is processed by the MFA. If an indefinite hold is placed on a mailbox, items will never be purged from the Purges subfolder.</span></span>

<span data-ttu-id="7f2cd-153">A imagem a seguir mostra as subpastas nas pastas Itens Recuperáveis e o processo de fluxo de trabalho de retenção.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-153">The following illustration shows the subfolders in the Recoverable Items folders and the hold workflow process.</span></span>

![Ciclo de vida de hold de litígio](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> <span data-ttu-id="7f2cd-155">Se uma isenção associada a uma ocorrência de Descoberta Eletrônico for colocada em uma caixa de correio, os itens limpos serão movidos da subpasta Deletions para a subpasta DiscoveryHolds e serão preservados até que a caixa de correio seja liberada da espera de Descoberta Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7f2cd-155">If a hold associated with an eDiscovery case is placed on a mailbox, purged items are moved from the Deletions subfolder to the DiscoveryHolds subfolder and are preserved until the mailbox is released from the eDiscovery hold.</span></span>
