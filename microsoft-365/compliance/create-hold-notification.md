---
title: Criar um aviso de espera legal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use a ferramenta Comunicações em um caso de Descoberta Eletrônica Avançada para enviar, coletar e rastrear notificações de responsabilidade legal.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840556"
---
# <a name="create-a-legal-hold-notice"></a>Criar um aviso de espera legal

Usando comunicações custodiantes de Descoberta Eletrônica Avançada, as organizações podem gerenciar seu fluxo de trabalho em torno da comunicação com os custodiantes. Por meio da ferramenta de Comunicações, as equipes jurídicas podem enviar, coletar e acompanhar sistematicamente as notificações de espera legal. O processo de criação flexível também permite que as equipes personalizem o fluxo de trabalho de notificação de espera e o conteúdo nos avisos enviados aos custodiantes.

![Página de Comunicações](../media/CommunicationPage.PNG)

O artigo descreve as etapas no fluxo de trabalho de notificação de espera.

## <a name="step-1-specify-communication-details"></a>Etapa 1: especificar detalhes de comunicação

A primeira etapa é especificar os detalhes apropriados para avisos de responsabilidade legal ou outras comunicações custodiais.

![Página de Comunicação de Nomes](../media/NameCommunication.PNG)

1. No Centro de Conformidade & Segurança, vá para a Descoberta > **eDiscovery** Avançada para exibir a lista de ocorrências em sua organização.

2. Selecione um caso, clique na guia **Comunicações** e clique em **Nova comunicação.**

3. Na página **de comunicação nome,** especifique os seguintes detalhes de comunicação (obrigatórios).

    - **Nome:** este é o nome da comunicação.

    - **Diretor de emissão:** a lista suspenso exibe uma lista de membros da ocorrência. For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case). Cada aviso enviado aos custodiantes será enviado em nome do responsável pela emissão especificada.

> [!NOTE]
> O diretor de emissão deve ter uma caixa de correio **ativa** para aparecer no menu suspenso do Diretor de Emissão


4. Clique em **Avançar**.

## <a name="step-2-define-the-portal-content"></a>Etapa 2: definir o conteúdo do portal

Em seguida, você pode criar e adicionar o conteúdo do aviso de espera. Na página **Definir conteúdo do portal** no assistente **Criar** comunicação, especifique o conteúdo do aviso de espera. Esse conteúdo será automaticamente anexado aos avisos de Emissão, Nova Emissão, Lembrete e Escalonamento. Além disso, esse conteúdo será exibido no Portal de Conformidade do custodiante. 

![Página de Conteúdo do Portal](../media/PortalContent.PNG)

Para criar o conteúdo do portal:

1. Digite (ou recorte e colar de outro documento) o aviso de espera na caixa de texto do conteúdo do portal. 

2. Insira variáveis mescladas em seu aviso para personalizar o aviso e compartilhar o Portal de Conformidade custodiantes.

3. Clique em **Avançar**.

  >[!Tip]
  >Para saber mais sobre como personalizar o conteúdo e o formato do conteúdo do portal, consulte [Usar o Editor de Comunicações.](using-communications-editor.md)

## <a name="step-3-set-the-required-notifications"></a>Etapa 3: Definir as notificações necessárias

Depois de definir o conteúdo do aviso de espera, você pode configurar os fluxos de trabalho para enviar e gerenciar o processo de notificação. As notificações são mensagens de email enviadas para notificar e acompanhar os custodiantes. Todos os custodiados adicionados à comunicação receberão a mesma notificação. 

Para configurar e enviar um aviso de espera, você deve incluir notificações de Emissão, Nova Emissão e Lançamento.

### <a name="issuance-notification"></a>Notificação de emissão 

Após a criação da comunicação, a **Notificação** de Emissão é iniciada pelo Diretor de Emissão especificado. A notificação de emissão é a primeira comunicação enviada ao custodiatário para informá-lo sobre suas obrigações de preservação. 

Para criar uma notificação de emissão:

