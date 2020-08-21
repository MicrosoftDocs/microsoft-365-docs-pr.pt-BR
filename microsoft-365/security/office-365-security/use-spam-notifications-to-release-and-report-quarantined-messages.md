---
title: Notificações de spam do usuário final no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827356"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="df4f3-103">Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="df4f3-103">Use user spam notifications to release and report quarantined messages</span></span>

<span data-ttu-id="df4f3-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="df4f3-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="df4f3-105">Para obter mais informações, consulte [mensagens em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="df4f3-105">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="df4f3-106">Por padrão, as notificações de spam do usuário final estão desabilitadas em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="df4f3-106">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="df4f3-107">Quando um administrador [habilita as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), os destinatários (incluindo caixas de correio compartilhadas com mapeamento automático habilitado) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou (em abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="df4f3-107">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="df4f3-108">Para caixas de correio compartilhadas, as notificações de spam do usuário final só são suportadas para usuários que receberam permissão FullAccess para a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="df4f3-108">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="df4f3-109">Para obter mais informações, consulte [use o Eat para editar a delegação de caixa de correio compartilhada](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span><span class="sxs-lookup"><span data-stu-id="df4f3-109">For more information, see [Use the EAC to edit shared mailbox delegation](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="df4f3-110">A notificação de spam do usuário final não é suportada para grupos.</span><span class="sxs-lookup"><span data-stu-id="df4f3-110">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="df4f3-111">As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) só estão disponíveis para administradores.</span><span class="sxs-lookup"><span data-stu-id="df4f3-111">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="df4f3-112">Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="df4f3-112">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="df4f3-113">Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="df4f3-113">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="df4f3-114">**Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="df4f3-114">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="df4f3-115">**Assunto**: o texto da linha de assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="df4f3-115">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="df4f3-116">**Date**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="df4f3-116">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="df4f3-117">**Remetente do bloco**: clique neste link para adicionar o remetente à sua lista de remetentes bloqueados.</span><span class="sxs-lookup"><span data-stu-id="df4f3-117">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="df4f3-118">Para obter mais informações, consulte [bloquear um remetente de email](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="df4f3-118">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="df4f3-119">**Release**: para mensagens de spam (não phishing), você pode liberar a mensagem aqui sem entrar em quarentena no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="df4f3-119">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="df4f3-120">**Revisão**: clique neste link para ir para quarentena no centro de conformidade do & de segurança, onde você pode (dependendo de por que a mensagem foi colocada em quarentena) exibir, liberar, excluir ou relatar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="df4f3-120">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="df4f3-121">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="df4f3-121">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)
