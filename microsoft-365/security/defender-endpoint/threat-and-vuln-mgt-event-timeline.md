---
title: Linha do tempo do evento Gerenciamento de Ameaças e Vulnerabilidades
description: A linha do tempo do evento é um feed de notícias de risco que ajuda você a interpretar como o risco é introduzido na organização e quais mitigações aconteceram para reduzi-lo.
keywords: linha do tempo do evento, linha do tempo do evento do Microsoft Defender for Endpoint, linha do tempo do evento tvm do Microsoft Defender para Endpoint, Gerenciamento de Ameaças e Vulnerabilidades, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 64362598ff4b0512eb110917071e6d32abb8ede9
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933476"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a>Linha do tempo do evento - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

A linha do tempo do evento é um feed de notícias de risco que ajuda você a interpretar como o risco é introduzido na organização por meio de novas vulnerabilidades ou explorações. Você pode exibir eventos que podem afetar o risco da sua organização. Por exemplo, você pode encontrar novas vulnerabilidades que foram introduzidas, vulnerabilidades que se tornaram exploradas, exploração que foi adicionada a um kit de exploração e muito mais.

A linha do tempo [](tvm-exposure-score.md) do evento também conta a história da sua pontuação de exposição e da Pontuação Segura da Microsoft para [Dispositivos](tvm-microsoft-secure-score-devices.md) para que você possa determinar a causa de grandes alterações. Os eventos podem afetar seus dispositivos ou sua pontuação para dispositivos. Reduza a exposição abordando o que precisa ser remediado com base nas recomendações de [segurança priorizadas.](tvm-security-recommendation.md)

>[!TIP]
>Para obter emails sobre novos eventos de vulnerabilidade, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-event-timeline-page"></a>Navegue até a página linha do tempo do evento

Há também três pontos de entrada do painel [de Gerenciamento de Ameaças e Vulnerabilidades](tvm-dashboard-insights.md):

- **Cartão de pontuação de** exposição da organização : passe o mouse sobre os pontos de evento no gráfico "Pontuação de Exposição ao longo do tempo" e selecione "Ver todos os eventos deste dia". Os eventos representam vulnerabilidades de software.
- **Pontuação segura da Microsoft para dispositivos**: passe o mouse sobre os pontos de evento no gráfico "Sua pontuação para dispositivos ao longo do tempo" e selecione "Ver todos os eventos deste dia". Os eventos representam novas avaliações de configuração.
- **Cartão de eventos principais**: Selecione "Mostrar mais" na parte inferior da tabela de eventos principais. O cartão exibe os três eventos mais impactados dos últimos 7 dias. Eventos impactáveis podem incluir se o evento afetar um grande número de dispositivos ou se for uma vulnerabilidade crítica.

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a>Pontuação de exposição e Pontuação Segura da Microsoft para Dispositivos gráficos

No painel Gerenciamento de Ameaças e Vulnerabilidades, passe o mouse sobre o gráfico de pontuação de exposição para exibir os principais eventos de vulnerabilidade de software desse dia que afetaram seus dispositivos. Passe o mouse sobre o gráfico Microsoft Secure Score for Devices para exibir novas avaliações de configuração de segurança que afetam sua pontuação.

Se não houver eventos que afetem seus dispositivos ou sua pontuação para dispositivos, nenhum será mostrado.

![Foco de pontuação de ](images/tvm-event-timeline-exposure-score350.png) 
 ![ exposição Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)

### <a name="drill-down-to-events-from-that-day"></a>Detalhar até eventos desse dia

Selecionar **Mostrar todos os eventos deste dia** leva você à página linha do tempo do evento com um intervalo de datas personalizado para esse dia.

![Intervalo de datas personalizado selecionado da linha do tempo do evento](images/tvm-event-timeline-drilldown.png)

Selecione **Intervalo personalizado** para alterar o intervalo de datas para outro personalizado ou um intervalo de tempo pré-definido.

