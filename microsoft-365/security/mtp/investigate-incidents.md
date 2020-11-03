---
title: Investigue incidentes no Microsoft 365 defender
description: Analisar incidentes relacionados a dispositivos, usuários e caixas de correio.
keywords: incidente, incidentes, computadores, dispositivos, usuários, identidades, correio, email, caixa de correio, investigação, gráfico, evidência
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846743"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Investigue incidentes no Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**

- Microsoft 365 defender

O Microsoft 365 defender agrega todos os alertas, ativos, investigações e evidências relacionados em seus dispositivos, usuários e caixas de correio para dar a você uma visão abrangente de todo um ataque.

Investigue os alertas que afetam a sua rede, entenda o que cada um significa e agrupe as evidências associadas aos incidentes para planejar uma correção eficaz.

## <a name="investigate-an-incident"></a>Investigar um incidente

1. Selecionar um incidente na fila de incidentes. <BR> Um painel lateral abre e oferece uma visualização de informações importantes, como status, gravidade, categorias e entidades impactadas.

    ![Imagem do painel lateral do incidente](../../media/incident-side-panel.png)

2. Selecione **Abrir página do incidente**. <BR> Isso abre a página de incidentes onde você encontrará mais detalhes de incidentes de informações, comentários e ações, guias (visão geral, alertas, dispositivos, usuários, investigações, evidências).

3. Examine os alertas, dispositivos, usuários e outras entidades envolvidas no incidente.

## <a name="incident-overview"></a>Visão geral do incidente

A página da visão geral oferece uma imagem instantânea das principais coisas a serem observadas sobre o incidente.

![Imagem da página da visão geral dos incidentes](../../media/incidents-overview.png)

As categorias de ataque oferecem uma visão visual e numérica da forma como o ataque evoluiu em relação à cadeia de Kill. Da mesma forma que outros produtos de segurança da Microsoft, o Microsoft 365 defender é alinhado à estrutura [Mitre ATT&CK &trade; ](https://attack.mitre.org/) .

A seção escopo fornece uma lista dos principais ativos afetados que fazem parte desse incidente. Se houver informações específicas sobre esse ativo, como nível de risco, prioridade de investigação, além de qualquer marcação nos ativos, também virão à tona nesta seção.

A linha do tempo de alerta apresenta uma amostra da ordem cronológica da ocorrência dos alertas, bem como os motivos pelos quais esses alertas estão vinculados a esse incidente.

Em seguida, a seção de evidências apresenta um resumo de quantos artefatos diferentes foram incluídos no incidente e o status da sua correção, para saber imediatamente se você precisa executar alguma ação.

Essa visão geral pode ajudar na triagem inicial do incidente, fornecendo ideias para as principais características do incidente que você deve conhecer.

## <a name="alerts"></a>Alertas

Você pode exibir todos os alertas relacionados ao incidente e outras informações sobre eles, como gravidade, entidades que estavam envolvidas no alerta, a fonte dos alertas (Microsoft defender para identidade, Microsoft defender para ponto de extremidade, Microsoft defender para Office 365) e o motivo pelo qual foram vinculados.

![Imagem da página de alertas de incidente](../../media/incident-alerts.png)

Por padrão, os alertas são classificados em ordem cronológica, para exibir primeiro como o ataque se desenvolveu. Ao clicar em cada alerta, você será direcionado para a página alerta relevante, onde poderá realizar uma investigação profunda desse alerta.

## <a name="devices"></a>Dispositivos

A guia Dispositivos lista todos os dispositivos onde os alertas relacionados ao incidente são exibidos.

Ao clicar no nome do computador onde ocorreu o ataque, você será direcionado para a página do computador, onde poderá ver os alertas disparados e os eventos relacionados para facilitar a investigação.

![Imagem da guia Computadores de um incidente](../../media/incident-machines.png)

Selecionar a guia Linha do tempo permite percorrer a linha do tempo do computador e exibir todos os eventos e comportamentos observados no computador em ordem cronológica, intercalados com os alertas gerados.

## <a name="users"></a>Usuários

Veja os usuários identificados como parte ou relacionados a um determinado incidente.

Ao clicar no nome do usuário, você será direcionado para a página do Cloud App Security, onde poderá ser realizada uma investigação mais detalhada.

![Imagem da guia Usuários de um incidente](../../media/incident-users.png)

## <a name="mailboxes"></a>Caixas de correio

Investigue os usuários identificados como parte ou relacionados a um determinado incidente. Para realizar um trabalho mais investigativo, selecionar o alerta relacionado ao email abrirá o Microsoft defender para Office 365, onde você poderá realizar ações de correção.

![Imagem da guia Caixas de correio de um incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Investigações

Selecione **investigações** para ver todas as investigações automatizadas disparadas por alertas neste incidente. As investigações executarão ações de correção ou aguardarão a aprovação de ações do analista, dependendo de como você configurou suas investigações automatizadas para executar no Microsoft defender para o ponto de extremidade e o defender para Office 365.

![Imagem da guia Investigações de um incidente](../../media/incident-investigations.png)

Clique em uma investigação para navegar até a página Detalhes da investigação e obter informações completas sobre o status da investigação e da correção. Se houver ações pendentes para aprovação como parte da investigação, elas serão exibidas na guia ações pendentes. Executar ação como parte da correção de incidentes.

## <a name="evidence"></a>Evidências

O Microsoft 365 defender investiga automaticamente todos os eventos com suporte de incidentes e entidades suspeitas nos alertas, fornecendo respostas automáticas e informações sobre arquivos, processos, serviços, emails e muito mais importantes. Isso ajuda a detectar e bloquear rapidamente ameaças potenciais no incidente.

![Imagem da guia Evidências de um incidente](../../media/incident-evidence.png)

Cada entidade analisada será marcada com um veredicto (mal-intencionada, suspeita, limpa), bem como um status de correção. Isso ajuda a entender o status da correção de todo o incidente e quais são as próximas etapas que podem ser seguidas para continuar a correção.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Gerenciar incidentes](manage-incidents.md)

