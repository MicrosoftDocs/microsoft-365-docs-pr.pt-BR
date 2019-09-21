---
title: Classificação de Segurança da Microsoft
description: Descreve a pontuação segura da Microsoft na central de segurança do Microsoft 365, como os detalhes são calculados e quais administradores de segurança podem esperar usá-lo.
keywords: segurança, malware, Microsoft 365, M365, Pontuação segura, central de segurança, ações de melhoria
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 17d2decc7374d9022c68cbe2f2d58da959f44a7d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073955"
---
# <a name="microsoft-secure-score"></a>Classificação de Segurança da Microsoft

>[!IMPORTANT]
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Com a pontuação segura da Microsoft na central de segurança do Microsoft 365, você pode ter maior visibilidade e controle sobre a postura de segurança da sua organização. A partir de um painel centralizado, você pode monitorar e aprimorar a segurança de suas identidades, dados, aplicativos, dispositivos e infraestrutura do Microsoft 365.

A pontuação segura da Microsoft oferece visualizações robustas, integração com outros produtos da Microsoft, comparação de sua pontuação com outras empresas, filtragem por categoria e muito mais. Com a ferramenta, você pode concluir as ações de melhoria de segurança em sua organização e acompanhar o histórico de sua pontuação. A pontuação também pode refletir quando soluções de terceiros solucionaram ações de melhoria recomendadas.  

## <a name="how-it-works"></a>Como funciona

Você receberá pontos para configurar os recursos de segurança recomendados, executar tarefas relacionadas à segurança (como exibir relatórios) ou abordar a ação de aperfeiçoamento com um aplicativo ou software de terceiros. Algumas ações são classificadas para conclusão parcial, como habilitar a MFA (autenticação multifator) para seus usuários. A segurança deve sempre ser balanceada com usabilidade, e nem todas as recomendações funcionarão para o seu ambiente.

## <a name="required-permissions"></a>Permissões obrigatórias

Atualmente, para exibir a pontuação segura da Microsoft, você deve receber uma das seguintes funções no Azure Active Directory:

* Administrador global
* Administrador de segurança
* Leitor de segurança

## <a name="rich-experiences--additional-security-recommendations"></a>Experiências avançadas & recomendações de segurança adicionais

Na pontuação segura da Microsoft, adicionamos recomendações do Azure AD, do Intune e do Cloud app Security, com recomendações da central de segurança do Azure e do Microsoft defender ATP em breve. Também adicionamos ainda mais recomendações de segurança para o Office 365. Com informações adicionais e mais visibilidade de um conjunto mais amplo de produtos e serviços da Microsoft, você pode se sentir confiável para o gerenciamento da integridade de segurança da sua organização. Você também pode obter sua pontuação usando a [API do Microsoft Graph](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta).

Para ajudá-lo a saber mais rapidamente as informações de que você precisa, as recomendações da Microsoft são organizadas em grupos:

* Identity (estado de proteção de suas contas e funções do Azure AD)
* Dados (estado de proteção de seus documentos do Office 365)
* Dispositivo (estado de proteção de seus dispositivos; Ações de melhoria do Microsoft defender ATP em breve)
* Aplicativo (estado de proteção de seus aplicativos de email e nuvem)
* Infraestrutura (estado de proteção dos seus recursos do Azure; em breve)

Na página de visão geral de Pontuação segura da Microsoft, você pode ver como os pontos são divididos entre esses grupos e que pontos estão disponíveis. A página de visão geral também é o local para obter uma visão completa da pontuação total, tendência histórica de sua pontuação segura com comparações de benchmark e ações de melhoria priorizadas que podem ser tomadas para melhorar sua pontuação. Você pode usar esses dados para agir e fazer grandes diferenças em sua postura de segurança.  

![M365 homepage](../media/secure-score/homepage-original.png)
*Figura 1: página de visão geral de Pontuação segura da Microsoft*

## <a name="take-action-to-improve-your-score"></a>Executar uma ação para melhorar sua pontuação

A guia ações de melhoria lista todas as recomendações de segurança aplicáveis ao seu locatário junto com o status (concluído, não concluído, resolvido por terceiros e ignorado). Você pode pesquisar, filtrar e agrupar todos os controles.  A classificação é baseada na avaliação da Microsoft de valor de segurança e esforço para concluir.

As ações rotuladas como [not score] não são rastreadas pela pontuação segura da Microsoft. Você ainda pode tomar ações, mas concluí-las não afetará sua pontuação. Se uma ação for rastreada pela pontuação segura da Microsoft no futuro e você já a tiver concluído, sua pontuação segura refletirá automaticamente a alteração.

