---
title: Saiba mais sobre a retenção para o Yammer
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
description: Saiba mais sobre as políticas de retenção que se aplicam ao Yammer.
ms.openlocfilehash: 1398bf385631967d92de760924ef94e2b3c16441
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362289"
---
# <a name="learn-about-retention-for-yammer"></a>Saiba mais sobre a retenção para o Yammer

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Este recurso está em versão prévia e sujeito a alterações.

As informações contidas neste artigo complementam [Saiba mais sobre retenção](retention.md) porque são informações específicas para o Yammer.

Para outras cargas de trabalho, confira:

- [Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o Microsoft OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre retenção para o Microsoft Teams](retention-policies-teams.md)
- [Saiba mais sobre a retenção para o Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>O que está incluído para retenção e exclusão

Os seguintes itens da Yammer podem ser retidos e excluídos utilizando as políticas de retenção da Yammer: Mensagens da comunidade e mensagens de usuário.

As reações de outras pessoas na forma de emoticons não estão incluídas nessas mensagens.

## <a name="how-retention-works-with-yammer"></a>Como a retenção funciona com o Yammer

Usar esta seção para entender como suas exigências de conformidade são atendidas pelo armazenamento e processos backend, e devem ser verificadas por ferramentas eDiscovery em vez de por mensagens que são atualmente visíveis no aplicativo Yammer.

Você pode usar uma política de retenção para reter dados de mensagens comunitárias e mensagens de usuários na Yammer, e apagar essas mensagens. Nos bastidores, as caixas de correio Exchange são usadas para armazenar dados copiados destas mensagens. Os dados das mensagens de usuário Yammer são armazenados em uma pasta oculta na caixa de correio de cada usuário incluído na mensagem de usuário, e uma pasta oculta semelhante em uma caixa de correio de grupo é usada para mensagens comunitárias.

Cópias das mensagens da comunidade também podem ser armazenadas na pasta oculta das caixas postais dos usuários quando eles @ mencionam usuários ou notificam o usuário de uma resposta. Embora estas mensagens se originem como uma mensagem comunitária, uma política de retenção para mensagens de usuários da Yammer muitas vezes incluirá cópias de mensagens comunitárias.

Essas pastas ocultas não foram projetadas para serem acessíveis diretamente para usuários ou administradores, em vez disso, armazenam dados que os administradores de conformidade podem pesquisar com ferramentas de Descoberta Eletrônica.

> [!IMPORTANT]
> Como as cópias das mensagens da comunidade também podem ser armazenadas nas caixas postais dos usuários, uma política de retenção com uma ação de exclusão das mensagens dos usuários Yammer pode resultar em que a mensagem original da comunidade não seja mais visível aos usuários no aplicativo Yammer.
> 
> Entretanto, uma cópia da mensagem original ainda está disponível na pasta oculta da caixa postal do grupo comunitário, e acessível com o eDiscovery busca a conformidade.

As mensagens Yammer não são afetadas pelas políticas de retenção que são configuradas para as caixas de correio Exchange. Embora as mensagens do Yammer sejam armazenadas no Exchange, esses dados do Yammer só serão incluídos em uma política de retenção configurada para os locais das **mensagens da comunidade do Yammer** e das **mensagens de usuário do Yammer**.

> [!NOTE]
> Se um usuário estiver incluído em uma política de retenção ativa que retém dados do Yammer e você excluir uma caixa de correio de um usuário incluído nessa política, para reter os dados do Yammer, a caixa de correio será convertida em uma [caixa de correio inativa](inactive-mailboxes-in-office-365.md). Se você não precisar reter esses dados do Yammer para o usuário, exclua a conta de usuário da política de retenção antes de excluir a caixa de correio.

Depois que uma política de retenção for configurada para mensagens do Yammer, um trabalho de temporizador do serviço do Exchange avaliará periodicamente os itens na pasta oculta em que essas mensagens do Yammer são armazenadas. O trabalho de temporizador leva até sete dias para ser executado. Quando o período de retenção desses itens expira, eles são movidos para a pasta SubstrateHolds, uma pasta oculta que toda caixa de correio de usuário ou grupo possui para armazenar itens “excluídos temporariamente” antes de serem excluídos permanentemente.

> [!NOTE]
> Por causa do [primeiro princípio de retenção](retention.md#the-principles-of-retention-or-what-takes-precedence), a eliminação permanente é sempre suspensa se o mesmo item tiver que ser retido por causa de outra política de retenção, ou se estiver sob Descoberta Eletrônica por motivos legais ou de investigação.

Depois que uma política de retenção for configurada para mensagens do Yammer, os caminhos que o conteúdo tomará vão depender se a política de retenção for para reter e excluir, somente reter ou somente excluir.

Quando a política de retenção for reter e excluir:

![Diagrama do fluxo de retenção de mensagens do Yammer](../media/yammerretentionlifecycle.png)

Para os dois caminhos no diagrama:

1. **Se uma mensagem do Yammer for editada ou excluída** pelo usuário durante o período de retenção, a mensagem original será copiada imediatamente (se foi editada) ou movida (se foi excluída) para a pasta SubstrateHolds. A mensagem é armazenada lá até que o período de retenção expirar e a mensagem será permanentemente excluída imediatamente.

2. **Se uma mensagem do Yammer não for excluída** e para as mensagens atuais após a edição, a mensagem será movida para a pasta SubstrateHolds após o período de retenção expirar. Essa ação leva sete dias após a data de vencimento. Quando a mensagem estiver na pasta SubstrateHolds, ela será permanentemente excluída imediatamente. 

> [!NOTE]
> As mensagens na pasta SubstrateHolds são pesquisáveis por ferramentas de descoberta eletrônica. Até que as mensagens sejam excluídas permanentemente (na pasta SubstrateHolds), elas permanecerão pesquisáveis por ferramentas de Descoberta Eletrônica.

Quando a política de retenção é somente retenção ou somente exclusão, os caminhos de conteúdo serão variações de reter e excluir.

### <a name="content-paths-for-retain-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção reter somente

1. **Se uma mensagem do Yammer for editada ou excluída**: uma cópia da mensagem original é criada imediatamente na pasta SubstrateHolds e mantida lá até que o período de retenção expire. Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds imediatamente.

2. **Se a mensagem do Yammer não for modificada ou excluída** e para as mensagens atuais após a edição durante o período de retenção: nada acontece antes e depois do período de retenção; a mensagem permanecerá no local original.

### <a name="content-paths-for-delete-only-retention-policy"></a>Caminhos de conteúdo para a política de retenção somente excluir

1. **Se a mensagem do Yammer não for excluída** durante o período de retenção: no final do período de retenção, a mensagem será movida para a pasta SubstrateHolds. Essa ação leva sete dias após a data de vencimento. Em seguida, a mensagem será permanentemente excluída da pasta SubstrateHolds imediatamente.

2. **Se a mensagem do Yammer for excluída pelo usuário** durante o período, o item será movido imediatamente para a pasta SubstrateHolds, onde será permanentemente excluído imediatamente.


## <a name="messages-and-external-users"></a>Mensagens e usuários externos

Por padrão, uma política de retenção para mensagens de usuário do Yammer se aplica a todos os usuários da organização, mas não a usuários externos. Você pode aplicar uma política de retenção a usuários externos se usar a opção **Editar** para usuários incluídos, e especificar sua conta.

No momento, não há suporte para os usuários convidados do Azure B2B.

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização 

Se um usuário deixar a organização e a conta do Microsoft 365 for excluída, suas mensagens de usuário do Yammer sujeitas a retenção serão armazenadas em uma caixa de correio inativa. Essas mensagens permanecem sujeitas a qualquer política de retenção que foi colocada no usuário antes da sua caixa de correio ser desativada, e o conteúdo fica disponível para uma pesquisa de Descoberta Eletrônica. Para obter mais informações, consulte [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md). 

Se o usuário tiver armazenado os arquivos no Yammer, consulte a [seção equivalente](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) do SharePoint e do OneDrive.

## <a name="limitations"></a>Limitações

No momento, as políticas de retenção do Yammer estão no modo de visualização e estamos trabalhando continuamente para otimizar a funcionalidade de retenção. Entretanto, esteja ciente da seguinte limitação quando utilizar retenção para mensagens da comunidade Yammer e mensagens de usuários:

- Quando você seleciona **Editar** para o **local** das mensagens do usuário Yammer, você pode ver convidados e usuários que não são da caixa postal. As políticas de retenção não são projetadas para esses usuários, portanto, não os selecione.

## <a name="configuration-guidance"></a>Instruções de configuração

Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

Se você estiver pronto para configurar uma política de retenção do Yammer, consulte [Criar e configurar políticas de retenção](create-retention-policies.md).