---
title: Compartilhar calendários com usuários externos
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd
description: 'Saiba como permitir que seus usuários compartilhem seus calendários com usuários externos para reuniões e compromissos. '
ms.openlocfilehash: 6e5a4a3a7e29dcbb6b19aeb1dd3b914ff98eb06e
ms.sourcegitcommit: 708857a82eab3d37da1dec027399b09bd306a5dd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44249867"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="077ac-103">Compartilhar calendários com usuários externos</span><span class="sxs-lookup"><span data-stu-id="077ac-103">Share calendars with external users</span></span>

<span data-ttu-id="077ac-104">Muitas vezes, é necessário agendar reuniões com pessoas de fora de sua organização.</span><span class="sxs-lookup"><span data-stu-id="077ac-104">It's often necessary to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="077ac-105">Para simplificar o processo de encontrar horários de reuniões mutuamente aceitos, a Microsoft 365 permite que você disponibilize calendários para "usuários externos", aqueles que precisam ver o horário de disponibilidade, mas não têm contas de usuário para seu ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="077ac-105">To simplify the process of finding mutually agreeable meeting times, Microsoft 365 enables you to make calendars available to "external users," those who need to see free/busy time but don't have user accounts for your Microsoft 365 environment.</span></span>
  
<span data-ttu-id="077ac-106">O compartilhamento de calendário é uma configuração global, o que significa que você, o administrador, pode habilitá-lo para todos os usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="077ac-106">Calendar sharing is a global setting, meaning that you, the admin, can enable it for all users in the tenant.</span></span> <span data-ttu-id="077ac-107">Depois que o compartilhamento é habilitado, os usuários podem usar o Outlook Web App para compartilhar seus calendários com qualquer pessoa dentro ou fora da organização.</span><span class="sxs-lookup"><span data-stu-id="077ac-107">Once sharing is enabled, users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="077ac-108">As pessoas dentro da organização podem exibir o calendário compartilhado lado a lado com seus próprios calendários.</span><span class="sxs-lookup"><span data-stu-id="077ac-108">People inside the organization can view the shared calendar side-by-side with their own.</span></span> <span data-ttu-id="077ac-109">As pessoas de fora da organização receberão uma URL que poderá ser usada para exibir o calendário.</span><span class="sxs-lookup"><span data-stu-id="077ac-109">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="077ac-110">Os usuários decidem quando e quanto compartilhar e quando manter seus calendários particulares.</span><span class="sxs-lookup"><span data-stu-id="077ac-110">Users decide when to share, how much to share, and when to keep their calendars private.</span></span>
  
> [!NOTE]
> <span data-ttu-id="077ac-p103">Se você quiser compartilhar agendas com uma organização que utiliza o Exchange Server 2013 (uma solução instalada no local), o administrador do Exchange precisará configurar uma relação de autenticação com a nuvem. Isso é conhecido como "federação" e deve atender aos requisitos mínimos de software. Consulte [Compartilhamento](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="077ac-p103">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud. This is known as "federation" and must meet minimum software requirements. See [Sharing](https://technet.microsoft.com/library/dd638083%28v=exchg.150%29.aspx) for more information.</span></span> 
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="077ac-114">Habilitar o compartilhamento de calendários usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="077ac-114">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="077ac-115">No centro de administração, vá para **Settings** \> **configurações**de configurações.</span><span class="sxs-lookup"><span data-stu-id="077ac-115">In the admin center, go to **Settings** \> **Settings**.</span></span> 
    
2. <span data-ttu-id="077ac-116">Na guia **Serviços** , selecione **calendário**.</span><span class="sxs-lookup"><span data-stu-id="077ac-116">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="077ac-117">Na página **calendário** que é aberta, escolha se você deseja permitir que seus usuários compartilhem seus calendários com pessoas de fora de sua organização que tenham o Microsoft 365 ou o Exchange.</span><span class="sxs-lookup"><span data-stu-id="077ac-117">On the **Calendar** page that opens, choose whether you want to let your users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span>
    
4. <span data-ttu-id="077ac-118">Escolha se você deseja permitir que usuários anônimos (usuários sem credenciais de logon) acessem calendários por meio de um convite por email.</span><span class="sxs-lookup"><span data-stu-id="077ac-118">Choose whether you want to allow anonymous users (users without logon credentials) to access calendars via an email invitation.</span></span>

5. <span data-ttu-id="077ac-119">Escolha quais tipos de informações de calendário disponibilizar para os usuários.</span><span class="sxs-lookup"><span data-stu-id="077ac-119">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="077ac-120">Você pode permitir todas as informações ou limitá-la somente a horário, assunto e local.</span><span class="sxs-lookup"><span data-stu-id="077ac-120">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

    
## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="077ac-121">Convidar pessoas para acessarem os calendários</span><span class="sxs-lookup"><span data-stu-id="077ac-121">Invite people to access calendars</span></span>

<span data-ttu-id="077ac-p105">Depois que o compartilhamento for habilitado para o locatário, os proprietários de calendários poderão enviar convites a usuários específicos. Consulte [Compartilhar seu calendário no Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="077ac-p105">Once sharing is enabled for the tenant, calendar owners can extend invitations to specific users. See [Sharing your calendar in Outlook Web App](https://support.office.com/article/7ecef8ae-139c-40d9-bae2-a23977ee58d5.aspx) for instructions.</span></span> 
  
