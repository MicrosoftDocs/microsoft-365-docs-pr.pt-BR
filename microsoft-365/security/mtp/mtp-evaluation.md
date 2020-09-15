---
title: Avaliar Proteção contra Ameaças da Microsoft
description: Configure seu laboratório de avaliação de proteção contra ameaças da Microsoft ou seu ambiente piloto para experimentar como a solução de proteção de ameaças coordenada projetada para proteger dispositivos, identidade, dados e aplicativos pode ajudar sua organização
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62852dfe75794d5d0e33453f978967fff40813e1
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816932"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="94b3a-104">Criar um laboratório de avaliação do Microsoft Threat Protection ou ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="94b3a-104">Create a Microsoft Threat Protection trial lab or pilot environment</span></span> 

<span data-ttu-id="94b3a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="94b3a-105">**Applies to:**</span></span>
- <span data-ttu-id="94b3a-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b3a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="94b3a-107">O objetivo de criar este laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes, integrados e inteligentes da proteção contra ameaças da Microsoft em detecção, prevenção, investigação e resposta que você pode usar em sua organização.</span><span class="sxs-lookup"><span data-stu-id="94b3a-107">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive, integrated, and intelligent capabilities of Microsoft Threat Protection in detection, prevention, investigation, and response that you can use in your organization.</span></span> 

<span data-ttu-id="94b3a-108">Este guia orienta as etapas para iniciar a avaliação de proteção contra ameaças da Microsoft com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="94b3a-108">This guide takes you through the steps to start your Microsoft Threat Protection evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="94b3a-109">O objetivo é ajudá-lo a configurar os serviços integrados de proteção contra ameaças da Microsoft em um ambiente de laboratório ao usar uma conta de avaliação ou em um ambiente piloto em produção ao usar uma licença completa.</span><span class="sxs-lookup"><span data-stu-id="94b3a-109">The goal is to help you set up the integrated Microsoft Threat Protection services in a lab environment when using a trial account, or in a pilot environment in production when using a full license.</span></span> <span data-ttu-id="94b3a-110">Os resultados do que serão úteis para a apresentação de casos de uso da operação de segurança para tomadores de decisões da solução de segurança em sua organização.</span><span class="sxs-lookup"><span data-stu-id="94b3a-110">The results of which will be useful in presenting security operation use cases to security solution decision makers in your organization.</span></span> <span data-ttu-id="94b3a-111">Quando você terminar de executar as simulações de ataque e estiver satisfeito com os resultados, você pode implantá-lo e operacionalá-lo em sua organização com a ajuda dos profissionais de vendas ou especialistas técnicos da Microsoft em sua organização.</span><span class="sxs-lookup"><span data-stu-id="94b3a-111">When you’re done running your attack simulations, and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="94b3a-112">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="94b3a-112">This guide will help you:</span></span>
- <span data-ttu-id="94b3a-113">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="94b3a-113">Set up your lab server and computers</span></span>
- <span data-ttu-id="94b3a-114">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="94b3a-114">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="94b3a-115">Configurar e configurar o Azure ATP, o Office ATP, o Microsoft defender ATP e o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="94b3a-115">Set up and configure Azure ATP, Office ATP, Microsoft Defender ATP, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="94b3a-116">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="94b3a-116">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="94b3a-117">Imitar um ataque de ameaça para gerar um incidente de teste ou alerta na proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b3a-117">Mimic a threat attack to generate a test incident or alert in Microsoft Threat Protection</span></span>

>[!IMPORTANT]
><span data-ttu-id="94b3a-118">Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="94b3a-118">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="94b3a-119">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="94b3a-119">Deployment phases</span></span>

<span data-ttu-id="94b3a-120">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft Threat Protection e sua implantação:</span><span class="sxs-lookup"><span data-stu-id="94b3a-120">There are three phases in creating a Microsoft Threat Protection trial lab environment and deploying it:</span></span>

