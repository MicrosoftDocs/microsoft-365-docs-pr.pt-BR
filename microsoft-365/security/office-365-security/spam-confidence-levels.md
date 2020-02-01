---
title: Níveis de confiança de spam
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Quando uma mensagem de email passa pela filtragem de spam, recebe uma pontuação de spam. Essa pontuação é mapeada para uma classificação individual de Nível de Confiança de Spam (SCL) em um cabeçalho X. O serviço executa ações nas mensagens, dependendo da interpretação da confiança do spam da classificação SCL. A tabela a seguir mostra como as diferentes classificações SCL são interpretadas pelos filtros e a ação padrão tomada em mensagens de entrada para cada classificação.
ms.openlocfilehash: c40317833ea61424dab60ac858c2071f7891c4f8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598308"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="ea28a-106">Níveis de confiança de spam</span><span class="sxs-lookup"><span data-stu-id="ea28a-106">Spam confidence levels</span></span>

<span data-ttu-id="ea28a-p102">Quando uma mensagem de email passa pela filtragem de spam, recebe uma pontuação de spam. Essa pontuação é mapeada para uma classificação individual de Nível de Confiança de Spam (SCL) em um cabeçalho X. O serviço executa ações nas mensagens, dependendo da interpretação da confiança do spam da classificação SCL. A tabela a seguir mostra como as diferentes classificações SCL são interpretadas pelos filtros e a ação padrão tomada em mensagens de entrada para cada classificação.</span><span class="sxs-lookup"><span data-stu-id="ea28a-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="ea28a-111">**Classificação SCL**</span><span class="sxs-lookup"><span data-stu-id="ea28a-111">**SCL Rating**</span></span>|<span data-ttu-id="ea28a-112">**Interpretação de confiança de spam**</span><span class="sxs-lookup"><span data-stu-id="ea28a-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="ea28a-113">**Ação padrão**</span><span class="sxs-lookup"><span data-stu-id="ea28a-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea28a-114">-1</span><span class="sxs-lookup"><span data-stu-id="ea28a-114">-1</span></span>|<span data-ttu-id="ea28a-115">Não spam proveniente de um remetente seguro, de um destinatário seguro ou de um endereço IP listado (parceiro confiável).</span><span class="sxs-lookup"><span data-stu-id="ea28a-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="ea28a-116">Entregar a mensagem para a caixa de entrada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ea28a-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="ea28a-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="ea28a-117">0, 1</span></span>|<span data-ttu-id="ea28a-118">Não spam porque a mensagem foi examinada e determinada como limpa.</span><span class="sxs-lookup"><span data-stu-id="ea28a-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="ea28a-119">Entregar a mensagem para a caixa de entrada do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ea28a-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="ea28a-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="ea28a-120">5, 6</span></span>|<span data-ttu-id="ea28a-121">Spam</span><span class="sxs-lookup"><span data-stu-id="ea28a-121">Spam</span></span>|<span data-ttu-id="ea28a-122">Entregar a mensagem na pasta Lixo Eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ea28a-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="ea28a-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="ea28a-123">7, 8, 9</span></span>|<span data-ttu-id="ea28a-124">Spam de alta confiança</span><span class="sxs-lookup"><span data-stu-id="ea28a-124">High confidence spam</span></span>|<span data-ttu-id="ea28a-125">Entregar a mensagem na pasta Lixo Eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="ea28a-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="ea28a-126">As classificações SCL 2, 3, 4, 7 e 8 não são definidas pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="ea28a-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="ea28a-127">Uma classificação SCL 5 ou 6 é considerada como spam suspeito, que é menos provável de ser um spam do que uma classificação 9, considerada como determinado spam.</span><span class="sxs-lookup"><span data-stu-id="ea28a-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="ea28a-128">Ações diferentes para spam e spam de alta confiança pode ser configuradas via políticas de filtro de conteúdo no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ea28a-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="ea28a-129">Para obter mais informações, consulte [Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ea28a-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="ea28a-130">Você também pode definir a classificação de SCL para mensagens que correspondem a condições específicas usando regras de fluxo de emails (também conhecidas como regras de transporte), conforme descrito em [usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ea28a-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="ea28a-131">Se você usar uma regra de fluxo de emails para definir SCL de 7, 8 ou 9, a mensagem será tratada como spam de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="ea28a-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="ea28a-p104">![O ícone pequeno do LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Começando a usar o Office 365?**         Descubra cursos em vídeo gratuitos para **Office 365 admins and IT pros**, oferecidos pelo LinkedIn Learning.</span><span class="sxs-lookup"><span data-stu-id="ea28a-p104">![The short icon for LinkedIn Learning](../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

