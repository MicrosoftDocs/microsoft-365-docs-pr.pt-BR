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
description: Saiba mais sobre a autenticação multifa factor no Microsoft 365.
ms.openlocfilehash: 5e72e3990db533b49041dc4167283b9487f23426
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105180"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="20f9f-103">Autenticação multifator para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f9f-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="20f9f-104">As senhas são o método mais comum de autenticação de uma assinatura em um computador ou serviço online, mas também são as mais vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="20f9f-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="20f9f-105">As pessoas podem escolher senhas fáceis e usar as mesmas senhas para várias logins em computadores e serviços diferentes.</span><span class="sxs-lookup"><span data-stu-id="20f9f-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="20f9f-106">Para fornecer um nível adicional de segurança para as logins, você deve usar a autenticação multifatofa (MFA), que usa uma senha, que deve ser forte, e um método de verificação adicional com base em:</span><span class="sxs-lookup"><span data-stu-id="20f9f-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="20f9f-107">Algo que você tem com você que não é facilmente duplicado, como um smartphone.</span><span class="sxs-lookup"><span data-stu-id="20f9f-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="20f9f-108">Algo que você tem de forma exclusiva e sem problemas, como suas impressões digitais, rosto ou outro atributo biométrico.</span><span class="sxs-lookup"><span data-stu-id="20f9f-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="20f9f-109">O método de verificação adicional não é empregado até que a senha do usuário tenha sido verificada.</span><span class="sxs-lookup"><span data-stu-id="20f9f-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="20f9f-110">Com a MFA, mesmo que uma senha de usuário forte seja comprometida, o invasor não tem seu smartphone ou sua impressão digital para concluir a login.</span><span class="sxs-lookup"><span data-stu-id="20f9f-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="20f9f-111">Suporte à MFA no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f9f-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="20f9f-112">Por padrão, o Microsoft 365 e o Office 365 suportam MFA para contas de usuário usando:</span><span class="sxs-lookup"><span data-stu-id="20f9f-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="20f9f-113">Uma mensagem de texto enviada para um telefone que exige que o usuário digite um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="20f9f-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="20f9f-114">Uma chamada telefônica.</span><span class="sxs-lookup"><span data-stu-id="20f9f-114">A phone call.</span></span>
- <span data-ttu-id="20f9f-115">O aplicativo de telefone inteligente Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="20f9f-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="20f9f-116">Em ambos os casos, o sign-in da MFA está usando o método "algo que você tem com você que não é facilmente duplicado" para a verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="20f9f-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="20f9f-117">Há várias maneiras de habilitar a MFA para o Microsoft 365 e o Office 365:</span><span class="sxs-lookup"><span data-stu-id="20f9f-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="20f9f-118">Com padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="20f9f-118">With security defaults</span></span>
- <span data-ttu-id="20f9f-119">Com políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-119">With Conditional Access policies</span></span>
- <span data-ttu-id="20f9f-120">Para cada conta de usuário individual (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="20f9f-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="20f9f-121">Essas maneiras são baseadas no seu plano do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20f9f-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="20f9f-122">Planejar</span><span class="sxs-lookup"><span data-stu-id="20f9f-122">Plan</span></span>|<span data-ttu-id="20f9f-123">Recomendação</span><span class="sxs-lookup"><span data-stu-id="20f9f-123">Recommendation</span></span>|<span data-ttu-id="20f9f-124">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="20f9f-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="20f9f-125">Todos os planos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f9f-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="20f9f-126">Use padrões de segurança, que exigem MFA para todas as contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="20f9f-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="20f9f-127">Você também pode configurar a MFA por usuário em contas de usuário individuais, mas isso não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="20f9f-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="20f9f-128">Pequena empresa</span><span class="sxs-lookup"><span data-stu-id="20f9f-128">Small business</span></span>|
|<span data-ttu-id="20f9f-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="20f9f-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="20f9f-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="20f9f-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="20f9f-131">Licenças do Azure Active Directory (Azure AD) Premium P1</span><span class="sxs-lookup"><span data-stu-id="20f9f-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="20f9f-132">Use políticas de Acesso Condicional para exigir MFA para contas de usuário com base na associação de grupo, aplicativos ou outros critérios.</span><span class="sxs-lookup"><span data-stu-id="20f9f-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="20f9f-133">Pequenas empresas para empresas</span><span class="sxs-lookup"><span data-stu-id="20f9f-133">Small business to enterprise</span></span>|
|<span data-ttu-id="20f9f-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="20f9f-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="20f9f-135">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="20f9f-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="20f9f-136">Use o Azure AD Identity Protection para exigir a MFA com base nos critérios de risco de login.</span><span class="sxs-lookup"><span data-stu-id="20f9f-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="20f9f-137">Empresa</span><span class="sxs-lookup"><span data-stu-id="20f9f-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="20f9f-138">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="20f9f-138">Security defaults</span></span>

<span data-ttu-id="20f9f-139">Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="20f9f-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="20f9f-140">Essas assinaturas têm os padrões de segurança ligado, que:</span><span class="sxs-lookup"><span data-stu-id="20f9f-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="20f9f-141">Exige que todos os seus usuários usem a MFA com o aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="20f9f-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="20f9f-142">Bloqueia a autenticação herdda.</span><span class="sxs-lookup"><span data-stu-id="20f9f-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="20f9f-143">Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados.</span><span class="sxs-lookup"><span data-stu-id="20f9f-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="20f9f-144">Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.</span><span class="sxs-lookup"><span data-stu-id="20f9f-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="20f9f-145">Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="20f9f-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="20f9f-146">Você pode desabilitar os padrões de segurança em favor da MFA com políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="20f9f-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="20f9f-147">Você habilita ou desabilita os padrões de segurança no painel Propriedades do Azure AD no portal do Azure. </span><span class="sxs-lookup"><span data-stu-id="20f9f-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![Imagem da página de propriedades do diretório.](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="20f9f-149">Você pode usar padrões de segurança com qualquer plano do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20f9f-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="20f9f-150">Para obter mais informações, confira esta [visão geral dos padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="20f9f-150">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="20f9f-151">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-151">Conditional Access policies</span></span>

<span data-ttu-id="20f9f-152">As políticas de acesso condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e permitidas.</span><span class="sxs-lookup"><span data-stu-id="20f9f-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="20f9f-153">Por exemplo, você pode criar uma política de acesso condicional que declare:</span><span class="sxs-lookup"><span data-stu-id="20f9f-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="20f9f-154">Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.</span><span class="sxs-lookup"><span data-stu-id="20f9f-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="20f9f-155">Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="20f9f-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="20f9f-156">Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir MFA para aplicativos específicos ou que a entrada seja feita em um dispositivo compatível, como seu laptop executando o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="20f9f-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="20f9f-157">Você configura políticas de Acesso Condicional **no** painel Segurança do Azure AD no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="20f9f-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![Imagem da opção de menu para Acesso Condicional](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="20f9f-159">Você pode usar políticas de Acesso Condicional com:</span><span class="sxs-lookup"><span data-stu-id="20f9f-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="20f9f-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="20f9f-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="20f9f-161">Microsoft 365 E3 e E5</span><span class="sxs-lookup"><span data-stu-id="20f9f-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="20f9f-162">Licenças do Azure AD Premium P1 e do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="20f9f-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="20f9f-163">Para pequenas empresas com o Microsoft 365 Business Premium, você pode facilmente usar políticas de Acesso Condicional com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="20f9f-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="20f9f-164">Crie um grupo para conter as contas de usuário que exigem MFA.</span><span class="sxs-lookup"><span data-stu-id="20f9f-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="20f9f-165">Habilita **a política Exigir MFA para administradores** globais.</span><span class="sxs-lookup"><span data-stu-id="20f9f-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="20f9f-166">Crie uma política de Acesso Condicional baseada em grupo com estas configurações:</span><span class="sxs-lookup"><span data-stu-id="20f9f-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="20f9f-167">Atribuições > Usuários e grupos: o nome do seu grupo da Etapa 1 acima.</span><span class="sxs-lookup"><span data-stu-id="20f9f-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="20f9f-168">Atribuições > ações ou aplicativos de nuvem: todos os aplicativos em nuvem.</span><span class="sxs-lookup"><span data-stu-id="20f9f-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="20f9f-169">Os controles > Conceder > Conceder acesso > Exigir autenticação multifafa.</span><span class="sxs-lookup"><span data-stu-id="20f9f-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="20f9f-170">Habilita a política.</span><span class="sxs-lookup"><span data-stu-id="20f9f-170">Enable the policy.</span></span>
5. <span data-ttu-id="20f9f-171">Adicione uma conta de usuário ao grupo criado na Etapa 1 acima e teste.</span><span class="sxs-lookup"><span data-stu-id="20f9f-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="20f9f-172">Para exigir MFA para contas de usuário adicionais, adicione-as ao grupo criado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="20f9f-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="20f9f-173">Essa política de Acesso Condicional permite que você roll out the MFA requirement to your users at your own pace.</span><span class="sxs-lookup"><span data-stu-id="20f9f-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="20f9f-174">As empresas devem usar [políticas comuns de Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="20f9f-174">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="20f9f-175">Exigir MFA para administradores</span><span class="sxs-lookup"><span data-stu-id="20f9f-175">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="20f9f-176">Exigir MFA para todos os usuários</span><span class="sxs-lookup"><span data-stu-id="20f9f-176">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="20f9f-177">Bloquear autenticação herdda</span><span class="sxs-lookup"><span data-stu-id="20f9f-177">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="20f9f-178">Para mais informações, confira esta [visão geral do Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="20f9f-178">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="20f9f-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="20f9f-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="20f9f-180">Com o Azure AD Identity Protection, você pode criar uma política de Acesso Condicional adicional para exigir a MFA quando o risco de entrada for [médio ou alto.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="20f9f-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="20f9f-181">Você pode usar o Azure AD Identity Protection e políticas de Acesso Condicional baseadas em risco com:</span><span class="sxs-lookup"><span data-stu-id="20f9f-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="20f9f-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="20f9f-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="20f9f-183">Licenças do Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="20f9f-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="20f9f-184">Para obter mais informações, confira esta [visão geral da Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="20f9f-184">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="20f9f-185">MFA herdda por usuário (não recomendada)</span><span class="sxs-lookup"><span data-stu-id="20f9f-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="20f9f-186">Você deve usar padrões de segurança ou políticas de Acesso Condicional para exigir MFA para as inserções da conta de usuário. No entanto, se um deles não puder ser usado, a Microsoft recomenda a MFA para contas de usuário que tenham funções de administrador, especialmente a função de administrador global, para qualquer tamanho de assinatura.</span><span class="sxs-lookup"><span data-stu-id="20f9f-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="20f9f-187">Você habilita a MFA para contas de usuário individuais no **painel** Usuário Ativo do Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="20f9f-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![Imagem da opção de autenticação multifaionável na página Usuários ativos](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="20f9f-189">Depois de habilitado, na próxima vez que o usuário entrar, ele será solicitado a se registrar na MFA e escolher e testar o método de verificação adicional.</span><span class="sxs-lookup"><span data-stu-id="20f9f-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="20f9f-190">Usando esses métodos juntos</span><span class="sxs-lookup"><span data-stu-id="20f9f-190">Using these methods together</span></span>

<span data-ttu-id="20f9f-191">Esta tabela mostra os resultados da ativação da MFA com padrões de segurança, políticas de Acesso Condicional e configurações de conta por usuário.</span><span class="sxs-lookup"><span data-stu-id="20f9f-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

||<span data-ttu-id="20f9f-192">Habilitado</span><span class="sxs-lookup"><span data-stu-id="20f9f-192">Enabled</span></span>|<span data-ttu-id="20f9f-193">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="20f9f-193">Disabled</span></span>|<span data-ttu-id="20f9f-194">Método de autenticação secundária</span><span class="sxs-lookup"><span data-stu-id="20f9f-194">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="20f9f-195">**Padrões de segurança**</span><span class="sxs-lookup"><span data-stu-id="20f9f-195">**Security defaults**</span></span>|<span data-ttu-id="20f9f-196">Não é possível usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-196">Can't use Conditional Access policies</span></span>|<span data-ttu-id="20f9f-197">Pode usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-197">Can use Conditional Access policies</span></span>|<span data-ttu-id="20f9f-198">Aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="20f9f-198">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="20f9f-199">**Políticas de Acesso Condicional**</span><span class="sxs-lookup"><span data-stu-id="20f9f-199">**Conditional Access policies**</span></span>|<span data-ttu-id="20f9f-200">Se algum estiver habilitado, você não poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="20f9f-200">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="20f9f-201">Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="20f9f-201">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="20f9f-202">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="20f9f-202">User-specified during MFA registration</span></span>|
|<span data-ttu-id="20f9f-203">**MFA herdda por usuário (não recomendada)**</span><span class="sxs-lookup"><span data-stu-id="20f9f-203">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="20f9f-204">Substitui os padrões de segurança e as políticas de Acesso Condicional que exigem MFA em cada entrada</span><span class="sxs-lookup"><span data-stu-id="20f9f-204">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="20f9f-205">Substituído por padrões de segurança e políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-205">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="20f9f-206">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="20f9f-206">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="20f9f-207">Se os padrões de segurança estão habilitados, todos os novos usuários são solicitados a solicitar o registro da MFA e o uso do aplicativo Microsoft Authenticator na próxima inscrição.</span><span class="sxs-lookup"><span data-stu-id="20f9f-207">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="20f9f-208">Maneiras de gerenciar configurações de MFA</span><span class="sxs-lookup"><span data-stu-id="20f9f-208">Ways to manage MFA settings</span></span>

<span data-ttu-id="20f9f-209">Há duas maneiras de gerenciar as configurações de MFA.</span><span class="sxs-lookup"><span data-stu-id="20f9f-209">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="20f9f-210">No portal do Azure, você pode:</span><span class="sxs-lookup"><span data-stu-id="20f9f-210">In the Azure portal, you can:</span></span>

- <span data-ttu-id="20f9f-211">Habilitar e desabilitar padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="20f9f-211">Enable and disable security defaults</span></span>
- <span data-ttu-id="20f9f-212">Configurar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="20f9f-212">Configure Conditional Access policies</span></span>

<span data-ttu-id="20f9f-213">No Centro de administração do Microsoft 365, você pode definir as configurações de MFA por usuário e serviço.</span><span class="sxs-lookup"><span data-stu-id="20f9f-213">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="20f9f-214">Sua próxima etapa</span><span class="sxs-lookup"><span data-stu-id="20f9f-214">Your next step</span></span>

[<span data-ttu-id="20f9f-215">Configurar a MFA para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="20f9f-215">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-topics"></a><span data-ttu-id="20f9f-216">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="20f9f-216">Related topics</span></span>

[<span data-ttu-id="20f9f-217">Vídeo: Ativar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="20f9f-217">Video: Turn on multi-factor authentication</span></span>](https://docs.microsoft.com/microsoft-365/business-video/turn-on-mfa)

[<span data-ttu-id="20f9f-218">Vídeo: Ativar a autenticação multifator para seu telefone</span><span class="sxs-lookup"><span data-stu-id="20f9f-218">Video: Turn on multi-factor authentication for your phone</span></span>](https://docs.microsoft.com/microsoft-365/business-video/set-up-mfa)
