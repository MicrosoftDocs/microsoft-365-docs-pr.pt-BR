---
title: Excluir um calendário de reservas
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Use o Centro de administração do Microsoft 365 ou o Windows PowerShell para excluir calendários do Bookings.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126644"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Excluir um calendário de reserva no Bookings

Este artigo explica como você pode excluir um calendário de reserva indesejado. Você pode excluir o calendário de reserva no centro de administração do Microsoft 365 ou usar o PowerShell. O calendário do Bookings é uma caixa de correio no Exchange Online para que você exclua a conta de usuário correspondente para excluir o calendário de reserva.

> [!IMPORTANT]
> Todos os calendários de reserva criados em 2017 ou anterior devem ser excluídos usando as instruções do PowerShell neste tópico. Todos os calendários de reserva criados em 2018 ou depois podem ser excluídos no Centro de administração do Microsoft 365.

O calendário de reserva é onde todas as informações relevantes sobre esse calendário e dados de reserva são armazenadas, incluindo:

- Informações comerciais, logotipo e horário de trabalho adicionados quando o calendário de reserva foi criado
- Equipe e serviços relevantes adicionados quando o calendário de reserva foi criado
- Todos os compromissos de reserva e folga adicionados ao calendário de reserva depois que ele foi criado.

> [!WARNING]
> Depois que um calendário de reserva é excluído, essas informações adicionais também são excluídas permanentemente e não podem ser recuperadas.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Excluir um calendário de reserva no centro de administração do Microsoft 365

1. Vá para o centro de administração do Microsoft 365.

1. No Centro de administração, selecione **Usuários**.

   ![Imagem da interface do usuário de usuários no Centro de administração do Microsoft 365](../media/bookings-admin-center-users.png)

1. Na página **Usuários Ativos**, escolha os nomes dos usuários que você deseja excluir e escolha **Excluir usuário**.

   ![Imagem da exclusão da interface do usuário no centro de administração do Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Excluir um calendário de reserva usando o PowerShell do Exchange Online

Consulte [Conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) para obter pré-requisitos e diretrizes para se conectar ao PowerShell do Exchange Online.

Para executar essas etapas, você deve estar usando uma janela de comando ativa do Microsoft PowerShell que você executava escolhendo a opção "Executar como administrador".

1. Insira o seguinte comando:

   ```PowerShell
    $user = get-credential
   ```

1. Quando solicitado, faça logoff com as credenciais de administrador de locatários no locatário do Microsoft 365 que hospeda o calendário de reserva que você deseja excluir permanentemente.

1. No prompt de comando do PowerShell, insira este comando:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Insira o seguinte comando:

   ```PowerShell
    Import-PSSession $s
   ```

1. Quando esse comando terminar o processamento, insira o seguinte comando para obter uma lista das caixas de correio de reserva em seu locatário:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Digite o seguinte comando:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Tenha cuidado para digitar o nome exato do alias da caixa de correio de reserva que você deseja excluir permanentemente.

1. Para verificar se o calendário foi excluído, digite o seguinte comando:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   O calendário excluído não aparecerá na saída.
