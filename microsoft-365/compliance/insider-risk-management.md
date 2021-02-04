---
title: Saiba mais sobre o gerenciamento de riscos internos
description: Saiba como ajudar a minimizar os riscos em sua organização com o gerenciamento de riscos interno no Microsoft 365.
keywords: Microsoft 365, risco interno, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: ceb35fa9e89a5393500cecb82e52f44852e47b6f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094662"
---
# <a name="learn-about-insider-risk-management-in-microsoft-365"></a>Saiba mais sobre o gerenciamento de riscos interno no Microsoft 365

O gerenciamento de riscos internos é uma solução de conformidade do Microsoft 365 que ajuda a minimizar os riscos internos, permitindo que você detecte, investigue e atue em atividades mal-intencionadas e inadvertida em sua organização. As políticas de risco interno permitem que você defina os tipos de riscos para identificar e detectar em sua organização, incluindo a ação em casos e o escalonamento de casos para a Descoberta Avançada da Microsoft, se necessário. Os analistas de risco em sua organização podem tomar rapidamente as medidas apropriadas para garantir que os usuários sejam compatíveis com os padrões de conformidade da sua organização.

Assista ao vídeo abaixo para saber como o gerenciamento de riscos interno pode ajudar sua organização a evitar, detectar e conter riscos enquanto prioriza os valores, a cultura e a experiência do usuário da sua organização:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Pontos de dor de risco modernos

O gerenciamento e a minimização de riscos em sua organização começam com a compreensão dos tipos de riscos encontrados no local de trabalho moderno. Alguns riscos são controlados por eventos externos e fatores que estão fora do controle direto. Outros riscos são orientados por eventos internos e atividades do usuário que podem ser minimizadas e evitadas. Alguns exemplos são os riscos de comportamentos e ações ilegais, inadequadas, não autorizadas ou inadequadas por usuários em sua organização. Esses comportamentos incluem uma ampla variedade de riscos internos dos usuários:

- Vazamentos de dados confidenciais e vazamento de dados
- Violações de confidencialidade
- Roubo de propriedade intelectual (IP)
- Fraude
- Troca de informações internas
- Violações de conformidade regulamentar

Os usuários no local de trabalho moderno têm acesso para criar, gerenciar e compartilhar dados em uma ampla gama de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir os riscos em toda a organização, além de atender aos padrões de privacidade do usuário.

O gerenciamento de riscos insider usa a abrangência completa dos indicadores de serviço e de terceiros para ajudá-lo a identificar, triagem e agir rapidamente sobre a atividade de risco. Usando logs do Microsoft 365 e do Microsoft Graph, o gerenciamento de riscos insider permite definir políticas específicas para identificar indicadores de risco. Essas políticas permitem identificar atividades arriscadas e agir para reduzir esses riscos.

O gerenciamento de riscos insider é centralizado em torno dos seguintes princípios:

- **Transparência:** equilibre a privacidade do usuário versus o risco da organização com a arquitetura de privacidade por design.
- **Configurável:** políticas configuráveis com base em grupos de setor, geográficos e de negócios.
- **Integrado:** fluxo de trabalho integrado em soluções de conformidade do Microsoft 365.
- **A actionable**: Fornece informações para habilitar notificações do usuário, investigações de dados e investigações de usuários.

## <a name="workflow"></a>Fluxo de trabalho

O fluxo de trabalho de gerenciamento de riscos internos ajuda a identificar, investigar e tomar medidas para lidar com os riscos internos em sua organização. Com modelos de política focados, sinalização de atividades abrangentes no serviço do Microsoft 365 e ferramentas de gerenciamento de alertas e casos, você pode usar informações ativas para identificar e agir rapidamente sobre o comportamento arriscado.

Identificar e resolver atividades de risco interno e problemas de conformidade com o gerenciamento de riscos internos no Microsoft 365 usa o seguinte fluxo de trabalho:

![Fluxo de trabalho de gerenciamento de riscos interno](../media/insider-risk-workflow.png)

### <a name="policies"></a>Políticas

