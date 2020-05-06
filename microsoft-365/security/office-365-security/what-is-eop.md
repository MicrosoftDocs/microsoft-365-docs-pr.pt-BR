---
title: O que é EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom:
- TN2DMC
- seo-marvel-apr2020
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Neste artigo, você aprenderá sobre o Exchange Online Protection (EOP), um serviço de filtragem de email baseado em nuvem.
ms.openlocfilehash: 7a9c122edf229d70f0ea5a1dbea8be56b5a2a3a9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034933"
---
# <a name="what-is-exchange-online-protection-eop"></a><span data-ttu-id="7c08f-103">O que é proteção do Exchange Online (EOP)</span><span class="sxs-lookup"><span data-stu-id="7c08f-103">What is Exchange Online Protection (EOP)</span></span>

<span data-ttu-id="7c08f-104">O Exchange Online Protection (EOP) é um serviço de filtragem de email baseado em nuvem que ajuda a proteger sua organização contra spam e malware.</span><span class="sxs-lookup"><span data-stu-id="7c08f-104">Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware.</span></span> <span data-ttu-id="7c08f-105">Se você tiver caixas de correio no Microsoft 365, elas serão automaticamente protegidas por EOP, uma vez que ela faz parte do serviço.</span><span class="sxs-lookup"><span data-stu-id="7c08f-105">If you have mailboxes in Microsoft 365, they are automatically protected by EOP since it is part of the service.</span></span> <span data-ttu-id="7c08f-106">Isso inclui as organizações que têm caixas de correio no Microsoft 365 e no local, que normalmente é conhecido como um cenário híbrido.</span><span class="sxs-lookup"><span data-stu-id="7c08f-106">This includes organizations that have mailboxes in both Microsoft 365 and on-premise, which is commonly known as a hybrid scenario.</span></span> <span data-ttu-id="7c08f-107">O EOP autônomo também está disponível para clientes que não têm caixas de correio na nuvem, mas querem proteger suas caixas de correio locais.</span><span class="sxs-lookup"><span data-stu-id="7c08f-107">EOP standalone is also available for customers who do not have mailboxes in the cloud but want to protect their on-premises mailboxes.</span></span>

<span data-ttu-id="7c08f-108">O EOP tenta filtrar o lixo eletrônico, mantendo a caixa de entrada limpa do conteúdo que os usuários não desejam ver.</span><span class="sxs-lookup"><span data-stu-id="7c08f-108">EOP attempts to filter out junk, keeping your Inbox clear of content that users don't want to see.</span></span> <span data-ttu-id="7c08f-109">Normalmente, o lixo eletrônico é enviado para a pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7c08f-109">Normally, junk mail is delivered to the Junk Email folder.</span></span> <span data-ttu-id="7c08f-110">Alguns usuários gostam de verificar se a filtragem está fazendo o que eles desejam, para que a pasta lixo eletrônico seja uma maneira fácil de os usuários verificarem por conta própria.</span><span class="sxs-lookup"><span data-stu-id="7c08f-110">Some users like to check to make sure the filtering is doing what they want so the Junk Email folder is an easy way for users to check on their own.</span></span>  

> [!TIP]
> <span data-ttu-id="7c08f-111">É uma boa coisa quando o lixo eletrônico ou emails mal incorretos entram na pasta lixo eletrônico automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7c08f-111">It is a good thing when junk or otherwise bad email goes into the Junk Email folder automatically.</span></span> <span data-ttu-id="7c08f-112">O serviço fará o que for necessário com base no que o padrão ou o estado de configurações personalizadas do administrador.</span><span class="sxs-lookup"><span data-stu-id="7c08f-112">The service will do what is necessary based on what the default or the custom admin settings state.</span></span> <span data-ttu-id="7c08f-113">Em outras palavras, os usuários não devem se preocupar em ver uma grande quantidade de mensagens de spam na pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7c08f-113">In other words, users should not worry about seeing a lot of spam mail in the Junk Email folder.</span></span> <span data-ttu-id="7c08f-114">Se os administradores preferem mover todo o lixo eletrônico para fora da visão, então a quarentena deve ser configurada.</span><span class="sxs-lookup"><span data-stu-id="7c08f-114">If admins prefer to move all junk out of sight, then the Quarantine should be configured.</span></span> <span data-ttu-id="7c08f-115">Para obter mais detalhes, consulte o artigo sobre [mensagens de email em quarentena](quarantine-email-messages.md) .</span><span class="sxs-lookup"><span data-stu-id="7c08f-115">For more details, see the [Quarantine email messages](quarantine-email-messages.md) article.</span></span>

## <a name="important-terms"></a><span data-ttu-id="7c08f-116">Termos importantes</span><span class="sxs-lookup"><span data-stu-id="7c08f-116">Important terms</span></span>

<span data-ttu-id="7c08f-117">**Entrada**: mensagens que estão chegando no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7c08f-117">**Inbound**: Messages that are coming into Microsoft 365.</span></span>

<span data-ttu-id="7c08f-118">**Saída**: mensagens que estão saindo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7c08f-118">**Outbound**: Messages that are going out of Microsoft 365.</span></span>

