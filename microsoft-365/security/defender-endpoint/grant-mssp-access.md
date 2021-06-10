---
title: Conceder acesso ao provedor de serviços de segurança gerenciado (MSSP)
description: Tomar as etapas necessárias para configurar a integração do MSSP com o Microsoft Defender para Ponto de Extremidade
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
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
ms.openlocfilehash: 311903cdd1409f4ab997641cc842ff199ce2500d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843101"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="cf700-104">Conceder acesso ao MSSP (provedor de serviços de segurança gerenciado) (visualização)</span><span class="sxs-lookup"><span data-stu-id="cf700-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cf700-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cf700-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf700-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf700-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf700-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf700-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="cf700-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cf700-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf700-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf700-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="cf700-110">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="cf700-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cf700-111">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="cf700-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cf700-112">Para implementar uma solução de acesso delegado de vários locatários, tome as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="cf700-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="cf700-113">Habilita o controle de acesso baseado em função no Defender para Ponto de Extremidade e [conecte-se](rbac.md) com grupos do Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="cf700-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="cf700-114">Configurar [Pacotes de Acesso à Governança](/azure/active-directory/governance/identity-governance-overview) para solicitação e provisionamento de acesso.</span><span class="sxs-lookup"><span data-stu-id="cf700-114">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="cf700-115">Gerenciar solicitações e auditorias de acesso no [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="cf700-115">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="cf700-116">Habilitar controles de acesso baseados em função no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf700-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="cf700-117">**Criar grupos de acesso para recursos MSSP no AAD do Cliente: Grupos**</span><span class="sxs-lookup"><span data-stu-id="cf700-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="cf700-118">Esses grupos serão vinculados às Funções que você criar no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="cf700-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="cf700-119">Para fazer isso, no locatário do AD do cliente, crie três grupos.</span><span class="sxs-lookup"><span data-stu-id="cf700-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="cf700-120">Em nossa abordagem de exemplo, criamos os seguintes grupos:</span><span class="sxs-lookup"><span data-stu-id="cf700-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="cf700-121">Analista de Camada 1</span><span class="sxs-lookup"><span data-stu-id="cf700-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="cf700-122">Analista de Camada 2</span><span class="sxs-lookup"><span data-stu-id="cf700-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="cf700-123">Aprovadores do analista MSSP</span><span class="sxs-lookup"><span data-stu-id="cf700-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="cf700-124">Crie funções do Defender para Ponto de Extremidade para níveis de acesso apropriados no Customer Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="cf700-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="cf700-125">Para habilitar o RBAC no cliente Central de Segurança do Microsoft Defender, acesse Configurações > Permissões > **Funções** e "Ativar funções", de uma conta de usuário com direitos de Administrador Global ou Administrador de Segurança.</span><span class="sxs-lookup"><span data-stu-id="cf700-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Imagem do acesso ao MSSP](images/mssp-access.png)

    <span data-ttu-id="cf700-127">Em seguida, crie funções RBAC para atender às necessidades de Camada SOC do MSSP.</span><span class="sxs-lookup"><span data-stu-id="cf700-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="cf700-128">Vincule essas funções aos grupos de usuários criados por meio de "Grupos de usuários atribuídos".</span><span class="sxs-lookup"><span data-stu-id="cf700-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="cf700-129">Duas funções possíveis:</span><span class="sxs-lookup"><span data-stu-id="cf700-129">Two possible roles:</span></span>

    - <span data-ttu-id="cf700-130">**Analistas de Camada 1**</span><span class="sxs-lookup"><span data-stu-id="cf700-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="cf700-131">Execute todas as ações, exceto a resposta ao vivo e gerencie as configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="cf700-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="cf700-132">**Analistas de Camada 2**</span><span class="sxs-lookup"><span data-stu-id="cf700-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="cf700-133">Recursos de camada 1 com a adição à [resposta ao vivo](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="cf700-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="cf700-134">Para obter mais informações, [consulte Use role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="cf700-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="cf700-135">Configurar pacotes de Acesso à Governança</span><span class="sxs-lookup"><span data-stu-id="cf700-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="cf700-136">**Adicionar MSSP como Organização Conectada no AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="cf700-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="cf700-137">Adicionar o MSSP como uma organização conectada permitirá que o MSSP solicite e tenha acessos provisionados.</span><span class="sxs-lookup"><span data-stu-id="cf700-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="cf700-138">Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Organização conectada.</span><span class="sxs-lookup"><span data-stu-id="cf700-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="cf700-139">Adicione uma nova organização e pesquise seu locatário do Analista MSSP por meio da ID do Locatário ou domínio.</span><span class="sxs-lookup"><span data-stu-id="cf700-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="cf700-140">Sugerimos a criação de um locatário AD separado para seus Analistas MSSP.</span><span class="sxs-lookup"><span data-stu-id="cf700-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="cf700-141">**Criar um catálogo de recursos no AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="cf700-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="cf700-142">Catálogos de recursos são uma coleção lógica de pacotes de acesso, criada no locatário do AD do cliente.</span><span class="sxs-lookup"><span data-stu-id="cf700-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="cf700-143">Para fazer isso, no locatário do AD do cliente, acesse a Governança de Identidade: Catálogos e adicione **Novo Catálogo.**</span><span class="sxs-lookup"><span data-stu-id="cf700-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="cf700-144">No nosso exemplo, vamos chamá-lo **de Acessos MSSP.**</span><span class="sxs-lookup"><span data-stu-id="cf700-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Imagem do novo catálogo](images/goverance-catalog.png)

    <span data-ttu-id="cf700-146">Mais informações em [Criar um catálogo de recursos.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="cf700-146">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="cf700-147">**Criar pacotes de acesso para recursos MSSP Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="cf700-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="cf700-148">Pacotes de acesso são a coleção de direitos e acessos que um solicitante será concedido mediante aprovação.</span><span class="sxs-lookup"><span data-stu-id="cf700-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="cf700-149">Para fazer isso, no locatário do AD do cliente, acesse Governança de Identidade: Pacotes de Acesso e **adicione Novo Pacote de Acesso.**</span><span class="sxs-lookup"><span data-stu-id="cf700-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="cf700-150">Crie um pacote de acesso para os aprovadores do MSSP e cada camada de analista.</span><span class="sxs-lookup"><span data-stu-id="cf700-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="cf700-151">Por exemplo, a seguinte configuração de Analista de Camada 1 cria um pacote de acesso que:</span><span class="sxs-lookup"><span data-stu-id="cf700-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="cf700-152">Requer um membro do grupo AD Aprovadores de **Analista MSSP** para autorizar novas solicitações</span><span class="sxs-lookup"><span data-stu-id="cf700-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="cf700-153">Tem avaliações de acesso anual, onde os analistas do SOC podem solicitar uma extensão de acesso</span><span class="sxs-lookup"><span data-stu-id="cf700-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="cf700-154">Só pode ser solicitado por usuários no Locatário SOC do MSSP</span><span class="sxs-lookup"><span data-stu-id="cf700-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="cf700-155">O access auto expira após 365 dias</span><span class="sxs-lookup"><span data-stu-id="cf700-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cf700-156">![Imagem do novo pacote de acesso](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="cf700-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="cf700-157">Para obter mais informações, [consulte Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span><span class="sxs-lookup"><span data-stu-id="cf700-157">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="cf700-158">**Fornecer link de solicitação de acesso aos recursos do MSSP do AAD do Cliente: Governança de Identidade**</span><span class="sxs-lookup"><span data-stu-id="cf700-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="cf700-159">O link do portal Meu Acesso é usado pelos analistas soc do MSSP para solicitar acesso por meio dos pacotes de acesso criados.</span><span class="sxs-lookup"><span data-stu-id="cf700-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="cf700-160">O link é durável, ou seja, o mesmo link pode ser usado ao longo do tempo para novos analistas.</span><span class="sxs-lookup"><span data-stu-id="cf700-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="cf700-161">A solicitação de analista entra em fila para aprovação pelos Aprovadores do **Analista MSSP.**</span><span class="sxs-lookup"><span data-stu-id="cf700-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="cf700-162">![Imagem das propriedades de acesso](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="cf700-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="cf700-163">O link está localizado na página de visão geral de cada pacote de acesso.</span><span class="sxs-lookup"><span data-stu-id="cf700-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="cf700-164">Gerenciar Acesso</span><span class="sxs-lookup"><span data-stu-id="cf700-164">Manage access</span></span> 

1. <span data-ttu-id="cf700-165">Revisar e autorizar solicitações de acesso no myaccess cliente e/ou MSSP.</span><span class="sxs-lookup"><span data-stu-id="cf700-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="cf700-166">As solicitações de acesso são gerenciadas no cliente Meu Acesso, por membros do grupo aprovadores de analistas do MSSP.</span><span class="sxs-lookup"><span data-stu-id="cf700-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="cf700-167">Para fazer isso, acesse o myaccess do cliente usando:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="cf700-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="cf700-168">Exemplo:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="cf700-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="cf700-169">Aprovar ou negar solicitações na seção **Aprovações** da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="cf700-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="cf700-170">Neste ponto, o acesso de analistas foi provisionado, e cada analista deve ser capaz de acessar o cliente Central de Segurança do Microsoft Defender:`https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="cf700-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf700-171">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cf700-171">Related topics</span></span>
- [<span data-ttu-id="cf700-172">Acessar o portal do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="cf700-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="cf700-173">Configurar notificações de alerta</span><span class="sxs-lookup"><span data-stu-id="cf700-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="cf700-174">Buscar alertas do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="cf700-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

