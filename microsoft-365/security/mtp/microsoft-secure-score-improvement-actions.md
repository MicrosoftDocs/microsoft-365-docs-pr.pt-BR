---
title: Avaliar a postura de segurança por meio do Microsoft Secure Score
description: Descreve como tomar medidas para melhorar o Microsoft Secure Score no centro de segurança do Microsoft 365.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 8cf416e773abc6cbe1fd891fcec9f02a5011c413
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930637"
---
# <a name="assess-your-security-posture-with-microsoft-secure-score"></a>Avaliar a postura de segurança com o Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

O Microsoft Secure Score é uma medição da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria tomadas. Ele pode ser encontrado no https://security.microsoft.com/securescore centro de segurança do Microsoft [365.](overview-security-center.md)

Para ajudar você a obter as informações necessárias mais rapidamente, as ações de aperfeiçoamento da Microsoft são organizadas em grupos:

* Identidade (contas do Azure Active Directory & funções)
* Dispositivo (Microsoft Defender para Ponto de Extremidade, conhecido como [Microsoft Secure Score para Dispositivos)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-microsoft-secure-score-devices)
* Aplicativo (aplicativos de email e nuvem, incluindo o Office 365 e o Microsoft Cloud App Security)

>[!NOTE]
>Na versão recente do Microsoft Secure Score, um modelo de pontuação aprimorado foi lançado, o que tornou o Microsoft Secure Score temporariamente incompatível com a Pontuação de Segurança de Identidade e a API do Graph. [Exibir detalhes](microsoft-secure-score-whats-new.md)

Na página de visão geral do Microsoft Secure Score, veja como os pontos são divididos entre esses grupos e quais pontos estão disponíveis. Você também pode obter uma visão geral da pontuação total, tendência histórica de sua pontuação segura com comparações de parâmetros de comparação e ações de melhoria priorizadas que podem ser tomadas para melhorar sua pontuação.

