---
title: Proteção contra Ameaças (Windows 10)
description: O Microsoft Defender ATP é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta.
keywords: proteção contra ameaças, Microsoft Defender para Ponto de Extremidade, redução de superfície de ataque, proteção de próxima geração, detecção e resposta do ponto de extremidade, investigação e resposta automatizadas, especialistas em ameaças da Microsoft, Pontuação Segura da Microsoft para Dispositivos, busca avançada, busca de ameaças cibernéticas, proteção contra ameaças da Web
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
ms.openlocfilehash: 3098c2786874650ad14d226beacd5ec760decef0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934928"
---
# <a name="threat-protection"></a>Proteção contra Ameaças
[O Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. O Defender for Endpoint protege os pontos de extremidade contra ameaças cibernéticas, detecta ataques avançados e violações de dados, automatiza incidentes de segurança e melhora a postura de segurança.

> [!TIP]
> Permitir que seus usuários acessem serviços de nuvem e aplicativos locais com facilidade e habilitam recursos modernos de gerenciamento para todos os dispositivos. Para obter mais informações, consulte [Secure your remote workforce](https://docs.microsoft.com/enterprise-mobility-security/remote-work/). 

<center><h2>Microsoft Defender para Ponto de Extremidade</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="threat and vulnerability icon"> <br><b>Gerenciamento de & de vulnerabilidades</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="attack surface reduction icon"> <br><b>Redução de superfície de ataque</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="next generation protection icon"><br> <b>Proteção de última geração</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="endpoint detection and response icon"><br> <b>Detecção e resposta do ponto de extremidade</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="automated investigation and remediation icon"><br> <b>Investigação e correção automatizadas</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="microsoft threat experts icon"><br> <b>Especialistas em ameaças da Microsoft</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Configuração centralizada e administração, APIs</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<a name="tvm"></a>


>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4obJq]

**[Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)**<br>
Esse recurso integrado usa uma abordagem baseada em risco que altera o jogo para a descoberta, priorização e correção de vulnerabilidades de ponto de extremidade e configurações in-loco.

- [Visão geral & gerenciamento de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Introdução](tvm-prerequisites.md)
- [Acessar sua postura de segurança](tvm-dashboard-insights.md)
- [Melhorar a postura de segurança e reduzir o risco](tvm-security-recommendation.md)
- [Entender as vulnerabilidades em seus dispositivos](tvm-software-inventory.md)

<a name="asr"></a>

**[Redução de superfície de ataque](overview-attack-surface-reduction.md)**<br>
O conjunto de recursos de redução de superfície de ataque fornece a primeira linha de defesa na pilha. Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, esse conjunto de recursos resistem a ataques e exploração.

- [Isolamento baseado em hardware](overview-hardware-based-isolation.md)
- [Controle da aplicação](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)
- [Controle de dispositivo](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [Proteção de exploração](exploit-protection.md)
- [Proteção de rede](network-protection.md), [proteção da Web](web-protection-overview.md)
- [Acesso controlado a pastas](controlled-folders.md)
- [Firewall de rede](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
- [Regras da redução da superfície de ataque](attack-surface-reduction.md)

<a name="ngp"></a>

**[Proteção de próxima geração](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Para reforçar ainda mais o perímetro de segurança da sua rede, o Microsoft Defender for Endpoint usa proteção de última geração projetada para capturar todos os tipos de ameaças emergentes.

- [Monitoramento de comportamento](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)
- [Proteção baseada em nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-protection-features-microsoft-defender-antivirus)
- [Aprendizado de máquina](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [Proteção de URL](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)
- [Serviço de área desatendido automatizado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

<a name="edr"></a>

**[Detecção de ponto de extremidade e resposta](overview-endpoint-detection-response.md)**<br>
Os recursos de detecção e resposta do ponto de extremidade são colocados para detectar, investigar e responder a tentativas de invasão e violações ativas. Com a busca avançada, você tem uma ferramenta de busca de ameaças baseada em consulta que permite que seu usuário encontre violações de forma proativa e crie detecções personalizadas.

- [Alertas](alerts-queue.md)
- [Dados de ponto de extremidade históricos](investigate-machines.md#timeline)
- [Orquestração de resposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
- [Coleção Forensic](respond-machine-alerts.md#collect-investigation-package-from-devices)
- [Inteligência contra ameaças](threat-indicator-concepts.md)
- [Serviço avançado de detonação e análise](respond-file-alerts.md#deep-analysis)
- [Busca avançada](advanced-hunting-overview.md)
    - [Detecções personalizadas](overview-custom-detections.md)

<a name="ai"></a>

**[Investigação e correção automatizadas](automated-investigations.md)**<br>
Além de responder rapidamente a ataques avançados, o Microsoft Defender for Endpoint oferece recursos automáticos de investigação e correção que ajudam a reduzir o volume de alertas em minutos em escala.

- [Investigação e correção automatizadas](automated-investigations.md)
- [Exibir detalhes e resultados das investigações automatizadas](auto-investigation-action-center.md)
- [Exibir e aprovar ações de correção](manage-auto-investigation.md)

<a name="mte"></a>

**[Especialistas em Ameaças da Microsoft](microsoft-threat-experts.md)**<br>
O novo serviço de busca de ameaças gerenciadas do Microsoft Defender para Endpoint fornece busca proativa, priorização e contexto e insights adicionais. Os Especialistas em Ameaças da Microsoft capacitam ainda mais os Centros de Operação de Segurança (SOCs) a identificar e responder a ameaças com rapidez e precisão.

- [Notificação de ataque direcionada](microsoft-threat-experts.md)
- [Especialistas sob demanda](microsoft-threat-experts.md)
- [Configurar seu serviço de busca gerenciada do Microsoft 365 Defender](configure-microsoft-threat-experts.md)

<a name="apis"></a>

**[Configuração centralizada e administração, APIs](management-apis.md)**<br>
Integre o Microsoft Defender para Ponto de Extremidade aos fluxos de trabalho existentes.
- [Integração](onboard-configure.md)
- [Integração de API e SIEM](configure-siem.md)
- [APIs expostas](apis-intro.md)
- [Controle de Acesso Baseado em Função (RBAC)](rbac.md)
- [Relatórios e tendências](threat-protection-reports.md)

<a name="integration"></a>
**[Integração com soluções da Microsoft](threat-protection-integration.md)** <br>
 O Microsoft Defender para Ponto de Extremidade integra-se diretamente com várias soluções da Microsoft, incluindo:
- Intune
- Microsoft Defender para Office 365
- Microsoft Defender para Identidade?
- Azure Defender
- Skype for Business
- Microsoft Cloud App Security

<a name="mtp"></a>
**[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)**<br>
 Com o Microsoft 365 Defender, o Microsoft Defender for Endpoint e várias soluções de segurança da Microsoft formam um pacote unificado de defesa empresarial de pré e pós-violação que se integra na verdade entre pontos de extremidade, identidade, email e aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados.
