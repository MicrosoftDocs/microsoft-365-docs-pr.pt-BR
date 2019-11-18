---
title: Conformidade de comunicação no Microsoft 365 (versão prévia)
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
description: Saiba mais sobre conformidade de comunicação no Microsoft 365
ms.openlocfilehash: 3765e8236b319eaadc543782f2254aefaa8914a2
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "38684749"
---
# <a name="communication-compliance-in-microsoft-365-preview"></a>Conformidade de comunicação no Microsoft 365 (versão prévia)

A conformidade com comunicações faz parte do novo conjunto de soluções de risco do insider no Microsoft 365 que ajuda a minimizar os riscos de comunicação ajudando você a detectar, capturar e realizar ações de correção para mensagens inadequadas em sua organização. As políticas predefinidas e personalizadas permitem que você examine as comunicações internas e externas para correspondências de política, de modo que eles possam ser examinados por revisores designados. Os revisores podem investigar emails, Microsoft Teams ou comunicações de terceiros em sua organização e tomar as ações de correção apropriadas para garantir que eles estejam em conformidade com os padrões de mensagem da sua organização.

As políticas de conformidade de comunicação no Microsoft 365 ajudam a superar muitos desafios modernos associados à conformidade e às comunicações internas e externas, incluindo:

- Verificação de aumento de tipos de canais de comunicação
- O aumento do volume de dados da mensagem
- A imposição normativa & o risco de multas

Em algumas organizações, pode haver uma separação de tarefas entre o suporte de ti e o grupo de gerenciamento de conformidade. A Microsoft 365 oferece suporte à separação entre a configuração de conformidade de comunicação e a configuração de políticas para a verificação de comunicações. Por exemplo, o grupo de ti de uma organização pode ser responsável por configurar permissões e grupos de função para dar suporte a políticas de conformidade de comunicação configuradas e gerenciadas pela equipe de conformidade da organização.

## <a name="scenarios-for-communication-compliance"></a>Cenários de conformidade de comunicação

As políticas de conformidade de comunicação podem ajudar na revisão de mensagens em sua organização em várias áreas importantes de conformidade:

- **Políticas corporativas**

    Os funcionários devem estar em conformidade com o uso aceitável, padrões éticos e outras políticas corporativas em todas as comunicações relacionadas aos negócios. As políticas de conformidade de comunicação podem detectar correspondências de política e ajudá-lo a realizar ações corretivas para ajudar a reduzir esses tipos de incidentes. Por exemplo, você pode examinar as comunicações de funcionários em sua organização em busca de possíveis problemas de recursos humanos, como assédio ou uso de linguagem inadequada ou ofensiva.

- **Gerenciamento de risco**

    As organizações são responsáveis por todas as comunicações distribuídas por toda a infraestrutura e sistemas corporativos de rede. O uso de políticas de supervisão de comunicações para ajudar a identificar e gerenciar a possível exposição e risco legais pode ajudar a minimizar os riscos antes que eles possam danificar as operações corporativas. Por exemplo, você pode examinar mensagens em sua organização para comunicações não autorizadas sobre projetos confidenciais, como aquisições futuras, fusões, divulgações de ganhos, reorganizações ou alterações da equipe de liderança.

- **Conformidade normativa**

    A maioria das organizações deve estar em conformidade com algum tipo de padrões de conformidade normativa como parte de seus procedimentos operacionais normais. Essas regulamentações geralmente exigem que as organizações implementem algum tipo de processo de supervisão ou supervisão para mensagens que sejam apropriadas para o seu setor. A regra 3110 da autoridade de regulamentação do setor financeiro (FINRA) é um bom exemplo de um requisito para que as organizações tenham procedimentos de supervisão em vigor para verificar as comunicações dos funcionários e os tipos de negócios nos quais ele está participando. Outro exemplo pode ser uma necessidade de revisar as comunicações do corretor de seus revendedores em sua organização para proteger contra possíveis atividades de dinheiro-Laundering, Insider Trading, collusion ou Bribery. As políticas de conformidade de comunicação podem ajudar sua organização a atender a esses requisitos fornecendo um processo de verificação e de relatório sobre comunicações corporativas.

