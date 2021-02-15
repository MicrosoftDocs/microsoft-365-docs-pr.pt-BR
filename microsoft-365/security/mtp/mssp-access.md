---
title: Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365
description: Saiba mais sobre as alterações da Central de Segurança do Microsoft Defender para a central de segurança do Microsoft 365
keywords: Getting started with the Microsoft 365 security center, OATP, MDATP, MDO, MDE, single pane of glass, converged portal, security portal, defender security portal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242923"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="56ebb-104">Fornecer acesso ao provedor de serviços de segurança gerenciado (MSSP)</span><span class="sxs-lookup"><span data-stu-id="56ebb-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="56ebb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="56ebb-105">**Applies to:**</span></span>

- [<span data-ttu-id="56ebb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56ebb-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="56ebb-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="56ebb-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="56ebb-108">Para implementar uma solução de acesso delegado de vários locatários, tome as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="56ebb-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="56ebb-109">Habilita o controle de acesso baseado em função no Defender para o ponto de extremidade no centro de segurança do Microsoft 365 e [conecte-se](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) aos grupos do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="56ebb-109">Enable [role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="56ebb-110">Configurar [Pacotes de Acesso de Governança](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) para solicitação de acesso e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="56ebb-110">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="56ebb-111">Gerenciar solicitações de acesso e auditorias [no Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="56ebb-111">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="56ebb-112">Habilitar controles de acesso baseados em função no Microsoft Defender para o ponto de extremidade no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56ebb-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="56ebb-113">**Criar grupos de acesso para recursos MSSP no AAD do Cliente: Grupos**</span><span class="sxs-lookup"><span data-stu-id="56ebb-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="56ebb-114">Esses grupos serão vinculados às Funções que você criar no Defender para o Ponto de Extremidade na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56ebb-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="56ebb-115">Para fazer isso, no locatário do AD do cliente, crie três grupos.</span><span class="sxs-lookup"><span data-stu-id="56ebb-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="56ebb-116">Na nossa abordagem de exemplo, criamos os seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="56ebb-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="56ebb-117">Analista de Nível 1</span><span class="sxs-lookup"><span data-stu-id="56ebb-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="56ebb-118">Analista de Nível 2</span><span class="sxs-lookup"><span data-stu-id="56ebb-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="56ebb-119">Aprovadores de analista do MSSP</span><span class="sxs-lookup"><span data-stu-id="56ebb-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="56ebb-120">Crie funções do Defender para o Ponto de Extremidade para níveis de acesso apropriados no Customer Defender para o Ponto de Extremidade nas funções e grupos da central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56ebb-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="56ebb-121">Para habilitar o RBAC no centro de segurança do Microsoft 365 do cliente, acesse permissões > Funções de pontos de extremidade & grupos **> Funções** com uma conta de usuário com direitos de Administrador Global ou Administrador de Segurança.</span><span class="sxs-lookup"><span data-stu-id="56ebb-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Imagem de acesso MSSP](../../media/mssp-access.png)

    <span data-ttu-id="56ebb-123">Em seguida, crie funções do RBAC para atender às necessidades de camada SOC do MSSP.</span><span class="sxs-lookup"><span data-stu-id="56ebb-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="56ebb-124">Vincule essas funções aos grupos de usuários criados por meio de "Grupos de usuários atribuídos".</span><span class="sxs-lookup"><span data-stu-id="56ebb-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="56ebb-125">Duas funções possíveis:</span><span class="sxs-lookup"><span data-stu-id="56ebb-125">Two possible roles:</span></span>

    - <span data-ttu-id="56ebb-126">**Nível 1 Analistas**</span><span class="sxs-lookup"><span data-stu-id="56ebb-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="56ebb-127">Execute todas as ações, exceto a resposta ao vivo e gerencie as configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="56ebb-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="56ebb-128">**Analistas de Nível 2**</span><span class="sxs-lookup"><span data-stu-id="56ebb-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="56ebb-129">Recursos do Nível 1 com a adição à [resposta ao vivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="56ebb-129">Tier 1 capabilities with the addition to [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="56ebb-130">Para obter mais informações, [consulte Usar controle de acesso baseado em função.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="56ebb-130">For more information, see [Use role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="56ebb-131">Configurar pacotes de acesso de governança</span><span class="sxs-lookup"><span data-stu-id="56ebb-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="56ebb-132">**Adicionar MSSP como Organização Conectada no AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="56ebb-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="56ebb-133">Adicionar o MSSP como uma organização conectada permitirá que o MSSP solicite e tenha acessos provisionados.</span><span class="sxs-lookup"><span data-stu-id="56ebb-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="56ebb-134">Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: organização conectada.</span><span class="sxs-lookup"><span data-stu-id="56ebb-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="56ebb-135">Adicione uma nova organização e pesquise seu locatário de analista MSSP por meio da ID de locatário ou domínio.</span><span class="sxs-lookup"><span data-stu-id="56ebb-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="56ebb-136">Sugerimos a criação de um locatário do AD separado para os analistas do MSSP.</span><span class="sxs-lookup"><span data-stu-id="56ebb-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="56ebb-137">**Criar um catálogo de recursos no AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="56ebb-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="56ebb-138">Catálogos de recursos são uma coleção lógica de pacotes de acesso, criada no locatário do AD do cliente.</span><span class="sxs-lookup"><span data-stu-id="56ebb-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="56ebb-139">Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Catálogos e adicione **Novo Catálogo.**</span><span class="sxs-lookup"><span data-stu-id="56ebb-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="56ebb-140">No nosso exemplo, vamos chamá-lo **de MSSP Accesses**.</span><span class="sxs-lookup"><span data-stu-id="56ebb-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Imagem do novo catálogo](../../media/goverance-catalog.png)

    <span data-ttu-id="56ebb-142">Mais informações, consulte [Criar um catálogo de recursos.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="56ebb-142">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="56ebb-143">**Criar pacotes de acesso para recursos MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="56ebb-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="56ebb-144">Pacotes de acesso são o conjunto de direitos e acessos que um solicitante receberá mediante aprovação.</span><span class="sxs-lookup"><span data-stu-id="56ebb-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="56ebb-145">Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Pacotes do Access e adicione **Novo Pacote de Acesso.**</span><span class="sxs-lookup"><span data-stu-id="56ebb-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="56ebb-146">Crie um pacote de acesso para os aprovadores do MSSP e para cada camada de analista.</span><span class="sxs-lookup"><span data-stu-id="56ebb-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="56ebb-147">Por exemplo, a seguinte configuração de Analista de Nível 1 cria um pacote de acesso que:</span><span class="sxs-lookup"><span data-stu-id="56ebb-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="56ebb-148">Requer um membro do grupo AD **MSSP Analista Aprovadores** para autorizar novas solicitações</span><span class="sxs-lookup"><span data-stu-id="56ebb-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="56ebb-149">Tem revisões de acesso anual, onde os analistas do SOC podem solicitar uma extensão de acesso</span><span class="sxs-lookup"><span data-stu-id="56ebb-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="56ebb-150">Só pode ser solicitado por usuários no locatário SOC do MSSP</span><span class="sxs-lookup"><span data-stu-id="56ebb-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="56ebb-151">O Access expira automaticamente após 365 dias</span><span class="sxs-lookup"><span data-stu-id="56ebb-151">Access auto expires after 365 days</span></span>

    ![Imagem do novo pacote de acesso](../../media/new-access-package.png)

    <span data-ttu-id="56ebb-153">Para obter mais informações, [consulte Criar um novo pacote de acesso.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="56ebb-153">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="56ebb-154">**Fornecer um link de solicitação de acesso aos recursos MSSP do AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="56ebb-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="56ebb-155">O link do portal Meu Acesso é usado por analistas de SOC do MSSP para solicitar acesso por meio dos pacotes de acesso criados.</span><span class="sxs-lookup"><span data-stu-id="56ebb-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="56ebb-156">O link é durável, o que significa que o mesmo link pode ser usado ao longo do tempo para novos analistas.</span><span class="sxs-lookup"><span data-stu-id="56ebb-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="56ebb-157">A solicitação de analista entra em uma fila para aprovação dos aprovadores de **analista do MSSP.**</span><span class="sxs-lookup"><span data-stu-id="56ebb-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Imagem das propriedades de acesso](../../media/access-properties.png)

    <span data-ttu-id="56ebb-159">O link está localizado na página de visão geral de cada pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="56ebb-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="56ebb-160">Gerenciar Acesso</span><span class="sxs-lookup"><span data-stu-id="56ebb-160">Manage access</span></span> 

1. <span data-ttu-id="56ebb-161">Revise e autorize solicitações de acesso no myaccess cliente e/ou MSSP.</span><span class="sxs-lookup"><span data-stu-id="56ebb-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="56ebb-162">As solicitações de acesso são gerenciadas no cliente Meu Acesso, por membros do grupo Aprovadores de Analista do MSSP.</span><span class="sxs-lookup"><span data-stu-id="56ebb-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="56ebb-163">Para fazer isso, acesse myaccess do cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="56ebb-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="56ebb-164">Exemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="56ebb-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="56ebb-165">Aprovar ou negar solicitações na **seção Aprovações** da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="56ebb-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="56ebb-166">Neste ponto, o acesso do analista foi provisionado, e cada analista deve poder acessar a Central de Segurança do Microsoft 365 do cliente:</span><span class="sxs-lookup"><span data-stu-id="56ebb-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="56ebb-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` com as permissões e funções que foram atribuídas.</span><span class="sxs-lookup"><span data-stu-id="56ebb-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56ebb-168">O acesso delegado ao Microsoft Defender para Ponto de Extremidade no centro de segurança do Microsoft 365 atualmente permite o acesso a um único locatário por janela do navegador.</span><span class="sxs-lookup"><span data-stu-id="56ebb-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span> 