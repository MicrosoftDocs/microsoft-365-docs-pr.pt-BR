---
title: Implantar o Microsoft Teams para o Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Percorra o processo de planejamento, implantação e geração de valor do Microsoft Teams no Microsoft 365 Enterprise para toda a sua organização.
ms.openlocfilehash: 1e7519817a10eb4aa710dff2d4c74c9390c9f6f6
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072851"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Implantar o Microsoft Teams para o Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

O Microsoft Teams reúne chat, conferências, compartilhamento de documentos e conversas em threads de forma que facilita a criação e o compartilhamento conteúdo em grupos. O Temas é uma maneira de trabalhar em equipe e colaborar com o Microsoft 365 Enterprise e é um elemento essencial do valor de trabalho em equipe do Microsoft 365. Se você não conhecer o Teams, confira a [Visão geral do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview).
 
Se você estiver usando o Skype for Business atualmente, estamos incorporando recursos desse aplicativo no Teams. Isso será feito ao longo do tempo e, no final, o Teams se tornará a única experiência do cliente. Como um cliente importante do Skype for Business, a Microsoft está aqui para ajudá-lo. Confira [Jornada do Skype for Business para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/journey-skypeforbusiness-teams) para saber mais.

As fases e etapas a seguir orientarão você pelo processo de concepção da função do Teams em sua organização, de integração da sua organização no Teams por meio de uma série de implantações progressivas e de geração de uso do Teams e do seu valor para os usuários finais. 

Antes de começar, verifique se você configurou as fases corretas da [infraestrutura básica](deploy-foundation-infrastructure.md) para que suas equipes tenham os recursos de segurança necessários.

## <a name="phase-1-envision"></a>Fase 1: visualizar

Nesta fase, reúna as pessoas para sua implantação do Teams e determine como sua organização usará o Teams para atender às suas necessidades de negócios.

### <a name="step-1-gather-your-teams-deployment-members"></a>Etapa 1: reunir sua equipe de implantação do Teams
Para obter uma implantação bem-sucedida do Teams sobre a [infraestrutura básica](deploy-foundation-infrastructure.md) do Microsoft 365, você precisa das pessoas certas para fornecer comentários e feedback. Pessoas essenciais incluem tomadores de decisão, funcionários de TI como arquitetos e implementadores, e representantes dos seus usuários finais. 

