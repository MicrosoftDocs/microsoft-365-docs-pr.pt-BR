---
title: Avaliar o Microsoft 365 defender
description: Configure seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
keywords: Avaliação de proteção contra ameaças da Microsoft, experimente a proteção contra ameaças da Microsoft, avalie a proteção contra ameaças da Microsoft, laboratório de avaliação de proteção contra ameaças da Microsoft, piloto de proteção contra ameaças da Microsoft, segurança persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
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
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659625"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="e8a91-104">Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="e8a91-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e8a91-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e8a91-105">**Applies to:**</span></span>
- <span data-ttu-id="e8a91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8a91-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="e8a91-107">Este guia ajuda você a trabalhar com a configuração de um ambiente de laboratório com usuários e grupos e, em seguida, orienta você pela configuração dos recursos no Microsoft 365 defender para que você possa imitar um ataque de ameaça e obter um resultado de avaliação significativo.</span><span class="sxs-lookup"><span data-stu-id="e8a91-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="e8a91-108">O objetivo de criar este laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="e8a91-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="e8a91-109">Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8a91-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="e8a91-110">Você será orientado pelas etapas para iniciar sua avaliação do Microsoft 365 defender com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="e8a91-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="e8a91-111">O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa.</span><span class="sxs-lookup"><span data-stu-id="e8a91-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="e8a91-112">Preparar o laboratório de avaliação ou o ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisões em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8a91-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="e8a91-113">Quando você terminar de executar as simulações de ataque e estiver satisfeito com os resultados, você pode implantá-lo e operacionalá-lo completamente em sua organização com a ajuda dos profissionais de vendas ou especialistas da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8a91-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="e8a91-114">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="e8a91-114">This guide will help you:</span></span>
- <span data-ttu-id="e8a91-115">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="e8a91-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="e8a91-116">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="e8a91-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="e8a91-117">Configurar e configurar o Microsoft defender para identidade, Microsoft defender para Office 365, Microsoft defender para ponto de extremidade e Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="e8a91-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e8a91-118">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="e8a91-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="e8a91-119">Imitar um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8a91-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="e8a91-120">Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="e8a91-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="e8a91-121">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="e8a91-121">Deployment phases</span></span>

<span data-ttu-id="e8a91-122">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="e8a91-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fases de implantação: preparação, configuração, integração](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="e8a91-124">Fase</span><span class="sxs-lookup"><span data-stu-id="e8a91-124">Phase</span></span> | <span data-ttu-id="e8a91-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8a91-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="e8a91-126">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="e8a91-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="e8a91-127">Saiba o que você precisa considerar ao implantar o Microsoft 365 defender em um laboratório de avaliação ou ambiente piloto:</span><span class="sxs-lookup"><span data-stu-id="e8a91-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="e8a91-128">– Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="e8a91-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="e8a91-129">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="e8a91-129">- Environment considerations</span></span> <br><span data-ttu-id="e8a91-130">– Acesso</span><span class="sxs-lookup"><span data-stu-id="e8a91-130">- Access</span></span> <br><span data-ttu-id="e8a91-131">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8a91-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e8a91-132">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="e8a91-132">- Configuration order</span></span>
|[<span data-ttu-id="e8a91-133">Fase 2: configuração</span><span class="sxs-lookup"><span data-stu-id="e8a91-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="e8a91-134">Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="e8a91-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="e8a91-135">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="e8a91-135">You'll be guided to:</span></span><br><br><span data-ttu-id="e8a91-136">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="e8a91-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="e8a91-137">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="e8a91-137">- Configure domain</span></span><br><span data-ttu-id="e8a91-138">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="e8a91-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="e8a91-139">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="e8a91-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="e8a91-140">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="e8a91-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e8a91-141">Configure cada Microsoft 365 defender pilar e pontos de extremidade integrados.</span><span class="sxs-lookup"><span data-stu-id="e8a91-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="e8a91-142">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="e8a91-142">You'll be guided to:</span></span><br><br><span data-ttu-id="e8a91-143">– Configurar o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8a91-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="e8a91-144">– Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="e8a91-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="e8a91-145">– Configurar o Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="e8a91-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="e8a91-146">– Configurar o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e8a91-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="e8a91-147">Depois de concluir este guia, você teria identificado os participantes envolvidos e as aprovações necessárias, têm as permissões de acesso corretas, se inscreveram para os domínios de avaliação, configurados e cada um dos pilares do Microsoft 365 defender, e seus pontos de extremidade serão integrados ao serviço.</span><span class="sxs-lookup"><span data-stu-id="e8a91-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="e8a91-148">Principais recursos</span><span class="sxs-lookup"><span data-stu-id="e8a91-148">Key capabilities</span></span>

<span data-ttu-id="e8a91-149">Embora o Microsoft 365 defender forneça muitos recursos, o principal objetivo deste guia de implantação é começar a usar dispositivos de integração.</span><span class="sxs-lookup"><span data-stu-id="e8a91-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="e8a91-150">Além da integração, esta orientação é iniciada com os seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="e8a91-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="e8a91-151">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="e8a91-151">Capability</span></span> | <span data-ttu-id="e8a91-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8a91-152">Description</span></span> 
:---|:---
<span data-ttu-id="e8a91-153">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8a91-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="e8a91-154">Ajuda a proteger todo o Office 365 ambiente das ameaças atuais</span><span class="sxs-lookup"><span data-stu-id="e8a91-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="e8a91-155">O que é o Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="e8a91-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="e8a91-156">Identifica e detecta ameaças sobre identidades comprometidas e ações mal-intencionadas de insider.</span><span class="sxs-lookup"><span data-stu-id="e8a91-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="e8a91-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8a91-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="e8a91-158">Fornece visibilidade avançada, controlar dados de viagem e detectar ciberataques nos serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e8a91-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="e8a91-159">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e8a91-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="e8a91-160">Impede, detecta e fornece recursos de resposta a ameaças avançadas com segurança de ponto de extremidade abrangente.</span><span class="sxs-lookup"><span data-stu-id="e8a91-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="e8a91-161">No escopo</span><span class="sxs-lookup"><span data-stu-id="e8a91-161">In scope</span></span>

<span data-ttu-id="e8a91-162">As seguintes tarefas estão no escopo deste guia:</span><span class="sxs-lookup"><span data-stu-id="e8a91-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="e8a91-163">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8a91-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="e8a91-164">Configurar o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8a91-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="e8a91-165">Inscreva-se no Microsoft 365 E5 Trial ou use sua licença completa se estiver executando um piloto</span><span class="sxs-lookup"><span data-stu-id="e8a91-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="e8a91-166">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="e8a91-166">Configure domain</span></span>
    -   <span data-ttu-id="e8a91-167">Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="e8a91-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="e8a91-168">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="e8a91-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="e8a91-169">Configurar todos os pilares do Microsoft 365 defender com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="e8a91-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="e8a91-170">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8a91-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="e8a91-171">O que é o Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="e8a91-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="e8a91-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8a91-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="e8a91-173">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e8a91-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="e8a91-174">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="e8a91-174">Out of scope</span></span>

<span data-ttu-id="e8a91-175">Os itens a seguir estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="e8a91-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="e8a91-176">Configuração de soluções de terceiros que podem ser integradas ao Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8a91-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="e8a91-177">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="e8a91-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="e8a91-178">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e8a91-178">Next step</span></span>
<span data-ttu-id="e8a91-179">[Fase 1: preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="e8a91-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="e8a91-180">Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="e8a91-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
