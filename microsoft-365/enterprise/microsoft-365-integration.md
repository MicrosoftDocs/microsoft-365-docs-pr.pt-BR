---
title: Integração do Microsoft 365 com ambientes locais
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: Neste artigo, saiba como integrar o Microsoft 365 com seus serviços de diretório existentes e ambientes locais.
ms.openlocfilehash: c0453b7685254ccbbb301a17749fe48549fae78d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923961"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="4d419-103">Integração do Microsoft 365 com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="4d419-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="4d419-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4d419-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4d419-105">Você pode integrar o Microsoft 365 com seus Serviços de Domínio do Active Directory (AD DS) existentes e com instalações locais do Exchange Server, Skype for Business Server 2015 ou SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="4d419-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="4d419-106">Ao integrar o AD DS, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="4d419-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="4d419-107">Você também pode adicionar a sincronização de hash de senha (PHS) ou logoff único (SSO) para que os usuários possam fazer logoff em ambos os ambientes com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="4d419-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="4d419-108">Quando você se integra com produtos de servidor local, cria um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="4d419-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="4d419-109">Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para o Microsoft 365 ou pode continuar a ter alguns usuários ou algumas informações locais e algumas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="4d419-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="4d419-110">Para obter mais informações sobre ambientes híbridos, consulte [nuvem híbrida](../solutions/cloud-architecture-models.md#hybrid).</span><span class="sxs-lookup"><span data-stu-id="4d419-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="4d419-111">Você também pode usar os consultores do Azure Active Directory (Azure AD) para orientação de configuração personalizada no Centro de administração do Microsoft 365 (você deve estar loco no Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="4d419-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="4d419-112">Guia de configuração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4d419-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="4d419-113">Sincronizar usuários do diretório da sua organização</span><span class="sxs-lookup"><span data-stu-id="4d419-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="4d419-114">Consultor de implantação dos Serviços de Federação do Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="4d419-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="4d419-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="4d419-115">Before you begin</span></span>

<span data-ttu-id="4d419-116">Antes de integrar o Microsoft 365 e um ambiente local, você também precisa fazer planejamento de rede e ajuste [de desempenho.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="4d419-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="4d419-117">Você também vai querer entender os modelos de identidade [disponíveis.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="4d419-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="4d419-118">Consulte [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span><span class="sxs-lookup"><span data-stu-id="4d419-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="4d419-119">Integrar o Microsoft 365 ao AD DS</span><span class="sxs-lookup"><span data-stu-id="4d419-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="4d419-120">Se você tiver contas de usuário existentes no AD DS, não deseja criar todas essas contas no Microsoft 365 e correr o risco de introduzir diferenças ou erros entre os ambientes.</span><span class="sxs-lookup"><span data-stu-id="4d419-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="4d419-121">A sincronização de diretórios ajuda você a espelhar essas contas entre seus ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="4d419-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="4d419-122">Com a sincronização de diretórios, os usuários não têm que se lembrar de novas informações para cada ambiente e você não precisa criar ou atualizar contas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="4d419-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="4d419-123">Você precisará preparar [seu diretório local](prepare-for-directory-synchronization.md) para sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="4d419-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usar a sincronização de diretórios para manter as informações de conta de usuário local e online sincronizadas](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="4d419-125">Se você quiser que os usuários possam fazer logoff no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO.</span><span class="sxs-lookup"><span data-stu-id="4d419-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="4d419-126">Com o SSO, o Microsoft 365 é configurado para confiar no ambiente local para autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="4d419-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Com o login único, a mesma conta está disponível nos ambientes local e online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="4d419-128">Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="4d419-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="4d419-129">Um usuário faz o login em seu ambiente local com sua conta de usuário (domínio\nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="4d419-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="4d419-130">Quando eles vão para o Microsoft 365, eles devem fazer logoff novamente com sua conta de trabalho ou de estudante (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="4d419-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="4d419-131">O nome de usuário é o mesmo em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="4d419-131">The user name is the same in both environments.</span></span> <span data-ttu-id="4d419-132">Quando você adiciona PHS ou PTA, o usuário tem a mesma senha para ambos os ambientes, mas terá que fornecer essas credenciais novamente ao entrar no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d419-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="4d419-133">A sincronização de diretório com o PHS é a sincronização de diretório mais usada.</span><span class="sxs-lookup"><span data-stu-id="4d419-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="4d419-134">Para configurar a sincronização de diretórios, use o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4d419-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="4d419-135">Para obter instruções, consulte [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span><span class="sxs-lookup"><span data-stu-id="4d419-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](/azure/active-directory/hybrid/how-to-connect-install-express).</span></span>

<span data-ttu-id="4d419-136">Saiba mais sobre [como preparar a sincronização de diretórios para o Microsoft 365](prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4d419-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="4d419-137">Sincronização de diretório com SSO</span><span class="sxs-lookup"><span data-stu-id="4d419-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="4d419-138">Um usuário faz o login em seu ambiente local com sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="4d419-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="4d419-139">Quando eles vão para o Microsoft 365, eles estão conectados automaticamente ou fazem logoff usando as mesmas credenciais que usam para seu ambiente local (domínio\nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="4d419-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="4d419-140">Para configurar o SSO, você também usa o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4d419-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="4d419-141">Para obter instruções, consulte [Instalação personalizada do Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span><span class="sxs-lookup"><span data-stu-id="4d419-141">For instructions, see [Custom installation of Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-custom).</span></span>

<span data-ttu-id="4d419-142">Para obter mais informações, consulte [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="4d419-142">For more information, see [single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="4d419-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="4d419-143">Azure AD Connect</span></span>

<span data-ttu-id="4d419-144">O Azure AD Connect substitui versões mais antigas de ferramentas de integração de identidade, como DirSync e Sincronização do Azure AD. Se você quiser atualizar do Azure Active Directory Sync para o Azure AD Connect, consulte [as instruções de atualização](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span><span class="sxs-lookup"><span data-stu-id="4d419-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started).</span></span> 

## <a name="see-also"></a><span data-ttu-id="4d419-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="4d419-145">See also</span></span>

[<span data-ttu-id="4d419-146">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4d419-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)