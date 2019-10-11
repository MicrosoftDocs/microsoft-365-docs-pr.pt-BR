---
title: Implantar o Exchange Online para o Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Percorra o processo de planejamento, distribuição e condução do valor do Exchange Online no Microsoft 365 Enterprise em toda a organização.
ms.openlocfilehash: c11a4ca0216d42f039005616c5d414759b8c0bad
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437811"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Implantar o Exchange Online para o Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

O Exchange Online é o principal serviço de nuvem para email e calendário que ajuda aos usuários colaborarem sem a necessidade de bate-papo em tempo real nem armazenamento centralizado de documentos. O Exchange Online é um elemento fundamental do valor do desenvolvido para trabalho em equipe do Microsoft 365 Enterprise. O Exchange Online permite que você realize mais e trabalhe com mais eficiência com o aplicativo conhecido do Outlook, independentemente do dispositivo em que você está.

O Exchange Online também possui recursos de segurança avançados de, incluindo anti-malware e filtragem de spam, para proteger caixas de correio e recursos de prevenção de perda de dados que impedem que os usuários enviem, por engano, informações confidenciais para pessoas não autorizadas. A segurança do Exchange Online é um elemento fundamental do valor de segurança inteligente do Microsoft 365 Enterprise.

Se você possui pouca experiência com o Exchange Online, confira [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

As fases e etapas a seguir orientam você durante o processo de provisionamento da função do Exchange Online em sua organização, a integração da sua organização ao Exchange Online por meio de uma série de distribuições progressivas e à condução do uso do Exchange Online e de seus valor para os seus usuários finais.

>[!Note]
>Essas instruções de implantação devem ser seguidas somente depois que você concluir [a fase 2-identidade da infraestrutura do Microsoft 365 Enterprise Foundation](identity-infrastructure.md).
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fase 1: prever sua implantação do Exchange Online

Nesta fase, reúna as pessoas para sua implantação do Exchange Online e determine como sua organização usará o Exchange Online para atender às suas necessidades de negócios.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Etapa 1: reunir seus membros de implantação do Exchange Online

Para uma implantação bem-sucedida do Exchange Online na parte superior da [fase 2 – identidade](identity-infrastructure.md) da infraestrutura do Microsoft 365 Enterprise Foundation, você precisa reunir as pessoas certas para entrada e comentários. As principais pessoas incluem tomadores de decisões de negócios, equipe de ti, como arquitetos e implementadores, e defende para seus usuários finais. 

Esses três grupos garantem que sua implantação do Exchange Online inclua considerações que atendam às necessidades de negócios, aspectos técnicos da migração e segurança de caixa de correio e que o resultado é algo que os usuários típicos usarão.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam os aspectos de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Etapa 2: determinar e priorizar seus cenários de negócios do Exchange Online

O Exchange Online pode ser usado para diferentes finalidades. Você precisa descobrir quais finalidades são mapeadas para suas necessidades de negócios nos níveis separados da sua organização, seus grupos de negócios, seus departamentos ou equipes de trabalho e projeto individuais. Você deve direcionar o Exchange Online para tratar de suas necessidades de agendamento e de comunicação de curto e de grupo pequeno. 

Uma maneira de ver os benefícios do Exchange Online é examinar como as pessoas, uma equipe ou a equipe de ti interagem hoje e, em seguida, localizam um cenário apropriado que fornece maneiras mais fáceis de se comunicar, agendar reuniões e colaborar. Tenha em mente que o [Microsoft Teams](teams-workload.md) pode ser uma opção melhor para alguns dos seus cenários de colaboração.

#### <a name="result"></a>Resultado
Uma lista de cenários do Exchange Online que atendem às necessidades da sua organização para comunicação, agendamento e colaboração de vida curta.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, você planeja os aspectos técnicos de uma implantação do Exchange Online e começa a refazê-lo para grupos de usuários selecionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso às caixas de correio do Exchange Online, verifique se você configurou [as políticas de acesso de dispositivo e identidade](identity-access-policies.md) e as [políticas de acesso recomendadas do Exchange Online](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: concluir seu planejamento técnico

Antes de começar o planejamento técnico, determine se deseja usar o FastTrack. Se sua organização tiver mais de 50 estações e estiver participando de um [plano qualificado](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), você poderá usar [o FastTrack para a Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *disponível sem custos adicionais* para orientá-lo durante o planejamento, a implantação e a adoção do serviço. Ou você mesmo pode cumprir essa tarefa usando os Assistentes de Integração do FastTrack, que estão disponíveis no [FastTrack](https://fasttrack.microsoft.com/) assim que você entrar com sua conta do Microsoft 365.

Se você estiver fazendo seu próprio planejamento ou em conjunto com o FastTrack, precisará determinar se a sua rede e organização estão prontos para o Exchange Online. É especialmente importante que você atenda aos critérios de saída para a [rede](networking-infrastructure.md) em sua infraestrutura de base para usuários conectados à rede da sua organização. Preste atenção especial à largura de banda da Internet, taxa de transferência e atrasos de tráfego para maximizar o desempenho do tráfego adicional para emails e anexos baseados no Exchange Online.

Use estes recursos para se preparar para os aspectos técnicos de uma distribuição do Exchange Online: 

- [Formas de migrar várias contas de email para o Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Colaboração no Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Destinatários no Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)

Para uma compreensão melhor da segurança no Exchange Online, revise os seguintes recursos:

- [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Segurança e conformidade para o Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Proteção antispam e antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

Em seguida, use estes recursos para entender o gerenciamento de caixa de correio do Exchange Online:

- [Criar caixas de correio do usuário no Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Gerenciar caixas de correio de usuários](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Criar e gerenciar grupos de distribuição](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Resultado

Você entende migração de caixa de correio, segurança e gerenciamento e está pronto para começar a implantar o Exchange Online para grupos selecionados em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Para a maioria das organizações de médio e grande porte, você deve executar um piloto de ti com seus stakeholders da fase 1, pioneiros e entusiastas técnicos. Durante um piloto de TI:

- Dê aos participantes do piloto licenças da Microsoft 365 e migre suas caixas de correio locais para o Exchange Online.
- Dê aos participantes do piloto um conjunto de exercícios para testar email, agendamento e outros recursos do Exchange Online.
- Determine sua estratégia de gerenciamento de mudanças e produzam materiais para conduzir a adoção de usuário de toda a organização do Outlook e do Exchange Online. 
 
  Os materiais de gerenciamento de mudanças podem incluir texto de comunicados de email, planos de treinamento internos, cartazes e apresentações. Esses materiais informarão à sua organização sobre o Exchange Online e seus benefícios com as metas de aumentar a conscientização e orientar o uso. Consulte o artigo [estratégia de gerenciamento de mudanças para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para algumas ideias.

- Peça aos participantes piloto de TI que examinem os materiais de gerenciamento de mudanças com base em suas experiências. Eles podem fornecer dicas sobre práticas recomendadas e conselhos sobre como descrever melhor os benefícios do Outlook e do Exchange Online e como usá-lo para comunicação e agendamento.

#### <a name="result"></a>Resultado

Seu piloto de ti do Exchange Online está completo e os materiais iniciais de gerenciamento de alterações foram desenvolvidos, revisados e refinados.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir o seu piloto de ti, distribua o Exchange Online para um grupo ou departamento comercial em sua organização. Se sua organização estiver usando um serviço de email local, como o Exchange Server, essa distribuição consistirá em migração de caixa de correio. Essa distribuição deve incluir:

- Identificação dos principais cenários de negócios do Exchange Online no grupo de negócios.
- Atividades de anúncio para informar os usuários sobre as expectativas e os cronogramas para o uso do Exchange Online para departamentos e equipes de trabalho ou de projeto.
- Migração de caixas de correio locais de membros do seu grupo de negócios para o Exchange Online.
- Fornecimento de [treinamento do usuário](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) no Outlook ou links para recursos para apresentar o Outlook e como usá-lo.
- Um mecanismo de feedback, como uma equipe central do Microsoft Teams que contém todos no grupo de negócios, para coletar comentários e solucionar problemas dos usuários no grupo de negócios.

Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios está funcionando com o Outlook e o Exchange Online, e os materiais de gerenciamento de alterações foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, você conclui a distribuição do Exchange Online e dá suporte aos usuários para ajudá-los a concretizar seus benefícios.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Etapa 1: distribuir o Exchange Online para o restante da sua organização

A implantação para o restante da sua organização deve incluir:

- Identificação de cenários de negócios importantes para o Exchange Online em grupos de negócios separados.
- Uso de seus materiais de gerenciamento de mudanças refinados para atividades de lançamento a fim de informar a organização sobre as expectativas e os cronogramas para o uso do Exchange Online.
- Migração das caixas de correio do restante da sua organização para o Exchange Online.
- Fornecer [treinamento do usuário](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) no Outlook ou fornecer links para recursos para apresentar o Outlook e como usá-lo.
- Um mecanismo de comentários, como uma Equipe central que contém todas as pessoas, para coletar comentários e problemas de usuários da organização. Se sua organização tiver menos de 2.500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado

Sua organização está em funcionamento e sua estratégia de gerenciamento de mudanças está no local para informar, treinar e permitir que os usuários usem o Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Depois de distribuir o Exchange Online para toda a sua organização, você deve continuar a empregar sua estratégia de gerenciamento de mudanças para:

- Sua liderança é promover o Exchange Online como a principal ferramenta para comunicação e agendamento individuais e de curta duração.
- Incentivar as pessoas a usá-lo para o grupo de negócios, o departamento, o trabalho e as comunicações da equipe de projeto, o calendário e a colaboração.

Veja algumas sugestões de atividades:

- Veja [Fatores de sucesso do Office 365](https://aka.ms/successfactors) para saber mais sobre as práticas recomendadas gerais para a adoção do serviço de nuvem. 
- Veja [relatórios de atividades do Office 365](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para entender o uso do serviço do Office 365 em sua organização. Se você não for um administrador global do Office 365 para sua organização, peça a um administrador global para conceder à sua conta de usuário permissões para ler relatórios, de forma que você possa acessar os relatórios de atividades.
- Monitore seu local de comentários (um canal público em uma equipe do Microsoft Teams ou Yammer) para problemas e comentários de pessoas sobre suas experiências com o Exchange Online. Solucione problemas e questões assim que possível para evitar pessoas frustradas e demonstrar suporte para a distribuição.
- Identificar e promova especialistas em cada grupo de negócios e destacar suas práticas recomendadas usando o Outlook. Comunique os sucessos dessas pessoas para a organização para demonstrar o sucesso e a adoção do projeto. O endosso por líderes técnicos dentro de um grupo de negócios pode exercer uma poderosa influência sobre líderes e colegas.

#### <a name="result"></a>Resultado

Sua organização adotou o Exchange Online e o Outlook como a ferramenta de agendamento e a comunicação de curta duração de grupo principal e de pequenos grupos.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para inspecionar a Microsoft e saber como migramos para o Exchange Online e usando o Exchange Online Protection para proteger contra ataques cibernéticos, consulte:

- [A Microsoft migra 150 mil caixas de correio para o Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [A Microsoft usa inteligência contra ameaças para proteger, detectar e responder a ameaças](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [A Microsoft impede tentativas de phishing com o Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Próximas etapas

Consulte estes recursos para a manutenção contínua do Exchange Online:

- [Centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Monitoramento, relatórios e rastreamento de mensagens no Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Fazendo backup de email no Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
