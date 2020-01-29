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
ms.openlocfilehash: fbe8a09f7da5df2df4b3b68bd524fa3ef2ed18b8
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572657"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="c2fbf-104">Usar notificações de spam do usuário para liberar e reportar mensagens em quarentena no Office 365spam</span><span class="sxs-lookup"><span data-stu-id="c2fbf-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="c2fbf-105">Se seu administrador habilitar notificações de spam para usuários, você receberá uma mensagem de notificação que lista as mensagens endereçadas à sua caixa de correio que foram identificadas como spam e colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>

> [!TIP]
> <span data-ttu-id="c2fbf-106">Se você é um administrador e deseja habilitar esse recurso, você pode escolher a opção ao [modificar uma política antispam padrão](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c2fbf-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c2fbf-107">A mensagem recebida inclui o número de mensagens de spam em quarentena que você tem e a data e a hora (no UTC ou horário coordenado universal) da última mensagem na lista.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="c2fbf-108">A lista inclui o seguinte para cada mensagem:</span><span class="sxs-lookup"><span data-stu-id="c2fbf-108">The list includes the following for each message:</span></span>

- <span data-ttu-id="c2fbf-109">**Remetente** O nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-109">**Sender** The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="c2fbf-110">**Assunto** O texto da linha do assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-110">**Subject** The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="c2fbf-111">**Data** A data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span>

<span data-ttu-id="c2fbf-112">Estas são as ações que você pode realizar com uma mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="c2fbf-112">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="c2fbf-113">**Bloquear remetente** se quiser que o Office 365 adicione o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-113">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

- <span data-ttu-id="c2fbf-114">**Versão** se a mensagem não for spam e se você quiser que o Office 365 envie a mensagem para sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-114">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="c2fbf-115">**Revise** para navegar até o portal de quarentena no centro de segurança e conformidade se você quiser realizar outras ações, como visualizar ou liberar.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-115">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>

<span data-ttu-id="c2fbf-116">Esteja ciente do seguinte:</span><span class="sxs-lookup"><span data-stu-id="c2fbf-116">Be aware of the following:</span></span>

- <span data-ttu-id="c2fbf-117">As mensagens colocadas em quarentena porque corresponderam a uma regra de fluxo de emails não estão incluídas nas mensagens em quarentena do usuário.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-117">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="c2fbf-118">Somente as mensagens em quarentena por spam estão listadas.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-118">Only spam-quarantined messages are listed.</span></span>

- <span data-ttu-id="c2fbf-119">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="c2fbf-119">You can only release a message and report it as a false positive (not junk) once.</span></span>
