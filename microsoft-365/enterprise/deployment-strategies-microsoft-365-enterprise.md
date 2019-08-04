---
title: Estratégias de implantação da infraestrutura de base do Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 01/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Conheça algumas maneiras de implantar as fases da infraestrutura de base para o Microsoft 365 Enterprise.
ms.openlocfilehash: 2c30420390be97d33f66888eac533b89c907b3b2
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073881"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure-deployment-strategies"></a><span data-ttu-id="ee3af-103">Estratégias de implantação da infraestrutura de base do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ee3af-103">Microsoft 365 Enterprise foundation infrastructure deployment strategies</span></span>

<span data-ttu-id="ee3af-p101">Há várias maneiras de implantar as fases da [infraestrutura de base](deploy-foundation-infrastructure.md) do Microsoft 365 Enterprise e distribuir os respectivos recursos, software e serviços para os usuários. Para iniciar o gerenciamento de projeto desta ação, que pode ser grande e complexa a depender do tamanho da sua organização e da infraestrutura existente, considere as estratégias de implantação a seguir:</span><span class="sxs-lookup"><span data-stu-id="ee3af-p101">There are many ways you can deploy the phases of the [foundation infrastructure](deploy-foundation-infrastructure.md) of Microsoft 365 Enterprise and roll out its capabilities, software, and services to your users. To get you started on the project management of this undertaking, which can be large and complex depending on the size of your organization and its existing infrastructure, consider the following deployment strategies:</span></span>

- <span data-ttu-id="ee3af-106">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="ee3af-106">Serial deployment</span></span>
- <span data-ttu-id="ee3af-107">Implantação paralela com lançamento não sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="ee3af-107">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="ee3af-108">Implantação paralela com lançamento sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="ee3af-108">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="ee3af-109">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="ee3af-109">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

<span data-ttu-id="ee3af-110">Use essas estratégias como ideias sobre como gerenciar o projeto em geral e por em prática mais rapidamente as vantagens do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ee3af-110">Use these strategies for ideas on how to manage the overall project and more quickly realize the business benefits of Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="ee3af-p102">Este artigo contém pressuposições e simplificações para um modo consistente de descrever as estratégias de implantação. Essas estratégias são generalizadas e seu objetivo não é de impor qualquer cronograma específico nem se destinam para aplicação em todas as situações e organizações.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p102">This article contains assumptions and simplifications for a consistent way to describe the deployment strategies. These deployment strategies are generalized and are not meant to imply any specific timeframes, nor are they meant to apply to all organizations and situations.</span></span>
>

## <a name="elements-of-it-project-management-for-typical-enterprise-organizations"></a><span data-ttu-id="ee3af-113">Elementos de gerenciamento de projetos de TI para organizações corporativas típicas</span><span class="sxs-lookup"><span data-stu-id="ee3af-113">Elements of IT project management for typical enterprise organizations</span></span>

<span data-ttu-id="ee3af-p103">A infraestrutura de TI inclui serviços de back-end e o lançamento de recursos novos ou aprimorados ou software instalado para usuários finais. Normalmente, os departamentos de TI implantam elementos de uma infraestrutura de TI de maneira metódica. Uma abordagem de implantação bem-sucedida de um elemento de infraestrutura de TI consiste de:</span><span class="sxs-lookup"><span data-stu-id="ee3af-p103">IT infrastructure includes both backend services and the rollout of new or improved capabilities or installed software to end users. IT departments typically deploy elements of an IT infrastructure in a methodical way. One approach to the successful deployment of an element of IT infrastructure consists of:</span></span>

- <span data-ttu-id="ee3af-117">Um lançamento piloto</span><span class="sxs-lookup"><span data-stu-id="ee3af-117">A pilot rollout</span></span> 

  <span data-ttu-id="ee3af-118">Isso inclui a configuração inicial da infraestrutura e o lançamento para um conjunto piloto de usuários, testes e modificações subsequentes na configuração da infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="ee3af-118">This includes initial infrastructure configuration and rollout to a pilot set of users, testing, and subsequent modifications to the infrastructure configuration.</span></span>

- <span data-ttu-id="ee3af-119">Um lançamento para usuários</span><span class="sxs-lookup"><span data-stu-id="ee3af-119">A user rollout</span></span>

  <span data-ttu-id="ee3af-120">Inclui o lançamento para o restante da organização com base nas regiões, departamentos, grupos ou outros tipos de propagação sistemática de configuração ou software.</span><span class="sxs-lookup"><span data-stu-id="ee3af-120">This includes the rollout to the rest of your organization based on regions, departments, groups, or other types of systematic propagation of configuration or software.</span></span>

