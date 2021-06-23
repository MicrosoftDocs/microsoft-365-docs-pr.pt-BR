---
title: Noções básicas do Explorador de Ameaças e detecções em tempo real no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use detecções do Explorer ou em tempo real para investigar e responder a ameaças com eficiência.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083183"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="f90d8-103">Noções básicas de detecções do Explorer e tempo real</span><span class="sxs-lookup"><span data-stu-id="f90d8-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="f90d8-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f90d8-104">**Applies to**</span></span>
- [<span data-ttu-id="f90d8-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f90d8-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f90d8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f90d8-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f90d8-107">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="f90d8-107">In this article:</span></span>

- [<span data-ttu-id="f90d8-108">Diferenças entre detecções do Explorer e em tempo real</span><span class="sxs-lookup"><span data-stu-id="f90d8-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="f90d8-109">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f90d8-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="f90d8-110">Isso faz parte de uma série de 3 artigos no **Explorer (também** conhecido como Explorador de Ameaças), segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="f90d8-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="f90d8-111">Os outros dois artigos desta série são a busca [de ameaças](threat-hunting-in-threat-explorer.md) no Explorer e a segurança de email com o [Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="f90d8-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="f90d8-112">Este artigo explica a diferença entre o explorer e o relatório de detecções em tempo real e as licenças e permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="f90d8-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="f90d8-113">Se sua organização tiver o [Microsoft Defender](defender-for-office-365.md)para Office 365 , e você tiver as permissões [,](#required-licenses-and-permissions)você poderá usar o **Explorer** (também conhecido como **Explorador** de Ameaças ) ou detecções em tempo **real** para detectar e remediar ameaças.</span><span class="sxs-lookup"><span data-stu-id="f90d8-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="f90d8-114">No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), acesse **Email & colaboração** e escolha **Explorer** _ou_ Detecções em tempo **real**.</span><span class="sxs-lookup"><span data-stu-id="f90d8-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="f90d8-115">Com essas ferramentas, você pode:</span><span class="sxs-lookup"><span data-stu-id="f90d8-115">With these tools, you can:</span></span>

- <span data-ttu-id="f90d8-116">Consulte malware detectado por Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="f90d8-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="f90d8-117">Exibir URL de phishing e clicar em dados de veredito.</span><span class="sxs-lookup"><span data-stu-id="f90d8-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="f90d8-118">Inicie um processo automatizado de investigação e resposta a partir de uma exibição no Explorer.</span><span class="sxs-lookup"><span data-stu-id="f90d8-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="f90d8-119">Investigar emails mal-intencionados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f90d8-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="f90d8-120">Para obter mais informações, consulte [Segurança de email com o Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="f90d8-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="f90d8-121">Diferenças entre detecções do Explorer e em tempo real</span><span class="sxs-lookup"><span data-stu-id="f90d8-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="f90d8-122">*Detecções em tempo* real é uma ferramenta de relatório disponível no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="f90d8-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="f90d8-123">*O Explorador* de Ameaças é uma ferramenta de busca e correção de ameaças disponível no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="f90d8-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="f90d8-124">O relatório de detecções em tempo real permite que você veja detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f90d8-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="f90d8-125">O Explorador de Ameaças também faz isso, mas fornece detalhes adicionais para um determinado ataque, como realçamento de campanhas de ataque, e oferece às equipes de operações de segurança a capacidade de correção de ameaças (incluindo a acionamento de uma investigação de Investigação e Resposta Automatizada [).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="f90d8-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="f90d8-126">Uma *exibição de todos* os emails está disponível no Explorador de Ameaças, mas não está incluída no relatório de detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="f90d8-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="f90d8-127">Recursos avançados de filtragem e ações de correção estão incluídos no Explorador de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="f90d8-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="f90d8-128">Para obter mais informações, consulte [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span><span class="sxs-lookup"><span data-stu-id="f90d8-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f90d8-129">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="f90d8-129">Required licenses and permissions</span></span>

<span data-ttu-id="f90d8-130">Você deve ter [o Microsoft Defender para Office 365](defender-for-office-365.md) usar detecções do Explorer ou em tempo real:</span><span class="sxs-lookup"><span data-stu-id="f90d8-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="f90d8-131">O Explorer só está incluído no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="f90d8-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="f90d8-132">O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="f90d8-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="f90d8-133">As equipes de Operações de Segurança precisam atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365 e estar cientes de que as detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="f90d8-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="f90d8-134">Para exibir e usar *detecções do* Explorer ou em tempo real, você precisa das seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="f90d8-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="f90d8-135">No Defender para Office 365:</span><span class="sxs-lookup"><span data-stu-id="f90d8-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="f90d8-136">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="f90d8-136">Organization Management</span></span>
  - <span data-ttu-id="f90d8-137">Administrador de Segurança (isso pode ser atribuído no Azure Active Directory de administração ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="f90d8-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="f90d8-138">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="f90d8-138">Security Reader</span></span>
- <span data-ttu-id="f90d8-139">Em Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f90d8-139">In Exchange Online:</span></span>
  - <span data-ttu-id="f90d8-140">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="f90d8-140">Organization Management</span></span>
  - <span data-ttu-id="f90d8-141">Gerenciamento de Organização Somente Exibição</span><span class="sxs-lookup"><span data-stu-id="f90d8-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="f90d8-142">Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="f90d8-142">View-Only Recipients</span></span>
  - <span data-ttu-id="f90d8-143">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="f90d8-143">Compliance Management</span></span>

<span data-ttu-id="f90d8-144">Para saber mais sobre funções e permissões, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="f90d8-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="f90d8-145">Permissões no portal do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f90d8-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="f90d8-146">Permissões no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f90d8-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="f90d8-147">Mais informações</span><span class="sxs-lookup"><span data-stu-id="f90d8-147">More information</span></span>

- [<span data-ttu-id="f90d8-148">O Explorador de Ameaças coleta detalhes de email na página entidade de email</span><span class="sxs-lookup"><span data-stu-id="f90d8-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="f90d8-149">Localizar e investigar emails mal-intencionados entregues</span><span class="sxs-lookup"><span data-stu-id="f90d8-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="f90d8-150">Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f90d8-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="f90d8-151">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="f90d8-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="f90d8-152">Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f90d8-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
