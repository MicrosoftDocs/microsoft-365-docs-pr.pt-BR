---
title: Entender a similaridade de documentos na descoberta eletrônica avançada do Office 365
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: 'Revise como o valor de similaridade do documento, o nível mínimo de aparência de dois arquivos a serem considerados próximos duplicados, funciona na descoberta eletrônica avançada do Office 365. '
ms.openlocfilehash: c11359681de4d1e078cde8ebf603396c9a71e3b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597328"
---
# <a name="understand-document-similarity-in-office-365-advanced-ediscovery"></a><span data-ttu-id="27a91-103">Entender a similaridade de documentos na descoberta eletrônica avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="27a91-103">Understand document similarity in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="27a91-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="27a91-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="27a91-106">Na descoberta eletrônica avançada, a similaridade de documentos é o nível mínimo de aparência necessária para dois documentos a serem considerados como duplicatas.</span><span class="sxs-lookup"><span data-stu-id="27a91-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="27a91-107">Para a maioria dos aplicativos de negócios, é recomendável usar um valor de similaridade de 60% a 75%.</span><span class="sxs-lookup"><span data-stu-id="27a91-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="27a91-108">Para material de reconhecimento óptico de caracteres (OCR) de qualidade muito ruim, valores de similaridade menores podem ser aplicados.</span><span class="sxs-lookup"><span data-stu-id="27a91-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="27a91-109">Após a definição e a execução de um determinado caso, o valor de similaridade não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="27a91-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="27a91-110">Dentro de um conjunto Near-Duplicate (ND), pode haver documentos com um nível de aparência abaixo do limite de similaridade.</span><span class="sxs-lookup"><span data-stu-id="27a91-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="27a91-111">Para que um documento ingresse em um conjunto de ND, deve haver pelo menos um documento no conjunto de ND com um nível de semelhante.</span><span class="sxs-lookup"><span data-stu-id="27a91-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="27a91-112">Por exemplo, suponha que a similaridade seja definida como 80%, o documento F1 se parece com o documento F2 em um nível de 85%, e o documento F2 é parecido com o documento F3 em um nível de 90%.</span><span class="sxs-lookup"><span data-stu-id="27a91-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="27a91-113">No entanto, o documento F1 pode se parecer com o documento F3 em um nível de apenas 70%, o que está abaixo do limite.</span><span class="sxs-lookup"><span data-stu-id="27a91-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="27a91-114">No entanto, neste exemplo, os documentos F1, F2 e F3 aparecem no conjunto de um.</span><span class="sxs-lookup"><span data-stu-id="27a91-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="27a91-115">Da mesma forma, usando um valor de similaridade de 80%, podemos criar dois conjuntos, EquiSet-1 e EquiSet-2.</span><span class="sxs-lookup"><span data-stu-id="27a91-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="27a91-116">EquiSet-1 contém documentos E1 e E2.</span><span class="sxs-lookup"><span data-stu-id="27a91-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="27a91-117">Equiset-2 contém documentos F1, F2 e F3.</span><span class="sxs-lookup"><span data-stu-id="27a91-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="27a91-118">Os níveis de semelhança são ilustrados da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="27a91-118">The levels of resemblance are illustrated as follows:</span></span>
  
![Similaridade de documentos](media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="27a91-120">Suponha que outro documento, x1, agora seja inserido.</span><span class="sxs-lookup"><span data-stu-id="27a91-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="27a91-121">A semelhança entre X1 e E3 é de 87%.</span><span class="sxs-lookup"><span data-stu-id="27a91-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="27a91-122">Da mesma forma, a semelhança entre X1 e F1 é de 92%.</span><span class="sxs-lookup"><span data-stu-id="27a91-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="27a91-123">Como resultado, EquiSet-1, EquiSet-2 e X1 agora são combinados em um conjunto de ND.</span><span class="sxs-lookup"><span data-stu-id="27a91-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![Similaridade de documentos](media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="27a91-125">Se houver dois documentos atribuídos a um conjunto de ND, eles permanecerão juntos no mesmo conjunto de ND, mesmo se os documentos adicionais forem adicionados ao conjunto ou se os conjuntos forem mesclados.</span><span class="sxs-lookup"><span data-stu-id="27a91-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="27a91-126">Após a mesclagem dos conjuntos, o documento dinâmico pode ser alterado quando novos documentos são adicionados a um conjunto.</span><span class="sxs-lookup"><span data-stu-id="27a91-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="27a91-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="27a91-127">See also</span></span>

[<span data-ttu-id="27a91-128">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="27a91-128">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="27a91-129">Configuração das opções de análise</span><span class="sxs-lookup"><span data-stu-id="27a91-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="27a91-130">Configuração ignorar texto</span><span class="sxs-lookup"><span data-stu-id="27a91-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="27a91-131">Configuração analisar configurações avançadas</span><span class="sxs-lookup"><span data-stu-id="27a91-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="27a91-132">Exibindo resultados de análise</span><span class="sxs-lookup"><span data-stu-id="27a91-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

