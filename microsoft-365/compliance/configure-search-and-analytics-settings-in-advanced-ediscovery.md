---
title: Definir configurações de pesquisa e análise
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
description: ''
ms.openlocfilehash: 5aa83f4f736c239b1cdfe940f27cfaa4b981ff64
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072216"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="b0dfb-102">Definir configurações de pesquisa e análise</span><span class="sxs-lookup"><span data-stu-id="b0dfb-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="b0dfb-103">Duplicados próximos e threads de email</span><span class="sxs-lookup"><span data-stu-id="b0dfb-103">Near duplicates and email threading</span></span>

<span data-ttu-id="b0dfb-104">Nesta seção, você pode definir parâmetros para detecção de duplicidades, detecção de duplicidade próxima e thread de email.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="b0dfb-105">Enable/disable: incluir a detecção de duplicidades, a detecção de duplicidade próxima e o encadeamento de email como parte do fluxo de análise, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="b0dfb-106">Como eles se baseiam uns dos outros, você deve habilitar todos eles ou desabilitá-los.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="b0dfb-107">Limite: se o nível de similaridade de dois documentos estiver acima do limite, ele será colocado no mesmo conjunto próximo duplicado.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="b0dfb-108">Ocultar duplicatas por padrão: se essa configuração estiver ativada, um filtro para ocultar documentos duplicados será aplicado na análise definida por padrão.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the review set by default.</span></span> <span data-ttu-id="b0dfb-109">O filtro pode ser removido manualmente no conjunto de revisão, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-109">The filter can be removed manually in the review set if necessary.</span></span>

- <span data-ttu-id="b0dfb-110">Número mínimo/máximo de palavras: próximas duplicatas e o encadeamento de emails será executado somente em documentos que tenham pelo menos o número mínimo de palavras e, no máximo, o número máximo de palavras.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="b0dfb-111">Para obter mais informações, consulte [Near Duplicate Detection](near-duplicates.md) and [e-mail Threading](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="b0dfb-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="b0dfb-112">Temas</span><span class="sxs-lookup"><span data-stu-id="b0dfb-112">Themes</span></span>

<span data-ttu-id="b0dfb-113">Nesta seção, você pode definir parâmetros para temas.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="b0dfb-114">Enable/disable: incluir agrupamento de temas como parte do fluxo de análise, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="b0dfb-115">Ajustar o número máximo de temas dinamicamente dinamicamente: em certos casos, não há documentos suficientes para produzir o número desejado de temas.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="b0dfb-116">Se essa configuração estiver ativada, em vez de tentar forçar o número máximo de temas desejado, o sistema ajustará o número máximo de temas dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="b0dfb-117">Número máximo de temas: número desejado de temas</span><span class="sxs-lookup"><span data-stu-id="b0dfb-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="b0dfb-118">Incluir números em temas: quando habilitado, ele incluirá números ao gerar temas.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="b0dfb-119">Reconhecimento óptico de caracteres (OCR)</span><span class="sxs-lookup"><span data-stu-id="b0dfb-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="b0dfb-120">Quando essa configuração estiver ativada, o OCR será executado em imagens que são incluídas nos conjuntos de revisão para que possam ser pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-120">When this setting is turned on, OCR will be run on images that are ingested into review sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="b0dfb-121">Ignorar texto</span><span class="sxs-lookup"><span data-stu-id="b0dfb-121">Ignore text</span></span>

<span data-ttu-id="b0dfb-122">Há situações em que determinados textos reduzirão a qualidade da análise, como avisos de isenção de responsabilidade longos que são adicionados a certos emails, independentemente do conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="b0dfb-123">Se você estiver ciente desses casos, poderá excluir esse texto da análise especificando o texto (RegEx é suportado) e de quais módulos o texto deve ser excluído.</span><span class="sxs-lookup"><span data-stu-id="b0dfb-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>