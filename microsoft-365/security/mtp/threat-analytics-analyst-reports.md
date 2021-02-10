---
title: Entenda a seção de relatório de analistas na análise de ameaças
ms.reviewer: ''
description: Saiba mais sobre a seção de relatório de analistas de cada relatório de análise de ameaças. Entenda como ele fornece informações sobre ameaças, mitigações, detecções, consultas de busca avançada e muito mais.
keywords: relatório de analista, análise de ameaças, detecções, consultas de busca avançada, mitigações,
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167547"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Entenda o relatório de analistas na análise de ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Cada [relatório de análise de ameaças](threat-analytics.md) inclui seções dinâmicas e uma seção por escrito abrangente chamada relatório de _analista._ Para acessar esta seção, abra o relatório sobre a ameaça controlada e selecione a guia **Relatório de** Analistas.

![Imagem da seção de relatório de analistas de um relatório de análise de ameaças](../../media/threat-analytics/ta_analystreport_mtp.png)

_Seção de relatório de analistas de um relatório de análise de ameaças_

## <a name="scan-the-analyst-report"></a>Verificar o relatório de analistas 
Cada seção do relatório de analistas foi projetada para fornecer informações a actionable. Embora os relatórios variem, a maioria dos relatórios inclui as seções descritas na tabela a seguir.