## <a name="new-enhancements"></a>Novos aprimoramentos

A conformidade com comunicações no Microsoft 365 baseia-se nos recursos das [políticas de supervisão no Office 365](supervision-policies.md) com vários novos aprimoramentos:

- Modelos inteligentes personalizáveis
- Fluxos de trabalho de correção flexíveis
- Informações acionáveis

![Home Page de conformidade de comunicação](media/communication-compliance-home.png)

### <a name="intelligent-customizable-templates"></a>Modelos inteligentes personalizáveis

Modelos inteligentes personalizáveis na conformidade de comunicação permitem que você aplique o Machine Learning para detectar com inteligência as violações de comunicação em sua organização.

- **Modelos pré-configurados personalizáveis**: novos modelos de política ajudam a lidar com os riscos de comunicação mais comuns. A criação da diretiva inicial e a atualização de acompanhamento são agora mais rápida com o predefinido e com o antiassédio, informações confidenciais e modelos de conformidade normativa pré-definidos.
- **Novo suporte de aprendizado de máquina**: os [classificadores](classifier-getting-started-with.md) incorporados de ameaças, assédio e profanação ajudam a reduzir falsos positivos em mensagens verificadas, poupando o tempo dos revisores durante o processo de investigação e correção.
- **Melhor Construtor de condições**: a configuração de condições de política agora é simplificada em uma única experiência integrada no assistente de política, reduzindo a confusão em como as condições são aplicadas para políticas.

### <a name="flexible-remediation-workflows"></a>Fluxos de trabalho de correção flexíveis

Os fluxos de trabalho de correção internos permitem que você identifique rapidamente e execute ações em mensagens com correspondências de política em sua organização. Os seguintes novos recursos aumentam a eficiência das atividades de investigação e correção:

- **Fluxo de trabalho de correção flexível**: o novo fluxo de trabalho de correção ajuda a realizar ações rapidamente sobre as correspondências de políticas, incluindo novas opções para encaminhar mensagens para outros revisores e enviar notificações por email aos usuários com correspondências de política.
- **Encadeamento de conversa**: agora, as mensagens são agrupadas visualmente pela mensagem original e por todas as mensagens de resposta associadas, dando a você um contexto melhor durante a investigação e as ações de correção.
- **Realce de palavras-chave**: termos de política de correspondência as condições são realçadas no modo de exibição de texto da mensagem para ajudar os revisores a localizar e corrigir os alertas de política rapidamente.
- **Detecção de duplicidades exatas e próximas**: além da verificação de termos exatas que correspondam a políticas de conformidade de comunicação, os grupos de detecção de duplicidades próximos, termos e mensagens parecidas em conjunto para ajudar a acelerar o processo de revisão.
- **Novos filtros**: investigue e corrija alertas de política mais rapidamente com filtros de mensagem para vários campos, incluindo remetente, destinatário, data, domínios e muito mais.
- **Visualizações de mensagens aprimoradas**: as ações de investigação e correção agora são mais rápidas com novas exibições de fonte de mensagens, de texto e de anotações. Os anexos de mensagem agora são visíveis para fornecer contexto completo ao realizar ações de correção.
- **Exibição de histórico do usuário**: modo de exibição histórico de todas as atividades de correção de mensagens do usuário, como notificações e escalonamentos passados para correspondências de política, agora fornecem aos revisores mais contexto durante o processo de fluxo de trabalho de correção. As instâncias de primeira vez ou de repetição das correspondências de política para os usuários agora estão arquivadas e facilmente visíveis.

### <a name="actionable-insights"></a>Informações acionáveis

Novos painéis interativos para alertas, correspondências de política, ações e tendências ajudam a exibir rapidamente o status de alertas pendentes e resolvidos em sua organização.

