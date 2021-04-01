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
description: Agora você pode aplicar políticas de DLP a chats e canais do Microsoft Teams. Leia este artigo para saber mais sobre como ele funciona.
ms.openlocfilehash: 40c55ed486efc75619b514a60b707ac75554953b
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445659"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="240ad-104">Prevenção contra perda de dados e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="240ad-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="240ad-105">Os recursos de prevenção contra perda de dados foram adicionados recentemente às mensagens de chat e canal do Microsoft Teams para usuários licenciados para Office 365 E5/A5, Microsoft 365 E5/A5, Proteção de Informações e Governança do Microsoft 365 ou Conformidade Avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="240ad-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="240ad-106">O Office 365 e o Microsoft 365 E3 incluem proteção DLP para SharePoint Online, OneDrive e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="240ad-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="240ad-107">Isso também inclui arquivos compartilhados pelo Teams porque o Teams usa o SharePoint Online e o OneDrive para compartilhar arquivos.</span><span class="sxs-lookup"><span data-stu-id="240ad-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="240ad-108">O suporte para proteção DLP no Teams Chat requer E5.</span><span class="sxs-lookup"><span data-stu-id="240ad-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="240ad-109">Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="240ad-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="240ad-110">Visão geral da DLP para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="240ad-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="240ad-111">Recentemente, [os recursos de](data-loss-prevention-policies.md) prevenção contra perda de dados (DLP) foram estendidos para incluir mensagens de chat e canal do Microsoft Teams, incluindo mensagens de canal **privado**.</span><span class="sxs-lookup"><span data-stu-id="240ad-111">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="240ad-112">A DLP atualmente só se aplica às mensagens reais no thread de chat ou canal.</span><span class="sxs-lookup"><span data-stu-id="240ad-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="240ad-113">As notificações de atividade - que incluem uma visualização de mensagem  curta e aparecem com base nas configurações de notificação de um usuário - não estão incluídas na DLP do Teams no momento.</span><span class="sxs-lookup"><span data-stu-id="240ad-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="240ad-114">Quaisquer informações confidenciais presentes na parte da mensagem exibida na visualização permanecerão visíveis na notificação mesmo após a política DLP ter sido aplicada e removida o inforamtion sensível da mensagem em si.</span><span class="sxs-lookup"><span data-stu-id="240ad-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive inforamtion the message itself.</span></span>

