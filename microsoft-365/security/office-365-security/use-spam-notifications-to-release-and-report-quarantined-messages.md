---
title: Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena
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
ms.openlocfilehash: 641efc024a2842f30f7754c52f624a9f668851de
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636411"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="6157e-103">Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="6157e-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="6157e-104">A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) independentes sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6157e-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="6157e-105">Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="6157e-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="6157e-106">Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="6157e-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="6157e-107">Quando um administrador [habilita notificações de spam para o usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), os destinatários receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (em abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="6157e-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span>

> [!NOTE]
> <span data-ttu-id="6157e-108">As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores.</span><span class="sxs-lookup"><span data-stu-id="6157e-108">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="6157e-109">Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="6157e-109">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="6157e-110">Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="6157e-110">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="6157e-111">**Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6157e-111">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="6157e-112">**Assunto**: o texto da linha de assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6157e-112">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="6157e-113">**Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6157e-113">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="6157e-114">**Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="6157e-114">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="6157e-115">Para obter mais informações, consulte [bloquear um remetente de email no Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="6157e-115">For more information, see [Block a mail sender in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="6157e-116">**Release**: para mensagens de spam (não Phish), você pode liberar a mensagem aqui sem ir para a quarentena do centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="6157e-116">**Release**: For spam (not phish) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="6157e-117">**Revisão**: clique neste link para ir para quarentena no centro de conformidade & segurança, onde você pode liberar, excluir ou relatar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6157e-117">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can release, delete or report your quarantined messages.</span></span> <span data-ttu-id="6157e-118">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6157e-118">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
