---
title: Configurar equipes com proteção de linha de base
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: Aprenda a implantar equipes com um nível de linha de base de proteção.
ms.openlocfilehash: 678e9824682339afda32342e70848492b738ec6d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052500"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="92fdc-103">Configurar equipes com proteção de linha de base</span><span class="sxs-lookup"><span data-stu-id="92fdc-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="92fdc-104">Neste artigo, veremos como implantar equipes com um nível de linha de base de proteção.</span><span class="sxs-lookup"><span data-stu-id="92fdc-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="92fdc-105">Esse nível permite aos usuários uma grande variedade de opções de colaboração, melhorando o gerenciamento de permissões e fornecendo proteção básica contra o compartilhamento em excesso.</span><span class="sxs-lookup"><span data-stu-id="92fdc-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="92fdc-106">As proteções recomendadas para esse nível incluem políticas de acesso a dispositivos e identidades e proteção contra malware.</span><span class="sxs-lookup"><span data-stu-id="92fdc-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="92fdc-107">Além disso, você pode aplicar políticas de acesso condicional e proteções contra perda de dados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="92fdc-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="92fdc-108">Proteções iniciais</span><span class="sxs-lookup"><span data-stu-id="92fdc-108">Initial protections</span></span>

<span data-ttu-id="92fdc-109">Como primeira etapa, recomendamos que você configure as políticas básicas de acesso a dispositivos e identidade.</span><span class="sxs-lookup"><span data-stu-id="92fdc-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="92fdc-110">Para saber mais, confira [Recomendações de política para proteger conversas, grupos e arquivos no Teams](../security/defender-365-security/teams-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="92fdc-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/defender-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="92fdc-111">Também recomendamos ativar os recursos básicos do Defender para Office 365 para proteção contra malware em documentos, anexos e links.</span><span class="sxs-lookup"><span data-stu-id="92fdc-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="92fdc-112">Recomendamos ativar cada uma das opções na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="92fdc-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="92fdc-113">Opção</span><span class="sxs-lookup"><span data-stu-id="92fdc-113">Option</span></span>|<span data-ttu-id="92fdc-114">Informações</span><span class="sxs-lookup"><span data-stu-id="92fdc-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="92fdc-115">Anexos seguros para SPO, Microsoft OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="92fdc-116">Anexos Seguros</span><span class="sxs-lookup"><span data-stu-id="92fdc-116">Safe Attachments</span></span>](../security/defender-365-security/safe-attachments.md)<br>[<span data-ttu-id="92fdc-117">Defender para Office 365 - Microsoft Office SharePoint Online, Microsoft OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](../security/defender-365-security/mdo-for-spo-odb-and-teams.md)|
|<span data-ttu-id="92fdc-118">Documentos Seguros</span><span class="sxs-lookup"><span data-stu-id="92fdc-118">Safe Documents</span></span>|[<span data-ttu-id="92fdc-119">Documentos Seguros no Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="92fdc-119">Safe Documents in Microsoft Defender for Office 365</span></span>](../security/defender-365-security/safe-docs.md)|
|<span data-ttu-id="92fdc-120">Links Seguros para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-120">Safe Links for Teams</span></span>|[<span data-ttu-id="92fdc-121">Links seguros do Office 365 no Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-121">Office 365 Safe Links in Teams</span></span>](../security/defender-365-security/safe-links.md#safe-links-settings-for-microsoft-teamssafe-links-settings-for-microsoft-teams)<br>[<span data-ttu-id="92fdc-122">Links Seguros</span><span class="sxs-lookup"><span data-stu-id="92fdc-122">Safe Links</span></span>](../security/defender-365-security/safe-links.md)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="92fdc-123">Compartilhamento de convidados no Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-123">Teams guest sharing</span></span>

<span data-ttu-id="92fdc-124">Em cada uma das camadas, temos a opção de compartilhar com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="92fdc-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="92fdc-125">Para as camadas confidenciais e altamente confidenciais, temos a opção de desativar o compartilhamento de convidados no nível da equipe usando rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="92fdc-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="92fdc-126">No entanto, a configuração de compartilhamento de convidados no nível da organização deve estar habilitada para que o compartilhamento de convidados funcione no Teams.</span><span class="sxs-lookup"><span data-stu-id="92fdc-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Captura de tela de alternância de acesso de convidados](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="92fdc-128">Para definir as configurações de acesso de convidado do Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="92fdc-129">Entre no Centro de administração do Microsoft 365 em [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="92fdc-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="92fdc-130">Na barra de navegação esquerda, clique em **Mostrar tudo**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="92fdc-131">Em **Centros de administração**, clique em **Teams**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-131">Under **Admin centers**, click **Teams**.</span></span>
4. <span data-ttu-id="92fdc-132">No Centro de administração do Teams, na navegação à esquerda, expanda **Configurações para toda a organização** e clique em **Acesso de convidado**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="92fdc-133">Certifique-se de que **Permitir acesso de convidado no Teams** esteja definido como **Ativado**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="92fdc-134">Faça as alterações desejadas nas configurações de convidado adicionais e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="92fdc-135">Depois de habilitá-la, pode levar até 24 horas para que a configuração de convidado do Teams se torne ativa.</span><span class="sxs-lookup"><span data-stu-id="92fdc-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="92fdc-136">O compartilhamento de convidados é habilitado por padrão para grupos do Office 365 e SharePoint, no entanto, se você alterou anteriormente qualquer uma das configurações de compartilhamento de convidados da sua organização, recomendamos que examine [Colaborar com convidados em uma equipe](./collaborate-as-team.md) para garantir que o compartilhamento de convidados esteja disponível no Teams.</span><span class="sxs-lookup"><span data-stu-id="92fdc-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](./collaborate-as-team.md) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="92fdc-137">Compartilhamento de sites e arquivos</span><span class="sxs-lookup"><span data-stu-id="92fdc-137">Site and file sharing</span></span>

