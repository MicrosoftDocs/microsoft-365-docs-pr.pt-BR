---
title: Recursos multi-geo no Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Saiba mais sobre como Teams funciona com Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362637"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Recursos multi-geo no Microsoft Teams

Recursos multi-geo no Teams permite que Teams dados de chat sejam armazenados em repouso em uma localização geográfica especificada. Os dados de chat consistem em mensagens de chat, incluindo mensagens privadas, mensagens de canal e imagens usadas em chats.

Teams usa o PDL (Preferred Data Location) para usuários e grupos determinarem onde armazenar dados. Se o PDL não estiver definido ou for inválido, os dados serão armazenados no local central do locatário.

## <a name="user-chat"></a>Chat do usuário

O chat do usuário inclui mensagens de reunião particulares, um para um e um para muitos.

Quando um novo usuário é criado, Teams lê o PDL do usuário e armazena todos os seus dados de chat nessa localização geográfica.

Para usuários existentes, se um administrador adicionar ou modificar o PDL de um usuário, os dados de chat desse usuário serão adicionados a uma fila de migração para serem movidos para a localização geográfica especificada.

O local de armazenamento para um chat de um para um ou um para muitos é baseado no PDL da pessoa que criou o chat. Se o PDL desse usuário for alterado, o chat será migrado para a nova localização geográfica. O local de armazenamento de um chat de reunião é baseado no PDL do organizador da reunião.

Para localizar o local atual dos dados de Teams de um usuário, conecte-se [ao Teams PowerShell](/powershell/module/teams/connect-microsoftteams) e execute o seguinte comando:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Mensagens de canal

Cada Microsoft 365 grupo tem um PDL (Preferred Data Location) que indica a localização geográfica onde os dados relacionados devem ser armazenados. Teams usa o PDL para o grupo associado a cada equipe para determinar onde armazenar dados de mensagens de canal para essa equipe. Isso inclui um chat que ocorre em uma reunião de canal.

Quando um usuário cria uma nova equipe, o PDL desse usuário determina qual PDL é atribuído ao Microsoft 365 grupo. O PDL do grupo determina onde os dados dessa equipe são armazenados. Se o PDL desse usuário for alterado posteriormente, o PDL do grupo não será alterado.

Para equipes existentes, se um administrador adicionar ou modificar o PDL para o grupo Microsoft 365 que faz o suporte a uma equipe, os dados de mensagens de canal dessa equipe serão adicionados a uma fila de migração a ser movida para a localização geográfica especificada.

A alteração da PDL do grupo Microsoft 365 enfileia os dados Teams para migrar para o local escolhido. No entanto, isso não migra automaticamente o site SharePoint ou arquivos associados ao Grupo. Você deve mover o site separadamente seguindo os procedimentos em [Move a SharePoint site para uma localização geográfica diferente.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations) Certifique-se de fazer as duas etapas para evitar Teams dados e SharePoint dados para um grupo em locais diferentes.

Para localizar o local atual dos dados de uma equipe, conecte-se ao [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) e execute o seguinte comando:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Experiência do Usuário

Teams Multi-Geo é perfeita para o usuário final. Depois que você alterar a PDL de um usuário ou grupo, os respectivos dados serão enfilados para migração e a migração ocorrerá automaticamente sem impacto para o usuário ou seu cliente Teams, mesmo que eles sejam ativos enquanto a migração ocorrer.

## <a name="see-also"></a>Confira também

[Configuração do locatário do Microsoft 365 Multi-Geo](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Administrar um ambiente multigeográfico](administering-a-multi-geo-environment.md)

[Administrar caixas de correio do Exchange Online em um ambiente multigeográfico](administering-exchange-online-multi-geo.md)
