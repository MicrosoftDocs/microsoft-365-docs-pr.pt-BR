---
title: Avaliar Proteção contra Ameaças da Microsoft
description: Configure seu laboratório de avaliação de proteção contra ameaças da Microsoft ou seu ambiente piloto para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447114"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="461bd-104">Criar um laboratório de avaliação do Microsoft Threat Protection ou ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="461bd-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="461bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="461bd-105">**Applies to:**</span></span>
- <span data-ttu-id="461bd-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461bd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="461bd-107">O objetivo de criar este laboratório de avaliação ou ambiente piloto é ilustrar os recursos de proteção de ameaças abrangentes e integrados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="461bd-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="461bd-108">Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="461bd-108">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 

<span data-ttu-id="461bd-109">Este guia orienta as etapas para iniciar a avaliação de proteção contra ameaças da Microsoft com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="461bd-109">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="461bd-110">O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa.</span><span class="sxs-lookup"><span data-stu-id="461bd-110">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="461bd-111">Preparar o laboratório de avaliação ou o ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisões em sua organização.</span><span class="sxs-lookup"><span data-stu-id="461bd-111">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="461bd-112">Quando você terminar de executar as simulações de ataque e estiver satisfeito com os resultados, você pode implantá-lo e operacionalá-lo completamente em sua organização com a ajuda dos profissionais de vendas ou especialistas da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="461bd-112">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="461bd-113">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="461bd-113">This guide will help you:</span></span>
- <span data-ttu-id="461bd-114">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="461bd-114">Set up your lab server and computers</span></span>
- <span data-ttu-id="461bd-115">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="461bd-115">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="461bd-116">Configurar e configurar o Azure ATP, o Office ATP, o Microsoft defender ATP e o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="461bd-116">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="461bd-117">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="461bd-117">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="461bd-118">Imitar um ataque de ameaça para gerar um incidente de teste ou alerta na proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461bd-118">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="461bd-119">Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="461bd-119">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="461bd-120">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="461bd-120">Deployment phases</span></span>

<span data-ttu-id="461bd-121">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft Threat Protection e sua implantação:</span><span class="sxs-lookup"><span data-stu-id="461bd-121">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="461bd-122">Fase</span><span class="sxs-lookup"><span data-stu-id="461bd-122">Phase</span></span> | <span data-ttu-id="461bd-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="461bd-123">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="461bd-124">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="461bd-124">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="461bd-125">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="461bd-125">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="461bd-126">Saiba o que você precisa considerar ao implantar a proteção contra ameaças da Microsoft em um laboratório de avaliação ou ambiente piloto:</span><span class="sxs-lookup"><span data-stu-id="461bd-126">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="461bd-127">– Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="461bd-127">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="461bd-128">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="461bd-128">- Environment considerations</span></span> <br><span data-ttu-id="461bd-129">– Acesso</span><span class="sxs-lookup"><span data-stu-id="461bd-129">- Access</span></span> <br><span data-ttu-id="461bd-130">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="461bd-130">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="461bd-131">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="461bd-131">- Configuration order</span></span>
|  <span data-ttu-id="461bd-132">![Fase 2: configuração](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="461bd-132">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="461bd-133">Fase 2: configuração</span><span class="sxs-lookup"><span data-stu-id="461bd-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="461bd-134">Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar seu laboratório de avaliação do Microsoft Threat Protection ou ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="461bd-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="461bd-135">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="461bd-135">You'll be guided to:</span></span><br><br><span data-ttu-id="461bd-136">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="461bd-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="461bd-137">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="461bd-137">- Configure domain</span></span><br><span data-ttu-id="461bd-138">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="461bd-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="461bd-139">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="461bd-139">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="461bd-140">![Fase 3: configurar o & integrado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="461bd-140">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="461bd-141">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="461bd-141">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="461bd-142">Configure cada pilar de proteção contra ameaças e pontos de extremidade integrados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="461bd-142">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="461bd-143">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="461bd-143">You'll be guided to:</span></span><br><br><span data-ttu-id="461bd-144">– Configurar a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="461bd-144">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="461bd-145">– Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="461bd-145">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="461bd-146">– Configurar a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="461bd-146">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="461bd-147">– Configurar a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="461bd-147">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="461bd-148">No escopo</span><span class="sxs-lookup"><span data-stu-id="461bd-148">In scope</span></span>

<span data-ttu-id="461bd-149">As seguintes tarefas estão no escopo deste guia:</span><span class="sxs-lookup"><span data-stu-id="461bd-149">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="461bd-150">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="461bd-150">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="461bd-151">Configurar a proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461bd-151">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="461bd-152">Inscreva-se no Microsoft 365 E5 Trial ou use sua licença completa se estiver executando um piloto</span><span class="sxs-lookup"><span data-stu-id="461bd-152">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="461bd-153">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="461bd-153">Configure domain</span></span>
    -   <span data-ttu-id="461bd-154">Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="461bd-154">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="461bd-155">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="461bd-155">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="461bd-156">Configurar todos os pilares de proteção contra ameaças da Microsoft com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="461bd-156">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="461bd-157">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="461bd-157">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="461bd-158">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="461bd-158">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="461bd-159">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461bd-159">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="461bd-160">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="461bd-160">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="461bd-161">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="461bd-161">Out of scope</span></span>

<span data-ttu-id="461bd-162">Os itens a seguir estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="461bd-162">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="461bd-163">Configuração de soluções de terceiros que podem ser integradas à proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="461bd-163">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="461bd-164">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="461bd-164">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="461bd-165">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="461bd-165">Next step</span></span>
<span data-ttu-id="461bd-166">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="461bd-166">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="461bd-167">[Fase 1: preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="461bd-167">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="461bd-168">Preparar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="461bd-168">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
