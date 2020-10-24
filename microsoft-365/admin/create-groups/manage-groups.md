---
title: Gerenciar um grupo no centro de administração
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Saiba como gerenciar os grupos do Microsoft 365, incluindo a adição de adicionar ou remover membros do grupo, editar o endereço de email, o nome do grupo ou a descrição e personalizar como o grupo funciona.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753296"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Gerenciar um grupo no centro de administração do Microsoft 365

Depois de [criar um grupo do Microsoft 365](create-groups.md) e adicionar membros de grupo, você pode configurar seu grupo. Você pode editar o nome ou a descrição do grupo, gerenciar proprietários ou membros e especificar se os remetentes externos podem enviar emails para o grupo e se deseja enviar cópias de conversas de grupo para membros.

Vá para o centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Editar o nome ou a descrição do grupo

1. No centro de administração, expanda **grupos**e clique em **grupos**.

2. Selecione o grupo que você deseja editar e clique em **Editar nome e descrição**.

3. Atualize o nome e a descrição e, em seguida, selecione **salvar**.

## <a name="manage-group-owners-and-members"></a>Gerenciar proprietários e membros do grupo

1. No centro de administração, expanda **grupos**e clique em **grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na guia **Membros** , escolha se você deseja gerenciar proprietários ou membros.

4. Escolha **Adicionar** para adicionar alguém ou clique em **X** para remover alguém.

5. Clique em **Fechar**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Enviar cópias de conversas para caixas de entrada de membros do grupo
  
Quando você usa o centro de administração para criar um grupo, por padrão, os usuários não recebem cópias de emails de grupo e convites de reunião enviados para suas caixas de entrada. Eles precisarão acessar o grupo para ver as conversas e reuniões. Você pode alterar essa configuração no centro de administração.

Quando você ativar essa configuração, os membros do grupo receberão uma cópia dos emails de grupo e convites de reunião enviados para a caixa de entrada do Outlook. Eles podem ler e excluir essa cópia do email e não afetar mais ninguém. Na caixa de entrada do Grupo, uma cópia do email ainda existe.

Os membros do grupo podem optar por receber esses emails escolhendo parar de seguir o grupo no Outlook.

1. No centro de administração, expanda **grupos**e clique em **grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na guia **configurações** , selecione **enviar cópias de conversas de grupo e eventos para agrupar Membros** se você quiser que os Membros recebam cópias de mensagens de grupo e itens de calendário em sua própria caixa de entrada.

4. Selecione **Salvar**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Permitir que pessoas de fora da organização enviem email para o grupo

Essa opção é ótima se você deseja ter um endereço de email da empresa, como o info@contoso.com.
 
1. No centro de administração, expanda **grupos**e clique em **grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na lista grupos do centro de administração, selecione o nome do grupo que você deseja alterar e, na guia **configurações** , selecione **permitir que remetentes externos enviem esse grupo por email**.
    
4. Selecione **Salvar**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Excluir permanentemente um grupo do Microsoft 365

Às vezes, você pode querer limpar permanentemente um grupo sem esperar que o período de exclusão reversível de 30 dias expire. Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Anote a ID de objeto do grupo, ou grupos, que você deseja excluir permanentemente.
  
> [!CAUTION]
> Ao limpar o grupo, você removerá o grupo e os dados nele para sempre. 
  
Para limpar o grupo, execute o seguinte comando no PowerShell:

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

Para confirmar que o grupo foi limpo, execute o cmdlet  *Get-AzureADMSDeletedGroup*  novamente para confirmar que ele não aparece mais na lista de grupos temporariamente excluídos. Em alguns casos pode levar até 24 horas para que o grupo e todos os dados nele sejam excluídos permanentemente. 
  
## <a name="related-articles"></a>Artigos relacionados

[Criar um grupo do Microsoft 365](create-groups.md)

[Gerenciar o acesso de convidados aos grupos do Microsoft 365](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Escolha o domínio a ser usado ao criar grupos do Microsoft 365](../../solutions/choose-domain-to-create-groups.md)

[Permitir que os membros enviem como ou enviem em nome de um grupo do Microsoft 365](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Atualizar listas de distribuição para grupos do Microsoft 365](../manage/upgrade-distribution-lists.md)

[Gerenciar os grupos do Microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
