---
title: Crie uma extranet B2B com convidados gerenciados
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- M365solutions
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
description: Saiba como criar um site de extranet B2B ou uma equipe com usuários convidados gerenciados de uma organização de parceiro.
ms.openlocfilehash: f01a558d55f497952494676f0148a1e3e4f06b35
ms.sourcegitcommit: b18949de721c6eef3521d5f8286d9b926ad4aabe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44342525"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="e0c9f-103">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="e0c9f-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="e0c9f-104">Você pode usar o [Gerenciamento de direitos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) para criar uma extranet B2B para colaborar com uma organização parceira que usa o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-104">You can use [Azure Active Directory Entitlement Management](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="e0c9f-105">Isso permite que os usuários se autoregistrem no site da extranet ou na equipe e recebam acesso por meio de um fluxo de trabalho de aprovação.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="e0c9f-106">Com esse método de compartilhamento de recursos para colaboração, a organização de parceiros pode ajudar a manter e aprovar os usuários convidados em suas finalidades, reduzindo a carga no departamento de ti e permitindo que eles sejam mais familiarizados com o contrato de colaboração para gerenciar o acesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guest users on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="e0c9f-107">Este artigo percorre as etapas para criar um pacote de recursos (neste caso, um site ou uma equipe) que você pode compartilhar com uma organização de parceiro por meio de um modelo de registro de acesso de autoatendimento.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="e0c9f-108">Antes de começar, crie o site ou a equipe que você deseja compartilhar com a organização do parceiro e habilite-o para o compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="e0c9f-109">Consulte [colaborar com convidados em um site](collaborate-in-site.md) ou [colaborar com convidados em uma equipe](collaborate-as-team.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="e0c9f-110">Recomendamos também que você revise [criar um ambiente de compartilhamento de convidados seguro](create-secure-guest-sharing-environment.md) para obter informações sobre os recursos de segurança e conformidade que você pode usar para ajudar a manter suas políticas de governança ao colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="e0c9f-111">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="e0c9f-111">Video demonstration</span></span>

<span data-ttu-id="e0c9f-112">Este vídeo demonstra os procedimentos abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-112">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="e0c9f-113">Conectar a organização de parceiro</span><span class="sxs-lookup"><span data-stu-id="e0c9f-113">Connect the partner organization</span></span>