1. No lado **da emissão,** clique em **Editar.**

2. Se necessário, adicione outros membros da ocorrência ou equipe aos **campos Cc** **e Cc.** Para adicionar vários usuários a esses campos, separe os endereços de email com pontos-e-vírgulas.

3. **Especifique o** Assunto para o aviso (obrigatório).

4. Especifique o conteúdo ou instruções adicionais que você gostaria de fornecer ao custodiatário (obrigatório). O conteúdo do portal definido na Etapa 2 é adicionado ao final do aviso de publicação. 

5. Clique em **Salvar**.

### <a name="re-issuance-notification"></a>Re-Issuance notificação

À medida que o caso progride, os custodiantes podem ser obrigados a preservar dados adicionais ou menores do que foi instruído anteriormente. Depois de atualizar o conteúdo do portal, a notificação de nova emissão é enviada e alerta os custodiantes sobre quaisquer alterações em suas obrigações de preservação.

Para criar uma notificação de nova emissão:

1. No lado **reemissão,** clique em **Editar.**

2. Se necessário, adicione outros membros da ocorrência ou equipe aos **campos Cc** **e Cc.** Para adicionar vários usuários a esses campos, separe os endereços de email com pontos-e-vírgulas.

3. **Especifique o** Assunto para o aviso (obrigatório).

4. Especifique o conteúdo ou instruções adicionais que você gostaria de fornecer ao custodiatário (obrigatório). O conteúdo do portal definido na Etapa 2 é adicionado ao final do aviso de reemissão.

5. Clique em **Salvar**.

> [!NOTE]
> Se o conteúdo do portal for modificado (na página Definir Conteúdo do **Portal** no assistente de comunicação Editar), a notificação de nova publicação será automaticamente enviada a todos os custodiantes atribuídos ao aviso.  Depois que a notificação for enviada, os custodiantes serão solicitados a confirmar o aviso de espera. Se você tiver definido algum fluxo de trabalho de lembrete ou escalonamento, eles também serão re-iniciar. Para obter mais informações sobre quais outros eventos de gerenciamento de casos disparam comunicações, consulte [Eventos que disparam notificações.](#events-that-trigger-notifications)

### <a name="release-notification"></a>Notificação de versão

Depois que uma questão for resolvida ou se um custodiante não estiver mais sujeito a preservar conteúdo, você poderá liberar o custodiante de uma ocorrência. Se o custodiante tiver emitido anteriormente um aviso de responsabilidade, a notificação de liberação poderá ser usada para alertar os custodiantes de que eles foram liberados de sua obrigação.

Para criar uma notificação de lançamento: 

1. In the **Release** tile, click **Edit**.

2. Se necessário, adicione outros membros da ocorrência ou equipe aos **campos Cc** **e Cc.** Para adicionar vários usuários a esses campos, separe os endereços de email com pontos-e-vírgulas.

3. **Especifique o** Assunto para o aviso (obrigatório).

4. Especifique o conteúdo ou instruções adicionais que você gostaria de fornecer ao custodiatário (obrigatório).

5. Clique **em** Salvar e vá para a próxima etapa.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Opcional) Etapa 4: Definir as notificações opcionais

Opcionalmente, você pode simplificar o fluxo de trabalho para acompanhar com custodiantes não responsivos criando e agendando notificações automatizadas de lembrete e escalonamento.

