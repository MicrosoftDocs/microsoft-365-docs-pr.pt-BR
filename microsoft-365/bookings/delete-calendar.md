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
description: Use o Centro de administração do Microsoft 365 ou Windows PowerShell excluir calendários do Bookings.
ms.openlocfilehash: 1ef67ce4dbf67da6f081106815f76ff85f11ef92
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288438"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="e05aa-103">Excluir um calendário de reserva no Bookings</span><span class="sxs-lookup"><span data-stu-id="e05aa-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="e05aa-104">Este artigo explica como você pode excluir um calendário de reserva indesejado.</span><span class="sxs-lookup"><span data-stu-id="e05aa-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="e05aa-105">Você pode excluir o calendário de reserva no Centro de administração do Microsoft 365 ou pode usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e05aa-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="e05aa-106">O calendário do Bookings é uma caixa de correio no Exchange Online para que você exclua a conta de usuário correspondente para excluir o calendário de reserva.</span><span class="sxs-lookup"><span data-stu-id="e05aa-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e05aa-107">Todos os calendários de reserva criados em 2017 ou anterior devem ser excluídos usando as instruções do PowerShell neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e05aa-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="e05aa-108">Todos os calendários de reserva criados em 2018 ou posterior podem ser excluídos no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e05aa-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="e05aa-109">O calendário de reserva é onde todas as informações relevantes sobre esse calendário de reserva e dados são armazenadas, incluindo:</span><span class="sxs-lookup"><span data-stu-id="e05aa-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="e05aa-110">Informações comerciais, logotipo e horários de trabalho adicionados quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="e05aa-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="e05aa-111">Equipe e serviços relevantes adicionados quando o calendário de reserva foi criado</span><span class="sxs-lookup"><span data-stu-id="e05aa-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="e05aa-112">Todas as reservas e compromissos de folga adicionados ao calendário de reserva depois que ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="e05aa-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="e05aa-113">Depois que um calendário de reserva é excluído, essas informações adicionais também são excluídas permanentemente e não podem ser recuperadas.</span><span class="sxs-lookup"><span data-stu-id="e05aa-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e05aa-114">Excluir um calendário de reserva no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e05aa-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="e05aa-115">Vá para o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e05aa-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="e05aa-116">No Centro de administração, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="e05aa-116">In the Admin center, select **Users**.</span></span>

   ![Imagem da interface do usuário de usuários no Centro de administração do Microsoft 365](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="e05aa-118">Na página **Usuários Ativos**, escolha os nomes dos usuários que você deseja excluir e escolha **Excluir usuário**.</span><span class="sxs-lookup"><span data-stu-id="e05aa-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Imagem da interface do usuário excluir no Centro de administração do Microsoft 365](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="e05aa-120">Excluir um calendário de reserva usando Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e05aa-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="e05aa-121">Consulte [Conexão para Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) para obter pré-requisitos e diretrizes para se conectar ao Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e05aa-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="e05aa-122">Para executar essas etapas, você deve estar usando uma janela de comando ativa do Microsoft PowerShell que você executava escolhendo a opção "Executar como administrador".</span><span class="sxs-lookup"><span data-stu-id="e05aa-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="e05aa-123">Em uma janela do Windows PowerShell, carregue o módulo EXO V2 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e05aa-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="e05aa-124">Se você já tiver [instalado o módulo EXO v2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), o comando anterior funcionará como escrito.</span><span class="sxs-lookup"><span data-stu-id="e05aa-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="e05aa-125">O comando que você precisa executar usa a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e05aa-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="e05aa-126">_\<UPN\>_ é a sua conta no formato de nome principal do usuário (por exemplo, `john@contoso.com`).</span><span class="sxs-lookup"><span data-stu-id="e05aa-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="e05aa-127">Quando você for solicitado, faça logoff com credenciais de administrador de locatário para o locatário Microsoft 365 que hospeda o calendário de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e05aa-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="e05aa-128">Depois que esse comando terminar de processar, insira o seguinte comando para obter uma lista das caixas de correio de reserva em seu locatário:</span><span class="sxs-lookup"><span data-stu-id="e05aa-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="e05aa-129">Digite o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e05aa-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="e05aa-130">Tenha cuidado para digitar o nome exato do alias de caixa de correio de reserva que você deseja excluir permanentemente.</span><span class="sxs-lookup"><span data-stu-id="e05aa-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="e05aa-131">Para verificar se o calendário foi excluído, insira o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e05aa-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="e05aa-132">O calendário excluído não aparecerá na saída.</span><span class="sxs-lookup"><span data-stu-id="e05aa-132">The deleted calendar will not appear in the output.</span></span>
