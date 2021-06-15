---
title: Autenticação multifator para Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: A autenticação multifato (MFA) usa uma senha, que deve ser forte, e um método de verificação adicional.
ms.openlocfilehash: d9af486cf5e53609557b519612f185a20729cf76
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924726"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="3e2e5-103">Autenticação multifator para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e2e5-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="3e2e5-104">As senhas são o método mais comum de autenticação de uma assinatura em um computador ou serviço online, mas também são as mais vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="3e2e5-105">As pessoas podem escolher senhas fáceis e usar as mesmas senhas para vários logins em computadores e serviços diferentes.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="3e2e5-106">Para fornecer um nível adicional de segurança para entrar, você deve usar a autenticação multifato (MFA), que usa uma senha, que deve ser forte, e um método de verificação adicional com base em:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="3e2e5-107">Algo que você tem com você que não é facilmente duplicado, como um telefone inteligente.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="3e2e5-108">Algo que você tem de forma exclusiva e biologicamente, como suas impressões digitais, face ou outro atributo biométrico.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="3e2e5-109">O método de verificação adicional não é empregado até que a senha do usuário seja verificada.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="3e2e5-110">Com o MFA, mesmo que uma senha de usuário forte seja comprometida, o invasor não tem seu smartphone ou sua impressão digital para concluir a login.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="3e2e5-111">Suporte A MFA no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e2e5-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="3e2e5-112">Por padrão, os Microsoft 365 e Office 365 suportam MFA para contas de usuário usando:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="3e2e5-113">Uma mensagem de texto enviada para um telefone que exige que o usuário digite um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="3e2e5-114">Uma chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-114">A phone call.</span></span>
- <span data-ttu-id="3e2e5-115">O Microsoft Authenticator de telefone inteligente.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="3e2e5-116">Em ambos os casos, a assinatura MFA está usando o método "algo que você tem com você que não é facilmente duplicado" para a verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="3e2e5-117">Há várias maneiras de habilitar o MFA para Microsoft 365 e Office 365:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="3e2e5-118">Com padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3e2e5-118">With security defaults</span></span>
- <span data-ttu-id="3e2e5-119">Com políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-119">With Conditional Access policies</span></span>
- <span data-ttu-id="3e2e5-120">Para cada conta de usuário individual (não recomendada)</span><span class="sxs-lookup"><span data-stu-id="3e2e5-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="3e2e5-121">Essas maneiras se baseiam no seu Microsoft 365 plano.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="3e2e5-122">Planejar</span><span class="sxs-lookup"><span data-stu-id="3e2e5-122">Plan</span></span>|<span data-ttu-id="3e2e5-123">Recomendação</span><span class="sxs-lookup"><span data-stu-id="3e2e5-123">Recommendation</span></span>|<span data-ttu-id="3e2e5-124">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="3e2e5-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="3e2e5-125">Todos os Microsoft 365 planos</span><span class="sxs-lookup"><span data-stu-id="3e2e5-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="3e2e5-126">Use padrões de segurança, que exigem MFA para todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="3e2e5-127">Você também pode configurar o MFA por usuário em contas de usuário individuais, mas isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="3e2e5-128">Pequena empresa</span><span class="sxs-lookup"><span data-stu-id="3e2e5-128">Small business</span></span>|
|<span data-ttu-id="3e2e5-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3e2e5-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="3e2e5-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="3e2e5-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="3e2e5-131">Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="3e2e5-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="3e2e5-132">Use políticas de Acesso Condicional para exigir MFA para contas de usuário com base em associação a grupos, aplicativos ou outros critérios.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="3e2e5-133">Pequenas empresas para empresas</span><span class="sxs-lookup"><span data-stu-id="3e2e5-133">Small business to enterprise</span></span>|
|<span data-ttu-id="3e2e5-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3e2e5-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="3e2e5-135">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="3e2e5-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="3e2e5-136">Use a Proteção de Identidade do Azure AD para exigir MFA com base nos critérios de risco de login.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="3e2e5-137">Corporativo</span><span class="sxs-lookup"><span data-stu-id="3e2e5-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="3e2e5-138">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3e2e5-138">Security defaults</span></span>

