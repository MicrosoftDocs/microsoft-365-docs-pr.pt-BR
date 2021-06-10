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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300092"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="adbd2-103">Noções básicas sobre o Explorador de Ameaças e detecção em tempo real</span><span class="sxs-lookup"><span data-stu-id="adbd2-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="adbd2-104">Neste artigo:</span><span class="sxs-lookup"><span data-stu-id="adbd2-104">In this article:</span></span>

- [<span data-ttu-id="adbd2-105">Diferenças entre o Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="adbd2-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="adbd2-106">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="adbd2-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="adbd2-107">Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las). </span><span class="sxs-lookup"><span data-stu-id="adbd2-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="adbd2-108">Os outros dois artigos desta série são Busca de ameaças no [Explorador de Ameaças](threat-hunting-in-threat-explorer.md) e Segurança de Email com o Explorador de [Ameaças.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="adbd2-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="adbd2-109">Este artigo explica a diferença entre a exploração de ameaças e o relatório de detecções em tempo real e as licenças e permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="adbd2-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="adbd2-110">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="adbd2-110">**Applies to**</span></span>
- [<span data-ttu-id="adbd2-111">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="adbd2-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="adbd2-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adbd2-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="adbd2-113">Se sua organização tiver o [Microsoft Defender](defender-for-office-365.md)para Office 365 , e você tiver as permissões [,](#required-licenses-and-permissions)você poderá usar o **Explorador** de Ameaças (chamado Explorer **)** ou detecções em tempo **real** para detectar e remediar ameaças.</span><span class="sxs-lookup"><span data-stu-id="adbd2-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="adbd2-114">No Centro **de Conformidade & segurança,** vá para Gerenciamento de ameaças **e** escolha **Explorer** _ou_ Detecções em tempo **real.**</span><span class="sxs-lookup"><span data-stu-id="adbd2-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="adbd2-115">Com o Microsoft Defender para Office 365 Plano 2, você verá:</span><span class="sxs-lookup"><span data-stu-id="adbd2-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="adbd2-116">Com o Microsoft Defender para Office 365 Plano 1, consulte:</span><span class="sxs-lookup"><span data-stu-id="adbd2-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Explorador de ameaças](../../media/threatmgmt-explorer.png)|![Detecções em tempo real](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="adbd2-119">Com essas ferramentas, você pode:</span><span class="sxs-lookup"><span data-stu-id="adbd2-119">With these tools, you can:</span></span>

- <span data-ttu-id="adbd2-120">Consulte malware detectado por Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="adbd2-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="adbd2-121">Exibir URL de phishing e clicar em dados de veredito.</span><span class="sxs-lookup"><span data-stu-id="adbd2-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="adbd2-122">Inicie um processo automatizado de investigação e resposta a partir de uma exibição no Explorer.</span><span class="sxs-lookup"><span data-stu-id="adbd2-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="adbd2-123">Investigar emails mal-intencionados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="adbd2-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="adbd2-124">Para obter mais informações, consulte [Segurança de email com o Explorador de Ameaças.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="adbd2-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="adbd2-125">Diferenças entre o Explorador de Ameaças e detecções em tempo real</span><span class="sxs-lookup"><span data-stu-id="adbd2-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="adbd2-126">*Detecções em tempo* real é uma ferramenta de relatório disponível no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="adbd2-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="adbd2-127">*O Explorador* de Ameaças é uma ferramenta de busca e correção de ameaças disponível no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="adbd2-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="adbd2-128">O relatório de detecções em tempo real permite que você veja detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="adbd2-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="adbd2-129">O Explorador de Ameaças também faz isso, mas fornece detalhes adicionais para um determinado ataque, como realçamento de campanhas de ataque, e oferece às equipes de operações de segurança a capacidade de correção de ameaças (incluindo a acionamento de uma investigação de Investigação e Resposta Automatizada [).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="adbd2-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="adbd2-130">Uma *exibição de todos* os emails está disponível no Explorador de Ameaças, mas não está incluída no relatório de detecções em tempo real.</span><span class="sxs-lookup"><span data-stu-id="adbd2-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="adbd2-131">Recursos avançados de filtragem e ações de correção estão incluídos no Explorador de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="adbd2-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="adbd2-132">Para obter mais informações, consulte [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span><span class="sxs-lookup"><span data-stu-id="adbd2-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="adbd2-133">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="adbd2-133">Required licenses and permissions</span></span>

<span data-ttu-id="adbd2-134">Você deve ter [o Microsoft Defender para Office 365](defender-for-office-365.md) usar detecções do Explorer ou em tempo real:</span><span class="sxs-lookup"><span data-stu-id="adbd2-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="adbd2-135">Mas o Explorer só está incluído no Defender para Office 365 Plano 2.</span><span class="sxs-lookup"><span data-stu-id="adbd2-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="adbd2-136">O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.</span><span class="sxs-lookup"><span data-stu-id="adbd2-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="adbd2-137">As equipes de Operações de Segurança precisam atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365 e estar cientes de que as detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="adbd2-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="adbd2-138">Para exibir e usar *detecções do* Explorer ou em tempo real, você deve ter o seguinte:</span><span class="sxs-lookup"><span data-stu-id="adbd2-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="adbd2-139">Para o Centro de Conformidade & segurança:</span><span class="sxs-lookup"><span data-stu-id="adbd2-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="adbd2-140">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="adbd2-140">Organization Management</span></span>
  - <span data-ttu-id="adbd2-141">Administrador de Segurança (isso pode ser atribuído no Azure Active Directory de administração ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="adbd2-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="adbd2-142">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="adbd2-142">Security Reader</span></span>

- <span data-ttu-id="adbd2-143">Para Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="adbd2-143">For Exchange Online:</span></span>

  - <span data-ttu-id="adbd2-144">Gerenciamento de Organização</span><span class="sxs-lookup"><span data-stu-id="adbd2-144">Organization Management</span></span>
  - <span data-ttu-id="adbd2-145">Gerenciamento de Organização Somente Exibição</span><span class="sxs-lookup"><span data-stu-id="adbd2-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="adbd2-146">Destinatários Somente para Exibição</span><span class="sxs-lookup"><span data-stu-id="adbd2-146">View-Only Recipients</span></span>
  - <span data-ttu-id="adbd2-147">Gerenciamento de Conformidade</span><span class="sxs-lookup"><span data-stu-id="adbd2-147">Compliance Management</span></span>

<span data-ttu-id="adbd2-148">Para saber mais sobre funções e permissões, consulte os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="adbd2-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="adbd2-149">Permissões no Centro de Segurança e Conformidade</span><span class="sxs-lookup"><span data-stu-id="adbd2-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="adbd2-150">Permissões de recursos no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="adbd2-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="adbd2-151">PowerShell do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="adbd2-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="adbd2-152">Mais informações</span><span class="sxs-lookup"><span data-stu-id="adbd2-152">More information</span></span>
- [<span data-ttu-id="adbd2-153">O Explorador de Ameaças coleta detalhes de email na página entidade de email</span><span class="sxs-lookup"><span data-stu-id="adbd2-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="adbd2-154">Localizar e investigar emails mal-intencionados entregues</span><span class="sxs-lookup"><span data-stu-id="adbd2-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="adbd2-155">Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="adbd2-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="adbd2-156">Relatório de status de proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="adbd2-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="adbd2-157">Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="adbd2-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)