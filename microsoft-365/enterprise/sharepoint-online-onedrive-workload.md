---
title: Implantar o SharePoint e o OneDrive no Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Percorra o processo de planejamento, implantação e geração de valor do SharePoint para toda a sua organização.
ms.openlocfilehash: 6b0483073a836f29b1faa5a30018848ef7b2df34
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268204"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Implantar o SharePoint e o OneDrive no Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

Você usará o SharePoint e o Microsoft Teams para armazenar e compartilhar arquivos, gerenciar o conteúdo e a colaboração, além de serem elementos essenciais para o bom trabalho em equipe do Microsoft 365 Enterprise. 

O SharePoint também tem recursos avançados de segurança, como controle de acesso com permissões e criptografia de dados em trânsito ou repouso. A segurança do SharePoint é um elemento essencial do valor de segurança do Microsoft 365 Enterprise.

Se você está começando a usar o SharePoint, confira [SharePoint](https://products.office.com/sharepoint/collaboration) e [Introdução ao SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).

As fases e etapas a seguir vão orientá-lo pelo processo de concepção da função do SharePoint em sua organização, para a integração da organização por várias distribuições progressivas, incentivando o seu uso e valor aos usuários finais. Antes de começar, verifique se você configurou as fases corretas da [infraestrutura básica](deploy-workloads.md#foundation-infrastructure-prerequisites) para que os sites do SharePoint tenham os recursos de segurança necessários. 

Para implantar o OneDrive no Microsoft 365 Enterprise, confira o [guia do OneDrive para empresas](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fase 1: visualizar
Nesta fase, reúna os parceiros da organização para a implantação do SharePoint e determine como sua organização vai usar o SharePoint para atender às necessidades de negócios.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Etapa 1: reunir os membros da implantação do SharePoint

Para realizar uma implantação bem-sucedida do SharePoint na [infraestrutura básica do Microsoft 365 Enterprise](deploy-foundation-infrastructure.md), você precisa dos comentários e feedback das pessoas certas. As pessoas essenciais incluem os tomadores de decisão, funcionários de TI, como arquitetos e implementadores, e representantes dos seus usuários. 

Esses três grupos garantem que sua implantação inclua considerações que atendam às suas necessidades de negócios, aos aspectos técnicos de migração e segurança de pastas e documentos e que o resultado será algo que os usuários tipicamente usarão.

#### <a name="result"></a>Resultado

Uma lista de pessoas que representam as perspectivas de negócios, técnicos e do usuário final da sua organização.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Etapa 2: determinar e priorizar os cenários de negócios do SharePoint

O SharePoint pode ser usado com finalidades diferentes. Você precisa descobrir quais finalidades atendem às suas necessidades de negócios. O SharePoint deve atender às necessidades de armazenamento e compartilhamento de documentos, gerenciamento de conteúdo e colaboração das equipes, da divisão ou de toda a organização. 

Veja a lista de cenários e recursos do [SharePoint](https://products.office.com/sharepoint/collaboration ).

Os seguintes pilares de negócios podem atender às necessidades da sua organização:

|||
|:-----|:-----|
| Compartilhar e trabalhar em conjunto | Aproveite os sites de equipe, sites de comunicação e sincronização. |
| Informar e envolver | Informações do que está por vir. |
| Transformar | Usa o Flow para criar fluxos de trabalho automatizados entre aplicativos e serviços. |
| Reunir o conhecimento coletivo | Use a Pesquisa para obter os resultados desejados em sua organização. |
| Proteger | Garante que sua organização esteja protegida e tenha a conformidade correta. |
|||

Confira [Administrador do SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-online) para encontrar recursos sobre como configurar o SharePoint para as suas necessidades.

Uma maneira de perceber os benefícios do SharePoint é examinar como as pessoas, equipes, divisões ou toda a organização interagem hoje e, em seguida, localizar um cenário apropriado que ofereça maneira mais fáceis de armazenar e compartilhar os arquivos. O [Microsoft Teams](teams-workload.md) pode ser a melhor opção para alguns cenários.

#### <a name="result"></a>Resultado
Uma lista de cenários do Microsoft Office SharePoint Online que atendem às necessidades da sua organização para armazenamento de documentos, gerenciamento de conteúdo, colaboração e segurança.

## <a name="phase-2-onboard"></a>Fase 2: integrar

Nesta fase, planeje os aspectos técnicos da implantação do SharePoint e comece a distribui-los em grupos de usuários selecionados.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Pré-requisitos: Identidade e configuração de acesso ao dispositivo

Para proteger o acesso a sites do SharePoint, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Etapa 1: concluir seu planejamento técnico

Antes de começar o planejamento técnico, determine se deseja usar o FastTrack. Se a sua organização tiver mais de 50 vagas e participar de um [plano qualificado](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365), você poderá usar os benefícios do FastTrack, disponíveis sem custo adicional para orientá-lo no planejamento, migração, implantação e adoção de serviços. Ou você mesmo pode cumprir essa tarefa usando os Assistentes de Integração do FastTrack, que estão disponíveis no [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) assim que você entrar com sua conta do Microsoft 365.

Se você estiver fazendo seu próprio planejamento ou trabalhando com o FastTrack, precisará determinar se a sua rede e organização estão prontas para o SharePoint. É especialmente importante que você atenda aos [critérios de saída para rede](networking-exit-criteria.md) na infraestrutura da sua fundação, com atenção especial à largura de banda da Internet, taxa de transferência e atrasos de tráfego para maximizar o desempenho do tráfego adicional para documentos baseados no SharePoint.

Use [Migrar para o SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online) para se preparar para a implantação do SharePoint: 

Para entender melhor a segurança no SharePoint, leia:

-     [Como o SharePoint e o OneDrive protegem seus dados na nuvem](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-     [Criptografia de dados no OneDrive e no SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Resultado

Você compreende a segurança e migração de documentos, pastas locais e sites do SharePoint e está pronto para distribuir o SharePoint para os grupos selecionados em sua organização.

### <a name="step-2-run-an-it-pilot"></a>Etapa 2: realizar um piloto de TI

Na maioria das organizações de médio e grande porte, você deve realizar um piloto de TI com os participantes da Fase 1, usuários pioneiros e entusiastas técnicos.  Durante um piloto de TI:

- Escolha um cenário de negócios do SharePoint no qual os participantes piloto de TI podem praticar.
- Dê a seus participantes pilotos um conjunto de exercícios para testar o armazenamento, compartilhamento, colaboração e outros recursos de documentos do SharePoint.
- Determine sua estratégia de gerenciamento de mudanças e produza materiais para conduzir a adoção do usuário do SharePoint para toda a organização. Os materiais de gerenciamento de mudanças podem incluir texto de comunicados de email, planos de treinamento internos, cartazes e apresentações. Esses materiais irão informá-lo sobre o SharePoint e seus benefícios com o objetivo de aumentar a conscientização e incentivar o uso. Veja os [recursos de adoção do SharePoint](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/) para começar.
- Peça aos participantes piloto de TI que examinem os materiais de gerenciamento de mudanças com base em suas experiências. Eles podem fornecer dicas sobre as práticas recomendadas e conselhos sobre como descrever melhor os benefícios do SharePoint e como usá-lo.

#### <a name="result"></a>Resultado

O piloto de TI do SharePoint foi concluído e os materiais iniciais sobre o gerenciamento de mudança foram desenvolvidos.

### <a name="step-3-roll-out-to-a-business-group"></a>Etapa 3: distribuir para um grupo de negócios

Depois de concluir o piloto de TI, distribua o SharePoint para um grupo de negócios ou departamento da sua organização. Essa distribuição deve incluir:

- Identificação de cenários de negócios importantes para o SharePoint dentro do grupo de negócios em questão.
- Atividades de comunicação para informar aos usuários sobre as expectativas e os cronogramas para o uso do SharePoint para departamentos e para equipes de trabalho ou projeto.
- Migração de documentos e pastas locais dos membros do grupo de negócios para o SharePoint.
- Fornecer treinamento de usuários ou links para recursos para apresentar o SharePoint e como usá-lo. Confira o treinamento em vídeo do [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- Um mecanismo de feedback, como uma equipe central do Microsoft Teams que contém todos no grupo de negócios, para coletar comentários e solucionar problemas dos usuários no grupo de negócios.
 
Durante a implementação, você pode refinar seus materiais de gerenciamento de mudanças para se preparar para a distribuição para toda a organização.

#### <a name="result"></a>Resultado

Um grupo de negócios está em funcionamento com o SharePoint e os materiais de gerenciamento de mudanças foram testados e refinados.

## <a name="phase-3-drive-value"></a>Fase 3: gerar valor

Nesta fase, você conclui a distribuição do SharePoint e ajuda seus usuários a obterem seus benefícios.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Etapa 1: distribuir para o restante da sua organização

A implantação para o restante da sua organização deve incluir:

- Identificação de cenários de negócios importantes para o SharePoint Online dentro de grupos de negócios separados.
- Uso dos materiais de gerenciamento de mudanças refinados para atividades de comunicação para informar a organização sobre as expectativas e os cronogramas para a utilização.
- Migração de pastas e documentos para o restante da sua organização no SharePoint.
- Fornecer treinamento de usuários ou links para recursos para apresentar o SharePoint e como usá-lo.
- Um mecanismo de comentários, como uma Equipe central que contém todas as pessoas, para coletar comentários e problemas de usuários da organização. Se sua organização tiver menos de 2.500 funcionários, use um canal público no Teams. Caso contrário, use um grupo público no Yammer.

#### <a name="result"></a>Resultado
Sua organização está em funcionamento e sua estratégia de gerenciamento de mudanças foi implementada para informar, treinar e capacitar os usuários para que comecem a usar o SharePoint.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Etapa 2: medir o uso, gerenciar a satisfação e estimular a adoção

Após a distribuição para toda a sua organização, você deverá continuar a implementar sua estratégia de gerenciamento de mudanças para:

- Direcione a sua liderança para promover o SharePoint como a principal ferramenta para armazenamento e compartilhamento de documentos.
- Incentive as pessoas a usá-lo para armazenamento e compartilhamento de documentos entre grupos de negócios, departamentos e equipes de trabalho e projetos.

Veja algumas sugestões de atividades:

- Confira [Fatores de sucesso para o Microsoft 365](https://aka.ms/successfactors) conhecer as práticas recomendadas gerais de adoção do serviço de nuvem. 
- Confira [Relatórios do Microsoft 365 no centro de administração](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) para compreender o uso do serviço em toda a organização. Se você não for um administrador global da sua organização, pergunte a alguém que é um administrador global para conceder permissões de leitor a relatórios para sua conta de usuário, para que você possa acessar os relatórios de atividades.
- Monitore seu local de comentários (um canal público em uma equipe central do Teams ou do Yammer) para ver problemas e comentários da pessoas sobre suas experiências com o SharePoint. Solucione problemas e questões assim que possível para evitar pessoas frustradas e demonstrar suporte para a distribuição.
- Identifique e incentive defensores da ferramenta em cada grupo de negócios e destaque suas realizações e práticas recomendadas ao usar o SharePoint. Comunique os sucessos dessas pessoas para a organização para demonstrar o sucesso e a adoção do projeto. O apoio de líderes técnicos em um grupo de negócios podem ter uma influência poderosa para líderes e colegas.

#### <a name="result"></a>Resultado

A organização adotou o SharePoint no Microsoft 365 Enterprise para oferecer suporte para a colaboração e o armazenamento de documentação.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para conhecer a Microsoft e saber como a empresa implantou o SharePoint, confira [SharePoint para a nuvem: saiba como a Microsoft realizou a própria migração](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration).

## <a name="next-steps"></a>Próximas etapas

Confira estes recursos sobre a manutenção contínua do SharePoint: 

- [Compreender os níveis de permissão no SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [Personalizar as permissões de site do SharePoint](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Ativar ou desativar o compartilhamento externo do SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Configurar e gerenciar solicitações de acesso](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
