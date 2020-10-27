---
title: Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas
description: Obtenha informações sobre as atividades que afetaram sua pontuação segura da Microsoft. Descubra tendências e defina metas.
keywords: Pontuação segura da Microsoft, Pontuação segura, Pontuação segura do Office 365, pontuação de segurança da Microsoft, centro de segurança da Microsoft 365, ações de melhoria
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 4dfe1c9595db869a59474a030a5dd8673cf7db24
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769239"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Acompanhar o histórico de Pontuação segura da Microsoft e atingir as metas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


A [Pontuação segura da Microsoft](microsoft-secure-score.md) é uma medida da postura de segurança de uma organização, com um número maior indicando ações mais aprimoradas. Ele pode ser encontrado no https://security.microsoft.com/securescore na [central de segurança do Microsoft 365](overview-security-center.md).

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Obter informações sobre atividades que afetaram sua pontuação

Exibir um gráfico da pontuação da sua organização com o tempo na guia **histórico** .

Abaixo do gráfico está uma lista de todas as ações realizadas no intervalo de tempo selecionado e seus atributos, como pontos e categorias resultantes. Você pode personalizar um intervalo de datas e filtrar por categoria.

![Histórico de atividades](../../media/secure-score/secure-score-history-activity.png)

Se você selecionar a ação de melhoria associada a uma atividade, o submenu ação de aprimoramento completo será exibido.

Para exibir todos os históricos para essa ação de aprimoramento específica, selecione o link histórico no submenu.

![Histórico de ações de melhorias](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Descobrir tendências e definir metas

Na guia **métricas & tendências** , há vários gráficos e gráficos para dar mais visibilidade às tendências e definir metas. Você pode definir o intervalo de datas para a página inteira de visualizações. As visualizações incluem:

* **Sua zona de Pontuação segura** -personalizada com base nas metas e definições da sua organização de intervalos de pontos bons, incorretos e ruins.
* **Tendência de regressão** -uma linha do tempo de pontos que foi regressivo devido à configuração, usuário ou alteração de dispositivo.  
* **Tendência de comparação** -como a pontuação segura da sua organização se compara com as outras, com o passar do tempo. Este modo de exibição pode incluir linhas que representam a média de Pontuação de organizações com contagem de assentos semelhante e uma exibição de comparação personalizada que você pode definir.
* **Tendência de aceitação de risco** -linha do tempo de ações de aperfeiçoamento marcadas como "risco aceito".
* **Alterações de Pontuação** -o número de pontos alcançados, pontos redefinidos, juntamente com a pontuação subsequente mudar, no intervalo de datas especificado.

### <a name="compare-your-score-to-organizations-like-yours"></a>Comparar sua pontuação com organizações como a sua

Há dois lugares para ver como sua pontuação se compara a organizações que são semelhantes a você. Em ambos os gráficos, você pode selecionar **gerenciar comparações** para exibir e editar as informações da sua organização. Você também pode criar uma comparação personalizada com base no setor, no tamanho da organização, nas licenças e nas regiões.

#### <a name="comparison-bar-chart"></a>Gráfico de barra de comparação

O gráfico de barra de comparação é a guia **visão geral** . Passe o mouse sobre o gráfico para exibir a oportunidade de Pontuação e pontuação. Os dados de comparação são mantidos para que não saiba exatamente quais outros locatários estão no mix.

![Gráfico de barras de pontos semelhantes da organização](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizações como a sua** : fornecemos uma pontuação média de outros locatários (desde que haja pelo menos 5 ou mais locatários a serem comparados) que se qualificam com os seguintes critérios:
    1. Mesmo setor
    2. Mesmo tamanho de organização
    3. Todas as regiões
    4. Os produtos da Microsoft usados são 80% semelhantes
    5. Oportunidade (a pontuação máxima que pode ser alcançada pela licença atual) dentro de um intervalo de 20% do locatário

- **Comparação personalizada** : deve ser configurada primeiro selecionando **gerenciar comparação** (somente se encontrarmos 5 ou mais locatários) com base nos seguintes critérios:
    1. Setor (es) selecionado (s)
    2. Tamanho (s) da organização selecionado (s)
    3. Região (s) selecionada (s)
    4. Licença (s) selecionada (s)
    5. Os produtos da Microsoft usados são 80% semelhantes
    6. Oportunidade (a pontuação máxima que pode ser alcançada pela licença atual) dentro de um intervalo de 20% do locatário

Se você não fez uma seleção para a seleção personalizada do resultado da seleção para ter menos de cinco locatários que possamos comparar, verá "não está disponível devido a dados limitados".

#### <a name="comparison-trend"></a>Tendência de comparação

Na guia **métricas & tendências** , veja como a pontuação segura da sua organização é comparada com o tempo.

![Gráfico de linhas de pontuações semelhantes da organização ao longo do tempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, fale conosco postando na Comunidade [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Pontuação segura da Microsoft](microsoft-secure-score.md)
- [Avaliar sua postura de segurança](microsoft-secure-score-improvement-actions.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
- [Novidades](microsoft-secure-score-whats-new.md)
