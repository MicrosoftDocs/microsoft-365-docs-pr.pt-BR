---
title: Gerenciar Microsoft 365 senhas de conta de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Saiba mais sobre como gerenciar Microsoft 365 senhas de conta de usuário.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905087"
---
# <a name="manage-microsoft-365-user-account-passwords"></a><span data-ttu-id="b0941-103">Gerenciar Microsoft 365 senhas de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b0941-103">Manage Microsoft 365 user account passwords</span></span>

<span data-ttu-id="b0941-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b0941-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b0941-105">Você pode gerenciar Microsoft 365 senhas de conta de usuário de várias maneiras diferentes, dependendo de sua configuração de identidade.</span><span class="sxs-lookup"><span data-stu-id="b0941-105">You can manage Microsoft 365 user account passwords in several different ways, depending on your identity configuration.</span></span> <span data-ttu-id="b0941-106">Você pode gerenciar contas de usuário no centro de administração do Microsoft 365 [,](../admin/add-users/index.yml)nos Serviços de Domínio do Active Directory (AD DS) ou no centro de administração Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b0941-106">You can manage user accounts in the [Microsoft 365 admin center](../admin/add-users/index.yml), in Active Directory Domain Services (AD DS), or in the Azure Active Directory (Azure AD) admin center.</span></span>

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a><span data-ttu-id="b0941-107">Planejar onde e como você gerenciará suas senhas de conta de usuário</span><span class="sxs-lookup"><span data-stu-id="b0941-107">Plan for where and how you will manage your user account passwords</span></span>

<span data-ttu-id="b0941-108">Onde e como você pode gerenciar suas contas de usuário depende do modelo de identidade que você deseja usar para sua Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0941-108">Where and how you can manage your user accounts depends on the identity model you want to use for your Microsoft 365.</span></span> <span data-ttu-id="b0941-109">Os dois modelos são somente na nuvem e híbridos.</span><span class="sxs-lookup"><span data-stu-id="b0941-109">The two models are cloud-only and hybrid.</span></span>
  
### <a name="cloud-only"></a><span data-ttu-id="b0941-110">Apenas Nuvem</span><span class="sxs-lookup"><span data-stu-id="b0941-110">Cloud-only</span></span>

<span data-ttu-id="b0941-111">Você gerencia senhas de conta de usuário em:</span><span class="sxs-lookup"><span data-stu-id="b0941-111">You manage user account passwords in:</span></span>

