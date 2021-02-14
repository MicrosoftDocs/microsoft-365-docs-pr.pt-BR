---
title: Configurar marcas inteligentes na Descoberta Inteligente Avançada
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
ROBOTS: NOINDEX, NOFOLLOW
description: As marcas inteligentes permitem que você aplique os recursos de aprendizado de máquina ao analisar o conteúdo em um caso de Descoberta Eletrônica Avançada. Use grupos de marca inteligente para exibir os resultados de modelos de detecção de aprendizado de máquina, como o modelo de privilégio advogado-cliente.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081078"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a><span data-ttu-id="2b718-104">Configurar marcas inteligentes na Descoberta Inteligente Avançada</span><span class="sxs-lookup"><span data-stu-id="2b718-104">Set up smart tags in Advanced eDiscovery</span></span>

<span data-ttu-id="2b718-105">Os recursos de aprendizado de máquina (ML) na Descoberta Eletrônica Avançada podem ajudá-lo a tornar o processo de decisão mais eficiente ao analisar documentos de caso em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2b718-105">Machine learning (ML) capabilities in Advanced eDiscovery can help you make the decision process more efficient when reviewing case documents in a review set.</span></span> <span data-ttu-id="2b718-106">As marcas inteligentes são uma maneira de trazer os recursos ml para onde as decisões são registradas: ao marcar documentos durante a revisão.</span><span class="sxs-lookup"><span data-stu-id="2b718-106">Smart tags are a way to bring the ML capabilities to where the decisions are recorded: when tagging documents during review.</span></span> <span data-ttu-id="2b718-107">Quando você cria um grupo de marcas inteligentes, as decisões que são o resultado do modelo ML que você associou ao grupo de marcas inteligentes são exibidas em linha com as marcas no grupo de marcas.</span><span class="sxs-lookup"><span data-stu-id="2b718-107">When you create a smart tag group, then the decisions that are the result of the ML model that you've associated with the smart tag group are displayed in-line with the tags in the tag group.</span></span> <span data-ttu-id="2b718-108">Isso ajuda a ver as informações de resultados do ML em linha quando você estiver revendo documentos específicos.</span><span class="sxs-lookup"><span data-stu-id="2b718-108">This helps see the ML results information in-line when you're reviewing specific documents.</span></span>

## <a name="how-to-set-up-a-smart-tag-group"></a><span data-ttu-id="2b718-109">Como configurar um grupo de marca inteligente</span><span class="sxs-lookup"><span data-stu-id="2b718-109">How to set up a smart tag group</span></span>

1. <span data-ttu-id="2b718-110">Em um conjunto de revisão, clique em **Gerenciar conjunto de revisão** e clique em Gerenciar **marcas.**</span><span class="sxs-lookup"><span data-stu-id="2b718-110">In a review set, click **Manage review set** and then click **Manage tags**.</span></span>

2. <span data-ttu-id="2b718-111">Clique **em Adicionar grupo de marca** e selecione Adicionar grupo de marca **inteligente.**</span><span class="sxs-lookup"><span data-stu-id="2b718-111">Click **Add tag group** and then select **Add smart tag group**.</span></span>

3. <span data-ttu-id="2b718-112">Selecione o modelo ML que você deseja associar ao grupo de marcações.</span><span class="sxs-lookup"><span data-stu-id="2b718-112">Select the ML model that you want to associate to the tag group.</span></span>
    
   <span data-ttu-id="2b718-113">Isso cria um grupo de marcas *e N* marcas filho, *onde N* é o número de possíveis saídas do modelo.</span><span class="sxs-lookup"><span data-stu-id="2b718-113">This creates a tag group and *N* child tags, where *N* is the number of possible outputs of the model.</span></span> <span data-ttu-id="2b718-114">Por exemplo, o [modelo de detecção de privilégio advogado-cliente](attorney-privilege-detection.md) tem duas saídas possíveis:</span><span class="sxs-lookup"><span data-stu-id="2b718-114">For example, the [attorney-client privilege detection model](attorney-privilege-detection.md) has two possible outputs:</span></span> 

   - <span data-ttu-id="2b718-115">**Positivo** – Use para marcar documentos que contenham conteúdo advogado-cliente privilegiado.</span><span class="sxs-lookup"><span data-stu-id="2b718-115">**Positive** – Use to tag documents that contain attorney-client privileged content.</span></span>
   
   - <span data-ttu-id="2b718-116">**Negativo** – Use para marcar documentos que não contenham conteúdo privilegiado advogado-cliente.</span><span class="sxs-lookup"><span data-stu-id="2b718-116">**Negative** – Use to tag documents that don't contain attorney-client privileged content.</span></span>
    
    <span data-ttu-id="2b718-117">Se você selecionar esse modelo, um grupo de marcas com duas marcas filho será criado (uma marca filho denominada **Positivo** e a outra com o nome **Negativo**) para o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2b718-117">If you select this model, a tag group with two child tags is created (one child tag named **Positive** and the other named **Negative**) for the review set.</span></span> <span data-ttu-id="2b718-118">Neste exemplo, cada marca filha corresponde a uma das possíveis saídas do modelo de detecção de privilégio advogado-cliente.</span><span class="sxs-lookup"><span data-stu-id="2b718-118">In this example, each child tag corresponds to one of the possible outputs from the attorney-client privilege detection model.</span></span>

4. <span data-ttu-id="2b718-119">Opcionalmente, você pode renomear o grupo de marcas e as marcas filho.</span><span class="sxs-lookup"><span data-stu-id="2b718-119">Optionally, you can rename the tag group and the child tags.</span></span> <span data-ttu-id="2b718-120">Por exemplo, você poderia renomear **a marca Positiva** como **Privileged** e a **marca Negative** como Not **privileged**.</span><span class="sxs-lookup"><span data-stu-id="2b718-120">For example, you could rename the **Positive** tag to **Privileged** and the **Negative** tag to **Not privileged**.</span></span>

## <a name="how-to-use-smart-tags"></a><span data-ttu-id="2b718-121">Como usar marcas inteligentes</span><span class="sxs-lookup"><span data-stu-id="2b718-121">How to use smart tags</span></span>

<span data-ttu-id="2b718-122">Ao analisar um documento, os resultados do modelo são exibidos ao lado da marca filha apropriada.</span><span class="sxs-lookup"><span data-stu-id="2b718-122">When reviewing a document, the model's results are displayed next to the appropriate child tag.</span></span> <span data-ttu-id="2b718-123">Por exemplo, se você tiver um grupo de marca inteligente para detecção de privilégio advogado-cliente e revisar um documento potencialmente privilegiado, o motivo dessa conclusão será exibido ao lado da marca apropriada.</span><span class="sxs-lookup"><span data-stu-id="2b718-123">For example, if you have a smart tag group for attorney-client privilege detection and you review a document that is potentially privileged, the reason for that conclusion is displayed next to the appropriate tag.</span></span> <span data-ttu-id="2b718-124">É importante observar que a marca não é aplicada automaticamente ao documento.</span><span class="sxs-lookup"><span data-stu-id="2b718-124">It's important to note that the tag isn't automatically applied to the document.</span></span> <span data-ttu-id="2b718-125">O revistor toma a decisão sobre como marcar o documento.</span><span class="sxs-lookup"><span data-stu-id="2b718-125">The reviewer makes the decision about how to tag the document.</span></span>
