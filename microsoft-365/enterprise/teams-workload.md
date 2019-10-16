---
title: Implantar o Microsoft Teams para o Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
ms.custom: ''
description: Siga as etapas de aprendizagem e implantação do Microsoft Teams em toda a organização.
ms.openlocfilehash: 2e34c4fcada0f80c597faf89b221321ffa9183ba
ms.sourcegitcommit: 31392b9599f4b4e9981a1278d6beb9f0a2839ecf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2019
ms.locfileid: "37503387"
---
# <a name="deploy-microsoft-teams-for-microsoft-365-enterprise"></a>Implantar o Microsoft Teams para o Microsoft 365 Enterprise

*Essa carga de trabalho está incluída nas versões E3 e E5 do Microsoft 365 Enterprise*

O Microsoft Teams reúne bate-papo, conferências, compartilhamento de documentos e conversas em threads de formas que facilita a criação e o compartilhamento de conteúdo em grupos. O Teams é uma maneira de trabalhar em equipe e colaborar com o Microsoft 365 Enterprise e é um elemento essencial do valor de trabalho em equipe do Microsoft 365.  

Se você não conhece o Teams, confira [Introdução ao Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-overview). 


## <a name="roll-out-teams-to-your-organization"></a>Implantar o Teams na sua organização

Antes de começar:

