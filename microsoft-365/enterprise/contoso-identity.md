---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: 81a1542edf82bbf773360af6b09e1f940f5fd061
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38627357"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="f4702-103">Identidade para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="f4702-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="f4702-104">**Resumo:** como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece autenticação baseada em nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="f4702-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="f4702-105">A Microsoft fornece identidade como um serviço (IDaaS) em todas as suas ofertas de nuvem com o Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f4702-105">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f4702-106">Para adotar o Microsoft 365 Enterprise, a solução IDaaS da Contoso teve que aproveitar seu provedor de identidade local e ainda assim incluir autenticação federada com seus atuais provedores de identidade confiáveis de terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4702-106">To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-active-directory-domain-services-forest"></a><span data-ttu-id="f4702-107">Floresta dos Serviços de Domínio do Active Directory da Contoso</span><span class="sxs-lookup"><span data-stu-id="f4702-107">Contoso's Active Directory Domain Services forest</span></span>

<span data-ttu-id="f4702-108">A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso.com com sete subdomínios, uma para cada região do mundo.</span><span class="sxs-lookup"><span data-stu-id="f4702-108">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso.com with seven sub-domains, one for each region of the world.</span></span> <span data-ttu-id="f4702-109">A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.</span><span class="sxs-lookup"><span data-stu-id="f4702-109">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="f4702-110">Esta é a floresta da Contoso com domínios regionais para diferentes partes do mundo que possuem hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="f4702-110">Here is the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Floresta e domínios da Contoso em todo o mundo](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="f4702-112">A Contoso queria usar as contas e grupos na floresta de contoso.com para autenticação e autorização de suas cargas de trabalho e serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4702-112">Contoso wanted to use the accounts and groups in the contoso.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="f4702-113">Infraestrutura de autenticação federada da Contoso</span><span class="sxs-lookup"><span data-stu-id="f4702-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="f4702-114">A Contoso permite que:</span><span class="sxs-lookup"><span data-stu-id="f4702-114">Contoso allows:</span></span>

- <span data-ttu-id="f4702-115">Clientes usem as contas da Microsoft, Facebook ou Google Mail para entrar no site público.</span><span class="sxs-lookup"><span data-stu-id="f4702-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="f4702-116">Fornecedores e parceiros usam as contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="f4702-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="f4702-117">Este é o DMZ da Contoso, que contém um site público, uma extranet parceira e um conjunto de servidores de Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="f4702-117">Here is the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="f4702-118">O DMZ está conectado à Internet que contém clientes, parceiros e serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="f4702-118">The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![Suporte da Contoso para autenticação federada para clientes e parceiros](./media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="f4702-120">Os servidores AD FS na DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acessar o site público e as credenciais de parceiro para acessar a extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="f4702-120">AD FS servers in the DMZ facilitate the authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="f4702-121">A Contoso decidiu manter essa infraestrutura e dedicar-se a autenticações de clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="f4702-121">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications.</span></span> <span data-ttu-id="f4702-122">Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="f4702-122">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="f4702-123">Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem</span><span class="sxs-lookup"><span data-stu-id="f4702-123">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="f4702-124">A Contoso queria aproveitar sua floresta do AD DS local para autenticação para os recursos de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4702-124">Contoso wanted to leverage its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="f4702-125">Ela escolheu sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="f4702-125">It decided on password hash synchronization (PHS).</span></span>

<span data-ttu-id="f4702-126">A PHS sincroniza a floresta do AD DS local com o locatário do Azure AD de sua assinatura do Microsoft 365 Enterprise, copiando contas de usuários e de grupo e uma versão especificada como hash de senhas de contas de usuários.</span><span class="sxs-lookup"><span data-stu-id="f4702-126">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span> 

<span data-ttu-id="f4702-127">Para realizar a sincronização de diretórios em andamento, a Contoso implantou a ferramenta Azure AD Connect em um servidor no seu datacenter em Paris.</span><span class="sxs-lookup"><span data-stu-id="f4702-127">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span> 

<span data-ttu-id="f4702-128">Este é o servidor executando o Azure AD Connect sondando mudanças na floresta do AD DS da Contoso e sincronizando essas mudanças com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4702-128">Here is the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![A infraestrutura PHS de sincronização de diretórios da Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="f4702-130">Políticas de Acesso Condicional para acesso de identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="f4702-130">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="f4702-131">A Contoso criou um conjunto de [políticas de Acesso Condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:</span><span class="sxs-lookup"><span data-stu-id="f4702-131">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="f4702-132">Proteções de **linha de base** aplicam-se a todas as contas de usuários</span><span class="sxs-lookup"><span data-stu-id="f4702-132">**Baseline** protections apply to all user accounts</span></span>
- <span data-ttu-id="f4702-133">Proteções **confidenciais** aplicam-se à liderança sênior e equipe executiva</span><span class="sxs-lookup"><span data-stu-id="f4702-133">**Sensitive** protections apply to senior leadership and executive staff</span></span>
- <span data-ttu-id="f4702-134">Proteções **altamente controladas** aplicam-se a usuários específicos nos departamentos de finanças, jurídico e de pesquisa que têm acesso a dados altamente controlados.</span><span class="sxs-lookup"><span data-stu-id="f4702-134">**Highly Regulated** protections apply to specific users in the finance, legal, and research departments that have access to highly regulated data</span></span>

<span data-ttu-id="f4702-135">Este é o conjunto resultante de políticas de Acesso Condicional de identidades e dispositivos da Contoso.</span><span class="sxs-lookup"><span data-stu-id="f4702-135">Here is Contoso's resulting set of identity and device Conditional Access policies.</span></span>

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](./media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="f4702-137">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f4702-137">Next step</span></span>

<span data-ttu-id="f4702-138">[Saiba](contoso-win10.md) mais sobre como a Contoso utiliza a infraestrutura do Microsoft Endpoint Configuration Manager para implantar e manter o Windows 10 Enterprise atualizado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="f4702-138">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="f4702-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4702-139">See also</span></span>

[<span data-ttu-id="f4702-140">Identidade para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4702-140">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="f4702-141">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="f4702-141">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="f4702-142">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="f4702-142">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