![Opções de intervalo de datas da linha do tempo do evento](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a>Visão geral da linha do tempo do evento

Na página Linha do tempo do evento, você pode exibir todas as informações necessárias relacionadas a um evento. 

Recursos:

- Personalizar colunas
- Filtrar por tipo de evento ou por cento de dispositivos afetados
- Exibir 30, 50 ou 100 itens por página

Os dois números grandes na parte superior da página mostram o número de novas vulnerabilidades e vulnerabilidades exploráveis, não eventos. Alguns eventos podem ter várias vulnerabilidades e algumas vulnerabilidades podem ter vários eventos.

![Página da linha do tempo do evento](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a>Colunas

- **Data**: mês, dia, ano
- **Evento**: evento impactante, incluindo componente, tipo e número de dispositivos afetados
- **Componente relacionado**: software
- **Dispositivos originalmente afetados**: o número e a porcentagem de dispositivos afetados quando esse evento ocorreu originalmente. Você também pode filtrar pela porcentagem de dispositivos originalmente afetados, do número total de dispositivos.
- **Dispositivos atualmente afetados**: o número atual e porcentagem de dispositivos que esse evento afeta no momento. Você pode encontrar esse campo selecionando **Personalizar colunas**.
- **Tipos**: refletem eventos marcados por hora que impactam a pontuação. Eles podem ser filtrados.
    - Exploit adicionado a um kit de exploração
    - Exploit foi verificado
    - Nova exploração pública
    - Nova vulnerabilidade
    - Nova avaliação de configuração
- **Tendência de pontuação**: tendência de pontuação de exposição

### <a name="icons"></a>Ícones

Os ícones a seguir aparecem ao lado de eventos:

- ![ícone de bug](images/tvm-black-bug-icon.png) Nova exploração pública
- ![ícone de aviso de relatório](images/report-warning-icon.png) Nova vulnerabilidade foi publicada
- ![exploit kit](images/bug-lightning-icon2.png) Exploit encontrado no kit de exploração
- ![ícone de bug com ícone de aviso](images/bug-caution-icon2.png) Explorar verificado

### <a name="drill-down-to-a-specific-event"></a>Fazer uma análise de um evento específico

Depois de selecionar um evento, um flyout aparecerá com uma lista de detalhes e CVEs atuais que afetam seus dispositivos. Você pode mostrar mais CVEs ou exibir a recomendação relacionada.

A seta abaixo de "tendência de pontuação" ajuda você a determinar se esse evento potencialmente aumentou ou baixou sua pontuação de exposição organizacional. Maior pontuação de exposição significa que os dispositivos são mais vulneráveis à exploração.

![Flyout da linha do tempo do evento](images/tvm-event-timeline-flyout500.png)

A partir daí, selecione **Ir para recomendação de segurança** relacionada exibir a recomendação que aborda a nova vulnerabilidade de software na página recomendações de [segurança](tvm-security-recommendation.md). Depois de ler a descrição e os detalhes de vulnerabilidade na recomendação de segurança, você pode enviar uma solicitação de correção e acompanhar a solicitação na página [de correção.](tvm-remediation.md)  

## <a name="view-event-timelines-in-software-pages"></a>Exibir cronogramas de eventos em páginas de software

Para abrir uma página de software, selecione um evento > selecione o nome do software hiperlink (como Visual Studio 2017) na seção chamada "Componente relacionado" no flyout. [Saiba mais sobre páginas de software](tvm-software-inventory.md#software-pages)

Uma página completa aparecerá com todos os detalhes de um software específico. Passe o mouse sobre o gráfico para ver a linha do tempo dos eventos para esse software específico.

![Página de software com um gráfico de linha do tempo do evento](images/tvm-event-timeline-software2.png)

Navegue até a guia linha do tempo do evento para exibir todos os eventos relacionados a esse software. Você também pode ver recomendações de segurança, vulnerabilidades descobertas, dispositivos instalados e distribuição de versão.

![Página de software com uma guia linha do tempo do evento](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Painel](tvm-dashboard-insights.md)
- [Pontuação de exposição](tvm-exposure-score.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
- [Correção de vulnerabilidades](tvm-remediation.md)
- [Inventário de software](tvm-software-inventory.md)

