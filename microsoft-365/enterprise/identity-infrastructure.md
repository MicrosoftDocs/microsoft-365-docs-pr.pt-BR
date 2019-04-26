---
title: 'Fase 2: identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura de identidade do Microsoft 365 Enterprise.
ms.openlocfilehash: 932b6fb2cfeb86edcf708bdfdea55cdd8b580838
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288727"
---
# <a name="phase-2-identity"></a><span data-ttu-id="f73bc-103">Fase 2: identidade</span><span class="sxs-lookup"><span data-stu-id="f73bc-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="f73bc-104">No Microsoft 365 Enterprise, uma infraestrutura de identidade bem planejada e executada fortalece a segurança e o acesso dos dados e cargas de trabalho de produtividade somente por usuários e dispositivos autenticados.</span><span class="sxs-lookup"><span data-stu-id="f73bc-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

>[!Note]
><span data-ttu-id="f73bc-105">Se você já implantou uma infraestrutura de identidade, confira [Critérios de saída de identidade](identity-exit-criteria.md) para garantir que atendam às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f73bc-105">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="f73bc-106">Planejar e implantar sua infraestrutura de identidade do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f73bc-106">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="f73bc-107">Antes de começar, assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f73bc-107">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

<span data-ttu-id="f73bc-p101">Use as etapas a seguir para planejar e implantar uma nova infraestrutura de identidade na nuvem. Também é possível usar estas etapas para adaptar a infraestrutura de identidade híbrida ou local existente para trabalhar com o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f73bc-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f73bc-110">Planejar usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="f73bc-110">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="f73bc-111">Proteger suas identidades privilegiadas</span><span class="sxs-lookup"><span data-stu-id="f73bc-111">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="f73bc-112">Configurar identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="f73bc-112">Configure hybrid identity</span></span>](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="f73bc-113">Configurar autenticação de usuário segura</span><span class="sxs-lookup"><span data-stu-id="f73bc-113">Configure secure user authentication</span></span>](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="f73bc-114">Simplificar o acesso para usuários</span><span class="sxs-lookup"><span data-stu-id="f73bc-114">Simplify access for users</span></span>](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="f73bc-115">Usar grupos para facilitar o gerenciamento</span><span class="sxs-lookup"><span data-stu-id="f73bc-115">Use groups for easier management</span></span>](identity-self-service-group-management.md) |

<span data-ttu-id="f73bc-116">Após concluir essas etapas, consulte os [critérios de saída](identity-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f73bc-116">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="f73bc-117">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="f73bc-117">Identity and device access recommendations</span></span>

<span data-ttu-id="f73bc-p102">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para a identidade, use as configurações e recomendações nos artigos a seguir em conjunto com as etapas nesta fase:</span><span class="sxs-lookup"><span data-stu-id="f73bc-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="f73bc-120">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f73bc-120">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="f73bc-121">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="f73bc-121">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="f73bc-122">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f73bc-122">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f73bc-123">Saiba como os especialistas de TI da Microsoft planejaram e implantaram os recursos de identidade do Microsoft 365 Enterprise com estes recursos:</span><span class="sxs-lookup"><span data-stu-id="f73bc-123">Learn how IT experts at Microsoft planned for and deployed the identity capabilities of Microsoft 365 Enterprise with these resources:</span></span>

- [<span data-ttu-id="f73bc-124">Gerenciamento de identidades de usuários e acesso seguro da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f73bc-124">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="f73bc-125">Usar o Azure AD Privileged Identity Management para acesso elevado</span><span class="sxs-lookup"><span data-stu-id="f73bc-125">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="f73bc-126">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f73bc-126">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="f73bc-127">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou uma infraestrutura de identidade híbrida](contoso-identity.md) dos serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f73bc-127">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="f73bc-128">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="f73bc-128">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="f73bc-129">Planejar usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="f73bc-129">Plan for users and groups</span></span>](identity-plan-users-groups.md) |
