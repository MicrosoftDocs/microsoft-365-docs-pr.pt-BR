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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Saiba como definir uma política de expiração de senha para sua organização no centro de administração do Microsoft 365.
ms.openlocfilehash: 0280f4fd43034f9ffb70104771fa4a099943af2d
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500229"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="cda3d-103">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="cda3d-103">Set the password expiration policy for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="cda3d-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="cda3d-104">The admin center is changing.</span></span> <span data-ttu-id="cda3d-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="cda3d-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?view=o365-worldwide).</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="cda3d-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cda3d-106">Before you begin</span></span>

<span data-ttu-id="cda3d-107">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="cda3d-107">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="cda3d-108">Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cda3d-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="cda3d-109">[O que é uma conta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span><span class="sxs-lookup"><span data-stu-id="cda3d-109">[What's an admin account?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview).</span></span>

<span data-ttu-id="cda3d-110">Como administrador, você pode fazer as senhas de usuário expirarem após um determinado número de dias ou definir as senhas para nunca expirarem.</span><span class="sxs-lookup"><span data-stu-id="cda3d-110">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> <span data-ttu-id="cda3d-111">Por padrão, as senhas da sua organização estão definidas para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="cda3d-111">By default, passwords are set to never expire for your organization.</span></span>

<span data-ttu-id="cda3d-112">A pesquisa atual indica que as alterações de senha obrigatórias são mais prejudicadas do que o recomendado.</span><span class="sxs-lookup"><span data-stu-id="cda3d-112">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="cda3d-113">Eles direcionam os usuários a escolher senhas mais fracas, reutilizar senhas ou atualizar senhas antigas de maneiras que são facilmente adivinhadas pelos hackers.</span><span class="sxs-lookup"><span data-stu-id="cda3d-113">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="cda3d-114">Recomendamos habilitar a [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="cda3d-114">We recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="cda3d-115">Você deve ser um administrador [global](../add-users/about-admin-roles.md) para executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="cda3d-115">You must be a [global admin](../add-users/about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="cda3d-116">Se é um usuário, você não tem as permissões para definir a senha para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="cda3d-116">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="cda3d-117">Peça ao suporte técnico do seu trabalho ou da sua escola que faça isso para você. </span><span class="sxs-lookup"><span data-stu-id="cda3d-117">Ask your work or school technical support to do the steps in this article for you.</span></span>

## <a name="set-password-expiration-policy"></a><span data-ttu-id="cda3d-118">Definir política de expiração de senha</span><span class="sxs-lookup"><span data-stu-id="cda3d-118">Set password expiration policy</span></span>

<span data-ttu-id="cda3d-119">Siga as etapas abaixo se desejar definir as senhas dos usuários para expirarem após um período de tempo específico.</span><span class="sxs-lookup"><span data-stu-id="cda3d-119">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>

1. <span data-ttu-id="cda3d-120">No centro de administração do, vá para **Configurações** \> **Configurações da Organização**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-120">In the admin center, go to the **Settings** \> **Org Settings**.</span></span>

2. <span data-ttu-id="cda3d-121">Vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Segurança e privacidade</a>.</span><span class="sxs-lookup"><span data-stu-id="cda3d-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="cda3d-122">Se você não for um administrador global, não verá a opção Segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="cda3d-122">If you aren't a global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="cda3d-123">Selecione **Política de expiração de senha**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-123">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="cda3d-124">Se você não deseja que os usuários alterem as senhas, desmarque a caixa ao lado de **Definir as senhas dos usuários para expirar após alguns dias**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-124">If you don't want users to have to change passwords, uncheck the box next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="cda3d-125">Digite a frequência com que as senhas devem expirar.</span><span class="sxs-lookup"><span data-stu-id="cda3d-125">Type how often passwords should expire.</span></span> <span data-ttu-id="cda3d-126">Escolha um número de dias entre 14 e 730.</span><span class="sxs-lookup"><span data-stu-id="cda3d-126">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="cda3d-127">Na segunda caixa, insira quando os usuários são notificados de que a senha expirará e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cda3d-127">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="cda3d-128">Escolha um número de dias de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="cda3d-128">Choose a number of days from 1 to 30.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="cda3d-129">Pontos importantes que você precisa saber sobre o recurso de expiração de senha</span><span class="sxs-lookup"><span data-stu-id="cda3d-129">Important things you need to know about the password expiration feature</span></span>
  
- <span data-ttu-id="cda3d-p109">As pessoas que só usam o aplicativo do Outlook não terão de redefinir a senha do Microsoft 365 até que ela expire no cache. Isso pode levar vários dias após a data de validade real. Não há soluções alternativas para isso ao nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="cda3d-p109">People who only use the Outlook app won't be forced to reset their Microsoft 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>

## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="cda3d-133">Impedir que a última senha seja utilizada novamente</span><span class="sxs-lookup"><span data-stu-id="cda3d-133">Prevent last password from being used again</span></span>

<span data-ttu-id="cda3d-134">Se quiser impedir que seus usuários reciclem senhas antigas, você pode fazê-lo aplicando essa regra no histórico de senhas do Active Directory (AD) local.</span><span class="sxs-lookup"><span data-stu-id="cda3d-134">If you want to prevent your users from recycling old passwords, you can do so by enforcing password history in on-premises Active Directory (AD).</span></span> <span data-ttu-id="cda3d-135">Confira [Criar uma política de senha personalizada](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span><span class="sxs-lookup"><span data-stu-id="cda3d-135">See [Create a custom password policy](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).</span></span>

<span data-ttu-id="cda3d-136">No Azure AD, a última senha não pode ser usada novamente quando o usuário altera uma senha.</span><span class="sxs-lookup"><span data-stu-id="cda3d-136">In Azure AD, The last password can't be used again when the user changes a password.</span></span> <span data-ttu-id="cda3d-137">A política de senha é aplicada a todas as contas de usuário que são criadas e gerenciadas diretamente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="cda3d-137">The password policy is applied to all user accounts that are created and managed directly in Azure AD.</span></span> <span data-ttu-id="cda3d-138">Essa política de senhas não pode ser modificada.</span><span class="sxs-lookup"><span data-stu-id="cda3d-138">This password policy can't be modified.</span></span> <span data-ttu-id="cda3d-139">Confira [Políticas de senha do Azure AD](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span><span class="sxs-lookup"><span data-stu-id="cda3d-139">See [Azure AD password policies](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).</span></span>

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a><span data-ttu-id="cda3d-140">Sincronizar os hashes de senhas do usuário de um Active Directory local para o Azure AD (Microsoft 365)</span><span class="sxs-lookup"><span data-stu-id="cda3d-140">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Microsoft 365)</span></span>

<span data-ttu-id="cda3d-141">Este artigo é para configurar a política de expiração para usuários somente na nuvem (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="cda3d-141">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="cda3d-142">Isto não se aplica a usuários de identidade híbrida que usam sincronização hash de senha, autenticação de passagem ou federação local como o ADFS.</span><span class="sxs-lookup"><span data-stu-id="cda3d-142">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication, or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="cda3d-143">Para saber como sincronizar hashes de senha de usuário do AD local para o Azure AD, confira [implementar a sincronização de hash de senha com a sincronização de Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="cda3d-143">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a><span data-ttu-id="cda3d-144">Confira as restrições de conta e políticas de senha no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cda3d-144">Password policies and account restrictions in Azure Active Directory</span></span>

<span data-ttu-id="cda3d-145">Você pode definir mais restrições e políticas de senha no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cda3d-145">You can set more password policies and restrictions in Azure active directory.</span></span> <span data-ttu-id="cda3d-146">Confira as [restrições de conta e políticas de senha no Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) para mais informações.</span><span class="sxs-lookup"><span data-stu-id="cda3d-146">Check out [Password policies and account restrictions in Azure Active Directory](/azure/active-directory/authentication/concept-sspr-policy) for more info.</span></span>

## <a name="update-password-policy"></a><span data-ttu-id="cda3d-147">Atualizar a Política de senhas</span><span class="sxs-lookup"><span data-stu-id="cda3d-147">Update password Policy</span></span>

<span data-ttu-id="cda3d-148">O cmdlet Set-MsolPasswordPolicy atualiza a política de senhas de um determinado domínio ou locatário.</span><span class="sxs-lookup"><span data-stu-id="cda3d-148">The Set-MsolPasswordPolicy cmdlet updates the password policy of a specified domain or tenant.</span></span> <span data-ttu-id="cda3d-149">Duas configurações são necessárias. a primeira é para indicar o período de tempo que uma senha permanece válida antes de ser alterada e a segunda é indicar o número de dias antes da data de vencimento da senha que será disparada quando os usuários receberem suas primeiras notificações de que a senha irá expirar em breve.</span><span class="sxs-lookup"><span data-stu-id="cda3d-149">Two settings are required; the first is to indicate the length of time that a password remains valid before it must be changed and the second is to indicate the number of days before the password expiration date that will trigger when users will receive their first notification that their password will soon expire.</span></span>

<span data-ttu-id="cda3d-150">Para saber como atualizar a política de senha de um específico domínio ou locatário, confira [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="cda3d-150">To learn how to update password policy for a specific domain or tenant, see [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).</span></span>

## <a name="related-content"></a><span data-ttu-id="cda3d-151">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="cda3d-151">Related content</span></span>

[<span data-ttu-id="cda3d-152">Permitir que os usuários redefinam as próprias senhas</span><span class="sxs-lookup"><span data-stu-id="cda3d-152">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="cda3d-153">Redefinir senhas</span><span class="sxs-lookup"><span data-stu-id="cda3d-153">Reset passwords</span></span>](../add-users/reset-passwords.md)