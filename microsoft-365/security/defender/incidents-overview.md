---
title: Incidentes no Microsoft 365 Defender
description: Investigue incidentes vistos em dispositivos, usuários e caixas de correio no centro de segurança do Microsoft 365.
keywords: incidentes, alertas, investigar, analisar, responder, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939571"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).
>

Um incidente no Microsoft 365 Defender é uma coleção de alertas correlacionados e dados associados que comentam a história de um ataque. 

Os serviços e aplicativos do Microsoft 365 criam alertas quando detectam um evento ou atividade suspeito ou mal-intencionado. Alertas individuais fornecem dicas valiosas sobre um ataque concluído ou contínuo. No entanto, os ataques geralmente empregam várias técnicas contra diferentes tipos de entidades, como dispositivos, usuários e caixas de correio. O resultado são vários alertas para várias entidades em seu locatário. 

Como reunir os alertas individuais para obter informações sobre um ataque pode ser desafiador e demorado, o Microsoft 365 Defender agrega automaticamente os alertas e suas informações associadas a um incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Como o Microsoft 365 Defender correlaciona eventos de entidades em um incidente":::

Assista a esta breve visão geral dos incidentes no Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Agrupar alertas relacionados a um incidente oferece uma visão abrangente de um ataque. Por exemplo, você pode ver:

- Onde o ataque começou.
- Quais táticas foram usadas.
- Até que ponto o ataque foi para o seu locatário.
- O escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados. 
- Todos os dados associados ao ataque.

Se [habilitado, o](m365d-enable.md)Microsoft 365 Defender pode investigar e resolver alertas automaticamente por meio da automação e da inteligência artificial. Você também pode executar etapas de correção adicionais para resolver o ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidentes e alertas no centro de segurança do Microsoft 365

Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="A página Incidentes no centro de segurança do Microsoft 365":::

Selecionar um nome de incidente exibe um resumo do incidente e fornece acesso a guias com informações adicionais.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro de segurança do Microsoft 365":::

As guias adicionais para um incidente são:

- Alertas 

  Todos os alertas relacionados ao incidente e suas informações.

- Dispositivos

  Todos os dispositivos que foram identificados para fazer parte ou relacionados ao incidente.

- Usuários

  Todos os usuários identificados para fazer parte ou relacionados ao incidente.

- Caixas de correio

  Todas as caixas de correio identificadas para fazer parte ou relacionadas ao incidente.

- Investigações

  Todas as investigações automatizadas disparadas por alertas no incidente.

- Evidências e resposta

  Todos os eventos com suporte e entidades suspeitas nos alertas no incidente.

Aqui está a relação entre um incidente e seus dados e as guias de um incidente no centro de segurança do Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="A relação de um incidente e seus dados com as guias de um incidente no centro de segurança do Microsoft 365":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Exemplo de fluxo de trabalho de resposta a incidentes para o Microsoft 365 Defender

Veja um exemplo de fluxo de trabalho para responder a incidentes no Microsoft 365 com o centro de segurança do Microsoft 365.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exemplo de um fluxo de trabalho de resposta a incidentes para o Microsoft 365":::

Em uma base contínua, identifique os incidentes de maior prioridade para análise e resolução na fila de incidentes e prepare-os para resposta. Esta é uma combinação de:

- [Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.
- [Gerenciando](manage-incidents.md) incidentes modificando seu título, atribuindo-os a um analista e adicionando marcas e comentários.

1. Para cada incidente, inicie uma análise [de ataque e alerta:](investigate-incidents.md)

   a. Exibir o resumo do incidente para entender seu escopo e gravidade e quais entidades são afetadas (a **guia Resumo).**

   b. Comece a analisar os alertas para entender sua origem, escopo e gravidade (a **guia Alertas).**

   c. Conforme necessário, reúna informações sobre dispositivos, usuários e caixas de correio afetados (as guias **Dispositivos,** **Usuários** e **Caixas** de Correio).

   d. Veja como o Microsoft 365 Defender resolveu automaticamente alguns alertas (a guia **Investigações).**
   
   e. Conforme necessário, use informações no conjunto de dados do incidente para obter mais informações (a **guia Evidências e Resposta).**

2. Após ou durante sua análise, contenção de endereços para reduzir qualquer impacto adicional do ataque e da erradicação da ameaça de segurança.

3. O máximo possível, recupere-se do ataque restaurando os recursos do locatário para o estado em que estavam antes do incidente.

4. [Resolver](manage-incidents.md#resolve-incident) o incidente e levar tempo para o aprendizado pós-incidente para:

   - Entenda o tipo de ataque e seu impacto.
   - Pesquise o ataque [no Threat Analytics](threat-analytics.md) e na comunidade de segurança para uma tendência de ataque de segurança.
   - Lembre-se do fluxo de trabalho usado para resolver o incidente e atualizar seus fluxos de trabalho, processos, políticas e playbooks padrão conforme necessário.
   - Determine se as alterações na configuração de segurança são necessárias e implementá-las.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Exemplo de operações de segurança para o Microsoft 365 Defender

Veja um exemplo de operações de segurança para o Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Um exemplo de operações de segurança para o Micosoft 365 Defender":::

Tarefas diárias podem incluir:

- [Gerenciando](manage-incidents.md) incidentes
- Revisão de [ações automatizadas de investigação e resposta (AIR)](m365d-action-center.md)
- Revisão da análise de [ameaças mais recente](threat-analytics.md)
- [Respondendo](investigate-incidents.md) a incidentes

As tarefas mensais podem incluir:

- Revisão das [configurações do AIR](m365d-configure-auto-investigation-response.md)
- Revisão da [pontuação segura](microsoft-secure-score-improvement-actions.md) e [do & gerenciamento de vulnerabilidades](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Relatórios para sua cadeia de gerenciamento de segurança de IT

As tarefas trimestrais podem incluir um relatório e uma reunião de resultados de segurança para o Diretor de Segurança da Informação (CISO).

As tarefas anuais podem incluir a realização de um grande incidente ou exercício de violação para testar sua equipe, sistemas e processos. 

Tarefas diárias, mensais, trimestrais e anuais podem ser usadas para atualizar ou refinar processos, políticas e configurações de segurança.

## <a name="next-steps"></a>Próximas etapas

A fila de **incidentes da página Incidentes** lista os incidentes mais recentes. A partir daqui, você pode:

- Confira quais incidentes devem ser [priorizados](incident-queue.md) com base na gravidade e em outros fatores. 
- [Gerenciar incidentes](manage-incidents.md), que inclui renomeação, atribuição, classificação e adição de marcas e comentários para o fluxo de trabalho de gerenciamento de incidentes.
- Execute uma [análise](investigate-incidents.md) de um incidente.
