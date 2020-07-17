---
title: Notificações de spam do usuário final no Microsoft 365
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre as notificações de spam do usuário final para mensagens em quarentena na proteção do Exchange Online (EOP).
ms.openlocfilehash: 14dcdfa8373e3826b23bc5574d1b5ae8ff76927b
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754779"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="97ea3-103">Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="97ea3-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="97ea3-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="97ea3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="97ea3-105">Para obter mais informações, consulte [mensagens em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="97ea3-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="97ea3-106">Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="97ea3-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="97ea3-107">Quando um administrador [habilita as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), os destinatários (incluindo caixas de correio compartilhadas) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="97ea3-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="97ea3-108">As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores.</span><span class="sxs-lookup"><span data-stu-id="97ea3-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="97ea3-109">Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="97ea3-109">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="97ea3-110">Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="97ea3-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="97ea3-111">**Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="97ea3-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="97ea3-112">**Assunto**: o texto da linha de assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="97ea3-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="97ea3-113">**Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="97ea3-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="97ea3-114">**Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="97ea3-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="97ea3-115">Para obter mais informações, consulte [bloquear um remetente de email](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="97ea3-115">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="97ea3-116">**Release**: para mensagens de spam (não Phish), você pode liberar a mensagem aqui sem ir para a quarentena do centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="97ea3-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="97ea3-117">**Revisão**: clique neste link para ir para quarentena no centro de conformidade & segurança, onde você pode liberar, excluir ou relatar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="97ea3-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="97ea3-118">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="97ea3-118">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
