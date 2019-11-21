---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura do Office 365 ProPlus para o Microsoft 365 Enterprise.
ms.openlocfilehash: 30e3956eba0e990d8d07a41dae924c3005f34d75
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757748"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="37cf8-103">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="37cf8-103">Phase 4: Office 365 ProPlus</span></span>

![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="37cf8-105">*Estes critérios aplicam-se às versões E3 e E5 do Microsoft 365 Enterprise e Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="37cf8-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="37cf8-106">O Microsoft 365 Enterprise inclui o Office 365 ProPlus, a versão de assinatura do Office.</span><span class="sxs-lookup"><span data-stu-id="37cf8-106">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office.</span></span> <span data-ttu-id="37cf8-107">Como o Office 2019, o Office 365 ProPlus inclui todos os aplicativos do Office, e esses aplicativos são instalados diretamente nos dispositivos clientes.</span><span class="sxs-lookup"><span data-stu-id="37cf8-107">Like Office 2019, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="37cf8-108">Diferentemente do Office 2019, o Office 365 ProPlus é atualizado regularmente com novos recursos e possui um modelo de licenciamento baseado no usuário que permite que as pessoas instalem o Office em vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="37cf8-108">Unlike Office 2019, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="37cf8-109">Para obter mais detalhes, consulte [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="37cf8-109">For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="37cf8-p102">Nesta fase, você implantará o Office 365 ProPlus em dispositivos cliente como parte do Microsoft 365 Enterprise. Além destas instruções, recomendamos usar o [Microsoft Fastrack](https://fasttrack.microsoft.com/office) para ajudar com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="37cf8-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="37cf8-112">Se você já implantou o Office 365 ProPlus, veja os [critérios de saída](office365proplus-exit-criteria.md) para esta fase para garantir que sua rede atenda às condições obrigatórias do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="37cf8-112">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="37cf8-113">Para implantar o Windows 10 Enterprise e o Office 365 ProPlus juntos, confira o [Centro de Implantação do Computador](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="37cf8-113">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="37cf8-114">Etapa 1: Avaliar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="37cf8-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="37cf8-p103">Antes de implantar o Office 365 ProPlus, siga as orientações em [Avaliar seu ambiente e seus requisitos para a implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Essa avaliação inclui requisitos do sistema, detalhes dos seus dispositivos cliente (como arquiteturas e idiomas necessários), requisitos de licenciamento, capacidade de rede e compatibilidade do aplicativo. Concluir a avaliação ajudará você a tomar decisões importantes como parte do planejamento da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="37cf8-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="37cf8-118">Etapa 2: Planejar sua implantação</span><span class="sxs-lookup"><span data-stu-id="37cf8-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="37cf8-p104">Após a avaliação do ambiente, siga as orientações em [Planejar sua implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) para criar um plano de implantação. Esse plano inclui as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="37cf8-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="37cf8-121">Como implantar o Office, incluindo qual ferramenta usar (como o Microsoft Endpoint Configuration Manager ou a Ferramenta de Implantação do Office) e a partir de onde instalar o Office</span><span class="sxs-lookup"><span data-stu-id="37cf8-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="37cf8-122">Como gerenciar as atualizações do Office</span><span class="sxs-lookup"><span data-stu-id="37cf8-122">How to manage updates to Office</span></span>
- <span data-ttu-id="37cf8-123">Quais canais de atualização utilizar (os canais de atualização do Office controlam a frequência com a qual seus usuários recebem atualizações de recursos para os aplicativos do Office)</span><span class="sxs-lookup"><span data-stu-id="37cf8-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="37cf8-124">Os pacotes de instalação e grupos de implantação do Office que você deseja usar, incluindo quais aplicativos do Office e idiomas devem ser instalados para quais usuários</span><span class="sxs-lookup"><span data-stu-id="37cf8-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="37cf8-125">O [artigo de planejamento](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) contém as práticas recomendadas para todas essas opções, incluindo como gerenciar sua implantação, gerenciar suas atualizações, definir os pacotes de instalação e criar grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="37cf8-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="37cf8-126">Etapa 3: Implantar</span><span class="sxs-lookup"><span data-stu-id="37cf8-126">Step 3: Deploy</span></span>

<span data-ttu-id="37cf8-127">Com base no seu plano de implantação, escolha como deseja implantar:</span><span class="sxs-lookup"><span data-stu-id="37cf8-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="37cf8-128">**[Implantar o Office 365 ProPlus com o Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Gerencie sua implantação com o Configuration Manager, baixe e implante o Office a partir de pontos de distribuição na sua rede.</span><span class="sxs-lookup"><span data-stu-id="37cf8-128">**[Deploy Office 365 ProPlus with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="37cf8-129">**[Implantar o Office 365 ProPlus com a ODT da nuvem](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Gerencie sua implantação com a ODT e instale o Office em dispositivos cliente diretamente do Office CDN</span><span class="sxs-lookup"><span data-stu-id="37cf8-129">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="37cf8-130">**[Instale o Office 365 ProPlus por conta própria pelo portal do Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Gerencie sua implantação pelo portal do Office e peça que seus usuários instalem o Office nos dispositivos cliente deles diretamente do portal</span><span class="sxs-lookup"><span data-stu-id="37cf8-130">**[Self-install Office 365 ProPlus from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="37cf8-p105">Muitas organizações usarão uma combinação dessas opções para diferentes usuários. Por exemplo, uma organização pode usar o Configuration Manager para implantar o Office para a maioria de seus usuários, mas permitir que um pequeno grupo de funcionários que não estejam conectados à rede interna com frequência instalem o Office por conta própria.</span><span class="sxs-lookup"><span data-stu-id="37cf8-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="37cf8-p106">Se sua organização usar o Configuration Manager, é recomendável atualizar para o Branch Atual e obter a versão mais recente. Para saber mais, confira [Qual branch do Configuration Manager devo usar?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="37cf8-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="37cf8-135">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="37cf8-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="37cf8-136">Saiba como os especialistas da Microsoft estão [implantando e gerenciando as atualizações para o Office 365 ProPlus.](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7)</span><span class="sxs-lookup"><span data-stu-id="37cf8-136">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="37cf8-137">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="37cf8-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="37cf8-138">Veja como a Contoso Corporation, uma empresa multinacional fictícia mas representativa, [implantou o Office 365 ProPlus](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="37cf8-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![A Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="37cf8-140">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="37cf8-140">Next step</span></span>

[<span data-ttu-id="37cf8-141">Critérios de saída da infraestrutura do Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="37cf8-141">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
