---
title: Rastrear e responder a ameaças emergentes com a análise de ameaças do Microsoft Defender ATP
ms.reviewer: ''
description: Saiba mais sobre ameaças e técnicas de ataque emergentes e como impedi-las. Avalie o impacto deles em sua organização e avalie sua resiliência organizacional.
keywords: análise de ameaças, avaliação de risco, mitigação do sistema operacional, mitigação de microcódigo, status de mitigação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f532d20e4fb7cfa101eb6b96a89a4dbc4e658956
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054550"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="03504-105">Rastrear e responder a ameaças emergentes com análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="03504-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="03504-106">**Applies to:**</span></span>
- [<span data-ttu-id="03504-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="03504-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="03504-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03504-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="03504-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="03504-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="03504-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="03504-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="03504-111">Com adversários mais sofisticados e novas ameaças surgindo com frequência e predominantemente, é fundamental poder fazer isso rapidamente:</span><span class="sxs-lookup"><span data-stu-id="03504-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="03504-112">Avaliar o impacto de novas ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="03504-113">Revise sua resiliência contra ou exposição às ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="03504-114">Identificar as ações que você pode tomar para parar ou conter as ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="03504-115">Análise de ameaças é um conjunto de relatórios de pesquisadores de segurança especialistas da Microsoft que abrangem as ameaças mais relevantes, incluindo:</span><span class="sxs-lookup"><span data-stu-id="03504-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="03504-116">Atores de ameaças ativos e suas campanhas</span><span class="sxs-lookup"><span data-stu-id="03504-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="03504-117">Técnicas de ataque populares e novas</span><span class="sxs-lookup"><span data-stu-id="03504-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="03504-118">Vulnerabilidades críticas</span><span class="sxs-lookup"><span data-stu-id="03504-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="03504-119">Superfícies de ataque comuns</span><span class="sxs-lookup"><span data-stu-id="03504-119">Common attack surfaces</span></span>
- <span data-ttu-id="03504-120">Malware predominante</span><span class="sxs-lookup"><span data-stu-id="03504-120">Prevalent malware</span></span>

<span data-ttu-id="03504-121">Cada relatório fornece uma análise detalhada de uma ameaça e orientações abrangentes sobre como se defender contra essa ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="03504-122">Ele também incorpora dados de sua rede, indicando se a ameaça está ativa e se você tem proteções aplicáveis no local.</span><span class="sxs-lookup"><span data-stu-id="03504-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="03504-123">Assista a este breve vídeo para saber mais sobre como a análise de ameaças pode ajudá-lo a rastrear as ameaças mais recentes e impedi-las.</span><span class="sxs-lookup"><span data-stu-id="03504-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="03504-124">Exibir o painel de análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="03504-125">O painel de análise de ameaças é um ótimo ponto de partida para obter os relatórios mais relevantes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="03504-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="03504-126">Ele resume as ameaças nas seções a seguir:</span><span class="sxs-lookup"><span data-stu-id="03504-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="03504-127">**Ameaças mais** recentes lista os relatórios de ameaças publicados mais recentemente, juntamente com o número de dispositivos com alertas ativos e resolvidos.</span><span class="sxs-lookup"><span data-stu-id="03504-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="03504-128">**Ameaças de alto impacto** lista as ameaças que tiveram o maior impacto para a organização.</span><span class="sxs-lookup"><span data-stu-id="03504-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="03504-129">Esta seção classifica as ameaças pelo número de dispositivos que têm alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="03504-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="03504-130">**Resumo de** ameaças — mostra o impacto geral das ameaças controladas mostrando o número de ameaças com alertas ativos e resolvidos.</span><span class="sxs-lookup"><span data-stu-id="03504-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="03504-131">Selecione uma ameaça no painel para exibir o relatório dessa ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Imagem de um painel de análise de ameaças](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="03504-133">Exibir um relatório de análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="03504-133">View a threat analytics report</span></span>

<span data-ttu-id="03504-134">Cada relatório de análise de ameaças fornece informações em três seções: **Overview**, **Analyst report** e **Mitigations**.</span><span class="sxs-lookup"><span data-stu-id="03504-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="03504-135">Visão geral: entenda rapidamente a ameaça, avalie seu impacto e revise as defesas</span><span class="sxs-lookup"><span data-stu-id="03504-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="03504-136">A **seção Visão** Geral fornece uma visualização do relatório detalhado do analista.</span><span class="sxs-lookup"><span data-stu-id="03504-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="03504-137">Ele também fornece gráficos que realçam o impacto da ameaça à sua organização e sua exposição por meio de dispositivos não configurados e não configurados.</span><span class="sxs-lookup"><span data-stu-id="03504-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="03504-138">![Imagem da seção visão geral de um relatório de análise de ameaças ](images/ta-overview.png)
 _Visão geral de um relatório de análise de ameaças_</span><span class="sxs-lookup"><span data-stu-id="03504-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="03504-139">Avaliar o impacto para sua organização</span><span class="sxs-lookup"><span data-stu-id="03504-139">Assess the impact to your organization</span></span>
<span data-ttu-id="03504-140">Cada relatório inclui gráficos projetados para fornecer informações sobre o impacto organizacional de uma ameaça:</span><span class="sxs-lookup"><span data-stu-id="03504-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="03504-141">**Dispositivos com alertas** mostram o número atual de dispositivos distintos que foram afetados pela ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="03504-142">Um dispositivo será categorizado como **Ativo** se houver pelo menos um  alerta associado a essa ameaça e **Resolvido** se todos os alertas associados à ameaça no dispositivo foram resolvidos.</span><span class="sxs-lookup"><span data-stu-id="03504-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="03504-143">**Dispositivos com alertas ao** longo do tempo mostram o número de dispositivos distintos com alertas **ativos** e **resolvidos** ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="03504-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="03504-144">O número de alertas resolvidos indica a rapidez com que sua organização responde a alertas associados a uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="03504-145">Idealmente, o gráfico deve mostrar alertas resolvidos em alguns dias.</span><span class="sxs-lookup"><span data-stu-id="03504-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="03504-146">Revisar a resiliência e a postura de segurança</span><span class="sxs-lookup"><span data-stu-id="03504-146">Review security resilience and posture</span></span>
<span data-ttu-id="03504-147">Cada relatório inclui gráficos que fornecem uma visão geral de como sua organização é resiliente contra uma determinada ameaça:</span><span class="sxs-lookup"><span data-stu-id="03504-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="03504-148">**Status da configuração** de segurança mostra o número de dispositivos que aplicaram as configurações de segurança recomendadas que podem ajudar a reduzir a ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="03504-149">Os dispositivos são **considerados Seguros** se eles aplicaram _todas as_ configurações controladas.</span><span class="sxs-lookup"><span data-stu-id="03504-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="03504-150">**Status de patch de vulnerabilidade** mostra o número de dispositivos que aplicaram atualizações de segurança ou patches que abordam vulnerabilidades exploradas pela ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="03504-151">Relatório de analistas: obter informações de especialistas de pesquisadores de segurança da Microsoft</span><span class="sxs-lookup"><span data-stu-id="03504-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="03504-152">Vá até a **seção Relatório** de Analistas para ler o relatório detalhado do especialista.</span><span class="sxs-lookup"><span data-stu-id="03504-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="03504-153">A maioria dos relatórios fornece descrições detalhadas de cadeias de ataque, incluindo táticas e técnicas mapeadas para [](advanced-hunting-overview.md) a estrutura de CK do MITRE ATT&, listas exaustivas de recomendações e orientações avançadas sobre a busca de ameaças.</span><span class="sxs-lookup"><span data-stu-id="03504-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="03504-154">Saiba mais sobre o relatório do analista</span><span class="sxs-lookup"><span data-stu-id="03504-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="03504-155">Mitigações: revise a lista de mitigações e o status de seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="03504-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="03504-156">Na seção **Mitigações,** revise a lista de recomendações ativas específicas que podem ajudá-lo a aumentar sua resiliência organizacional em relação à ameaça.</span><span class="sxs-lookup"><span data-stu-id="03504-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="03504-157">A lista de mitigações controladas inclui:</span><span class="sxs-lookup"><span data-stu-id="03504-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="03504-158">**Atualizações de segurança**— implantação de atualizações de segurança ou patches para vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="03504-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="03504-159">**Configurações do Microsoft Defender Antivírus**</span><span class="sxs-lookup"><span data-stu-id="03504-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="03504-160">Versão de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="03504-160">Security intelligence version</span></span>
  - <span data-ttu-id="03504-161">Proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="03504-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="03504-162">Proteção de aplicativo potencialmente indesejado (PUA)</span><span class="sxs-lookup"><span data-stu-id="03504-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="03504-163">Proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="03504-163">Real-time protection</span></span>
 
<span data-ttu-id="03504-164">As informações de mitigação nesta seção incorporam dados do gerenciamento de ameaças e vulnerabilidades [,](next-gen-threat-and-vuln-mgt.md)que também fornece informações detalhadas de detalhamento de vários links no relatório.</span><span class="sxs-lookup"><span data-stu-id="03504-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="03504-165">![Imagem da seção mitigações de um relatório de análise de ameaças ](images/ta-mitigations.png)
 _Seção Mitigações de um relatório de análise de ameaças_</span><span class="sxs-lookup"><span data-stu-id="03504-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="03504-166">Detalhes e limitações adicionais do relatório</span><span class="sxs-lookup"><span data-stu-id="03504-166">Additional report details and limitations</span></span>
<span data-ttu-id="03504-167">Ao usar os relatórios, lembre-se do seguinte:</span><span class="sxs-lookup"><span data-stu-id="03504-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="03504-168">Os dados têm escopo com base no escopo do RBAC (controle de acesso baseado em função).</span><span class="sxs-lookup"><span data-stu-id="03504-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="03504-169">Você verá o status dos dispositivos em [grupos que você pode acessar](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="03504-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="03504-170">Os gráficos refletem apenas mitigações controladas.</span><span class="sxs-lookup"><span data-stu-id="03504-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="03504-171">Verifique a visão geral do relatório para obter mitigações adicionais que não são mostradas nos gráficos.</span><span class="sxs-lookup"><span data-stu-id="03504-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="03504-172">Mitigações não garantem resiliência completa.</span><span class="sxs-lookup"><span data-stu-id="03504-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="03504-173">As mitigações fornecidas refletem as melhores ações possíveis necessárias para melhorar a resiliência.</span><span class="sxs-lookup"><span data-stu-id="03504-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="03504-174">Os dispositivos serão contados como "indisponíveis" se não transmitirem dados para o serviço.</span><span class="sxs-lookup"><span data-stu-id="03504-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="03504-175">As estatísticas relacionadas ao antivírus são baseadas nas configurações do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="03504-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="03504-176">Dispositivos com soluções antivírus de terceiros podem aparecer como "expostos".</span><span class="sxs-lookup"><span data-stu-id="03504-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="03504-177">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="03504-177">Related topics</span></span>
- [<span data-ttu-id="03504-178">Encontrar proativamente ameaças com busca avançada</span><span class="sxs-lookup"><span data-stu-id="03504-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="03504-179">Compreender a seção relatório de analistas</span><span class="sxs-lookup"><span data-stu-id="03504-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="03504-180">Avaliar e resolver deficiências e exposições de segurança</span><span class="sxs-lookup"><span data-stu-id="03504-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)