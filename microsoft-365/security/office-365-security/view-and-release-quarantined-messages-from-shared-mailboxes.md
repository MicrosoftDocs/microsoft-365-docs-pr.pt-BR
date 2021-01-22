---
title: Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Os usuários podem aprender a exibir e agir em mensagens em quarentena que foram enviadas a caixas de correio compartilhadas para as quais eles têm permissões.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3efccca375745b0850c91039165b72a7d6f0bcb3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931441"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas

> [!NOTE]
> Os recursos descritos neste artigo estão atualmente na visualização, não estão disponíveis para todos e estão sujeitos a alterações.

Os usuários podem gerenciar mensagens em quarentena onde são um dos destinatários, conforme descrito em [Find e release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md). Mas e as caixas de correio compartilhadas onde o usuário tem permissões de Acesso Total e Enviar como ou Enviar em nome de para a caixa de correio, conforme descrito em caixas de correio [compartilhadas no Exchange Online?](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)

Anteriormente, a capacidade de os usuários gerenciarem mensagens em quarentena enviadas a uma caixa de correio compartilhada exigiam que os administradores deixem o automapeamento habilitado para a caixa de correio compartilhada (ele é habilitado por padrão quando um administrador dá a um usuário acesso a outra caixa de correio). No entanto, dependendo do tamanho e do número de caixas de correio às  que o usuário tem acesso, o desempenho pode ser prejudicado à medida que o Outlook tenta abrir todas as caixas de correio às que o usuário tem acesso. Por esse motivo, muitos administradores optam por [remover o autopping para caixas de correio compartilhadas.](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Agora, o automapeamento não é mais necessário para que os usuários gerenciem mensagens em quarentena que foram enviadas para caixas de correio compartilhadas. Funciona apenas. Há dois métodos diferentes para acessar mensagens em quarentena que foram enviadas para uma caixa de correio compartilhada:

- Se o administrador tiver habilitado as notificações de spam do usuário final em políticas anti-spam, qualquer usuário que  tenha acesso às notificações de spam do usuário final na caixa de correio compartilhada poderá clicar no botão Revisão na notificação para ir para a quarentena no Centro de Conformidade e & Segurança. [](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) Observe que esse método só permite que os usuários gerenciem mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. Os usuários não podem gerenciar suas próprias mensagens de quarentena nesse contexto.

- O usuário pode [ir para a quarentena no Centro de Conformidade & segurança.](find-and-release-quarantined-messages-as-a-user.md) Por padrão, apenas as mensagens que foram enviadas para o usuário são mostradas. No entanto, o usuário pode alterar os resultados de classificação (o botão **ID** da mensagem  por padrão) para o endereço de email do destinatário, insira o endereço de **email** da caixa de correio compartilhada e clique em Atualizar para ver as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. 

  ![Classificar mensagens em quarentena por endereço de email do destinatário.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Independentemente do método, os usuários podem evitar confusão incluindo a coluna **Destinatário** para mensagens em quarentena. O número máximo de colunas a exibir é 7, portanto, o usuário precisará clicar em Modificar  **colunas,** remover  uma coluna existente (por **exemplo,** tipo de política ), selecionar Destinatário e clicar em Salvar ou Salvar como **padrão.**

  ![Remova a coluna Tipo de Política e adicione a coluna Destinatário à quarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Tenha em mente

- O primeiro usuário a agir na mensagem em quarentena decide o nome da mensagem para todos que usam a caixa de correio compartilhada. Por exemplo, se uma caixa de correio compartilhada for acessada por 10 usuários e um usuário decidir excluir a mensagem de quarentena, a mensagem será excluída para todos os 10 usuários. Da mesma forma, se um usuário decidir liberar a mensagem, ela será liberada para a caixa de correio compartilhada e poderá ser acessada por todos os outros usuários da caixa de correio compartilhada.

- Atualmente, o **botão Bloquear** remetente não está disponível no flyout Detalhes para mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. 

- Para gerenciar mensagens em quarentena para a caixa de correio compartilhada no PowerShell do [Exchange Online,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)o usuário final precisará usar o cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) com o endereço de email da caixa de correio compartilhada para o valor do parâmetro _RecipientAddress_ para identificar as mensagens. Por exemplo:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Em seguida, o usuário final pode selecionar uma mensagem em quarentena na lista para exibir ou tomar medidas.

  Este exemplo mostra todas as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada e, em seguida, libera a primeira mensagem da lista da quarentena (a primeira mensagem na lista é 0, a segunda é 1 e assim por diante).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte os seguintes tópicos:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
