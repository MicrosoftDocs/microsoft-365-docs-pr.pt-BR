---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: 5c78e8cc9235eb2ca5de091c05d1883ed6cca1b4
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369602"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="32d5a-103">Identidade para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="32d5a-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="32d5a-104">**Resumo:** como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece autenticação baseada em nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="32d5a-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="32d5a-105">A Microsoft fornece identidade como um serviço (IDaaS) em todas as suas ofertas de nuvem com o Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="32d5a-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="32d5a-106">Para adotar o Microsoft 365 Enterprise, a solução IDaaS da Contoso teve que aproveitar seu provedor de identidade local e ainda assim incluir autenticação federada com seus atuais provedores de identidade confiáveis de terceiros.</span><span class="sxs-lookup"><span data-stu-id="32d5a-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="32d5a-107">Floresta dos Serviços de Domínio do Active Directory da Contoso</span><span class="sxs-lookup"><span data-stu-id="32d5a-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="32d5a-108">A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso.com com sete subdomínios, uma para cada região do mundo.</span><span class="sxs-lookup"><span data-stu-id="32d5a-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="32d5a-109">A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.</span><span class="sxs-lookup"><span data-stu-id="32d5a-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="32d5a-110">A Figura 1 mostra a floresta da Contoso com domínios regionais para diferentes partes do mundo que possuem hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="32d5a-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Floresta e domínios da Contoso em todo o mundo](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="32d5a-112">**Figura 1: floresta e domínios da Contoso em todo o mundo**</span><span class="sxs-lookup"><span data-stu-id="32d5a-112">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="32d5a-113">A Contoso queria usar as contas e grupos na floresta de contoso.com para autenticação e autorização de suas cargas de trabalho e serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32d5a-113">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="32d5a-114">Infraestrutura de autenticação federada da Contoso</span><span class="sxs-lookup"><span data-stu-id="32d5a-114">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="32d5a-115">A Contoso permite que:</span><span class="sxs-lookup"><span data-stu-id="32d5a-115">Contoso allows:</span></span>

- <span data-ttu-id="32d5a-116">Clientes usem as contas da Microsoft, Facebook ou Google Mail para entrar no site público.</span><span class="sxs-lookup"><span data-stu-id="32d5a-116">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="32d5a-117">Fornecedores e parceiros usam as contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="32d5a-117">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="32d5a-p103">A Figura 2 mostra a DMZ da Contoso, contendo um site público, uma extranet de parceiro e um conjunto de servidores dos Serviços de Federação do Active Directory (AD FS). A DMZ está conectada à Internet, onde estão os clientes, parceiros e serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="32d5a-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Suporte da Contoso para autenticação federada para clientes e parceiros](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="32d5a-121">**Figura 2: suporte da Contoso para autenticação federada para clientes e parceiros**</span><span class="sxs-lookup"><span data-stu-id="32d5a-121">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="32d5a-122">Os servidores AD FS na DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acessar o site público e as credenciais de parceiro para acessar a extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="32d5a-122">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="32d5a-123">A Contoso decidiu manter essa infraestrutura e dedicar-se a autenticações de clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="32d5a-123">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD B2B and B2C solutions.</span></span> <span data-ttu-id="32d5a-124">Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="32d5a-124">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="32d5a-125">Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem</span><span class="sxs-lookup"><span data-stu-id="32d5a-125">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="32d5a-126">A Contoso queria aproveitar sua floresta do AD DS local para autenticação para os recursos de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="32d5a-126">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="32d5a-127">Ela escolheu sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="32d5a-127">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="32d5a-128">A PHS sincroniza a floresta do AD DS local com o locatário do Azure AD de sua assinatura do Microsoft 365 Enterprise, copiando contas de usuários e de grupo e uma versão especificada como hash de senhas de contas de usuários.</span><span class="sxs-lookup"><span data-stu-id="32d5a-128">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="32d5a-129">Para realizar a sincronização de diretórios em andamento, a Contoso implantou a ferramenta Azure AD Connect em um servidor no seu datacenter em Paris.</span><span class="sxs-lookup"><span data-stu-id="32d5a-129">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> <span data-ttu-id="32d5a-130">A figura 3 mostra o servidor executando o Azure AD Connect sondando mudanças na floresta do AD DS da Contoso e sincronizando essas mudanças com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="32d5a-130">Figure 3 shows the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![A infraestrutura PHS de sincronização de diretórios da Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="32d5a-132">**Figura 3: infraestrutura PHS de sincronização de diretórios da Contoso**</span><span class="sxs-lookup"><span data-stu-id="32d5a-132">**Figure 3: Contoso's PHS directory synchronization infrastructure**</span></span>


## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="32d5a-133">Políticas de acesso condicional para identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="32d5a-133">Conditional access policies for identity and device access</span></span>

<span data-ttu-id="32d5a-134">A Contoso criou um conjunto de [políticas de acesso condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:</span><span class="sxs-lookup"><span data-stu-id="32d5a-134">Contoso created a set of Azure AD and Intune [conditional access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="32d5a-135">Proteções de **linha de base** aplicam-se a todas as contas de usuários</span><span class="sxs-lookup"><span data-stu-id="32d5a-135">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="32d5a-136">Proteções **confidenciais** aplicam-se à liderança sênior e equipe executiva</span><span class="sxs-lookup"><span data-stu-id="32d5a-136">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="32d5a-137">Proteções **altamente controladas** aplicam-se a usuários específicos nos departamentos de finanças, jurídico e de pesquisa que têm acesso a dados altamente controlados.</span><span class="sxs-lookup"><span data-stu-id="32d5a-137">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="32d5a-138">A figura 4 mostra o conjunto resultante de políticas de acesso condicional de identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="32d5a-138">Figure 4 shows their resulting set of identity and device conditional access policies.</span></span>

![As políticas de acesso condicional de identidades e dispositivos da Contoso](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="32d5a-140">**Figura 4: as políticas de acesso condicional de identidades e dispositivos da Contoso**</span><span class="sxs-lookup"><span data-stu-id="32d5a-140">**Figure 4: Contoso’s identity and device conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="32d5a-141">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="32d5a-141">Next step</span></span>

<span data-ttu-id="32d5a-142">[Saiba](contoso-win10.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Windows 10 Enterprise atualizado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="32d5a-142">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="32d5a-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="32d5a-143">See also</span></span>

[<span data-ttu-id="32d5a-144">Identidade para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="32d5a-144">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="32d5a-145">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="32d5a-145">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="32d5a-146">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="32d5a-146">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
