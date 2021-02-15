---
title: Obter notificações de incidentes no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email sobre incidentes no Microsoft 365 Defender
keywords: incidente, email, notações de email, configurar, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9db025818fdd5eb2635a9a676e4a10e20f3036b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930973"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="2b233-104">Obter notificações de incidentes por email</span><span class="sxs-lookup"><span data-stu-id="2b233-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2b233-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2b233-105">**Applies to:**</span></span>
- <span data-ttu-id="2b233-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b233-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2b233-107">Você pode configurar o Microsoft 365 Defender para notificá-lo por email sempre que houver novos incidentes ou novas atualizações para incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="2b233-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="2b233-108">Você pode optar por receber notificações com base na gravidade do incidente ou por grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2b233-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="2b233-109">Você também pode optar por receber uma notificação somente na primeira atualização por incidente.</span><span class="sxs-lookup"><span data-stu-id="2b233-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="2b233-110">Você pode adicionar ou remover destinatários nas notificações por email.</span><span class="sxs-lookup"><span data-stu-id="2b233-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="2b233-111">Os destinatários recém-adicionados são notificados sobre incidentes depois que são adicionados.</span><span class="sxs-lookup"><span data-stu-id="2b233-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="2b233-112">A notificação por email contém detalhes importantes sobre o incidente, como o nome do incidente, a gravidade e as categorias, entre outros.</span><span class="sxs-lookup"><span data-stu-id="2b233-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="2b233-113">Você também pode ir diretamente a incidentes para iniciar a investigação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2b233-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="2b233-114">Para obter mais informações sobre como investigar incidentes, consulte [Investigar incidentes no Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="2b233-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="2b233-115">Você precisa de permissões de "Gerenciar configurações de segurança" para definir as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="2b233-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="2b233-116">Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações por email para você.</span><span class="sxs-lookup"><span data-stu-id="2b233-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="2b233-117">Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="2b233-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="2b233-118">Criar regras para notificações de incidentes</span><span class="sxs-lookup"><span data-stu-id="2b233-118">Create rules for incident notifications</span></span>

<span data-ttu-id="2b233-119">Para configurar sua primeira notificação por email para incidentes, crie uma nova regra e personalize as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="2b233-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="2b233-120">No painel de navegação, selecione **Notificações por**  >  **email do Incidente de Configurações.**</span><span class="sxs-lookup"><span data-stu-id="2b233-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="2b233-121">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="2b233-121">Select **Add item**.</span></span>
3. <span data-ttu-id="2b233-122">Dê um nome à regra em **Nome e** fornecer uma **Descrição.**</span><span class="sxs-lookup"><span data-stu-id="2b233-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Criar janela de regra para notifica o email de incidente](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="2b233-124">Selecione **Próximo** para ir para **configurações de Notificação.**</span><span class="sxs-lookup"><span data-stu-id="2b233-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="2b233-125">Aqui você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="2b233-125">Here you can specify:</span></span>
    - <span data-ttu-id="2b233-126">**Gravidade do alerta** - Escolha a gravidade do alerta que disparará uma notificação de incidente.</span><span class="sxs-lookup"><span data-stu-id="2b233-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="2b233-127">Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione Alta.</span><span class="sxs-lookup"><span data-stu-id="2b233-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="2b233-128">**Escopo do grupo de** dispositivos - Essa lista suspenso exibe todos os grupos de dispositivos que o usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="2b233-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="2b233-129">Selecione para quais grupos de dispositivos você está criando as regras de notificação de incidentes.</span><span class="sxs-lookup"><span data-stu-id="2b233-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="2b233-130">**Notificar somente na primeira ocorrência por incidente-** Selecionar essa opção enviará uma notificação por email somente no primeiro alerta que corresponde às outras seleções.</span><span class="sxs-lookup"><span data-stu-id="2b233-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="2b233-131">Atualizações ou alertas posteriores relacionados ao incidente não dispararão uma notificação.</span><span class="sxs-lookup"><span data-stu-id="2b233-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="2b233-132">**Incluir nome da** organização - Indica se o nome do cliente aparece na notificação por email ou não.</span><span class="sxs-lookup"><span data-stu-id="2b233-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="2b233-133">**Inclua um link de portal específico do locatário** : adiciona um link com a ID de locatário para permitir o acesso a um locatário específico.</span><span class="sxs-lookup"><span data-stu-id="2b233-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="2b233-135">Selecione **Próximo** para ir na **seção Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="2b233-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="2b233-136">Aqui você pode especificar endereços de email que receberão as notificações por email de incidente.</span><span class="sxs-lookup"><span data-stu-id="2b233-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="2b233-137">Selecione **Adicionar um destinatário depois** de digitar cada endereço de email.</span><span class="sxs-lookup"><span data-stu-id="2b233-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Janela Adicionar destinatários para notifica o email de incidente](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="2b233-139">Por fim, **selecione Próximo** para ir **para a** regra revisão para que você possa ver todas as configurações associadas à sua nova regra.</span><span class="sxs-lookup"><span data-stu-id="2b233-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="2b233-140">Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.</span><span class="sxs-lookup"><span data-stu-id="2b233-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b233-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b233-141">See also</span></span>
- [<span data-ttu-id="2b233-142">Visão geral de incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b233-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="2b233-143">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b233-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="2b233-144">Investigar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b233-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

