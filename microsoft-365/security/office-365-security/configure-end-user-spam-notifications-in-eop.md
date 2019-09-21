---
title: Configurar as notificações de spam para o usuário final no EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Você pode configurar as notificações de spam do usuário final para a política padrão de filtro de conteúdo para toda a organização ou para políticas personalizadas de filtro de conteúdo que são aplicadas aos domínios.
ms.openlocfilehash: 45cc75a7b090df86d0c5f9b1d47d452520693530
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073768"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a>Configurar as notificações de spam para o usuário final no EOP
  
> [!IMPORTANT]
> Este tópico é voltado aos clientes autônomos do EOP (Exchange Online Protection) que estão protegendo caixas de correio locais. Os clientes do Exchange Online que estão protegendo caixas de correio hospedadas na nuvem devem ler o seguinte tópico em vez disso: [configurar notificações de spam para o usuário final no Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md). 
  
Você pode configurar as notificações de spam do usuário final para a política padrão de filtro de conteúdo para toda a organização ou para políticas personalizadas de filtro de conteúdo que são aplicadas aos domínios. Habilitar mensagens de notificação de spam do usuário final permite que os usuários finais gerenciem as suas próprias mensagens de spam em quarentena. As notificações de spam do usuário final não podem ser usadas com as políticas aplicadas a usuários ou grupos, ou a uma política com exceções.
  
As notificações de spam do usuário final contém uma lista de todas as mensagens de spam em quarentena que o usuário final recebeu durante um período de tempo que você configurou (você pode especificar um valor entre 1 e 15 dias). Você também pode configurar o idioma no qual a mensagem de notificação será escrita.
  
Após receber uma mensagem de notificação, os usuários finais podem escolher entre as seguintes opções:

**Visualize** a mensagem se quiser visualizar o conteúdo ou o cabeçalho antes de executar a ação.

**Baixe** a mensagem se quiser revisar a mensagem e os anexos (se houver) no dispositivo antes de executar a ação.

**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.

**Versão & permitir remetente** se a mensagem não for spam e se você quiser que o Office 365 adicione o remetente à sua lista de remetentes e destinatários confiáveis para futuros emails. Tenha em mente que seu administrador pode ter outras configurações de permissão/bloqueio de toda a organização que substituem sua lista de remetentes seguros.

**Release & Report**, se a mensagem não for spam e você quiser enviar a mensagem para sua caixa de correio e relatá-la para a Microsoft para análise.

**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?
<a name="sectionSection0"> </a>

Tempo estimado para conclusão: 5 minutos
  
Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Antispam", no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md). 
  
Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>Use o EAC para configurar as notificações de spam do usuário final

1. No centro de administração do Exchange (Eat), navegue até**filtro de spam**de **proteção** > .
    
2. Selecione a política de filtro de conteúdo para a qual você deseja habilitar as notificações de spam do usuário final (elas são desabilitadas por padrão).
    
3. No painel direito, onde as informações resumidas sobre política aparecem, clique no link **Configurar notificações de spam para o usuário final**. 
    
4. Na caixa de diálogo posterior, você pode configurar as seguintes opções:
    
1. **Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.) 
    
2. **Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam. 
    
3. **Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva. 
    
5. Clique em **salvar**. Um resumo das suas configurações de política de filtro de conteúdo, incluindo as suas cnfigurações de notificação de spam para o usuário final, aparecem no painel do lado direito.
    
> [!NOTE]
>  As notificações de spam do usuário final só serão funcionais para as políticas de filtragem de conteúdo que estiverem habilitadas. >  As notificações de spam do usuário final só são enviadas uma vez por dia. O horário de entrega da notificação não pode ser garantido para qualquer cliente específico e não é configurável. 
  
 **Dica:** Se você deseja testar notificações de spam do usuário final enviando-as para um conjunto limitado de usuários antes de implementá-las completamente, crie uma política de filtro de conteúdo personalizado que habilite as notificações de spam do usuário final dos domínios nos quais os usuários residem. Em seguida, no Eat, em **regras de \> fluxo de emails**, crie uma regra de fluxo de emails (também conhecida como regra de transporte) para bloquear mensagens do Quarantine@messaging.microsoft.com (o endereço de email que envia notificações) com exceções para os usuários que você deseja para receber notificações. A imagem a seguir é um exemplo de criação de uma exceção de dois usuários (SaraD e AlbertoD) do domínio Contoso.com: 
  
![Regra de transporte para testar notificações de spam do usuário final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a>Para saber mais

[Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md)
  
