---
title: Interações de serviços de grupos
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interações de serviços de grupos
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613221"
---
# <a name="groups-services-interactions"></a>Interações de serviços de grupos

O Microsoft 365 grupos fornece uma malha comum para vários serviços e cargas de trabalho dentro da plataforma do Microsoft 365 para fornecer uma experiência de conexão para usuários finais. Em seu núcleo, existe um grupo 365 da Microsoft para fornecer:

- Uma maneira de gerenciar a associação (Azure AD)
- Um local para mensagens e conversas a serem realizadas (caixa de correio do Exchange, Microsoft Teams, Yammer)
- Um local para os arquivos a serem armazenados (SharePoint)
- Um calendário para agendamento (Exchange)
- Um bloco de anotações para capturar anotações (OneNote)

No ponto de criação de grupo, vários outros recursos também são provisionados, mas não ficam visíveis até serem acessados pela primeira vez do serviço:

- Uma placa para gerenciar tarefas de grupo (Planner)
- Um espaço de trabalho para relatórios (Power BI)
- Uma área para vídeos compartilhados (Microsoft Stream)
- Uma área para formulários compartilhados (formulários)

No Microsoft 365, outros serviços podem interagir com os grupos do Microsoft 365 para fornecer funcionalidade adicional e recursos para membros do grupo.
Estes são alguns exemplos:

- Aplicativos de energia para aplicativos
- Automatização de energia para fluxos de trabalho
- Projeto na Web e mapa para o gerenciamento de projetos baseado em cascata
- Teams para conversas baseadas em canal
- Yammer para comunidades de interesse

## <a name="user-interactions-with-groups"></a>Interações do usuário com grupos

Os grupos do Microsoft 365 podem ser criados e gerenciados de várias interfaces, tanto por administradores quanto por usuários finais. 

### <a name="administrative-experiences"></a>Experiências administrativas

Os administradores podem criar e gerenciar os grupos do Microsoft 365 de vários centros de administração de carga de trabalho, interfaces de linha de comando que oferecem suporte a scripts, bem como aplicativos criados por personalização que interagem com a API do Graph. A única exceção é os grupos do Yammer, que devem ser criados de dentro da interface da Web do Yammer.

**Configurações relacionadas**

Entre as várias interfaces administrativas que podem gerenciar configurações de grupo existem várias sobreposições das quais você deve estar ciente.

**Centro de administração do Microsoft 365**

No centro de administração do Microsoft 365, o acesso de convidados aos grupos é habilitado por padrão, como é a capacidade de permitir que os proprietários adicionem convidados. Não há outros controles no nível da organização disponíveis para grupos desse centro de administração.

**Centro de Administração do Microsoft Azure AD**

O centro de administração do Azure AD oferece controles que envolvem se os usuários podem criar grupos ou atribuir proprietários nos portais do Azure, bem como configurações de política de expiração e de nomenclatura.

O centro de administração também fornece várias medidas de controle de convite de convidados que vão além da do centro de administração do Microsoft 365, como a capacidade de limitar se os não proprietários também podem convidar convidados

**SharePoint**

Os sites do SharePoint são criados com grupos de segurança de proprietário, membro e visitante, com as duas primeiras correspondências em suas contrapartes de grupo do Microsoft 365. Embora a associação aos sites do SharePoint Online seja geralmente gerenciada pelo grupo associado da Microsoft 365, ela não é uma relação bidirecional. As alterações de associação no nível de grupo do Microsoft 365 são refletidas no SharePoint, no entanto, se a associação for alterada no grupo do SharePoint, isso não será refletido no grupo Microsoft 365.

### <a name="user-experiences"></a>Experiências do usuário

Os usuários finais podem criar grupos de vários serviços no Microsoft 365 e, em outros, eles só podem compartilhar com um grupo.

Os seguintes serviços permitem a criação de grupos por usuários finais:
                         
Projeto do Office Planner para o Web SharePoint Stream Microsoft Teams Yammer

**Restrição de criação de grupo**

