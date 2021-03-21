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
ms.openlocfilehash: 331c30c86481b1729251c685de2d663fb14f390b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921019"
---
# <a name="groups-services-interactions"></a>Interações de serviços de grupos

Os Grupos do Microsoft 365 oferecem um fabric comum para vários serviços e cargas de trabalho na plataforma do Microsoft 365 para oferecer uma experiência conectada aos usuários finais. No seu núcleo, existe um grupo do Microsoft 365 para fornecer:

- Uma maneira de gerenciar a associação (Azure AD)
- Um local para mensagens e conversas ocorrerem (caixa de correio do Exchange, Microsoft Teams, Yammer)
- Um local para que os arquivos sejam armazenados (SharePoint)
- Um calendário para agendamento (Exchange)
- Um bloco de anotações para captura de anotações (OneNote)

No ponto de criação do grupo, vários outros recursos também são provisionados, no entanto, eles não ficam visíveis até que sejam acessados pela primeira vez a partir do serviço:

- Um quadro para gerenciar tarefas de grupo (Planner)
- Um espaço de trabalho para relatórios (Power BI)
- Uma área para vídeos compartilhados (Microsoft Stream)
- Uma área para formulários compartilhados (Formulários)

No Microsoft 365, outros serviços são capazes de interagir com grupos do Microsoft 365 para oferecer funcionalidades e recursos adicionais aos membros do grupo.
Exemplos disso incluem:

- Power Apps para aplicativos
- Power Automate para fluxos de trabalho
- Project on the web and Roadmap for waterfall-based project management
- Teams para conversas baseadas em canal
- Yammer para comunidades de interesse

## <a name="user-interactions-with-groups"></a>Interações do usuário com grupos

Os Grupos do Microsoft 365 podem ser criados e gerenciados a partir de uma variedade de interfaces, tanto por administradores quanto por usuários finais. 

### <a name="administrative-experiences"></a>Experiências administrativas

Os administradores podem criar e gerenciar grupos do Microsoft 365 a partir de vários centros de administração de carga de trabalho, interfaces de linha de comando que suportam scripts, bem como aplicativos personalizados que interagem com a API do Graph. A única exceção a isso são os grupos do Yammer – que devem ser criados a partir da interface da Web do Yammer.

**Configurações relacionadas**

Entre as várias interfaces administrativas que podem gerenciar as configurações de grupo existem várias sobreposições que você deve estar ciente.

**Centro de administração do Microsoft 365**

No Centro de administração do Microsoft 365, o acesso de convidados a Grupos é habilitado por padrão, assim como a capacidade de permitir que os proprietários adicionem convidados. Não há mais controles no nível da organização disponíveis para grupos deste centro de administração.

**Centro de Administração do Microsoft Azure AD**

O centro de administração do Azure AD oferece controles sobre se os usuários podem criar Grupos ou atribuir proprietários em portais do Azure, bem como definições de política de expiração e nomenização.

O centro de administração também fornece várias medidas de controle de convite para convidados que vão além do centro de administração do Microsoft 365, como a capacidade de limitar se não proprietários também podem convidar convidados

**SharePoint**

Os sites do SharePoint são criados com grupos de segurança proprietário, membro e visitante, com os dois primeiros correspondentes aos seus equivalentes do Grupo do Microsoft 365. Embora a associação para sites do SharePoint Online seja geralmente gerenciada pelo Grupo do Microsoft 365 associado, não é uma relação bidirecional. Quaisquer alterações na associação no nível de grupo do Microsoft 365 são refletidas no SharePoint, no entanto, se a associação for alterada no grupo do SharePoint, isso não será refletido no grupo do Microsoft 365.

### <a name="user-experiences"></a>Experiências do usuário

Os usuários finais podem criar grupos de vários dos serviços no Microsoft 365 e, em outros, eles só podem compartilhar com um grupo.

Os seguintes serviços permitem a criação de grupos por usuários finais:
                         
Outlook Planner Project para o Web SharePoint Stream Microsoft Teams Yammer

