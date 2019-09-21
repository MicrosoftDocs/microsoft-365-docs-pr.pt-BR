---
title: Localizar e liberar mensagens em quarentena como usuário do Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 'Como usuário do Office 365, você pode gerenciar as mensagens de spam em quarentena de duas maneiras: responder às notificações de spam enviadas diretamente para você (se o administrador configurou esse recurso) ou usar o recurso Quarentena de spam, no &amp; Centro de Conformidade e Segurança.'
ms.openlocfilehash: 341e56049926851c4a84989c5a437e5d994aff5f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072483"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Localizar e liberar mensagens em quarentena como usuário do Office 365

Como usuário do Office 365, você pode gerenciar as mensagens que foram enviadas para a quarentena, em vez de enviá-las para você em uma destas maneiras: [, ](use-spam-notifications-to-release-and-report-quarantined-messages.md)responder às notificações de spam enviadas diretamente para você (se o administrador configurou isso)&amp; ou usar o Centro de Conformidade e Segurança. 
  
> [!NOTE]
> Se você é o administrador, pode [gerenciar mensagens em quarentena](manage-quarantined-messages-and-files.md) para outras pessoas da organização. 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Exibir mensagens que foram enviadas para a quarentena, em vez de serem enviadas para você

1. Entre no Office 365 e [vá para o Centro de Conformidade e Segurança](../../compliance/go-to-the-securitycompliance-center.md), usando uma conta corporativa ou de estudante. 
    
2. No lado esquerdo, expanda **Gerenciamento de Ameaças**, escolha **Revisão** e escolha **Quarentena**.
    
    > [!TIP]
    > Para acessar diretamente a página **Quarentena ** no Centro de &amp;Conformidade e Segurança, use a seguinte URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
Por padrão, o Centro de &amp; Conformidade e Segurança exibe todas as mensagens de email que foram enviadas para a quarentena como spam. As mensagens são classificadas da mais recente à mais antiga, de acordo com a **Data** de recebimento da mensagem. **Remetente**, **Assunto**, e a data de vencimento (em **expiras** ) também são exibidos para cada mensagem. Para classificar um campo, clique no cabeçalho da coluna correspondente. clique no cabeçalho de uma coluna novamente para inverter a ordem da classificação.  
  
Você pode exibir uma lista de todas as mensagens em quarentena ou pesquisar mensagens específicas por meio de filtragem. Nosso sistema permite realizar operações em massa com até 100 itens, portanto a filtragem também pode ajudar a reduzir o conjunto de resultados, se você tiver mais do que essa quantidade de itens. Para filtrar rapidamente as mensagens por um único motivo de quarentena, escolha uma opção na lista suspensa. As opções são:
  
- Email identificado como spam. Essas mensagens em quarentena são mostradas por padrão.
    
- Email identificado como email em massa.
    
Depois de localizar uma mensagem específica em quarentena, clique nela para exibir os detalhes e realizar ações. Você pode liberar a mensagem para a Caixa de Entrada, visualizar, baixar ou excluir imediatamente a mensagem da quarentena.
  
> [!NOTE]
> É necessário ter permissões de administrador do Office 365 para tratar as mensagens em quarentena que foram enviadas para outros usuários. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>Para filtrar e localizar mensagens em quarentena:

Caso tenha muitos itens em quarentena, filtre-os para reduzi-los a uma quantidade mais fácil de gerenciar.
  
1. Na página **Quarentena**, escolha se deseja exibir mensagens em quarentena nas modalidades **Spam** ou **Em massa**. 
    
