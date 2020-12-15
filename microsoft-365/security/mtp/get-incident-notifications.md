---
title: Obter notificações de incidentes no Microsoft 365 defender
description: Saiba como criar regras para receber notificações por email para incidentes no Microsoft 365 defender
keywords: incidente, email, email notfications, configurar, usuários, caixa de correio, email, incidentes
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668107"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="08def-104">Obter notificações de incidentes por email</span><span class="sxs-lookup"><span data-stu-id="08def-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="08def-105">O recurso notificações por email para incidentes está atualmente em visualização pública.</span><span class="sxs-lookup"><span data-stu-id="08def-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="08def-106">Algumas informações sobre esse recurso podem ser alteradas antes da disponibilidade comercial.</span><span class="sxs-lookup"><span data-stu-id="08def-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="08def-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="08def-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="08def-108">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="08def-108">**Applies to:**</span></span>
- <span data-ttu-id="08def-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="08def-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="08def-110">Você pode configurar o Microsoft 365 defender para notificá-lo por email sempre que houver novos incidentes ou novas atualizações nos incidentes existentes.</span><span class="sxs-lookup"><span data-stu-id="08def-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="08def-111">Você pode optar por obter notificações com base na severidade de incidentes ou no grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08def-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="08def-112">Você também pode optar por obter uma notificação somente na primeira atualização por incidente.</span><span class="sxs-lookup"><span data-stu-id="08def-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="08def-113">Você pode adicionar ou remover destinatários nas notificações por email.</span><span class="sxs-lookup"><span data-stu-id="08def-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="08def-114">Destinatários adicionados recentemente são notificados sobre incidentes depois de adicionados.</span><span class="sxs-lookup"><span data-stu-id="08def-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="08def-115">A notificação por email contém detalhes importantes sobre o incidente como o nome do incidente, severidade e categorias, entre outros.</span><span class="sxs-lookup"><span data-stu-id="08def-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="08def-116">Você também pode ir diretamente para incidentes, para que possa começar sua investigação imediatamente.</span><span class="sxs-lookup"><span data-stu-id="08def-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="08def-117">Para saber mais sobre incidentes de investigação, consulte [investigar incidentes no Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="08def-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="08def-118">Você precisa de ' Gerenciar configurações de segurança ' para definir as configurações de notificação por email.</span><span class="sxs-lookup"><span data-stu-id="08def-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="08def-119">Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de administrador de segurança ou administrador global poderão configurar notificações por email para você.</span><span class="sxs-lookup"><span data-stu-id="08def-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="08def-120">Da mesma forma, se sua organização estiver usando o controle de acesso baseado em função (RBAC), você só poderá criar, editar, excluir e receber notificações com base nos grupos de dispositivos que você tem permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="08def-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="08def-121">Criar regras para notificações de incidentes</span><span class="sxs-lookup"><span data-stu-id="08def-121">Create rules for incident notifications</span></span>

<span data-ttu-id="08def-122">Para configurar sua primeira notificação de email para incidentes, crie uma nova regra e personalize as configurações de notificação de email.</span><span class="sxs-lookup"><span data-stu-id="08def-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="08def-123">No painel de navegação, selecione **configurações**  >  **notificações de email de incidente**.</span><span class="sxs-lookup"><span data-stu-id="08def-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="08def-124">Selecione **Adicionar item**.</span><span class="sxs-lookup"><span data-stu-id="08def-124">Select **Add item**.</span></span>
3. <span data-ttu-id="08def-125">Dê um nome à regra em **nome** e forneça uma **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="08def-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Janela criar regra para email de notifs](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="08def-127">Selecione **Avançar** para ir para **configurações de notificação**.</span><span class="sxs-lookup"><span data-stu-id="08def-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="08def-128">Aqui você pode especificar:</span><span class="sxs-lookup"><span data-stu-id="08def-128">Here you can specify:</span></span>
    - <span data-ttu-id="08def-129">**Severidade do alerta** -escolha a severidade do alerta que iniciará uma notificação de incidente.</span><span class="sxs-lookup"><span data-stu-id="08def-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="08def-130">Por exemplo, se você deseja ser informado apenas sobre incidentes de alta gravidade, selecione alto.</span><span class="sxs-lookup"><span data-stu-id="08def-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="08def-131">**Escopo do grupo de dispositivos** -essa lista suspensa exibe todos os grupos de dispositivos que o usuário pode acessar.</span><span class="sxs-lookup"><span data-stu-id="08def-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="08def-132">Selecione para quais grupos de dispositivos você está criando as regras de notificação de incidente.</span><span class="sxs-lookup"><span data-stu-id="08def-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="08def-133">**Somente notificar a primeira ocorrência por incidente** -a seleção dessa opção enviará uma notificação por email somente no primeiro alerta que corresponda às outras seleções.</span><span class="sxs-lookup"><span data-stu-id="08def-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="08def-134">Atualizações ou alertas posteriores relacionados ao incidente não acionarão uma notificação.</span><span class="sxs-lookup"><span data-stu-id="08def-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="08def-135">**Incluir nome da organização** : indica se o nome do cliente aparece na notificação por email ou não.</span><span class="sxs-lookup"><span data-stu-id="08def-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="08def-136">**Incluir link do portal específico do locatário** – adiciona um link com a ID do locatário para permitir o acesso a um locatário específico.</span><span class="sxs-lookup"><span data-stu-id="08def-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Janela de configurações do Notif para o notifs de email de incidente](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="08def-138">Selecione **Avançar** para ir para a seção **destinatários** .</span><span class="sxs-lookup"><span data-stu-id="08def-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="08def-139">Aqui você pode especificar endereços de email que receberão as notificações por email de incidentes.</span><span class="sxs-lookup"><span data-stu-id="08def-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="08def-140">Selecione **Adicionar um destinatário** depois de digitar todos os endereços de email.</span><span class="sxs-lookup"><span data-stu-id="08def-140">Select **Add a recipient** after typing every email address.</span></span>

    ![Janela Adicionar destinatários para email de notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="08def-142">Por fim, selecione **Avançar** para ir para a **regra de revisão** , para que você possa ver todas as configurações associadas à nova regra.</span><span class="sxs-lookup"><span data-stu-id="08def-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="08def-143">Os destinatários começarão a receber notificações de incidentes por email com base nas configurações.</span><span class="sxs-lookup"><span data-stu-id="08def-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="08def-144">Também consulte</span><span class="sxs-lookup"><span data-stu-id="08def-144">See also</span></span>
- [<span data-ttu-id="08def-145">Visão geral de incidentes no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="08def-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="08def-146">Priorizar incidentes no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="08def-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="08def-147">Investigue incidentes no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="08def-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

