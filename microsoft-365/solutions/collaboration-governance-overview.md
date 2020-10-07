---
title: Visão geral da governança de colaboração no Microsoft 365
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saiba mais sobre como governar os recursos relacionados no Microsoft 365 Groups, Teams, SharePoint e Yammer.
ms.openlocfilehash: 8784f14530ec94a3151ef58589944947b5de9514
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377576"
---
# <a name="overview-of-collaboration-governance-in-microsoft-365"></a>Visão geral da governança de colaboração no Microsoft 365

O Microsoft 365 tem um conjunto avançado de ferramentas para implementar qualquer recurso de governança que sua organização possa exigir. Este artigo orienta os profissionais de ti a fazer as perguntas certas para determinar seus requisitos de governança e como atendê-los com base em seu perfil organizacional.

## <a name="what-are-microsoft-365-groups"></a>O que são grupos do Microsoft 365?

Sabemos que as organizações atuais estão usando um conjunto de ferramentas diversificado. Há a equipe de desenvolvedores usando o chat de equipe, os executivos que enviam emails e toda a organização que se conecta através da empresa social. Várias ferramentas de colaboração estão sendo usadas porque cada grupo é exclusivo e tem suas próprias necessidades funcionais e estilo de trabalho. Algumas usarão apenas emails, enquanto outros moram principalmente no chat. 

Se os usuários acharem que as ferramentas fornecidas não atendem às suas necessidades, elas provavelmente baixarão seus aplicativos de consumidor favorito que dão suporte aos seus cenários. Embora esse processo permita que os usuários sejam iniciados rapidamente, ele leva a uma experiência de usuário frustrante em toda a organização com vários logins, compartilhamento de dificuldade e sem um local para exibir conteúdo. Esse conceito é conhecido como "Shadow IT" e representa um risco significativo para as organizações. Ele reduz a capacidade de gerenciar de forma uniforme o acesso do usuário, garantir a segurança e as necessidades de conformidade do serviço.

Serviços como o Microsoft 365 Groups, Teams e Yammer capacitam os usuários e reduzem o risco de sombreamento de ti, fornecendo as ferramentas necessárias para colaborar. Os grupos do Microsoft 365 permitem que você escolha um conjunto de pessoas com as quais você deseja colaborar e configure facilmente uma coleção de recursos para que as pessoas compartilhem. A adição de membros ao grupo concede automaticamente as permissões necessárias a todos os ativos fornecidos pelo grupo. As duas equipes e o Yammer usam os grupos do Microsoft 365 para gerenciar sua associação.

![Diagrama mostrando os grupos do Microsoft 365 e os serviços relacionados](../media/microsoft-365-groups-hub-spoke.png)

Os grupos do Microsoft 365 incluem uma variedade de controles de governança, incluindo uma política de expiração, convenções de nomenclatura e uma política de palavras bloqueadas, para ajudá-lo a gerenciar grupos na sua organização. Consulte [Plan Organization and Lifecycle Governance for microsoft 365 Groups e Microsoft Teams](plan-organization-lifecycle-governance.md) para obter detalhes.

## <a name="technical-architecture"></a>Arquitetura técnica

Há três métodos de comunicação principais suportados pelo Microsoft 365:

- Outlook: colaboração por email com um grupo compartilhado caixa de entrada e calendário
- Microsoft Teams: um espaço de trabalho com base em chat persistente onde você pode ter conversas informais, em tempo real, em torno de vários tópicos, organizados por subgrupos específicos
- Yammer: experiência social corporativa para colaboração

> [!NOTE]
> Criar um novo grupo por meio de outros aplicativos de trabalho em equipe-como o SharePoint, o Planner ou o Stream-criará um grupo com uma caixa de entrada do Outlook e a capacidade de se conectar ao Microsoft Teams.

