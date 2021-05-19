---
title: Crie uma extranet B2B com convidados gerenciados
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Normal
f1.keywords: NOCSH
recommendations: false
description: Saiba como criar um site de extranet B2B ou uma equipe com convidados gerenciados de uma organização parceira.
ms.openlocfilehash: d76951da5d8affa1dac08cbdc68a91329ca069ed
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538238"
---
# <a name="create-a-b2b-extranet-with-managed-guests"></a><span data-ttu-id="70be9-103">Crie uma extranet B2B com convidados gerenciados</span><span class="sxs-lookup"><span data-stu-id="70be9-103">Create a B2B extranet with managed guests</span></span>

<span data-ttu-id="70be9-104">Você pode usar [Azure Active Directory Gerenciamento](/azure/active-directory/governance/entitlement-management-overview) de Direitos para criar uma extranet B2B para colaborar com uma organização parceira que usa Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70be9-104">You can use [Azure Active Directory Entitlement Management](/azure/active-directory/governance/entitlement-management-overview) to create a B2B extranet to collaborate with a partner organization that uses Azure Active Directory.</span></span> <span data-ttu-id="70be9-105">Isso permite que os usuários se inscrevam no site ou equipe da extranet e recebam acesso por meio de um fluxo de trabalho de aprovação.</span><span class="sxs-lookup"><span data-stu-id="70be9-105">This allows users to self-enroll in the extranet site or team and receive access via an approval workflow.</span></span>

<span data-ttu-id="70be9-106">Com esse método de compartilhamento de recursos para colaboração, a organização do parceiro pode ajudar a manter e aprovar os convidados em suas extremidades, reduzindo a carga em seu departamento de IT e permitindo que os mais familiarizados com o contrato de colaboração gerenciem o acesso do usuário.</span><span class="sxs-lookup"><span data-stu-id="70be9-106">With this method of sharing resources for collaboration, the partner organization can help maintain and approve the guests on their end, reducing the burden on your IT department and allowing those most familiar with the collaboration agreement to manage user access.</span></span>

<span data-ttu-id="70be9-107">Este artigo percorre as etapas para criar um pacote de recursos (nesse caso, um site ou uma equipe) que você pode compartilhar com uma organização parceira por meio de um modelo de registro de acesso autoatendido.</span><span class="sxs-lookup"><span data-stu-id="70be9-107">This article walks through the steps to create a package of resources (in this case, a site or team) that you can share with a partner organization through a self-service access registration model.</span></span> 

<span data-ttu-id="70be9-108">Antes de começar, crie o site ou a equipe que você deseja compartilhar com a organização do parceiro e habilita-o para compartilhamento de convidados.</span><span class="sxs-lookup"><span data-stu-id="70be9-108">Before you begin, create the site or team that you want to share with the partner organization and enable it for guest sharing.</span></span> <span data-ttu-id="70be9-109">Confira [Colaborar com convidados em um site ou](collaborate-in-site.md) Colaborar com convidados em uma [equipe](collaborate-as-team.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="70be9-109">See [Collaborate with guests in a site](collaborate-in-site.md) or [Collaborate with guests in a team](collaborate-as-team.md) for more information.</span></span> <span data-ttu-id="70be9-110">Também recomendamos que você revise Criar um ambiente de compartilhamento de convidados seguro para obter informações sobre recursos de segurança e conformidade que você pode usar para ajudar [a](create-secure-guest-sharing-environment.md) manter suas políticas de governança ao colaborar com convidados.</span><span class="sxs-lookup"><span data-stu-id="70be9-110">We also recommend that you review [Create a secure guest sharing environment](create-secure-guest-sharing-environment.md) for information about security and compliance features that you can use to help maintain your governance policies when collaborating with guests.</span></span>

## <a name="license-requirements"></a><span data-ttu-id="70be9-111">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="70be9-111">License requirements</span></span>

<span data-ttu-id="70be9-112">Usar esse recurso requer uma licença do Azure AD Premium P2.</span><span class="sxs-lookup"><span data-stu-id="70be9-112">Using this feature requires an Azure AD Premium P2 license.</span></span> 

<span data-ttu-id="70be9-113">Nuvens especializadas, como o Azure Germany e o Azure China 21Vianet, não estão disponíveis no momento para uso.</span><span class="sxs-lookup"><span data-stu-id="70be9-113">Specialized clouds, such as Azure Germany and Azure China 21Vianet, are not currently available for use.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="70be9-114">Demonstração de vídeo</span><span class="sxs-lookup"><span data-stu-id="70be9-114">Video demonstration</span></span>

<span data-ttu-id="70be9-115">Este vídeo demonstra os procedimentos abordados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="70be9-115">This video demonstrates the procedures covered in this article.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wKUj?autoplay=false]

