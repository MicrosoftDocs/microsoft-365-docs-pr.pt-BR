---
title: Integração do Microsoft 365 com ambientes locais
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
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
description: Neste artigo, saiba como integrar o Microsoft 365 com os serviços de diretório existentes e ambientes locais.
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687482"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="b2f6d-103">Integração do Microsoft 365 com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="b2f6d-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="b2f6d-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="b2f6d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="b2f6d-105">Você pode integrar o Microsoft 365 com os serviços de diretório existentes e com uma instalação local do Exchange Server, do Skype for Business Server 2015 ou do SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-105">You can integrate Microsoft 365 with your existing directory services and with an on-premises installation of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="b2f6d-106">Ao se integrar aos serviços de diretório, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-106">When you integrate with directory services, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="b2f6d-107">Você também pode adicionar a sincronização de hash de senha ou SSO (logon único) para que os usuários possam fazer logon em ambos os ambientes com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-107">You can also add password hash synchronization or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="b2f6d-108">Ao se integrar aos produtos do servidor local, você cria um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="b2f6d-109">Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para a Microsoft 365, ou pode continuar a ter alguns usuários ou algumas informações no local e alguns na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="b2f6d-110">Para obter mais informações sobre ambientes híbridos, consulte [Hybrid Cloud Overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-110">For more information about hybrid environments, see [Hybrid cloud overview](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).</span></span>

