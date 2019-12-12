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
ms.openlocfilehash: 4cf592f0aec948c3c8f6383cf288fb32ac644cd6
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971359"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="d11f4-104">Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam</span><span class="sxs-lookup"><span data-stu-id="d11f4-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="d11f4-105">Se seu administrador habilitar notificações de spam para usuários, você receberá uma mensagem de notificação que lista as mensagens endereçadas à sua caixa de correio que foram identificadas como spam e colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d11f4-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="d11f4-106">Se você é um administrador e deseja habilitar esse recurso, você pode escolher a opção ao [modificar uma política antispam padrão](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d11f4-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="d11f4-107">A mensagem recebida inclui o número de mensagens de spam em quarentena que você tem e a data e a hora (no UTC ou horário coordenado universal) da última mensagem na lista.</span><span class="sxs-lookup"><span data-stu-id="d11f4-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="d11f4-108">A lista inclui o seguinte para cada mensagem:</span><span class="sxs-lookup"><span data-stu-id="d11f4-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="d11f4-109">**Remetente** O nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d11f4-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="d11f4-110">**Assunto** O texto da linha do assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d11f4-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="d11f4-111">**Data** A data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="d11f4-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="d11f4-112">Estas são as ações que você pode realizar com uma mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="d11f4-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="d11f4-113">**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="d11f4-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="d11f4-114">**Revise** para navegar até o portal de quarentena no centro de segurança e conformidade se você quiser realizar outras ações, como visualizar ou liberar.</span><span class="sxs-lookup"><span data-stu-id="d11f4-114">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="d11f4-115">Esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="d11f4-115">Be aware of the following:</span></span>

- <span data-ttu-id="d11f4-116">As mensagens colocadas em quarentena porque corresponderam a uma regra de fluxo de emails não estão incluídas nas mensagens em quarentena do usuário.</span><span class="sxs-lookup"><span data-stu-id="d11f4-116">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="d11f4-117">Somente as mensagens em quarentena por spam estão listadas.</span><span class="sxs-lookup"><span data-stu-id="d11f4-117">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="d11f4-118">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="d11f4-118">You can only release a message and report it as a false positive (not junk) once.</span></span>