<span data-ttu-id="ee3af-121">O conjunto de usuários do lançamento piloto não é o mesmo que o do lançamento os usuários.</span><span class="sxs-lookup"><span data-stu-id="ee3af-121">The set of users in the pilot rollout are not the same as those in the user rollout.</span></span>

<span data-ttu-id="ee3af-122">Este artigo usa o gráfico a seguir para representar essas definições:</span><span class="sxs-lookup"><span data-stu-id="ee3af-122">This article uses the following graphics to depict these definitions:</span></span> 

![](./media/deployment-strategies-microsoft-365-enterprise/definitions.png) 

<span data-ttu-id="ee3af-123">O sombreamento do gráfico de porcentagem para os usuários indica o lançamento de 0% a 100% em sua organização, usando uma abordagem metódica ou estruturada como grupos, departamentos ou regiões.</span><span class="sxs-lookup"><span data-stu-id="ee3af-123">The shading for the user rollout graphic indicates the percentage across your organization from 0% to 100% using a structured or methodical approach such as groups, departments, or regions.</span></span>

## <a name="deployment-strategies"></a><span data-ttu-id="ee3af-124">Estratégias de implantação</span><span class="sxs-lookup"><span data-stu-id="ee3af-124">Deployment strategies</span></span>

<span data-ttu-id="ee3af-125">Considere as seguintes estratégias de implantação:</span><span class="sxs-lookup"><span data-stu-id="ee3af-125">Consider the following deployment strategies:</span></span>

- <span data-ttu-id="ee3af-126">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="ee3af-126">Serial deployment</span></span>
- <span data-ttu-id="ee3af-127">Implantação paralela com lançamento não sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="ee3af-127">Parallel deployment with non-overlapping user rollout</span></span>
- <span data-ttu-id="ee3af-128">Implantação paralela com lançamento sobreposto para o usuário</span><span class="sxs-lookup"><span data-stu-id="ee3af-128">Parallel deployment with overlapping user rollout</span></span>
- <span data-ttu-id="ee3af-129">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="ee3af-129">Up-front infrastructure and rollout of the end-to-end configuration</span></span>

### <a name="serial-deployment"></a><span data-ttu-id="ee3af-130">Implantação em série</span><span class="sxs-lookup"><span data-stu-id="ee3af-130">Serial deployment</span></span>

<span data-ttu-id="ee3af-p104">Com uma implantação em série, você lança totalmente uma fase, permitindo que ela atinja 100% de conclusão da implantação para todos os usuários antes de seguir para a próxima etapa. Veja alguns dos motivos que justificam essa implantação:</span><span class="sxs-lookup"><span data-stu-id="ee3af-p104">With a serial deployment, you completely roll out a phase, allowing the phase to reach 100% completion of deployment to all of your users, before moving on to the next one. Here are some of the reasons why you might deploy this way:</span></span>

- <span data-ttu-id="ee3af-133">Redução de riscos</span><span class="sxs-lookup"><span data-stu-id="ee3af-133">Risk mitigation</span></span>
- <span data-ttu-id="ee3af-134">Restrições de alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="ee3af-134">Resourcing constraints</span></span>
- <span data-ttu-id="ee3af-135">Ciclos de financiamento para o departamento de TI</span><span class="sxs-lookup"><span data-stu-id="ee3af-135">IT department funding cycles</span></span>
- <span data-ttu-id="ee3af-136">Dependências de tecnologia do TI</span><span class="sxs-lookup"><span data-stu-id="ee3af-136">IT technology dependencies</span></span>
- <span data-ttu-id="ee3af-137">Gestão de mudança nos negócios e resistência dos usuários finais</span><span class="sxs-lookup"><span data-stu-id="ee3af-137">Business change management and end-user resistance</span></span>

<span data-ttu-id="ee3af-138">Este gráfico de Gantt mostra uma implantação em série simplificada das etapas 2 a 6 da infraestrutura de base para o Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ee3af-138">This Gantt chart shows a simplified serial deployment of phases 2-6 of the foundation infrastructure for Microsoft 365 Enterprise.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/serial.png) 
 
<span data-ttu-id="ee3af-139">Para simplificar a discussão e o exemplo, presume-se que cada fase e segmento de implantação de cada etapa duram o mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ee3af-139">To simplify the discussion and example, each phase and deployment segment within each phase are assumed to take the same amount of time.</span></span>

