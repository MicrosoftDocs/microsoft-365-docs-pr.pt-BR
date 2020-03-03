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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Saiba como definir uma política de expiração de senha para sua organização no centro de administração do Microsoft 365. '
ms.openlocfilehash: 88953317bea2b96c04c291dd028a4e9131b9a83e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361656"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a><span data-ttu-id="02556-103">Definir a política de expiração de senha para sua organização</span><span class="sxs-lookup"><span data-stu-id="02556-103">Set the password expiration policy for your organization</span></span>

<span data-ttu-id="02556-104">Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.</span><span class="sxs-lookup"><span data-stu-id="02556-104">This article is for people who set password expiration policy for a business, school, or nonprofit.</span></span>  

<span data-ttu-id="02556-105">Se é um usuário, você não tem as permissões para definir a senha para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="02556-105">If you're a user, you don't have the permissions to set your password to never expire.</span></span> <span data-ttu-id="02556-106">Peça ao suporte técnico do seu trabalho ou da sua escola que faça isso para você. </span><span class="sxs-lookup"><span data-stu-id="02556-106">Ask your work or school technical support to do the steps in this article for you.</span></span>

<span data-ttu-id="02556-107">Como administrador, você pode fazer as senhas de usuário expirarem após um determinado número de dias ou definir as senhas para nunca expirarem.</span><span class="sxs-lookup"><span data-stu-id="02556-107">As an admin, you can make user passwords expire after a certain number of days, or set passwords to never expire.</span></span> 

