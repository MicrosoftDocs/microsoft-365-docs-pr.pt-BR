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
ms.openlocfilehash: 938d530447d1a798e5a2d6d4c2f622a04827bf1c
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529596"
---
# <a name="disposition-of-content"></a><span data-ttu-id="1dfeb-103">Disposição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="1dfeb-103">Disposition of content</span></span>

><span data-ttu-id="1dfeb-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="1dfeb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1dfeb-105">Use a guia **disposição** do **Gerenciamento de registros** no centro de conformidade da Microsoft 365 para gerenciar revisões de disposição e exibir [registros](records.md) que foram excluídos automaticamente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records.md) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="1dfeb-106">Pré-requisitos para exibir desposições de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1dfeb-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="1dfeb-107">Para gerenciar revisões de disposição e confirmar que os registros foram excluídos, você deve ter permissões suficientes e a auditoria deve estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="1dfeb-108">Permissões para descarte</span><span class="sxs-lookup"><span data-stu-id="1dfeb-108">Permissions for disposition</span></span>

<span data-ttu-id="1dfeb-109">Para acessar com êxito a guia de **descarte** no centro de conformidade do Microsoft 365, os usuários devem ter a função de **Gerenciamento de descarte** e a função de **logs de auditoria somente para exibição** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** role and the **View-Only Audit Logs** role.</span></span> <span data-ttu-id="1dfeb-110">Embora o Conselho padrão seja adicionar usuários aos grupos de função padrão, neste caso, recomendamos que você crie um novo grupo de função chamado **revisores de disposição** que tenha essas duas funções e adicione usuários a esse grupo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-110">Although the standard advice is to add users to the default role groups, in this case, we recommend you create a new role group called **Disposition Reviewers** that has these two roles and add users to this group as needed.</span></span> <span data-ttu-id="1dfeb-111">Um único grupo de função para descarte reduz a sobrecarga da administração e torna mais fácil para os usuários ter as permissões combinadas de que precisam.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-111">A single role group for disposition reduces administration overheads and makes it easier for users have the combined permissions that they need.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfeb-112">Até mesmo um administrador global precisa receber a função de **Gerenciamento de descarte** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-112">Even a global admin needs to be granted the **Disposition Management** role.</span></span> <span data-ttu-id="1dfeb-113">Portanto, se os administradores globais precisarem acessar a guia disposição, eles como membros do grupo de funções **revisores de descarte** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-113">So if global admins need to access the disposition tab, them as members of the **Disposition Reviewers** role group.</span></span> 

<span data-ttu-id="1dfeb-114">Específico para a função de **logs de auditoria somente para exibição** :</span><span class="sxs-lookup"><span data-stu-id="1dfeb-114">Specific to the **View-Only Audit Logs** role:</span></span>

