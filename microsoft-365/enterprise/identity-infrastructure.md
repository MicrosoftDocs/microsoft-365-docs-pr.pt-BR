---
title: 'Fase 2: identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de identidade do Microsoft 365 Enterprise.
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865084"
---
# <a name="phase-2-identity"></a><span data-ttu-id="bbbbf-103">Fase 2: identidade</span><span class="sxs-lookup"><span data-stu-id="bbbbf-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="bbbbf-104">No Microsoft 365 Enterprise, uma infraestrutura de identidade bem planejada e executada fortalece a segurança e o acesso dos dados e cargas de trabalho de produtividade somente por usuários e dispositivos autenticados.</span><span class="sxs-lookup"><span data-stu-id="bbbbf-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="bbbbf-105">Se você já implantou uma infraestrutura de identidade, confira [Critérios de saída de identidade](identity-exit-criteria.md) para garantir que atendam às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bbbbf-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="bbbbf-106">Planejar e implantar sua infraestrutura de identidade do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbbbf-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="bbbbf-p101">Use as etapas a seguir para planejar e implantar uma nova infraestrutura de identidade na nuvem. Também é possível usar estas etapas para adaptar a infraestrutura de identidade híbrida ou local existente para trabalhar com o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bbbbf-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="bbbbf-109">Planejar usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="bbbbf-109">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="bbbbf-110">Proteger contas de administradores globais</span><span class="sxs-lookup"><span data-stu-id="bbbbf-110">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="bbbbf-111">Configurar administradores globais sob demanda</span><span class="sxs-lookup"><span data-stu-id="bbbbf-111">Set up on-demand global administrators</span></span>](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="bbbbf-112">Simplificar redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="bbbbf-112">Simplify password resets</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="bbbbf-113">Configurar autenticações multifatoriais</span><span class="sxs-lookup"><span data-stu-id="bbbbf-113">Set up multi-factor authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="bbbbf-114">Proteger-se do comprometimento de credenciais</span><span class="sxs-lookup"><span data-stu-id="bbbbf-114">Protect against credential compromise</span></span>](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="bbbbf-115">Sincronizar diretórios</span><span class="sxs-lookup"><span data-stu-id="bbbbf-115">Synchronize directories</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [<span data-ttu-id="bbbbf-116">Monitorar integridades de sincronização</span><span class="sxs-lookup"><span data-stu-id="bbbbf-116">Monitor synchronization health</span></span>](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="bbbbf-117">Simplificar atualizações de senha</span><span class="sxs-lookup"><span data-stu-id="bbbbf-117">Simplify password updates</span></span>](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="bbbbf-118">Simplificar entradas de usuário</span><span class="sxs-lookup"><span data-stu-id="bbbbf-118">Simplify user sign-in</span></span>](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [<span data-ttu-id="bbbbf-119">Personalizar páginas de entrada do Office 365</span><span class="sxs-lookup"><span data-stu-id="bbbbf-119">Customize the Office 365 sign-in page</span></span>](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [<span data-ttu-id="bbbbf-120">Configurar licenciamentos automáticos</span><span class="sxs-lookup"><span data-stu-id="bbbbf-120">Set up automatic licensing</span></span>](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="bbbbf-121">Monitorar atividades de entrada e do locatário</span><span class="sxs-lookup"><span data-stu-id="bbbbf-121">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="bbbbf-122">Permitir que usuários criem e gerenciem os próprios grupos</span><span class="sxs-lookup"><span data-stu-id="bbbbf-122">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [<span data-ttu-id="bbbbf-123">Configurar associações de grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="bbbbf-123">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md) |

<span data-ttu-id="bbbbf-124">Após concluir essas etapas, consulte os [critérios de saída](identity-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bbbbf-124">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="bbbbf-125">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="bbbbf-125">Identity and device access prerequisites</span></span>

<span data-ttu-id="bbbbf-p102">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para a identidade, use as configurações e recomendações nos artigos a seguir em conjunto com as etapas nesta fase:</span><span class="sxs-lookup"><span data-stu-id="bbbbf-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="bbbbf-128">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bbbbf-128">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="bbbbf-129">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="bbbbf-129">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="bbbbf-130">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbbbf-130">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bbbbf-131">Saiba como os especialistas de TI da Microsoft planejaram e implantaram os recursos de identidade do Microsoft 365 Enterprise com estes recursos:</span><span class="sxs-lookup"><span data-stu-id="bbbbf-131">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="bbbbf-132">Gerenciamento de identidades de usuários e acesso seguro da Microsoft</span><span class="sxs-lookup"><span data-stu-id="bbbbf-132">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="bbbbf-133">Usar o Azure AD Privileged Identity Management para acesso elevado</span><span class="sxs-lookup"><span data-stu-id="bbbbf-133">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="bbbbf-134">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bbbbf-134">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="bbbbf-135">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou uma infraestrutura de identidade híbrida](contoso-identity.md) dos serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbbbf-135">See how the Contoso Corporation, a fictional but representative multi-national business, [optimized their network](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="bbbbf-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="bbbbf-136">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="bbbbf-137">Planejar usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="bbbbf-137">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
