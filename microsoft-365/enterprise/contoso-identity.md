---
title: Identidade para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece a autenticação baseada na nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.
ms.openlocfilehash: 7571aa455cac4da9e56d7d2001ae4421c3769c94
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865148"
---
# <a name="identity-for-the-contoso-corporation"></a><span data-ttu-id="46e8f-103">Identidade para a Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="46e8f-103">Identity for the Contoso Corporation</span></span>

<span data-ttu-id="46e8f-104">**Resumo:** como a Contoso tira proveito da Identidade como um Serviço (IDaaS) e fornece autenticação baseada em nuvem para seus funcionários e autenticação federada para seus clientes e parceiros.</span><span class="sxs-lookup"><span data-stu-id="46e8f-104">**Summary:** How Contoso takes advantage of Identity as a Service (IDaaS) and provides cloud-based authentication for its employees and federated authentication for its partners and customers.</span></span>

<span data-ttu-id="46e8f-p101">A Microsoft fornece IDaaS (Identidade como um Serviço) em suas ofertas de nuvem com o Azure Active Directory (AD). Para adotar o Microsoft 365 Enterprise, a solução de IDaaS da Contoso teve que aproveitar seu provedor de identidade local e ainda assim incluir autenticação federada com seus atuais provedores de identidade confiáveis de terceiros.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p101">Microsoft provides an Identity as a Service (IDaaS) across its cloud offerings with Azure Active Directory (AD). To adopt Microsoft 365 Enterprise, Contoso's IDaaS solution had to leverage their on-premises identity provider and still include federated authentication with their existing trusted, third-party identity providers.</span></span>

## <a name="contosos-windows-server-ad-forest"></a><span data-ttu-id="46e8f-107">Floresta do AD do Windows Server da Contoso</span><span class="sxs-lookup"><span data-stu-id="46e8f-107">Contoso's Windows Server AD forest</span></span>

<span data-ttu-id="46e8f-p102">A Contoso usa uma única floresta do AD (Active Directory) do Windows Server para contoso.com com sete subdomínios, um para cada região do mundo. A sede, os escritórios de hubs regionais e filiais contêm controladores de domínio para autenticação e autorização locais.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p102">Contoso uses a single Windows Server Active Directory (AD) forest for contoso.com with seven sub-domains, one for each region of the world. The headquarters, regional hub offices, and satellite offices contain domain controllers for local authentication and authorization.</span></span>

<span data-ttu-id="46e8f-110">A Figura 1 mostra a floresta da Contoso com domínios regionais para diferentes partes do mundo que possuem hubs regionais.</span><span class="sxs-lookup"><span data-stu-id="46e8f-110">Figure 1 shows the Contoso forest with regional domains for the different parts of the world that contain regional hubs.</span></span>

![](./media/contoso-identity/contoso-identity-fig1.png)
 
<span data-ttu-id="46e8f-111">**Figura 1: floresta e domínios da Contoso em todo o mundo**</span><span class="sxs-lookup"><span data-stu-id="46e8f-111">**Figure 1: Contoso's forest and domains worldwide**</span></span>

<span data-ttu-id="46e8f-112">A Contoso deseja usar as contas e os grupos na floresta contoso.com para autenticação e autorização dos respectivos aplicativos e cargas de trabalho baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="46e8f-112">Contoso wants to use the accounts and groups in the contoso.com forest for authentication and authorization for its cloud-based apps and workloads.</span></span>

## <a name="contosos-federated-authentication-infrastructure"></a><span data-ttu-id="46e8f-113">Infraestrutura de autenticação federada da Contoso</span><span class="sxs-lookup"><span data-stu-id="46e8f-113">Contoso's federated authentication infrastructure</span></span>

<span data-ttu-id="46e8f-114">A Contoso permite que:</span><span class="sxs-lookup"><span data-stu-id="46e8f-114">Contoso allows:</span></span>

- <span data-ttu-id="46e8f-115">Clientes usem as contas da Microsoft, Facebook ou Google Mail para entrar no site público.</span><span class="sxs-lookup"><span data-stu-id="46e8f-115">Customers to use their Microsoft, Facebook, or Google Mail accounts to sign in to their public web site.</span></span>
- <span data-ttu-id="46e8f-116">Fornecedores e parceiros usam as contas do LinkedIn, Salesforce ou Google Mail para entrar na extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="46e8f-116">Vendors and partners to use their LinkedIn, Salesforce, or Google Mail accounts to sign in to the partner extranet.</span></span>

