---
title: Restaurar um grupo excluído
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Saiba como restaurar um grupo do Microsoft 365 excluído.
ms.openlocfilehash: 870db3c92cd1f28f91540633a1dce9d0353c2b87
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049150"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="78fd1-103">Restaurar um grupo excluído</span><span class="sxs-lookup"><span data-stu-id="78fd1-103">Restore a deleted Group</span></span>

<span data-ttu-id="78fd1-104">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="78fd1-104">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="78fd1-105">Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="78fd1-105">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="78fd1-106">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="78fd1-106">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="78fd1-107">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="78fd1-107">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="78fd1-108">Azure Active Directory (AD) Microsoft 365 groups Object, Properties e Members.</span><span class="sxs-lookup"><span data-stu-id="78fd1-108">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="78fd1-109">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="78fd1-109">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="78fd1-110">Calendário e caixa de entrada compartilhada do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78fd1-110">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="78fd1-111">Arquivos e site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78fd1-111">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="78fd1-112">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="78fd1-112">OneNote notebook</span></span>
    
- <span data-ttu-id="78fd1-113">Planner</span><span class="sxs-lookup"><span data-stu-id="78fd1-113">Planner</span></span>
    
- <span data-ttu-id="78fd1-114">Teams</span><span class="sxs-lookup"><span data-stu-id="78fd1-114">Teams</span></span>

- <span data-ttu-id="78fd1-115">Grupo e conteúdo de grupo do Yammer (se o grupo Microsoft 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="78fd1-115">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook"></a><span data-ttu-id="78fd1-116">Restaurar um grupo que você possui usando o Outlook</span><span class="sxs-lookup"><span data-stu-id="78fd1-116">Restore a group that you own by using Outlook</span></span>

<span data-ttu-id="78fd1-117">Se você é o proprietário de um grupo do Microsoft 365, é possível restaurar o grupo em Outlook, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="78fd1-117">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook by following these steps:</span></span>

1. <span data-ttu-id="78fd1-118">Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.</span><span class="sxs-lookup"><span data-stu-id="78fd1-118">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="78fd1-119">Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="78fd1-119">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="78fd1-120">Se o grupo excluído não aparecer aqui, entre em contato com um administrador.</span><span class="sxs-lookup"><span data-stu-id="78fd1-120">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="78fd1-121">Restaurar um grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="78fd1-121">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="78fd1-122">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="78fd1-122">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="78fd1-123">Vá para o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="78fd1-123">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="78fd1-124">Expanda **grupos**e, em seguida, clique em **grupos excluídos**.</span><span class="sxs-lookup"><span data-stu-id="78fd1-124">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="78fd1-125">Selecione o grupo que você deseja restaurar e clique em **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="78fd1-125">Select the group that you want to restore, and then click **Restore group**.</span></span>
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="78fd1-126">Excluir permanentemente um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="78fd1-126">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="78fd1-127">Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire.</span><span class="sxs-lookup"><span data-stu-id="78fd1-127">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="78fd1-128">Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:</span><span class="sxs-lookup"><span data-stu-id="78fd1-128">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="78fd1-129">Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="78fd1-129">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="78fd1-130">Ao limpar o grupo, você removerá o grupo e os dados nele para sempre.</span><span class="sxs-lookup"><span data-stu-id="78fd1-130">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="78fd1-131">Para limpar o grupo, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="78fd1-131">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="78fd1-p103">Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="78fd1-p103">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="78fd1-134">Você tem dúvidas sobre os grupos da Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="78fd1-134">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="78fd1-135">Visite a [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78fd1-135">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="78fd1-136">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="78fd1-136">Related articles</span></span>

[<span data-ttu-id="78fd1-137">Gerenciar os grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="78fd1-137">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="78fd1-138">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="78fd1-138">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="78fd1-139">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="78fd1-139">Manage your group-connected team site settings</span></span>](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[<span data-ttu-id="78fd1-140">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="78fd1-140">Delete a group in Outlook</span></span>](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