<span data-ttu-id="b2f6d-111">Você também pode usar os supervisor do Azure Active Directory (Azure AD) para obter orientação de instalação personalizada (você deve estar conectado ao Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="b2f6d-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="b2f6d-112">Sincronizar usuários do diretório da sua organização</span><span class="sxs-lookup"><span data-stu-id="b2f6d-112">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="b2f6d-113">Supervisor de implantação do AD FS</span><span class="sxs-lookup"><span data-stu-id="b2f6d-113">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
- [<span data-ttu-id="b2f6d-114">Guia de instalação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2f6d-114">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="b2f6d-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b2f6d-115">Before you begin</span></span>

<span data-ttu-id="b2f6d-116">Antes de integrar o Microsoft 365 e um ambiente local, você também precisará participar do [planejamento de rede e do ajuste de desempenho](network-planning-and-performance.md).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to attend to [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="b2f6d-117">Você também vai querer entender os modelos de [identidade](about-microsoft-365-identity.md)disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="b2f6d-118">Confira [onde gerenciar contas da microsoft 365](manage-microsoft-365-accounts.md) para obter uma lista de ferramentas que você pode usar para gerenciar usuários e contas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-118">See [where to manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 users and accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-directory-services"></a><span data-ttu-id="b2f6d-119">Integrar o Microsoft 365 com os serviços de diretório</span><span class="sxs-lookup"><span data-stu-id="b2f6d-119">Integrate Microsoft 365 with directory services</span></span>
<span data-ttu-id="b2f6d-120">Se você tiver contas de usuário existentes em um diretório local, não será necessário recriar todas essas contas no Microsoft 365 e correr o risco de introdução a diferenças ou erros entre os ambientes.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-120">If you have existing user accounts in an on-premises directory, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="b2f6d-121">A sincronização de diretórios ajuda você a espelhar essas contas entre seus ambientes online e local.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-121">Directory synchronization helps you mirror those accounts between your online and on-premises environments.</span></span> <span data-ttu-id="b2f6d-122">Com a sincronização de diretórios, os usuários não precisam se lembrar de novas informações para cada ambiente, e você não precisa criar ou atualizar contas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="b2f6d-123">Você precisará [preparar o diretório local para a](prepare-for-directory-synchronization.md) sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usar a sincronização de diretórios para manter as informações de conta de usuário local e online sincronizadas](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
<span data-ttu-id="b2f6d-125">Se quiser que os usuários possam fazer logon no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="b2f6d-126">Com o SSO, a Microsoft 365 é configurada para confiar no ambiente local para autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Com o logon único, a mesma conta está disponível nos ambientes local e online](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
<span data-ttu-id="b2f6d-128">Diferentes técnicas de gerenciamento de contas de usuário fornecem experiências diferentes para seus usuários, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-128">Different user account management techniques provide different experiences for your users, as shown in the following table.</span></span>
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a><span data-ttu-id="b2f6d-129">Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem</span><span class="sxs-lookup"><span data-stu-id="b2f6d-129">Directory synchronization with or without password hash synchronization or pass-through authentication</span></span>

<span data-ttu-id="b2f6d-130">Um usuário faz logon no seu ambiente local com a conta de usuário (domínio \ nome_de_usuário).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-130">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="b2f6d-131">Quando eles acessam o Microsoft 365, eles devem fazer logon novamente com sua conta corporativa ou de estudante (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-131">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="b2f6d-132">O nome de usuário é o mesmo em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-132">The user name is the same in both environments.</span></span> <span data-ttu-id="b2f6d-133">Quando você adiciona a sincronização de hash de senha ou a autenticação de passagem, o usuário tem a mesma senha para os dois ambientes, mas precisará fornecer essas credenciais novamente ao fazer logon no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-133">When you add password hash sync or pass-through authentication, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="b2f6d-134">A sincronização de diretórios com sincronização de hash de senha é o cenário de sincronização de diretório mais comumente usado.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-134">Directory synchronization with password hash sync is the most commonly used directory sync scenario.</span></span>

<span data-ttu-id="b2f6d-135">Para configurar a sincronização de diretórios, use o Azure Active Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-135">To set up directory synchronization, use Azure Active Directory Connect.</span></span> <span data-ttu-id="b2f6d-136">Para obter instruções, leia [Configurar a sincronização de diretório para o Microsoft 365 e o](set-up-directory-synchronization.md) [Azure ad Connect com as configurações expressas](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-136">For instructions, read [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md), and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="b2f6d-137">Saiba mais sobre [a preparação para a sincronização de diretório para o Microsoft 365](prepare-for-directory-synchronization.md) e [integração de seus identificações locais com o Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-137">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md) and [integrating your on-premises identifies with Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="b2f6d-138">Sincronização de diretórios com SSO</span><span class="sxs-lookup"><span data-stu-id="b2f6d-138">Directory synchronization with SSO</span></span>

<span data-ttu-id="b2f6d-139">Um usuário faz logon no seu ambiente local com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-139">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="b2f6d-140">Quando eles acessam o Microsoft 365, eles são conectados automaticamente ou fazem logon usando as mesmas credenciais que usam para seu ambiente local (domínio \ nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-140">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="b2f6d-141">Para configurar o SSO, você também usa o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b2f6d-141">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="b2f6d-142">Para obter instruções, leia [instalação personalizada do Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-142">For instructions, read [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="b2f6d-143">Saiba mais sobre o [logon único para aplicativos no Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-143">Learn more about [single sign-on to applications in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="b2f6d-144">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b2f6d-144">Azure AD Connect</span></span>

<span data-ttu-id="b2f6d-145">O Azure AD Connect substitui versões antigas das ferramentas de integração de identidades como DirSync e sincronização do Azure AD. Para obter mais informações, consulte [o que é a identidade híbrida com o Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-145">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. For more information, see [What is hybrid identity with Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969).</span></span> <span data-ttu-id="b2f6d-146">Se você deseja atualizar da sincronização do Azure Active Directory para o Azure AD Connect, consulte [as instruções de atualização](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-146">If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

<span data-ttu-id="b2f6d-147">Confira também a [implantação da sincronização de diretórios do microsoft 365 no Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span><span class="sxs-lookup"><span data-stu-id="b2f6d-147">Also see [Deploy Microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).</span></span>

## <a name="see-also"></a><span data-ttu-id="b2f6d-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="b2f6d-148">See also</span></span>

[<span data-ttu-id="b2f6d-149">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b2f6d-149">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