<span data-ttu-id="3e2e5-139">Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="3e2e5-140">Essas assinaturas têm padrões de segurança ativas, que:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="3e2e5-141">Exige que todos os usuários usem o MFA com o Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="3e2e5-142">Bloqueia a autenticação herdda.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="3e2e5-143">Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="3e2e5-144">Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="3e2e5-145">Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="3e2e5-146">Você pode desabilitar os padrões de segurança em favor do MFA com políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="3e2e5-147">Você habilita ou desabilita os padrões de segurança no painel **Propriedades** do Azure AD no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Imagem da página Propriedades do diretório.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="3e2e5-149">Você pode usar padrões de segurança com qualquer Microsoft 365 plano.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="3e2e5-150">Para obter mais informações, confira esta [visão geral dos padrões de segurança](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="3e2e5-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="3e2e5-151">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-151">Conditional Access policies</span></span>

<span data-ttu-id="3e2e5-152">As políticas de acesso condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e permitidas.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="3e2e5-153">Por exemplo, você pode criar uma política de acesso condicional que declare:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="3e2e5-154">Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="3e2e5-155">Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="3e2e5-156">Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir MFA para aplicativos específicos ou que a entrada é feita a partir de um dispositivo compatível, como seu laptop executando Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="3e2e5-157">Você configura políticas de Acesso Condicional no **painel** Segurança do Azure AD no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Imagem da opção de menu para Acesso Condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="3e2e5-159">Você pode usar políticas de Acesso Condicional com:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="3e2e5-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3e2e5-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="3e2e5-161">Microsoft 365 E3 e E5</span><span class="sxs-lookup"><span data-stu-id="3e2e5-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="3e2e5-162">Licenças do Azure AD Premium P1 e Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="3e2e5-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="3e2e5-163">Para pequenas empresas com Microsoft 365 Business Premium, você pode usar facilmente as políticas de Acesso Condicional com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="3e2e5-164">Crie um grupo para conter as contas de usuário que exigem MFA.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="3e2e5-165">Habilita **a política Exigir MFA para administradores globais.**</span><span class="sxs-lookup"><span data-stu-id="3e2e5-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="3e2e5-166">Crie uma política de Acesso Condicional baseada em grupo com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="3e2e5-167">Atribuições > Usuários e grupos: o nome do seu grupo da Etapa 1 acima.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="3e2e5-168">Atribuições > aplicativos ou ações na nuvem: todos os aplicativos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="3e2e5-169">Controles de acesso > conceder > conceder acesso > exigir autenticação multifagássion.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="3e2e5-170">Habilita a política.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-170">Enable the policy.</span></span>
5. <span data-ttu-id="3e2e5-171">Adicione uma conta de usuário ao grupo criado na Etapa 1 acima e teste.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="3e2e5-172">Para exigir MFA para contas de usuário adicionais, adicione-as ao grupo criado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="3e2e5-173">Esta política de Acesso Condicional permite que você íntega o requisito de MFA para seus usuários em seu próprio ritmo.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="3e2e5-174">As empresas devem usar [políticas comuns de Acesso Condicional](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="3e2e5-175">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="3e2e5-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="3e2e5-176">Exigir MFA para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="3e2e5-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="3e2e5-177">Bloquear autenticação herdada</span><span class="sxs-lookup"><span data-stu-id="3e2e5-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="3e2e5-178">Para mais informações, confira esta [visão geral do Acesso Condicional](/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="3e2e5-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="3e2e5-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3e2e5-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="3e2e5-180">Com a Proteção de Identidade do Azure AD, você pode criar uma política de Acesso Condicional adicional para exigir MFA quando o risco de entrada [for médio ou alto.](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="3e2e5-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="3e2e5-181">Você pode usar a Proteção de Identidade do Azure AD e políticas de Acesso Condicional baseadas em risco com:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="3e2e5-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3e2e5-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="3e2e5-183">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="3e2e5-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="3e2e5-184">Para obter mais informações, confira esta [visão geral da Azure Active Directory Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="3e2e5-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="3e2e5-185">MFA herdda por usuário (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="3e2e5-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="3e2e5-186">Você deve estar usando os padrões de segurança ou políticas de Acesso Condicional para exigir MFA para suas inserções de conta de usuário. No entanto, se um desses não puder ser usado, a Microsoft recomenda fortemente o MFA para contas de usuário que tenham funções de administrador, especialmente a função de administrador global, para qualquer assinatura de tamanho.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="3e2e5-187">Você habilita o MFA para contas de usuário individuais no **painel** Usuário Ativo do Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Imagem da opção de autenticação de vários fatores na página Usuários ativos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="3e2e5-189">Depois de habilitado, na próxima vez que o usuário entrar, ele será solicitado a se registrar no MFA e escolher e testar o método de verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="3e2e5-190">Usando esses métodos juntos</span><span class="sxs-lookup"><span data-stu-id="3e2e5-190">Using these methods together</span></span>

<span data-ttu-id="3e2e5-191">Esta tabela mostra os resultados da ativação da MFA com padrões de segurança, políticas de Acesso Condicional e configurações de conta por usuário.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="3e2e5-192">*Item*</span><span class="sxs-lookup"><span data-stu-id="3e2e5-192">*Item*</span></span>|<span data-ttu-id="3e2e5-193">Habilitado</span><span class="sxs-lookup"><span data-stu-id="3e2e5-193">Enabled</span></span>|<span data-ttu-id="3e2e5-194">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="3e2e5-194">Disabled</span></span>|<span data-ttu-id="3e2e5-195">Método de autenticação secundária</span><span class="sxs-lookup"><span data-stu-id="3e2e5-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="3e2e5-196">**Padrões de segurança**</span><span class="sxs-lookup"><span data-stu-id="3e2e5-196">**Security defaults**</span></span>|<span data-ttu-id="3e2e5-197">Não é possível usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="3e2e5-198">Pode usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="3e2e5-199">Aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3e2e5-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="3e2e5-200">**Políticas de Acesso Condicional**</span><span class="sxs-lookup"><span data-stu-id="3e2e5-200">**Conditional Access policies**</span></span>|<span data-ttu-id="3e2e5-201">Se algum estiver habilitado, você não poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3e2e5-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="3e2e5-202">Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3e2e5-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="3e2e5-203">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="3e2e5-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="3e2e5-204">**MFA herdda por usuário (não recomendado)**</span><span class="sxs-lookup"><span data-stu-id="3e2e5-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="3e2e5-205">Substitui os padrões de segurança e as políticas de Acesso Condicional que exigem MFA em cada entrada</span><span class="sxs-lookup"><span data-stu-id="3e2e5-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="3e2e5-206">Substituído por padrões de segurança e políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="3e2e5-207">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="3e2e5-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="3e2e5-208">Se os padrões de segurança estão habilitados, todos os novos usuários são solicitados a solicitar o registro MFA e o uso do aplicativo Microsoft Authenticator em sua próxima login.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="3e2e5-209">Maneiras de gerenciar configurações de MFA</span><span class="sxs-lookup"><span data-stu-id="3e2e5-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="3e2e5-210">Há duas maneiras de gerenciar configurações de MFA.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="3e2e5-211">No portal do Azure, você pode:</span><span class="sxs-lookup"><span data-stu-id="3e2e5-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="3e2e5-212">Habilitar e desabilitar padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3e2e5-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="3e2e5-213">Configurar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3e2e5-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="3e2e5-214">No centro Microsoft 365 de administração, você pode configurar as configurações de MFA por usuário e serviço.</span><span class="sxs-lookup"><span data-stu-id="3e2e5-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3e2e5-215">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3e2e5-215">Next steps</span></span>

[<span data-ttu-id="3e2e5-216">Configurar o MFA para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3e2e5-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="3e2e5-217">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="3e2e5-217">Related content</span></span>

<span data-ttu-id="3e2e5-218">[Ativar a autenticação multifator](../../business-video/turn-on-mfa.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="3e2e5-218">[Turn on multi-factor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="3e2e5-219">[Ativar a autenticação multifator para seu telefone](../../business-video/set-up-mfa.md) (vídeo)</span><span class="sxs-lookup"><span data-stu-id="3e2e5-219">[Turn on multi-factor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>