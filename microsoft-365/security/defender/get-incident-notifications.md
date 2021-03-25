---
title: Obter notificações de incidentes no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email para incidentes no Microsoft 365 Defender
keywords: incidente, email, notficações de email, configurar, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
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
ms.openlocfilehash: 42600b360061626938aa13a09f1ed1b42fdfe48c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052840"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="3ca52-104">Obter notificações de incidentes por email</span><span class="sxs-lookup"><span data-stu-id="3ca52-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3ca52-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3ca52-105">**Applies to:**</span></span>
- <span data-ttu-id="3ca52-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca52-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3ca52-107">Você pode configurar o Microsoft 365 Defender para notificá-lo por email sempre que houver novos incidentes ou novas atualizações para incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="3ca52-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="3ca52-108">Você pode optar por receber notificações com base na gravidade do incidente ou no grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3ca52-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="3ca52-109">Você também pode optar por receber uma notificação somente na primeira atualização por incidente.</span><span class="sxs-lookup"><span data-stu-id="3ca52-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="3ca52-110">Você pode adicionar ou remover destinatários nas notificações de email.</span><span class="sxs-lookup"><span data-stu-id="3ca52-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="3ca52-111">Os destinatários recém-adicionados são notificados sobre incidentes depois que são adicionados.</span><span class="sxs-lookup"><span data-stu-id="3ca52-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="3ca52-112">A notificação de email contém detalhes importantes sobre o incidente, como o nome do incidente, gravidade e categorias, entre outros.</span><span class="sxs-lookup"><span data-stu-id="3ca52-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="3ca52-113">Você também pode ir diretamente a incidentes para que possa iniciar sua investigação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="3ca52-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="3ca52-114">Para obter mais informações sobre a investigação de incidentes, consulte [Investigar incidentes no Microsoft 365 Defender](./investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="3ca52-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](./investigate-incidents.md).</span></span>

>[!NOTE]
><span data-ttu-id="3ca52-115">Você precisa de permissões "Gerenciar configurações de segurança" para configurar as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="3ca52-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="3ca52-116">Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações de email para você.</span><span class="sxs-lookup"><span data-stu-id="3ca52-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="3ca52-117">Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="3ca52-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="3ca52-118">Criar regras para notificações de incidentes</span><span class="sxs-lookup"><span data-stu-id="3ca52-118">Create rules for incident notifications</span></span>

<span data-ttu-id="3ca52-119">Para configurar sua primeira notificação de email para incidentes, crie uma nova regra e personalize as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="3ca52-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="3ca52-120">No painel de navegação, selecione **Configurações**  >  **Notificações de email de incidentes.**</span><span class="sxs-lookup"><span data-stu-id="3ca52-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="3ca52-121">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="3ca52-121">Select **Add item**.</span></span>
3. <span data-ttu-id="3ca52-122">Dê à regra um nome em **Name e** fornece uma **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="3ca52-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Criar janela de regra para notificações de email de incidentes](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="3ca52-124">Selecione **Próximo** para ir para **Configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="3ca52-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="3ca52-125">Aqui você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="3ca52-125">Here you can specify:</span></span>
    - <span data-ttu-id="3ca52-126">**Gravidade do alerta** - Escolha a gravidade do alerta que disparará uma notificação de incidente.</span><span class="sxs-lookup"><span data-stu-id="3ca52-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="3ca52-127">Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione Alta.</span><span class="sxs-lookup"><span data-stu-id="3ca52-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="3ca52-128">**Escopo do grupo de** dispositivos - Essa lista lista exibe todos os grupos de dispositivos que o usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="3ca52-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="3ca52-129">Selecione para quais grupos de dispositivos você está criando as regras de notificação de incidentes.</span><span class="sxs-lookup"><span data-stu-id="3ca52-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="3ca52-130">**Notificar somente a primeira ocorrência por incidente** - Selecionar essa opção enviará uma notificação de email somente no primeiro alerta que corresponde às outras seleções.</span><span class="sxs-lookup"><span data-stu-id="3ca52-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="3ca52-131">Atualizações posteriores ou alertas relacionados ao incidente não dispararão uma notificação.</span><span class="sxs-lookup"><span data-stu-id="3ca52-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="3ca52-132">**Incluir nome da** organização - Indica se o nome do cliente aparece na notificação de email ou não.</span><span class="sxs-lookup"><span data-stu-id="3ca52-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="3ca52-133">**Incluir link de portal específico do locatário** - Adiciona um link com a ID do locatário para permitir o acesso a um locatário específico.</span><span class="sxs-lookup"><span data-stu-id="3ca52-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Notif settings window for incident email notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="3ca52-135">Selecione **Próximo** para ir na **seção Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="3ca52-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="3ca52-136">Aqui você pode especificar endereços de email que receberão as notificações de email de incidente.</span><span class="sxs-lookup"><span data-stu-id="3ca52-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="3ca52-137">Selecione **Adicionar um destinatário após** digitar cada endereço de email.</span><span class="sxs-lookup"><span data-stu-id="3ca52-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Adicionar janela de destinatários para notificações de email de incidentes](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="3ca52-139">Por fim, **selecione Próximo** a ir para **Revisar regra** para que você possa ver todas as configurações associadas à nova regra.</span><span class="sxs-lookup"><span data-stu-id="3ca52-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="3ca52-140">Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.</span><span class="sxs-lookup"><span data-stu-id="3ca52-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ca52-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="3ca52-141">See also</span></span>
- [<span data-ttu-id="3ca52-142">Visão geral de incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca52-142">Incidents overview in Microsoft 365 Defender</span></span>](./incidents-overview.md)
- [<span data-ttu-id="3ca52-143">Priorizar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca52-143">Prioritize incidents in Microsoft 365 Defender</span></span>](./incident-queue.md)
- [<span data-ttu-id="3ca52-144">Investigar incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca52-144">Investigate incidents in Microsoft 365 Defender</span></span>](./investigate-incidents.md)