- **Alertas inteligentes proativos**: alertas para correspondências de política que exigem atenção imediata incluem novos painéis de itens pendentes classificados por gravidade e novas notificações automáticas de email enviadas a revisores designados.
- **Painéis interativos**: novos painéis exibem correspondências de política, ações pendentes e resolvidas e tendências por usuários e políticas.
- **Suporte de auditoria**: um log completo de atividades de política e revisão é facilmente exportado do centro de conformidade da Microsoft 365 para ajudar a oferecer suporte a solicitações de análise de auditoria.

## <a name="integration-with-microsoft-365-services"></a>Integração com serviços do Microsoft 365

As políticas de conformidade de comunicação verificam e capturam mensagens em vários canais de comunicação para ajudá-lo a analisar e corrigir problemas de conformidade rapidamente:

- **Microsoft Teams**: comunicações de chat e anexos associados para canais do [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) públicos e privados e chats individuais têm suporte na conformidade de comunicação como uma fonte de canal autônomo ou com outros serviços do Microsoft 365. Agora, as políticas verificam automaticamente todos os canais e equipes do Microsoft Teams para usuários específicos definidos em uma política, eliminando a necessidade de manter uma lista de mapeamento separada para as atribuições do Microsoft Teams.
- **Exchange Online**: todas as caixas de correio hospedadas no [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) na sua organização do Microsoft 365 estão qualificadas para verificação. Os emails e anexos que correspondem às condições de política de conformidade de comunicação estão disponíveis instantaneamente para monitoramento e relatórios de supervisão. O Exchange Online agora é um canal de origem opcional e não é mais necessário em políticas de conformidade de comunicação.
- **Skype for Business online**: as políticas de conformidade de comunicação dão suporte à verificação de comunicações de chat e anexos associados no [Skype for Business online](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online).
- **Fontes de terceiros**: você pode examinar mensagens de [fontes de terceiros](archiving-third-party-data.md) para dados importados em caixas de correio em sua organização do Microsoft 365. A conformidade de comunicação oferece suporte a conexões com várias plataformas populares, incluindo Bloomberg imediato, Facebook, Twitter e outros.

