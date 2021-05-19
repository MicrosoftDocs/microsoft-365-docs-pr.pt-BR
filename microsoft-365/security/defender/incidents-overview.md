---
title: Incidentes no Microsoft 365 Defender
description: Investigue incidentes vistos em dispositivos, usuários e caixas de correio no centro Microsoft 365 segurança.
keywords: incidentes, alertas, investigar, analisar, resposta, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365, resposta a incidentes, ataques cibernéticos
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
ms.openlocfilehash: cc2fcd7410c2f3122fb3ce49a40e93bfa0767331
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539018"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).
>

Um incidente no Microsoft 365 Defender é uma coleção de alertas correlacionados e dados associados que comentam a história de um ataque. 

Microsoft 365 serviços e aplicativos criam alertas quando detectam um evento ou atividade suspeito ou mal-intencionado. Alertas individuais fornecem dicas valiosas sobre um ataque concluído ou contínuo. No entanto, os ataques geralmente empregam várias técnicas contra diferentes tipos de entidades, como dispositivos, usuários e caixas de correio. O resultado são vários alertas para várias entidades em seu locatário. 

Como reunir os alertas individuais para obter informações sobre um ataque pode ser desafiador e demorado, o Microsoft 365 Defender agrega automaticamente os alertas e suas informações associadas a um incidente.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Como Microsoft 365 Defender correlaciona eventos de entidades em um incidente":::

Assista a esta breve visão geral dos incidentes Microsoft 365 Defender (4 minutos).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Agrupar alertas relacionados a um incidente oferece uma visão abrangente de um ataque. Por exemplo, você pode ver:

- Onde o ataque começou.
- Quais táticas foram usadas.
- Até que ponto o ataque foi para o seu locatário.
- O escopo do ataque, como quantos dispositivos, usuários e caixas de correio foram afetados. 
- Todos os dados associados ao ataque.

Se [habilitado, o](m365d-enable.md)Microsoft 365 Defender pode investigar [e resolver](m365d-autoir.md) alertas automaticamente por meio da automação e da inteligência artificial. Você também pode executar etapas de correção adicionais para resolver o ataque. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidentes e alertas no centro Microsoft 365 segurança

Você gerencia incidentes de **incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="A página Incidentes no centro Microsoft 365 segurança":::

Selecionar um nome de incidente exibe um resumo do incidente e fornece acesso a guias com informações adicionais.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro Microsoft 365 segurança":::

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

  Todas as [investigações automatizadas](m365d-autoir.md) disparadas por alertas no incidente.

- Evidências e resposta

  Todos os eventos com suporte e entidades suspeitas nos alertas no incidente.

- Graph (em visualização)

  Uma figura mostrando a conexão de alertas aos ativos afetados em sua organização.

Aqui está a relação entre um incidente e seus dados e as guias de um incidente no centro Microsoft 365 segurança.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="A relação de um incidente e seus dados com as guias de um incidente no Microsoft 365 de segurança":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a>Exemplo de fluxo de trabalho de resposta a incidentes Microsoft 365 Defender

Aqui está um exemplo de fluxo de trabalho para responder a incidentes em Microsoft 365 com o centro de Microsoft 365 de segurança.

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Exemplo de um fluxo de trabalho de resposta a incidentes para Microsoft 365":::

Em uma base contínua, identifique os incidentes de maior prioridade para análise e resolução na fila de incidentes e prepare-os para resposta. Esta é uma combinação de:

- [Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.
- [Gerenciando](manage-incidents.md) incidentes modificando seu título, atribuindo-os a um analista e adicionando marcas e comentários.

1. Para cada incidente, inicie uma investigação e análise de ataques [e alertas:](investigate-incidents.md)
 
   a. Exibir o resumo do incidente para entender seu escopo e gravidade e quais entidades são afetadas (a **guia Resumo).**

   b. Comece a analisar os alertas para entender sua origem, escopo e gravidade (a **guia Alertas).**

   c. Conforme necessário, reúna informações sobre dispositivos, usuários e caixas de correio afetados (as guias **Dispositivos,** **Usuários** e **Caixas** de Correio).

   d. Veja como Microsoft 365 o Defender [resolveu automaticamente alguns alertas](m365d-autoir.md) (a **guia Investigações).**
   
   e. Conforme necessário, use informações no conjunto de dados do incidente para obter mais informações (a **guia Evidências e Resposta).**

2. Após ou durante sua análise, execute a contenção para reduzir qualquer impacto adicional do ataque e da erradicação da ameaça de segurança.

3. O máximo possível, recupere-se do ataque restaurando os recursos do locatário para o estado em que estavam antes do incidente.

4. [Resolver](manage-incidents.md#resolve-an-incident) o incidente e levar tempo para o aprendizado pós-incidente para:

   - Entenda o tipo de ataque e seu impacto.
   - Pesquise o ataque [no Threat Analytics](threat-analytics.md) e na comunidade de segurança para uma tendência de ataque de segurança.
   - Lembre-se do fluxo de trabalho usado para resolver o incidente e atualizar seus fluxos de trabalho, processos, políticas e playbooks padrão conforme necessário.
   - Determine se as alterações na configuração de segurança são necessárias e implementá-las.

Se você for novo na [](incidents-overview.md) análise de segurança, consulte a introdução para responder ao seu primeiro incidente para obter informações adicionais e passar por um incidente de exemplo.

## <a name="example-security-operations-for-microsoft-365-defender"></a>Exemplo de operações de segurança para Microsoft 365 Defender

Veja um exemplo de operações de segurança para o Microsoft 365 Defender.

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Um exemplo de operações de segurança para Microsoft 365 Defender":::

Tarefas diárias podem incluir:

- [Gerenciando](manage-incidents.md) incidentes
- Revisão de ações automatizadas de investigação e resposta [(AIR)](m365d-action-center.md) no Centro de Ações
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

**Se você for novo na** análise de segurança e na resposta a incidentes:

- Consulte o [passo](first-incident-overview.md) a passo Responder ao seu primeiro incidente para obter uma visita guiada de um processo típico de análise, correção e revisão pós-incidente no centro de segurança Microsoft 365 com um exemplo de ataque.

**Se você tiver experiência com** análise de segurança e resposta a incidentes:

- Começar com a fila de incidentes da página **Incidentes** do centro Microsoft 365 segurança. A partir daqui, você poderá:

  - Confira quais incidentes devem ser [priorizados](incident-queue.md) com base na gravidade e em outros fatores. 

  - [Gerencie incidentes](manage-incidents.md), que inclui renomeação, atribuição, classificação e adição de marcas e comentários com base no fluxo de trabalho de gerenciamento de incidentes.

  - Realize [investigações](investigate-incidents.md) de incidentes.

- Consulte estes [playbooks de resposta](https://docs.microsoft.com/security/compass/incident-response-playbooks) a incidentes para obter orientações detalhadas sobre phishing, pulverização de senha e ataques de concessão de consentimento do aplicativo.

