---
title: Investigar incidentes em Microsoft 365 Defender
description: Investigue incidentes relacionados a dispositivos, usuários e caixas de correio.
keywords: incidentes, incidentes, análise, resposta, máquinas, dispositivos, usuários, identidades, email, email, caixa de correio, investigação, gráfico, evidência
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105351"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Investigar incidentes em Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

Microsoft 365 Defender agrega todos os alertas, ativos, investigações e evidências relacionados de todos os dispositivos, usuários e caixas de correio em um incidente para dar uma olhada abrangente na amplitude de um ataque.

Em um incidente, você analisa os alertas que afetam sua rede, entende o que significam e cola as evidências para que você possa planejar um plano de correção eficaz.

## <a name="initial-investigation"></a>Investigação inicial

Antes de mergulhar nos detalhes, confira as propriedades e o resumo do incidente.

Você pode começar selecionando o incidente na coluna marca de seleção. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Exemplo de seleção de um incidente na coluna marca de verificação":::

Quando você faz isso, um painel de resumo é aberto com informações importantes sobre o incidente, como gravidade, a quem ele é atribuído, e as categorias de CK do [MITRE ATT &trade; ](https://attack.mitre.org/)&CK para o incidente. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Exemplo do painel de resumo de um incidente":::

A partir daqui, você pode selecionar **Abrir página de incidentes**. Isso abre a página principal do incidente em que você encontrará mais informações resumidas e guias para alertas, dispositivos, usuários, investigações e evidências.

Você também pode abrir a página principal de um incidente selecionando o nome do incidente na fila de incidentes.

## <a name="summary"></a>Resumo

A **página** Resumo fornece um resumo das principais coisas a observar sobre o incidente.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Exemplo da página Resumo de um incidente no centro Microsoft 365 segurança":::

As categorias de ataque dão a você uma visão visual e numérica de como o ataque avançou contra a cadeia de kill. Assim como com outros produtos de segurança da Microsoft, Microsoft 365 Defender está alinhado à estrutura de CK do [MITRE ATT&&trade; CK.](https://attack.mitre.org/)

A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente. Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.

A linha do tempo de alertas fornece uma prévia da ordem cronológica na qual os alertas ocorreram, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.

E por último - a seção de evidências fornece um resumo de quantos artefatos diferentes foram incluídos no incidente e seu status de correção, para que você possa identificar imediatamente se qualquer ação é necessária por você.

Essa visão geral pode ajudar na triagem inicial do incidente fornecendo informações sobre as principais características do incidente que você deve estar ciente.

## <a name="alerts"></a>Alertas

Na guia **Alerta,** você pode exibir a fila de alertas para alertas relacionados ao incidente e outras informações sobre eles, como:

- Severidade.
- As entidades envolvidas no alerta.
- A origem dos alertas (Microsoft Defender para Identidade, Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365).
- O motivo pelo qual eles foram vinculados.

Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Exemplo de uma página Alertas para um incidente":::

Por padrão, os alertas são ordenados cronologicamente para permitir que você veja como o incidente ocorreu ao longo do tempo. Quando você seleciona um alerta dentro de um incidente, Microsoft 365 Defender exibe as informações de alerta específicas para o contexto do incidente geral. 

Você pode ver os eventos do alerta, quais outros alertas disparados causaram o alerta atual e todas as entidades e atividades afetadas envolvidas no ataque, incluindo arquivos, usuários e caixas de correio.

Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Exemplo de uma página de detalhes de alerta dentro de um incidente":::

Esta página de alerta de incidente é composta por estas seções:

- História do alerta, que inclui um resumo do que aconteceu
- Eventos e alertas relacionados
- Detalhes de resumo

Saiba como usar a fila de alertas e as páginas de alerta em [alertas de investigação.](investigate-alerts.md)

## <a name="devices"></a>Dispositivos

A **guia Dispositivos** lista todos os dispositivos relacionados ao incidente. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Exemplo de uma página Dispositivos para um incidente":::

Você pode selecionar a marca de seleção de um dispositivo para ver detalhes do dispositivo, dados de diretório, alertas ativos e usuários conectados. Selecione o nome do dispositivo para ver detalhes do dispositivo no inventário de dispositivos do Microsoft Defender for Endpoints.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Exemplo de uma página de dispositivos do Microsoft Defender para Pontos de Extremidade":::

Na página do dispositivo, você pode coletar informações adicionais sobre o dispositivo, como todos os alertas, uma linha do tempo e recomendações de segurança. Por exemplo,  na guia Linha do Tempo, você pode rolar pela linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.

> [!TIP]
> Você pode fazer verificações sob demanda em uma página de dispositivo. No centro de Microsoft 365 de segurança, escolha **Pontos de extremidade > Inventário de dispositivos**. Selecione um dispositivo que tenha alertas e execute uma verificação antivírus. Ações, como verificações de antivírus, são controladas e ficam visíveis na página **Inventário de** dispositivos. Para saber mais, confira [Executar Microsoft Defender Antivírus verificação em dispositivos](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).

## <a name="users"></a>Usuários

A **guia** Usuários lista todos os usuários que foram identificados para fazer parte ou relacionados ao incidente. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

Você pode selecionar a marca de seleção de um usuário para ver detalhes da ameaça, exposição e informações de contato da conta de usuário. Selecione o nome de usuário para ver detalhes adicionais da conta de usuário.

Saiba como exibir informações adicionais do usuário e gerenciar os usuários de um incidente na [investigação de usuários](investigate-users.md).


## <a name="mailboxes"></a>Caixas de correio

A **guia Caixas de** Correio lista todas as caixas de correio identificadas como parte ou relacionadas ao incidente. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Exemplo de uma página de Caixas de Correio para um incidente":::

Você pode selecionar a marca de seleção de uma caixa de correio para ver uma lista de alertas ativos. Selecione o nome da caixa de correio para ver detalhes adicionais da caixa de correio na página Explorer do Microsoft Defender para Office 365.

## <a name="investigations"></a>Investigações

A **guia Investigações** lista todas [as investigações automatizadas](m365d-autoir.md) disparadas por alertas neste incidente. As investigações executarão ações de correção ou aguardarão a aprovação de ações do analista, dependendo de como você configurou suas investigações automatizadas para executar no Microsoft Defender para Ponto de Extremidade e Defender para Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Exemplo de uma página Investigações para um incidente":::

Selecione uma investigação para navegar até sua página de detalhes para obter informações completas sobre o status da investigação e correção. Se houver ações pendentes para aprovação como parte da investigação, elas aparecerão na guia Histórico de ações **pendentes.** Tome medidas como parte da correção de incidentes.

Há também uma guia **Gráfico de Investigação** que mostra:

- A conexão de alertas com os ativos afetados em sua organização.
- Quais entidades estão relacionadas a quais alertas e como eles fazem parte da história do ataque.
- Os alertas do incidente.

O gráfico de investigação ajuda você a entender rapidamente o escopo completo do ataque conectando as diferentes entidades suspeitas que fazem parte do ataque com seus ativos relacionados, como usuários, dispositivos e caixas de correio. 

Para obter mais informações, consulte [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).

## <a name="evidence-and-response"></a>Evidências e resposta

A **guia Evidências e Resposta** mostra todos os eventos com suporte e entidades suspeitas nos alertas do incidente. Veja um exemplo.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Exemplo de uma página evidências e resposta para um incidente":::

Microsoft 365 Defender investiga automaticamente todos os eventos com suporte dos incidentes e entidades suspeitas nos alertas, fornecendo informações sobre os emails importantes, arquivos, processos, serviços, endereços IP e muito mais. Isso ajuda você a detectar e bloquear rapidamente possíveis ameaças no incidente.

Cada uma das entidades analisadas é marcada com um veredito (Mal-intencionado, suspeito, limpo) e um status de correção. Isso ajuda você a entender o status de correção de todo o incidente e quais próximas etapas podem ser tomadas.

## <a name="next-steps"></a>Próximas etapas

Conforme necessário:

- [Investigar os alertas de um incidente](investigate-alerts.md)
- [Investigar os usuários de um incidente](investigate-users.md)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Gerenciar incidentes](manage-incidents.md)

