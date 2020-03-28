---
title: Relatar mensagens de spam, não spam e phishing à Microsoft
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 'O Suplemento de Relatório de Lixo Eletrônico da Microsoft do Microsoft Office Outlook oferece várias maneiras para você relatar mensagens de lixo eletrônico:'
ms.openlocfilehash: b7e7ed56f171ee3b74b36ed7c10c46286fb1e570
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033657"
---
# <a name="report-messages-and-files-to-microsoft"></a><span data-ttu-id="3fef4-103">Relatar mensagens e arquivos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3fef4-103">Report messages and files to Microsoft</span></span>

<span data-ttu-id="3fef4-104">Usuários e administradores nas organizações do Office 365 com caixas de correio no Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online para enviar mensagens de email têm vários métodos diferentes para relatar mensagens e arquivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3fef4-104">Users and admins in Office 365 organizations with mailboxes in Exchange Online, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes to submit email messages have several different methods for reporting messages and files to Microsoft.</span></span>

|||
|---|---|
|<span data-ttu-id="3fef4-105">**Method**</span><span class="sxs-lookup"><span data-stu-id="3fef4-105">**Method**</span></span>|<span data-ttu-id="3fef4-106">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3fef4-106">**Description**</span></span>|
|[<span data-ttu-id="3fef4-107">Usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3fef4-107">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>](admin-submission.md)|<span data-ttu-id="3fef4-108">Este é o método de relatório recomendado para administradores em organizações com caixas de correio do Exchange Online (não está disponível em EOP autônomo).</span><span class="sxs-lookup"><span data-stu-id="3fef4-108">This is the recommended reporting method for admins in organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="3fef4-109">Habilitar o suplemento de mensagem de relatório no Office 365</span><span class="sxs-lookup"><span data-stu-id="3fef4-109">Enable the Report Message add-in in Office 365</span></span>](enable-the-report-message-add-in.md)|<span data-ttu-id="3fef4-110">Funciona com o Outlook, o Outlook para Mac e o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="3fef4-110">Works with Outlook, Outlook for Mac, and Outlook on the web.</span></span> <span data-ttu-id="3fef4-111">Este é o suplemento recomendado.</span><span class="sxs-lookup"><span data-stu-id="3fef4-111">This is the recommended add-in.</span></span> <br/><br/> <span data-ttu-id="3fef4-112">Dependendo da sua licença, as mensagens relatadas estão disponíveis em [resultados de investigação e resposta automatizados (Air)](air-view-investigation-results.md), o [relatório de mensagens relatadas pelo usuário](view-email-security-reports.md#user-reported-messages-report) e o explorador de [ameaças](threat-explorer-views.md#email--submissions).</span><span class="sxs-lookup"><span data-stu-id="3fef4-112">Depending on your license, the reported messages are available in [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report) and [Threat Explorer](threat-explorer-views.md#email--submissions).</span></span>|
|[<span data-ttu-id="3fef4-113">Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook no Office 365</span><span class="sxs-lookup"><span data-stu-id="3fef4-113">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>](junk-email-reporting-add-in-for-microsoft-outlook.md)|<span data-ttu-id="3fef4-114">O só funciona no Outlook.</span><span class="sxs-lookup"><span data-stu-id="3fef4-114">Only works in Outlook.</span></span>|
|[<span data-ttu-id="3fef4-115">Relatar emails de lixo eletrônico e phishing no Outlook na Web no Office 365</span><span class="sxs-lookup"><span data-stu-id="3fef4-115">Report junk and phishing email in Outlook on the web in Office 365</span></span>](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|<span data-ttu-id="3fef4-116">Use os recursos internos do Outlook na Web para organizações com caixas de correio do Exchange Online (não estão disponíveis em EOP autônomos).</span><span class="sxs-lookup"><span data-stu-id="3fef4-116">Use the built-in capabilities in Outlook on the web for organizations with Exchange Online mailboxes (not available in standalone EOP).</span></span>|
|[<span data-ttu-id="3fef4-117">Enviar malware e não malware para a Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="3fef4-117">Submit malware and non-malware to Microsoft for analysis</span></span>](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|<span data-ttu-id="3fef4-118">Use o site do Microsoft Security Intelligence para enviar anexos e outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="3fef4-118">Use the Microsoft Security Intelligence site to submit attachments and other files.</span></span>|
|

<span data-ttu-id="3fef4-119">Se as mensagens de spam ou phishing foram colocadas em quarentena em vez de entregues, os usuários podem relatar as mensagens para a Microsoft do portal de quarentena no centro de conformidade & segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3fef4-119">If the spam or phishing messages were quarantined instead of delivered, users can report the messages to Microsoft from the Quarantine portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3fef4-120">Para obter detalhes, consulte [Localizar e liberar mensagens em quarentena como um usuário no Office 365](find-and-release-quarantined-messages-as-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="3fef4-120">For details, see [Find and release quarantined messages as a user in Office 365](find-and-release-quarantined-messages-as-a-user.md).</span></span>