## <a name="connect-the-partner-organization"></a><span data-ttu-id="70be9-116">Conexão a organização do parceiro</span><span class="sxs-lookup"><span data-stu-id="70be9-116">Connect the partner organization</span></span>

<span data-ttu-id="70be9-117">Para convidar convidados de uma organização parceira, você precisa adicionar o domínio do parceiro como uma organização conectada Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70be9-117">In order to invite guests from a partner organization, you need to add the partner's domain as a connected organization in Azure Active Directory.</span></span>

<span data-ttu-id="70be9-118">Para adicionar uma organização conectada</span><span class="sxs-lookup"><span data-stu-id="70be9-118">To add a connected organization</span></span>
1. <span data-ttu-id="70be9-119">Em [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**</span><span class="sxs-lookup"><span data-stu-id="70be9-119">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="70be9-120">Clique **em Organizações Conectadas**.</span><span class="sxs-lookup"><span data-stu-id="70be9-120">Click **Connected organizations**.</span></span>
4. <span data-ttu-id="70be9-121">Clique **em Adicionar organização conectada.**</span><span class="sxs-lookup"><span data-stu-id="70be9-121">Click **Add connected organization**.</span></span>
5. <span data-ttu-id="70be9-122">Digite um nome e uma descrição para a organização e clique em **Next: Directory + domain**.</span><span class="sxs-lookup"><span data-stu-id="70be9-122">Type a name and description for the organization, and then click **Next: Directory + domain**.</span></span>
6. <span data-ttu-id="70be9-123">Clique **em Adicionar diretório + domínio.**</span><span class="sxs-lookup"><span data-stu-id="70be9-123">Click **Add directory + domain**.</span></span>
7. <span data-ttu-id="70be9-124">Digite o domínio da organização que você deseja conectar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-124">Type the domain for the organization that you want to connect, and then click **Add**.</span></span>
8. <span data-ttu-id="70be9-125">Clique **Conexão** e clique em **Next: Sponsors**.</span><span class="sxs-lookup"><span data-stu-id="70be9-125">Click **Connect**, and then click **Next: Sponsors**.</span></span>
9. <span data-ttu-id="70be9-126">Adicione pessoas da sua organização ou da organização que você está conectando a quem deseja aprovar o acesso aos convidados.</span><span class="sxs-lookup"><span data-stu-id="70be9-126">Add people from your organization or the organization that you're connecting to who you want to approve access for guests.</span></span>
10. <span data-ttu-id="70be9-127">Clique em **Avançar: Analisar + Criar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-127">Click **Next: Review + Create**.</span></span>
11. <span data-ttu-id="70be9-128">Revise as configurações escolhidas e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-128">Review the settings that you've chosen and then click **Create**.</span></span>

    ![Captura de tela da página organizações conectadas Azure Active Directory](../media/identity-governance-connected-organizations.png)

## <a name="choose-the-resources-to-share"></a><span data-ttu-id="70be9-130">Escolha os recursos a compartilhar</span><span class="sxs-lookup"><span data-stu-id="70be9-130">Choose the resources to share</span></span>

<span data-ttu-id="70be9-131">A primeira etapa na seleção de recursos para compartilhar com uma organização parceira é criar um catálogo para contê-los.</span><span class="sxs-lookup"><span data-stu-id="70be9-131">The first step in selecting resources to share with a partner organization is to create a catalog to contain them.</span></span>

<span data-ttu-id="70be9-132">Para criar um catálogo</span><span class="sxs-lookup"><span data-stu-id="70be9-132">To create a catalog</span></span>
1. <span data-ttu-id="70be9-133">Em [Azure Active Directory,](https://aad.portal.azure.com)clique em **Governança de Identidade.**</span><span class="sxs-lookup"><span data-stu-id="70be9-133">In [Azure Active Directory](https://aad.portal.azure.com), click **Identity Governance**.</span></span>
2. <span data-ttu-id="70be9-134">Clique **em Catálogos**.</span><span class="sxs-lookup"><span data-stu-id="70be9-134">Click **Catalogs**.</span></span>
3. <span data-ttu-id="70be9-135">Clique **em Novo catálogo**.</span><span class="sxs-lookup"><span data-stu-id="70be9-135">Click **New catalog**.</span></span>
4. <span data-ttu-id="70be9-136">Digite um nome e uma descrição para  o catálogo e verifique se **Habilitado** e Habilitado para usuários externos estão definidos como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="70be9-136">Type a name and description for the catalog and ensure that **Enabled** and **Enabled for external users** are both set to **Yes**.</span></span>
5. <span data-ttu-id="70be9-137">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-137">Click **Create**.</span></span>

   ![Captura de tela da página catálogos em Azure Active Directory Identity Governance](../media/identity-governance-catalogs.png)

<span data-ttu-id="70be9-139">Depois que o catálogo tiver sido criado, você adicionará o site SharePoint ou a equipe que deseja compartilhar com a organização do parceiro.</span><span class="sxs-lookup"><span data-stu-id="70be9-139">Once the catalog has been created, you add the SharePoint site or team that you want to share with the partner organization.</span></span>

<span data-ttu-id="70be9-140">Para adicionar recursos a um catálogo</span><span class="sxs-lookup"><span data-stu-id="70be9-140">To add resources to a catalog</span></span>
1. <span data-ttu-id="70be9-141">No Azure AD Identity Governance, clique em **Catálogos** e clique no catálogo onde você deseja adicionar recursos.</span><span class="sxs-lookup"><span data-stu-id="70be9-141">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to add resources.</span></span>
2. <span data-ttu-id="70be9-142">Clique **em Recursos** e clique em Adicionar **recursos.**</span><span class="sxs-lookup"><span data-stu-id="70be9-142">Click **Resources** and then click **Add resources**.</span></span>
3. <span data-ttu-id="70be9-143">Selecione as equipes ou SharePoint sites que você deseja incluir em sua extranet e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-143">Select the teams or SharePoint sites that you want to include in your extranet, and then click **Add**.</span></span>

   ![Captura de tela da página de recursos do catálogo Azure Active Directory Governança de Identidade](../media/identity-governance-catalog-resource.png)

<span data-ttu-id="70be9-145">Depois de definir os recursos que você deseja compartilhar, a próxima etapa é criar um pacote de acesso, que define o tipo de acesso que os usuários parceiros são concedidos e o processo de aprovação para novos usuários parceiros solicitando acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-145">Once you've defined the resources that you want to share, the next step is to create an access package, which defines the type of access that partner users are granted and the approval process for new partner users requesting access.</span></span>

<span data-ttu-id="70be9-146">Para criar um pacote de acesso</span><span class="sxs-lookup"><span data-stu-id="70be9-146">To create an access package</span></span>
1. <span data-ttu-id="70be9-147">No Azure AD Identity Governance, clique em **Catálogos** e, em seguida, clique no catálogo onde você deseja criar um pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-147">In Azure AD Identity Governance, click **Catalogs**, and then click the catalog where you want to create an access package.</span></span>
2. <span data-ttu-id="70be9-148">Clique **em Acessar pacotes** e clique em Novo pacote de **acesso.**</span><span class="sxs-lookup"><span data-stu-id="70be9-148">Click **Access packages**, and then click **New access package**.</span></span>
3. <span data-ttu-id="70be9-149">Digite um nome e uma descrição para o pacote de acesso e clique em **Next: Resource roles**.</span><span class="sxs-lookup"><span data-stu-id="70be9-149">Type a name and description for the access package, and then click **Next: Resource roles**.</span></span>
4. <span data-ttu-id="70be9-150">Escolha os recursos do catálogo que você deseja usar para sua extranet.</span><span class="sxs-lookup"><span data-stu-id="70be9-150">Choose the resources from the catalog that you want to use for your extranet.</span></span>
5. <span data-ttu-id="70be9-151">Para cada recurso, na coluna **Função,** escolha a função de usuário que você deseja conceder aos convidados que usam a extranet.</span><span class="sxs-lookup"><span data-stu-id="70be9-151">For each resource, in the **Role** column, choose the user role you want to grant to the guests who use the extranet.</span></span>
6. <span data-ttu-id="70be9-152">Clique **em Próximo: Solicitações**.</span><span class="sxs-lookup"><span data-stu-id="70be9-152">Click **Next: Requests**.</span></span>
7. <span data-ttu-id="70be9-153">Em **Usuários que podem solicitar acesso,** escolha Para usuários que não estão em seu **diretório**.</span><span class="sxs-lookup"><span data-stu-id="70be9-153">Under **Users who can request access**, choose **For users not in your directory**.</span></span>
8. <span data-ttu-id="70be9-154">Verifique se a **opção Organizações Conectadas** Específicas está selecionada e clique em **Adicionar diretórios**.</span><span class="sxs-lookup"><span data-stu-id="70be9-154">Ensure that the **Specific connected organizations** option is selected, and then click **Add directories**.</span></span>
9. <span data-ttu-id="70be9-155">Escolha a organização conectada que você adicionar anteriormente e clique em **Selecionar**</span><span class="sxs-lookup"><span data-stu-id="70be9-155">Choose the connected organization that you add earlier, and then click **Select**</span></span>
10. <span data-ttu-id="70be9-156">Em **Aprovação**, escolha **Sim** para **Exigir aprovação**.</span><span class="sxs-lookup"><span data-stu-id="70be9-156">Under **Approval**, choose **Yes** for **Require approval**.</span></span>
11. <span data-ttu-id="70be9-157">Em **Primeiro aprovador,** escolha um dos patrocinadores que você adicionou anteriormente ou escolha um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="70be9-157">Under **First approver**, choose one of the sponsors that you added earlier or choose a specific user.</span></span>
12. <span data-ttu-id="70be9-158">Clique **em Adicionar fallback** e selecione um aprovador de fallback.</span><span class="sxs-lookup"><span data-stu-id="70be9-158">Click **Add fallback** and select a fallback approver.</span></span>
13. <span data-ttu-id="70be9-159">Em **Habilitar**, escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="70be9-159">Under **Enable**, choose **Yes**.</span></span>
14. <span data-ttu-id="70be9-160">Clique **em Próximo: Ciclo de Vida**.</span><span class="sxs-lookup"><span data-stu-id="70be9-160">Click **Next: Lifecycle**.</span></span>
15. <span data-ttu-id="70be9-161">Escolha as configurações de revisão de expiração e acesso que você deseja usar e clique em **Next: Review + Create**.</span><span class="sxs-lookup"><span data-stu-id="70be9-161">Choose the expiration and access review settings that you want to use, and then click **Next: Review + Create**.</span></span>
16. <span data-ttu-id="70be9-162">Revise suas configurações e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-162">Review your settings, and then click **Create**.</span></span>

    ![Captura de tela da tela de pacotes de acesso Azure Active Directory Governança de Identidade](../media/identity-governance-access-packages.png)

<span data-ttu-id="70be9-164">Se você estiver fazendo parceria com uma organização grande, talvez queira ocultar o pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-164">If you're partnering with a large organization, you may want to hide the access package.</span></span> <span data-ttu-id="70be9-165">Se o pacote estiver oculto, os usuários da organização parceira não verão o pacote em seu portal *do Meu* Acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-165">If the package is hidden, then users in the partner organization will not see the package on their *My Access* portal.</span></span> <span data-ttu-id="70be9-166">Em vez disso, eles devem ser enviados um link direto para se inscrever no pacote.</span><span class="sxs-lookup"><span data-stu-id="70be9-166">Instead, they must be sent a direct link to sign up for the package.</span></span> <span data-ttu-id="70be9-167">Ocultar o pacote de acesso pode reduzir o número de solicitações de acesso inadequadas e também pode ajudar a manter pacotes de acesso disponíveis organizados no portal da organização do parceiro.</span><span class="sxs-lookup"><span data-stu-id="70be9-167">Hiding the access package can reduce the number of inappropriate access requests and can also help keep available access packages organized in the partner organization's portal.</span></span>

<span data-ttu-id="70be9-168">Para definir um pacote de acesso como oculto</span><span class="sxs-lookup"><span data-stu-id="70be9-168">To set an access package to hidden</span></span>
1. <span data-ttu-id="70be9-169">Em Governança de Identidade do Azure AD, clique em **Pacotes de Acesso** e clique em seu pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-169">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="70be9-170">Na página **Visão** Geral, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-170">On the **Overview** page, click **Edit**.</span></span>
3. <span data-ttu-id="70be9-171">Em **Propriedades,** escolha **Sim** para **Oculto** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="70be9-171">Under **Properties**, choose **Yes** for **Hidden**, and then click **Save**.</span></span>

   ![Captura de tela de uma tela editar propriedades do pacote de acesso](../media/identity-governance-access-package-hidden.png)

## <a name="invite-partner-users"></a><span data-ttu-id="70be9-173">Convidar usuários parceiros</span><span class="sxs-lookup"><span data-stu-id="70be9-173">Invite partner users</span></span>

<span data-ttu-id="70be9-174">Se você definir o pacote de acesso como oculto, precisará enviar um link direto para a organização do parceiro para que ele possa solicitar acesso ao seu site ou equipe.</span><span class="sxs-lookup"><span data-stu-id="70be9-174">If you set the access package to hidden, you need to send a direct link to the partner organization so that they can request access to your site or team.</span></span>

<span data-ttu-id="70be9-175">Para encontrar o link do portal de acesso</span><span class="sxs-lookup"><span data-stu-id="70be9-175">To find the access portal link</span></span>
1. <span data-ttu-id="70be9-176">Em Governança de Identidade do Azure AD, clique em **Pacotes de Acesso** e clique em seu pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="70be9-176">In Azure AD Identity Governance, click **Access packages**, and then click your access package.</span></span>
2. <span data-ttu-id="70be9-177">Na página **Visão** Geral, clique em **Copiar para** o link da área de transferência para o link do portal **Meu Acesso.**</span><span class="sxs-lookup"><span data-stu-id="70be9-177">On the **Overview** page, click **Copy to clipboard** link for the **My Access portal link**.</span></span>

   ![Captura de tela das propriedades do pacote de acesso com link do portal de acesso](../media/identity-governance-access-portal-link.png)

<span data-ttu-id="70be9-179">Depois de copiar o link, você pode compartilhá-lo com seu contato na organização do parceiro e eles podem enviá-lo para os usuários em sua equipe de colaboração.</span><span class="sxs-lookup"><span data-stu-id="70be9-179">Once you have copied the link, you can share it with your contact at the partner organization and they can send it to the users on their collaboration team.</span></span>

## <a name="see-also"></a><span data-ttu-id="70be9-180">Confira também</span><span class="sxs-lookup"><span data-stu-id="70be9-180">See Also</span></span>

[<span data-ttu-id="70be9-181">Criar um ambiente de compartilhamento de convidados seguro</span><span class="sxs-lookup"><span data-stu-id="70be9-181">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)