Esses três grupos garantem que sua implantação do Teams inclua considerações que atendam às suas necessidades de negócios, aos aspectos técnicos do licenciamento e da segurança e que o Teams será algo que seus usuários tipicamente usarão.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam os aspectos de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-teams-business-scenarios"></a>Etapa 2: determinar e priorizar seus cenários de negócios do Teams
O Teams pode ser usado para várias finalidades diferentes. Você precisa descobrir quais finalidades atendem às suas necessidades de negócios nos diferentes níveis de sua organização, em seus grupos de negócios, seus departamentos e suas equipes individuais de trabalho e de projetos. Confira a [Biblioteca de produtividade do Microsoft 365](https://www.microsoft.com/microsoft-365/success/?rtc=1) para obter exemplos para ajudar a definir seus cenários do Teams. 

Você deve direcionar o Teams para lidar com equipes rápidas e altamente colaborativas que trabalham próximas e exigem mais recursos do que o email com o Exchange Online pode fornecer. Exemplos são chats de grupo em tempo real com um histórico gravado e um local comum e de fácil acesso para armazenar arquivos e anotações. 

Uma maneira de ver os benefícios do Teams é examinar como uma equipe física ou virtual interage hoje e, então, descobrir o cenário do Teams apropriado que substitui a interação e oferece maneiras mais fáceis de colaborar e oferecer recursos adicionais.

O Teams habilita esses cenários estratégicos de negócios para o Microsoft 365 Enterprise:

- Comunicar-se com sua equipe para se manter informado, solicitar sugestões e criar coesão e consenso
- Envolver os firstline workers para habilitar a transformação digital
- Compreender os hábitos de trabalho para melhorar a influência e o impacto

Para saber mais, confira [Transformação digital usando o Microsoft 365](http://transform.microsoft.com). 

#### <a name="microsoft-teams-for-highly-regulated-data"></a>Microsoft Teams para dados altamente controlados

Dados altamente controlados estão sujeitos a normas regionais ou são os dados mais importantes para sua organização, como segredos comerciais, informações financeiras ou de recursos humanos e de estratégia da organização. Você pode configurar uma equipe para acesso restrito, classificação de dados, prevenção de perda de dados e criptografia desse tipo de dados. Para saber mais, confira [Sites do Microsoft Teams e SharePoint Online para dados altamente controlados](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultado

Uma lista dos cenários do Teams que atendem às necessidades par sua organização para colaboração e trabalho de equipe.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, planeje os aspectos técnicos de uma implantação do Teams e comece a distribua o Teams para grupos seletos de usuários.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso das equipes, assegure-se de ter configurado as [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint Online](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: Concluir seu planejamento técnico

Antes de começar o planejamento técnico, determine se deseja usar o FastTrack. Se sua organização tiver mais de 50 licenças e participar de um [plano qualificado](https://technet.microsoft.com/library/dn783224.aspx), é possível usar o [FastTrack para Microsoft 365](https://fasttrack.microsoft.com/microsoft365), disponível sem custo adicional para orientá-lo pelo planejamento, a implantação e a adoção do serviço. Ou você mesmo pode realizar esse trabalho usando os assistentes de integração do FastTrack, que estão disponíveis em [FastTrack](https://fasttrack.microsoft.com/) depois de entrar com sua conta do Office 365.

Se estiver fazendo seu próprio planejamento (ou se estiver trabalhando com o FastTrack), você precisará determinar se sua rede e organização estão prontas para o Teams. É especialmente importante que você atenda aos critérios de saída de rede na sua [infraestrutura básica](deploy-foundation-infrastructure.md), com atenção especial para a largura de banda, a taxa de transferência e os atrasos de tráfego para maximizar o desempenho de equipes que utilizem o Teams.

Use estes recursos para preparar os aspectos técnicos da sua organização para uma distribuição do Teams: 

- [Verificar a preparação do seu ambiente para o Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Preparar sua rede para o Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

Para compreender melhor a segurança no Teams, confira os seguintes recursos adicionais:

- [Visão geral da segurança e conformidade no Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Grupos do Office 365 e o Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Acesso de convidado ao Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)

Em seguida, use estes recursos para entender o licenciamento do Teams e para configurar o Teams para sua organização:

- [Licenciamento do Office 365 para o Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Gerenciar o acesso de usuários ao Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Obter clientes para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Ativar o Microsoft Teams em sua organização do Office 365](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Gerenciar os recursos do Microsoft Teams em sua organização do Office 365](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)

#### <a name="result"></a>Resultado

Sua rede, sua segurança e seu planejamento de licenciamento do Office 365 estão prontos e você pode começar a distribuir o Teams para grupos seletos em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Na maioria das organizações de médio e grande porte, você deve realizar um piloto de TI com os participantes da Fase 1 e usuários pioneiros e entusiastas técnicos. Durante um piloto de TI:

- Escolha um cenário de negócios do Teams que os participantes do piloto de TI possam praticar. Confira o [Kit de introdução ao Microsoft Teams](http://microsoft.com/download/56505) para obter ideias.
- Dê aos participantes do piloto um conjunto de exercícios para testar chats, o armazenamento de arquivos, reuniões e outros recursos do Teams.
- Determine sua estratégia de gerenciamento de mudanças e produza materiais para promover a adoção de usuários em toda a organização. Os materiais de gerenciamento de mudanças podem incluir textos de comunicados de email, planos de treinamento internos, cartazes e apresentações. Esses materiais informam sua organização sobre o Teams e seus benefícios com as metas de geração de reconhecimento e uso. Veja [Estratégia de gerenciamento de mudanças para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para obter algumas ideias.
- Peça que os participantes do piloto de TI vejam os materiais de estratégia de gerenciamento de mudanças com base em suas próprias experiências. Eles podem oferecer dicas de práticas recomendadas e conselhos sobre como melhor descrever os benefícios do Teams e como usá-lo para colaboração e trabalho em equipe.

#### <a name="result"></a>Resultado

O piloto de TI o Teams foi concluído e os materiais iniciais sobre o gerenciamento de mudanças foram desenvolvidos, revisados e refinados.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir o piloto de TI, distribua o Teams para um grupo de negócios ou departamento da sua organização. Essa distribuição deve incluir:

- Identificação de cenários de negócios importantes para o Teams dentro do grupo de negócios em questão.
- Atividades de comunicação para informar os usuários sobre as expectativas e os cronogramas para o uso do Teams para trabalho departamental ou equipes de projetos.
- Treinamento direto para os usuários sobre o Teams ou links para recursos para apresentar o Teams e como usá-lo.
- Um mecanismo de feedback, como uma equipe central que contém todos no grupo de negócios, para coletar comentários e problemas dos usuários no grupo de negócios.

Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios utilizando o Teams e os materiais de gerenciamento de mudanças foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, conclua a distribuição do Teams para sua organização e ofereça suporte para que seus usuários reconheçam suas vantagens.

### <a name="step-1-roll-out-teams-to-the-rest-of-your-organization"></a>Etapa 1: distribuir o Teams para o restante da sua organização

Depois de concluir a distribuição para um grupo de negócios direcionado, distribua o Teams para o restante da sua organização. Essa distribuição deve incluir:

- Identificação de cenários de negócios importantes para o Teams dentro de cada grupo de negócios.
- Uso dos materiais de gerenciamento de mudanças refinados para atividades de comunicação para informar a organização sobre as expectativas e os cronogramas para o uso do Teams para trabalho departamental ou equipes de projetos.
- Realização de treinamento para os usuários sobre o Teams ou links para recursos para introduzir o Teams e como usá-lo. Confira os recursos de treinamento em [Treinamento do Microsoft Teams para o usuário final](https://docs.microsoft.com/microsoftteams/enduser-training).
- Um mecanismo de comentários, como uma equipe central que contém todas as pessoas, para coletar comentários e tomar medidas sobre problemas de usuários da organização. Se sua organização tiver menos de 2500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado

Sua organização está em funcionamento e sua estratégia de gerenciamento de mudanças foi implementada para informar, treinar e capacitar os usuários para que eles comecem a usar o Teams.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Após distribuir o Teams para toda a sua organização, você deverá continuar a implementar sua estratégia de gerenciamento de mudanças para:

- Direcionar sua liderança para promover o Teams como a ferramenta de colaboração e trabalho em equipe para a sua organização.
- Incentivar as pessoas a usar o Teams para a comunicação e colaboração entre grupos de negócios, departamentos e equipes de trabalho e projetos.

Veja algumas sugestões de atividades:

- Veja [Orientação sobre a adoção do Office 365](https://aka.ms/successfactors) para saber mais sobre as práticas recomendadas gerais para a adoção do serviço de nuvem. 
- Veja [relatórios de atividades do Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) para entender o uso do serviço do Office 365 em sua organização. Se você não for um administrador global do Office 365 para sua organização, peça alguém que seja para conceder à sua conta de usuário permissões para ler relatórios, de forma que você possa acessar os relatórios de atividades.
- Monitore seu local de comentários (um canal público de uma equipe central ou do Yammer) para saber sobre os problemas e obter feedback das pessoas sobre suas experiências com o Teams. Responda a perguntas e problemas assim que possível para evitar que as pessoas se frustrem e abandonem o Teams.
- Identifique e incentive os defensores da ferramenta em cada grupo de negócios e destaque suas realizações e práticas recomendadas ao usar o Teams. Comunique o sucesso dessas pessoas para a organização para demonstrar o sucesso e a adoção do projeto. O apoio de líderes técnicos em um grupo de negócios pode ser uma influência poderosa para líderes e colegas.

#### <a name="result"></a>Resultado

Sua organização adotou o Teams como sua ferramenta de colaboração e trabalho em equipe.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para conhecer a Microsoft e aprender como a empresa implantou e está usando o Microsoft Teams para colaboração, confira:

- [A implantação do Microsoft Teams simplifica a colaboração e melhora o trabalho em equipe](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [O Microsoft Teams amplia a colaboração no ambiente de trabalho moderno da Microsoft](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

## <a name="next-steps"></a>Próximas etapas

- [Gerenciar os recursos do Microsoft Teams em sua organização do Office 365](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Treinamento de administrador para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/itadmin-readiness)