<span data-ttu-id="240ad-115">Se sua organização tiver DLP, agora você pode definir políticas que impedem que as pessoas compartilhem informações confidenciais em um canal do Microsoft Teams ou sessão de chat.</span><span class="sxs-lookup"><span data-stu-id="240ad-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="240ad-116">Aqui estão alguns exemplos de como essa proteção funciona:</span><span class="sxs-lookup"><span data-stu-id="240ad-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="240ad-117">**Exemplo 1: Protegendo informações confidenciais em mensagens**.</span><span class="sxs-lookup"><span data-stu-id="240ad-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="240ad-118">Suponha que alguém tenta compartilhar informações confidenciais em um chat ou canal do Teams com convidados (usuários externos).</span><span class="sxs-lookup"><span data-stu-id="240ad-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="240ad-119">Se você tiver uma política de DLP definida para evitar isso, as mensagens com informações confidenciais enviadas a usuários externos serão excluídas.</span><span class="sxs-lookup"><span data-stu-id="240ad-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="240ad-120">Isso acontece automaticamente e em segundos, de acordo com a configuração da política de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="240ad-121">A DLP do Microsoft Teams bloqueia conteúdos confidenciais quando compartilhados com usuários do Microsoft Teams que têm:</span><span class="sxs-lookup"><span data-stu-id="240ad-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="240ad-122">- [acesso de convidados](/MicrosoftTeams/guest-access) em equipes e canais; ou</span><span class="sxs-lookup"><span data-stu-id="240ad-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="240ad-123">- [acesso externo](/MicrosoftTeams/manage-external-access) em reuniões e sessões de chat.</span><span class="sxs-lookup"><span data-stu-id="240ad-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="240ad-124">A DLP para sessões de chat externo só funcionará se o remetente e o receptor estão no modo Teams Only e usando a federação nativa [do Microsoft Teams.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="240ad-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="240ad-125">A DLP para o Teams não bloqueia mensagens [em interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) com o Skype for Business ou sessões de chat federadas não nativas.</span><span class="sxs-lookup"><span data-stu-id="240ad-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="240ad-126">**Exemplo 2: Protegendo informações confidenciais em documentos**.</span><span class="sxs-lookup"><span data-stu-id="240ad-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="240ad-127">Suponha que alguém tenta compartilhar um documento com convidados em um canal ou chat do Microsoft Teams e o documento contém informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="240ad-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="240ad-128">Se você tiver uma política de DLP definida para evitar isso, o documento não abrirá para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="240ad-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="240ad-129">Observe que, nesse caso, sua política de DLP deve incluir o SharePoint e o OneDrive para que a proteção seja realizada.</span><span class="sxs-lookup"><span data-stu-id="240ad-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="240ad-130">(Este é um exemplo de DLP para SharePoint que aparece no Microsoft Teams e, portanto, exige que os usuários sejam licenciados para a DLP do Office 365 (incluído no Office 365 E3), mas não exige que os usuários sejam licenciados para a Conformidade Avançada do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="240ad-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="240ad-131">Dicas de política ajudam a instruir os usuários</span><span class="sxs-lookup"><span data-stu-id="240ad-131">Policy tips help educate users</span></span>

<span data-ttu-id="240ad-132">Semelhante a como a DLP funciona no [Exchange, Outlook, Outlook na Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)Sites do [SharePoint Online, OneDrive for Business](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)e clientes da área de trabalho do [Office,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)as dicas de política aparecem quando uma ação entra em conflito com uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="240ad-133">Veja um exemplo de uma dica de política:</span><span class="sxs-lookup"><span data-stu-id="240ad-133">Here's an example of a policy tip:</span></span>

![Notificação de mensagem bloqueada no Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="240ad-135">Nesse caso, o remetente tentou compartilhar um número de segurança social em um canal do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="240ad-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="240ad-136">O **link O que posso fazer?** abre uma caixa de diálogo que fornece opções para o remetente resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="240ad-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="240ad-137">Observe que, nesse caso, o remetente pode optar por substituir a política ou notificar um administrador para revisá-la e resolvê-la.</span><span class="sxs-lookup"><span data-stu-id="240ad-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Opções para resolver mensagens bloqueadas](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="240ad-139">Em sua organização, você pode optar por permitir que os usuários substituam uma política de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="240ad-140">E, ao configurar suas políticas de DLP, você pode usar as dicas de política padrão ou [personalizar dicas](#to-customize-policy-tips) de política para sua organização.</span><span class="sxs-lookup"><span data-stu-id="240ad-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="240ad-141">Retornando ao nosso exemplo, onde um remetente compartilhou um número de segurança social em um canal do Teams, veja o que o destinatário viu:</span><span class="sxs-lookup"><span data-stu-id="240ad-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="240ad-142">![Mensagem bloqueada](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

<span data-ttu-id="240ad-143">O **link O que é isso?** abre um [artigo](data-loss-prevention-policies.md) sobre políticas DLP, que ajuda a explicar por que a mensagem foi bloqueada.</span><span class="sxs-lookup"><span data-stu-id="240ad-143">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="240ad-144">Para personalizar dicas de política</span><span class="sxs-lookup"><span data-stu-id="240ad-144">To customize policy tips</span></span>

<span data-ttu-id="240ad-145">Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-145">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="240ad-146">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="240ad-146">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="240ad-147">Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="240ad-147">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="240ad-148">Escolha **Política de prevenção contra perda de**  >  **dados**.</span><span class="sxs-lookup"><span data-stu-id="240ad-148">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="240ad-149">Selecione uma política e, ao lado de **Configurações de Política,** escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-149">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="240ad-150">Crie uma nova regra ou edite uma regra existente para a política.</span><span class="sxs-lookup"><span data-stu-id="240ad-150">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-151">![Editar uma regra para uma política](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-151">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="240ad-152">Na guia **Notificações do usuário,** selecione **Personalizar o texto de email** e/ou Personalizar as opções de texto da dica **de** política.</span><span class="sxs-lookup"><span data-stu-id="240ad-152">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-153">![Personalizar notificações do usuário e dicas de política](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-153">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="240ad-154">Especifique o texto que você deseja usar para notificações por email e/ou dicas de política e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-154">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="240ad-155">Na guia **Configurações de Política,** escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-155">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="240ad-156">Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="240ad-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="240ad-157">Adicionar o Microsoft Teams como local às políticas de DLP existentes</span><span class="sxs-lookup"><span data-stu-id="240ad-157">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="240ad-158">Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="240ad-159">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="240ad-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="240ad-160">Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="240ad-160">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="240ad-161">Escolha **Política de prevenção contra perda de**  >  **dados**.</span><span class="sxs-lookup"><span data-stu-id="240ad-161">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="240ad-162">Selecione uma política e veja os valores em **Locais.**</span><span class="sxs-lookup"><span data-stu-id="240ad-162">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="240ad-163">Se você vir mensagens **de chat e canal do Teams,** você está definido.</span><span class="sxs-lookup"><span data-stu-id="240ad-163">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="240ad-164">Se não, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-164">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-165">![Locais para política existente](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-165">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="240ad-166">Na coluna **Status,** a política é a ativas para mensagens de chat e **canal do Teams.**</span><span class="sxs-lookup"><span data-stu-id="240ad-166">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-167">![DLP para chats e canais do Teams](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-167">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="240ad-168">Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="240ad-168">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="240ad-169">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="240ad-169">You can specify:</span></span>

    1. <span data-ttu-id="240ad-170">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="240ad-170">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="240ad-171">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="240ad-171">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="240ad-172">**Esse é um recurso de visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="240ad-172">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="240ad-173">Depois clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="240ad-173">Then choose **Next**.</span></span>

7. <span data-ttu-id="240ad-174">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-174">Click **Save**.</span></span>

<span data-ttu-id="240ad-175">Permita aproximadamente uma hora para que suas alterações funcionem por meio do data center e sincronizem com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="240ad-175">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="240ad-176">Definir uma nova política de DLP para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="240ad-176">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="240ad-177">Para executar essa tarefa, você deve ter uma função que tenha permissões para editar políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="240ad-177">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="240ad-178">Para saber mais, confira [permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="240ad-178">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="240ad-179">Vá para o Centro de Conformidade & segurança ( [https://protection.office.com](https://protection.office.com) ) e entre.</span><span class="sxs-lookup"><span data-stu-id="240ad-179">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="240ad-180">Escolha **Política de prevenção contra perda**  >  **de** dados + Criar uma  >  **política**.</span><span class="sxs-lookup"><span data-stu-id="240ad-180">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="240ad-181">Escolha um [modelo](data-loss-prevention-policies.md#dlp-policy-templates)e escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="240ad-181">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="240ad-182">No nosso exemplo, escolhemos o modelo de Dados de Informações de Identificação Pessoal dos EUA.</span><span class="sxs-lookup"><span data-stu-id="240ad-182">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-183">![Modelo de privacidade para política de DLP](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-183">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="240ad-184">Na guia **Nomear sua política,** especifique um nome e uma descrição para a política e escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="240ad-184">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="240ad-185">Na guia **Escolher locais,** mantenha a configuração padrão de todas as contas ou selecione **Deixe-me escolher locais específicos**.</span><span class="sxs-lookup"><span data-stu-id="240ad-185">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="240ad-186">É possível especificar:</span><span class="sxs-lookup"><span data-stu-id="240ad-186">You can specify:</span></span>

    1. <span data-ttu-id="240ad-187">até 1000 contas individuais para incluir ou excluir</span><span class="sxs-lookup"><span data-stu-id="240ad-187">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="240ad-188">listas de distribuição e grupos de segurança para incluir ou excluir.</span><span class="sxs-lookup"><span data-stu-id="240ad-188">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="240ad-189">**Esse é um recurso de visualização pública.**</span><span class="sxs-lookup"><span data-stu-id="240ad-189">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![Locais de política DLP](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="240ad-191">Se você quiser garantir que documentos que contenham informações confidenciais não sejam compartilhados de forma inadequada no Teams, certifique-se de que sites do **SharePoint** e contas do **OneDrive** estão ativas, juntamente com mensagens de chat e canal do **Teams.**</span><span class="sxs-lookup"><span data-stu-id="240ad-191">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="240ad-192">Na guia **Configurações de** Política, em Personalizar o tipo de conteúdo que você deseja **proteger,** mantenha as configurações simples padrão ou escolha Usar configurações **avançadas** e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-192">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="240ad-193">Se você escolher configurações avançadas, poderá criar ou editar regras para sua política.</span><span class="sxs-lookup"><span data-stu-id="240ad-193">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="240ad-194">(Para obter ajuda com isso, consulte [Configurações simples versus configurações avançadas](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span><span class="sxs-lookup"><span data-stu-id="240ad-194">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="240ad-195">Na guia **Configurações de** Política, em O que você deseja fazer se detectarmos informações **confidenciais?**, revise as configurações.</span><span class="sxs-lookup"><span data-stu-id="240ad-195">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="240ad-196">(Aqui é onde você pode optar por manter dicas de política padrão e [notificações de email](use-notifications-and-policy-tips.md)ou personalizá-las.)</span><span class="sxs-lookup"><span data-stu-id="240ad-196">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-197">![Configurações de política de DLP com dicas e notificações](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-197">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="240ad-198">Quando terminar de revisar ou editar configurações, escolha **Next**.</span><span class="sxs-lookup"><span data-stu-id="240ad-198">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="240ad-199">Na  guia Configurações de Política, em Deseja ativar a política ou testar as coisas **primeiro?**, escolha se deseja ativar a [política,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)testá-la primeiro ou mantê-la desligada por enquanto e, em seguida, escolher **Next**.</span><span class="sxs-lookup"><span data-stu-id="240ad-199">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="240ad-200">![Especificar se a política deve ser a a ativar](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-200">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="240ad-201">Na guia **Revisar suas configurações,** revise as configurações da nova política.</span><span class="sxs-lookup"><span data-stu-id="240ad-201">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="240ad-202">Escolha **Editar** para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="240ad-202">Choose **Edit** to make changes.</span></span> <span data-ttu-id="240ad-203">Quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="240ad-203">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="240ad-204">Permita aproximadamente uma hora para que sua nova política funcione por meio do data center e sincronize com contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="240ad-204">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="240ad-205">Impedir o acesso externo a documentos confidenciais</span><span class="sxs-lookup"><span data-stu-id="240ad-205">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="240ad-206">Para garantir que documentos do SharePoint que contenham informações confidenciais não podem ser acessados por convidados externos do SharePoint ou do Teams por padrão, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="240ad-206">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="240ad-207">Você pode garantir que os documentos sejam protegidos até que a DLP os verifique e os marque como seguros para compartilhar marcando novos arquivos como confidenciais [por padrão.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="240ad-207">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="240ad-208">Estrutura de política de DLP recomendada</span><span class="sxs-lookup"><span data-stu-id="240ad-208">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="240ad-209">**Condições**</span><span class="sxs-lookup"><span data-stu-id="240ad-209">**Conditions**</span></span>
        - <span data-ttu-id="240ad-210">O conteúdo contém qualquer um desses tipos de informações confidenciais: [Selecione tudo o que se aplica]</span><span class="sxs-lookup"><span data-stu-id="240ad-210">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="240ad-211">O conteúdo é compartilhado do Microsoft 365 com pessoas de fora da minha organização</span><span class="sxs-lookup"><span data-stu-id="240ad-211">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="240ad-212">![Condições de DLP para detectar o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-212">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="240ad-213">**Ações**</span><span class="sxs-lookup"><span data-stu-id="240ad-213">**Actions**</span></span>
        - <span data-ttu-id="240ad-214">Restringir o acesso ao conteúdo para usuários externos</span><span class="sxs-lookup"><span data-stu-id="240ad-214">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="240ad-215">Notificar os usuários com dicas de política e email</span><span class="sxs-lookup"><span data-stu-id="240ad-215">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="240ad-216">Enviar relatórios de incidentes ao Administrador</span><span class="sxs-lookup"><span data-stu-id="240ad-216">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="240ad-217">![Ação DLP para bloquear o compartilhamento externo de conteúdos confidenciais](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-217">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="240ad-218">Política de DLP em ação ao tentar compartilhar um documento no SharePoint que contém informações confidenciais com um convidado externo:</span><span class="sxs-lookup"><span data-stu-id="240ad-218">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="240ad-219">![Compartilhamento externo bloqueado](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-219">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="240ad-220">Política de DLP em ação quando o convidado tenta abrir um documento no Teams com bloqueio externo:</span><span class="sxs-lookup"><span data-stu-id="240ad-220">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="240ad-221">![Acesso externo bloqueado](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="240ad-221">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="240ad-222">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="240ad-222">Related articles</span></span>

[<span data-ttu-id="240ad-223">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="240ad-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="240ad-224">Enviar notificações por email e mostrar dicas para políticas de DLP</span><span class="sxs-lookup"><span data-stu-id="240ad-224">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
