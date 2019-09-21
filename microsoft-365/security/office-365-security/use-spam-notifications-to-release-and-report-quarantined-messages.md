---
title: Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: Se seu administrador habilitar as notificações para usuários, você receberá uma mensagem de notificação que lista as mensagens enviadas para sua caixa de correio que foram identificadas como spam, massa ou mensagens de phishing. Você pode liberar ou relatar mensagens depois de ser notificado.
ms.openlocfilehash: 499af3ae2934eed19e421918af07a45b72fe2518
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073333"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="09ade-104">Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam</span><span class="sxs-lookup"><span data-stu-id="09ade-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="09ade-105">Se seu administrador habilitar notificações de spam para usuários, você receberá uma mensagem de notificação que lista as mensagens endereçadas à sua caixa de correio que foram identificadas como spam e colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="09ade-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="09ade-106">Se você é um administrador e deseja habilitar esse recurso, você pode escolher a opção ao [modificar uma política antispam padrão](https://go.microsoft.com/fwlink/?LinkId=800313).</span><span class="sxs-lookup"><span data-stu-id="09ade-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="09ade-107">A mensagem recebida inclui o número de mensagens de spam em quarentena que você tem e a data e a hora (no UTC ou horário coordenado universal) da última mensagem na lista.</span><span class="sxs-lookup"><span data-stu-id="09ade-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="09ade-108">A lista inclui o seguinte para cada mensagem:</span><span class="sxs-lookup"><span data-stu-id="09ade-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="09ade-109">**Remetente** O nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="09ade-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="09ade-110">**Assunto** O texto da linha do assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="09ade-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="09ade-111">**Data** A data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="09ade-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="09ade-112">**Tamanho** O tamanho da mensagem, em kilobytes (KBs).</span><span class="sxs-lookup"><span data-stu-id="09ade-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="09ade-113">Estas são as ações que você pode realizar com uma mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="09ade-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="09ade-114">**Visualize** a mensagem se quiser visualizar o conteúdo ou o cabeçalho antes de executar a ação.</span><span class="sxs-lookup"><span data-stu-id="09ade-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="09ade-115">**Baixe** a mensagem se quiser revisar a mensagem e os anexos (se houver) no dispositivo antes de executar a ação.</span><span class="sxs-lookup"><span data-stu-id="09ade-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="09ade-116">**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="09ade-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="09ade-117">**Versão & permitir remetente** se a mensagem não for spam e se você quiser que o Office 365 adicione o remetente à sua lista de remetentes e destinatários confiáveis para futuros emails.</span><span class="sxs-lookup"><span data-stu-id="09ade-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="09ade-118">Tenha em mente que seu administrador pode ter outras configurações de permissão/bloqueio de toda a organização que substituem sua lista de remetentes seguros.</span><span class="sxs-lookup"><span data-stu-id="09ade-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="09ade-119">**Release & Report**, se a mensagem não for spam e você quiser enviar a mensagem para sua caixa de correio e relatá-la para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="09ade-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="09ade-120">**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="09ade-120">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="09ade-121">Esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="09ade-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="09ade-122">As mensagens colocadas em quarentena porque corresponderam a uma regra de fluxo de emails não estão incluídas nas mensagens em quarentena do usuário.</span><span class="sxs-lookup"><span data-stu-id="09ade-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="09ade-123">Somente as mensagens em quarentena por spam estão listadas.</span><span class="sxs-lookup"><span data-stu-id="09ade-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="09ade-124">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="09ade-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

