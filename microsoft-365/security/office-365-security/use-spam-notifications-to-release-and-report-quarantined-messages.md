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
description: Os administradores podem aprender sobre notificações de spam do usuário final para mensagens em quarentena no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203114"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a><span data-ttu-id="dff76-103">Usar notificações de spam do usuário para liberar e relatar mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="dff76-103">Use user spam notifications to release and report quarantined messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="dff76-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="dff76-104">**Applies to**</span></span>
- [<span data-ttu-id="dff76-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dff76-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="dff76-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="dff76-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="dff76-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dff76-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="dff76-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="dff76-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="dff76-109">Para obter mais informações, consulte [Mensagens em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="dff76-109">For more information, see [Quarantined messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="dff76-110">Por padrão, as notificações de spam do usuário final são desabilitadas em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="dff76-110">By default, end-user spam notifications are disabled in anti-spam policies.</span></span> <span data-ttu-id="dff76-111">Quando um administrador habilita notificações de spam do usuário final, os [destinatários](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)(incluindo caixas de correio compartilhadas com automação habilitada) receberão notificações periódicas sobre suas mensagens que foram colocadas em quarentena como spam, email em massa ou phishing (a partir de abril de 2020).</span><span class="sxs-lookup"><span data-stu-id="dff76-111">When an admin [enables end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications), recipients (including shared mailboxes with automapping enabled) will receive periodic notifications about their messages that were quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span>

<span data-ttu-id="dff76-112">Para caixas de correio compartilhadas, as notificações de spam do usuário final só são suportadas para usuários que têm permissão FullAccess para a caixa de correio compartilhada.</span><span class="sxs-lookup"><span data-stu-id="dff76-112">For shared mailboxes, end-user spam notifications are only supported for users who are granted FullAccess permission to the shared mailbox.</span></span> <span data-ttu-id="dff76-113">Para obter mais informações, [consulte Usar o EAC para editar a delegação de caixa de correio compartilhada.](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)</span><span class="sxs-lookup"><span data-stu-id="dff76-113">For more information, see [Use the EAC to edit shared mailbox delegation](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).</span></span>

<span data-ttu-id="dff76-114">A notificação de Spam do Usuário Final não é suportada para grupos.</span><span class="sxs-lookup"><span data-stu-id="dff76-114">End User Spam notification is not supported for groups.</span></span>

> [!NOTE]
> <span data-ttu-id="dff76-115">As mensagens que foram colocadas em quarentena como phishing de alta confiança, malware ou por regras de fluxo de emails (também conhecidas como regras de transporte) estão disponíveis apenas para administradores.</span><span class="sxs-lookup"><span data-stu-id="dff76-115">Messages that were quarantined as high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="dff76-116">Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="dff76-116">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

<span data-ttu-id="dff76-117">Uma notificação de spam do usuário final contém as seguintes informações para cada mensagem em quarentena:</span><span class="sxs-lookup"><span data-stu-id="dff76-117">An end-user spam notification contains the following information for each quarantined message:</span></span>

- <span data-ttu-id="dff76-118">**Remetente**: o nome de envio e o endereço de email da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="dff76-118">**Sender**: The send name and email address of the quarantined message.</span></span>

- <span data-ttu-id="dff76-119">**Assunto**: O texto da linha de assunto da mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="dff76-119">**Subject**: The subject line text of the quarantined message.</span></span>

- <span data-ttu-id="dff76-120">**Data**: a data e a hora (em UTC) em que a mensagem foi colocada em quarentena.</span><span class="sxs-lookup"><span data-stu-id="dff76-120">**Date**: The date and time (in UTC) that the message was quarantined.</span></span>

- <span data-ttu-id="dff76-121">**Bloquear Remetente**: clique neste link para adicionar o remetente à sua lista de Remetentes Bloqueados.</span><span class="sxs-lookup"><span data-stu-id="dff76-121">**Block Sender**: Click this link to add the sender to your Blocked Senders list.</span></span> <span data-ttu-id="dff76-122">Para obter mais informações, consulte [Bloquear um remetente de email](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="dff76-122">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="dff76-123">**Versão**: para mensagens de spam (não phishing), você pode liberar a mensagem aqui sem ir para Quarentena do Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="dff76-123">**Release**: For spam (not phishing) messages, you can release the message here without going to Quarantine the Security & Compliance Center.</span></span>

- <span data-ttu-id="dff76-124">**Revisão**: clique neste link para ir para Quarentena no Centro de Conformidade de Segurança &, onde você pode (dependendo do motivo pelo qual a mensagem foi colocada em quarentena), liberar, excluir ou relatar suas mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="dff76-124">**Review**: Click this link to go to Quarantine in the Security & Compliance Center, where you can (depending on why the message was quarantined) view, release, delete or report your quarantined messages.</span></span> <span data-ttu-id="dff76-125">Para obter mais informações, [consulte Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="dff76-125">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

![Exemplo de notificação de spam do usuário final](../../media/end-user-spam-notification.png)

> [!NOTE]
> <span data-ttu-id="dff76-127">Um remetente bloqueado ainda pode enviar emails.</span><span class="sxs-lookup"><span data-stu-id="dff76-127">A blocked sender can still send you mail.</span></span> <span data-ttu-id="dff76-128">Todas as mensagens desse remetente que o fizerem para sua caixa de correio serão movidas imediatamente para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="dff76-128">Any messages from this sender that make it to your mailbox will be immediately moved to the Junk Email folder.</span></span> <span data-ttu-id="dff76-129">Mensagens futuras desse remetente irão para sua pasta Lixo Eletrônico ou para a quarentena do usuário final.</span><span class="sxs-lookup"><span data-stu-id="dff76-129">Future messages from this sender will go to your Junk Email folder or to the end-user quarantine.</span></span> <span data-ttu-id="dff76-130">Se você quiser excluir essas mensagens na chegada, em vez de quarantir-las, [use](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) As Regras de fluxo de emails (também conhecidas como regras de transporte) para excluir as mensagens na chegada.</span><span class="sxs-lookup"><span data-stu-id="dff76-130">If you would like to delete these messages on arrival instead of quarantining them, use [mail flow Rules](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (also known as transport rules) to delete the messages on arrival.</span></span>