---
title: Definir as configurações avançadas de análise na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: Saiba como definir as configurações avançadas, incluindo as duplicatas, threads de email e temas, para o processo de análise na descoberta eletrônica avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 39d99609cfff92dcd6e6d2f4483076b8bfe808be
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936748"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="b586d-103">Definir as configurações avançadas de análise na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="b586d-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="b586d-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="b586d-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="b586d-106">A descoberta eletrônica avançada fornece parâmetros avançados padrão para analisar configurações de módulo.</span><span class="sxs-lookup"><span data-stu-id="b586d-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="b586d-107">O procedimento a seguir descreve as configurações que podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="b586d-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="b586d-108">Na guia **preparar \> \> configuração de análise** , clique em **Configurações avançadas** (na parte inferior da página).</span><span class="sxs-lookup"><span data-stu-id="b586d-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="b586d-109">O painel a seguir é exibido.</span><span class="sxs-lookup"><span data-stu-id="b586d-109">The following panel is displayed.</span></span> 
    
    ![Definir as configurações avançadas de análise](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="b586d-111">Em **parâmetros Near-Duplicate e threads de email**, selecione valores para os seguintes, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="b586d-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="b586d-112">**Número mínimo de palavras**: o número mínimo de palavras, abaixo do qual um arquivo não é enviado para análise quase duplicada.</span><span class="sxs-lookup"><span data-stu-id="b586d-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="b586d-113">**Número máximo de palavras**: número máximo de palavras, acima do qual um arquivo não é enviado para análise quase duplicada.</span><span class="sxs-lookup"><span data-stu-id="b586d-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="b586d-114">**Similaridade de email**: nível mínimo de aparência de dois emails a serem considerados semelhantes.</span><span class="sxs-lookup"><span data-stu-id="b586d-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="b586d-115">O valor é sempre igual ou maior que a similaridade de documentos.</span><span class="sxs-lookup"><span data-stu-id="b586d-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="b586d-116">O padrão é 90%.</span><span class="sxs-lookup"><span data-stu-id="b586d-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="b586d-117">Em **parâmetros de temas**, marque a caixa de seleção **incluir números na análise de temas** para incluir números no processamento de temas durante a análise.</span><span class="sxs-lookup"><span data-stu-id="b586d-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="b586d-118">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b586d-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="b586d-119">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b586d-119">Related topics</span></span>

[<span data-ttu-id="b586d-120">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="b586d-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="b586d-121">Noções básicas sobre a similaridade de documentos</span><span class="sxs-lookup"><span data-stu-id="b586d-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b586d-122">Configuração das opções de análise</span><span class="sxs-lookup"><span data-stu-id="b586d-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b586d-123">Configuração ignorar texto</span><span class="sxs-lookup"><span data-stu-id="b586d-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="b586d-124">Exibindo resultados de análise</span><span class="sxs-lookup"><span data-stu-id="b586d-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

