---
title: Microsoft Defender para Ponto de Extremidade
description: O Microsoft Defender for Endpoint é uma plataforma de segurança de ponto de extremidade empresarial que ajuda a se defender contra ameaças persistentes avançadas.
keywords: introdução ao Microsoft Defender para Ponto de Extremidade, introdução ao Microsoft Defender para Ponto de Extremidade, segurança cibernética, ameaça persistente avançada, segurança corporativa, sensor comportamental de máquina, segurança na nuvem, análise, inteligência contra ameaças, redução de superfície de ataque, proteção de próxima geração, investigação automatizada e correção, especialistas em ameaças da Microsoft, pontuação segura, busca avançada, Microsoft 365 Defender, busca de ameaças cibernéticas
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
ms.openlocfilehash: 23a9b99a71d700bdeddb3398c592eeb778ceef23
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879247"
---
# <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> Para obter mais informações sobre Windows 10 Enterprise e funcionalidades do Windows 10 Enterprise Edition, [consulte Windows 10 Enterprise edição](https://www.microsoft.com/WindowsForBusiness/buy).

O Microsoft Defender for Endpoint é uma plataforma de segurança de ponto de extremidade empresarial projetada para ajudar as redes corporativas a evitar, detectar, investigar e responder a ameaças avançadas.
<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

O Defender para Ponto de Extremidade usa a seguinte combinação de tecnologia Windows 10 e o serviço de nuvem robusto da Microsoft:

-   **Sensores comportamentais** de ponto de extremidade : incorporados Windows 10, esses sensores coletam e processam sinais comportamentais do sistema operacional e enviam esses dados de sensor para sua instância privada, isolada e de nuvem do Microsoft Defender para Ponto de Extremidade.


-   Análise de segurança na nuvem **:** aproveitando big-data, aprendizado de dispositivo e óptica exclusiva da Microsoft no ecossistema do Windows, produtos de nuvem empresarial (como Office 365) e ativos online, sinais comportamentais são convertidos em insights, detecções e respostas recomendadas a ameaças avançadas.

-   **Inteligência** contra ameaças : gerada por caçadores da Microsoft, equipes de segurança e aumentadas pela inteligência contra ameaças fornecidas por parceiros, a inteligência contra ameaças permite que o Defender para o Ponto de Extremidade identifique ferramentas, técnicas e procedimentos do invasor e gere alertas quando eles são observados nos dados do sensor coletados.

<center><h2>Microsoft Defender para Ponto de Extremidade</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/TVM_icon.png" alt="Threat & Vulnerability Management"> <br><b>Gerenciamento & de vulnerabilidades</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Redução de superfície de ataque</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Proteção de última geração</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Detecção e resposta do ponto de extremidade</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Investigação e correção automatizadas</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Especialistas em Ameaças da Microsoft</b></a></center></td>
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

<p></p>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0] 

> [!TIP]
> - Saiba mais sobre os aprimoramentos mais recentes no Defender para Ponto de Extremidade: Novidades [no Microsoft Defender para Ponto de Extremidade.](whats-new-in-microsoft-defender-atp.md)
> - O Microsoft Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE. Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

<a name="tvm"></a>

**[Gerenciamento & de vulnerabilidades](next-gen-threat-and-vuln-mgt.md)**<br>
Esse recurso integrado usa uma abordagem baseada em risco que altera o jogo para a descoberta, priorização e correção de vulnerabilidades de ponto de extremidade e configurações in-loco. 

<a name="asr"></a>

**[Redução de superfície de ataque](overview-attack-surface-reduction.md)**<br>
O conjunto de recursos de redução de superfície de ataque fornece a primeira linha de defesa na pilha. Ao garantir que as configurações sejam definidas corretamente e que as técnicas de mitigação de exploração sejam aplicadas, os recursos resistem a ataques e exploração. Esse conjunto de recursos também inclui proteção de rede e [proteção da Web](web-protection-overview.md), que regulam o acesso a endereços IP mal-intencionados, domínios e URLs. [](network-protection.md) 

<a name="ngp"></a>

