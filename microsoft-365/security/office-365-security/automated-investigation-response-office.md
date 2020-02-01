---
title: Investigação e resposta automatizadas (AIR) no Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenha uma visão geral dos recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 975c6d8a00e3e1cd8c30b2d417c74cde39b8cd5a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599798"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Investigação e resposta automatizadas (AIR) no Office 365

Os recursos de investigação e resposta automatizados permitem que você execute processos de investigação automatizados em resposta a ameaças bem conhecidas que existem hoje. O AIR pode ajudar sua equipe de operações de segurança a operar com mais eficiência e eficácia.
- Para obter uma visão geral de como o AIR funciona, use este artigo.
- Para começar a usar o AIR, consulte [investigar automaticamente e responder a ameaças no Office 365](office-365-air.md).

> [!TIP]
> Você tem o Microsoft 365 E5 ou Microsoft 365 E3 juntamente com Proteção contra Identidade e Ameaças? Considere tentar [Proteção contra ameaças da Microsoft](../mtp/microsoft-threat-protection.md).

## <a name="the-overall-flow-of-air"></a>O fluxo de ar geral

Em um nível alto, o fluxo de ar funciona da seguinte maneira:

|Fase  |O que está envolvido  |
|---------|---------|
|1     |Um [alerta](#alerts) é disparado por um evento do Office e um [Guia de segurança](#security-playbooks) inicia uma investigação automatizada para alertas selecionados. <br/><br/>Como alternativa, um analista de segurança pode [iniciar uma investigação automatizada manualmente](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer), a partir de um email do [Explorer](threat-explorer.md).        |
|duas     |Enquanto uma investigação automatizada é executada, ela coleta dados adicionais sobre o email e as entidades relacionadas a esse email – arquivos, URLs e destinatários.  O escopo da investigação pode aumentar, pois novos alertas relacionados são acionados.         |
|3D     |Durante e após uma investigação automatizada, [detalhes e resultados](#investigation-graph) estão disponíveis para exibição. Os resultados incluem [ações recomendadas](#recommended-actions) que podem ser tomadas para responder e corrigir quaisquer ameaças encontradas. Além disso, um [log](#playbook-log) de análise manual está disponível que controla todas as atividades de investigação.<br/><br/>Se sua organização estiver usando uma solução de relatórios personalizada ou uma solução de terceiros, você poderá [usar a API da atividade de gerenciamento do Office 365](office-365-air.md#use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions) para exibir informações sobre investigações e ameaças automatizadas.         |
|4      |Sua equipe de operações de segurança revisa os resultados e recomendações da investigação e aprova ações de correção. No Office 365, as ações de correção são realizadas apenas após a aprovação da equipe de segurança da sua organização.         |

As seções a seguir fornecem mais detalhes sobre o AIR, incluindo detalhes sobre alertas, guias de segurança e detalhes de investigação. Além disso, dois exemplos de como o AIR funciona são incluídos neste artigo. Para começar a usar o AIR, consulte [investigar automaticamente e responder a ameaças no Office 365](office-365-air.md).

## <a name="alerts"></a>Alertas

Os [alertas](../../compliance/alert-policies.md#viewing-alerts) representam disparadores de fluxos de trabalho da equipe de operações de segurança para resposta a incidentes. Priorizar o conjunto certo de alertas para investigação e, ao mesmo tempo, garantir que nenhuma ameaça seja difícil. Quando as investigações nos alertas são realizadas manualmente, as equipes de operações de segurança devem procurar e correlacionar entidades (como conteúdo, dispositivos e usuários) em risco de ameaças. Essas tarefas e fluxos de trabalho podem ser muito demorados e envolver várias ferramentas e sistemas. Com o AIR, a investigação e a resposta dos eventos de segurança do Office 365 são automatizados por ter os principais alertas de segurança e gerenciamento de ameaças disparam guias de resposta de segurança automaticamente. 

Atualmente para o AIR, os alertas gerados a partir dos seguintes tipos de políticas de alerta são investigados automaticamente:  

- Um clique em URL potencialmente mal-intencionado foi detectado
- Email relatado pelo usuário como Phish *
- Mensagens de email contendo malware removidos após a entrega *
- Mensagens de email que contêm URLs de phishing removidos após a entrega *
- Padrões de envio de emails suspeitos detectados #
- Usuário impedido de enviar email #

> [!NOTE]
> Os alertas marcados com um asterisco (*) recebem uma severidade *informativa* nas respectivas políticas de alerta no centro de conformidade com segurança &, com notificações por email desativadas. As notificações por email podem ser ativadas por meio da [configuração da política de alerta](../../compliance/alert-policies.md#alert-policy-settings). Os alertas marcados com um hash (#) são geralmente alertas associados aos guias de visualização pública.

Para exibir alertas, no centro de conformidade & segurança, escolha **alertas** > **exibir alertas**. Selecione um alerta para exibir seus detalhes e, em seguida, use o link **Exibir investigação** para ir para a [investigação](#investigation-graph)correspondente.  

> [!NOTE]
> Os alertas informativos ficam ocultos no modo de exibição de alerta por padrão. Para vê-los, altere a filtragem de alerta para incluir alertas informativos.

Se sua organização gerencia seus alertas de segurança por meio de um sistema de gerenciamento de alerta, sistema de gerenciamento de serviços ou informações de segurança e sistema de gerenciamento de eventos (SIEM), você pode enviar alertas do Office 365 para esse sistema por meio de uma notificação por email ou por meio da [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). As notificações de alerta de investigação via email ou API incluem links para acessar os alertas no centro de conformidade & segurança, permitindo que o administrador de segurança atribuído Navegue rapidamente para a investigação.

![Alertas que se vinculam a investigações](../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Guias de segurança

Os guias de segurança são políticas de back-end que estão no coração de automação no Office Advanced Threat Protection e proteção contra ameaças da Microsoft. Os guias estratégicos de segurança fornecidos no AIR são baseados em cenários comuns de segurança do mundo real e desenvolvidos com base nos comentários das equipes de operações de segurança. Um guia de segurança é iniciado automaticamente quando alertas específicos são disparados em sua organização. Depois que o alerta é acionado, o manual associado é executado pelo sistema de investigação e resposta automatizada (AIR). As etapas de investigação por meio da análise do alerta com base no manual de alerta específico, em todos os metadados associados (incluindo mensagens de email, usuários, assuntos, remetentes, etc.). Com base nas conclusões do guia estratégico, o AIR recomenda um conjunto de ações que a equipe de segurança de sua organização pode executar para controlar e reduzir a ameaça. 

Os guias de segurança que você receberá com o AIR são projetados para lidar com as ameaças mais frequentes que as organizações encontram atualmente com o email. Eles são baseados na entrada de operações de segurança e em equipes de resposta a incidentes, incluindo aqueles que ajudam a defender o Microsoft e os ativos de nossos clientes.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Os guias de segurança estão distribuindo em fases

Como parte do AIR, os guias de segurança são implantados em fases. Agora, a fase 1 está disponível e inclui vários guias estratégicos que fornecem recomendações para ações que os administradores de segurança podem revisar e aprovar:
- Mensagem de phishing relatada pelo usuário
- URL clique em alterar veredicto
- Malware detectado após a entrega (malware ZAP)
- O phishing detectou o post-Delivery ZAP (Phish ZAP)

A fase 1 também inclui suporte para investigações de email disparadas pelo administrador (usando o [Explorador de ameaças](threat-explorer.md)).

A fase 2 agora está em andamento com os seguintes guias estratégicos na **Visualização pública**, fornecendo recomendações para ações e administradores de segurança do auxiliar em problemas de investigação:
- Usuário relatado como comprometido (visualização pública)

Os guias estratégicos serão lançados à medida que forem concluídos. Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver o que mais está planejado e disponível em breve.

### <a name="playbooks-include-investigation-and-recommendations"></a>Os guias estratégicos incluem investigação e recomendações

No AIR, cada guia estratégico de segurança inclui: 
- uma investigação raiz de entidades de email (arquivos, URLs, destinatários, endereços IP, etc.)
- busca detalhada de emails semelhantes recebidos pela organização 
- etapas seguidas para identificar e correlacionar outras ameaças potenciais e 
- ações de correção de ameaças recomendadas.

Cada etapa de alto nível inclui várias subetapas executadas para fornecer uma resposta detalhada, detalhada e exaustiva às ameaças.

## <a name="automated-investigations"></a>Investigações automatizadas

A página de investigações automatizadas mostra as investigações da organização e seus Estados atuais.

![Página de investigação principal para AIR](../media/air-maininvestigationpage.png) 
  
Você pode:
- Navegue diretamente para uma investigação (selecione uma **ID de investigação**).
- Aplicar filtros. Escolha um **tipo de investigação**, **intervalo de tempo**, **status**ou uma combinação desses.
- Exporte os dados para um arquivo. csv.

O status de investigação indica o progresso das análises e ações. À medida que a investigação é executada, o status é alterado para indicar se as ameaças foram encontradas e se as ações foram aprovadas. 


|Status  |O que significa  |
|---------|---------|
|Iniciando | A investigação será enfileirada para começar em breve |
|Em execução | A investigação foi iniciada e está conduzindo sua análise |
|Nenhuma ameaça encontrada | A investigação concluiu a análise e nenhuma ameaça foi encontrada |
|Encerrado pelo sistema | A investigação não foi fechada e expirou após 7 dias |
|Ação Pendente | A investigação encontrou ameaças com ações recomendadas.  A investigação continua a ser executada Depois de encontrar as ameaças iniciais e as ações recomendadas, portanto, você deve verificar o log antes de aprovar as ações para ver se os analisadores ainda estão em andamento. |
|Ameaça Encontrada | A investigação encontrou ameaças, mas as ameaças não têm ações disponíveis no AIR.  Estas são as ações do usuário onde não há ação de ar de direção ainda. |
|Remediado | A investigação foi concluída e foi totalmente corrigida (todas as ações foram aprovadas) |
|Parcialmente corrigido | A investigação terminou e algumas das ações recomendadas foram aprovadas |
|Encerrado Pelo Usuário | Um administrador terminou a investigação |
|Falhou | Ocorreu um erro durante a investigação que o impediu de chegar a uma conclusão em relação a ameaças |
|Em fila por limitação | A investigação está aguardando a análise devido a limitações de processamento do sistema (para proteger o desempenho do serviço) |
|Terminada pela limitação | A investigação não pôde ser concluída em tempo suficiente devido à investigação de limitações de processamento de volume e sistema. Você pode acionar novamente a investigação selecionando o email no Explorer e selecionando a ação investigar. |

### <a name="investigation-graph"></a>Gráficos de investigação

Ao abrir uma investigação específica, você verá a página de gráfico de investigação. Esta página mostra todas as diferentes entidades: mensagens de email, usuários (e suas atividades) e dispositivos que foram investigados automaticamente como parte do alerta que foi acionado.

![Página de gráfico de investigação aérea](../media/air-investigationgraphpage.png)

Você pode:
- Obtenha uma visão geral da investigação atual.
- Exibir um resumo da duração da investigação.
- Selecione um nó na visualização para exibir detalhes desse nó.
- Selecione uma guia na parte superior para exibir os detalhes dessa guia.

### <a name="alert-investigation"></a>Investigação de alerta

Na guia **alertas** de uma investigação, você pode ver alertas relevantes para a investigação. Os detalhes incluem o alerta que disparou a investigação e outros alertas correlacionados, como entrada arriscada, violações de política de DLP, etc., que são correlacionadas à investigação. A partir dessa página, um analista de segurança também pode exibir detalhes adicionais sobre alertas individuais.

![Página alertas de ar](../media/air-investigationalertspage.png)

Você pode:
- Obtenha uma visão geral do alerta de acionamento atual e de todos os alertas associados.
- Selecione um alerta na lista para abrir uma página de sobrevôo que mostre detalhes completos do alerta.

### <a name="email-investigation"></a>Investigação de email

Na guia **email** de uma investigação, você pode ver os emails originais e os clusters de emails semelhantes identificados como parte da investigação. 

Dado o volume simples de email que os usuários de uma organização enviam e recebem, além da natureza de comunicação de email e ataques de vários usuários, o processo de 
- agrupar mensagens de email com base em atributos semelhantes de um cabeçalho de mensagem, corpo, URL e anexos; 
- separar emails mal-intencionados do email em bom estado; e 
- executar ações em mensagens de email mal-intencionadas 

pode levar muito tempo. Agora, o ar automatiza esse processo, poupando o tempo e esforço da equipe de segurança da sua organização. 

Dois tipos diferentes de clusters de email podem ser identificados durante a etapa de análise de email: clusters de similaridade e clusters de indicador. 
- Os clusters de similaridade são mensagens de email identificadas pela busca de emails com atributos de remetente e conteúdo semelhantes. Esses clusters são avaliados para conteúdo mal-intencionado com base nas descobertas de detecção originais. Os clusters de emails que contêm detecções de email maliciosas suficientes são considerados mal-intencionados.
- Os clusters de indicadores são mensagens de email identificadas por busca da mesma entidade de indicador (hash de arquivo ou URL) do email original. Quando a entidade de arquivo/URL original é identificada como mal-intencionada, o AIR aplica o indicador veredicto a todo o cluster de mensagens de email contendo essa entidade. Um arquivo identificado como malware significa que o cluster de mensagens de email que contém esse arquivo é tratado como mensagens de email de malware.

O objetivo do clustering é procurar e encontrar outras mensagens de email relacionadas enviadas pelo mesmo remetente como parte de um ataque ou uma campanha.  Em alguns casos, os emails legítimos podem acionar uma investigação (por exemplo, um usuário relata um email de marketing).  Nesses cenários, o clustering de emails deve identificar que os clusters de emails não são mal-intencionados, quando isso o faz adequadamente, ele **não** indica uma ameaça nem recomenda a remoção de email.

A guia **email** também mostra os itens de email relacionados à investigação, como os detalhes de email relatados pelo usuário, o email original relatado, a (s) mensagem (ns) de email zapped devido a malware/phishing, etc.

A contagem de emails identificada na guia email representa atualmente a soma total de todas as mensagens de email exibidas na guia **email** . Como as mensagens de email estão presentes em vários clusters, a contagem total real de mensagens de email identificadas (e afetadas por ações de correção) é a contagem de mensagens de email exclusivas em todos os clusters e mensagens de email dos destinatários originais. 

O Explorer e o AIR contam mensagens de email por destinatário, já que os locais de segurança verdicts, ações e entrega variam de acordo com cada destinatário. Portanto, um email original enviado a três usuários conta como um total de três mensagens de email em vez de um email. Observação pode haver casos em que um email é contado duas ou mais vezes, uma vez que o email pode ter várias ações nela, pode haver várias cópias do email quando todas as ações ocorrerem. Por exemplo, um email de malware detectado na entrega pode resultar em um email bloqueado (em quarentena) e um email substituído (arquivo de ameaça substituído por um arquivo de aviso e, em seguida, entregue à caixa de correio do usuário). Como há, literalmente, duas cópias do email no sistema, ambas podem ser contadas em contagens de cluster. 

As contagens de email são calculadas no momento da investigação e algumas contagens são recalculadas quando você abre submenus de investigação (com base em uma consulta subjacente). As contagens de email mostradas para os clusters de email na guia email e o valor de quantidade de email mostrado no submenu de cluster são calculados no momento da investigação e não são alterados. A contagem de email mostrada na parte inferior da guia email do submenu de cluster de emails e a contagem de mensagens de email exibidas no Explorer refletem mensagens de email recebidas após a análise inicial da investigação. Portanto, um cluster de emails que mostra uma quantidade original de 10 mensagens de email mostraria uma lista de emails de 15 a cinco mensagens de email que chegam entre a fase de análise de investigação e quando o administrador revisa a investigação.  Da mesma forma, investigações antigas podem começar a ter contagens maiores do que as consultas do Explorer, já que ATP P2 expira dados após 7 dias para tentativas e 30 dias para licenças pagas.  Mostrar as contagens históricas e atuais de contagem em modos de exibição diferentes é feita para indicar o impacto do email no momento da investigação e o impacto atual até o momento em que a correção é executada.

Por exemplo, considere o cenário a seguir. O primeiro cluster de três mensagens de email foi considerado como phishing. Outro cluster de mensagens semelhantes com o mesmo IP e assunto foi encontrado e considerado mal-intencionado, pois alguns deles foram identificados como phishing durante a detecção inicial. 

![Página investigação de emails de ar](../media/air-investigationemailpage.png)

Você pode:
- Obtenha uma visão geral das ameaças e dos resultados de agrupamento atuais encontrados.
- Clique em uma entidade de cluster ou uma lista de ameaças para abrir uma página de saída que mostra os detalhes completos do alerta.
- Investigue mais o cluster de emails clicando no link "abrir no Explorer" na parte superior da guia "detalhes do cluster de emails"

![Email de investigação de ar com detalhes de submenu](../media/air-investigationemailpageflyoutdetails.png)

> [!NOTE]
> No contexto de email, você pode ver uma superfície de ameaça de anomalias de volume como parte da investigação. Uma anomalia de volume indica um pico em mensagens de email semelhantes em torno do tempo de evento de investigação em comparação aos prazos anteriores. Esse pico no tráfego de email com características semelhantes (por exemplo, domínio de assunto e remetente, semelhança de corpo e IP de remetente) é típico do início de campanhas ou ataques de email. No entanto, as campanhas de emails em massa, spam e legítimas normalmente compartilham essas características. As anomalias de volume representam uma possível ameaça e, portanto, podem ser menos graves em comparação às ameaças de malware ou phishing identificadas usando mecanismos antivírus, acionamento ou reputação mal-intencionados.

### <a name="user-investigation"></a>Investigação de usuário

Na guia **usuários** , você pode ver todos os usuários identificados como parte da investigação. As contas de usuário são exibidas na investigação quando há um evento ou indicação de que essas contas de usuário podem ser afetadas ou comprometidas.

Por exemplo, na imagem a seguir, o AIR identificou indicadores de comprometimento e anomalias com base em uma nova regra de caixa de entrada que foi criada. Detalhes adicionais (evidência) da investigação estão disponíveis por meio de exibições detalhadas nesta guia. os indicadores de comprometimento e anomalias também podem incluir detecções de anomalias do [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security).

![Página usuários de investigação aérea](../media/air-investigationuserspage.png)

Você pode:
- Obtenha uma visão geral dos resultados do usuário identificados e dos riscos encontrados.
- Selecione um usuário para abrir uma página de sobrevôo que mostre os detalhes completos do alerta.

### <a name="machine-investigation"></a>Investigação de máquina

Na guia **computadores** , você pode ver todas as máquinas identificadas como parte da investigação. 

![Página da máquina de investigação de ar](../media/air-investigationmachinepage.png)

Como parte de alguns guias estratégicos, o AIR correlaciona ameaças de email a dispositivos (por exemplo, malware zapped). Por exemplo, uma investigação passa um hash de arquivo mal-intencionado no [Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection
) para investigar. Isso permite a investigação automatizada de máquinas relevantes para seus usuários, para ajudar a garantir que as ameaças sejam tratadas na nuvem e nos seus pontos de extremidade. 

Você pode:
- Obtenha uma visão geral das máquinas e ameaças atuais encontradas.
- Selecione uma máquina para abrir um modo de exibição que nas [investigações ATP do Microsoft](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) defender relacionadas na central de segurança do Microsoft defender.

### <a name="entity-investigation"></a>Investigação de entidade

Na guia **entidades** , você pode ver as entidades identificadas e analisadas como parte da investigação. 

Aqui, você pode ver as entidades investigadas e os detalhes dos tipos de entidades, como mensagens de email, clusters, endereços IP, usuários e muito mais. Você também pode ver quantas entidades foram analisadas e as ameaças que foram associadas a cada uma delas. 

![Página de entidades de investigação aérea](../media/air-investigationentitiespage.png)

Você pode:
- Obtenha uma visão geral das entidades e ameaças de investigação encontradas.
- Selecione uma entidade para abrir uma página de sobrevôo que mostre os detalhes relacionados da entidade.

![Detalhes das entidades de investigação aérea](../media/air-investigationsentitiespagedetails.png)

### <a name="playbook-log"></a>Log do guia estratégico

Na guia **log** , você pode ver todas as etapas do guia estratégico que ocorreram durante a investigação. O log captura um inventário completo de todas as análises e ações concluídas pelos recursos de investigação automática do Office 365 como parte do AIR. Ele fornece uma visão clara de todas as etapas executadas, incluindo a ação em si, uma descrição e a duração do real do início ao fim. 

![Página de log de investigação de ar](../media/air-investigationlogpage.png)

Você pode:
- Obtenha uma visão geral das etapas do guia estratégico.
- Exportar os resultados para um arquivo CSV.
- Filtrar o modo de exibição.

|Analyz | Descrição |
|-----|-----|
|Investigação de violações de DLP |Investigue todas as violações detectadas pela [prevenção de perda de dados do Office 365](../../compliance/data-loss-prevention-policies.md) (DLP) |
|Extração de indicadores de email |Extrair indicadores do cabeçalho, do corpo e do conteúdo de uma mensagem de email para investigação |
|Reputação de hash de arquivo |Detectar anomalias com base nos hashes de arquivo para usuários e computadores em sua organização |
|Identificação de cluster de email |Análise do cluster de emails com base no cabeçalho, corpo, conteúdo e URLs |
|Análise de volume de cluster de email |Análise de cluster de email com base em padrões de volume de fluxo de emails de saída |
|Investigação de delegação de email |Investigar o acesso de delegação de email para caixas de correio de usuário relacionadas a essa investigação |
|Investigação de regras de encaminhamento de email |Investigue qualquer regra de encaminhamento de email para caixas de correio do usuário relacionadas a esta investigação |
|Malware perdido detectado |Detectar o malware perdido para a caixa de correio do usuário em sua organização |
|Acionamento sob demanda |Acionamento sob demanda disparado para mensagens de email, anexos e URLs |
|Investigação de anomalia de email de saída |Detectar anomalias com base em fluxo de emails históricos enviando padrões para usuários em sua organização |
|Investigação anormal de malware e spam de saída |Detectar malware, phishing ou spam da organização e de saída provenientes de usuários em sua organização |
|Investigação de domínio do remetente |Verificação sob demanda da reputação do domínio do [gráfico de segurança inteligente da Microsoft](https://www.microsoft.com/security/operations/intelligence) e de fontes de inteligência de ameaças externas |
|Investigação de IP do remetente | Verificação por demanda da reputação de IP do [gráfico de segurança inteligente da Microsoft](https://www.microsoft.com/security/operations/intelligence) e de fontes de inteligência de ameaças externas |
|Investigação de cliques de URL | Investigar cliques de usuários protegidos por [links seguros de ATP do Office 365](atp-safe-links.md) em sua organização |
|Investigação de reputação de URL |Verificação sob demanda na reputação da URL do [gráfico de segurança inteligente da Microsoft](https://www.microsoft.com/security/operations/intelligence) e de fontes de inteligência de ameaças externas |
|Investigação de atividades do usuário |Analisar anomalias de atividades do usuário no [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) |
|Extração de indicadores de email relatados pelo usuário |Extrair indicadores do cabeçalho, do corpo e do conteúdo de [emails relatados pelo usuário](enable-the-report-message-add-in.md) para investigação |


### <a name="recommended-actions"></a>Ações recomendadas

Na guia **ações** , você pode ver todas as ações do guia estratégico que são recomendadas para correção após a conclusão da investigação. 

As ações capturam as etapas que a Microsoft recomenda que você faça no final de uma investigação. Você pode realizar ações de correção aqui selecionando uma ou mais ações. Clicar em **aprovar** permite que a correção seja iniciada. (As permissões apropriadas são necessárias-a função de ' pesquisa e limpeza ' é necessária para executar ações do Explorer e do AIR). Por exemplo, um leitor de segurança pode exibir ações, mas não aprová-las. Observação: não é necessário aprovar todas as ações. Se você não concordar com a ação recomendada ou sua organização não escolher determinados tipos de ações, você poderá optar por **rejeitar** as ações ou simplesmente ignorá-las e não executar nenhuma ação. Aprovar e/ou rejeitar todas as ações permite que a investigação seja totalmente fechada (o status é corrigido), enquanto deixa algumas ações incompletas resultam na alteração do status de investigação para um estado parcialmente corrigido.

![Página de ação de investigações aéreas](../media/air-investigationactionspage.png)

Você pode:
- Obtenha uma visão geral das ações recomendadas para o guia estratégico.
- Selecione uma única ação ou várias ações.
- Aprovar ou rejeitar ações recomendadas com comentários.
- Exportar os resultados para um arquivo CSV.
- Filtrar o modo de exibição.

## <a name="remediation-actions"></a>Ações de correção

Quando uma investigação automatizada é executada ou concluída, você geralmente verá uma ou mais ações de correção. A tabela a seguir lista as ações de correção possíveis no Office 365 AIR.

|Ação | Descrição |
|-----|-----|
|Bloquear URL (hora do clique) |Proteger contra emails e documentos que contenham URLs mal-intencionadas. Isso permite o bloqueio de links mal-intencionados e quaisquer páginas da Web relacionadas por meio de [links seguros](atp-safe-links.md) quando o usuário clica em um link em um arquivo do Office existente ou em uma mensagem de email mais antiga. |
|Email de exclusão reversível  |Exclusão reversível de mensagens de email específicas da caixa de correio de um usuário|
|Clusters de emails de exclusão reversível  |Exclusão reversível de mensagens de email mal-intencionadas que correspondem a uma consulta de todas as caixas de correio dos usuários|
|Desativar o encaminhamento de emails externo |Remove a regra de encaminhamento de uma caixa de correio de usuário final específica|

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exemplo: uma mensagem de phishing relatada pelo usuário inicia um guia estratégico de investigação

Quando um usuário em sua organização envia uma mensagem de email e o relata à Microsoft usando o [suplemento de mensagem de relatório para o Outlook ou o Outlook Web App](enable-the-report-message-add-in.md), o relatório também é enviado para o seu sistema e fica visível no Explorer no modo de exibição relatado pelo usuário. Essa mensagem relatada pelo usuário agora dispara um alerta informativo baseado no sistema, que inicia automaticamente o guia estratégico de investigação.

Durante a fase de investigação de raiz, vários aspectos do email são avaliados. Entre elas:
- Uma determinação sobre o tipo de ameaça que ela pode ser;
- Quem o enviou;
- De onde o email foi enviado (infraestrutura de envio);
- Se outras instâncias do email foram entregues ou bloqueadas;
- Uma avaliação de nossos analistas;
- Se o email está associado a qualquer campanha conhecida;
- e muito mais.

Depois que a investigação raiz estiver concluída, o guia estratégico fornecerá uma lista de ações recomendadas a serem executadas no email original e entidades associadas a ela.
  
Em seguida, várias etapas de investigação e busca de ameaças são executadas:

- Mensagens de email semelhantes são identificadas por pesquisas de clusters de email.
- O sinal é compartilhado com outras plataformas, como [o Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- É possível determinar se qualquer usuário clicou por links mal-intencionados em mensagens de email suspeitas.
- Uma verificação é feita no Office 365 proteção do Exchange Online ([EOP](exchange-online-protection-eop.md)) e no Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) para ver se há outras mensagens semelhantes relatadas pelos usuários.
- Uma verificação é feita para ver se um usuário foi comprometido. Esta verificação utiliza sinais no Office 365, no [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security)e no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando qualquer anomalia relacionada à atividade do usuário. 

Durante a fase de caça, riscos e ameaças são atribuídos a várias etapas de busca. 

Correção é a fase final do guia estratégico. Durante esta fase, as etapas de correção são tomadas, com base nas fases de investigação e busca. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exemplo: um administrador de segurança dispara uma investigação do explorador de ameaças

Além de investigações automáticas disparadas por um alerta, a equipe de operações de segurança da sua organização pode acionar uma investigação automática de um modo de exibição no [Explorador de ameaças](threat-explorer.md).

Por exemplo, suponha que você está exibindo dados no Explorer sobre mensagens relatadas pelo usuário. Você pode selecionar um item na lista de resultados e, em seguida, clicar em **investigar** no menu Ação (supondo que você tenha permissões de correção apropriadas).

![Mensagens relatadas pelo usuário no Explorer com o botão investigar](../media/Explorer-UserReported-Investigate.png)

Como outro exemplo, suponha que você esteja exibindo dados sobre mensagens de email detectadas como contendo malware e que há várias mensagens de email detectadas como contendo malware. Você pode selecionar a guia **email** , selecionar uma ou mais mensagens de email e, em seguida, no menu **ações** , selecionar **investigar**. 

![Iniciando uma investigação de malware no Explorer](../media/Explorer-Malware-Email-ActionsInvestigate.png)

Semelhante aos guias estratégicos acionados por um alerta, as investigações automáticas disparadas de um modo de exibição no Explorer incluem uma investigação raiz, etapas para identificar e correlacionar ameaças e ações recomendadas para atenuar essas ameaças.

## <a name="how-to-get-air"></a>Como obter o AIR

O Office 365 AIR está incluído nas seguintes assinaturas:

- Microsoft 365 E5
- Office 365 E5
- Proteção contra Ameaças da Microsoft
- Plano 2 de proteção avançada contra ameaças do Office 365

Se você não tiver nenhuma dessas assinaturas, [inicie uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Para saber mais sobre a disponibilidade de recursos, visite a [disponibilidade de recursos nos planos de proteção avançada contra ameaças (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar os recursos de ar

As permissões são concedidas por determinadas funções, como aquelas descritas na tabela a seguir: 

|Tarefa |Função (ões) necessária |
|--|--|
|Para configurar os recursos de ar |Uma das seguintes funções: <br/>- **Administrador global**<br/>- **Administrador de segurança** <br/>Essas funções podem ser atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>- **Administrador global** <br/>- **Administrador de segurança**<br/>- **Leitor de segurança** <br/>---e---<br/>- **Pesquisa e limpeza** (esta função é atribuída somente no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Talvez seja necessário criar um novo grupo de função e adicionar a função de pesquisa e limpeza a esse novo grupo de função.)

## <a name="next-steps"></a>Próximas etapas

- [Introdução ao uso do AIR no Office 365](office-365-air.md)
- [Saiba mais sobre o AIR no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) 
- [Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir](https://www.microsoft.com/microsoft-365/roadmap?filters=)

## <a name="see-also"></a>Confira também

- [Proteção contra Ameaças da Microsoft](../mtp/microsoft-threat-protection.md)
- [Investigação e correção automatizadas (ar) na proteção contra ameaças da Microsoft](../mtp/mtp-autoir.md)