- [<span data-ttu-id="b0941-112">O Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0941-112">The Microsoft 365 admin center</span></span>](../admin/add-users/index.yml)
- <span data-ttu-id="b0941-113">Centro de administração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b0941-113">The Azure AD admin center</span></span>
    
### <a name="hybrid"></a><span data-ttu-id="b0941-114">Híbrido</span><span class="sxs-lookup"><span data-stu-id="b0941-114">Hybrid</span></span>

<span data-ttu-id="b0941-115">Com a identidade híbrida, as senhas são armazenadas no AD DS, portanto, você deve usar as ferramentas locais do AD DS para gerenciar senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b0941-115">With hybrid identity, passwords are stored in AD DS so you must use on-premises AD DS tools to manage user account passwords.</span></span> <span data-ttu-id="b0941-116">Mesmo ao usar a Sincronização de Hash de Senha (PHS), na qual o Azure AD armazena uma versão com hash da versão já com hash no AD DS, você e os usuários devem gerenciar suas senhas no AD DS.</span><span class="sxs-lookup"><span data-stu-id="b0941-116">Even when using Password Hash Synchronization (PHS), in which Azure AD stores a hashed version of the already hashed version in AD DS, you and users must manage their passwords in AD DS.</span></span>

<span data-ttu-id="b0941-117">Com [o writeback de senha,](#pw_writeback)os usuários podem alterar suas senhas do AD DS por meio do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b0941-117">With [password writeback](#pw_writeback), your users can change their AD DS passwords through Azure AD.</span></span>

## <a name="prevent-bad-passwords"></a><span data-ttu-id="b0941-118">Evitar o uso de senhas ruins</span><span class="sxs-lookup"><span data-stu-id="b0941-118">Prevent bad passwords</span></span>

<span data-ttu-id="b0941-119">Todos os usuários devem usar as [Diretrizes de senhas da Microsoft](https://www.microsoft.com/research/publication/password-guidance) para criar senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b0941-119">All your users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance) to create their user account passwords.</span></span>

<span data-ttu-id="b0941-120">Para impedir que os usuários criem senhas que possam ser facilmente descobertas, use a proteção de senhas do Azure AD, que usa uma lista geral e uma opcional personalizada de senhas proibidas, sendo a última especificada por você.</span><span class="sxs-lookup"><span data-stu-id="b0941-120">To prevent users from creating an easily-determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="b0941-121">Você pode, por exemplo, usar termos específicos da sua organização, como:</span><span class="sxs-lookup"><span data-stu-id="b0941-121">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="b0941-122">Nomes de marcas</span><span class="sxs-lookup"><span data-stu-id="b0941-122">Brand names</span></span>
- <span data-ttu-id="b0941-123">Nomes de produtos</span><span class="sxs-lookup"><span data-stu-id="b0941-123">Product names</span></span>
- <span data-ttu-id="b0941-124">Locais (por exemplo, sedes de empresas)</span><span class="sxs-lookup"><span data-stu-id="b0941-124">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="b0941-125">Termos internos específicos da empresa</span><span class="sxs-lookup"><span data-stu-id="b0941-125">Company-specific internal terms</span></span>
- <span data-ttu-id="b0941-126">Abreviaturas com significados específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="b0941-126">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="b0941-127">Você pode proibir senhas [incorretas na](/azure/active-directory/authentication/concept-password-ban-bad) nuvem e para o [AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)local.</span><span class="sxs-lookup"><span data-stu-id="b0941-127">You can ban bad passwords [in the cloud](/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises AD DS](/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

## <a name="simplify-user-sign-in"></a><span data-ttu-id="b0941-128">Simplificar a entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="b0941-128">Simplify user sign-in</span></span>

<span data-ttu-id="b0941-129">O Azure AD Seamless Single Sign-On (SSO Contínuo do Azure AD) funciona com PHS e autenticação Pass-Through (PTA), para permitir que seus usuários entre em serviços que usam contas de usuário do Azure AD sem precisar digitar suas senhas e, em muitos casos, seus nomes de usuário.</span><span class="sxs-lookup"><span data-stu-id="b0941-129">Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) works with PHS and Pass-Through Authentication (PTA), to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="b0941-130">Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.</span><span class="sxs-lookup"><span data-stu-id="b0941-130">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="b0941-131">Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b0941-131">You configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span> <span data-ttu-id="b0941-132">Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="b0941-132">See the [instructions to configure Azure AD Seamless SSO](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a><span data-ttu-id="b0941-133">Simplificar atualizações de senha para o AD DS</span><span class="sxs-lookup"><span data-stu-id="b0941-133">Simplify password updates to AD DS</span></span>

<span data-ttu-id="b0941-134">Com o writeback de senha, você pode permitir que os usuários redefinirem suas senhas por meio do Azure AD, que é replicado para o AD DS.</span><span class="sxs-lookup"><span data-stu-id="b0941-134">With password writeback, you can allow users to reset their passwords through Azure AD, which is then replicated to AD DS.</span></span> <span data-ttu-id="b0941-135">Os usuários não precisam acessar o AD DS local para atualizar suas senhas.</span><span class="sxs-lookup"><span data-stu-id="b0941-135">Users don’t need to access their on-premises AD DS to update their passwords.</span></span> <span data-ttu-id="b0941-136">Isso é valioso para usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.</span><span class="sxs-lookup"><span data-stu-id="b0941-136">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="b0941-137">O write-back de senha é necessário para o uso por completo das capacidades de Proteção de Identidade do Azure AD, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.</span><span class="sxs-lookup"><span data-stu-id="b0941-137">Password writeback is required to fully utilize Azure AD Identity Protection capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="b0941-138">Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="b0941-138">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="b0941-p108">Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="b0941-p108">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

## <a name="simplify-password-resets"></a><span data-ttu-id="b0941-141">Simplificar as redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="b0941-141">Simplify password resets</span></span>

<span data-ttu-id="b0941-142">A redefinição de senha de autoatendados (SSPR) permite que os usuários redefinir ou desbloquear suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="b0941-142">Self-service password reset (SSPR) allows users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="b0941-143">Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações.</span><span class="sxs-lookup"><span data-stu-id="b0941-143">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="b0941-144">Você deve [habilitar o writeback de senha](#pw_writeback) antes de implantar redefinições de senha.</span><span class="sxs-lookup"><span data-stu-id="b0941-144">You must enable [password writeback](#pw_writeback) before you can deploy password resets.</span></span>

<span data-ttu-id="b0941-145">Confira as[instruções para implantar redefinição de senha](/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="b0941-145">See the [instructions to roll out password reset](/azure/active-directory/authentication/howto-sspr-deployment).</span></span>