>[!Note]
><span data-ttu-id="ee3af-p105">Fase 1: a fase de rede da infraestrutura de base do Microsoft 365 Enterprise é de responsabilidade exclusiva do TI. Os usuários colhem os benefícios de uma conectividade otimizada com os recursos de nuvem da Microsoft, mas não sofrem pressão para alcançá-los.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p105">Phase 1: Networking of the Microsoft 365 Enterprise Foundation Infrastructure is an IT department-only phase. Users reap the benefits of optimized connectivity to Microsoft’s cloud resources but are not imposed upon to achieve it.</span></span>
>

<span data-ttu-id="ee3af-142">Exemplo simplificado da experiência piloto do usuário:</span><span class="sxs-lookup"><span data-stu-id="ee3af-142">Simplified example pilot user experience:</span></span>

- <span data-ttu-id="ee3af-p106">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p106">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p107">Em março, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p107">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p108">Em junho, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p108">In June, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p109">Em setembro, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p109">In September, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p110">Em dezembro, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p110">In December, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-153">O resultado é uma cadência de 90 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="ee3af-153">The result is a 90-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="ee3af-154">Exemplo simplificado de experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="ee3af-154">Simplified example end-user experience:</span></span>

- <span data-ttu-id="ee3af-p111">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p111">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p112">Em abril, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p112">In April, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p113">Em julho, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p113">In July, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p114">Em outubro, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p114">In October, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p115">Em janeiro do ano subsequente, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p115">In January of the following year, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-165">O resultado é uma cadência de 90 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ee3af-165">The result is a 90-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="ee3af-166">A desvantagem dessa estratégia de implantação é que pode levar muito tempo para implantar totalmente a infraestrutura de base do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ee3af-166">The disadvantage to this deployment strategy is that it can take a long time to fully deploy the Microsoft 365 Enterprise foundation infrastructure.</span></span>

### <a name="parallel-deployment-with-non-overlapping-user-rollout-parallel-1"></a><span data-ttu-id="ee3af-167">Implantação paralela com lançamento não sobreposto para o usuário (Paralelo 1)</span><span class="sxs-lookup"><span data-stu-id="ee3af-167">Parallel deployment with non-overlapping user rollout (Parallel 1)</span></span>

<span data-ttu-id="ee3af-p116">Para essa estratégia de implantação, o lançamento piloto da fase seguinte começa durante a última parte do lançamento para o usuário da fase atual. Esta é a implantação das etapas 2 a 6 quando o lançamento piloto ocorre enquanto o lançamento para o usuário da fase anterior está se encerrando.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p116">For this deployment strategy, you start the pilot rollout of the next phase during the last part of the user rollout of the current phase. Here is the deployment of phases 2-6 when the pilot rollout occurs as the user rollout of the previous phase is wrapping up.</span></span>

<span data-ttu-id="ee3af-170">Esta é uma comparação simplificada entre as estratégias de implantação em série e paralela.</span><span class="sxs-lookup"><span data-stu-id="ee3af-170">Here is a simplified comparison between parallel and serial deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel1.png) 
 
<span data-ttu-id="ee3af-p117">O resultado final é que o lançamento para o usuário da fase atual se encerra em sua organização antes de começar a seguinte. Os usuários que não fazem parte do lançamento piloto não lidam com os lançamentos de várias fases ao mesmo tempo, mas os lançamentos piloto acontecem em paralelo aos lançamentos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p117">The end result is that user rollout for the current phase completes across your organization before the next one starts. Users that are not in pilot rollouts are not dealing with the rollouts of multiple phases at the same time, but pilot rollouts are done in parallel with user rollouts.</span></span>

<span data-ttu-id="ee3af-173">Exemplo simplificado da experiência piloto do usuário:</span><span class="sxs-lookup"><span data-stu-id="ee3af-173">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="ee3af-p118">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p118">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p119">Em fevereiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p119">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p120">Em abril, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p120">In April, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p121">Em junho, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p121">In June, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p122">Em agosto, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p122">In August, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-184">O resultado é uma cadência de 60 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="ee3af-184">The result is a 60-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="ee3af-185">Exemplo simplificado de experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="ee3af-185">Simplified example end-user experience:</span></span>

- <span data-ttu-id="ee3af-p123">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p123">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p124">Em março, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p124">In March, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p125">Em maio, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p125">In May, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p126">Em julho, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p126">In July, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p127">Em setembro, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p127">In September, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-196">O resultado é uma cadência de 60 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ee3af-196">The result is a 60-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="ee3af-197">A vantagem dessa estratégia de implantação é que pode levar menos tempo para implantar totalmente a infraestrutura de base do Microsoft 365 Enterprise, sem forçar seu departamento de TI e os usuários a lidar com vários lançamentos simultâneos.</span><span class="sxs-lookup"><span data-stu-id="ee3af-197">The advantage to this deployment strategy is that it can take less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, without having your IT department and users deal with multiple rollouts the same time.</span></span>

