---
title: 'Etapa 6: Proteger contra o comprometimento de credenciais'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar a Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865323"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="4ab8e-103">Etapa 6: Proteger contra o comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="4ab8e-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="4ab8e-104">*Esta etapa é opcional e aplica-se apenas à versão E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="4ab8e-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="4ab8e-p101">Nesta etapa, você vai aprender a configurar as políticas de proteção contra o comprometimento de credenciais, que ocorre quando um invasor determina o nome de conta do usuário e a senha para ter acesso aos serviços de nuvem e dados da organização. A Azure AD Identity Protection fornece várias maneiras de ajudar a impedir que um invasor percorra todas as suas contas e grupos e posteriormente acesse seus dados mais importantes.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="4ab8e-107">Com a Azure AD Identity Protection, você pode:</span><span class="sxs-lookup"><span data-stu-id="4ab8e-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="4ab8e-108">Determinar e administrar possíveis vulnerabilidades nas identidades da organização</span><span class="sxs-lookup"><span data-stu-id="4ab8e-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="4ab8e-p102">O Azure AD utiliza o aprendizado de máquina para detectar anomalias e atividades suspeitas, como atividades de entrada e pós-entrada. Usando esses dados, a Proteção de Identidade gera relatórios e alertas que lhe ajudarão a avaliar os problemas e a tomar as medidas necessárias.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="4ab8e-111">Detectar ações suspeitas relacionadas às identidades da organização e responder a essas suspeitas automaticamente</span><span class="sxs-lookup"><span data-stu-id="4ab8e-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="4ab8e-p103">Você pode configurar as políticas baseadas em risco que são acionadas automaticamente para detectar problemas quando um nível de risco específico é atingido. Essas políticas, além de outros controles de acesso condicional fornecidos pelo Azure Active Directory e pelo Enterprise Mobility + Security EMS (), podem bloquear automaticamente o acesso ou realizar ações corretivas, incluindo a redefinição de senha e exigindo a autenticação multifator para entradas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="4ab8e-114">Investigar incidentes suspeitos e resolvê-los com medidas administrativas</span><span class="sxs-lookup"><span data-stu-id="4ab8e-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="4ab8e-p104">Você pode investigar eventos de risco usando informações sobre o incidente de segurança. Fluxos básicos de trabalho estão disponíveis para controlar investigações e iniciar ações de correção, como a redefinição de senhas.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="4ab8e-117">Consulte mais [informações sobre a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span><span class="sxs-lookup"><span data-stu-id="4ab8e-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="4ab8e-118">Consulte as [etapas para habilitar a Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span><span class="sxs-lookup"><span data-stu-id="4ab8e-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="4ab8e-119">Os resultados desta etapa incluem a habilitação da Azure AD Identity Protection e o uso dessa para:</span><span class="sxs-lookup"><span data-stu-id="4ab8e-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="4ab8e-120">Solucionar possíveis vulnerabilidades de identidade.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="4ab8e-121">Detectar possíveis tentativas de ataque à credencial.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="4ab8e-122">Investigar e resolver incidentes suspeitos e contínuos relacionados a questões de identidade.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="4ab8e-124">Guia do Laboratório de Teste: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="4ab8e-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="4ab8e-125">Como ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-ident-prot) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="4ab8e-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="4ab8e-126">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="4ab8e-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="4ab8e-127">Sincronizar diretórios</span><span class="sxs-lookup"><span data-stu-id="4ab8e-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


