---
title: Criar rótulos de retenção e aplicá-los em aplicativos para reter ou excluir conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Instruções para criar e publicar rótulos de retenção para que você possa aplicá-los em aplicativos para manter o que precisa e excluir o que não
ms.openlocfilehash: a301568e80bdfe0681b052225852cde8bf8cdf50
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778309"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a><span data-ttu-id="b23d3-103">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="b23d3-103">Create retention labels and apply them in apps</span></span>

><span data-ttu-id="b23d3-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="b23d3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="b23d3-105">Use as informações a seguir para ajudá-lo a criar e publicar [rótulos de retenção](retention.md)e, em seguida, aplicá-los a documentos e emails.</span><span class="sxs-lookup"><span data-stu-id="b23d3-105">Use the following information to help you create and publish [retention labels](retention.md), and then apply them to documents and emails.</span></span>

<span data-ttu-id="b23d3-106">Os rótulos de retenção ajudam você a manter o que é necessário e a excluir o que não o é no nível de item (documento ou email).</span><span class="sxs-lookup"><span data-stu-id="b23d3-106">Retention labels help you retain what you need and delete what you don't at the item level (document or email).</span></span> <span data-ttu-id="b23d3-107">Eles também são usados para declarar um item como um registro como parte de uma solução de [gerenciamento de registros](records-management.md) para seus dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b23d3-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="b23d3-108">Disponibilizar os rótulos de retenção para as pessoas em sua organização para que eles possam classificar o conteúdo é um processo de duas etapas:</span><span class="sxs-lookup"><span data-stu-id="b23d3-108">Making retention labels available to people in your organization so that they can classify content is a two-step process:</span></span> 

1. <span data-ttu-id="b23d3-109">Criar os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="b23d3-109">Create the retention labels</span></span>

2. <span data-ttu-id="b23d3-110">Publicar os rótulos de retenção usando uma política de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="b23d3-110">Publish the retention labels by using a retention label policy</span></span>
  
