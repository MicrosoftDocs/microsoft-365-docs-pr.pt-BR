---
title: Disposição de conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitore e gerencie a disposição do conteúdo, se você usa uma revisão de disposição ou o conteúdo é excluído automaticamente de acordo com as configurações definidas.
ms.openlocfilehash: d9786b5e93801153e168784d51e37a00ee1822bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051923"
---
# <a name="disposition-of-content"></a><span data-ttu-id="5a88c-103">Disposição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="5a88c-103">Disposition of content</span></span>

><span data-ttu-id="5a88c-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="5a88c-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="5a88c-105">Use a guia **Disposição** do **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365 para gerenciar análises de disposição e exibir [registros](records-management.md#records) que foram excluídos automaticamente no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="5a88c-105">Use the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center to manage disposition reviews and view [records](records-management.md#records) that have been automatically deleted at the end of their retention period.</span></span> 

## <a name="prerequisites-for-viewing-content-dispositions"></a><span data-ttu-id="5a88c-106">Pré-requisitos para exibir disposições de conteúdo</span><span class="sxs-lookup"><span data-stu-id="5a88c-106">Prerequisites for viewing content dispositions</span></span>

<span data-ttu-id="5a88c-107">Para gerenciar as revisões de disposição e confirmar que os registros foram excluídos, você deve ter permissões suficientes e a auditoria deve ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="5a88c-107">To manage disposition reviews and confirm that records have been deleted, you must have sufficient permissions and auditing must be enabled.</span></span>

### <a name="permissions-for-disposition"></a><span data-ttu-id="5a88c-108">Permissões para disposição</span><span class="sxs-lookup"><span data-stu-id="5a88c-108">Permissions for disposition</span></span>

<span data-ttu-id="5a88c-109">Para acessar a guia **Disposição** no Centro de conformidade do Microsoft 365, os usuários devem ter função de administrador **Gerenciamento de disposição**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-109">To successfully access the **Disposition** tab in the Microsoft 365 compliance center, users must have the **Disposition Management** admin role.</span></span> <span data-ttu-id="5a88c-110">A partir de dezembro de 2020, esta função está incluída no grupo de função de administrador padrão **Gerenciamento de Registros**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-110">From December 2020, this role is now included in the **Records Management** default admin role group.</span></span>

> [!NOTE]
> <span data-ttu-id="5a88c-111">Por padrão, até mesmo um administrador global precisa ter a função de **Gerenciamento de Disposição**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-111">By default, a global admin isn't granted the **Disposition Management** role.</span></span> 

<span data-ttu-id="5a88c-112">Para conceder aos usuários apenas as permissões necessárias para revisões de disposição sem conceder permissões para exibir e configurar outros recursos para gerenciamento de retenção e de registros, crie um grupo de função personalizada (por exemplo, chamado "Revisores de Disposição") e conceda a esse grupo a função de Gerenciamento de Disposição.</span><span class="sxs-lookup"><span data-stu-id="5a88c-112">To grant users just the permissions they need for disposition reviews without granting them permissions to view and configure other features for retention and records management, create a custom role group (for example, named "Disposition Reviewers") and grant this group the Disposition Management role.</span></span>

<span data-ttu-id="5a88c-113">Além disso, para exibir o conteúdo dos itens durante o processo de disposição, adicione usuários aos dois grupos de funções a seguir: **Visualizador de conteúdo do Explorador de Conteúdos** e **Visualizador de Lista de Explorador de Conteúdos**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-113">Additionally, to view the contents of items during the disposition process, add users to the following two role groups: **Content Explorer Content Viewer** and **Content Explorer List Viewer**.</span></span> <span data-ttu-id="5a88c-114">Se os usuários não tiverem as permissões desses grupos de função, ainda poderão selecionar uma ação de revisão de disposição para concluir a revisão de disposição, mas deve fazê-lo sem a capacidade de exibir o conteúdo do item do centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="5a88c-114">If users don't have the permissions from these role groups, they can still select a disposition review action to complete the disposition review, but must do so without being able to view the item's contents from the compliance center.</span></span>

<span data-ttu-id="5a88c-115">Para obter instruções, consulte [Fornecer aos usuários acesso ao Centro de Segurança e Conformidade do Office 365](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="5a88c-115">For instructions to configure these permissions, see [Give users access to the Office 365 Security & Compliance Center](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>

### <a name="enable-auditing"></a><span data-ttu-id="5a88c-116">Habilitar auditoria</span><span class="sxs-lookup"><span data-stu-id="5a88c-116">Enable auditing</span></span>

<span data-ttu-id="5a88c-117">Verifique se a auditoria está habilitada pelo menos um dia antes da primeira ação de disposição.</span><span class="sxs-lookup"><span data-stu-id="5a88c-117">Make sure that auditing is enabled at least one day before the first disposition action.</span></span> <span data-ttu-id="5a88c-118">Para saber mais, confira [Pesquisar o log de auditoria no Centro de Conformidade &amp; e Segurança do Office 365](search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="5a88c-118">For more information, see [Search the audit log in the Office 365 Security &amp; Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> 

## <a name="disposition-reviews"></a><span data-ttu-id="5a88c-119">Revisões de disposição</span><span class="sxs-lookup"><span data-stu-id="5a88c-119">Disposition reviews</span></span>

<span data-ttu-id="5a88c-120">Quando o conteúdo atinge o fim do período de retenção, existem vários motivos pelos quais você pode querer revisar o conteúdo e confirmar se ele pode ser excluído com segurança ("descartado").</span><span class="sxs-lookup"><span data-stu-id="5a88c-120">When content reaches the end of its retention period, there are several reasons why you might want to review that content and confirm whether it can be permanently deleted ("disposed").</span></span> <span data-ttu-id="5a88c-121">Por exemplo, em vez de excluir o conteúdo, você pode precisar:</span><span class="sxs-lookup"><span data-stu-id="5a88c-121">For example, instead of deleting the content, you might need to:</span></span>
  
- <span data-ttu-id="5a88c-122">Suspender a exclusão de conteúdo relevante no caso de litígio ou auditoria.</span><span class="sxs-lookup"><span data-stu-id="5a88c-122">Suspend the deletion of relevant content in the event of litigation or an audit.</span></span>

- <span data-ttu-id="5a88c-123">Atribuir um período de retenção diferente ao conteúdo, talvez porque as configurações originais de retenção fossem uma solução temporária ou provisória.</span><span class="sxs-lookup"><span data-stu-id="5a88c-123">Assign a different retention period to the content, perhaps because the original retention settings were a temporary or provisional solution.</span></span>

- <span data-ttu-id="5a88c-124">Mova o conteúdo de seu local existente para um local de arquivamento, por exemplo, se esse conteúdo tiver valor de pesquisa ou histórico.</span><span class="sxs-lookup"><span data-stu-id="5a88c-124">Move the content from its existing location to an archive location, for example, if that content has research or historical value.</span></span>

<span data-ttu-id="5a88c-125">Quando uma revisão de disposição é disparada no final do período de retenção:</span><span class="sxs-lookup"><span data-stu-id="5a88c-125">When a disposition review is triggered at the end of the retention period:</span></span>
  
- <span data-ttu-id="5a88c-126">As pessoas que você escolher receberão uma notificação por email com o conteúdo a ser revisado.</span><span class="sxs-lookup"><span data-stu-id="5a88c-126">The people you choose receive an email notification that they have content to review.</span></span> <span data-ttu-id="5a88c-127">Esses revisores podem ser usuários individuais ou grupos de segurança habilitados para email.</span><span class="sxs-lookup"><span data-stu-id="5a88c-127">These reviewers can be individual users or mail-enabled security groups.</span></span> <span data-ttu-id="5a88c-128">As notificações são enviadas semanalmente.</span><span class="sxs-lookup"><span data-stu-id="5a88c-128">Note that notifications are sent on a weekly basis.</span></span>
    
- <span data-ttu-id="5a88c-129">Os revisores vão para a guia **Disposição**, no Centro de conformidade do Microsoft 365, para revisar o conteúdo e decidir se desejam ou não excluí-lo permanentemente, estender o período de retenção ou aplicar um rótulo de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="5a88c-129">The reviewers go to the **Disposition** tab in the Microsoft 365 compliance center to review the content and decide whether to permanently delete it, extend its retention period, or apply a different retention label.</span></span>

<span data-ttu-id="5a88c-130">Uma revisão de disposição pode incluir conteúdo nas caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a88c-130">A disposition review can include content in Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft 365 groups.</span></span> <span data-ttu-id="5a88c-131">O conteúdo que aguarda uma revisão de disposição nesses locais é excluído apenas após um revisor optar por excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5a88c-131">Content awaiting a disposition review in those locations is deleted only after a reviewer chooses to permanently delete the content.</span></span>

> [!NOTE]
> <span data-ttu-id="5a88c-132">Uma caixa de correio deve ter pelo menos 10 MB de dados para suportar revisões de disposição.</span><span class="sxs-lookup"><span data-stu-id="5a88c-132">A mailbox must have at least 10 MB data to support disposition reviews.</span></span>

<span data-ttu-id="5a88c-133">Você pode ver uma visão geral de todas as disposições pendentes na guia **Visão Geral**. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a88c-133">You can see an overview of all pending dispositions in the **Overview** tab. For example:</span></span>

![Disposições pendentes na visão geral do Gerenciamento de registros](../media/dispositions-overview.png)

<span data-ttu-id="5a88c-135">Ao selecionar **Exibir todas as disposições pendentes**, você será levado à página **Disposição**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-135">When you select the **View all pending dispositions**, you're taken to the **Disposition** page.</span></span> <span data-ttu-id="5a88c-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a88c-136">For example:</span></span>

![Página Disposições no Centro de conformidade do Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a><span data-ttu-id="5a88c-138">Fluxo de trabalho de revisão de disposição</span><span class="sxs-lookup"><span data-stu-id="5a88c-138">Workflow for a disposition review</span></span>

<span data-ttu-id="5a88c-139">O diagrama a seguir mostra o fluxo de trabalho básico para uma revisão de disposição quando um rótulo de retenção é publicado e aplicado manualmente por um usuário.</span><span class="sxs-lookup"><span data-stu-id="5a88c-139">The following diagram shows the basic workflow for a disposition review when a retention label is published and then manually applied by a user.</span></span> <span data-ttu-id="5a88c-140">Como alternativa, um rótulo de retenção configurado para uma revisão de disposição poderá ser aplicado automaticamente ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5a88c-140">Alternatively, a retention label configured for a disposition review can be auto-applied to content.</span></span>
  
![Gráfico mostrando o fluxo de como a disposição funciona](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
<span data-ttu-id="5a88c-142">Disparar uma revisão de disposição ao fim do período de retenção é uma opção de configuração disponível somente com um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="5a88c-142">Triggering a disposition review at the end of the retention period is a configuration option that's available only with a retention label.</span></span> <span data-ttu-id="5a88c-143">Esta opção não está disponível para política de retenção.</span><span class="sxs-lookup"><span data-stu-id="5a88c-143">This option is not available for a retention policy.</span></span> <span data-ttu-id="5a88c-144">Para obter mais informações sobre essas duas soluções de retenção, consulte [Saber mais sobre as políticas de retenção e os rótulos de retenção](retention.md).</span><span class="sxs-lookup"><span data-stu-id="5a88c-144">For more information about these two retention solutions, see [Learn about retention policies and retention labels](retention.md).</span></span>

<span data-ttu-id="5a88c-145">Da página **Definir configurações de retenção** para um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="5a88c-145">From the **Define retention settings** page for a retention label:</span></span>

![Configurações de retenção para um rótulo](../media/disposition-review-option.png)
 
<span data-ttu-id="5a88c-147">Depois de selecionar esta opção **Disparar uma revisão de disposição**, especifique os revisores de disposição na próxima página do assistente:</span><span class="sxs-lookup"><span data-stu-id="5a88c-147">After you select this **Trigger a disposition review** option, you specify the disposition reviewers on the next page of the wizard:</span></span>

![Especificando revisores de disposição](../media/disposition-reviewers.png)

<span data-ttu-id="5a88c-149">Para os revisores, especifique um usuário ou um grupo de segurança habilitado para email.</span><span class="sxs-lookup"><span data-stu-id="5a88c-149">For the reviewers, specify a user or mail-enabled security group.</span></span> <span data-ttu-id="5a88c-150">Grupos do Microsoft 365 ([antigo Grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa opção.</span><span class="sxs-lookup"><span data-stu-id="5a88c-150">Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) are not supported for this option.</span></span>

### <a name="viewing-and-disposing-of-content"></a><span data-ttu-id="5a88c-151">Exibir e descartar o conteúdo</span><span class="sxs-lookup"><span data-stu-id="5a88c-151">Viewing and disposing of content</span></span>

<span data-ttu-id="5a88c-152">Quando um revisor é notificado por email informando que o conteúdo está pronto para ser revisado, ele vai para a guia **Disposição** em **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5a88c-152">When a reviewer is notified by email that content is ready to review, they go to the **Disposition** tab from **Records Management** in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5a88c-153">Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecionar um rótulo de retenção para ver todo o conteúdo com esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="5a88c-153">The reviewers can see how many items for each retention label are awaiting disposition, and then select a retention label to see all content with that label.</span></span>

<span data-ttu-id="5a88c-154">Depois de selecionar um rótulo de retenção, você verá todas as suas disposições pendentes na guia **Disposição pendente**. Selecione um ou mais itens em que você pode escolher uma ação e inserir um comentário de justificação:</span><span class="sxs-lookup"><span data-stu-id="5a88c-154">After you select a retention label, you then see all pending dispositions for that label from the **Pending disposition** tab. Select one or more items where you can then choose an action and enter a justification comment:</span></span>

![Opções de disposição](../media/retention-disposition-options.png)

<span data-ttu-id="5a88c-156">Como você pode ver na imagem, as ações com suporte são:</span><span class="sxs-lookup"><span data-stu-id="5a88c-156">As you can see from the picture, the actions supported are:</span></span> 
  
- <span data-ttu-id="5a88c-157">Excluir permanentemente o item</span><span class="sxs-lookup"><span data-stu-id="5a88c-157">Permanently delete the item</span></span>
- <span data-ttu-id="5a88c-158">Estender o período de retenção</span><span class="sxs-lookup"><span data-stu-id="5a88c-158">Extend the retention period</span></span>
- <span data-ttu-id="5a88c-159">Aplicar um rótulo de retenção diferente</span><span class="sxs-lookup"><span data-stu-id="5a88c-159">Apply a different retention label</span></span>

<span data-ttu-id="5a88c-160">Fornecendo permissões para o local e o conteúdo, você pode usar o link na coluna **Local** para exibir os documentos no local original.</span><span class="sxs-lookup"><span data-stu-id="5a88c-160">Providing you have permissions to the location and the content, you can use the link in the **Location** column to view documents in their original location.</span></span> <span data-ttu-id="5a88c-161">Durante uma revisão de disposição, o conteúdo nunca se moverá do local original e nunca será excluído até que o revisor opte por fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="5a88c-161">During a disposition review, the content never moves from its original location, and it's never deleted until the reviewer chooses to do so.</span></span>

<span data-ttu-id="5a88c-162">As notificações de email são enviadas automaticamente para os revisores semanalmente.</span><span class="sxs-lookup"><span data-stu-id="5a88c-162">The email notifications are sent automatically to reviewers on a weekly basis.</span></span> <span data-ttu-id="5a88c-163">Esse processo agendado significa que, quando o conteúdo atinge o fim do período de retenção, pode levar até sete dias para que os revisores recebam a notificação de email informando que o conteúdo está aguardando a disposição.</span><span class="sxs-lookup"><span data-stu-id="5a88c-163">This scheduled process means that when content reaches the end of its retention period, it might take up to seven days for reviewers to receive the email notification that content is awaiting disposition.</span></span>
  
<span data-ttu-id="5a88c-164">Todas as ações podem ser auditadas, e o texto de justificativa digitado pelo revisor é salvo e exibido na coluna **Comentário** na página **Itens Descartados**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-164">All disposition actions can be audited and the justification text entered by the reviewer is saved and displayed in the **Comment** column on the **Disposed items** page.</span></span>
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a><span data-ttu-id="5a88c-165">Quanto tempo leva até que o conteúdo seja permanentemente excluído</span><span class="sxs-lookup"><span data-stu-id="5a88c-165">How long until disposed content is permanently deleted</span></span>

<span data-ttu-id="5a88c-166">O conteúdo que aguarda uma revisão de disposição é excluído apenas após um revisor optar por excluir permanentemente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="5a88c-166">Content awaiting a disposition review is deleted only after a reviewer chooses to permanently delete the content.</span></span> <span data-ttu-id="5a88c-167">Quando o revisor escolhe essa opção, o conteúdo no site do SharePoint ou na conta do OneDrive fica qualificado para o processo de limpeza padrão descrito em [Como as configurações de retenção funcionam com o conteúdo no local](retention.md#how-retention-settings-work-with-content-in-place).</span><span class="sxs-lookup"><span data-stu-id="5a88c-167">When the reviewer chooses this option, the content in the SharePoint site or OneDrive account becomes eligible for the standard cleanup process described in [How retention settings work with content in place](retention.md#how-retention-settings-work-with-content-in-place).</span></span>

## <a name="disposition-of-records"></a><span data-ttu-id="5a88c-168">Disposição de registros</span><span class="sxs-lookup"><span data-stu-id="5a88c-168">Disposition of records</span></span>

<span data-ttu-id="5a88c-169">Use a guia **Disposição** da página **Gerenciamento de registros** para identificar os registros excluídos, automaticamente ou após uma revisão de disposição.</span><span class="sxs-lookup"><span data-stu-id="5a88c-169">Use the **Disposition** tab from the **Records Management** page to identify records that are now deleted, either automatically or after a disposition review.</span></span> <span data-ttu-id="5a88c-170">Esses itens exibem **Registros Descartados** na coluna **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-170">These items display **Records Disposed** in the **Type** column.</span></span> <span data-ttu-id="5a88c-171">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5a88c-171">For example:</span></span>

![Itens que foram descartados sem uma revisão de disposição](../media/records-disposed2.png)

<span data-ttu-id="5a88c-173">Os itens mostrados na guia **Itens descartados** de rótulos de registro serão mantidos por até sete anos após o item ter sido descartado, com um limite de 1 milhão itens por registro para esse período.</span><span class="sxs-lookup"><span data-stu-id="5a88c-173">Items that are shown in the **Disposed Items** tab for record labels are kept for up to seven years after the item was disposed, with a limit of one million items per record for that period.</span></span> <span data-ttu-id="5a88c-174">Se você vir que o número de **Contagem** se aproxima desse limite de 1 milhão e precisar de prova de disposição para seus registros, contate o [Suporte da Microsoft](/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="5a88c-174">If you see the **Count** number nearing this limit of one million, and you need proof of disposition for your records, contact [Microsoft Support](/office365/admin/contact-support-for-business-products).</span></span>

> [!NOTE]
> <span data-ttu-id="5a88c-175">Esta funcionalidade baseia-se em informações do[Log de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) e, portanto, exige que a auditoria seja [habilitada e pesquisável](turn-audit-log-search-on-or-off.md), para que os eventos correspondentes sejam capturados.</span><span class="sxs-lookup"><span data-stu-id="5a88c-175">This functionality is based on information from the [unified audit log](search-the-audit-log-in-security-and-compliance.md) and therefore requires auditing to be [enabled and searchable](turn-audit-log-search-on-or-off.md) so the corresponding events are captured.</span></span>

<span data-ttu-id="5a88c-176">Para auditoria, pesquise **Arquivo excluído marcado como registro** na categoria **Arquivo e atividades de página**.</span><span class="sxs-lookup"><span data-stu-id="5a88c-176">For auditing, search for **Deleted file marked as a record** in the **File and page activities** category.</span></span> <span data-ttu-id="5a88c-177">Esse evento de auditoria é aplicável a documentos e emails.</span><span class="sxs-lookup"><span data-stu-id="5a88c-177">This audit event is applicable to documents and emails.</span></span>

## <a name="filter-and-export-the-views"></a><span data-ttu-id="5a88c-178">Filtrar e exportar os modos de exibição</span><span class="sxs-lookup"><span data-stu-id="5a88c-178">Filter and export the views</span></span>

<span data-ttu-id="5a88c-179">Quando você seleciona um rótulo de retenção na página **Disposição**, a guia **Disposição pendente** (se aplicável) e a guia **Itens descartados** permitem filtrar os modos de exibição para facilitar a localização de itens.</span><span class="sxs-lookup"><span data-stu-id="5a88c-179">When you select a retention label from the **Disposition** page, the **Pending disposition** tab (if applicable) and the **Disposed items** tab let you filter the views to help you more easily find items.</span></span> 

<span data-ttu-id="5a88c-180">Para as disposições pendentes, o intervalo de tempo se baseia na data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="5a88c-180">For pending dispositions, the time range is based on the expiration date.</span></span> <span data-ttu-id="5a88c-181">Para itens descartados, o intervalo de tempo se baseia na data de exclusão.</span><span class="sxs-lookup"><span data-stu-id="5a88c-181">For disposed items, the time range is based on the deletion date.</span></span>
  
<span data-ttu-id="5a88c-182">Você pode exportar informações sobre os itens no modo de exibição como um arquivo .csv, que pode ser classificado e gerenciado usando o Excel:</span><span class="sxs-lookup"><span data-stu-id="5a88c-182">You can export information about the items in either view as a .csv file that you can then sort and manage using Excel:</span></span>

![Opção de exportação para disposição](../media/retention-export-option.png)