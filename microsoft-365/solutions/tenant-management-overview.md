---
title: Gerenciamento de locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Uma visão geral do planejamento, implantação e operação contínua dos locatários do Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908451"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a><span data-ttu-id="f5cd6-103">Gerenciamento de locatários do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f5cd6-103">Tenant management for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="f5cd6-104">Criar um caminho para a transformação digital da sua organização com a computação em nuvem requer uma base sólida na qual seus funcionários podem confiar em produtividade, colaboração, desempenho, privacidade, conformidade e segurança.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-104">Creating a path to your organization's digital transformation with cloud computing requires a firm foundation upon which your workers can rely for productivity, collaboration, performance, privacy, compliance, and security.</span></span>

<span data-ttu-id="f5cd6-105">A configuração correta dos locatários do Microsoft 365 fornece essa base, deixando os funcionários focados na execução do trabalho e no departamento de TI a fim de se concentrar nas soluções de ponta a ponta que fornecem valor comercial adicional.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-105">Correct configuration of your Microsoft 365 tenants provides that foundation, leaving your workers to focus on getting their work done and your IT department to focus on end-to-end solutions that provide additional business value.</span></span> 

<span data-ttu-id="f5cd6-106">Esta solução o leva até a configuração dessa base nestas etapas:</span><span class="sxs-lookup"><span data-stu-id="f5cd6-106">This solution takes you through the configuration of that foundation in these steps:</span></span>

1. <span data-ttu-id="f5cd6-107">Determinar seus locatários</span><span class="sxs-lookup"><span data-stu-id="f5cd6-107">Determine your tenants</span></span>
2. <span data-ttu-id="f5cd6-108">Otimizar sua rede</span><span class="sxs-lookup"><span data-stu-id="f5cd6-108">Optimize your networking</span></span>
3. <span data-ttu-id="f5cd6-109">Sincronizar suas identidades e impor logins seguros</span><span class="sxs-lookup"><span data-stu-id="f5cd6-109">Synchronize your identities and enforce secure sign-ins</span></span>
4. <span data-ttu-id="f5cd6-110">Migrar seus dispositivos Windows, clientes do Office e dados e servidores do Office locais</span><span class="sxs-lookup"><span data-stu-id="f5cd6-110">Migrate your Windows devices, Office clients, and on-premises Office servers and data</span></span>
5. <span data-ttu-id="f5cd6-111">Implantar o gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="f5cd6-111">Deploy device and app management</span></span>

<span data-ttu-id="f5cd6-112">Mas primeiro, vamos dar um tempo para entender o que é um locatário e a aparência de um locatário que fornece uma base sólida.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-112">But first, let's take a moment to understand what a tenant is and what a tenant that provides a firm foundation looks like.</span></span>

## <a name="a-microsoft-365-tenant-defined"></a><span data-ttu-id="f5cd6-113">Um locatário do Microsoft 365 definido</span><span class="sxs-lookup"><span data-stu-id="f5cd6-113">A Microsoft 365 tenant defined</span></span>

<span data-ttu-id="f5cd6-114">Um locatário do Microsoft 365 é uma instância dedicada dos serviços do Microsoft 365 e os dados da sua organização armazenados em um local padrão específico, como a Europa ou a América do Norte.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-114">A Microsoft 365 tenant is a dedicated instance of the services of Microsoft 365 and your organization data stored within a specific default location, such as Europe or North America.</span></span> <span data-ttu-id="f5cd6-115">Esse local é especificado quando você cria o locatário para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-115">This location is specified when you create the tenant for your organization.</span></span> <span data-ttu-id="f5cd6-116">Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-116">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="f5cd6-117">Você cria um locatário do Microsoft 365 quando compra um ou mais produtos da Microsoft, como o Microsoft 365 E3 ou E5, e um conjunto de licenças para cada um.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-117">You create a Microsoft 365 tenant when you purchase one or more products from Microsoft, such as Microsoft 365 E3 or E5, and a set of licenses for each.</span></span>

