---
title: Excluir um calendário de reserva
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use o centro de administração do Microsoft 365 ou o Windows PowerShell para excluir os calendários de reservas.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422437"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Excluir um calendário de reservas em reservas

Este artigo explica como você pode excluir um calendário de reserva indesejado. Você pode excluir o calendário de reserva no centro de administração do Microsoft 365 ou pode usar o PowerShell. O calendário de livros é uma caixa de correio no Exchange Online para que você exclua a conta de usuário correspondente para excluir o calendário de reserva.

> [!IMPORTANT]
> Todos os calendários de reserva criados no 2017 ou antes devem ser excluídos usando as instruções do PowerShell sobre este tópico. Todos os calendários de reserva criados no 2018 ou após podem ser excluídos no centro de administração do Microsoft 365.

O calendário de reserva é onde são armazenadas todas as informações relevantes sobre o calendário e os dados de reserva, incluindo:

- Informações comerciais, logotipos e horas de trabalho adicionadas quando o calendário de reserva foi criado
- Pessoal e serviços relevantes adicionados quando o calendário de reserva foi criado
- Todos os compromissos de livros e folga adicionados ao calendário de reserva após serem criados.

> [!WARNING]
> Depois que um calendário de reserva é excluído, essas informações adicionais também são excluídas permanentemente e não podem ser recuperadas.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Excluir um calendário de reserva no centro de administração do Microsoft 365

1. Vá para o centro de administração do Microsoft 365.

1. No Centro de administração, selecione **Usuários**.

   ![Imagem da interface do usuário de usuários no centro de administração do Microsoft 365](../media/bookings-admin-center-users.png)

1. Na página **Usuários Ativos**, escolha os nomes dos usuários que você deseja excluir e escolha **Excluir usuário**.

   ![Imagem da interface do usuário de exclusão no centro de administração do Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Excluir um calendário de reserva usando o PowerShell do Exchange Online

Confira [conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obter pré-requisitos e orientações para a conexão ao PowerShell do Exchange Online.

Para executar essas etapas, você deve usar uma janela ativa de comando do Microsoft PowerShell, escolhendo a opção "executar como administrador".

1. Insira o seguinte comando:

   ```PowerShell
    $user = get-credential
   ```

1. Quando for solicitado, faça logon com as credenciais de administrador de locatários no locatário do Microsoft 365 que hospeda o calendário de reserva que você deseja excluir permanentemente.

1. No prompt de comando do PowerShell, digite este comando:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Insira o seguinte comando:

   ```PowerShell
    Import-PSSession $s
   ```

1. Quando este comando terminar o processamento, insira o seguinte comando para obter uma lista das caixas de correio de reserva em seu locatário:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Digite o seguinte comando:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Tenha cuidado para digitar o nome exato do alias de caixa de correio de reserva que você deseja excluir permanentemente.

1. Para verificar se o calendário foi excluído, insira o seguinte comando:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   O calendário excluído não será exibido na saída.
