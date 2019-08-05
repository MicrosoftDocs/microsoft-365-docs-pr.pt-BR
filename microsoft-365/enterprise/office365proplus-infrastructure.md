---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Etapas para implantar a infraestrutura do Office 365 ProPlus para o Microsoft 365 Enterprise.
ms.openlocfilehash: cf698e4dbee17a811a4d2bc01d08d4d97d1961c1
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074171"
---
# <a name="phase-4-office-365-proplus"></a><span data-ttu-id="5de60-103">Fase 4: Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="5de60-103">Phase 4: Office 365 ProPlus</span></span>

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="5de60-104">*Estes critérios aplicam-se às versões E3 e E5 do Microsoft 365 Enterprise e Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="5de60-104">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="5de60-p101">O Microsoft 365 Enterprise inclui o Office 365 ProPlus, a versão de assinatura do Office. Como o Office 2016, o Office 365 ProPlus inclui todos os aplicativos do Office e esses aplicativos são instalados diretamente em seus dispositivos cliente. Ao contrário do Office 2016, o Office 365 ProPlus é atualizado com novos recursos regularmente e tem um modelo de licenciamento baseado em usuário que permite instalar o Office em até 5 dispositivos. Para saber mais, confira [Sobre o Office 365 ProPlus na empresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span><span class="sxs-lookup"><span data-stu-id="5de60-p101">Microsoft 365 Enterprise includes Office 365 ProPlus, the subscription version of Office. Like Office 2016, Office 365 ProPlus includes all the Office applications, and those applications are installed directly on your client devices. Unlike Office 2016, Office 365 ProPlus is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on up to 5 devices. For more details, see [About Office 365 ProPlus in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="5de60-p102">Nesta fase, você implantará o Office 365 ProPlus em dispositivos cliente como parte do Microsoft 365 Enterprise. Além destas instruções, recomendamos usar o [Microsoft Fastrack](https://fasttrack.microsoft.com/office) para ajudar com sua implantação.</span><span class="sxs-lookup"><span data-stu-id="5de60-p102">In this phase, you deploy Office 365 ProPlus to client devices as part of Microsoft 365 Enterprise. In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="5de60-111">O Office 365 ProPlus habilita esses cenários estratégicos de negócios para o Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="5de60-111">Office 365 ProPlus enables these strategic business scenarios for Microsoft 365 Enterprise:</span></span>

- <span data-ttu-id="5de60-112">Colaborar em documentos em tempo real ou em seu próprio tempo para simplificar o processo de cocriação</span><span class="sxs-lookup"><span data-stu-id="5de60-112">Collaborate on documents in real time or on your own time to simplify the cocreation process</span></span>
- <span data-ttu-id="5de60-113">Aproveitar o conhecimento e a experiência coletiva, capacitando as pessoas a descobrir, compartilhar e dar andamento a arquivos, informações e ideias em toda a sua organização</span><span class="sxs-lookup"><span data-stu-id="5de60-113">Harness collective knowledge and expertise by empowering people to discover, share, and progress files, information, and ideas across your organization</span></span>
- <span data-ttu-id="5de60-114">Capacitar os usuários a transformar processos de negócios e aumentar a eficiência</span><span class="sxs-lookup"><span data-stu-id="5de60-114">Empower users to transform business processes and increase efficiency</span></span>
- <span data-ttu-id="5de60-115">Gerenciar projetos, tarefas e prazos para atender seus objetivos de negócios</span><span class="sxs-lookup"><span data-stu-id="5de60-115">Manage projects, tasks, and deadlines to meet your business objectives</span></span>
- <span data-ttu-id="5de60-116">Usar assistência inteligente para design, escrita, descoberta de conteúdo e muito mais para ajudar seu trabalho a se destacar</span><span class="sxs-lookup"><span data-stu-id="5de60-116">Use intelligent assistance for design, writing, content discovery, and more to help your work shine</span></span>
- <span data-ttu-id="5de60-117">Descobrir ideias, analisar dados e compartilhar descobertas para ajudar todos a tomar decisões informadas</span><span class="sxs-lookup"><span data-stu-id="5de60-117">Discover insights, analyze your data, and share your findings to help everyone make informed decisions</span></span>
- <span data-ttu-id="5de60-118">Comunicar-se com sua equipe para se manter informado, solicitar sugestões e criar coesão e consenso</span><span class="sxs-lookup"><span data-stu-id="5de60-118">Communicate with your team to stay informed, solicit input, and build cohesion and consensus</span></span>
- <span data-ttu-id="5de60-119">Comunicar-se com parceiros, colegas e clientes em todo o mundo para chamadas agendadas e ad hoc e reuniões online com grupos de todos os portes</span><span class="sxs-lookup"><span data-stu-id="5de60-119">Communicate with partners, colleagues, and customers around the world for scheduled and ad hoc calls and online meetings with groups of all sizes</span></span>
- <span data-ttu-id="5de60-120">Armazenar e compartilhar arquivos dentro e fora de sua organização para trabalhar de forma transparente entre os limites organizacionais</span><span class="sxs-lookup"><span data-stu-id="5de60-120">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="5de60-121">Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível</span><span class="sxs-lookup"><span data-stu-id="5de60-121">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="5de60-122">Fornecer tranquilidade com controles e visibilidade para conformidade verificada no setor com padrões globais em conformidade</span><span class="sxs-lookup"><span data-stu-id="5de60-122">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="5de60-123">Proteger informações e reduzir o risco de perda de dados</span><span class="sxs-lookup"><span data-stu-id="5de60-123">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="5de60-124">Ficar atualizado e manter-se atualizado em seu software e dispositivos de desktop, reduzindo os riscos de segurança e maximizando a eficiência de TI</span><span class="sxs-lookup"><span data-stu-id="5de60-124">Get current and stay current on your desktop software and devices while reducing security risks and maximizing IT efficiency</span></span>

<span data-ttu-id="5de60-125">Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5de60-125">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="5de60-126">Se você já implantou o Office 365 ProPlus, veja os [critérios de saída](office365proplus-exit-criteria.md) para esta fase para garantir que sua rede atenda às condições obrigatórias do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5de60-126">If you already have Office 365 ProPlus deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="5de60-127">Para implantar o Windows 10 Enterprise e o Office 365 ProPlus juntos, confira o [Centro de Implantação do Computador](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="5de60-127">To deploy both Windows 10 Enterprise and Office 365 ProPlus together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="5de60-128">Etapa 1: Avaliar seu ambiente</span><span class="sxs-lookup"><span data-stu-id="5de60-128">Step 1: Assess your environment</span></span>

<span data-ttu-id="5de60-p103">Antes de implantar o Office 365 ProPlus, siga as orientações em [Avaliar seu ambiente e seus requisitos para a implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Essa avaliação inclui requisitos do sistema, detalhes dos seus dispositivos cliente (como arquiteturas e idiomas necessários), requisitos de licenciamento, capacidade de rede e compatibilidade do aplicativo. Concluir a avaliação ajudará você a tomar decisões importantes como parte do planejamento da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="5de60-p103">Before deploying Office 365 ProPlus, follow the guidance in [Assess your environment and requirements for deploying Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility. Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="5de60-132">Etapa 2: Planejar sua implantação</span><span class="sxs-lookup"><span data-stu-id="5de60-132">Step 2: Plan your deployment</span></span>

<span data-ttu-id="5de60-p104">Após a avaliação do ambiente, siga as orientações em [Planejar sua implantação do Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) para criar um plano de implantação. Esse plano inclui as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="5de60-p104">After assessing your environment, follow the guidance in [Plan your deployment of Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan. This plan includes the following decisions:</span></span> 

- <span data-ttu-id="5de60-135">Como implantar o Office, incluindo qual ferramenta usar (como o System Center Configuration Manager ou a Ferramenta de Implantação do Office [ODT]) e de onde instalar o Office</span><span class="sxs-lookup"><span data-stu-id="5de60-135">How to deploy Office, including what tool to use (such as System Center Configuration Manager or the Office Deployment Tool [ODT]) and where to install Office from</span></span>
- <span data-ttu-id="5de60-136">Como gerenciar as atualizações do Office</span><span class="sxs-lookup"><span data-stu-id="5de60-136">How to manage updates to Office</span></span>
- <span data-ttu-id="5de60-137">Quais canais de atualização utilizar (os canais de atualização do Office controlam a frequência com a qual seus usuários recebem atualizações de recursos para os aplicativos do Office)</span><span class="sxs-lookup"><span data-stu-id="5de60-137">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="5de60-138">Os pacotes de instalação e grupos de implantação do Office que você deseja usar, incluindo quais aplicativos do Office e idiomas devem ser instalados para quais usuários</span><span class="sxs-lookup"><span data-stu-id="5de60-138">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="5de60-139">O [artigo de planejamento](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) contém as práticas recomendadas para todas essas opções, incluindo como gerenciar sua implantação, gerenciar suas atualizações, definir os pacotes de instalação e criar grupos de implantação.</span><span class="sxs-lookup"><span data-stu-id="5de60-139">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="5de60-140">Etapa 3: Implantar</span><span class="sxs-lookup"><span data-stu-id="5de60-140">Step 3: Deploy</span></span>

<span data-ttu-id="5de60-141">Com base no seu plano de implantação da etapa 2, escolha como deseja implantar:</span><span class="sxs-lookup"><span data-stu-id="5de60-141">Based on your deployment plan from step 2, choose how you want to deploy:</span></span>

- <span data-ttu-id="5de60-142">**[Implantar o Office 365 ProPlus com o System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Gerencie sua implantação com o Configuration Manager, e baixar e implante o Office de pontos de distribuição em sua rede</span><span class="sxs-lookup"><span data-stu-id="5de60-142">**[Deploy Office 365 ProPlus with System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="5de60-143">**[Implantar o Office 365 ProPlus com a ODT da nuvem](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Gerencie sua implantação com a ODT e instale o Office em dispositivos cliente diretamente do Office CDN</span><span class="sxs-lookup"><span data-stu-id="5de60-143">**[Deploy Office 365 ProPlus with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="5de60-144">**[Implantar o Office 365 ProPlus com a ODT de uma origem local](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Gerencie sua implantação com a ODT, e baixe e implante o Office de uma origem local na sua rede</span><span class="sxs-lookup"><span data-stu-id="5de60-144">**[Deploy Office 365 ProPlus with the ODT from a local source](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Manage your deployment with the ODT, and download and deploy Office from a local source on your network</span></span> 

- <span data-ttu-id="5de60-145">**[Instale o Office 365 ProPlus por conta própria pelo portal do Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Gerencie sua implantação pelo portal do Office e peça que seus usuários instalem o Office nos dispositivos cliente deles diretamente do portal</span><span class="sxs-lookup"><span data-stu-id="5de60-145">**[Self-install Office 365 ProPlus from the Office portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="5de60-p105">Muitas organizações usarão uma combinação dessas opções para diferentes usuários. Por exemplo, uma organização pode usar o Configuration Manager para implantar o Office para a maioria de seus usuários, mas permitir que um pequeno grupo de funcionários que não estejam conectados à rede interna com frequência instalem o Office por conta própria.</span><span class="sxs-lookup"><span data-stu-id="5de60-p105">Many organizations will use a combination of these options for different users. For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="5de60-p106">Se sua organização usar o Configuration Manager, é recomendável atualizar para o Branch Atual e obter a versão mais recente. Para saber mais, confira [Qual branch do Configuration Manager devo usar?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span><span class="sxs-lookup"><span data-stu-id="5de60-p106">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release. For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="5de60-150">Como a Microsoft desenvolve o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5de60-150">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5de60-151">Saiba como os especialistas da Microsoft estão [implantando e gerenciando as atualizações para o Office 365 ProPlus.](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7)</span><span class="sxs-lookup"><span data-stu-id="5de60-151">Learn how the experts at Microsoft are [deploying and mananging updates for Office 365 ProPlus](https://www.microsoft.com/en-us/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="5de60-152">Como a Contoso desenvolveu o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5de60-152">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="5de60-153">Veja como a Contoso Corporation, uma empresa multinacional fictícia mas representativa, [implantou o Office 365 ProPlus](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="5de60-153">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Office 365 ProPlus](contoso-o365pp.md).</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="5de60-154">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5de60-154">Next step</span></span>

[<span data-ttu-id="5de60-155">Critérios de saída da infraestrutura do Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="5de60-155">Office 365 ProPlus infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
