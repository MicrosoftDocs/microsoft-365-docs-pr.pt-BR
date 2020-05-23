---
title: Saiba mais sobre as políticas de retenção para o Teams
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
ms.openlocfilehash: 709d4414ebb01081172aff932899146c06d05a19
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268265"
---
# <a name="learn-about-retention-policies-for-microsoft-teams"></a>Saiba mais sobre as políticas de retenção para o Microsoft Teams

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

As informações contidas neste artigo complementam [Saiba mais sobre as políticas de retenção](retention-policies.md) porque são informações específicas para o Microsoft Teams.

## <a name="how-a-retention-policy-works-with-microsoft-teams"></a>Como uma política de retenção funciona com o Microsoft Teams

Você pode usar uma política de retenção para reter chats e mensagens de canal no Teams. Os chats do Teams são armazenados em uma pasta oculta na caixa de correio de cada usuário participante do chat, e as mensagens do canal do Teams são armazenadas em uma pasta oculta semelhante na caixa de correio do grupo da equipe. 

No entanto, é importante compreender que o Teams usa um serviço de chat fornecido pelo Azure que também armazena esses dados e, por padrão, esse serviço armazena os dados para sempre. Por esse motivo, é altamente recomendável usar os locais do Teams para reter e excluir os dados do Teams. Usar os locais do Teams exclui permanentemente os dados da caixa de correio do Exchange e do serviço de chat subjacente fornecido pelo Azure. Para saber mais, confira [Segurança e conformidade no Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258) e, especificamente, a seção [Arquitetura de Proteção de Informações](https://docs.microsoft.com/MicrosoftTeams/security-compliance-overview#information-protection-architecture).

Os chats e mensagens do canal do Teams não são afetados pelas políticas de retenção aplicadas às caixas de correio de usuário ou de grupos. Embora conversas de equipe e mensagens de canal do Teams sejam armazenadas no Exchange, estes dados do Teams só serão incluídos em uma política de retenção configurada para os locais das **mensagens de canal do Teams** e **chats do Teams**.

> [!NOTE]
> Se um usuário estiver incluído em uma política de retenção ativa que retém dados do Teams e você excluir uma caixa de correio de um usuário incluído nessa política, para reter os dados do Teams, a caixa de correio será convertida em uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md). Se você não precisar reter esses dados do Teams para o usuário, exclua o usuário da política de retenção antes de excluir a caixa de correio.

Depois que uma política de retenção for configurada para mensagens de chat ou canal, os caminhos que o conteúdo tomará vai depender se a política de retenção for para reter e excluir, somente reter ou somente excluir.

Quando a política de retenção for reter e excluir:

![Diagrama do fluxo de retenção para mensagens do chat e do canal do Teams](../media/TeamsRetentionLifecycle.png)

1. **Se uma mensagem do chat ou do canal for modificada ou excluída** pelo usuário durante o período de retenção, a mensagem será movida (ou copiada, no caso de edição) para a pasta SubstrateHolds (que é uma pasta oculta em todas as caixas de correio de usuários ou grupos) e será armazenada nessa pasta até que o período de retenção expire. As mensagens são excluídas permanentemente no dia do término do período de retenção.

2. **Se uma mensagem do chat ou do canal não for excluída** durante o período de retenção, a mensagem será movida para a pasta SubstrateHolds dentro de um dia após o término do período de retenção (de 0 a 24 horas). A mensagem é permanentemente excluída um dia após ser movida para a pasta SubstrateHolds. 

> [!NOTE]
> As mensagens na pasta SubstrateHolds são pesquisáveis por ferramentas de descoberta eletrônica. Após a exclusão permanente de uma mensagem, ela não será exibida em uma pesquisa de descoberta eletrônica.

Quando a política de retenção for reter somente ou excluir somente, os caminhos de conteúdo serão variações de reter e excluir:

### <a name="content-paths-for-retain-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção reter somente

1. **Se uma mensagem de chat ou canal for modificada ou excluída** durante o período de retenção: uma cópia da mensagem original será criada na pasta SubstrateHolds e retida até o fim do período de retenção, quando a cópia dessa pasta será excluída permanentemente um dia após o item expirar. 