<span data-ttu-id="46e8f-p103">A Figura 2 mostra a DMZ da Contoso, contendo um site público, uma extranet de parceiro e um conjunto de servidores dos Serviços de Federação do Active Directory (AD FS). A DMZ está conectada à Internet, onde estão os clientes, parceiros e serviços de Internet.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p103">Figure 2 shows the Contoso DMZ containing a public web site, a partner extranet, and a set of Active Directory Federation Services (AD FS) servers. The DMZ is connected to the Internet that contains customers, partners, and Internet services.</span></span>

![](./media/contoso-identity/contoso-identity-fig2.png)

<span data-ttu-id="46e8f-119">**Figura 2: suporte da Contoso para autenticação federada para clientes e parceiros**</span><span class="sxs-lookup"><span data-stu-id="46e8f-119">**Figure 2: Contoso's support for federated authentication for customers and partners**</span></span>
 
<span data-ttu-id="46e8f-120">Os servidores AD FS (Serviços de Federação do Active Directory) na DMZ autenticam as credenciais do cliente para acesso ao site público e as credenciais de parceiro para acesso à extranet do parceiro.</span><span class="sxs-lookup"><span data-stu-id="46e8f-120">AD FS servers in the DMZ authenticate customer credentials for access to the public web site and partner credentials for access to the partner extranet.</span></span>

