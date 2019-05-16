---
title: 'Etapa 4: Configurar autenticação de usuário segura'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/17/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a autenticação multifator nas contas de usuário.
ms.openlocfilehash: 73e884802329765fd6a89cfb7d0e04116c17968c
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072081"
---
# <a name="step-4-configure-secure-user-authentication"></a><span data-ttu-id="c94f0-103">Etapa 4: Configurar autenticação de usuário segura</span><span class="sxs-lookup"><span data-stu-id="c94f0-103">Step 4: Configure secure user authentication</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-mfa"></a>
## <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="c94f0-104">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="c94f0-104">Set up multi-factor authentication</span></span>

<span data-ttu-id="c94f0-105">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c94f0-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c94f0-p101">Nesta etapa, você vai configurar a autenticação multifator (MFA) para adicionar uma segunda camada de segurança nas transações e entradas de usuário. A MFA requer um método de verificação adicional após os usuários inserirem corretamente a sua senha. Sem a MFA, a senha é o único método de verificação. O problema com as senhas é que muitas delas são facilmente decifradas por invasores ou compartilhadas sem intenção com terceiros não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p101">In this step, you'll set up multi-factor authentication (MFA) to add a second layer of security to user sign-ins and transactions. MFA requires an additional verification method after users have correctly entered their password. Without MFA, the password is the only verification method. The problem with passwords is that many of them are easily guessed by an attacker or unknowingly shared with untrusted parties.</span></span>

<span data-ttu-id="c94f0-110">Com a MFA, a segunda camada de segurança pode ser:</span><span class="sxs-lookup"><span data-stu-id="c94f0-110">With MFA, the second layer of security can be:</span></span>

- <span data-ttu-id="c94f0-111">Um dispositivo pessoal de confiança que não seja facilmente forjado ou duplicado, como um smartphone.</span><span class="sxs-lookup"><span data-stu-id="c94f0-111">A personal and trusted device that isn’t easily spoofed or duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="c94f0-112">Um atributo biométrico, como uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="c94f0-112">A biometric attribute, such as a fingerprint.</span></span>

<span data-ttu-id="c94f0-p102">Você vai habilitar a MFA e configurar o método de autenticação secundária em cada conta de usuário. Avise os usuários que a MFA será ativada para que eles compreendam os requisitos, como o uso obrigatório de um Smartphone para acesso, e possam entrar na rede com êxito.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p102">You'll enable MFA and configure the secondary authentication method on a per-user account basis. Make sure to let users know that MFA is being enabled so they understand the requirements, such as mandatory use of a smart phone to sign in, and can sign in successfully.</span></span>

