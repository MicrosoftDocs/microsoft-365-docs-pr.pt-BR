---
title: Proteção contra Ameaças (Windows 10)
description: O Microsoft Defender ATP é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta.
keywords: proteção contra ameaças, Microsoft Defender para Ponto de Extremidade, redução de superfície de ataque, proteção de próxima geração, detecção e resposta de ponto de extremidade, investigação e resposta automatizadas, especialistas em ameaças da Microsoft, Pontuação Segura da Microsoft para Dispositivos, busca avançada, busca de ameaças cibernéticas, proteção contra ameaças da Web
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 3db1517d87a47aae254d36cfb28f6c057830ef3e
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840989"
---
# <a name="threat-protection"></a><span data-ttu-id="155b1-104">Proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="155b1-104">Threat Protection</span></span>
<span data-ttu-id="155b1-105">[O Microsoft Defender ATP](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta.</span><span class="sxs-lookup"><span data-stu-id="155b1-105">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) is a unified platform for preventative protection, post-breach detection, automated investigation, and response.</span></span> <span data-ttu-id="155b1-106">O Defender for Endpoint protege os pontos de extremidade contra ameaças cibernéticas, detecta ataques avançados e violações de dados, automatiza incidentes de segurança e melhora a postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="155b1-106">Defender for Endpoint protects endpoints from cyber threats, detects advanced attacks and data breaches, automates security incidents, and improves security posture.</span></span>

> [!TIP]
> <span data-ttu-id="155b1-107">Permitir que seus usuários acessem serviços de nuvem e aplicativos locais com facilidade e habilitam recursos modernos de gerenciamento para todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="155b1-107">Enable your users to access cloud services and on-premises applications with ease and enable modern management capabilities for all devices.</span></span> <span data-ttu-id="155b1-108">Para obter mais informações, consulte [Secure your remote workforce](/enterprise-mobility-security/remote-work/).</span><span class="sxs-lookup"><span data-stu-id="155b1-108">For more information, see [Secure your remote workforce](/enterprise-mobility-security/remote-work/).</span></span> 

<center><h2><span data-ttu-id="155b1-109">Microsoft Defender para Ponto de Extremidade</center></span><span class="sxs-lookup"><span data-stu-id="155b1-109">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><span data-ttu-id="155b1-110"><b>Ameaças & Gerenciamento de Vulnerabilidades</b></center></a></span><span class="sxs-lookup"><span data-stu-id="155b1-110"><b>Threat & vulnerability management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><span data-ttu-id="155b1-111"><b>Redução de superfície de ataque</b></center></a></span><span class="sxs-lookup"><span data-stu-id="155b1-111"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <span data-ttu-id="155b1-112"><b>Proteção de última geração</b></a></center></span><span class="sxs-lookup"><span data-stu-id="155b1-112"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <span data-ttu-id="155b1-113"><b>Detecção e resposta do ponto de extremidade</b></a></center></span><span class="sxs-lookup"><span data-stu-id="155b1-113"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <span data-ttu-id="155b1-114"><b>Investigação e correção automatizadas</b></a></center></span><span class="sxs-lookup"><span data-stu-id="155b1-114"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <span data-ttu-id="155b1-115"><b>Especialistas em Ameaças da Microsoft</b></a></center></span><span class="sxs-lookup"><span data-stu-id="155b1-115"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="155b1-116">
<a href="#apis"><center><b>Configuração centralizada e administração, APIs</a></span><span class="sxs-lookup"><span data-stu-id="155b1-116">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="155b1-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span><span class="sxs-lookup"><span data-stu-id="155b1-117"><a href="#mtp"><center><b>Microsoft 365 Defender</a></span></span></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

