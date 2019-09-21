---
title: Configurar notificações de spam do usuário final no Exchange Online
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
ms.openlocfilehash: 1c2832110c98af07752ac7dc7fc985fcb75bc0dd
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073329"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="b6eb7-103">Configurar notificações de spam do usuário final no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b6eb7-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6eb7-104">Este tópico é para os clientes do Exchange Online que estão protegendo caixas de correio hospedadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="b6eb7-105">Os clientes autônomos do Exchange Online Protection (EOP) que estão protegendo caixas de correio locais devem ler o seguinte tópico em vez disso: [configurar notificações de spam para o usuário final no EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b6eb7-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="b6eb7-106">Você pode configurar as notificações de spam para o usuário final para a política de filtro de spam padrão para toda a empresa ou para políticas de filtro de spam personalizadas que são aplicadas a domínios.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains.</span></span> <span data-ttu-id="b6eb7-107">Habilitar mensagens de notificação de spam do usuário final permite que os usuários finais gerenciem as suas próprias mensagens de spam em quarentena.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-107">Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages.</span></span> <span data-ttu-id="b6eb7-108">As notificações de spam do usuário final não podem ser usadas com as políticas aplicadas a usuários ou grupos, ou a uma política com exceções.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-108">End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="b6eb7-p103">As notificações de spam do usuário final contém uma lista de todas as mensagens de spam em quarentena que o usuário final recebeu durante um período de tempo que você configurou (você pode especificar um valor entre 1 e 15 dias). Você também pode configurar o idioma no qual a mensagem de notificação será escrita.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="b6eb7-111">Após receber uma mensagem de notificação, os usuários finais podem escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b6eb7-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="b6eb7-112">**Visualize** a mensagem se quiser visualizar o conteúdo ou o cabeçalho antes de executar a ação.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="b6eb7-113">**Baixe** a mensagem se quiser revisar a mensagem e os anexos (se houver) no dispositivo antes de executar a ação.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="b6eb7-114">**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="b6eb7-115">**Versão & permitir remetente** se a mensagem não for spam e se você quiser que o Office 365 adicione o remetente à sua lista de remetentes e destinatários confiáveis para futuros emails.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-115">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="b6eb7-116">Tenha em mente que seu administrador pode ter outras configurações de permissão/bloqueio de toda a organização que substituem sua lista de remetentes seguros.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-116">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="b6eb7-117">**Release & Report**, se a mensagem não for spam e você quiser enviar a mensagem para sua caixa de correio e relatá-la para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="b6eb7-118">**Bloquear** se você quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6eb7-119">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="b6eb7-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="b6eb7-120">Tempo estimado para conclusão: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="b6eb7-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="b6eb7-121">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b6eb7-122">Para ver de que permissões você precisa, consulte o entrada "anti-spam" no tópico [permissões de recursos no Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="b6eb7-122">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="b6eb7-123">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b6eb7-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b6eb7-124">Use o EAC para configurar as notificações de spam do usuário final</span><span class="sxs-lookup"><span data-stu-id="b6eb7-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="b6eb7-125">No Centro de Administração do Exchange (EAC), navegue até **Proteção** \> **Filtro de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="b6eb7-126">Selecione a política de filtro de spam para a qual você deseja habilitar as notificações de spam do usuário final (elas estão desabilitadas por padrão).</span><span class="sxs-lookup"><span data-stu-id="b6eb7-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="b6eb7-127">No painel direito, onde as informações resumidas sobre política aparecem, clique no link **Configurar notificações de spam para o usuário final**.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="b6eb7-128">Na caixa de diálogo posterior, você pode configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b6eb7-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="b6eb7-p106">**Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.)</span><span class="sxs-lookup"><span data-stu-id="b6eb7-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="b6eb7-p107">**Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="b6eb7-135">**Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="b6eb7-136">Clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-136">Click **save**.</span></span> <span data-ttu-id="b6eb7-137">Um resumo das configurações de política de filtro de spam, incluindo as configurações de notificação de spam do usuário final, aparece no painel direito.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-137">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b6eb7-138">As notificações de spam do usuário final só serão funcionais para políticas de filtro de spam habilitadas.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-138">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="b6eb7-139">>  As notificações de spam do usuário final só são enviadas uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-139">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="b6eb7-140">O horário de entrega da notificação não pode ser garantido para qualquer cliente específico e não é configurável.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-140">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="b6eb7-141">**Dica:** Se você quiser testar as notificações de spam do usuário final enviando-as a um conjunto limitado de usuários antes de implementá-las totalmente, crie uma política de filtro de spam personalizada que permite as notificações de spam do usuário final para os domínios nos quais os usuários residem.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-141">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="b6eb7-142">Em seguida, no Eat, em **regras de \> fluxo de emails**, crie uma regra de fluxo de emails (também conhecida como regra de transporte) para bloquear mensagens do Quarantine@messaging.microsoft.com (o endereço de email que envia notificações) com exceções para os usuários que você deseja para receber notificações.</span><span class="sxs-lookup"><span data-stu-id="b6eb7-142">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="b6eb7-143">A imagem a seguir é um exemplo de criação de uma exceção de dois usuários (SaraD e AlbertoD) do domínio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b6eb7-143">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regra de transporte para testar notificações de spam do usuário final](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="b6eb7-145">Para saber mais</span><span class="sxs-lookup"><span data-stu-id="b6eb7-145">For more information</span></span>

[<span data-ttu-id="b6eb7-146">Configurar suas políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="b6eb7-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