Dependendo de onde um grupo é criado, determinados recursos são provisionados automaticamente, como:
- [Caixa de entrada](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) -para conversas por email entre membros do grupo. Esta caixa de entrada tem um endereço de email e pode ser definida para aceitar mensagens de pessoas de fora do grupo e até mesmo fora da organização, muito parecida com uma lista de distribuição tradicional.
 - [Calendário](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – para eventos de agendamento relacionados ao grupo
- [Site de equipe do SharePoint](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – um repositório central para informações, links e conteúdo relacionados ao seu grupo
- [Bloco de anotações do OneNote](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – para coletar ideias, pesquisa e informações
- [Planejador](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – para atribuir e gerenciar tarefas de projeto entre seus membros do grupo
- [Grupo do Yammer](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) – um local comum para ter conversas e compartilhar informações
- Teams – um espaço de trabalho baseado em chat no Microsoft 365
- Stream-um serviço de streaming de vídeo

> [!NOTE]
> Quando um novo grupo do Office 365 é criado por meio do Yammer ou do Teams, o grupo não fica visível no Outlook ou no catálogo de endereços porque a comunicação principal entre esses usuários ocorre em seus respectivos clientes. Os grupos do Yammer não podem ser conectados ao Teams.

## <a name="collaboration-options"></a>Opções de colaboração

Há vários lugares para colaborar e ter conversas no Microsoft 365. A compreensão de onde iniciar uma conversa pode ajudá-lo a definir uma estratégia de comunicação.

![Diagrama mostrando quando usar o Teams, o Yammer e o Outlook](../media/inner-loop-outer-loop.png)

- Teams: espaço de trabalho baseado em chat (colaboração de alta velocidade) – loop interno
  - Projetado para colaboração com as pessoas com as quais você trabalha todos os dias
  - Coloca informações ao alcance dos usuários em uma única experiência
  - Adicionar guias, conectores e bots
  - Chat ao vivo, conferência de áudio/vídeo, reuniões gravadas

- Yammer: conectar-se ao org (Enterprise social) – loop externo
  - Comunidades de grupos de pessoas de prática, que compartilham um interesse ou conhecimento comum, mas não estão necessariamente trabalhando juntas em uma base diária
  - Conexão de liderança, comunidades de aprendizagem, comunidades baseadas em função

- Caixa de correio e calendário (colaboração baseada em email)
  - Usar para comunicação direcionada com um grupo de pessoas
  - Calendário compartilhado para reuniões com outros membros do grupo
 
Todos os grupos recebem um site de equipe do SharePoint conectado onde os usuários podem compartilhar conteúdo, criar páginas personalizadas e notícias de autor. Você também pode [conectar sites de equipe do SharePoint existentes a novos grupos do Microsoft 365](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview).

## <a name="illustrations"></a>Ilustrações

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams e serviços de produtividade relacionados no Microsoft 365 para arquitetos de TI
A arquitetura lógica dos serviços de produtividade no Microsoft 365, liderada pelo Microsoft Teams.

|**Item**|**Descrição**|
|:-----|:-----|
|[![Imagem em miniatura para o cartaz de arquitetura lógica do Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Atualizado em abril de 2019   |A Microsoft fornece um conjunto de serviços de produtividade que trabalham juntos para fornecer experiências de colaboração com recursos de governança de dados, segurança e conformidade. <br/> <br/>Esta série de ilustrações oferece uma visão da arquitetura lógica dos serviços de produtividade para arquitetos empresariais, liderada pelo Microsoft Teams.|


### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos no Microsoft 365 para arquitetos de TI
O que os arquitetos de TI precisam saber sobre os grupos no Microsoft 365

|**Item**|**Descrição**|
|:-----|:-----|
|[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Atualizado em junho de 2019|Essas ilustrações detalham os diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.|

## <a name="conference-sessions"></a>Sessões de conferência

Assista a estas sessões de conferência para saber mais sobre governança para o Microsoft 365 grupos e equipes.

**Conceitos básicos**

Saiba mais sobre os conceitos básicos e as novas inovações nos grupos do Microsoft 365, incluindo gerenciamento e governança em escala, práticas recomendadas para a condução de uso e adoção e autoatendimento.

- [Abraçar os grupos do Microsoft 365](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Governança**

Saiba como configurar seu ciclo de vida de expiração de grupos, políticas de nomeação, rótulos de classificação, colaboração com convidados externos e gerenciar permissões de criação de grupo.

- [Transformar a colaboração e combater a sombra com grupos do Office 365](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Exemplo de cliente**

Veja um exemplo de bastidores de como o Microsoft 365 Groups, SharePoint, Teams e Yammer trabalham em conjunto para fornecer uma plataforma de colaboração global.

- [Encontrando seu ponto central de colaboração com os grupos do Office 365, SharePoint, Teams e Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
