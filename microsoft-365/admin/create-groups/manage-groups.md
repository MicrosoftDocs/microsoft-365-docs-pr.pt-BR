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
description: Aprenda a gerenciar grupos do Microsoft 365, incluindo adicionar remover membros do grupo, editar o endereço de email, o nome do grupo ou a descrição e personalizar como o grupo funciona.
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908705"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Gerenciar um grupo no centro de administração do Microsoft 365

Depois de criar [um grupo do Microsoft 365](create-groups.md) e adicionar membros do grupo, você poderá configurar seu grupo. Você pode editar o nome ou a descrição do grupo, gerenciar proprietários ou membros e especificar se os envios externos podem enviar emails para o grupo e se devem enviar cópias de conversas de grupo para membros.

Vá para o Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Editar o nome ou a descrição do grupo

1. No centro de administração, **expanda Grupos** e clique em **Grupos**.

2. Selecione o grupo que você deseja editar e clique em **Editar nome e descrição.**

3. Atualize o nome e a descrição e selecione **Salvar**.

## <a name="manage-group-owners-and-members"></a>Gerenciar proprietários e membros do grupo

1. No centro de administração, **expanda Grupos** e clique em **Grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na guia **Membros,** escolha se deseja gerenciar proprietários ou membros.

4. Escolha **Adicionar** para adicionar alguém ou clique **em X** para remover alguém.

5. Clique em **Fechar**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Enviar cópias de conversas para caixas de entrada de membros do grupo
  
Quando você usa o centro de administração para criar um grupo, por padrão, os usuários não têm cópias de emails de grupo e convites de reunião enviados para suas caixas de entrada. Eles precisarão ir ao grupo para ver conversas e reuniões. Você pode alterar essa configuração no centro de administração.

Quando você ativar essa configuração, os membros do grupo receberão uma cópia de emails de grupo e convites de reunião enviados para sua Caixa de Entrada do Outlook. Eles podem ler e excluir essa cópia do email e não afetar mais ninguém. Na caixa de entrada do Grupo, uma cópia do email ainda existe.

Os membros do grupo podem optar por não receber esses emails optando por parar de seguir o grupo no Outlook.

1. No centro de administração, **expanda Grupos** e clique em **Grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na guia **Configurações,** selecione **Enviar** cópias de conversas e eventos de grupo para membros do grupo se quiser que os membros recebam cópias de mensagens de grupo e itens de calendário em sua própria caixa de entrada.

4. Selecione **Salvar**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Permitir que pessoas de fora da organização enviem emails para o grupo

Essa opção é ótima se você quiser ter um endereço de email da empresa como info@contoso.com.
 
1. No centro de administração, **expanda Grupos** e clique em **Grupos**.

2. Clique no nome do grupo que você deseja gerenciar para abrir o painel de configurações.

3. Na lista grupos do centro de administração, selecione o nome do grupo que você deseja alterar e, na guia Configurações, selecione Permitir que os **envios externos** enviem emails **para esse grupo**.
    
4. Selecione **Salvar**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Excluir permanentemente um grupo do Microsoft 365

Às vezes, você pode querer limpar permanentemente um grupo sem esperar o período de exclusão suave de 30 dias expirar. Para fazer isso, inicie o PowerShell e execute este comando para obter a ID de objeto do grupo:
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Anote a ID do objeto do grupo ou grupos que você deseja excluir permanentemente.
  
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

[Gerenciar grupos do Microsoft 365 com o PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)