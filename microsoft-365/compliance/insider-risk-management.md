---
title: Gerenciamento de risco interno
description: Saiba como ajudar a minimizar o risco em sua organização com o gerenciamento de risco do insider no Microsoft 365.
keywords: Microsoft 365, risco de insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 92b8802325ea6d80241d59bd506051ad048b8422
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208673"
---
# <a name="insider-risk-management-in-microsoft-365"></a>Gerenciamento de risco do insider no Microsoft 365

O gerenciamento de riscos do Insider é uma solução de conformidade no Microsoft 365 que ajuda a minimizar os riscos internos, permitindo que você detecte, investigue e atue em atividades mal-intencionadas e inadvertidas em sua organização. As políticas de risco do insider permitem que você defina os tipos de riscos para identificar e detectar em sua organização, incluindo a ação em casos e encaminhar casos para a descoberta eletrônica avançada da Microsoft, se necessário. Os analistas de risco em sua organização podem tomar as ações apropriadas rapidamente para garantir que os usuários estejam em conformidade com os padrões de conformidade da sua organização.

Assista ao vídeo abaixo para saber como o gerenciamento de riscos do insider pode ajudar sua organização a impedir, detectar e conter riscos enquanto prioriza os valores da organização, cultura e experiência do usuário:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Pontos problemáticos do risco moderno

O gerenciamento e minimização de riscos na sua organização é iniciado com a compreensão dos tipos de riscos encontrados no local de trabalho moderno. Alguns riscos são orientados por eventos externos e fatores que estão fora do controle direto. Outros riscos são orientados por eventos internos e atividades do usuário que podem ser minimizados e evitados. Alguns exemplos são riscos de comportamento ilegal, inadequado, não autorizado ou não-ético e ações por usuários em sua organização. Estes comportamentos incluem uma ampla variedade de riscos internos de usuários:

- Vazamentos de dados confidenciais e derramamento de dados
- Violações de confidencialidade
- Roubo de propriedade intelectual (IP)
- Relacionadas
- Comercialização de insider
- Violações de conformidade normativa

Os usuários no local de trabalho moderno têm acesso para criar, gerenciar e compartilhar dados em um amplo espectro de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir os riscos da organização e, ao mesmo tempo, atendem aos padrões de privacidade do usuário.

O gerenciamento de riscos do insider usa toda a amplitude de serviços e indicadores de terceiros para ajudá-lo a identificar, fazer a triagem e agir rapidamente na atividade de riscos. Usando logs do Microsoft 365 e Microsoft Graph, o gerenciamento de riscos do insider permite que você defina políticas específicas para identificar os indicadores de risco. Essas políticas permitem identificar atividades arriscadas e agir para reduzir esses riscos.

O gerenciamento de riscos do insider está centralizado em torno dos seguintes princípios:

- **Transparência**: Equilibre a privacidade do usuário em relação ao risco da organização com a arquitetura de privacidade de design.
- **Configurável**: políticas configuráveis com base em grupos de negócios, geográficos e setores.
- **Integrado**: fluxo de trabalho integrado entre as soluções de conformidade da Microsoft 365.
- **Acionável**: fornece ideias para habilitar notificações de usuário, investigações de dados e investigações de usuários.

## <a name="workflow"></a>Fluxo de trabalho

O fluxo de trabalho de gerenciamento de risco do insider ajuda você a identificar, investigar e realizar ações para lidar com riscos internos em sua organização. Com os modelos de política prioritários, a sinalização abrangente de atividades no serviço Microsoft 365 e as ferramentas de gerenciamento de alertas e casos, você pode usar o insights acionáveis para identificar e agir rapidamente sobre o comportamento arriscado.

A identificação e a resolução de problemas de conformidade e atividades de riscos internos no Microsoft 365 usa o seguinte fluxo de trabalho:

![Fluxo de trabalho de gerenciamento de risco](../media/insider-risk-workflow.png)

### <a name="policies"></a>Políticas

[As políticas de gerenciamento de risco do insider](insider-risk-management-policies.md) são criadas usando modelos predefinidos e condições de política que definem o que os eventos de acionamento e os indicadores de risco são examinados em sua organização. Essas condições incluem como os indicadores de risco são usados para alertas, quais usuários estão incluídos na política, quais serviços são priorizados e o período de tempo de monitoramento.

