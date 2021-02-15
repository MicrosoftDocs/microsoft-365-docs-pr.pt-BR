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
description: Neste artigo, saiba como integrar o Microsoft 365 com seus serviços de diretório e ambientes locais existentes.
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384859"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a><span data-ttu-id="2b91b-103">Integração do Microsoft 365 com ambientes locais</span><span class="sxs-lookup"><span data-stu-id="2b91b-103">Microsoft 365 integration with on-premises environments</span></span>

<span data-ttu-id="2b91b-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2b91b-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2b91b-105">Você pode integrar o Microsoft 365 com seus Active Directory Domain Services (AD DS) locais existentes e com instalações locais do Exchange Server, Skype for Business Server 2015 ou SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="2b91b-105">You can integrate Microsoft 365 with your existing on-premises Active Directory Domain Services (AD DS) and with on-premises installations of Exchange Server, Skype for Business Server 2015, or SharePoint Server.</span></span>
  
 - <span data-ttu-id="2b91b-106">Ao integrar o AD DS, você pode sincronizar e gerenciar contas de usuário para ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="2b91b-106">When you integrate AD DS, you can synchronize and manage user accounts for both environments.</span></span> <span data-ttu-id="2b91b-107">Você também pode adicionar a sincronização de hash de senha (PHS) ou o logoff único (SSO) para que os usuários possam fazer logoff em ambos os ambientes com suas credenciais locais.</span><span class="sxs-lookup"><span data-stu-id="2b91b-107">You can also add password hash synchronization (PHS) or single sign-on (SSO) so users can log on to both environments with their on-premises credentials.</span></span>
 - <span data-ttu-id="2b91b-108">Ao se integrar aos produtos de servidor local, você cria um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="2b91b-108">When you integrate with on-premises server products, you create a hybrid environment.</span></span> <span data-ttu-id="2b91b-109">Um ambiente híbrido pode ajudar à medida que você migra usuários ou informações para o Microsoft 365 ou pode continuar a ter alguns usuários ou algumas informações locais e algumas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="2b91b-109">A hybrid environment can help as you migrate users or information to Microsoft 365, or you can continue to have some users or some information on-premises and some in the cloud.</span></span> <span data-ttu-id="2b91b-110">Para obter mais informações sobre ambientes híbridos, consulte [nuvem híbrida.](../solutions/cloud-architecture-models.md#hybrid)</span><span class="sxs-lookup"><span data-stu-id="2b91b-110">For more information about hybrid environments, see [hybrid cloud](../solutions/cloud-architecture-models.md#hybrid).</span></span>

<span data-ttu-id="2b91b-111">Você também pode usar os consultores do Azure Active Directory (Azure AD) para obter orientações de configuração personalizadas no Centro de administração do Microsoft 365 (você deve estar assinado no Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="2b91b-111">You can also use the Azure Active Directory (Azure AD) advisors for customized setup guidance in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

- [<span data-ttu-id="2b91b-112">Guia de configuração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2b91b-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
- [<span data-ttu-id="2b91b-113">Sincronizar usuários do diretório da sua organização</span><span class="sxs-lookup"><span data-stu-id="2b91b-113">Sync users from your org's directory</span></span>](https://aka.ms/aadconnectpwsync)
- [<span data-ttu-id="2b91b-114">Consultor de implantação dos Serviços de Federação do Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="2b91b-114">Active Directory Federation Services (AD FS) deployment advisor</span></span>](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a><span data-ttu-id="2b91b-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2b91b-115">Before you begin</span></span>

<span data-ttu-id="2b91b-116">Antes de integrar o Microsoft 365 e um ambiente local, você também precisa fazer planejamento de rede e ajuste [de desempenho.](network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="2b91b-116">Before you integrate Microsoft 365 and an on-premises environment, you also need to do [network planning and performance tuning](network-planning-and-performance.md).</span></span> <span data-ttu-id="2b91b-117">Você também vai querer entender os modelos de [identidade disponíveis.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="2b91b-117">You will also want to understand the available [identity models](about-microsoft-365-identity.md).</span></span> 

<span data-ttu-id="2b91b-118">Confira [gerenciar contas do Microsoft 365](manage-microsoft-365-accounts.md) para ver uma lista de ferramentas que você pode usar para gerenciar contas de usuário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b91b-118">See [manage Microsoft 365 accounts](manage-microsoft-365-accounts.md) for a list of tools you can use to manage Microsoft 365 user accounts.</span></span> 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a><span data-ttu-id="2b91b-119">Integrar o Microsoft 365 ao AD DS</span><span class="sxs-lookup"><span data-stu-id="2b91b-119">Integrate Microsoft 365 with AD DS</span></span>

<span data-ttu-id="2b91b-120">Se você tiver contas de usuário existentes no AD DS, não será necessário criar todas essas contas no Microsoft 365 com risco de introduzir diferenças ou erros entre os ambientes.</span><span class="sxs-lookup"><span data-stu-id="2b91b-120">If you have existing user accounts in AD DS, you don't want to re-create all of those accounts in Microsoft 365 and risk introducing differences or errors between the environments.</span></span> <span data-ttu-id="2b91b-121">A sincronização de diretórios ajuda a espelhar essas contas entre seus ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="2b91b-121">Directory synchronization helps you mirror those accounts between your on-premises and online environments.</span></span> <span data-ttu-id="2b91b-122">Com a sincronização de diretórios, os usuários não têm que se lembrar de novas informações para cada ambiente e você não precisa criar ou atualizar contas duas vezes.</span><span class="sxs-lookup"><span data-stu-id="2b91b-122">With directory synchronization, your users don't have to remember new information for each environment, and you don't have to create or update accounts twice.</span></span> <span data-ttu-id="2b91b-123">Você precisará preparar [seu diretório local](prepare-for-directory-synchronization.md) para a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="2b91b-123">You will need to [prepare your on-premises directory](prepare-for-directory-synchronization.md) for directory synchronization.</span></span>
  
![Usar a sincronização de diretórios para manter as informações da conta de usuário local e online sincronizadas](../media/microsoft-365-integration/directory-synchronization.png)
  
<span data-ttu-id="2b91b-125">Se quiser que os usuários possam fazer logoff no Microsoft 365 com suas credenciais locais, você também pode configurar o SSO.</span><span class="sxs-lookup"><span data-stu-id="2b91b-125">If you want users to be able to log on to Microsoft 365 with their on-premises credentials, you can also configure SSO.</span></span> <span data-ttu-id="2b91b-126">Com o SSO, o Microsoft 365 é configurado para confiar no ambiente local para autenticação do usuário.</span><span class="sxs-lookup"><span data-stu-id="2b91b-126">With SSO, Microsoft 365 is configured to trust the on-premises environment for user authentication.</span></span>
  
![Com o single sign-on, a mesma conta está disponível nos ambientes local e online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a><span data-ttu-id="2b91b-128">Sincronização de diretório com ou sem sincronização de hash de senha ou autenticação de passagem (PTA)</span><span class="sxs-lookup"><span data-stu-id="2b91b-128">Directory synchronization with or without password hash synchronization or pass-through authentication (PTA)</span></span>

<span data-ttu-id="2b91b-129">Um usuário faz o login em seu ambiente local com sua conta de usuário (domínio /nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="2b91b-129">A user logs on to their on-premises environment with their user account (domain\username).</span></span> <span data-ttu-id="2b91b-130">Ao acessar o Microsoft 365, eles devem fazer logoff novamente com a conta de trabalho ou de estudante (user@domain.com).</span><span class="sxs-lookup"><span data-stu-id="2b91b-130">When they go to Microsoft 365, they must log on again with their work or school account (user@domain.com).</span></span> <span data-ttu-id="2b91b-131">O nome de usuário é o mesmo em ambos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="2b91b-131">The user name is the same in both environments.</span></span> <span data-ttu-id="2b91b-132">Quando você adiciona PHS ou PTA, o usuário tem a mesma senha para ambos os ambientes, mas terá que fornecer essas credenciais novamente ao fazer logor no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2b91b-132">When you add PHS or PTA, the user has the same password for both environments, but will have to provide those credentials again when logging on to Microsoft 365.</span></span> <span data-ttu-id="2b91b-133">A sincronização de diretórios com o PHS é a sincronização de diretório mais usada.</span><span class="sxs-lookup"><span data-stu-id="2b91b-133">Directory synchronization with PHS is the most commonly used directory synchronization .</span></span>

<span data-ttu-id="2b91b-134">Para configurar a sincronização de diretórios, use o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2b91b-134">To set up directory synchronization, use Azure AD Connect.</span></span> <span data-ttu-id="2b91b-135">Para obter instruções, confira Configurar a sincronização de diretórios para [o Microsoft 365](set-up-directory-synchronization.md) e [o Azure AD Connect com configurações expressas.](https://go.microsoft.com/fwlink/p/?LinkId=698537)</span><span class="sxs-lookup"><span data-stu-id="2b91b-135">For instructions, see [Set up directory synchronization for Microsoft 365](set-up-directory-synchronization.md) and [Azure AD Connect with express settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).</span></span>

<span data-ttu-id="2b91b-136">Saiba mais sobre [como se preparar para a sincronização de diretórios com o Microsoft 365.](prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="2b91b-136">Learn more about [preparing for directory synchronization to Microsoft 365](prepare-for-directory-synchronization.md).</span></span>

### <a name="directory-synchronization-with-sso"></a><span data-ttu-id="2b91b-137">Sincronização de diretório com SSO</span><span class="sxs-lookup"><span data-stu-id="2b91b-137">Directory synchronization with SSO</span></span>

<span data-ttu-id="2b91b-138">Um usuário faz o login em seu ambiente local com sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2b91b-138">A user logs on to their on-premises environment with their user account.</span></span> <span data-ttu-id="2b91b-139">Quando eles vão para o Microsoft 365, eles estão conectados automaticamente ou fazem logoff usando as mesmas credenciais que usam para seu ambiente local (domínio /nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="2b91b-139">When they go to Microsoft 365, they are either logged on automatically, or they log on using the same credentials they use for their on-premises environment (domain\username).</span></span>

<span data-ttu-id="2b91b-140">Para configurar o SSO, você também usa o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2b91b-140">To set up SSO you also use Azure AD Connect.</span></span> <span data-ttu-id="2b91b-141">Para obter instruções, [confira Instalação personalizada do Azure AD Connect.](https://go.microsoft.com/fwlink/p/?LinkID=698430)</span><span class="sxs-lookup"><span data-stu-id="2b91b-141">For instructions, see [Custom installation of Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).</span></span>

<span data-ttu-id="2b91b-142">Para obter mais informações, [consulte o single sign-on.](https://go.microsoft.com/fwlink/p/?LinkId=698604)</span><span class="sxs-lookup"><span data-stu-id="2b91b-142">For more information, see [single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>

## <a name="azure-ad-connect"></a><span data-ttu-id="2b91b-143">Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="2b91b-143">Azure AD Connect</span></span>

<span data-ttu-id="2b91b-144">O Azure AD Connect substitui versões mais antigas das ferramentas de integração de identidade, como DirSync e Azure AD Sync. Se você quiser atualizar da Sincronização do Azure Active Directory para o Azure AD Connect, confira [as instruções de atualização.](https://go.microsoft.com/fwlink/p/?LinkId=733240)</span><span class="sxs-lookup"><span data-stu-id="2b91b-144">Azure AD Connect replaces older versions of identity integration tools such as DirSync and Azure AD Sync. If you want to update from Azure Active Directory Sync to Azure AD Connect, see [the upgrade instructions](https://go.microsoft.com/fwlink/p/?LinkId=733240).</span></span> 

## <a name="see-also"></a><span data-ttu-id="2b91b-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b91b-145">See also</span></span>

[<span data-ttu-id="2b91b-146">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2b91b-146">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
