---
title: Identidade híbrida e sincronização de diretórios para o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 06/09/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Descreve a sincronização de diretórios com o Microsoft 365, limpeza de serviços de domínio do Active Directory e a ferramenta Azure Active Directory Connect.
ms.openlocfilehash: 2d3161fb835073a22743ea4f3b00ac508479f0f2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687171"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="9023b-103">Identidade híbrida e sincronização de diretórios para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9023b-103">Hybrid identity and directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="9023b-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="9023b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="9023b-105">Dependendo das necessidades de negócios e dos requisitos técnicos, o modelo de identidade híbrida e a sincronização de diretórios é a opção mais comum para clientes corporativos que estão adotando o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-105">Depending on your business needs and technical requirements, the hybrid identity model and directory synchronization is the most common choice for enterprise customers who are adopting Microsoft 365.</span></span> <span data-ttu-id="9023b-106">A sincronização de diretórios permite gerenciar identidades em seus serviços de domínio do Active Directory (AD DS) e todas as atualizações de contas de usuário, grupos e contatos são sincronizadas com o locatário do Azure Active Directory (Azure AD) de sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-106">Directory synchronization allows you to manage identities in your Active Directory Domain Services (AD DS) and all updates to user accounts, groups, and contacts are synchronized to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span>

>[!Note]
><span data-ttu-id="9023b-107">Quando as contas de usuário do AD DS são sincronizadas pela primeira vez, elas não recebem automaticamente uma licença do Microsoft 365 e não podem acessar os serviços do Microsoft 365, como email.</span><span class="sxs-lookup"><span data-stu-id="9023b-107">When AD DS user accounts are synchronized for the first time, they are not automatically assigned a Microsoft 365 license and cannot access Microsoft 365 services, such as email.</span></span> <span data-ttu-id="9023b-108">Primeiro você deve atribuir um local de uso a eles.</span><span class="sxs-lookup"><span data-stu-id="9023b-108">You must first assign them a usage location.</span></span> <span data-ttu-id="9023b-109">Em seguida, atribua uma licença a essas contas de usuário, individualmente ou dinamicamente por meio da Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="9023b-109">Then, assign a license to these user accounts, either individually or dynamically through group membership.</span></span>
>

## <a name="authentication-for-hybrid-identity"></a><span data-ttu-id="9023b-110">Autenticação para identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="9023b-110">Authentication for hybrid identity</span></span>

<span data-ttu-id="9023b-111">Há dois tipos de autenticação ao usar o modelo de identidade híbrida:</span><span class="sxs-lookup"><span data-stu-id="9023b-111">There are two types of authentication when using the hybrid identity model:</span></span>

- <span data-ttu-id="9023b-112">Autenticação gerenciada</span><span class="sxs-lookup"><span data-stu-id="9023b-112">Managed authentication</span></span>

  <span data-ttu-id="9023b-113">O Azure AD lida com o processo de autenticação usando uma versão de hash armazenada localmente da senha ou envia as credenciais para um agente de software local para ser autenticado pelo AD DS local.</span><span class="sxs-lookup"><span data-stu-id="9023b-113">Azure AD handles the authentication process by using a locally-stored hashed version of the password or sends the credentials to an on-premises software agent to be authenticated by the on-premises AD DS.</span></span>

- <span data-ttu-id="9023b-114">Autenticação federada</span><span class="sxs-lookup"><span data-stu-id="9023b-114">Federated authentication</span></span>

  <span data-ttu-id="9023b-115">O Azure AD redireciona o computador cliente solicitando autenticação para outro provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="9023b-115">Azure AD redirects the client computer requesting authentication to another identity provider.</span></span>

### <a name="managed-authentication"></a><span data-ttu-id="9023b-116">Autenticação gerenciada</span><span class="sxs-lookup"><span data-stu-id="9023b-116">Managed authentication</span></span>

<span data-ttu-id="9023b-117">Há dois tipos de autenticação gerenciada:</span><span class="sxs-lookup"><span data-stu-id="9023b-117">There are two types of managed authentication:</span></span>

- <span data-ttu-id="9023b-118">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="9023b-118">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="9023b-119">O Azure AD realiza a própria autenticação.</span><span class="sxs-lookup"><span data-stu-id="9023b-119">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="9023b-120">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="9023b-120">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="9023b-121">O Azure AD faz o AD DS executar a autenticação.</span><span class="sxs-lookup"><span data-stu-id="9023b-121">Azure AD has AD DS perform the authentication.</span></span>