2. Em **Classificar resultados por**, defina os filtros adequados para escolher uma combinação de condições (no momento, não é possível usar caracteres curinga). Entre as várias condições disponíveis, estão as seguintes:
    
  - **ID de Mensagem** Use esse recurso para selecionar uma mensagem específica se souber a identificação da mensagem. 
    
    Por exemplo, se uma mensagem específica é enviada por, ou destinada a, um usuário em sua organização, mas ela nunca chega ao seu destino, você pode procurar a mensagem, utilizando um recurso de rastreamento de mensagens.(consulte [Executar um rastreamento de mensagem e exibir resultados](https://go.microsoft.com/fwlink/?LinkId=799737)). Se você descobrir que a mensagem foi enviada para a quarentena, talvez porque ela corresponde a uma regra ou foi identificada como spam, é possível encontrá-la facilmente na quarentena especificando sua ID de Mensagem. Certifique-se de incluir a cadeia de caracteres de ID de Mensagem completa. Isso pode incluir colchetes angulares\<(\>), por exemplo:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **Endereço de email do remetente** Escolha essa opção para filtrar por um único endereço de email de remetente. 
    
  - **Endereço de email do destinatário** Escolha essa opção para filtrar por um único endereço de email de destinatário. 
    
  - **Assunto** Insira o assunto do endereço de email que você deseja localizar. 
    
  - **Intervalo de datas** Escolha essa opção para filtrar pela data em que a mensagem foi enviada à quarentena. É possível especificar a data ou o intervalo de datas, inclusive o horário. 
    
  - **Data de validade** Para filtrar a data de validade, escolha **Filtro avançado**. Você pode selecionar mensagens que serão excluídas da quarentena dentro de 24 horas ( **Hoje **), nas próximas 48 horas ( **Próximos 2 dias**), na próxima semana ( **Próximos 7 dias **), ou escolha um intervalo de tempo personalizado.
    
    > [!IMPORTANT]
    > Por padrão, as mensagens de spam ou de email em massa são mantidas na quarentena por 30 dias. No entanto, esse período é configurável, e o administrador pode ter definido um período de retenção em quarentena diferente. Quando o Office 365 exclui uma mensagem da quarentena, não é possível recuperá-la. 
  
## <a name="view-details-for-a-specific-message"></a>Exibir os detalhes de uma mensagem específica

Depois de selecionar uma mensagem, você verá um resumo das propriedades da mensagem em um painel, no lado direito da página.
  
- **ID de Mensagem**: identificador exclusivo da mensagem. 
    
- **Endereço do Remetente**: a pessoa que enviou a mensagem. 
    
- **Recebida:** data em que a mensagem foi recebida. 
    
- **Assunto: ** O texto da linha de assunto da mensagem. 
    
- **Motivo da quarentena**: mostra se a mensagem foi identificada como **Spam** ou **Em massa**.
    
- **Expira em**: data em que a mensagem será excluída da quarentena. 
    
- **Liberação para**: todos os endereços de email (se houver) para os quais a mensagem foi liberada. 
    
- **Sem liberação para**. Todos os endereços de email (se houver) para os quais a mensagem não foi liberada. Você pode optar por **Liberar ** caso pretenda liberar a mensagem para a Caixa de Entrada.(Saiba mais sobre a liberação de mensagens na próxima seção). 
    
Para obter mais detalhes sobre a mensagem, escolha uma das seguintes opções:
  
- **Exibir cabeçalho da mensagem** Escolha para ver o texto do cabeçalho da mensagem. Para analisar o cabeçalho em detalhes, copie o respectivo texto para a área de transferência; em seguida, escolha **Analisador de Cabeçalho de Mensagens da Microsoft** para ir até o Analisador de Conectividade Remota. (Se não quiser sair do Office 365 para realizar esta tarefa, clique com o botão direito do mouse e escolha Abrir em uma nova guia). Cole o cabeçalho da mensagem na página, na seção do Analisador de Cabeçalho de Mensagem, e escolha Analisar cabeçalhos. 
    
- **Visualizar mensagem** Permite exibir versões brutas ou em HTML do texto do corpo da mensagem. No modo de exibição de HTML. 
    
## <a name="manage-your-quarantined-messages"></a>Gerenciar as mensagens em quarentena

Depois de selecionar uma mensagem ou um grupo de mensagens, há várias opções disponíveis para gerenciar mensagens em quarentena.
  
- Não tomar nenhuma medida. Se optar por não fazer nada, o Office 365 excluirá automaticamente a mensagem, após a data de expiração. Lembre-se: quando o Office 365 exclui uma mensagem da quarentena, não é possível recuperá-la.
    
- **Liberar mensagem** Libere uma mensagem ou um conjunto de mensagens em quarentena para que elas sejam enviadas para a Caixa de Entrada. Quando libera uma mensagem, você tem a opção de relatá-la à Microsoft para análise. 
    
    Se optar por relatar uma mensagem, fato referido também como "relatar mensagem como falso positivo", ela será relatada à Equipe de Análise de Spam da Microsoft. A equipe avalia e analisa mensagens identificadas como falsos positivos e, dependendo dos resultados da análise, é possível ajustar as regras de filtro de conteúdo de spam de todo o serviço para permitir o envio dessas mensagens.
    
- **Baixar mensagem** Permite baixar a mensagem como um arquivo .eml. Depois de baixar a mensagem, é possível examinar o arquivo .eml, usando o cliente de email, antes de liberá-la. 
    
- **Remover da quarentena** Exclui a mensagem imediatamente da quarentena, sem liberá-la para a Caixa de Entrada. 
    

