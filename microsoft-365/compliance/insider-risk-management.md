---
title: Gerenciamento de risco do insider
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
ms.openlocfilehash: 5a3401b80469fa6d22d973204703a6b012ebb11b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072719"
---
# <a name="insider-risk-management-in-microsoft-365-preview"></a>Gerenciamento de risco do insider no Microsoft 365 (versão prévia)

O gerenciamento de riscos do Insider é uma solução de risco interno no Microsoft 365 que ajuda a minimizar os riscos internos, permitindo que você detecte, investigue e execute ações em atividades arriscadas em sua organização. As políticas personalizadas permitem que você detecte e execute ações em atividades de risco maliciosos e inadvertidas em sua organização, incluindo casos de escalonamento para outras soluções de investigação da Microsoft 365, se necessário. Os analistas de risco em sua organização podem tomar as ações apropriadas rapidamente para garantir que os usuários estejam em conformidade com os padrões de conformidade da sua organização.

Assista ao vídeo abaixo para saber como o gerenciamento de riscos do insider pode ajudar sua organização a impedir, detectar e conter riscos enquanto prioriza seus valores de organização, cultura e experiência do funcionário:
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4j9CN]

## <a name="modern-risk-pain-points"></a>Pontos problemáticos do risco moderno

O gerenciamento e minimização de riscos na sua organização é iniciado com a compreensão dos tipos de riscos encontrados no local de trabalho moderno. Alguns riscos são orientados por eventos e fatores externos e estão fora do controle direto. Outros riscos são orientados por eventos internos e atividades de funcionários que podem ser eliminados e evitados. Alguns exemplos são riscos de comportamento ilegal, inadequado, não autorizado ou não-ético e ações por funcionários e gerentes. Estes comportamentos incluem uma ampla variedade de riscos internos de funcionários:

- Vazamentos de dados confidenciais e derramamento de dados
- Violações de confidencialidade
- Roubo de propriedade intelectual (IP)
- Relacionadas
- Comercialização de insider
- Violações de conformidade normativa

Os funcionários no local de trabalho moderno têm acesso para criar, gerenciar e compartilhar dados em um amplo espectro de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir os riscos da organização e, ao mesmo tempo, atendem aos padrões de privacidade dos funcionários.

O gerenciamento de riscos do insider no Microsoft 365 usa a amplitude completa de serviços e indicadores de terceiros para ajudá-lo a identificar rapidamente, fazer a triagem e realizar ações na atividade de riscos. Usando logs do Office 365 e do Microsoft Graph, o gerenciamento de riscos do insider permite que você defina políticas específicas para identificar os indicadores de risco. Essas políticas permitem identificar atividades arriscadas e tomar medidas para reduzir esses riscos.

O gerenciamento de riscos do insider está centralizado em torno dos seguintes princípios:

- **Transparência**: Equilibre a privacidade do funcionário em relação ao risco da organização com a arquitetura de privacidade de design.
- **Configurável**: políticas configuráveis com base em grupos de negócios, geográficos e setores.
- **Integrado**: fluxo de trabalho integrado entre as soluções de conformidade da Microsoft 365.
- **Acionável**: fornece ideias para habilitar notificações de funcionários, investigações de dados e investigações de funcionários.

## <a name="workflow"></a>Fluxo de trabalho

O gerenciamento de riscos do insider ajuda você a identificar, investigar e realizar ações para lidar com riscos internos em sua organização. Com os modelos de política prioritários, a sinalização abrangente de atividades no serviço Microsoft 365 e um fluxo de trabalho flexível, você pode usar o insights acionáveis para identificar e resolver rapidamente o comportamento arriscado.

A identificação e a resolução de problemas de conformidade e atividades de riscos internos no Microsoft 365 usa o seguinte fluxo de trabalho:

![Fluxo de trabalho de gerenciamento de risco](../media/insider-risk-workflow.png)

### <a name="policies"></a>Políticas

As políticas de gerenciamento de risco do insider são criadas usando modelos predefinidos e condições de política que definem quais indicadores de risco são examinados nas áreas de recursos do Microsoft 365. Essas condições incluem como os indicadores são usados para alertas, quais usuários estão incluídos na política, quais serviços são priorizados e o período de tempo de monitoramento.

