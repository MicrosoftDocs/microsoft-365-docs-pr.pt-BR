---
title: Estratégias de implantação da infraestrutura de base do Microsoft 365 para empresas
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 09/24/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Conheça algumas maneiras de implantar as fases da infraestrutura de base do Microsoft 365 para empresas.
ms.openlocfilehash: 765bba743485c13c65cd6377abe01f80f2df4c23
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067778"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="82308-103">Estratégias de implantação da infraestrutura de base do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="82308-103">Microsoft 365 for enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="82308-p101">Há várias maneiras de implantar as fases da [infraestrutura de base](deploy-foundation-infrastructure.md) do Microsoft 365 para empresas e distribuir os respectivos recursos, software e serviços para os usuários. Para iniciar o gerenciamento de projeto desta ação, que pode ser grande e complexa a depender do tamanho da sua organização e da infraestrutura existente, considere as estratégias de implantação a seguir:</span><span class="sxs-lookup"><span data-stu-id="82308-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 for enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="82308-106">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="82308-106">Serial deployment</span></span>
- <span data-ttu-id="82308-107">Implantação paralela com lançamento não sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="82308-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="82308-108">Implantação paralela com lançamento sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="82308-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="82308-109">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="82308-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="82308-110">Use essas estratégias como ideias sobre como gerenciar o projeto em geral e obter mais rapidamente as vantagens do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="82308-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 for enterprise.</span></span>

>[!Note]
><span data-ttu-id="82308-p102">Este artigo contém pressuposições e simplificações para um modo consistente de descrever as estratégias de implantação. Essas estratégias são generalizadas e seu objetivo não é de impor qualquer cronograma específico nem se destinam para aplicação em todas as situações e organizações.</span><span class="sxs-lookup"><span data-stu-id="82308-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="82308-113">Elementos de gerenciamento de projetos de TI para organizações corporativas típicas</span><span class="sxs-lookup"><span data-stu-id="82308-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="82308-p103">A infraestrutura de TI inclui serviços de back-end e o lançamento de recursos novos ou aprimorados ou software instalado para usuários finais. Normalmente, os departamentos de TI implantam elementos de uma infraestrutura de TI de maneira metódica. Uma abordagem de implantação bem-sucedida de um elemento de infraestrutura de TI consiste de:</span><span class="sxs-lookup"><span data-stu-id="82308-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="82308-117">Um lançamento piloto</span><span class="sxs-lookup"><span data-stu-id="82308-117">A pilot rollout</span></span> 

  <span data-ttu-id="82308-118">Isso inclui a configuração inicial da infraestrutura e o lançamento para um conjunto piloto de usuários, testes e modificações subsequentes na configuração da infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="82308-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="82308-119">Um lançamento para usuários</span><span class="sxs-lookup"><span data-stu-id="82308-119">A user rollout</span></span>

  <span data-ttu-id="82308-120">Inclui o lançamento para o restante da organização com base nas regiões, departamentos, grupos ou outros tipos de propagação sistemática de configuração ou software.</span><span class="sxs-lookup"><span data-stu-id="82308-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="82308-121">O conjunto de usuários do lançamento piloto não é o mesmo que o do lançamento os usuários.</span><span class="sxs-lookup"><span data-stu-id="82308-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="82308-122">Este artigo usa o gráfico a seguir para representar essas definições:</span><span class="sxs-lookup"><span data-stu-id="82308-122">This article uses the following graphics to depict these definitions:</span></span> 

