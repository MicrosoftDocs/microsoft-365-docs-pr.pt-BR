---
title: Investigar alertas no Microsoft 365 Defender
description: Investigue alertas vistos em dispositivos, usuários e caixas de correio.
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651339"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Investigar alertas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Os alertas são a base de todos os incidentes e indicam a ocorrência de eventos mal-intencionados ou suspeitos em seu ambiente. Os alertas geralmente fazem parte de um ataque mais amplo e fornecem pistas sobre um incidente.

No Microsoft 365 Defender, alertas relacionados são agregados juntos a [incidentes de formulário.](incidents-overview.md) Os incidentes sempre fornecerão o contexto mais amplo de um ataque, no entanto, a análise de alertas pode ser valiosa quando uma análise mais profunda é necessária. 

A **fila Alertas** mostra o conjunto atual de alertas. Você pode chegar à fila de alertas de **Incidentes & alertas** > alertas sobre o início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Exemplo da fila de alertas":::

Alertas de diferentes soluções de segurança da Microsoft, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Defender para Office 365 e Microsoft 365 Defender aparecem aqui.

Por padrão, a fila de alertas no centro de segurança Microsoft 365 exibe os alertas novos e em andamento dos últimos 30 dias. O alerta mais recente está na parte superior da lista para que você possa vê-lo primeiro. 

Na fila de alertas padrão, você pode selecionar **Filtros** para ver um painel **Filtros,** do qual você pode especificar um subconjunto dos alertas. Veja um exemplo.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Exemplo do painel filtros para a fila de alertas":::

Você pode filtrar alertas de acordo com estes critérios:

- Severity
- Status
- Categoria
- Fonte de detecção
- Tags
- Política
- Ativos afetados

## <a name="analyze-an-alert"></a>Analisar um alerta

Para ver a página de alerta principal, selecione o nome do alerta. Veja um exemplo.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exemplo da página de detalhes de um alerta no centro Microsoft 365 segurança":::

Você também pode selecionar **a ação Abrir a página de alerta** principal no painel **Gerenciar** alerta.

Uma página de alerta é composta por estas seções: 

- História do alerta, que é a cadeia de eventos e alertas relacionados a esse alerta em ordem cronológica
- Detalhes de resumo

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Exemplo da página de detalhes de um alerta no centro Microsoft 365 segurança":::

Ao longo de uma página de alerta, você pode selecionar as regiões (**...**) ao lado de qualquer entidade para ver ações disponíveis, como abrir a página de alerta ou vincular o alerta a outro incidente.

### <a name="analyze-affected-assets"></a>Analisar ativos afetados

A **seção Ações realizadas** tem uma lista de ativos afetados, como caixas de correio, dispositivos e usuários afetados por esse alerta. 

Você também pode selecionar **Exibir no centro de** ações para exibir a guia **Histórico** do **Centro** de Ações no centro de Microsoft 365 de segurança. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Rastrear a função de um alerta no artigo de alerta

O artigo de alerta exibe todos os ativos ou entidades relacionados ao alerta em uma exibição de árvore de processo. O alerta no título é aquele em foco quando você aterra pela primeira vez na página do alerta selecionado. Os ativos no artigo de alerta são expansíveis e clicáveis. Eles fornecem informações adicionais e aceleram sua resposta permitindo que você tome medidas imediatamente no contexto da página de alerta. 

> [!NOTE]
> A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.

### <a name="view-more-alert-information-on-the-details-page"></a>Exibir mais informações de alerta na página de detalhes

A página de detalhes mostra os detalhes do alerta selecionado, com detalhes e ações relacionadas a ele. Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alerta, a página de detalhes será mudada para fornecer informações contextuais e ações para o objeto selecionado.

Depois de selecionar uma entidade de interesse, a página de detalhes muda para exibir informações sobre o tipo de entidade selecionado, informações históricas quando ela estiver disponível e opções para tomar medidas nessa entidade diretamente na página de alerta.

## <a name="manage-alerts"></a>Gerenciar alertas

Para gerenciar um alerta, selecione o alerta na fila de alertas em sua linha para ver um **painel Gerenciar** alerta. Veja um exemplo.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Exemplo do painel de resumo para um alerta":::

O **painel Gerenciar** alerta permite que você especifique:

- O status do alerta (Novo, Resolvido, Em andamento).
- A classificação do alerta (Não definido, Alerta Verdadeiro, Alerta Falso).
- Para a classificação como um alerta verdadeiro, o tipo de ameaça para o alerta no campo **Determinação.**
- Um comentário sobre o alerta.

> [!NOTE]
> Uma maneira de gerenciar o alerta por meio do uso de marcas. O recurso de marcação do Microsoft Defender para Office 365 está sendo gradualmente lançado e está atualmente em visualização. <br>
> Atualmente, os nomes de marcas modificadas só são aplicados a alertas criados *após* a atualização. Alertas gerados antes da modificação não refletirão o nome da marca atualizado. 

Neste painel, você também pode executar estas ações adicionais: 

- Abra a página de alerta principal
- Consultar um especialista em ameaças da Microsoft
- Exibir envio
- Link para outro incidente
- Consulte o alerta em uma linha do tempo
- Criar uma regra de supressão

Veja um exemplo.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Exemplo das ações em um alerta no centro Microsoft 365 segurança":::

A lista de ações adicionais depende do tipo de alerta.

## <a name="resolve-an-alert"></a>Resolver um alerta

Depois de terminar de analisar um alerta e ele  puder ser resolvido, vá para o  painel Gerenciar alerta para o alerta e marque o status dele como Resolvido e classifique-o como um alerta **False** ou **Alerta** True. Para alertas verdadeiros, especifique o tipo de ameaça do alerta no campo **Determinação.**

Classificar alertas e especificar sua determinação ajuda a ajustar o Microsoft 365 Defender para fornecer alertas mais verdadeiros e menos alertas falsos.

## <a name="next-steps"></a>Próximas etapas

Conforme necessário para incidentes no processo, continue sua [investigação](investigate-incidents.md).

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Gerenciar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)
