---
title: Definir a política de expiração de senha para sua organização
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Saiba como definir uma política de expiração de senha para sua organização no centro de administração do Microsoft 365. '
ms.openlocfilehash: a4d5f5240a6d4cca686b4809d05970b5e18b897f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399573"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="16731-103">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="16731-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="16731-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="16731-104">The admin center is changing.</span></span> <span data-ttu-id="16731-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="16731-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="16731-106">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="16731-106">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="16731-107">Se é um usuário, você não tem as permissões para definir a senha para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="16731-107">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="16731-108">Peça ao suporte técnico do seu trabalho ou da sua escola que faça isso para você. </span><span class="sxs-lookup"><span data-stu-id="16731-108">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="16731-109">Como administrador, você pode fazer as senhas de usuário expirarem após um determinado número de dias ou definir as senhas para nunca expirarem.</span><span class="sxs-lookup"><span data-stu-id="16731-109">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="16731-110">Por padrão, as senhas estão definidas para expirar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="16731-110">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="16731-111">A pesquisa atual indica que as alterações de senha obrigatórias são mais prejudicadas do que o recomendado.</span><span class="sxs-lookup"><span data-stu-id="16731-111">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="16731-112">Eles direcionam os usuários a escolher senhas mais fracas, reutilizar senhas ou atualizar senhas antigas de maneiras que são facilmente adivinhadas pelos hackers.</span><span class="sxs-lookup"><span data-stu-id="16731-112">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="16731-113">Se a senha for configurada para nunca expirar, recomendamos habilitar a [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="16731-113">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="16731-114">Siga as etapas abaixo se desejar definir as senhas dos usuários para expirarem após um período de tempo específico.</span><span class="sxs-lookup"><span data-stu-id="16731-114">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="16731-115">Apenas os [administradores globais ](../add-users/about-admin-roles.md) podem executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="16731-115">Only [global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="16731-116">No centro de administração do, vá para **Configurações** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="16731-116">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="16731-117">Vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Segurança e privacidade</a>.</span><span class="sxs-lookup"><span data-stu-id="16731-117">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="16731-118">Se você não for um administrador global, não verá a opção Segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="16731-118">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="16731-119">Selecione **Política de expiração de senha**.</span><span class="sxs-lookup"><span data-stu-id="16731-119">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="16731-120">Se você não quiser que os usuários tenham que alterar as senhas, marque a caixa de seleção ao lado de **Definir senhas de usuário para expirar após um número de dias**.</span><span class="sxs-lookup"><span data-stu-id="16731-120">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="16731-121">Digite a frequência com que as senhas devem expirar.</span><span class="sxs-lookup"><span data-stu-id="16731-121">Type how often passwords should expire.</span></span> <span data-ttu-id="16731-122">Escolha um número de dias entre 14 e 730.</span><span class="sxs-lookup"><span data-stu-id="16731-122">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="16731-123">Na segunda caixa, insira quando os usuários são notificados de que a senha expirará e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="16731-123">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="16731-124">Escolha um número de dias de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="16731-124">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="16731-125">Quando a senha do usuário expirar, ele receberá uma notificação que aparecerá no canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="16731-125">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="16731-126">Pontos importantes que você precisa saber sobre o recurso de expiração de senha</span><span class="sxs-lookup"><span data-stu-id="16731-126">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="16731-127">Vejamos alguns pontos que você precisa saber sobre como esse recurso funcionará a partir de janeiro de 2018:</span><span class="sxs-lookup"><span data-stu-id="16731-127">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="16731-p107">As pessoas que só usam o aplicativo do Outlook não terão de redefinir a senha do Microsoft 365 até que ela expire no cache. Isso pode levar vários dias após a data de validade real. Não há soluções alternativas para isso ao nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="16731-p107">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="16731-p108">Os usuários não receberão uma notificação por email informando que a senha expirará em um número X de dias. Quer esse recurso? **[Vote aqui!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="16731-p108">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="16731-134">Impedir que a última senha seja utilizada novamente</span><span class="sxs-lookup"><span data-stu-id="16731-134">Prevent last password from being used again</span></span>

<span data-ttu-id="16731-135">Se quiser impedir que os usuários promovam a reciclagem de senhas antigas, use o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="16731-135">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="16731-136">Confira [Impor histórico de senhas](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span><span class="sxs-lookup"><span data-stu-id="16731-136">See [Enforce password history](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history).</span></span>

<span data-ttu-id="16731-137">Além disso, se um funcionário tiver usado um dispositivo móvel para acessar o Microsoft 365, você poderá apagá-lo a fim de garantir que a senha não seja armazenada e reciclada desse local.</span><span class="sxs-lookup"><span data-stu-id="16731-137">In addition, if an employee used a mobile device to access Microsoft 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="16731-138">Para saber mais, confira [Apagar e bloquear o dispositivo móvel de um funcionário antigo](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="16731-138">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="16731-139">Sincronizar os hashes de senhas do usuário de um Active Directory local para o Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="16731-139">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="16731-140">Este artigo é para configurar a política de expiração para usuários somente na nuvem (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="16731-140">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="16731-141">Isso não se aplica a usuários de identidade híbrida que usam sincronização hash de senha, autenticação de passagem ou federação local como o ADFS.</span><span class="sxs-lookup"><span data-stu-id="16731-141">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="16731-142">Para saber como sincronizar hashes de senha de usuário do AD local para o Azure AD, confira [implementar a sincronização de hash de senha com a sincronização de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="16731-142">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
