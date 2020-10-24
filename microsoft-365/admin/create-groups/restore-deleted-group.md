---
title: Restaurar um grupo do Microsoft 365 excluído
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
description: Saiba como restaurar um grupo do Microsoft 365 excluído.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753238"
---
# <a name="restore-a-deleted-microsoft-365-group"></a><span data-ttu-id="117d3-103">Restaurar um grupo do Microsoft 365 excluído</span><span class="sxs-lookup"><span data-stu-id="117d3-103">Restore a deleted Microsoft 365 group</span></span>

<span data-ttu-id="117d3-104">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="117d3-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="117d3-105">Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="117d3-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="117d3-106">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="117d3-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="117d3-107">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="117d3-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="117d3-108">Azure Active Directory (AD) Microsoft 365 groups Object, Properties e Members.</span><span class="sxs-lookup"><span data-stu-id="117d3-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="117d3-109">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="117d3-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="117d3-110">Calendário e caixa de entrada compartilhada do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="117d3-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="117d3-111">Arquivos e site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="117d3-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="117d3-112">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="117d3-112">OneNote notebook</span></span>
    
- <span data-ttu-id="117d3-113">Planner</span><span class="sxs-lookup"><span data-stu-id="117d3-113">Planner</span></span>
    
- <span data-ttu-id="117d3-114">Teams</span><span class="sxs-lookup"><span data-stu-id="117d3-114">Teams</span></span>

- <span data-ttu-id="117d3-115">Grupo e conteúdo de grupo do Yammer (se o grupo Microsoft 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="117d3-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

> [!NOTE]
> <span data-ttu-id="117d3-116">Este artigo descreve a restauração somente de grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="117d3-116">This article describes restoring only Microsoft 365 groups.</span></span> <span data-ttu-id="117d3-117">Todos os outros grupos não podem ser restaurados depois de excluídos.</span><span class="sxs-lookup"><span data-stu-id="117d3-117">All other groups cannot be restored once deleted.</span></span>

## <a name="restore-a-group"></a><span data-ttu-id="117d3-118">Restaurar um grupo</span><span class="sxs-lookup"><span data-stu-id="117d3-118">Restore a group</span></span>

# <a name="outlook"></a>[<span data-ttu-id="117d3-119">Outlook</span><span class="sxs-lookup"><span data-stu-id="117d3-119">Outlook</span></span>](#tab/outlook)

<span data-ttu-id="117d3-120">Se você é o proprietário de um grupo do Microsoft 365, é possível restaurar o grupo sozinho no Outlook na Web seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="117d3-120">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="117d3-121">Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.</span><span class="sxs-lookup"><span data-stu-id="117d3-121">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="117d3-122">Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="117d3-122">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="117d3-123">Se o grupo excluído não aparecer aqui, entre em contato com um administrador.</span><span class="sxs-lookup"><span data-stu-id="117d3-123">If the deleted group doesn't appear here, contact an administrator.</span></span>

# <a name="admin-center"></a>[<span data-ttu-id="117d3-124">Centro de administração</span><span class="sxs-lookup"><span data-stu-id="117d3-124">Admin center</span></span>](#tab/admin-center)

<span data-ttu-id="117d3-125">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="117d3-125">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="117d3-126">Acesse o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="117d3-126">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="117d3-127">Expanda **grupos**e, em seguida, clique em **grupos excluídos**.</span><span class="sxs-lookup"><span data-stu-id="117d3-127">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="117d3-128">Selecione o grupo que você deseja restaurar e clique em **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="117d3-128">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="117d3-129">Em alguns casos, pode levar até 24 horas para o grupo e todos os seus dados a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="117d3-129">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 

---

## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="117d3-130">Você tem dúvidas sobre os grupos da Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="117d3-130">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="117d3-131">Visite a [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="117d3-131">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="117d3-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="117d3-132">Related articles</span></span>

[<span data-ttu-id="117d3-133">Gerenciar os grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="117d3-133">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[<span data-ttu-id="117d3-134">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="117d3-134">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="117d3-135">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="117d3-135">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="117d3-136">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="117d3-136">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
