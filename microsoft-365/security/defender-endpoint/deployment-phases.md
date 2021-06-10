---
title: Fases da implementação
description: Saiba como implantar o Microsoft Defender para Ponto de Extremidade preparando, configurando e integrando pontos de extremidade para esse serviço
keywords: implantar, preparar, configurar, integração, fase, implantação, implantação, adoção, configuração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165160"
---
# <a name="deployment-phases"></a><span data-ttu-id="1a1fd-104">Fases da implementação</span><span class="sxs-lookup"><span data-stu-id="1a1fd-104">Deployment phases</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a1fd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1a1fd-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a1fd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1a1fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a1fd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a1fd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1a1fd-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1a1fd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a1fd-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1a1fd-110">Saiba como implantar o Microsoft Defender para o Ponto de Extremidade para que sua empresa possa aproveitar a proteção preventiva, a detecção pós-violação, a investigação automatizada e a resposta.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-110">Learn how to deploy Microsoft Defender for Endpoint so that your enterprise can take advantage of preventative protection, post-breach detection, automated investigation, and response.</span></span> 


<span data-ttu-id="1a1fd-111">Este guia ajuda você a trabalhar entre as partes interessadas para preparar seu ambiente e, em seguida, integrar dispositivos de forma metodista, mudando da avaliação para um piloto significativo, para a implantação completa.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-111">This guide helps you work across stakeholders to prepare your environment and then onboard devices in a methodical way, moving from evaluation, to a meaningful pilot, to full deployment.</span></span>

<span data-ttu-id="1a1fd-112">Cada seção corresponde a um artigo separado nesta solução.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-112">Each section corresponds to a separate article in this solution.</span></span>

![Imagem das fases de implantação com detalhes da tabela](images/deployment-guide-phases.png)


![Resumo das fases de implantação: preparar, configurar, integração](images/phase-diagrams/deployment-phases.png)

