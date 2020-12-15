---
title: Obter insights por meio do treinamento de simulação de Ataque
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem aprender como o treinamento de simulação de ataque no centro de segurança do Microsoft 365 afeta os funcionários e pode obter informações sobre os resultados de simulação e treinamento.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667584"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obter insights por meio do treinamento de simulação de Ataque

Dentro do treinamento de simulação de ataques, a Microsoft fornece ideias com base em resultados de simulações e treinamentos que os funcionários passaram. Esses insights ajudarão você a se informar sobre o andamento da prontidão da ameaça de seus funcionários, além de recomendar as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Estamos trabalhando continuamente para expandir os insights que estão disponíveis para você. O impacto do comportamento e as ações recomendadas estão disponíveis no momento. Para começar, vá para [o treinamento de simulação de ataque no centro de segurança do Microsoft 365](https://security.microsoft.com/attacksimulator?viewid=overview).

## <a name="behavior-impact-on-compromise-rate"></a>Impacto do comportamento na taxa de comprometimento

Na guia **visão geral** do treinamento de simulação de ataque, você encontrará o **impacto do comportamento no cartão de Tarifa de comprometimento** . Este cartão mostra como os funcionários lidar com as simulações que você executou em comparação com a **taxa de comprometimento prevista**. Você pode usar esses percepções para acompanhar o progresso da prontidão de ameaças dos funcionários, executando várias simulações em relação aos mesmos grupos de funcionários.

No gráfico, você pode ver:

- **Taxa de comprometimento prevista** que reflete a taxa de comprometimento média de simulações usando o mesmo tipo de carga em outros locatários do Microsoft 365 que usam o treinamento de simulação de ataque.
- **Taxa de comprometimento real** reflete a porcentagem de funcionários que foram desefetivados para a simulação.

Além disso, `<number> less susceptible to phishing` reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a taxa de comprometimento prevista. Esse número de funcionários é menos provável de ser comprometido por ataques similares no futuro, enquanto `<percent%> better than predicted rate` indica como os funcionários faziam o total em comparação com a taxa de comprometimento prevista.

> [!div class="mx-imgBorder"]
> ![Cartão de impacto de comportamento na simulação de ataque visão geral do treinamento](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver um relatório mais detalhado, clique em **Exibir relatório de eficácia de simulações e treinamento**. Este relatório fornece as mesmas informações com contexto adicional da simulação (por exemplo, técnica de simulação e total de usuários direcionados).

## <a name="recommended-actions"></a>Ações recomendadas

Na guia [ **Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations), selecionando uma simulação o levará para os detalhes de simulação, onde você encontrará a seção **ações recomendadas** .

A seção de ações recomendadas detalha as recomendações, conforme disponível na [Pontuação segura da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score). Essas recomendações são baseadas na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente. Ao clicar em cada ação de melhoria, você terá seus detalhes.

> [!div class="mx-imgBorder"]
> ![Seção ações de recomendação no treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Links relacionados

**Simulador de ataque** [crie uma simulação de ataque de phishing](attack-simulation-training.md) e [crie uma carga para treinar suas pessoas](attack-simulation-training-payloads.md)
