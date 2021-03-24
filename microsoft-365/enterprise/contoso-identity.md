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
ms.openlocfilehash: f3c8746345683652ce601400ae7297e96fff2ee3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051515"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="b8ceb-103">Identidade para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="b8ceb-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="b8ceb-104">A Microsoft fornece Identidade como Serviço (IDaaS) em suas ofertas de nuvem por meio do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b8ceb-104">Microsoft provides Identity as a Service (IDaaS) across its cloud offerings through Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b8ceb-105">Para adotar o Microsoft 365 para empresas, a solução contoso IDaaS precisava usar seu provedor de identidade local e incluir a autenticação federada com seus provedores de identidade confiáveis e de terceiros existentes.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-105">To adopt Microsoft 365 for enterprise, the Contoso IDaaS solution had to use their on-premises identity provider and include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="the-contoso-active-directory-domain-services-forest"></a><span data-ttu-id="b8ceb-106">Floresta dos Serviços de Domínio do Active Directory da Contoso</span><span class="sxs-lookup"><span data-stu-id="b8ceb-106">The Contoso Active Directory Domain Services forest</span></span>

<span data-ttu-id="b8ceb-107">A Contoso usa uma única floresta dos Serviços de Domínio do Active Directory (AD DS) para contoso com sete subdomas, um para cada \. região do mundo.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-107">Contoso uses a single Active Directory Domain Services (AD DS) forest for contoso\.com with seven subdomains, one for each region of the world.</span></span> <span data-ttu-id="b8ceb-108">A sede, escritórios de hub regionais e escritórios satélite contêm controladores de domínio para autenticação e autorização local.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-108">The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="b8ceb-109">Aqui está a floresta Contoso com domínios regionais para as diferentes partes do mundo que contêm hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-109">Here's the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![Floresta e domínios da Contoso em todo o mundo](../media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="b8ceb-111">A Contoso decidiu usar as contas e grupos na floresta contoso com para autenticação e autorização para suas cargas de trabalho e serviços \. do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-111">Contoso decided to use the accounts and groups in the contoso\.com forest for authentication and authorization for its Microsoft 365 workloads and services.</span></span>

## <a name="the-contoso-federated-authentication-infrastructure"></a><span data-ttu-id="b8ceb-112">A infraestrutura de autenticação federada da Contoso</span><span class="sxs-lookup"><span data-stu-id="b8ceb-112">The Contoso federated authentication infrastructure</span></span>

<span data-ttu-id="b8ceb-113">A Contoso permite que:</span><span class="sxs-lookup"><span data-stu-id="b8ceb-113">Contoso allows:</span></span>

- <span data-ttu-id="b8ceb-114">Os clientes usam suas contas microsoft, Facebook ou Google Mail para entrar no site público da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-114">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to the company's public web site.</span></span>
- <span data-ttu-id="b8ceb-115">Fornecedores e parceiros para usar suas contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-115">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the company's partner extranet.</span></span>

<span data-ttu-id="b8ceb-116">Aqui está o DMZ da Contoso que contém um site público, uma extranet de parceiro e um conjunto de servidores do AD FS (Serviços de Federação do Active Directory).</span><span class="sxs-lookup"><span data-stu-id="b8ceb-116">Here's the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers.</span></span> <span data-ttu-id="b8ceb-117">O DMZ está conectado à Internet que contém clientes, parceiros e serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-117">The DMZ is connected to the internet that contains customers, partners, and internet services.</span></span>

![Suporte da Contoso para autenticação federada para clientes e parceiros](../media/contoso-identity/contoso-identity-fig2.png)
 