[As políticas de gerenciamento de](insider-risk-management-policies.md) riscos internas são criadas usando modelos predefinidas e condições de política que definem quais eventos de disparo e indicadores de risco são examinados em sua organização. Essas condições incluem como os indicadores de risco são usados para alertas, quais usuários estão incluídos na política, quais serviços são priorizados e o período de monitoramento.

Você pode selecionar entre os seguintes[modelos de política para começar rapidamente com o gerenciamento de riscos insider:

- [Roubo de dados por parte dos usuários](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Vazamentos gerais de dados](insider-risk-management-policies.md#general-data-leaks)
- [Vazamentos de dados por usuários prioritários (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Vazamentos de dados por usuários não coerentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violações gerais da política de segurança (visualização)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violações da política de segurança ao separar usuários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violações de política de segurança por usuários prioritários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violações da política de segurança por usuários não coerentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

![Painel de política de gerenciamento de riscos interno](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Os alertas são gerados automaticamente por indicadores de risco que corresponderem às condições da política e são exibidos no [painel Alertas.](insider-risk-management-alerts.md) Esse painel permite uma exibição rápida de todos os alertas que precisam de revisão, alertas abertos ao longo do tempo e estatísticas de alerta para sua organização. Todos os alertas de política são exibidos com as seguintes informações para ajudá-lo a identificar rapidamente o status de alertas existentes e novos alertas que precisam de ação:

- Status
- Severity
- Tempo detectado
- Caso
- Status da ocorrência

![Painel de alerta de gerenciamento de riscos interno](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triagem

Novas atividades do usuário que precisam de investigação geram automaticamente alertas atribuídos a um status *de revisão de* necessidades. Os revisadores podem identificar e analisar, avaliar e triagem rapidamente esses alertas.

Os alertas são resolvidos abrindo um novo caso, atribuindo o alerta a um caso existente ou descartando o alerta. Usando filtros de alerta, é fácil identificar rapidamente alertas por status, gravidade ou tempo detectado. Como parte do processo de triagem, os revisores podem exibir detalhes do alerta para as atividades identificadas pela política, exibir a atividade do usuário associada à política de match, ver a gravidade do alerta e revisar as informações de perfil do usuário.

![Triagem de gerenciamento de riscos interno](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

[Os](insider-risk-management-cases.md) casos são criados para alertas que exigem uma revisão e investigação mais profundas dos detalhes e circunstâncias da atividade em torno da política de match. O **painel caso** fornece uma exibição completa de todos os casos ativos, casos abertos ao longo do tempo e estatísticas de caso para sua organização. Os revisadores podem filtrar rapidamente casos por status, a data em que a ocorrência foi aberta e a data em que o caso foi atualizado pela última vez.

Selecionar uma ocorrência no painel de ocorrências abre o caso para investigação e revisão. Esta etapa é o coração do fluxo de trabalho de gerenciamento de riscos interno. Essa área é onde atividades de risco, condições de política, detalhes de alertas e detalhes do usuário são sintetizados em uma exibição integrada para revisores. As principais ferramentas de investigação nesta área são:

- **Atividade do** usuário: a atividade do usuário é exibida automaticamente em um gráfico interativo que plota as atividades ao longo do tempo e pelo nível de risco para atividades de risco atuais ou passadas. Os revisores podem filtrar e exibir rapidamente todo o histórico de riscos do usuário e detalhar atividades específicas para obter mais detalhes.
- **Explorador de Conteúdo:** todos os arquivos de dados e mensagens de email associados às atividades de alerta são automaticamente capturados e exibidos no Explorador de Conteúdo. Os revisadores podem filtrar e exibir arquivos e mensagens por fonte de dados, tipo de arquivo, marcas, conversa e muito mais atributos.
- **Observações de** caso: Os revisadores podem fornecer notas sobre uma ocorrência na seção Anotações de Caso. Essa lista consolida todas as anotações em uma exibição central e inclui o revisador e a data de envio das informações.

![Investigação de gerenciamento de riscos interno](../media/insider-risk-investigate.png)

### <a name="action"></a>Ação

Depois que os casos são investigados, os revisadores podem agir rapidamente para resolver o caso ou colaborar com outros participantes de risco em sua organização. Se os usuários violarem acidentalmente ou inadvertidamente condições de política, um aviso de lembrete simples poderá ser enviado para o usuário a partir de modelos de aviso que você pode personalizar para sua organização. Esses avisos podem servir como lembretes simples ou podem direcionar o usuário para atualizar o treinamento ou diretrizes para ajudar a evitar futuros comportamentos arriscados. Para obter mais informações, consulte [modelos de aviso de gerenciamento de riscos do Insider.](insider-risk-management-notices.md)

Nas situações mais sérias, talvez seja necessário compartilhar as informações de caso de gerenciamento de riscos interno com outros revisadores ou serviços em sua organização. O gerenciamento de riscos insider está totalmente integrado com outras soluções de conformidade do Microsoft 365 para ajudá-lo com a resolução de riscos de ponta a ponta.

- **Descoberta Eletrônica Avançada:** o escalonamento de um caso de investigação permite transferir dados e gerenciamento do caso para a Descoberta Eletrônica Avançada no Microsoft 365. A Descoberta Avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar conteúdo que responde às investigações internas e externas da sua organização. Ele permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de responsabilidade legal. Para saber mais sobre os casos de Descoberta Avançada, confira Visão Geral da Descoberta Avançada no [Microsoft 365.](overview-ediscovery-20.md)
- **ServiceNow (visualização)**: ServiceNow é uma plataforma popular de computação em nuvem que ajuda as organizações a gerenciar fluxos de trabalho digitais para operações corporativas. O gerenciamento de riscos insider dá suporte a alertas de caso de compartilhamento com seu serviço ServiceNow e permite que você crie incidentes e altere solicitações relacionadas a casos individuais de risco interno. Para saber mais sobre como compartilhar informações de alerta com o ServiceNow, consulte [Compartilhar um caso com o ServiceNow](insider-risk-management-cases.md#share-the-case).
- Integração de APIs de Gerenciamento do **Office 365 (visualização)**: o gerenciamento de riscos do Insider oferece suporte à exportação de informações de alerta para serviços de gerenciamento de eventos e informações de segurança (SIEM) por meio das APIs de Gerenciamento do Office 365. Ter acesso às informações de alerta na plataforma é o melhor para os processos de risco da sua organização oferece mais flexibilidade na forma de agir em atividades de risco. Para saber mais sobre como exportar informações de alerta com APIs de Gerenciamento do Office 365, confira [Exportar alertas.](insider-risk-management-settings.md#export-alerts-preview)

>[!NOTE]
>Agradecemos seus comentários e suporte durante a visualização do conector do ServiceNow. Decidimos encerrar a visualização do conector serviceNow e interromper o suporte no gerenciamento de riscos insider em 30 de novembro de 2020. Estamos avaliando ativamente métodos alternativos para fornecer aos clientes a integração do ServiceNow no gerenciamento de riscos insider.

## <a name="scenarios"></a>Cenários

O gerenciamento de riscos internos pode ajudá-lo a detectar, investigar e tomar medidas para reduzir os riscos internos em sua organização em vários cenários comuns:

### <a name="data-theft-by-departing-users"></a>Roubo de dados por parte dos usuários

Quando os usuários saem de uma organização, de forma organizada ou como resultado da rescisão, muitas vezes há preocupações legítimas de que os dados da empresa, do cliente e do usuário estão em risco. Os usuários podem assumir que os dados do projeto não são proprietários ou podem ser tentados a obter dados da empresa para obter ganho pessoal e violar a política da empresa e os padrões legais. As políticas de gerenciamento [](insider-risk-management-policies.md#policy-templates) de riscos insider que usam o modelo de política de roubo de dados de usuários desassociando o modelo de política de usuários detectam automaticamente atividades normalmente associadas a esse tipo de roubo. Com essa política, você receberá automaticamente alertas para atividades suspeitas associadas ao roubo de dados, para que os usuários possam tomar as ações investigativas apropriadas. A configuração [de um conector de RH do Microsoft 365](import-hr-data.md) para sua organização é necessária para esse modelo de política.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Vazamento intencional ou não intencional de informações confidenciais ou confidenciais

Na maioria dos casos, os usuários tentam o melhor para lidar corretamente com informações confidenciais ou confidenciais. Mas ocasionalmente, os usuários podem cometer erros e as informações são compartilhadas acidentalmente fora da sua organização ou violando suas políticas de proteção de informações. Em outras circunstâncias, os usuários podem intencionalmente vazamento ou compartilhar informações confidenciais e confidenciais com intenção mal-intencionada e para ganho pessoal potencial. As políticas de gerenciamento de riscos internas criadas usando os seguintes modelos de política de vazamento de dados detectam automaticamente atividades normalmente associadas ao compartilhamento de informações confidenciais ou confidenciais:

- [Vazamentos gerais de dados](insider-risk-management-policies.md#general-data-leaks)
- [Vazamentos de dados por usuários prioritários (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Vazamentos de dados por usuários não coerentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Violações intencionais ou não intencionais da política de segurança (visualização)

Os usuários geralmente têm um grande grau de controle ao gerenciar seus dispositivos no local de trabalho moderno. Isso pode incluir permissões para instalar ou desinstalar aplicativos necessários no desempenho de suas funções ou a capacidade de desabilitar temporariamente os recursos de segurança do dispositivo. Se essa atividade for inadvertida, acidental ou mal-intencionada, essa conduta pode representar riscos para sua organização e é importante identificar e agir para minimizar. Para ajudar a identificar essas atividades de segurança arriscadas, os seguintes modelos de violação de política de segurança de gerenciamento de risco interno pontuam indicadores de risco de segurança e usam o Microsoft Defender para alertas de ponto de extremidade para fornecer insights para atividades relacionadas à segurança:

- [Violações gerais da política de segurança (visualização)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violações da política de segurança ao separar usuários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violações de política de segurança por usuários prioritários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violações da política de segurança por usuários não coerentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Políticas para usuários com base em posição, nível de acesso ou histórico de riscos (visualização)

Os usuários em sua organização podem ter níveis diferentes de risco, dependendo de sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Isso pode incluir membros da equipe de liderança executiva da sua organização, administradores de IT que têm amplos privilégios de acesso à rede e dados ou usuários com um histórico anterior de atividades arriscadas. Nessas circunstâncias, inspeção mais próxima e pontuação de risco mais agressiva são importantes para ajudar a surgir alertas para investigação e ação rápida. Para ajudar a identificar atividades arriscadas para esses tipos de usuários, você pode criar grupos de usuários com prioridade e criar políticas a partir dos seguintes modelos de política:

- [Violações de política de segurança por usuários prioritários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Vazamentos de dados por usuários prioritários (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Ações e comportamentos por usuários não coerentes (visualização)

Os eventos de estresse de emprego podem afetar o comportamento do usuário de várias maneiras relacionadas a riscos de uso interno. Esses stressores podem ser uma revisão de desempenho ruim, um rebaixamento de posição ou o usuário sendo colocado em um plano de revisão de desempenho. Embora a maioria dos usuários não responda maliciosamente a esses eventos, o estresse dessas ações pode fazer com que alguns usuários tomem ações que eles normalmente não consideram em circunstâncias normais. Para ajudar a identificar esses tipos de atividades arriscadas, os seguintes modelos de política de gerenciamento de riscos insider usam o conector de RH do Microsoft 365 e iniciam a pontuação de indicadores de risco relacionados a comportamentos que podem ocorrer próximos a eventos do stressor de emprego:

- [Vazamentos de dados por usuários não coerentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violações da política de segurança por usuários não coerentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>Pronto para começar?

- Consulte [Planejar o gerenciamento de riscos insider](insider-risk-management-plan.md) sobre como se preparar para habilitar políticas de gerenciamento de riscos insider em sua organização.
- Consulte [Começar a trabalhar com as configurações de](insider-risk-management-settings.md) gerenciamento de riscos internas para definir as configurações globais das políticas de risco interno.
- Consulte Começar a trabalhar com o gerenciamento de riscos [insider](insider-risk-management-configure.md) para configurar pré-requisitos, criar políticas e começar a receber alertas.
