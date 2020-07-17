---
title: Permitir que os membros enviem como ou enviem em nome de um grupo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Saiba como permitir que os membros enviem email como um grupo do Microsoft 365 ou enviem email em nome de um grupo do Microsoft 365.
ms.openlocfilehash: 090a5e177ed843c035155cd735e0b7b9560e5631
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844663"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="ab3ab-103">Permitir que os membros enviem como ou enviem em nome de um grupo</span><span class="sxs-lookup"><span data-stu-id="ab3ab-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="ab3ab-104">Um membro de um grupo do Microsoft 365 que tenha recebido as permissões **Enviar como** ou **enviar em nome** de pode enviar emails como o grupo ou em nome do grupo.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="ab3ab-105">Este tópico explica como um administrador pode definir essas permissões.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="ab3ab-106">Por exemplo, se Megan Bowen fizer parte do grupo **Training** Microsoft 365, e tiver permissões **Send** as no grupo, se ele enviar um email como o grupo, será parecido com o grupo de **treinamento** enviado por email.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="ab3ab-107">A permissão **enviar em nome** de permite que um usuário envie um email em nome de um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="ab3ab-108">Por exemplo, se Alex Wilber é parte do grupo **marketing** da Microsoft 365 e tem permissões **de enviar em nome** de e envia um email como grupo, o email parece que foi enviado por **Alex Wilber em nome de marketing**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab3ab-109">Você pode configurar **Enviar como** ou **enviar em nome** de um determinado usuário, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="ab3ab-110">Se você configurar ambos, o padrão será **Enviar como**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="ab3ab-111">Consulte [Enviar email de ou em nome de um grupo do Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) para saber como usar o Outlook e o Outlook na Web para enviar emails de um grupo.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="ab3ab-112">Permitir que os membros enviem email como um grupo</span><span class="sxs-lookup"><span data-stu-id="ab3ab-112">Allow members to send email as a group</span></span>

<span data-ttu-id="ab3ab-113">Esta seção explica como permitir que os usuários enviem emails como um grupo no [centro de administração do Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (Eat) no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ab3ab-114">No <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administração do Exchange</a>, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ab3ab-115">Selecione **Editar** ![ ícone de grupo ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) no grupo para o qual você deseja permitir que os usuários enviem.  </span><span class="sxs-lookup"><span data-stu-id="ab3ab-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ab3ab-116">Selecione **delegação de grupo**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ab3ab-117">Na seção **Enviar como** , selecione o **+** sinal para adicionar os usuários que você deseja enviar como o grupo.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecione o sinal de adição para adicionar os usuários que você deseja enviar como o grupo do Microsoft 365](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="ab3ab-119">Digite para pesquisar ou selecionar um usuário da lista.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ab3ab-120">Selecione **OK** e **salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-120">Select **OK** and **Save**.</span></span>
    
    ![Digite para pesquisar ou selecionar um usuário na lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="ab3ab-122">Permitir que os membros enviem email em nome de um grupo</span><span class="sxs-lookup"><span data-stu-id="ab3ab-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="ab3ab-123">Esta seção explica como permitir que os usuários enviem emails em nome de um grupo no centro de administração do Exchange (Eat) no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="ab3ab-124">No <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">centro de administração do Exchange</a>, vá para grupos de **destinatários** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="ab3ab-125">Selecione **Editar** ![ ícone de grupo ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) no grupo para o qual você deseja permitir que os usuários enviem.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="ab3ab-126">Selecione **delegação de grupo**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="ab3ab-127">Na seção enviar em nome de, selecione o **+** sinal para adicionar os usuários que você deseja enviar como o grupo.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selecione o sinal de adição para adicionar os usuários que você deseja enviar como o grupo do Microsoft 365](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="ab3ab-129">Digite para pesquisar ou selecionar um usuário da lista.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="ab3ab-130">Selecione **OK** e **salvar**.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-130">Select **OK** and **Save**.</span></span>
    
    ![Digite para pesquisar ou selecionar um usuário na lista](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
    
> [!NOTE]
> <span data-ttu-id="ab3ab-132">Pode levar até duas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="ab3ab-132">It may take up to two hours for changes to take effect.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ab3ab-133">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="ab3ab-133">Related articles</span></span>

[<span data-ttu-id="ab3ab-134">Saiba mais sobre os grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ab3ab-134">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="ab3ab-135">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="ab3ab-135">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="ab3ab-136">Conjunto-unificado</span><span class="sxs-lookup"><span data-stu-id="ab3ab-136">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
