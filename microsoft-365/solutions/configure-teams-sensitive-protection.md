---
title: Configurar equipes com proteção para dados altamente confidenciais
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
recommendations: false
description: Aprenda a implantar equipes com proteção para dados altamente confidenciais.
ms.openlocfilehash: a3f715cb05ad1d5acf3c93c58959f12ebec46978
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788335"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="c386e-103">Configurar equipes com proteção para dados altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="c386e-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="c386e-104">Neste artigo, examinamos a criação de uma equipe com um nível de proteção altamente confidencial.</span><span class="sxs-lookup"><span data-stu-id="c386e-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="c386e-105">Certifique-se de ter concluído as etapas em [Implantar equipes com proteção de linha de base](configure-teams-baseline-protection.md) antes de seguir as etapas deste artigo.</span><span class="sxs-lookup"><span data-stu-id="c386e-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="c386e-106">A camada altamente confidencial oferece as seguintes proteções adicionais sobre a camada de linha de base:</span><span class="sxs-lookup"><span data-stu-id="c386e-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="c386e-p102">Um rótulo de confidencialidade para a equipe que permite ativar ou desativar o compartilhamento de convidados e limita o acesso ao conteúdo do Microsoft Office SharePoint Online a somente Web para dispositivos não gerenciados. Este rótulo também pode ser usado para classificar arquivos.</span><span class="sxs-lookup"><span data-stu-id="c386e-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="c386e-109">Um tipo de link de compartilhamento padrão mais restritivo</span><span class="sxs-lookup"><span data-stu-id="c386e-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="c386e-110">Somente os proprietários da equipe podem criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="c386e-110">Only team owners can create private channels.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="c386e-111">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="c386e-111">Video demonstration</span></span>

<span data-ttu-id="c386e-112">Assista a este vídeo para ver um passo a passo dos procedimentos descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c386e-112">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NMS6]

## <a name="guest-sharing"></a><span data-ttu-id="c386e-113">Compartilhamento de convidados</span><span class="sxs-lookup"><span data-stu-id="c386e-113">Guest sharing</span></span>

<span data-ttu-id="c386e-114">Dependendo da natureza da sua empresa, você pode ou não querer ativar o compartilhamento de convidados para equipes que contenham dados altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="c386e-114">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="c386e-115">Se você planeja colaborar com pessoas de fora da sua organização na equipe, recomendamos ativar o compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="c386e-115">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="c386e-116">O Microsoft 365 inclui vários recursos de segurança e conformidade para ajudar você a compartilhar conteúdo confidencial com segurança.</span><span class="sxs-lookup"><span data-stu-id="c386e-116">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="c386e-117">Geralmente, esta é uma opção mais segura do que enviar conteúdo por email diretamente para pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c386e-117">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="c386e-118">Para obter detalhes sobre como compartilhar com convidados com segurança, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="c386e-118">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="c386e-119">Limitar a exposição acidental a arquivos ao compartilhar arquivos com pessoas de fora da sua organização</span><span class="sxs-lookup"><span data-stu-id="c386e-119">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="c386e-120">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="c386e-120">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="c386e-121">Para permitir ou bloquear o compartilhamento de convidados, usamos uma combinação de um rótulo de confidencialidade para a equipe e controles de compartilhamento no nível do site para o Microsoft Office SharePoint Online associado, ambos discutidos mais adiante.</span><span class="sxs-lookup"><span data-stu-id="c386e-121">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="c386e-122">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="c386e-122">Sensitivity labels</span></span>

