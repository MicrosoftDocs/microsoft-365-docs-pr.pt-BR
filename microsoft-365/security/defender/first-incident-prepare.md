---
title: Preparar sua postura de segurança para o primeiro incidente
description: Configurar a postura Microsoft 365 segurança do locatário para o primeiro incidente no Microsoft 365 Defender.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 76bead8fd855e4119db6297d2ab1a3d08d64a48c
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297159"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a><span data-ttu-id="66e3b-104">Preparar sua postura de segurança para o primeiro incidente</span><span class="sxs-lookup"><span data-stu-id="66e3b-104">Prepare your security posture for your first incident</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="66e3b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="66e3b-105">**Applies to:**</span></span>
- <span data-ttu-id="66e3b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="66e3b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="66e3b-107">A preparação para o tratamento de incidentes envolve a configuração de proteção suficiente da rede de uma organização contra diferentes tipos de incidentes de segurança.</span><span class="sxs-lookup"><span data-stu-id="66e3b-107">Preparing for incident handling involves setting up sufficient protection of an organization's network from different kinds of security incidents.</span></span> <span data-ttu-id="66e3b-108">Para reduzir o risco de incidentes de segurança, o Instituto Nacional de Padrões e Tecnologia (NIST) recomenda várias práticas de segurança, incluindo avaliações de risco, proteção da segurança do host, configuração de redes com segurança e prevenção de malware.</span><span class="sxs-lookup"><span data-stu-id="66e3b-108">To reduce the risk of security incidents, National Institute of Standards and Technology (NIST) recommends several security practices including risk assessments, hardening host security, configuring networks securely, and preventing malware.</span></span> 

<span data-ttu-id="66e3b-109">Microsoft 365 O Defender pode ajudar a resolver vários aspectos da prevenção de incidentes:</span><span class="sxs-lookup"><span data-stu-id="66e3b-109">Microsoft 365 Defender can help address several aspects of incident prevention:</span></span> 