### <a name="parallel-deployment-with-overlapping-user-rollout-parallel-2"></a><span data-ttu-id="ee3af-198">Implantação paralela com lançamento sobreposto para o usuário (Paralelo 2)</span><span class="sxs-lookup"><span data-stu-id="ee3af-198">Parallel deployment with overlapping user rollout (Parallel 2)</span></span>

<span data-ttu-id="ee3af-199">Para essa estratégia de implantação, inicie:</span><span class="sxs-lookup"><span data-stu-id="ee3af-199">For this deployment strategy, you start the:</span></span>

- <span data-ttu-id="ee3af-200">O lançamento piloto da fase seguinte durante a última parte do lançamento para o usuário da fase atual.</span><span class="sxs-lookup"><span data-stu-id="ee3af-200">Pilot rollout of the next phase during the last part of the user rollout of the current phase.</span></span>
- <span data-ttu-id="ee3af-p128">O lançamento para o usuário da fase seguinte durante o lançamento para o usuário da fase atual de forma que nenhum usuário precise lidar com o lançamento das várias fases ao mesmo tempo. Isso supõe que você esteja lançando cada fase da infraestrutura de base da mesma forma, nas regiões, departamentos ou outros.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p128">User rollout of the next phase during the user rollout of the current phase in such a way that no user is dealing with the rollouts of multiple phases at the same time. This assumes that you are rolling out each phase of the foundation infrastructure in the same way, via regions, departments, or other.</span></span>

<span data-ttu-id="ee3af-203">Esta é uma comparação simplificada entre as diversas estratégias de implantação.</span><span class="sxs-lookup"><span data-stu-id="ee3af-203">Here is a simplified comparison between the different deployment strategies.</span></span>

![](./media/deployment-strategies-microsoft-365-enterprise/parallel2.png) 

<span data-ttu-id="ee3af-204">O resultado final é que:</span><span class="sxs-lookup"><span data-stu-id="ee3af-204">The end result is that:</span></span>

- <span data-ttu-id="ee3af-205">Os lançamentos piloto passam de uma fase para a próxima sem pausas.</span><span class="sxs-lookup"><span data-stu-id="ee3af-205">Pilot rollouts go from one phase to the next without a pause.</span></span>
- <span data-ttu-id="ee3af-206">O lançamento para o usuário de uma fase começa antes da conclusão do lançamento para o usuário da fase anterior, mas nenhum usuário individual está lançando mais de uma fase por vez.</span><span class="sxs-lookup"><span data-stu-id="ee3af-206">The user rollout for a phase begins before the completion of the user rollout of the previous phase, but no individual user is rolling out more than one phase at a time.</span></span>

<span data-ttu-id="ee3af-207">Exemplo simplificado da experiência piloto do usuário:</span><span class="sxs-lookup"><span data-stu-id="ee3af-207">Simplified example pilot user experience:</span></span> 

- <span data-ttu-id="ee3af-p129">Em dezembro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p129">In December, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p130">Em janeiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p130">In January, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p131">Em fevereiro, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p131">In February, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p132">Em março, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p132">In March, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p133">Em abril, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p133">In April, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-218">O resultado é uma cadência de 30 dias entre lançamentos piloto sucessivos.</span><span class="sxs-lookup"><span data-stu-id="ee3af-218">The result is a 30-day cadence between successive pilot rollouts.</span></span>

<span data-ttu-id="ee3af-219">Exemplo simplificado de experiência do usuário final:</span><span class="sxs-lookup"><span data-stu-id="ee3af-219">Simplified example end-user experience:</span></span>

