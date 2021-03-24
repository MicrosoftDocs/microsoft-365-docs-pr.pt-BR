---
title: Mensagens de email em quarentena
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a quarentena no Exchange Online Protection (EOP) que contém mensagens potencialmente perigosas ou indesejadas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054245"
---
# <a name="quarantined-email-messages-in-eop"></a><span data-ttu-id="a845b-103">Mensagens de email em quarentena no EOP</span><span class="sxs-lookup"><span data-stu-id="a845b-103">Quarantined email messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a845b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a845b-104">**Applies to**</span></span>
- [<span data-ttu-id="a845b-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a845b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a845b-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a845b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a845b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a845b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a845b-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena está disponível para manter mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="a845b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine is available to hold potentially dangerous or unwanted messages.</span></span>

<span data-ttu-id="a845b-109">As políticas anti-malware colocarão automaticamente uma mensagem em quarentena se *algum* anexo for encontrado com malware.</span><span class="sxs-lookup"><span data-stu-id="a845b-109">Anti-malware policies automatically quarantine a message if *any* attachment is found to contain malware.</span></span> <span data-ttu-id="a845b-110">Para obter mais informações, consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a845b-110">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>

<span data-ttu-id="a845b-111">Por padrão, a política anti-spam coloca mensagens de phishing em quarentena e entrega mensagens de spam e email em massa para a pasta Lixo Eletrônico do usuário.</span><span class="sxs-lookup"><span data-stu-id="a845b-111">By default, anti-spam polices quarantine phishing messages, and deliver spam and bulk email messages to the user's Junk Email folder.</span></span> <span data-ttu-id="a845b-112">Porém, você também pode criar e personalizar políticas anti-spam para colocar em quarentena mensagens de spam e email em massa.</span><span class="sxs-lookup"><span data-stu-id="a845b-112">But, you can also create and customize anti-spam policies to quarantine spam and bulk-email messages.</span></span> <span data-ttu-id="a845b-113">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a845b-113">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a845b-114">Os usuários e administradores podem trabalhar com mensagens em quarentena:</span><span class="sxs-lookup"><span data-stu-id="a845b-114">Both users and admins can work with quarantined messages:</span></span>

- <span data-ttu-id="a845b-115">Os administradores podem trabalhar com todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="a845b-115">Admins can work with all types of quarantined messages for all users.</span></span> <span data-ttu-id="a845b-116">Somente os administradores podem trabalhar com mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="a845b-116">Only admins can work with messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a845b-117">Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="a845b-117">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="a845b-118">Os usuários podem trabalhar com mensagens em quarentena em que são destinatários se a mensagem foi colocada em quarentena como spam, email em massa ou phishing (a partir de abril de 2020).</span><span class="sxs-lookup"><span data-stu-id="a845b-118">Users can work with quarantined messages where they are a recipient if the message was quarantined as spam, bulk email, or (as of April 2020) phishing.</span></span> <span data-ttu-id="a845b-119">Para obter mais informações, [consulte Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a845b-119">For more information, see [Find and release quarantined messages as a user in EOP](find-and-release-quarantined-messages-as-a-user.md).</span></span>

  <span data-ttu-id="a845b-120">Para impedir que os usuários gere o gerenciamento de suas próprias mensagens de phishing em quarentena, os administradores podem configurar uma ação diferente para o veredito de filtragem de email de **phishing** em políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="a845b-120">To prevent users from managing their own quarantined phishing messages, admins can configure a different action for the **Phishing email** filtering verdict in anti-spam policies.</span></span> <span data-ttu-id="a845b-121">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a845b-121">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="a845b-122">Os administradores e usuários podem relatar falsos positivos à Microsoft em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a845b-122">Admins and users can report false positives to Microsoft in quarantine.</span></span>

<span data-ttu-id="a845b-123">Para obter mais informações sobre a quarentena, consulte [Perguntas frequentes sobre quarentena.](quarantine-faq.md)</span><span class="sxs-lookup"><span data-stu-id="a845b-123">For more information about, quarantine, see [Quarantine FAQ](quarantine-faq.md).</span></span>
