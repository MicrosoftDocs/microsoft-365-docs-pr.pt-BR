---
title: 'Fase 2: identidade'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: As etapas para implantar sua infraestrutura de identidade do Microsoft 365 Enterprise.
ms.openlocfilehash: 2d9ffcc5122b5a5dfc94fb007167655e879d6799
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071690"
---
# <a name="phase-2-identity"></a><span data-ttu-id="26da6-103">Fase 2: identidade</span><span class="sxs-lookup"><span data-stu-id="26da6-103">Phase 2: Identity</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="26da6-104">No Microsoft 365 Enterprise, uma infraestrutura de identidade bem planejada e executada fortalece a segurança e o acesso dos dados e cargas de trabalho de produtividade somente por usuários e dispositivos autenticados.</span><span class="sxs-lookup"><span data-stu-id="26da6-104">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="26da6-105">Assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26da6-105">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="26da6-106"><p> </p></span><span class="sxs-lookup"><span data-stu-id="26da6-106"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="26da6-107">Se você já implantou uma infraestrutura de identidade, confira [Critérios de saída de identidade](identity-exit-criteria.md) para garantir que atendam às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26da6-107">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="26da6-108">Para os recursos de identidade de cada plano do Microsoft 365 Enterprise, a função do Azure Active Directory (Azure AD), os componentes locais e os baseados em nuvem, e as configurações de autenticação mais comuns, consulte o [pôster sobre Infraestrutura de Identidade](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="26da6-108">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="26da6-109">[![Pôster sobre a Infraestrutura de Identidade](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="26da6-109">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="26da6-110">Esse pôster de duas páginas é uma maneira rápida de aumentar os conceitos e as configurações do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26da6-110">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="26da6-111">Você também pode [baixar esse pôster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) e imprimir em formatos de carta, oficial ou tablóide (11x17).</span><span class="sxs-lookup"><span data-stu-id="26da6-111">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="26da6-112">Planejar e implantar sua infraestrutura de identidade do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26da6-112">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="26da6-p101">Use as etapas a seguir para planejar e implantar uma nova infraestrutura de identidade na nuvem. Também é possível usar estas etapas para adaptar a infraestrutura de identidade híbrida ou local existente para trabalhar com o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26da6-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="26da6-115">Criar e proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="26da6-115">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="26da6-116">Proteger suas senhas</span><span class="sxs-lookup"><span data-stu-id="26da6-116">Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="26da6-117">Proteger e gerenciar as entradas do seu usuário</span><span class="sxs-lookup"><span data-stu-id="26da6-117">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="26da6-118">Adicionar suas contas de usuário</span><span class="sxs-lookup"><span data-stu-id="26da6-118">Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="26da6-119">Usar grupos de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="26da6-119">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="26da6-120">Configurar a governança de identidade</span><span class="sxs-lookup"><span data-stu-id="26da6-120">Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="26da6-121">Após concluir essas etapas, consulte os [critérios de saída](identity-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais à identidade do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26da6-121">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="26da6-122">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="26da6-122">Identity and device access recommendations</span></span>

<span data-ttu-id="26da6-p102">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para a identidade, use as configurações e recomendações nos artigos a seguir em conjunto com as etapas nesta fase:</span><span class="sxs-lookup"><span data-stu-id="26da6-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="26da6-125">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26da6-125">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="26da6-126">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="26da6-126">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="26da6-127">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26da6-127">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="26da6-128">Saiba como os especialistas de TI [da Microsoft gerenciam identidades e protegem o acesso.](https://www.microsoft.com/pt-BR/itshowcase/deploying-and-managing-microsoft-365#primaryR5)</span><span class="sxs-lookup"><span data-stu-id="26da6-128">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/pt-BR/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="26da6-129">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26da6-129">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="26da6-130">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou uma infraestrutura de identidade híbrida](contoso-identity.md) dos serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26da6-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="26da6-131">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="26da6-131">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [<span data-ttu-id="26da6-132">Criar e proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="26da6-132">Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