<span data-ttu-id="c94f0-115">Para saber mais, confira [Planejar autenticações multifatoriais](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span><span class="sxs-lookup"><span data-stu-id="c94f0-115">For more information, see [Plan for multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted).</span></span>

>[!Note]
><span data-ttu-id="c94f0-p103">Em alguns aplicativos, como o Microsoft Office 2010 ou mais antigos e o Apple Mail, não é possível usar a MFA. Para usar esses aplicativos, é necessário usar "senhas de aplicativo" em vez da sua senha tradicional. A senha de aplicativo permite que o aplicativo ignore a MFA e continue funcionando. Para saber mais sobre as senhas de aplicativo, consulte as informações sobre como [criar uma senha de aplicativo para o Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span><span class="sxs-lookup"><span data-stu-id="c94f0-p103">In some applications, such as Microsoft Office 2010 or older and Apple Mail, you can’t use MFA. To use these apps, you’ll need to use “app passwords” in place of your traditional password. The app password allows the app to bypass MFA and continue working. To learn more about app passwords, see [Create an app password for Office 365](https://support.office.com/article/Create-an-app-password-for-Office-365-3e7c860f-bda4-4441-a618-b53953ee1183).</span></span>
>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c94f0-121">Guia do Laboratório de Teste: autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="c94f0-121">Test Lab Guide: Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="c94f0-122">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-mfa) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="c94f0-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-mfa) for this section.</span></span>



<a name="identity-ident-prot"></a>
## <a name="protect-against-credential-compromise"></a><span data-ttu-id="c94f0-123">Proteger-se contra o comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="c94f0-123">Protect against credential compromise</span></span>

<span data-ttu-id="c94f0-124">*Isso é opcional e se aplica somente às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c94f0-124">*This is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c94f0-125">Nesta seção, você aprenderá a configurar políticas de proteção contra o comprometimento de credenciais, onde um invasor determina o nome e senha da conta de um usuário para obter acesso aos serviços de nuvem e dados de uma organização.</span><span class="sxs-lookup"><span data-stu-id="c94f0-125">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="c94f0-126">O Azure AD Identity Protection fornece várias maneiras de ajudar a evitar que um invasor se mova lateralmente por suas contas e grupos e posteriormente, até seus dados mais valiosos.</span><span class="sxs-lookup"><span data-stu-id="c94f0-126">Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="c94f0-127">Com a Azure AD Identity Protection, você pode:</span><span class="sxs-lookup"><span data-stu-id="c94f0-127">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="c94f0-128">Determinar e administrar possíveis vulnerabilidades nas identidades da organização</span><span class="sxs-lookup"><span data-stu-id="c94f0-128">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="c94f0-p105">O Azure AD utiliza o aprendizado de máquina para detectar anomalias e atividades suspeitas, como atividades de entrada e pós-entrada. Usando esses dados, a Proteção de Identidade gera relatórios e alertas que lhe ajudarão a avaliar os problemas e a tomar as medidas necessárias.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p105">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="c94f0-131">Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente</span><span class="sxs-lookup"><span data-stu-id="c94f0-131">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="c94f0-p106">Você pode configurar as políticas baseadas em risco que são acionadas automaticamente para detectar problemas quando um nível de risco específico é atingido. Essas políticas, além de outros controles de acesso condicional fornecidos pelo Azure Active Directory e pelo Enterprise Mobility + Security EMS (), podem bloquear automaticamente o acesso ou realizar ações corretivas, incluindo a redefinição de senha e exigindo a autenticação multifator para entradas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p106">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="c94f0-134">Investigar incidentes suspeitos e resolvê-los com medidas administrativas</span><span class="sxs-lookup"><span data-stu-id="c94f0-134">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="c94f0-p107">Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p107">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="c94f0-137">Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="c94f0-137">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="c94f0-138">Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="c94f0-138">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="c94f0-139">Os resultados desta etapa incluem a habilitação da Azure AD Identity Protection e o uso dessa para:</span><span class="sxs-lookup"><span data-stu-id="c94f0-139">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="c94f0-140">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="c94f0-140">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="c94f0-141">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="c94f0-141">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="c94f0-142">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="c94f0-142">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c94f0-144">Guia do Laboratório de Teste: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="c94f0-144">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="c94f0-145">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="c94f0-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this section.</span></span>

## <a name="monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="c94f0-146">Monitorar a atividade de entrada e do locatário</span><span class="sxs-lookup"><span data-stu-id="c94f0-146">Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="c94f0-147">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="c94f0-147">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="c94f0-p108">Nesta etapa, você vai revisar os logs de auditoria e a atividade de entrada usando os relatórios do Azure AD. Estão disponíveis dois tipos de relatório.</span><span class="sxs-lookup"><span data-stu-id="c94f0-p108">In this step, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="c94f0-p109">O **relatório de atividade de logs de auditoria** registra o histórico de todas as tarefas realizadas em seu locatário do Azure AD. Esse relatório responde a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="c94f0-p109">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="c94f0-152">Quem adicionou uma pessoa a um grupo de administração?</span><span class="sxs-lookup"><span data-stu-id="c94f0-152">Who added someone to an admin group?</span></span>
- <span data-ttu-id="c94f0-153">Que usuários estão se conectando em um aplicativo específico?</span><span class="sxs-lookup"><span data-stu-id="c94f0-153">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="c94f0-154">Quantas redefinições de senhas estão ocorrendo?</span><span class="sxs-lookup"><span data-stu-id="c94f0-154">How many password resets are happening?</span></span>

<span data-ttu-id="c94f0-p110">O **relatório de atividade de entradas** registra quem executou as tarefas relatadas pelo relatório de logs de auditoria. Esse relatório responde a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="c94f0-p110">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="c94f0-157">Qual é o padrão de entrada de um usuário específico que está sob investigação?</span><span class="sxs-lookup"><span data-stu-id="c94f0-157">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="c94f0-158">Qual é o volume de entradas em um dia, uma semana ou um mês?</span><span class="sxs-lookup"><span data-stu-id="c94f0-158">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="c94f0-159">Quantas dessas tentativas de entrada não foram bem-sucedidas, e em que contas ocorreram?</span><span class="sxs-lookup"><span data-stu-id="c94f0-159">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="c94f0-160">Para saber mais sobre os relatórios e como acessá-los, consulte as informações sobre os [relatórios do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="c94f0-160">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="c94f0-161">Como resultado desta etapa, você ficará ciente desses relatórios e saberá como usá-los para obter informações de atividades e eventos ocorridos no Azure AD para poder planejar a segurança.</span><span class="sxs-lookup"><span data-stu-id="c94f0-161">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>



## <a name="next-step"></a><span data-ttu-id="c94f0-162">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c94f0-162">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="c94f0-163">Simplificar o acesso para usuários</span><span class="sxs-lookup"><span data-stu-id="c94f0-163">Simplify access for users</span></span>](identity-password-reset.md) |