2. **Se o item não for modificado ou excluído** durante o período de retenção: nada acontece antes e depois do período de retenção; o item permanecerá no local original.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção somente excluir

1. **Se a mensagem não for excluída** durante o período de retenção: no final do período de retenção, a mensagem será movida para a pasta SubstrateHolds. 

2. **Se o item for excluído pelo usuário** durante o período, o item será movido imediatamente para a pasta SubstrateHolds. Se um usuário excluir a mensagem da pasta SubstrateHolds ou esvaziá-la, o item será excluído permanentemente. A mensagem é permanentemente excluída um dia após ser movida para a pasta SubstrateHolds.


## <a name="skype-for-business-and-teams-interop-chats"></a>Chats de Interoperabilidade entre Skype for Business e Teams

O mesmo fluxo funciona para bate-papos de interoperabilidade entre Skype for Business Online e Teams. Quando um chat do Skype for Business entra no Teams, ele se torna uma mensagem em um thread de chat do Teams e recebe uma caixa de correio adequada. As políticas de retenção do Teams vão excluir essas mensagens do thread do Teams. 

No entanto, se o histórico de chats estiver ativado para o Skype for Business e, do lado do cliente do Skype for Business, estiverem sendo salvos em uma caixa de correio, esses dados de bate-papo não serão manejados por uma política de retenção do Teams.

## <a name="files-in-teams"></a>Arquivos no Teams.

No Teams, os arquivos compartilhados no chat são armazenados na conta do OneDrive do usuário que compartilhou o arquivo. Os arquivos carregados nos canais são armazenados no site do SharePoint usado pela equipe. Isso significa que, para manter ou excluir arquivos no Teams, você deve configurar uma ou mais políticas de retenção que se apliquem a **contas do OneDrive** e **sites do SharePoint** além das políticas de retenção configuradas para o Teams. Para saber mais sobre como funcionam as políticas de retenção para esses locais, confira [Saiba mais sobre as políticas de retenção do SharePoint e do OneDrive](retention-policies-sharepoint.md).

> [!NOTE]
> Uma política de retenção que inclui mensagens de canal do Teams ou chats do Teams só pode incluir locais do Teams. Para manter ou excluir esses arquivos no Teams, você deve criar uma política de retenção separada.
> 
> Para aplicar uma política aos arquivos apenas para uma equipe específica, escolha o site do SharePoint para essa equipe e as contas do OneDrive de usuários da equipe.

É possível que uma política de retenção que seja aplicada ao SharePoint ou ao OneDrive for Business exclua um arquivo referenciado em uma mensagem de bate-papo ou de um canal do Team antes que as mensagens sejam excluídas. Neste cenário, o arquivo ainda será mostrado na mensagem do Teams, mas quando os usuários clicarem no arquivo, eles receberão o erro "arquivo não encontrado". Esse comportamento não é específico das políticas de retenção e também pode acontecer se um usuário exclui manualmente um arquivo do SharePoint ou do OneDrive.

## <a name="meetings-and-external-users"></a>Reuniões e usuários externos

As mensagens de reunião de canal são armazenadas da mesma forma que as mensagens de canal; portanto, para esses dados, selecione o local de **mensagens de canal do Teams**ao configurar sua política de retenção.

As mensagens de reunião improvisada são armazenadas da mesma forma que as mensagens de chat de grupo; portanto, para esses dados, selecione o local de **chat do Teams**ao configurar sua política de retenção.

Quando usuários externos são incluídos em uma reunião hospedada por sua organização:

- Se um usuário externo ingressar na reunião usando uma conta de convidado no locatário, esse usuário terá uma caixa de correio de sombra que pode estar sujeita à política de retenção da sua organização para o Teams. Todas as mensagens da reunião são armazenadas na caixa de correio dos seus usuários e na caixa de correio de sombra. 