Você pode selecionar um dos seguintes [modelos de política para começar a usar rapidamente o gerenciamento de risco do insider:

- [Roubo de dados por parte de usuários](insider-risk-management-policies.md#data-theft-by-departing-users)
- [Vazamentos de dados gerais](insider-risk-management-policies.md#general-data-leaks)
- [Vazamentos de dados por usuários de prioridade (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Vazamentos de dados por usuários descontentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violações de política de segurança geral (versão prévia)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violações de política de segurança por parte dos usuários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violações de política de segurança por usuários de prioridade (prévia)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violações de política de segurança por usuários descontentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)
- [Idioma ofensivo no email](insider-risk-management-policies.md#offensive-language-in-email)

![Painel de política de gerenciamento de risco do insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Os alertas são gerados automaticamente pelos indicadores de risco que correspondem às condições da política e são exibidos no [painel de alertas](insider-risk-management-alerts.md). Este painel permite uma visualização rápida de todos os alertas que precisam de revisão, abrir alertas ao longo do tempo e estatísticas de alerta para sua organização. Todos os alertas de política são exibidos com as seguintes informações para ajudá-lo a identificar rapidamente o status dos alertas existentes e os novos alertas que precisam de ação:

- Status
- Severity
- Tempo detectado
- Caso
- Status do caso

![Painel de alerta de gerenciamento de risco do insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triagem

Novas atividades de usuário que precisam de investigação geram automaticamente alertas que são atribuídos a um status de *revisão de necessidades* . Os revisores podem identificar e revisar, avaliar e analisar rapidamente esses alertas.

Os alertas são resolvidos abrindo um novo caso, atribuindo o alerta a um caso existente ou descartando o alerta. Usando filtros de alerta, é fácil identificar rapidamente os alertas por status, severidade ou tempo detectado. Como parte do processo de triagem, os revisores podem exibir detalhes de alerta para as atividades identificadas pela política, exibir a atividade do usuário associada à correspondência de política, ver a gravidade do alerta e revisar as informações do perfil de usuário.

![Triagem de gerenciamento de risco do insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

Os [casos](insider-risk-management-cases.md) são criados para alertas que exigem análise detalhada e investigação dos detalhes da atividade e das circunstâncias em torno da correspondência da política. O **painel de casos** fornece uma visão de todas as ocorrências ativas, casos abertos ao longo do tempo e estatísticas de caso de sua organização. Os revisores podem filtrar ocorrências rapidamente por status, a data em que o caso foi aberto e a data em que o caso foi atualizado pela última vez.

Selecionar um caso no painel de casos abre o caso de investigação e análise. Esta etapa é o coração do fluxo de trabalho de gerenciamento de risco do insider. Esta área é onde as atividades de risco, as condições da política, os detalhes dos alertas e os detalhes do usuário são sintetizadas em um modo de exibição integrado para revisores. As ferramentas de investigação principal nessa área são:

- **Atividade do usuário**: a atividade do usuário é exibida automaticamente em um gráfico interativo que plota atividades ao longo do tempo e por nível de risco para atividades de risco atuais ou antigas. Os revisores podem filtrar e exibir rapidamente todo o histórico de riscos para o usuário e analisar atividades específicas para obter mais detalhes.
- **Gerenciador de conteúdo**: todos os arquivos de dados e mensagens de email associados às atividades de alerta são automaticamente capturados e exibidos no Gerenciador de conteúdo. Os revisores podem filtrar e exibir arquivos e mensagens por fonte de dados, tipo de arquivo, marcas, conversa e muitos outros atributos.
- **Anotações de caso**: os revisores podem fornecer anotações para uma ocorrência na seção notas de caso. Essa lista consolida todas as anotações em um modo de exibição central e inclui informações de revisor e data de envio.

![Investigação de gerenciamento de risco do insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Action

Após os casos serem investigados, os revisores podem agir rapidamente para resolver o caso ou colaborar com outros participantes de risco em sua organização. Se os usuários violarem acidentalmente ou inadvertidamente as condições de política, um aviso de lembrete simples poderá ser enviado ao usuário dos modelos de aviso que você pode personalizar para sua organização. Esses avisos podem servir como lembretes simples ou podem direcionar o usuário para o treinamento ou orientação para ajudar a evitar um comportamento arriscado futuro. Para obter mais informações, consulte [modelos de aviso de gerenciamento de risco do insider](insider-risk-management-notices.md).

Nas situações mais sérias, talvez você precise compartilhar as informações do caso de gerenciamento de risco do insider com outros revisores ou serviços em sua organização. O gerenciamento de riscos do insider está totalmente integrado a outras soluções de conformidade da Microsoft 365 para ajudá-lo com a resolução de riscos de ponta a ponta.

- **Descoberta eletrônica avançada**: o escalonamento de um caso para investigação permite transferir dados e gerenciamento do caso para descoberta eletrônica avançada no Microsoft 365. A descoberta eletrônica avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar o conteúdo que responde às investigações internas e externas da sua organização. Ele permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de retenção legal. Para saber mais sobre casos de descoberta eletrônica avançada, confira [visão geral da descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md).
- **Servicenow (visualização)**: o servicenow é uma plataforma de computação em nuvem popular que ajuda as organizações a gerenciar fluxos de trabalho digitais para operações empresariais. O gerenciamento de risco do insider oferece suporte ao compartilhamento de alertas de casos com o serviço do ServiceNow e permite que você crie incidentes e altere solicitações relacionadas a casos de risco do insider. Para saber mais sobre como compartilhar informações de alerta com o ServiceNow, confira [compartilhar um caso com o servicenow](insider-risk-management-cases.md#share-the-case).
- **Integração de APIs de gerenciamento do Office 365 (versão prévia)**: o gerenciamento de risco do insider oferece suporte à exportação de informações de alerta para serviços de gerenciamento de eventos e informações de segurança por meio das APIs de gerenciamento do Office 365 Ter acesso a informações de alerta na plataforma o mais adequado para os processos de risco da sua organização oferece maior flexibilidade na forma de agir em atividades de risco. Para saber mais sobre como exportar informações de alerta com as APIs de gerenciamento do Office 365, confira [Exportar alertas](insider-risk-management-settings.md#export-alerts-preview).

## <a name="scenarios"></a>Cenários

O gerenciamento de riscos do insider pode ajudá-lo a detectar, investigar e realizar ações para reduzir os riscos internos em sua organização em vários cenários comuns:

### <a name="data-theft-by-departing-users"></a>Roubo de dados por parte de usuários

Quando os usuários deixam uma organização, voluntaria ou como resultado da finalização, há muitas vezes legítimas preocupações que a empresa, o cliente e os dados do usuário estão em risco. Os usuários podem supor inocentemente que os dados do projeto não são proprietários, ou podem estar tentado a obter dados da empresa para obter um ganho pessoal e violar a política e os padrões jurídicos da empresa. As políticas de gerenciamento de risco do insider que usam o modelo de política de [usuários que fazem parte do usuário](insider-risk-management-policies.md#policy-templates) detectam automaticamente as atividades geralmente associadas a esse tipo de roubo. Com esta política, você receberá automaticamente alertas de atividades suspeitas associadas ao roubo de dados, fazendo com que os usuários possam realizar ações investigativas apropriadas. A configuração de um [conector de RH da Microsoft 365](import-hr-data.md) para a sua organização é necessária para este modelo de política.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Perda intencional ou involuntária de informações confidenciais ou confidenciais

Na maioria dos casos, os usuários experimentam o melhor para lidar corretamente com informações confidenciais e confidenciais. Mas ocasionalmente, os usuários podem fazer erros e informações são compartilhados acidentalmente fora da sua organização ou violando suas políticas de proteção de informações. Em outras circunstâncias, os usuários podem acidentalmente vazar ou compartilhar informações confidenciais e confidenciais com más intenções e obter um potencial pessoal. As políticas de gerenciamento de risco do insider criadas com os seguintes modelos de política de vazamento de dados detectam automaticamente as atividades geralmente associadas ao compartilhamento de informações confidenciais ou confidenciais:

- [Vazamentos de dados gerais](insider-risk-management-policies.md#general-data-leaks)
- [Vazamentos de dados por usuários de prioridade (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)
- [Vazamentos de dados por usuários descontentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)

### <a name="offensive-behavior-that-violates-corporate-policies"></a>Comportamento ofensivo que viola as políticas corporativas

As comunicações de usuário para usuário são, em geral, uma fonte de violações inadvertidas ou mal-intencionadas de políticas corporativas. Essas violações podem incluir linguagem ofensiva, ameaças e assédio entre os usuários. Esse tipo de atividade contribui para um ambiente de trabalho hostil e pode resultar em ações legais em relação a usuários e à organização de grande porte. O gerenciamento de riscos do insider usa novos classificadores internos do Microsoft 365 e a [linguagem ofensiva no](insider-risk-management-policies.md#offensive-language-in-email) modelo de política de email para ajudar a minimizar esses riscos. Este modelo de política ajuda você a configurar e habilitar rapidamente uma política para detectar e alertar automaticamente esse tipo de comportamento em sua organização.

## <a name="intentional-or-unintentional-security-policy-violations-preview"></a>Violações de política de segurança intencional ou não intencional (visualização)

Os usuários normalmente têm um grande grau de controle ao gerenciar seus dispositivos no local de trabalho moderno. Isso pode incluir permissões para instalar ou desinstalar aplicativos necessários no desempenho de suas tarefas ou a capacidade de desabilitar temporariamente os recursos de segurança de dispositivos. Se essa atividade é inadvertida, acidental ou mal-intencionada, essa conduta pode representar risco à sua organização e é importante identificar e agir para minimizar. Para ajudar a identificar essas atividades de segurança arriscadas, os seguintes modelos de violação de política de segurança de gerenciamento de risco do insider classificam indicadores de risco de segurança e usam os alertas da proteção avançada contra ameaças da Microsoft defender (ATP) para fornecer ideias para atividades relacionadas à segurança:

- [Violações de política de segurança geral (versão prévia)](insider-risk-management-policies.md#general-security-policy-violations-preview)
- [Violações de política de segurança por parte dos usuários (visualização)](insider-risk-management-policies.md#security-policy-violations-by-departing-users-preview)
- [Violações de política de segurança por usuários de prioridade (prévia)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Violações de política de segurança por usuários descontentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="policies-for-users-based-on-position-access-level-or-risk-history-preview"></a>Políticas para usuários com base na posição, nível de acesso ou histórico de risco (versão prévia)

Os usuários da sua organização podem ter níveis diferentes de risco dependendo da sua posição, nível de acesso a informações confidenciais ou histórico de riscos. Isso pode incluir membros da equipe de liderança executiva da sua organização, administradores de ti que têm privilégios de acesso à rede e dados abrangentes, ou usuários com um histórico de atividades arriscadas. Nessas circunstâncias, a inspeção mais próxima e a pontuação de risco mais agressiva são importantes para ajudar os alertas de superfície para investigação e ação rápida. Para ajudar a identificar atividades arriscadas para esses tipos de usuários, você pode criar grupos de usuários de prioridade e criar políticas dos seguintes modelos de política:

- [Violações de política de segurança por usuários de prioridade (prévia)](insider-risk-management-policies.md#security-policy-violations-by-priority-users-preview)
- [Vazamentos de dados por usuários de prioridade (visualização)](insider-risk-management-policies.md#data-leaks-by-priority-users-preview)

## <a name="actions-and-behaviors-by-disgruntled-users-preview"></a>Ações e comportamentos por usuários descontentes (visualização)

Eventos de estresse de emprego podem impactar o comportamento do usuário de várias maneiras relacionadas a riscos insideres. Esses encargores podem ser uma análise de desempenho ruim, um rebaixamento de posições ou o usuário que está sendo posicionado em um plano de avaliação de desempenho. Embora a maioria dos usuários não respondam de forma mal-intencionada a esses eventos, a sobrecarga dessas ações pode fazer com que alguns usuários tomem ações que não podem ser consideradas normalmente durante circunstâncias normais. Para ajudar a identificar esses tipos de atividades arriscadas, os seguintes modelos de política de gerenciamento de riscos do insider usam o conector de RH da Microsoft 365 e começam a pontuação de indicadores de risco relacionados a comportamentos que podem ocorrer próximos eventos de estresse de emprego:

- [Vazamentos de dados por usuários descontentes (visualização)](insider-risk-management-policies.md#data-leaks-by-disgruntled-users-preview)
- [Violações de política de segurança por usuários descontentes (visualização)](insider-risk-management-policies.md#security-policy-violations-by-disgruntled-users-preview)

## <a name="ready-to-get-started"></a>Pronto para começar?

- Consulte [planejar o gerenciamento de risco do insider](insider-risk-management-plan.md) para saber como se preparar para habilitar as políticas de gerenciamento de risco do insider em sua organização.
- Confira [introdução às configurações de gerenciamento de risco do insider](insider-risk-management-settings.md) para definir configurações globais para políticas de risco do insider.
- Confira [introdução ao gerenciamento de risco do insider](insider-risk-management-configure.md) para configurar os pré-requisitos, criar políticas e começar a receber alertas.
