---
title: Saiba mais sobre a retenção para o Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre as políticas de retenção que se aplicam ao Yammer.
ms.openlocfilehash: 1b99d0915cfb159f821818fb1425d7191a011351
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "52710701"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="0cfe5-103">Saiba mais sobre a retenção para o Yammer</span><span class="sxs-lookup"><span data-stu-id="0cfe5-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="0cfe5-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="0cfe5-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="0cfe5-105">Este recurso está na versão prévia e ainda não está disponível para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="0cfe5-106">As informações contidas neste artigo complementam [Saiba mais sobre retenção](retention.md) porque são informações específicas para o Yammer.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="0cfe5-107">Para outras cargas de trabalho, confira:</span><span class="sxs-lookup"><span data-stu-id="0cfe5-107">For other workloads, see:</span></span>

- [<span data-ttu-id="0cfe5-108">Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o Microsoft OneDrive</span><span class="sxs-lookup"><span data-stu-id="0cfe5-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="0cfe5-109">Saiba mais sobre retenção para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0cfe5-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="0cfe5-110">Saiba mais sobre a retenção para o Exchange</span><span class="sxs-lookup"><span data-stu-id="0cfe5-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="0cfe5-111">O que está incluído para retenção e exclusão</span><span class="sxs-lookup"><span data-stu-id="0cfe5-111">What's included for retention and deletion</span></span>

<span data-ttu-id="0cfe5-112">Os seguintes itens do Yammer podem ser retidos e excluídos usando as políticas de retenção do Yammer: Mensagens da Comunidade e mensagens privadas.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="0cfe5-113">As reações de outras pessoas na forma de emoticons não estão incluídas nessas mensagens.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="0cfe5-114">Como a retenção funciona com o Yammer</span><span class="sxs-lookup"><span data-stu-id="0cfe5-114">How retention works with Yammer</span></span>

<span data-ttu-id="0cfe5-115">Você pode usar uma política de retenção para reter e excluir mensagens da comunidade e mensagens privadas no Yammer.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="0cfe5-116">As mensagens privadas são armazenadas em uma pasta oculta na caixa de correio de cada usuário participante da mensagem, e as mensagens da comunidade são armazenadas em uma pasta oculta semelhante na caixa de correio da comunidade.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="0cfe5-117">As mensagens do Yammer não são afetadas pelas políticas de retenção configuradas para as caixas de correio de usuário ou de grupos.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="0cfe5-118">Embora as mensagens do Yammer sejam armazenadas no Exchange, esses dados do Yammer só serão incluídos em uma política de retenção configurada para os locais das **mensagens da comunidade do Yammer** e das **mensagens de usuário do Yammer**.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="0cfe5-119">Se um usuário estiver incluído em uma política de retenção ativa que retém dados do Yammer e você excluir uma caixa de correio de um usuário incluído nessa política, para reter os dados do Yammer, a caixa de correio será convertida em uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0cfe5-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="0cfe5-120">Se você não precisar reter esses dados do Yammer para o usuário, exclua a conta de usuário da política de retenção antes de excluir a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="0cfe5-121">Depois que uma política de retenção for configurada para mensagens do Yammer, um trabalho de temporizador do serviço do Exchange avaliará periodicamente os itens na pasta oculta em que essas mensagens do Yammer são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="0cfe5-122">O trabalho de temporizador leva até sete dias para ser executado.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="0cfe5-123">Quando o período de retenção desses itens expira, eles são movidos para a pasta SubstrateHolds, uma pasta oculta que toda caixa de correio de usuário ou grupo possui para armazenar itens “excluídos temporariamente” antes de serem excluídos permanentemente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="0cfe5-124">Depois que uma política de retenção for configurada para mensagens do Yammer, os caminhos que o conteúdo tomará vão depender se a política de retenção for para reter e excluir, somente reter ou somente excluir.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-124">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="0cfe5-125">Quando a política de retenção for reter e excluir:</span><span class="sxs-lookup"><span data-stu-id="0cfe5-125">When the retention policy is to retain and then delete:</span></span>

![Diagrama do fluxo de retenção de mensagens do Yammer](../media/yammerretentionlifecycle.png)

<span data-ttu-id="0cfe5-127">Para os dois caminhos no diagrama:</span><span class="sxs-lookup"><span data-stu-id="0cfe5-127">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="0cfe5-128">**Se uma mensagem do Yammer for editada ou excluída** pelo usuário durante o período de retenção, a mensagem original será copiada imediatamente (se foi editada) ou movida (se foi excluída) para a pasta SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-128">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="0cfe5-129">A mensagem é armazenada lá até que o período de retenção expirar e a mensagem será permanentemente excluída imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-129">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="0cfe5-130">**Se uma mensagem do Yammer não for excluída** e para as mensagens atuais após a edição, a mensagem será movida para a pasta SubstrateHolds após o período de retenção expirar.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-130">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="0cfe5-131">Essa ação leva sete dias após a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-131">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0cfe5-132">Quando a mensagem estiver na pasta SubstrateHolds, ela será permanentemente excluída imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-132">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cfe5-133">As mensagens na pasta SubstrateHolds são pesquisáveis por ferramentas de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-133">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="0cfe5-134">Até que as mensagens sejam excluídas permanentemente (na pasta SubstrateHolds), elas permanecerão pesquisáveis por ferramentas de Descoberta Eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-134">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="0cfe5-135">Quando a política de retenção é somente retenção ou somente exclusão, os caminhos de conteúdo serão variações de reter e excluir.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-135">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="0cfe5-136">Caminhos de conteúdo para a política de retenção reter somente</span><span class="sxs-lookup"><span data-stu-id="0cfe5-136">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="0cfe5-137">**Se uma mensagem do Yammer for editada ou excluída**: uma cópia da mensagem original é criada imediatamente na pasta SubstrateHolds e mantida lá até que o período de retenção expire.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-137">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="0cfe5-138">Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-138">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0cfe5-139">**Se a mensagem do Yammer não for modificada ou excluída** e para as mensagens atuais após a edição durante o período de retenção: nada acontece antes e depois do período de retenção; a mensagem permanecerá no local original.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-139">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="0cfe5-140">Caminhos de conteúdo para a política de retenção somente excluir</span><span class="sxs-lookup"><span data-stu-id="0cfe5-140">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="0cfe5-141">**Se a mensagem do Yammer não for excluída** durante o período de retenção: no final do período de retenção, a mensagem será movida para a pasta SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-141">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="0cfe5-142">Essa ação leva sete dias após a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-142">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0cfe5-143">Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-143">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0cfe5-144">**Se a mensagem do Yammer for excluída pelo usuário** durante o período, o item será movido imediatamente para a pasta SubstrateHolds, onde será permanentemente excluído imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-144">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="0cfe5-145">Mensagens e usuários externos</span><span class="sxs-lookup"><span data-stu-id="0cfe5-145">Messages and external users</span></span>

<span data-ttu-id="0cfe5-146">Por padrão, uma política de retenção para mensagens de usuário do Yammer se aplica a todos os usuários da organização, mas não a usuários externos.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-146">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="0cfe5-147">Você pode aplicar uma política de retenção a usuários externos se usar **Escolher usuário** e especificar sua conta.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-147">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="0cfe5-148">No momento, não há suporte para os usuários convidados do Azure B2B.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-148">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="0cfe5-149">Quando um usuário sair da organização</span><span class="sxs-lookup"><span data-stu-id="0cfe5-149">When a user leaves the organization</span></span> 

<span data-ttu-id="0cfe5-150">Se um usuário deixar a organização e a conta do Microsoft 365 for excluída, suas mensagens de usuário do Yammer sujeitas a retenção serão armazenadas em uma caixa de correio inativa.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-150">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="0cfe5-151">Essas mensagens permanecem sujeitas a qualquer política de retenção que foi colocada no usuário antes da sua caixa de correio ser desativada, e o conteúdo fica disponível para uma pesquisa de Descoberta Eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-151">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="0cfe5-152">Para obter mais informações, consulte [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0cfe5-152">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="0cfe5-153">Se o usuário tiver armazenado os arquivos no Yammer, consulte a [seção equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) do SharePoint e do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-153">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="0cfe5-154">Limitações</span><span class="sxs-lookup"><span data-stu-id="0cfe5-154">Limitations</span></span>

<span data-ttu-id="0cfe5-155">No momento, as políticas de retenção do Yammer estão no modo de visualização e estamos trabalhando continuamente para otimizar a funcionalidade de retenção.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-155">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="0cfe5-156">Enquanto isso, esteja ciente da seguinte limitação ao usar a retenção para mensagens da comunidade Yammer e mensagens privadas:</span><span class="sxs-lookup"><span data-stu-id="0cfe5-156">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="0cfe5-157">Ao selecionar **Escolher usuários** do local **mensagens de usuário do Yammer**, você poderá ver os convidados e usuários sem caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-157">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="0cfe5-158">As políticas de retenção não são projetadas para esses usuários, portanto, não os selecione.</span><span class="sxs-lookup"><span data-stu-id="0cfe5-158">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="0cfe5-159">Instruções de configuração</span><span class="sxs-lookup"><span data-stu-id="0cfe5-159">Configuration guidance</span></span>

<span data-ttu-id="0cfe5-160">Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="0cfe5-160">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="0cfe5-161">Se você estiver pronto para configurar uma política de retenção do Yammer, consulte [Criar e configurar políticas de retenção](create-retention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="0cfe5-161">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>