- Se um usuário externo ingressar na reunião usando uma conta do Microsoft 365 de outra organização, suas políticas de retenção não podem excluir as mensagens para esse usuário porque elas são armazenadas na caixa de correio desse usuário em outro locatário. No entanto, as políticas de retenção podem excluir mensagens para os seus usuários.


## <a name="limitations"></a>Limitações

Estamos trabalhando continuamente para otimizar a funcionalidade de retenção no Teams. Enquanto isso, estas são algumas limitações a considerar:
  
- **O Teams exige uma política de retenção independente**. Ao criar uma política de retenção e ativar os locais do Teams, todos os demais locais são desativados. Uma política de retenção que inclui o Teams só pode incluí-lo e nenhum outro local. 
    
- **O Teams não está incluído em uma política no âmbito de toda a organização**. Se criar uma política no âmbito da organização, o Teams não estará incluído, porque ele exige uma política de retenção independente. 
    
- **O Teams não é compatível com retenção avançada.** Ao criar uma política de retenção, se você escolher as [Configurações avançadas para identificar conteúdo que atende a determinadas condições](create-retention-policies.md#advanced-settings-to-identify-content-that-meets-specific-conditions), os locais do Teams não estarão disponíveis. Atualmente, a retenção no Teams se aplica a todo o conteúdo de chat e de mensagem de canal quando você seleciona esses locais. 

- **As mensagens do Teams em canais privados não são incluídas quando você configura uma política de retenção para mensagens de canal do Teams**. Em vez disso, as mensagens de canais privados são incluídas para os usuários como conversas em grupo com a opção **chats do Teams**. 
    
- **O Teams pode levar até três dias para limpar as mensagens expiradas**. Uma política de retenção aplicada ao Teams excluirá mensagens de chat e de canal ao fim do período de retenção. No entanto, pode levar até três dias para limpar essas mensagens e excluí-las permanentemente. Além disso, as mensagens de chat e de canal serão pesquisáveis com as ferramentas de descoberta eletrônica durante o período de retenção e quando as mensagens forem excluídas permanentemente.
    
   > [!NOTE]
   > Antes, uma política de retenção não podia excluir o conteúdo do Teams em menos de 30 dias, mas removemos essa limitação. Agora, o período de retenção do conteúdo do Teams pode ser personalizado, sendo no mínimo de um dia. Se o período de retenção for de um dia, as mensagens serão excluídas permanentemente três dias após o término do período de retenção.

- **Problema de exibição incorreto no Outlook**. Se você criar políticas de retenção para os locais do Skype ou Teams, uma dessas políticas será exibida como a política de pasta padrão quando um usuário exibir as propriedades de uma pasta de caixa de correio no cliente da área de trabalho do Outlook. Esse é um problema de exibição incorreta no Outlook e [um problema conhecido](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). O que deve ser exibido como a política de pasta padrão é a política de retenção da caixa de correio aplicada à pasta. A política de retenção do Skype ou Teams não é aplicada à caixa de correio do usuário.

- **Problemas de configuração **: 
    - Ao selecionar **Escolher equipes** para a linha de localização**mensagens de canal do Teams**, você pode ver outros grupos do Office 365 que não são equipes. Não selecione esses grupos.
    
    - Ao **Escolher usuários** para o local **Chats do Teams**, você poderá ver convidados e usuários sem caixa de correio. As políticas de retenção não são projetadas para esses usuários, portanto, não os selecione.


## <a name="how-to-configure-a-retention-policy-for-microsoft-teams"></a>Como configurar uma política de retenção para o Microsoft Teams

Confira [Criar e configurar políticas de retenção](create-retention-policies.md).

Na página do assistente **Escolha locais**, selecione as seguintes opções:

- **Deixe-me escolher locais específicos** > **mensagens de canal do Teams** e **chats do Teams**

Uma política de retenção que se aplica ao Teams pode usar o [Bloqueio de preservação](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements), o que pode ser necessário para motivos normativos.

## <a name="related-information"></a>Informações relacionadas

[Políticas de retenção no Microsoft Teams](https://docs.microsoft.com/microsoftteams/retention-policies)
