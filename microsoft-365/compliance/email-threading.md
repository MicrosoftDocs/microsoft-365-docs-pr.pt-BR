---
title: Encadeamento de e-mails – investigações de dados
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
ms.assetid: ''
description: Ao gerenciar uma investigação de dados, o encadeamento de emails analisa uma conversa por email e separa cada mensagem em diferentes categorias.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 66238d87bd314f2b29e77886f33cb53f9a879aff
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527659"
---
# <a name="email-threading"></a><span data-ttu-id="721da-103">Threading de emails</span><span class="sxs-lookup"><span data-stu-id="721da-103">Email threading</span></span>

<span data-ttu-id="721da-104">Considere uma conversa por email que está acontecendo por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="721da-104">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="721da-105">Na maioria dos casos, o último email no thread incluirá o conteúdo de todos os emails anteriores; a revisão do último email fornecerá um contexto completo da conversa que aconteceu no thread.</span><span class="sxs-lookup"><span data-stu-id="721da-105">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="721da-106">O encadeamento de emails identifica esses emails para que os Revisores possam revisar uma fração de documentos coletados sem perder nenhum contexto.</span><span class="sxs-lookup"><span data-stu-id="721da-106">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="721da-107">O que o thread de email faz?</span><span class="sxs-lookup"><span data-stu-id="721da-107">What does email threading do?</span></span>

<span data-ttu-id="721da-108">O thread de email analisa cada email e o deconstrói para mensagens individuais; cada email é uma cadeia de mensagens individuais.</span><span class="sxs-lookup"><span data-stu-id="721da-108">Email threading parses each email and deconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="721da-109">Em seguida, ele analisa todos os emails no conjunto de trabalho para determinar se um email tem conteúdo exclusivo ou se a cadeia está totalmente contida em um email diferente.</span><span class="sxs-lookup"><span data-stu-id="721da-109">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="721da-110">Nos emails finais estão divididos em quatro categorias:</span><span class="sxs-lookup"><span data-stu-id="721da-110">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="721da-111">**Inclusive**: a última mensagem no email tem conteúdo exclusivo e o email tem todos os anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.</span><span class="sxs-lookup"><span data-stu-id="721da-111">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="721da-112">**Inclusive menos**: a última mensagem no email tem conteúdo exclusivo, mas o email não contém alguns dos anexos que foram incluídos em outros emails dos quais o conteúdo está totalmente contido neste email.</span><span class="sxs-lookup"><span data-stu-id="721da-112">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="721da-113">**Cópia inclusiva**: uma cópia exata de um email incluindo menos de um</span><span class="sxs-lookup"><span data-stu-id="721da-113">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="721da-114">**Nenhum**: o conteúdo desse email está totalmente contido em pelo menos um email marcado como incluindo, inclusive, o menos.</span><span class="sxs-lookup"><span data-stu-id="721da-114">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="721da-115">Qual é a diferença entre conversas no Outlook?</span><span class="sxs-lookup"><span data-stu-id="721da-115">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="721da-116">Em um relance, isso parece semelhante aos agrupamentos de conversa no Outlook.</span><span class="sxs-lookup"><span data-stu-id="721da-116">At a glance, this sounds similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="721da-117">No entanto, há algumas diferenças importantes.</span><span class="sxs-lookup"><span data-stu-id="721da-117">However, there are some important distinctions.</span></span> <span data-ttu-id="721da-118">Considere uma conversa de email que foi bifurcada em duas conversas; por exemplo, alguém respondeu a um email que não é o mais recente na conversa para que os dois últimos emails da conversa tenham conteúdo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="721da-118">Consider an email conversation that got forked into two conversations; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="721da-119">O Outlook ainda agruparia os emails em uma única conversa; somente leitura o último email significaria ter o contexto do segundo email, que também contém conteúdo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="721da-119">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="721da-120">Como o encadeamento de emails analisa cada email em componentes individuais e os compara, o encadeamento de emails marcaria ambos os dois últimos emails, o que garante que você não perderá nenhum contexto, desde que você leia todos os emails marcados como inclusive.</span><span class="sxs-lookup"><span data-stu-id="721da-120">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusive, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>
