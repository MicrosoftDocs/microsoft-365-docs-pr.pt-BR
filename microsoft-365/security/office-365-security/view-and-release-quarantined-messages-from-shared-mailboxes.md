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
description: Os usuários podem aprender a exibir e agir em mensagens em quarentena enviadas a caixas de correio compartilhadas às quais eles têm permissões.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb915ad6ad6e6130d8704339559f4c370cef3a20
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599506"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Exibir e liberar mensagens em quarentena de caixas de correio compartilhadas

> [!NOTE]
> Os recursos descritos neste artigo estão atualmente em Visualização, não estão disponíveis para todos e estão sujeitos a alterações.

Os usuários podem gerenciar mensagens em quarentena em que são um dos destinatários, conforme descrito em [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md). Mas e as caixas de correio compartilhadas em que o usuário tem permissões de Acesso Total e Enviar como ou Enviar em Nome para a caixa de correio, conforme descrito em Caixas de correio compartilhadas em [Exchange Online?](/exchange/collaboration-exo/shared-mailboxes)

Anteriormente, a capacidade dos usuários de gerenciar mensagens em quarentena enviadas a uma caixa de correio compartilhada exigia que os administradores deixassem a automação habilitada para a caixa de correio compartilhada (ela é habilitada por padrão quando um administrador dá acesso ao usuário a outra caixa de correio). No entanto, dependendo do tamanho e do número de caixas de correio às  que o usuário tem acesso, o desempenho pode sofrer à medida que o Outlook tenta abrir todas as caixas de correio às que o usuário tem acesso. Por esse motivo, muitos administradores optam por [remover o automapping para caixas de correio compartilhadas.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Agora, a automação não é mais necessária para que os usuários gerenciem mensagens em quarentena enviadas para caixas de correio compartilhadas. Ele só funciona. Há dois métodos diferentes para acessar mensagens em quarentena enviadas a uma caixa de correio compartilhada:

- Se o administrador habilitar notificações de spam do usuário final em políticas [anti-spam](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), qualquer usuário que  tenha acesso às notificações de & spam do usuário final na caixa de correio compartilhada poderá clicar no botão Revisar na notificação para ir para a quarentena no Centro de Conformidade e Segurança. Observe que esse método só permite que os usuários gerenciem mensagens em quarentena enviadas para a caixa de correio compartilhada. Os usuários não podem gerenciar suas próprias mensagens de quarentena neste contexto.

- O usuário pode [ir para a quarentena no Centro de Conformidade & Segurança.](find-and-release-quarantined-messages-as-a-user.md) Por padrão, apenas as mensagens enviadas ao usuário são mostradas. No entanto, o usuário pode alterar os resultados de classificação (o botão **ID** da mensagem  por padrão) para o endereço de **email** do destinatário, inserir o endereço de email da caixa de correio compartilhada e clicar em Atualizar para ver as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada. 

  ![Classificação de mensagens em quarentena por endereço de email do destinatário.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Independentemente do método, os usuários podem evitar confusão incluindo a **coluna Destinatário** para mensagens em quarentena. O número máximo de colunas a ser exibido é 7, portanto, o usuário precisará clicar em Modificar **colunas,** remover uma coluna existente (por **exemplo,** tipo de política ), selecionar **Destinatário** e clicar em **Salvar** ou Salvar como **padrão**.

  ![Remova a coluna Tipo de Política e adicione a coluna Destinatário à quarentena.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Tenha em mente

- O primeiro usuário a agir na mensagem em quarentena decide o destino da mensagem para todos que usam a caixa de correio compartilhada. Por exemplo, se uma caixa de correio compartilhada for acessada por 10 usuários e um usuário decidir excluir a mensagem de quarentena, a mensagem será excluída para todos os 10 usuários. Da mesma forma, se um usuário decidir liberar a mensagem, ela será liberada para a caixa de correio compartilhada e será acessível por todos os outros usuários da caixa de correio compartilhada.

- Atualmente, o **botão Bloquear remetente** não está disponível no sobremenu **de** Detalhes para mensagens em quarentena enviadas à caixa de correio compartilhada.

- Em relação às operações de quarentena para caixas de correio compartilhadas, se você usar grupos de segurança aninhados para conceder acesso a uma caixa de correio compartilhada, recomendamos não mais do que dois níveis de grupos aninhados. Por exemplo, o Grupo A é membro do Grupo B, que é membro do Grupo C. Para atribuir permissões a uma caixa de correio compartilhada, não adicione o usuário ao Grupo A e atribua o Grupo C à caixa de correio compartilhada.  

- Para gerenciar mensagens em quarentena para a caixa de correio compartilhada no [Exchange Online PowerShell,](/powershell/exchange/connect-to-exchange-online-powershell)o usuário final precisará usar o cmdlet [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) com endereço de email de caixa de correio compartilhado para o valor do parâmetro _RecipientAddress_ para identificar as mensagens. Por exemplo:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Em seguida, o usuário final pode selecionar uma mensagem em quarentena na lista para exibir ou tomar medidas.

  Este exemplo mostra todas as mensagens em quarentena que foram enviadas para a caixa de correio compartilhada e, em seguida, libera a primeira mensagem na lista de quarentena (a primeira mensagem na lista é 0, a segunda é 1 e assim por diante).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte os seguintes tópicos:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