<span data-ttu-id="e0c9f-114">Para convidar convidados de uma organização de parceiro, você precisa adicionar o domínio do parceiro como uma organização conectada no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-114">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="e0c9f-115">Para adicionar uma organização conectada</span><span class="sxs-lookup"><span data-stu-id="e0c9f-115">To add a connected organization</span></span>
1. <span data-ttu-id="e0c9f-116">No [Azure Active Directory](https://aad.portal.azure.com), clique em **governança de identidade**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-116">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="e0c9f-117">Clique em **organizações conectadas**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-117">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="e0c9f-118">Clique em **Adicionar organização conectada**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-118">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="e0c9f-119">Digite um nome e uma descrição para a organização e clique em **Avançar: diretório + domínio**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-119">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="e0c9f-120">Clique em **Adicionar diretório + domínio**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-120">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="e0c9f-121">Digite o domínio da organização que você deseja conectar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-121">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="e0c9f-122">Clique em **conectar**e, em seguida, clique em **Avançar: patrocinadores**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-122">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="e0c9f-123">Adicione pessoas da sua organização ou da organização à qual você está se conectando para quem deseja aprovar o acesso para usuários convidados.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-123">Add people from your organization or the organization that you're connecting to who you want to approve access for guest users.</span></span>
10. <span data-ttu-id="e0c9f-124">Clique em **Avançar: revisar + criar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-124">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="e0c9f-125">Revise as configurações escolhidas e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-125">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Captura de tela da página de organizações conectadas no Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="e0c9f-127">Escolha os recursos para compartilhar</span><span class="sxs-lookup"><span data-stu-id="e0c9f-127">Choose the resources to share</span></span>

<span data-ttu-id="e0c9f-128">A primeira etapa na seleção de recursos para compartilhar com uma organização parceira é criar um catálogo para contê-los.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-128">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="e0c9f-129">Para criar um catálogo</span><span class="sxs-lookup"><span data-stu-id="e0c9f-129">To create a catalog</span></span>
1. <span data-ttu-id="e0c9f-130">No [Azure Active Directory](https://aad.portal.azure.com), clique em **governança de identidade**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-130">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="e0c9f-131">Clique em **catálogos**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-131">Click **Catalogs**.</span></span>
3. <span data-ttu-id="e0c9f-132">Clique em **novo catálogo**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-132">Click **New catalog**.</span></span>
4. <span data-ttu-id="e0c9f-133">Digite um nome e uma descrição para o catálogo e verifique se **habilitado** e **habilitado para usuários externos** estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-133">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="e0c9f-134">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-134">Click **Create**.</span></span>

   ![Captura de tela da página catálogos na governança de identidade do Azure Active Directory](../media/identity-governance-catalogs.png)

<span data-ttu-id="e0c9f-136">Depois que o catálogo tiver sido criado, adicione o site do SharePoint ou a equipe que você deseja compartilhar com a organização do parceiro.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-136">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="e0c9f-137">Para adicionar recursos a um catálogo</span><span class="sxs-lookup"><span data-stu-id="e0c9f-137">To add resources to a catalog</span></span>
1. <span data-ttu-id="e0c9f-138">No Azure AD Identity Governance, clique em **catálogos**e, em seguida, clique no catálogo onde você deseja adicionar recursos.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-138">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="e0c9f-139">Clique em **recursos** e em **Adicionar recursos**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-139">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="e0c9f-140">Selecione as equipes ou os sites do SharePoint que você deseja incluir na extranet e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-140">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Captura de tela da página de recursos do catálogo no Azure Active Directory Identity Governance](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="e0c9f-142">Depois de definir os recursos que você deseja compartilhar, a próxima etapa é criar um pacote de acesso, que define o tipo de acesso que os usuários parceiros recebem e o processo de aprovação para novos usuários parceiros que solicitarem o acesso.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-142">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="e0c9f-143">Para criar um pacote de acesso</span><span class="sxs-lookup"><span data-stu-id="e0c9f-143">To create an access package</span></span>
1. <span data-ttu-id="e0c9f-144">No Azure AD Identity Governance, clique em **catálogos**e, em seguida, clique no catálogo onde você deseja criar um pacote do Access.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-144">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="e0c9f-145">Clique em **pacotes do Access**e, em seguida, clique em **novo pacote do Access**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-145">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="e0c9f-146">Digite um nome e uma descrição para o pacote do Access e, em seguida, clique em **Avançar: funções de recurso**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-146">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="e0c9f-147">Escolha os recursos do catálogo que você deseja usar para a extranet.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-147">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="e0c9f-148">Para cada recurso, na coluna **função** , escolha a função de usuário que você deseja conceder aos usuários convidados que usam a extranet.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-148">For each resource, in the **Role** column, choose the user role you want to grant to the guest users who use the extranet.</span></span>
6. <span data-ttu-id="e0c9f-149">Clique em **Avançar: solicitações**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-149">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="e0c9f-150">Em **usuários que podem solicitar acesso**, escolha **os usuários que não estão no diretório**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-150">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="e0c9f-151">Certifique-se de que a opção **específico organizações conectadas** esteja selecionada e clique em **adicionar diretórios**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-151">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="e0c9f-152">Escolha a organização conectada que você adicionou anteriormente e clique em **selecionar**</span><span class="sxs-lookup"><span data-stu-id="e0c9f-152">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="e0c9f-153">Em **aprovação**, escolha **Sim** para **exigir aprovação**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-153">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="e0c9f-154">Em **primeiro aprovador**, escolha um dos patrocinadores que você adicionou anteriormente ou escolha um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-154">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="e0c9f-155">Clique em **Adicionar fallback** e selecione um Aprovador de fallback.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-155">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="e0c9f-156">Em **habilitar**, escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-156">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="e0c9f-157">Clique em **Avançar: ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-157">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="e0c9f-158">Escolha as configurações de análise de validade e acesso que você deseja usar e clique em **Avançar: revisar + criar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-158">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="e0c9f-159">Revise suas configurações e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-159">Review your settings, and then click **Create**.</span></span>

    ![Captura de tela da tela pacotes de acesso no controle de identidade do Azure Active Directory](../media/identity-governance-access-packages.png)

<span data-ttu-id="e0c9f-161">Se você estiver fazendo parcerias com uma organização de grande porte, talvez queira ocultar o pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-161">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="e0c9f-162">Se o pacote estiver oculto, os usuários na organização do parceiro não verão o pacote no meu portal do *meu acesso* .</span><span class="sxs-lookup"><span data-stu-id="e0c9f-162">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="e0c9f-163">Em vez disso, eles devem receber um link direto para inscrever-se no pacote.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-163">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="e0c9f-164">Ocultar o pacote do Access pode reduzir o número de solicitações de acesso inadequadas e também pode ajudar a manter os pacotes de acesso disponíveis organizados no portal da organização do parceiro.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-164">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="e0c9f-165">Para definir um pacote do Access para oculto</span><span class="sxs-lookup"><span data-stu-id="e0c9f-165">To set an access package to hidden</span></span>
1. <span data-ttu-id="e0c9f-166">No Azure AD Identity Governance, clique em **pacotes do Access**e, em seguida, clique em seu pacote do Access.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-166">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="e0c9f-167">Na página **visão geral** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-167">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="e0c9f-168">Em **Propriedades**, escolha **Sim** para **oculto**e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-168">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Captura de tela de uma tela Editar propriedades do pacote de acesso](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="e0c9f-170">Convidar usuários parceiros</span><span class="sxs-lookup"><span data-stu-id="e0c9f-170">Invite partner users</span></span>

<span data-ttu-id="e0c9f-171">Se você definir o pacote do Access para oculto, precisará enviar um link direto para a organização do parceiro para que eles possam solicitar acesso ao seu site ou equipe.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-171">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="e0c9f-172">Para localizar o link do portal de acesso</span><span class="sxs-lookup"><span data-stu-id="e0c9f-172">To find the access portal link</span></span>
1. <span data-ttu-id="e0c9f-173">No Azure AD Identity Governance, clique em **pacotes do Access**e, em seguida, clique em seu pacote do Access.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-173">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="e0c9f-174">Na página **visão geral** , clique em **copiar para** o link da área de transferência para o **link meu portal de acesso**.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-174">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Captura de tela das propriedades do pacote do Access com link do portal do Access](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="e0c9f-176">Depois de copiar o link, você poderá compartilhá-lo com seu contato na organização parceira e ele poderá enviá-lo aos usuários em sua equipe de colaboração.</span><span class="sxs-lookup"><span data-stu-id="e0c9f-176">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0c9f-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="e0c9f-177">See Also</span></span>

[<span data-ttu-id="e0c9f-178">Criar um ambiente seguro de compartilhamento para convidados</span><span class="sxs-lookup"><span data-stu-id="e0c9f-178">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