- <span data-ttu-id="66e3b-110">Implementando uma [estrutura de Confiança](https://docs.microsoft.com/security/zero-trust/) Zero</span><span class="sxs-lookup"><span data-stu-id="66e3b-110">Implementing a [Zero Trust](https://docs.microsoft.com/security/zero-trust/) framework</span></span>
- <span data-ttu-id="66e3b-111">Determinando sua postura de segurança atribuindo uma pontuação com a [Pontuação Segura da Microsoft](microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="66e3b-111">Determining your security posture by assigning a score with [Microsoft Secure Score](microsoft-secure-score.md)</span></span>
- <span data-ttu-id="66e3b-112">Prevenção de ameaças por meio de avaliações de vulnerabilidade no [Gerenciamento de Ameaças e Vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="66e3b-112">Preventing threats through vulnerability assessments in [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="66e3b-113">Noções básicas sobre as ameaças de segurança mais recentes para que você possa se preparar para elas</span><span class="sxs-lookup"><span data-stu-id="66e3b-113">Understanding the latest security threats so you can prepare for them</span></span>

## <a name="step-1-implement-zero-trust"></a><span data-ttu-id="66e3b-114">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="66e3b-114">Step 1.</span></span> <span data-ttu-id="66e3b-115">Implementar Confiança Zero</span><span class="sxs-lookup"><span data-stu-id="66e3b-115">Implement Zero Trust</span></span>

<span data-ttu-id="66e3b-116">[A](https://docs.microsoft.com/security/zero-trust/) Confiança Zero é uma filosofia de segurança integrada e uma estratégia de ponta a ponta que considera a natureza complexa de qualquer ambiente moderno, incluindo a força de trabalho móvel e os usuários, dispositivos, aplicativos e dados, onde quer que estejam localizados.</span><span class="sxs-lookup"><span data-stu-id="66e3b-116">[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is an integrated security philosophy and end-to-end strategy that considers the complex nature of any modern environment, including the mobile workforce and the users, devices, applications and data, wherever they may be located.</span></span> <span data-ttu-id="66e3b-117">Ao fornecer um único painel de vidro para gerenciar todas as detecções de ponto de extremidade de forma [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) consistente, o Microsoft 365 Defender pode facilitar para a sua equipe de operações de segurança implementar os princípios de orientação da Confiança Zero.</span><span class="sxs-lookup"><span data-stu-id="66e3b-117">By providing a single pane of glass to manage all endpoint detections in a consistent way, Microsoft 365 Defender can make it easier for your security operations team to implement the [guiding principles](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) of Zero Trust.</span></span> 

<span data-ttu-id="66e3b-118">Os componentes do Microsoft 365 Defender podem exibir violações de regras implementadas para estabelecer políticas de Acesso Condicional para Confiança Zero integrando dados do Microsoft Defender para Ponto de Extremidade (MDE) ou outros fornecedores de segurança móvel como fonte de informações para políticas de conformidade de dispositivo e implementação de políticas de Acesso Condicional baseadas em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66e3b-118">Components of Microsoft 365 Defender can display violations of rules that have been implemented to establish Conditional Access policies for Zero Trust by integrating data from Microsoft Defender for Endpoint (MDE) or other mobile security vendors as an information source for device compliance policies and implementation of device-based Conditional Access policies.</span></span> 

<span data-ttu-id="66e3b-119">O risco do dispositivo influencia diretamente quais recursos serão acessíveis pelo usuário desse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66e3b-119">Device risk directly influences what resources will be accessible by the user of that device.</span></span> <span data-ttu-id="66e3b-120">A negação de acesso a recursos com base em determinados critérios é o tema principal do Zero Trust e Microsoft 365 Defender fornece informações necessárias para determinar os critérios de nível de confiança.</span><span class="sxs-lookup"><span data-stu-id="66e3b-120">The denial of access to resources based on certain criteria is the main theme of Zero Trust and Microsoft 365 Defender provides information needed to determine the trust level criteria.</span></span> <span data-ttu-id="66e3b-121">Por exemplo, o Microsoft 365 Defender pode fornecer o nível de versão de software de um dispositivo por meio da página Gerenciamento de Ameaças e Vulnerabilidades, enquanto as políticas de Acesso Condicional restringem dispositivos que têm versões desatualizadas ou vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="66e3b-121">For example, Microsoft 365 Defender can provide the software version level of a device through the Threat and Vulnerability Management page while Conditional Access policies restrict devices that have outdated or vulnerable versions.</span></span>

<span data-ttu-id="66e3b-122">A automação é uma parte crucial da implementação e manutenção de um ambiente de Confiança Zero, além de reduzir o número de alertas que potencialmente levariam a eventos de resposta a incidentes (IR).</span><span class="sxs-lookup"><span data-stu-id="66e3b-122">Automation is a crucial part of implementing and maintaining a Zero Trust environment while also reducing the number of alerts that would potentially lead to incident response (IR) events.</span></span> <span data-ttu-id="66e3b-123">Componentes do Microsoft 365 Defender podem ser [](m365d-autoir.md) automatizados, como ações de correção (conhecidas como investigações de um incidente no centro de segurança do Microsoft 365), ações de notificação e até mesmo a criação de tíquetes de suporte, como [em ServiceNow](https://microsoft.service-now.com/sp/).</span><span class="sxs-lookup"><span data-stu-id="66e3b-123">Components of Microsoft 365 Defender can be automated such as [remediation actions](m365d-autoir.md) (known as investigations for an incident in the Microsoft 365 security center), notification actions, and even the creation of support tickets such as in [ServiceNow](https://microsoft.service-now.com/sp/).</span></span>

## <a name="step-2-determine-your-organizations-security-posture"></a><span data-ttu-id="66e3b-124">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="66e3b-124">Step 2.</span></span> <span data-ttu-id="66e3b-125">Determinar a postura de segurança da sua organização</span><span class="sxs-lookup"><span data-stu-id="66e3b-125">Determine your organization’s security posture</span></span>

<span data-ttu-id="66e3b-126">Em seguida, as organizações podem usar o [Microsoft Secure Score](microsoft-secure-score.md) no Microsoft 365 Defender para determinar sua postura de segurança atual e considerar recomendações sobre como aprimora-la.</span><span class="sxs-lookup"><span data-stu-id="66e3b-126">Next, organizations can use the [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender to determine your current security posture and consider recommendations on how to improve it.</span></span> <span data-ttu-id="66e3b-127">Quanto maior a pontuação, mais recomendações de segurança e ações de melhoria foram tomadas pela organização.</span><span class="sxs-lookup"><span data-stu-id="66e3b-127">The higher the score is, the more security recommendations and improvement actions have been taken by the organization.</span></span> <span data-ttu-id="66e3b-128">As recomendações de Pontuação Segura podem ser tomadas em diferentes produtos e permitir que as organizações aumentem ainda mais suas pontuações.</span><span class="sxs-lookup"><span data-stu-id="66e3b-128">Secure Score recommendations can be taken across different products and allow organizations to raise their scores even higher.</span></span> 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Exemplo de Pontuação Segura da Microsoft no centro de segurança da Microsoft":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a><span data-ttu-id="66e3b-130">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="66e3b-130">Step 3.</span></span> <span data-ttu-id="66e3b-131">Avaliar a exposição de vulnerabilidade da sua organização</span><span class="sxs-lookup"><span data-stu-id="66e3b-131">Assess your organization’s vulnerability exposure</span></span>

<span data-ttu-id="66e3b-132">A prevenção de incidentes pode ajudar a simplificar os esforços de operações de segurança para se concentrar em ocorrências críticas e importantes de segurança.</span><span class="sxs-lookup"><span data-stu-id="66e3b-132">Preventing incidents can help streamline security operations efforts to focus on on-going critical and important security incidents.</span></span> <span data-ttu-id="66e3b-133">As vulnerabilidades de software geralmente são um ponto de entrada impedivel para ataques que podem levar a roubo de dados, perda de dados ou interrupção de operações comerciais.</span><span class="sxs-lookup"><span data-stu-id="66e3b-133">Software vulnerabilities are often a preventable entry point for attacks that can lead to data theft, data loss, or disruption of business operations.</span></span> <span data-ttu-id="66e3b-134">Se nenhum ataque estiver em funcionamento, as operações de segurança devem se esforçar para alcançar e manter um nível aceitável de exposição [de vulnerabilidade](../defender-endpoint/tvm-exposure-score.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="66e3b-134">If no attacks are on-going, security operations must strive to achieve and maintain an acceptable level of [vulnerability exposure](../defender-endpoint/tvm-exposure-score.md) in their organization.</span></span>

<span data-ttu-id="66e3b-135">Para verificar o progresso da [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) correção de software, visite a página Gerenciamento de Ameaças e Vulnerabilidades no Defender para Ponto de **Extremidade,** que você pode acessar do Microsoft 365 Defender por meio da guia Mais recursos.</span><span class="sxs-lookup"><span data-stu-id="66e3b-135">To check your software patching progress, visit the [Threat and Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) page in Defender for Endpoint, which you can access from Microsoft 365 Defender through the **More resources** tab.</span></span>

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Exemplo da página Ameaça e Vulnerabilidade no centro de segurança da Microsoft"::: 
 
## <a name="4-understand-emerging-threats"></a><span data-ttu-id="66e3b-137">4. Entenda as ameaças emergentes</span><span class="sxs-lookup"><span data-stu-id="66e3b-137">4. Understand emerging threats</span></span>

<span data-ttu-id="66e3b-138">Use [a análise de](threat-analytics.md) ameaças no Microsoft 365 de segurança para se manter atualizado com o cenário atual de ameaças à segurança.</span><span class="sxs-lookup"><span data-stu-id="66e3b-138">Use [threat analytics](threat-analytics.md) in the Microsoft 365 security center to keep up-to-date with the current security threat landscape.</span></span> <span data-ttu-id="66e3b-139">Especialistas em segurança da Microsoft criam relatórios que descrevem as ameaças cibernéticas mais recentes em detalhes para que você possa entender como elas podem afetar sua assinatura de Microsoft 365, dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="66e3b-139">Expert Microsoft security researchers create reports that describe the latest cyber-threats in detail so you can understand how they might affect your Microsoft 365 subscription, devices, and users.</span></span> <span data-ttu-id="66e3b-140">Esses relatórios podem incluir:</span><span class="sxs-lookup"><span data-stu-id="66e3b-140">These reports can include:</span></span>

- <span data-ttu-id="66e3b-141">Atores de ameaças ativos e suas campanhas</span><span class="sxs-lookup"><span data-stu-id="66e3b-141">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="66e3b-142">Técnicas de ataque populares e novas</span><span class="sxs-lookup"><span data-stu-id="66e3b-142">Popular and new attack techniques</span></span>
- <span data-ttu-id="66e3b-143">Vulnerabilidades críticas</span><span class="sxs-lookup"><span data-stu-id="66e3b-143">Critical vulnerabilities</span></span>
- <span data-ttu-id="66e3b-144">Superfícies de ataque comuns</span><span class="sxs-lookup"><span data-stu-id="66e3b-144">Common attack surfaces</span></span>
- <span data-ttu-id="66e3b-145">Malware predominante</span><span class="sxs-lookup"><span data-stu-id="66e3b-145">Prevalent malware</span></span>

<span data-ttu-id="66e3b-146">Você pode implementar as recomendações de uma ameaça emergente para fortalecer sua postura de segurança e minimizar sua área de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="66e3b-146">You can implement the recommendations of an emerging threat to strengthen your security posture and minimize your attack surface area.</span></span>

<span data-ttu-id="66e3b-147">Faça o tempo em sua agenda para verificar regularmente a seção [Análise](threat-analytics.md) de Ameaças do centro de Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="66e3b-147">Make time in your schedule to regularly check the [Threat Analytics](threat-analytics.md) section of the Microsoft 365 security center.</span></span>

## <a name="next-step"></a><span data-ttu-id="66e3b-148">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="66e3b-148">Next step</span></span>

<span data-ttu-id="66e3b-149">[![Etapa 1: Saiba como triagem e analisar incidentes](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="66e3b-149">[![Step 1: Learn how to triage and analyze incidents](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)</span></span>

<span data-ttu-id="66e3b-150">Saiba como [triagem e análise de incidentes.](first-incident-analyze.md)</span><span class="sxs-lookup"><span data-stu-id="66e3b-150">Learn how to [triage and analyze incidents](first-incident-analyze.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="66e3b-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="66e3b-151">See also</span></span>

- [<span data-ttu-id="66e3b-152">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="66e3b-152">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="66e3b-153">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="66e3b-153">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="66e3b-154">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="66e3b-154">Manage incidents</span></span>](manage-incidents.md)