<span data-ttu-id="c386e-123">Para o nível de proteção altamente confidencial, usaremos um rótulo de confidencialidade para classificar a equipe.</span><span class="sxs-lookup"><span data-stu-id="c386e-123">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="c386e-124">Este rótulo também pode ser usado para classificar e criptografar arquivos individuais nesta ou em outras equipes ou em outros locais de arquivos, como o Microsoft Office SharePoint Online ou o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c386e-124">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="c386e-125">Como primeira etapa, você deve habilitar os rótulos de confidencialidade para o Teams.</span><span class="sxs-lookup"><span data-stu-id="c386e-125">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="c386e-126">Confira [Usar rótulos de confidencialidade para proteger o conteúdo no Microsoft Teams, grupos do Office 365 e sites do Microsoft Office SharePoint Online](../compliance/sensitivity-labels-teams-groups-sites.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="c386e-126">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="c386e-127">Se você já possui rótulos de confidencialidade implantados em sua organização, considere como este rótulo se ajusta à sua estratégia geral de rotulação.</span><span class="sxs-lookup"><span data-stu-id="c386e-127">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="c386e-128">Você pode alterar o nome ou as configurações, se necessário, para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c386e-128">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="c386e-129">Depois de ativar os rótulos de confidencialidade para o Teams, a próxima etapa é criar o rótulo.</span><span class="sxs-lookup"><span data-stu-id="c386e-129">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="c386e-130">Para criar um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="c386e-130">To create a sensitivity label</span></span>
1. <span data-ttu-id="c386e-131">Abra o [Centro de conformidade do Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c386e-131">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="c386e-132">Em **Soluções**, clique em **Proteção de informações**.</span><span class="sxs-lookup"><span data-stu-id="c386e-132">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="c386e-133">Clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="c386e-133">Click **Create a label**.</span></span>
4. <span data-ttu-id="c386e-134">Dê um nome ao rótulo.</span><span class="sxs-lookup"><span data-stu-id="c386e-134">Give the label a name.</span></span> <span data-ttu-id="c386e-135">Sugerimos **Confidencial**, mas você pode escolher um nome diferente se esse já estiver em uso.</span><span class="sxs-lookup"><span data-stu-id="c386e-135">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="c386e-136">Adicione um nome de exibição e uma descrição e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-136">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="c386e-137">Na página **Definir o escopo para este rótulo**, selecione **Arquivos e emails** e **Grupos e sites** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-137">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="c386e-138">Na página **Escolher configurações de proteção para arquivos e emails**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-138">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="c386e-139">Na página \*Rotulagem automática para arquivos e emails\*\*, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-139">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="c386e-140">Na página **Definir configurações de proteção para grupos e sites**, selecione **Configurações de privacidade e acesso de usuário externo** e **Configurações de acesso ao dispositivo e compartilhamento externo** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-140">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="c386e-141">Na página **Definir privacidade e configurações de acesso de usuário externo**, em **Privacidade**, selecione a opção **Privado**.</span><span class="sxs-lookup"><span data-stu-id="c386e-141">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="c386e-142">Se desejar permitir o acesso de convidado, em **Acesso de usuário externo**, selecione **Permitir que proprietários do Grupo Microsoft 365 adicionem pessoas de fora de sua organização ao grupo como convidados**.</span><span class="sxs-lookup"><span data-stu-id="c386e-142">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="c386e-143">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-143">Click **Next**.</span></span>
13. <span data-ttu-id="c386e-144">Na página **Definir compartilhamento externo e configurações de acesso ao dispositivo**, selecione **Controlar compartilhamento externo de sites rotulados do Microsoft Office SharePoint Online**.</span><span class="sxs-lookup"><span data-stu-id="c386e-144">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="c386e-145">Em **O conteúdo pode ser compartilhado com**, escolha **Convidados novos e existentes** se estiver permitindo o acesso de convidado ou **Somente as pessoas em sua organização** se não.</span><span class="sxs-lookup"><span data-stu-id="c386e-145">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="c386e-146">Em **Acesso de dispositivos não gerenciados**, escolha **Permitir acesso limitado apenas à web**.</span><span class="sxs-lookup"><span data-stu-id="c386e-146">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="c386e-147">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-147">Click **Next**.</span></span>
17. <span data-ttu-id="c386e-148">Na página **Rotulagem automática para colunas do banco de dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-148">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="c386e-149">Clique em **Criar rótulo** e, a seguir, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="c386e-149">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="c386e-150">Depois de criar o rótulo, você precisará publicá-lo para os usuários que o usarão.</span><span class="sxs-lookup"><span data-stu-id="c386e-150">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="c386e-151">Para proteção confidencial, disponibilizaremos o rótulo para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c386e-151">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="c386e-152">Publique o rótulo no Centro de conformidade do Microsoft 365, na guia **Políticas de rótulo** da página **Proteção de informações**.</span><span class="sxs-lookup"><span data-stu-id="c386e-152">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="c386e-153">Se você possuir uma política que se aplique a todos os usuários, adicione este rótulo a essa política.</span><span class="sxs-lookup"><span data-stu-id="c386e-153">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="c386e-154">Se você precisar criar uma nova política, confira [Publicar rótulos de confidencialidade por meio da criação de uma política de rótulos](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span><span class="sxs-lookup"><span data-stu-id="c386e-154">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="c386e-155">Criar uma equipe</span><span class="sxs-lookup"><span data-stu-id="c386e-155">Create a team</span></span>

<span data-ttu-id="c386e-156">A configuração adicional do cenário altamente confidencial é feita no site do Microsoft Office SharePoint Online associado à equipe; portanto, a próxima etapa é criar uma equipe.</span><span class="sxs-lookup"><span data-stu-id="c386e-156">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="c386e-157">Para criar uma equipe para informações altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="c386e-157">To create a team for sensitive information</span></span>
1. <span data-ttu-id="c386e-158">No Teams, clique em **Equipes** no lado esquerdo do aplicativo e clique em **Criar equipe ou ingressar em uma** na parte inferior da lista de equipes.</span><span class="sxs-lookup"><span data-stu-id="c386e-158">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="c386e-159">Clique em **Criar equipe** (primeiro cartão, canto superior esquerdo).</span><span class="sxs-lookup"><span data-stu-id="c386e-159">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="c386e-160">Escolha **Criar uma equipe do zero**.</span><span class="sxs-lookup"><span data-stu-id="c386e-160">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="c386e-161">Na lista **Confidencialidade**, escolha o rótulo **Altamente confidencial** que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="c386e-161">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="c386e-162">Em **Privacidade**, clique em **Privado**.</span><span class="sxs-lookup"><span data-stu-id="c386e-162">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="c386e-163">Digite um nome para a equipe e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-163">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="c386e-164">Adicione usuários à equipe e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-164">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="c386e-165">Configurações de canal privado</span><span class="sxs-lookup"><span data-stu-id="c386e-165">Private channel settings</span></span>

<span data-ttu-id="c386e-166">Nesta camada, restringimos a criação de canais privados os proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="c386e-166">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="c386e-167">Para restringir a criação de canais privados</span><span class="sxs-lookup"><span data-stu-id="c386e-167">To restrict private channel creation</span></span>
1. <span data-ttu-id="c386e-168">Na equipe, clique em **Mais opções** e em **Gerenciar equipe**.</span><span class="sxs-lookup"><span data-stu-id="c386e-168">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="c386e-169">Na guia **Configurações**, expanda **Permissões de membro**.</span><span class="sxs-lookup"><span data-stu-id="c386e-169">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="c386e-170">Desmarque a caixa de seleção **Permitir que os membros criem canais privados**.</span><span class="sxs-lookup"><span data-stu-id="c386e-170">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="c386e-171">Você também pode usar [políticas de equipes](/MicrosoftTeams/teams-policies) para controlar quem pode criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="c386e-171">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="c386e-172">Configurações do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c386e-172">SharePoint settings</span></span>

<span data-ttu-id="c386e-173">Sempre que você cria uma nova equipe com o rótulo altamente confidencial, há duas etapas a serem executadas no Microsoft Office SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c386e-173">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="c386e-174">Atualize as configurações de compartilhamento do site no Centro de administração do SharePoint para atualizar o link padrão de compartilhamento para *Pessoas específicas*.</span><span class="sxs-lookup"><span data-stu-id="c386e-174">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="c386e-175">Atualize as configurações de compartilhamento do site no próprio site para impedir que os membros compartilhem o site.</span><span class="sxs-lookup"><span data-stu-id="c386e-175">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="c386e-176">Configurações de link de compartilhamento padrão do site</span><span class="sxs-lookup"><span data-stu-id="c386e-176">Site default sharing link settings</span></span>

<span data-ttu-id="c386e-177">Para atualizar o tipo de link de compartilhamento padrão do site</span><span class="sxs-lookup"><span data-stu-id="c386e-177">To update the site default sharing link type</span></span>

1. <span data-ttu-id="c386e-178">Abra o [Centro de Administração do SharePoint Online](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="c386e-178">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="c386e-179">Em **Sites**, clique em **Sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="c386e-179">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="c386e-180">Clique no site associado à equipe.</span><span class="sxs-lookup"><span data-stu-id="c386e-180">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="c386e-181">Na guia **Políticas**, em **Compartilhamento externo**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-181">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="c386e-182">Em tipo de link de compartilhamento padrão, desmarque a caixa de seleção **igual ao nível da organização** e selecione **pessoas específicas (somente as pessoas que o usuário especificar)**.</span><span class="sxs-lookup"><span data-stu-id="c386e-182">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="c386e-183">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-183">Click **Save**.</span></span>

<span data-ttu-id="c386e-184">Se deseja criar um script como parte do processo de criação de equipe, você poderá usar o [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) com o `-DefaultSharingLinkType Direct` parâmetro para alterar o link de compartilhamento padrão para *Pessoas específicas*.</span><span class="sxs-lookup"><span data-stu-id="c386e-184">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="c386e-185">Canais privados</span><span class="sxs-lookup"><span data-stu-id="c386e-185">Private channels</span></span>

<span data-ttu-id="c386e-186">Se você adicionar canais privados à equipe, cada canal privado criará um novo site do Microsoft Office SharePoint Online com as configurações de compartilhamento padrão.</span><span class="sxs-lookup"><span data-stu-id="c386e-186">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="c386e-187">Estes sites não estão visíveis no Centro de Administração do SharePoint Online; portanto, você deve usar o cmdlet Set-SPOSite do Windows PowerShell para atualizar as configurações de compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="c386e-187">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="c386e-188">Configurações de compartilhamento de site</span><span class="sxs-lookup"><span data-stu-id="c386e-188">Site sharing settings</span></span>

<span data-ttu-id="c386e-189">Para ajudar a garantir que o site do Microsoft Office SharePoint Online não seja compartilhado com pessoas que não sejam membros da equipe, limitamos esse compartilhamento aos proprietários.</span><span class="sxs-lookup"><span data-stu-id="c386e-189">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="c386e-190">Para configurar o compartilhamento de site somente para proprietários</span><span class="sxs-lookup"><span data-stu-id="c386e-190">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="c386e-191">No Teams, navegue até a guia **Geral** da equipe que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="c386e-191">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="c386e-192">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="c386e-192">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="c386e-193">Clique nas reticências e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c386e-193">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="c386e-194">Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="c386e-194">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="c386e-195">No painel **Permissões do site**, em **Compartilhamento do site**, clique em **Alterar como os membros podem compartilhar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-195">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="c386e-196">Em **Compartilhar permissões**, escolha **Proprietários de membros do site e pessoas com permissões de edição podem compartilhar arquivos e pastas, mas apenas os proprietários do site podem compartilhar o site** e em seguida clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c386e-196">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="c386e-197">Confira também</span><span class="sxs-lookup"><span data-stu-id="c386e-197">See Also</span></span>

[<span data-ttu-id="c386e-198">Criar e configurar rótulos de confidencialidade e suas políticas</span><span class="sxs-lookup"><span data-stu-id="c386e-198">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