Você pode selecionar um dos seguintes [modelos de política](insider-risk-management-policies.md#policy-templates) para começar rapidamente com o gerenciamento de risco do insider:

- Como a parte do roubo de dados do funcionário
- Vazamentos de dados
- Linguagem ofensiva em comunicação

Confira mais informações em [políticas de gerenciamento de risco do insider](insider-risk-management-policies.md).

![Painel de política de gerenciamento de risco do insider](../media/insider-risk-policy-dashboard.png)

### <a name="alerts"></a>Alertas

Os alertas são gerados automaticamente pelos indicadores de risco que correspondem às condições da política e são exibidos no **painel de alertas**. Este painel permite uma visualização rápida de todos os alertas que precisam de revisão, abrir alertas ao longo do tempo e estatísticas de alerta para sua organização. Todos os alertas de política são exibidos com informações associadas para ajudá-lo a identificar rapidamente o status atual dos alertas existentes e os novos alertas que precisam de ação:

- Status
- Severity
- Tempo detectado
- Caso
- Status do caso

Confira mais informações em [alertas de gerenciamento de risco do insider](insider-risk-management-alerts.md).

![Painel de alerta de gerenciamento de risco do insider](../media/insider-risk-alerts-dashboard.png)

### <a name="triage"></a>Triagem

Novas atividades que precisam de investigação geram automaticamente alertas que são atribuídos a um status de *revisão de necessidades* . Os revisores podem identificar rapidamente esses alertas e rolar por cada um para avaliar e fazer a triagem. 

Os alertas são resolvidos abrindo um novo caso, atribuindo o alerta a um caso existente ou descartando o alerta. Usando filtros de alerta, é fácil identificar rapidamente os alertas por status, severidade ou tempo detectado. Como parte do processo de triagem, os revisores podem exibir detalhes de alerta para a correspondência de política, exibir a atividade do usuário associada à correspondência, ver a gravidade do alerta e revisar as informações do perfil de usuário.

![Triagem de gerenciamento de risco do insider](../media/insider-risk-triage.png)

### <a name="investigate"></a>Investigar

Os casos são criados para alertas que exigem análise detalhada e investigação dos detalhes e das circunstâncias em torno da correspondência da política. O **painel de casos** fornece uma visão de todas as ocorrências ativas, casos abertos ao longo do tempo e estatísticas de caso de sua organização. Os revisores podem filtrar ocorrências rapidamente por status, a data em que o caso foi aberto e a data em que o caso foi atualizado pela última vez.

Selecionar um caso no painel de casos abre o caso de investigação e análise. Esta etapa é o coração do fluxo de trabalho de gerenciamento de risco do insider. Esta área é onde os indicadores de atividade de risco, as condições da política, os detalhes dos alertas e os detalhes dos funcionários são sintetizados em um modo de exibição integrado para revisores. As ferramentas de investigação principal nessa área são:

- **Atividade do usuário**: a atividade do usuário é exibida automaticamente em um gráfico interativo que plota as atividades de risco ao longo do tempo e pelo nível de risco das atividades de risco atuais ou anteriores. Os revisores podem filtrar e exibir rapidamente todo o histórico de riscos para o funcionário e analisar atividades específicas para obter mais detalhes.
- **Gerenciador de conteúdo**: todos os arquivos de dados e mensagens de email associados às atividades de risco de alerta são automaticamente capturados e exibidos no Gerenciador de conteúdo. Os revisores podem filtrar e exibir arquivos e mensagens por fonte de dados, tipo de arquivo, marcas, conversa e muitos outros atributos.
- **Anotações de caso**: os revisores fornecem observações para uma ocorrência na seção notas de caso. Essa lista consolida todas as anotações em um modo de exibição central e inclui informações de revisor e data de envio.

Confira mais informações em [casos de gerenciamento de risco do insider](insider-risk-management-cases.md).

![Investigação de gerenciamento de risco do insider](../media/insider-risk-investigate.png)

### <a name="action"></a>Action

Após os casos serem investigados, os revisores podem tomar medidas rapidamente para resolver o caso ou colaborar com outros participantes do risco em sua organização. Quando os funcionários violam acidentalmente ou inadvertidamente as condições de política, um aviso de lembrete simples pode ser enviado para o funcionário de modelos de aviso que você pode configurar para sua organização. Esses avisos podem servir como lembretes simples ou podem direcionar o funcionário para o treinamento ou orientação para ajudar a evitar um comportamento arriscado futuro. Para obter mais informações, consulte [modelos de aviso de gerenciamento de risco do insider](insider-risk-management-notices.md).

Nas situações mais sérias, talvez você precise compartilhar as informações do caso de gerenciamento de risco do insider com outros revisores em sua organização. O gerenciamento de riscos do insider está totalmente integrado a outros recursos de conformidade da Microsoft 365 para ajudá-lo com a resolução de riscos de ponta a ponta. O escalonamento de um caso para investigação permite transferir dados e gerenciamento do caso para descoberta eletrônica avançada no Microsoft 365. A descoberta eletrônica avançada fornece um fluxo de trabalho de ponta a ponta para preservar, coletar, analisar, analisar e exportar o conteúdo que responde às investigações internas e externas da sua organização. Ele permite que as equipes jurídicas gerenciem todo o fluxo de trabalho de notificação de retenção legal. Para saber mais sobre casos de descoberta eletrônica avançada, confira [visão geral da descoberta eletrônica avançada no Microsoft 365](overview-ediscovery-20.md).

## <a name="scenarios"></a>Cenários

O gerenciamento de riscos do insider pode ajudá-lo a detectar, investigar e realizar ações para reduzir os riscos internos em sua organização em vários cenários comuns:

### <a name="data-theft-by-departing-employee"></a>Roubo de dados por parte do funcionário

Quando os funcionários deixam uma organização, voluntaria ou como resultado da finalização, há muitas vezes legítimas preocupações que a empresa, o cliente e os dados de funcionários estão em risco. Os funcionários podem supor inocentemente que os dados do projeto não são proprietários ou podem estar tentado a assumir dados da empresa para obter um ganho pessoal e violar a política e os padrões jurídicos da empresa. As políticas de gerenciamento de risco do insider que usam o modelo de política de [roubo de dados do funcionário de canpartes](insider-risk-management-policies.md#policy-templates) detectam automaticamente as atividades geralmente associadas a esse tipo de roubo. Com esta política, você receberá automaticamente alertas de atividades suspeitas associadas ao roubo de funcionários de parte, para que possa tomar as ações apropriadas investigativas. A configuração de um [conector de RH da Microsoft 365](import-hr-data.md) para a sua organização é necessária para este modelo de política.

### <a name="intentional-or-unintentional-leak-of-sensitive-or-confidential-information"></a>Perda intencional ou involuntária de informações confidenciais ou confidenciais

Na maioria dos casos, os funcionários experimentam o melhor para lidar corretamente com informações confidenciais e confidenciais. Mas, ocasionalmente, os funcionários fazem erros e informações são acidentalmente compartilhados fora da sua organização ou violam suas políticas de proteção de informações. Às vezes, os funcionários podem acidentalmente vazar ou compartilhar informações confidenciais com más intenções e obter um ganho pessoal. As políticas de gerenciamento de risco do insider criadas usando o modelo de política de [vazamento de dados](insider-risk-management-policies.md#policy-templates) detectam automaticamente as atividades geralmente associadas ao compartilhamento de informações confidenciais ou confidenciais. A configuração de pelo menos uma política de proteção de perda de dados do Microsoft 365 [(DLP)](create-test-tune-dlp-policy.md) para sua organização é necessária para esse modelo de política.

### <a name="actions-and-behaviors-that-violate-corporate-policies"></a>Ações e comportamentos que violam as políticas corporativas

A comunicação entre funcionários é geralmente uma fonte de violações inadvertidas ou mal-intencionadas das políticas corporativas. Essas violações podem incluir linguagem ofensiva, ameaças e anti-intimidação entre funcionários. Esse tipo de atividade contribui para um ambiente de trabalho hostil e pode resultar em ações legais em relação a funcionários e à organização de grande porte. O gerenciamento de riscos do insider usa novos classificadores internos do Microsoft 365 e o [idioma ofensivo no modelo de política de email](insider-risk-management-policies.md#policy-templates) . Esses classificadores e modelos permitem a configuração rápida de uma política para detectar e alertar automaticamente esse tipo de comportamento.

## <a name="ready-to-get-started"></a>Pronto para começar?

Pronto para configurar o gerenciamento de risco do insider para sua organização? Confira [introdução ao gerenciamento de risco do insider](insider-risk-management-configure.md) para configurar os pré-requisitos, criar políticas e começar a receber alertas.
