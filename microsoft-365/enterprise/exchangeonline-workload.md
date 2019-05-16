---
title: Implantar o Exchange Online para o Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/28/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Percorra o processo de planejamento, distribuição e condução do valor do Exchange Online no Microsoft 365 Enterprise em toda a organização.
ms.openlocfilehash: c54c80a955d86028ac473857cbdcb8b1a8f272d3
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072281"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Implantar o Exchange Online para o Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

O Exchange Online é o seu serviço de nuvem principal para email e calendário que ajuda os usuários a colaborar de maneiras que não exigem chat em tempo real ou armazenamento de documento centralizado. O Exchange Online é o modo como você realiza comunicação e agendamento de curto e pequeno grupo e é um elemento fundamental do valor do desenvolvido para trabalho em equipe do Microsoft 365 Enterprise. O Exchange Online permite que você realize mais e trabalhe com mais eficiência com o aplicativo conhecido do Outlook, independentemente do dispositivo em que você está.

O Exchange Online também tem recursos avançados de segurança, incluindo filtragem antimalware e antispam para proteger caixas de correio e recursos de prevenção contra perda de dados que impedem que os usuários enviem incorretamente informações confidenciais para pessoas não autorizadas. A segurança do Exchange Online é um elemento fundamental do valor de segurança inteligente do Microsoft 365 Enterprise.

