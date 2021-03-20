---
title: Relatar lixo eletrônico e email de phishing no Outlook para iOS e Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook para iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eda0d8d43244834236a70374df6b7d6ccf0b69ab
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908806"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="7a82c-103">Relatar lixo eletrônico e email de phishing no Outlook para iOS e Android no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7a82c-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7a82c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="7a82c-104">**Applies to**</span></span>
- [<span data-ttu-id="7a82c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7a82c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7a82c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7a82c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="7a82c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7a82c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="7a82c-108">Nas organizações do Microsoft 365 com caixas de correio [](../../enterprise/hybrid-modern-auth-overview.md)no Exchange Online ou caixas de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para a Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="7a82c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7a82c-109">O que você precisa saber antes de começar</span><span class="sxs-lookup"><span data-stu-id="7a82c-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="7a82c-110">Para a melhor experiência de envio de usuário, recomendamos usar a Mensagem de Relatório e os complementos de Phishing de Relatório. Consulte [Habilitar](./enable-the-report-message-add-in.md) o complemento Mensagem de Relatório e [Habilitar o add-in de Phishing de Relatório](./enable-the-report-phish-add-in.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7a82c-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="7a82c-111">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="7a82c-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7a82c-112">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7a82c-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="7a82c-113">Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="7a82c-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7a82c-114">Para obter mais informações, consulte [User Submissions policies](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7a82c-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="7a82c-115">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7a82c-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7a82c-116">Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio do usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta Lixo Eletrônico e não relatadas ao administrador ou à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a82c-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>