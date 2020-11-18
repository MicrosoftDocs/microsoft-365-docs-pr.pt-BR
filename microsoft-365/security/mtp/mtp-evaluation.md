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
ms.openlocfilehash: fe0a06dd104f0f0532363ee046f4bad1c03c5400
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130871"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="e8cd8-104">Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="e8cd8-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e8cd8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e8cd8-105">**Applies to:**</span></span>
- <span data-ttu-id="e8cd8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8cd8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e8cd8-107">O objetivo de criar este laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="e8cd8-108">Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="e8cd8-109">Este guia orienta as etapas para iniciar sua avaliação do Microsoft 365 defender com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-109">This guide takes you through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="e8cd8-110">O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="e8cd8-111">Preparar o laboratório de avaliação ou o ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisões em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="e8cd8-112">Quando você terminar de executar as simulações de ataque e estiver satisfeito com os resultados, você pode implantá-lo e operacionalá-lo completamente em sua organização com a ajuda dos profissionais de vendas ou especialistas da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="e8cd8-113">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-113">This guide will help you:</span></span>
- <span data-ttu-id="e8cd8-114">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="e8cd8-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="e8cd8-115">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="e8cd8-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="e8cd8-116">Configurar e configurar o Microsoft defender para identidade, Microsoft defender para Office 365, Microsoft defender para ponto de extremidade e Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="e8cd8-116">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="e8cd8-117">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="e8cd8-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="e8cd8-118">Imitar um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8cd8-118">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="e8cd8-119">Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="e8cd8-120">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="e8cd8-120">Deployment phases</span></span>

<span data-ttu-id="e8cd8-121">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 defender e sua implantação:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-121">There are three phases in creating a Microsoft 365 Defender trial lab environment and deploying it:</span></span>

![Fases de implantação: preparação, configuração, integração](../../media/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="e8cd8-123">Fase</span><span class="sxs-lookup"><span data-stu-id="e8cd8-123">Phase</span></span> | <span data-ttu-id="e8cd8-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="e8cd8-124">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="e8cd8-125">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="e8cd8-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="e8cd8-126">Saiba o que você precisa considerar ao implantar o Microsoft 365 defender em um laboratório de avaliação ou ambiente piloto:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-126">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="e8cd8-127">– Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="e8cd8-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="e8cd8-128">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="e8cd8-128">- Environment considerations</span></span> <br><span data-ttu-id="e8cd8-129">– Acesso</span><span class="sxs-lookup"><span data-stu-id="e8cd8-129">- Access</span></span> <br><span data-ttu-id="e8cd8-130">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8cd8-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="e8cd8-131">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="e8cd8-131">- Configuration order</span></span>
|[<span data-ttu-id="e8cd8-132">Fase 2: configuração</span><span class="sxs-lookup"><span data-stu-id="e8cd8-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="e8cd8-133">Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="e8cd8-134">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-134">You'll be guided to:</span></span><br><br><span data-ttu-id="e8cd8-135">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="e8cd8-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="e8cd8-136">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="e8cd8-136">- Configure domain</span></span><br><span data-ttu-id="e8cd8-137">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="e8cd8-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="e8cd8-138">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="e8cd8-138">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="e8cd8-139">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="e8cd8-139">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="e8cd8-140">Configure cada Microsoft 365 defender pilar e pontos de extremidade integrados.</span><span class="sxs-lookup"><span data-stu-id="e8cd8-140">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="e8cd8-141">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-141">You'll be guided to:</span></span><br><br><span data-ttu-id="e8cd8-142">– Configurar o Microsoft defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8cd8-142">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="e8cd8-143">– Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="e8cd8-143">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="e8cd8-144">– Configurar o Microsoft defender para identidade</span><span class="sxs-lookup"><span data-stu-id="e8cd8-144">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="e8cd8-145">– Configurar o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e8cd8-145">- Configure Microsoft Defender for Endpoint</span></span>


## <a name="in-scope"></a><span data-ttu-id="e8cd8-146">No escopo</span><span class="sxs-lookup"><span data-stu-id="e8cd8-146">In scope</span></span>

<span data-ttu-id="e8cd8-147">As seguintes tarefas estão no escopo deste guia:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-147">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="e8cd8-148">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e8cd8-148">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="e8cd8-149">Configurar o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8cd8-149">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="e8cd8-150">Inscreva-se no Microsoft 365 E5 Trial ou use sua licença completa se estiver executando um piloto</span><span class="sxs-lookup"><span data-stu-id="e8cd8-150">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="e8cd8-151">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="e8cd8-151">Configure domain</span></span>
    -   <span data-ttu-id="e8cd8-152">Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="e8cd8-152">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="e8cd8-153">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="e8cd8-153">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="e8cd8-154">Configurar todos os pilares do Microsoft 365 defender com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="e8cd8-154">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="e8cd8-155">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e8cd8-155">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="e8cd8-156">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="e8cd8-156">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="e8cd8-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8cd8-157">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="e8cd8-158">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e8cd8-158">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="e8cd8-159">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="e8cd8-159">Out of scope</span></span>

<span data-ttu-id="e8cd8-160">Os itens a seguir estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="e8cd8-160">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="e8cd8-161">Configuração de soluções de terceiros que podem ser integradas ao Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="e8cd8-161">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="e8cd8-162">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="e8cd8-162">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="e8cd8-163">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e8cd8-163">Next step</span></span>
<span data-ttu-id="e8cd8-164">[Fase 1: preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="e8cd8-164">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="e8cd8-165">Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="e8cd8-165">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
