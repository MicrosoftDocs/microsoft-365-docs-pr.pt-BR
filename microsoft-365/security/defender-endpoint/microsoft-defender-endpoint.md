---
title: Microsoft Defender para Ponto de Extremidade
description: O Microsoft Defender for Endpoint é uma plataforma de segurança de ponto de extremidade empresarial que ajuda a se defender contra ameaças persistentes avançadas.
keywords: introdução ao Microsoft Defender para Ponto de Extremidade, introdução à Proteção Avançada contra Ameaças do Microsoft Defender, introdução ao Microsoft Defender ATP, segurança cibernética, ameaças persistentes avançadas, segurança corporativa, sensor comportamental de máquina, segurança na nuvem, análise, inteligência contra ameaças, redução de superfície de ataque, proteção de última geração, investigação e correção automatizadas, especialistas em ameaças da Microsoft, pontuação segura, busca avançada, proteção contra ameaças da Microsoft, busca de ameaças cibernéticas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 8c5d02a4d76ae7e031ad9f3af0db282cc4cb45ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187025"
---
# <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="f841f-104">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f841f-104">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f841f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f841f-105">**Applies to:**</span></span>
- [<span data-ttu-id="f841f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f841f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f841f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f841f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f841f-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f841f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f841f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f841f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> <span data-ttu-id="f841f-110">Para obter mais informações sobre recursos e funcionalidade do Windows 10 Enterprise Edition, consulte [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span><span class="sxs-lookup"><span data-stu-id="f841f-110">For more info about Windows 10 Enterprise Edition features and functionality, see [Windows 10 Enterprise edition](https://www.microsoft.com/WindowsForBusiness/buy).</span></span>

<span data-ttu-id="f841f-111">O Microsoft Defender for Endpoint é uma plataforma de segurança de ponto de extremidade empresarial projetada para ajudar as redes corporativas a evitar, detectar, investigar e responder a ameaças avançadas.</span><span class="sxs-lookup"><span data-stu-id="f841f-111">Microsoft Defender for Endpoint is an enterprise endpoint security platform designed to help enterprise networks prevent, detect, investigate, and respond to advanced threats.</span></span>
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

<span data-ttu-id="f841f-112">O Defender para Ponto de Extremidade usa a seguinte combinação de tecnologia criada no Windows 10 e no serviço de nuvem robusto da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="f841f-112">Defender for Endpoint uses the following combination of technology built into Windows 10 and Microsoft's robust cloud service:</span></span>

-   <span data-ttu-id="f841f-113">**Sensores comportamentais** de ponto de extremidade : incorporados no Windows 10, esses sensores coletam e processam sinais comportamentais do sistema operacional e enviam esses dados de sensor para sua instância privada, isolada e de nuvem do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f841f-113">**Endpoint behavioral sensors**: Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and send this sensor data to your private, isolated, cloud instance of Microsoft Defender for Endpoint.</span></span>


-   <span data-ttu-id="f841f-114">Análise de segurança na nuvem **:** aproveitando big-data, aprendizado de dispositivo e óptica exclusiva da Microsoft no ecossistema do Windows, produtos de nuvem empresarial (como o Office 365) e ativos online, sinais comportamentais são convertidos em insights, detecções e respostas recomendadas a ameaças avançadas.</span><span class="sxs-lookup"><span data-stu-id="f841f-114">**Cloud security analytics**: Leveraging big-data, device-learning, and unique Microsoft optics across the Windows ecosystem, enterprise cloud products (such as Office 365), and online assets, behavioral signals are translated into insights, detections, and recommended responses to advanced threats.</span></span>

-   <span data-ttu-id="f841f-115">**Inteligência** contra ameaças : gerada por caçadores da Microsoft, equipes de segurança e aumentadas pela inteligência contra ameaças fornecidas por parceiros, a inteligência contra ameaças permite que o Defender para o Ponto de Extremidade identifique ferramentas, técnicas e procedimentos do invasor e gere alertas quando eles são observados nos dados do sensor coletados.</span><span class="sxs-lookup"><span data-stu-id="f841f-115">**Threat intelligence**: Generated by Microsoft hunters, security teams, and augmented by threat intelligence provided by partners, threat intelligence enables Defender for Endpoint to identify attacker tools, techniques, and procedures, and generate alerts when they are observed in collected sensor data.</span></span>

<center><h2><span data-ttu-id="f841f-116">Microsoft Defender para Ponto de Extremidade</center></span><span class="sxs-lookup"><span data-stu-id="f841f-116">Microsoft Defender for Endpoint</center></span></span></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><span data-ttu-id="f841f-117"><b>Gerenciamento & de vulnerabilidades</b></center></a></span><span class="sxs-lookup"><span data-stu-id="f841f-117"><b>Threat & Vulnerability Management</b></center></a></span></span></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><span data-ttu-id="f841f-118"><b>Redução de superfície de ataque</b></center></a></span><span class="sxs-lookup"><span data-stu-id="f841f-118"><b>Attack surface reduction</b></center></a></span></span></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <span data-ttu-id="f841f-119"><b>Proteção de última geração</b></a></center></span><span class="sxs-lookup"><span data-stu-id="f841f-119"><b>Next-generation protection</b></a></center></span></span></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <span data-ttu-id="f841f-120"><b>Detecção e resposta do ponto de extremidade</b></a></center></span><span class="sxs-lookup"><span data-stu-id="f841f-120"><b>Endpoint detection and response</b></a></center></span></span></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <span data-ttu-id="f841f-121"><b>Investigação e correção automatizadas</b></a></center></span><span class="sxs-lookup"><span data-stu-id="f841f-121"><b>Automated investigation and remediation</b></a></center></span></span></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <span data-ttu-id="f841f-122"><b>Especialistas em ameaças da Microsoft</b></a></center></span><span class="sxs-lookup"><span data-stu-id="f841f-122"><b>Microsoft Threat Experts</b></a></center></span></span></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="f841f-123">
<a href="#apis"><center><b>Configuração centralizada e administração, APIs</a></span><span class="sxs-lookup"><span data-stu-id="f841f-123">
<a href="#apis"><center><b>Centralized configuration and administration, APIs</a></span></span></b></center></td>
</tr>
<tr>
<td colspan="7"><span data-ttu-id="f841f-124"><a href="#mtp"><center><b>Proteção contra Ameaças da Microsoft</a></span><span class="sxs-lookup"><span data-stu-id="f841f-124"><a href="#mtp"><center><b>Microsoft Threat Protection</a></span></span></center></b></td>
</tr>
</table>
<br>

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - <span data-ttu-id="f841f-125">Saiba mais sobre os aprimoramentos mais recentes no Defender para Ponto de Extremidade: Novidades [no Microsoft Defender para Ponto de Extremidade.](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="f841f-125">Learn about the latest enhancements in Defender for Endpoint: [What's new in Microsoft Defender for Endpoint](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
> - <span data-ttu-id="f841f-126">O Microsoft Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE.</span><span class="sxs-lookup"><span data-stu-id="f841f-126">Microsoft Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="f841f-127">Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="f841f-127">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<a name="tvm"></a>

<span data-ttu-id="f841f-128">**[Gerenciamento & de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-128">**[Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md)**</span></span><br>
<span data-ttu-id="f841f-129">Esse recurso integrado usa uma abordagem baseada em risco que altera o jogo para a descoberta, priorização e correção de vulnerabilidades de ponto de extremidade e configurações in-loco.</span><span class="sxs-lookup"><span data-stu-id="f841f-129">This built-in capability uses a game-changing risk-based approach to the discovery, prioritization, and remediation of endpoint vulnerabilities and misconfigurations.</span></span> 

<a name="asr"></a>

<span data-ttu-id="f841f-130">**[Redução da superfície do ataque.](overview-attack-surface-reduction.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-130">**[Attack surface reduction](overview-attack-surface-reduction.md)**</span></span><br>
<span data-ttu-id="f841f-131">O conjunto de recursos de redução de superfície de ataque fornece a primeira linha de defesa na pilha.</span><span class="sxs-lookup"><span data-stu-id="f841f-131">The attack surface reduction set of capabilities provides the first line of defense in the stack.</span></span> <span data-ttu-id="f841f-132">Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, os recursos resistem a ataques e exploração.</span><span class="sxs-lookup"><span data-stu-id="f841f-132">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, the capabilities resist attacks and exploitation.</span></span> <span data-ttu-id="f841f-133">Esse conjunto de recursos também inclui proteção de rede e [proteção da Web](web-protection-overview.md), que regulam o acesso a endereços IP mal-intencionados, domínios e URLs. [](network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f841f-133">This set of capabilities also includes [network protection](network-protection.md) and [web protection](web-protection-overview.md), which regulate access to malicious IP addresses, domains, and URLs.</span></span> 

<a name="ngp"></a>

<span data-ttu-id="f841f-134">**[Proteção de última geração](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span><span class="sxs-lookup"><span data-stu-id="f841f-134">**[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**</span></span><br>
<span data-ttu-id="f841f-135">Para reforçar ainda mais o perímetro de segurança da sua rede, o Microsoft Defender for Endpoint usa proteção de última geração projetada para capturar todos os tipos de ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="f841f-135">To further reinforce the security perimeter of your network, Microsoft Defender for Endpoint uses next-generation protection designed to catch all types of emerging threats.</span></span>

<a name="edr"></a>

<span data-ttu-id="f841f-136">**[Detecção e resposta do terminal.](overview-endpoint-detection-response.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-136">**[Endpoint detection and response](overview-endpoint-detection-response.md)**</span></span><br>
<span data-ttu-id="f841f-137">Os recursos de detecção e resposta do ponto de extremidade são colocados para detectar, investigar e responder a ameaças avançadas que podem ter passado dos dois primeiros pilares de segurança.</span><span class="sxs-lookup"><span data-stu-id="f841f-137">Endpoint detection and response capabilities are put in place to detect, investigate, and respond to advanced threats that may have made it past the first two security pillars.</span></span> <span data-ttu-id="f841f-138">[A busca avançada](advanced-hunting-overview.md) fornece uma ferramenta de busca de ameaças baseada em consulta que permite que você encontre violações e crie detecções personalizadas proativamente.</span><span class="sxs-lookup"><span data-stu-id="f841f-138">[Advanced hunting](advanced-hunting-overview.md) provides a query-based threat-hunting tool that lets you proactively find breaches and create custom detections.</span></span>

<a name="ai"></a>

<span data-ttu-id="f841f-139">**[Investigação e correção automatizadas](automated-investigations.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-139">**[Automated investigation and remediation](automated-investigations.md)**</span></span><br>
<span data-ttu-id="f841f-140">Em conjunto com a capacidade de responder rapidamente a ataques avançados, o Microsoft Defender for Endpoint oferece recursos automáticos de investigação e correção que ajudam a reduzir o volume de alertas em minutos em escala.</span><span class="sxs-lookup"><span data-stu-id="f841f-140">In conjunction with being able to quickly respond to advanced attacks, Microsoft Defender for Endpoint offers automatic investigation and remediation capabilities that help reduce the volume of alerts in minutes at scale.</span></span> 

<a name="ss"></a>

<span data-ttu-id="f841f-141">**[Pontuação segura da Microsoft para dispositivos](tvm-microsoft-secure-score-devices.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-141">**[Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md)**</span></span><br>

<span data-ttu-id="f841f-142">O Defender for Endpoint inclui a Pontuação Segura da Microsoft para Dispositivos para ajudá-lo a avaliar dinamicamente o estado de segurança da sua rede corporativa, identificar sistemas desprotegidos e a tomar ações recomendadas para melhorar a segurança geral da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f841f-142">Defender for Endpoint includes Microsoft Secure Score for Devices to help you dynamically assess the security state of your enterprise network, identify unprotected systems, and take recommended actions to improve the overall security of your organization.</span></span>

<a name="mte"></a>

<span data-ttu-id="f841f-143">**[Especialistas em ameaças da Microsoft](microsoft-threat-experts.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-143">**[Microsoft Threat Experts](microsoft-threat-experts.md)**</span></span><br>
<span data-ttu-id="f841f-144">O novo serviço gerenciado de busca de ameaças do Microsoft Defender for Endpoint fornece busca proativa, priorização e contexto adicional e percepções que capacitam ainda mais os Centros de Operação de Segurança (SOCs) a identificar e responder a ameaças de forma rápida e precisa.</span><span class="sxs-lookup"><span data-stu-id="f841f-144">Microsoft Defender for Endpoint's new managed threat hunting service provides proactive hunting, prioritization, and additional context and insights that further empower Security operation centers (SOCs) to identify and respond to threats quickly and accurately.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f841f-145">Os clientes do Defender para Ponto de Extremidade precisam solicitar o serviço de busca de ameaças gerenciado por especialistas em ameaças da Microsoft para obter notificações de ataque direcionadas proativas e colaborar com especialistas sob demanda.</span><span class="sxs-lookup"><span data-stu-id="f841f-145">Defender for Endpoint customers need to apply for the Microsoft Threat Experts managed threat hunting service to get proactive Targeted Attack Notifications and to collaborate with experts on demand.</span></span> <span data-ttu-id="f841f-146">Especialistas sob Demanda é um serviço de complemento.</span><span class="sxs-lookup"><span data-stu-id="f841f-146">Experts on Demand is an add-on service.</span></span> <span data-ttu-id="f841f-147">Notificações de ataque direcionadas são sempre incluídas depois que você foi aceito no serviço de busca de ameaças gerenciado por especialistas em ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f841f-147">Targeted Attack Notifications are always included after you have been accepted into Microsoft Threat Experts managed threat hunting service.</span></span><p>
><p><span data-ttu-id="f841f-148">Se você ainda não estiver inscrito e quiser experimentar seus benefícios, acesse <b>Configurações</b> > <b>Gerais</b> > <b></b> Recursos avançados > <b>da Microsoft Threat Experts</b> para aplicar.</span><span class="sxs-lookup"><span data-stu-id="f841f-148">If you are not enrolled yet and would like to experience its benefits, go to <b>Settings</b> > <b>General</b> > <b>Advanced features</b> > <b>Microsoft Threat Experts</b> to apply.</span></span> <span data-ttu-id="f841f-149">Depois de aceitar, você receberá os benefícios das Notificações de Ataque Direcionado e iniciará uma avaliação de 90 dias de Especialistas sob Demanda.</span><span class="sxs-lookup"><span data-stu-id="f841f-149">Once accepted, you will get the benefits of Targeted Attack Notifications, and start a  90-day trial of Experts on Demand.</span></span> <span data-ttu-id="f841f-150">Entre em contato com seu representante da Microsoft para obter uma assinatura completa especialistas sob demanda.</span><span class="sxs-lookup"><span data-stu-id="f841f-150">Contact your Microsoft representative to get a full Experts on Demand subscription.</span></span>

<a name="apis"></a>

<span data-ttu-id="f841f-151">**[Configuração centralizada e administração, APIs](management-apis.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-151">**[Centralized configuration and administration, APIs](management-apis.md)**</span></span><br>
<span data-ttu-id="f841f-152">Integre o Microsoft Defender para Ponto de Extremidade aos fluxos de trabalho existentes.</span><span class="sxs-lookup"><span data-stu-id="f841f-152">Integrate Microsoft Defender for Endpoint into your existing workflows.</span></span>

<a name="mtp"></a>

<span data-ttu-id="f841f-153">**[Integração com soluções da Microsoft](threat-protection-integration.md)**</span><span class="sxs-lookup"><span data-stu-id="f841f-153">**[Integration with Microsoft solutions](threat-protection-integration.md)**</span></span> <br>
<span data-ttu-id="f841f-154">O Defender para Ponto de Extremidade integra-se diretamente a várias soluções da Microsoft, incluindo:</span><span class="sxs-lookup"><span data-stu-id="f841f-154">Defender for Endpoint directly integrates with various Microsoft solutions, including:</span></span>
- <span data-ttu-id="f841f-155">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="f841f-155">Azure Security Center</span></span>
- <span data-ttu-id="f841f-156">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="f841f-156">Azure Sentinel</span></span>
- <span data-ttu-id="f841f-157">Intune</span><span class="sxs-lookup"><span data-stu-id="f841f-157">Intune</span></span>
- <span data-ttu-id="f841f-158">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f841f-158">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f841f-159">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="f841f-159">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="f841f-160">Microsoft Defender para Office</span><span class="sxs-lookup"><span data-stu-id="f841f-160">Microsoft Defender for Office</span></span>
- <span data-ttu-id="f841f-161">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f841f-161">Skype for Business</span></span>

<span data-ttu-id="f841f-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span><span class="sxs-lookup"><span data-stu-id="f841f-162">**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**</span></span><br>
<span data-ttu-id="f841f-163">Com o Microsoft 365 Defender, o Defender for Endpoint e várias soluções de segurança da Microsoft formam um pacote unificado de defesa empresarial de pré e pós-violação que se integra na verdade entre o ponto de extremidade, a identidade, o email e os aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="f841f-163">With Microsoft 365 Defender, Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate, and automatically respond to sophisticated attacks.</span></span>


## <a name="related-topic"></a><span data-ttu-id="f841f-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f841f-164">Related topic</span></span>
[<span data-ttu-id="f841f-165">O Microsoft Defender para Ponto de Extremidade ajuda a detectar ameaças sofisticadas</span><span class="sxs-lookup"><span data-stu-id="f841f-165">Microsoft Defender for Endpoint helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