<span data-ttu-id="46e8f-p104">A Contoso decidiu manter esta infraestrutura e dedicá-la a autenticações de parceiros e clientes. Os engenheiros de identidade da Contoso estão investigando a conversão desta infraestrutura para as soluções de [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p104">Contoso decided to keep this infrastructure and dedicate it to customer and partner authentications. Contoso identity engineers are investigating the conversion of this infrastructure to Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) and [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) solutions.</span></span>

## <a name="hybrid-identity-with-pass-through-authentication-for-cloud-based-authentication"></a><span data-ttu-id="46e8f-123">Identidade híbrida com autenticação de passagem para autenticação baseada em nuvem</span><span class="sxs-lookup"><span data-stu-id="46e8f-123">Hybrid identity with pass-through authentication for cloud-based authentication</span></span>

<span data-ttu-id="46e8f-p105">A Contoso queria aproveitar a floresta local do AD do Windows Server para autenticação nos recursos de nuvem do Microsoft 365. Ela decidiu usar autenticação de passagem (PTA) com sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="46e8f-p105">Contoso wanted to leverage its on-premises Windows Server AD forest for authentication to Microsoft 365 cloud resources. It decided on pass-through authentication (PTA) with password hash synchronization (PHS).</span></span>

### <a name="pta-authentication"></a><span data-ttu-id="46e8f-126">Autenticação PTA</span><span class="sxs-lookup"><span data-stu-id="46e8f-126">PTA authentication</span></span>

<span data-ttu-id="46e8f-p106">Para autenticação de credenciais de usuário, a Contoso está usando PTA. Quando um usuário da Contoso acessa recursos de nuvem, as credenciais que ele envia são passadas pelo Azure AD para um servidor que executa um Agente de Autenticação no datacenter sede da Contoso. Um desses servidores de Agente de Autenticação valida as credenciais de usuário em nome do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p106">For authentication of user credentials, Contoso is using PTA. When a Contoso user accesses a cloud-based resources, the credentials it sends are passed by Azure AD to a server running an Authentication Agent in the Contoso headquarters datacenter. One of these Authentication Agent servers validates the user credentials on behalf of Azure AD.</span></span>

<span data-ttu-id="46e8f-130">A Figura 3 mostra um conjunto de servidores na sede da Contoso executando o Agente de Autenticação, que processa solicitações de autenticação passadas para ele do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="46e8f-130">Figure 3 shows a set of servers in the Contoso headquarters running the Authentication Agent, which process authentication requests passed to it from Azure AD.</span></span> 

![](./media/contoso-identity/contoso-identity-fig3.png)
 
<span data-ttu-id="46e8f-131">**Figura 3: infraestrutura de autenticação de passagem da Contoso**</span><span class="sxs-lookup"><span data-stu-id="46e8f-131">**Figure 3: Contoso's pass-through authentication infrastructure**</span></span>

<span data-ttu-id="46e8f-132">A Contoso escolheu a autenticação de passagem para atender ao requisito de segurança no qual todas as tentativas de autenticação são avaliadas para alteração imediata a estados de conta de usuário, políticas de senha e horas de entrada na floresta local do AD do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="46e8f-132">Contoso chose PTA to fulfill its security requirement that all authentication attempts be evaluated for immediate changes to user account states, password policies, and sign-in hours made to the on-premises Windows Server AD forest.</span></span>

### <a name="phs"></a><span data-ttu-id="46e8f-133">PHS</span><span class="sxs-lookup"><span data-stu-id="46e8f-133">PHS</span></span>

<span data-ttu-id="46e8f-p107">A PHS sincroniza a floresta do AD do Windows Server local com o locatário do Azure AD da assinatura do Microsoft 365 Enterprise, copiando contas de usuário e grupo e uma versão de hash de senhas da conta. A Contoso decidiu usar a PHS para oferecer um método alternativo de autenticação diretamente com o locatário do Azure AD, caso esse PTA não esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p107">PHS synchronizes the on-premises Windows Server AD forest with the Azure AD tenant of their Microsoft 365 Enterprise subscription, copying user and group accounts and a hashed version of user account passwords. Contoso decided on PHS to provide an alternate method of authentication directly with the Azure AD tenant in the event that PTA is not available.</span></span>

<span data-ttu-id="46e8f-p108">Para executar a sincronização de diretório contínua, a Contoso implantou a ferramenta Azure AD Connect em um servidor no seu datacenter em Paris. A Figura 4 mostra o servidor que executa o Azure AD Connect sondando a floresta do AD do Windows Server da Contoso para procurar alterações e sincronizá-las com o locatário do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="46e8f-p108">To perform the ongoing directory synchronization, Contoso has deployed the Azure AD Connect tool on a server in its Paris datacenter. Figure 4 shows the server running Azure AD Connect polling the Contoso Windows Server AD forest for changes and then synchronizing those changes with the Azure AD tenant.</span></span>

![](./media/contoso-identity/contoso-identity-fig4.png)
 
<span data-ttu-id="46e8f-138">**Figura 4: infraestrutura PHS de sincronização de diretórios da Contoso**</span><span class="sxs-lookup"><span data-stu-id="46e8f-138">**Figure 4: Contoso's PHS directory synchronization infrastructure**</span></span>

## <a name="conditional-access-policies-for-identity"></a><span data-ttu-id="46e8f-139">Políticas de acesso condicional para identidade</span><span class="sxs-lookup"><span data-stu-id="46e8f-139">Conditional access policies for identity</span></span>

<span data-ttu-id="46e8f-140">A Contoso criou um conjunto de [políticas de acesso condicional](identity-access-policies.md) do Azure AD para garantir que a autenticação multifator e as alterações de senha sejam impostas quando o Azure AD determinar que há risco de entrada para uma solicitação de autenticação.</span><span class="sxs-lookup"><span data-stu-id="46e8f-140">Contoso created a set of Azure AD [conditional access policies](identity-access-policies.md) to ensure that multi-factor authentication and password changes are enforced when Azure AD determines there is sign-in risk for an authentication request.</span></span>

<span data-ttu-id="46e8f-141">A Figura 5 mostra o conjunto de políticas de acesso condicional para identidade resultante.</span><span class="sxs-lookup"><span data-stu-id="46e8f-141">Figure 5 shows their resulting set of conditional access policies for identity.</span></span>

![](./media/contoso-identity/contoso-identity-fig5.png)
 
<span data-ttu-id="46e8f-142">**Figura 5: políticas de acesso condicional baseado em identidade da Contoso**</span><span class="sxs-lookup"><span data-stu-id="46e8f-142">**Figure 5: Contoso’s identity-based conditional access policies**</span></span>

## <a name="next-step"></a><span data-ttu-id="46e8f-143">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="46e8f-143">Next step</span></span>

<span data-ttu-id="46e8f-144">[Saiba](contoso-win10.md) mais sobre como a Contoso utiliza a infraestrutura do System Center Configuration Manager para implantar e manter o Windows 10 Enterprise atualizado em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="46e8f-144">[Learn](contoso-win10.md) how Contoso is leveraging its System Center Configuration Manager infrastructure to deploy and keep current Windows 10 Enterprise across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="46e8f-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="46e8f-145">See also</span></span>

[<span data-ttu-id="46e8f-146">Identidade para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="46e8f-146">Identity for Microsoft 365 Enterprise</span></span>](identity-infrastructure.md)

[<span data-ttu-id="46e8f-147">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="46e8f-147">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="46e8f-148">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="46e8f-148">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