<span data-ttu-id="b8ceb-119">Os servidores do AD FS no DMZ facilitam a autenticação de credenciais do cliente por seus provedores de identidade para acesso ao site público e credenciais de parceiro para acesso à extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-119">AD FS servers in the DMZ facilitate authentication of customer credentials by their identity providers for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="b8ceb-120">A Contoso decidiu manter essa infraestrutura e dedicá-la à autenticação de clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-120">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentication.</span></span> <span data-ttu-id="b8ceb-121">Os arquitetos de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções do Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) e [B2C](/azure/active-directory-b2c/solution-articles).</span><span class="sxs-lookup"><span data-stu-id="b8ceb-121">Contoso identity architects are investigating the conversion of this infrastructure to Azure AD [B2B](/azure/active-directory/b2b/hybrid-organizations) and [B2C](/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a><span data-ttu-id="b8ceb-122">Identidade híbrida com sincronização de hash de senha para autenticação baseada na nuvem</span><span class="sxs-lookup"><span data-stu-id="b8ceb-122">Hybrid identity with password hash synchronization for cloud-based authentication</span></span>

<span data-ttu-id="b8ceb-123">A Contoso queria usar sua floresta local do AD DS para autenticação aos recursos de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-123">Contoso wanted to use its on-premises AD DS forest for authentication to Microsoft 365 cloud resources.</span></span> <span data-ttu-id="b8ceb-124">Ele decidiu usar a sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="b8ceb-124">It decided to use password hash synchronization (PHS).</span></span>

<span data-ttu-id="b8ceb-125">O PHS sincroniza a floresta local do AD DS com o locatário do Azure AD de sua assinatura do Microsoft 365 para empresas, copiando contas de usuário e grupo e uma versão com controle de senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-125">PHS synchronizes the on-premises AD DS forest with the Azure AD tenant of their Microsoft 365 for enterprise subscription, copying user and group accounts and a hashed version of user account passwords.</span></span>

<span data-ttu-id="b8ceb-126">Para fazer a sincronização de diretórios, a Contoso implantou a ferramenta do Azure AD Connect em um servidor em seu datacenter de Paris.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-126">To do directory synchronization, Contoso deployed the Azure AD Connect tool on a server in its Paris datacenter.</span></span>

<span data-ttu-id="b8ceb-127">Aqui está o servidor executando o Azure AD Connect sondando a floresta contoso AD DS para alterações e, em seguida, sincronizando essas alterações com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-127">Here's the server running Azure AD Connect polling the Contoso AD DS forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![A infraestrutura de sincronização de diretórios PHS contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a><span data-ttu-id="b8ceb-129">Políticas de Acesso Condicional para acesso de identidades e dispositivos</span><span class="sxs-lookup"><span data-stu-id="b8ceb-129">Conditional Access policies for identity and device access</span></span>

<span data-ttu-id="b8ceb-130">A Contoso criou um conjunto de [políticas de Acesso Condicional](../security/defender-365-security/identity-access-policies.md) do Azure AD e Intune para três níveis de proteção:</span><span class="sxs-lookup"><span data-stu-id="b8ceb-130">Contoso created a set of Azure AD and Intune [Conditional Access policies](../security/defender-365-security/identity-access-policies.md) for three protection levels:</span></span>

- <span data-ttu-id="b8ceb-131">*As* proteções de linha de base se aplicam a todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-131">*Baseline* protections apply to all user accounts.</span></span>
- <span data-ttu-id="b8ceb-132">*Proteções* confidenciais se aplicam à liderança sênior e à equipe executiva.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-132">*Sensitive* protections apply to senior leadership and executive staff.</span></span>
- <span data-ttu-id="b8ceb-133">*Proteções altamente regulamentadas* se aplicam a usuários específicos nos departamentos de finanças, jurídicos e de pesquisa que têm acesso a dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-133">*Highly Regulated* protections apply to specific users in the finance, legal, and research departments who have access to highly regulated data.</span></span>

<span data-ttu-id="b8ceb-134">Aqui está o conjunto resultante de políticas de Acesso Condicional da Contoso e identidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-134">Here's the resulting set of Contoso identity and device Conditional Access policies.</span></span>

![Políticas de Acesso Condicional de identidades e dispositivos da Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a><span data-ttu-id="b8ceb-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b8ceb-136">Next step</span></span>

<span data-ttu-id="b8ceb-137">Saiba como a Contoso usa sua infraestrutura do Microsoft Endpoint Configuration Manager para implantar e manter o [Windows 10 Enterprise](contoso-win10.md) atual em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b8ceb-137">Learn how Contoso uses its Microsoft Endpoint Configuration Manager infrastructure to [deploy and keep current Windows 10 Enterprise](contoso-win10.md) across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8ceb-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="b8ceb-138">See also</span></span>

[<span data-ttu-id="b8ceb-139">Mapa da identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b8ceb-139">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="b8ceb-140">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b8ceb-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b8ceb-141">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="b8ceb-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)