![Diagrama de funções e tarefas para rótulos](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

<span data-ttu-id="b23d3-112">Use as instruções a seguir para as duas etapas de administrador.</span><span class="sxs-lookup"><span data-stu-id="b23d3-112">Use the following instructions for the two admin steps.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b23d3-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b23d3-113">Before you begin</span></span>

<span data-ttu-id="b23d3-114">O administrador global da sua organização tem permissões completas para criar e editar os rótulos de retenção e suas políticas.</span><span class="sxs-lookup"><span data-stu-id="b23d3-114">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="b23d3-115">Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b23d3-115">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-create-and-publish-retention-labels"></a><span data-ttu-id="b23d3-116">Como criar e publicar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="b23d3-116">How to create and publish retention labels</span></span>

<span data-ttu-id="b23d3-117">Primeiro, crie seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="b23d3-117">First, create your retention labels.</span></span> <span data-ttu-id="b23d3-118">Em seguida, crie uma política de rótulo para tornar os rótulos disponíveis para aplicar nos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b23d3-118">Then create a label policy to make the labels available to apply in apps.</span></span>

<span data-ttu-id="b23d3-119">Onde você cria e configura seus rótulos de retenção depende se você está usando o gerenciamento de registros ou não.</span><span class="sxs-lookup"><span data-stu-id="b23d3-119">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="b23d3-120">São fornecidas instruções para ambos os cenários.</span><span class="sxs-lookup"><span data-stu-id="b23d3-120">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-retention-labels"></a><span data-ttu-id="b23d3-121">Etapa 1: Crie rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="b23d3-121">Step 1: Create retention labels</span></span>

1. <span data-ttu-id="b23d3-122">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="b23d3-122">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b23d3-123">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="b23d3-123">If you are using records management:</span></span>
        - <span data-ttu-id="b23d3-124">**Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**</span><span class="sxs-lookup"><span data-stu-id="b23d3-124">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="b23d3-125">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="b23d3-125">If you are not using records management:</span></span>
       - <span data-ttu-id="b23d3-126">**Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**</span><span class="sxs-lookup"><span data-stu-id="b23d3-126">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="b23d3-127">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="b23d3-127">Don't immediately see your option?</span></span> <span data-ttu-id="b23d3-128">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="b23d3-128">First select **Show all**.</span></span> 

2. <span data-ttu-id="b23d3-129">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="b23d3-129">Follow the prompts in the wizard.</span></span> <span data-ttu-id="b23d3-130">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="b23d3-130">If you are using records management:</span></span>
    
    - <span data-ttu-id="b23d3-131">Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="b23d3-131">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="b23d3-132">Para usar o rótulo de retenção para declarar conteúdo como um registro, ative a caixa de seleção **Usar rótulo para classificar o conteúdo como um "Registro"**.</span><span class="sxs-lookup"><span data-stu-id="b23d3-132">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="b23d3-133">Repita essas etapas para criar mais rótulos.</span><span class="sxs-lookup"><span data-stu-id="b23d3-133">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="b23d3-134">Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para começar o mesmo assistente que permite alterar as descrições de rótulo e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b23d3-134">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="b23d3-135">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="b23d3-135">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="step-2-publish-retention-labels"></a><span data-ttu-id="b23d3-136">Etapa 2: Publique os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="b23d3-136">Step 2: Publish retention labels</span></span>

<span data-ttu-id="b23d3-137">Publique seus rótulos de retenção, para que possam ser aplicados manualmente pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="b23d3-137">Publish retention labels so that they can be applied by admins and users.</span></span>

1. <span data-ttu-id="b23d3-138">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="b23d3-138">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="b23d3-139">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="b23d3-139">If you are using records management:</span></span>
        - <span data-ttu-id="b23d3-140">**Soluções** > **Gerenciamento de Registros** > > guia **Políticas de Rótulo** > **Publicar Rótulos**</span><span class="sxs-lookup"><span data-stu-id="b23d3-140">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="b23d3-141">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="b23d3-141">If you are not using records management:</span></span>
        - <span data-ttu-id="b23d3-142">**Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Publicar Rótulos**</span><span class="sxs-lookup"><span data-stu-id="b23d3-142">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="b23d3-143">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="b23d3-143">Don't immediately see your option?</span></span> <span data-ttu-id="b23d3-144">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="b23d3-144">First select **Show all**.</span></span> 

2. <span data-ttu-id="b23d3-145">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="b23d3-145">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="b23d3-146">Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="b23d3-146">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="b23d3-147">Para editar uma política de rótulo de retenção existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b23d3-147">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="b23d3-148">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="b23d3-148">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="when-retention-labels-become-available-to-apply"></a><span data-ttu-id="b23d3-149">Quando os rótulos de retenção se tornam disponíveis para aplicar</span><span class="sxs-lookup"><span data-stu-id="b23d3-149">When retention labels become available to apply</span></span>

<span data-ttu-id="b23d3-150">Se você publicar os rótulos de retenção no SharePoint ou no OneDrive, os rótulos geralmente serão exibidos para os usuários finais selecionarem dentro de um dia.</span><span class="sxs-lookup"><span data-stu-id="b23d3-150">If you publish retention labels to SharePoint or OneDrive, those labels  typically appear for end users to select within one day.</span></span> <span data-ttu-id="b23d3-151">No entanto, espere até sete dias.</span><span class="sxs-lookup"><span data-stu-id="b23d3-151">However, allow up to seven days.</span></span> 

<span data-ttu-id="b23d3-152">Se você publicar rótulos de retenção no Exchange, pode levar até sete dias para que esses rótulos de retenção apareçam para os usuários finais, e a caixa de correio deve conter pelo menos 10 MB de dados.</span><span class="sxs-lookup"><span data-stu-id="b23d3-152">If you publish retention labels to Exchange, it can take up to seven days for those retention labels to appear for end users, and the mailbox must contain at least 10 MB of data.</span></span>

<span data-ttu-id="b23d3-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b23d3-153">For example:</span></span>
  
![Diagrama de quando os rótulos manuais entram em vigor](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="b23d3-155">Como verificar o status dos rótulos de retenção publicados no Exchange</span><span class="sxs-lookup"><span data-stu-id="b23d3-155">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="b23d3-156">No Exchange Online, os rótulos são disponibilizados para os usuários finais por um processo que é executado a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="b23d3-156">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="b23d3-157">Usando o Powershell, você pode ver quando esse processo foi executado pela última vez e, assim, determinar quando ele será executado novamente.</span><span class="sxs-lookup"><span data-stu-id="b23d3-157">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="b23d3-158">[Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="b23d3-158">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="b23d3-159">Execute estes comandos.</span><span class="sxs-lookup"><span data-stu-id="b23d3-159">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}   ```

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

### Manually apply retention labels 

End users, as well as administrators, can manually apply retention labels from the following locations:  

- Outlook and Outlook on the web
    
- OneDrive
    
- SharePoint
    
- Microsoft 365 groups (both the group site and group mailbox in Outlook on the web)
    
Use the following sections to understand how to apply retention labels. 

#### Applying retention labels in Outlook

To label an item in the Outlook desktop client, select the item. On the **Home** tab on the ribbon, click **Assign Policy**, and then choose the retention label. 
  
![Assign Policy button](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
You can also right-click an item, click **Assign Policy** in the context menu, and then choose the retention label. 

After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email has a retention label applied that has an associated retention period, you can see at a glance when the email expires.
  
You can also apply retention labels to folders, in which case:
  
- All items in the folder automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them. Explicitly labeled items keep their existing retention label. For more information, see [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page. 
    
- If you change or remove the default retention label for a folder, the retention label's also changed or removed for all items in the folder, **except** items with explicitly assigned retention labels. 
    
- If you move an item with a default retention label from one folder to another folder with a different default retention label, the item gets the new default retention label.
    
- If you move an item with a default retention label from one folder to another folder with no default retention label, the old default retention label is removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with Outlook on the web, you can also apply retention labels to folders. 

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Office 365 groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to enabling people to apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set, so that all documents in that location get the default retention label.
  
For a document library, this is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library. 
  
For example, if you have a tag for marketing materials, and you know a specific document library contains only that type of content, you can make the Marketing Materials tag the default for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
If you apply a default retention label to existing items in the library, folder, or document set:
  
- All items in the library, folder, or document set automatically get the same retention label, **except** for items that have had a retention label applied explicitly to them (such as records). Explicitly labeled items keep their existing label. For more information, see the below section on [The principles of retention, or what takes precedence](retention.md#the-principles-of-retention-or-what-takes-precedence).
    
- If you change or remove the default retention label for a library, folder, or document set, the retention label is also changed or removed for all items in the library, folder, or document set, **except** items with explicit retention labels (such as records).
    
- If you move an item with a default retention label from one site collection, library, folder, or document set to another site collection, library, folder, or document set that has a different label, the item keeps its existing default retention label, even if the new location has a different default retention label. If the item does not have a label before moving, it will take on the default retention label of the new location.

**Records:** If you apply a default record label to a library, folder, or document set, then a record label is applied to all the individual items within those locations. When you move a new item into a location with a record label, that item is labeled a record. However, if you change the default retention label to a label that doesn't declare content as a record, that action does not remove the record label from the individual items; those items retain their record label. Only a site collection admin can explicitly remove or change the retention label of record items.

For more information about retention labels that declare content as a record, see [Records](records-management.md#records).

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.
- The option to classify as a record.

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](automate-event-driven-retention.md)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)
