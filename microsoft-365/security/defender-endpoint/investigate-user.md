---
title: Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade
description: Investigue uma conta de usuário para possíveis credenciais comprometidas ou pivô na conta de usuário associada durante uma investigação.
keywords: investigar, conta, usuário, entidade de usuário, alerta, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935060"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="c493b-104">Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c493b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c493b-105">**Applies to:**</span></span>
- [<span data-ttu-id="c493b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c493b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c493b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="c493b-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c493b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c493b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c493b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="c493b-110">Investigar entidades de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="c493b-110">Investigate user account entities</span></span>

<span data-ttu-id="c493b-111">Identifique as contas de usuário com os alertas mais ativos (exibidos no painel como "Usuários em risco") e investigue casos de possíveis credenciais comprometidas ou pivô na conta de usuário associada ao investigar um alerta ou dispositivo para identificar possível movimento lateral entre dispositivos com essa conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c493b-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="c493b-112">Você pode encontrar informações de conta de usuário nos seguintes exibições:</span><span class="sxs-lookup"><span data-stu-id="c493b-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="c493b-113">Painel</span><span class="sxs-lookup"><span data-stu-id="c493b-113">Dashboard</span></span>
- <span data-ttu-id="c493b-114">Fila de alertas</span><span class="sxs-lookup"><span data-stu-id="c493b-114">Alert queue</span></span>
- <span data-ttu-id="c493b-115">Página de detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c493b-115">Device details page</span></span>

<span data-ttu-id="c493b-116">Um link de conta de usuário clicável está disponível nessas exibições, que o levará até a página de detalhes da conta de usuário, onde mais detalhes sobre a conta de usuário são mostrados.</span><span class="sxs-lookup"><span data-stu-id="c493b-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="c493b-117">Ao investigar uma entidade de conta de usuário, você verá:</span><span class="sxs-lookup"><span data-stu-id="c493b-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="c493b-118">Detalhes da conta de usuário, alertas do Microsoft Defender para Identidade e logon em dispositivos, função, tipo de logon e outros detalhes</span><span class="sxs-lookup"><span data-stu-id="c493b-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="c493b-119">Visão geral dos incidentes e dispositivos do usuário</span><span class="sxs-lookup"><span data-stu-id="c493b-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="c493b-120">Alertas relacionados a esse usuário</span><span class="sxs-lookup"><span data-stu-id="c493b-120">Alerts related to this user</span></span>
- <span data-ttu-id="c493b-121">Observado na organização (dispositivos conectados)</span><span class="sxs-lookup"><span data-stu-id="c493b-121">Observed in organization (devices logged on to)</span></span>

![Imagem da página de detalhes da entidade de conta de usuário](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="c493b-123">Detalhes do usuário</span><span class="sxs-lookup"><span data-stu-id="c493b-123">User details</span></span>

<span data-ttu-id="c493b-124">O  painel de detalhes do usuário à esquerda fornece informações sobre o usuário, como incidentes abertos relacionados, alertas ativos, nome SAM, SID, alertas do Microsoft Defender para Identidade, número de dispositivos aos quais o usuário está conectado, quando o usuário foi visto pela primeira e última vez, função e tipos de logon.</span><span class="sxs-lookup"><span data-stu-id="c493b-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="c493b-125">Dependendo dos recursos de integração habilitados, você verá outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="c493b-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="c493b-126">Por exemplo, se você habilitar a integração do Skype for Business, poderá entrar em contato com o usuário a partir do portal.</span><span class="sxs-lookup"><span data-stu-id="c493b-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="c493b-127">A **seção alertas do Azure ATP** contém um link que o levará para a página Do Microsoft Defender para Identidade, se você tiver habilitado o recurso Microsoft Defender para Identidade e houver alertas relacionados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="c493b-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="c493b-128">A página Do Microsoft Defender para Identidade fornecerá mais informações sobre os alertas.</span><span class="sxs-lookup"><span data-stu-id="c493b-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="c493b-129">Você precisará habilitar a integração no Microsoft Defender for Identity e no Defender for Endpoint para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="c493b-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="c493b-130">No Defender para Ponto de Extremidade, você pode habilitar esse recurso em recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="c493b-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="c493b-131">Para obter mais informações sobre como habilitar recursos avançados, consulte [Ativar recursos avançados](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="c493b-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="c493b-132">A Visão Geral, Alertas e Observados na organização são guias diferentes que exibem vários atributos sobre a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="c493b-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="c493b-133">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="c493b-133">Overview</span></span>

<span data-ttu-id="c493b-134">A **guia Visão** geral mostra os detalhes dos incidentes e uma lista dos dispositivos aos que o usuário fez logor.</span><span class="sxs-lookup"><span data-stu-id="c493b-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="c493b-135">Você pode expandi-los para ver detalhes dos eventos de logoff para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c493b-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="c493b-136">Alertas</span><span class="sxs-lookup"><span data-stu-id="c493b-136">Alerts</span></span>

<span data-ttu-id="c493b-137">A **guia Alertas** fornece uma lista de alertas associados à conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="c493b-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="c493b-138">Esta lista é uma exibição filtrada da fila alerta [e](alerts-queue.md)mostra alertas onde o contexto do usuário é a conta de usuário selecionada, a data em que a última atividade foi detectada, uma breve descrição do alerta, o dispositivo associado ao alerta, a gravidade do alerta, o status do alerta na fila e quem recebe o alerta.</span><span class="sxs-lookup"><span data-stu-id="c493b-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="c493b-139">Observado na organização</span><span class="sxs-lookup"><span data-stu-id="c493b-139">Observed in organization</span></span>

<span data-ttu-id="c493b-140">A guia **Observado** na organização permite que você especifique um intervalo de datas para ver uma lista de dispositivos em que esse usuário foi observado conectado, a conta de usuário mais frequente e menos frequente registrada em cada um desses dispositivos e o total de usuários observados em cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c493b-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="c493b-141">Selecionar um item na tabela Observado na organização expandirá o item, revelando mais detalhes sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c493b-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="c493b-142">Selecionar diretamente um link dentro de um item o enviará para a página correspondente.</span><span class="sxs-lookup"><span data-stu-id="c493b-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="c493b-143">Pesquisar contas de usuário específicas</span><span class="sxs-lookup"><span data-stu-id="c493b-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="c493b-144">Selecione **Usuário** no menu suspenso **barra** de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c493b-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="c493b-145">Insira a conta de usuário no **campo** Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c493b-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="c493b-146">Clique no ícone de pesquisa ou pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="c493b-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="c493b-147">Uma lista de usuários que coincidem com o texto da consulta é exibida.</span><span class="sxs-lookup"><span data-stu-id="c493b-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="c493b-148">Você verá o domínio e o nome da conta de usuário, quando a conta de usuário foi vista pela última vez, e o número total de dispositivos nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c493b-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="c493b-149">Você pode filtrar os resultados pelos seguintes períodos de tempo:</span><span class="sxs-lookup"><span data-stu-id="c493b-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="c493b-150">1 dia</span><span class="sxs-lookup"><span data-stu-id="c493b-150">1 day</span></span>
- <span data-ttu-id="c493b-151">3 dias</span><span class="sxs-lookup"><span data-stu-id="c493b-151">3 days</span></span>
- <span data-ttu-id="c493b-152">7 dias</span><span class="sxs-lookup"><span data-stu-id="c493b-152">7 days</span></span>
- <span data-ttu-id="c493b-153">30 dias</span><span class="sxs-lookup"><span data-stu-id="c493b-153">30 days</span></span>
- <span data-ttu-id="c493b-154">6 meses</span><span class="sxs-lookup"><span data-stu-id="c493b-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="c493b-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c493b-155">Related topics</span></span>

- [<span data-ttu-id="c493b-156">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c493b-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="c493b-157">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="c493b-158">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="c493b-159">Investigar um arquivo associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="c493b-160">Investigar dispositivos na lista Defender para Dispositivos de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="c493b-161">Investigar um endereço IP associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="c493b-162">Investigar um domínio associado a um alerta do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c493b-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
