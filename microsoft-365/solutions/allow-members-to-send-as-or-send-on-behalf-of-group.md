---
title: Permitir que os membros enviem como ou enviem em nome de um grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Saiba como permitir que os membros do grupo enviem emails como um grupo do Microsoft 365 ou enviem emails em nome de um grupo do Microsoft 365.
ms.openlocfilehash: 44a0a7a690c8faa9fe00732e8154f36aa5a6fe6f
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727074"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="9102a-103">Permitir que os membros enviem como ou enviem em nome de um grupo</span><span class="sxs-lookup"><span data-stu-id="9102a-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="9102a-104">Um membro de um grupo do Microsoft 365  que recebeu permissões **Enviar** como ou Enviar em nome pode enviar emails como o grupo ou em nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="9102a-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="9102a-105">(Os convidados no grupo não podem receber essas permissões.)</span><span class="sxs-lookup"><span data-stu-id="9102a-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="9102a-106">Este artigo explica como um administrador global ou do Exchange pode definir essas permissões.</span><span class="sxs-lookup"><span data-stu-id="9102a-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="9102a-107">Por exemplo, se Megan Bowen faz parte do grupo Treinamento do **Microsoft** 365 e tem **Send** como permissões no  grupo, se ela enviar um email como o grupo, ele será parecido com o grupo de treinamento enviado pelo email.</span><span class="sxs-lookup"><span data-stu-id="9102a-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="9102a-108">A **permissão Enviar em Nome** permite que um usuário envie emails em nome de um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9102a-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="9102a-109">Por exemplo, se Alex Wilber faz parte do grupo **marketing** do Microsoft 365 e tem permissões **Enviar** em Nome e envia um email como o grupo, o email parece ter sido enviado por **Alex Wilber** em nome do Marketing .</span><span class="sxs-lookup"><span data-stu-id="9102a-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9102a-110">Você pode configurar **Enviar como** ou Enviar **em nome** de um determinado usuário, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="9102a-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="9102a-111">Se você configurar ambos, ele será padrão **para Enviar como**.</span><span class="sxs-lookup"><span data-stu-id="9102a-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="9102a-112">Consulte Enviar emails de ou em nome de um grupo do [Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para saber como usar o Outlook e o Outlook na Web para enviar emails de um grupo.</span><span class="sxs-lookup"><span data-stu-id="9102a-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="9102a-113">Permitir que os membros enviem emails como um grupo</span><span class="sxs-lookup"><span data-stu-id="9102a-113">Allow members to send email as a group</span></span>

<span data-ttu-id="9102a-114">Esta seção explica como permitir que os usuários enviem emails como um grupo no Centro de administração do [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9102a-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="9102a-115">No Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">de administração do Exchange,</a>vá para **Grupos de** \> **Destinatários**.</span><span class="sxs-lookup"><span data-stu-id="9102a-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="9102a-116">Selecione **Editar** ![ Editar ícone do grupo no grupo que você deseja permitir que os ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) usuários enviem como.  </span><span class="sxs-lookup"><span data-stu-id="9102a-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="9102a-117">Selecione **delegação de grupo**.</span><span class="sxs-lookup"><span data-stu-id="9102a-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="9102a-118">Na seção **Enviar como,** selecione o **+** sinal para adicionar os usuários que você deseja enviar como o Grupo.</span><span class="sxs-lookup"><span data-stu-id="9102a-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Captura de tela da caixa de diálogo enviar como](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="9102a-120">Digite para pesquisar ou escolher um usuário na lista.</span><span class="sxs-lookup"><span data-stu-id="9102a-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="9102a-121">Selecione **OK** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9102a-121">Select **OK** and **Save**.</span></span>
    
    ![Digite para pesquisar ou escolher um usuário na lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="9102a-123">Permitir que os membros enviem emails em nome de um grupo</span><span class="sxs-lookup"><span data-stu-id="9102a-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="9102a-124">Esta seção explica como permitir que os usuários enviem emails em nome de um grupo no Centro de administração do Exchange (EAC) no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9102a-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="9102a-125">No Centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">de administração do Exchange,</a>vá para **Grupos de** \> **Destinatários**.</span><span class="sxs-lookup"><span data-stu-id="9102a-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="9102a-126">Selecione **Editar** ![ Editar ícone do grupo no grupo que você deseja permitir que os ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) usuários enviem como.</span><span class="sxs-lookup"><span data-stu-id="9102a-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="9102a-127">Selecione **delegação de grupo**.</span><span class="sxs-lookup"><span data-stu-id="9102a-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="9102a-128">Na seção Enviar em Nome, selecione o sinal para adicionar **+** os usuários que você deseja enviar como o Grupo.</span><span class="sxs-lookup"><span data-stu-id="9102a-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Captura de tela de envio em nome da caixa de diálogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="9102a-130">Digite para pesquisar ou escolher um usuário na lista.</span><span class="sxs-lookup"><span data-stu-id="9102a-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="9102a-131">Selecione **OK** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9102a-131">Select **OK** and **Save**.</span></span>
    
    ![Digite para pesquisar ou escolher um usuário na lista](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="9102a-133">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="9102a-133">Related articles</span></span>

[<span data-ttu-id="9102a-134">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="9102a-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="9102a-135">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="9102a-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="9102a-136">Saiba mais sobre grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9102a-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="9102a-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="9102a-137">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="9102a-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="9102a-138">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
