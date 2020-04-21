---
title: Qual é a diferença entre lixo eletrônico e email em massa?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: Este tópico explica a diferença entre o lixo eletrônico (spam) e o email em massa e os controles relacionados no Office 365.
ms.openlocfilehash: 15ca00b007ef0b8470e1b30608a695a90bd638b2
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630828"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="778e0-103">Qual é a diferença entre lixo eletrônico e email em massa?</span><span class="sxs-lookup"><span data-stu-id="778e0-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="778e0-104">Os clientes do Microsoft 365 com caixas de correio no Exchange Online ou no Exchange Online Protection (EOP) clientes sem caixas de correio do Exchange Online às vezes perguntar: "Qual é a diferença entre lixo eletrônico e email em massa?"</span><span class="sxs-lookup"><span data-stu-id="778e0-104">Microsoft 365 customers with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) customers without Exchange Online mailboxes sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="778e0-105">Este tópico explica a diferença e descreve os controles disponíveis no EOP.</span><span class="sxs-lookup"><span data-stu-id="778e0-105">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="778e0-106">O **lixo eletrônico** é spam, que são mensagens não solicitadas e indesejadas universalmente (quando identificadas corretamente).</span><span class="sxs-lookup"><span data-stu-id="778e0-106">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="778e0-107">Por padrão, o EOP rejeita spam com base na reputação do servidor de email de origem.</span><span class="sxs-lookup"><span data-stu-id="778e0-107">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="778e0-108">Se uma mensagem transmite a inspeção de IP de origem, ela é enviada para filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="778e0-108">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="778e0-109">Se a mensagem for classificada como spam por filtragem de spam, a mensagem será (por padrão) entregue aos destinatários pretendidos e movida para a pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="778e0-109">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="778e0-110">Você pode configurar as ações a serem executadas no verdicts de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="778e0-110">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="778e0-111">Para obter instruções, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="778e0-111">For instructions, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="778e0-112">Se você discordar do veredicto de filtragem de spam, poderá relatar mensagens que você considerar como spam ou não spam para a Microsoft de várias maneiras, conforme descrito em [mensagens e arquivos de relatório para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="778e0-112">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="778e0-113">**Email em massa** (também conhecido como _email cinza_), é mais difícil de classificá-lo.</span><span class="sxs-lookup"><span data-stu-id="778e0-113">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="778e0-114">Enquanto spam é uma ameaça constante, o email em massa geralmente é um anúncio único ou mensagens de marketing.</span><span class="sxs-lookup"><span data-stu-id="778e0-114">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="778e0-115">Alguns usuários querem mensagens de email em massa (e, na verdade, eles se assinaram propositalmente para recebê-los), enquanto outros usuários consideram o email em massa como spam.</span><span class="sxs-lookup"><span data-stu-id="778e0-115">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="778e0-116">Por exemplo, alguns usuários desejam receber mensagens de publicidade da Contoso Corporation ou convites para uma conferência futura no Cyber Security, enquanto outros usuários consideram essas mesmas mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="778e0-116">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="778e0-117">Para obter mais informações sobre como os emails em massa são identificados, confira [BCL (nível de reclamação em massa) no Office 365](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="778e0-117">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in Office 365](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="778e0-118">Como gerenciar o email em massa</span><span class="sxs-lookup"><span data-stu-id="778e0-118">How to manage bulk email</span></span>

<span data-ttu-id="778e0-119">Devido à reação mista para email em massa, não há orientações universais que se aplicam a todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="778e0-119">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="778e0-120">As políticas antispam têm um limite de BCL padrão usado para identificar emails em massa como spam.</span><span class="sxs-lookup"><span data-stu-id="778e0-120">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="778e0-121">Os administradores podem aumentar ou diminuir o limite.</span><span class="sxs-lookup"><span data-stu-id="778e0-121">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="778e0-122">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="778e0-122">For more information, see the following topics:</span></span>

- <span data-ttu-id="778e0-123">[Configure as políticas antispam no Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="778e0-123">[Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="778e0-124">Configurações de política antispam do EOP</span><span class="sxs-lookup"><span data-stu-id="778e0-124">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="778e0-125">Outra opção que é fácil de ser ignorada: se um usuário reclamar de receber emails em massa, mas as mensagens forem provenientes de remetentes confiáveis que passam a filtragem de spam no EOP, peça que o usuário Verifique se há uma opção de cancelamento de assinatura na mensagem de email em massa.</span><span class="sxs-lookup"><span data-stu-id="778e0-125">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
