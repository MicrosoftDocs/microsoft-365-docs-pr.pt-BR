---
title: Colocar mensagens de email em quarentena no Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: A quarentena no Office 365 contém mensagens potencialmente perigosas ou indesejadas. Administradores e usuários finais podem acessar a quarentena.
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857304"
---
# <a name="quarantine-in-office-365"></a><span data-ttu-id="fd4a7-104">Quarentena no Office 365</span><span class="sxs-lookup"><span data-stu-id="fd4a7-104">Quarantine in Office 365</span></span>

<span data-ttu-id="fd4a7-105">Se você for um cliente do Office 365 com caixas de correio no Exchange Online ou um cliente autônomo do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena estará disponível para armazenar mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-105">If you're an Office 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="fd4a7-106">As políticas Antimalware automaticamente colocarão uma mensagem em quarentena se *qualquer* anexo tiver malware.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-106">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="fd4a7-107">Para obter mais informações, consulte [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-107">For more information, see [Configure anti-malware policies in Office 365](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="fd4a7-108">Por padrão, o anti-spam policia as mensagens de phishing e entrega mensagens de email em massa e spam para a pasta lixo eletrônico do usuário.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-108">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="fd4a7-109">No entanto, você também pode criar e personalizar políticas antispam para colocar em quarentena spam e mensagens de email em massa.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-109">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="fd4a7-110">Para obter mais informações, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-110">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="fd4a7-111">Tanto usuários quanto administradores podem trabalhar com mensagens em quarentena:</span><span class="sxs-lookup"><span data-stu-id="fd4a7-111">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="fd4a7-112">Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-112">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="fd4a7-113">Somente os administradores podem trabalhar com mensagens colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-113">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="fd4a7-114">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-114">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="fd4a7-115">Os usuários podem trabalhar com mensagens em quarentena onde eles são um destinatário se a mensagem foi colocada em quarentena como spam, email em massa ou (a partir de abril de 2020).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-115">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="fd4a7-116">Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-116">For more information, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="fd4a7-117">Para impedir que os usuários gerenciem suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para a veredicto de filtragem de **email de phishing** em políticas antispam.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-117">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="fd4a7-118">Para obter mais informações, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-118">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="fd4a7-119">Administradores e usuários podem relatar falsos positivos para a Microsoft em quarentena.</span><span class="sxs-lookup"><span data-stu-id="fd4a7-119">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="fd4a7-120">Para obter mais informações sobre, quarentena, consulte [perguntas frequentes sobre quarentena](quarantine-faq.md).</span><span class="sxs-lookup"><span data-stu-id="fd4a7-120">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