![Os gráficos para mostrar as definições de distribuição piloto e de usuário](../media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="82308-124">O sombreamento do gráfico de porcentagem para os usuários indica o lançamento de 0% a 100% em sua organização, usando uma abordagem metódica ou estruturada como grupos, departamentos ou regiões.</span><span class="sxs-lookup"><span data-stu-id="82308-124">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="82308-125">Estratégias de implantação</span><span class="sxs-lookup"><span data-stu-id="82308-125">Deployment strategies</span></span>

<span data-ttu-id="82308-126">Considere as seguintes estratégias de implantação:</span><span class="sxs-lookup"><span data-stu-id="82308-126">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="82308-127">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="82308-127">Serial deployment</span></span>
- <span data-ttu-id="82308-128">Implantação paralela com lançamento não sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="82308-128">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="82308-129">Implantação paralela com lançamento sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="82308-129">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="82308-130">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="82308-130">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="82308-131">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="82308-131">Serial deployment</span></span>

<span data-ttu-id="82308-p104">Com uma implantação em série, você lança totalmente uma fase, permitindo que ela atinja 100% de conclusão da implantação para todos os usuários antes de seguir para a próxima etapa. Veja alguns dos motivos que justificam essa implantação:</span><span class="sxs-lookup"><span data-stu-id="82308-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="82308-134">Redução de riscos</span><span class="sxs-lookup"><span data-stu-id="82308-134">Risk mitigation</span></span>
- <span data-ttu-id="82308-135">Restrições de alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="82308-135">Resourcing constraints</span></span>
- <span data-ttu-id="82308-136">Ciclos de financiamento para o departamento de TI</span><span class="sxs-lookup"><span data-stu-id="82308-136">IT department funding cycles</span></span>
- <span data-ttu-id="82308-137">Dependências de tecnologia do TI</span><span class="sxs-lookup"><span data-stu-id="82308-137">IT technology dependencies</span></span>
- <span data-ttu-id="82308-138">Gestão de mudança nos negócios e resistência dos usuários finais</span><span class="sxs-lookup"><span data-stu-id="82308-138">Business change management and end-user resistance</span></span>

<span data-ttu-id="82308-139">Este gráfico de Gantt mostra uma implantação em série simplificada das etapas 2 a 6 da infraestrutura de base para o Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="82308-139">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 for enterprise.</span></span>

![A implantação serial das fases 2-6 da infraestrutura de base](../media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="82308-141">Para simplificar a discussão e o exemplo, presume-se que cada fase e segmento de implantação de cada etapa duram o mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="82308-141">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="82308-p105">Fase 1: A fase de rede da infraestrutura de base do Microsoft 365 para empresas é de responsabilidade exclusiva do TI. Os usuários colhem os benefícios de uma conectividade otimizada com os recursos de nuvem da Microsoft, mas não sofrem pressão para alcançá-los.</span><span class="sxs-lookup"><span data-stu-id="82308-p105">Phase 1: Networking of the Microsoft 365 for enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="82308-144">Esta é uma experiência teste de usuário simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-144">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="82308-p106">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p107">Em março, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p108">Em junho, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-151">Em setembro, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-151">In September, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-152">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-152">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p110">Em dezembro, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-155">O resultado é uma cadência de 90 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="82308-155">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="82308-156">Esta é uma experiência teste de usuário final simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-156">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="82308-p111">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p112">Em abril, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p113">Em julho, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-163">Em outubro, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-163">In October, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-164">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-164">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p115">Em janeiro do ano subsequente, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-167">O resultado é uma cadência de 90 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="82308-167">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="82308-168">A desvantagem dessa estratégia de implantação é que pode levar muito tempo para implantar totalmente a infraestrutura de base do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="82308-168">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 for enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="82308-169">Implantação paralela com lançamento não sobreposto para o usuário (Paralelo 1)</span><span class="sxs-lookup"><span data-stu-id="82308-169">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="82308-p116">Para essa estratégia de implantação, o lançamento piloto da fase seguinte começa durante a última parte do lançamento para o usuário da fase atual. Esta é a implantação das etapas 2 a 6 quando o lançamento piloto ocorre enquanto o lançamento para o usuário da fase anterior está se encerrando.</span><span class="sxs-lookup"><span data-stu-id="82308-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

![A implantação paralela das fases 2-6 com distribuição de usuário não sobrepostas. ](../media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="82308-p117">O resultado final é que o lançamento para o usuário da fase atual se encerra em sua organização antes de começar a seguinte. Os usuários que não fazem parte do lançamento piloto não lidam com os lançamentos de várias fases ao mesmo tempo, mas os lançamentos piloto acontecem em paralelo aos lançamentos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="82308-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="82308-175">Esta é uma experiência teste de usuário simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-175">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="82308-p118">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p119">Em fevereiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p120">Em abril, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-182">Em junho, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-182">In June, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-183">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-183">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p122">Em agosto, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-186">O resultado é uma cadência de 60 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="82308-186">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="82308-187">Esta é uma experiência teste de usuário final simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-187">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="82308-p123">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p124">Em março, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p125">Em maio, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-194">Em julho, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-194">In July, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-195">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-195">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p127">Em setembro, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-198">O resultado é uma cadência de 60 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="82308-198">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="82308-199">A vantagem dessa estratégia de implantação é que pode levar menos tempo para implantar totalmente a infraestrutura de base do Microsoft 365 para empresas, sem que o departamento de TI e os usuários lidem com várias distribuições ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="82308-199">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="82308-200">Implantação paralela com lançamento sobreposto para o usuário (Paralelo 2)</span><span class="sxs-lookup"><span data-stu-id="82308-200">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="82308-201">Para essa estratégia de implantação, inicie:</span><span class="sxs-lookup"><span data-stu-id="82308-201">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="82308-202">O lançamento piloto da fase seguinte durante a última parte do lançamento para o usuário da fase atual.</span><span class="sxs-lookup"><span data-stu-id="82308-202">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="82308-203">Distribuição ao usuário da próxima fase durante a distribuição da fase atual, de modo que nenhum usuário esteja lidando com distribuições de várias fases ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="82308-203">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time.</span></span> <span data-ttu-id="82308-204">Isso pressupõe que você esteja distribuindo todas as fases da infraestrutura de base da mesma forma, usando regiões, departamentos ou outros agrupamentos.</span><span class="sxs-lookup"><span data-stu-id="82308-204">This assumes that you are rolling out each phase of the foundation infrastructure in the same way, using regions, departments, or other groupings.</span></span>

<span data-ttu-id="82308-205">Esta é uma comparação simplificada entre as diversas estratégias de implantação.</span><span class="sxs-lookup"><span data-stu-id="82308-205">Here is a simplified comparison between the different deployment strategies.</span></span>

![A implantação paralela das fases 2-6 com distribuição de usuário sobrepostas. ](../media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="82308-207">O resultado final é que:</span><span class="sxs-lookup"><span data-stu-id="82308-207">The end result is that:</span></span>

- <span data-ttu-id="82308-208">Os lançamentos piloto passam de uma fase para a próxima sem pausas.</span><span class="sxs-lookup"><span data-stu-id="82308-208">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="82308-209">O lançamento para o usuário de uma fase começa antes da conclusão do lançamento para o usuário da fase anterior, mas nenhum usuário individual está lançando mais de uma fase por vez.</span><span class="sxs-lookup"><span data-stu-id="82308-209">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="82308-210">Esta é uma experiência teste de usuário simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-210">Here’s a simplified pilot user experience as an example:</span></span>

- <span data-ttu-id="82308-p129">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p130">Em janeiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p131">Em fevereiro, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-217">Em março, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-217">In March, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-218">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-218">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p133">Em abril, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-221">O resultado é uma cadência de 30 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="82308-221">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="82308-222">Esta é uma experiência teste de usuário final simplificada como um exemplo:</span><span class="sxs-lookup"><span data-stu-id="82308-222">Here’s a simplified end-user experience as an example:</span></span>

- <span data-ttu-id="82308-p134">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="82308-p135">Em fevereiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-p136">Em março, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-229">Em abril, registro o dispositivo e aplico as políticas de dispositivo e de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82308-229">In April, I get device enrollment and app and device policies applied.</span></span> <span data-ttu-id="82308-230">(Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="82308-230">(Mobile device management)</span></span>
- <span data-ttu-id="82308-p138">Em maio, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="82308-233">O resultado é uma cadência de 30 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="82308-233">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="82308-234">A vantagem dessa estratégia de implantação é que pode levar menos tempo para implantar totalmente a infraestrutura de base do Microsoft 365 para empresas, ainda sem que os usuários lidem com vários lançamentos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="82308-234">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 for enterprise foundation infrastructure, still without having end-users deal with multiple rollouts the same time.</span></span> <span data-ttu-id="82308-235">No entanto, não há interrupção entre as fases sucessivas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="82308-235">However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-the-end-to-end-configuration"></a><span data-ttu-id="82308-236">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="82308-236">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="82308-237">Para empresas menores com a capacidade de compactar as etapas 2 a 6 em um único segmento de implantação, a implantação resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="82308-237">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![Infraestrutura frontal e implantação da configuração de ponta a ponta](../media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="82308-p140">O departamento de TI configura a infraestrutura das fases 2 a 6 e faz o lançamento para os usuários piloto para verificar a funcionalidade de ponta a ponta. Por exemplo, os usuários piloto recebem todas essas funcionalidades ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="82308-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="82308-241">A MFA e outros recursos de identidade (Identidade)</span><span class="sxs-lookup"><span data-stu-id="82308-241">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="82308-242">O Windows 10 Enterprise em dispositivos Windows (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="82308-242">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="82308-243">O Office 365 ProPlus para o pacote do Office (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="82308-243">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="82308-244">Políticas de dispositivo e aplicativos (Gerenciamento de dispositivos móveis)</span><span class="sxs-lookup"><span data-stu-id="82308-244">App and device policies (Mobile device management)</span></span>
- <span data-ttu-id="82308-245">Instalação do cliente de Proteção de Informações do Azure e treinamento sobre como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="82308-245">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="82308-246">Após a conclusão do lançamento piloto, começa o lançamento para os usuários, em que cada usuário recebe todas as funcionalidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="82308-246">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="82308-247">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="82308-247">Next step</span></span>

<span data-ttu-id="82308-248">Iniciar a implantação do Microsoft 365 para empresas com a [infraestrutura de base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="82308-248">Start your deployment of Microsoft 365 for enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
