---
title: Modelos de identidade do Microsoft 365 e Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Saiba como gerenciar o serviço de identidade de usuário do Azure AD no Microsoft 365 usando modelos de identidade híbrida ou somente na nuvem.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327946"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a><span data-ttu-id="3ffca-103">Modelos de identidade do Microsoft 365 e Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3ffca-103">Microsoft 365 identity models and Azure Active Directory</span></span>

<span data-ttu-id="3ffca-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="3ffca-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3ffca-105">O Microsoft 365 usa o Azure Active Directory (Azure AD), um serviço de autenticação e identidade de usuário baseado em nuvem que está incluído na sua assinatura do Microsoft 365 para gerenciar identidades e autenticação do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-105">Microsoft 365 uses Azure Active Directory (Azure AD), a cloud-based user identity and authentication service that is included with your Microsoft 365 subscription, to manage identities and authentication for Microsoft 365.</span></span> <span data-ttu-id="3ffca-106">Configurar a infraestrutura de identidade corretamente é essencial para gerenciar o acesso e as permissões de usuário do Microsoft 365 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3ffca-106">Getting your identity infrastructure configured correctly is vital to managing Microsoft 365 user access and permissions for your organization.</span></span>

<span data-ttu-id="3ffca-107">Antes de começar, assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="3ffca-108"><p> </p></span><span class="sxs-lookup"><span data-stu-id="3ffca-108"><p> </p></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="3ffca-109">Sua primeira opção de planejamento é o modelo de identidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-109">Your first planning choice is the Microsoft 365 identity model.</span></span>

## <a name="microsoft-365-identity-models"></a><span data-ttu-id="3ffca-110">Modelos de identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ffca-110">Microsoft 365 identity models</span></span>

<span data-ttu-id="3ffca-111">Para planejar contas de usuário, primeiro você precisa entender os dois modelos de identidade no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-111">To plan for user accounts, you first need to understand the two identity models in Microsoft 365.</span></span> <span data-ttu-id="3ffca-112">Você pode manter as identidades da sua organização somente na nuvem ou manter suas identidades locais do AD DS (Serviços de Domínio Active Directory) e usá-las para autenticação quando os usuários acessarem os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-112">You can maintain your organization's identities only in the cloud, or you can maintain your on-premises Active Directory Domain Services (AD DS) identities and use them for authentication when users access Microsoft 365 cloud services.</span></span>  

<span data-ttu-id="3ffca-113">Aqui estão os dois tipos de identidade e seu melhor ajuste e benefícios.</span><span class="sxs-lookup"><span data-stu-id="3ffca-113">Here are the two types of identity and their best fit and benefits.</span></span>

| <span data-ttu-id="3ffca-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="3ffca-114">Attribute</span></span> | <span data-ttu-id="3ffca-115">Identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="3ffca-115">Cloud-only identity</span></span> | <span data-ttu-id="3ffca-116">Identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="3ffca-116">Hybrid identity</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="3ffca-117">**Definição**</span><span class="sxs-lookup"><span data-stu-id="3ffca-117">**Definition**</span></span> | <span data-ttu-id="3ffca-118">A conta de usuário existe apenas no locatário do Azure AD para sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-118">User account only exists in the Azure AD tenant for your Microsoft 365 subscription.</span></span> | <span data-ttu-id="3ffca-119">A conta de usuário existe no AD DS e uma cópia também está no locatário do Azure AD para sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-119">User account exists in AD DS and a copy is also in the Azure AD tenant for your Microsoft 365 subscription.</span></span> <span data-ttu-id="3ffca-120">A conta de usuário no Azure AD também pode incluir uma versão com hashed da senha da conta de usuário do AD DS já com hashed.</span><span class="sxs-lookup"><span data-stu-id="3ffca-120">The user account in Azure AD might also include a hashed version of the already hashed AD DS user account password.</span></span> |
| <span data-ttu-id="3ffca-121">**Como o Microsoft 365 autentica as credenciais do usuário**</span><span class="sxs-lookup"><span data-stu-id="3ffca-121">**How Microsoft 365 authenticates user credentials**</span></span> | <span data-ttu-id="3ffca-122">O locatário do Azure AD para sua assinatura do Microsoft 365 executa a autenticação com a conta de identidade na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3ffca-122">The Azure AD tenant for your Microsoft 365 subscription performs the authentication with the cloud identity account.</span></span> | <span data-ttu-id="3ffca-123">O locatário do Azure AD para sua assinatura do Microsoft 365 lida com o processo de autenticação ou redireciona o usuário para outro provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="3ffca-123">The Azure AD tenant for your Microsoft 365 subscription either handles the authentication process or redirects the user to another identity provider.</span></span> |
| <span data-ttu-id="3ffca-124">**Melhor para**</span><span class="sxs-lookup"><span data-stu-id="3ffca-124">**Best for**</span></span> | <span data-ttu-id="3ffca-125">Organizações que não têm ou precisam de um AD DS local.</span><span class="sxs-lookup"><span data-stu-id="3ffca-125">Organizations that do not have or need an on-premises AD DS.</span></span> | <span data-ttu-id="3ffca-126">Organizações que usam o AD DS ou outro provedor de identidade.</span><span class="sxs-lookup"><span data-stu-id="3ffca-126">Organizations using AD DS or another identity provider.</span></span> |
| <span data-ttu-id="3ffca-127">**Maior benefício**</span><span class="sxs-lookup"><span data-stu-id="3ffca-127">**Greatest benefit**</span></span> | <span data-ttu-id="3ffca-128">Simples de usar.</span><span class="sxs-lookup"><span data-stu-id="3ffca-128">Simple to use.</span></span> <span data-ttu-id="3ffca-129">Nenhum servidor ou ferramentas de diretório adicional é necessário.</span><span class="sxs-lookup"><span data-stu-id="3ffca-129">No extra directory tools or servers required.</span></span> | <span data-ttu-id="3ffca-130">Os usuários podem usar as mesmas credenciais ao acessar recursos locais ou baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="3ffca-130">Users can use the same credentials when accessing on-premises or cloud-based resources.</span></span> |
||||

