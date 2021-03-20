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
ms.openlocfilehash: c327081109fe9d7c4d85d4cf8f01a9e5466432d1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908415"
---
# <a name="create-retention-labels-and-apply-them-in-apps"></a>Criar rótulos de retenção e aplicá-los em aplicativos

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Esse cenário é compatível com todas as configurações de rótulo de retenção, inclusive [registros regulatórios](records-management.md#records).

Use as informações a seguir para ajudá-lo a criar e publicar [rótulos de retenção](retention.md)e, em seguida, aplicá-los a documentos e emails.

Os rótulos de retenção ajudam você a manter o que é necessário e a excluir o que não o é no nível de item (documento ou email). Eles também são usados para declarar um item como um registro como parte de uma solução de [gerenciamento de registros](records-management.md) para seus dados do Microsoft 365.

Disponibilizar os rótulos de retenção para as pessoas em sua organização para que eles possam classificar o conteúdo é um processo de duas etapas: 

1. Crie os rótulos de retenção.

2. Publique os rótulos de retenção usando uma política de rótulos de retenção.
  
![Diagrama de funções e tarefas para rótulos](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)

Use as instruções a seguir para as duas etapas de administrador.

## <a name="before-you-begin"></a>Antes de começar

O administrador global da sua organização tem permissões completas para criar e editar os rótulos de retenção e suas políticas. Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-create-and-publish-retention-labels"></a>Como criar e publicar rótulos de retenção

Primeiro, crie seu rótulo de retenção. Em seguida, crie uma política de rótulo para tornar os rótulos disponíveis para aplicar nos aplicativos.

Onde você cria e configura seus rótulos de retenção depende se você está usando o gerenciamento de registros ou não. São fornecidas instruções para ambos os cenários.

### <a name="step-1-create-retention-labels"></a>Etapa 1: Crie rótulos de retenção.

1. No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros:
        - **Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**
        
    - Se você não estiver usando o gerenciamento de registros:
       - **Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente. Se você estiver usando o gerenciamento de registros:
    
    - Para obter informações sobre os descritores do plano de arquivo, confira [Usar plano de arquivo para gerenciar rótulos de retenção](file-plan-manager.md).
    
    - Para usar o rótulo de retenção para declarar registros, selecione **Marcar itens como registros** ou **Marcar itens como registros regulatórios**. Para saber mais, confira [Configuração de rótulos de retenção para declarar registros](declare-records.md#configuring-retention-labels-to-declare-records).

3. Depois de criar o rótulo, você verá as opções para publicar a etiqueta, aplicar o rótulo automaticamente ou salvar o rótulo: selecione **Basta salvar o rótulo para agora** e, em seguida, selecione **Concluído**.

4. Repita essas etapas para criar mais rótulos.

Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para iniciar o Assistente do editor de retenção que permite alterar as descrições de rótulo e quaisquer [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.

### <a name="step-2-publish-retention-labels"></a>Etapa 2: Publique os rótulos de retenção

Publique os rótulos de retenção para que eles possam ser aplicados pelos usuários em aplicativos, como o Microsoft Office SharePoint Online e o Outlook.

1. No [Centro de conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros:
        - **Soluções** > **Gerenciamento de Registros** > > guia **Políticas de Rótulo** > **Publicar Rótulos**
    
    - Se você não estiver usando o gerenciamento de registros:
        - **Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Publicar Rótulos**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente.
    
    Para obter informações sobre os locais com suporte de rótulos de retenção, confira [Rótulos e locais de retenção](retention.md#retention-label-policies-and-locations). 

Para editar uma política de rótulo de retenção existente (o tipo de política é **Publicar**), selecione-a e, em seguida, selecione a opção **Editar** para iniciar a política de retenção de edição. Esse assistente permite alterar a descrição da política e as [configurações elegíveis](#updating-retention-labels-and-their-policies) na etapa 2.


## <a name="when-retention-labels-become-available-to-apply"></a>Quando os rótulos de retenção se tornam disponíveis para aplicar

Se você publicar os rótulos de retenção no SharePoint ou no OneDrive, os rótulos geralmente serão exibidos para os usuários finais selecionarem dentro de um dia. No entanto, espere até sete dias. 

Se você publicar rótulos de retenção no Exchange, pode levar até sete dias para que esses rótulos de retenção apareçam para os usuários finais, e a caixa de correio deve conter pelo menos 10 MB de dados.

Por exemplo:
  
![Diagrama de quando os rótulos manuais entram em vigor](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  

Se os rótulos não aparecerem após sete dias, verifique o **Status** da política de rótulo selecionando-o na página **Políticas de rótulo** no centro de conformidade. Se você ver o status **Desativado (Erro)** e nos detalhes dos locais vir uma mensagem de que está demorando mais do que o esperado para implantar a política (para SharePoint) ou para tentar reimplantar a política (para OneDrive), tente executar [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy), um comando do PowerShell, para repetir a distribuição da política:

1. [Conectar-se ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Execute o seguinte comando:
    
    ``` PowerShell
    Set-RetentionCompliancePolicy -Identity <policy name> -RetryDistribution
   ```

### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Como verificar o status dos rótulos de retenção publicados no Exchange

No Exchange Online, os rótulos são disponibilizados para os usuários finais por um processo que é executado a cada sete dias. Usando o PowerShell, você pode ver quando esse processo foi executado pela última vez e, portanto, identificar quando ele será executado novamente.
  
1. [Conectar-se ao Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Execute estes comandos.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}

In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox. If it has not happened since the time you created the policy, the labels are not going to appear. To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.
    
If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).
    

## How to apply published retention labels

Use the following sections to learn how published retention labels can be applied in apps:

- [Manually apply retention labels](#manually-apply-retention-labels)

- [Applying a default retention label to all content in a SharePoint library, folder, or document set](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)

- [Automatically applying a retention label to email by using rules](#automatically-applying-a-retention-label-to-email-by-using-rules)

In addition, when you use [SharePoint Syntex](../contentunderstanding/index.md) and publish retention labels to SharePoint locations, you can [apply a retention label to a document understanding model](../contentunderstanding/apply-a-retention-label-to-a-model.md) so that identified documents are automatically labeled.

After content is labeled, see the following information to understand when the applied label can be removed or changed: [Only one retention label at a time](retention.md#only-one-retention-label-at-a-time).

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

##### Applying a default retention label to an Outlook folder

You can apply retention labels to Outlook folders as a default label that can be inherited by messages in that folder. Right-click the folder, select **Properties**, the **Policy** tab, and select the retention label you want to use as that folder's default retention label.

When you use a a standard retention label as your default label for an Outlook folder:
  
- All unlabeled items in the folder have this retention label applied.

- The inheritance flows to any child folders and items inherit the label from their nearest folder.

- Items that are already labeled retain their retention label, unless it was applied by a different default label.

- If you change or remove the default retention label for the folder: Existing retention labels applied to items in that folder are also changed or removed only if those labels were applied by a default label.

- If you move an item with a default retention label from one folder to another folder with a different default retention label: The item gets the new default retention label.

- If you move an item with a default retention label from one folder to another folder with no default retention label: The old default retention label is removed.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

#### Applying retention labels in Outlook on the web

To label an item in Outlook on the web, right-click the item \> **Assign policy** \> choose the retention label. 
  
![Assign policy menu in Outlook on the web](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
After the retention label is applied, you can view that retention label and what action it takes at the top of the item. If an email is classified and has an associated retention period, you can know at a glance when the email will expire.
  
![Label assigned to email in Outlook on the web](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
As with the desktop version of Outlook on the web, you can also apply retention labels to folders. Right-click the folder, select **Assign policy**, and change **Use parent folder policy** to the retention label you want to use as that folder's default retention label.

#### Applying retention labels in OneDrive and SharePoint

To label a document (including OneNote files) in OneDrive or SharePoint, select the item \> in the upper-right corner, choose **Open the details pane**![Information pane icon](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **Apply retention label** \> choose the retention label. 
  
You can also apply a retention label to a folder or document set, and you can set a [default retention label for a document library](#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
  
![Apply label list for an item in SharePoint](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
After a retention label is applied to an item, you can view it in the details pane when that item's selected.
  
![Applied label shown in Details pane](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)

For SharePoint, but not OneDrive, you can create a view of the library that contains the **Labels** column or **Item is a Record** column. This view lets you see at a glance the retention labels assigned to all items and which items are records. Note, however, that you can't filter the view by the **Item is a Record** column. For instructions how to add columns, see [Show or hide columns in a list or library](https://support.microsoft.com/en-us/office/show-or-hide-columns-in-a-list-or-library-b820db0d-9e3e-4ff9-8b8b-0b2dbefa87e2).


#### Applying retention labels in Microsoft 365 groups

When you publish retention labels to Microsoft 365 groups ([formerly Office 365 groups](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), the retention labels appear in both the group site and group mailbox in Outlook on the web. The experience of applying a retention label to content is identical to that for email and documents.

To retain content for a Microsoft 365 group, use the **Microsoft 365 Groups** location. Even though a Microsoft 365 group has an Exchange mailbox, a retention policy that includes the entire Exchange location won't include content in Microsoft 365 group mailboxes.

In addition, it's not possible to use the Exchange location to include or exclude a specific group mailbox. Although the Exchange location initially allows a group mailbox to be selected, when you try to save the retention policy, you receive an error that "RemoteGroupMailbox" is not a valid selection for the Exchange location.
  
First, create and configure the sensitivity labels that you want to make available for apps and other services. For example, the labels you want users to see and apply from Office apps. 

Then, create one or more label policies that contain the labels and policy settings that you configure. It's the label policy that publishes the labels and settings for your chosen users and locations.

### Applying a default retention label to all content in a SharePoint library, folder, or document set

This method requires retention labels to be published to a retention label policy.

In addition to letting people apply a retention label to individual documents, you can also apply a default retention label to a SharePoint library, folder, or document set. In this scenario, documents in that location can inherit your selected default retention label. Although the same label is applied, each document will be retained and deleted separately, according to the start of the retention period setting in the label. 
  
For a document library, the default label configuration is done on the **Library settings** page for a document library. When you choose the default retention label, you can also choose to apply it to existing items in the library.
  
For example, if you have a retention label for marketing materials, and you know a specific document library contains only that type of content, you can make the **Marketing Materials** retention label the default label for all documents in that library.
  
![Apply label option on library Settings page](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)

#### Label behavior when you use a default label for SharePoint

For standard retention labels that you apply as a default retention label to a library, folder, or document set:

- All new, unlabeled items in the container will have this retention label applied.

- For folders, the inheritance flows to any child folders and items inherit the label from their nearest folder.

- If you selected the option to apply the default label to existing items: Items that are already labeled retain their retention label, unless it was applied by a different default label.
    
- If you change the default retention label for the container: Existing retention labels applied to items in that container are changed only if you selected the option to apply the default label to existing items and those labels were applied by a default label.

- If you remove the default retention label for the container: Items retain their labels.
    
- If you move an item with a default retention label applied from one container to another container: The item keeps its existing default retention label, even if the new location has a different default retention label. Only if you then change the default label for this new location can the moved item inherit the default label from its current location.

When labels are applied that aren't standard retention labels but mark items as [records (or regulatory records)](records-management.md#records), these labels can only be manually changed or removed.

### Automatically applying a retention label to email by using rules

In Outlook, you can create rules to apply a retention label.
  
For example, you can create a rule that applies a specific retention label to all messages sent to or from a specific distribution group.
  
To create a rule, right-click an item \> **Rules** \> **Create Rule** \> **Advanced Options** \> **Rules Wizard** \> **apply retention policy**.
  
![Rules wizard with option to apply retention policies](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)

Although the UI refers to retention policies, it's your retention labels that display here and can be selected, not your retention policies.

## Updating retention labels and their policies

When you edit a retention label or retention label policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.

Some settings can't be changed after the label or policy is created and saved, which include:
- The retention label and policy name, and the retention settings except the retention period. However, you can't change the retention period when the retention period is based on when items were labeled.
- The option to mark items as a record.

### Deleting retention labels

You can delete retention labels that aren't currently included in any retention label policies, that aren't configured for event-based retention, or mark items as regulatory records. The ability to delete retention labels that mark items as records is currently rolling out in preview.

For retention labels that you can delete, if they have been applied to items, the deletion fails and you see a link to content explorer to identify the labeled items.

However, it can take up to two days for content explorer to show the items that are labeled. In this scenario, the retention label might be deleted without showing you the link to content explorer.

## Locking the policy to prevent changes

If you need to ensure that no one can turn off the policy, delete the policy, or make it less restrictive, see [Use Preservation Lock to restrict changes to retention policies and retention label policies](retention-preservation-lock.md).

## Next steps

Event-based retention is another supported scenario for retention labels. For more information, see the following articles:

- [Start retention when an event occurs](event-driven-retention.md)
- [Automate event-based retention](./event-driven-retention.md#automate-events-by-using-a-rest-api)
- [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md)