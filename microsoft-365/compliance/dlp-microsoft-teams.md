---
title: Prevenção contra perda de dados e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams chats e canais suportam políticas de Prevenção contra Perda de Dados (DLP).
ms.openlocfilehash: e55bfa34b2495465f573bcede3ebda2308dbbbbc
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583383"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="49269-103">Prevenção contra perda de dados e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49269-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="49269-104">Se sua organização tiver DLP (prevenção contra perda de dados), você poderá definir políticas que impedem que as pessoas compartilhem informações confidenciais em um canal Microsoft Teams ou sessão de chat.</span><span class="sxs-lookup"><span data-stu-id="49269-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="49269-105">Aqui estão alguns exemplos de como essa proteção funciona:</span><span class="sxs-lookup"><span data-stu-id="49269-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="49269-106">**Exemplo 1: Protegendo informações confidenciais em mensagens**.</span><span class="sxs-lookup"><span data-stu-id="49269-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="49269-107">Suponha que alguém tenta compartilhar informações confidenciais em um Teams ou canal com convidados (usuários externos).</span><span class="sxs-lookup"><span data-stu-id="49269-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="49269-108">Se você tiver uma política de DLP definida para evitar isso, as mensagens com informações confidenciais enviadas a usuários externos serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="49269-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="49269-109">Isso acontece automaticamente e em segundos, de acordo com a configuração da política de DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49269-110">A DLP para Microsoft Teams o conteúdo confidenciais quando compartilhado com Microsoft Teams usuários que têm:</span><span class="sxs-lookup"><span data-stu-id="49269-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="49269-111">- [acesso de convidados](/MicrosoftTeams/guest-access) em equipes e canais; ou</span><span class="sxs-lookup"><span data-stu-id="49269-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="49269-112">- [acesso externo](/MicrosoftTeams/manage-external-access) em reuniões e sessões de chat.</span><span class="sxs-lookup"><span data-stu-id="49269-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="49269-113">A DLP para sessões de chat externo só funcionará se o remetente e o receptor estão no modo Somente Teams e usando Microsoft Teams [federação nativa](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="49269-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="49269-114">A DLP para Teams não bloqueia mensagens em [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com Skype for Business ou sessões de chat federadas não nativas.</span><span class="sxs-lookup"><span data-stu-id="49269-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="49269-115">**Exemplo 2: Protegendo informações confidenciais em documentos**.</span><span class="sxs-lookup"><span data-stu-id="49269-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="49269-116">Suponha que alguém tenta compartilhar um documento com convidados em um canal Microsoft Teams ou chat, e o documento contém informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="49269-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="49269-117">Se você tiver uma política de DLP definida para evitar isso, o documento não abrirá para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="49269-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="49269-118">Sua política DLP deve incluir o SharePoint e o OneDrive para que a proteção seja colocada em ação.</span><span class="sxs-lookup"><span data-stu-id="49269-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="49269-119">Este é um exemplo de DLP para SharePoint que aparece no Microsoft Teams e, portanto, exige que os usuários sejam licenciados para Office 365 DLP (incluído no Office 365 E3), mas não exige que os usuários sejam licenciados para Conformidade Avançada do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="49269-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="49269-120">Licenciamento de DLP para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49269-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="49269-121">[Os recursos de prevenção](dlp-learn-about-dlp.md) contra perda de dados foram estendidos para incluir Microsoft Teams mensagens de chat e canal, **incluindo mensagens de canal privado** para:</span><span class="sxs-lookup"><span data-stu-id="49269-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="49269-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="49269-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="49269-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="49269-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="49269-124">Governança e Proteção de Informações do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49269-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="49269-125">Conformidade Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="49269-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="49269-126">Office 365 e Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="49269-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="49269-127">Isso também inclui arquivos compartilhados por meio Teams porque Teams usa SharePoint Online e OneDrive para compartilhar arquivos.</span><span class="sxs-lookup"><span data-stu-id="49269-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="49269-128">O suporte para a proteção DLP no Teams Chat requer E5.</span><span class="sxs-lookup"><span data-stu-id="49269-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="49269-129">Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="49269-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49269-130">A DLP aplica-se apenas às mensagens reais no thread de chat ou canal.</span><span class="sxs-lookup"><span data-stu-id="49269-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="49269-131">As notificações de atividade - que incluem uma visualização de mensagem  curta e aparecem com base nas configurações de notificação de um usuário - não são incluídas no Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="49269-132">Quaisquer informações confidenciais presentes na parte da mensagem exibida na visualização permanecerão visíveis na notificação mesmo depois que a política DLP tiver sido aplicada e removida informações confidenciais da própria mensagem.</span><span class="sxs-lookup"><span data-stu-id="49269-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="49269-133">Escopo da proteção DLP</span><span class="sxs-lookup"><span data-stu-id="49269-133">Scope of DLP protection</span></span>

<span data-ttu-id="49269-134">A proteção DLP é aplicada de forma diferente Teams entidades.</span><span class="sxs-lookup"><span data-stu-id="49269-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="49269-135">Contas de usuário/grupos/lista</span><span class="sxs-lookup"><span data-stu-id="49269-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="49269-136">Teams Entity</span><span class="sxs-lookup"><span data-stu-id="49269-136">Teams Entity</span></span> |<span data-ttu-id="49269-137">Proteção DLP disponível</span><span class="sxs-lookup"><span data-stu-id="49269-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="49269-138">contas de usuário individuais</span><span class="sxs-lookup"><span data-stu-id="49269-138">individual user accounts</span></span>     |<span data-ttu-id="49269-139">Chats 1:1/n</span><span class="sxs-lookup"><span data-stu-id="49269-139">1:1/n chats</span></span>         |<span data-ttu-id="49269-140">sim</span><span class="sxs-lookup"><span data-stu-id="49269-140">yes</span></span>         |
|     |<span data-ttu-id="49269-141">chats gerais</span><span class="sxs-lookup"><span data-stu-id="49269-141">general chats</span></span>         |<span data-ttu-id="49269-142">não</span><span class="sxs-lookup"><span data-stu-id="49269-142">no</span></span>         |
|     |<span data-ttu-id="49269-143">canais compartilhados</span><span class="sxs-lookup"><span data-stu-id="49269-143">shared channels</span></span>         |<span data-ttu-id="49269-144">não</span><span class="sxs-lookup"><span data-stu-id="49269-144">no</span></span>         |
|     |<span data-ttu-id="49269-145">canais privados</span><span class="sxs-lookup"><span data-stu-id="49269-145">private channels</span></span>         |<span data-ttu-id="49269-146">sim</span><span class="sxs-lookup"><span data-stu-id="49269-146">yes</span></span>         |
|<span data-ttu-id="49269-147">grupos de segurança/listas de distribuição</span><span class="sxs-lookup"><span data-stu-id="49269-147">security groups/distribution lists</span></span>  | <span data-ttu-id="49269-148">Chats 1:1/n</span><span class="sxs-lookup"><span data-stu-id="49269-148">1:1/n chats</span></span>         |<span data-ttu-id="49269-149">sim</span><span class="sxs-lookup"><span data-stu-id="49269-149">yes</span></span>         |
|     |<span data-ttu-id="49269-150">chats gerais</span><span class="sxs-lookup"><span data-stu-id="49269-150">general chats</span></span>         |<span data-ttu-id="49269-151">não</span><span class="sxs-lookup"><span data-stu-id="49269-151">no</span></span>         |
|     |<span data-ttu-id="49269-152">canais compartilhados</span><span class="sxs-lookup"><span data-stu-id="49269-152">shared channels</span></span>         |<span data-ttu-id="49269-153">não</span><span class="sxs-lookup"><span data-stu-id="49269-153">no</span></span>      |
|     |<span data-ttu-id="49269-154">canais privados</span><span class="sxs-lookup"><span data-stu-id="49269-154">private channels</span></span>         |<span data-ttu-id="49269-155">sim</span><span class="sxs-lookup"><span data-stu-id="49269-155">yes</span></span>        |
|<span data-ttu-id="49269-156">Microsoft 365 grupo</span><span class="sxs-lookup"><span data-stu-id="49269-156">Microsoft 365 group</span></span>    |<span data-ttu-id="49269-157">Chats 1:1/n</span><span class="sxs-lookup"><span data-stu-id="49269-157">1:1/n chats</span></span>          |<span data-ttu-id="49269-158">não</span><span class="sxs-lookup"><span data-stu-id="49269-158">no</span></span>         |
|     |<span data-ttu-id="49269-159">chats gerais</span><span class="sxs-lookup"><span data-stu-id="49269-159">general chats</span></span>          |<span data-ttu-id="49269-160">sim</span><span class="sxs-lookup"><span data-stu-id="49269-160">yes</span></span>        |
|     |<span data-ttu-id="49269-161">canais compartilhados</span><span class="sxs-lookup"><span data-stu-id="49269-161">shared channels</span></span>|<span data-ttu-id="49269-162">sim</span><span class="sxs-lookup"><span data-stu-id="49269-162">yes</span></span> |
|     |<span data-ttu-id="49269-163">canais privados</span><span class="sxs-lookup"><span data-stu-id="49269-163">private channels</span></span>|<span data-ttu-id="49269-164">não</span><span class="sxs-lookup"><span data-stu-id="49269-164">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="49269-165">Dicas de política ajudam a instruir os usuários</span><span class="sxs-lookup"><span data-stu-id="49269-165">Policy tips help educate users</span></span>

<span data-ttu-id="49269-166">Semelhante à forma como a DLP funciona no [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)na Web , [SharePoint Online, sites OneDrive for Business e](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)clientes de área de trabalho do [Office](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), as dicas de política aparecem quando uma ação dispara com uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-166">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="49269-167">Veja um exemplo de uma dica de política:</span><span class="sxs-lookup"><span data-stu-id="49269-167">Here's an example of a policy tip:</span></span>

![Notificação de mensagem bloqueada Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="49269-169">Aqui, o remetente tentou compartilhar um número de segurança social em um Microsoft Teams canal.</span><span class="sxs-lookup"><span data-stu-id="49269-169">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="49269-170">O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="49269-170">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="49269-171">Observe que, o remetente pode optar por substituir a política ou notificar um administrador para revisá-la e resolvê-la.</span><span class="sxs-lookup"><span data-stu-id="49269-171">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opções para resolver mensagens bloqueadas](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="49269-173">Em sua organização, você pode optar por permitir que os usuários substituam uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-173">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="49269-174">Ao configurar suas políticas de DLP, você pode usar as dicas de política padrão ou [personalizar dicas de política](#to-customize-policy-tips) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="49269-174">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="49269-175">Retornando ao nosso exemplo, onde um remetente compartilhou um número de seguro social em um canal de Teams, veja o que o destinatário viu:</span><span class="sxs-lookup"><span data-stu-id="49269-175">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49269-176">![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="49269-176">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="49269-177">Dicas para personalizar a política</span><span class="sxs-lookup"><span data-stu-id="49269-177">To customize policy tips</span></span>

<span data-ttu-id="49269-178">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-178">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="49269-179">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="49269-179">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="49269-180">Vá para o Centro de Conformidade ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="49269-180">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="49269-181">Clique em **Prevenção contra perda de dados** > **Política**.</span><span class="sxs-lookup"><span data-stu-id="49269-181">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="49269-182">Selecione uma política e, ao lado de **Configurações de Política,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="49269-182">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="49269-183">Crie uma nova regra ou edite uma regra existente para a política.</span><span class="sxs-lookup"><span data-stu-id="49269-183">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-184">![Editar uma regra para uma política](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="49269-184">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="49269-185">Na guia **Notificações do usuário,** selecione **Personalizar o texto de email** e/ou Personalizar as opções de texto da dica **de** política.</span><span class="sxs-lookup"><span data-stu-id="49269-185">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-186">![Personalizar notificações do usuário e dicas de política](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="49269-186">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="49269-187">Especifique o texto que você deseja usar para notificações por email e/ou dicas de política e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49269-187">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="49269-188">Na guia **Configurações de Política,** escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49269-188">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="49269-189">Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="49269-189">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="49269-190">Adicionar o Microsoft Teams como um local para as políticas de DLP existentes</span><span class="sxs-lookup"><span data-stu-id="49269-190">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="49269-191">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-191">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="49269-192">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="49269-192">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="49269-193">Vá para o Centro de Conformidade ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="49269-193">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="49269-194">Clique em **Prevenção contra perda de dados** > **Política**.</span><span class="sxs-lookup"><span data-stu-id="49269-194">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="49269-195">Selecione uma política e veja os valores em **Locais.**</span><span class="sxs-lookup"><span data-stu-id="49269-195">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="49269-196">Se você vir **Teams mensagens de chat e canal**, você está definido.</span><span class="sxs-lookup"><span data-stu-id="49269-196">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="49269-197">Se não, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="49269-197">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-198">![Locais para política existente](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="49269-198">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="49269-199">Na coluna **Status,** a política é Teams mensagens de canal e **chat.**</span><span class="sxs-lookup"><span data-stu-id="49269-199">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-200">![DLP para Teams chats e canais](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="49269-200">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="49269-201">Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="49269-201">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="49269-202">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="49269-202">You can specify:</span></span>

    1. <span data-ttu-id="49269-203">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="49269-203">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="49269-204">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="49269-204">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="49269-205">Depois clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="49269-205">Then choose **Next**.</span></span>

7. <span data-ttu-id="49269-206">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="49269-206">Click **Save**.</span></span>

<span data-ttu-id="49269-207">Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="49269-207">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="49269-208">Definir uma nova política DLP para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="49269-208">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="49269-209">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="49269-209">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="49269-210">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="49269-210">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="49269-211">Vá para o Centro de Conformidade ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="49269-211">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="49269-212">Escolha **Prevenção contra perda de dados** > **Política** > **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="49269-212">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="49269-213">Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="49269-213">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="49269-214">No nosso exemplo, escolhemos o modelo de Dados de Informações de Identificação Pessoal dos EUA.</span><span class="sxs-lookup"><span data-stu-id="49269-214">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-215">![Modelo de privacidade para política de DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="49269-215">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="49269-216">Na guia **Nomear sua política,** especifique um nome e uma descrição para a política e escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="49269-216">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="49269-217">Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="49269-217">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="49269-218">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="49269-218">You can specify:</span></span>

    1. <span data-ttu-id="49269-219">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="49269-219">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="49269-220">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="49269-220">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="49269-221">**Esse é um recurso de visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="49269-221">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Locais de política DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="49269-223">Se você quiser garantir que os documentos que contêm informações confidenciais não sejam compartilhados de forma inadequada no Teams, certifique-se de que os **sites** SharePoint e contas OneDrive **estão** ativas, juntamente com mensagens de chat e canal do Teams **.**</span><span class="sxs-lookup"><span data-stu-id="49269-223">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="49269-224">Na guia **Configurações de** Política, em Personalizar o tipo de conteúdo que você deseja **proteger,** mantenha as configurações simples padrão ou escolha Usar configurações **avançadas** e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="49269-224">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="49269-225">Se você escolher configurações avançadas, poderá criar ou editar regras para sua política.</span><span class="sxs-lookup"><span data-stu-id="49269-225">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="49269-226">Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span><span class="sxs-lookup"><span data-stu-id="49269-226">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="49269-227">Na guia **Configurações de** Política, em O que você deseja fazer se detectarmos informações **confidenciais?**, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="49269-227">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="49269-228">Aqui é onde você pode optar por manter dicas de política padrão e notificações [de email](use-notifications-and-policy-tips.md)ou personalizá-las.</span><span class="sxs-lookup"><span data-stu-id="49269-228">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-229">![Configurações de política de DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="49269-229">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="49269-230">Quando terminar de revisar ou editar configurações, escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="49269-230">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="49269-231">Na  guia Configurações de Política, em Deseja ativar a política ou testar as coisas **primeiro?**, escolha se deseja ativar a [política,](dlp-overview-plan-for-dlp.md#policy-deployment)testá-la primeiro ou mantê-la desligada por enquanto e, em seguida, escolher **Next**.</span><span class="sxs-lookup"><span data-stu-id="49269-231">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49269-232">![Especificar se a política deve ser a a ativar](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="49269-232">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="49269-233">Na guia **Revisar suas configurações,** revise as configurações da nova política.</span><span class="sxs-lookup"><span data-stu-id="49269-233">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="49269-234">Escolha **Editar** para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="49269-234">Choose **Edit** to make changes.</span></span> <span data-ttu-id="49269-235">Quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="49269-235">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="49269-236">Permita aproximadamente uma hora para que sua nova política funcione por meio do data center e sincronize com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="49269-236">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="49269-237">Impedir o acesso externo a documentos confidenciais</span><span class="sxs-lookup"><span data-stu-id="49269-237">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="49269-238">Para garantir que SharePoint documentos que contenham informações confidenciais não podem ser acessados por convidados externos de SharePoint ou Teams por padrão, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="49269-238">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="49269-239">Você pode garantir que os documentos sejam protegidos até que a DLP os verifique e os marque como seguros para compartilhar marcando novos arquivos como confidenciais [por padrão.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="49269-239">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="49269-240">Estrutura de política DLP recomendada</span><span class="sxs-lookup"><span data-stu-id="49269-240">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="49269-241">**Condições**</span><span class="sxs-lookup"><span data-stu-id="49269-241">**Conditions**</span></span>
        - <span data-ttu-id="49269-242">O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]</span><span class="sxs-lookup"><span data-stu-id="49269-242">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="49269-243">O conteúdo é compartilhado de Microsoft 365 com pessoas de fora da minha organização</span><span class="sxs-lookup"><span data-stu-id="49269-243">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="49269-244">![Condições de DLP para detectar o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="49269-244">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="49269-245">**Actions**</span><span class="sxs-lookup"><span data-stu-id="49269-245">**Actions**</span></span>
        - <span data-ttu-id="49269-246">Restringir acesso de usuários externos ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="49269-246">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="49269-247">Notificar usuários com dicas de política e email</span><span class="sxs-lookup"><span data-stu-id="49269-247">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="49269-248">Enviar relatórios de incidentes para o administrador</span><span class="sxs-lookup"><span data-stu-id="49269-248">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="49269-249">![Ação DLP para bloquear o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="49269-249">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="49269-250">Política de DLP em ação ao tentar compartilhar um documento em SharePoint que contém informações confidenciais com um convidado externo:</span><span class="sxs-lookup"><span data-stu-id="49269-250">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49269-251">![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="49269-251">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="49269-252">Política de DLP em ação quando o convidado tenta abrir um documento em Teams com bloqueio externo:</span><span class="sxs-lookup"><span data-stu-id="49269-252">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49269-253">![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="49269-253">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="49269-254">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="49269-254">Related articles</span></span>

- [<span data-ttu-id="49269-255">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="49269-255">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="49269-256">Enviar notificações por email e mostrar dicas para políticas de DLP</span><span class="sxs-lookup"><span data-stu-id="49269-256">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
