---
title: Microsoft 365 Defender
description: Configurar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
keywords: Avaliação da Proteção contra Ameaças da Microsoft, experimente a Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft, laboratório de avaliação da Proteção contra Ameaças da Microsoft, piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930205"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="5e740-104">Criar um laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-104">Create a Microsoft 365 Defender trial lab or pilot environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5e740-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5e740-105">**Applies to:**</span></span>
- <span data-ttu-id="5e740-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="5e740-107">Este guia ajuda você a trabalhar na configuração de um ambiente de laboratório com usuários e grupos e, em seguida, orienta você na configuração dos recursos no Microsoft 365 Defender para que você possa imitar um ataque de ameaça e obter um resultado de avaliação significativo.</span><span class="sxs-lookup"><span data-stu-id="5e740-107">This guide helps you work across setting up a lab environment with users and groups, then guides you through the configuration of the capabilities in Microsoft 365 Defender so that you can mimic a threat attack and obtain a meaningful trial result.</span></span> 

<span data-ttu-id="5e740-108">O objetivo da criação deste laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5e740-108">The purpose of creating this trial lab or pilot environment is to illustrate the comprehensive and integrated Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="5e740-109">Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas à sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e740-109">Experience how this intelligent security solution detects, prevents, automatically investigates, and responds to advanced threats your organization.</span></span> 


<span data-ttu-id="5e740-110">Você será orientado pelas etapas para iniciar a avaliação do Microsoft 365 Defender com base nos caminhos de implantação recomendados.</span><span class="sxs-lookup"><span data-stu-id="5e740-110">You will be guided through the steps to start your Microsoft 365 Defender evaluation based on the recommended deployment paths.</span></span> <span data-ttu-id="5e740-111">O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa.</span><span class="sxs-lookup"><span data-stu-id="5e740-111">The goal is to help you set up the security solution either in a lab environment with a trial account, or in a pilot environment in production with a full license.</span></span> <span data-ttu-id="5e740-112">Preparar seu laboratório de avaliação ou ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisão em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e740-112">Preparing your trial lab or pilot environment can help you present security operation use cases to decision makers in your organization.</span></span> <span data-ttu-id="5e740-113">Quando terminar de executar suas simulações de ataque e estiver satisfeito com os resultados, você poderá implantá-la e operacionalizá-la totalmente em sua organização com a ajuda dos Profissionais de Vendas Técnicos da Microsoft ou de especialistas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5e740-113">When you’re done running your attack simulations and are satisfied with the results, you can fully deploy and operationalize it in your organization with the help of Microsoft Technical Sales Professionals or experts in your organization.</span></span> 

<span data-ttu-id="5e740-114">Este guia ajudará você a:</span><span class="sxs-lookup"><span data-stu-id="5e740-114">This guide will help you:</span></span>
- <span data-ttu-id="5e740-115">Configurar seu servidor de laboratório e computadores</span><span class="sxs-lookup"><span data-stu-id="5e740-115">Set up your lab server and computers</span></span>
- <span data-ttu-id="5e740-116">Configurar o Active Directory com usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="5e740-116">Configure Active Directory with users and groups</span></span>
- <span data-ttu-id="5e740-117">Configurar e configurar o Microsoft Defender para Identidade, o Microsoft Defender para Office 365, o Microsoft Defender para Ponto de Extremidade e o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5e740-117">Set up and configure Microsoft Defender for Identity, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, and Microsoft Cloud App Security</span></span>
- <span data-ttu-id="5e740-118">Configurar políticas locais para seu servidor e computadores</span><span class="sxs-lookup"><span data-stu-id="5e740-118">Set up local policies for your server and computers</span></span>
- <span data-ttu-id="5e740-119">Simular um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-119">Mimic a threat attack to generate a test incident or alert in Microsoft 365 Defender</span></span>

>[!IMPORTANT]
><span data-ttu-id="5e740-120">Para obter os melhores resultados, siga as instruções de configuração do laboratório o mais próximo possível.</span><span class="sxs-lookup"><span data-stu-id="5e740-120">For optimum results, follow the lab setup instructions as closely as possible.</span></span>


## <a name="deployment-phases"></a><span data-ttu-id="5e740-121">Fases de implantação</span><span class="sxs-lookup"><span data-stu-id="5e740-121">Deployment phases</span></span>

<span data-ttu-id="5e740-122">Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5e740-122">There are three phases in creating a Microsoft 365 Defender trial lab environment.</span></span>

![Fases de implantação: preparar, configurar, integração](../../media/evaluation-guide-phases.png)

