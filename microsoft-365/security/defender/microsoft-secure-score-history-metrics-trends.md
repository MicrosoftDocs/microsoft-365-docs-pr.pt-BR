---
title: Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas
description: Obtenha informações sobre atividades que afetaram sua Pontuação Segura da Microsoft. Descobrir tendências e definir metas.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.technology: m365d
ms.openlocfilehash: e97ec0c970ed767edd30419c14db8b1073da64c8
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571027"
---
# <a name="track-your-microsoft-secure-score-history-and-meet-goals"></a>Rastrear seu histórico de Pontuação Segura da Microsoft e cumprir metas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[A Pontuação Segura](microsoft-secure-score.md) da Microsoft é uma medida da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria tomadas. Ele pode ser encontrado no centro de segurança do https://security.microsoft.com/securescore [Microsoft 365.](overview-security-center.md)

## <a name="gain-insights-into-activity-that-has-affected-your-score"></a>Obtenha informações sobre atividades que afetaram sua pontuação

Exibir um gráfico da pontuação da sua organização ao longo do tempo na **guia Histórico.**

Abaixo do gráfico está uma lista de todas as ações realizadas no intervalo de tempo selecionado e seus atributos, como pontos resultantes e categoria. Você pode personalizar um intervalo de datas e filtrar por categoria.

![Histórico de atividades](../../media/secure-score/secure-score-history-activity.png)

Se você selecionar a ação de melhoria associada a uma atividade, o flyout de ação de melhoria total aparecerá.

Para exibir todo o histórico dessa ação de melhoria específica, selecione o link histórico no flyout.

![Histórico de ações de melhoria](../../media/secure-score/secure-score-history-flyout.png)

## <a name="discover-trends-and-set-goals"></a>Descobrir tendências e definir metas

Na guia **Métricas & tendências,** há vários gráficos e gráficos para dar mais visibilidade às tendências e definir metas. Você pode definir o intervalo de datas para toda a página de visualizações. As visualizações incluem:

* **Sua zona de Pontuação** Segura – Personalizada com base nas metas e definições de intervalos de pontuação boas, ok e ruins da sua organização.
* **Tendência de regressão** - Uma linha do tempo de pontos que foram regredidas devido às alterações de configuração, usuário ou dispositivo.  
* **Tendência de comparação** - Como a Pontuação Segura da sua organização se compara à dos outros ao longo do tempo. Esse modo de exibição pode incluir linhas que representam a média de pontuação das organizações com contagem de assentos semelhante e uma exibição de comparação personalizada que você pode definir.
* **Tendência de aceitação de risco** - Linha do tempo das ações de melhoria marcadas como "risco aceito".
* **Alterações na** pontuação - O número de pontos atingidos, pontos regredidos e alterações na pontuação no intervalo de datas especificado.

### <a name="compare-your-score-to-organizations-like-yours"></a>Comparar sua pontuação com organizações como a sua

Há dois lugares para ver como sua pontuação se compara a organizações semelhantes a você. Em ambos os **gráficos,** você pode selecionar Gerenciar comparações para exibir e editar as informações da sua organização. Você também pode criar uma comparação personalizada com base no setor, tamanho da organização, licenças e regiões.

#### <a name="comparison-bar-chart"></a>Gráfico de barras de comparação

O gráfico da barra de comparação é a guia **Visão** geral. Passe o mouse sobre o gráfico para exibir a oportunidade de pontuação e pontuação. Os dados de comparação são anonimizados, portanto, não sabemos exatamente quais outros locatários estão na mistura.

![Gráfico de barras de pontuações semelhantes da organização](../../media/secure-score/secure-score-comparison-bar.png)

- **Organizações como** a sua : uma pontuação média de outros locatários (desde que temos pelo menos cinco ou mais locatários para comparar) que se qualificam com os seguintes critérios:
    1. Mesmo setor
    2. Mesmo tamanho da organização
    3. Todas as regiões
    4. Os produtos da Microsoft usados são 80% semelhantes
    5. Oportunidade (pontuação máxima que pode ser atingida pela licença atual) em um intervalo de 20% do seu locatário

- **Comparação Personalizada**: precisa ser configurada selecionando **Gerenciar Comparação** com base nos seguintes critérios:
    1. Setor selecionado
    2. Tamanhos da organização selecionados
    3. Região selecionada
    4. Licenças selecionadas
    5. Os produtos da Microsoft usados são 80% semelhantes
    6. Oportunidade (pontuação máxima que pode ser atingida pela licença atual) em um intervalo de 20% do seu locatário

Se você tiver feito uma seleção personalizada, mas os resultados têm menos de cinco outros locatários que podemos comparar, você verá "Não disponível devido a dados limitados".

#### <a name="comparison-trend"></a>Tendência de comparação

Na guia **Métricas & tendências,** veja como a Pontuação Segura da sua organização se compara com a dos outros ao longo do tempo.

![Gráfico de linha das pontuações da organização semelhantes ao longo do tempo](../../media/secure-score/secure-score-comparison-trend.png)

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver algum problema, nos avise postando na comunidade [Segurança, Privacidade & Conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos monitorando a comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Pontuação Segura da Microsoft](microsoft-secure-score.md)
- [Avaliar postura de segurança](microsoft-secure-score-improvement-actions.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
- [Novidades](microsoft-secure-score-whats-new.md)
