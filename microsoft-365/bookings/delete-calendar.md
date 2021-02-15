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
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="db0c2-103">Excluir um calendário de reserva no Bookings</span><span class="sxs-lookup"><span data-stu-id="db0c2-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="db0c2-104">Este artigo explica como você pode excluir um calendário de reserva indesejado.</span><span class="sxs-lookup"><span data-stu-id="db0c2-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="db0c2-105">Você pode excluir o calendário de reserva no centro de administração do Microsoft 365 ou usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db0c2-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="db0c2-106">O calendário do Bookings é uma caixa de correio no Exchange Online para que você exclua a conta de usuário correspondente para excluir o calendário de reserva.</span><span class="sxs-lookup"><span data-stu-id="db0c2-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db0c2-107">Todos os calendários de reserva criados em 2017 ou anterior devem ser excluídos usando as instruções do PowerShell neste tópico.</span><span class="sxs-lookup"><span data-stu-id="db0c2-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="db0c2-108">Todos os calendários de reserva criados em 2018 ou depois podem ser excluídos no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db0c2-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="db0c2-109">O calendário de reserva é onde todas as informações relevantes sobre esse calendário e dados de reserva são armazenadas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="db0c2-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="db0c2-110">Informações comerciais, logotipo e horário de trabalho adicionados quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="db0c2-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="db0c2-111">Equipe e serviços relevantes adicionados quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="db0c2-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="db0c2-112">Todos os compromissos de reserva e folga adicionados ao calendário de reserva depois que ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="db0c2-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="db0c2-113">Depois que um calendário de reserva é excluído, essas informações adicionais também são excluídas permanentemente e não podem ser recuperadas.</span><span class="sxs-lookup"><span data-stu-id="db0c2-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="db0c2-114">Excluir um calendário de reserva no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="db0c2-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="db0c2-115">Vá para o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db0c2-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="db0c2-116">No Centro de administração, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="db0c2-116">In the Admin center, select **Users**.</span></span>

   ![Imagem da interface do usuário de usuários no Centro de administração do Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="db0c2-118">Na página **Usuários Ativos**, escolha os nomes dos usuários que você deseja excluir e escolha **Excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="db0c2-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Imagem da exclusão da interface do usuário no centro de administração do Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="db0c2-120">Excluir um calendário de reserva usando o PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="db0c2-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="db0c2-121">Consulte [Conectar-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) para obter pré-requisitos e diretrizes para se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="db0c2-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="db0c2-122">Para executar essas etapas, você deve estar usando uma janela de comando ativa do Microsoft PowerShell que você executava escolhendo a opção "Executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="db0c2-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="db0c2-123">Insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db0c2-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="db0c2-124">Quando solicitado, faça logoff com as credenciais de administrador de locatários no locatário do Microsoft 365 que hospeda o calendário de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="db0c2-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="db0c2-125">No prompt de comando do PowerShell, insira este comando:</span><span class="sxs-lookup"><span data-stu-id="db0c2-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="db0c2-126">Insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db0c2-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="db0c2-127">Quando esse comando terminar o processamento, insira o seguinte comando para obter uma lista das caixas de correio de reserva em seu locatário:</span><span class="sxs-lookup"><span data-stu-id="db0c2-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="db0c2-128">Digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db0c2-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="db0c2-129">Tenha cuidado para digitar o nome exato do alias da caixa de correio de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="db0c2-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="db0c2-130">Para verificar se o calendário foi excluído, digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="db0c2-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="db0c2-131">O calendário excluído não aparecerá na saída.</span><span class="sxs-lookup"><span data-stu-id="db0c2-131">The deleted calendar will not appear in the output.</span></span>
