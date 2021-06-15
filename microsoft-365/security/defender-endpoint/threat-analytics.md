---
title: Rastrear e responder a ameaças emergentes com o Microsoft Defender para análise de ameaças do Ponto de Extremidade
ms.reviewer: ''
description: Entenda as ameaças e técnicas de ataque emergentes e como impedi-las. Avalie o impacto deles em sua organização e avalie sua resiliência organizacional.
keywords: análise de ameaças, avaliação de risco, mitigação do sistema operacional, mitigação de microcódigo, status de mitigação
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 63303f9eacd25a8de1c7154ac66c73578bfd495a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924450"
---
# <a name="track-and-respond-to-emerging-threats-through-threat-analytics"></a>Rastrear e responder a ameaças emergentes por meio da análise de ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Com adversários mais sofisticados e novas ameaças surgindo com frequência e predominantemente, é fundamental poder fazer isso rapidamente:

- Avaliar o impacto de novas ameaças
- Revise sua resiliência contra ou exposição às ameaças
- Identificar as ações que você pode tomar para parar ou conter as ameaças

Análise de ameaças é um conjunto de relatórios de pesquisadores de segurança especialistas da Microsoft que abrangem as ameaças mais relevantes, incluindo:

- Atores de ameaças ativos e suas campanhas
- Técnicas de ataque populares e novas
- Vulnerabilidades críticas
- Superfícies de ataque comuns
- Malware predominante

Cada relatório fornece uma análise detalhada de uma ameaça e orientações abrangentes sobre como se defender contra essa ameaça. Ele também incorpora dados de sua rede, indicando se a ameaça está ativa e se você tem proteções aplicáveis no local.

Assista a este breve vídeo para saber mais sobre como a análise de ameaças pode ajudá-lo a rastrear as ameaças mais recentes e impedi-las.
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a>Exibir o painel de análise de ameaças

O painel de análise de ameaças é um ótimo ponto de partida para obter os relatórios mais relevantes para sua organização. Ele resume as ameaças nas seções a seguir:

- **Ameaças mais** recentes lista os relatórios de ameaças publicados mais recentemente, juntamente com o número de dispositivos com alertas ativos e resolvidos.
- **Ameaças de alto impacto** lista as ameaças que tiveram o maior impacto para a organização. Esta seção classifica as ameaças pelo número de dispositivos que têm alertas ativos.
- **Resumo de** ameaças — mostra o impacto geral das ameaças controladas mostrando o número de ameaças com alertas ativos e resolvidos.

Selecione uma ameaça no painel para exibir o relatório dessa ameaça.

![Imagem de um painel de análise de ameaças](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a>Exibir um relatório de análise de ameaças

Cada relatório de análise de ameaças fornece informações em três seções: **Overview**, **Analyst report** e **Mitigations**.

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Visão geral: entenda rapidamente a ameaça, avalie seu impacto e revise as defesas

A **seção Visão** Geral fornece uma visualização do relatório detalhado do analista. Ele também fornece gráficos que realçam o impacto da ameaça à sua organização e sua exposição por meio de dispositivos não configurados e não configurados.

![Imagem da seção visão geral de um relatório de análise de ameaças ](images/ta-overview.png)
 _Visão geral de um relatório de análise de ameaças_

#### <a name="assess-the-impact-to-your-organization"></a>Avaliar o impacto para sua organização
Cada relatório inclui gráficos projetados para fornecer informações sobre o impacto organizacional de uma ameaça:
- **Dispositivos com alertas** mostram o número atual de dispositivos distintos que foram afetados pela ameaça. Um dispositivo será categorizado como **Ativo** se houver pelo menos um  alerta associado a essa ameaça e **Resolvido** se todos os alertas associados à ameaça no dispositivo foram resolvidos.
- **Dispositivos com alertas ao** longo do tempo mostram o número de dispositivos distintos com alertas **ativos** e **resolvidos** ao longo do tempo. O número de alertas resolvidos indica a rapidez com que sua organização responde a alertas associados a uma ameaça. Idealmente, o gráfico deve mostrar alertas resolvidos em alguns dias.

#### <a name="review-security-resilience-and-posture"></a>Revisar a resiliência e a postura de segurança
Cada relatório inclui gráficos que fornecem uma visão geral de como sua organização é resiliente contra uma determinada ameaça:
- **Status da configuração** de segurança mostra o número de dispositivos que aplicaram as configurações de segurança recomendadas que podem ajudar a reduzir a ameaça. Os dispositivos são **considerados Seguros** se eles aplicaram _todas as_ configurações controladas.
- **Status de patch de vulnerabilidade** mostra o número de dispositivos que aplicaram atualizações de segurança ou patches que abordam vulnerabilidades exploradas pela ameaça.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Relatório de analistas: obter informações de especialistas de pesquisadores de segurança da Microsoft
Vá até a **seção Relatório** de Analistas para ler o relatório detalhado do especialista. A maioria dos relatórios fornece descrições detalhadas de cadeias de ataque, incluindo táticas e técnicas mapeadas para [](advanced-hunting-overview.md) a estrutura de CK do MITRE ATT&, listas exaustivas de recomendações e orientações avançadas sobre a busca de ameaças.

[Saiba mais sobre o relatório do analista](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Mitigações: revise a lista de mitigações e o status de seus dispositivos
Na seção **Mitigações,** revise a lista de recomendações ativas específicas que podem ajudá-lo a aumentar sua resiliência organizacional em relação à ameaça. A lista de mitigações controladas inclui:

- **Atualizações de segurança**— implantação de atualizações de segurança ou patches para vulnerabilidades
- **Microsoft Defender Antivírus configurações**
  - Versão de inteligência de segurança
  - Proteção fornecida na nuvem  
  - Proteção de aplicativo potencialmente indesejado (PUA)
  - Proteção em tempo real
 
As informações de mitigação nesta seção incorporam dados [do Gerenciamento de Ameaças e Vulnerabilidades](next-gen-threat-and-vuln-mgt.md), que também fornece informações detalhadas de detalhamento de vários links no relatório.

![Imagem da seção mitigações de um relatório de análise de ameaças ](images/ta-mitigations.png)
 _Seção Mitigações de um relatório de análise de ameaças_

## <a name="additional-report-details-and-limitations"></a>Detalhes e limitações adicionais do relatório
Ao usar os relatórios, lembre-se do seguinte: 

- Os dados têm escopo com base no escopo do RBAC (controle de acesso baseado em função). Você verá o status dos dispositivos em [grupos que você pode acessar](machine-groups.md).
- Os gráficos refletem apenas mitigações controladas. Verifique a visão geral do relatório para obter mitigações adicionais que não são mostradas nos gráficos.
- Mitigações não garantem resiliência completa. As mitigações fornecidas refletem as melhores ações possíveis necessárias para melhorar a resiliência.
- Os dispositivos serão contados como "indisponíveis" se não transmitirem dados para o serviço.
- Estatísticas relacionadas a antivírus são baseadas em Microsoft Defender Antivírus configurações. Dispositivos com soluções antivírus de terceiros podem aparecer como "expostos".

## <a name="related-topics"></a>Tópicos relacionados
- [Encontrar proativamente ameaças com busca avançada](advanced-hunting-overview.md) 
- [Compreender a seção relatório de analistas](threat-analytics-analyst-reports.md)
- [Avaliar e resolver deficiências e exposições de segurança](next-gen-threat-and-vuln-mgt.md)