| Seção Report | Descrição |
|--|--|
| Resumo executivo | Visão geral da ameaça, incluindo quando ela foi vista pela primeira vez, suas motivações, eventos notáveis, principais alvos e ferramentas e técnicas distintas. Você pode usar essas informações para avaliar ainda mais como priorizar a ameaça no contexto do seu setor, localização geográfica e rede. |
| Análise | Informações técnicas sobre as ameaças, incluindo os detalhes de um ataque e como os invasores podem utilizar uma nova técnica ou superfície de ataque | 
| TÉCNICAS MITRE ATT&CK observadas | Como as técnicas observadas mapeiam para a [estrutura de ataque CK do MITRE ATT&CK](https://attack.mitre.org/) | 
| [Mitigações](#apply-additional-mitigations) | Recomendações que podem parar ou ajudar a reduzir o impacto da ameaça. Esta seção também inclui mitigações que não são controladas dinamicamente como parte do relatório de análise de ameaças. |
| [Detalhes da detecção](#understand-how-each-threat-can-be-detected) | Detecções específicas e genéricas fornecidas pelas soluções de segurança da Microsoft que podem surgir atividade ou componentes associados à ameaça. | 
| [Busca avançada](#find-subtle-threat-artifacts-using-advanced-hunting) | [Consultas de busca avançada para](advanced-hunting-overview.md) identificar proativamente possíveis atividades de ameaças. A maioria das consultas é fornecida para complementar detecções, especialmente para localizar componentes ou comportamentos potencialmente mal-intencionados que não puderam ser avaliados dinamicamente como mal-intencionados. | 
| Referências | Publicações da Microsoft e de terceiros referenciadas por analistas durante a criação do relatório. O conteúdo da análise de ameaças é baseado em dados validados por pesquisadores da Microsoft. As informações de fontes de terceiros publicamente disponíveis são identificadas claramente como tal. | 
| Log de mudanças | A hora em que o relatório foi publicado e quando alterações significativas foram feitas no relatório. |

## <a name="apply-additional-mitigations"></a>Aplicar mitigações adicionais
A Análise de ameaças rastreia [dinamicamente o status de atualizações de segurança e configurações seguras.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Essas informações estão disponíveis como gráficos e tabelas na **guia Mitigações.**

Além dessas mitigações controladas, o relatório de analistas também discute mitigações que não _são_ monitoradas dinamicamente. Aqui estão alguns exemplos de mitigações importantes que não são controladas dinamicamente:

- Bloquear emails com _anexos .lnk_ ou outros tipos de arquivo suspeitos
- Randomizar senhas de administrador local
- Instrua os usuários finais sobre phishing de email e outros vetores de ameaças
- Ativar regras de [redução de superfície de ataque específicas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Embora você possa usar a guia **Mitigações** para avaliar a postura de segurança em relação a uma ameaça, essas recomendações permitem que você tome medidas adicionais para melhorar a postura de segurança. Leia cuidadosamente todas as diretrizes de mitigação no relatório de analistas e aplique-as sempre que possível.

## <a name="understand-how-each-threat-can-be-detected"></a>Entender como cada ameaça pode ser detectada
O relatório de analista também fornece as detecções do Microsoft Defender para recursos de detecção e resposta _de_ ponto de extremidade (EDR) antivírus e ponto de extremidade.

### <a name="antivirus-detections"></a>Detecções de antivírus
Essas detecções estão disponíveis em dispositivos com [o Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) ligado. Quando essas detecções ocorrem em dispositivos que foram onboarded ao Microsoft Defender para Ponto de Extremidade, eles também disparam alertas que acendem os gráficos no relatório.

>[!NOTE]
>O relatório de analistas também lista detecções **genéricas** que podem identificar uma ampla variedade de ameaças, além de componentes ou comportamentos específicos da ameaça controlada. Essas detecções genéricas não refletem nos gráficos.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Alertas de detecção e resposta de ponto de extremidade (EDR)
Os alertas de EDR são gerados [para dispositivos integrados ao Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Esses alertas geralmente dependem de sinais de segurança coletados pelo Microsoft Defender para sensor de ponto de extremidade e outros recursos de ponto de extremidade, como antivírus, proteção de rede, proteção contra adulterações, que servem como fontes de sinal poderosas.

Como a lista de detecções de antivírus, alguns alertas de EDR são projetados para sinalizar genericamente um comportamento suspeito que pode não estar associado à ameaça controlada. Nesses casos, o relatório identificará claramente o alerta como "genérico" e não influenciará nenhum gráfico no relatório.

### <a name="email-related-detections-and-mitigations"></a>Mitigações e detecções relacionadas a email
As detecções e mitigações relacionadas a email do Microsoft Defender para Office 365 estão incluídas em relatórios de analistas, além dos dados de ponto de extremidade já disponíveis no Microsoft Defender para o Ponto de Extremidade. 

As informações de tentativa de email impedidas dão informações sobre se sua organização era um alvo da ameaça abordada no relatório do analista, mesmo que o ataque tenha sido efetivamente bloqueado antes da entrega ou da entrega na pasta lixo eletrônico.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Encontrar artefatos sutis de ameaças usando a busca avançada
Embora as detecções permitam identificar e parar a ameaça controlada automaticamente, muitas atividades de ataque deixam rastreamentos sutis que exigem inspeção adicional. Algumas atividades de ataque apresentam comportamentos que também podem ser normais, portanto, detectá-los dinamicamente pode resultar em ruído operacional ou até mesmo falsos positivos.

[A busca](advanced-hunting-overview.md) avançada fornece uma interface de consulta baseada na linguagem de consulta Kusto que simplifica a localização de indicadores sutis de atividade de ameaças. Ele também permite que você surface informações contextuais e verifique se os indicadores estão conectados a uma ameaça.

Consultas de busca avançada nos relatórios de analistas foram feitas por analistas da Microsoft e estão prontas para você executar no editor de consulta de busca [avançada.](https://security.microsoft.com/advanced-hunting) Você também pode usar as consultas para criar [regras](custom-detection-rules.md) de detecção personalizadas que disparam alertas para futuras combinações.


>[!NOTE]
> A análise de ameaças também está disponível [no Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) No entanto, ele não tem a integração de dados entre o Microsoft Defender for Office e o Microsoft Defender for Endpoint que a análise do Microsoft 365 Defender Threat tem.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da análise de ameaças](threat-analytics.md)
- [Encontrar ameaças proativamente com a busca avançada](advanced-hunting-overview.md) 
- [Regras de detecção personalizadas](custom-detection-rules.md)
