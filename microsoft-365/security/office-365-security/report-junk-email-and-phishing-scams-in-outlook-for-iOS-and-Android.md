---
title: Relatar lixo eletrônico e phishing no Outlook para iOS e Android
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
description: Os administradores podem saber mais sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook para iOS e Android.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289168"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a><span data-ttu-id="95806-103">Relatar lixo eletrônico e phishing no Outlook para iOS e Android no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95806-103">Report junk and phishing email in Outlook for iOS and Android in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95806-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="95806-104">**Applies to**</span></span>
- [<span data-ttu-id="95806-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95806-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="95806-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="95806-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="95806-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95806-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="95806-108">Nas organizações do Microsoft 365 com caixas de correio [](../../enterprise/hybrid-modern-auth-overview.md)no Exchange Online ou caixas de correio locais usando a autenticação moderna híbrida, você pode usar as opções de relatório internas no Outlook para iOS e Android para enviar falsos positivos (emails bons marcados como spam), falsos negativos (emails falsos permitidos) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="95806-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can use the built-in reporting options in Outlook for iOS and Android to submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95806-109">O que você precisa saber antes de começar</span><span class="sxs-lookup"><span data-stu-id="95806-109">What do you need to know before you begin</span></span>

- <span data-ttu-id="95806-110">Para a melhor experiência de envio de usuário, recomendamos usar a Mensagem de Relatório e os complementos de Phishing de Relatório. Consulte [Habilitar o complemento Mensagem de Relatório e](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) [Habilitar o complemento Phishing de Relatório](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="95806-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) and [Enable the Report Phishing add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in) for more information.</span></span>

- <span data-ttu-id="95806-111">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="95806-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="95806-112">Para obter mais informações, consulte Usar o Envio de Administrador para [enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="95806-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="95806-113">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="95806-113">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="95806-114">Para obter mais informações, consulte [políticas de Envios de Usuário.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="95806-114">For more information, see [User Submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="95806-115">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="95806-115">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="95806-116">Se o relatório de lixo eletrônico estiver desabilitado para o Outlook na política de envio de usuário, as mensagens de lixo eletrônico ou phishing serão movidas para a pasta Lixo eletrônico e não relatadas ao administrador ou à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95806-116">If junk email reporting is disabled for Outlook in the user submission policy, junk or phishing messages will be moved to the Junk folder and not reported to your admin or Microsoft.</span></span>