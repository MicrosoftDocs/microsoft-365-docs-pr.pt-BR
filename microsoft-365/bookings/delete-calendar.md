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
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="e8ab0-103">Excluir um calendário de reservas em reservas</span><span class="sxs-lookup"><span data-stu-id="e8ab0-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="e8ab0-104">Este artigo explica como você pode excluir um calendário de reserva indesejado.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="e8ab0-105">Você pode excluir o calendário de reserva no centro de administração do Microsoft 365 ou pode usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="e8ab0-106">O calendário de livros é uma caixa de correio no Exchange Online para que você exclua a conta de usuário correspondente para excluir o calendário de reserva.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8ab0-107">Todos os calendários de reserva criados no 2017 ou antes devem ser excluídos usando as instruções do PowerShell sobre este tópico.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="e8ab0-108">Todos os calendários de reserva criados no 2018 ou após podem ser excluídos no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e8ab0-109">O calendário de reserva é onde são armazenadas todas as informações relevantes sobre o calendário e os dados de reserva, incluindo:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="e8ab0-110">Informações comerciais, logotipos e horas de trabalho adicionadas quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="e8ab0-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="e8ab0-111">Pessoal e serviços relevantes adicionados quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="e8ab0-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="e8ab0-112">Todos os compromissos de livros e folga adicionados ao calendário de reserva após serem criados.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="e8ab0-113">Depois que um calendário de reserva é excluído, essas informações adicionais também são excluídas permanentemente e não podem ser recuperadas.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e8ab0-114">Excluir um calendário de reserva no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8ab0-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e8ab0-115">Vá para o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="e8ab0-116">No Centro de administração, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-116">In the Admin center, select **Users**.</span></span>

   ![Imagem da interface do usuário de usuários no centro de administração do Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="e8ab0-118">Na página **Usuários Ativos**, escolha os nomes dos usuários que você deseja excluir e escolha **Excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Imagem da interface do usuário de exclusão no centro de administração do Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="e8ab0-120">Excluir um calendário de reserva usando o PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e8ab0-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="e8ab0-121">Confira [conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) para obter pré-requisitos e orientações para a conexão ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="e8ab0-122">Para executar essas etapas, você deve usar uma janela ativa de comando do Microsoft PowerShell, escolhendo a opção "executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="e8ab0-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="e8ab0-123">Insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="e8ab0-124">Quando for solicitado, faça logon com as credenciais de administrador de locatários no locatário do Microsoft 365 que hospeda o calendário de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="e8ab0-125">No prompt de comando do PowerShell, digite este comando:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="e8ab0-126">Insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="e8ab0-127">Quando este comando terminar o processamento, insira o seguinte comando para obter uma lista das caixas de correio de reserva em seu locatário:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="e8ab0-128">Digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="e8ab0-129">Tenha cuidado para digitar o nome exato do alias de caixa de correio de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="e8ab0-130">Para verificar se o calendário foi excluído, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e8ab0-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="e8ab0-131">O calendário excluído não será exibido na saída.</span><span class="sxs-lookup"><span data-stu-id="e8ab0-131">The deleted calendar will not appear in the output.</span></span>