- Verifique se você configurou as fases corretas da [infraestrutura básica](deploy-foundation-infrastructure.md) para que suas equipes tenham as contas de usuário e os recursos de segurança necessários. As fases de Proteção de Identidade e Informações são as mais importantes para o logon e proteger o email e arquivos com rótulos de retenção e confidencialidade.
- Saiba mais sobre segurança e conformidade no Teams lendo [este artigo](https://docs.microsoft.com/microsoftteams/security-compliance-overview).
- Saiba mais sobre o licenciamento do Office 365 para o Teams lendo [este artigo](https://docs.microsoft.com/microsoftteams/office-365-licensing).

Para implantar o Teams em sua organização, leia [Como implantar o Teams](https://docs.microsoft.com/microsoftteams/how-to-roll-out-teams).

Para o seu primeiro conjunto de recursos do Teams, confira [Bate-papo, equipes, canais e aplicativos no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/deploy-chat-teams-channels-microsoft-teams-landing-page).

Para obter recursos mais avançados do Teams, confira:

- [Reuniões e conferências](https://docs.microsoft.com/microsoftteams/deploy-meetings-microsoft-teams-landing-page)
- [Cloud Voice](https://docs.microsoft.com/microsoftteams/cloud-voice-landing-page) (requer o Microsoft 365 Enterprise E5)

Para monitorar o uso do Teams na sua organização, confira:

- [Análise entre equipes e por equipes no Teams](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/cross-team-per-team-analytics)
- [Análises e relatórios](https://docs.microsoft.com/microsoftteams/teams-analytics-and-reports/teams-reporting-reference)


## <a name="upgrade-to-teams"></a>Atualizar para o Teams

Se ainda não tiver ocorrido, você receberá a atualização em breve do Skype for Business para o Microsoft Teams. Quer você esteja começando a usar o Teams, usando o Teams em conjunto com o Skype for Business ou pronto para atualizar, queremos garantir que você tenha tudo o que precisa para realizar uma migração tranquila para o Teams.

Se você estiver atualizando do Skype for Business Online para o Teams ou de um ambiente local do Skype for Business para o Teams, a estrutura de atualização o orientará pelo processo de acordo com o seu cenário de negócios.
 
Para saber mais, confira [Introdução à atualização para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Como a Microsoft desenvolve o Microsoft 365 Enterprise

Para conhecer a Microsoft e aprender como implantamos e estamos usando o Teams para colaboração, confira:

- [Estratégia de adoção do Microsoft Teams prepara funcionários para uma nova cultura de trabalho](https://www.microsoft.com/pt-BR/itshowcase/microsoft-teams-adoption-strategy-prepares-employees-for-a-new-culture-of-work)
- [Com as salas do Microsoft Teams, temos uma experiência de reunião moderna e globalmente dimensionável](https://www.microsoft.com/pt-BR/itshowcase/with-microsoft-teams-rooms-comes-a-globally-scalable-modern-meeting-experience)

## <a name="next-steps"></a>Próximas etapas

- [Gerenciar os recursos do Microsoft Teams para sua organização](https://docs.microsoft.com/microsoftteams/enable-features-office-365)
- [Treinamento de administrador para o Microsoft Teams](https://docs.microsoft.com/microsoftteams/itadmin-readiness)

<!--

## Phase 1: Envision

In this phase, you gather the people for your Teams deployment and determine how your organization will use Teams to address its business needs.

### Step 1: Gather your Teams deployment members

For a successful deployment of Teams on top of the Microsoft 365 [foundation infrastructure](deploy-foundation-infrastructure.md), you need to get the right people for input and feedback. Key people include business decision makers, IT staff such as architects and implementers, and advocates for your end users. 

These three groups ensure that your Teams deployment includes considerations that address business needs, technical aspects of licensing and security, and that Teams is something that your typical users will use.

#### Result

A list of people that represent the business, technical, and end user perspectives of your organization.

### Step 2: Determine and prioritize your Teams business scenarios
Teams can be used for many different purposes. You need to figure out which purposes map to your business needs on the separate levels of your organization, your business groups, your departments, and individual working and project teams. Take a look at the [Microsoft 365 Productivity Library](https://www.microsoft.com/microsoft-365/success/?rtc=1) for examples to help you define Teams scenarios. 

You should target Teams to address fast-moving and highly collaborative teams that work closely together and require many more facilities than just email with Exchange Online can provide. Examples are live group chats with a recorded history and a common and easy-to-find place to store files and notes. 

One way to see the benefits of Teams is to examine how a team or v-team interacts today, and then find an appropriate Teams scenario that replaces the interaction and provides easier ways to collaborate and provide additional capabilities.

#### Microsoft Teams for highly regulated data

Highly regulated data is subject to regional regulations or is the most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy. You can configure a team for restricted access, data classification, data loss prevention, and encryption for this type of data. For the details, see [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).

#### Result

A list of Teams scenarios that address your organization’s needs for collaboration and teamwork.

## Phase 2: Onboard

In this phase, you plan for the technical aspects of a Teams deployment and start rolling out Teams to selected groups of users.

### Prerequisites: Identity and device access configuration

To protect access to teams, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).

### Step 1: Complete your technical planning

Before you begin technical planning, determine whether you want to use FastTrack. If your organization has over 50 seats and is participating in an [eligible plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365, you can use [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365), *available at no additional cost* to guide you through planning, deployment and service adoption. Or, you can complete this work yourself using our FastTrack Onboarding Wizards, which are available from [FastTrack](https://fasttrack.microsoft.com/) once you sign in with your Microsoft 365 account.

If you are doing your own planning (or in conjunction with FastTrack), you need to determine if your network and organization are ready for Teams. It is especially important that you meet the exit criteria for [networking](networking-infrastructure.md) in your foundation infrastructure for users connected to your organization network. Pay special attention to bandwidth, throughput, and traffic delays to maximize performance for Teams-based meetings.

Use these resources to prepare the technical aspects of your organization for a Teams rollout: 

- [Check your environment's readiness for Teams](https://docs.microsoft.com/MicrosoftTeams/environment-readiness)
- [Prepare your network for Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)
- [Office 365 URLs and IP address ranges](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)

For a better understanding of security in Teams, review the following additional resources:

- [Overview of security and compliance in Teams](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview)
- [Office 365 groups and Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-groups)
- [Guest access in Teams](https://docs.microsoft.com/microsoftteams/guest-access)

Next, use these resources to understand Teams licensing and to perform the setup of Teams for your organization:

- [Office 365 licensing for Teams](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)
- [Manage user access to Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/user-access)
- [Get clients for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/get-clients)
- [Turn on Microsoft Teams in your organization](https://docs.microsoft.com/MicrosoftTeams/office-365-set-up)
- [Manage Microsoft Teams features for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365)

#### Result

Your network, security, and Microsoft 365 licensing planning are done and you are ready to begin rolling out Teams to selected groups in your organization.

### Step 2: Run an IT pilot

In most medium-sized and large organizations, you should run an IT pilot with your stakeholders from Phase 1, early adopters, and technical enthusiasts. During the IT pilot:

- Choose a Teams business scenario in which your IT pilot participants can practice. See the [Microsoft Teams getting started kit](http://microsoft.com/download/56505) for ideas.
- Give your pilot participants a set of exercises to test Teams-based chats, meetings, file storage, meetings, and other capabilities.
- Determine your change management strategy and produce materials to drive organization-wide user adoption. 

  Change management materials can include email announcement text, internal training plans, hallway posters, and presentations. These materials will inform your organization about Teams and its benefits with the goals of raising awareness and driving usage. See [change management strategy for Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy) for some ideas.

- Have your IT pilot participants review the change management strategy materials based on their experiences. They can provide tips on best practices and advice on how to best describe the benefits of Teams and how to use it for collaboration.

#### Result

Your Teams IT pilot is complete and the initial change management materials have been developed, reviewed, and refined.

### Step 3: Roll out to a business group

After completing your IT pilot, roll out Teams to a business group or department in your organization. This rollout should include:

- Identification of key business scenarios for Teams within the business group.
- Announcement activities to inform users of the expectations and timelines for Teams usage for departmental, work, or project teams.
- Delivery of [user training on Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) or links to resources to introduce Teams and how to use it.
- A feedback mechanism, such as a central team containing everyone in the business group, to collect comments and issues from users in the business group.

During the rollout, you can refine your change management materials in preparation for the organization-wide rollout.

#### Result

A business group is up and running with Teams and the change management materials have been tested and refined.

## Phase 3: Drive value

In this phase, you complete the rollout of Teams to your organization and support your users so that they are realizing its benefits.

### Step 1: Roll out Teams to the rest of your organization

After completing your rollout to a targeted business group, roll out Teams to the rest of your organization. This rollout should include:

- Identification of key business scenarios for Teams within your separate business groups.
- Use of your refined change management materials for announcement activities to inform your organization of the expectations and timelines for Teams usage for departmental, work, or project teams.
- Delivery of [user training on Teams](https://docs.microsoft.com/microsoftteams/training-microsoft-teams-landing-page) or links to resources to introduce Teams and how to use it.
- A feedback mechanism, such as a central team containing everyone, to collect comments and act on issues from organization users. If your organization has less than 2500 individuals, use a public team or channel in Teams. Otherwise, use a public group in Yammer.

#### Result

Your organization is up and running and your change management strategy is in place to inform, train, and enable users to begin using Teams.

### Step 2: Measure usage, manage satisfaction, and drive adoption

After rolling out Teams to your entire organization, you must continue to employ your change management strategy to:

- Have your leadership promote Teams as the teamwork and collaboration tool for the organization.
- Encourage individuals to use it for business group, departmental, work, and project team communications and collaboration.

Here are some suggested activities:

- See [Success factors for Office 365](https://aka.ms/successfactors) to learn about general best practices for cloud service adoption. 
- See [Office 365 activity reports](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263) to understand Office 365 service usage across your organization. If you aren’t an Office 365 global admin for your organization, ask someone who is to grant your user account Reports Reader permissions so you can access activity reports.
- Monitor your feedback venue (a public channel in a central team or a public Yammer group) for issues and feedback from individuals about their experiences with Teams. Address questions and issues as quickly as you can to prevent frustration and abandonment of Teams by individuals.
- Identify and nurture your champions in each business group and highlight their accomplishments and best practices using Teams. Reflect their successes out to the organization to show project success and adoption. Endorsement by technical leaders within a business group can exert a powerful influence over leaders and peers.

#### Result

Your organization has adopted Teams as its collaboration and teamwork tool.


--> 
