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
description: Agora você pode aplicar políticas DLP para Microsoft Teams chats e canais. Leia este artigo para saber mais sobre como funciona.
ms.openlocfilehash: 9fdce86473dcfbb7ec75b9d371b8782d4141ef57
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572460"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="06527-104">Prevenção contra perda de dados e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06527-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="06527-105">Os recursos de prevenção de perda de dados foram recentemente adicionados a mensagens de chat e canal Microsoft Teams para usuários licenciados para Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Proteção e Governança de Informações ou Conformidade Avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="06527-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="06527-106">Office 365 e Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="06527-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="06527-107">Isso também inclui arquivos que são compartilhados através de Teams porque Teams usa SharePoint Online e OneDrive para compartilhar arquivos.</span><span class="sxs-lookup"><span data-stu-id="06527-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="06527-108">O suporte para proteção DLP no Chat Teams requer E5.</span><span class="sxs-lookup"><span data-stu-id="06527-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="06527-109">Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="06527-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="06527-110">Visão geral da DLP para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06527-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="06527-111">Recentemente, os recursos de [prevenção de perda de dados](dlp-learn-about-dlp.md) foram estendidos para incluir Microsoft Teams mensagens de chat e canais, incluindo **mensagens de canais privados.**</span><span class="sxs-lookup"><span data-stu-id="06527-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="06527-112">Atualmente, o DLP se aplica apenas às mensagens reais no segmento de chat ou canal.</span><span class="sxs-lookup"><span data-stu-id="06527-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="06527-113">As notificações de atividade - que incluem uma visualização de mensagem curta e aparecem com base nas configurações de notificação de um usuário - **não** estão incluídas em Teams DLP neste momento.</span><span class="sxs-lookup"><span data-stu-id="06527-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="06527-114">Quaisquer informações confidenciais presentes na parte da mensagem que aparece na visualização permanecerão visíveis na notificação mesmo após a aplicação da política DLP e removida informações confidenciais da própria mensagem.</span><span class="sxs-lookup"><span data-stu-id="06527-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="06527-115">Se sua organização tiver DLP, agora você pode definir políticas que impeçam as pessoas de compartilhar informações confidenciais em um canal de Microsoft Teams ou sessão de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="06527-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="06527-116">Aqui estão alguns exemplos de como essa proteção funciona:</span><span class="sxs-lookup"><span data-stu-id="06527-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="06527-117">**Exemplo 1: Proteção de informações confidenciais em mensagens**.</span><span class="sxs-lookup"><span data-stu-id="06527-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="06527-118">Suponha que alguém tente compartilhar informações confidenciais em um chat ou canal Teams com convidados (usuários externos).</span><span class="sxs-lookup"><span data-stu-id="06527-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="06527-119">Se você tiver uma política DLP definida para evitar isso, mensagens com informações confidenciais enviadas a usuários externos serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="06527-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="06527-120">Isso acontece automaticamente e em segundos, de acordo com a forma como sua política de DLP é configurada.</span><span class="sxs-lookup"><span data-stu-id="06527-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06527-121">O DLP for Microsoft Teams bloqueia conteúdo sensível quando compartilhado com Microsoft Teams usuários que têm:</span><span class="sxs-lookup"><span data-stu-id="06527-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="06527-122">- [acesso de hóspedes](/MicrosoftTeams/guest-access) em equipes e canais; ou</span><span class="sxs-lookup"><span data-stu-id="06527-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="06527-123">- [acesso externo](/MicrosoftTeams/manage-external-access) em reuniões e sessões de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="06527-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="06527-124">O DLP para sessões de bate-papo externo só funcionará se o remetente e o receptor estiverem no modo somente Teams e usando [Microsoft Teams federação nativa](/microsoftteams/manage-external-access).</span><span class="sxs-lookup"><span data-stu-id="06527-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="06527-125">O DLP para Teams não bloqueia mensagens em [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com sessões de bate-papo federadas Skype for Business ou não nativas.</span><span class="sxs-lookup"><span data-stu-id="06527-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="06527-126">**Exemplo 2: Proteção de informações confidenciais em documentos**.</span><span class="sxs-lookup"><span data-stu-id="06527-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="06527-127">Suponha que alguém tente compartilhar um documento com convidados em um canal ou chat Microsoft Teams, e o documento contém informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="06527-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="06527-128">Se você tiver uma política DLP definida para evitar isso, o documento não será aberto para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="06527-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="06527-129">Observe que, neste caso, sua política de DLP deve incluir SharePoint e OneDrive para que a proteção esteja em vigor.</span><span class="sxs-lookup"><span data-stu-id="06527-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="06527-130">(Este é um exemplo de DLP para SharePoint que aparece em Microsoft Teams e, portanto, exige que os usuários sejam licenciados para Office 365 DLP (incluído em Office 365 E3), mas não exige que os usuários sejam licenciados por Conformidade Avançada do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="06527-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="06527-131">Dicas de políticas ajudam a educar os usuários</span><span class="sxs-lookup"><span data-stu-id="06527-131">Policy tips help educate users</span></span>

<span data-ttu-id="06527-132">Semelhante à forma como o DLP funciona em [Exchange, Outlook, Outlook na web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, sites de OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e Office [clientes de desktop](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), as dicas de políticas aparecem quando uma ação entra em conflito com uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="06527-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="06527-133">Aqui está um exemplo de uma dica de política:</span><span class="sxs-lookup"><span data-stu-id="06527-133">Here's an example of a policy tip:</span></span>

![Notificação de mensagem bloqueada em Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="06527-135">Neste caso, o remetente tentou compartilhar um número de segurança social em um canal Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="06527-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="06527-136">O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="06527-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="06527-137">Observe que, neste caso, o remetente pode optar por substituir a apólice ou notificar um administrador para revisá-la e resolvê-la.</span><span class="sxs-lookup"><span data-stu-id="06527-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opções para resolver mensagem bloqueada](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="06527-139">Em sua organização, você pode optar por permitir que os usuários substituam uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="06527-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="06527-140">E, ao configurar suas políticas DLP, você pode usar as dicas de política padrão ou [personalizar dicas de política](#to-customize-policy-tips) para sua organização.</span><span class="sxs-lookup"><span data-stu-id="06527-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="06527-141">Voltando ao nosso exemplo, onde um remetente compartilhou um número de segurança social em um canal de Teams, aqui está o que o destinatário viu:</span><span class="sxs-lookup"><span data-stu-id="06527-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06527-142">![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="06527-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="06527-143">Dicas para personalizar a política</span><span class="sxs-lookup"><span data-stu-id="06527-143">To customize policy tips</span></span>

<span data-ttu-id="06527-144">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="06527-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="06527-145">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="06527-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="06527-146">Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.</span><span class="sxs-lookup"><span data-stu-id="06527-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="06527-147">Clique em **Prevenção contra perda de dados** > **Política**.</span><span class="sxs-lookup"><span data-stu-id="06527-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="06527-148">Selecione uma política e, ao lado **das configurações de política,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="06527-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="06527-149">Crie uma nova regra ou edite uma regra existente para a política.</span><span class="sxs-lookup"><span data-stu-id="06527-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-150">![Editando uma regra para uma política](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="06527-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="06527-151">Na guia **Notificações do Usuário,** selecione **Personalizar o texto de e-mail** e/ou Personalizar as opções **de texto de ponta de política.**</span><span class="sxs-lookup"><span data-stu-id="06527-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-152">![Personalize notificações e dicas de políticas de usuários](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="06527-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="06527-153">Especifique o texto que deseja usar para notificações de e-mail e/ou dicas de política e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="06527-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="06527-154">Na guia **Configurações de políticas,** escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="06527-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="06527-155">Permita aproximadamente uma hora para que suas alterações funcionem através do data center e sincronizem com as contas de usuários.</span><span class="sxs-lookup"><span data-stu-id="06527-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="06527-156">Adicionar o Microsoft Teams como um local para as políticas de DLP existentes</span><span class="sxs-lookup"><span data-stu-id="06527-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="06527-157">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="06527-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="06527-158">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="06527-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="06527-159">Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.</span><span class="sxs-lookup"><span data-stu-id="06527-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="06527-160">Clique em **Prevenção contra perda de dados** > **Política**.</span><span class="sxs-lookup"><span data-stu-id="06527-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="06527-161">Selecione uma política e veja os valores em **Locais**.</span><span class="sxs-lookup"><span data-stu-id="06527-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="06527-162">Se você vir **Teams chat e mensagens de canal,** está tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="06527-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="06527-163">Se não o fizer, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="06527-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-164">![Locais para a política existente](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="06527-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="06527-165">Na coluna **Status,** ligue a política para **Teams mensagens de chat e canal**.</span><span class="sxs-lookup"><span data-stu-id="06527-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-166">![DLP para Teams chats e canais](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="06527-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="06527-167">Na guia **Escolher locais,** manter a configuração padrão de todas as contas ou selecionar **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="06527-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="06527-168">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="06527-168">You can specify:</span></span>

    1. <span data-ttu-id="06527-169">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="06527-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="06527-170">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="06527-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="06527-171">Depois clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="06527-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="06527-172">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="06527-172">Click **Save**.</span></span>

<span data-ttu-id="06527-173">Permita aproximadamente uma hora para que suas alterações funcionem através do data center e sincronizem com as contas de usuários.</span><span class="sxs-lookup"><span data-stu-id="06527-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="06527-174">Definir uma nova política DLP para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="06527-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="06527-175">Para executar essa tarefa, você deverá receber uma função que tenha permissões para editar as políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="06527-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="06527-176">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="06527-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="06527-177">Vá ao Centro de Conformidade & de Segurança [https://protection.office.com](https://protection.office.com) e faça login.</span><span class="sxs-lookup"><span data-stu-id="06527-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="06527-178">Escolha **Prevenção contra perda de dados** > **Política** > **+ Criar uma política**.</span><span class="sxs-lookup"><span data-stu-id="06527-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="06527-179">Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **o Next**.</span><span class="sxs-lookup"><span data-stu-id="06527-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="06527-180">Em nosso exemplo, escolhemos o modelo de dados de informações pessoalmente identificáveis dos EUA.</span><span class="sxs-lookup"><span data-stu-id="06527-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-181">![Modelo de privacidade para a política DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="06527-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="06527-182">Na guia **Nomear sua política,** especifique um nome e descrição para a política e, em seguida, escolha **o Próximo**.</span><span class="sxs-lookup"><span data-stu-id="06527-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="06527-183">Na guia **Escolher locais,** manter a configuração padrão de todas as contas ou selecionar **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="06527-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="06527-184">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="06527-184">You can specify:</span></span>

    1. <span data-ttu-id="06527-185">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="06527-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="06527-186">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="06527-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="06527-187">**Este é um recurso de pré-visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="06527-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Localizações de políticas DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="06527-189">Se você quiser garantir que documentos que contenham informações confidenciais não sejam compartilhados inapropriadamente em Teams, certifique-se **de que SharePoint sites** e contas **OneDrive** sejam ligados, juntamente com **Teams mensagens de chat e canal**.</span><span class="sxs-lookup"><span data-stu-id="06527-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="06527-190">Na guia **Configurações De políticas,** em **Personalizar o tipo de conteúdo que deseja proteger,** mantenha as configurações simples padrão ou escolha **Usar configurações avançadas** e, em seguida, escolha **o Próximo**.</span><span class="sxs-lookup"><span data-stu-id="06527-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="06527-191">Se você escolher configurações avançadas, você pode criar ou editar regras para sua política.</span><span class="sxs-lookup"><span data-stu-id="06527-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="06527-192">(Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span><span class="sxs-lookup"><span data-stu-id="06527-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="06527-193">Na guia **Configurações De políticas,** em **que você deseja fazer se detectarmos informações confidenciais?**</span><span class="sxs-lookup"><span data-stu-id="06527-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="06527-194">(Aqui é onde você pode optar por manter dicas de política padrão [e notificações de e-mail](use-notifications-and-policy-tips.md), ou personalizá-las.)</span><span class="sxs-lookup"><span data-stu-id="06527-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-195">![Configurações de políticas DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="06527-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="06527-196">Quando terminar de revisar ou editar configurações, escolha **o Next**.</span><span class="sxs-lookup"><span data-stu-id="06527-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="06527-197">Na guia **Configurações de políticas,** em **Você deseja ativar a política ou testar as coisas primeiro?**, escolha se ativar a política, [testá-la primeiro](dlp-overview-plan-for-dlp.md#policy-deployment)ou mantê-la desligada por enquanto e, em seguida, escolher o **Next**.</span><span class="sxs-lookup"><span data-stu-id="06527-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06527-198">![Especifique se ativar a política](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="06527-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="06527-199">Na guia **Analisar suas configurações,** revise as configurações da sua nova política.</span><span class="sxs-lookup"><span data-stu-id="06527-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="06527-200">Escolha **Editar** para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="06527-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="06527-201">Quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="06527-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="06527-202">Permita que aproximadamente uma hora para sua nova política funcione através do seu data center e sincronize com as contas de usuários.</span><span class="sxs-lookup"><span data-stu-id="06527-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="06527-203">Impedir o acesso externo a documentos confidenciais</span><span class="sxs-lookup"><span data-stu-id="06527-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="06527-204">Para garantir que SharePoint documentos que contenham informações confidenciais não possam ser acessados por hóspedes externos SharePoint ou Teams por padrão, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="06527-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="06527-205">Você pode garantir que os documentos estejam protegidos até que o DLP os digitaliza e os marque como seguros de compartilhar [marcando novos arquivos como sensíveis por padrão](/sharepoint/sensitive-by-default).</span><span class="sxs-lookup"><span data-stu-id="06527-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="06527-206">Estrutura de política DLP recomendada</span><span class="sxs-lookup"><span data-stu-id="06527-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="06527-207">**Condições**</span><span class="sxs-lookup"><span data-stu-id="06527-207">**Conditions**</span></span>
        - <span data-ttu-id="06527-208">O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]</span><span class="sxs-lookup"><span data-stu-id="06527-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="06527-209">O conteúdo é compartilhado de Microsoft 365 com pessoas de fora da minha organização</span><span class="sxs-lookup"><span data-stu-id="06527-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="06527-210">![Condições de DLP para detectar compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="06527-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="06527-211">**Actions**</span><span class="sxs-lookup"><span data-stu-id="06527-211">**Actions**</span></span>
        - <span data-ttu-id="06527-212">Restringir acesso de usuários externos ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="06527-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="06527-213">Notificar usuários com dicas de política e email</span><span class="sxs-lookup"><span data-stu-id="06527-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="06527-214">Enviar relatórios de incidentes para o administrador</span><span class="sxs-lookup"><span data-stu-id="06527-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="06527-215">![Ação do DLP para bloquear o compartilhamento externo de conteúdo sensível](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="06527-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="06527-216">Política DLP em ação ao tentar compartilhar um documento em SharePoint que contenha informações confidenciais com um convidado externo:</span><span class="sxs-lookup"><span data-stu-id="06527-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06527-217">![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="06527-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="06527-218">Política DLP em ação quando o hóspede tenta abrir um documento em Teams com bloco externo:</span><span class="sxs-lookup"><span data-stu-id="06527-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06527-219">![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="06527-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="06527-220">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="06527-220">Related articles</span></span>

[<span data-ttu-id="06527-221">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="06527-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="06527-222">Enviar notificações por email e mostrar dicas para políticas de DLP</span><span class="sxs-lookup"><span data-stu-id="06527-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