Para saber mais sobre o suporte de canal de mensagens em políticas de conformidade de comunicação, confira [tipos de comunicação com suporte](communication-compliance-feature-reference.md#supported-communication-types).

## <a name="workflow"></a>Fluxo de Trabalho

A conformidade com comunicações ajuda você a lidar com pontos problemáticos comuns associados à conformidade com políticas internas e requisitos de conformidade normativa. Com modelos de política prioritárias e um fluxo de trabalho flexível, você pode usar o insights acionáveis para resolver rapidamente problemas de conformidade detectados.

Identificar e resolver problemas de conformidade com a conformidade de comunicação no Microsoft 365 usa o seguinte fluxo de trabalho:

![Fluxo de trabalho de conformidade de comunicação](media/communication-compliance-workflow.png)

### <a name="configure"></a>Configurar

Nesta etapa de fluxo de trabalho, você identifica seus requisitos de conformidade e configura as políticas de conformidade de comunicação aplicáveis. Os modelos de política são uma ótima maneira de configurar rapidamente uma nova política de conformidade, mas também modificar e atualizar rapidamente as políticas conforme suas necessidades mudam. Por exemplo, você pode querer testar rapidamente uma política para a linguagem ofensiva e o antiassédio em comunicações para um pequeno grupo de usuários antes de configurar uma política para todos os usuários da sua organização.

Você pode escolher entre os seguintes modelos de política no centro de conformidade da Microsoft 365:

- **Linguagem ofensiva e antiassédio**: Use este modelo para criar rapidamente uma política que usa o classificador interno para detectar automaticamente o conteúdo que pode ser considerado abusivo ou ofensivo.
- **Informações confidenciais**: Use este modelo para criar uma política de verificação de comunicações contendo tipos de informações confidenciais definidos ou palavras-chave para ajudar a garantir que dados importantes não sejam compartilhados com pessoas que não deveriam ter acesso.
- **Conformidade normativa**: Use este modelo para criar uma política para verificar as comunicações de referências a termos financeiros padrão associados a padrões normativos.
- **Política personalizada**: Use este modelo para configurar canais de comunicação específicos, condições de detecção individuais e a quantidade de conteúdo a ser revisada para supervisão em sua organização.

### <a name="investigate"></a>Investigar

Nesta etapa, você tem uma visão mais profunda dos problemas detectados como correspondentes às políticas de conformidade de comunicação. Esta etapa inclui as seguintes ações disponíveis no centro de conformidade da Microsoft 365:

- **Alertas**: quando uma mensagem corresponde a uma política de supervisão, um alerta é gerado automaticamente. Para cada alerta, você pode ver o status, a gravidade, o tempo detectado e se um caso é atribuído e seu status. Novos alertas são exibidos na home page de conformidade de comunicação e na página **alertas** e são listados em ordem de gravidade.
- **Gerenciamento de problemas**: para cada alerta, você pode tomar medidas investigativas para ajudar a corrigir o problema detectado na mensagem
- **Revisão de documentos**: durante a investigação de um problema, você pode usar vários modos de exibição da mensagem para ajudar a avaliar corretamente o problema detectado. Os modos de exibição incluem um resumo de conversa, somente texto, anotações e detalhes da conversa de comunicação.
- **Revisão do histórico de atividades do usuário**: exibir o histórico de atividades de mensagens do usuário e ações de correção, como notificações e escalonamentos passados para correspondências de política.
- **Filtros**: Use filtros como remetente, destinatário, data e assunto para restringir rapidamente os alertas de mensagem que você deseja examinar.

### <a name="remediate"></a>Corrigir

A próxima etapa é corrigir problemas de conformidade de comunicação que você investigou usando as seguintes opções:

- **Resolver**: após revisar um problema, você pode remediar resolvendo o alerta. A resolução de um alerta remove-o da fila de alerta pendente e a ação é preservada como uma entrada na fila resolvida para a política de correspondência. Os alertas são resolvidos automaticamente após a marcação do alerta como falso positivo, envio de um aviso a um funcionário sobre o alerta ou abertura de um novo caso para o alerta.
- **Marcar uma mensagem**: como parte da resolução de um problema, é possível marcar a mensagem detectada como compatível, não compatível ou como questionável, pois ela se relaciona com as políticas e os padrões da sua organização. A marcação pode ajudá-lo a enfiltrar alertas de política para escalonamento ou como parte de outros processos de revisão internos.
- **Notificar o usuário**: frequentemente, os usuários violam acidentalmente ou inadvertidamente uma política de conformidade de comunicação. Você pode usar o recurso Notify para fornecer um aviso de aviso ao usuário e resolver o problema.
- **Escalonar para outro revisor**: às vezes, o revisor inicial de um problema precisa de entrada de outros revisores para ajudar a resolver o incidente. Você pode escalonar facilmente os problemas de mensagem para revisores em outras áreas da organização como parte do processo de resolução.
- **Mark como um falso positivo**: as mensagens detectadas incorretamente como correspondências de políticas de conformidade irão, ocasionalmente, passar para o processo de revisão. Você pode marcar esses tipos de alerta como falsos positivos e resolver automaticamente o problema.

### <a name="monitor"></a>Monitorar

Manter o controle e o gerenciamento de problemas de conformidade identificados por políticas de conformidade de comunicação abrange todo o processo de fluxo de trabalho. À medida que os alertas são gerados e as ações de investigação e correção são implementadas, as políticas existentes podem precisar de análise e atualizações, e novas políticas podem precisar ser criadas.

- **Monitorar e relatar**: usar painéis de conformidade de comunicação, relatórios, exportar logs e eventos registrados nos logs unificados de auditoria do Office 365 para avaliar continuamente e aprimorar a postura de conformidade.

## <a name="ready-to-get-started"></a>Pronto para começar?

Para configurar a conformidade de comunicação para sua organização do Microsoft 365, consulte [Configurar a conformidade de comunicação para o microsoft 365 (versão prévia)](communication-compliance-configure.md).