|<span data-ttu-id="5e740-124">Fase</span><span class="sxs-lookup"><span data-stu-id="5e740-124">Phase</span></span> | <span data-ttu-id="5e740-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e740-125">Description</span></span> | 
|:-------|:-----|
|[<span data-ttu-id="5e740-126">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="5e740-126">Phase 1: Prepare</span></span>](prepare-mtpeval.md)| <span data-ttu-id="5e740-127">Saiba o que você precisa considerar ao implantar o Microsoft 365 Defender em um laboratório de avaliação ou ambiente piloto:</span><span class="sxs-lookup"><span data-stu-id="5e740-127">Learn what you need to consider when deploying Microsoft 365 Defender in a trial lab or pilot environment:</span></span> <br><br><span data-ttu-id="5e740-128">- Participantes e aprovação</span><span class="sxs-lookup"><span data-stu-id="5e740-128">- Stakeholders and sign-off</span></span> <br> <span data-ttu-id="5e740-129">- Considerações sobre o ambiente</span><span class="sxs-lookup"><span data-stu-id="5e740-129">- Environment considerations</span></span> <br><span data-ttu-id="5e740-130">- Acesso</span><span class="sxs-lookup"><span data-stu-id="5e740-130">- Access</span></span> <br><span data-ttu-id="5e740-131">- Configuração do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5e740-131">- Azure Active Directory setup</span></span> <br> <span data-ttu-id="5e740-132">- Ordem de configuração</span><span class="sxs-lookup"><span data-stu-id="5e740-132">- Configuration order</span></span>
|[<span data-ttu-id="5e740-133">Fase 2: Instalação</span><span class="sxs-lookup"><span data-stu-id="5e740-133">Phase 2: Setup</span></span>](setup-mtpeval.md)|  <span data-ttu-id="5e740-134">Tome as etapas iniciais para acessar a Central de Segurança do Microsoft 365 para configurar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5e740-134">Take the initial steps to access Microsoft 365 Security Center to set up your Microsoft 365 Defender trial lab or pilot environment.</span></span> <span data-ttu-id="5e740-135">Você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="5e740-135">You'll be guided to:</span></span><br><br><span data-ttu-id="5e740-136">- Inscreva-se na avaliação do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5e740-136">- Sign up for Microsoft 365 E5 Trial</span></span> <br>  <span data-ttu-id="5e740-137">- Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="5e740-137">- Configure domain</span></span><br><span data-ttu-id="5e740-138">- Atribuir licenças do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5e740-138">- Assign Microsoft 365 E5 licenses</span></span><br><span data-ttu-id="5e740-139">– Conclua o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="5e740-139">- Complete the setup wizard in the portal</span></span>|
|[<span data-ttu-id="5e740-140">Fase 3: Configurar o & Onboard</span><span class="sxs-lookup"><span data-stu-id="5e740-140">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="5e740-141">Configure cada pilar do Microsoft 365 Defender e pontos de extremidade de integração.</span><span class="sxs-lookup"><span data-stu-id="5e740-141">Configure each Microsoft 365 Defender pillar and onboard endpoints.</span></span> <span data-ttu-id="5e740-142">Você será orientado a:</span><span class="sxs-lookup"><span data-stu-id="5e740-142">You'll be guided to:</span></span><br><br><span data-ttu-id="5e740-143">- Configurar o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5e740-143">- Configure Microsoft Defender for Office 365</span></span><br><span data-ttu-id="5e740-144">- Configurar o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5e740-144">- Configure Microsoft Cloud App Security</span></span><br><span data-ttu-id="5e740-145">- Configurar o Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="5e740-145">- Configure Microsoft Defender for Identity</span></span><br><span data-ttu-id="5e740-146">- Configurar o Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5e740-146">- Configure Microsoft Defender for Endpoint</span></span>


<span data-ttu-id="5e740-147">Depois de concluir este guia, você teria identificado as partes envolvidas e as aprovações necessárias, ter as permissões de acesso corretas, se inscreveu para avaliação, configurar domínios e cada um dos pilares do Microsoft 365 Defender, e seus pontos de extremidade serão integrados ao serviço.</span><span class="sxs-lookup"><span data-stu-id="5e740-147">After you've completed this guide, you would have identified the stakeholders involved and the required approvals,  have the right access permissions, signed up for trial, configured domains and each of the Microsoft 365 Defender pillars, and your endpoints will be onboarded to the service.</span></span>

## <a name="key-capabilities"></a><span data-ttu-id="5e740-148">Principais recursos</span><span class="sxs-lookup"><span data-stu-id="5e740-148">Key capabilities</span></span>

<span data-ttu-id="5e740-149">Embora o Microsoft 365 Defender fornece muitos recursos, o objetivo principal deste guia de implantação é começar a trabalhar com dispositivos de integração.</span><span class="sxs-lookup"><span data-stu-id="5e740-149">While Microsoft 365 Defender provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="5e740-150">Além da integração, essas diretrizes orientam você começa com os seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="5e740-150">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>


<span data-ttu-id="5e740-151">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="5e740-151">Capability</span></span> | <span data-ttu-id="5e740-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e740-152">Description</span></span> 
:---|:---
<span data-ttu-id="5e740-153">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5e740-153">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="5e740-154">Ajuda a proteger toda a sua empresa do Office 365 contra ameaças atuais</span><span class="sxs-lookup"><span data-stu-id="5e740-154">Helps protect your entire Office 365 envrionment from today's threats</span></span>
<span data-ttu-id="5e740-155">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="5e740-155">Microsoft Defender for Identity</span></span> | <span data-ttu-id="5e740-156">Identifica e detecta ameaças em identidades comprometidas e ações internas mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="5e740-156">Identifies and detects  threats on compromised identities and malicious insider actions.</span></span>
<span data-ttu-id="5e740-157">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5e740-157">Microsoft Cloud App Security</span></span> | <span data-ttu-id="5e740-158">Fornece visibilidade rica, controle o deslocamento de dados e detecte ameaças cibernéticas em serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5e740-158">Provides rich visibility, control data travel, and detect cyberthreats across cloud services.</span></span>
<span data-ttu-id="5e740-159">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5e740-159">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="5e740-160">Impede, detecta e fornece recursos de resposta a ameaças avançadas com segurança abrangente do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5e740-160">Prevents, detects, and provides response capabilities to advanced threats with comprehensive endpoint security.</span></span>


## <a name="in-scope"></a><span data-ttu-id="5e740-161">No escopo</span><span class="sxs-lookup"><span data-stu-id="5e740-161">In scope</span></span>

<span data-ttu-id="5e740-162">As seguintes tarefas estão no escopo deste guia:</span><span class="sxs-lookup"><span data-stu-id="5e740-162">The following tasks are in scope for this guide:</span></span>
-   <span data-ttu-id="5e740-163">Configurar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5e740-163">Set up Azure Active Directory</span></span>
-   <span data-ttu-id="5e740-164">Configurar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-164">Set up Microsoft 365 Defender</span></span>
    -   <span data-ttu-id="5e740-165">Inscreva-se na avaliação do Microsoft 365 E5 ou use sua licença completa se estiver executando um piloto</span><span class="sxs-lookup"><span data-stu-id="5e740-165">Sign up for Microsoft 365 E5 Trial or use your full license if you're running a pilot</span></span>
    -   <span data-ttu-id="5e740-166">Configurar domínio</span><span class="sxs-lookup"><span data-stu-id="5e740-166">Configure domain</span></span>
    -   <span data-ttu-id="5e740-167">Atribuir licenças do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5e740-167">Assign Microsoft 365 E5 licenses</span></span>
    -   <span data-ttu-id="5e740-168">Concluindo o assistente de configuração no portal</span><span class="sxs-lookup"><span data-stu-id="5e740-168">Completing the setup wizard within the portal</span></span>
-   <span data-ttu-id="5e740-169">Configurar todos os pilares do Microsoft 365 Defender com base nas práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="5e740-169">Configure all Microsoft 365 Defender pillars based on best practices</span></span>
    -   <span data-ttu-id="5e740-170">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5e740-170">Microsoft Defender for Office 365</span></span>
    -   <span data-ttu-id="5e740-171">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="5e740-171">Microsoft Defender for Identity</span></span>
    -   <span data-ttu-id="5e740-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5e740-172">Microsoft Cloud App Security</span></span>
    -   <span data-ttu-id="5e740-173">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5e740-173">Microsoft Defender for Endpoint</span></span>

## <a name="out-of-scope"></a><span data-ttu-id="5e740-174">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="5e740-174">Out of scope</span></span>

<span data-ttu-id="5e740-175">Os seguintes estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="5e740-175">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="5e740-176">Configuração de soluções de terceiros que podem se integrar ao Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-176">Configuration of third-party solutions that might integrate with Microsoft 365 Defender</span></span>
-   <span data-ttu-id="5e740-177">Teste de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="5e740-177">Penetration testing in production environment</span></span>

## <a name="next-step"></a><span data-ttu-id="5e740-178">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5e740-178">Next step</span></span>
<span data-ttu-id="5e740-179">[Fase 1: Preparar](prepare-mtpeval.md) 
</span><span class="sxs-lookup"><span data-stu-id="5e740-179">[Phase 1: Prepare](prepare-mtpeval.md) 
</span></span><br> <span data-ttu-id="5e740-180">Preparar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e740-180">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>
