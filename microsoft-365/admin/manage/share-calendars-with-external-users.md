---
title: Compartilhar calendários com usuários externos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Saiba como permitir que seus usuários compartilhem seus calendários com usuários externos para reuniões e compromissos. '
ms.openlocfilehash: 972e8376ae3d71b11205d4a6611dc6900c063ffe
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780056"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="a7983-103">Compartilhar calendários com usuários externos</span><span class="sxs-lookup"><span data-stu-id="a7983-103">Share calendars with external users</span></span>

<span data-ttu-id="a7983-104">Muitas vezes, é necessário agendar reuniões com pessoas de fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7983-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="a7983-105">Para simplificar o processo de encontrar horários de reuniões mutuamente aceitos, a Microsoft 365 permite que você disponibilize calendários para "usuários externos", aqueles que precisam ver o horário de disponibilidade, mas não têm contas de usuário para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7983-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="a7983-106">O compartilhamento de calendário é uma configuração global, o que significa que você, o administrador, pode habilitá-lo para todos os usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="a7983-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="a7983-107">Depois que o compartilhamento é habilitado, os usuários podem usar o Outlook Web App para compartilhar seus calendários com qualquer pessoa dentro ou fora da organização.</span><span class="sxs-lookup"><span data-stu-id="a7983-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="a7983-108">As pessoas dentro da organização podem exibir o calendário compartilhado lado a lado com seus próprios calendários.</span><span class="sxs-lookup"><span data-stu-id="a7983-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="a7983-109">As pessoas de fora da organização receberão uma URL que poderá ser usada para exibir o calendário.</span><span class="sxs-lookup"><span data-stu-id="a7983-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="a7983-110">Os usuários decidem quando e quanto compartilhar e quando manter seus calendários particulares.</span><span class="sxs-lookup"><span data-stu-id="a7983-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7983-111">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span><span class="sxs-lookup"><span data-stu-id="a7983-111">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="a7983-112">This is known as "federation" and must meet minimum software requirements.</span><span class="sxs-lookup"><span data-stu-id="a7983-112">This is known as "federation" and must meet minimum software requirements.</span></span> <span data-ttu-id="a7983-113">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span><span class="sxs-lookup"><span data-stu-id="a7983-113">See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="a7983-114">Habilitar o compartilhamento de calendários usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a7983-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a7983-115">No centro de administração, vá para configurações da organização de **configurações** \> **Org Settings**.</span><span class="sxs-lookup"><span data-stu-id="a7983-115">In the admin center, go to **Settings** \> **Org Settings**.</span></span> 
    
2. <span data-ttu-id="a7983-116">Na guia **Serviços** , selecione **calendário**.</span><span class="sxs-lookup"><span data-stu-id="a7983-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="a7983-117">Na página **calendário** que é aberta, escolha se você deseja permitir que seus usuários compartilhem seus calendários com pessoas de fora de sua organização que tenham o Microsoft 365 ou o Exchange.</span><span class="sxs-lookup"><span data-stu-id="a7983-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="a7983-118">Escolha se você deseja permitir que usuários anônimos (usuários sem credenciais de logon) acessem calendários por meio de um convite por email.</span><span class="sxs-lookup"><span data-stu-id="a7983-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="a7983-119">Escolha quais tipos de informações de calendário disponibilizar para os usuários.</span><span class="sxs-lookup"><span data-stu-id="a7983-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="a7983-120">Você pode permitir todas as informações ou limitá-la somente a horário, assunto e local.</span><span class="sxs-lookup"><span data-stu-id="a7983-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="a7983-121">Convidar pessoas para acessarem os calendários</span><span class="sxs-lookup"><span data-stu-id="a7983-121">Invite people to access calendars</span></span>

<span data-ttu-id="a7983-122">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users.</span><span class="sxs-lookup"><span data-stu-id="a7983-122">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="a7983-123">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span><span class="sxs-lookup"><span data-stu-id="a7983-123">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span> 
  