Uma abordagem comum para controlar a proliferação de equipes é limitar quais usuários podem criá-los. Isso só pode ser feito limitando a criação de grupos. Isso afeta a capacidade de criar grupos de outros serviços onde eles podem ser necessários para o usuário final. Os grupos do Microsoft 365 não oferecem suporte à capacidade de restringir a criação de grupos de alguns aplicativos ou serviços, permitindo que eles sejam de outras pessoas.

A experiência da restrição de criação de grupo varia entre aplicativos e serviços:


|Aplicativo ou serviço|Experiência|
|:-------------|:---------|
|Outlook|A opção **novo grupo** é removida do menu novo na página pessoas|
|Planner|**Novo plano** explica que a criação do grupo foi desativada e oferece para adicionar o plano a um grupo existente|
|Projeto para a Web e o mapa|Menu **Criar grupo** explica que a criação do grupo é restrita e sugere o uso de um grupo existente.|
|SharePoint|Ainda é possível criar um site de equipe que não esteja conectado a um grupo.|
|Stream|A opção **grupo** não aparece no **Menu criar**.|
|Teams|O usuário não pode criar uma equipe com um novo grupo, mas ainda pode criar uma equipe que utiliza um grupo existente.<br><br>**Criar um botão de equipe** é substituído por **criar equipe de um grupo**.|
|Yammer|**Criar uma** opção de grupo é removida da navegação de grupos principais/comunidades.|

## <a name="services-interactions-with-groups"></a>Interações de serviços com grupos

Confira os grupos no cartaz do Microsoft 365 para obter informações sobre diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.

