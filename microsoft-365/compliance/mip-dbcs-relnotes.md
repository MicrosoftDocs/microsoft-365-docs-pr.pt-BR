---
title: Suporte ao Centro de conformidade do Microsoft 365 para as notas de versão do conjunto de caracteres de dois bytes (visualização)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão para suporte a conjuntos de caracteres de dois bytes.
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695227"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a><span data-ttu-id="354a4-103">Suporte para as notas de versão do conjunto de caracteres de dois bytes (visualização)</span><span class="sxs-lookup"><span data-stu-id="354a4-103">Support for double byte character set release notes (preview)</span></span>

 <span data-ttu-id="354a4-104">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="354a4-104">Microsoft 365 Information Protection now supports in preview double byte character set languages for:</span></span>

- <span data-ttu-id="354a4-105">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="354a4-105">Chinese (simplified)</span></span>
- <span data-ttu-id="354a4-106">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="354a4-106">Chinese (traditional)</span></span>
- <span data-ttu-id="354a4-107">Coreano</span><span class="sxs-lookup"><span data-stu-id="354a4-107">Korean</span></span>
- <span data-ttu-id="354a4-108">Japonês</span><span class="sxs-lookup"><span data-stu-id="354a4-108">Japanese</span></span>

<span data-ttu-id="354a4-109">Esta visualização está apenas na nuvem comercial e a implementação está limitada para:</span><span class="sxs-lookup"><span data-stu-id="354a4-109">This preview is only in the commercial cloud and the rollout is limited to:</span></span>

- <span data-ttu-id="354a4-110">Japão</span><span class="sxs-lookup"><span data-stu-id="354a4-110">Japan</span></span>
- <span data-ttu-id="354a4-111">Coreia</span><span class="sxs-lookup"><span data-stu-id="354a4-111">Korea</span></span>
- <span data-ttu-id="354a4-112">China</span><span class="sxs-lookup"><span data-stu-id="354a4-112">China</span></span>
- <span data-ttu-id="354a4-113">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="354a4-113">Hong Kong</span></span>
- <span data-ttu-id="354a4-114">Macau</span><span class="sxs-lookup"><span data-stu-id="354a4-114">Macau</span></span>
- <span data-ttu-id="354a4-115">Taiwan</span><span class="sxs-lookup"><span data-stu-id="354a4-115">Taiwan</span></span>

<span data-ttu-id="354a4-116">Esse suporte está disponível para tipos de informações confidenciais e dicionários de palavras-chave, e será refletido em soluções de prevenção de perda de dados, de conformidade de comunicações, do Exchange Online, do SharePoint Online, do OneDrive for Business e do Teams.</span><span class="sxs-lookup"><span data-stu-id="354a4-116">This support is available for sensitive information types and keyword dictionaries and will be reflected in data loss prevention, communications compliance, Exchange Online, SharePoint Online, OneDrive for Business, and Teams solutions.</span></span>

## <a name="known-issues"></a><span data-ttu-id="354a4-117">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="354a4-117">Known issues</span></span>

- <span data-ttu-id="354a4-118">Quando um arquivo de texto anexado a um email está no formato UTF-8 sem BOM (marca de ordem de byte), o email não é detectado pela política de conformidade de comunicação.</span><span class="sxs-lookup"><span data-stu-id="354a4-118">When a text file attached to an email is in UTF-8 format without byte order mark (BOM), the email is not detected by the Communication Compliance policy.</span></span>

- <span data-ttu-id="354a4-119">As políticas de conformidade de comunicação não conseguem detectar valores se uma frase for inserida na condição da política: “A mensagem contém qualquer uma destas palavras”.</span><span class="sxs-lookup"><span data-stu-id="354a4-119">Communication Compliance policies cannot detect values if a sentence is entered for the policy condition: “Message contains any of these words”.</span></span> <span data-ttu-id="354a4-120">Se o texto especificado na política for escrito como uma palavra, ele poderá ser detectado; no entanto, se for escrito no meio de uma frase, ele não será detectado.</span><span class="sxs-lookup"><span data-stu-id="354a4-120">If the text specified in the policy is written as a word, it can be detected; however, if it is written in the middle of a sentence, it will not be detected.</span></span>

- <span data-ttu-id="354a4-121">As políticas de conformidade de comunicação que especificam dicionários como informações de tipo não detectam chats privados do Teams e chats de canal.</span><span class="sxs-lookup"><span data-stu-id="354a4-121">Communication Compliance policies that specify dictionaries as type information do not detect Teams private chats and channel chats.</span></span>

- <span data-ttu-id="354a4-122">As condições a seguir não são compatíveis com a conformidade de comunicação nesta fase (planejamos corrigir esses problemas no futuro):</span><span class="sxs-lookup"><span data-stu-id="354a4-122">The following conditions are not supported for Communication Compliance at this stage (we plan to fix these issues in the future):</span></span> 
  - <span data-ttu-id="354a4-123">“A mensagem contém qualquer uma destas palavras”</span><span class="sxs-lookup"><span data-stu-id="354a4-123">“Message contains any of these words”</span></span>
  - <span data-ttu-id="354a4-124">“A mensagem não contém nenhuma destas palavras”</span><span class="sxs-lookup"><span data-stu-id="354a4-124">“Message contains none of these words”</span></span>
  - <span data-ttu-id="354a4-125">“O anexo contém qualquer uma destas palavras”</span><span class="sxs-lookup"><span data-stu-id="354a4-125">“Attachment contains any of these words”</span></span>
  - <span data-ttu-id="354a4-126">“O anexo contém qualquer uma destas palavras”</span><span class="sxs-lookup"><span data-stu-id="354a4-126">“Attachment contains any of these words”</span></span>

<span data-ttu-id="354a4-127">Em vez disso, recomendamos a criação de um SIT (tipo de informação confidencial) personalizado com dicionário de palavras-chave, que detectará padrões em mensagens e anexos, e o uso desse SIT personalizado como uma condição de política de conformidade de comunicação.</span><span class="sxs-lookup"><span data-stu-id="354a4-127">Instead we recommend creating a custom Sensitive Information Type (SIT) with keyword dictionary which will detect patterns across messages and attachments, and using this custom SIT as a Communication Compliance policy condition.</span></span>
