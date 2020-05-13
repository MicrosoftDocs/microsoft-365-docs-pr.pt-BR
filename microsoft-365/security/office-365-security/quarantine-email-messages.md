---
title: Mensagens de email em quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre a quarentena na proteção do Exchange Online (EOP) que mantém mensagens potencialmente perigosas ou indesejadas.
ms.openlocfilehash: 71a5f32fe6888d751bf2c4020fca4df671ac96d1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208277"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="bf444-103">Mensagens de email em quarentena no EOP</span><span class="sxs-lookup"><span data-stu-id="bf444-103">Quarantined email messages in EOP</span></span>

<span data-ttu-id="bf444-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena está disponível para reter mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="bf444-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="bf444-105">As políticas Antimalware automaticamente colocarão uma mensagem em quarentena se *qualquer* anexo tiver malware.</span><span class="sxs-lookup"><span data-stu-id="bf444-105">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="bf444-106">Para obter mais informações, consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-106">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="bf444-107">Por padrão, o anti-spam policia as mensagens de phishing e entrega mensagens de email em massa e spam para a pasta lixo eletrônico do usuário.</span><span class="sxs-lookup"><span data-stu-id="bf444-107">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="bf444-108">No entanto, você também pode criar e personalizar políticas antispam para colocar em quarentena spam e mensagens de email em massa.</span><span class="sxs-lookup"><span data-stu-id="bf444-108">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="bf444-109">Para obter mais informações, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bf444-110">Tanto usuários quanto administradores podem trabalhar com mensagens em quarentena:</span><span class="sxs-lookup"><span data-stu-id="bf444-110">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="bf444-111">Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="bf444-111">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="bf444-112">Somente os administradores podem trabalhar com mensagens colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="bf444-112">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="bf444-113">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-113">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="bf444-114">Os usuários podem trabalhar com mensagens em quarentena onde eles são um destinatário se a mensagem foi colocada em quarentena como spam, email em massa ou (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="bf444-114">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="bf444-115">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-115">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="bf444-116">Para impedir que os usuários gerenciem suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para a veredicto de filtragem de **email de phishing** em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="bf444-116">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="bf444-117">Para obter mais informações, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-117">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="bf444-118">Administradores e usuários podem relatar falsos positivos para a Microsoft em quarentena.</span><span class="sxs-lookup"><span data-stu-id="bf444-118">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="bf444-119">Para obter mais informações sobre, quarentena, consulte [perguntas frequentes sobre quarentena](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="bf444-119">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
