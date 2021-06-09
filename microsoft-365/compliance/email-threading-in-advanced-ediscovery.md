---
title: Threading de email no Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Ao realizar uma Advanced eDiscovery, o threading de email analisará uma conversa de email e separará cada mensagem em categorias diferentes.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285557"
---
# <a name="email-threading-in-advanced-ediscovery"></a><span data-ttu-id="489a6-103">Threading de email no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="489a6-103">Email threading in Advanced eDiscovery</span></span>

<span data-ttu-id="489a6-104">Considere uma conversa de email que está acontecendo há algum tempo.</span><span class="sxs-lookup"><span data-stu-id="489a6-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="489a6-105">Na maioria dos casos, o último email no thread incluirá o conteúdo de todos os emails anteriores; analisar o último email dará um contexto completo da conversa que aconteceu no thread.</span><span class="sxs-lookup"><span data-stu-id="489a6-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="489a6-106">O threading de email identifica esses emails para que os revisadores possam revisar uma fração de documentos coletados sem perder nenhum contexto.</span><span class="sxs-lookup"><span data-stu-id="489a6-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="489a6-107">O que o threading de email faz?</span><span class="sxs-lookup"><span data-stu-id="489a6-107">What does email threading do?</span></span>

<span data-ttu-id="489a6-108">O threading de email analisará cada email e o desconstrói para mensagens individuais; cada email é uma cadeia de mensagens individuais.</span><span class="sxs-lookup"><span data-stu-id="489a6-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="489a6-109">Em seguida, ele analisa todos os emails no conjunto de revisão para determinar se um email tem conteúdo exclusivo ou se a cadeia está totalmente contida em um email diferente.</span><span class="sxs-lookup"><span data-stu-id="489a6-109">Then, it analyzes all emails in the review set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="489a6-110">No final, os emails são divididos em quatro categorias:</span><span class="sxs-lookup"><span data-stu-id="489a6-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="489a6-111">**Inclusivo**: a última mensagem do email tem conteúdo exclusivo e o email tem todos os anexos dos outros emails dos quais o conteúdo está todo neste email.</span><span class="sxs-lookup"><span data-stu-id="489a6-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="489a6-112">**Inclusivo menos**: a última mensagem do email tem conteúdo exclusivo, mas o email não possui alguns anexos dos outros emails dos quais o conteúdo está todo neste email.</span><span class="sxs-lookup"><span data-stu-id="489a6-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="489a6-113">**Cópia inclusiva**: uma cópia exata de um email inclusivo/inclusivo menos</span><span class="sxs-lookup"><span data-stu-id="489a6-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="489a6-114">**Nenhum**: o conteúdo deste email está todo contido em pelo menos um email marcado como inclusivo/inclusivo menos.</span><span class="sxs-lookup"><span data-stu-id="489a6-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="489a6-115">Como é diferente das conversas em Outlook?</span><span class="sxs-lookup"><span data-stu-id="489a6-115">How is it different from conversations in Outlook?</span></span>

<span data-ttu-id="489a6-116">Em um relance, isso soa semelhante a grupos de conversa em Outlook.</span><span class="sxs-lookup"><span data-stu-id="489a6-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="489a6-117">No entanto, há algumas distinções importantes.</span><span class="sxs-lookup"><span data-stu-id="489a6-117">However, there are some important distinctions.</span></span> <span data-ttu-id="489a6-118">Considere uma conversa de email bifurcada em duas conversas; por exemplo, alguém respondeu a um email que não é o mais recente na conversa para que os dois últimos emails da conversa tenham conteúdo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="489a6-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="489a6-119">Outlook ainda agruparia os emails em uma única conversa; ler apenas o último email significaria perder o contexto do segundo e último email, que também contém conteúdo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="489a6-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="489a6-120">Como o threading de email analisará cada email em componentes individuais e os comparará, o threading de email marcaria os dois últimos emails como inclusivos, garantindo que você não perca nenhum contexto desde que leia todos os emails marcados como inclusivos.</span><span class="sxs-lookup"><span data-stu-id="489a6-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
