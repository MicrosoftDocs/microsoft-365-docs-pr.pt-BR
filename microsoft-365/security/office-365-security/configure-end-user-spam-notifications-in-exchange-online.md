---
title: Configurar notificações de spam para o usuário final no Exchange Online
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341293"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="388bb-103">Configurar notificações de spam para o usuário final no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="388bb-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="388bb-104">Este tópico é para os clientes do Exchange Online que estão protegendo caixas de correio hospedadas em nuvem.</span><span class="sxs-lookup"><span data-stu-id="388bb-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="388bb-105">Os clientes autônomos do Exchange Online Protection (EOP) que estão protegendo caixas de correio locais devem ler o seguinte tópico em vez disso: [configurar notificações de spam para o usuário final no EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="388bb-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="388bb-106">Você pode configurar as notificações de spam para o usuário final para a política de filtro de spam padrão para toda a empresa ou para políticas personalizadas de filtro de spam.</span><span class="sxs-lookup"><span data-stu-id="388bb-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="388bb-107">Habilitar mensagens de notificação de spam do usuário final permite que os usuários gerenciem suas próprias mensagens de spam, de massa e de phishing em quarentena.</span><span class="sxs-lookup"><span data-stu-id="388bb-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="388bb-p103">As notificações de spam do usuário final contém uma lista de todas as mensagens de spam em quarentena que o usuário final recebeu durante um período de tempo que você configurou (você pode especificar um valor entre 1 e 15 dias). Você também pode configurar o idioma no qual a mensagem de notificação será escrita.</span><span class="sxs-lookup"><span data-stu-id="388bb-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="388bb-110">Após receber uma mensagem de notificação, os usuários finais podem escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="388bb-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="388bb-111">**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="388bb-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="388bb-112">**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="388bb-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="388bb-113">**Revise** para navegar até o portal de quarentena dentro do centro de conformidade de & de segurança se você quiser realizar outras ações, como visualização ou lançamento.</span><span class="sxs-lookup"><span data-stu-id="388bb-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="388bb-114">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="388bb-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="388bb-115">Tempo estimado para conclusão: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="388bb-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="388bb-116">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="388bb-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="388bb-117">Para ver de que permissões você precisa, consulte o entrada "anti-spam" no tópico [permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) .</span><span class="sxs-lookup"><span data-stu-id="388bb-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="388bb-118">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="388bb-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="388bb-119">Use o EAC para configurar as notificações de spam do usuário final</span><span class="sxs-lookup"><span data-stu-id="388bb-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="388bb-120">No Centro de Administração do Exchange (EAC), navegue até **Proteção** \> **Filtro de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="388bb-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="388bb-121">Selecione a política de filtro de spam para a qual você deseja habilitar as notificações de spam do usuário final (elas estão desabilitadas por padrão).</span><span class="sxs-lookup"><span data-stu-id="388bb-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="388bb-122">No painel direito, onde as informações resumidas sobre política aparecem, clique no link **Configurar notificações de spam para o usuário final**.</span><span class="sxs-lookup"><span data-stu-id="388bb-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="388bb-123">Na caixa de diálogo posterior, você pode configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="388bb-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="388bb-p105">**Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.)</span><span class="sxs-lookup"><span data-stu-id="388bb-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="388bb-p106">**Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="388bb-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="388bb-130">**Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="388bb-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="388bb-131">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="388bb-131">Click **Save**.</span></span> <span data-ttu-id="388bb-132">Um resumo das configurações de política de filtro de spam, incluindo as configurações de notificação de spam do usuário final, aparece no painel direito.</span><span class="sxs-lookup"><span data-stu-id="388bb-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="388bb-133">As notificações de spam do usuário final só serão funcionais para políticas de filtro de spam habilitadas.</span><span class="sxs-lookup"><span data-stu-id="388bb-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="388bb-134">>  As notificações de spam do usuário final só são enviadas uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="388bb-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="388bb-135">O horário de entrega da notificação não pode ser garantido para qualquer cliente específico e não é configurável.</span><span class="sxs-lookup"><span data-stu-id="388bb-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="388bb-136">**Dica:** Se você quiser testar as notificações de spam do usuário final enviando-as a um conjunto limitado de usuários antes de implementá-las totalmente, crie uma política de filtro de spam personalizada que permite as notificações de spam do usuário final para os domínios nos quais os usuários residem.</span><span class="sxs-lookup"><span data-stu-id="388bb-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="388bb-137">Em seguida, no Eat, em **regras de \> fluxo de emails**, crie uma regra de fluxo de emails (também conhecida como regra de transporte) para bloquear mensagens de Quarantine@messaging.microsoft.com (o endereço de email que envia notificações) com exceções para os usuários que você deseja receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="388bb-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="388bb-138">A imagem a seguir é um exemplo de criação de uma exceção de dois usuários (SaraD e AlbertoD) do domínio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="388bb-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regra de transporte para testar notificações de spam do usuário final](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="388bb-140">Usar o SCC para configurar notificações de spam para o usuário final</span><span class="sxs-lookup"><span data-stu-id="388bb-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="388bb-141">Você também pode usar o centro de conformidade e segurança (SCC) para configurar as notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="388bb-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="388bb-142">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="388bb-142">Follow these steps:</span></span>

1. <span data-ttu-id="388bb-143">Abra o centro de segurança e conformidade, navegue até **anti-spam** da **política** \> de **Gerenciamento** \> de ameaças ou https://protection.office.com/antispamuse o link direto.</span><span class="sxs-lookup"><span data-stu-id="388bb-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="388bb-144">Clique na seta para baixo ao lado da política de filtro de spam para a qual você deseja habilitar as notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="388bb-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="388bb-145">Clique no link **configurar notificações de spam para o usuário final** .</span><span class="sxs-lookup"><span data-stu-id="388bb-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="388bb-146">Na caixa de diálogo posterior, você pode configurar as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="388bb-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="388bb-p111">**Habilitar notificações de spam para o usuário final** Marque esta caixa de seleção para habilitar notificações de spam para o usuário final para esta política. (De outra forma, se esta política estiver habilitada, você pode desmarcar esta caixa de seleção para desabilitar as notificações de spam para usuário final para esta política.)</span><span class="sxs-lookup"><span data-stu-id="388bb-p111">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="388bb-p112">**Envie notificações de spam para o usuário final a cada (dias)** Especifique a frequência com a qual as notificações de spam para o usuário final são enviadas. O padrão é 3 dias. Você pode especificar entre 1 e 15 dias. Se você especificar 7 dias, por exemplo, a notificação incluirá uma lista de todas as mensagens para aquele usuários dos últimos 7 dias que foram enviadas para a quarentena de spam.</span><span class="sxs-lookup"><span data-stu-id="388bb-p112">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="388bb-153">**Idioma da notificação** Usando a lista suspensa, escolha o idioma de escrita das notificações de spam para o usuário final para esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="388bb-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="388bb-154">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="388bb-154">Click **Save**.</span></span> <span data-ttu-id="388bb-155">Um resumo das configurações de política de filtro de spam, incluindo as configurações de notificação de spam do usuário final, aparece no painel.</span><span class="sxs-lookup"><span data-stu-id="388bb-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="388bb-156">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="388bb-156">For more information</span></span>

[<span data-ttu-id="388bb-157">Configurar suas políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="388bb-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="388bb-158">Set-HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="388bb-158">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