<span data-ttu-id="f5cd6-118">Seu locatário do Microsoft 365 também inclui um locatário do Azure Active Directory (Azure AD), que é uma instância dedicada do Azure AD para contas de usuário, grupos e outros objetos.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-118">Your Microsoft 365 tenant also includes an Azure Active Directory (Azure AD) tenant, which is a dedicated instance of Azure AD for user accounts, groups, and other objects.</span></span> <span data-ttu-id="f5cd6-119">Cada locatário do Azure AD é distinto, exclusivo e separado de todos os outros locatários do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-119">Each Azure AD tenant is distinct, unique, and separate from all other Azure AD tenants.</span></span> <span data-ttu-id="f5cd6-120">Embora sua organização possa ter vários locatários do Azure AD que você pode configurar com assinaturas do Azure, os locatários do Microsoft 365 só podem usar um único locatário do Azure AD, aquele que foi criado quando você criou o locatário.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-120">While your organization can have multiple Azure AD tenants that you can set up with Azure subscriptions, Microsoft 365 tenants can only use a single Azure AD tenant, the one that was created when you created the tenant.</span></span> 

<span data-ttu-id="f5cd6-121">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="f5cd6-121">Here is an example:</span></span>

![Um exemplo de locatário do Microsoft 365 com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

<span data-ttu-id="f5cd6-123">*O gerenciamento de* locatários é o planejamento, a implantação e a operação contínua dos locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-123">*Tenant management* is the planning, deployment, and ongoing operation of your Microsoft 365 tenants.</span></span> 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a><span data-ttu-id="f5cd6-124">Atributos de um locatário bem projetado e operacional</span><span class="sxs-lookup"><span data-stu-id="f5cd6-124">Attributes of a well-designed and operating tenant</span></span>

<span data-ttu-id="f5cd6-125">Além do nome e do local corretos para seu locatário, há elementos adicionais para planejar, implantar e gerenciar para garantir que suas experiências de usuário com aplicativos de produtividade na nuvem, como o Microsoft Teams e o Exchange Online, sejam eficazes, seguras e &mdash; &mdash; eficazes.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-125">Beyond the correct name and location for your tenant, there are additional elements to plan, deploy, and manage to ensure that your user experiences with cloud productivity apps&mdash;such as Microsoft Teams and Exchange Online&mdash;are effective, secure, and performant.</span></span>

<span data-ttu-id="f5cd6-126">Aqui estão os elementos:</span><span class="sxs-lookup"><span data-stu-id="f5cd6-126">Here are the elements:</span></span>

- <span data-ttu-id="f5cd6-127">Você tem o conjunto correto de produtos (assinaturas) e licenças.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-127">You have the correct set of products (subscriptions) and licenses.</span></span>
  - <span data-ttu-id="f5cd6-128">O conjunto de produtos combina com suas necessidades comerciais, de IT e de segurança.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-128">The set of products match your business, IT, and security needs.</span></span>
  - <span data-ttu-id="f5cd6-129">Há um número adequado de licenças para seus funcionários e alterações previstas no pessoal.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-129">There is an adequate number of licenses for your workers and anticipated changes in staffing.</span></span>
- <span data-ttu-id="f5cd6-130">Para rede:</span><span class="sxs-lookup"><span data-stu-id="f5cd6-130">For networking:</span></span>
  - <span data-ttu-id="f5cd6-131">Você configurou os nomes de domínio DNS corretos.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-131">You have configured the correct DNS domain names.</span></span>
  - <span data-ttu-id="f5cd6-132">Para redes corporativas, você otimizou o tráfego de rede para a rede da Microsoft para funcionários no local.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-132">For enterprise networks, you have optimized network traffic to the Microsoft network for onsite workers.</span></span>
  - <span data-ttu-id="f5cd6-133">Você otimizou o tráfego de rede para funcionários remotos que estão usando um cliente VPN.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-133">You have optimized network traffic for remote workers who are using a VPN client.</span></span>
- <span data-ttu-id="f5cd6-134">Você sincronizou suas contas, grupos e outros objetos do Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="f5cd6-134">You have synchronized your Active Directory Domain Services (AD DS) accounts, groups, and other objects.</span></span>
  - <span data-ttu-id="f5cd6-135">Suas contas de locatário do Azure AD são mapeadas para caixas de correio do Exchange Online com os domínios DNS corretos para endereços de email.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-135">Your Azure AD tenant accounts are mapped to Exchange Online mailboxes with the correct DNS domains for email addresses.</span></span>
  - <span data-ttu-id="f5cd6-136">Suas contas de usuário foram atribuídas com as licenças corretas dos produtos comprados corretos (como o Microsoft 365 E3 ou E5).</span><span class="sxs-lookup"><span data-stu-id="f5cd6-136">Your user accounts have been assigned the correct licenses from the correct purchased products (such as Microsoft 365 E3 or E5).</span></span>
- <span data-ttu-id="f5cd6-137">Você configurou um gerenciamento forte de identidade e acesso.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-137">You have configured strong identity and access management.</span></span>
  - <span data-ttu-id="f5cd6-138">Você está exigindo uma conexão de usuário segura com autenticação sem senha ou multifafação (MFA).</span><span class="sxs-lookup"><span data-stu-id="f5cd6-138">You are requiring secure user sign-in with passwordless or multi-factor authentication (MFA).</span></span>
  - <span data-ttu-id="f5cd6-139">Você tem políticas de Acesso Condicional que impõem restrições e requisitos de entrada para níveis mais altos de segurança.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-139">You have Conditional Access policies that enforce sign-in requirements and restrictions for higher levels of security.</span></span>
- <span data-ttu-id="f5cd6-140">Os servidores locais do Office e seus dados foram migrados para aplicativos de nuvem ou estão sendo usados em uma configuração híbrida.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-140">On-premises Office servers and their data have been migrated to cloud apps or are being used in a hybrid configuration.</span></span>
- <span data-ttu-id="f5cd6-141">Você está fazendo o gerenciamento de dispositivos com o Intune ou o Basic Mobility and Security integrados ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-141">You are doing device management with Intune or Basic Mobility and Security built into Microsoft 365.</span></span>
  - <span data-ttu-id="f5cd6-142">Os dispositivos de propriedade da sua organização são inscritos e gerenciados.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-142">Your organization-owned devices are enrolled and managed.</span></span>
  - <span data-ttu-id="f5cd6-143">Os aplicativos para dispositivos pessoais são gerenciados.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-143">The apps for personal devices are managed.</span></span>

<span data-ttu-id="f5cd6-144">Aqui está um exemplo de um locatário do Microsoft 365 com todos esses elementos no local.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-144">Here is an example of a Microsoft 365 tenant with all these elements in place.</span></span>

![Um exemplo de locatário do Microsoft 365](../media/tenant-management-overview/tenant-management-tenant-config.png)

<span data-ttu-id="f5cd6-146">Nesta ilustração, o locatário do Microsoft 365 inclui:</span><span class="sxs-lookup"><span data-stu-id="f5cd6-146">In this illustration, the Microsoft 365 tenant includes:</span></span>

- <span data-ttu-id="f5cd6-147">Produtos e licenças para o Microsoft 365 E3 e E5.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-147">Products and licenses for Microsoft 365 E3 and E5.</span></span>
- <span data-ttu-id="f5cd6-148">Aplicativos de produtividade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-148">Microsoft 365 productivity apps.</span></span>
- <span data-ttu-id="f5cd6-149">Intune com dispositivos inscritos e políticas de dispositivos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-149">Intune with enrolled devices and device and application policies.</span></span>
- <span data-ttu-id="f5cd6-150">Um locatário do Azure AD que sincronizou a conta de usuário (grupos e outros objetos de diretório não são mostrados), domínios e políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-150">An Azure AD tenant that has synchronized user account (groups and other directory objects are not shown), domains, and Conditional Access policies.</span></span>

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a><span data-ttu-id="f5cd6-151">Recursos de locatário do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f5cd6-151">Tenant capabilities for Microsoft 365 for enterprise</span></span>

<span data-ttu-id="f5cd6-152">As seções e tabelas a seguir listam os principais recursos e licenciamento para as etapas desta solução.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-152">The following sections and table list the key capabilities and licensing for the steps in this solution.</span></span>

### <a name="tenant"></a><span data-ttu-id="f5cd6-153">Tenant</span><span class="sxs-lookup"><span data-stu-id="f5cd6-153">Tenant</span></span>

| <span data-ttu-id="f5cd6-154">Capcidade ou recurso</span><span class="sxs-lookup"><span data-stu-id="f5cd6-154">Capability or feature</span></span> | <span data-ttu-id="f5cd6-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5cd6-155">Description</span></span> | <span data-ttu-id="f5cd6-156">Licenças</span><span class="sxs-lookup"><span data-stu-id="f5cd6-156">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f5cd6-157">Vários locatários</span><span class="sxs-lookup"><span data-stu-id="f5cd6-157">Multiple tenants</span></span> | <span data-ttu-id="f5cd6-158">Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-158">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="f5cd6-159">Com vários locatários, há restrições e considerações adicionais ao gerenciar e fornecer serviços aos usuários.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-159">With multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span> | <span data-ttu-id="f5cd6-160">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-160">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-161">Migração de caixa de correio entre locatários</span><span class="sxs-lookup"><span data-stu-id="f5cd6-161">Cross-tenant mailbox migration</span></span> | <span data-ttu-id="f5cd6-162">Os administradores de locatários podem mover caixas de correio entre locatários com dependências mínimas de infraestrutura em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-162">Tenant administrators can move mailboxes between tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="f5cd6-163">Isso elimina a necessidade de remoção e integração de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-163">This removes the need to off-board and onboard mailboxes.</span></span> | <span data-ttu-id="f5cd6-164">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-164">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-165">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="f5cd6-165">Multi-Geo</span></span> | <span data-ttu-id="f5cd6-166">Seu locatário pode armazenar dados em repouso em outras localizações geográficas do datacenter que você escolheu para atender aos requisitos de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-166">Your tenant can store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements.</span></span> | <span data-ttu-id="f5cd6-167">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-167">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-168">Mover os dados principais para uma nova área geográfica de datacenter</span><span class="sxs-lookup"><span data-stu-id="f5cd6-168">Move core data to a new datacenter geo</span></span> | <span data-ttu-id="f5cd6-169">À medida que a Microsoft adiciona novas áreas geográficas de datacenter para capacidade adicional e recursos de computação, você pode solicitar uma movimentação geográfica de datacenter para residência de dados na área geográfica dos dados principais do cliente.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-169">As Microsoft adds new datacenter geos for additional capacity and compute resources, you can request a datacenter geo move for in-geo data residency for your core customer data.</span></span> | <span data-ttu-id="f5cd6-170">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-170">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="networking"></a><span data-ttu-id="f5cd6-171">Rede</span><span class="sxs-lookup"><span data-stu-id="f5cd6-171">Networking</span></span>

| <span data-ttu-id="f5cd6-172">Capcidade ou recurso</span><span class="sxs-lookup"><span data-stu-id="f5cd6-172">Capability or feature</span></span> | <span data-ttu-id="f5cd6-173">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5cd6-173">Description</span></span> | <span data-ttu-id="f5cd6-174">Licenças</span><span class="sxs-lookup"><span data-stu-id="f5cd6-174">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f5cd6-175">Network Insights</span><span class="sxs-lookup"><span data-stu-id="f5cd6-175">Network Insights</span></span> | <span data-ttu-id="f5cd6-176">Métricas de desempenho de rede coletadas do locatário do Microsoft 365 para ajudá-lo a projetar perímetros de rede para seus locais de escritório.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-176">Network performance metrics collected from your Microsoft 365 tenant to help you design network perimeters for your office locations.</span></span> | <span data-ttu-id="f5cd6-177">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-177">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-178">Automatizar atualizações de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f5cd6-178">Automate endpoint updates</span></span> | <span data-ttu-id="f5cd6-179">Automatize a configuração e as atualizações contínuas dos pontos de extremidade do Microsoft 365 em seus arquivos PAC do cliente e dispositivos e serviços de rede.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-179">Automate the configuration and ongoing updates for Microsoft 365 endpoints in your client PAC files and network devices and services.</span></span> | <span data-ttu-id="f5cd6-180">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-180">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="identity"></a><span data-ttu-id="f5cd6-181">Identidade</span><span class="sxs-lookup"><span data-stu-id="f5cd6-181">Identity</span></span>

| <span data-ttu-id="f5cd6-182">Capcidade ou recurso</span><span class="sxs-lookup"><span data-stu-id="f5cd6-182">Capability or feature</span></span> | <span data-ttu-id="f5cd6-183">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5cd6-183">Description</span></span> | <span data-ttu-id="f5cd6-184">Licenças</span><span class="sxs-lookup"><span data-stu-id="f5cd6-184">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f5cd6-185">Sincronizar os Serviços de Domínio do Active Directory (AD DS) local com seu locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f5cd6-185">Synchronize on-premises Active Directory Domain Services (AD DS) with your Azure AD tenant</span></span>    | <span data-ttu-id="f5cd6-186">Aproveite seu provedor de identidade local para contas de usuário, grupos e outros objetos.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-186">Leverage your on-premises identity provider for user accounts, groups, and other objects.</span></span> | <span data-ttu-id="f5cd6-187">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-187">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f5cd6-188">MFA imposta com padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="f5cd6-188">MFA enforced with security defaults</span></span>   | <span data-ttu-id="f5cd6-189">Proteja-se contra os dispositivos e identidades comprometidos exigindo uma segunda forma de autenticação para as entradas. O padrão de segurança exige MFA para todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-189">Protect against compromised identities and devices by requiring a second form of authentication for sign-ins. Security defaults requires MFA for all user accounts.</span></span>   | <span data-ttu-id="f5cd6-190">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-190">Microsoft 365 E3 or E5</span></span> |
| <span data-ttu-id="f5cd6-191">MFA imposta com Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="f5cd6-191">MFA enforced with Conditional Access</span></span>| <span data-ttu-id="f5cd6-192">Exigir MFA com base nos atributos da entrada com políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-192">Require MFA based on the attributes of the sign-in with Conditional Access policies.</span></span>    | <span data-ttu-id="f5cd6-193">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-193">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-194">MFA imposta com Acesso Condicional baseado em risco</span><span class="sxs-lookup"><span data-stu-id="f5cd6-194">MFA enforced with risk-based Conditional Access</span></span>   | <span data-ttu-id="f5cd6-195">Exija MFA com base no risco de o usuário entrar no Microsoft Defender para Identidade.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-195">Require MFA based on the risk of the user sign-in with Microsoft Defender for Identity.</span></span> | <span data-ttu-id="f5cd6-196">Microsoft 365 E5 ou E3 com as licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="f5cd6-196">Microsoft 365 E5 or E3 with Azure AD Premium P2 licenses</span></span> | 
| <span data-ttu-id="f5cd6-197">Redefinição de Senha por autoatendimento (SSPR)</span><span class="sxs-lookup"><span data-stu-id="f5cd6-197">Self-Service Password Reset (SSPR)</span></span>    | <span data-ttu-id="f5cd6-198">Permita que os usuários redefinam ou desbloqueiem suas contas ou senhas.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-198">Allow your users to reset or unlock their passwords or accounts.</span></span>  | <span data-ttu-id="f5cd6-199">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-199">Microsoft 365 E3 or E5</span></span> |
||||

### <a name="migration"></a><span data-ttu-id="f5cd6-200">Migração</span><span class="sxs-lookup"><span data-stu-id="f5cd6-200">Migration</span></span>

| <span data-ttu-id="f5cd6-201">Capcidade ou recurso</span><span class="sxs-lookup"><span data-stu-id="f5cd6-201">Capability or feature</span></span> | <span data-ttu-id="f5cd6-202">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5cd6-202">Description</span></span> | <span data-ttu-id="f5cd6-203">Licenças</span><span class="sxs-lookup"><span data-stu-id="f5cd6-203">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f5cd6-204">Migrar para o Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5cd6-204">Migrate to Windows 10</span></span> | <span data-ttu-id="f5cd6-205">Migre seus dispositivos que executem o Windows 7 ou o Windows 8.1 para o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-205">Migrate your devices that run Windows 7 or Windows 8.1 to Windows 10 Enterprise.</span></span> | <span data-ttu-id="f5cd6-206">Licenças do Windows 10 Enterprise incluídas no Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-206">Windows 10 Enterprise licenses included with Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-207">Migrar para o Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="f5cd6-207">Migrate to Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="f5cd6-208">Migre seus aplicativos cliente do Office, como Word e PowerPoint, para as versões instaladas da nuvem que são atualizadas com novos recursos.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-208">Migrate your Office client apps such as Word and PowerPoint to the versions installed from the cloud that are updated with new features.</span></span> | <span data-ttu-id="f5cd6-209">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-209">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-210">Migrar dados e servidores locais para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f5cd6-210">Migrate on-premises servers and data to Microsoft 365</span></span> | <span data-ttu-id="f5cd6-211">Migre suas caixas de correio do Exchange, sites do SharePoint e Skype for Business Online para os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-211">Migrate your Exchange mailboxes, SharePoint sites, and Skype for Business Online to Microsoft 365 cloud services.</span></span> | <span data-ttu-id="f5cd6-212">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-212">Microsoft 365 E3 or E5</span></span> | 
||||

### <a name="device-and-app-management"></a><span data-ttu-id="f5cd6-213">Gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="f5cd6-213">Device and app management</span></span>

| <span data-ttu-id="f5cd6-214">Capcidade ou recurso</span><span class="sxs-lookup"><span data-stu-id="f5cd6-214">Capability or feature</span></span> | <span data-ttu-id="f5cd6-215">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5cd6-215">Description</span></span> | <span data-ttu-id="f5cd6-216">Licenças</span><span class="sxs-lookup"><span data-stu-id="f5cd6-216">Licensing</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="f5cd6-217">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f5cd6-217">Microsoft Intune</span></span> | <span data-ttu-id="f5cd6-218">Um serviço baseado em nuvem que fornece gerenciamento de dispositivo móvel (MDM) e gerenciamento de aplicativo móvel (MAM) para controlar como o aplicativo da sua organização e os dispositivos são usados, incluindo celulares, tablets e laptops.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-218">A cloud-based service that provides mobile device management (MDM) and mobile application management (MAM) to control how your organization’s application and the devices are used, including mobile phones, tablets, and laptops.</span></span> | <span data-ttu-id="f5cd6-219">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-219">Microsoft 365 E3 or E5</span></span> | 
| <span data-ttu-id="f5cd6-220">Mobilidade e Segurança Básica</span><span class="sxs-lookup"><span data-stu-id="f5cd6-220">Basic Mobility and Security</span></span> | <span data-ttu-id="f5cd6-221">Proteja e gerencie os dispositivos móveis dos usuários, como iPhones, iPads, Androids e telefones Windows com esse serviço integrado.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-221">Secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones with this built-in service.</span></span>  | <span data-ttu-id="f5cd6-222">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="f5cd6-222">Microsoft 365 E3 or E5</span></span> | 
||||

## <a name="next-steps"></a><span data-ttu-id="f5cd6-223">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f5cd6-223">Next steps</span></span>

<span data-ttu-id="f5cd6-224">Use estas etapas para configurar e gerenciar seus locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-224">Use these steps to set up and manage your Microsoft 365 tenants.</span></span>

1. [<span data-ttu-id="f5cd6-225">Determinar seus locatários</span><span class="sxs-lookup"><span data-stu-id="f5cd6-225">Determine your tenants</span></span>](tenant-management-tenants.md)
2. [<span data-ttu-id="f5cd6-226">Otimizar sua rede</span><span class="sxs-lookup"><span data-stu-id="f5cd6-226">Optimize your networking</span></span>](tenant-management-networking.md)
3. [<span data-ttu-id="f5cd6-227">Sincronizar suas identidades e impor logins seguros</span><span class="sxs-lookup"><span data-stu-id="f5cd6-227">Synchronize your identities and enforce secure sign-ins</span></span>](tenant-management-identity.md)
4. [<span data-ttu-id="f5cd6-228">Migrar seus dados e servidores do Office locais</span><span class="sxs-lookup"><span data-stu-id="f5cd6-228">Migrate your on-premises Office servers and data</span></span>](tenant-management-migration.md)
5. [<span data-ttu-id="f5cd6-229">Implantar o gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="f5cd6-229">Deploy device and app management</span></span>](tenant-management-device-management.md)

<span data-ttu-id="f5cd6-230">[![As etapas para implantar e gerenciar um locatário do Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="f5cd6-230">[![The steps to deploy and manage a Microsoft 365 tenant](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)</span></span>

<span data-ttu-id="f5cd6-231">Cada etapa descreve as opções de implantação, resume os resultados e tarefas contínuas de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f5cd6-231">Each step describes deployment options, summarizes the results, and ongoing maintenance tasks.</span></span>

<span data-ttu-id="f5cd6-232">Para entender como uma organização multinacional fictícia, mas representativa, implantou os elementos de seu locatário do Microsoft 365, consulte o estudo de caso [da Contoso.](../enterprise/contoso-case-study.md)</span><span class="sxs-lookup"><span data-stu-id="f5cd6-232">To understand how a fictional but representative multi-national organization deployed the elements of their Microsoft 365 tenant, see the [Contoso case study](../enterprise/contoso-case-study.md).</span></span>