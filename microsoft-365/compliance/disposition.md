---
title: Disposição do conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitore e gerencie a eliminação de conteúdo, se você usar uma revisão de disposição ou se o conteúdo é excluído automaticamente de acordo com as configurações que você configurou.
ms.openlocfilehash: 07790175d56db9b82610b4882070a54ddce3d0c2
ms.sourcegitcommit: 8a15038a6ac16f41f6b90af52e367f888104cec9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44156886"
---
# <a name="disposition-of-content"></a><span data-ttu-id="22c76-103">Disposição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="22c76-103">Disposition of content</span></span>

><span data-ttu-id="22c76-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="22c76-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="22c76-105">Use a guia **disposição** do **Gerenciamento de registros** no centro de conformidade da Microsoft 365 para gerenciar revisões de disposição e exibir [registros](records.md) que foram excluídos automaticamente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="22c76-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="22c76-106">Pré-requisitos para exibir desposições de conteúdo</span><span class="sxs-lookup"><span data-stu-id="22c76-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="22c76-107">Para gerenciar revisões de disposição e confirmar que os registros foram excluídos, você deve ter permissões suficientes e a auditoria deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="22c76-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="22c76-108">Permissões para descarte</span><span class="sxs-lookup"><span data-stu-id="22c76-108">Permissions for disposition</span></span>

<span data-ttu-id="22c76-109">Para acessar com êxito a guia **disposição** no centro de conformidade da Microsoft 365, você deve ser membro da função de **Gerenciamento de descarte** e da função de logs de **auditoria somente para exibição** .</span><span class="sxs-lookup"><span data-stu-id="22c76-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, you must be members of the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="22c76-110">Recomendamos criar um novo grupo de função chamado **revisores de disposição**e adicionar essas duas funções a esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="22c76-110">We recommend creating a new role group called **Disposition Reviewers**, and add these two roles to that role group.</span></span> 