<span data-ttu-id="7c08f-119">**Interno**: mensagens de alguém dentro da organização para alguém dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="7c08f-119">**Internal**: Messages that are from someone inside the organization to someone inside the organization.</span></span> <span data-ttu-id="7c08f-120">Isso inclui os clientes que estão em cenários híbridos e uma caixa de correio pode ser local e a outra caixa de correio está na nuvem.</span><span class="sxs-lookup"><span data-stu-id="7c08f-120">This includes customers who are in hybrid scenarios and one mailbox could be on-premises and the other mailbox is in the cloud.</span></span>

<span data-ttu-id="7c08f-121">**Falso negativo (FN)**: spam e outros lixos que são enviados incorretamente para a caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="7c08f-121">**False Negative (FN)**: Spam and other junk that incorrectly gets sent into the inbox.</span></span>

<span data-ttu-id="7c08f-122">**Falso positivo (FP)**: mensagens legítimas que são marcadas incorretamente como spam e colocadas na pasta ou quarentena do lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7c08f-122">**False Positive (FP)**: Legitimate messages that incorrectly get marked as spam and put into the Junk Email folder or Quarantine.</span></span>

<span data-ttu-id="7c08f-123">**Spam, também conhecido como email não solicitado**: isso vem na forma de propaganda comercial, correntes, correspondências políticas, etc. Essa é uma mensagem de email informando que os usuários não se inscrevem e de spammers que estão tentando solicitar produtos ou tentar confirmar a fraude.</span><span class="sxs-lookup"><span data-stu-id="7c08f-123">**Spam, also known as unsolicited e-mail**: This comes in the form of commercial advertising, chain letters, political mailings, etc. This is email that users do not sign up for and from spammers who are trying to solicit products or attempting to commit fraud.</span></span>

<span data-ttu-id="7c08f-124">**Phish**: phishing é um tipo especial de spam destinado a induzir você a fornecer informações pessoais com o objetivo de confirmar o roubo de identidade ou fraude.</span><span class="sxs-lookup"><span data-stu-id="7c08f-124">**Phish**: Phishing is a special type of spam that is intended to trick you into giving up personal information for the purpose of committing identity theft or fraud.</span></span> <span data-ttu-id="7c08f-125">Esse tipo de mensagem normalmente contém um link ou anexo mal-intencionado, mas nem sempre.</span><span class="sxs-lookup"><span data-stu-id="7c08f-125">This type of message usually contains a malicious link or attachment, but not always.</span></span>

<span data-ttu-id="7c08f-126">**Spoof**: o spoofing é quando os spammers forjam o cabeçalho from para que as mensagens pareçam ter sido originadas de alguém ou de outro lugar que não seja a fonte real.</span><span class="sxs-lookup"><span data-stu-id="7c08f-126">**Spoof**: Spoofing is when spammers forge the FROM header so that messages appear to have originated from someone or somewhere other than the actual source.</span></span> <span data-ttu-id="7c08f-127">Isso pode ser spam, mas usado com mais frequência para usuários de Phish.</span><span class="sxs-lookup"><span data-stu-id="7c08f-127">This can be spam but most commonly used to phish users.</span></span>

<span data-ttu-id="7c08f-128">**Representação**: esse tipo de spam também é uma maneira de forjar o endereço do remetente, mas isso é feito modificando parte do nome ou domínio de forma que ele se pareça com a fonte real.</span><span class="sxs-lookup"><span data-stu-id="7c08f-128">**Impersonation**: This type of spam is also a way to forge the sender address, but it is done by modifying part of the name or domain so that it looks like the real source.</span></span> <span data-ttu-id="7c08f-129">Por exemplo, Bi11@micr0s0ft.com, onde "l" no Bill foi realmente o número onze e o "o" no Microsoft foi substituído pelo número zero.</span><span class="sxs-lookup"><span data-stu-id="7c08f-129">For example, Bi11@micr0s0ft.com, where the "l" in Bill was actually the number eleven and the "o" in Microsoft was replaced with the number zero.</span></span>

<span data-ttu-id="7c08f-130">**Em massa**: o email em massa geralmente é solicitado por usuários, embora às vezes as empresas vendem as informações para outras empresas.</span><span class="sxs-lookup"><span data-stu-id="7c08f-130">**Bulk**: Bulk mail is usually solicited by users, although sometimes indirectly when companies sell information to other companies.</span></span> <span data-ttu-id="7c08f-131">É comum que os usuários se inscrevam intencionalmente no email em massa (ou seja, newletters), mas se esqueçam mais tarde e pense que é spam.</span><span class="sxs-lookup"><span data-stu-id="7c08f-131">It is common that users intentionally sign up for bulk mail (i.e. newletters) but forget later on and think it is spam.</span></span> <span data-ttu-id="7c08f-132">O email em massa se torna spam quando os emails em massa enviam mais do que os níveis de inscrição e de reclamação ficam muito altos.</span><span class="sxs-lookup"><span data-stu-id="7c08f-132">Bulk mail becomes spam when bulk mailers send more than users sign up and complaint levels get too high.</span></span>
