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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Saiba como restaurar um grupo do Microsoft 365 excluído.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818502"
---
# <a name="restore-a-deleted-group"></a><span data-ttu-id="aca89-103">Restaurar um grupo excluído</span><span class="sxs-lookup"><span data-stu-id="aca89-103">Restore a deleted Group</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="aca89-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="aca89-104">The admin center is changing.</span></span> <span data-ttu-id="aca89-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="aca89-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="aca89-106">Se você tiver excluído um grupo, ele será mantido por 30 dias por padrão.</span><span class="sxs-lookup"><span data-stu-id="aca89-106">If you've deleted a group, it will be retained for 30 days by default.</span></span> <span data-ttu-id="aca89-107">Este período de 30 dias é considerado uma "exclusão reversível" porque você ainda pode restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="aca89-107">This 30-day period is considered a "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="aca89-108">Após 30 dias, o grupo e seu conteúdo associado são excluídos permanentemente e não podem ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="aca89-108">After 30 days, the group and its associated contents are permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="aca89-109">Quando um grupo de é restaurado, o seguinte conteúdo é restaurado:</span><span class="sxs-lookup"><span data-stu-id="aca89-109">When a group is restored, the following content is restored:</span></span>
  
- <span data-ttu-id="aca89-110">Azure Active Directory (AD) Microsoft 365 groups Object, Properties e Members.</span><span class="sxs-lookup"><span data-stu-id="aca89-110">Azure Active Directory (AD) Microsoft 365 Groups object, properties, and members.</span></span>
    
- <span data-ttu-id="aca89-111">Endereços de email do grupo.</span><span class="sxs-lookup"><span data-stu-id="aca89-111">Group's e-mail addresses.</span></span>
    
- <span data-ttu-id="aca89-112">Calendário e caixa de entrada compartilhada do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="aca89-112">Exchange Online shared Inbox and calendar.</span></span>
    
- <span data-ttu-id="aca89-113">Arquivos e site de equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="aca89-113">SharePoint Online team site and files.</span></span>
    
- <span data-ttu-id="aca89-114">Bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="aca89-114">OneNote notebook</span></span>
    
- <span data-ttu-id="aca89-115">Planner</span><span class="sxs-lookup"><span data-stu-id="aca89-115">Planner</span></span>
    
- <span data-ttu-id="aca89-116">Teams</span><span class="sxs-lookup"><span data-stu-id="aca89-116">Teams</span></span>

- <span data-ttu-id="aca89-117">Grupo e conteúdo de grupo do Yammer (se o grupo Microsoft 365 foi criado a partir do Yammer)</span><span class="sxs-lookup"><span data-stu-id="aca89-117">Yammer group and group content (If the Microsoft 365 group was created from Yammer)</span></span>

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a><span data-ttu-id="aca89-118">Restaurar um grupo que você possui usando o Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="aca89-118">Restore a group that you own by using Outlook on the web</span></span>

<span data-ttu-id="aca89-119">Se você é o proprietário de um grupo do Microsoft 365, é possível restaurar o grupo sozinho no Outlook na Web seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="aca89-119">If you are the owner of a Microsoft 365 group, you can restore the group yourself in Outlook on the web by following these steps:</span></span>