Quando você clica em uma ação de melhoria, uma saída é exibida. Para concluir a ação, você tem algumas opções:

1. Selecione **configurações de exibição** para ir para a tela de configuração e fazer a alteração. Em seguida, você obterá os pontos que a ação vale a pena, visível na parte superior da saída. Os pontos podem levar até 24 horas para serem atualizados.

2. Selecione **resolver por meio** de terceiros, pois a ação de aprimoramento já foi abordada por um aplicativo ou software de terceiros. Você ganhará os pontos que a ação vale a pena, para que sua pontuação segura reflita melhor a sua postura geral de segurança. Se um terceiro não mais cobrir o controle, você poderá marcar a ação de melhoria como não concluída. Tenha em mente que a Microsoft não terá visibilidade se os requisitos de Pontuação foram atendidos se a ação de melhoria for marcada como resolvida por terceiros.

3. Selecione **ignorar** porque você optou por aceitar o risco e não enact a ação de aperfeiçoamento. Após ignorar uma ação de melhoria, o número total de pontos de Pontuação segura que você pode alcançar será reduzido. Você pode exibir essa ação no histórico ou desfazê-la a qualquer momento.

4. Selecione **revisar** porque a ação de aprimoramento exige que você examine regularmente uma parte do seu ambiente para ganhar e manter pontos. Por exemplo, as regras de encaminhamento de caixa de correio devem ser revisadas semanalmente para garantir que os dados não sejam vazadas da sua rede. Você não precisa fazer alterações, mas será necessário executar uma ação. Se você examinar as regras regularmente, receberá os pontos. Caso contrário, a pontuação será reduzida.

![Página inicial do M365](../media/secure-score/secure-score1x450.png) ![Página inicial do M365](../media/secure-score/secure-score2x450.png)

*Figuras 2 & 3: aprimorar submenus de ação*

## <a name="monitor-improvements-over-time"></a>Monitorar melhorias ao longo do tempo

Você pode exibir um gráfico da pontuação da sua organização com o tempo na guia **histórico** . Este modo de exibição inclui a média global, média da indústria e contagem de assentos similares, juntamente com todas as ações realizadas no intervalo de tempo selecionado. Você também pode personalizar um intervalo de datas e filtrar por categoria.

A pontuação é calculada uma vez por dia (em torno de 1:00 AM PST). Se você fizer uma alteração em uma ação medida, a pontuação será automaticamente atualizada no dia seguinte. Também é importante observar que alguns outros portais mostram partes da Pontuação segura da Microsoft (como a central de segurança do Microsoft defender). Se você concluir uma ação de melhoria e a pontuação for aumentada nesses portais, pode levar até 24 horas para que a pontuação atualizada seja exibida no centro de segurança do Microsoft 365.  

## <a name="how-improvement-actions-are-scored"></a>Como as ações de aperfeiçoamento são pontuadas

A maioria é classificada de uma maneira binária-você obtém 100% dos pontos se implementar a ação de melhoria, como criar uma nova política ou ativar uma configuração específica. Para outras ações de melhoria, os pontos são fornecidos como uma porcentagem da configuração total. Por exemplo, se a ação de melhoria diz que você receberá 30 pontos se você proteger todos os seus usuários com a autenticação multifator e tiver apenas 5 de 100 total de usuários protegidos, você terá uma pontuação parcial de cerca de 2 pontos (5 protegidos/100 total * 30 pt máx.  Pontuação parcial de pts).

## <a name="risk-awareness"></a>Reconhecimento de risco

A pontuação segura da Microsoft é um resumo numérico de sua postura de segurança com base nas configurações do sistema, no comportamento do usuário e em outras medidas relacionadas à segurança; Não é uma medida absoluta da probabilidade de que seu sistema ou dados seja violado. Em vez disso, ele representa a extensão à qual você adotou os controles de segurança no seu ambiente Microsoft, o que pode ajudar a reduzir o risco de ser violado. Nenhum serviço online é totalmente imune às brechas de segurança e a pontuação segura não deve ser interpretada como uma garantia contra violação de segurança de qualquer forma.

## <a name="we-want-to-hear-from-you"></a>Queremos ouvir sua opinião

Se você tiver problemas, informe-nos por postagem na Comunidade de [segurança, privacidade & conformidade](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . Estamos monitorando a Comunidade e forneceremos ajuda.