![Página Lembrete/Escalonamento](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Reminders

Depois de enviar uma notificação de espera, você pode acompanhar os custodiantes sem resposta definindo um fluxo de trabalho de lembrete.

Para agendar lembretes:

1. No lado **lembrete,** clique em **Editar**.

2. **Habilita o fluxo** de trabalho Lembrete ativando a **alternância status** (obrigatório).

3. **Especifique o intervalo de Lembrete (em dias)** (obrigatório). Esse é o número de dias de espera antes de enviar as primeiras notificações de lembrete e acompanhamento. Por exemplo, se você definir o intervalo de lembrete como sete dias, o primeiro lembrete será enviado sete dias após a notificação de espera ter sido inicialmente emitida. Todos os lembretes subsequentes também seriam enviados a cada sete dias.

4. **Especifique o Número de lembretes** (obrigatório). Este campo especifica quantos lembretes enviar a custodiantes não responsivos. Por exemplo, se você definir o número de lembretes como 3, um custodiante receberá no máximo três lembretes. Depois que um custodiante reconhecer a notificação de espera, os lembretes não serão mais enviados para esse usuário.

5. **Especifique o** Assunto para o aviso (obrigatório). 

6. Especifique o conteúdo ou instruções adicionais que você gostaria de fornecer ao custodiatário (obrigatório). O conteúdo do portal definido na Etapa 2 é adicionado ao final do aviso de lembrete.

7. Clique **em** Salvar e vá para a próxima etapa.

### <a name="escalations"></a>Escalonamentos

Em algumas situações, talvez você precise de maneiras adicionais de acompanhar os custodiantes não responsivos. Se um custodiante não confirmar uma notificação de suspensão após receber o número especificado de lembretes, a equipe jurídica poderá especificar um fluxo de trabalho para enviar automaticamente um aviso de escalonamento para o custodiante e seu gerente.

Para agendar escalonamentos:

1. No lado **do escalonamento,** clique em **Editar.**

2. **Habilita o fluxo de** trabalho de escalonamento ativando a **alternância Status.**

3. **Especifique o intervalo de escalonamento (em dias)** (obrigatório).

4. **Especifique o número de escalonamentos** (obrigatório). Este campo especifica quantas escalações enviar para custodiantes não responsivos. Por exemplo, se você definir o número de escalonamentos como 3, um aviso de escalonamento será enviado ao custodiante e ao gerente no máximo três vezes. Depois que um custodiante reconhecer a notificação de espera, os escalonamentos não serão mais enviados.

5. **Especifique o** Assunto para o aviso (obrigatório). 

6. Especifique o conteúdo ou instruções adicionais que você gostaria de fornecer ao custodiatário (obrigatório). O conteúdo do portal definido na Etapa 2 é adicionado ao final do aviso de escalonamento.

7. Clique **em** Salvar e vá para a próxima etapa.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Etapa 5: Atribuir custodiantes para receber notificações

Depois de finalizar o conteúdo para notificações, selecione os custodiantes aos que você gostaria de enviar notificações. 

![Página Selecionar Custodiantes](../media/SelectCustodians.PNG)

Para adicionar custodiantes:

1. Atribua custodiantes à comunicação clicando na caixa de seleção ao lado do nome.

    Após a criação da comunicação, o fluxo de trabalho de notificação será aplicado automaticamente aos custodiantes selecionados.

2. Clique **em Próximo** para revisar as configurações e os detalhes da comunicação.

>[!NOTE]
>Você só pode adicionar custodiantes que foram adicionados à ocorrência e não foram enviadas outra notificação dentro da ocorrência.

## <a name="step-6-review-settings"></a>Etapa 6: Revisar as configurações

Depois de revisar as configurações e clicar em **Enviar** para concluir a comunicação, o sistema iniciará automaticamente o fluxo de trabalho de comunicação enviando o aviso de emissão.

## <a name="events-that-trigger-notifications"></a>Eventos que disparam notificações

A tabela a seguir descreve eventos no processo de gerenciamento de casos que disparam quando os diferentes tipos de notificações são enviados aos custodiantes.

|Tipo de comunicação|Gatilho |
|:---------|:---------|
|Avisos de emissão|A criação inicial da notificação. Você também pode resendá-la manualmente. |
|Avisos de reemissão|Atualizando o conteúdo do portal na página **Definir Conteúdo do Portal** no assistente editar **comunicação.**|
|Avisos de versão|O custodiante é liberado da ocorrência.|
|Reminders|O intervalo e o número de lembretes configurados para o lembrete.|
|Escalonamentos|O intervalo e o número de lembretes configurados para o escalonamento.|
|||
