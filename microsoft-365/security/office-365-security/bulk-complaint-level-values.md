---
title: Valores de nível de reclamação em massa, remetentes de email em massa, níveis de BCL, como a BCL funciona, classificações de BCL, antispam, cabeçalho antispam, filtragem de email em massa, emails em massa
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Saiba mais sobre os valores de nível de reclamar em massa (BCL) no Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599718"
---
# <a name="bulk-complaint-level-values"></a><span data-ttu-id="c4d29-103">Valores do nível de reclamação em massa</span><span class="sxs-lookup"><span data-stu-id="c4d29-103">Bulk Complaint Level values</span></span>

<span data-ttu-id="c4d29-104">Os emails em massa variam em seus padrões de envio, criação de conteúdo e práticas de aquisição de lista.</span><span class="sxs-lookup"><span data-stu-id="c4d29-104">Bulk mailers vary in their sending patterns, content creation, and list acquisition practices.</span></span> <span data-ttu-id="c4d29-105">Alguns são bons remetentes em massa que enviam mensagens desejadas com conteúdo relevante para seus assinantes.</span><span class="sxs-lookup"><span data-stu-id="c4d29-105">Some are good bulk mailers that send wanted messages with relevant content to their subscribers.</span></span> <span data-ttu-id="c4d29-106">Essas mensagens geram poucas reclamações de destinatários.</span><span class="sxs-lookup"><span data-stu-id="c4d29-106">These messages generate few complaints from recipients.</span></span> <span data-ttu-id="c4d29-107">Outros remetentes em massa enviam mensagens não solicitadas que parecem muito parecidas com spam e geram muitas queixas de destinatários.</span><span class="sxs-lookup"><span data-stu-id="c4d29-107">Other bulk mailers send unsolicited messages that closely resemble spam and generate many complaints from recipients.</span></span>

<span data-ttu-id="c4d29-108">Para distinguir esses tipos de remetentes em massa, as mensagens de email em massa recebem uma classificação de BCL (nível de reclamação em massa).</span><span class="sxs-lookup"><span data-stu-id="c4d29-108">To distinguish these types of bulk mailers, messages from bulk mailers are assigned a Bulk Complaint Level (BCL) rating.</span></span> <span data-ttu-id="c4d29-109">A classificação de BCL varia de 1 a 9, dependendo da probabilidade de o remetente de mensagens em massa gerar queixas.</span><span class="sxs-lookup"><span data-stu-id="c4d29-109">BCL ratings range from 1 to 9 depending on how likely the bulk mailer is to generate complaints.</span></span> <span data-ttu-id="c4d29-110">Um remetente que tenha uma classificação da BCL 9 provavelmente gerará muitas queixas de destinatários, enquanto uma classificação da BCL 3 será improvável de gerar muitas queixas.</span><span class="sxs-lookup"><span data-stu-id="c4d29-110">A sender that has a rating of BCL 9 is likely to generate many complaints from recipients, whereas a rating of BCL 3 is unlikely to generate many complaints.</span></span> <span data-ttu-id="c4d29-111">A Microsoft usa fontes internas e de terceiros para identificar emails em massa e determinar a BCL apropriada.</span><span class="sxs-lookup"><span data-stu-id="c4d29-111">Microsoft uses both internal and third-party sources to identify bulk mail and determine the appropriate BCL.</span></span> <span data-ttu-id="c4d29-112">Para obter mais informações sobre esse cabeçalho de mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="c4d29-112">For more information about this message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="c4d29-113">Como um remetente de email em massa com uma classificação de 9 provavelmente gerará queixas, a BCL padrão será 7.</span><span class="sxs-lookup"><span data-stu-id="c4d29-113">Since a bulk mailer with a rating of 9 is likely to generate complaints, the default BCL is 7.</span></span> <span data-ttu-id="c4d29-114">Isso significa que os emails em massa serão aceitos até que o nível de reclamação de 7 e email não seja aceito posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4d29-114">This means that bulk mails will be accepted until the complaint level of 7 and mail won't be accepted thereafter.</span></span> <span data-ttu-id="c4d29-115">Quanto menor a classificação, menos mensagens em massa serão aceitas.</span><span class="sxs-lookup"><span data-stu-id="c4d29-115">The lower the rating, the less bulk mail is accepted.</span></span> <span data-ttu-id="c4d29-116">Se os seus usuários são, e seu trabalho é, confidencial para email em massa e sua BCL está definida como 4, então nenhum email em massa com uma BCL maior do que 4 será aceito.</span><span class="sxs-lookup"><span data-stu-id="c4d29-116">If your users are, and their work is, sensitive to bulk mail, and your BCL is set to 4, then no bulk mail with a higher BCL than 4 will be accepted.</span></span>

<span data-ttu-id="c4d29-117">Você pode usar valores de BCL para definir o nível desejado de filtragem em massa que sua organização requer, seguindo as etapas em [Configure Your spam filter Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c4d29-117">You can use BCL values to set the desired level of bulk filtering your organization requires by following the steps in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="c4d29-118">A tabela a seguir descreve os valores de BCL que estão em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="c4d29-118">The following table describes the BCL values that are currently in use.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c4d29-119">**Valor de BCL**</span><span class="sxs-lookup"><span data-stu-id="c4d29-119">**BCL Value**</span></span>|<span data-ttu-id="c4d29-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c4d29-120">**Description**</span></span>|
|<span data-ttu-id="c4d29-121">,0</span><span class="sxs-lookup"><span data-stu-id="c4d29-121">0</span></span>|<span data-ttu-id="c4d29-122">A mensagem não é de um remetente em massa.</span><span class="sxs-lookup"><span data-stu-id="c4d29-122">The message isn't from a bulk sender.</span></span>|
|<span data-ttu-id="c4d29-123">1, 2, 3</span><span class="sxs-lookup"><span data-stu-id="c4d29-123">1, 2, 3</span></span>|<span data-ttu-id="c4d29-124">A mensagem é de um remetente em massa que gera algumas reclamações.</span><span class="sxs-lookup"><span data-stu-id="c4d29-124">The message is from a bulk sender that generates few complaints.</span></span>|
|<span data-ttu-id="c4d29-125">4, 5, 6, 7</span><span class="sxs-lookup"><span data-stu-id="c4d29-125">4, 5, 6, 7</span></span>|<span data-ttu-id="c4d29-126">A mensagem é de um remetente em massa que gera um número misto de reclamações.</span><span class="sxs-lookup"><span data-stu-id="c4d29-126">The message is from a bulk sender that generates a mixed number of complaints.</span></span>|
|<span data-ttu-id="c4d29-127">8, 9</span><span class="sxs-lookup"><span data-stu-id="c4d29-127">8, 9</span></span>|<span data-ttu-id="c4d29-128">A mensagem é de um remetente em massa que gera um grande número de reclamações.</span><span class="sxs-lookup"><span data-stu-id="c4d29-128">The message is from a bulk sender that generates a high number of complaints.</span></span>|