|<span data-ttu-id="1a1fd-115">Fase</span><span class="sxs-lookup"><span data-stu-id="1a1fd-115">Phase</span></span> | <span data-ttu-id="1a1fd-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a1fd-116">Description</span></span> | 
|:-------|:-----|
| [<span data-ttu-id="1a1fd-117">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-117">Phase 1: Prepare</span></span>](prepare-deployment.md)| <span data-ttu-id="1a1fd-118">Saiba mais sobre o que você precisa considerar ao implantar o Defender para o Ponto de Extremidade, como aprovações de participantes, considerações de ambiente, permissões de acesso e ordem de adoção de recursos.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-118">Learn about what you need to consider when deploying Defender for Endpoint such as stakeholder approvals, environment considerations, access permissions, and adoption order of capabilities.</span></span> 
| [<span data-ttu-id="1a1fd-119">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-119">Phase 2: Setup</span></span>](production-deployment.md)|  <span data-ttu-id="1a1fd-120">Receba orientações sobre as etapas iniciais necessárias para que você possa acessar o portal, como validar o licenciamento, concluir o assistente de instalação e a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-120">Get guidance on the initial steps you need to take so that you can access the portal such as validating licensing, completing the setup wizard, and network configuration.</span></span> 
| [<span data-ttu-id="1a1fd-121">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-121">Phase 3: Onboard</span></span>](onboarding.md) | <span data-ttu-id="1a1fd-122">Saiba como usar anéis de implantação, ferramentas de integração com suporte com base no tipo de ponto de extremidade e configurando os recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-122">Learn how to make use of deployment rings, supported onboarding tools based on the type of endpoint, and configuring available capabilities.</span></span> 


<span data-ttu-id="1a1fd-123">Depois de concluir este guia, você será configurado com as permissões de acesso corretas, seus pontos de extremidade serão integrados e os dados do sensor de relatório para o serviço, e recursos como proteção de próxima geração e redução de superfície de ataque estarão no local.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-123">After you've completed this guide, you'll be setup with the right access permissions, your endpoints will be onboarded and reporting sensor data to the service, and capabilities such as next-generation protection and attack surface reduction will be in place.</span></span>



<span data-ttu-id="1a1fd-124">Independentemente da arquitetura do ambiente e do [](deployment-strategy.md) método de implantação que você escolher descrito nas diretrizes de implantação do Plano, este guia irá dar suporte a você nos pontos de extremidade de integração.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-124">Regardless of the environment architecture and method of deployment you choose outlined in the [Plan deployment](deployment-strategy.md) guidance, this guide is going to support you in onboarding endpoints.</span></span> 








## <a name="key-capabilities"></a><span data-ttu-id="1a1fd-125">Principais recursos</span><span class="sxs-lookup"><span data-stu-id="1a1fd-125">Key capabilities</span></span>

<span data-ttu-id="1a1fd-126">Embora o Microsoft Defender para Ponto de Extremidade fornece muitos recursos, o principal objetivo deste guia de implantação é começar a trabalhar com dispositivos de integração.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-126">While Microsoft Defender for Endpoint provides many capabilities, the primary purpose of this deployment guide is to get you started by onboarding devices.</span></span> <span data-ttu-id="1a1fd-127">Além da integração, essas diretrizes são iniciadas com os seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-127">In addition to onboarding, this guidance gets you started with the following capabilities.</span></span>



<span data-ttu-id="1a1fd-128">Funcionalidade</span><span class="sxs-lookup"><span data-stu-id="1a1fd-128">Capability</span></span> | <span data-ttu-id="1a1fd-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a1fd-129">Description</span></span> 
:---|:---
<span data-ttu-id="1a1fd-130">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="1a1fd-130">Endpoint detection and response</span></span> | <span data-ttu-id="1a1fd-131">Os recursos de detecção e resposta do ponto de extremidade são colocados para detectar, investigar e responder a tentativas de invasão e violações ativas.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-131">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span>
<span data-ttu-id="1a1fd-132">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="1a1fd-132">Next-generation protection</span></span> | <span data-ttu-id="1a1fd-133">Para reforçar ainda mais o perímetro de segurança da sua rede, o Microsoft Defender for Endpoint usa proteção de última geração projetada para capturar todos os tipos de ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-133">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>
<span data-ttu-id="1a1fd-134">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="1a1fd-134">Attack surface reduction</span></span> |  <span data-ttu-id="1a1fd-135">Forneça a primeira linha de defesa na pilha.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-135">Provide the first line of defense in the stack.</span></span> <span data-ttu-id="1a1fd-136">Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, esse conjunto de recursos resistem a ataques e exploração.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-136">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

<span data-ttu-id="1a1fd-137">Todos esses recursos estão disponíveis para o Microsoft Defender para titulares de licença do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="1a1fd-137">All these capabilities are available for Microsoft Defender for Endpoint license holders.</span></span> <span data-ttu-id="1a1fd-138">Para obter mais informações, consulte [Requisitos de licenciamento](minimum-requirements.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="1a1fd-138">For more information, see [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

## <a name="scope"></a><span data-ttu-id="1a1fd-139">Escopo</span><span class="sxs-lookup"><span data-stu-id="1a1fd-139">Scope</span></span>

### <a name="in-scope"></a><span data-ttu-id="1a1fd-140">No escopo</span><span class="sxs-lookup"><span data-stu-id="1a1fd-140">In scope</span></span>

-   <span data-ttu-id="1a1fd-141">Uso de Microsoft Endpoint Manager e Microsoft Endpoint Manager para pontos de extremidade de integração no serviço e configurar recursos</span><span class="sxs-lookup"><span data-stu-id="1a1fd-141">Use of Microsoft Endpoint Manager and Microsoft Endpoint Manager to onboard endpoints into the service and configure capabilities</span></span>

-   <span data-ttu-id="1a1fd-142">Habilitando o Defender para detecção e resposta de ponto de extremidade (EDR)</span><span class="sxs-lookup"><span data-stu-id="1a1fd-142">Enabling Defender for Endpoint endpoint detection and response (EDR)  capabilities</span></span>

-   <span data-ttu-id="1a1fd-143">Habilitando os recursos da Plataforma de Proteção de Ponto de Extremidade (EPP) do Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1a1fd-143">Enabling Defender for Endpoint endpoint protection platform (EPP) capabilities</span></span>

    -   <span data-ttu-id="1a1fd-144">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="1a1fd-144">Next-generation protection</span></span>

    -   <span data-ttu-id="1a1fd-145">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="1a1fd-145">Attack surface reduction</span></span>


### <a name="out-of-scope"></a><span data-ttu-id="1a1fd-146">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="1a1fd-146">Out of scope</span></span>

<span data-ttu-id="1a1fd-147">Os seguintes estão fora do escopo deste guia de implantação:</span><span class="sxs-lookup"><span data-stu-id="1a1fd-147">The following are out of scope of this deployment guide:</span></span>

-   <span data-ttu-id="1a1fd-148">Configuração de soluções de terceiros que podem se integrar ao Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1a1fd-148">Configuration of third-party solutions that might integrate with Defender for Endpoint</span></span>

-   <span data-ttu-id="1a1fd-149">Testes de penetração no ambiente de produção</span><span class="sxs-lookup"><span data-stu-id="1a1fd-149">Penetration testing in production environment</span></span>




## <a name="see-also"></a><span data-ttu-id="1a1fd-150">Confira também</span><span class="sxs-lookup"><span data-stu-id="1a1fd-150">See also</span></span>
- [<span data-ttu-id="1a1fd-151">Fase 1: Preparar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-151">Phase 1: Prepare</span></span>](prepare-deployment.md)
- [<span data-ttu-id="1a1fd-152">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-152">Phase 2: Set up</span></span>](production-deployment.md)
- [<span data-ttu-id="1a1fd-153">Fase 3: Integrar</span><span class="sxs-lookup"><span data-stu-id="1a1fd-153">Phase 3: Onboard</span></span>](onboarding.md)
- [<span data-ttu-id="1a1fd-154">Planejar a implantação</span><span class="sxs-lookup"><span data-stu-id="1a1fd-154">Plan deployment</span></span>](deployment-strategy.md)