---
title: Implantar o SharePoint Online e o OneDrive for Business no Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/28/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Percorra o processo de planejamento, implantação e geração de valor do SharePoint Online no Microsoft 365 Enterprise para toda a sua organização.
ms.openlocfilehash: 9ceadbb0268d3a2aa82309d01933a8bd05429188
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981762"
---
# <a name="deploy-sharepoint-online-and-onedrive-for-business-for-microsoft-365-enterprise"></a>Implantar o SharePoint Online e o OneDrive for Business no Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

Você usará o SharePoint Online e o Microsoft Teams para armazenar e compartilhar arquivos, gerenciar o conteúdo e a colaboração, além de serem elementos essenciais para o bom trabalho em equipe do Microsoft 365 Enterprise. 

O SharePoint Online também tem recursos avançados de segurança, como controle de acesso e permissões e criptografia de dados em trânsito ou repouso. A segurança do SharePoint Online é um elemento essencial do valor de Segurança Inteligente do Microsoft 365 Enterprise.

Se você está começando a usar o SharePoint Online, confira [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software) e [Introdução ao SharePoint](https://support.office.com/article/Get-started-with-SharePoint-3a26444b-08c5-46ad-b80a-cda82b11b27b#ID0EAABAAA=Basics).

As fases e as etapas a seguir vão orientá-lo pelo processo de concepção da função do SharePoint Online em sua organização, para a integração da organização por várias implantações progressivas, incentivando o uso de seu valor pelos usuários finais. Antes de começar, verifique se você configurou as fases corretas da [infraestrutura básica](deploy-foundation-infrastructure.md) para que os sites do SharePoint Online tenham os recursos de segurança necessários. 

Para implantar o OneDrive for Business para o Microsoft 365 Enterprise, confira a [guia do OneDrive para empresas](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fase 1: visualizar
Nesta fase, reúna as pessoas para a implantação do SharePoint Online for Business e determine como sua organização vai usá-los para atender às necessidades de negócios.

### <a name="step-1-gather-your-sharepoint-online-deployment-members"></a>Etapa 1: reunir os membros da implantação do SharePoint Online

Para realizar uma implantação bem-sucedida do SharePoint Online for Business na [infraestrutura básica do Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), você precisa dos comentários e feedback das pessoas certas. As pessoas essenciais incluem tomadores de decisão, funcionários de TI, como arquitetos e implementadores, e representantes dos seus usuários finais. 

Esses três grupos garantem que sua implantação inclua considerações que atendam às suas necessidades de negócios, aos aspectos técnicos de migração e segurança de pastas e documentos e que o resultado será algo que os usuários tipicamente usarão.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam os aspectos de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-sharepoint-online-business-scenarios"></a>Etapa 2: determinar e priorizar os cenários de negócios do SharePoint Online

O SharePoint Online pode ser usado com finalidades diferentes. Você precisa descobrir quais finalidades atendem às suas necessidades de negócios. O SharePoint Online deve atender às necessidades de armazenamento e compartilhamento de documentos, gerenciamento de conteúdo e colaboração das equipes, da divisão ou de toda a organização. 

Veja a lista de cenários e recursos do [SharePoint Online](https://products.office.com/sharepoint/sharepoint-online-collaboration-software).

Os seguintes pontos centrais de negócios podem atender às necessidades da sua organização:

|||
|:-----|:-----|
| Compartilhar e trabalhar em conjunto | Aproveite os sites de equipe, de colaboração e a sincronização. |
| Informar e envolver | Informações do que está por vir. |
| Transformar | Usa o Fluxo para criar uma loja ou um fluxo de trabalho. |
| Reunir o conhecimento coletivo | Use a Pesquisa para obter os resultados desejados em sua organização. |
| Proteger | Garante que sua organização esteja protegida e tenha a conformidade correta. |
| Desenvolver/Externo | Permite que sua organização desenvolva soluções e aplicativos personalizados usando a Estrutura do SharePoint. |
|||

Confira [Administrador do SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online) para encontrar recursos sobre como configurar o SharePoint Online para suas necessidades.

Uma maneira de perceber os benefícios do SharePoint Online é examinar como as pessoas, equipes, divisões ou toda a organização interagem hoje e, em seguida, localizar um cenário apropriado que ofereça maneiras mais fáceis de armazenar e compartilhar os arquivos de colaboração. O [Microsoft Teams](teams-workload.md) pode ser a melhor opção para alguns cenários.

#### <a name="sharepoint-online-site-for-highly-regulated-data"></a>Site do SharePoint Online para dados altamente controlados

Dados altamente controlados estão sujeito a normas regionais ou são os dados mais importantes para sua organização, como segredos comerciais, informações financeiras ou de recursos humanos e de estratégia da organização. Você pode configurar um site do SharePoint Online para acesso restrito, classificação de dados, prevenção de perda de dados e criptografia desse tipo de dados. Para saber mais, confira [Sites do Microsoft Teams e SharePoint Online para dados altamente controlados](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultado
Uma lista de cenários do SharePoint Online for Business que atendem às necessidades da sua organização para armazenamento e compartilhamento de documentos, gerenciamento de conteúdo e colaboração.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, planeje os aspectos técnicos da implantação do SharePoint Online for Business e comece, em seguida, a distribuir em grupos de usuários selecionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso ao site do SharePoint Online, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint Online](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: concluir seu planejamento técnico

Antes de começar o planejamento técnico, determine se deseja usar o Microsoft FastTrack. Se sua organização tiver mais de 50 usuários e participar de um [plano qualificado](https://technet.microsoft.com/library/dn783224.aspx), você poderá usar os benefícios do FastTrack, disponível sem custo adicional para orientar você pelo planejamento, a implantação e a adoção do serviço. Ou você mesmo pode realizar esse trabalho usando os assistentes de integração do FastTrack, que estão disponíveis em [FastTrack](https://fasttrack.microsoft.com/) depois de entrar com sua conta do Office 365.

Se estiver fazendo seu próprio planejamento ou trabalhando com o FastTrack, você precisará determinar se sua rede e organização estão prontas para o SharePoint Online. É especialmente importante que você atenda aos critérios de saída de rede na sua infraestrutura básica, com atenção especial para a largura de banda, a taxa de transferência e os atrasos de tráfego da Internet para maximizar o desempenho para o tráfego adicional de documentos com base no SharePoint Online.

Use estes recursos para se preparar para os aspectos técnicos da distribuição do SharePoint Online: 

- [Guia de Planejamento do SharePoint Online](https://support.office.com/article/sharepoint-online-planning-guide-abacd1bb-295d-4235-afdd-15f5e4cc2e6c)
- [Migrar para o SharePoint Online](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) 

Para entender melhor sobre a segurança no SharePoint Online, leia:

-   [Como o SharePoint Online e o OneDrive protegem seus dados na nuvem](https://support.office.com/article/How-SharePoint-Online-and-OneDrive-safeguard-your-data-in-the-cloud-5aa038e8-8ff0-4704-9e6a-fd72af0a2035)
-   [Criptografia de dados no OneDrive for Business e no SharePoint Online](https://support.office.com/article/Data-Encryption-in-OneDrive-for-Business-and-SharePoint-Online-6501B5EF-6BF7-43DF-B60D-F65781847D6C)

#### <a name="result"></a>Resultado

Você compreende sobre a segurança e migração de documentos, pastas locais e sites do SharePoint Online e estar pronto para distribuir o SharePoint Online para os grupos selecionados em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Na maioria das organizações de médio e grande porte, você deve realizar um piloto de TI com os participantes da Fase 1 e usuários pioneiros e entusiastas técnicos. Durante um piloto de TI:

- Escolha um cenário de negócios do SharePoint Online no qual os participantes piloto de TI podem praticar.
- Forneça aos participantes piloto um conjunto de exercícios para testar o armazenamento, o compartilhamento, a colaboração de documentos, o agendamento com base em equipe e outros recursos do SharePoint Online.
- Determine sua estratégia de gerenciamento de mudanças e produza materiais para promover a adoção do SharePoint Online por usuários em toda a organização. Os materiais de gerenciamento de mudanças podem incluir textos de comunicados de email, planos de treinamento internos, cartazes e apresentações. Esses materiais informam sua organização sobre o SharePoint Online e seus benefícios com as metas de geração de reconhecimento e uso. Veja o artigo Estratégia de gerenciamento de mudanças para o [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) para obter algumas ideias.
- Peça que os participantes do piloto de TI vejam os materiais de gerenciamento de mudanças com base em suas próprias experiências. Eles podem oferecer dicas de práticas recomendadas e conselhos sobre como melhor descrever os benefícios do SharePoint Online e como usá-lo para comunicação e agendamento.

#### <a name="result"></a>Resultado

O piloto de TI do SharePoint Online foi concluído e os materiais iniciais sobre o gerenciamento de mudanças foram desenvolvidos, revisados e refinados.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir o piloto de TI, distribua o SharePoint Online para um grupo de negócios ou departamento da sua organização. Essa distribuição deve incluir:

- Identificação de cenários de negócios importantes para o SharePoint Online dentro do grupo de negócios em questão.
- Atividades de comunicação para informar aos usuários sobre as expectativas e os cronogramas para o uso do SharePoint Online para departamentos ou equipes de trabalho ou projeto.
- Migração de documentos e pastas locais dos membros do grupo de negócios para o SharePoint Online.
- Fornecer treinamento do usuário ou links de recursos para apresentar o SharePoint Online e como usá-lo. Confira o treinamento em vídeo do [SharePoint Online](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Um mecanismo de feedback, como uma equipe central do Microsoft Teams que contém todos no grupo de negócios, para coletar comentários e solucionar problemas dos usuários no grupo de negócios.
 
Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios está pronto e funcionando com o SharePoint Online e os materiais de gerenciamento de alterações foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, você conclui a distribuição do SharePoint Online e oferece suporte aos usuários para ajudá-los a obter os benefícios.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Etapa 1: distribuir para o restante da sua organização

A implantação para o restante da sua organização deve incluir:

- Identificação de cenários de negócios importantes para o SharePoint Online dentro de grupo de negócios separados.
- Uso dos materiais de gerenciamento de mudanças refinados para atividades de comunicação para informar a organização sobre as expectativas e os cronogramas para a utilização.
- Migração de pastas e documentos para o restante da sua organização no SharePoint Online.
- Fornecer treinamento de usuários ou links para recursos para apresentar o SharePoint Online e como usá-lo.
- Um mecanismo de comentários, como uma Equipe central que contém todas as pessoas, para coletar comentários e problemas de usuários da organização. Se sua organização tiver menos de 2.500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado
Sua organização está em funcionamento e sua estratégia de gerenciamento de mudanças foi implementada para informar, treinar e capacitar os usuários para que eles comecem a usar o SharePoint Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Após a distribuição para toda a sua organização, você deverá continuar a implementar sua estratégia de gerenciamento de mudanças para:

- Sua liderança promove o SharePoint Online como a principal ferramenta de armazenamento e compartilhamento de documentos e de colaboração entre equipes, divisões e por toda a organização.
- Incentivar as pessoas a usá-la para a colaboração e a programação de calendários entre grupos de negócios, departamentos e equipes de trabalho e projetos.

Veja algumas sugestões de atividades:

- Veja [Orientação sobre a adoção do Office 365](https://aka.ms/successfactors) para saber mais sobre as práticas recomendadas gerais para a adoção do serviço de nuvem. 
- Veja [relatórios de atividades do Office 365](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) para entender o uso do serviço do Office 365 em sua organização. Se você não for um administrador global do Office 365 para sua organização, peça a um administrador global para conceder à sua conta de usuário permissões para ler relatórios, de forma que você possa acessar os relatórios de atividades.
- Monitore seu local de comentários (um canal público de uma equipe central ou do Yammer) para saber sobre os problemas e obter feedback das pessoas sobre suas experiências com o SharePoint Online. Responda a perguntas e problemas assim que possível para evitar que as pessoas se frustrem e para demonstrar o suporte para a distribuição.
- Identifique e incentive os defensores da ferramenta em cada grupo de negócios e destaque suas realizações e práticas recomendadas ao usar o SharePoint Online. Comunique o sucesso dessas pessoas para a organização para demonstrar o sucesso e a adoção do projeto. O apoio de líderes técnicos em um grupo de negócios pode ser uma influência poderosa para líderes e colegas.

#### <a name="result"></a>Resultado

A organização adotou o SharePoint Online como um serviço para viabilizar a colaboração e o armazenamento de documentação.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para conhecer a Microsoft e aprender como a empresa implantou o SharePoint Online, confira [SharePoint para a nuvem: saiba como a Microsoft realizou a própria migração](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Próximas etapas

Confira estes recursos sobre a manutenção contínua do SharePoint Online: 

- [Compreender os níveis de permissão no SharePoint](https://support.office.com/article/Understanding-permission-levels-in-SharePoint-87ecbb0e-6550-491a-8826-c075e4859848)
- [Personalizar as permissões de site do SharePoint](https://support.office.com/article/Customize-SharePoint-site-permissions-b1e3cd23-1a78-4264-9284-87fed7282048)
- [Ativar ou desativar o compartilhamento externo do SharePoint Online](https://support.office.com/article/Turn-external-sharing-on-or-off-for-SharePoint-Online-6288296a-b6b7-4ea4-b4ed-c297bf833e30)
- [Configurar e gerenciar solicitações de acesso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)

