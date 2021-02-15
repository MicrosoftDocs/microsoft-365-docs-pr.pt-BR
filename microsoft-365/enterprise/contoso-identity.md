---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754627"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="d71dd-103">Identidade para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d71dd-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="d71dd-104">A Microsoft fornece a Identidade como serviço (IDaaS) em suas ofertas de nuvem por meio do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d71dd-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="d71dd-105">Para adotar o Microsoft 365 para empresas, a solução IDaaS da Contoso precisava usar seu provedor de identidade local e incluir a autenticação federada com seus provedores de identidade confiáveis de terceiros existentes.</span><span class="sxs-lookup"><span data-stu-id="d71dd-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="d71dd-106">A floresta dos Serviços de Domínio active Directory da Contoso</span><span class="sxs-lookup"><span data-stu-id="d71dd-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="d71dd-107">A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso com sete sub-domínios, um para cada \. região do mundo.</span><span class="sxs-lookup"><span data-stu-id="d71dd-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="d71dd-108">A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.</span><span class="sxs-lookup"><span data-stu-id="d71dd-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="d71dd-109">Esta é a floresta da Contoso com domínios regionais para as diferentes partes do mundo que contêm hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="d71dd-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Floresta e domínios da Contoso em todo o mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="d71dd-111">A Contoso decidiu usar as contas e grupos na floresta contoso com para autenticação e autorização para suas cargas de trabalho e serviços \. do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d71dd-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="d71dd-112">A infraestrutura de autenticação federada da Contoso</span><span class="sxs-lookup"><span data-stu-id="d71dd-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="d71dd-113">A Contoso permite que:</span><span class="sxs-lookup"><span data-stu-id="d71dd-113">Contoso allows:</span></span>

- <span data-ttu-id="d71dd-114">Clientes usem suas contas da Microsoft, Facebook ou Google Mail para entrar no site público da empresa.</span><span class="sxs-lookup"><span data-stu-id="d71dd-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="d71dd-115">Fornecedores e parceiros usem suas contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro da empresa.</span><span class="sxs-lookup"><span data-stu-id="d71dd-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="d71dd-116">Aqui está a DMZ da Contoso que contém um site público, uma extranet de parceiro e um conjunto de servidores dos Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="d71dd-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="d71dd-117">A DMZ está conectada à Internet que contém clientes, parceiros e serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="d71dd-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Suporte da Contoso para autenticação federada para clientes e parceiros](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="d71dd-119">Os servidores do AD FS na DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acessar o site público e as credenciais de parceiros para acessar a extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="d71dd-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="d71dd-120">A Contoso decidiu manter essa infraestrutura e dedicá-la à autenticação de clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="d71dd-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="d71dd-121">Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="d71dd-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="d71dd-122">Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem</span><span class="sxs-lookup"><span data-stu-id="d71dd-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="d71dd-123">A Contoso queria usar sua floresta local do AD DS para autenticação em recursos de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d71dd-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="d71dd-124">Ele decidiu usar a sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="d71dd-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="d71dd-125">O PHS sincroniza a floresta local do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 para empresas, copiando contas de usuário e grupo e uma versão com senhas de conta de usuário com código.</span><span class="sxs-lookup"><span data-stu-id="d71dd-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="d71dd-126">Para fazer a sincronização de diretórios, a Contoso implantou a ferramenta Azure AD Connect em um servidor em seu datacenter de Paris.</span><span class="sxs-lookup"><span data-stu-id="d71dd-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="d71dd-127">Aqui está o servidor que executa o Azure AD Connect sondando a floresta do AD DS da Contoso para alterações e sincronizando essas alterações com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d71dd-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![A infraestrutura de sincronização de diretórios PHS da Contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="d71dd-129">Políticas de Acesso Condicional para acesso de identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="d71dd-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="d71dd-130">A Contoso criou um conjunto de [políticas de Acesso Condicional](identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:</span><span class="sxs-lookup"><span data-stu-id="d71dd-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="d71dd-131">*As proteções* de linha de base se aplicam a todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="d71dd-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="d71dd-132">*Proteções* confidenciais se aplicam à liderança sênior e à equipe executiva.</span><span class="sxs-lookup"><span data-stu-id="d71dd-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="d71dd-133">*As proteções altamente* regulamentadas se aplicam a usuários específicos nos departamentos de finanças, jurídicos e de pesquisa que têm acesso a dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="d71dd-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="d71dd-134">Aqui está o conjunto resultante de políticas de Acesso Condicional de dispositivo e identidade da Contoso.</span><span class="sxs-lookup"><span data-stu-id="d71dd-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="d71dd-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d71dd-136">Next step</span></span>

<span data-ttu-id="d71dd-137">Saiba como a Contoso usa sua infraestrutura do Microsoft Endpoint Configuration Manager para implantar e manter [o Windows 10 Enterprise](contoso-win10.md) atual em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="d71dd-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="d71dd-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="d71dd-138">See also</span></span>

[<span data-ttu-id="d71dd-139">Mapa da identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d71dd-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="d71dd-140">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d71dd-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d71dd-141">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="d71dd-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