**Restrição da criação de grupo**

Uma abordagem comum para controlar a expansão de equipes é limitar quais usuários podem criar. Isso só pode ser feito limitando a criação de grupos. Isso afeta a capacidade de criar grupos de outros serviços onde isso pode ser necessário para o usuário final. Os Grupos do Microsoft 365 não suportam a capacidade de restringir a criação de grupos de alguns aplicativos ou serviços, permitindo-o de outros.

A experiência da restrição de criação de grupo varia entre aplicativos e serviços:


|Aplicativo ou serviço|Experiência|
|:-------------|:---------|
|Outlook|**Nova opção** de grupo é removida do novo menu na página pessoas|
|Planner|**Novo plano** explica que a criação de grupo foi desligada e oferece para adicionar o plano a um grupo existente|
|Project for the web and Roadmap|**O menu** Criar grupo explica que a criação de grupo é restrita e sugere o uso de um grupo existente.|
|SharePoint|Ainda é possível criar um site de equipe que não esteja conectado a um grupo.|
|Stream|**A** opção Group não aparece no **menu Criar**.|
|Teams|O usuário não pode criar uma equipe com um novo grupo, mas ainda pode criar uma equipe que utilize um grupo existente.<br><br>**Criar um botão de** equipe é substituído por **Criar equipe de um grupo**.|
|Yammer|**A opção Criar um** grupo é removida da navegação principal Grupos/Comunidades.|

## <a name="services-interactions-with-groups"></a>Interações de serviços com grupos

Consulte o cartaz Grupos no Microsoft 365 para obter informações sobre diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.