![Home page do Secure Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="check-your-current-score"></a>Verifique sua pontuação atual

Para verificar sua pontuação atual, vá para a página de visão geral do Microsoft Secure Score e procure o pacote que diz Sua **pontuação segura.** Sua pontuação será mostrada como uma porcentagem, juntamente com o número de pontos que você atingiu do total de pontos possíveis.

Além disso, se você selecionar o **botão Incluir** ao lado de sua pontuação, poderá escolher diferentes exibições da sua pontuação. Esses diferentes visualizações de pontuação serão exibidos no gráfico no gráfico de pontuação e no gráfico de divisão de pontos.

Veja a seguir as pontuações que você pode adicionar ao seu modo de exibição de sua pontuação geral para lhe dar uma visão mais completa da sua pontuação geral:

- **Pontuação planejada:** Mostrar pontuação projetada quando as ações planejadas são concluídas
- **Pontuação de licença atual:** Mostrar pontuação que pode ser atingida com sua licença atual da Microsoft
- **Pontuação possível:** Mostrar pontuação que pode ser atingida com as licenças da Microsoft e a aceitação de risco atual

Esta exibição será a aparência se você tiver incluído todas as exibições de pontuação possíveis:

![Sua pontuação segura, incluindo pontuação planejada, pontuação de licença atual e pontuação possível](../../media/secure-score/your-secure-score.png)

## <a name="take-action-to-improve-your-score"></a>Tomar medidas para melhorar sua pontuação

A **guia Ações de aperfeiçoamento** lista as recomendações de segurança que abordam possíveis superfícies de ataque. Ele também inclui seu status (para abordar, planejado, risco aceito, resolvido por terceiros, resolvido por meio de mitigação alternativa e concluído). Você pode pesquisar, filtrar e agrupar todas as ações de melhoria.  

### <a name="ranking"></a>Classificação

A classificação é baseada no número de pontos que resta para alcançar, dificuldade de implementação, impacto do usuário e complexidade. As ações de melhoria mais elevadas classificadas têm um grande número de pontos restantes com baixa dificuldade, impacto do usuário e complexidade.

### <a name="view-improvement-action-details"></a>Exibir detalhes da ação de melhoria

Quando você seleciona uma ação de melhoria específica, um flyout de página inteira é exibido.  

![Exemplo de exemplo de ação de melhoria](../../media/secure-score/secure-score-improvement-action-details.png)

Para concluir a ação, você tem algumas opções:

- Selecione **Gerenciar** para ir na tela de configuração e fazer a alteração. Em seguida, você obterá os pontos que a ação vale a pena, visíveis no fly out. Os pontos geralmente levam cerca de 24 horas para ser atualizados.

- Selecione **Compartilhar** para copiar o link direto para a ação de melhoria. Você também pode escolher a plataforma para compartilhar o link, como email, Microsoft Teams, Microsoft Planner ou ServiceNow. Selecionar o ServiceNow permitirá que você crie um tíquete de alteração que ficará visível no ServiceNow e na página da central de segurança do Microsoft 365. Para saber mais, confira o [centro de segurança do Microsoft 365 e a integração com o ServiceNow.](tickets-security-center.md)

Adicione **Anotações** para acompanhar o progresso ou qualquer outra coisa que você queira comentar. Se você adicionar suas próprias **marcas à** ação de melhoria, poderá filtrar por essas marcas.

### <a name="choose-an-improvement-action-status"></a>Escolher um status de ação de melhoria

Escolha todos os status e grave anotações específicas para a ação de melhoria.

- **Para tratar** - Você reconhece que a ação de melhoria é necessária e planeja a resolver em algum momento no futuro. Esse estado também se aplica a ações que são detectadas como parcialmente, mas não totalmente concluídas.
- **Planejado -** Há planos concretos para concluir a ação de melhoria.
- **Risco aceito** - A segurança sempre deve ser equilibrada com a usabilidade, e nem todas as recomendações funcionarão para seu ambiente. Nesse caso, você pode optar por aceitar o risco ou o risco restante e não aprovar a ação de melhoria. Você não receberá nenhum ponto, mas a ação não estará mais visível na lista de ações de melhoria. Você pode exibir essa ação no histórico ou desfazê-la a qualquer momento.
- **Resolvido por meio de terceiros** e Resolvido por meio de **mitigação** alternativa - A ação de melhoria já foi abordada por um aplicativo ou software de terceiros ou por uma ferramenta interna. Você obterá os pontos que a ação vale, para que sua pontuação reflita melhor a postura de segurança geral. Se uma ferramenta interna ou de terceiros não abranger mais o controle, você poderá escolher outro status. Lembre-se de que a Microsoft não terá visibilidade da conclusão da implementação se a ação de melhoria estiver marcada como um desses status.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Ações de & de gerenciamento de vulnerabilidades

Para ações de melhoria na categoria "Dispositivo", você não pode escolher status. Em vez disso, você será [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) direcionado para a recomendação de segurança de gerenciamento de ameaças e vulnerabilidades associada na Central de Segurança do [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) para tomar medidas. A exceção escolhida e a justificativa que você escreve serão específicas para esse portal. Ele não estará presente no portal do Microsoft Secure Score.

#### <a name="completed-improvement-actions"></a>Ações de melhoria concluídas

As ações de melhoria têm um status "concluído" depois que todos os pontos possíveis para a ação de melhoria foram alcançados. As ações de melhoria concluídas são confirmadas por meio dos dados da Microsoft, e você não pode alterar o status.

### <a name="assess-information-and-review-user-impact"></a>Avaliar informações e analisar o impacto do usuário

A seção chamada **Rapidamente lhe** dirá a categoria, os ataques que ela pode proteger contra e o produto.

**O impacto** ao usuário é o que os usuários  experimentarão se a ação de melhoria for acionada, e os Usuários afetados serão as pessoas que serão afetadas.

### <a name="implement-the-improvement-action"></a>Implementar a ação de melhoria

A **seção** Implementação mostra os pré-requisitos, as próximas etapas passo a passo para concluir a ação de melhoria, o status atual da implementação da ação de melhoria e saber mais links.

Os pré-requisitos incluem todas as licenças necessárias ou ações a serem concluídas antes que a ação de melhoria seja abordada. Certifique-se de que você tenha licenças suficientes para concluir a ação de melhoria e que essas licenças sejam aplicadas aos usuários necessários.  

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir de você

Se você tiver algum problema, deixe-nos saber postando na comunidade segurança, privacidade [& conformidade.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Estamos monitorando a comunidade e forneceremos ajuda.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral do Microsoft Secure Score](microsoft-secure-score.md)
- [Acompanhar o histórico do Microsoft Secure Score e cumprir as metas](microsoft-secure-score-history-metrics-trends.md)
- [O que estar por vir.](microsoft-secure-score-whats-coming.md)
- [Novidades](microsoft-secure-score-whats-new.md)
