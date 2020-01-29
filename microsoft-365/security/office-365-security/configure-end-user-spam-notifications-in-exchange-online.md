---
title: Configurar notificações de spam para o usuário final no Exchange Online
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Você pode configurar as notificações de spam para o usuário final para a política de filtro de spam padrão para toda a empresa ou para políticas de filtro de spam personalizadas que são aplicadas a domínios.
ms.openlocfilehash: 7292d75afb07864fc50d4df30fa5f84691087820
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573008"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Configurar notificações de spam para o usuário final no Exchange Online

> [!IMPORTANT]
> Este tópico é para os clientes do Exchange Online que estão protegendo caixas de correio hospedadas em nuvem. Os clientes autônomos do Exchange Online Protection (EOP) que estão protegendo caixas de correio locais devem ler o seguinte tópico em vez disso: [configurar notificações de spam para o usuário final no EOP](configure-end-user-spam-notifications-in-eop.md). 
  
Você pode configurar as notificações de spam para o usuário final para a política de filtro de spam padrão para toda a empresa ou para políticas personalizadas de filtro de spam. Habilitar mensagens de notificação de spam do usuário final permite que os usuários gerenciem suas próprias mensagens de spam em quarentena. 
  
As notificações de spam do usuário final contém uma lista de todas as mensagens de spam em quarentena que o usuário final recebeu durante um período de tempo que você configurou (você pode especificar um valor entre 1 e 15 dias). Você também pode configurar o idioma no qual a mensagem de notificação será escrita.
  
Após receber uma mensagem de notificação, os usuários finais podem escolher entre as seguintes opções:

**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.

**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.

**Revise** para navegar até o portal de quarentena dentro do centro de conformidade de & de segurança se você quiser realizar outras ações, como visualização ou lançamento.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

Tempo estimado para conclusão: 2 minutos
  
Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o entrada "anti-spam" no tópico [permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) . 
  
Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Use o EAC para configurar as notificações de spam do usuário final

1. No Centro de Administração do Exchange (EAC), navegue até **Proteção** \> **Filtro de conteúdo**.
    
2. Selecione a política de filtro de spam para a qual você deseja habilitar as notificações de spam do usuário final (elas estão desabilitadas por padrão).
    
3. No painel direito, onde as informações resumidas sobre política aparecem, clique no link **Configurar notificações de spam para o usuário final**. 
    
4. Na caixa de diálogo posterior, você pode configurar as seguintes opções:
    
   - **Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.) 
    
   - **Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam. 
    
   - **Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva. 
    
   - Clique em **Salvar**. Um resumo das configurações de política de filtro de spam, incluindo as configurações de notificação de spam do usuário final, aparece no painel direito.
    
> [!NOTE]
>  As notificações de spam do usuário final só serão funcionais para políticas de filtro de spam habilitadas. >  As notificações de spam do usuário final só são enviadas uma vez por dia. O horário de entrega da notificação não pode ser garantido para qualquer cliente específico e não é configurável. 
  
 **Dica:** Se você quiser testar as notificações de spam do usuário final enviando-as a um conjunto limitado de usuários antes de implementá-las totalmente, crie uma política de filtro de spam personalizada que permite as notificações de spam do usuário final para os domínios nos quais os usuários residem. Em seguida, no Eat, em **regras de \> fluxo de emails**, crie uma regra de fluxo de emails (também conhecida como regra de transporte) para bloquear mensagens de Quarantine@messaging.microsoft.com (o endereço de email que envia notificações) com exceções para os usuários que você deseja receber as notificações. A imagem a seguir é um exemplo de criação de uma exceção de dois usuários (SaraD e AlbertoD) do domínio Contoso.com: 
  
![Regra de transporte para testar notificações de spam do usuário final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>Usar o SCC para configurar notificações de spam para o usuário final

Você também pode usar o centro de conformidade e segurança (SCC) para configurar as notificações de spam do usuário final. Siga estas etapas:

1. Abra o centro de segurança e conformidade, navegue até **anti-spam** da **política** \> de **Gerenciamento** \> de ameaças ou https://protection.office.com/antispamuse o link direto.

2. Clique na seta para baixo ao lado da política de filtro de spam para a qual você deseja habilitar as notificações de spam do usuário final.

3. Clique no link **configurar notificações de spam para o usuário final** .

4. Na caixa de diálogo posterior, você pode configurar as seguintes opções:
    
   - **Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.) 
    
   - **Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam. 
    
   - **Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva. 
    
   - Clique em **Salvar**. Um resumo das configurações de política de filtro de spam, incluindo as configurações de notificação de spam do usuário final, aparece no painel.

## <a name="for-more-information"></a>Para obter mais informações

[Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md)
  
