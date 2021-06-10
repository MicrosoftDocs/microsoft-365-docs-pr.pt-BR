---
title: Ativar padrões de segurança
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como os padrões de segurança podem ajudar a proteger sua organização contra ataques relacionados à identidade fornecendo configurações de segurança pré-configuradas.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398284"
---
# <a name="turn-on-security-defaults"></a><span data-ttu-id="da205-103">Ativar padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="da205-103">Turn on security defaults</span></span>

<span data-ttu-id="da205-104">Os padrões de segurança ajudam a proteger sua organização contra ataques relacionados à identidade fornecendo configurações de segurança pré-configuradas que a Microsoft gerencia em nome da sua organização.</span><span class="sxs-lookup"><span data-stu-id="da205-104">Security defaults help protect your organization from identity-related attacks by providing preconfigured security settings that Microsoft manages on behalf of your organization.</span></span> <span data-ttu-id="da205-105">Essas configurações incluem a habilitação da autenticação multifafação (MFA) para todos os administradores e contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="da205-105">These settings include enabling multi-factor authentication (MFA) for all admins and user accounts.</span></span> <span data-ttu-id="da205-106">Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança de login adicional.</span><span class="sxs-lookup"><span data-stu-id="da205-106">For most organizations, security defaults offer a good level of additional sign-in security.</span></span>