- <span data-ttu-id="1dfeb-115">Como o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online, você deve atribuir essa função aos usuários usando o [centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), em vez de usar a página de **permissões** no centro de conformidade de segurança &.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-115">Because the underlying cmdlet used to search the audit log is an Exchange Online cmdlet, you must assign users this role by using the [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), rather than by using the **Permissions** page in the Security & Compliance Center.</span></span> <span data-ttu-id="1dfeb-116">Para obter instruções, consulte [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-116">For instructions, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="1dfeb-117">Os grupos do Microsoft 365 ([anteriormente Office 365 grupos](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa função.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-117">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) aren't supported for this role.</span></span> <span data-ttu-id="1dfeb-118">Em vez disso, atribua caixas de correio de usuário, usuários de email ou grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-118">Instead, assign user mailboxes, mail users, or mail-enabled security groups.</span></span>

<span data-ttu-id="1dfeb-119">Para obter instruções para conceder aos usuários a função de **Gerenciamento de descarte** e criar sua nova função de **revisores de disposição** , consulte [dar aos usuários acesso ao &amp; centro de conformidade de segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-119">For instructions to grant users the **Disposition Management** role and create your new **Disposition Reviewers** role, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="1dfeb-120">Habilitar a auditoria</span><span class="sxs-lookup"><span data-stu-id="1dfeb-120">Enable auditing</span></span>

<span data-ttu-id="1dfeb-121">Certifique-se de que a auditoria esteja habilitada pelo menos um dia antes da primeira ação de disposição.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-121">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="1dfeb-122">Para obter mais informações, consulte [Pesquisar o log de auditoria no centro de &amp; conformidade de segurança do Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-122">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="1dfeb-123">Revisões de disposição</span><span class="sxs-lookup"><span data-stu-id="1dfeb-123">Disposition reviews</span></span>

<span data-ttu-id="1dfeb-124">Quando o conteúdo atinge o final do período de retenção, há vários motivos para que você possa querer revisar o conteúdo para decidir se ele pode ser excluído com segurança ("descartado").</span><span class="sxs-lookup"><span data-stu-id="1dfeb-124">When content reaches the end of its retention period, there are several reasons why you might want to review that content to decide whether it can be safely deleted ("disposed").</span></span> <span data-ttu-id="1dfeb-125">Por exemplo, você pode precisar:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-125">For example, you might need to:</span></span>
  
- <span data-ttu-id="1dfeb-126">Suspender a exclusão de conteúdo relevante no caso de litígio ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-126">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>
    
- <span data-ttu-id="1dfeb-127">Remova o conteúdo da lista de descarte para armazenar em um arquivo morto, se esse conteúdo tiver um valor de pesquisa ou histórico.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-127">Remove content from the disposition list to store in an archive, if that content has research or historical value.</span></span>
    
- <span data-ttu-id="1dfeb-128">Atribua um período de retenção diferente ao conteúdo, talvez porque as configurações de retenção originais foram uma solução temporária ou provisionada.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-128">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>
    
- <span data-ttu-id="1dfeb-129">Retornar o conteúdo aos clientes ou transferi-lo para outra organização.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-129">Return the content to clients or transfer it to another organization.</span></span>

<span data-ttu-id="1dfeb-130">Quando uma revisão de disposição é disparada no final do período de retenção:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-130">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="1dfeb-131">As pessoas escolhidas recebem uma notificação por email de que o conteúdo deve ser revisado.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-131">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="1dfeb-132">Esses revisores podem ser usuários individuais, grupos de distribuição ou segurança ou grupos do Microsoft 365 ([anteriormente grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-132">These reviewers can be individual users, distribution or security groups, or Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)).</span></span> <span data-ttu-id="1dfeb-133">Observe que as notificações são enviadas semanalmente.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-133">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="1dfeb-134">Os revisores vão para a guia **disposição** no centro de conformidade da Microsoft 365 para analisar o conteúdo e decidir se ele será excluído permanentemente, estender o período de retenção ou aplicar um rótulo de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-134">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="1dfeb-135">Uma análise de disposição pode incluir conteúdo em caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-135">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="1dfeb-136">O conteúdo que está aguardando uma revisão de disposição nesses locais é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-136">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="1dfeb-137">Uma caixa de correio deve ter pelo menos 10 MB de dados para suportar revisões de disposição.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-137">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="1dfeb-138">Você pode ver uma visão geral de todas as desposições pendentes na guia **visão geral** . Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-138">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Desposições pendentes na visão geral do gerenciamento de registros](../media/dispositions-overview.png)

<span data-ttu-id="1dfeb-140">Ao selecionar a página **Exibir todas as reposições pendentes**, você será levado para a página de **disposição** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-140">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="1dfeb-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-141">For example:</span></span>

![Página de desposições no centro de conformidade do Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="1dfeb-143">Fluxo de trabalho para uma análise de disposição</span><span class="sxs-lookup"><span data-stu-id="1dfeb-143">Workflow for a disposition review</span></span>

<span data-ttu-id="1dfeb-144">O diagrama a seguir mostra o fluxo de trabalho básico para uma revisão de disposição quando um rótulo de retenção é publicado e, em seguida, aplicado manualmente por um usuário.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-144">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="1dfeb-145">Como alternativa, um rótulo de retenção configurado para uma revisão de disposição pode ser aplicado automaticamente ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-145">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico mostrando o fluxo de como o descarte funciona](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="1dfeb-147">O disparo de uma revisão de disposição no final do período de retenção é uma opção de configuração que está disponível apenas com um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-147">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="1dfeb-148">Essa opção não está disponível para uma política de retenção.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-148">This option is not available for a retention policy.</span></span> <span data-ttu-id="1dfeb-149">Para obter mais informações sobre essas duas soluções de retenção, consulte [saiba mais sobre políticas de retenção e rótulos de retenção](retention.md).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-149">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>
  
![Configurações de retenção para um rótulo](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> <span data-ttu-id="1dfeb-151">Quando você seleciona a opção **notificar essas pessoas quando há itens prontos para revisão**, especifique um usuário ou um grupo de segurança habilitado para email.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-151">When you select the option **Notify these people when there are items ready to review**, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="1dfeb-152">Os grupos do Microsoft 365 ([anteriormente Office 365 grupos](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa opção.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-152">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="1dfeb-153">Exibindo e descartando conteúdo</span><span class="sxs-lookup"><span data-stu-id="1dfeb-153">Viewing and disposing of content</span></span>

<span data-ttu-id="1dfeb-154">Quando um revisor é notificado por email que o conteúdo está pronto para revisão, ele vai para a guia **disposição** do **Gerenciamento de registros** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-154">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1dfeb-155">Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecione um rótulo de retenção para ver todo o conteúdo com esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-155">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="1dfeb-156">Depois de selecionar um rótulo de retenção, você verá todas as desposições pendentes para esse rótulo da guia **eliminação pendente** . Selecione um ou mais itens onde você pode escolher uma ação e inserir um comentário de justificativa:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-156">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opções de disposição](../media/retention-disposition-options.png)

<span data-ttu-id="1dfeb-158">Como você pode ver na imagem, as ações suportadas são:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-158">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="1dfeb-159">Excluir permanentemente o item</span><span class="sxs-lookup"><span data-stu-id="1dfeb-159">Permanently delete the item</span></span>
- <span data-ttu-id="1dfeb-160">Estender o período de retenção</span><span class="sxs-lookup"><span data-stu-id="1dfeb-160">Extend the retention period</span></span>
- <span data-ttu-id="1dfeb-161">Aplicar um rótulo de retenção diferente</span><span class="sxs-lookup"><span data-stu-id="1dfeb-161">Apply a different retention label</span></span>

<span data-ttu-id="1dfeb-162">Fornecendo permissões para o local e o conteúdo, você pode usar o link na coluna **local** para exibir documentos em seu local original.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-162">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="1dfeb-163">Durante uma revisão de disposição, o conteúdo nunca se move do local original e nunca é excluído até que o revisor opte por fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-163">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="1dfeb-164">As notificações por email são enviadas automaticamente para os revisores de forma semanal.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-164">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="1dfeb-165">Esse processo agendado significa que, quando o conteúdo atinge o final do período de retenção, pode levar até sete dias para que os revisores recebam a notificação de email de que o conteúdo está aguardando a eliminação.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-165">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="1dfeb-166">Todas as ações de disposição podem ser auditadas e o texto de justificativa inserido pelo revisor é salvo e exibido na coluna **Comentário** da página **itens descartados** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-166">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="1dfeb-167">Quanto tempo até o conteúdo Descartado é excluído permanentemente</span><span class="sxs-lookup"><span data-stu-id="1dfeb-167">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="1dfeb-168">O conteúdo que está aguardando uma análise de disposição é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-168">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="1dfeb-169">Quando o revisor escolhe essa opção, o conteúdo do site do SharePoint ou da conta do OneDrive fica qualificado para o processo de limpeza padrão descrito em [como as configurações de retenção funcionam com o conteúdo](retention.md#how-retention-settings-work-with-content-in-place)in-loco.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-169">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="1dfeb-170">Disposição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1dfeb-170">Disposition of records</span></span>

> [!NOTE]
><span data-ttu-id="1dfeb-171">A distribuição de provas de eliminação para registros no SharePoint e no OneDrive foi concluída.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-171">The rollout for proof of disposal for records in SharePoint and OneDrive is complete.</span></span> <span data-ttu-id="1dfeb-172">Você verá a lista de rótulos de retenção que marcou o conteúdo como registros do SharePoint e do OneDrive na seção disposição da página Gerenciamento de registros no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-172">You will see the list of retention labels that marked content as records for SharePoint and OneDrive in the Disposition section of the Records Management page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="1dfeb-173">Sob esses rótulos, você pode ver a lista de itens no SharePoint e no OneDrive que foram descartados automaticamente ou após uma revisão de disposição.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-173">Under these labels, you can see the list of items in SharePoint and OneDrive that were disposed automatically or after a disposition review.</span></span>

<span data-ttu-id="1dfeb-174">A prova de alienação de registros no Exchange ainda não está ativa.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-174">Proof of disposal for records in Exchange is not yet active.</span></span> <span data-ttu-id="1dfeb-175">Quando esta distribuição for iniciada e quando estiver concluída, atualizaremos esta nota.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-175">When this rollout begins and when it is complete, we will update this note.</span></span>

<span data-ttu-id="1dfeb-176">Use a guia **disposição** da página **Gerenciamento de registros** para identificar os registros excluídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-176">Use the **Disposition** tab from the **Records Management** page to identify records that are automatically deleted.</span></span> <span data-ttu-id="1dfeb-177">Estes itens exibem os **registros descartados** na coluna **tipo** .</span><span class="sxs-lookup"><span data-stu-id="1dfeb-177">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="1dfeb-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-178">For example:</span></span>

![Itens que foram descartados sem uma revisão de disposição](../media/records-disposed2.png)

<span data-ttu-id="1dfeb-180">Os itens que são mostrados na guia **itens descartados** para rótulos de registro são mantidos por até sete anos após o item ter sido descartado, com um limite de 1 milhão itens por registro para esse período.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-180">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="1dfeb-181">Se você vir o número de **contagem** perto desse limite de 1 milhão e precisar de uma prova de disposição para os seus registros, entre em contato com o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="1dfeb-181">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="1dfeb-182">Essa funcionalidade é baseada nas informações do [log de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) e, portanto, requer que a auditoria seja [habilitada e pesquisável](turn-audit-log-search-on-or-off.md) para que os eventos correspondentes sejam capturados.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-182">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>
    
## <a name="filter-and-export-the-views"></a><span data-ttu-id="1dfeb-183">Filtrar e exportar os modos de exibição</span><span class="sxs-lookup"><span data-stu-id="1dfeb-183">Filter and export the views</span></span>

<span data-ttu-id="1dfeb-184">Quando você seleciona um rótulo de retenção na página **disposição** , a guia de **disposição pendente** (se aplicável) e a guia **itens descartados** permitem filtrar os modos de exibição para ajudá-lo a localizar itens com mais facilidade.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-184">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="1dfeb-185">Para desposições pendentes, o intervalo de tempo é baseado na data de expiração.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-185">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="1dfeb-186">Para itens descartados, o intervalo de tempo é baseado na data de exclusão.</span><span class="sxs-lookup"><span data-stu-id="1dfeb-186">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="1dfeb-187">Você pode exportar informações sobre os itens em um modo de exibição como um arquivo. csv que você pode classificar e gerenciar usando o Excel:</span><span class="sxs-lookup"><span data-stu-id="1dfeb-187">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opção de exportação para descarte](../media/retention-export-option.png)
  
![Dados de disposição exportados no Excel](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)


