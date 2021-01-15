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
- m365initiative-defender-office365
description: Os administradores podem saber como o treinamento de simulação de ataque no centro de segurança do Microsoft 365 afeta os funcionários e pode obter informações sobre os resultados de simulação e treinamento.
ms.openlocfilehash: c283819550872691d8dd23d3921c22cb23637633
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870950"
---
# <a name="gain-insights-through-attack-simulation-training"></a>Obter insights por meio do treinamento de simulação de Ataque

No treinamento de simulação de ataques, a Microsoft fornece informações com base nos resultados de simulações e treinamentos que os funcionários passaram. Essas informações ajudarão a mantê-lo informado sobre o progresso da prontidão contra ameaças de seus funcionários, bem como recomendará as próximas etapas para preparar melhor seus funcionários e seu ambiente para ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Estamos trabalhando continuamente para expandir as informações disponíveis para você. O impacto no comportamento e as ações recomendadas estão disponíveis no momento. Para começar, vá para o treinamento [de simulação de ataque no centro de segurança do Microsoft 365.](https://security.microsoft.com/attacksimulator?viewid=overview)

## <a name="behavior-impact-on-compromise-rate"></a>Impacto do comportamento na taxa de comprometimento

Na guia **Visão geral do** treinamento de simulação de ataque, você encontrará o impacto do comportamento no cartão de taxa **de** comprometimento. Este cartão mostra como os funcionários lidaram com as simulações que você fez em contraste com a taxa **de comprometimento prevista.** Você pode usar essas informações para controlar o progresso da prontidão contra ameaças dos funcionários executando várias simulações nos mesmos grupos de funcionários.

No gráfico, você pode ver:

- **Taxa de** comprometimento prevista que reflete a taxa média de comprometimento para simulações usando o mesmo tipo de carga em outros locatários do Microsoft 365 que usam treinamento de simulação de ataque.
- **A taxa de comprometimento** real reflete a porcentagem de funcionários que ficaram inocentados para a simulação.

Além disso, reflete a diferença entre o número real de funcionários comprometidos pelo ataque e a `<number> less susceptible to phishing` taxa de comprometimento prevista. É menos provável que esse número de funcionários seja comprometido por ataques semelhantes no futuro, enquanto indica como os funcionários fizeram em geral em contraste com a taxa de `<percent%> better than predicted rate` comprometimento prevista.

> [!div class="mx-imgBorder"]
> ![Visão geral do cartão de impacto do comportamento no treinamento de simulação de ataques](../../media/attack-sim-preview-behavior-impact-card.png)

Para ver um relatório mais detalhado, clique em Exibir simulações **e relatório de treinamento.** Esse relatório fornece as mesmas informações com contexto adicional da própria simulação (por exemplo, técnica de simulação e total de usuários direcionados).

## <a name="recommended-actions"></a>Ações recomendadas

Na guia [ **Simulações,**](https://security.microsoft.com/attacksimulator?viewid=simulations)selecionar uma simulação levará você aos detalhes da simulação, onde você encontrará a **seção Ações recomendadas.**

A seção de ações recomendadas detalha as recomendações conforme disponíveis no [Microsoft Secure Score.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) Essas recomendações são baseadas na carga usada na simulação e ajudarão você a proteger seus funcionários e seu ambiente. Clicar em cada ação de melhoria levará você aos detalhes.

> [!div class="mx-imgBorder"]
> ![Seção de ações de recomendação sobre treinamento de simulação de ataque](../../media/attack-sim-preview-recommended-actions.png)

## <a name="related-links"></a>Links relacionados

[Começar a usar o treinamento de simulação de ataque](attack-simulation-training-get-started.md)

[Criar uma simulação de ataque de phishing](attack-simulation-training.md)

[criar uma carga para treinar suas pessoas](attack-simulation-training-payloads.md)
