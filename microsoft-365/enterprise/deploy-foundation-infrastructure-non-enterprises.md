---
title: Infraestrutura do Microsoft 365 Enterprise Foundation não empresarial
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Percorra as fases simplificadas da infraestrutura da fundação do Microsoft 365 Enterprise para organizações não empresariais.
ms.openlocfilehash: 8e2c254bf352baa14ff62dad500e5cdfa0af4563
ms.sourcegitcommit: 639607bbf02bdedd3fa5cd7b0984b422fe6c874e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2019
ms.locfileid: "35624629"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="bb50d-103">Infraestrutura do Microsoft 365 Enterprise Foundation não empresarial</span><span class="sxs-lookup"><span data-stu-id="bb50d-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="bb50d-104">Organizações não empresariais também podem implantar o Microsoft 365 Enterprise e perceber o valor comercial de uma infraestrutura integrada e segura, que permite o trabalho em equipe e desbloqueia a criatividade.</span><span class="sxs-lookup"><span data-stu-id="bb50d-104">Non-enterprise organizations can also deploy Microsoft 365 Enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="bb50d-105">Uma organização não empresarial tipicamente possui:</span><span class="sxs-lookup"><span data-stu-id="bb50d-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="bb50d-106">Uma pequena quantidade de infraestrutura de TI local, como servidores de email e de arquivos e um domínio dos Serviços de Domínio do Active Directory (AD DS), ou nada.</span><span class="sxs-lookup"><span data-stu-id="bb50d-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="bb50d-107">Uma pequena equipe de TI, composta em sua maioria por generalistas de TI, em vez de especialistas em uma tecnologia ou carga de trabalho específica, como rede ou email.</span><span class="sxs-lookup"><span data-stu-id="bb50d-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="bb50d-108">Para sua organização menor e não empresarial, a Microsoft oferece o [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span><span class="sxs-lookup"><span data-stu-id="bb50d-108">For your smaller, non-enterprise organization, Microsoft offers [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="bb50d-109">No entanto, existem razões pelas quais você pode precisar do Microsoft 365 Enterprise, como por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb50d-109">However, there are reasons why you might need Microsoft 365 Enterprise, such as:</span></span>

- <span data-ttu-id="bb50d-110">Sua organização precisa de mais ou precisará de mais de 300 licenças do Microsoft 365, que é o máximo para o Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bb50d-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 Business.</span></span>
- <span data-ttu-id="bb50d-111">Sua organização precisa das análises, segurança, voz e produtividade avançadas não disponíveis no Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bb50d-111">Your organization needs the advanced productivity, voice, security, and analytics that are not available with Microsoft 365 Business.</span></span>

<span data-ttu-id="bb50d-112">Este artigo orienta você para a realização de uma implantação simplificada da infraestrutura básica do Microsoft 365 Enterprise adequada para a sua organização não empresarial.</span><span class="sxs-lookup"><span data-stu-id="bb50d-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 Enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="bb50d-113">Primeiro, configure sua assinatura</span><span class="sxs-lookup"><span data-stu-id="bb50d-113">First, set up your subscription</span></span>

<span data-ttu-id="bb50d-114">Você deve configurar os domínios do Sistema de Nomes de Domínio (DNS) para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bb50d-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="bb50d-115">Se você já tiver uma assinatura do Office 365, isso já deve ter sido feito.</span><span class="sxs-lookup"><span data-stu-id="bb50d-115">If you already have an Office 365 subscription, this should have been done.</span></span> <span data-ttu-id="bb50d-116">Caso contrário, siga as instruções em [Adicionar um domínio ao Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="bb50d-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="bb50d-117">Em seguida, você precisará configurar segurança adicional para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb50d-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="bb50d-118">Siga as instruções em [Configurar segurança aumentada](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="bb50d-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="bb50d-119">Fase 1: Rede</span><span class="sxs-lookup"><span data-stu-id="bb50d-119">Phase 1: Networking</span></span>

<span data-ttu-id="bb50d-120">Organizações não empresariais geralmente têm conexões locais com a Internet em cada escritório e não usam servidores proxy, firewalls ou dispositivos de inspeção de pacotes.</span><span class="sxs-lookup"><span data-stu-id="bb50d-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="bb50d-121">O provedor de serviços de Internet (ISP) em cada escritório tem um servidor DNS regionalmente local para que o tráfego seja direcionado para os servidores em nuvem do Microsoft 365 mais próximos de seus escritórios e usuários locais.</span><span class="sxs-lookup"><span data-stu-id="bb50d-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span>

<span data-ttu-id="bb50d-122">Portanto, você precisa apenas verificar com seu ISP a conexão em cada um dos locais de seu escritório:</span><span class="sxs-lookup"><span data-stu-id="bb50d-122">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="bb50d-123">Usa um servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="bb50d-123">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="bb50d-124">É adequada para as suas necessidades atuais e futuras à medida que seus usuários comecem a usar mais serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb50d-124">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="bb50d-125">Se você usa servidores proxy, firewalls ou dispositivos de inspeção de pacotes, consulte [infraestrutura de rede do Microsoft 365 Enterprise ](networking-infrastructure.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="bb50d-125">If you do use proxy servers, firewalls, or packet inspection devices, see [Networking infrastructure for Microsoft 365 Enterprise](networking-infrastructure.md) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-126">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-126">Your configuration so far</span></span>

<span data-ttu-id="bb50d-127">Aqui está um resumo visual com o elemento da Fase 1 em destaque.</span><span class="sxs-lookup"><span data-stu-id="bb50d-127">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="bb50d-128">**Sua organização** pode ter vários escritórios, cada um com uma conexão de Internet local com um ISP (provedor de serviços de Internet) que usa um servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="bb50d-128">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="bb50d-129">Por meio do ISP, os usuários em cada escritório podem acessar o local de rede da Microsoft 365 mais próximo e os recursos da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb50d-129">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="bb50d-130">Fase 2: identidade</span><span class="sxs-lookup"><span data-stu-id="bb50d-130">Phase 2: Identity</span></span>

<span data-ttu-id="bb50d-131">Cada um dos funcionários da sua organização deve ser capaz de fazer logon, o que requer uma conta de usuário no locatário do Azure Active Directory (Azure AD) da sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bb50d-131">Each of the employees of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="bb50d-132">Os grupos são então usados para conter contas de usuário e outros grupos para se comunicar ou obter acesso a recursos autorizados, como um site ou uma equipe do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bb50d-132">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="bb50d-133">Contas de administrador</span><span class="sxs-lookup"><span data-stu-id="bb50d-133">Administrator accounts</span></span>

<span data-ttu-id="bb50d-134">Proteja suas contas de usuário globais de administrador, exigindo senhas muito fortes e autenticação de vários fatores (MFA).</span><span class="sxs-lookup"><span data-stu-id="bb50d-134">Protect your global administrator user accounts by requiring very strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="bb50d-135">Confira [Proteger contas globais de administrador](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-135">See [Protect your Office 365 global administrator accounts](identity-designate-protect-admin-accounts.md#protect-global-administrator-accounts) for more information about configuration.</span></span>

<span data-ttu-id="bb50d-136">Se a sua organização exigir alta segurança e você tiver o Microsoft 365 Enterprise E5, use o Azure AD Privileged Identity Management para habilitar o acesso just-in-time de administrador.</span><span class="sxs-lookup"><span data-stu-id="bb50d-136">If your organization requires high security and you have Microsoft 365 Enterprise E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="bb50d-137">Confira [Configurar administradores globais sob demanda](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-137">See [Set up on-demand global administrators](identity-designate-protect-admin-accounts.md#set-up-on-demand-global-administrators) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="bb50d-138">Recomendações para grupos</span><span class="sxs-lookup"><span data-stu-id="bb50d-138">Recommendations for groups</span></span>

<span data-ttu-id="bb50d-139">Se você tiver um domínio do AD DS no local, continue usando esses grupos no Microsoft 365 Enterprise como grupos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-139">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 Enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="bb50d-140">Se você não tiver um domínio do AD DS no local, crie grupos de segurança no Azure AD usando esses níveis de segurança.</span><span class="sxs-lookup"><span data-stu-id="bb50d-140">If you don’t have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="bb50d-141">Nível de segurança</span><span class="sxs-lookup"><span data-stu-id="bb50d-141">Security level</span></span> | <span data-ttu-id="bb50d-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb50d-142">Description</span></span> | <span data-ttu-id="bb50d-143">Exemplos</span><span class="sxs-lookup"><span data-stu-id="bb50d-143">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="bb50d-144">Linha de base</span><span class="sxs-lookup"><span data-stu-id="bb50d-144">Baseline</span></span> | <span data-ttu-id="bb50d-145">Este é um padrão mínimo para proteger dados e as identidades e dispositivos que acessam seus dados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-145">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="bb50d-146">Normalmente, estes são os dados da sua organização gerenciados pela maioria dos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="bb50d-146">This is typically most of your organization’s data managed by most of your users.</span></span> | <span data-ttu-id="bb50d-147">Grupos para trabalhadores de primeira linha, como de vendas, marketing, suporte, administração e manufatura.</span><span class="sxs-lookup"><span data-stu-id="bb50d-147">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="bb50d-148">Confidencial</span><span class="sxs-lookup"><span data-stu-id="bb50d-148">Sensitive</span></span> | <span data-ttu-id="bb50d-149">Esta é uma proteção adicional para um subconjunto de dados que deve ser protegido além do nível da linha de base.</span><span class="sxs-lookup"><span data-stu-id="bb50d-149">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="bb50d-150">Esses grupos contêm usuários que usam e criam dados confidenciais específicos de departamentos e projetos que não devem estar disponíveis para todos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-150">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="bb50d-151">Equipes de produtos ou marketing que estão desenvolvendo produtos futuros</span><span class="sxs-lookup"><span data-stu-id="bb50d-151">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="bb50d-152">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="bb50d-152">Highly regulated</span></span> | <span data-ttu-id="bb50d-153">Este é o nível mais alto de proteção para uma quantidade normalmente pequena de dados altamente confidenciais, considerados propriedade intelectual ou segredo comercial, ou dados que devem obedecer a regulamentações de segurança.</span><span class="sxs-lookup"><span data-stu-id="bb50d-153">Highly regulated: This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span> |  <span data-ttu-id="bb50d-154">Equipes de pesquisa, jurídica e financeira ou equipes que armazenam ou usam dados de clientes ou parceiros.</span><span class="sxs-lookup"><span data-stu-id="bb50d-154">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="bb50d-155">Identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="bb50d-155">Hybrid identity</span></span>

<span data-ttu-id="bb50d-156">Se você tiver um domínio do AD DS local, precisará sincronizar o conjunto de contas de usuários, grupos e contatos do seu domínio com o locatário do Azure AD de sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bb50d-156">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span> <span data-ttu-id="bb50d-157">Se você tiver um domínio do AD DS no local, configure o Azure AD Connect em um servidor com PHS (sincronização de hash de senha).</span><span class="sxs-lookup"><span data-stu-id="bb50d-157">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="bb50d-158">Confira [Sincronizar identidades](identity-azure-ad-connect.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-158">See [Synchronize identities](identity-azure-ad-connect.md) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="bb50d-159">Acesso de usuário mais seguro com políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="bb50d-159">More secure user access with conditional access policies</span></span>

<span data-ttu-id="bb50d-160">O Azure AD avalia as condições de logons de usuários e pode usar políticas de acesso condicional para conceder ou negar o acesso, bem como impor outras ações que devem ser tomadas para concluir o logon.</span><span class="sxs-lookup"><span data-stu-id="bb50d-160">Azure AD evaluates the conditions of user sign-ins and can use conditional access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="bb50d-161">Por exemplo, se o Azure AD determinar que o logon está acontecendo sob condições de médio ou alto risco, ele pode exigir que o usuário execute o MFA para concluir o logon.</span><span class="sxs-lookup"><span data-stu-id="bb50d-161">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="bb50d-162">As políticas de acesso condicional são aplicadas por você a contas ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="bb50d-162">You apply conditional access policies to user accounts or groups.</span></span> <span data-ttu-id="bb50d-163">Para facilitar uma atribuição mais fácil de políticas de acesso condicional, crie esses grupos de segurança do Azure AD em sua organização:</span><span class="sxs-lookup"><span data-stu-id="bb50d-163">To facilitate an easier assignment of conditional access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="bb50d-164">LINHA DE BASE</span><span class="sxs-lookup"><span data-stu-id="bb50d-164">Baseline</span></span>

  <span data-ttu-id="bb50d-165">Contém os grupos ou contas de usuários para usuários com acesso a dados de linha de base.</span><span class="sxs-lookup"><span data-stu-id="bb50d-165">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="bb50d-166">CONFIDENCIAL</span><span class="sxs-lookup"><span data-stu-id="bb50d-166">Sensitive</span></span>

  <span data-ttu-id="bb50d-167">Contém os grupos ou contas de usuários para usuários com acesso a dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="bb50d-167">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="bb50d-168">ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-168">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="bb50d-169">Contém os grupos ou contas de usuários para usuários com acesso a dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-169">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="bb50d-170">ACESSO-COND-EXCLUIR</span><span class="sxs-lookup"><span data-stu-id="bb50d-170">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="bb50d-171">Um grupo vazio que você pode usar para excluir temporariamente um usuário de políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="bb50d-171">An empty group that you can use to temporarily exclude a user from conditional access policies.</span></span>

<span data-ttu-id="bb50d-172">Esta é a lista de políticas de acesso condicional do Azure AD para ativar ou criar.</span><span class="sxs-lookup"><span data-stu-id="bb50d-172">Here is the list of Azure AD conditional access policies to enable or create.</span></span>

| <span data-ttu-id="bb50d-173">Política de acesso condicional do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb50d-173">Azure AD conditional access policy</span></span> | <span data-ttu-id="bb50d-174">Grupos aos quais se aplica</span><span class="sxs-lookup"><span data-stu-id="bb50d-174">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="bb50d-175">Política de linha de base: exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="bb50d-175">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="bb50d-176">Esta política se aplica a funções administrativas, portanto, nenhum grupo precisa ser especificado.</span><span class="sxs-lookup"><span data-stu-id="bb50d-176">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="bb50d-177">Esta política precisa ser ativada.</span><span class="sxs-lookup"><span data-stu-id="bb50d-177">This policy just needs to be enabled.</span></span> <span data-ttu-id="bb50d-178">Todas as políticas subsequentes precisam ser criadas e ativadas.</span><span class="sxs-lookup"><span data-stu-id="bb50d-178">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="bb50d-179">Bloquear clientes que não oferecem suporte à autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bb50d-179">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="bb50d-180">Selecione "Todos os usuários" nas configurações de política.</span><span class="sxs-lookup"><span data-stu-id="bb50d-180">Select “All users” in the policy settings.</span></span> |
| <span data-ttu-id="bb50d-181">Exigir MFA quando o risco de logon é médio ou alto (requer o Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="bb50d-181">Require MFA when sign-in risk is medium or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="bb50d-182">LINHA DE BASE</span><span class="sxs-lookup"><span data-stu-id="bb50d-182">Baseline</span></span> |
| <span data-ttu-id="bb50d-183">Exigir MFA quando o risco de logon é baixo, médio ou alto (requer o Microsoft 365 Enterprise E5)</span><span class="sxs-lookup"><span data-stu-id="bb50d-183">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 Enterprise E5)</span></span> | <span data-ttu-id="bb50d-184">CONFIDENCIAL</span><span class="sxs-lookup"><span data-stu-id="bb50d-184">Sensitive</span></span> |
| <span data-ttu-id="bb50d-185">Sempre exigir MFA</span><span class="sxs-lookup"><span data-stu-id="bb50d-185">Always require MFA</span></span> | <span data-ttu-id="bb50d-186">ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-186">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-187">Exigir aplicativos aprovados em dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="bb50d-187">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="bb50d-188">LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-188">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-189">Exigir PCs compatíveis</span><span class="sxs-lookup"><span data-stu-id="bb50d-189">Require compliant PCs</span></span> | <span data-ttu-id="bb50d-190">LINHA DE BASE</span><span class="sxs-lookup"><span data-stu-id="bb50d-190">Baseline</span></span> |
| <span data-ttu-id="bb50d-191">Exigir PCs compatíveis e dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="bb50d-191">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="bb50d-192">CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-192">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="bb50d-193">Aqui está a política de risco do usuário do Azure AD Identity Protection (requer o Microsoft 365 Enterprise E5) para criar e ativar.</span><span class="sxs-lookup"><span data-stu-id="bb50d-193">Here is the Azure AD Identity Protection (requires Microsoft 365 Enterprise E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="bb50d-194">Política de risco do usuário do Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="bb50d-194">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="bb50d-195">Grupos aos quais se aplica</span><span class="sxs-lookup"><span data-stu-id="bb50d-195">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="bb50d-196">Usuários de alto risco devem alterar suas senhas</span><span class="sxs-lookup"><span data-stu-id="bb50d-196">High risk users must change passwords</span></span> | <span data-ttu-id="bb50d-197">Selecione "Todos os usuários" nas configurações de política.</span><span class="sxs-lookup"><span data-stu-id="bb50d-197">Select “All users” in the policy settings.</span></span> |
|||

<span data-ttu-id="bb50d-198">Confira [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bb50d-198">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="bb50d-199">Grupos para um gerenciamento mais fácil</span><span class="sxs-lookup"><span data-stu-id="bb50d-199">Groups for easier management</span></span>

<span data-ttu-id="bb50d-200">Aqui estão alguns recursos que podem tornar o gerenciamento de grupos e licenças mais fácil para você.</span><span class="sxs-lookup"><span data-stu-id="bb50d-200">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="bb50d-201">Recurso</span><span class="sxs-lookup"><span data-stu-id="bb50d-201">Feature</span></span> | <span data-ttu-id="bb50d-202">Usar</span><span class="sxs-lookup"><span data-stu-id="bb50d-202">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="bb50d-203">Gerenciamento de grupo de autoatendimento</span><span class="sxs-lookup"><span data-stu-id="bb50d-203">Self-service group management</span></span> | <span data-ttu-id="bb50d-204">Permitir o gerenciamento de grupos do Azure AD por proprietários de grupos em vez da equipe de TI.</span><span class="sxs-lookup"><span data-stu-id="bb50d-204">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="bb50d-205">Confira [Gerenciamento de grupo de autoatendimento](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-205">See [Self-service group management](identity-self-service-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="bb50d-206">Associação de grupos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="bb50d-206">Dynamic group membership</span></span> | <span data-ttu-id="bb50d-207">Configurar adição ou remoção automática de contas de usuários de grupos do Azure AD com base nos atributos da conta do usuário, como Departamento ou País.</span><span class="sxs-lookup"><span data-stu-id="bb50d-207">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="bb50d-208">Confira [Associação de grupos dinâmicos](identity-self-service-group-management.md#set-up-dynamic-group-membership) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-208">See [Dynamic group membership](identity-self-service-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="bb50d-209">Licenciamento com base em grupo</span><span class="sxs-lookup"><span data-stu-id="bb50d-209">Group-based licensing</span></span> | <span data-ttu-id="bb50d-210">Use a associação a grupos para atribuir ou cancelar a atribuição de licenças a contas de usuários automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bb50d-210">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="bb50d-211">Confira [Licenciamento baseado em grupo](identity-self-service-group-management.md#set-up-automatic-licensing) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-211">See [Group-based licensing](identity-self-service-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="bb50d-212">Se você estiver usando licenciamento baseado em grupo, crie um grupo denominado LICENCIADO para conter nomes de contas de usuários que possuem atribuída uma licença do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bb50d-212">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 Enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="bb50d-213">Monitorar o acesso a usuários</span><span class="sxs-lookup"><span data-stu-id="bb50d-213">Monitor user access</span></span>

<span data-ttu-id="bb50d-214">Se você tiver o Microsoft 365 Enterprise E5, poderá usar o Azure AD Identity Protection para monitorar e analisar logons de usuário para detectar comprometimento de credenciais.</span><span class="sxs-lookup"><span data-stu-id="bb50d-214">If you have Microsoft 365 Enterprise E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="bb50d-215">Confira [Proteger contra comprometimento de credenciais](identity-multi-factor-authentication.md#protect-against-credential-compromise) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-215">See [Protect against credential compromise](identity-multi-factor-authentication.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-216">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-216">Your configuration so far</span></span>

<span data-ttu-id="bb50d-217">Aqui está um resumo visual da fase Identidade para identidade híbrida, com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-217">Here is a visual summary of the Identity phase for hybrid identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="bb50d-218">Os novos elementos de identidade destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-218">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="bb50d-219">Um domínio do AD DS no local com contas e grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="bb50d-219">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="bb50d-220">Um servidor baseado no Windows executando o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="bb50d-220">A Windows-based server running Azure AD Connect.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="bb50d-221">O conjunto sincronizado de contas e grupos do AD DS no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-221">The synchronized set of AD DS accounts and groups in Azure AD.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="bb50d-222">Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças.</span><span class="sxs-lookup"><span data-stu-id="bb50d-222">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="bb50d-223">Políticas de acesso condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-223">Azure AD conditional access policies.</span></span> |
|||

<span data-ttu-id="bb50d-224">Aqui está um resumo visual da fase Identidade para identidade somente na nuvem, com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-224">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="bb50d-225">Os novos elementos de identidade somente na nuvem destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-225">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="bb50d-226">Configurações do Azure AD para autenticação, proteção de contas globais e simplificação do gerenciamento de grupos e licenças.</span><span class="sxs-lookup"><span data-stu-id="bb50d-226">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="bb50d-227">Políticas de acesso condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-227">Azure AD conditional access policies.</span></span> |
|||



## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="bb50d-228">Fase 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bb50d-228">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="bb50d-229">Para garantir que seus dispositivos do Windows 10 Enterprise sejam integrados à infraestrutura de identidade e segurança do Microsoft 365, veja as opções:</span><span class="sxs-lookup"><span data-stu-id="bb50d-229">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365, here are your options:</span></span>

- <span data-ttu-id="bb50d-230">Híbrido (você possui um domínio do AD DS no local)</span><span class="sxs-lookup"><span data-stu-id="bb50d-230">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="bb50d-231">Para cada dispositivo empresarial do Windows 10 já existente no seu domínio AD DS, ingresse-o no locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-231">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="bb50d-232">Confira [Como configurar dispositivos associados híbridos do Active Directory do Azure](https://go.microsoft.com/fwlink/p/?linkid=872870) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bb50d-232">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="bb50d-233">Para cada novo dispositivo do Windows 10 Enterprise, associe-o ao seu domínio do AD DS e, em seguida, associe-o ao locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-233">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="bb50d-234">Inscreva cada dispositivo do Windows 10 Enterprise para o gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="bb50d-234">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="bb50d-235">Confira [Inscrever um dispositivo do Windows 10 no Intune usando uma Política de Grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bb50d-235">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="bb50d-236">Somente na nuvem (você não possui um domínio do AD DS no local)</span><span class="sxs-lookup"><span data-stu-id="bb50d-236">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="bb50d-237">Associe cada dispositivo do Windows 10 Enterprise ao locatário do Azure AD da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="bb50d-237">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="bb50d-238">Confira [Adicione seu dispositivo de trabalho à rede da sua organização](https://docs.microsoft.com/pt-BR/azure/active-directory/user-help/user-help-join-device-on-network) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-238">See [Join your work device to your organization's network](https://docs.microsoft.com/en-us/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="bb50d-239">Depois de instalados e associados, cada dispositivo do Windows 10 Enterprise instala automaticamente as atualizações do serviço em nuvem do Windows Update for Business.</span><span class="sxs-lookup"><span data-stu-id="bb50d-239">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="bb50d-240">Em uma organização não empresarial, normalmente não há necessidade de configurar uma infraestrutura para distribuir e instalar atualizações do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="bb50d-240">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-241">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-241">Your configuration so far</span></span>

<span data-ttu-id="bb50d-242">Aqui está um resumo visual da fase do Windows 10 Enterprise com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-242">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="bb50d-243">Os novos elementos do Windows 10 Enterprise destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-243">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="bb50d-244">Windows 10 Enterprise instalado em dispositivos Windows, com o laptop local como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="bb50d-244">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="bb50d-245">O Centro de Serviços de Licenciamento por Volume, que fornece imagens para novas instalações do Windows 10 Enterprise, e o serviço Windows Update for Business, que fornece as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bb50d-245">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-office-365-proplus"></a><span data-ttu-id="bb50d-246">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="bb50d-246">Phase 4: Office 365 ProPlus</span></span>

<span data-ttu-id="bb50d-247">O Microsoft 365 Enterprise inclui o Office 365 ProPlus, a versão de assinatura do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="bb50d-247">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="bb50d-248">Como o Office 2016 ou Office 2019, o Office 365 ProPlus é instalado diretamente em seus dispositivos clientes.</span><span class="sxs-lookup"><span data-stu-id="bb50d-248">Like Office 2016 or Office 2019, Office 365 ProPlus is installed directly on your client devices.</span></span> <span data-ttu-id="bb50d-249">No entanto, o Office 365 ProPlus recebe novos recursos regularmente.</span><span class="sxs-lookup"><span data-stu-id="bb50d-249">However, Office 365 ProPlus receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="bb50d-250">Confira [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-250">See [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="bb50d-251">Para sua organização não empresarial, instale manualmente o Office 365 ProPlus em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-251">For your non-enterprise organization, you manually install Office 365 ProPlus on devices.</span></span> <span data-ttu-id="bb50d-252">Isso pode ser feito como parte da preparação de um novo dispositivo para uso ou pode ser feito pelo usuário como parte de seu processo de integração.</span><span class="sxs-lookup"><span data-stu-id="bb50d-252">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="bb50d-253">Em ambos os casos, o administrador ou o usuário entra no portal do Office 365 em https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="bb50d-253">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="bb50d-254">Na guia **Página inicial do Microsoft Office**, clique em **Instalar o Office** e percorra o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="bb50d-254">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="bb50d-255">Atualizações de recursos para o Office 365 ProPlus são baixadas mensalmente por cada computador em que ele está instalado.</span><span class="sxs-lookup"><span data-stu-id="bb50d-255">Feature updates to Office 365 ProPlus are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="bb50d-256">Em uma organização não empresarial, normalmente não há necessidade de configurar uma infraestrutura para distribuir atualizações do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="bb50d-256">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Office 365 ProPlus updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-257">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-257">Your configuration so far</span></span>

<span data-ttu-id="bb50d-258">Aqui está um resumo visual da fase do Office 365 ProPlus com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-258">Here is a visual summary of the Office 365 ProPlus phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="bb50d-259">Os novos elementos do Office 365 ProPlus destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-259">The new and highlighted Office 365 ProPlus elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="bb50d-260">Office 365 ProPlus instalado em dispositivos, com o laptop local como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="bb50d-260">Office 365 ProPlus installed on devices, with an on-premises laptop as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="bb50d-261">A Rede de Distribuição de Conteúdo (CDN) do Office para o Office 365 ProPlus, a qual os dispositivos acessam para atualizações do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="bb50d-261">The Office Content Delivery Network (CDN) for Office 365 ProPlus, which devices access for Office 365 ProPlus updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="bb50d-262">Fase 5: gerenciamento de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="bb50d-262">Phase 5: Mobile device management</span></span>

<span data-ttu-id="bb50d-263">O Microsoft 365 Enterprise inclui o Microsoft Intune para gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="bb50d-263">Microsoft 365 Enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="bb50d-264">Com o Intune, você pode gerenciar dispositivos iOS, Android, macOS e Windows para proteger o acesso aos recursos da sua organização, incluindo seus dados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-264">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="bb50d-265">O Intune usa as contas de usuários, grupos e computadores do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-265">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="bb50d-266">O Intune fornece dois tipos de gerenciamento de dispositivos móveis:</span><span class="sxs-lookup"><span data-stu-id="bb50d-266">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="bb50d-267">O gerenciamento de dispositivos móveis (MDM) é quando os dispositivos são inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="bb50d-267">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="bb50d-268">Uma vez inscritos, eles se tornam dispositivos gerenciados e podem receber as políticas, regras e configurações usadas por sua organização.</span><span class="sxs-lookup"><span data-stu-id="bb50d-268">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="bb50d-269">Esses tipos de dispositivos são normalmente de propriedade da sua organização e emitidos para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="bb50d-269">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="bb50d-270">Os usuários com seus próprios dispositivos pessoais podem não querer inscrever seus dispositivos ou serem gerenciados pelo Intune com suas políticas e configurações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-270">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="bb50d-271">No entanto, você ainda precisa proteger os recursos e dados de sua organização.</span><span class="sxs-lookup"><span data-stu-id="bb50d-271">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="bb50d-272">Para este cenário, você pode proteger seus aplicativos usando o gerenciamento de aplicativos móveis (MAM).</span><span class="sxs-lookup"><span data-stu-id="bb50d-272">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="bb50d-273">As políticas do Intune podem impor a conformidade do dispositivo e a proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bb50d-273">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="bb50d-274">Aqui está a lista de políticas do Intune para criar.</span><span class="sxs-lookup"><span data-stu-id="bb50d-274">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="bb50d-275">Políticas do Intune</span><span class="sxs-lookup"><span data-stu-id="bb50d-275">Intune policies</span></span> | <span data-ttu-id="bb50d-276">Grupos aos quais se aplica</span><span class="sxs-lookup"><span data-stu-id="bb50d-276">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="bb50d-277">Política de conformidade de dispositivos para o Windows</span><span class="sxs-lookup"><span data-stu-id="bb50d-277">Device compliance policy for Windows</span></span> | <span data-ttu-id="bb50d-278">LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-278">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-279">Política de conformidade de dispositivos para iOS</span><span class="sxs-lookup"><span data-stu-id="bb50d-279">Device compliance policy for iOS</span></span> | <span data-ttu-id="bb50d-280">CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-280">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-281">Conformidade de dispositivos para macOS</span><span class="sxs-lookup"><span data-stu-id="bb50d-281">Device compliance for macOS</span></span> | <span data-ttu-id="bb50d-282">CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-282">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-283">Política de conformidade de dispositivos para Android e Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="bb50d-283">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="bb50d-284">CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-284">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-285">Política de proteção de aplicativos para iOS</span><span class="sxs-lookup"><span data-stu-id="bb50d-285">App protection policy for iOS</span></span> | <span data-ttu-id="bb50d-286">LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-286">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-287">Política de proteção de aplicativos para macOS</span><span class="sxs-lookup"><span data-stu-id="bb50d-287">App protection policy for macOS</span></span> | <span data-ttu-id="bb50d-288">LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-288">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="bb50d-289">Política de proteção de aplicativos para Android e Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="bb50d-289">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="bb50d-290">LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULAMENTADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-290">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="bb50d-291">Confira [Políticas comuns de acesso a identidades e dispositivos](identity-access-policies.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="bb50d-291">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-292">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-292">Your configuration so far</span></span>

<span data-ttu-id="bb50d-293">Aqui está um resumo visual da fase de Gerenciamento de Dispositivos Móveis com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-293">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="bb50d-294">Os novos elementos de gerenciamento de dispositivos móveis destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-294">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="bb50d-295">Dispositivos inscritos no Intune, mostrando o laptop local executando o Windows 10 Enterprise como exemplo.</span><span class="sxs-lookup"><span data-stu-id="bb50d-295">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![](./media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="bb50d-296">Políticas do Intune para conformidade de dispositivos e proteção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-296">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="bb50d-297">Fase 6: proteção de informações</span><span class="sxs-lookup"><span data-stu-id="bb50d-297">Phase 6: Information protection</span></span>

<span data-ttu-id="bb50d-298">O Microsoft 365 Enterprise tem um host de recursos de proteção de informações que permitem tratar classificações de dados de maneira diferente, aplicando níveis diferentes de governança, segurança e proteção.</span><span class="sxs-lookup"><span data-stu-id="bb50d-298">Microsoft 365 Enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="bb50d-299">Por exemplo, as correspondências normais entre a maioria dos funcionários e os documentos com os quais eles trabalham precisam de um certo nível de linha de base de proteção.</span><span class="sxs-lookup"><span data-stu-id="bb50d-299">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="bb50d-300">Registros financeiros, dados do cliente e sua propriedade intelectual precisam de um nível mais alto de proteção.</span><span class="sxs-lookup"><span data-stu-id="bb50d-300">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="bb50d-301">O primeiro passo para uma estratégia de proteção da informação é determinar os níveis de proteção.</span><span class="sxs-lookup"><span data-stu-id="bb50d-301">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="bb50d-302">Muitas organizações usam esses níveis, que já estão sendo usados para políticas de acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="bb50d-302">Many organizations use these levels, which are already being used for conditional access policies:</span></span>

- <span data-ttu-id="bb50d-303">Linha de base</span><span class="sxs-lookup"><span data-stu-id="bb50d-303">Baseline</span></span>

  <span data-ttu-id="bb50d-304">Os exemplos incluem comunicações comerciais normais (email) e arquivos para funcionários administrativos, de vendas e de suporte.</span><span class="sxs-lookup"><span data-stu-id="bb50d-304">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="bb50d-305">Confidencial</span><span class="sxs-lookup"><span data-stu-id="bb50d-305">Sensitive</span></span>

  <span data-ttu-id="bb50d-306">Os exemplos incluem informações financeiras e jurídicas e dados de pesquisa e desenvolvimento para novos produtos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="bb50d-306">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span>

- <span data-ttu-id="bb50d-307">Altamente controlado</span><span class="sxs-lookup"><span data-stu-id="bb50d-307">Highly regulated</span></span>

  <span data-ttu-id="bb50d-308">Exemplos incluem informações de identificação pessoal de clientes e parceiros e a propriedade intelectual da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bb50d-308">Examples include customer and partner personally identifiable information and your organization’s financial information or intellectual property.</span></span>

<span data-ttu-id="bb50d-309">Com base nesses níveis de segurança de dados, o próximo passo é identificar e implementar:</span><span class="sxs-lookup"><span data-stu-id="bb50d-309">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="bb50d-310">Tipos de informações confidenciais personalizadas</span><span class="sxs-lookup"><span data-stu-id="bb50d-310">Custom sensitive information types</span></span>

  <span data-ttu-id="bb50d-311">O Microsoft 365 fornece uma ampla seleção de tipos de informações confidenciais, como serviços de saúde e números de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="bb50d-311">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="bb50d-312">Se você não encontrar o que precisa na lista fornecida, poderá criar o seu próprio.</span><span class="sxs-lookup"><span data-stu-id="bb50d-312">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="bb50d-313">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="bb50d-313">Retention labels</span></span>

  <span data-ttu-id="bb50d-314">Para cumprir as políticas da organização e os regulamentos regionais, talvez seja necessário especificar por quanto tempo os tipos específicos de documentos ou documentos com conteúdo específico devem ser mantidos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-314">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="bb50d-315">Você pode implementar isto para emails e documentos usando rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="bb50d-315">You can implement this for email and documents using retention labels.</span></span>

- <span data-ttu-id="bb50d-316">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="bb50d-316">Sensitivity labels</span></span>

  <span data-ttu-id="bb50d-317">Você pode rotular emails ou documentos com um rótulo de confidencialidade nomeado para que os níveis adicionais de segurança possam ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-317">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="bb50d-318">Exemplos são marcas d'água, criptografia e permissões, que especificam quem tem permissão para acessar o email ou documento e o que eles podem fazer.</span><span class="sxs-lookup"><span data-stu-id="bb50d-318">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="bb50d-319">Confira os [tipos de classificação do Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="bb50d-319">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="bb50d-320">Se você usar rótulos de confidencialidade com permissões, poderá ser necessário criar grupos de segurança adicionais do Azure AD para definir quem tem permissão para fazer o quê com emails e documentos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-320">If you use sensitivity labels with permissions, you might have to create additional Azure AD security groups to define who is allowed to do what with email and documents.</span></span> 

<span data-ttu-id="bb50d-321">Por exemplo, você precisa criar um rótulo de confidencialidade PESQUISA para proteger os emails e documentos da sua equipe de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bb50d-321">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="bb50d-322">Você determina que:</span><span class="sxs-lookup"><span data-stu-id="bb50d-322">You determine that:</span></span>

- <span data-ttu-id="bb50d-323">Os pesquisadores devem ter a capacidade de alterar documentos marcados com o rótulo de sensibilidade da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bb50d-323">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="bb50d-324">Os funcionários que não são de pesquisa só precisam ter a capacidade de exibir documentos marcados com o rótulo de sensibilidade da PESQUISA.</span><span class="sxs-lookup"><span data-stu-id="bb50d-324">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="bb50d-325">Isso significa que você precisa criar e gerenciar dois grupos adicionais:</span><span class="sxs-lookup"><span data-stu-id="bb50d-325">This means you need to create and manage two additional groups:</span></span>

- <span data-ttu-id="bb50d-326">PESQUISA-TODOS</span><span class="sxs-lookup"><span data-stu-id="bb50d-326">RESEARCH-ALL</span></span>
- <span data-ttu-id="bb50d-327">PESQUISA-VISUALIZAR</span><span class="sxs-lookup"><span data-stu-id="bb50d-327">RESEARCH-VIEW</span></span>

<span data-ttu-id="bb50d-328">Esses grupos e suas permissões se tornam parte da configuração do rótulo de confidencialidade PESQUISA.</span><span class="sxs-lookup"><span data-stu-id="bb50d-328">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="bb50d-329">Para rótulos de confidencialidade configurados com permissões baseadas em grupo, você deve gerenciar a associação desses grupos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-329">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="bb50d-330">Sua configuração até agora</span><span class="sxs-lookup"><span data-stu-id="bb50d-330">Your configuration so far</span></span>

<span data-ttu-id="bb50d-331">Aqui está um resumo visual da fase de Proteção de Informações com os novos elementos destacados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-331">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="bb50d-332">Os novos elementos de proteção de informações destacados incluem:</span><span class="sxs-lookup"><span data-stu-id="bb50d-332">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![](./media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="bb50d-333">Rótulos de confidencialidade para os três níveis de segurança que os usuários podem aplicar aos documentos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-333">Sensitivity labels for the three levels of security that users can apply to documents.</span></span> |
|||

<span data-ttu-id="bb50d-334">Rótulos de retenção e tipos de informações personalizadas não são mostrados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-334">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="bb50d-335">Integração</span><span class="sxs-lookup"><span data-stu-id="bb50d-335">Onboarding</span></span>

<span data-ttu-id="bb50d-336">Com a infraestrutura do Microsoft 365 Enterprise instalada, você pode integrar seus funcionários facilmente.</span><span class="sxs-lookup"><span data-stu-id="bb50d-336">With your Microsoft 365 Enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="bb50d-337">Um novo dispositivo do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bb50d-337">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="bb50d-338">Antes de fornecer ao funcionário um novo dispositivo do Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="bb50d-338">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="bb50d-339">Para identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="bb50d-339">For hybrid identity</span></span>

  <span data-ttu-id="bb50d-340">Associe o dispositivo ao seu AD DS, associe o dispositivo ao seu locatário do Azure AD e, em seguida, inscreva o dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="bb50d-340">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="bb50d-341">Para identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="bb50d-341">For cloud-only identity</span></span>

  <span data-ttu-id="bb50d-342">Associe o dispositivo ao locatário do Azure AD da sua assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bb50d-342">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="bb50d-343">Funcionário existente com uma conta de usuário do AD DS</span><span class="sxs-lookup"><span data-stu-id="bb50d-343">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="bb50d-344">Como parte da integração inicial da sua organização ao usar a identidade híbrida, adicione a conta de usuário do AD DS a estes grupos do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="bb50d-344">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="bb50d-345">LICENCIADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-345">Licensed</span></span>
- <span data-ttu-id="bb50d-346">Os grupos de segurança apropriados do AD DS ou do Azure AD que são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-346">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="bb50d-347">Grupos de rótulos de confidencialidade (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="bb50d-347">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="bb50d-348">O funcionário existente já deve ser adicionado aos grupos de grupo de trabalho e grupos departamentais e regionais do AD DS.</span><span class="sxs-lookup"><span data-stu-id="bb50d-348">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="bb50d-349">Você pode adicionar uma conta de usuário a vários grupos do Azure AD no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bb50d-349">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bb50d-350">Nas propriedades da conta do usuário, clique em **gerenciar grupos > Adicionar associações**.</span><span class="sxs-lookup"><span data-stu-id="bb50d-350">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="bb50d-351">Caso pretenda usar o PowerShell, confira [esta pasta de trabalho](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true)do Excel para baixá-la, que gera os comandos do PowerShell com base em uma conta de usuário especificada e os nomes dos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-351">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/microsoft-365/enterprise/media/Group-License-Mgmt-PowerShell.xlsx?raw=true), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="bb50d-352">Novo funcionário com conta de usuário somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="bb50d-352">New employee with a cloud-only user account</span></span>

<span data-ttu-id="bb50d-353">Como parte da integração inicial da sua organização ao usar a identidade somente na nuvem, adicione a nova conta de usuário a estes grupos:</span><span class="sxs-lookup"><span data-stu-id="bb50d-353">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="bb50d-354">LICENCIADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-354">Licensed</span></span>
- <span data-ttu-id="bb50d-355">Os grupos de segurança apropriados do Azure AD que são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULAMENTADO do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb50d-355">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="bb50d-356">Grupo de trabalho, departamental, e grupos regionais</span><span class="sxs-lookup"><span data-stu-id="bb50d-356">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="bb50d-357">Grupos de rótulos de confidencialidade (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="bb50d-357">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="bb50d-358">Logon inicial no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb50d-358">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="bb50d-359">Na primeira vez que os funcionários entram no Microsoft 365, instrua-os a:</span><span class="sxs-lookup"><span data-stu-id="bb50d-359">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="bb50d-360">Fazerem logon em seus dispositivos com suas credenciais de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="bb50d-360">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="bb50d-361">Usando um navegador, entre no portal do Office 365, em https://portal.office.com.</span><span class="sxs-lookup"><span data-stu-id="bb50d-361">Using a browser on your local computer, sign in to the https://portal.office.com using your global administrator account.</span></span>
3. <span data-ttu-id="bb50d-362">Na guia **Página Inicial do Office 365**, clique em **Instalar o Office** para instalar o Office 365 ProPlus em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bb50d-362">From the **Office 365 Home** tab, click **Install Office** to install Office 365 ProPlus on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="bb50d-363">Resultados finais</span><span class="sxs-lookup"><span data-stu-id="bb50d-363">End results</span></span>

<span data-ttu-id="bb50d-364">Aqui estão os resultados da configuração da infraestrutura de base do Microsoft 365 Enterprise para sua organização não empresarial.</span><span class="sxs-lookup"><span data-stu-id="bb50d-364">Here are the results of configuring the Microsoft 365 Enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="bb50d-365">Resultados de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="bb50d-365">Infrastructure results</span></span>

<span data-ttu-id="bb50d-366">Após o desenvolvimento e a configuração da infraestrutura do Microsoft 365 Enterprise, você deve ter:</span><span class="sxs-lookup"><span data-stu-id="bb50d-366">After the build-out and configuration of your Microsoft 365 Enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="bb50d-367">Uma conexão de Internet local para cada um de seus escritórios com largura de banda suficiente fornecida por um ISP (provedor de serviços de Internet) que usa um servidor DNS regionalmente local.</span><span class="sxs-lookup"><span data-stu-id="bb50d-367">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="bb50d-368">Para identidade híbrida, o Azure AD Connect é executado em um servidor que sincroniza seu domínio do AD DS local com o seu locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-368">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="bb50d-369">Esses grupos:</span><span class="sxs-lookup"><span data-stu-id="bb50d-369">These universal groups include:</span></span>
  - <span data-ttu-id="bb50d-370">LICENCIADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-370">Licensed</span></span>
  - <span data-ttu-id="bb50d-371">ACESSO-COND-EXCLUIR</span><span class="sxs-lookup"><span data-stu-id="bb50d-371">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="bb50d-372">Os grupos de segurança apropriados do AD DS ou do Azure AD que também são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb50d-372">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="bb50d-373">Grupo de trabalho, departamental, e grupos regionais</span><span class="sxs-lookup"><span data-stu-id="bb50d-373">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="bb50d-374">Grupos de rótulos de confidencialidade (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="bb50d-374">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="bb50d-375">Políticas de acesso condicional de logon do Azure AD que usam os grupos LINHA DE BASE, CONFIDENCIAL, ALTAMENTE REGULADO, ACESSO-COND-EXCLUIR do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb50d-375">Azure AD sign-in conditional access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="bb50d-376">Políticas de conformidade de aplicativos e dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="bb50d-376">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="bb50d-377">Tipos de informações confidenciais personalizadas (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="bb50d-377">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="bb50d-378">Rótulos de retenção (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="bb50d-378">Retention labels (as needed).</span></span>
- <span data-ttu-id="bb50d-379">Rótulos de confidencialidade (conforme necessário).</span><span class="sxs-lookup"><span data-stu-id="bb50d-379">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="bb50d-380">Este é um resumo visual da infraestrutura se sua organização usa identidade híbrida, a qual inclui seu domínio do AD DS, um servidor do Azure AD Connect e grupos e usuários do AD DS sincronizados.</span><span class="sxs-lookup"><span data-stu-id="bb50d-380">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![](./media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="bb50d-381">Aqui está um resumo visual da infraestrutura se a sua organização usa a identidade somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="bb50d-381">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![](./media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="bb50d-382">Resultados dos funcionários</span><span class="sxs-lookup"><span data-stu-id="bb50d-382">Employee results</span></span>

<span data-ttu-id="bb50d-383">Após a integração, cada funcionário deve ter:</span><span class="sxs-lookup"><span data-stu-id="bb50d-383">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="bb50d-384">Um caminho de rede local de alto desempenho conectando os dispositivos deles aos serviços de nuvem da Microsoft 365 na região deles.</span><span class="sxs-lookup"><span data-stu-id="bb50d-384">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="bb50d-385">Uma conta de usuário com estas associações de grupo:</span><span class="sxs-lookup"><span data-stu-id="bb50d-385">A user account with these group memberships:</span></span>
   - <span data-ttu-id="bb50d-386">LICENCIADO</span><span class="sxs-lookup"><span data-stu-id="bb50d-386">Licensed</span></span>
   - <span data-ttu-id="bb50d-387">Os grupos de segurança apropriados do AD DS ou do Azure AD, que também são membros dos grupos LINHA DE BASE, CONFIDENCIAL e ALTAMENTE REGULADO do Azure AD para políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="bb50d-387">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for conditional access policies</span></span> 
   - <span data-ttu-id="bb50d-388">Os grupos apropriados de grupos de trabalho e grupos departamentais e regionais</span><span class="sxs-lookup"><span data-stu-id="bb50d-388">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="bb50d-389">Grupos de rótulos de confidencialidade (conforme necessário)</span><span class="sxs-lookup"><span data-stu-id="bb50d-389">Sensitivity label groups (as needed)</span></span>
- <span data-ttu-id="bb50d-390">Um dispositivo do Windows 10 Enterprise que:</span><span class="sxs-lookup"><span data-stu-id="bb50d-390">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="bb50d-391">É associado ao locatário do Azure AD (somente nuvem) ou ao locatário do Azure AD e ao seu domínio do AD DS (híbrido).</span><span class="sxs-lookup"><span data-stu-id="bb50d-391">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="bb50d-392">Atualiza automaticamente com as melhorias e aprimoramentos de segurança mais recentes do produto Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bb50d-392">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="bb50d-393">Tem o Office 365 ProPlus instalado, o qual atualiza automaticamente com os aprimoramentos de segurança e aprimoramentos de produtos do Office mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bb50d-393">Has Office 365 ProPlus installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="bb50d-394">Está inscrito no Intune e sujeito às políticas de conformidade de dispositivos e políticas de proteção de aplicativos do Intune.</span><span class="sxs-lookup"><span data-stu-id="bb50d-394">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="bb50d-395">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bb50d-395">Next step</span></span>

<span data-ttu-id="bb50d-396">Implante suas [cargas de trabalho e cenários](deploy-workloads.md) e aproveite os recursos e a configuração da infraestrutura de fundação do Microsoft Enterprise 365.</span><span class="sxs-lookup"><span data-stu-id="bb50d-396">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