|<span data-ttu-id="94b3a-121">Fase</span><span class="sxs-lookup"><span data-stu-id="94b3a-121">Phase</span></span> | <span data-ttu-id="94b3a-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="94b3a-122">Description</span></span> | 
|:-------|:-----|
| <span data-ttu-id="94b3a-123">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="94b3a-123">![Phase 1: Prepare](../../media/prepare.png)</span></span><br>[<span data-ttu-id="94b3a-124">Fase 1: preparar</span><span class="sxs-lookup"><span data-stu-id="94b3a-124">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="94b3a-125">Saiba o que você precisa considerar ao implantar a proteção contra ameaças da Microsoft em um laboratório de avaliação ou ambiente piloto:</span><span class="sxs-lookup"><span data-stu-id="94b3a-125">Learn what you need to consider when deploying Microsoft Threat Protection in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="94b3a-126">– Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="94b3a-126">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="94b3a-127">-Considerações de ambiente</span><span class="sxs-lookup"><span data-stu-id="94b3a-127">- Environment considerations</span></span> <br><span data-ttu-id="94b3a-128">– Acesso</span><span class="sxs-lookup"><span data-stu-id="94b3a-128">- Access</span></span> <br><span data-ttu-id="94b3a-129">-Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="94b3a-129">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="94b3a-130">-Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="94b3a-130">- Configuration order</span></span>
|  <span data-ttu-id="94b3a-131">![Fase 2: configuração](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="94b3a-131">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="94b3a-132">Fase 2: configuração</span><span class="sxs-lookup"><span data-stu-id="94b3a-132">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="94b3a-133">Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar seu laboratório de avaliação do Microsoft Threat Protection ou ambiente piloto.</span><span class="sxs-lookup"><span data-stu-id="94b3a-133">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft Threat Protection trial lab or pilot environment.</span></span> <span data-ttu-id="94b3a-134">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="94b3a-134">You'll be guided to:</span></span><br><br><span data-ttu-id="94b3a-135">-Inscrever-se no Microsoft 365 E5 Trial</span><span class="sxs-lookup"><span data-stu-id="94b3a-135">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="94b3a-136">-Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="94b3a-136">- Configure domain</span></span><br><span data-ttu-id="94b3a-137">-Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="94b3a-137">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="94b3a-138">– Concluir o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="94b3a-138">- Complete the setup wizard in the portal</span></span>|
|  <span data-ttu-id="94b3a-139">![Fase 3: configurar o & integrado](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="94b3a-139">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="94b3a-140">Fase 3: configurar o & integrado</span><span class="sxs-lookup"><span data-stu-id="94b3a-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="94b3a-141">Configure cada pilar de proteção contra ameaças e pontos de extremidade integrados da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="94b3a-141">Configure each Microsoft Threat Protection pillar and onboard endpoints.</span></span> <span data-ttu-id="94b3a-142">Você será orientado para:</span><span class="sxs-lookup"><span data-stu-id="94b3a-142">You'll be guided to:</span></span><br><br><span data-ttu-id="94b3a-143">– Configurar a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="94b3a-143">- Configure Office 365 Advanced Threat Protection</span></span><br><span data-ttu-id="94b3a-144">– Configurar o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="94b3a-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="94b3a-145">– Configurar a proteção avançada contra ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="94b3a-145">- Configure Azure Advanced Threat Protection</span></span><br><span data-ttu-id="94b3a-146">– Configurar a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="94b3a-146">- Configure Microsoft Defender Advanced Threat Protection</span></span> 


## <a name="in-scope"></a><span data-ttu-id="94b3a-147">No escopo</span><span class="sxs-lookup"><span data-stu-id="94b3a-147">In scope</span></span>

<span data-ttu-id="94b3a-148">As seguintes tarefas estão no escopo deste guia:</span><span class="sxs-lookup"><span data-stu-id="94b3a-148">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="94b3a-149">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="94b3a-149">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="94b3a-150">Configurar a proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b3a-150">Set up Microsoft Threat Protection</span></span>
    -   <span data-ttu-id="94b3a-151">Inscreva-se no Microsoft 365 E5 Trial ou use sua licença completa se estiver executando um piloto</span><span class="sxs-lookup"><span data-stu-id="94b3a-151">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="94b3a-152">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="94b3a-152">Configure domain</span></span>
    -   <span data-ttu-id="94b3a-153">Atribuir licenças do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="94b3a-153">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="94b3a-154">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="94b3a-154">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="94b3a-155">Configurar todos os pilares de proteção contra ameaças da Microsoft com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="94b3a-155">Configure all Microsoft Threat Protection pillars based on best practices</span></span>
    -   <span data-ttu-id="94b3a-156">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="94b3a-156">Office 365 Advanced Threat Protection</span></span>
    -   <span data-ttu-id="94b3a-157">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="94b3a-157">Azure Advanced Threat Protection</span></span>
    -   <span data-ttu-id="94b3a-158">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b3a-158">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="94b3a-159">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="94b3a-159">Microsoft Defender Advanced Threat Protection</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="94b3a-160">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="94b3a-160">Out of scope</span></span>

<span data-ttu-id="94b3a-161">Os itens a seguir estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="94b3a-161">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="94b3a-162">Configuração de soluções de terceiros que podem ser integradas à proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="94b3a-162">Configuration of third-party solutions that might integrate with Microsoft Threat Protection</span></span>
-   <span data-ttu-id="94b3a-163">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="94b3a-163">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="94b3a-164">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="94b3a-164">Next step</span></span>
<span data-ttu-id="94b3a-165">![Fase 1: preparar](../../media/prepare.png)</span><span class="sxs-lookup"><span data-stu-id="94b3a-165">![Phase 1: Prepare](../../media/prepare.png)</span></span> <br><span data-ttu-id="94b3a-166">[Fase 1: preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="94b3a-166">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="94b3a-167">Preparar o laboratório de avaliação de proteção contra ameaças da Microsoft ou o ambiente piloto</span><span class="sxs-lookup"><span data-stu-id="94b3a-167">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>
