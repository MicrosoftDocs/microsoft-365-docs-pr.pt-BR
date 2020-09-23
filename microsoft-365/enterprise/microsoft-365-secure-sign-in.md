---
title: Proteger as entradas do usuário ao locatário do seu Microsoft 365
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Exija que seus usuários se conectem com segurança usando a autenticação multifator (MFA) e outros recursos.
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132233"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="3f9f6-103">Proteger as entradas do usuário ao locatário do seu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f9f6-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="3f9f6-104">Para aumentar a segurança das entradas do usuário:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="3f9f6-105">Use a Proteção por Senha do Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-105">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="3f9f6-106">Use a autenticação multifator (MFA)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-106">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="3f9f6-107">Implante políticas de identidade e acesso a dispositivos</span><span class="sxs-lookup"><span data-stu-id="3f9f6-107">Deploy identity and device access policies</span></span>

## <a name="azure-ad-password-protection"></a><span data-ttu-id="3f9f6-108">Proteção por Senha do Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f9f6-108">Azure AD Password Protection</span></span>

<span data-ttu-id="3f9f6-109">A Proteção por Senha do Microsoft Azure AD detecta e bloqueia senhas fracas conhecidas e suas variantes e também pode bloquear termos fracos adicionais específicos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-109">Azure AD Password Protection detects and blocks known weak passwords and their variants, and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="3f9f6-110">Listas de senhas globais proibidas padrão são aplicadas automaticamente a todos os usuários em um locatário do Microsoft Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-110">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="3f9f6-111">Você pode definir entradas adicionais em uma lista de senhas proibidas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-111">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="3f9f6-112">Quando os usuários alteram ou redefinem suas senhas, essas listas de senhas proibidas são verificadas para garantir o uso de senhas fortes.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-112">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="3f9f6-113">Para obter mais informações, confira [Configurar a proteção por senha do Microsoft Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span><span class="sxs-lookup"><span data-stu-id="3f9f6-113">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="3f9f6-114">MFA</span><span class="sxs-lookup"><span data-stu-id="3f9f6-114">MFA</span></span>

<span data-ttu-id="3f9f6-115">A MFA exige que as entradas do usuário estejam sujeitas a uma verificação adicional, além da senha da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-115">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="3f9f6-116">Mesmo que um usuário mal-intencionado determine uma senha de conta de usuário, ele também deverá responder a uma verificação adicional, como uma mensagem de texto enviada a um smartphone antes do acesso ser concedido.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-116">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![A senha correta, mais uma verificação adicional, resulta em uma entrada bem-sucedida](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="3f9f6-118">A primeira etapa para usar a MFA é ***exigi-lo para todas as contas de administrador***, também conhecidas como contas privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-118">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="3f9f6-119">Além dessa primeira etapa, a Microsoft recomenda a MFA para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-119">Beyond this first step, Microsoft strongly recommends MFA For all users.</span></span>

<span data-ttu-id="3f9f6-120">Há três maneiras de exigir que seus administradores ou usuários usem a MFA com base no seu plano do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-120">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="3f9f6-121">Planejar</span><span class="sxs-lookup"><span data-stu-id="3f9f6-121">Plan</span></span> | <span data-ttu-id="3f9f6-122">Recomendação</span><span class="sxs-lookup"><span data-stu-id="3f9f6-122">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="3f9f6-123">Planos do Microsoft 365 (sem licenças do Microsoft Azure AD Premium P1 ou P2)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-123">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="3f9f6-124">[Habilitar os padrões de segurança no Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="3f9f6-124">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="3f9f6-125">Os padrões de segurança no Microsoft Azure Active Directory incluem a MFA para usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-125">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="3f9f6-126">Microsoft 365 E3 (inclui licenças do Azure AD Premium P1)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-126">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="3f9f6-127">Use [políticas de Acesso Condicional Comuns](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-127">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="3f9f6-128">- [Exigir MFA para administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-128">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="3f9f6-129">- [Exigir MFA para todos os usuários](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-129">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="3f9f6-130">- [Bloquear autenticação herdada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-130">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="3f9f6-131">Microsoft 365 E5 (inclui licenças do Azure AD Premium P2)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-131">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="3f9f6-132">Aproveitando a Azure Active Directory Identity Protection, comece a implementar o [conjunto recomendado de acesso condicional e políticas relacionadas](../enterprise/identity-access-policies.md) da Microsoft, criando estas duas políticas:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-132">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="3f9f6-133">- [Exigir MFA quando o risco de entrada for médio ou alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-133">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="3f9f6-134">- [Usuários de alto risco devem alterar a senha](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-134">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="3f9f6-135">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3f9f6-135">Security defaults</span></span>

<span data-ttu-id="3f9f6-136">Os padrões de segurança são um novo recurso para assinaturas pagas ou de avaliação do Microsoft 365 e Office 365 criadas após 21 de outubro de 2019.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-136">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="3f9f6-137">Essas assinaturas têm padrões de segurança ativados, o que ***exige que todos os seus usuários usem a MFA com o aplicativo Microsoft Authenticator***.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-137">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="3f9f6-138">Os usuários têm 14 dias para se registrar na MFA com o aplicativo Microsoft Authenticator em seus smartphones, que começa na primeira vez em que eles entram depois de os padrões de segurança terem sido habilitados.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-138">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="3f9f6-139">Após 14 dias, o usuário não poderá entrar até que o registro da MFA seja concluído.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-139">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="3f9f6-140">Os padrões de segurança garantem que todas as organizações tenham um nível básico de segurança para a entrada do usuário, que é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-140">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="3f9f6-141">Você pode desativar os padrões de segurança em favor da MFA com políticas de Acesso Condicional ou para contas individuais.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-141">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="3f9f6-142">Para obter mais informações, confira esta [visão geral dos padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span><span class="sxs-lookup"><span data-stu-id="3f9f6-142">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="3f9f6-143">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3f9f6-143">Conditional Access policies</span></span>

<span data-ttu-id="3f9f6-144">As políticas de Acesso Condicional são um conjunto de regras que especificam as condições sob as quais as entradas são avaliadas e o acesso é concedido.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-144">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="3f9f6-145">Por exemplo, você pode criar uma política de acesso condicional que declare:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-145">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="3f9f6-146">Se o nome da conta de usuário for membro de um grupo para usuários a quem são atribuídas as funções de administrador do Exchange, de usuário, de senha, de segurança, do SharePoint ou global, exija a MFA antes de permitir o acesso.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-146">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="3f9f6-147">Essa política permite exigir a MFA com base na associação ao grupo, em vez de tentar configurar contas de usuário individuais para a MFA quando elas são atribuídas ou não a essas funções de administrador.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-147">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="3f9f6-148">Você também pode usar políticas de Acesso Condicional para recursos mais avançados, como exigir que a entrada seja feita a partir de um dispositivo compatível, como o seu laptop executando o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-148">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="3f9f6-149">O Acesso Condicional requer as licenças do Microsoft Azure AD Premium P1, incluídas no Microsoft 365 E3 e E5.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-149">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="3f9f6-150">Para mais informações, confira esta [visão geral do Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="3f9f6-150">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="3f9f6-151">Usando esses métodos juntos</span><span class="sxs-lookup"><span data-stu-id="3f9f6-151">Using these methods together</span></span>

<span data-ttu-id="3f9f6-152">Lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-152">Keep the following in mind:</span></span>

- <span data-ttu-id="3f9f6-153">Você não pode habilitar os padrões de segurança se tiver alguma política de Acesso Condicional ativada.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-153">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="3f9f6-154">Você não pode habilitar nenhuma política de Acesso Condicional se tiver os padrões de segurança habilitados.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-154">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="3f9f6-155">Se os padrões de segurança estiverem ativados, todos os novos usuários serão solicitados a fazer o registro da MFA e usar o aplicativo Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-155">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="3f9f6-156">Esta tabela mostra os resultados da habilitação da MFA com padrões de segurança e políticas de Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-156">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="3f9f6-157">Método</span><span class="sxs-lookup"><span data-stu-id="3f9f6-157">Method</span></span> | <span data-ttu-id="3f9f6-158">Habilitado</span><span class="sxs-lookup"><span data-stu-id="3f9f6-158">Enabled</span></span> | <span data-ttu-id="3f9f6-159">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="3f9f6-159">Disabled</span></span> | <span data-ttu-id="3f9f6-160">Método de autenticação adicional</span><span class="sxs-lookup"><span data-stu-id="3f9f6-160">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="3f9f6-161">**Padrões de segurança**</span><span class="sxs-lookup"><span data-stu-id="3f9f6-161">**Security defaults**</span></span>  | <span data-ttu-id="3f9f6-162">Não é possível usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3f9f6-162">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="3f9f6-163">Pode usar políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3f9f6-163">Can use Conditional Access policies</span></span> | <span data-ttu-id="3f9f6-164">Aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="3f9f6-164">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="3f9f6-165">**Políticas de Acesso Condicional**</span><span class="sxs-lookup"><span data-stu-id="3f9f6-165">**Conditional Access policies**</span></span> | <span data-ttu-id="3f9f6-166">Se alguma delas estiver habilitada, você não poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3f9f6-166">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="3f9f6-167">Se todas estiverem desabilitadas, você poderá habilitar os padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3f9f6-167">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="3f9f6-168">Especificado pelo usuário durante o registro da MFA</span><span class="sxs-lookup"><span data-stu-id="3f9f6-168">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-policies"></a><span data-ttu-id="3f9f6-169">Políticas de identidade e acesso a dispositivos</span><span class="sxs-lookup"><span data-stu-id="3f9f6-169">Identity and device access policies</span></span>

<span data-ttu-id="3f9f6-170">As configurações e políticas de identidade e acesso a dispositivos são recursos de pré-requisito recomendados e suas configurações combinadas com as políticas de Acesso Condicional, Intune e Azure AD Identity Protection que determinam se uma determinada solicitação de acesso deve ser concedida e sob quais condições.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-170">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="3f9f6-171">Essa determinação é baseada na conta do usuário da entrada, no dispositivo que está sendo usado, no aplicativo que o usuário está usando para acessar, no local a partir do qual a solicitação de acesso é feita e em uma avaliação do risco da solicitação.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-171">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="3f9f6-172">Esse recurso ajuda a garantir que apenas usuários e dispositivos aprovados possam acessar os recursos críticos.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-172">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="3f9f6-173">A Azure AD Identity Protection exige as licenças do Microsoft Azure AD Premium P2, incluídas no Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-173">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="3f9f6-174">As políticas de identidade e acesso a dispositivos são definidas para serem usadas em três camadas:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-174">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="3f9f6-175">A proteção de linha de base é um nível mínimo de segurança para suas identidades e dispositivos que acessam seus aplicativos e dados.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-175">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="3f9f6-176">A proteção confidencial fornece segurança adicional para dados específicos.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-176">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="3f9f6-177">Identidades e dispositivos estão sujeitos a níveis mais altos de requisitos de segurança e integridade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-177">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="3f9f6-178">A proteção para ambientes com dados altamente regulamentados ou confidenciais é geralmente destinada para pequenas quantidades de dados extremamente confidenciais, contêm segredos comerciais ou estão sujeitos a regulamentações de dados.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-178">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="3f9f6-179">Identidades e dispositivos estão sujeitos a níveis muito mais altos de requisitos de segurança e integridade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-179">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="3f9f6-180">Essas camadas e suas configurações correspondentes fornecem níveis consistentes de proteção em seus dados, identidades e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-180">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="3f9f6-181">A Microsoft recomenda a configuração e distribuição de políticas de identidade de acesso a dispositivos em sua organização, incluindo configurações específicas para o Microsoft Teams, Exchange Online e SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-181">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="3f9f6-182">Para obter mais informações, confira [Configurações de identidade e acesso a dispositivos](microsoft-365-policies-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="3f9f6-182">For more information, see [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="3f9f6-183">Recursos técnicos de administração para MFA e entradas seguras</span><span class="sxs-lookup"><span data-stu-id="3f9f6-183">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="3f9f6-184">MFA do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f9f6-184">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="3f9f6-185">Roteiro da identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3f9f6-185">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="3f9f6-186">Vídeos de treinamento do Microsoft Azure Active Directory da Azure Academy</span><span class="sxs-lookup"><span data-stu-id="3f9f6-186">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="3f9f6-187">Configurar a política de registro da Autenticação Multifator do Azure</span><span class="sxs-lookup"><span data-stu-id="3f9f6-187">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="3f9f6-188">Configurações de identidade e acesso a dispositivos</span><span class="sxs-lookup"><span data-stu-id="3f9f6-188">Identity and device access configurations</span></span>](microsoft-365-policies-configurations.md)

