---
title: Restaurar um grupo excluído do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Saiba como restaurar um grupo excluído do Microsoft 365.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753238"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="6f6ab-103">Restaurar um grupo excluído do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f6ab-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="6f6ab-104">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="6f6ab-105">Esse período de 30 dias é considerado uma "exclusão suave" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="6f6ab-106">Após 30 dias, o grupo e seu conteúdo associado serão excluídos permanentemente e não poderão ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="6f6ab-107">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="6f6ab-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="6f6ab-108">Objeto, propriedades e membros dos Grupos do Microsoft 365 do Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="6f6ab-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="6f6ab-109">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="6f6ab-110">Caixa de Entrada e calendário compartilhados do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="6f6ab-111">Arquivos e sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="6f6ab-112">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="6f6ab-112">OneNote notebook</span></span>
    
- <span data-ttu-id="6f6ab-113">Planner</span><span class="sxs-lookup"><span data-stu-id="6f6ab-113">Planner</span></span>
    
- <span data-ttu-id="6f6ab-114">Teams</span><span class="sxs-lookup"><span data-stu-id="6f6ab-114">Teams</span></span>

- <span data-ttu-id="6f6ab-115">Conteúdo de grupo e grupo do Yammer (se o grupo do Microsoft 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="6f6ab-116">Este artigo descreve a restauração apenas de grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="6f6ab-117">Todos os outros grupos não podem ser restaurados depois de excluídos.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="6f6ab-118">Restaurar um grupo</span><span class="sxs-lookup"><span data-stu-id="6f6ab-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="6f6ab-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="6f6ab-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="6f6ab-120">Se você for o proprietário de um grupo do Microsoft 365, poderá restaurar o grupo por conta própria no Outlook na Web seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6f6ab-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="6f6ab-121">Na página grupos [excluídos,](https://outlook.office.com/people/group/deleted)selecione a  **opção Gerenciar grupos** no nó Grupos e, em seguida, escolha **Excluído .**</span><span class="sxs-lookup"><span data-stu-id="6f6ab-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="6f6ab-122">Clique na guia **Restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="6f6ab-123">Se o grupo excluído não aparecer aqui, entre em contato com um administrador.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="6f6ab-124">Centro de administração</span><span class="sxs-lookup"><span data-stu-id="6f6ab-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="6f6ab-125">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no Centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="6f6ab-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="6f6ab-126">Acesse o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6f6ab-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="6f6ab-127">Expanda **Grupos** e clique em **Grupos Excluídos.**</span><span class="sxs-lookup"><span data-stu-id="6f6ab-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="6f6ab-128">Selecione o grupo que você deseja restaurar e clique em **Restaurar grupo.**</span><span class="sxs-lookup"><span data-stu-id="6f6ab-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="6f6ab-129">Em alguns casos, pode levar até 24 horas para que o grupo e todos os seus dados sejam restaurados.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="6f6ab-130">Tem dúvidas sobre os Grupos do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="6f6ab-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="6f6ab-131">Visite a [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f6ab-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="6f6ab-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6f6ab-132">Related articles</span></span>

[<span data-ttu-id="6f6ab-133">Gerenciar grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f6ab-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="6f6ab-134">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="6f6ab-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="6f6ab-135">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="6f6ab-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="6f6ab-136">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="6f6ab-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
