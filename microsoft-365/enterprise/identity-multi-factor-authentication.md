---
title: 'Etapa 5: Configurar a autenticação multifator'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/05/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a autenticação multifator nas contas de usuário.
ms.openlocfilehash: a54eb047c94430a2b3f61d06500c929e400e3d82
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865163"
---
# <a name="step-5-set-up-multi-factor-authentication"></a><span data-ttu-id="8c749-103">Etapa 5: Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="8c749-103">Step 5: Set up multi-factor authentication</span></span>

<span data-ttu-id="8c749-104">*Esta etapa é opcional e aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="8c749-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="8c749-p101">Nesta etapa, você vai configurar a autenticação multifator (MFA) para adicionar uma segunda camada de segurança nas transações e entradas de usuário. A MFA requer um método de verificação adicional após os usuários inserirem corretamente a sua senha. Sem a MFA, a senha é o único método de verificação. O problema com as senhas é que muitas delas são facilmente decifradas por invasores ou compartilhadas sem intenção com terceiros não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="8c749-p101">In Step 7, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="8c749-109">Com a MFA, a segunda camada de segurança pode ser:</span><span class="sxs-lookup"><span data-stu-id="8c749-109">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="8c749-110">Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.</span><span class="sxs-lookup"><span data-stu-id="8c749-110">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="8c749-111">Um atributo biométrico, como uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="8c749-111">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="8c749-p102">Você vai habilitar a MFA e configurar o método de autenticação secundária em cada conta de usuário. Avise os usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito.</span><span class="sxs-lookup"><span data-stu-id="8c749-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements (such as mandatory use of a smart phone to sign in) and can sign in successfully.</span></span>

<span data-ttu-id="8c749-114">Para saber mais, consulte as informações sobre como [planejar a autenticação multifator para implantações do Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span><span class="sxs-lookup"><span data-stu-id="8c749-114">For more information, see [Plan for multi-factor authentication for Office 365 Deployments](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba).</span></span>

<span data-ttu-id="8c749-115">Para saber mais, consulte o artigo sobre como [configurar a autenticação multifator para usuários do Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span><span class="sxs-lookup"><span data-stu-id="8c749-115">To configure multifactor authentication, [Set up multi-factor authentication for Office 365 users](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6).</span></span>

<span data-ttu-id="8c749-p103">Você pode exigir a MFA com políticas de acesso condicional. Por exemplo, é possível configurar uma política que exige a MFA quando a autenticação for considerada de médio ou alto risco. Para saber mais, confira [Políticas de acesso de dispositivo e identidade comuns](identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span><span class="sxs-lookup"><span data-stu-id="8c749-p103">You can also require MFA with conditional access policies. For example, you can configure a policy that required MFA when the authentication is determined to be of medium or high risk. For more information, see [Step 2: Configure conditional access policy settings](identity-access-policies.md#require-mfa-based-on-sign-in-risk) in the Information Protection phase.</span></span>

>[!Note]
><span data-ttu-id="8c749-p104">Em alguns aplicativos, como o Microsoft Office 2010 ou mais antigos e o Apple Mail, não é possível usar a MFA. Para usar esses aplicativos, é necessário usar "senhas de aplicativo" em vez da sua senha tradicional. A senha de aplicativo permite que o aplicativo ignore a MFA e continue funcionando. Para saber mais sobre as senhas de aplicativo, consulte as informações sobre como [criar uma senha de aplicativo para o Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="8c749-p104">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="8c749-124">Guia do Laboratório de Teste: autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="8c749-124">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="8c749-125">Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="8c749-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8c749-126">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8c749-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="8c749-127">Proteger contra o comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="8c749-127">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |

