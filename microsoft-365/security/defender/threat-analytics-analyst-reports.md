---
title: Compreender a seção relatório de analistas na análise de ameaças
ms.reviewer: ''
description: Saiba mais sobre a seção relatório de analistas de cada relatório de análise de ameaças. Entenda como ele fornece informações sobre ameaças, mitigações, detecções, consultas avançadas de busca e muito mais.
keywords: relatório de analista, análise de ameaças, detecções, consultas avançadas de busca, mitigações,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dc534b7bec27784ccf25f92ab0282fdbecdc9196
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054028"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a><span data-ttu-id="5e81c-105">Compreender o relatório do analista na análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="5e81c-105">Understand the analyst report in threat analytics</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5e81c-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5e81c-106">**Applies to:**</span></span>
- <span data-ttu-id="5e81c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e81c-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="5e81c-108">Deseja experimentar o Microsoft 365 Defender?</span><span class="sxs-lookup"><span data-stu-id="5e81c-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="5e81c-109">Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou executar seu projeto piloto em [produção](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="5e81c-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="5e81c-110">Cada [relatório de análise de ameaças](threat-analytics.md) inclui seções dinâmicas e uma seção por escrito abrangente chamada relatório de _analista._</span><span class="sxs-lookup"><span data-stu-id="5e81c-110">Each [threat analytics report](threat-analytics.md) includes dynamic sections and a comprehensive written section called the _analyst report_.</span></span> <span data-ttu-id="5e81c-111">Para acessar esta seção, abra o relatório sobre a ameaça controlada e selecione a **guia Relatório do** Analista.</span><span class="sxs-lookup"><span data-stu-id="5e81c-111">To access this section, open the report about the tracked threat and select the **Analyst report** tab.</span></span>

![Imagem da seção relatório do analista de um relatório de análise de ameaças](../../media/threat-analytics/ta_analystreport_mtp.png)

<span data-ttu-id="5e81c-113">_Seção relatório de analista de um relatório de análise de ameaças_</span><span class="sxs-lookup"><span data-stu-id="5e81c-113">_Analyst report section of a threat analytics report_</span></span>

## <a name="scan-the-analyst-report"></a><span data-ttu-id="5e81c-114">Examinar o relatório do analista</span><span class="sxs-lookup"><span data-stu-id="5e81c-114">Scan the analyst report</span></span> 
<span data-ttu-id="5e81c-115">Cada seção do relatório do analista foi projetada para fornecer informações a actionable.</span><span class="sxs-lookup"><span data-stu-id="5e81c-115">Each section of the analyst report is designed to provide actionable information.</span></span> <span data-ttu-id="5e81c-116">Embora os relatórios variem, a maioria dos relatórios inclui as seções descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5e81c-116">While reports vary, most reports include the sections described in the following table.</span></span>

| <span data-ttu-id="5e81c-117">Seção Relatório</span><span class="sxs-lookup"><span data-stu-id="5e81c-117">Report section</span></span> | <span data-ttu-id="5e81c-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="5e81c-118">Description</span></span> |
|--|--|
| <span data-ttu-id="5e81c-119">Resumo executivo</span><span class="sxs-lookup"><span data-stu-id="5e81c-119">Executive summary</span></span> | <span data-ttu-id="5e81c-120">Visão geral da ameaça, incluindo quando ela foi vista pela primeira vez, suas motivações, eventos notáveis, principais alvos e ferramentas e técnicas distintas.</span><span class="sxs-lookup"><span data-stu-id="5e81c-120">Overview of the threat, including when it was first seen, its motivations, notable events, major targets, and distinct tools and techniques.</span></span> <span data-ttu-id="5e81c-121">Você pode usar essas informações para avaliar ainda mais como priorizar a ameaça no contexto de sua indústria, localização geográfica e rede.</span><span class="sxs-lookup"><span data-stu-id="5e81c-121">You can use this information to further assess how to prioritize the threat in the context of your industry, geographic location, and network.</span></span> |
| <span data-ttu-id="5e81c-122">Análise</span><span class="sxs-lookup"><span data-stu-id="5e81c-122">Analysis</span></span> | <span data-ttu-id="5e81c-123">Informações técnicas sobre as ameaças, incluindo os detalhes de um ataque e como os invasores podem utilizar uma nova técnica ou superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="5e81c-123">Technical information about the threats, including the details of an attack and how attackers might utilize a new technique or attack surface</span></span> | 
| <span data-ttu-id="5e81c-124">Mitre ATT&técnicas de CK observadas</span><span class="sxs-lookup"><span data-stu-id="5e81c-124">MITRE ATT&CK techniques observed</span></span> | <span data-ttu-id="5e81c-125">Como as técnicas observadas mapeiam para o [MITRE ATT](https://attack.mitre.org/)&de ataque CK</span><span class="sxs-lookup"><span data-stu-id="5e81c-125">How observed techniques map to the [MITRE ATT&CK attack framework](https://attack.mitre.org/)</span></span> | 
| [<span data-ttu-id="5e81c-126">Mitigações</span><span class="sxs-lookup"><span data-stu-id="5e81c-126">Mitigations</span></span>](#apply-additional-mitigations) | <span data-ttu-id="5e81c-127">Recomendações que podem parar ou ajudar a reduzir o impacto da ameaça.</span><span class="sxs-lookup"><span data-stu-id="5e81c-127">Recommendations that can stop or help reduce the impact of the threat.</span></span> <span data-ttu-id="5e81c-128">Esta seção também inclui mitigações que não são rastreadas dinamicamente como parte do relatório de análise de ameaças.</span><span class="sxs-lookup"><span data-stu-id="5e81c-128">This section also includes mitigations that aren't tracked dynamically as part of the threat analytics report.</span></span> |
| [<span data-ttu-id="5e81c-129">Detalhes da detecção</span><span class="sxs-lookup"><span data-stu-id="5e81c-129">Detection details</span></span>](#understand-how-each-threat-can-be-detected) | <span data-ttu-id="5e81c-130">Detecções específicas e genéricas fornecidas pelas soluções de segurança da Microsoft que podem surgir atividade ou componentes associados à ameaça.</span><span class="sxs-lookup"><span data-stu-id="5e81c-130">Specific and generic detections provided by Microsoft security solutions that can surface activity or components associated with the threat.</span></span> | 
| [<span data-ttu-id="5e81c-131">Busca avançada</span><span class="sxs-lookup"><span data-stu-id="5e81c-131">Advanced hunting</span></span>](#find-subtle-threat-artifacts-using-advanced-hunting) | <span data-ttu-id="5e81c-132">[Consultas avançadas de busca](advanced-hunting-overview.md) para identificar proativamente as possíveis atividades de ameaça.</span><span class="sxs-lookup"><span data-stu-id="5e81c-132">[Advanced hunting queries](advanced-hunting-overview.md) for proactively identifying possible threat activity.</span></span> <span data-ttu-id="5e81c-133">A maioria das consultas é fornecida para complementar detecções, especialmente para localizar componentes ou comportamentos potencialmente mal-intencionados que não puderam ser avaliados dinamicamente como mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="5e81c-133">Most queries are provided to supplement detections, especially for locating potentially malicious components or behaviors that couldn't be dynamically assessed to be malicious.</span></span> | 
| <span data-ttu-id="5e81c-134">Referências</span><span class="sxs-lookup"><span data-stu-id="5e81c-134">References</span></span> | <span data-ttu-id="5e81c-135">Publicações da Microsoft e de terceiros referenciadas por analistas durante a criação do relatório.</span><span class="sxs-lookup"><span data-stu-id="5e81c-135">Microsoft and third-party publications referenced by analysts during the creation of the report.</span></span> <span data-ttu-id="5e81c-136">O conteúdo da análise de ameaças baseia-se nos dados validados pelos pesquisadores da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e81c-136">Threat analytics content is based on data validated by Microsoft researchers.</span></span> <span data-ttu-id="5e81c-137">As informações de fontes de terceiros disponíveis publicamente são identificadas claramente como tal.</span><span class="sxs-lookup"><span data-stu-id="5e81c-137">Information from publicly available, third-party sources are identified clearly as such.</span></span> | 
| <span data-ttu-id="5e81c-138">Log de mudanças</span><span class="sxs-lookup"><span data-stu-id="5e81c-138">Change log</span></span> | <span data-ttu-id="5e81c-139">A hora em que o relatório foi publicado e quando alterações significativas foram feitas no relatório.</span><span class="sxs-lookup"><span data-stu-id="5e81c-139">The time the report was published and when significant changes were made to the report.</span></span> |

## <a name="apply-additional-mitigations"></a><span data-ttu-id="5e81c-140">Aplicar mitigações adicionais</span><span class="sxs-lookup"><span data-stu-id="5e81c-140">Apply additional mitigations</span></span>
<span data-ttu-id="5e81c-141">A análise de ameaças rastreia [dinamicamente o status de atualizações de segurança e configurações seguras.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)</span><span class="sxs-lookup"><span data-stu-id="5e81c-141">Threat analytics dynamically tracks the [status of security updates and secure configurations](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices).</span></span> <span data-ttu-id="5e81c-142">Essas informações estão disponíveis como gráficos e tabelas na **guia Mitigações.**</span><span class="sxs-lookup"><span data-stu-id="5e81c-142">This information is available as charts and tables in the **Mitigations** tab.</span></span>

<span data-ttu-id="5e81c-143">Além dessas mitigações controladas, o relatório do analista também aborda mitigações que não _são_ monitoradas dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="5e81c-143">In addition to these tracked mitigations, the analyst report also discusses mitigations that are _not_ dynamically monitored.</span></span> <span data-ttu-id="5e81c-144">Aqui estão alguns exemplos de mitigações importantes que não são controladas dinamicamente:</span><span class="sxs-lookup"><span data-stu-id="5e81c-144">Here are some examples of important mitigations that are not dynamically tracked:</span></span>

- <span data-ttu-id="5e81c-145">Bloquear emails com _anexos .lnk_ ou outros tipos de arquivo suspeitos</span><span class="sxs-lookup"><span data-stu-id="5e81c-145">Block emails with _.lnk_ attachments or other suspicious file types</span></span>
- <span data-ttu-id="5e81c-146">Aleatoriamente senhas de administrador local</span><span class="sxs-lookup"><span data-stu-id="5e81c-146">Randomize local administrator passwords</span></span>
- <span data-ttu-id="5e81c-147">Instruir os usuários finais sobre phishing de email e outros vetores de ameaças</span><span class="sxs-lookup"><span data-stu-id="5e81c-147">Educate end users about phishing email and other threat vectors</span></span>
- <span data-ttu-id="5e81c-148">Ativar regras [específicas de redução de superfície de ataque](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)</span><span class="sxs-lookup"><span data-stu-id="5e81c-148">Turn on specific [attack surface reduction rules](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)</span></span>

<span data-ttu-id="5e81c-149">Embora você possa usar a guia **Mitigações** para avaliar sua postura de segurança contra uma ameaça, essas recomendações permitem que você tome medidas adicionais para melhorar sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="5e81c-149">While you can use the **Mitigations** tab to assess your security posture against a threat, these recommendations let you take additional steps towards improving your security posture.</span></span> <span data-ttu-id="5e81c-150">Leia cuidadosamente todas as diretrizes de mitigação no relatório do analista e aplique-as sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="5e81c-150">Carefully read all the mitigation guidance in the analyst report and apply them whenever possible.</span></span>

## <a name="understand-how-each-threat-can-be-detected"></a><span data-ttu-id="5e81c-151">Entender como cada ameaça pode ser detectada</span><span class="sxs-lookup"><span data-stu-id="5e81c-151">Understand how each threat can be detected</span></span>
<span data-ttu-id="5e81c-152">O relatório de analista também fornece as detecções do Microsoft Defender para recursos de detecção e resposta _de_ antivírus e ponto de extremidade (EDR).</span><span class="sxs-lookup"><span data-stu-id="5e81c-152">The analyst report also provides the detections from Microsoft Defender for Endpoint antivirus and _endpoint detection and response_ (EDR) capabilities.</span></span>

### <a name="antivirus-detections"></a><span data-ttu-id="5e81c-153">Detecções antivírus</span><span class="sxs-lookup"><span data-stu-id="5e81c-153">Antivirus detections</span></span>
<span data-ttu-id="5e81c-154">Essas detecções estão disponíveis em dispositivos com [o Microsoft Defender Antivírus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) ligado.</span><span class="sxs-lookup"><span data-stu-id="5e81c-154">These detections are available on devices with [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) turned on.</span></span> <span data-ttu-id="5e81c-155">Quando essas detecções ocorrem em dispositivos que foram integrados ao Microsoft Defender para Ponto de Extremidade, eles também disparam alertas que acendem os gráficos no relatório.</span><span class="sxs-lookup"><span data-stu-id="5e81c-155">When these detections occur on devices that have been onboarded to Microsoft Defender for Endpoint, they also trigger alerts that light up the charts in the report.</span></span>

>[!NOTE]
><span data-ttu-id="5e81c-156">O relatório do analista também lista detecções **genéricas** que podem identificar uma ampla variedade de ameaças, além de componentes ou comportamentos específicos da ameaça controlada.</span><span class="sxs-lookup"><span data-stu-id="5e81c-156">The analyst report also lists **generic detections** that can identify a wide-range of threats, in addition to components or behaviors specific to the tracked threat.</span></span> <span data-ttu-id="5e81c-157">Essas detecções genéricas não refletem nos gráficos.</span><span class="sxs-lookup"><span data-stu-id="5e81c-157">These generic detections don't reflect in the charts.</span></span>

### <a name="endpoint-detection-and-response-edr-alerts"></a><span data-ttu-id="5e81c-158">Alertas de detecção e resposta de ponto de extremidade (EDR)</span><span class="sxs-lookup"><span data-stu-id="5e81c-158">Endpoint detection and response (EDR) alerts</span></span>
<span data-ttu-id="5e81c-159">Alertas de EDR são gerados para [dispositivos conectados ao Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="5e81c-159">EDR alerts are raised for [devices onboarded to Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).</span></span> <span data-ttu-id="5e81c-160">Esses alertas geralmente dependem de sinais de segurança coletados pelo sensor do Microsoft Defender para Ponto de Extremidade e outros recursos de ponto de extremidade, como antivírus, proteção de rede, proteção contra adulteração, que servem como fontes de sinal poderosas.</span><span class="sxs-lookup"><span data-stu-id="5e81c-160">These alerts generally rely on security signals collected by the Microsoft Defender for Endpoint sensor and other endpoint capabilities—such as antivirus, network protection, tamper protection—that serve as powerful signal sources.</span></span>

<span data-ttu-id="5e81c-161">Como a lista de detecções de antivírus, alguns alertas de EDR são projetados para sinalizar genericamente comportamentos suspeitos que podem não estar associados à ameaça controlada.</span><span class="sxs-lookup"><span data-stu-id="5e81c-161">Like the list of antivirus detections, some EDR alerts are designed to generically flag suspicious behavior that might not be associated with the tracked threat.</span></span> <span data-ttu-id="5e81c-162">Nesses casos, o relatório identificará claramente o alerta como "genérico" e não influenciará nenhum dos gráficos no relatório.</span><span class="sxs-lookup"><span data-stu-id="5e81c-162">In such cases, the report will clearly identify the alert as "generic" and that it doesn't influence any of the charts in the report.</span></span>

### <a name="email-related-detections-and-mitigations"></a><span data-ttu-id="5e81c-163">Detecções e mitigações relacionadas a email</span><span class="sxs-lookup"><span data-stu-id="5e81c-163">Email-related detections and mitigations</span></span>
<span data-ttu-id="5e81c-164">As detecções e mitigações relacionadas a email do Microsoft Defender para Office 365 são incluídas em relatórios de analistas, além dos dados de ponto de extremidade já disponíveis do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5e81c-164">Email-related detections and mitigations from Microsoft Defender for Office 365, are included in analyst reports in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="5e81c-165">As informações de tentativa de email evitadas dão informações sobre se sua organização era um alvo da ameaça abordada no relatório do analista, mesmo que o ataque tenha sido efetivamente bloqueado antes da entrega ou entrega à pasta de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5e81c-165">Prevented email attempt information gives you insights on whether your organization were a target of the threat tackled in the analyst report even if the attack has been effectively blocked before delivery or delivered to the junk mail folder.</span></span>

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a><span data-ttu-id="5e81c-166">Encontrar artefatos de ameaças sutis usando a busca avançada</span><span class="sxs-lookup"><span data-stu-id="5e81c-166">Find subtle threat artifacts using advanced hunting</span></span>
<span data-ttu-id="5e81c-167">Embora as detecções permitam identificar e interromper a ameaça controlada automaticamente, muitas atividades de ataque deixam rastreamentos sutis que exigem inspeção adicional.</span><span class="sxs-lookup"><span data-stu-id="5e81c-167">While detections allow you to identify and stop the tracked threat automatically, many attack activities leave subtle traces that require additional inspection.</span></span> <span data-ttu-id="5e81c-168">Algumas atividades de ataque exibem comportamentos que também podem ser normais, portanto, detectá-los dinamicamente pode resultar em ruído operacional ou até mesmo falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="5e81c-168">Some attack activities exhibit behaviors that can also be normal, so detecting them dynamically can result in operational noise or even false positives.</span></span>

<span data-ttu-id="5e81c-169">[A busca avançada](advanced-hunting-overview.md) fornece uma interface de consulta com base no Idioma de Consulta kusto que simplifica a localização de indicadores sutis de atividade de ameaça.</span><span class="sxs-lookup"><span data-stu-id="5e81c-169">[Advanced hunting](advanced-hunting-overview.md) provides a query interface based on Kusto Query Language that simplifies locating subtle indicators of threat activity.</span></span> <span data-ttu-id="5e81c-170">Ele também permite que você superfície informações contextuais e verificar se os indicadores estão conectados a uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="5e81c-170">It also allows you to surface contextual information and verify whether indicators are connected to a threat.</span></span>

<span data-ttu-id="5e81c-171">Consultas de busca avançadas nos relatórios de analistas foram vetada por analistas da Microsoft e estão prontas para você executar no editor de consulta de [busca avançada.](https://security.microsoft.com/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="5e81c-171">Advanced hunting queries in the analyst reports have been vetted by Microsoft analysts and are ready for you to run in the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> <span data-ttu-id="5e81c-172">Você também pode usar as consultas para criar regras de detecção [personalizadas](custom-detection-rules.md) que disparam alertas para futuras combinações.</span><span class="sxs-lookup"><span data-stu-id="5e81c-172">You can also use the queries to create [custom detection rules](custom-detection-rules.md) that trigger alerts for future matches.</span></span>


>[!NOTE]
> <span data-ttu-id="5e81c-173">A análise de ameaças também está disponível no [Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="5e81c-173">Threat analytics is also available in [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics).</span></span> <span data-ttu-id="5e81c-174">No entanto, ele não tem a integração de dados entre o Microsoft Defender para Office e o Microsoft Defender para o Ponto de Extremidade que a análise de ameaças do Microsoft 365 Defender tem.</span><span class="sxs-lookup"><span data-stu-id="5e81c-174">However, it does not have the data integration between Microsoft Defender for Office and Microsoft Defender for Endpoint that Microsoft 365 Defender threat analytics has.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5e81c-175">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5e81c-175">Related topics</span></span>
- [<span data-ttu-id="5e81c-176">Visão geral de análise de ameaças</span><span class="sxs-lookup"><span data-stu-id="5e81c-176">Threat analytics overview</span></span>](threat-analytics.md)
- [<span data-ttu-id="5e81c-177">Encontrar proativamente ameaças com busca avançada</span><span class="sxs-lookup"><span data-stu-id="5e81c-177">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="5e81c-178">Regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="5e81c-178">Custom detection rules</span></span>](custom-detection-rules.md)