> [!Tip]
> <span data-ttu-id="02556-108">Por padrão, as senhas estão definidas para expirar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="02556-108">By default, passwords are set to expire in 90 days.</span></span> <span data-ttu-id="02556-109">A pesquisa atual indica que as alterações de senha obrigatórias são mais prejudicadas do que o recomendado.</span><span class="sxs-lookup"><span data-stu-id="02556-109">Current research strongly indicates that mandated password changes do more harm than good.</span></span> <span data-ttu-id="02556-110">Eles direcionam os usuários a escolher senhas mais fracas, reutilizar senhas ou atualizar senhas antigas de maneiras que são facilmente adivinhadas pelos hackers.</span><span class="sxs-lookup"><span data-stu-id="02556-110">They drive users to choose weaker passwords, re-use passwords, or update old passwords in ways that are easily guessed by hackers.</span></span> <span data-ttu-id="02556-111">Se a senha for configurada para nunca expirar, recomendamos habilitar a [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="02556-111">If setting password to never expire, we recommend enabling [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

<span data-ttu-id="02556-112">Siga as etapas abaixo se desejar definir as senhas dos usuários para expirarem após um período de tempo específico.</span><span class="sxs-lookup"><span data-stu-id="02556-112">Follow the steps below if you want to set user passwords to expire after a specific amount of time.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="02556-113">Apenas os [administradores globais do Office 365](../add-users/about-admin-roles.md) pode executar essas etapas.</span><span class="sxs-lookup"><span data-stu-id="02556-113">Only [Office 365 global admins](../add-users/about-admin-roles.md) can perform these steps.</span></span>
  
1. <span data-ttu-id="02556-114">No centro de administração do, vá para **Configurações** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="02556-114">In the admin center, go to the **Settings** \> **Settings**.</span></span>

2. <span data-ttu-id="02556-115">Vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Segurança e privacidade</a>.</span><span class="sxs-lookup"><span data-stu-id="02556-115">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Security & privacy</a> page.</span></span>
 <span data-ttu-id="02556-116">Se você não for um administrador global do Office 365, não verá a opção de Segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="02556-116">If you aren't an Office 365 global admin, you won't see the Security and privacy option.</span></span>
  
3. <span data-ttu-id="02556-117">Selecione **Política de expiração de senha**.</span><span class="sxs-lookup"><span data-stu-id="02556-117">Select **Password expiration policy**.</span></span>
  
4. <span data-ttu-id="02556-118">Se você não quiser que os usuários tenham que alterar as senhas, marque a caixa de seleção ao lado de **Definir senhas de usuário para expirar após um número de dias**.</span><span class="sxs-lookup"><span data-stu-id="02556-118">If you don't want users to have to change passwords, select the checkbox next to **Set user passwords to expire after a number of days**.</span></span>
  
5. <span data-ttu-id="02556-119">Digite a frequência com que as senhas devem expirar.</span><span class="sxs-lookup"><span data-stu-id="02556-119">Type how often passwords should expire.</span></span> <span data-ttu-id="02556-120">Escolha um número de dias entre 14 e 730.</span><span class="sxs-lookup"><span data-stu-id="02556-120">Choose a number of days from 14 to 730.</span></span>
  
6. <span data-ttu-id="02556-121">Na segunda caixa, insira quando os usuários são notificados de que a senha expirará e, em seguida, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02556-121">In the second box type when users are notified that their password will expire, and then select **Save**.</span></span> <span data-ttu-id="02556-122">Escolha um número de dias de 1 a 30.</span><span class="sxs-lookup"><span data-stu-id="02556-122">Choose a number of days from 1 to 30.</span></span>
    
7. <span data-ttu-id="02556-123">Quando a senha do usuário expirar, ele receberá uma notificação que aparecerá no canto inferior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="02556-123">When the user's password expires, they'll get a notification that appears in the lower right corner of their screen.</span></span>
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a><span data-ttu-id="02556-124">Pontos importantes que você precisa saber sobre o recurso de expiração de senha</span><span class="sxs-lookup"><span data-stu-id="02556-124">Important things you need to know about the password expiration feature</span></span>

<span data-ttu-id="02556-125">Vejamos alguns pontos que você precisa saber sobre como esse recurso funcionará a partir de janeiro de 2018:</span><span class="sxs-lookup"><span data-stu-id="02556-125">Here are some things to know about how this feature currently works as of January 2018:</span></span>
  
- <span data-ttu-id="02556-p106">As pessoas que só usam o aplicativo do Outlook não terão de redefinir a senha do Office 365 até que ela expire no cache. Isso pode ser vários dias após a data de validade real. Não há soluções alternativas para isso ao nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="02556-p106">People who only use the Outlook app won't be forced to reset their Office 365 password until it expires in the cache. This can be several days after the actual expiration date. There's no workaround for this at the admin level.</span></span>
    
- <span data-ttu-id="02556-p107">Os usuários não receberão uma notificação por email informando que a senha expirará em um número X de dias. Quer esse recurso? **[Vote aqui!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span><span class="sxs-lookup"><span data-stu-id="02556-p107">Users do not get an email notification that their password is going to expire in X number of days. Do you want this feature? **[Vote here!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**</span></span>
    
## <a name="prevent-last-password-from-being-used-again"></a><span data-ttu-id="02556-132">Impedir que a última senha seja utilizada novamente</span><span class="sxs-lookup"><span data-stu-id="02556-132">Prevent last password from being used again</span></span>

<span data-ttu-id="02556-133">Se quiser impedir que os usuários promovam a reciclagem de senhas antigas, use o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="02556-133">If you want to prevent your users from recycling old passwords, you can do so in Azure AD.</span></span> <span data-ttu-id="02556-134">Consulte [Definir a política de expiração da senha da sua organização](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="02556-134">See [Set the password expiration policy for your organization](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).</span></span>

<span data-ttu-id="02556-135">Além disso, se um funcionário tiver usado um dispositivo móvel para acessar o Office 365, você poderá apagá-lo a fim de garantir que a senha não seja armazenada e reciclada desse local.</span><span class="sxs-lookup"><span data-stu-id="02556-135">In addition, if an employee used a mobile device to access Office 365, you can wipe it to ensure the password is no longer stored and recycled from there.</span></span> <span data-ttu-id="02556-136">Para saber mais, confira [Apagar e bloquear o dispositivo móvel de um funcionário antigo](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span><span class="sxs-lookup"><span data-stu-id="02556-136">To learn more, see [Wipe and block a former employee's mobile device](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).</span></span>


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-office-365"></a><span data-ttu-id="02556-137">Sincronizar hashes de senhas do usuário de um Active Directory local para o Azure AD (Office 365)</span><span class="sxs-lookup"><span data-stu-id="02556-137">Synchronize user passwords hashes from an on-premises Active Directory to Azure AD (Office 365)</span></span>

<span data-ttu-id="02556-138">Este artigo é para configurar a política de expiração para usuários somente na nuvem (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="02556-138">This article is for setting the expiration policy for cloud-only users (Azure AD).</span></span> <span data-ttu-id="02556-139">Isso não se aplica a usuários de identidade híbrida que usam sincronização hash de senha, autenticação de passagem ou federação local como o ADFS.</span><span class="sxs-lookup"><span data-stu-id="02556-139">It doesn't apply to hybrid identity users who use password hash sync, pass-through authentication or on-premises federation like ADFS.</span></span>
  
<span data-ttu-id="02556-140">Para saber como sincronizar hashes de senha de usuário do AD local para o Azure AD, confira [implementar a sincronização de hash de senha com a sincronização de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span><span class="sxs-lookup"><span data-stu-id="02556-140">To learn how to synchronize user password hashes from on premises AD to Azure AD, see [Implement password hash synchronization with Azure AD Connect sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).</span></span>