[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

A tabela a seguir fornece uma visão geral das interações dos Grupos do Microsoft 365 com vários serviços:

|Produto|Recursos|O serviço<br>existir sem um grupo?|O serviço pode<br>criar um grupo?|Exclui o<br>exclua o grupo?|
|:---|:---|:---|:---|:---|
|Azure AD|Associação, controles de grupo, Convidados|Sim|Sim|Sim|
|Exchange|Calendário, caixa de correio|Sim|Sim|Sim|
|Forms|Formulário|Sim|Não|Não|
|OneNote|Bloco de anotações|Sim|Não|Não|
|Planner|Quadro de Tarefas|Não|Sim|Sim|
|Aplicativo do Power Apps|Aplicativo|Sim|Não|Não|
|Ligar/Desligar Automação|Fluxo de trabalho|Sim|Não|Não|
|Power BI (clássico)|Workspace|Não|Sim|Sim|
|Power BI (novo)|Workspace|Sim|Não|Sim|
|Project para a Web|Plano de projeto|Sim|Sim|Não|
|Roteiro|Roteiro|Sim|Sim|Não|
|SharePoint|Site|Sim|Sim|Sim|
|Stream|Canal, vídeo|Sim|Sim|Sim|
|Teams|Equipe|Não|Sim|Sim|
|Yammer|Group|Sim|Sim|Sim|

Embora a tabela acima fornece uma visão geral de alto nível das interações de grupo com os serviços do Microsoft 365, há várias nuances e complexidades que você deve entender. As seções a seguir abordam mais detalhadamente as cargas de trabalho específicas e suas interações com grupos.

## <a name="azure-ad"></a>Azure AD

O Azure AD fornece os recursos de gerenciamento de identidade subjacentes no Microsoft 365.

**Principais recursos fornecidos para grupos**

- Associação a um grupo
- Política de nomenrção
- Política de expiração
- Convidados
- Restrição da criação de grupo

**O Azure AD pode criar um Grupo?**

Sim, os Grupos do Microsoft 365 podem ser criados a partir do Azure AD por meio do portal da Web de administração, por meio do PowerShell ou da API graph.

**O Azure AD existe sem um grupo?**

Sim, o Azure AD executa um grande número de serviços que não têm relação com grupos do Microsoft 365. Cada grupo do Microsoft 365 é representado como um objeto no Azure AD.

**Pode haver várias instâncias do Azure AD por Grupo?**

Não, há apenas uma instância do Azure AD.

**O Azure AD pode ser associado a vários Grupos?**

Sim, porque o Azure AD é a plataforma subjacente que fornece o serviço de associação ao grupo.

**A associação do Azure AD com uma mudança de grupo pode ser mudada?**

Não, o Azure AD é a plataforma subjacente onde os grupos existem.

**Excluir a instância exclui o Grupo?**

Excluir o grupo no Azure AD excluirá conteúdo e serviços associados a grupos relevantes.

## <a name="teams"></a>Teams

O Teams é um espaço de trabalho centralizado em chat destinado a aprimorar a colaboração, fornecendo uma interface singular para interagir com uma variedade de serviços da Microsoft e de terceiros.

Por padrão, quando uma equipe é criada, a caixa de correio e o calendário associados ao grupo do Microsoft 365 ficam ocultos da Lista de Endereços Global no Exchange, bem como do Outlook. Isso pode ser substituído manualmente por um administrador se o usuário quiser usar o Outlook e o Teams no mesmo Grupo do Microsoft 365.

**Principais recursos fornecidos para grupos**

- Conversas
- Canais & guias
- Reuniões

**O Teams pode criar um grupo?**

Sim, criar uma nova equipe criará um novo grupo do Microsoft 365. Também é possível criar uma equipe para um grupo existente que não tenha uma.

**As equipes existem sem um grupo?**

Não, não é possível que uma equipe exista sem um Grupo.

**Pode haver várias equipes por grupo?**

Não, a relação entre uma equipe e um grupo é 1:1.

**Uma equipe pode ser associada a vários grupos?**

Não, a própria equipe só pode ser associada a um único grupo.

**A associação de uma equipe com um grupo pode mudar?**

Não, a equipe só pode ser associada ao grupo ao qual foi originalmente associada.

**Excluir a equipe exclui o grupo?**

Sim, a exclusão da equipe no Microsoft Teams excluirá o grupo, os serviços associados ao grupo e o conteúdo.

## <a name="exchange"></a>Exchange

O Exchange Online fornece mensagens, calendário, contatos e funcionalidades associadas. No contexto de um Grupo, apenas um único recurso está associado – em vez de uma instância de serviço inteira.

**Principais recursos fornecidos para grupos**

- Caixa de correio e calendário
- Capacidade de enviar emails a todos os membros do Grupo
- Armazenamento de conversas de canal do Teams para fins de Descoberta Virtual, comentários do Planner

**O Exchange pode criar um grupo?**

Sim, é possível criar um grupo a partir do Centro de administração do Exchange Online, bem como do Outlook. Você também pode converter listas de distribuição do Exchange em grupos do Microsoft 365.

**O Exchange existe sem um Grupo?**

Sim, o Exchange Online fornece vários serviços, incluindo caixas de correio compartilhadas e calendários, sem nenhuma associação de grupo.

**Pode haver várias instâncias de caixas de correio ou calendários do Exchange por grupo?**

Não, só pode haver uma única caixa de correio e calendário do Exchange Online para um grupo.

**Caixas de correio e calendários do Exchange podem ser associados a vários grupos?**

Não, a caixa de correio e o calendário têm uma relação 1:1 com o grupo. É possível compartilhar a caixa de correio com outros usuários ou grupos, no entanto, isso não estabelece nenhuma forma de associação de serviço.

**A caixa de correio do Exchange ou a associação do calendário com uma alteração de grupo?**

Não, a caixa de correio e o calendário não podem ser alterados para um grupo diferente. No entanto, o conteúdo pode ser movido de uma caixa de correio para outra no Outlook ou usando uma ferramenta de terceiros.

**Excluir a caixa de correio exclui o grupo?**

Sim, excluir a caixa de correio no Exchange excluirá o grupo, bem como os serviços e conteúdo associados ao grupo.

## <a name="forms"></a>Forms

Os formulários fornece pesquisas baseadas na Web e testes.

**Principais recursos fornecidos aos grupos**

- Propriedade de formulários

**Os formulários podem criar um grupo?**

Não, o Forms não pode criar um grupo.

**Os formulários existem sem um grupo?**

Sim, pesquisas e testes podem ser criados diretamente na conta de um usuário final.

**Pode haver vários formulários por grupo?**

Sim, pode haver vários formulários associados a um grupo.

**Os formulários podem ser associados a vários grupos?**

Não, um formulário só pode ser associado a um único grupo.

**A associação de um formulário com um grupo pode mudar?**

Não, uma vez que um formulário é associado a um grupo (criado diretamente dentro ou a propriedade transferida de um indivíduo) ele não pode ser movido para outro grupo.

**Excluir o formulário exclui o grupo?**

Não, não é possível excluir um grupo da interface Forms, apenas formulários individuais.

## <a name="onenote"></a>OneNote

O OneNote é um aplicativo de bloco de anotações digital. O bloco de anotações do OneNote criado com um grupo é um arquivo no site do SharePoint associado, em vez de um serviço conectado a um grupo.

**Principais recursos fornecidos aos grupos**

- Bloco de anotações compartilhado (armazenado na biblioteca do SharePoint associada ao grupo)

**O OneNote pode criar um grupo?**

Não, o aplicativo do OneNote não pode criar um grupo.

**Os blocos de anotações do OneNote existem sem um grupo?**

Sim, os blocos de anotações podem ser criados diretamente no OneDrive ou em outros locais compartilhados.

**Pode haver vários blocos de anotações do OneNote por grupo?**

Sim, um bloco de anotações é criado por padrão e outros podem ser adicionados, no entanto, qualquer link para o OneNote de serviços associados ao grupo sempre irá para o bloco de anotações padrão.

**Um bloco de anotações do OneNote pode ser associado a vários grupos?**

Não, o bloco de anotações é armazenado na biblioteca de sites do SharePoint associada ao grupo e vinculado de várias interfaces. No entanto, ele pode ser compartilhado com outros Grupos da mesma maneira que pode ser compartilhado com indivíduos.

**A associação do bloco de anotações com um grupo pode mudar?**

Não, o bloco de anotações em si está associado ao grupo e pode ser acessado diretamente de outros serviços conectados a grupos, no entanto, o conteúdo pode ser movido de um bloco de anotações para outro dentro do aplicativo do OneNote.

**Excluir o bloco de anotações exclui o grupo?**

No entanto, se o bloco de anotações do OneNote for excluído, talvez haja links quebrados em alguns dos serviços associados ao grupo.

## <a name="planner"></a>Planner

O Planner é um serviço leve de gerenciamento de tarefas de grupo.

**Principais recursos fornecidos aos grupos**

- Quadro para gerenciar tarefas de grupo

**O Planner pode criar um grupo?**

Sim, a criação de um plano criará um novo grupo.

**Existe um quadro do Planner sem um grupo?**

Não, um plano deve ser associado a um grupo.

**Pode haver vários planos por grupo?**

Sim, pode haver vários planos por grupo.

**Um plano pode ser associado a vários grupos?**

Não, um plano depende somente da associação ao grupo para determinar o acesso.

**A associação de um plano com um grupo pode mudar?**

Não, no entanto, copiar um plano cria um novo grupo.

> [!NOTE]
> Um Grupo criado por qualquer outro aplicativo não será automaticamente aparecer no Planner para um usuário. Para acessar a placa inicialmente, eles precisarão abri-lo a partir de outra interface baseada em grupo, como o Outlook.

**Excluir o plano exclui o grupo?**

Sim, a exclusão do plano excluirá o conteúdo e os serviços associados ao grupo e ao grupo.

## <a name="power-apps"></a>Power Apps

O Power Apps fornece uma tela para desenvolvimento de aplicativos sem código.

**Principais recursos fornecidos para grupos**

- Os aplicativos podem ser compartilhados com um grupo a ser executado e modificado

**O Power Apps pode criar um grupo?**

Não, o Power Apps não pode criar um grupo do Microsoft 365.

**O Power Apps existe sem um grupo?**

Sim, os aplicativos podem ser criados no Power Apps e residir na conta de criadores até serem compartilhados ou publicados.

**Pode haver vários aplicativos por grupo?**

Sim, pode haver vários aplicativos compartilhados com um grupo.

**Os aplicativos podem ser associados a vários grupos?**

Sim, um aplicativo pode ser compartilhado com vários grupos.

**A associação de um aplicativo com um grupo pode mudar?**

Sim, como a associação entre o Power Apps e um grupo do Microsoft 365 está compartilhando apenas – o aplicativo ainda reside com o criador.

> [!IMPORTANT]
> [Os grupos devem estar habilitados para que os aplicativos possam ser compartilhados com eles.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**Excluir o aplicativo exclui o grupo?**

Não, os aplicativos não estão conectados ao grupo além de serem compartilhados com eles.

## <a name="power-automate"></a>Ligar/Desligar Automação

O Power Automate (anteriormente conhecido como Microsoft Flow) fornece fluxos de trabalho e serviços de automação.

**Principais recursos fornecidos aos grupos**

- Fluxos de trabalho podem ser compartilhados com um grupo a ser executado e modificado.

**O Power Automate pode criar um grupo?**

Não, o Power Automate não pode criar um grupo do Microsoft 365 no contexto de estar associado a um.

No entanto, é possível criar um fluxo que execute várias operações, como criar um grupo de segurança do Azure AD ou atualizar a associação de um grupo do Microsoft 365.

**Existem fluxos sem um grupo?**

Sim, os fluxos podem ser criados no Power Automate e residir na conta de criadores até serem compartilhados ou publicados.

**Pode haver vários fluxos por grupo?**

Sim, pode haver vários fluxos compartilhados com um grupo.

**Um fluxo pode ser associado a vários grupos?**

Sim, um fluxo pode ser compartilhado com vários grupos.

**A associação de um fluxo com um grupo pode mudar?**

Sim, como a associação entre o Power Automate e um grupo do Microsoft 365 está compartilhando apenas – o fluxo ainda reside com o criador.

**Excluir um fluxo exclui o grupo?**

Não, como o Power Apps, os fluxos não estão conectados ao grupo além de serem compartilhados com eles.

## <a name="power-bi-classic"></a>Power BI (clássico)

O Power BI fornece painéis e relatórios interativos orientados por dados.

**Principais recursos fornecidos aos grupos**

- Relatório de dados

**O Power BI pode criar um grupo?**

Sim, criar um espaço de trabalho clássico criará um grupo do Microsoft 365.

**Existe um espaço de trabalho clássico do Power BI sem um grupo?**

Não, [um espaço de trabalho clássico no Power BI deve estar associado a um grupo](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Pode haver vários espaços de trabalho do Power BI por grupo?**

Não, a relação entre um espaço de trabalho clássico e um grupo é 1:1.

**Um espaço de trabalho pode ser associado a vários grupos?**

Tecnicamente não, enquanto o espaço de trabalho clássico é criado com o grupo, o conteúdo pode ser compartilhado fora do Grupo com usuários e grupos de segurança.

**A associação do espaço de trabalho com um grupo pode mudar?**

Não, o espaço de trabalho clássico em si está associado ao Grupo, no entanto, o conteúdo pode ser movido de um espaço de trabalho para outro dentro da interface do Power BI ou exportando conteúdo localmente.

**Excluir o espaço de trabalho exclui o grupo?**

Sim, a exclusão do espaço de trabalho no Power BI excluirá conteúdo e serviços associados a grupos e grupos.

## <a name="power-bi-new"></a>Power BI (novo)

O Power BI fornece painéis e relatórios interativos orientados por dados.

Ao criar um novo espaço de trabalho no Power BI não cria um Grupo do Microsoft 365, criar um grupo por qualquer outro meio cria um novo espaço de trabalho (não clássico) no Power BI.

**Principais recursos fornecidos aos grupos**

- Relatório de dados

**O Power BI pode criar um grupo?**

Não, não é possível criar um grupo do Microsoft 365 a partir da nova interface do Power BI.

**O novo espaço de trabalho do Power BI existe sem um grupo?**

Sim, é possível ter relatórios e espaços de trabalho criados no Power BI que não estão associados aos grupos do Microsoft 365.

**Pode haver vários espaços de trabalho por grupo?**

Sim, [vários espaços de trabalho criados pelo Power BI podem ser compartilhados com um único grupo](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Um espaço de trabalho pode ser associado a vários grupos?**

Não, um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo.

**A associação de um espaço de trabalho com um grupo pode mudar?**

Sim e não. Um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo por vez, mas pode alterar a associação a qualquer momento. Um espaço de trabalho criado no Power BI por um grupo é permanentemente associado a esse grupo.

**Excluir o espaço de trabalho exclui o grupo?**

Sim, excluir o espaço de trabalho no Power BI excluirá o grupo e os serviços e conteúdo associados ao grupo.

## <a name="project-for-the-web"></a>Project para a Web

O Project para a Web oferece a capacidade de criar planos de projeto, gráficos de Gantt e roteiros.
Principais recursos fornecidos aos grupos.

- Planos de projeto

**O Project para a Web pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Project para a Web.

**Os projetos existem sem um grupo?**

Sim, os projetos podem existir sem serem associados a um grupo do Microsoft 365, no entanto, a atribuição de tarefas requer associação de grupo.

**Pode haver vários projetos por grupo?**

Sim, é possível conectar vários projetos em um único grupo.

**O projeto pode ser associado a vários grupos?**

Não, um projeto só pode ser associado a um único grupo.

**A associação de um projeto com um grupo pode mudar?**

Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.

**Excluir o projeto exclui o grupo?**

Não, excluir o projeto no Project para a Web não excluirá o grupo.

## <a name="roadmap"></a>Roteiro

O roteiro oferece a capacidade de criar roteiros de projeto com o Project para a Web e o Project Online.

**Principais recursos fornecidos para grupos**

- Roteiros do projeto

**O Roteiro pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente a partir do roteiro.

**O Roteiro existe sem um grupo?**

Sim, os roteiros podem existir sem serem associados a um grupo do Microsoft 365, no entanto, o compartilhamento do roteiro requer associação de grupo.

**Pode haver vários roteiros por grupo?**

Sim, é possível conectar vários roteiros a um único grupo.

**Um roteiro pode ser associado a vários grupos?**

Não, um roteiro só pode ser associado a um único grupo.

**A associação de um roteiro com uma mudança de grupo pode ser feita?**

Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.

**Excluir o roteiro exclui o grupo?**

Não, excluir o roteiro não excluirá o grupo.

## <a name="sharepoint"></a>SharePoint

O SharePoint é uma plataforma de gerenciamento de conteúdo baseada na Web que fornece, entre outras coisas, serviços de armazenamento para vários serviços do Microsoft 365.

**Principais recursos fornecidos para grupos**

- Biblioteca de documentos
- Biblioteca para armazenamento do bloco de anotações do OneNote
- Armazenamento de arquivos wiki do Teams

**O SharePoint pode criar um grupo?**

Sim, criar um site de equipe no SharePoint criará um grupo do Microsoft 365 por padrão. Também é possível criar um grupo e, opcionalmente, uma equipe para um site existente.

**Os sites do SharePoint existem sem um grupo?**

Sim, o SharePoint oferece vários serviços e sites não associados a grupos, como sites de comunicação e hub. 

**Pode haver vários sites por grupo?**

Não, só pode haver um único site por grupo. Canais privados no Teams usam sites adicionais que não estão conectados ao grupo.

**Os sites podem ser associados a vários grupos?**

Tecnicamente não, mas embora um site seja criado com um grupo, o conteúdo pode ser compartilhado com outros grupos.

**A associação de um site com um grupo pode mudar?**

Não, o site em si está associado ao grupo, no entanto, o conteúdo pode ser movido de um site para outro dentro da interface do SharePoint, exportando conteúdo localmente ou usando uma ferramenta de terceiros.

**A exclusão do site exclui o grupo?**

Sim, excluir o site no SharePoint excluirá conteúdo e serviços associados a grupos e grupos.

## <a name="stream"></a>Stream

O Microsoft Stream é uma plataforma de hospedagem e compartilhamento de vídeo.

**Principais recursos fornecidos para grupos**

- Armazenamento de vídeo
- Gravação de reunião do Teams
- Canais de vídeo

**O Stream pode criar um grupo?**

Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Stream.

**O Stream existe sem um grupo?**

Sim, canais de vídeo e vídeos podem existir no Stream sem serem associados a um grupo.

**Pode haver vários vídeos e canais por Grupo?**

Sim, pode haver vários vídeos e canais em cada grupo.

**Um vídeo ou canal pode ser associado a vários grupos?**

Sim, enquanto um vídeo ou canal é criado com um grupo, ele pode ser compartilhado com outros grupos.

**Sua associação com um grupo pode mudar?**

Sim e não; os vídeos no Stream são de propriedade do uploader original ou do gravador de reunião e, portanto, podem ser associados a qualquer grupo, no entanto, os canais de vídeo só podem ser associados ao grupo em que foram criados originalmente.

**A exclusão de vídeos ou canais exclui o grupo?**

Não, excluir vídeos ou canais não exclui o grupo. No entanto, a exclusão do próprio grupo no Stream excluirá os serviços e conteúdo associados ao grupo, exceto os vídeos reais.

## <a name="yammer"></a>Yammer

O Yammer é uma plataforma social corporativa projetada para promover o envolvimento da comunidade dentro e entre organizações.

Criar uma comunidade (anteriormente conhecido como "grupo") no Yammer cria uma caixa de correio, mas, no momento, isso não é usado.

Um grupo do Microsoft 365 associado ao Yammer não pode ser usado com uma equipe no Microsoft Teams.

**Principais recursos fornecidos para grupos**

- Área de conversa

**O Yammer pode criar um grupo do Microsoft 365?**

Sim, criar um novo grupo no Yammer criará um novo grupo do Microsoft 365, se as plataformas estão conectadas e o usuário tem a capacidade de criar um grupo.

Um grupo do Yammer com o grupo associado do Microsoft 365 não pode ser criado em qualquer interface ou serviço diferente do próprio Yammer.

**Existe um grupo do Yammer sem um grupo do Microsoft 365?**

Sim, é possível criar um grupo do Yammer sem um grupo do Microsoft 365.

Se a plataforma yammer não estiver conectada a grupos do Microsoft 365 ou os usuários não têm a capacidade de criar um grupo do Microsoft 365, os grupos do Yammer serão criados sem uma associação de grupo do Microsoft 365.

**Pode haver vários grupos do Yammer por grupo do Microsoft 365?**

Não, a relação entre um grupo do Yammer e um grupo do Microsoft 365 é 1:1.

**Um grupo do Yammer pode ser associado a vários grupos do Microsoft 365?**

Não, o grupo do Yammer só pode ser associado a um único grupo do Microsoft 365. É possível que as postagens sejam compartilhadas ou movidas para outros grupos do Yammer.

**A associação de um grupo do Yammer com um grupo do Microsoft 365 pode mudar?**

Não, o grupo do Yammer só pode ser associado ao grupo do Microsoft 365 ao qual foi originalmente associado.

**Excluir o grupo do Yammer exclui o grupo do Microsoft 365?**

Sim, a exclusão do grupo no Yammer excluirá conteúdo e serviços e serviços associados a grupos relacionados à Microsoft.

## <a name="related-topics"></a>Tópicos relacionados

[Planejamento de governança de colaboração passo a passo](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Criar seu plano de governança de colaboração](collaboration-governance-first.md)