---
title: Implantar o Exchange Online para Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Strat_O365_Enterprise
description: As etapas no processo de planejamento, aplicação e orientando o valor do Exchange Online no Microsoft 365 Enterprise em toda a organização.
ms.openlocfilehash: aafa1b28546eb77938bb3e4a5ebe9ccd60b9a60b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865301"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Implantar o Exchange Online para Microsoft 365 Enterprise

O Exchange Online é o serviço de nuvem principal do email e calendário que ajuda os usuários colaborem de formas que não exigem bate-papo em tempo real ou centralizados de armazenamento de documentos. O Exchange Online como fazer comunicação temporários e de grupo individuais e pequenas e agendamento e é um elemento importante dos de criação para o valor de trabalho em equipe do Microsoft 365 Enterprise. Exchange Online permite realizar mais e trabalhar com mais eficiência com o aplicativo conhecido do Outlook, não importa qual dispositivo estiver.

O Exchange Online também tem recursos avançados de segurança incluindo antimalware e antispam filtragem para proteger as caixas de correio e recursos de prevenção de perda de dados que impedir que usuários por engano enviando informações confidenciais para pessoas não autorizadas. Segurança do Exchange Online é um elemento importante do valor inteligentes de segurança do Microsoft 365 Enterprise.

Se você estiver totalmente nova para o Exchange Online, consulte [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

As fases e etapas a seguir orientam você pelo processo de envisioning a função do Exchange Online em sua organização, a inclusão de sua organização para o Exchange Online por meio de uma série de distribuições progressivas e orientando o uso do Exchange Online e sua valor para seus usuários finais.

>[!Note]
>Estas instruções de implantação devem ser seguidas somente depois que você tiver concluído a [Fase 2-Identity](identity-infrastructure.md) da infra-estrutura 365 Enterprise do Microsoft foundation.
>

## <a name="phase-1-envision"></a>Fase 1: visualizar

Nesta fase, você pode reunir as pessoas para sua implantação do Exchange Online e determinar como sua organização usará o Exchange Online para atender às suas necessidades de negócios.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Etapa 1: Reúna os membros da sua implantação Exchange Online

Para uma implantação bem-sucedida do Exchange Online na parte superior da [Fase 2-Identity](identity-infrastructure.md) da infra-estrutura 365 Enterprise do Microsoft foundation, você precisará fazer as pessoas certas para entrada e comentários. Pessoas-chave incluem tomadores de decisão de negócios, a equipe de TI, como arquitetos e implementadores e defensores para seus usuários finais. 

Esses três grupos Certifique-se de que sua implantação do Exchange Online inclui considerações que abordam as necessidades comerciais, aspectos técnicos de migração de caixa de correio e de segurança e que o resultado será algo que os usuários típicos usará.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam os aspectos de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Etapa 2: Determine e priorizar os cenários de negócios Exchange Online

O Exchange Online pode ser usado para diferentes objetivos. Você precisa descobrir quais fins mapeiam para suas necessidades de negócios nos níveis separados de sua organização, os grupos de negócios, sua departamentos ou equipes de projetos e de trabalho individuais. Você deve orientar o Exchange Online para atender às sua comunicação temporários e de grupo individuais e pequenas e necessidades de agendamento. 

Uma maneira de ver os benefícios do Exchange Online é examinar como indivíduos, uma equipe ou equipe v interagir hoje e localizar um cenário apropriado que fornece formas mais fácil para agendar reuniões, se comunicar e colaborar. Tenha em mente que [Equipes da Microsoft que](teams-workload.md) pode ser uma melhor opção para alguns dos seus cenários de colaboração.

O Exchange Online habilita esses cenários estratégicos de negócios para o Microsoft 365 Enterprise:

- Colaborar em documentos em tempo real ou em seu próprio tempo para simplificar o processo de cocriação
- Gerenciar projetos, tarefas e prazos para atender seus objetivos de negócios
- Compreender os hábitos de trabalho para melhorar a influência e o impacto
- Comunicar-se com sua equipe para se manter informado, solicitar sugestões e criar coesão e consenso
- Armazenar e compartilhar arquivos dentro e fora de sua organização para trabalhar de forma transparente entre os limites organizacionais
- Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível
- Proteger informações e reduzir o risco de perda de dados
- Detectar e proteger contra ameaças externas 
- Monitorar, relatar e analisar atividade para reagir imediatamente para fornecer segurança da organização
- Oferecer suporte à sua organização com privacidade e conformidade aprimoradas para atender ao RGPD (Regulamento Geral sobre a Proteção de Dados)

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Resultado
Uma lista de cenários Exchange Online que abordam as necessidades da sua organização para comunicação, agendamento e temporários e colaboração.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, você planeje os aspectos técnicos de uma implantação do Exchange Online e iniciar a distribuição para grupos selecionados de usuários.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso a caixas de correio Exchange Online, certifique-se de que você tenha configurado a [identidade e dispositivo políticas de acesso](identity-access-policies.md) e o [recomendado políticas de acesso do Exchange Online](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: Concluir seu planejamento técnico

Antes de começar a planejar técnica, determine se você deseja usar FastTrack. Se sua organização tiver mais de 50 estações e estiver participando de um [plano de elegível](https://technet.microsoft.com/library/dn783224.aspx), você pode usar [FastTrack para 365 da Microsoft](https://fasttrack.microsoft.com/microsoft365), disponíveis sem custo adicional para guiá-lo por meio de planejamento, implantação e adoção do serviço. Ou então, você pode concluir este trabalho por conta própria usando os assistentes de inclusão de FastTrack, que foram disponibilizados por [FastTrack](https://fasttrack.microsoft.com/) depois que você entrar com sua conta do Office 365.

Se você estiver fazendo seu próprio processo de planejamento, ou em conjunto com FastTrack, você precisa determinar se a sua rede e a organização estão prontos para o Exchange Online. É especialmente importante que você atenda aos critérios de saída de rede em sua infra-estrutura foundation, com atenção especial a largura de banda da Internet, produtividade e atrasos de tráfego para maximizar o desempenho para o tráfego adicional para o Exchange Online com base no email e anexos.

Use estes recursos para preparar os aspectos técnicos de uma distribuição do Exchange Online: 

- [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Supervisor de migração de email do Office 365](https://portal.office.com/onboarding/mailsetupadvisor#/) (deve estar conectado à sua assinatura do Office 365)
- [Colaboração no Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatários no Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Para melhor compreensão da segurança no Exchange Online, revise os seguintes recursos:

- [Permissões no Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Segurança e conformidade para Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Proteção antispam e antimalware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Em seguida, use esses recursos para compreender o gerenciamento de caixas de correio Exchange Online:

- [Criar caixas de correio do usuário no Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Gerenciar caixas de correio de usuários](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Criar e gerenciar grupos de distribuição](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Resultado

Entender o gerenciamento, segurança e migração de caixa de correio e estiver pronto para iniciar a aplicação do Exchange Online para grupos selecionados em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Na maioria das organizações de médio e grande porte, você deve realizar um piloto de TI com os participantes da Fase 1 e usuários pioneiros e entusiastas técnicos. Durante um piloto de TI:

- Escolha um cenário de negócios Exchange Online em que os participantes piloto IT podem practice.
- Dê participantes piloto licenças do Office 365 e migrar suas caixas de correio no local para o Exchange Online.
- Dê um conjunto de exercícios para testar o email do Exchange Online, agendamento e outros recursos de participantes piloto.
- Determine sua estratégia de gerenciamento de alteração e produzir materiais para incentivar a adoção de usuário de toda a organização do Exchange Online. Materiais de gerenciamento de alteração podem incluir texto de comunicado de e-mail, planos de treinamento interno, cartazes corredor e apresentações. Esses materiais informará sua organização sobre o Exchange Online e seus benefícios com as metas de geração de divulgação e o uso que controla. Consulte o artigo de [alterar a estratégia de gerenciamento para equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para algumas ideias.
- Peça participantes piloto IT para revisar os materiais de gerenciamento de alteração com base nas suas experiências. Eles podem fornecer dicas sobre as práticas recomendadas e recomendações sobre como melhor descrevem os benefícios do Exchange Online e como usá-lo para comunicação e agendamento.

#### <a name="result"></a>Resultado

Seu piloto de TI do Exchange Online é concluído e os materiais de gerenciamento de alteração inicial foram desenvolvidos, analisados e refinados.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir seu piloto IT, distribuir o Exchange Online para um grupo comercial ou o departamento na sua organização. Se sua organização estiver usando um serviço de email local como o Exchange Server, essa distribuição consiste de migração de caixa de correio. Essa distribuição deve incluir:

- Identificação dos cenários de negócios para o Exchange Online dentro do grupo de negócios.
- Atividades de comunicado para informar aos usuários as expectativas e cronogramas para uso do Exchange Online para departamentos e equipes de trabalho ou projeto.
- Migração de caixas de correio local dos seus membros do grupo de negócios para o Exchange Online.
- Fornecimento de treinamento de usuário no Exchange Online ou links para recursos para introduzir o Exchange Online e como usá-lo.
- Um mecanismo de feedback, como uma equipe central do Microsoft Teams que contém todos no grupo de negócios, para coletar comentários e solucionar problemas dos usuários no grupo de negócios.

Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios está atualizado e execução com o Exchange Online e os materiais de gerenciamento de alteração foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, você concluir a distribuição do Exchange Online e suporte para seus usuários para ajudá-los a obter os seus benefícios.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Etapa 1: Implementar o Exchange Online para o restante de sua organização

A implantação para o restante da sua organização deve incluir:

- Identificação dos cenários de negócios para o Exchange Online dentro dos grupos de negócios separado.
- Uso de seus materiais de gerenciamento de alteração refinados para atividades de comunicado informar a sua organização das expectativas e cronogramas para uso do Exchange Online.
- Migração de caixas de correio para o restante da sua organização para o Exchange Online.
- Fornecimento de treinamento de usuário no Exchange Online ou fornecem links para recursos para introduzir o Exchange Online e como usá-lo.
- Um mecanismo de comentários, como uma Equipe central que contém todas as pessoas, para coletar comentários e problemas de usuários da organização. Se sua organização tiver menos de 2.500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado

Sua organização está atualizado e execução e sua estratégia de gerenciamento de alteração está em andamento para informar, treinar e permitir que os usuários usem o Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Após a aplicação do Exchange Online em toda sua organização, você deve continuar a empregar sua estratégia de gerenciamento de alteração para:

- Ter sua liderança promover o Exchange Online como a principal ferramenta para individual e temporários e comunicação e agendamento.
- Incentive indivíduos usá-lo para o grupo de negócios, departamental, work e comunicações de equipe, calendário e colaboração do projeto.

Aqui estão algumas sugestões de atividades:

- Veja [Orientação sobre a adoção do Office 365](https://aka.ms/successfactors) para saber mais sobre as práticas recomendadas gerais para a adoção do serviço de nuvem. 
- Veja [relatórios de atividades do Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para entender o uso do serviço do Office 365 em sua organização. Se você não for um administrador global do Office 365 para sua organização, peça a um administrador global para conceder à sua conta de usuário permissões para ler relatórios, de forma que você possa acessar os relatórios de atividades.
- Monitore sua jurisdição comentários (um canal pública em uma equipe de equipes ou o Yammer central) para os problemas e comentários de pessoas sobre suas experiências com o Exchange Online. Resolver problemas e perguntas mais rápido possível para impedir frustrados indivíduos e demonstrar o suporte para a distribuição.
- Identificar e criar campeões em cada grupo de negócios e realce seus trabalhos realizados e práticas recomendadas usando o Exchange Online. Refletem seus êxitos check-out para a organização para mostrar a adoção e o sucesso do projeto. Aval líderes técnicos dentro de um grupo de negócios pode exercer uma poderosa influência sobre líderes e pares.

#### <a name="result"></a>Resultado

Sua organização adotou Exchange Online como sua comunicação temporários e de grupo individuais e pequenos primário e a ferramenta de agendamento.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para surgir dentro da Microsoft e saiba como a empresa migradas para o Exchange Online e está usando o Exchange Online Protection para proteger contra ataques virtuais, consulte:

- [A Microsoft migra 150 mil caixas de correio para o Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [A Microsoft usa inteligência contra ameaças para proteger, detectar e responder a ameaças](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [A Microsoft impede tentativas de phishing com o Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Próximas etapas

Consulte estes recursos para a manutenção contínua do Exchange Online:

- [Centro de administração do Exchange no Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Monitoramento, relatórios e rastreamento de mensagem no Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Fazendo backup de email no Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