## <a name="cloud-only-identity"></a><span data-ttu-id="3ffca-131">Identidade somente na nuvem</span><span class="sxs-lookup"><span data-stu-id="3ffca-131">Cloud-only identity</span></span>

<span data-ttu-id="3ffca-132">Uma identidade somente na nuvem usa contas de usuário que existem somente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-132">A cloud-only identity uses user accounts that exist only in Azure AD.</span></span> <span data-ttu-id="3ffca-133">A identidade somente na nuvem é normalmente usada por pequenas organizações que não têm servidores locais ou não usam o AD DS para gerenciar identidades locais.</span><span class="sxs-lookup"><span data-stu-id="3ffca-133">Cloud-only identity is typically used by small organizations that do not have on-premises servers or do not use AD DS to manage local identities.</span></span> 

<span data-ttu-id="3ffca-134">Aqui estão os componentes básicos da identidade somente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="3ffca-134">Here are the basic components of cloud-only identity.</span></span>
 
![Componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="3ffca-136">Os usuários locais e remotos (online) usam suas contas de usuário e senhas do Azure AD para acessar os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-136">Both on-premises and remote (online) users use their Azure AD user accounts and passwords to access Microsoft 365 cloud services.</span></span> <span data-ttu-id="3ffca-137">O Azure AD autentica credenciais de usuário com base em suas contas de usuário e senhas armazenadas.</span><span class="sxs-lookup"><span data-stu-id="3ffca-137">Azure AD authenticates user credentials based on its stored user accounts and passwords.</span></span>

### <a name="administration"></a><span data-ttu-id="3ffca-138">Administração</span><span class="sxs-lookup"><span data-stu-id="3ffca-138">Administration</span></span>
<span data-ttu-id="3ffca-139">Como as contas de usuário só são armazenadas no Azure AD, você gerencia identidades de nuvem com ferramentas como o Centro de administração do [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/) e [o Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3ffca-139">Because user accounts are only stored in Azure AD, you manage cloud identities with tools such as the [Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/add-users/) and [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md).</span></span> 

## <a name="hybrid-identity"></a><span data-ttu-id="3ffca-140">Identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="3ffca-140">Hybrid identity</span></span>

<span data-ttu-id="3ffca-141">A identidade híbrida usa contas originadas em um AD DS local e têm uma cópia no locatário do Azure AD de uma assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3ffca-141">Hybrid identity uses accounts that originate in an on-premises AD DS and have a copy in the Azure AD tenant of a Microsoft 365 subscription.</span></span> <span data-ttu-id="3ffca-142">No entanto, a maioria das alterações só flui de uma maneira.</span><span class="sxs-lookup"><span data-stu-id="3ffca-142">However, most changes only flow one way.</span></span> <span data-ttu-id="3ffca-143">As alterações feitas nas contas de usuário do AD DS são sincronizadas com sua cópia no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-143">Changes that you make to AD DS user accounts are synchronized to their copy in Azure AD.</span></span> <span data-ttu-id="3ffca-144">Mas as alterações feitas em contas baseadas em nuvem no Azure AD, como novas contas de usuário, não são sincronizadas com o AD DS.</span><span class="sxs-lookup"><span data-stu-id="3ffca-144">But changes made to cloud-based accounts in Azure AD, such as new user accounts, are not synchronized with AD DS.</span></span>

<span data-ttu-id="3ffca-145">O Azure AD Connect fornece a sincronização de conta em andamento.</span><span class="sxs-lookup"><span data-stu-id="3ffca-145">Azure AD Connect provides the ongoing account synchronization.</span></span> <span data-ttu-id="3ffca-146">Ele é executado em um servidor local, verifica se há alterações no AD DS e encaminha essas alterações para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-146">It runs on an on-premises server, checks for changes in the AD DS, and forwards those changes to Azure AD.</span></span> <span data-ttu-id="3ffca-147">O Azure AD Connect oferece a capacidade de filtrar quais contas são sincronizadas e se sincronizar uma versão com hash de senhas de usuário, conhecida como sincronização de hash de senha (PHS).</span><span class="sxs-lookup"><span data-stu-id="3ffca-147">Azure AD Connect provides the ability to filter which accounts are synchronized and whether to synchronize a hashed version of user passwords, known as password hash synchronization (PHS).</span></span>

<span data-ttu-id="3ffca-148">Quando você implementa a identidade híbrida, o AD DS local é a fonte autoritativa para informações da conta.</span><span class="sxs-lookup"><span data-stu-id="3ffca-148">When you implement hybrid identity, your on-premises AD DS is the authoritative source for account information.</span></span> <span data-ttu-id="3ffca-149">Isso significa que você executa tarefas de administração principalmente no local, que são sincronizadas com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-149">This means that you perform administration tasks mostly on-premises, which are then synchronized to Azure AD.</span></span> 

<span data-ttu-id="3ffca-150">Aqui estão os componentes da identidade híbrida.</span><span class="sxs-lookup"><span data-stu-id="3ffca-150">Here are the components of hybrid identity.</span></span>

![Componentes da identidade híbrida](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="3ffca-152">O locatário do Azure AD tem uma cópia das contas do AD DS.</span><span class="sxs-lookup"><span data-stu-id="3ffca-152">The Azure AD tenant has a copy of the AD DS accounts.</span></span> <span data-ttu-id="3ffca-153">Nessa configuração, os usuários locais e remotos que acessam os serviços de nuvem do Microsoft 365 são autenticados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-153">In this configuration, both on-premises and remote users accessing Microsoft 365 cloud services authenticate against Azure AD.</span></span>

>[!Note]
><span data-ttu-id="3ffca-154">Você sempre precisa usar o Azure AD Connect para sincronizar contas de usuário para identidade híbrida.</span><span class="sxs-lookup"><span data-stu-id="3ffca-154">You always need to use Azure AD Connect to synchronize user accounts for hybrid identity.</span></span> <span data-ttu-id="3ffca-155">Você precisa das contas de usuário sincronizadas no Azure AD para executar a atribuição de licença e o gerenciamento de grupo, configurar permissões e outras tarefas administrativas que envolvam contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="3ffca-155">You need the synchronized user accounts in Azure AD to perform license assignment and group management, configure permissions, and other administrative tasks that involve user accounts.</span></span>
>

### <a name="administration"></a><span data-ttu-id="3ffca-156">Administração</span><span class="sxs-lookup"><span data-stu-id="3ffca-156">Administration</span></span>

<span data-ttu-id="3ffca-157">Como as contas de usuário originais e autoritativas são armazenadas no AD DS local, você gerencia suas identidades com as mesmas ferramentas que gerencia seu AD DS.</span><span class="sxs-lookup"><span data-stu-id="3ffca-157">Because the original and authoritative user accounts are stored in the on-premises AD DS, you manage your identities with the same tools as you manage your AD DS.</span></span> 

<span data-ttu-id="3ffca-158">Você não usa o Centro de administração do Microsoft 365 ou o PowerShell para Microsoft 365 para gerenciar contas de usuário sincronizadas no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ffca-158">You don't use the Microsoft 365 admin center or PowerShell for Microsoft 365 to manage synchronized user accounts in Azure AD.</span></span>

## <a name="next-step"></a><span data-ttu-id="3ffca-159">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3ffca-159">Next step</span></span>

<span data-ttu-id="3ffca-160">Se você precisar do modelo de identidade somente na nuvem, consulte [Identidade somente na nuvem.](cloud-only-identities.md)</span><span class="sxs-lookup"><span data-stu-id="3ffca-160">If you need the cloud-only identity model, see [Cloud-only identity](cloud-only-identities.md).</span></span>

<span data-ttu-id="3ffca-161">Se você precisar do modelo de identidade híbrida, consulte [Identidade híbrida.](plan-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="3ffca-161">If you need the hybrid identity model, see [Hybrid identity](plan-for-directory-synchronization.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="3ffca-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="3ffca-162">See also</span></span>

[<span data-ttu-id="3ffca-163">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3ffca-163">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