Se você tiver uma identidade visual no Exchange Online, confira [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

As fases e etapas a seguir orientam você durante o processo de provisionamento da função do Exchange Online em sua organização, a integração da sua organização ao Exchange Online por meio de uma série de distribuições progressivas e à condução do uso do Exchange Online e de seus valor para os seus usuários finais.

>[!Note]
>Essas instruções de implantação devem ser seguidas somente depois que você concluir a [fase 2-identidade](identity-infrastructure.md) da infraestrutura do Microsoft 365 Enterprise Foundation.
>

## <a name="phase-1-envision"></a>Fase 1: visualizar

Nesta fase, reúna as pessoas para sua implantação do Exchange Online e determine como sua organização usará o Exchange Online para atender às suas necessidades de negócios.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Etapa 1: reunir seus membros de implantação do Exchange Online

Para uma implantação bem-sucedida do Exchange Online na parte superior da [fase 2 – identidade](identity-infrastructure.md) da infraestrutura do Microsoft 365 Enterprise Foundation, você precisa ter as pessoas certas para obter informações e obter comentários. As principais pessoas incluem tomadores de decisões de negócios, equipe de ti, como arquitetos e implementadores, e defende para seus usuários finais. 

Esses três grupos garantem que sua implantação do Exchange Online inclua considerações que atendam às necessidades de negócios, aspectos técnicos da migração e segurança de caixa de correio e que o resultado será algo que os usuários típicos usarão.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam os aspectos de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Etapa 2: determinar e priorizar seus cenários de negócios do Exchange Online

O Exchange Online pode ser usado para diferentes finalidades. Você precisa descobrir quais finalidades são mapeadas para suas necessidades de negócios nos níveis separados da sua organização, seus grupos de negócios, seus departamentos ou equipes de trabalho e projeto individuais. Você deve direcionar o Exchange Online para tratar de suas necessidades de agendamento e de comunicação de curto e de grupo pequeno. 

Uma maneira de ver os benefícios do Exchange Online é examinar como as pessoas, uma equipe ou a equipe de ti interagem hoje e, em seguida, localizam um cenário apropriado que fornece maneiras mais fáceis de se comunicar, agendar reuniões e colaborar. Tenha em mente que o [Microsoft Teams](teams-workload.md) pode ser uma opção melhor para alguns dos seus cenários de colaboração.

O Exchange Online habilita esses cenários estratégicos de negócios para o Microsoft 365 Enterprise:

- Colaborar em documentos em tempo real ou em seu próprio tempo para simplificar o processo de cocriação
- Gerenciar projetos, tarefas e prazos para atender seus objetivos de negócios
- Compreender os hábitos de trabalho para melhorar a influência e o impacto
- Comunicar-se com sua equipe para se manter informado, solicitar sugestões e criar coesão e consenso
- Armazenar e compartilhar arquivos dentro e fora de sua organização para trabalhar de forma transparente entre os limites organizacionais
- Trabalhar com segurança de qualquer lugar, a qualquer momento e em qualquer dispositivo para alcançar mais, mantendo um estilo de trabalho flexível
- Proteger informações e reduzir o risco de perda de dados
- Detectar e proteger contra ameaças externas 
- Monitorar, relatar e analisar atividade para reagir de forma imediata para fornecer segurança organizacional
- Oferecer suporte à sua organização com privacidade e conformidade aprimoradas para atender ao RGPD (Regulamento Geral sobre a Proteção de Dados)

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

#### <a name="result"></a>Resultado
Uma lista de cenários do Exchange Online que atendem às necessidades da sua organização para comunicação, agendamento e colaboração de vida curta.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, você planeja os aspectos técnicos de uma implantação do Exchange Online e começa a refazê-lo para grupos de usuários selecionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso às caixas de correio do Exchange Online, verifique se você configurou [as políticas de acesso de dispositivo e identidade](identity-access-policies.md) e as [políticas de acesso recomendadas do Exchange Online](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: Concluir seu planejamento técnico

Antes de começar o planejamento técnico, determine se você deseja usar o FastTrack. Se sua organização tiver mais de 50 estações e estiver participando de um [plano qualificado](https://technet.microsoft.com/library/dn783224.aspx), você poderá usar [o FastTrack para a Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponível sem custos adicionais para orientá-lo durante o planejamento, a implantação e a adoção do serviço. Ou você pode fazer isso sozinho usando assistentes de integração do FastTrack, que estão disponíveis no [FastTrack](https://fasttrack.microsoft.com/) quando você entra com sua conta do Office 365.

Se você estiver fazendo seu próprio planejamento ou em conjunto com o FastTrack, precisará determinar se a sua rede e organização estão prontos para o Exchange Online. É especialmente importante que você atenda aos critérios de saída para a rede em sua infraestrutura de base, com atenção especial à largura de banda da Internet, taxa de transferência e atrasos de tráfego para maximizar o desempenho do tráfego adicional para o Exchange Emails e anexos baseados em online.

Use estes recursos para se preparar para os aspectos técnicos de uma distribuição do Exchange Online: 

- [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Colaboração no Exchange Online](https://technet.microsoft.com/library/jj983794(v=exchg.150).aspx)
- [Destinatários no Exchange Online](https://technet.microsoft.com/library/jj200702(v=exchg.150).aspx)

Para uma compreensão melhor da segurança no Exchange Online, revise os seguintes recursos:

- [Permissões no Exchange Online](https://technet.microsoft.com/library/jj200692(v=exchg.150).aspx) 
- [Segurança e conformidade para o Exchange Online](https://technet.microsoft.com/library/jj200706(v=exchg.150).aspx) 
- [Proteção antispam e antimalware](https://technet.microsoft.com/library/jj200731(v=exchg.150).aspx)

Em seguida, use estes recursos para entender o gerenciamento de caixa de correio do Exchange Online:

- [Criar caixas de correio do usuário no Exchange Online](https://technet.microsoft.com/library/jj907304(v=exchg.150).aspx)
- [Gerenciar caixas de correio de usuários](https://technet.microsoft.com/library/bb123809(v=exchg.150).aspx) 
- [Criar e gerenciar grupos de distribuição](https://technet.microsoft.com/library/bb124513%28v=exchg.150%29.aspx)

#### <a name="result"></a>Resultado

Você entende migração de caixa de correio, segurança e gerenciamento e está pronto para começar a implantar o Exchange Online para grupos selecionados em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Na maioria das organizações de médio e grande porte, você deve realizar um piloto de TI com os participantes da Fase 1 e usuários pioneiros e entusiastas técnicos. Durante um piloto de TI:

- Escolha um cenário comercial do Exchange Online no qual os participantes do seu piloto de ti podem praticar.
- Dê aos participantes do piloto licenças do Office 365 e migre suas caixas de correio locais para o Exchange Online.
- Dê aos participantes do piloto um conjunto de exercícios para testar email, agendamento e outros recursos do Exchange Online.
- Determine sua estratégia de gerenciamento de mudanças e produzam materiais para conduzir a adoção de usuário do Exchange Online para toda a organização. Os materiais de gerenciamento de alterações podem incluir texto de anúncio de email, planos de treinamento internos, cartazes de corredor e apresentações. Esses materiais informarão à sua organização sobre o Exchange Online e seus benefícios com as metas de aumentar a conscientização e orientar o uso. Consulte o artigo [estratégia de gerenciamento de mudanças para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para algumas ideias.
- Peça aos participantes do piloto de ti para analisar os materiais de gerenciamento de mudanças com base em suas experiências. Eles podem fornecer dicas sobre práticas recomendadas e conselhos sobre como descrever melhor os benefícios do Exchange Online e como usá-lo para comunicação e agendamento.

#### <a name="result"></a>Resultado

Seu piloto de ti do Exchange Online está completo e os materiais iniciais de gerenciamento de alterações foram desenvolvidos, revisados e refinados.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir o seu piloto de ti, distribua o Exchange Online para um grupo ou departamento comercial em sua organização. Se sua organização estiver usando um serviço de email local, como o Exchange Server, essa distribuição consistirá em migração de caixa de correio. Essa distribuição deve incluir:

- Identificação dos principais cenários de negócios do Exchange Online no grupo de negócios.
- Atividades de anúncio para informar os usuários sobre as expectativas e os cronogramas para o uso do Exchange Online para departamentos e equipes de trabalho ou de projeto.
- Migração de caixas de correio locais de membros do seu grupo de negócios para o Exchange Online.
- Fornecimento de treinamento do usuário no Exchange Online ou links para recursos para apresentar o Exchange Online e como usá-lo.
- Um mecanismo de feedback, como uma equipe central do Microsoft Teams que contém todos no grupo de negócios, para coletar comentários e solucionar problemas dos usuários no grupo de negócios.

Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios está em execução com o Exchange Online e os materiais de gerenciamento de alterações foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, você conclui a distribuição do Exchange Online e dá suporte aos usuários para ajudá-los a concretizar seus benefícios.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Etapa 1: distribuir o Exchange Online para o restante da sua organização

A implantação para o restante da sua organização deve incluir:

- Identificação de cenários de negócios importantes para o Exchange Online em grupos de negócios separados.
- Uso de seus materiais de gerenciamento de mudanças refinados para atividades de lançamento a fim de informar a organização sobre as expectativas e os cronogramas para o uso do Exchange Online.
- Migração das caixas de correio do restante da sua organização para o Exchange Online.
- Fornecer treinamento do usuário no Exchange Online ou fornecer links para recursos para apresentar o Exchange Online e como usá-lo.
- Um mecanismo de comentários, como uma Equipe central que contém todas as pessoas, para coletar comentários e problemas de usuários da organização. Se sua organização tiver menos de 2.500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado

Sua organização está em funcionamento e sua estratégia de gerenciamento de mudanças está no local para informar, treinar e permitir que os usuários usem o Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Depois de distribuir o Exchange Online para toda a sua organização, você deve continuar a empregar sua estratégia de gerenciamento de mudanças para:

- Sua liderança é promover o Exchange Online como a principal ferramenta para comunicação e agendamento individuais e de curta duração.
- Incentivar as pessoas a usá-lo para o grupo de negócios, o departamento, o trabalho e as comunicações da equipe de projeto, o calendário e a colaboração.

Veja algumas sugestões de atividades:

- Veja [Orientação sobre a adoção do Office 365](https://aka.ms/successfactors) para saber mais sobre as práticas recomendadas gerais para a adoção do serviço de nuvem. 
- Veja [relatórios de atividades do Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para entender o uso do serviço do Office 365 em sua organização. Se você não for um administrador global do Office 365 para sua organização, peça a um administrador global para conceder à sua conta de usuário permissões para ler relatórios, de forma que você possa acessar os relatórios de atividades.
- Monitore seu local de comentários (um canal público em uma equipe do Microsoft Teams ou Yammer) para problemas e comentários de pessoas sobre suas experiências com o Exchange Online. Atenda perguntas e problemas com a mesma rapidez possível para evitar pessoas frustradas e demonstrar o suporte para a distribuição.
- Identificar e promova especialistas em cada grupo de negócios e destacar suas realizações e práticas recomendadas usando o Exchange Online. Reflita o sucesso da organização para mostrar o sucesso e a adoção do projeto. O endosso por líderes técnicos dentro de um grupo de negócios pode exercer uma poderosa influência sobre líderes e colegas.

#### <a name="result"></a>Resultado

Sua organização adotou o Exchange Online como a ferramenta de agendamento e a comunicação de curta duração de grupo principal e de pequeno porte.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para inspecionar a Microsoft e aprender como a empresa migrou para o Exchange Online e está usando o Exchange Online Protection para proteger contra ataques cibernéticos, consulte:

- [A Microsoft migra 150 mil caixas de correio para o Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [A Microsoft usa inteligência contra ameaças para proteger, detectar e responder a ameaças](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [A Microsoft impede tentativas de phishing com o Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Próximas etapas

Consulte estes recursos para a manutenção contínua do Exchange Online:

- [Centro de administração do Exchange no Exchange Online](https://technet.microsoft.com/library/jj200743(v=exchg.150).aspx) 
- [Monitoramento, relatórios e rastreamento de mensagens no Exchange Online](https://technet.microsoft.com/library/jj200725(v=exchg.150).aspx)
- [Fazendo backup de email no Exchange Online](https://technet.microsoft.com/library/dn440734(v=exchg.150).aspx) 