**[Proteção de próxima geração](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)**<br>
Para reforçar ainda mais o perímetro de segurança da sua rede, o Microsoft Defender for Endpoint usa proteção de última geração projetada para capturar todos os tipos de ameaças emergentes.

<a name="edr"></a>

**[Detecção de ponto de extremidade e resposta](overview-endpoint-detection-response.md)**<br>
Os recursos de detecção e resposta do ponto de extremidade são colocados para detectar, investigar e responder a ameaças avançadas que podem ter passado dos dois primeiros pilares de segurança. [A busca avançada](advanced-hunting-overview.md) fornece uma ferramenta de busca de ameaças baseada em consulta que permite que você encontre violações e crie detecções personalizadas proativamente.

<a name="ai"></a>

**[Investigação e correção automatizadas](automated-investigations.md)**<br>
Em conjunto com a capacidade de responder rapidamente a ataques avançados, o Microsoft Defender for Endpoint oferece recursos automáticos de investigação e correção que ajudam a reduzir o volume de alertas em minutos em escala. 

<a name="ss"></a>

**[Microsoft Secure Score para dispositivos](tvm-microsoft-secure-score-devices.md)**<br>

O Defender for Endpoint inclui a Pontuação Segura da Microsoft para Dispositivos para ajudá-lo a avaliar dinamicamente o estado de segurança da sua rede corporativa, identificar sistemas desprotegidos e a tomar ações recomendadas para melhorar a segurança geral da sua organização.

<a name="mte"></a>

**[Especialistas em Ameaças da Microsoft](microsoft-threat-experts.md)**<br>
O novo serviço gerenciado de busca de ameaças do Microsoft Defender for Endpoint fornece busca proativa, priorização e contexto adicional e percepções que capacitam ainda mais os Centros de Operação de Segurança (SOCs) a identificar e responder a ameaças de forma rápida e precisa.

>[!IMPORTANT]
>Os clientes do Defender para Ponto de Extremidade precisam solicitar o serviço de Especialistas em Ameaças da Microsoft de busca de ameaças gerenciadas para obter notificações de ataque direcionadas proativas e colaborar com especialistas sob demanda. Especialistas sob Demanda é um serviço de complemento. Notificações de ataque direcionadas são sempre incluídas depois que você é aceito no Especialistas em Ameaças da Microsoft de busca de ameaças gerenciadas.<p>
><p>Se você ainda não estiver inscrito e quiser experimentar <b></b> seus benefícios, acesse Configurações > <b>recursos</b> > <b></b> avançados > <b>gerais</b> Especialistas em Ameaças da Microsoft aplicar. Depois de aceitar, você receberá os benefícios das Notificações de Ataque Direcionado e iniciará uma avaliação de 90 dias de Especialistas sob Demanda. Entre em contato com seu representante da Microsoft para obter uma assinatura completa especialistas sob demanda.

<a name="apis"></a>

**[Configuração centralizada e administração, APIs](management-apis.md)**<br>
Integre o Microsoft Defender para Ponto de Extremidade aos fluxos de trabalho existentes.

<a name="mtp"></a>

**[Integração com soluções da Microsoft](threat-protection-integration.md)** <br>
O Defender para Ponto de Extremidade integra-se diretamente a várias soluções da Microsoft, incluindo:
- Azure Defender
- Azure Sentinel
- Intune
- Microsoft Cloud App Security
- Microsoft Defender para Identidade?
- Microsoft Defender para Office
- Skype for Business

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-threat-protection)**<br>
Com o Microsoft 365 Defender, o Defender para o Ponto de Extremidade e várias soluções de segurança da Microsoft formam um pacote de defesa empresarial unificado de pré e pós-violação que se integra na verdade ao ponto de extremidade, identidade, email e aplicativos para detectar, impedir, investigar e responder automaticamente a ataques sofisticados.


## <a name="related-topic"></a>Tópicos relacionados
[O Microsoft Defender para Ponto de Extremidade ajuda a detectar ameaças sofisticadas](https://www.microsoft.com/itshowcase/microsoft-defender-atps-antivirus-capabilities-boost-malware-protection)