[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

A tabela a seguir fornece uma visão geral das interações de grupos do Microsoft 365 com vários serviços:

|Produto|Recursos|O serviço<br>existe sem um grupo?|O serviço pode<br>criar um grupo?|Exclui o<br>a instância exclui o grupo?|
|:---|:---|:---|:---|:---|
|Azure AD|Associação, controles de grupo, convidados|Sim|Sim|Sim|
|Exchange|Calendário, caixa de correio|Sim|Sim|Sim|
|Forms|Formulário|Sim|Não|Não|
|OneNote|Bloco de anotações|Sim|Não|Não|
|Planner|Quadro de tarefas|Não|Sim|Sim|
|Aplicativo de aplicativos de energia|App|Sim|Não|Não|
|Power Automate|Fluxo de trabalho|Sim|Não|Não|
|Power BI (clássico)|Workspace|Não|Sim|Sim|
|Power BI (novo)|Workspace|Sim|Não|Sim|
|Project para a Web|Plano de projeto|Sim|Sim|Não|
|Roteiro|Roteiro|Sim|Sim|Não|
|SharePoint|Site|Sim|Sim|Sim|
|Stream|Canal, vídeo|Sim|Sim|Sim|
|Teams|Equipe|Não|Sim|Sim|
|Yammer|Group|Sim|Sim|Sim|

Embora a tabela acima forneça uma visão geral de alto nível das interações de grupo com os serviços do Microsoft 365, há várias nuances e complexidades que você deve entender. As seções a seguir levam uma análise mais detalhada das cargas de trabalho específicas e suas interações com grupos.

## <a name="azure-ad"></a>Azure AD

O Azure AD fornece os recursos de gerenciamento de identidade subjacentes no Microsoft 365.

**Principais recursos fornecidos a grupos**

- Associação a um grupo
- Política de nomenclatura
- Política de expiração
- Convidados
- Restrição de criação de grupo

**O Azure AD pode criar um grupo?**

Sim, os grupos do Microsoft 365 podem ser criados a partir do Azure AD através do portal da Web de administração, através do PowerShell ou da API do Graph.

**O Azure AD existe sem um grupo?**

Sim, o Azure AD executa um grande número de serviços que não têm relação com grupos do Microsoft 365. Cada grupo do Microsoft 365 é representado como um objeto no Azure AD.

**É possível haver várias instâncias do Azure AD por grupo?**

Não, há apenas uma instância do Azure AD.

**O Azure Active Directory pode ser associado a vários grupos?**

Sim, porque o Azure AD é a plataforma subjacente que fornece o serviço de associação de grupo.

**A associação do Azure AD pode ser alterada com um grupo?**

Não, o Azure AD é a plataforma subjacente em que os grupos existem.

**Excluir a instância excluir o grupo?**

A exclusão do grupo no Azure AD excluirá os serviços associados ao grupo e o conteúdo relevantes.

## <a name="teams"></a>Teams

O Microsoft Teams é um espaço de trabalho centrado no chat destinado a aprimorar a colaboração, fornecendo uma interface singular para interagir com uma variedade de serviços da Microsoft e de terceiros.

Por padrão, quando uma equipe é criada, a caixa de correio e o calendário associados ao grupo do Microsoft 365 estão ocultos da lista de endereços global no Exchange, bem como do Outlook. Isso pode ser substituído manualmente por um administrador se o usuário quiser usar o Outlook e o Teams no mesmo grupo do Microsoft 365.

**Principais recursos fornecidos a grupos**

- Conversas
- & guias de canais
- Reuniões

**O Microsoft Teams pode criar um grupo?**

Sim, a criação de uma nova equipe criará um novo grupo do Microsoft 365. Também é possível criar uma equipe para um grupo existente que atualmente não tenha um.

**As equipes existem sem um grupo?**

Não, não é possível que uma equipe exista sem um grupo.

**É possível haver várias equipes por grupo?**

Não, a relação entre uma equipe e um grupo é de 1:1.

**Uma equipe pode ser associada a vários grupos?**

Não, a própria equipe só pode ser associada a um único grupo.

**A associação de uma equipe com um grupo é alterada?**

Não, a equipe só pode estar associada ao grupo ao qual foi originalmente associada.

**Excluir a equipe excluirá o grupo?**

Sim, a exclusão da equipe no Microsoft Teams excluirá o grupo, os serviços associados ao grupo e o conteúdo.

## <a name="exchange"></a>Exchange

O Exchange Online fornece mensagens, calendário, contato e funcionalidade associada. No contexto de um grupo, somente um único recurso é associado – em oposição a uma instância de serviço inteira.

**Principais recursos fornecidos a grupos**

- Caixa de correio e calendário
- Capacidade de enviar todos os membros do grupo por email
- Armazenamento de conversas de canal do teams para fins de descoberta eletrônica, comentários do Planner

**O Exchange pode criar um grupo?**

Sim, é possível criar um grupo a partir do centro de administração do Exchange Online, bem como do Outlook. Você também pode converter listas de distribuição do Exchange para grupos do Microsoft 365.

**O Exchange existe sem um grupo?**

Sim, o Exchange Online fornece vários serviços, incluindo caixas de correio compartilhadas e calendários, sem qualquer associação de grupo.

**É possível haver várias instâncias de caixas de correio do Exchange ou calendários por grupo?**

Não, só pode haver uma única caixa de correio e calendário do Exchange Online para um grupo.

**As caixas de correio e os calendários do Exchange podem ser associados a vários grupos?**

Não, a caixa de correio e o calendário têm uma relação 1:1 com o grupo. É possível compartilhar a caixa de correio com outros usuários ou grupos, mas isso não estabelece nenhuma forma de associação de serviço.

**A associação da caixa de correio do Exchange ou do calendário é alterada?**

Não, a caixa de correio e o calendário não podem ser alterados para um grupo diferente. No entanto, o conteúdo pode ser movido de uma caixa de correio para outra no Outlook ou usando uma ferramenta de terceiros.

**A exclusão da caixa de correio exclui o grupo?**

Sim, a exclusão da caixa de correio no Exchange excluirá o grupo, bem como os serviços e o conteúdo associados ao grupo.

## <a name="forms"></a>Forms

Os formulários fornecem pesquisas e testes baseados na Web.

**Principais recursos fornecidos a grupos**

- Propriedade de formulários

**Os formulários podem criar um grupo?**

Não, os formulários não podem criar um grupo.

**Existem formulários sem um grupo?**

Sim, pesquisas e testes podem ser criados diretamente na conta de um usuário final.

**Podem existir vários formulários por grupo?**

Sim, pode haver vários formulários associados a um grupo.

**Os formulários podem ser associados a vários grupos?**

Não, um formulário só pode ser associado a um único grupo.

**É possível que a associação de um formulário com um grupo seja alterada?**

Não, depois que um formulário é associado a um grupo (criado diretamente no ou a propriedade transferida de um indivíduo), ele não pode ser movido para outro grupo.

**Excluir o formulário excluir o grupo?**

Não, não é possível excluir um grupo da interface formulários, somente formulários individuais.

## <a name="onenote"></a>OneNote

O OneNote é um aplicativo de bloco de anotações digital. O bloco de anotações do OneNote criado com um grupo é um arquivo no site associado do SharePoint em vez de um serviço conectado ao grupo.

**Principais recursos fornecidos a grupos**

- Bloco de anotações compartilhado (armazenado na biblioteca do SharePoint associada ao grupo)

**O OneNote pode criar um grupo?**

Não, o aplicativo OneNote não pode criar um grupo.

**Os blocos de anotações do OneNote existem sem um grupo?**

Sim, os blocos de anotações podem ser criados diretamente no OneDrive ou em outros locais compartilhados.

**É possível haver vários blocos de anotações do OneNote por grupo?**

Sim, um bloco de anotações é criado por padrão e outros podem ser adicionados, no entanto, qualquer link para o OneNote de serviços associados ao grupo sempre vai para o bloco de anotações padrão.

**Um bloco de anotações do OneNote pode ser associado a vários grupos?**

Não, o bloco de anotações é armazenado na biblioteca de sites do SharePoint associada ao grupo e vinculado de várias interfaces. No entanto, ele pode ser compartilhado com outros grupos da mesma forma que pode ser compartilhado com pessoas.

**É possível que a associação do bloco de anotações com um grupo seja alterada?**

Não, o próprio bloco de anotações é associado ao grupo e pode ser acessado diretamente a partir de outros serviços conectados ao grupo, no entanto, o conteúdo pode ser movido de um bloco de anotações para outro no aplicativo do OneNote.

**Excluir o bloco de anotações excluirá o grupo?**

Não, no entanto, se o bloco de anotações do OneNote for excluído, poderão existir links desfeitos em alguns dos serviços associados ao grupo.

## <a name="planner"></a>Planner

O Planner é um serviço de gerenciamento de tarefas de grupos leves.

**Principais recursos fornecidos a grupos**

- Placa para gerenciar tarefas de grupo

**O Planner pode criar um grupo?**

Sim, a criação de um plano criará um novo grupo.

**Há um quadro do Planner sem um grupo?**

Não, um plano deve ser associado a um grupo.

**É possível haver vários planos por grupo?**

Sim, pode haver vários planos por grupo.

**É possível associar um plano a vários grupos?**

Não, um plano depende exclusivamente da Associação de grupo para determinar o acesso.

**A associação de um plano a um grupo é alterada?**

Não, no entanto, copiar um plano cria um novo grupo.

> [!NOTE]
> Um grupo criado por qualquer outro aplicativo não será exibido no Planner automaticamente para um usuário. Para acessar a placa inicialmente, ela precisará abri-la a partir de outra interface baseada em grupo, como o Outlook.

**Excluir o plano excluirá o grupo?**

Sim, a exclusão do plano excluirá o grupo e os serviços associados ao grupo e o conteúdo.

## <a name="power-apps"></a>Aplicativos de energia

Os aplicativos de energia fornecem uma tela para o desenvolvimento de aplicativos sem código.

**Principais recursos fornecidos a grupos**

- Os aplicativos podem ser compartilhados com um grupo a ser executado e modificado

**Os aplicativos de energia podem criar um grupo?**

Não, os aplicativos de energia não podem criar um grupo do Microsoft 365.

**Os aplicativos de energia existem sem um grupo?**

Sim, os aplicativos podem ser criados em aplicativos de energia e residem na conta de criadores até serem compartilhados ou publicados.

**Podem existir vários aplicativos por grupo?**

Sim, pode haver vários aplicativos compartilhados com um grupo.

**Os aplicativos podem ser associados a vários grupos?**

Sim, um aplicativo pode ser compartilhado com vários grupos.

**A associação de um aplicativo com um grupo é alterada?**

Sim, como a associação entre os aplicativos de energia e um grupo do Microsoft 365 é somente compartilhamento – o aplicativo ainda reside com o criador.

> [!IMPORTANT]
> [Os grupos devem estar habilitados para segurança antes que os aplicativos possam ser compartilhados com eles](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**Excluir o aplicativo excluirá o grupo?**

Não, os aplicativos não estão conectados ao grupo que não estão sendo compartilhados com eles.

## <a name="power-automate"></a>Power Automate

A automatização de energia (anteriormente conhecida como Microsoft Flow) fornece fluxos de trabalho e serviços de automação.

**Principais recursos fornecidos a grupos**

- Os fluxos de trabalho podem ser compartilhados com um grupo a ser executado e modificado.

**A automatização pode criar um grupo?**

Não, a automatização de energia não pode criar um grupo do Microsoft 365 no contexto de ser associado a um.

No entanto, é possível criar um fluxo que execute várias operações, como criar um grupo de segurança do Azure AD ou atualizar a associação de um grupo do Microsoft 365.

**Os fluxos existem sem um grupo?**

Sim, os fluxos podem ser criados dentro da automatização de energia e residem dentro da conta de criadores até que seja compartilhado ou publicado.

**É possível haver vários fluxos por grupo?**

Sim, pode haver vários fluxos compartilhados com um grupo.

**Um fluxo pode ser associado a vários grupos?**

Sim, um fluxo pode ser compartilhado com vários grupos.

**É possível uma associação de fluxo com uma alteração de grupo?**

Sim, como a associação entre energia automatizada e um grupo do Microsoft 365 é somente compartilhamento: o fluxo ainda reside com o criador.

**Excluir um fluxo exclui o grupo?**

Não, como os aplicativos de energia, os fluxos não estão conectados ao grupo que não estão sendo compartilhados com eles.

## <a name="power-bi-classic"></a>Power BI (clássico)

O Power BI fornece painéis e relatórios orientados por dados interativos.

**Principais recursos fornecidos a grupos**

- Relatórios de dados

**O Power BI pode criar um grupo?**

Sim, a criação de um espaço de trabalho clássico criará um grupo do Microsoft 365.

**Existe um espaço de trabalho clássico do Power BI sem um grupo?**

Não, [um espaço de trabalho clássico no Power bi deve estar associado a um grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**É possível haver vários espaços de trabalho do Power BI por grupo?**

Não, a relação entre um espaço de trabalho clássico e um grupo é de 1:1.

**Um espaço de trabalho pode ser associado a vários grupos?**

Tecnicamente, enquanto o espaço de trabalho clássico é criado com o grupo, o conteúdo pode ser compartilhado fora do grupo com usuários e grupos de segurança.

**A associação do espaço de trabalho com um grupo é alterada?**

Não, o próprio espaço de trabalho clássico é associado ao grupo, no entanto, o conteúdo pode ser movido de um espaço de trabalho para outro dentro da interface do Power BI ou exportando o conteúdo localmente.

**A exclusão do espaço de trabalho exclui o grupo?**

Sim, a exclusão do espaço de trabalho no Power BI excluirá o conteúdo e os serviços associados ao grupo e ao grupo.

## <a name="power-bi-new"></a>Power BI (novo)

O Power BI fornece painéis e relatórios orientados por dados interativos.

Durante a criação de um novo espaço de trabalho no Power BI não cria um grupo do Microsoft 365, a criação de um grupo por outro meio cria um novo espaço de trabalho (não clássico) no Power BI.

**Principais recursos fornecidos a grupos**

- Relatórios de dados

**O Power BI pode criar um grupo?**

Não, não é possível criar um grupo do Microsoft 365 a partir da nova interface do Power BI.

**O novo espaço de trabalho do Power BI existe sem um grupo?**

Sim, é possível ter relatórios e espaços de trabalho criados no Power BI que não estão associados aos grupos do Microsoft 365.

**É possível haver vários espaços de trabalho por grupo?**

Sim, [vários espaços de trabalho criados pelo Power bi podem ser compartilhados com um único grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Um espaço de trabalho pode ser associado a vários grupos?**

Não, um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo.

**A associação de um espaço de trabalho com um grupo é alterada?**

Sim e não. Um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo por vez, mas pode alterar a associação a qualquer momento. Um espaço de trabalho criado no Power BI por um grupo é permanentemente associado a esse grupo.

**A exclusão do espaço de trabalho exclui o grupo?**

Sim, a exclusão do espaço de trabalho no Power BI excluirá os serviços e o conteúdo associados ao grupo e ao grupo.

## <a name="project-for-the-web"></a>Project para a Web

O Project para a Web oferece a capacidade de criar planos de projeto, gráficos de Gantt e mapas.
Principais recursos fornecidos a grupos.

- Planos de projeto

**O Project para a Web pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Project para a Web.

**Os projetos existem sem um grupo?**

Sim, os projetos podem existir sem serem associados a um grupo do Microsoft 365, mas a atribuição de tarefas requer Associação de grupo.

**É possível haver vários projetos por grupo?**

Sim, é possível conectar vários projetos em um único grupo.

**O projeto pode ser associado a vários grupos?**

Não, um projeto só pode ser associado a um único grupo.

**É possível que a associação de um projeto com um grupo seja alterada?**

Não, depois que a associação com um grupo é estabelecida, ela não pode ser alterada.

**Excluir o projeto excluirá o grupo?**

Não, a exclusão do projeto no Project para a Web não excluirá o grupo.

## <a name="roadmap"></a>Roteiro

O roadmap oferece a capacidade de criar mapas de projeto com o Project para a Web e o Project online.

**Principais recursos fornecidos a grupos**

- Roteiros do projeto

**O roteiro pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente do mapa.

**O roteiro existe sem um grupo?**

Sim, os roteiros podem existir sem serem associados a um grupo do Microsoft 365, no entanto, compartilhar o mapa requer Associação de grupo.

**Podem existir vários roteiros por grupo?**

Sim, é possível conectar vários mapas a um único grupo.

**É possível associar um roteiro a vários grupos?**

Não, um mapa só pode ser associado a um único grupo.

**A associação de um mapa a um grupo é alterada?**

Não, depois que a associação com um grupo é estabelecida, ela não pode ser alterada.

**Excluir o roteiro excluirá o grupo?**

Não, a exclusão do roteiro não excluirá o grupo.

## <a name="sharepoint"></a>SharePoint

O SharePoint é uma plataforma de gerenciamento de conteúdo baseada na Web que oferece entre outras coisas, serviços de armazenamento para vários serviços da Microsoft 365.

**Principais recursos fornecidos a grupos**

- Biblioteca de documentos
- Biblioteca para armazenamento de bloco de anotações do OneNote
- Armazenamento de arquivos wiki do teams

**O SharePoint pode criar um grupo?**

Sim, a criação de um site de equipe no SharePoint criará um grupo do Microsoft 365 por padrão. Também é possível criar um grupo e, opcionalmente, uma equipe para um site existente.

**Existem sites do SharePoint sem um grupo?**

Sim, o SharePoint oferece vários serviços e sites não associados ao grupo, como sites de comunicação e de Hub. 

**Podem existir vários sites por grupo?**

Não, só pode haver um único site por grupo. Os canais privados no Microsoft Teams usam sites adicionais que não estão conectados ao grupo.

**Os sites podem ser associados a vários grupos?**

Tecnicamente, mas enquanto um site é criado com um grupo, o conteúdo pode ser compartilhado com outros grupos.

**A associação de um site a um grupo é alterada?**

Não, o próprio site é associado ao grupo, no entanto, o conteúdo pode ser movido de um site para outro dentro da interface do SharePoint, exportando o conteúdo localmente ou usando uma ferramenta de terceiros.

**Excluir o site exclui o grupo?**

Sim, a exclusão do site no SharePoint excluirá os serviços e o conteúdo associados ao grupo e ao grupo.

## <a name="stream"></a>Stream

O Microsoft Stream é uma plataforma de hospedagem e compartilhamento de vídeo.

**Principais recursos fornecidos a grupos**

- Armazenamento de vídeo
- Gravação de reunião do teams
- Canais de vídeo

**O Stream pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Stream.

**O fluxo existe sem um grupo?**

Sim, os canais de vídeo e vídeos podem existir no Stream sem serem associados a um grupo.

**Podem existir vários vídeos e canais por grupo?**

Sim, pode haver vários vídeos e canais em cada grupo.

**É possível associar um vídeo ou canal a vários grupos?**

Sim, enquanto um vídeo ou canal é criado com um grupo, ele pode ser compartilhado com outros grupos.

**A associação a um grupo pode ser alterada?**

Sim e não; os vídeos no Stream são pertencentes ao carregador de reunião ou ao gravador original e, portanto, podem ser associados a qualquer grupo, mas os canais de vídeo só podem ser associados ao grupo em que foram originalmente criados.

**A exclusão de vídeos ou canais excluirá o grupo?**

Não, a exclusão de vídeos ou canais não exclui o grupo. No entanto, excluir o próprio grupo no Stream excluirá os serviços associados ao grupo e o conteúdo, exceto os vídeos reais.

## <a name="yammer"></a>Yammer

O Yammer é uma plataforma social corporativa projetada para promover o envolvimento da Comunidade dentro e entre organizações.

A criação de uma comunidade (anteriormente conhecida como "grupo") no Yammer cria uma caixa de correio, mas no momento não é usada.

Um grupo do Microsoft 365 associado ao Yammer não pode ser usado com uma equipe no Microsoft Teams.

**Principais recursos fornecidos a grupos**

- Área de conversa

**O Yammer pode criar um grupo do Microsoft 365?**

Sim, a criação de um novo grupo no Yammer criará um novo grupo do Microsoft 365, se as plataformas estiverem conectadas e o usuário tiver a capacidade de criar um grupo.

Um grupo do Yammer com o Microsoft 365 Group associado não pode ser criado em qualquer interface ou serviço que não seja o próprio Yammer.

**Há um grupo do Yammer sem um grupo do Microsoft 365?**

Sim, é possível criar um grupo do Yammer sem um grupo do Microsoft 365.

Se a plataforma Yammer não estiver conectada a grupos do Microsoft 365 ou se os usuários não tiverem a capacidade de criar um grupo do Microsoft 365, os grupos do Yammer serão criados sem uma associação de grupo do Microsoft 365.

**É possível haver vários grupos do Yammer por grupo do Microsoft 365?**

Não, a relação entre um grupo do Yammer e um grupo do Microsoft 365 é 1:1.

**Um grupo do Yammer pode ser associado a vários grupos do Microsoft 365?**

Não, o grupo do Yammer só pode ser associado a um único grupo do Microsoft 365. É possível que as postagens sejam compartilhadas ou movidas para outros grupos do Yammer.

**A associação de um grupo do Yammer pode ser alterada com um grupo do Microsoft 365?**

Não, o grupo do Yammer só pode ser associado ao grupo do Microsoft 365 ao qual ele foi originalmente associado.

**Excluir o grupo do Yammer exclui o grupo do Microsoft 365?**

Sim, a exclusão do grupo no Yammer excluirá o grupo da Microsoft e o conteúdo e serviços associados ao grupo relacionados.

## <a name="related-topics"></a>Tópicos relacionados

[Passo a passo de planejamento de governança de colaboração](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)

