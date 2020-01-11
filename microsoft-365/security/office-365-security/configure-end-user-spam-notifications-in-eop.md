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
ms.openlocfilehash: ea65081b1b312af3ee15335721ec042dc9d3b1da
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021997"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="c5e89-103">Configurar as notificações de spam para o usuário final no EOP</span><span class="sxs-lookup"><span data-stu-id="c5e89-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5e89-104">Este tópico é voltado aos clientes autônomos do EOP (Exchange Online Protection) que estão protegendo caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="c5e89-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="c5e89-105">Os clientes do Exchange Online que estão protegendo caixas de correio hospedadas na nuvem devem ler o seguinte tópico em vez disso: [configurar notificações de spam para o usuário final no Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="c5e89-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="c5e89-106">Você pode configurar as notificações de spam para o usuário final para a política de filtro de spam padrão para toda a empresa ou para políticas personalizadas de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="c5e89-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="c5e89-107">Habilitar mensagens de notificação de spam do usuário final permite que os usuários gerenciem suas próprias mensagens de spam em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c5e89-107">Enabling end-user spam notification messages lets your users manage their own spam-quarantined messages.</span></span> 
  
<span data-ttu-id="c5e89-p103">As notificações de spam do usuário final contém uma lista de todas as mensagens de spam em quarentena que o usuário final recebeu durante um período de tempo que você configurou (você pode especificar um valor entre 1 e 15 dias). Você também pode configurar o idioma no qual a mensagem de notificação será escrita.</span><span class="sxs-lookup"><span data-stu-id="c5e89-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="c5e89-110">Após receber uma mensagem de notificação, os usuários finais podem escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c5e89-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="c5e89-111">**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c5e89-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="c5e89-112">**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c5e89-112">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="c5e89-113">**Revise** para navegar até o portal de quarentena no centro de segurança e conformidade se você quiser realizar outras ações, como visualizar ou liberar.</span><span class="sxs-lookup"><span data-stu-id="c5e89-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5e89-114">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c5e89-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="c5e89-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="c5e89-115"></span></span>

<span data-ttu-id="c5e89-116">Tempo estimado para conclusão: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="c5e89-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="c5e89-p104">Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Entrada "Antispam", no tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="c5e89-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="c5e89-119">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c5e89-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="c5e89-120">Use o EAC para configurar as notificações de spam do usuário final</span><span class="sxs-lookup"><span data-stu-id="c5e89-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="c5e89-121">No centro de administração do Exchange (Eat), navegue até**filtro de spam**de **proteção** > .</span><span class="sxs-lookup"><span data-stu-id="c5e89-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="c5e89-122">Selecione a política de filtro de conteúdo para a qual você deseja habilitar as notificações de spam do usuário final (elas são desabilitadas por padrão).</span><span class="sxs-lookup"><span data-stu-id="c5e89-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="c5e89-123">No painel direito, onde as informações resumidas sobre política aparecem, clique no link **Configurar notificações de spam para o usuário final**.</span><span class="sxs-lookup"><span data-stu-id="c5e89-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="c5e89-124">Na caixa de diálogo posterior, você pode configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c5e89-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="c5e89-p105">**Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.)</span><span class="sxs-lookup"><span data-stu-id="c5e89-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="c5e89-p106">**Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="c5e89-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="c5e89-131">**Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="c5e89-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="c5e89-p107">Clique em **salvar**. Um resumo das suas configurações de política de filtro de conteúdo, incluindo as suas cnfigurações de notificação de spam para o usuário final, aparecem no painel do lado direito.</span><span class="sxs-lookup"><span data-stu-id="c5e89-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="c5e89-p108">As notificações de spam do usuário final só serão funcionais para as políticas de filtragem de conteúdo que estiverem habilitadas. >  As notificações de spam do usuário final só são enviadas uma vez por dia. O horário de entrega da notificação não pode ser garantido para qualquer cliente específico e não é configurável.</span><span class="sxs-lookup"><span data-stu-id="c5e89-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="c5e89-137">**Dica:** Se você deseja testar notificações de spam do usuário final enviando-as para um conjunto limitado de usuários antes de implementá-las completamente, crie uma política de filtro de conteúdo personalizado que habilite as notificações de spam do usuário final dos domínios nos quais os usuários residem.</span><span class="sxs-lookup"><span data-stu-id="c5e89-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="c5e89-138">Em seguida, no Eat, em **regras de \> fluxo de emails**, crie uma regra de fluxo de emails (também conhecida como regra de transporte) para bloquear mensagens de Quarantine@messaging.microsoft.com (o endereço de email que envia notificações) com exceções para os usuários que você deseja receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="c5e89-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="c5e89-139">A imagem a seguir é um exemplo de criação de uma exceção de dois usuários (SaraD e AlbertoD) do domínio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="c5e89-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regra de transporte para testar notificações de spam do usuário final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="c5e89-141">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="c5e89-141">For more information</span></span>

[<span data-ttu-id="c5e89-142">Configurar suas políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="c5e89-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
