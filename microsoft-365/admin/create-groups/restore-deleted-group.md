---
title: Restaurar um grupo Microsoft 365 excluído
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
description: Um grupo excluído é mantido por 30 dias e você ainda pode restaurar o grupo. Após 30 dias, o grupo e seu conteúdo serão excluídos permanentemente.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635733"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="67ccb-104">Restaurar um grupo Microsoft 365 excluído</span><span class="sxs-lookup"><span data-stu-id="67ccb-104">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="67ccb-105">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="67ccb-105">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="67ccb-106">Esse período de 30 dias é considerado uma "exclusão suave" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="67ccb-106">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="67ccb-107">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="67ccb-107">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="67ccb-108">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="67ccb-108">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="67ccb-109">Azure Active Directory (AD) Microsoft 365 objeto Groups, propriedades e membros.</span><span class="sxs-lookup"><span data-stu-id="67ccb-109">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="67ccb-110">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="67ccb-110">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="67ccb-111">Exchange Online caixa de entrada compartilhada e calendário.</span><span class="sxs-lookup"><span data-stu-id="67ccb-111">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="67ccb-112">SharePoint Site e arquivos de equipe online.</span><span class="sxs-lookup"><span data-stu-id="67ccb-112">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="67ccb-113">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="67ccb-113">OneNote notebook</span></span>
    
- <span data-ttu-id="67ccb-114">Planner</span><span class="sxs-lookup"><span data-stu-id="67ccb-114">Planner</span></span>
    
- <span data-ttu-id="67ccb-115">Teams</span><span class="sxs-lookup"><span data-stu-id="67ccb-115">Teams</span></span>

- <span data-ttu-id="67ccb-116">Yammer conteúdo de grupo e grupo (se o grupo Microsoft 365 foi criado Yammer)</span><span class="sxs-lookup"><span data-stu-id="67ccb-116">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="67ccb-117">Este artigo descreve a restauração apenas Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="67ccb-117">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="67ccb-118">Todos os outros grupos não podem ser restaurados uma vez excluídos.</span><span class="sxs-lookup"><span data-stu-id="67ccb-118">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="67ccb-119">Restaurar um grupo</span><span class="sxs-lookup"><span data-stu-id="67ccb-119">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="67ccb-120">Outlook</span><span class="sxs-lookup"><span data-stu-id="67ccb-120">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="67ccb-121">Se você for o proprietário de um grupo de Microsoft 365, poderá restaurar o grupo sozinho Outlook na Web seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="67ccb-121">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="67ccb-122">Na página [grupos excluídos,](https://outlook.office.com/people/group/deleted)selecione a opção **Gerenciar grupos** no nó **Grupos** e escolha **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-122">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="67ccb-123">Clique na guia **Restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="67ccb-123">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="67ccb-124">Se o grupo excluído não aparecer aqui, contate um administrador.</span><span class="sxs-lookup"><span data-stu-id="67ccb-124">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="67ccb-125">Centro de administração</span><span class="sxs-lookup"><span data-stu-id="67ccb-125">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="67ccb-126">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no Microsoft 365 de administração:</span><span class="sxs-lookup"><span data-stu-id="67ccb-126">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="67ccb-127">Acesse o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="67ccb-127">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="67ccb-128">Expanda **Grupos** e clique em **Grupos Excluídos.**</span><span class="sxs-lookup"><span data-stu-id="67ccb-128">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="67ccb-129">Selecione o grupo que você deseja restaurar e clique em **Restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="67ccb-129">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="67ccb-130">Em alguns casos, pode levar até 24 horas para que o grupo e todos os seus dados sejam restaurados.</span><span class="sxs-lookup"><span data-stu-id="67ccb-130">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="67ccb-131">Tem perguntas sobre Microsoft 365 Grupos?</span><span class="sxs-lookup"><span data-stu-id="67ccb-131">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="67ccb-132">Visite o [microsoft tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="67ccb-132">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-content"></a><span data-ttu-id="67ccb-133">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="67ccb-133">Related content</span></span>

<span data-ttu-id="67ccb-134">[Gerenciar Microsoft 365 grupos com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="67ccb-134">[Manage Microsoft 365 Groups with PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (article)</span></span>\
<span data-ttu-id="67ccb-135">[Excluir grupos usando o cmdlet Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup) (artigo)</span><span class="sxs-lookup"><span data-stu-id="67ccb-135">[Delete groups using the Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (article)</span></span>\
<span data-ttu-id="67ccb-136">[Gerenciar suas configurações de site](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) de equipe conectadas ao grupo (artigo)</span><span class="sxs-lookup"><span data-stu-id="67ccb-136">[Manage your group-connected team site settings](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (article)</span></span>\
<span data-ttu-id="67ccb-137">[Excluir um grupo no Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artigo)</span><span class="sxs-lookup"><span data-stu-id="67ccb-137">[Delete a group in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (article)</span></span>