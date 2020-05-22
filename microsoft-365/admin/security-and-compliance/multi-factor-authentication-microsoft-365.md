---
title: Autenticação multifator para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre a autenticação multifator no Microsoft 365.
ms.openlocfilehash: 128296b7dbc37ba5ebffb25a87bce589f8e5a904
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340817"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="b1df0-103">Autenticação multifator para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1df0-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="b1df0-104">As senhas são o método mais comum de autenticar uma entrada em um computador ou serviço online, mas elas também são mais vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="b1df0-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="b1df0-105">As pessoas podem escolher senhas fáceis e usar as mesmas senhas para várias entradas em diferentes computadores e serviços.</span><span class="sxs-lookup"><span data-stu-id="b1df0-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="b1df0-106">Para fornecer um nível adicional de segurança para os logins, você deve usar a MFA (autenticação multifator), que usa uma senha, que deve ser forte, e um método de verificação adicional baseado em:</span><span class="sxs-lookup"><span data-stu-id="b1df0-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="b1df0-107">Algo que você tem com você não é facilmente duplicado, como um telefone inteligente.</span><span class="sxs-lookup"><span data-stu-id="b1df0-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="b1df0-108">Algo que você tem exclusivamente e biológica, como digitalização, face ou outro atributo biométrico.</span><span class="sxs-lookup"><span data-stu-id="b1df0-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="b1df0-109">O método de verificação adicional não é empregado até que a senha do usuário tenha sido verificada.</span><span class="sxs-lookup"><span data-stu-id="b1df0-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="b1df0-110">Com a MFA, mesmo que uma senha de usuário forte seja comprometida, o invasor não tem seu telefone inteligente ou impressão digital para concluir a entrada.</span><span class="sxs-lookup"><span data-stu-id="b1df0-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="b1df0-111">Suporte da MFA no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1df0-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="b1df0-112">Por padrão, tanto o Microsoft 365 quanto o Office 365 dão suporte à MFA de contas de usuário usando:</span><span class="sxs-lookup"><span data-stu-id="b1df0-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="b1df0-113">Uma mensagem de texto enviada a um telefone que exige que o usuário digite um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="b1df0-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="b1df0-114">Uma chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="b1df0-114">A phone call.</span></span>
- <span data-ttu-id="b1df0-115">O aplicativo de telefone inteligente Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="b1df0-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="b1df0-116">Em ambos os casos, a entrada MFA está usando o método "algo que você tem com você não é facilmente duplicado" para a verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="b1df0-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="b1df0-117">Há várias maneiras nas quais você pode habilitar a MFA para o Microsoft 365 e o Office 365:</span><span class="sxs-lookup"><span data-stu-id="b1df0-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="b1df0-118">Com padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="b1df0-118">With security defaults</span></span>
- <span data-ttu-id="b1df0-119">Com políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-119">With Conditional Access policies</span></span>
- <span data-ttu-id="b1df0-120">Para cada conta de usuário individual (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="b1df0-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="b1df0-121">Essas formas se baseiam no seu plano Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1df0-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="b1df0-122">Plano</span><span class="sxs-lookup"><span data-stu-id="b1df0-122">Plan</span></span>  |<span data-ttu-id="b1df0-123">Recomendação</span><span class="sxs-lookup"><span data-stu-id="b1df0-123">Recommendation</span></span>  | <span data-ttu-id="b1df0-124">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="b1df0-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="b1df0-125">Todos os planos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1df0-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="b1df0-126">Use os padrões de segurança, que requerem MFA para todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="b1df0-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="b1df0-127">Você também pode exigir a MFA em uma conta por usuário, mas isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="b1df0-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="b1df0-128">Pequena empresa</span><span class="sxs-lookup"><span data-stu-id="b1df0-128">Small business</span></span> |
| <span data-ttu-id="b1df0-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1df0-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="b1df0-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="b1df0-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="b1df0-131">Azure Active Directory (Azure AD) licenças Premium P1</span><span class="sxs-lookup"><span data-stu-id="b1df0-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="b1df0-132">Use as políticas de acesso condicional para exigir a MFA de contas de usuário com base na associação de grupo, aplicativos ou outros critérios.</span><span class="sxs-lookup"><span data-stu-id="b1df0-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="b1df0-133">Pequena empresa para empresas</span><span class="sxs-lookup"><span data-stu-id="b1df0-133">Small business to enterprise</span></span> |
| <span data-ttu-id="b1df0-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b1df0-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="b1df0-135">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="b1df0-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="b1df0-136">Use a proteção de identidade do Azure AD para exigir a MFA com base nos critérios de risco de entrada.</span><span class="sxs-lookup"><span data-stu-id="b1df0-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="b1df0-137">Corporativo</span><span class="sxs-lookup"><span data-stu-id="b1df0-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="b1df0-138">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="b1df0-138">Security defaults</span></span>

<span data-ttu-id="b1df0-139">Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="b1df0-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="b1df0-140">Essas assinaturas têm os padrões de segurança ativados, que:</span><span class="sxs-lookup"><span data-stu-id="b1df0-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="b1df0-141">Requer que todos os usuários usem a MFA com o aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="b1df0-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="b1df0-142">Bloqueia a autenticação herdada.</span><span class="sxs-lookup"><span data-stu-id="b1df0-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="b1df0-143">Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados.</span><span class="sxs-lookup"><span data-stu-id="b1df0-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="b1df0-144">Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.</span><span class="sxs-lookup"><span data-stu-id="b1df0-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="b1df0-145">Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b1df0-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="b1df0-146">Você pode desabilitar os padrões de segurança em favor da MFA com políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="b1df0-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="b1df0-147">Habilite ou desabilite os padrões de segurança no painel de **Propriedades** do Azure AD no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b1df0-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="b1df0-148">Você pode usar os padrões de segurança com qualquer plano do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1df0-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="b1df0-149">Para obter mais informações, confira esta [visão geral dos padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="b1df0-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="b1df0-150">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-150">Conditional Access policies</span></span>

<span data-ttu-id="b1df0-151">As políticas de acesso condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e permitidas.</span><span class="sxs-lookup"><span data-stu-id="b1df0-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="b1df0-152">Por exemplo, você pode criar uma política de acesso condicional que declare:</span><span class="sxs-lookup"><span data-stu-id="b1df0-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="b1df0-153">Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.</span><span class="sxs-lookup"><span data-stu-id="b1df0-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="b1df0-154">Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="b1df0-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="b1df0-155">Você também pode usar as políticas de acesso condicional para recursos mais avançados, como a solicitação de MFA de aplicativos específicos ou que a entrada é feita de um dispositivo compatível, como o laptop executando o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b1df0-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="b1df0-156">Configure as políticas de acesso condicional do painel de **segurança** para o Azure AD no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b1df0-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="b1df0-157">Você pode usar políticas de acesso condicional com:</span><span class="sxs-lookup"><span data-stu-id="b1df0-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="b1df0-158">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1df0-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="b1df0-159">Microsoft 365 E3 e e5</span><span class="sxs-lookup"><span data-stu-id="b1df0-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="b1df0-160">Licenças do Azure AD Premium P1 e do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="b1df0-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="b1df0-161">Para pequenas empresas com o Microsoft 365 Business Premium, você pode facilmente usar as políticas de acesso condicional com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b1df0-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="b1df0-162">Crie um grupo para conter as contas de usuário que requerem MFA.</span><span class="sxs-lookup"><span data-stu-id="b1df0-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="b1df0-163">Habilite a política **exigir MFA para administradores globais** .</span><span class="sxs-lookup"><span data-stu-id="b1df0-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="b1df0-164">Crie uma política de acesso condicional com base em grupo com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="b1df0-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="b1df0-165">Atribuições > usuários e grupos: o nome do grupo da etapa 1 acima.</span><span class="sxs-lookup"><span data-stu-id="b1df0-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="b1df0-166">Atribuições > aplicativos ou ações em nuvem: todos os aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b1df0-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="b1df0-167">Controles de acesso > conceder > conceder acesso > exigem autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="b1df0-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="b1df0-168">Habilitar a política.</span><span class="sxs-lookup"><span data-stu-id="b1df0-168">Enable the policy.</span></span>
5. <span data-ttu-id="b1df0-169">Adicione uma conta de usuário ao grupo criado na etapa 1 acima e teste.</span><span class="sxs-lookup"><span data-stu-id="b1df0-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="b1df0-170">Para exigir a MFA de contas de usuário adicionais, adicione-as ao grupo criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b1df0-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="b1df0-171">Essa política de acesso condicional permite que você distribua o requisito da MFA para seus usuários em seu próprio ritmo.</span><span class="sxs-lookup"><span data-stu-id="b1df0-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="b1df0-172">As empresas devem usar [políticas de acesso condicional comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="b1df0-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="b1df0-173">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="b1df0-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="b1df0-174">Exigir MFA para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="b1df0-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="b1df0-175">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="b1df0-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="b1df0-176">Para mais informações, confira esta [visão geral do Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="b1df0-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="b1df0-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b1df0-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="b1df0-178">Com o Azure AD Identity Protection, você pode criar uma política de acesso condicional adicional para [exigir a MFA quando o risco de entrada for médio ou alto](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="b1df0-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="b1df0-179">Você pode usar a proteção de identidade do Azure AD e políticas de acesso condicional com base em risco com:</span><span class="sxs-lookup"><span data-stu-id="b1df0-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="b1df0-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="b1df0-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="b1df0-181">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="b1df0-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="b1df0-182">Para obter mais informações, confira esta [visão geral da Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="b1df0-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="b1df0-183">MFA de uma conta de usuário individual (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="b1df0-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="b1df0-184">Você deve usar os padrões de segurança ou as políticas de acesso condicional para exigir a MFA de suas entradas de conta de usuário. No entanto, se qualquer um desses não puder ser usado, a Microsoft recomenda a MFA de contas de usuário com funções de administrador, especialmente a função de administrador global, para qualquer assinatura de tamanho.</span><span class="sxs-lookup"><span data-stu-id="b1df0-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="b1df0-185">Habilite a MFA para contas de usuário individuais no painel de **usuário ativo** do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1df0-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="b1df0-186">Após a habilitação, na próxima vez que o usuário entrar, ele será solicitado a registrar a MFA e a escolher e testar o método de verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="b1df0-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="b1df0-187">Usando esses métodos juntos</span><span class="sxs-lookup"><span data-stu-id="b1df0-187">Using these methods together</span></span>

<span data-ttu-id="b1df0-188">Esta tabela mostra os resultados da ativação da MFA com padrões de segurança, políticas de Acesso Condicional e configurações de conta por usuário.</span><span class="sxs-lookup"><span data-stu-id="b1df0-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="b1df0-189">Habilitado</span><span class="sxs-lookup"><span data-stu-id="b1df0-189">Enabled</span></span> | <span data-ttu-id="b1df0-190">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="b1df0-190">Disabled</span></span> | <span data-ttu-id="b1df0-191">Método de autenticação secundária</span><span class="sxs-lookup"><span data-stu-id="b1df0-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="b1df0-192">**Padrões de segurança**</span><span class="sxs-lookup"><span data-stu-id="b1df0-192">**Security defaults**</span></span> | <span data-ttu-id="b1df0-193">Não é possível usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="b1df0-194">Pode usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="b1df0-195">Aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="b1df0-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="b1df0-196">**Políticas de Acesso Condicional**</span><span class="sxs-lookup"><span data-stu-id="b1df0-196">**Conditional Access policies**</span></span> |<span data-ttu-id="b1df0-197">Se alguma delas estiver habilitada, você não poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="b1df0-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="b1df0-198">Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="b1df0-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="b1df0-199">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="b1df0-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="b1df0-200">**Configuração de conta por usuário (não recomendado)**</span><span class="sxs-lookup"><span data-stu-id="b1df0-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="b1df0-201">Substituído por padrões de segurança e políticas de acesso condicional que exigem MFA</span><span class="sxs-lookup"><span data-stu-id="b1df0-201">Overridden by security defaults and Conditional Access policies requiring MFA</span></span> | <span data-ttu-id="b1df0-202">Substituído por padrões de segurança e políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="b1df0-203">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="b1df0-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="b1df0-204">Se os padrões de segurança estiverem habilitados, todos os novos usuários serão solicitados a registrar o registro MFA e o uso do aplicativo Microsoft Authenticator na próxima entrada.</span><span class="sxs-lookup"><span data-stu-id="b1df0-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

<span data-ttu-id="b1df0-205">No entanto, se um usuário tiver um telefone mais antigo que possa receber mensagens de texto, mas não puder executar o aplicativo Microsoft Authenticator, você poderá habilitar a MFA nessa conta de usuário específica e fazer com que ela se registre usando o método de verificação adicional de código de texto com estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b1df0-205">However, if a user has an older phone that can receive text messages but cannot run the Microsoft Authenticator app, you can enable MFA on that specific user account and have them register using the text code additional verification method with these steps:</span></span>

1. <span data-ttu-id="b1df0-206">Desabilite os padrões de segurança no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b1df0-206">Disable security defaults in the Azure portal.</span></span>
2. <span data-ttu-id="b1df0-207">Habilitar a MFA da conta de usuário no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1df0-207">Enable MFA for the user account in the Microsoft 365 admin center.</span></span>
3. <span data-ttu-id="b1df0-208">Faça o usuário entrar e registrar-se na MFA e o método de autenticação de código de texto.</span><span class="sxs-lookup"><span data-stu-id="b1df0-208">Have the user sign in and register for MFA and the text code authentication method.</span></span>
4. <span data-ttu-id="b1df0-209">Ao concluir, habilitar padrões de segurança no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="b1df0-209">When complete, enable security defaults in the Azure portal</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="b1df0-210">Maneiras de gerenciar as configurações da MFA</span><span class="sxs-lookup"><span data-stu-id="b1df0-210">Ways to manage MFA settings</span></span>

<span data-ttu-id="b1df0-211">Há duas maneiras de gerenciar as configurações da MFA.</span><span class="sxs-lookup"><span data-stu-id="b1df0-211">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="b1df0-212">No portal do Azure, você pode:</span><span class="sxs-lookup"><span data-stu-id="b1df0-212">In the Azure portal, you can:</span></span>

- <span data-ttu-id="b1df0-213">Habilitar e desabilitar padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="b1df0-213">Enable and disable security defaults</span></span>
- <span data-ttu-id="b1df0-214">Configurar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b1df0-214">Configure Conditional Access policies</span></span>

<span data-ttu-id="b1df0-215">No centro de administração do Microsoft 365, é possível definir as configurações do serviço por usuário e da MFA.</span><span class="sxs-lookup"><span data-stu-id="b1df0-215">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="b1df0-216">Sua próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b1df0-216">Your next step</span></span>

[<span data-ttu-id="b1df0-217">Configurar a MFA para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1df0-217">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