<span data-ttu-id="92fdc-138">Para reduzir o risco de compartilhar acidentalmente arquivos ou pastas com pessoas de fora da sua organização, recomendamos alterar o link de compartilhamento padrão no SharePoint para *Somente as pessoas da sua organização*.</span><span class="sxs-lookup"><span data-stu-id="92fdc-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="92fdc-139">(Se os usuários precisarem compartilhar externamente e você tiver habilitado o compartilhamento de convidados, eles ainda poderão alterar o tipo de link quando compartilharem.)</span><span class="sxs-lookup"><span data-stu-id="92fdc-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="92fdc-140">Para alterar o link de compartilhamento padrão</span><span class="sxs-lookup"><span data-stu-id="92fdc-140">To change the default sharing link</span></span>
1. <span data-ttu-id="92fdc-141">Abra o [Centro de Administração do SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="92fdc-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="92fdc-142">Em **Políticas**, clique em **Compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-142">Under **Policies**, click **Sharing**.</span></span>
3. <span data-ttu-id="92fdc-143">Em **Links de arquivos e pastas**, selecione **Somente as pessoas da sua organização**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-143">Under **File and folder links**, select **Only people in your organization**.</span></span>
4. <span data-ttu-id="92fdc-144">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-144">Click **Save**.</span></span>

<span data-ttu-id="92fdc-145">Para obter a melhor experiência de compartilhamento de convidados, recomendamos também que você habilite a [Integração do SharePoint e do OneDrive com o B2B do Azure AD](/sharepoint/sharepoint-azureb2b-integration-preview).</span><span class="sxs-lookup"><span data-stu-id="92fdc-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="92fdc-146">Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="92fdc-146">Create a team</span></span>

<span data-ttu-id="92fdc-147">A configuração adicional para o nível de linha de base de proteção foi realizada no site do SharePoint associado a uma equipe.</span><span class="sxs-lookup"><span data-stu-id="92fdc-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="92fdc-148">[Crie uma equipe pública ou privada](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) antes de prosseguir para a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="92fdc-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="92fdc-149">Configurações de compartilhamento de site</span><span class="sxs-lookup"><span data-stu-id="92fdc-149">Site sharing settings</span></span>

<span data-ttu-id="92fdc-150">Por padrão, os membros de um site do SharePoint podem convidar outras pessoas para o site.</span><span class="sxs-lookup"><span data-stu-id="92fdc-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="92fdc-151">Quando um site faz parte de uma equipe, os membros da equipe são incluídos como membros do site.</span><span class="sxs-lookup"><span data-stu-id="92fdc-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="92fdc-152">No entanto, as pessoas adicionadas diretamente ao site não têm acesso ao restante da equipe.</span><span class="sxs-lookup"><span data-stu-id="92fdc-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="92fdc-153">Por esse motivo, recomendamos o gerenciamento de permissões exclusivamente por meio da equipe.</span><span class="sxs-lookup"><span data-stu-id="92fdc-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="92fdc-154">Para ajudar com o gerenciamento de permissões, recomendamos configurar o site associado para permitir que somente os proprietários compartilhem o site por si só.</span><span class="sxs-lookup"><span data-stu-id="92fdc-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="92fdc-155">Isso simplifica o gerenciamento de permissões e ajuda a impedir o acesso de pessoas sem o conhecimento do proprietário da equipe.</span><span class="sxs-lookup"><span data-stu-id="92fdc-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="92fdc-156">Faça isso para cada equipe que precise da proteção da linha de base.</span><span class="sxs-lookup"><span data-stu-id="92fdc-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="92fdc-157">Para atualizar as configurações de compartilhamento de site</span><span class="sxs-lookup"><span data-stu-id="92fdc-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="92fdc-158">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="92fdc-159">Clique em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="92fdc-160">Na barra de ferramentas do site do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="92fdc-161">No painel **Permissões do site**, em **Compartilhamento do site**, clique em **Alterar como os membros podem compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-161">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
5. <span data-ttu-id="92fdc-162">Em **Compartilhar permissões**, escolha **Proprietários e membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site** e, em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="92fdc-162">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="92fdc-163">Proteções adicionais</span><span class="sxs-lookup"><span data-stu-id="92fdc-163">Additional protections</span></span>

<span data-ttu-id="92fdc-164">O Microsoft 365 oferece métodos adicionais para proteger seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="92fdc-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="92fdc-165">Considere se as seguintes opções ajudariam a melhorar a segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="92fdc-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="92fdc-166">Faça com que os convidados concordem com os [termos de uso](/azure/active-directory/conditional-access/terms-of-use).</span><span class="sxs-lookup"><span data-stu-id="92fdc-166">Have guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="92fdc-167">Configurar uma [política de tempo limite de sessão](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) para convidados.</span><span class="sxs-lookup"><span data-stu-id="92fdc-167">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="92fdc-168">Criar [tipos de informações confidenciais](../compliance/sensitive-information-type-learn-about.md) e usar a [proteção contra perda de dados](../compliance/data-loss-prevention-policies.md) para definir políticas de acesso a informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="92fdc-168">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/data-loss-prevention-policies.md) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="92fdc-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="92fdc-169">See Also</span></span>

[<span data-ttu-id="92fdc-170">Gerenciar políticas de reunião no Teams</span><span class="sxs-lookup"><span data-stu-id="92fdc-170">Manage meeting policies in Teams</span></span>](/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="92fdc-171">Introdução ao gerenciamento de riscos internos</span><span class="sxs-lookup"><span data-stu-id="92fdc-171">Get started with insider risk management</span></span>](../compliance/insider-risk-management-configure.md)