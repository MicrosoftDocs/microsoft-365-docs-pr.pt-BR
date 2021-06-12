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
ms.openlocfilehash: 908c6a1482761815995330b71f0d2d2f96677b64
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908264"
---
# <a name="learn-about-retention-for-microsoft-teams"></a>Saiba mais sobre retenção para o Microsoft Teams

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Se você estiver vendo uma mensagem no Teams informando que os seus chats ou mensagens foram excluídos por uma política de retenção, consulte [Mensagens do Teams sobre políticas de retenção](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).
> 
> As informações nesta página são para administradores de TI que gerenciam essas políticas de retenção.

As informações neste artigo complementam [Saiba mais sobre retenção](retention.md) porque contém informações específicas das mensagens do Microsoft Teams.

Para outras cargas de trabalho, confira:

- [Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o Microsoft OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre retenção no Yammer](retention-policies-yammer.md)
- [Saiba mais sobre a retenção para o Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>O que está incluído para retenção e exclusão

As mensagens de chat e as mensagens de canal do Teams podem ser excluídas usando políticas de retenção para o Teams e, além do texto nas mensagens, os seguintes itens podem ser mantidos por razões de conformidade: imagens incorporadas, tabelas, links de hipertexto, links para outras mensagens e arquivos do Teams e [conteúdo do cartão](/microsoftteams/platform/task-modules-and-cards/what-are-cards). As mensagens do chat incluem todos os nomes das pessoas no chat e as mensagens do canal incluem o nome da equipe e o título da mensagem (se fornecido). 

Atualmente, as mensagens do Teams em canais privados não possuem suporte para políticas de retenção. Trechos de código, memorandos de voz gravados a partir do cliente móvel do Teams, miniaturas, imagens de anúncios e reações de outras pessoas na forma de emoticons não são mantidos quando você usa políticas de retenção para o Teams.

Emails e arquivos que você usa com o Teams não são incluídos nas políticas de retenção para Teams. Esses itens possuem suas próprias políticas de retenção.

## <a name="how-retention-works-with-microsoft-teams"></a>Como a retenção funciona com o Microsoft Teams

Use esta seção para entender como os requisitos de conformidade são atendidos pelo armazenamento e processos back-end e devem ser verificados pelas ferramentas de Descoberta Eletrônica em vez das mensagens que estão visíveis atualmente no aplicativo do Teams.

Você pode usar uma política de retenção para manter os dados de chats e mensagens de canal no Teams, e excluir esses chats e mensagens. Nos bastidores, as caixas de correio do Exchange são utilizadas para armazenar os dados copiados dessas mensagens. Os dados dos bate-papos do Teams são armazenados em uma pasta oculta na caixa de correio de cada usuário incluído no bate-papo, e uma pasta oculta semelhante em uma caixa de correio do grupo é usada para mensagens do canal do Teams. Essas pastas ocultas não foram projetadas para serem acessíveis diretamente para usuários ou administradores, em vez disso, armazenam dados que os administradores de conformidade podem pesquisar com ferramentas de Descoberta Eletrônica.

Estas caixas de correio são listadas pelo atributo RecipientTypeDetails:

- **UserMailbox**: estas caixas de correio armazenam dados de mensagens para usuários do Teams baseados em nuvem.
- **MailUser**: essas caixas de correio armazenam dados para [usuários do Teams no local](search-cloud-based-mailboxes-for-on-premises-users.md).
- **GroupMailbox**: Estas caixas de correio armazenam dados de mensagens para os canais do Teams.

Outros tipos de caixa de correio, como RoomMailbox que é usado em salas de conferência do Teams, não têm suporte das políticas de retenção do Teams.

O Teams utiliza um serviço de chat alimentado pelo Azure como seu principal armazenamento para todas as mensagens (chats e mensagens de canal), Se você precisar excluir mensagens do Teams por razões de conformidade, as políticas de retenção para o Teams podem excluir as mensagens após um período específico, com base em quando elas foram criadas. Em seguida, as mensagens são excluídas das caixas de correio do Exchange, onde são armazenadas para operações de conformidade e do armazenamento principal usado pelo serviço de chat subjacente alimentado pelo Azure. Para obter mais informações sobre a arquitetura subjacente, consulte [Segurança e conformidade no Microsoft Teams](/MicrosoftTeams/security-compliance-overview) e, especificamente, a seção [Arquitetura de Proteção de Informações](/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Embora esses dados dos chats e das mensagens de canal do Teams sejam armazenadas em caixas de correio, você deve configurar uma política de retenção para os locais **Mensagens de canal do Teams** e **Chats do Teams**. Os chats do Teams e as mensagens do canal não são incluídas nas políticas de retenção configuradas para caixas de correio de usuário ou grupo do Exchange.

> [!NOTE]
> Se um usuário estiver incluído em uma política de retenção ativa que retenha as mensagens do Teams e você exclui uma caixa de correio de um usuário incluído nesta política, a caixa de correio será convertida em uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md) para reter os dados do Teams. Se você não precisar reter esses dados do Teams para o usuário, exclua o usuário da política de retenção antes de excluir a caixa de correio.

Depois que uma política de retenção for configurada para mensagens de chat e de canal, um trabalho de temporizador do serviço do Exchange avaliará periodicamente os itens na pasta oculta em que essas mensagens do Teams são armazenadas. O trabalho de temporizador leva de 1 a 7 dias para ser executado. Quando esses itens expiraram o período de retenção, eles são movidos para a pasta SubstrateHolds, outra pasta oculta que todo usuário ou caixa de correio de grupo possui para armazenar itens “excluídos temporariamente” antes de serem permanentemente excluídos. 

As mensagens permanecem na pasta SubstrateHolds por pelo menos 1 dia e, se forem qualificadas para exclusão, o trabalho de temporalizador as excluirá permanentemente na próxima vez que for executado.

> [!NOTE]
> Por causa do [primeiro princípio de retenção](retention.md#the-principles-of-retention-or-what-takes-precedence), a eliminação permanente é sempre suspensa se o mesmo item tiver que ser retido por causa de outra política de retenção, ou se estiver sob Descoberta Eletrônica por motivos legais ou de investigação.

Depois que uma política de retenção for configurada para mensagens de chat ou canal, os caminhos que o conteúdo tomará vão depender se a política de retenção for para reter e excluir, somente reter ou somente excluir.

Quando a política de retenção for reter e excluir:

![Diagrama do fluxo de retenção para mensagens do chat e do canal do Teams](../media/teamsretentionlifecycle.png)

Para os dois caminhos no diagrama:

1. **Se uma mensagem de chat ou canal for editada ou excluída** por um usuário durante o período de retenção, a mensagem original é copiada (se tiver sido editada) ou movida (se tiver sido excluída) para a pasta SubstrateHolds. A mensagem é armazenada lá por pelo menos 1 dia. Quando o período de retenção expirar, a mensagem será excluída permanentemente na próxima vez que o trabalho de temporizador for executado (normalmente de 1 a 7 dias).

2. **Se uma mensagem de chat ou canal não for excluída** por um usuário e para as mensagens atuais após a edição, a mensagem será movida para a pasta SubstrateHolds após o período de retenção expirar. Esta ação normalmente leva de 1 a 7 dias partir da data de vencimento. Quando a mensagem estiver na pasta SubstrateHolds, ela é armazenada lá por pelo menos 1 dia, em seguida, a mensagem será excluída permanentemente na próxima vez que o trabalho de temporizador for executado (normalmente de 1 a 7 dias). 

> [!NOTE]
> As mensagens armazenadas nas caixas de correio, incluindo as pastas ocultas, são pesquisáveis por ferramentas de Descoberta Eletrônica. Até que as mensagens sejam excluídas permanentemente (na pasta SubstrateHolds), elas permanecerão pesquisáveis por ferramentas de Descoberta Eletrônica.

Quando as mensagens forem excluídas permanentemente da pasta SubstrateHolds, uma operação excluir será comunicada ao serviço de chat do Azure subjacente, que passará a mesma operação para o aplicativo cliente do Teams. Atrasos na comunicação ou cache podem explicar por que, por um curto período de tempo, os usuários ainda podiam ver essas mensagens no aplicativo do Teams, mas os dados dessas mensagens não são retornados nas pesquisas de Descoberta Eletrônica. As mensagens visíveis no aplicativo do Teams não são um reflexo preciso de se as mensagens são mantidas ou excluídas permanentemente por requisitos de conformidade.

Quando a política de retenção é somente retenção ou somente exclusão, os caminhos de conteúdo serão variações de reter e excluir.

### <a name="content-paths-for-retain-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção reter somente

1. **Se uma mensagem de chat ou canal for editada ou excluída** por um usuário durante o período de retenção: a mensagem original será copiada (se tiver sido editada) ou movida (se tiver sido excluída) para a pasta SubstrateHolds e mantida lá por pelo menos 1 dia. Se a política de retenção for configurada para reter permanentemente, o item permanecerá lá. Se a política de retenção tiver uma data de término para o período de retenção e ele expirar, a mensagem será excluída permanentemente na próxima vez que o trabalho de temporalizador for executado (normalmente de 1 a 7 dias).

2. **Se a mensagem de chat ou canal não for modificada ou excluída** por um usuário e para as mensagens atuais após a edição durante o período de retenção: nada acontece antes e depois do período de retenção; a mensagem permanecerá no local original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção excluir somente

1. **Se uma mensagem de chat ou canal for editada ou excluída** pelo usuário durante o período de retenção: a mensagem original será copiada (se tiver sido editada) ou movida (se tiver sido excluída) para a pasta SubstrateHolds. A mensagem é mantida lá por pelo menos 1 dia e será excluída permanentemente na próxima vez que o trabalho de temporalizador for executado (normalmente de 1 a 7 dias).

2. **Se uma mensagem de chat ou canal não for excluída** por um usuário durante o período de retenção: no final do período de retenção, a mensagem será movida para a pasta SubstrateHolds. Esta ação normalmente leva de 1 a 7 dias partir da data de vencimento. A mensagem é mantida lá por pelo menos 1 dia e depois será excluída permanentemente na próxima vez que o trabalho de temporalizador for executado (normalmente de 1 a 7 dias).

#### <a name="example-flows-and-timings-for-retention-policies"></a>Fluxos e intervalos de exemplo para políticas de retenção

Use os exemplos a seguir para ver como os processos e intervalos explicados nas seções anteriores se aplicam às políticas de retenção que possuem as seguintes configurações:

- [Exemplo 1: manter somente por 7 anos](#example-1-retain-only-for-7-years)
- [Exemplo 2: manter por 30 dias e depois excluir](#example-2-retain-for-30-days-and-then-delete)
- [Exemplo 3: excluir somente após 1 dia](#example-3-delete-only-after-1-day)

Para todos os exemplos que se referem à exclusão permanente, por causa dos [princípios da retenção](retention.md#the-principles-of-retention-or-what-takes-precedence), esta ação é suspensa se a mensagem estiver sujeita a outra política de retenção para manter o item ou estiver sujeita a uma retenção de Descoberta Eletrônica.

##### <a name="example-1-retain-only-for-7-years"></a>Exemplo 1: manter somente por 7 anos

No 1º dia, um usuário cria uma mensagem de chat ou canal.

No 5º dia, o usuário edita aquela mensagem.

No 30º dia, o usuário exclui a mensagem atual.

Resultados de retenção:

- Para a mensagem original:
    - No 5º dia, a mensagem é copiada para a pasta SubstrateHolds, onde ainda pode ser pesquisada com as ferramentas de Descoberta Eletrônica por um período mínimo de 7 anos a partir do 1º dia (o período de retenção).

- Para a mensagem atual (editada):
    - No 30º dia, a mensagem é movida para a pasta SubstrateHolds, onde ainda pode ser pesquisada com as ferramentas de Descoberta Eletrônica por um período mínimo de 7 anos a partir do 1º dia (o período de retenção).

Se o usuário excluiu a mensagem atual após o período de retenção especificado, em vez de ser movida dentro do período de retenção, a mensagem ainda seria movida para a pasta SubstrateHolds. No entanto, agora que o período de retenção expirou, a mensagem seria excluída permanentemente após o período mínimo de 1 dia e depois normalmente de 1 a 7 dias.

##### <a name="example-2-retain-for-30-days-and-then-delete"></a>Exemplo 2: manter por 30 dias e depois excluir

No 1º dia, um usuário cria uma mensagem de chat ou canal.

No 10º dia, o usuário edita aquela mensagem.

O usuário não faz mais edições e não exclui a mensagem.

Resultados de retenção:

- Para a mensagem original:
    - No 10º dia, a mensagem é copiada para a pasta SubstrateHolds, onde ainda pode ser pesquisada com as ferramentas de Descoberta Eletrônica.
    - Após o fim do período de retenção (30 dias a partir do 1º dia), a mensagem é permanentemente excluída, normalmente de 1 a 7 dias, após o período mínimo de 1 dia e não será retornada com pesquisas de Descoberta Eletrônica.

- Para a mensagem atual (editada):
    - Após o fim do período de retenção (30 dias a partir do 1º dia), a mensagem é movida para a pasta SubstrateHolds, normalmente de 1 a 7 dias, onde ainda pode ser pesquisada com as ferramentas de Descoberta Eletrônica.
    - Em seguida, a mensagem é excluída permanentemente, normalmente de 1 a 7 dias após o período mínimo de 1 dia e não será retornada com pesquisas de Descoberta Eletrônica.

##### <a name="example-3-delete-only-after-1-day"></a>Exemplo 3: excluir somente após 1 dia

> [!NOTE]
> Por causa da duração curta de um dia destes processos de configuração e retenção que operam em um período de tempo de 1 a 7 dias, esta seção mostra intervalos de exemplo que estão dentro dos intervalos de tempo típicos.

No 1º dia, um usuário cria uma mensagem de chat ou canal.

Resultado de retenção de exemplo se o usuário não editar ou excluir a mensagem:

- 5º dia (normalmente de 1 a 7 dias após o início do período de retenção no 2º dia):
    - A mensagem é movida para a pasta SubstrateHolds e permanece lá por pelo menos 1 dia, onde ainda pode ser pesquisada com as ferramentas de Descoberta Eletrônica.

- 9º dia (normalmente de 1 a 7 dias após o período mínimo de 1 dia na pasta SubstrateHolds):
    - A mensagem é excluída permanentemente e não será retornada com pesquisas de Descoberta Eletrônica.

Como o exemplo mostra, embora seja possível configurar uma política de retenção para excluir mensagem após somente um dia, o serviço passa por vários processos para garantir uma exclusão compatível. Como resultado, uma ação de exclusão após 1 dia pode levar 16 dias antes que a mensagem seja excluída permanentemente para não ser retornada em pesquisas de Descoberta Eletrônica.

## <a name="skype-for-business-and-teams-interop-chats"></a>Chats de Interoperabilidade entre Skype for Business e Teams

Quando um chat do Skype for Business entra no Teams, ele se torna uma mensagem em um thread de chat do Teams e recebe uma caixa de correio adequada. As políticas de retenção do Teams serão aplicadas a essas mensagens do thread do Teams. 

No entanto, se o histórico de conversas estiver ativado para o Skype for Business e, do lado do cliente do Skype for Business, estiver sendo salvo em uma caixa de correio, esses dados de chat não serão manejados por uma política de retenção do Teams. Para este conteúdo, use uma política de retenção configurada para o Skype for Business.

## <a name="meetings-and-external-users"></a>Reuniões e usuários externos

As mensagens de reunião de canal são armazenadas da mesma forma que as mensagens de canal; portanto, para esses dados, selecione o local de **mensagens de canal do Teams** ao configurar sua política de retenção.

As mensagens de reunião improvisada são armazenadas da mesma forma que as mensagens de chat de grupo; portanto, para esses dados, selecione o local de **chat do Teams** ao configurar sua política de retenção.

Quando usuários externos são incluídos em uma reunião hospedada por sua organização:

- Se um usuário externo ingressar na reunião usando uma conta de convidado no locatário, esse usuário terá uma caixa de correio de sombra que pode estar sujeita à política de retenção da sua organização para o Teams. Todas as mensagens da reunião são armazenadas na caixa de correio dos seus usuários e na caixa de correio de sombra. 

- Se um usuário externo ingressar na reunião usando uma conta do Microsoft 365 de outra organização, suas políticas de retenção não podem excluir as mensagens para esse usuário porque elas são armazenadas na caixa de correio desse usuário em outro locatário. No entanto, para a mesma reunião, suas políticas de retenção podem excluir mensagens para os seus usuários.

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização 

Se um usuário com uma caixa de correio no Exchange Online deixar a organização e a conta Microsoft 365 for excluída, suas mensagens de chat sujeitas a retenção serão armazenadas em uma caixa de correio inativa. As mensagens de bate-papo permanecem sujeitas a qualquer política de retenção que foi colocada no usuário antes da sua caixa de correio ser desativada, e o conteúdo fica disponível para uma pesquisa de descoberta eletrônica. Para obter mais informações, consulte [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md). 

Se o usuário tiver armazenado os arquivos no Teams, consulte a [seção equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) do SharePoint e do OneDrive.

## <a name="limitations"></a>Limitações

Estamos continuamente trabalhando para otimizar a funcionalidade de retenção no Teams. Enquanto isso, esteja ciente da seguinte limitação ao usar políticas de retenção para mensagens e chats de canal do Teams:

- **Problema de exibição incorreto no Outlook**. Se você criar políticas de retenção para os locais do Skype ou Teams, uma dessas políticas será exibida como a política de pasta padrão quando um usuário exibir as propriedades de uma pasta de caixa de correio no cliente da área de trabalho do Outlook. Esse é um problema de exibição incorreta no Outlook e [um problema conhecido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Em vez disso, você deve ver a política de retenção de caixa de correio aplicada à pasta. A política de retenção do Skype ou Teams não é aplicada à caixa de correio do usuário.

## <a name="configuration-guidance"></a>Instruções de configuração

Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

Se você estiver pronto para configurar uma política de retenção do Teams, consulte [Criar e configurar políticas de retenção](create-retention-policies.md).