<span data-ttu-id="22c76-111">Específico para a função de **logs de auditoria somente para exibição** :</span><span class="sxs-lookup"><span data-stu-id="22c76-111">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="22c76-112">Como o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online, você deve atribuir essa função aos usuários usando o [centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), em vez de usar a página de **permissões** no centro de conformidade de segurança &.</span><span class="sxs-lookup"><span data-stu-id="22c76-112">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="22c76-113">Para obter instruções, consulte [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="22c76-113">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="22c76-114">Os grupos do Microsoft 365 ([anteriormente Office 365 grupos](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa função.</span><span class="sxs-lookup"><span data-stu-id="22c76-114">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="22c76-115">Em vez disso, atribua caixas de correio de usuário, usuários de email ou grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="22c76-115">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="22c76-116">Para obter instruções para conceder aos usuários a função de **Gerenciamento de descarte** e criar sua nova função de **revisores de disposição** , consulte [dar aos &amp; usuários acesso ao centro de conformidade de segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="22c76-116">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="22c76-117">Habilitar a auditoria</span><span class="sxs-lookup"><span data-stu-id="22c76-117">Enable auditing</span></span>

<span data-ttu-id="22c76-118">Certifique-se de que a auditoria esteja habilitada pelo menos um dia antes da primeira ação de disposição.</span><span class="sxs-lookup"><span data-stu-id="22c76-118">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="22c76-119">Para obter mais informações, consulte [Pesquisar o log de auditoria no centro de &amp; conformidade de segurança do Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="22c76-119">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="22c76-120">Revisões de disposição</span><span class="sxs-lookup"><span data-stu-id="22c76-120">Disposition reviews</span></span>

<span data-ttu-id="22c76-121">Quando o conteúdo atinge o final do período de retenção, há vários motivos para que você possa querer revisar o conteúdo para decidir se ele pode ser excluído com segurança ("descartado").</span><span class="sxs-lookup"><span data-stu-id="22c76-121">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="22c76-122">Por exemplo, você pode precisar:</span><span class="sxs-lookup"><span data-stu-id="22c76-122">For example, you might need to:</span></span>
  
- <span data-ttu-id="22c76-123">Suspender a exclusão de conteúdo relevante no caso de litígio ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="22c76-123">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="22c76-124">Remova o conteúdo da lista de descarte para armazenar em um arquivo morto, se esse conteúdo tiver um valor de pesquisa ou histórico.</span><span class="sxs-lookup"><span data-stu-id="22c76-124">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="22c76-125">Atribua um período de retenção diferente ao conteúdo, talvez porque as configurações de retenção originais foram uma solução temporária ou provisionada.</span><span class="sxs-lookup"><span data-stu-id="22c76-125">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="22c76-126">Retornar o conteúdo aos clientes ou transferi-lo para outra organização.</span><span class="sxs-lookup"><span data-stu-id="22c76-126">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="22c76-127">Quando uma revisão de disposição é disparada no final do período de retenção:</span><span class="sxs-lookup"><span data-stu-id="22c76-127">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="22c76-128">As pessoas escolhidas recebem uma notificação por email de que o conteúdo deve ser revisado.</span><span class="sxs-lookup"><span data-stu-id="22c76-128">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="22c76-129">Esses revisores podem ser usuários individuais, grupos de distribuição ou segurança ou grupos do Microsoft 365 ([anteriormente grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="22c76-129">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="22c76-130">Observe que as notificações são enviadas semanalmente.</span><span class="sxs-lookup"><span data-stu-id="22c76-130">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="22c76-131">Os revisores vão para a guia **disposição** no centro de conformidade da Microsoft 365 para analisar o conteúdo e decidir se ele será excluído permanentemente, estender o período de retenção ou aplicar um rótulo de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="22c76-131">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="22c76-132">Uma análise de disposição pode incluir conteúdo em caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="22c76-132">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="22c76-133">O conteúdo que está aguardando uma revisão de disposição nesses locais é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="22c76-133">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="22c76-134">Uma caixa de correio deve ter pelo menos 10 MB de dados para suportar revisões de disposição.</span><span class="sxs-lookup"><span data-stu-id="22c76-134">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="22c76-135">Você pode ver uma visão geral de todas as desposições pendentes na guia **visão geral** . Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22c76-135">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Desposições pendentes na visão geral do gerenciamento de registros](../media/dispositions-overview.png)

<span data-ttu-id="22c76-137">Ao selecionar a página **Exibir todas as reposições pendentes**, você será levado para a página de **disposição** .</span><span class="sxs-lookup"><span data-stu-id="22c76-137">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="22c76-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22c76-138">For example:</span></span>

![Página de desposições no centro de conformidade do Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="22c76-140">Fluxo de trabalho para uma análise de disposição</span><span class="sxs-lookup"><span data-stu-id="22c76-140">Workflow for a disposition review</span></span>

<span data-ttu-id="22c76-141">Este é o fluxo de trabalho básico para uma revisão de disposição quando um rótulo de retenção é publicado e, em seguida, aplicado manualmente por um usuário.</span><span class="sxs-lookup"><span data-stu-id="22c76-141">This is the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="22c76-142">Como alternativa, um rótulo de retenção configurado para uma revisão de disposição pode ser aplicado automaticamente ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="22c76-142">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico mostrando o fluxo de como o descarte funciona](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="22c76-144">O disparo de uma revisão de disposição no final do período de retenção é uma opção de configuração que está disponível apenas com um [rótulo de retenção](labels.md).</span><span class="sxs-lookup"><span data-stu-id="22c76-144">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a [retention label](labels.md).</span></span> <span data-ttu-id="22c76-145">Essa opção não está disponível em uma política de retenção.</span><span class="sxs-lookup"><span data-stu-id="22c76-145">This option is not available in a retention policy.</span></span>
  
![Configurações de retenção para um rótulo](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="22c76-147">Quando você seleciona a opção **notificar essas pessoas quando há itens prontos para revisão**, especifique um usuário ou um grupo de segurança habilitado para email.</span><span class="sxs-lookup"><span data-stu-id="22c76-147">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="22c76-148">Os grupos do Microsoft 365 ([anteriormente Office 365 grupos](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa opção.</span><span class="sxs-lookup"><span data-stu-id="22c76-148">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="22c76-149">Exibindo e descartando conteúdo</span><span class="sxs-lookup"><span data-stu-id="22c76-149">Viewing and disposing of content</span></span>

<span data-ttu-id="22c76-150">Quando um revisor é notificado por email que o conteúdo está pronto para revisão, ele vai para a guia **disposição** do **Gerenciamento de registros** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22c76-150">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="22c76-151">Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecione um rótulo de retenção para ver todo o conteúdo com esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="22c76-151">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="22c76-152">Depois de selecionar um rótulo de retenção, você verá todas as desposições pendentes para esse rótulo da guia **eliminação pendente** . Selecione um ou mais itens onde você pode escolher uma ação e inserir um comentário de justificativa:</span><span class="sxs-lookup"><span data-stu-id="22c76-152">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opções de disposição](../media/retention-disposition-options.png)

<span data-ttu-id="22c76-154">Como você pode ver na imagem, as ações suportadas são:</span><span class="sxs-lookup"><span data-stu-id="22c76-154">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="22c76-155">Excluir permanentemente o item</span><span class="sxs-lookup"><span data-stu-id="22c76-155">Permanently delete the item</span></span>
- <span data-ttu-id="22c76-156">Estender o período de retenção</span><span class="sxs-lookup"><span data-stu-id="22c76-156">Extend the retention period</span></span>
- <span data-ttu-id="22c76-157">Aplicar um rótulo de retenção diferente</span><span class="sxs-lookup"><span data-stu-id="22c76-157">Apply a different retention label</span></span>

<span data-ttu-id="22c76-158">Fornecendo permissões para o local e o conteúdo, você pode usar o link na coluna **local** para exibir documentos em seu local original.</span><span class="sxs-lookup"><span data-stu-id="22c76-158">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="22c76-159">Durante uma revisão de disposição, o conteúdo nunca se move do local original e nunca é excluído até que o revisor opte por fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="22c76-159">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="22c76-160">As notificações por email são enviadas automaticamente para os revisores de forma semanal.</span><span class="sxs-lookup"><span data-stu-id="22c76-160">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="22c76-161">Esse processo agendado significa que, quando o conteúdo atinge o final do período de retenção, pode levar até sete dias para que os revisores recebam a notificação de email de que o conteúdo está aguardando a eliminação.</span><span class="sxs-lookup"><span data-stu-id="22c76-161">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="22c76-162">Todas as ações de disposição podem ser auditadas e o texto de justificativa inserido pelo revisor é salvo e exibido na coluna **Comentário** da página **itens descartados** .</span><span class="sxs-lookup"><span data-stu-id="22c76-162">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="22c76-163">Quanto tempo até o conteúdo Descartado é excluído permanentemente</span><span class="sxs-lookup"><span data-stu-id="22c76-163">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="22c76-164">O conteúdo que está aguardando uma análise de disposição é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="22c76-164">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="22c76-165">Quando o revisor escolhe essa opção, o conteúdo do site do SharePoint ou da conta do OneDrive fica qualificado para o processo de limpeza padrão descrito em [como uma política de retenção funciona com o conteúdo](retention-policies.md#how-a-retention-policy-works-with-content-in-place)in-loco.</span><span class="sxs-lookup"><span data-stu-id="22c76-165">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How a retention policy works with content in place](retention-policies.md#how-a-retention-policy-works-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="22c76-166">Disposição de registros</span><span class="sxs-lookup"><span data-stu-id="22c76-166">Disposition of records</span></span>

> [!NOTE]
> <span data-ttu-id="22c76-167">A capacidade de ver os registros que foram excluídos automaticamente sem uma análise de descarte é descontínua para os locatários durante abril e maio de 2020, portanto, talvez você não veja essa experiência imediatamente.</span><span class="sxs-lookup"><span data-stu-id="22c76-167">The ability to see records that were automatically deleted without a disposition review is gradually rolling out to tenants during April and May 2020, so you might not see this experience immediately.</span></span>

<span data-ttu-id="22c76-168">Use a guia **disposição** da página **Gerenciamento de registros** para identificar os registros excluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="22c76-168">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="22c76-169">Estes itens exibem os **registros descartados** na coluna **tipo** .</span><span class="sxs-lookup"><span data-stu-id="22c76-169">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="22c76-170">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="22c76-170">For example:</span></span>

![Itens que foram descartados sem uma revisão de disposição](../media/records-disposed2.png)

<span data-ttu-id="22c76-172">Os itens que são mostrados na guia **itens descartados** para rótulos de registro são mantidos por até 7 anos após o item ter sido descartado, com um limite de 1 milhão itens por registro para esse período.</span><span class="sxs-lookup"><span data-stu-id="22c76-172">Items that are shown in the **Disposed Items** tab for record labels are kept for up to 7 years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="22c76-173">Se você vir o número de **contagem** perto desse limite de 1 milhão e precisar de uma prova de disposição para os seus registros, entre em contato com o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="22c76-173">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="22c76-174">Essa funcionalidade é baseada nas informações do [log de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) e, portanto, requer que a auditoria seja [habilitada e pesquisável](turn-audit-log-search-on-or-off.md) para que os eventos correspondentes sejam capturados.</span><span class="sxs-lookup"><span data-stu-id="22c76-174">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="22c76-175">Filtrar e exportar os modos de exibição</span><span class="sxs-lookup"><span data-stu-id="22c76-175">Filter and export the views</span></span>

<span data-ttu-id="22c76-176">Quando você seleciona um rótulo de retenção na página **disposição** , a guia de **disposição pendente** (se aplicável) e a guia **itens descartados** permitem filtrar os modos de exibição para ajudá-lo a localizar itens com mais facilidade.</span><span class="sxs-lookup"><span data-stu-id="22c76-176">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="22c76-177">Para desposições pendentes, o intervalo de tempo é baseado na data de expiração.</span><span class="sxs-lookup"><span data-stu-id="22c76-177">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="22c76-178">Para itens descartados, o intervalo de tempo é baseado na data de exclusão.</span><span class="sxs-lookup"><span data-stu-id="22c76-178">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="22c76-179">Você pode exportar informações sobre os itens em um modo de exibição como um arquivo. csv que você pode classificar e gerenciar usando o Excel:</span><span class="sxs-lookup"><span data-stu-id="22c76-179">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opção de exportação para descarte](../media/retention-export-option.png)
  
![Dados de disposição exportados no Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