<span data-ttu-id="da205-107">Para obter mais informações sobre os padrões de segurança e as políticas que eles impõem, consulte [O que são padrões de segurança?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span><span class="sxs-lookup"><span data-stu-id="da205-107">For more information about security defaults and the policies they enforce, see [What are security defaults?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)</span></span>

<span data-ttu-id="da205-108">Se sua assinatura foi criada em ou após 22 de outubro de 2019, os padrões de segurança podem ter sido habilitados automaticamente para você, você deve verificar suas configurações para &mdash; confirmar.</span><span class="sxs-lookup"><span data-stu-id="da205-108">If your subscription was created on or after October 22, 2019, security defaults might have been automatically enabled for you&mdash;you should check your settings to confirm.</span></span>

<span data-ttu-id="da205-109">Para habilitar os padrões de segurança em seu Azure Active Directory (Azure AD) ou para verificar se eles já estão habilitados:</span><span class="sxs-lookup"><span data-stu-id="da205-109">To enable security defaults in your Azure Active Directory (Azure AD) or to check to see if they're already enabled:</span></span>

1. <span data-ttu-id="da205-110">Entre no centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 com</a> credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="da205-110">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> with Global admin credentials.</span></span>

2. <span data-ttu-id="da205-111">No painel esquerdo, selecione **Mostrar Tudo e,** em Centros **de administração,** selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="da205-111">In the left pane, select **Show All,** and then under **Admin centers**, select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="da205-112">No painel esquerdo do centro de administração **Azure Active Directory,** selecione **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="da205-112">In the left pane of the **Azure Active Directory admin center,** select **Azure Active Directory**.</span></span>

4. <span data-ttu-id="da205-113">No menu esquerdo do Painel, na seção **Gerenciar,** selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="da205-113">From the left menu of the Dashboard, in the **Manage** section, select **Properties**.</span></span>

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Captura de tela do Azure Active Directory de administração mostrando o local do item de menu Propriedades.":::

5. <span data-ttu-id="da205-115">Na parte inferior da página **Propriedades,** selecione **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="da205-115">At the bottom of the **Properties** page, select **Manage Security defaults**.</span></span>

6. <span data-ttu-id="da205-116">No painel direito, você verá a configuração **Habilitar padrões de** segurança.</span><span class="sxs-lookup"><span data-stu-id="da205-116">In the right pane, you'll see the **Enable Security defaults** setting.</span></span> <span data-ttu-id="da205-117">Se **Sim** estiver selecionado, os padrões de segurança já estão habilitados e nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="da205-117">If **Yes** is selected, then security defaults are already enabled and no further action is required.</span></span> <span data-ttu-id="da205-118">Se os padrões de segurança não estão habilitados no momento, selecione **Sim** para habilita-los e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="da205-118">If security defaults are not currently enabled, then select **Yes** to enable them, and then select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="da205-119">Se você estiver usando políticas de Acesso Condicional, precisará afuní-las antes de usar os padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="da205-119">If you've been using Conditional Access policies, you'll need to turn them off before using security defaults.</span></span>
>
> <span data-ttu-id="da205-120">Você pode usar os padrões de segurança ou políticas de Acesso Condicional, mas não pode usar ambos ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="da205-120">You can use either security defaults or Conditional Access policies, but you can't use both at the same time.</span></span>

## <a name="consider-using-conditional-access"></a><span data-ttu-id="da205-121">Considere usar o Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="da205-121">Consider using Conditional Access</span></span>

<span data-ttu-id="da205-122">Se sua organização tiver requisitos complexos de segurança ou precisar de controle mais granular sobre suas políticas de segurança, considere usar o Acesso Condicional em vez de padrões de segurança para obter uma postura de segurança semelhante ou superior.</span><span class="sxs-lookup"><span data-stu-id="da205-122">If your organization has complex security requirements or you need more granular control over your security policies, then you should consider using Conditional Access instead of security defaults to achieve a similar or higher security posture.</span></span> 

<span data-ttu-id="da205-123">O Acesso Condicional permite criar e definir políticas que reagem a eventos de entrada e solicitam ações adicionais antes que um usuário tenha acesso a um aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="da205-123">Conditional Access lets you create and define policies that react to sign-in events and request additional actions before a user is granted access to an application or service.</span></span> <span data-ttu-id="da205-124">As políticas de Acesso Condicional podem ser granulares e específicas, capacitando os usuários a serem produtivos sempre e sempre, mas também protegendo sua organização.</span><span class="sxs-lookup"><span data-stu-id="da205-124">Conditional Access policies can be granular and specific, empowering users to be productive wherever and whenever, but also protecting your organization.</span></span>

<span data-ttu-id="da205-125">Os padrões de segurança estão disponíveis para todos os clientes, enquanto o Acesso Condicional requer uma licença para um dos seguintes planos:</span><span class="sxs-lookup"><span data-stu-id="da205-125">Security defaults are available to all customers, while Conditional Access requires a license for one of the following plans:</span></span>

- <span data-ttu-id="da205-126">Azure Active Directory Premium P1 ou P2</span><span class="sxs-lookup"><span data-stu-id="da205-126">Azure Active Directory Premium P1 or P2</span></span>
- <span data-ttu-id="da205-127">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="da205-127">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="da205-128">Microsoft 365 E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="da205-128">Microsoft 365 E3 or E5</span></span>
- <span data-ttu-id="da205-129">Enterprise Mobility & Security E3 ou E5</span><span class="sxs-lookup"><span data-stu-id="da205-129">Enterprise Mobility & Security E3 or E5</span></span>

<span data-ttu-id="da205-130">Se você quiser usar o Acesso Condicional para configurar políticas equivalentes às habilitadas por padrões de segurança, confira os seguintes guias passo a passo:</span><span class="sxs-lookup"><span data-stu-id="da205-130">If you want to use Conditional Access to configure policies equivalent to those enabled by security defaults, check out the following step-by-step guides:</span></span>

- [<span data-ttu-id="da205-131">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="da205-131">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="da205-132">Exigir MFA para gerenciamento do Azure</span><span class="sxs-lookup"><span data-stu-id="da205-132">Require MFA for Azure management</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [<span data-ttu-id="da205-133">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="da205-133">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [<span data-ttu-id="da205-134">Exigir MFA para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="da205-134">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- <span data-ttu-id="da205-135">[Exigir o registro MFA do Azure AD](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requer a Proteção de Identidade do Azure AD, que faz parte Azure Active Directory Premium P2</span><span class="sxs-lookup"><span data-stu-id="da205-135">[Require Azure AD MFA registration](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requires Azure AD Identity Protection, which is part of Azure Active Directory Premium P2</span></span>

<span data-ttu-id="da205-136">Para saber mais sobre o Acesso Condicional, consulte [O que é o Acesso Condicional?](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="da205-136">To learn more about Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span> <span data-ttu-id="da205-137">Para obter mais informações sobre como criar políticas de Acesso Condicional, consulte [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span><span class="sxs-lookup"><span data-stu-id="da205-137">For more information about creating Conditional Access policies, see [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).</span></span>

> [!NOTE]
> <span data-ttu-id="da205-138">Se você tiver um plano ou licença que fornece Acesso Condicional, mas ainda não criou nenhuma política de Acesso Condicional, você pode usar os padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="da205-138">If you have a plan or license that provides Conditional Access but haven't yet created any Conditional Access policies, you're welcome to use security defaults.</span></span> <span data-ttu-id="da205-139">No entanto, você precisará desativar os padrões de segurança antes de poder usar as políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="da205-139">However, you'll need to turn off security defaults before you can use Conditional Access policies.</span></span>