- <span data-ttu-id="ee3af-p134">Em janeiro, preciso usar meu smartphone para MFA. (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p134">In January, I need to use my smart phone for MFA. (Identity)</span></span>
- <span data-ttu-id="ee3af-p135">Em fevereiro, instalo o Windows 10 Enterprise no meu computador com Windows 8.1. (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p135">In February, I get Windows 10 Enterprise installed on my Windows 8.1 desktop. (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-p136">Em março, instalo o Office 365 ProPlus em substituição ao Office 2013. (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p136">In March, I get Office 365 ProPlus installed, replacing Office 2013. (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-p137">Em abril, registro o dispositivo e aplico as políticas de acesso condicional e do aplicativo. (Gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p137">In April, I get device enrollment and app and conditional access policies applied. (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-p138">Em maio, instalo o cliente de Proteção de Informações do Azure e aprendo como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-p138">In May, I get the Azure Information Protection client installed and get trained on how to apply labels to documents. (Information protection)</span></span>

<span data-ttu-id="ee3af-230">O resultado é uma cadência de 30 dias entre lançamentos sucessivos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="ee3af-230">The result is a 30-day cadence between successive user rollouts.</span></span>

<span data-ttu-id="ee3af-p139">A vantagem dessa estratégia de implantação é que pode levar até menos tempo para implantar totalmente a infraestrutura de base do Microsoft 365 Enterprise, sem fazer com que os usuários individuais tenham que lidar com vários lançamentos simultâneos. No entanto, os usuários não têm uma pausa entre fases sucessivas.</span><span class="sxs-lookup"><span data-stu-id="ee3af-p139">The advantage to this deployment strategy is that it can take even less time to fully deploy the Microsoft 365 Enterprise foundation infrastructure, still without having individual users deal with multiple rollouts the same time. However, users don’t get a break between successive phases.</span></span>

### <a name="up-front-infrastructure-and-rollout-of-end-to-end-configuration"></a><span data-ttu-id="ee3af-233">Infraestrutura inicial e lançamento da configuração de ponta a ponta</span><span class="sxs-lookup"><span data-stu-id="ee3af-233">Up-front infrastructure and rollout of end-to-end configuration</span></span>

<span data-ttu-id="ee3af-234">Para empresas menores com a capacidade de compactar as etapas 2 a 6 em um único segmento de implantação, a implantação resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="ee3af-234">For smaller organizations with the ability to compress phases 2-6 into a single deployment segment, the resulting deployment looks like this:</span></span>
 
![](./media/deployment-strategies-microsoft-365-enterprise/up-front.png) 

<span data-ttu-id="ee3af-p140">O departamento de TI configura a infraestrutura das fases 2 a 6 e faz o lançamento para os usuários piloto para verificar a funcionalidade de ponta a ponta. Por exemplo, os usuários piloto recebem todas essas funcionalidades ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="ee3af-p140">The IT department configures the infrastructure for phases 2-6, then rolls out to the pilot users to check for the end-to-end functionality. For example, pilot users get all of this functionality at the same time:</span></span>

- <span data-ttu-id="ee3af-237">A MFA e outros recursos de identidade (Identidade)</span><span class="sxs-lookup"><span data-stu-id="ee3af-237">MFA and other identity features (Identity)</span></span>
- <span data-ttu-id="ee3af-238">O Windows 10 Enterprise em dispositivos Windows (Windows 10 Enterprise)</span><span class="sxs-lookup"><span data-stu-id="ee3af-238">Windows 10 Enterprise on Windows devices (Windows 10 Enterprise)</span></span>
- <span data-ttu-id="ee3af-239">O Office 365 ProPlus para o pacote do Office (Office 365 ProPlus)</span><span class="sxs-lookup"><span data-stu-id="ee3af-239">Office 365 ProPlus for the Office suite (Office 365 ProPlus)</span></span>
- <span data-ttu-id="ee3af-240">Políticas de acesso condicional e a aplicativos (Gerenciamento de dispositivos móveis)</span><span class="sxs-lookup"><span data-stu-id="ee3af-240">App and conditional access policies (Mobile device management)</span></span>
- <span data-ttu-id="ee3af-241">Instalação do cliente de Proteção de Informações do Azure e treinamento sobre como aplicar rótulos a documentos. (Proteção de Informações)</span><span class="sxs-lookup"><span data-stu-id="ee3af-241">Azure Information Protection client installed and training on how to apply labels to documents (Information protection)</span></span>

<span data-ttu-id="ee3af-242">Após a conclusão do lançamento piloto, começa o lançamento para os usuários, em que cada usuário recebe todas as funcionalidades ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ee3af-242">Once the pilot rollout is concluded, the user rollout begins in which each user gets all the functionality the same time.</span></span>

## <a name="next-step"></a><span data-ttu-id="ee3af-243">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ee3af-243">Next step</span></span>

<span data-ttu-id="ee3af-244">Iniciar a implantação do Microsoft 365 Enterprise com a [infraestrutura de base](deploy-foundation-infrastructure.md).</span><span class="sxs-lookup"><span data-stu-id="ee3af-244">Start your deployment of Microsoft 365 Enterprise with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
