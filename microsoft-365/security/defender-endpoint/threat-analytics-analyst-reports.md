---
title: Compreender a seção relatório de analistas na análise de ameaças
ms.reviewer: ''
description: Saiba mais sobre a seção relatório de analistas de cada relatório de análise de ameaças. Entenda como ele fornece informações sobre ameaças, mitigações, detecções, consultas avançadas de busca e muito mais.
keywords: relatório de analista, análise de ameaças, detecções, consultas avançadas de busca, mitigações,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2ebc826e21246381d3220855f7e8cb01741f12e9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499384"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Compreender o relatório do analista na análise de ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP)](https://go.microsoft.com/fwlink/p/?linkid=2069559)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Cada [relatório de análise de ameaças](threat-analytics.md) inclui seções dinâmicas e uma seção por escrito abrangente chamada relatório de _analista._ Para acessar esta seção, abra o relatório sobre a ameaça controlada e selecione a **guia Relatório do** Analista.

![Imagem da seção relatório do analista de um relatório de análise de ameaças](images/ta-analyst-report-small.png)

_Seção relatório de analista de um relatório de análise de ameaças_

## <a name="scan-the-analyst-report"></a>Examinar o relatório do analista 
Cada seção do relatório do analista foi projetada para fornecer informações a actionable. Embora os relatórios variem, a maioria dos relatórios inclui as seções descritas na tabela a seguir.

| Seção Relatório | Descrição |
|--|--|
| Resumo executivo | Visão geral da ameaça, incluindo quando ela foi vista pela primeira vez, suas motivações, eventos notáveis, principais alvos e ferramentas e técnicas distintas. Você pode usar essas informações para avaliar ainda mais como priorizar a ameaça no contexto de sua indústria, localização geográfica e rede. |
| Análise | Informações técnicas sobre as ameaças, incluindo os detalhes de um ataque e como os invasores podem utilizar uma nova técnica ou superfície de ataque | 
| Mitre ATT&técnicas de CK observadas | Como as técnicas observadas mapeiam para o [MITRE ATT](https://attack.mitre.org/)&de ataque CK | 
| [Mitigações](#apply-additional-mitigations) | Recomendações que podem parar ou ajudar a reduzir o impacto da ameaça. Esta seção também inclui mitigações que não são rastreadas dinamicamente como parte do relatório de análise de ameaças. |
| [Detalhes da detecção](#understand-how-each-threat-can-be-detected) | Detecções específicas e genéricas fornecidas pelas soluções de segurança da Microsoft que podem surgir atividade ou componentes associados à ameaça. | 
| [Busca avançada](#find-subtle-threat-artifacts-using-advanced-hunting) | [Consultas avançadas de busca](advanced-hunting-overview.md) para identificar proativamente as possíveis atividades de ameaça. A maioria das consultas é fornecida para complementar detecções, especialmente para localizar componentes ou comportamentos potencialmente mal-intencionados que não puderam ser avaliados dinamicamente como mal-intencionados. | 
| Referências | Publicações da Microsoft e de terceiros referenciadas por analistas durante a criação do relatório. O conteúdo da análise de ameaças baseia-se nos dados validados pelos pesquisadores da Microsoft. As informações de fontes de terceiros disponíveis publicamente são identificadas claramente como tal. | 
| Log de mudanças | A hora em que o relatório foi publicado e quando alterações significativas foram feitas no relatório. |

## <a name="apply-additional-mitigations"></a>Aplicar mitigações adicionais
A análise de ameaças rastreia [dinamicamente o status de atualizações de segurança e configurações seguras.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Essas informações estão disponíveis como gráficos e tabelas na **guia Mitigações.**

Além dessas mitigações controladas, o relatório do analista também aborda mitigações que não _são_ monitoradas dinamicamente. Aqui estão alguns exemplos de mitigações importantes que não são controladas dinamicamente:

- Bloquear emails com _anexos .lnk_ ou outros tipos de arquivo suspeitos
- Aleatoriamente senhas de administrador local
- Instruir os usuários finais sobre phishing de email e outros vetores de ameaças
- Ativar regras [específicas de redução de superfície de ataque](attack-surface-reduction.md)

Embora você possa usar a guia **Mitigações** para avaliar sua postura de segurança contra uma ameaça, essas recomendações permitem que você tome medidas adicionais para melhorar sua postura de segurança. Leia cuidadosamente todas as diretrizes de mitigação no relatório do analista e aplique-as sempre que possível.

## <a name="understand-how-each-threat-can-be-detected"></a>Entender como cada ameaça pode ser detectada
O relatório de analista também fornece as detecções do Microsoft Defender para recursos de detecção e resposta _de_ antivírus e ponto de extremidade (EDR).

### <a name="antivirus-detections"></a>Detecções antivírus
Essas detecções estão disponíveis em dispositivos com [o Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) ligado. Quando essas detecções ocorrem em dispositivos que foram integrados ao Microsoft Defender para Ponto de Extremidade, eles também disparam alertas que acendem os gráficos no relatório.

>[!NOTE]
>O relatório do analista também lista detecções **genéricas** que podem identificar uma ampla variedade de ameaças, além de componentes ou comportamentos específicos da ameaça controlada. Essas detecções genéricas não refletem nos gráficos.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Alertas de detecção e resposta de ponto de extremidade (EDR)
Alertas de EDR são gerados para [dispositivos conectados ao Microsoft Defender para Ponto de Extremidade.](onboard-configure.md) Esses alertas geralmente dependem de sinais de segurança coletados pelo sensor do Microsoft Defender para Ponto de Extremidade e outros recursos de ponto de extremidade, como antivírus, proteção de rede, proteção contra adulteração, que servem como fontes de sinal poderosas.

Como a lista de detecções de antivírus, alguns alertas de EDR são projetados para sinalizar genericamente comportamentos suspeitos que podem não estar associados à ameaça controlada. Nesses casos, o relatório identificará claramente o alerta como "genérico" e não influenciará nenhum dos gráficos no relatório.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Encontrar artefatos de ameaças sutis usando a busca avançada
Embora as detecções permitam identificar e interromper a ameaça controlada automaticamente, muitas atividades de ataque deixam rastreamentos sutis que exigem inspeção adicional. Algumas atividades de ataque exibem comportamentos que também podem ser normais, portanto, detectá-los dinamicamente pode resultar em ruído operacional ou até mesmo falsos positivos.

[A busca avançada](advanced-hunting-overview.md) fornece uma interface de consulta com base no Idioma de Consulta kusto que simplifica a localização de indicadores sutis de atividade de ameaça. Ele também permite que você superfície informações contextuais e verificar se os indicadores estão conectados a uma ameaça.

Consultas de busca avançadas nos relatórios de analistas foram vetada por analistas da Microsoft e estão prontas para você executar no editor de consulta de [busca avançada.](https://securitycenter.windows.com/advanced-hunting) Você também pode usar as consultas para criar regras de detecção [personalizadas](custom-detection-rules.md) que disparam alertas para futuras combinações.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da análise de ameaças](threat-analytics.md)
- [Encontrar proativamente ameaças com busca avançada](advanced-hunting-overview.md) 
- [Regras de detecção personalizadas](custom-detection-rules.md)