#### <a name="password-hash-synchronization-phs"></a><span data-ttu-id="9023b-122">Sincronização de hash de senha (PHS)</span><span class="sxs-lookup"><span data-stu-id="9023b-122">Password hash synchronization (PHS)</span></span>

<span data-ttu-id="9023b-123">Com o PHS, você sincroniza suas contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local.</span><span class="sxs-lookup"><span data-stu-id="9023b-123">With PHS, you synchronize your AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> <span data-ttu-id="9023b-124">Hashes de senhas de usuário são sincronizados do AD DS para o Azure AD para que os usuários tenham a mesma senha no local e na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9023b-124">Hashes of user passwords are synchronized from your AD DS to Azure AD so that the users have the same password on-premises and in the cloud.</span></span> <span data-ttu-id="9023b-125">Essa é a maneira mais simples de habilitar a autenticação para identidades do AD DS no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9023b-125">This is the simplest way to enable authentication for AD DS identities in Azure AD.</span></span> 

![Sincronização de hash de senha (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

<span data-ttu-id="9023b-127">Quando as senhas são alteradas ou redefinidas no local, os novos hashes de senha são sincronizados com o Azure AD para que os usuários sempre possam usar a mesma senha para recursos de nuvem e recursos locais.</span><span class="sxs-lookup"><span data-stu-id="9023b-127">When passwords are changed or reset on-premises, the new password hashes are synchronized to Azure AD so that your users can always use the same password for cloud resources and on-premises resources.</span></span> <span data-ttu-id="9023b-128">As senhas do usuário nunca são enviadas para o Azure AD ou armazenadas no Azure AD em texto não criptografado.</span><span class="sxs-lookup"><span data-stu-id="9023b-128">The user passwords are never sent to Azure AD or stored in Azure AD in clear text.</span></span> <span data-ttu-id="9023b-129">Alguns recursos premium do Azure AD, como proteção de identidade, exigem PHS independentemente do método de autenticação selecionado.</span><span class="sxs-lookup"><span data-stu-id="9023b-129">Some premium features of Azure AD, such as Identity Protection, require PHS regardless of which authentication method is selected.</span></span>
  
<span data-ttu-id="9023b-130">Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9023b-130">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="pass-through-authentication-pta"></a><span data-ttu-id="9023b-131">Autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="9023b-131">Pass-through authentication (PTA)</span></span>

<span data-ttu-id="9023b-132">O PTA fornece uma validação de senha simples para os serviços de autenticação do Azure AD usando um agente de software em execução em um ou mais servidores locais para validar os usuários diretamente com o AD DS.</span><span class="sxs-lookup"><span data-stu-id="9023b-132">PTA provides a simple password validation for Azure AD authentication services using a software agent running on one or more on-premises servers to validate the users directly with your AD DS.</span></span> <span data-ttu-id="9023b-133">Com o PTA, você sincroniza contas de usuário do AD DS com o Microsoft 365 e gerencia seus usuários no local.</span><span class="sxs-lookup"><span data-stu-id="9023b-133">With PTA, you synchronize AD DS user accounts with Microsoft 365 and manage your users on-premises.</span></span> 

![Autenticação de passagem (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

<span data-ttu-id="9023b-135">O PTA permite que os usuários entrem em recursos e aplicativos locais e do Microsoft 365 usando sua conta e senha local.</span><span class="sxs-lookup"><span data-stu-id="9023b-135">PTA allows your users to sign in to both on-premises and Microsoft 365 resources and applications using their on-premises account and password.</span></span> <span data-ttu-id="9023b-136">Essa configuração valida senhas de usuários diretamente em seu AD DS local sem armazenar hashes de senha no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9023b-136">This configuration validates users passwords directly against your on-premises AD DS without storing password hashes in Azure AD.</span></span> 

<span data-ttu-id="9023b-137">PTA também é para organizações com um requisito de segurança para impor imediatamente os Estados de conta de usuário local, as diretivas de senha e o horário de logon.</span><span class="sxs-lookup"><span data-stu-id="9023b-137">PTA is also for organizations with a security requirement to immediately enforce on-premises user account states, password policies, and logon hours.</span></span> 
  
<span data-ttu-id="9023b-138">Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9023b-138">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
### <a name="federated-authentication"></a><span data-ttu-id="9023b-139">Autenticação federada</span><span class="sxs-lookup"><span data-stu-id="9023b-139">Federated authentication</span></span>

<span data-ttu-id="9023b-140">A autenticação federada é principalmente para grandes organizações corporativas com requisitos de autenticação mais complexos.</span><span class="sxs-lookup"><span data-stu-id="9023b-140">Federated authentication is primarily for large enterprise organizations with more complex authentication requirements.</span></span> <span data-ttu-id="9023b-141">As identidades do AD DS são sincronizadas com o Microsoft 365 e as contas de usuários são gerenciadas no local.</span><span class="sxs-lookup"><span data-stu-id="9023b-141">AD DS identities are synchronized with Microsoft 365 and users accounts are managed on-premises.</span></span> <span data-ttu-id="9023b-142">Com a autenticação federada, os usuários têm a mesma senha no local e na nuvem, e não precisam entrar novamente para usar o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-142">With federated authentication, users have the same password on-premises and in the cloud and they do not have to sign in again to use Microsoft 365.</span></span> 

<span data-ttu-id="9023b-143">A autenticação federada pode dar suporte a requisitos de autenticação adicionais, como a autenticação com base em Smartcard ou uma autenticação multifator de terceiros e geralmente é necessária quando as organizações têm um requisito de autenticação não suportado nativamente pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9023b-143">Federated authentication can support additional authentication requirements, such as smartcard-based authentication or a third-party multi-factor authentication and is typically required when organizations have an authentication requirement not natively supported by Azure AD.</span></span>
 
<span data-ttu-id="9023b-144">Consulte [escolher o método de autenticação certo](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9023b-144">See [choosing the right authentication method](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) to learn more.</span></span>
  
#### <a name="third-party-authentication-and-identity-providers"></a><span data-ttu-id="9023b-145">Provedores de autenticação e identidade de terceiros</span><span class="sxs-lookup"><span data-stu-id="9023b-145">Third-party authentication and identity providers</span></span>

<span data-ttu-id="9023b-146">Os objetos de diretório no local podem ser sincronizados com o Microsoft 365 e o acesso a recursos em nuvem é basicamente gerenciado por um provedor de identidade de terceiros (IdP).</span><span class="sxs-lookup"><span data-stu-id="9023b-146">On-premises directory objects may be synchronized to Microsoft 365 and cloud resource access is primarily managed by a third-party identity provider (IdP).</span></span> <span data-ttu-id="9023b-147">Se sua organização usa uma solução de Federação de terceiros, você pode configurar o logon com essa solução para o Microsoft 365, desde que a solução de Federação de terceiros seja compatível com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9023b-147">If your organization uses a third-party federation solution, you can configure sign-on with that solution for Microsoft 365 provided that the third-party federation solution is compatible with Azure AD.</span></span>
  
<span data-ttu-id="9023b-148">Consulte a [lista de compatibilidade de Federação do Azure ad](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9023b-148">See the [Azure AD federation compatibility list](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) to learn more.</span></span>
  
## <a name="ad-ds-preparation"></a><span data-ttu-id="9023b-149">Preparação do AD DS</span><span class="sxs-lookup"><span data-stu-id="9023b-149">AD DS Preparation</span></span>

<span data-ttu-id="9023b-150">Para ajudar a garantir uma transição contínua para o Microsoft 365 usando a sincronização, você deve preparar sua floresta do AD DS antes de começar sua implantação de sincronização de diretório do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-150">To help ensure a seamless transition to Microsoft 365 by using synchronization, you must prepare your AD DS forest before you begin your Microsoft 365 directory synchronization deployment.</span></span>
  
<span data-ttu-id="9023b-151">A preparação do diretório deve se concentrar nas seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9023b-151">Your directory preparation should focus on the following tasks:</span></span>

- <span data-ttu-id="9023b-152">Remover os atributos **ProxyAddress** e **userPrincipalName** duplicados.</span><span class="sxs-lookup"><span data-stu-id="9023b-152">Remove duplicate **proxyAddress** and **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="9023b-153">Atualizar atributos **userPrincipalName** em branco e inválidos com atributos **userPrincipalName** válidos.</span><span class="sxs-lookup"><span data-stu-id="9023b-153">Update blank and invalid **userPrincipalName** attributes with valid **userPrincipalName** attributes.</span></span>
- <span data-ttu-id="9023b-154">Remover caracteres inválidos e questionáveis nos atributos **repassado**, sobrenome ( **SN** ), **sAMAccountName**, **DisplayName**, **mail**, **proxyAddresses**, **mailNickname**e **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="9023b-154">Remove invalid and questionable characters in the **givenName**, surname ( **sn** ), **sAMAccountName**, **displayName**, **mail**, **proxyAddresses**, **mailNickname**, and **userPrincipalName** attributes.</span></span> <span data-ttu-id="9023b-155">Para obter detalhes sobre como preparar atributos, consulte [lista de atributos que são sincronizados pela ferramenta de sincronização do Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span><span class="sxs-lookup"><span data-stu-id="9023b-155">For details about preparing attributes, see [List of attributes that are synced by the Azure Active Directory Sync Tool](https://go.microsoft.com/fwlink/p/?LinkId=396719).</span></span>

    > [!NOTE]
    > <span data-ttu-id="9023b-156">Estes são os mesmos atributos que o Azure AD Connect sincroniza.</span><span class="sxs-lookup"><span data-stu-id="9023b-156">These are the same attributes that Azure AD Connect synchronizes.</span></span> 
  
## <a name="multi-forest-deployment-considerations"></a><span data-ttu-id="9023b-157">Considerações de implantação de várias florestas</span><span class="sxs-lookup"><span data-stu-id="9023b-157">Multi-forest deployment considerations</span></span>

<span data-ttu-id="9023b-158">Para várias florestas e opções de SSO, use uma [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span><span class="sxs-lookup"><span data-stu-id="9023b-158">For multiple forests and SSO options, use a [Custom Installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkId=698430).</span></span>
  
<span data-ttu-id="9023b-159">Se sua organização tiver várias florestas para autenticação (florestas de logon), recomendamos enfaticamente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9023b-159">If your organization has multiple forests for authentication (logon forests), we highly recommend the following:</span></span>
  
- <span data-ttu-id="9023b-160">**Considere a consolidação de suas florestas.**</span><span class="sxs-lookup"><span data-stu-id="9023b-160">**Consider consolidating your forests.**</span></span> <span data-ttu-id="9023b-161">Em geral, há mais sobrecarga necessária para manter várias florestas.</span><span class="sxs-lookup"><span data-stu-id="9023b-161">In general, there's more overhead required to maintain multiple forests.</span></span> <span data-ttu-id="9023b-162">A menos que sua organização tenha restrições de segurança que ditem a necessidade de florestas separadas, considere simplificar o ambiente local.</span><span class="sxs-lookup"><span data-stu-id="9023b-162">Unless your organization has security constraints that dictate the need for separate forests, consider simplifying your on-premises environment.</span></span>
- <span data-ttu-id="9023b-163">**Use somente na floresta de logon principal.**</span><span class="sxs-lookup"><span data-stu-id="9023b-163">**Use only in your primary logon forest.**</span></span> <span data-ttu-id="9023b-164">Considere a implantação do Microsoft 365 somente em sua floresta de logon principal para a sua distribuição inicial do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-164">Consider deploying Microsoft 365 only in your primary logon forest for your initial rollout of Microsoft 365.</span></span> 

<span data-ttu-id="9023b-165">Se você não puder consolidar sua implantação do AD DS de várias florestas ou se estiver usando outros serviços de diretório para gerenciar identidades, talvez seja possível sincronizá-las com a ajuda da Microsoft ou de um parceiro.</span><span class="sxs-lookup"><span data-stu-id="9023b-165">If you can't consolidate your multi-forest AD DS deployment or are using other directory services to manage identities, you may be able to synchronize these with the help of Microsoft or a partner.</span></span>
  
<span data-ttu-id="9023b-166">Consulte [topologias para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9023b-166">See [Topologies for Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies) for more information.</span></span>
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a><span data-ttu-id="9023b-167">Recursos que dependem da sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="9023b-167">Features that are dependent on directory synchronization</span></span>
  
<span data-ttu-id="9023b-168">A sincronização de diretórios é necessária para os seguintes recursos e funcionalidade:</span><span class="sxs-lookup"><span data-stu-id="9023b-168">Directory synchronization is required for the following features and functionality:</span></span>
  
- <span data-ttu-id="9023b-169">Logon único (SSO) contínuo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="9023b-169">Azure AD Seamless Single Sign-On (SSO)</span></span>
- <span data-ttu-id="9023b-170">Coexistência do Skype</span><span class="sxs-lookup"><span data-stu-id="9023b-170">Skype coexistence</span></span>
- <span data-ttu-id="9023b-171">Implantação híbrida do Exchange, incluindo:</span><span class="sxs-lookup"><span data-stu-id="9023b-171">Exchange hybrid deployment, including:</span></span>
  - <span data-ttu-id="9023b-172">GAL (lista de endereços global) totalmente compartilhada entre o seu ambiente do Exchange local e o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-172">Fully shared global address list (GAL) between your on-premises Exchange environment and Microsoft 365.</span></span>
  - <span data-ttu-id="9023b-173">Sincronizar informação de GAL de sistemas de email diferentes.</span><span class="sxs-lookup"><span data-stu-id="9023b-173">Synchronizing GAL information from different mail systems.</span></span>
  - <span data-ttu-id="9023b-174">A capacidade de adicionar usuários e remover usuários das ofertas de serviço do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-174">The ability to add users to and remove users from Microsoft 365 service offerings.</span></span> <span data-ttu-id="9023b-175">Isto exige o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9023b-175">This requires the following:</span></span>
  - <span data-ttu-id="9023b-176">A sincronização bidirecional deve ser configurada durante a configuração de sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="9023b-176">Two-way synchronization must be configured during directory synchronization setup.</span></span> <span data-ttu-id="9023b-177">Por padrão, as ferramentas de sincronização de diretório gravam informações de diretório somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9023b-177">By default, directory synchronization tools write directory information only to the cloud.</span></span> <span data-ttu-id="9023b-178">Ao configurar a sincronização bidirecional, você habilita a funcionalidade de write-back para que um número limitado de atributos de objeto seja copiado da nuvem e, em seguida, os escreveu novamente no AD DS local.</span><span class="sxs-lookup"><span data-stu-id="9023b-178">When you configure two-way synchronization, you enable write-back functionality so that a limited number of object attributes are copied from the cloud, and then written them back to your local AD DS.</span></span> <span data-ttu-id="9023b-179">O Write-back também é conhecido como modo híbrido do Exchange.</span><span class="sxs-lookup"><span data-stu-id="9023b-179">Write-back is also referred to as Exchange hybrid mode.</span></span> 
  - <span data-ttu-id="9023b-180">Uma implantação híbrida local do Exchange</span><span class="sxs-lookup"><span data-stu-id="9023b-180">An on-premises Exchange hybrid deployment</span></span>
  - <span data-ttu-id="9023b-181">A capacidade de mover algumas caixas de correio do usuário para a Microsoft 365 enquanto mantém outras caixas de correio do usuário no local.</span><span class="sxs-lookup"><span data-stu-id="9023b-181">The ability to move some user mailboxes to Microsoft 365 while keeping other user mailboxes on-premises.</span></span>
  - <span data-ttu-id="9023b-182">Remetentes confiáveis e remetentes bloqueados no local são replicados para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9023b-182">Safe senders and blocked senders on-premises are replicated to Microsoft 365.</span></span>
  - <span data-ttu-id="9023b-183">Delegação básica e funcionalidade de email enviar em nome de.</span><span class="sxs-lookup"><span data-stu-id="9023b-183">Basic delegation and send-on-behalf-of email functionality.</span></span>
  - <span data-ttu-id="9023b-184">Você tem uma solução integrada de cartão inteligente ou de autenticação multifator no local.</span><span class="sxs-lookup"><span data-stu-id="9023b-184">You have an integrated on-premises smart card or multi-factor authentication solution.</span></span>
- <span data-ttu-id="9023b-185">Sincronização de fotos, miniaturas, salas de conferência e grupos de segurança</span><span class="sxs-lookup"><span data-stu-id="9023b-185">Synchronization of photos, thumbnails, conference rooms, and security groups</span></span>

## <a name="next-step"></a><span data-ttu-id="9023b-186">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9023b-186">Next step</span></span>

<span data-ttu-id="9023b-187">Quando estiver pronto para implantar a identidade híbrida, confira [preparar para provisionar usuários](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="9023b-187">When you are ready to deploy hybrid identity, see [prepare to provision users](prepare-for-directory-synchronization.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9023b-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="9023b-188">See also</span></span>

[<span data-ttu-id="9023b-189">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9023b-189">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)

