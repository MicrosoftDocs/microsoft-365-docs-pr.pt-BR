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
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910541"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="831c2-103">Restaurar um grupo excluído do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="831c2-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="831c2-104">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="831c2-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="831c2-105">Esse período de 30 dias é considerado uma "exclusão suave" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="831c2-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="831c2-106">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="831c2-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="831c2-107">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="831c2-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="831c2-108">Objeto, propriedades e membros do Microsoft 365 Groups do Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="831c2-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="831c2-109">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="831c2-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="831c2-110">Caixa de entrada e calendário compartilhados do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="831c2-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="831c2-111">Arquivos e sites de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="831c2-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="831c2-112">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="831c2-112">OneNote notebook</span></span>
    
- <span data-ttu-id="831c2-113">Planner</span><span class="sxs-lookup"><span data-stu-id="831c2-113">Planner</span></span>
    
- <span data-ttu-id="831c2-114">Teams</span><span class="sxs-lookup"><span data-stu-id="831c2-114">Teams</span></span>

- <span data-ttu-id="831c2-115">Conteúdo de grupo e grupo do Yammer (Se o grupo do Microsoft 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="831c2-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="831c2-116">Este artigo descreve a restauração apenas de grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="831c2-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="831c2-117">Todos os outros grupos não podem ser restaurados uma vez excluídos.</span><span class="sxs-lookup"><span data-stu-id="831c2-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="831c2-118">Restaurar um grupo</span><span class="sxs-lookup"><span data-stu-id="831c2-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="831c2-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="831c2-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="831c2-120">Se você for o proprietário de um grupo do Microsoft 365, poderá restaurar o grupo por conta própria no Outlook na Web seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="831c2-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="831c2-121">Na página [grupos excluídos,](https://outlook.office.com/people/group/deleted)selecione a opção **Gerenciar grupos** no nó **Grupos** e escolha **Excluído**.</span><span class="sxs-lookup"><span data-stu-id="831c2-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="831c2-122">Clique na guia **Restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="831c2-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="831c2-123">Se o grupo excluído não aparecer aqui, contate um administrador.</span><span class="sxs-lookup"><span data-stu-id="831c2-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="831c2-124">Centro de administração</span><span class="sxs-lookup"><span data-stu-id="831c2-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="831c2-125">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="831c2-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="831c2-126">Acesse o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="831c2-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="831c2-127">Expanda **Grupos** e clique em **Grupos Excluídos.**</span><span class="sxs-lookup"><span data-stu-id="831c2-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="831c2-128">Selecione o grupo que você deseja restaurar e clique em **Restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="831c2-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="831c2-129">Em alguns casos, pode levar até 24 horas para que o grupo e todos os seus dados sejam restaurados.</span><span class="sxs-lookup"><span data-stu-id="831c2-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="831c2-130">Tem dúvidas sobre grupos do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="831c2-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="831c2-131">Visite a [Comunidade do Microsoft Tech para](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) postar perguntas e participar de conversas sobre grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="831c2-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="831c2-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="831c2-132">Related articles</span></span>

[<span data-ttu-id="831c2-133">Gerenciar grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="831c2-133">Manage Microsoft 365 Groups with PowerShell</span></span>](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[<span data-ttu-id="831c2-134">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="831c2-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](/powershell/module/exchange/remove-unifiedgroup)
  
[<span data-ttu-id="831c2-135">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="831c2-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="831c2-136">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="831c2-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)