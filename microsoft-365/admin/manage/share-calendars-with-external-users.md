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
description: Habilita o compartilhamento de calendário no centro de administração Microsoft 365 para que os usuários possam compartilhar seus calendários com qualquer pessoa dentro ou fora da organização.
ms.openlocfilehash: 6f4c215403e16ac6658619e50e6115606f106397
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582711"
---
# <a name="share-calendars-with-external-users"></a><span data-ttu-id="605d2-103">Compartilhar calendários com usuários externos</span><span class="sxs-lookup"><span data-stu-id="605d2-103">Share calendars with external users</span></span>

<span data-ttu-id="605d2-104">Às vezes, é necessário que os usuários agendem reuniões com pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="605d2-104">It's sometimes necessary for your users to schedule meetings with people outside your organization.</span></span> <span data-ttu-id="605d2-105">Para simplificar o processo de encontrar horários comuns de reunião, Microsoft 365 permite disponibilizar calendários para essas pessoas.</span><span class="sxs-lookup"><span data-stu-id="605d2-105">To simplify the process of finding common meeting times, Microsoft 365 enables you to make calendars available to these people.</span></span> <span data-ttu-id="605d2-106">São pessoas que precisam ver os horários de livre e ocupado dos usuários em sua organização, mas não têm contas de usuário para sua Microsoft 365 organização.</span><span class="sxs-lookup"><span data-stu-id="605d2-106">These are people who need to see free and busy times for users in your organization, but don't have user accounts for your Microsoft 365 organization.</span></span>

<span data-ttu-id="605d2-107">Você pode habilitar o compartilhamento de calendário para todos os usuários em sua organização no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="605d2-107">You can enable calendar sharing for all users in your organization in the Microsoft 365 admin center.</span></span> <span data-ttu-id="605d2-108">Depois que o compartilhamento for habilitado, os usuários poderão usar Outlook Web App compartilhar seus calendários com qualquer pessoa dentro ou fora da organização.</span><span class="sxs-lookup"><span data-stu-id="605d2-108">Once sharing is enabled, your users can use Outlook Web App to share their calendars with anyone inside or outside the organization.</span></span> <span data-ttu-id="605d2-109">As pessoas dentro da organização podem exibir o calendário compartilhado juntamente com seu próprio calendário.</span><span class="sxs-lookup"><span data-stu-id="605d2-109">People inside the organization can view the shared calendar along with their own calendar.</span></span> <span data-ttu-id="605d2-110">As pessoas de fora da organização receberão uma URL que poderá ser usada para exibir o calendário.</span><span class="sxs-lookup"><span data-stu-id="605d2-110">People outside the organization will be sent a URL that they can use to view the calendar.</span></span> <span data-ttu-id="605d2-111">Os usuários em sua organização decidem quando compartilhar e quanto compartilhar.</span><span class="sxs-lookup"><span data-stu-id="605d2-111">Users in your organization decide when to share and how much to share.</span></span>

> [!NOTE]
> <span data-ttu-id="605d2-112">Se você quiser compartilhar agendas com uma organização que utiliza o Exchange Server 2013 (uma solução instalada no local), o administrador do Exchange precisará configurar uma relação de autenticação com a nuvem.</span><span class="sxs-lookup"><span data-stu-id="605d2-112">If you want to share calendars with an organization that uses Exchange Server 2013 (an on-premises solution), the Exchange administrator will need to set up an authentication relationship with the cloud.</span></span> <span data-ttu-id="605d2-113">Isso é conhecido como federação e deve atender aos requisitos mínimos de software.</span><span class="sxs-lookup"><span data-stu-id="605d2-113">This is known as federation, and must meet minimum software requirements.</span></span> <span data-ttu-id="605d2-114">Consulte [Compartilhamento](/exchange/sharing-exchange-2013-help) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="605d2-114">See [Sharing](/exchange/sharing-exchange-2013-help) for more information.</span></span>
  
## <a name="enable-calendar-sharing-using-the-microsoft-365-admin-center"></a><span data-ttu-id="605d2-115">Habilitar o compartilhamento de calendário usando o Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="605d2-115">Enable calendar sharing using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="605d2-116">No centro de administração, vá **para** Configurações \> **Org Configurações**.</span><span class="sxs-lookup"><span data-stu-id="605d2-116">In the admin center, go to **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="605d2-117">Na guia **Serviços,** selecione **Calendário**.</span><span class="sxs-lookup"><span data-stu-id="605d2-117">On the **Services** tab, select **Calendar**.</span></span>
  
3. <span data-ttu-id="605d2-118">Na página **Calendário,** escolha se deseja permitir que os usuários compartilhem seus calendários com pessoas de fora da sua organização que tenham Microsoft 365 ou Exchange.</span><span class="sxs-lookup"><span data-stu-id="605d2-118">On the **Calendar** page, choose whether you want to let users share their calendars with people outside of your organization who have Microsoft 365 or Exchange.</span></span> <span data-ttu-id="605d2-119">Escolha se deseja permitir que usuários anônimos (usuários sem credenciais) acessem calendários por meio de um convite de email.</span><span class="sxs-lookup"><span data-stu-id="605d2-119">Choose whether you want to allow anonymous users (users without credentials) to access calendars via an email invitation.</span></span>

4. <span data-ttu-id="605d2-120">Escolha que tipo de informações de calendário disponibilizar aos usuários.</span><span class="sxs-lookup"><span data-stu-id="605d2-120">Choose what type of calendar information to make available to users.</span></span> <span data-ttu-id="605d2-121">Você pode permitir todas as informações ou limitá-la somente a hora ou hora, assunto e local somente.</span><span class="sxs-lookup"><span data-stu-id="605d2-121">You can allow all information, or limit it to time only or time, subject, and location only.</span></span>

## <a name="invite-people-to-access-calendars"></a><span data-ttu-id="605d2-122">Convidar pessoas para acessarem os calendários</span><span class="sxs-lookup"><span data-stu-id="605d2-122">Invite people to access calendars</span></span>

<span data-ttu-id="605d2-123">Depois que o compartilhamento é habilitado, os proprietários de calendários podem estender convites para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="605d2-123">Once sharing is enabled, calendar owners can extend invitations to specific users.</span></span> <span data-ttu-id="605d2-124">Consulte [Compartilhar seu calendário no Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="605d2-124">See [Sharing your calendar in Outlook Web App](https://support.microsoft.com/office/7ecef8ae-139c-40d9-bae2-a23977ee58d5) for instructions.</span></span>

## <a name="related-content"></a><span data-ttu-id="605d2-125">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="605d2-125">Related content</span></span>

<span data-ttu-id="605d2-126">[Ativar ou desativar o compartilhamento externo para um site](/sharepoint/change-external-sharing-site) (artigo)</span><span class="sxs-lookup"><span data-stu-id="605d2-126">[Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site) (article)</span></span>

<span data-ttu-id="605d2-127">[Visão geral do Centro de administração do Microsoft 365](../../business-video/admin-center-overview.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="605d2-127">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>

<span data-ttu-id="605d2-128">[Gerenciar emails e calendários](../email/index.yml) (página de link)</span><span class="sxs-lookup"><span data-stu-id="605d2-128">[Manage email and calendars](../email/index.yml) (link page)</span></span>