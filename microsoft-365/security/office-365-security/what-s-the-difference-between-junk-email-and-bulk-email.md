---
title: Qual &apos; é a diferença entre lixo eletrônico e email em massa?
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre as diferenças entre lixo eletrônico (spam) e email em massa (email cinza) no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c656ed1807b451ae03ecfeb0f220f5d7b902c7ac
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290640"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email-in-eop"></a><span data-ttu-id="9141f-103">Qual é a diferença entre lixo eletrônico e email em massa no EOP?</span><span class="sxs-lookup"><span data-stu-id="9141f-103">What's the difference between junk email and bulk email in EOP?</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9141f-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9141f-104">**Applies to**</span></span>
- [<span data-ttu-id="9141f-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9141f-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9141f-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9141f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="9141f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9141f-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="9141f-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, os clientes às vezes perguntam: "Qual é a diferença entre lixo eletrônico e email em massa?"</span><span class="sxs-lookup"><span data-stu-id="9141f-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, customers sometimes ask: "what's the difference between junk email and bulk email?"</span></span> <span data-ttu-id="9141f-109">Este tópico explica a diferença e descreve os controles que estão disponíveis no EOP.</span><span class="sxs-lookup"><span data-stu-id="9141f-109">This topic explains the difference and describes the controls that are available in EOP.</span></span>

- <span data-ttu-id="9141f-110">**Lixo eletrônico** é spam, que são mensagens não solicitadas e universalmente indesejadas (quando identificadas corretamente).</span><span class="sxs-lookup"><span data-stu-id="9141f-110">**Junk email** is spam, which are unsolicited and universally unwanted messages (when identified correctly).</span></span> <span data-ttu-id="9141f-111">Por padrão, o EOP rejeita spam com base na reputação do servidor de email de origem.</span><span class="sxs-lookup"><span data-stu-id="9141f-111">By default, the EOP rejects spam based on the reputation of the source email server.</span></span> <span data-ttu-id="9141f-112">Se uma mensagem passar pela inspeção IP de origem, ela será enviada para a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="9141f-112">If a message passes source IP inspection, it's sent to spam filtering.</span></span> <span data-ttu-id="9141f-113">Se a mensagem for classificada como spam pela filtragem de spam, a mensagem será (por padrão) entregue aos destinatários pretendido e movida para sua pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9141f-113">If the message is classified as spam by spam filtering, the message is (by default) delivered to the intended recipients and moved to their Junk Email folder.</span></span>

  - <span data-ttu-id="9141f-114">Você pode configurar as ações a tomar em vereditos de filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="9141f-114">You can configure the actions to take on spam filtering verdicts.</span></span> <span data-ttu-id="9141f-115">Para obter instruções, [consulte Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9141f-115">For instructions, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="9141f-116">Se você não concordar com o veredito de filtragem de spam, poderá relatar à Microsoft as mensagens que considera como sendo spam ou não spam, conforme descrito em Relatar mensagens e arquivos para a [Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="9141f-116">If you disagree with the spam filtering verdict, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

- <span data-ttu-id="9141f-117">**É mais difícil** classificar emails em massa (também conhecidos como _emails cinzas)._</span><span class="sxs-lookup"><span data-stu-id="9141f-117">**Bulk email** (also known as _gray mail_), is more difficult to classify.</span></span> <span data-ttu-id="9141f-118">Enquanto spam é uma ameaça constante, o email em massa costuma ser anúncios avões ou mensagens de marketing.</span><span class="sxs-lookup"><span data-stu-id="9141f-118">Whereas spam is a constant threat, bulk email is often one-time advertisements or marketing messages.</span></span> <span data-ttu-id="9141f-119">Alguns usuários querem mensagens de email em massa (e, na verdade, eles se inscreveram deliberadamente para recebê-las), enquanto outros consideram o email em massa spam.</span><span class="sxs-lookup"><span data-stu-id="9141f-119">Some users want bulk email messages (and in fact, they have deliberately signed up to receive them), while other users consider bulk email to be spam.</span></span> <span data-ttu-id="9141f-120">Por exemplo, alguns usuários querem receber mensagens publicitárias da Contoso Corporation ou convites para uma conferência futura sobre segurança cibernética, enquanto outros consideram essas mesmas mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="9141f-120">For example, some users want to receive advertising messages from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider these same messages to be spam.</span></span>

  <span data-ttu-id="9141f-121">Para obter mais informações sobre como o email em massa é identificado, consulte BcL (nível de reclamação [em massa) no EOP.](bulk-complaint-level-values.md)</span><span class="sxs-lookup"><span data-stu-id="9141f-121">For more information about how bulk email is identified, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="9141f-122">Como gerenciar o email em massa</span><span class="sxs-lookup"><span data-stu-id="9141f-122">How to manage bulk email</span></span>

<span data-ttu-id="9141f-123">Devido à reação misturada ao email em massa, não há diretrizes universais que se apliquem a todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="9141f-123">Because of the mixed reaction to bulk email, there isn't universal guidance that applies to every organization.</span></span>

<span data-ttu-id="9141f-124">As polícias anti-spam têm um limite padrão de BCL usado para identificar emails em massa como spam.</span><span class="sxs-lookup"><span data-stu-id="9141f-124">Anti-spam polices have a default BCL threshold that's used to identify bulk email as spam.</span></span> <span data-ttu-id="9141f-125">Os administradores podem aumentar ou diminuir o limite.</span><span class="sxs-lookup"><span data-stu-id="9141f-125">Admins can increase or decrease the threshold.</span></span> <span data-ttu-id="9141f-126">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9141f-126">For more information, see the following topics:</span></span>

- <span data-ttu-id="9141f-127">[Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="9141f-127">[Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- [<span data-ttu-id="9141f-128">Configurações de política anti-spam do EOP</span><span class="sxs-lookup"><span data-stu-id="9141f-128">EOP anti-spam policy settings</span></span>](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)

<span data-ttu-id="9141f-129">Outra opção que é fácil de ignorar: se um usuário reclama de receber emails em massa, mas as mensagens são de remetentes confiáveis que passam pela filtragem de spam no EOP, fazer com que o usuário verifique se há uma opção de cancelamento de assinatura na mensagem de email em massa.</span><span class="sxs-lookup"><span data-stu-id="9141f-129">Another option that's easy to overlook: if a user complains about receiving bulk email, but the messages are from reputable senders that pass spam filtering in EOP, have the user check for a unsubscribe option in the bulk email message.</span></span>
