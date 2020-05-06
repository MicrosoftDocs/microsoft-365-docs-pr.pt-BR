---
title: Avaliar a proteção contra ameaças da Microsoft
description: Configure seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft para experimentar como a solução de proteção de ameaças coordenada projetada para proteger dispositivos, identidade, dados e aplicativos pode ajudar sua organização
keywords: Avaliação de proteção contra ameaças da Microsoft, experimente a proteção contra ameaças da Microsoft, avaliar a proteção contra ameaças da Microsoft, laboratório de avaliação de proteção contra ameaças da Microsoft, segurança da CyberSource, ameaça persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049634"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="b2285-104">Criar um ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2285-104">Create a Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="b2285-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b2285-105">**Applies to:**</span></span>
- <span data-ttu-id="b2285-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2285-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="b2285-107">O objetivo de criar este ambiente de laboratório de avaliação é ilustrar os recursos abrangentes, integrados e inteligentes da proteção contra ameaças da Microsoft em detecção, prevenção, investigação e resposta que você pode usar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b2285-107">The purpose of creating this trial lab environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="b2285-108">Este guia orienta as etapas para iniciar a avaliação de proteção contra ameaças da Microsoft com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="b2285-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="b2285-109">O objetivo é ajudá-lo a configurar os serviços integrados de proteção contra ameaças da Microsoft em um ambiente de laboratório ou como uma verificação de conceito (VDC) ao apresentar aos tomadores de decisões da solução de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b2285-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment or as a proof of concept (POC) when presenting to security solution decision makers in your organization.</span></span> <span data-ttu-id="b2285-110">Quando você terminar de executar as simulações de ataque, investigação e resposta automatizadas e estiver satisfeito com os resultados, você pode implantá-lo em seu ambiente de produção com a ajuda dos profissionais de vendas técnicos ou especialistas da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b2285-110">When you’re done running your attack simulations, automated investigation and response, and are satisfied with the results, you can deploy it in your production environment with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="b2285-111">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="b2285-111">This guide will help you:</span></span>
- <span data-ttu-id="b2285-112">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="b2285-112">Set up your lab server and computers</span></span>
- <span data-ttu-id="b2285-113">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="b2285-113">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="b2285-114">Configurar e configurar o Azure ATP, o Office ATP, o Microsoft defender ATP e o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b2285-114">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="b2285-115">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="b2285-115">Setup local policies for your server and computers</span></span>
- <span data-ttu-id="b2285-116">Imitar um ataque de ameaça para gerar um incidente de teste ou alerta na proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2285-116">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="b2285-117">Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="b2285-117">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="b2285-118">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="b2285-118">Deployment phases</span></span>

<span data-ttu-id="b2285-119">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft Threat Protection e sua implantação:</span><span class="sxs-lookup"><span data-stu-id="b2285-119">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="b2285-120">Fase</span><span class="sxs-lookup"><span data-stu-id="b2285-120">Phase</span></span> | <span data-ttu-id="b2285-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="b2285-121">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="b2285-122">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b2285-122">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="b2285-123">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="b2285-123">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="b2285-124">Saiba o que você precisa considerar ao implantar a proteção contra ameaças da Microsoft em um ambiente de laboratório de avaliação:</span><span class="sxs-lookup"><span data-stu-id="b2285-124">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab environment:</span></span> <br><br><span data-ttu-id="b2285-125">– Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="b2285-125">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="b2285-126">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="b2285-126">- Environment considerations</span></span> <br><span data-ttu-id="b2285-127">– Acesso</span><span class="sxs-lookup"><span data-stu-id="b2285-127">- Access</span></span> <br><span data-ttu-id="b2285-128">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2285-128">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="b2285-129">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="b2285-129">- Configuration order</span></span>
|  <span data-ttu-id="b2285-130">![Fase 2: configuração](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b2285-130">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b2285-131">Fase 2: configuração</span><span class="sxs-lookup"><span data-stu-id="b2285-131">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="b2285-132">Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar seu ambiente de laboratório de avaliação do Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="b2285-132">Take the initial steps to access Microsoft 365 Security Center to setup your Microsoft Threat Protection trial lab environment.</span></span> <span data-ttu-id="b2285-133">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="b2285-133">You will be guided to:</span></span><br><br><span data-ttu-id="b2285-134">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="b2285-134">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="b2285-135">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="b2285-135">- Configure domain</span></span><br><span data-ttu-id="b2285-136">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="b2285-136">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="b2285-137">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="b2285-137">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="b2285-138">![Fase 3: configurar o & integrado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b2285-138">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="b2285-139">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="b2285-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="b2285-140">Configure cada pilar de proteção contra ameaças e pontos de extremidade integrados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2285-140">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="b2285-141">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="b2285-141">You will be guided to:</span></span><br><br><span data-ttu-id="b2285-142">– Configurar a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="b2285-142">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="b2285-143">– Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b2285-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="b2285-144">– Configurar a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="b2285-144">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="b2285-145">– Configurar a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="b2285-145">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="b2285-146">No escopo</span><span class="sxs-lookup"><span data-stu-id="b2285-146">In scope</span></span>

<span data-ttu-id="b2285-147">O seguinte é o escopo deste guia de ambiente de laboratório de avaliação:</span><span class="sxs-lookup"><span data-stu-id="b2285-147">The following is in scope for this trial lab environment guide:</span></span>
-   <span data-ttu-id="b2285-148">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2285-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="b2285-149">Configurar a proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2285-149">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="b2285-150">Inscreva-se na versão de avaliação do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="b2285-150">Sign up for Microsoft 365 E5 Trial</span></span>
    -   <span data-ttu-id="b2285-151">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="b2285-151">Configure domain</span></span>
    -   <span data-ttu-id="b2285-152">Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="b2285-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="b2285-153">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="b2285-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="b2285-154">Configurar todos os pilares de proteção contra ameaças da Microsoft com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="b2285-154">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="b2285-155">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="b2285-155">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b2285-156">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="b2285-156">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="b2285-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b2285-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="b2285-158">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b2285-158">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="b2285-159">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="b2285-159">Out of scope</span></span>

<span data-ttu-id="b2285-160">Os itens a seguir estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="b2285-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="b2285-161">Configuração de soluções de terceiros que podem ser integradas ao Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="b2285-161">Configuration of third-party solutions that might integrate with Microsoft Defender ATP</span></span>
-   <span data-ttu-id="b2285-162">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="b2285-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="b2285-163">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b2285-163">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="b2285-164">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="b2285-164">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br>[<span data-ttu-id="b2285-165">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="b2285-165">Phase 1: Prepare</span></span>](prepare-mtpeval.md) | <span data-ttu-id="b2285-166">Preparar seu ambiente de laboratório de avaliação de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b2285-166">Prepare your Microsoft Threat Protection evaluation lab environment</span></span>
