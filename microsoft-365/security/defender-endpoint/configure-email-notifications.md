---
title: Configurar notificações de alerta no Microsoft Defender para Ponto de Extremidade
description: Você pode usar o Microsoft Defender para o Ponto de Extremidade para configurar as configurações de notificação de email para alertas de segurança, com base na gravidade e em outros critérios.
keywords: notificações por email, configurar notificações de alerta, notificações do microsoft defender atp, alertas do microsoft defender atp, windows 10 enterprise, windows 10 education
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d8b68e6b6dc42de5730aa634386406d4762b1fa2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163678"
---
# <a name="configure-alert-notifications-in-microsoft-defender-atp"></a><span data-ttu-id="6c870-104">Configurar notificações de alerta no Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="6c870-104">Configure alert notifications in Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6c870-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6c870-105">**Applies to:**</span></span>
- [<span data-ttu-id="6c870-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6c870-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6c870-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c870-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6c870-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6c870-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6c870-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6c870-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="6c870-110">Você pode configurar o Defender para o Ponto de Extremidade para enviar notificações de email para destinatários especificados para novos alertas.</span><span class="sxs-lookup"><span data-stu-id="6c870-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="6c870-111">Esse recurso permite identificar um grupo de indivíduos que serão imediatamente informados e poderão agir em alertas com base em sua gravidade.</span><span class="sxs-lookup"><span data-stu-id="6c870-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="6c870-112">Somente usuários com permissões "Gerenciar configurações de segurança" podem configurar notificações por email.</span><span class="sxs-lookup"><span data-stu-id="6c870-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="6c870-113">Se você optou por usar o gerenciamento de permissões básicas, os usuários com funções de Administrador de Segurança ou Administrador Global podem configurar notificações por email.</span><span class="sxs-lookup"><span data-stu-id="6c870-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="6c870-114">Você pode definir os níveis de gravidade do alerta que disparam notificações.</span><span class="sxs-lookup"><span data-stu-id="6c870-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="6c870-115">Você também pode adicionar ou remover destinatários da notificação de email.</span><span class="sxs-lookup"><span data-stu-id="6c870-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="6c870-116">Novos destinatários são notificados sobre alertas encontrados depois que são adicionados.</span><span class="sxs-lookup"><span data-stu-id="6c870-116">New recipients get notified about alerts encountered after they are added.</span></span> <span data-ttu-id="6c870-117">Para obter mais informações sobre alertas, consulte [Exibir e organizar a fila de alertas.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="6c870-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="6c870-118">Se você estiver usando o controle de acesso baseado em função (RBAC), os destinatários receberão notificações apenas com base nos grupos de dispositivos que foram configurados na regra de notificação.</span><span class="sxs-lookup"><span data-stu-id="6c870-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="6c870-119">Os usuários com a permissão adequada só podem criar, editar ou excluir notificações limitadas ao escopo de gerenciamento do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c870-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="6c870-120">Somente os usuários atribuídos à função de administrador global podem gerenciar regras de notificação configuradas para todos os grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6c870-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="6c870-121">A notificação por email inclui informações básicas sobre o alerta e um link para o portal onde você pode fazer uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="6c870-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>


## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="6c870-122">Criar regras para notificações de alerta</span><span class="sxs-lookup"><span data-stu-id="6c870-122">Create rules for alert notifications</span></span>
<span data-ttu-id="6c870-123">Você pode criar regras que determinam os dispositivos e as gravidades de alerta para enviar notificações por email e para os destinatários de notificação.</span><span class="sxs-lookup"><span data-stu-id="6c870-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="6c870-124">No painel de navegação, selecione **Configurações**  >  **Notificações de alerta.**</span><span class="sxs-lookup"><span data-stu-id="6c870-124">In the navigation pane, select **Settings** > **Alert notifications**.</span></span>

2. <span data-ttu-id="6c870-125">Clique **em Adicionar regra de notificação**.</span><span class="sxs-lookup"><span data-stu-id="6c870-125">Click **Add notification rule**.</span></span>

3. <span data-ttu-id="6c870-126">Especifique as informações gerais:</span><span class="sxs-lookup"><span data-stu-id="6c870-126">Specify the General information:</span></span>
    - <span data-ttu-id="6c870-127">**Nome da** regra - Especifique um nome para a regra de notificação.</span><span class="sxs-lookup"><span data-stu-id="6c870-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="6c870-128">**Incluir nome da** organização - Especifique o nome do cliente que aparece na notificação de email.</span><span class="sxs-lookup"><span data-stu-id="6c870-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="6c870-129">**Incluir link de portal específico do locatário** - Adiciona um link com a ID do locatário para permitir o acesso a um locatário específico.</span><span class="sxs-lookup"><span data-stu-id="6c870-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="6c870-130">**Incluir informações do dispositivo** - Inclui o nome do dispositivo no corpo do alerta de email.</span><span class="sxs-lookup"><span data-stu-id="6c870-130">**Include device information** - Includes the device name in the email alert body.</span></span>
    
        >[!NOTE]
        > <span data-ttu-id="6c870-131">Essas informações podem ser processadas por servidores de email de destinatário que não estão na localização geográfica selecionada para os dados do Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6c870-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="6c870-132">**Dispositivos** - Escolha se deve notificar os destinatários para alertas em todos os dispositivos (função de administrador global somente) ou em grupos de dispositivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="6c870-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="6c870-133">Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6c870-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="6c870-134">**Gravidade do alerta** - Escolha o nível de gravidade do alerta.</span><span class="sxs-lookup"><span data-stu-id="6c870-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="6c870-135">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6c870-135">Click **Next**.</span></span>
    
5. <span data-ttu-id="6c870-136">Insira o endereço de email do destinatário e clique em **Adicionar destinatário**.</span><span class="sxs-lookup"><span data-stu-id="6c870-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="6c870-137">Você pode adicionar vários endereços de email.</span><span class="sxs-lookup"><span data-stu-id="6c870-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="6c870-138">Verifique se os destinatários de email podem receber as notificações de email selecionando **Enviar email de teste.**</span><span class="sxs-lookup"><span data-stu-id="6c870-138">Check that email recipients are able to receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="6c870-139">Clique **em Salvar regra de notificação**.</span><span class="sxs-lookup"><span data-stu-id="6c870-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="6c870-140">Editar uma regra de notificação</span><span class="sxs-lookup"><span data-stu-id="6c870-140">Edit a notification rule</span></span>
1. <span data-ttu-id="6c870-141">Selecione a regra de notificação que você gostaria de editar.</span><span class="sxs-lookup"><span data-stu-id="6c870-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="6c870-142">Atualize as informações da guia Geral e destinatário.</span><span class="sxs-lookup"><span data-stu-id="6c870-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="6c870-143">Clique **em Salvar regra de notificação**.</span><span class="sxs-lookup"><span data-stu-id="6c870-143">Click **Save notification rule**.</span></span>


## <a name="delete-notification-rule"></a><span data-ttu-id="6c870-144">Excluir regra de notificação</span><span class="sxs-lookup"><span data-stu-id="6c870-144">Delete notification rule</span></span>

1. <span data-ttu-id="6c870-145">Selecione a regra de notificação que você gostaria de excluir.</span><span class="sxs-lookup"><span data-stu-id="6c870-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="6c870-146">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6c870-146">Click **Delete**.</span></span>


## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="6c870-147">Solucionar problemas de notificações por email para alertas</span><span class="sxs-lookup"><span data-stu-id="6c870-147">Troubleshoot email notifications for alerts</span></span>
<span data-ttu-id="6c870-148">Esta seção lista vários problemas que você pode encontrar ao usar notificações de email para alertas.</span><span class="sxs-lookup"><span data-stu-id="6c870-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="6c870-149">**Problema:** Os destinatários pretendido relatam que não estão recebendo as notificações.</span><span class="sxs-lookup"><span data-stu-id="6c870-149">**Problem:** Intended recipients report they are not getting the notifications.</span></span>

<span data-ttu-id="6c870-150">**Solução:** Certifique-se de que as notificações não sejam bloqueadas por filtros de email:</span><span class="sxs-lookup"><span data-stu-id="6c870-150">**Solution:** Make sure that the notifications are not blocked by email filters:</span></span>

1. <span data-ttu-id="6c870-151">Verifique se as notificações de email do Defender para Ponto de Extremidade não são enviadas para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6c870-151">Check that the Defender for Endpoint email notifications are not sent to the Junk Email folder.</span></span> <span data-ttu-id="6c870-152">Marcá-los como Não lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6c870-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="6c870-153">Verifique se seu produto de segurança de email não está bloqueando as notificações de email do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6c870-153">Check that your email security product is not blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="6c870-154">Verifique as regras do aplicativo de email que podem estar capturando e movendo o Defender para notificações de email do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6c870-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c870-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6c870-155">Related topics</span></span>
- [<span data-ttu-id="6c870-156">Atualizar configurações de retenção de dados</span><span class="sxs-lookup"><span data-stu-id="6c870-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="6c870-157">Configurar recursos avançados</span><span class="sxs-lookup"><span data-stu-id="6c870-157">Configure advanced features</span></span>](advanced-features.md)