<span data-ttu-id="155b1-118">**[Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-118">**[Threat & vulnerability management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="155b1-119">Esse recurso integrado usa uma abordagem baseada em risco que altera o jogo para a descoberta, priorização e correção de vulnerabilidades de ponto de extremidade e configurações in-loco.</span><span class="sxs-lookup"><span data-stu-id="155b1-119">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span>

- [<span data-ttu-id="155b1-120">Visão geral & Gerenciamento de Vulnerabilidades ameaças</span><span class="sxs-lookup"><span data-stu-id="155b1-120">Threat & vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="155b1-121">Introdução</span><span class="sxs-lookup"><span data-stu-id="155b1-121">Get started</span></span>](tvm-prerequisites.md)
- [<span data-ttu-id="155b1-122">Acessar sua postura de segurança</span><span class="sxs-lookup"><span data-stu-id="155b1-122">Access your security posture</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="155b1-123">Melhorar a postura de segurança e reduzir o risco</span><span class="sxs-lookup"><span data-stu-id="155b1-123">Improve your security posture and reduce risk</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="155b1-124">Entender as vulnerabilidades em seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="155b1-124">Understand vulnerabilities on your devices</span></span>](tvm-software-inventory.md)

<a name="asr"></a>

<span data-ttu-id="155b1-125">**[Redução de superfície de ataque](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-125">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="155b1-126">O conjunto de recursos de redução de superfície de ataque fornece a primeira linha de defesa na pilha.</span><span class="sxs-lookup"><span data-stu-id="155b1-126">The attack surface reduction set of capabilities provide the first line of defense in the stack.</span></span> <span data-ttu-id="155b1-127">Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, esse conjunto de recursos resistem a ataques e exploração.</span><span class="sxs-lookup"><span data-stu-id="155b1-127">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span>

- [<span data-ttu-id="155b1-128">Isolamento baseado em hardware</span><span class="sxs-lookup"><span data-stu-id="155b1-128">Hardware based isolation</span></span>](overview-hardware-based-isolation.md)
- [<span data-ttu-id="155b1-129">Controle da aplicação</span><span class="sxs-lookup"><span data-stu-id="155b1-129">Application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [<span data-ttu-id="155b1-130">Controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="155b1-130">Device control</span></span>](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [<span data-ttu-id="155b1-131">Proteção de exploração</span><span class="sxs-lookup"><span data-stu-id="155b1-131">Exploit protection</span></span>](exploit-protection.md)
- <span data-ttu-id="155b1-132">[Proteção de rede](network-protection.md), [proteção da Web](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="155b1-132">[Network protection](network-protection.md), [web protection](web-protection-overview.md)</span></span>
- [<span data-ttu-id="155b1-133">Acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="155b1-133">Controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="155b1-134">Firewall de rede</span><span class="sxs-lookup"><span data-stu-id="155b1-134">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [<span data-ttu-id="155b1-135">Regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="155b1-135">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

<a name="ngp"></a>

<span data-ttu-id="155b1-136">**[Proteção de próxima geração](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="155b1-136">**[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="155b1-137">Para reforçar ainda mais o perímetro de segurança da sua rede, o Microsoft Defender for Endpoint usa proteção de última geração projetada para capturar todos os tipos de ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="155b1-137">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

- [<span data-ttu-id="155b1-138">Monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="155b1-138">Behavior monitoring</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="155b1-139">Proteção baseada em nuvem</span><span class="sxs-lookup"><span data-stu-id="155b1-139">Cloud-based protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [<span data-ttu-id="155b1-140">Aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="155b1-140">Machine learning</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="155b1-141">Proteção de URL</span><span class="sxs-lookup"><span data-stu-id="155b1-141">URL Protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [<span data-ttu-id="155b1-142">Serviço de área desatendido automatizado</span><span class="sxs-lookup"><span data-stu-id="155b1-142">Automated sandbox service</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

<span data-ttu-id="155b1-143">**[Detecção de ponto de extremidade e resposta](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-143">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="155b1-144">Os recursos de detecção e resposta do ponto de extremidade são colocados para detectar, investigar e responder a tentativas de invasão e violações ativas.</span><span class="sxs-lookup"><span data-stu-id="155b1-144">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to intrusion attempts and active breaches.</span></span> <span data-ttu-id="155b1-145">Com a busca avançada, você tem uma ferramenta de busca de ameaças baseada em consulta que permite que seu usuário encontre violações de forma proativa e crie detecções personalizadas.</span><span class="sxs-lookup"><span data-stu-id="155b1-145">With Advanced hunting, you have a query-based threat-hunting tool that lets your proactively find breaches and create custom detections.</span></span>

- [<span data-ttu-id="155b1-146">Alertas</span><span class="sxs-lookup"><span data-stu-id="155b1-146">Alerts</span></span>](alerts-queue.md)
- [<span data-ttu-id="155b1-147">Dados de ponto de extremidade históricos</span><span class="sxs-lookup"><span data-stu-id="155b1-147">Historical endpoint data</span></span>](investigate-machines.md#timeline)
- [<span data-ttu-id="155b1-148">Orquestração de resposta</span><span class="sxs-lookup"><span data-stu-id="155b1-148">Response orchestration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [<span data-ttu-id="155b1-149">Coleção Forensic</span><span class="sxs-lookup"><span data-stu-id="155b1-149">Forensic collection</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [<span data-ttu-id="155b1-150">Inteligência contra ameaças</span><span class="sxs-lookup"><span data-stu-id="155b1-150">Threat intelligence</span></span>](threat-indicator-concepts.md)
- [<span data-ttu-id="155b1-151">Serviço avançado de detonação e análise</span><span class="sxs-lookup"><span data-stu-id="155b1-151">Advanced detonation and analysis service</span></span>](respond-file-alerts.md#deep-analysis)
- [<span data-ttu-id="155b1-152">Busca avançada</span><span class="sxs-lookup"><span data-stu-id="155b1-152">Advanced hunting</span></span>](advanced-hunting-overview.md)
    - [<span data-ttu-id="155b1-153">Detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="155b1-153">Custom detections</span></span>](overview-custom-detections.md)

<a name="ai"></a>

<span data-ttu-id="155b1-154">**[Investigação e correção automatizadas](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-154">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="155b1-155">Além de responder rapidamente a ataques avançados, o Microsoft Defender for Endpoint oferece recursos automáticos de investigação e correção que ajudam a reduzir o volume de alertas em minutos em escala.</span><span class="sxs-lookup"><span data-stu-id="155b1-155">In addition to quickly responding to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span>

- [<span data-ttu-id="155b1-156">Investigação e correção automatizadas</span><span class="sxs-lookup"><span data-stu-id="155b1-156">Automated investigation and remediation</span></span>](automated-investigations.md)
- [<span data-ttu-id="155b1-157">Exibir detalhes e resultados das investigações automatizadas</span><span class="sxs-lookup"><span data-stu-id="155b1-157">View details and results of automated investigations</span></span>](auto-investigation-action-center.md)
- [<span data-ttu-id="155b1-158">Exibir e aprovar ações de correção</span><span class="sxs-lookup"><span data-stu-id="155b1-158">View and approve remediation actions</span></span>](manage-auto-investigation.md)

<a name="mte"></a>

<span data-ttu-id="155b1-159">**[Especialistas em Ameaças da Microsoft](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-159">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="155b1-160">O novo serviço de busca de ameaças gerenciadas do Microsoft Defender para Endpoint fornece busca proativa, priorização e contexto e insights adicionais.</span><span class="sxs-lookup"><span data-stu-id="155b1-160">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights.</span></span> <span data-ttu-id="155b1-161">Especialistas em Ameaças da Microsoft mais capacita os Centros de Operação de Segurança (SOCs) a identificar e responder a ameaças com rapidez e precisão.</span><span class="sxs-lookup"><span data-stu-id="155b1-161">Microsoft Threat Experts further empowers Security Operation Centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

- [<span data-ttu-id="155b1-162">Notificação de ataque direcionada</span><span class="sxs-lookup"><span data-stu-id="155b1-162">Targeted attack notification</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="155b1-163">Especialistas sob demanda</span><span class="sxs-lookup"><span data-stu-id="155b1-163">Experts-on-demand</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="155b1-164">Configurar seu serviço Microsoft 365 de busca gerenciada do Defender</span><span class="sxs-lookup"><span data-stu-id="155b1-164">Configure your Microsoft 365 Defender managed hunting service</span></span>](configure-microsoft-threat-experts.md)

<a name="apis"></a>

<span data-ttu-id="155b1-165">**[Configuração centralizada e administração, APIs](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-165">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="155b1-166">Integre o Microsoft Defender para Ponto de Extremidade aos fluxos de trabalho existentes.</span><span class="sxs-lookup"><span data-stu-id="155b1-166">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>
- [<span data-ttu-id="155b1-167">Integração</span><span class="sxs-lookup"><span data-stu-id="155b1-167">Onboarding</span></span>](onboard-configure.md)
- [<span data-ttu-id="155b1-168">Integração de API e SIEM</span><span class="sxs-lookup"><span data-stu-id="155b1-168">API and SIEM integration</span></span>](configure-siem.md)
- [<span data-ttu-id="155b1-169">APIs expostas</span><span class="sxs-lookup"><span data-stu-id="155b1-169">Exposed APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="155b1-170">Controle de Acesso Baseado em Função (RBAC)</span><span class="sxs-lookup"><span data-stu-id="155b1-170">Role-based access control (RBAC)</span></span>](rbac.md)
- [<span data-ttu-id="155b1-171">Relatórios e tendências</span><span class="sxs-lookup"><span data-stu-id="155b1-171">Reporting and trends</span></span>](threat-protection-reports.md)

<a name="integration"></a>
<span data-ttu-id="155b1-172">**[Integração com soluções da Microsoft](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="155b1-172">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
 <span data-ttu-id="155b1-173">O Microsoft Defender para Ponto de Extremidade integra-se diretamente com várias soluções da Microsoft, incluindo:</span><span class="sxs-lookup"><span data-stu-id="155b1-173">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="155b1-174">Intune</span><span class="sxs-lookup"><span data-stu-id="155b1-174">Intune</span></span>
- <span data-ttu-id="155b1-175">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="155b1-175">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="155b1-176">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="155b1-176">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="155b1-177">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="155b1-177">Azure Defender</span></span>
- <span data-ttu-id="155b1-178">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="155b1-178">Skype for Business</span></span>
- <span data-ttu-id="155b1-179">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="155b1-179">Microsoft Cloud App Security</span></span>

<a name="mtp"></a>
<span data-ttu-id="155b1-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="155b1-180">**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
 <span data-ttu-id="155b1-181">Com o Microsoft 365 Defender, o Microsoft Defender para o Ponto de Extremidade e várias soluções de segurança da Microsoft formam um pacote unificado de defesa empresarial de pré e pós-violação que se integra na verdade ao ponto de extremidade, identidade, email e aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="155b1-181">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>
