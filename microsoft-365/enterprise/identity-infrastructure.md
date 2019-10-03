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
ms.openlocfilehash: cb5b714afcacd1e21951ec9f83fd7f09cbd88662
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370438"
---
# <a name="phase-2-identity"></a><span data-ttu-id="5cf01-103">Fase 2: identidade</span><span class="sxs-lookup"><span data-stu-id="5cf01-103">Phase 2: Identity</span></span>

![Fase 2: identidade](./media/deploy-foundation-infrastructure/identity_icon.png)

<span data-ttu-id="5cf01-105">No Microsoft 365 Enterprise, uma infraestrutura de identidade bem planejada e executada fortalece a segurança e o acesso dos dados e cargas de trabalho de produtividade somente por usuários e dispositivos autenticados.</span><span class="sxs-lookup"><span data-stu-id="5cf01-105">In Microsoft 365 Enterprise, a well-planned and executed identity infrastructure paves the way for stronger security and access to your productivity workloads and their data only by authenticated users and devices.</span></span>

<span data-ttu-id="5cf01-106">Assista a este vídeo para ter uma visão geral dos modelos de identidade e autenticação do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5cf01-106">Before you begin, watch this video for an overview of identity models and authentication for Microsoft 365.</span></span>

<span data-ttu-id="5cf01-107"><p> </p></span><span class="sxs-lookup"><span data-stu-id="5cf01-107"></span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
><span data-ttu-id="5cf01-108">Se você já implantou uma infraestrutura de identidade, confira [Critérios de saída de identidade](identity-exit-criteria.md) para garantir que atendam às condições obrigatórias e opcionais do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5cf01-108">If you’ve already deployed an identity infrastructure, please see the [identity exit criteria](identity-exit-criteria.md) to make sure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>
>

<span data-ttu-id="5cf01-109">Para os recursos de identidade de cada plano do Microsoft 365 Enterprise, a função do Azure Active Directory (Azure AD), os componentes locais e os baseados em nuvem, e as configurações de autenticação mais comuns, consulte o [pôster sobre Infraestrutura de Identidade](media/identity-infrastructure/M365E-ID-Infra.pdf).</span><span class="sxs-lookup"><span data-stu-id="5cf01-109">For the identity features of each Microsoft 365 Enterprise plan, the role of Azure Active Directory (Azure AD), on-premises and cloud-based components, and the most common authentication configurations, see the [Identity Infrastructure poster](media/identity-infrastructure/M365E-ID-Infra.pdf).</span></span>

<span data-ttu-id="5cf01-110">[![Pôster sobre a Infraestrutura de Identidade](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span><span class="sxs-lookup"><span data-stu-id="5cf01-110">[![The Identity Infrastructure poster](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)</span></span>

<span data-ttu-id="5cf01-111">Esse pôster de duas páginas é uma maneira rápida de aumentar os conceitos e as configurações do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5cf01-111">This two-page poster is a quick way to ramp up on identity concepts and configurations for Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="5cf01-112">Você também pode [baixar esse pôster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) e imprimir em formatos de carta, oficial ou tablóide (11x17).</span><span class="sxs-lookup"><span data-stu-id="5cf01-112">You can also [download this poster](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf) and print it in letter, legal, or tabloid (11 x 17) formats.</span></span>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a><span data-ttu-id="5cf01-113">Planejar e implantar sua infraestrutura de identidade do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cf01-113">Plan and deploy your Microsoft 365 Enterprise identity infrastructure</span></span> 

<span data-ttu-id="5cf01-p101">Use as etapas a seguir para planejar e implantar uma nova infraestrutura de identidade na nuvem. Também é possível usar estas etapas para adaptar a infraestrutura de identidade híbrida ou local existente para trabalhar com o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5cf01-p101">Use the following steps to plan and deploy your new identity infrastructure in the cloud. You can also use these steps to adapt your existing on-premises or hybrid identity infrastructure to work with Microsoft 365 Enterprise.</span></span> 

|||
|:-------|:-----|
|![Etapa 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="5cf01-117">Criar e proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="5cf01-117">Step 1: Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
|![Etapa 2](./media/stepnumbers/Step2.png)| [<span data-ttu-id="5cf01-119">Proteger suas senhas</span><span class="sxs-lookup"><span data-stu-id="5cf01-119">Step 2: Secure your passwords</span></span>](identity-secure-your-passwords.md) |
|![Etapa 3](./media/stepnumbers/Step3.png)| [<span data-ttu-id="5cf01-121">Proteger e gerenciar as entradas do seu usuário</span><span class="sxs-lookup"><span data-stu-id="5cf01-121">Step 3: Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
|![Etapa 4](./media/stepnumbers/Step4.png)| [<span data-ttu-id="5cf01-123">Adicionar suas contas de usuário</span><span class="sxs-lookup"><span data-stu-id="5cf01-123">Step 4: Add your user accounts</span></span>](identity-add-user-accounts.md) |
|![Etapa 5](./media/stepnumbers/Step5.png)| [<span data-ttu-id="5cf01-125">Usar grupos de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="5cf01-125">Use groups for easier management</span></span>](identity-use-group-management.md) |
|![Etapa 6](./media/stepnumbers/Step6.png)| [<span data-ttu-id="5cf01-127">Configurar o controle de identidade</span><span class="sxs-lookup"><span data-stu-id="5cf01-127">Step 6: Configure identity governance</span></span>](identity-configure-identity-governance.md) |

<span data-ttu-id="5cf01-128">Após concluir essas etapas, consulte os [critérios de saída](identity-exit-criteria.md) para esta fase a fim de garantir que sua rede atende às condições obrigatórias e opcionais à identidade do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5cf01-128">When you've completed these steps, go to the [exit criteria](identity-exit-criteria.md) for this phase to ensure that you meet the required and optional conditions for Microsoft 365 Enterprise.</span></span>

## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="5cf01-129">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="5cf01-129">Identity and device access recommendations</span></span>

<span data-ttu-id="5cf01-p102">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para a identidade, use as configurações e recomendações nos artigos a seguir em conjunto com as etapas nesta fase:</span><span class="sxs-lookup"><span data-stu-id="5cf01-p102">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For identity, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="5cf01-132">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5cf01-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="5cf01-133">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="5cf01-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="5cf01-134">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cf01-134">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5cf01-135">Saiba como os especialistas de TI [da Microsoft gerenciam identidades e protegem o acesso.](https://www.microsoft.com/pt-BR/itshowcase/deploying-and-managing-microsoft-365#primaryR5)</span><span class="sxs-lookup"><span data-stu-id="5cf01-135">Learn how IT experts at Microsoft [manage identities and secure access](https://www.microsoft.com/pt-BR/itshowcase/deploying-and-managing-microsoft-365#primaryR5).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="5cf01-136">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cf01-136">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5cf01-137">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou uma infraestrutura de identidade híbrida](contoso-identity.md) dos serviços em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5cf01-137">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed a hybrid identity infrastructure](contoso-identity.md) for Microsoft 365 cloud services.</span></span>

![A Contoso Corporation](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a><span data-ttu-id="5cf01-139">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5cf01-139">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 1](./media/stepnumbers/Step1.png)| [<span data-ttu-id="5cf01-141">Criar e proteger contas de administrador global</span><span class="sxs-lookup"><span data-stu-id="5cf01-141">Step 1: Create and protect your global admin accounts</span></span>](identity-create-protect-global-admins.md) |
