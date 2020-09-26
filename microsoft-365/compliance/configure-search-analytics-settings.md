---
title: Definir configurações de pesquisa e análise – investigações de dados
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
description: Saiba como definir as configurações de pesquisa e análise, como duplicatas, encadeamentos de email e temas ao gerenciar investigações de dados.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebc04e68c4d8854c91ceae75b164cc061e77aad4
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277071"
---
# <a name="configure-search-and-analytics-settings-in-data-investigations"></a><span data-ttu-id="2d302-103">Definir as configurações de pesquisa e análise em investigações de dados</span><span class="sxs-lookup"><span data-stu-id="2d302-103">Configure search and analytics settings in Data Investigations</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="2d302-104">Duplicados próximos e threads de email</span><span class="sxs-lookup"><span data-stu-id="2d302-104">Near duplicates and email threading</span></span>

<span data-ttu-id="2d302-105">Nesta seção, você pode definir parâmetros para detecção de duplicidades, detecção de duplicidade próxima e thread de email.</span><span class="sxs-lookup"><span data-stu-id="2d302-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="2d302-106">Enable/disable: incluir a detecção de duplicidades, a detecção de duplicidade próxima e o encadeamento de email como parte do fluxo de análise, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="2d302-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="2d302-107">Como eles se baseiam uns dos outros, você deve habilitar todos eles ou desabilitá-los.</span><span class="sxs-lookup"><span data-stu-id="2d302-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="2d302-108">Limite: se o nível de similaridade de dois documentos estiver acima do limite, ele será colocado no mesmo conjunto próximo duplicado.</span><span class="sxs-lookup"><span data-stu-id="2d302-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="2d302-109">Ocultar duplicatas por padrão: se essa configuração estiver ativada, um filtro para ocultar documentos duplicados será aplicado no conjunto de trabalho por padrão.</span><span class="sxs-lookup"><span data-stu-id="2d302-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="2d302-110">O filtro pode ser removido manualmente no conjunto de trabalho, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2d302-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="2d302-111">Número mínimo/máximo de palavras: próximas duplicatas e o encadeamento de emails será executado somente em documentos que tenham pelo menos o número mínimo de palavras e, no máximo, o número máximo de palavras.</span><span class="sxs-lookup"><span data-stu-id="2d302-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="2d302-112">Para obter mais informações, consulte [Near Duplicate Detection](near-duplicates.md) and [e-mail Threading](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="2d302-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="2d302-113">Temas</span><span class="sxs-lookup"><span data-stu-id="2d302-113">Themes</span></span>

<span data-ttu-id="2d302-114">Nesta seção, você pode definir parâmetros para temas.</span><span class="sxs-lookup"><span data-stu-id="2d302-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="2d302-115">Enable/disable: incluir agrupamento de temas como parte do fluxo de análise, se habilitado.</span><span class="sxs-lookup"><span data-stu-id="2d302-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="2d302-116">Ajustar o número máximo de temas dinamicamente: em determinados casos, não há documentos suficientes para produzir o número desejado de temas.</span><span class="sxs-lookup"><span data-stu-id="2d302-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="2d302-117">Se essa configuração estiver ativada, em vez de tentar forçar o número máximo de temas desejado, o sistema ajustará o número máximo de temas dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="2d302-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="2d302-118">Número máximo de temas: número desejado de temas.</span><span class="sxs-lookup"><span data-stu-id="2d302-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="2d302-119">Incluir números em temas: quando habilitado, ele incluirá números ao gerar temas.</span><span class="sxs-lookup"><span data-stu-id="2d302-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="2d302-120">Reconhecimento óptico de caracteres (OCR)</span><span class="sxs-lookup"><span data-stu-id="2d302-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="2d302-121">Quando essa configuração estiver ativada, o OCR será executado em imagens que são incluídas em conjuntos de trabalho para que possam ser pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="2d302-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="2d302-122">Ignorar texto</span><span class="sxs-lookup"><span data-stu-id="2d302-122">Ignore text</span></span>

<span data-ttu-id="2d302-123">Há situações em que determinados textos reduzirão a qualidade da análise, como avisos de isenção de responsabilidade longos que são adicionados a certos emails, independentemente do conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="2d302-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="2d302-124">Se você estiver ciente desses casos, poderá excluir esse texto da análise especificando o texto (RegEx é suportado) e de quais módulos o texto deve ser excluído.</span><span class="sxs-lookup"><span data-stu-id="2d302-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
