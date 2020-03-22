---
title: Notificações de spam do usuário final no Office 36
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: Quando um administrador habilita as notificações de spam para o usuário final em políticas antispam, os destinatários da mensagem receberão notificações periódicas sobre suas mensagens em quarentena.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895054"
---
# <a name="end-user-spam-notifications-in-office-365"></a><span data-ttu-id="5c709-103">Notificações de spam do usuário final no Office 365</span><span class="sxs-lookup"><span data-stu-id="5c709-103">End-user spam notifications in Office 365</span></span>

<span data-ttu-id="5c709-104">A quarentena mantém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio do Exchange Online ou de organizações autônomas do Exchange Online Protection (EOP) sem as caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5c709-104">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="5c709-105">Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="5c709-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="5c709-106">Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="5c709-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="5c709-107">Quando um administrador [habilita as notificações de spam para o usuário final](configure-your-spam-filter-policies.md), os destinatários das mensagens receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, emails em massa ou (em abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="5c709-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md), message recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="5c709-108">Em outubro de 2019, removemos a capacidade de liberar mensagens em quarentena diretamente de notificações de spam do usuário final.</span><span class="sxs-lookup"><span data-stu-id="5c709-108">In October 2019, we removed the ability to release quarantined messages directly from end-user spam notifications.</span></span> <span data-ttu-id="5c709-109">Em vez disso, os usuários agora podem ir para o centro de conformidade & segurança do Office 365 para liberar as mensagens em quarentena (seja diretamente ou clicando em **revisar** na notificação).</span><span class="sxs-lookup"><span data-stu-id="5c709-109">Instead, users can now go to the Office 365 Security & Compliance Center to release their quarantined messages (either directly, or by clicking **Review** in the notification).</span></span> <span data-ttu-id="5c709-110">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="5c709-110">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span> <br/><br/> <span data-ttu-id="5c709-111">As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores.</span><span class="sxs-lookup"><span data-stu-id="5c709-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="5c709-112">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="5c709-112">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="5c709-113">Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="5c709-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="5c709-114">**Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="5c709-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="5c709-115">**Assunto**: o texto da linha de assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="5c709-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="5c709-116">**Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="5c709-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="5c709-117">**Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="5c709-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span>

- <span data-ttu-id="5c709-118">**Revisão**: clique neste link para ir para a quarentena no centro de conformidade & segurança, onde você pode liberar, excluir ou relatar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="5c709-118">**Review**: Click this link to go the the Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span>

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