1. <span data-ttu-id="aca89-120">Na [página grupos excluídos](https://outlook.office.com/people/group/deleted), selecione a opção **gerenciar grupos** no nó **grupos** e, em seguida, escolha **excluído**.</span><span class="sxs-lookup"><span data-stu-id="aca89-120">On the [deleted groups page](https://outlook.office.com/people/group/deleted), select the **Manage groups** option under the **Groups** node, and then choose **Deleted**.</span></span>

2. <span data-ttu-id="aca89-121">Clique na guia **restaurar** ao lado do grupo que você deseja restaurar.</span><span class="sxs-lookup"><span data-stu-id="aca89-121">Click on the **Restore** tab next to the group you want to restore.</span></span>

<span data-ttu-id="aca89-122">Se o grupo excluído não aparecer aqui, entre em contato com um administrador.</span><span class="sxs-lookup"><span data-stu-id="aca89-122">If the deleted group doesn't appear here, contact an administrator.</span></span>

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a><span data-ttu-id="aca89-123">Restaurar um grupo no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aca89-123">Restore a group in the Microsoft 365 admin center</span></span>

<span data-ttu-id="aca89-124">Se você for um administrador global ou um administrador de grupos, poderá restaurar um grupo excluído no centro de administração do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="aca89-124">If you are a global administrator or a groups administrator, you can restore a deleted group in the Microsoft 365 admin center:</span></span>

1. <span data-ttu-id="aca89-125">Vá para o [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="aca89-125">Go to the [admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="aca89-126">Expanda **grupos**e, em seguida, clique em **grupos excluídos**.</span><span class="sxs-lookup"><span data-stu-id="aca89-126">Expand **Groups**, and then click **Deleted groups**.</span></span>
3. <span data-ttu-id="aca89-127">Selecione o grupo que você deseja restaurar e clique em **restaurar grupo**.</span><span class="sxs-lookup"><span data-stu-id="aca89-127">Select the group that you want to restore, and then click **Restore group**.</span></span>

> [!NOTE]
> <span data-ttu-id="aca89-128">Em alguns casos, pode levar até 24 horas para o grupo e todos os seus dados a serem restaurados.</span><span class="sxs-lookup"><span data-stu-id="aca89-128">In some cases, it may take as long as 24 hours for the group and all of its data to be restored.</span></span> 
  
## <a name="permanently-delete-a-microsoft-365-group"></a><span data-ttu-id="aca89-129">Excluir permanentemente um grupo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aca89-129">Permanently delete a Microsoft 365 group</span></span>

<span data-ttu-id="aca89-130">Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire.</span><span class="sxs-lookup"><span data-stu-id="aca89-130">Sometimes you may want to permanently purge a group without waiting for the 30 day soft-deletion period to expire.</span></span> <span data-ttu-id="aca89-131">Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:</span><span class="sxs-lookup"><span data-stu-id="aca89-131">To do that, start PowerShell and run this command to get the object ID of the group:</span></span>
  
```
Get-AzureADMSDeletedGroup
```

<span data-ttu-id="aca89-132">Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="aca89-132">Take note of the object ID of the group, or groups, that you want to permanently delete.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="aca89-133">Ao limpar o grupo, você removerá o grupo e os dados nele para sempre.</span><span class="sxs-lookup"><span data-stu-id="aca89-133">Purging the group removes the group and its data forever.</span></span> 
  
<span data-ttu-id="aca89-134">Para limpar o grupo, execute o seguinte comando no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aca89-134">To purge the group run this command in PowerShell:</span></span>
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

<span data-ttu-id="aca89-p104">Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="aca89-p104">To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted.</span></span> 
  
## <a name="got-questions-about-microsoft-365-groups"></a><span data-ttu-id="aca89-137">Você tem dúvidas sobre os grupos da Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="aca89-137">Got questions about Microsoft 365 Groups?</span></span>

<span data-ttu-id="aca89-138">Visite a [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) para postar perguntas e participar de conversas sobre os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aca89-138">Visit the [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) to post questions and participate in conversations about Microsoft 365 groups.</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="aca89-139">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="aca89-139">Related articles</span></span>

[<span data-ttu-id="aca89-140">Gerenciar os grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="aca89-140">Manage Microsoft 365 Groups with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[<span data-ttu-id="aca89-141">Excluir grupos usando o cmdlet Remove-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="aca89-141">Delete groups using the Remove-UnifiedGroup cmdlet</span></span>](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[<span data-ttu-id="aca89-142">Gerenciar as configurações do site de equipe conectado ao grupo</span><span class="sxs-lookup"><span data-stu-id="aca89-142">Manage your group-connected team site settings</span></span>](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[<span data-ttu-id="aca89-143">Excluir um grupo no Outlook</span><span class="sxs-lookup"><span data-stu-id="aca89-143">Delete a group in Outlook</span></span>](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
