---
title: Saiba mais sobre retenção para o Teams
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre as políticas de retenção que se aplicam ao Microsoft Teams.
ms.openlocfilehash: b3b0451f2f1b0950f2b2ee723025a796f1814038
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261498"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Saiba mais sobre retenção para o Microsoft Teams

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

As informações neste artigo complementam [Saiba mais sobre retenção](retention.md) porque contém informações específicas das mensagens do Microsoft Teams.

Para outras cargas de trabalho, confira:

- [Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o Microsoft OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre retenção no Yammer](retention-policies-yammer.md)
- [Saiba mais sobre a retenção para o Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>O que está incluído para retenção e exclusão

Os seguintes itens de equipes podem ser retidos e excluídos usando políticas de retenção para equipes: Mensagens de bate-papo e mensagens de canal, incluindo imagens incorporadas, tabelas, links de hipertexto e links para outras mensagens e arquivos de equipes e [conteúdo de cartão](https://docs.microsoft.com/microsoftteams/platform/task-modules-and-cards/what-are-cards). As mensagens do chat incluem todos os nomes das pessoas no chat e as mensagens do canal incluem o nome da equipe e o título da mensagem (se fornecido). 

> [!NOTE]
> Incluir o conteúdo do cartão é uma adição recente e está sendo implementada atualmente para os locatários. Para obter mais informações, confira [Centro de conformidade do Microsoft 365 para conteúdo do Cartão Adaptável por meio de aplicativos no Teams agora disponíveis](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-365-compliance-capabilities-for-adaptive-card-content/ba-p/2095869).

No momento, as mensagens em canais privados do Teams não têm suporte das políticas de retenção. Trechos de código, memorandos de voz gravados do cliente móvel do Teams e reações de outras pessoas na forma de emoticons não são incluídos quando você usa políticas de retenção para Teams.

Emails e arquivos que você usa com o Teams não são incluídos nas políticas de retenção para Teams. Esses itens têm suas próprias políticas de retenção.

## <a name="how-retention-works-with-microsoft-teams"></a>Como retenção funciona com o Microsoft Teams

Você pode usar uma política de retenção para reter e excluir dados de bate-papos e mensagens de canal no Teams. Nos bastidores, as caixas de correio do Exchange são usadas para armazenar essas mensagens. Os dados dos bate-papos do Teams são armazenados em uma pasta oculta na caixa de correio de cada usuário incluído no bate-papo, e uma pasta oculta semelhante em uma caixa de correio do grupo é usada para mensagens do canal do Teams.

Estas caixas de correio são listadas pelo atributo RecipientTypeDetails:

- **UserMailbox**: essas caixas de correio armazenam mensagens de usuários do Teams que têm uma caixa de correio do Exchange Online.
- **MailUser**: essas caixas de correio armazenam mensagens de usuários do Teams que têm uma caixa de correio de um servidor do Exchange local e não do Exchange Online.
- **GroupMailbox**: essas caixas de correio armazenam mensagens de canais do Teams.

Outros tipos de caixa de correio, como RoomMailbox que é usado em salas de conferência do Teams, não têm suporte das políticas de retenção do Teams.

No entanto, é importante compreender que o Teams usa um serviço de chat fornecido pelo Azure que também armazena esses dados e, por padrão, esse serviço armazena os dados para sempre. Por esse motivo, se você precisar excluir mensagens do Teams por motivos de conformidade, recomendamos que você use políticas de retenção para Teams que podem excluir permanentemente esses dados das caixas de correio do Exchange e do serviço de bate-papo baseado no Azure. Para obter mais informações sobre a arquitetura subjacente, confira [Segurança e conformidade no Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) e, especificamente, a seção [Arquitetura de Proteção de Informações](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Embora os chats do Teams e as mensagens do canal sejam armazenados em caixas de correio, esses dados do Teams são incluídos apenas por uma política de retenção configurada para as **mensagens do canal do Teams** e os **locais dos chats do Teams**. Os chats do Teams e as mensagens do canal não são afetados pelas políticas de retenção configuradas para caixas de correio de usuário ou grupo do Exchange.

> [!NOTE]
> Se um usuário estiver incluído em uma política de retenção ativa que retém dados do Teams e você excluir uma caixa de correio de um usuário incluído nessa política, para reter os dados do Teams, a caixa de correio será convertida em uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md). Se você não precisar reter esses dados do Teams para o usuário, exclua o usuário da política de retenção antes de excluir a caixa de correio.

Depois que uma política de retenção for configurada para mensagens de chat e de canal, um trabalho de temporizador do serviço do Exchange avaliará periodicamente os itens na pasta oculta em que essas mensagens do Teams são armazenadas. O trabalho de temporizador leva até sete dias para ser executado. Quando esses itens expiraram o período de retenção, eles são movidos para a pasta SubstrateHolds, outra pasta oculta que todo usuário ou caixa de correio de grupo possui para armazenar itens “excluídos temporariamente” antes de serem permanentemente excluídos.

Depois que uma política de retenção for configurada para mensagens de chat ou canal, os caminhos que o conteúdo tomará vão depender se a política de retenção for para reter e excluir, somente reter ou somente excluir.

Quando a política de retenção for reter e excluir:

![Diagrama do fluxo de retenção para mensagens do chat e do canal do Teams](../media/teamsretentionlifecycle.png)

Para os dois caminhos no diagrama:

1. **Se uma mensagem de chat ou canal for editada ou excluída** pelo usuário durante o período de retenção, a mensagem original será copiada (se tiver sido editada) ou movida (se tiver sido excluída) para a pasta SubstrateHolds dentro de 21 dias. A mensagem é armazenada lá até o período de retenção expirar e a mensagem será excluída permanentemente dentro de 24 horas.

2. **Se uma mensagem de chat ou canal não for excluída** e para as mensagens atuais após a edição, a mensagem será movida para a pasta SubstrateHolds após o período de retenção expirar. Essa ação leva sete dias após a data de vencimento. Quando a mensagem estiver na pasta SubstrateHolds, ela será excluída permanentemente dentro de 24 horas. 

> [!NOTE]
> As mensagens na pasta SubstrateHolds são pesquisáveis por ferramentas de descoberta eletrônica. Até que as mensagens sejam excluídas permanentemente (na pasta SubstrateHolds), elas permanecerão pesquisáveis por ferramentas de Descoberta Eletrônica.

Quando a política de retenção é somente retenção ou somente exclusão, os caminhos de conteúdo serão variações de reter e excluir.

### <a name="content-paths-for-retain-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção reter somente

1. **Se uma mensagem de chat ou canal for editada ou excluída**: uma cópia da mensagem original é criada na pasta SubstrateHolds dentro de 21 dias e mantida lá até que o período de retenção expire. Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds dentro de 24 horas.

2. **Se o item não for modificado ou excluído** e para as mensagens atuais após a edição durante o período de retenção: nada acontece antes e depois do período de retenção; a mensagem permanecerá no local original. 

### <a name="content-paths-for-delete-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção somente excluir

1. **Se a mensagem não for excluída** durante o período de retenção: no final do período de retenção, a mensagem será movida para a pasta SubstrateHolds. Essa ação leva sete dias após a data de vencimento. Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds dentro de 24 horas.

2. **Se o item for excluído pelo usuário** durante o período, o item será movido para a pasta SubstrateHolds dentro de 21 dias, onde será excluído permanentemente dentro de 24 horas.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chats de Interoperabilidade entre Skype for Business e Teams

Quando um chat do Skype for Business entra no Teams, ele se torna uma mensagem em um thread de chat do Teams e recebe uma caixa de correio adequada. As políticas de retenção do Teams serão aplicadas a essas mensagens do thread do Teams. 

No entanto, se o histórico de chats estiver ativado para o Skype for Business e, do lado do cliente do Skype for Business, estiverem sendo salvos em uma caixa de correio, esses dados de bate-papo não serão manejados por uma política de retenção do Teams. Para esse conteúdo, use uma política de retenção configurada para o Skype for Business.

## <a name="meetings-and-external-users"></a>Reuniões e usuários externos

As mensagens de reunião de canal são armazenadas da mesma forma que as mensagens de canal; portanto, para esses dados, selecione o local de **mensagens de canal do Teams** ao configurar sua política de retenção.

As mensagens de reunião improvisada são armazenadas da mesma forma que as mensagens de chat de grupo; portanto, para esses dados, selecione o local de **chat do Teams** ao configurar sua política de retenção.

Quando usuários externos são incluídos em uma reunião hospedada por sua organização:

- Se um usuário externo ingressar na reunião usando uma conta de convidado no locatário, esse usuário terá uma caixa de correio de sombra que pode estar sujeita à política de retenção da sua organização para o Teams. Todas as mensagens da reunião são armazenadas na caixa de correio dos seus usuários e na caixa de correio de sombra. 

- Se um usuário externo ingressar na reunião usando uma conta do Microsoft 365 de outra organização, suas políticas de retenção não podem excluir as mensagens para esse usuário porque elas são armazenadas na caixa de correio desse usuário em outro locatário. No entanto, as políticas de retenção podem excluir mensagens para os seus usuários.

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização 

Se um usuário com uma caixa de correio no Exchange Online deixar a organização e a conta Microsoft 365 for excluída, suas mensagens de chat sujeitas a retenção serão armazenadas em uma caixa de correio inativa. As mensagens de bate-papo permanecem sujeitas a qualquer política de retenção que foi colocada no usuário antes da sua caixa de correio ser desativada, e o conteúdo fica disponível para uma pesquisa de descoberta eletrônica. Para obter mais informações, consulte [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md). 

Se o usuário tiver armazenado os arquivos no Teams, consulte a [seção equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) do SharePoint e do OneDrive.

## <a name="limitations"></a>Limitações

Estamos trabalhando continuamente para otimizar a funcionalidade de retenção no Teams. Enquanto isso, aqui estão algumas limitações que você deve conhecer ao usar a retenção para os canais de conversa e mensagens do Teams:

- **Problema de exibição incorreto no Outlook**. Se você criar políticas de retenção para os locais do Skype ou Teams, uma dessas políticas será exibida como a política de pasta padrão quando um usuário exibir as propriedades de uma pasta de caixa de correio no cliente da área de trabalho do Outlook. Esse é um problema de exibição incorreta no Outlook e [um problema conhecido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). O que deve ser exibido como a política de pasta padrão é a política de retenção da caixa de correio aplicada à pasta. A política de retenção do Skype ou Teams não é aplicada à caixa de correio do usuário.

- **Problemas de configuração**: 
    - Ao selecionar **Escolher equipes** para a linha de localização **mensagens de canal do Teams**, você pode ver outros grupos do Microsoft 365 que não são equipes. Não selecione esses grupos.
    
    - Ao **Escolher usuários** para o local **Chats do Teams**, você poderá ver convidados e usuários sem caixa de correio. As políticas de retenção não são projetadas para esses usuários, portanto, não os selecione.

## <a name="configuration-guidance"></a>Instruções de configuração

Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

Se você estiver pronto para configurar uma política de retenção do Teams, consulte [Criar e configurar políticas de retenção](create-retention-policies.md).
