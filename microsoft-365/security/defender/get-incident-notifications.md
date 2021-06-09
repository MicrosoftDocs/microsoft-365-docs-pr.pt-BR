---
title: Obter notificações de incidentes por email no Microsoft 365 Defender
description: Saiba como criar regras para receber notificações por email para incidentes no Microsoft 365 Defender
keywords: incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 2e47b35646a1cd6e1075d80f9ed0550e8e1e819f
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651387"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="b8254-104">Obter notificações de incidentes por email</span><span class="sxs-lookup"><span data-stu-id="b8254-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b8254-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b8254-105">**Applies to:**</span></span>
- <span data-ttu-id="b8254-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b8254-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b8254-107">Você pode configurar o Microsoft 365 Defender para notificar sua equipe com um email sobre novos incidentes ou atualizações para incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="b8254-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="b8254-108">Você pode optar por receber notificações com base em:</span><span class="sxs-lookup"><span data-stu-id="b8254-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="b8254-109">Gravidade do incidente.</span><span class="sxs-lookup"><span data-stu-id="b8254-109">Incident severity.</span></span>
- <span data-ttu-id="b8254-110">Grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b8254-110">Device group.</span></span>
- <span data-ttu-id="b8254-111">Somente na primeira atualização por incidente.</span><span class="sxs-lookup"><span data-stu-id="b8254-111">Only on the first update per incident.</span></span>

<span data-ttu-id="b8254-112">A notificação de email contém detalhes importantes sobre o incidente, como o nome do incidente, gravidade e categorias, entre outros.</span><span class="sxs-lookup"><span data-stu-id="b8254-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="b8254-113">Você também pode ir diretamente para o incidente e iniciar sua análise imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b8254-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="b8254-114">Para obter mais informações, consulte [Investigar incidentes](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="b8254-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="b8254-115">Você pode adicionar ou remover destinatários nas notificações de email.</span><span class="sxs-lookup"><span data-stu-id="b8254-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="b8254-116">Novos destinatários são notificados sobre incidentes depois que são adicionados.</span><span class="sxs-lookup"><span data-stu-id="b8254-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="b8254-117">Você precisa da permissão "Gerenciar configurações de segurança" para configurar as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="b8254-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="b8254-118">Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações de email para você.</span><span class="sxs-lookup"><span data-stu-id="b8254-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="b8254-119">Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b8254-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="b8254-120">Criar uma regra para notificações por email</span><span class="sxs-lookup"><span data-stu-id="b8254-120">Create a rule for email notifications</span></span>

<span data-ttu-id="b8254-121">Siga estas etapas para criar uma nova regra e personalizar as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="b8254-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="b8254-122">No painel de navegação, selecione Configurações > Microsoft 365 **notificações de email > Incidentes.**</span><span class="sxs-lookup"><span data-stu-id="b8254-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="b8254-123">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="b8254-123">Select **Add item**.</span></span>
3. <span data-ttu-id="b8254-124">Na página **Noções Básicas,** digite o nome da regra e uma descrição e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b8254-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="b8254-125">Na página **Configurações de notificação,** configure:</span><span class="sxs-lookup"><span data-stu-id="b8254-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="b8254-126">**Gravidade do alerta** - Escolha as gravidades de alerta que dispararão uma notificação de incidente.</span><span class="sxs-lookup"><span data-stu-id="b8254-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="b8254-127">Por exemplo, se você quiser apenas ser informado sobre incidentes de alta gravidade, selecione **Alta**.</span><span class="sxs-lookup"><span data-stu-id="b8254-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="b8254-128">**Escopo do grupo de** dispositivos - Você pode especificar todos os grupos de dispositivos ou selecionar na lista de grupos de dispositivos em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b8254-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="b8254-129">**Notificar somente a primeira ocorrência por incidente** - Selecione se quiser uma notificação somente no primeiro alerta que corresponde às outras seleções.</span><span class="sxs-lookup"><span data-stu-id="b8254-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="b8254-130">Atualizações ou alertas posteriores relacionados ao incidente não enviarão notificações adicionais.</span><span class="sxs-lookup"><span data-stu-id="b8254-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="b8254-131">**Inclua o nome da organização no email** - Selecione se você deseja que o nome da sua organização apareça na notificação de email.</span><span class="sxs-lookup"><span data-stu-id="b8254-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="b8254-132">**Inclua o link de portal** específico do locatário - Selecione se deseja adicionar um link com a ID do locatário na notificação de email para acesso a um locatário Microsoft 365 locatário específico.</span><span class="sxs-lookup"><span data-stu-id="b8254-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Configurações de notificação para notificações de email de incidentes":::

5. <span data-ttu-id="b8254-134">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8254-134">Select **Next**.</span></span> <span data-ttu-id="b8254-135">Na página **Destinatários,** adicione os endereços de email que receberão as notificações de incidentes.</span><span class="sxs-lookup"><span data-stu-id="b8254-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="b8254-136">Selecione **Adicionar** após digitar cada novo endereço de email.</span><span class="sxs-lookup"><span data-stu-id="b8254-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="b8254-137">Para testar notificações e garantir que os destinatários as recebam nas caixas de entrada, selecione **Enviar email de teste.**</span><span class="sxs-lookup"><span data-stu-id="b8254-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="b8254-138">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b8254-138">Select **Next**.</span></span> <span data-ttu-id="b8254-139">Na página **Revisar regra,** revise as configurações da regra e selecione **Criar regra**.</span><span class="sxs-lookup"><span data-stu-id="b8254-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="b8254-140">Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.</span><span class="sxs-lookup"><span data-stu-id="b8254-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="b8254-141">Para editar uma regra existente, selecione-a na lista de regras.</span><span class="sxs-lookup"><span data-stu-id="b8254-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="b8254-142">No painel com o nome da regra, selecione **Editar** regra e faça suas alterações nas páginas **Noções Básicas,** Configurações de Notificação e **Destinatários.** </span><span class="sxs-lookup"><span data-stu-id="b8254-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="b8254-143">Para excluir uma regra, selecione-a na lista de regras.</span><span class="sxs-lookup"><span data-stu-id="b8254-143">To delete a rule, select it from the list of rules.</span></span> <span data-ttu-id="b8254-144">No painel com o nome da regra, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b8254-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8254-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8254-145">See also</span></span>
- [<span data-ttu-id="b8254-146">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="b8254-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b8254-147">Priorizar incidentes</span><span class="sxs-lookup"><span data-stu-id="b8254-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="b8254-148">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="b8254-148">Investigate incidents</span></span>](investigate-incidents.md)
