---
title: Use rótulos de confidencialidade como condições em políticas DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: saiba mais sobre os serviços e os tipos de item que você pode usar rótulos de confidencialidade como condições em políticas DLP
ms.openlocfilehash: 94d5e9f53471f6113dcc755995a3f94e95a58e53
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779838"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="73d2b-103">Use rótulos de confidencialidade como condições em políticas DLP</span><span class="sxs-lookup"><span data-stu-id="73d2b-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="73d2b-104">Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:</span><span class="sxs-lookup"><span data-stu-id="73d2b-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="73d2b-105">Mensagens de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73d2b-105">Exchange Online email messages</span></span>
- <span data-ttu-id="73d2b-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73d2b-106">SharePoint Online</span></span>
- <span data-ttu-id="73d2b-107">Sites do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="73d2b-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="73d2b-108">Dispositivos do Windows 10</span><span class="sxs-lookup"><span data-stu-id="73d2b-108">Windows 10 devices</span></span>

<span data-ttu-id="73d2b-109">Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.</span><span class="sxs-lookup"><span data-stu-id="73d2b-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="73d2b-110">![rótulo de confidencialidade como condição](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="73d2b-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73d2b-111">Como condição, os **Rótulos de Confidencialidade** não estarão disponíveis se você tiver selecionado o **chat do Teams e as mensagens do canal** como um local para aplicar a política DLP.</span><span class="sxs-lookup"><span data-stu-id="73d2b-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="73d2b-112">Itens com suporte, cenários e dicas de política</span><span class="sxs-lookup"><span data-stu-id="73d2b-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="73d2b-113">Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.</span><span class="sxs-lookup"><span data-stu-id="73d2b-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="73d2b-114">Itens com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-114">Supported items</span></span>

|<span data-ttu-id="73d2b-115">Serviço</span><span class="sxs-lookup"><span data-stu-id="73d2b-115">Service</span></span>  |<span data-ttu-id="73d2b-116">Tipo de item</span><span class="sxs-lookup"><span data-stu-id="73d2b-116">Item type</span></span>  |<span data-ttu-id="73d2b-117">Disponível para a dica de política</span><span class="sxs-lookup"><span data-stu-id="73d2b-117">Available to policy tip</span></span>  |<span data-ttu-id="73d2b-118">Aplicável</span><span class="sxs-lookup"><span data-stu-id="73d2b-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="73d2b-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="73d2b-119">Exchange</span></span>    |<span data-ttu-id="73d2b-120">mensagem de email</span><span class="sxs-lookup"><span data-stu-id="73d2b-120">email message</span></span>         |<span data-ttu-id="73d2b-121">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-121">yes</span></span>         |<span data-ttu-id="73d2b-122">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-122">yes</span></span>         |
|<span data-ttu-id="73d2b-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="73d2b-123">Exchange</span></span>    |<span data-ttu-id="73d2b-124">anexos de email</span><span class="sxs-lookup"><span data-stu-id="73d2b-124">email attachment</span></span>         |<span data-ttu-id="73d2b-125">não</span><span class="sxs-lookup"><span data-stu-id="73d2b-125">no</span></span>         |<span data-ttu-id="73d2b-126">sim \*</span><span class="sxs-lookup"><span data-stu-id="73d2b-126">yes \*</span></span>         |
|<span data-ttu-id="73d2b-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73d2b-127">SharePoint Online</span></span>     |<span data-ttu-id="73d2b-128">itens no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="73d2b-128">items in SharePoint Online</span></span>         |<span data-ttu-id="73d2b-129">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-129">yes</span></span>         |<span data-ttu-id="73d2b-130">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-130">yes</span></span>         |
|<span data-ttu-id="73d2b-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="73d2b-131">OneDrive for Business</span></span>     |<span data-ttu-id="73d2b-132">itens</span><span class="sxs-lookup"><span data-stu-id="73d2b-132">items</span></span>         |<span data-ttu-id="73d2b-133">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-133">yes</span></span>         |<span data-ttu-id="73d2b-134">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-134">yes</span></span>         |
|<span data-ttu-id="73d2b-135">Teams</span><span class="sxs-lookup"><span data-stu-id="73d2b-135">Teams</span></span>     |<span data-ttu-id="73d2b-136">Teams e mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="73d2b-136">Teams and channel messages</span></span>         |<span data-ttu-id="73d2b-137">não se aplica</span><span class="sxs-lookup"><span data-stu-id="73d2b-137">not applicable</span></span>         |<span data-ttu-id="73d2b-138">não se aplica</span><span class="sxs-lookup"><span data-stu-id="73d2b-138">not applicable</span></span>         |
|<span data-ttu-id="73d2b-139">Teams</span><span class="sxs-lookup"><span data-stu-id="73d2b-139">Teams</span></span>     |<span data-ttu-id="73d2b-140">anexos</span><span class="sxs-lookup"><span data-stu-id="73d2b-140">attachments</span></span>         |<span data-ttu-id="73d2b-141">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="73d2b-141">yes \*\*</span></span>         |<span data-ttu-id="73d2b-142">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="73d2b-142">yes \*\*</span></span>         |
|<span data-ttu-id="73d2b-143">Dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="73d2b-143">Windows 10 devices</span></span>     |<span data-ttu-id="73d2b-144">itens</span><span class="sxs-lookup"><span data-stu-id="73d2b-144">items</span></span>         |<span data-ttu-id="73d2b-145">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-145">yes</span></span>         |<span data-ttu-id="73d2b-146">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-146">yes</span></span>         |
|<span data-ttu-id="73d2b-147">MCAS (visualização)</span><span class="sxs-lookup"><span data-stu-id="73d2b-147">MCAS (preview)</span></span> |<span data-ttu-id="73d2b-148">itens</span><span class="sxs-lookup"><span data-stu-id="73d2b-148">items</span></span>         |<span data-ttu-id="73d2b-149">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-149">yes</span></span>         |<span data-ttu-id="73d2b-150">sim</span><span class="sxs-lookup"><span data-stu-id="73d2b-150">yes</span></span>         |

<span data-ttu-id="73d2b-151">\* A detecção de DLP de anexos de email rotulados como confidenciais são compatíveis apenas com tipos de arquivos do Office.</span><span class="sxs-lookup"><span data-stu-id="73d2b-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="73d2b-152">\*\* Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o OneDrive for Business e para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="73d2b-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="73d2b-153">Portanto, se o SharePoint Online ou OneDrive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição.</span><span class="sxs-lookup"><span data-stu-id="73d2b-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="73d2b-154">O Teams como local não precisa ser selecionado na política de DLP.</span><span class="sxs-lookup"><span data-stu-id="73d2b-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

> [!NOTE]
> <span data-ttu-id="73d2b-155">A capacidade da DLP para detectar rótulos de sensibilidade no SharePoint e no OneDrive for Business é limitada.</span><span class="sxs-lookup"><span data-stu-id="73d2b-155">DLP's ability to detect sensitivity labels in SharePoint and OneDrive for business is limited.</span></span> <span data-ttu-id="73d2b-156">Para obter mais informações, confira [Habilitar rótulos de confidencialidade para arquivos do Office no Microsoft Office SharePoint Online e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span><span class="sxs-lookup"><span data-stu-id="73d2b-156">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive](sensitivity-labels-sharepoint-onedrive-files.md#limitations).</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="73d2b-157">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-157">Supported scenarios</span></span>

- <span data-ttu-id="73d2b-158">O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="73d2b-158">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="73d2b-159">Como condição, o uso de rótulos de confidencialidade tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima.</span><span class="sxs-lookup"><span data-stu-id="73d2b-159">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="73d2b-160">As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="73d2b-160">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="73d2b-161">Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.</span><span class="sxs-lookup"><span data-stu-id="73d2b-161">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="73d2b-162">Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="73d2b-162">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="73d2b-163">Dicas de política com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-163">Support policy tips</span></span>


|<span data-ttu-id="73d2b-164">Carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="73d2b-164">Workload</span></span>  |<span data-ttu-id="73d2b-165">Dicas de política com suporte/sem suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-165">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="73d2b-166">OWA</span><span class="sxs-lookup"><span data-stu-id="73d2b-166">OWA</span></span> |    <span data-ttu-id="73d2b-167">com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-167">supported</span></span>     |
|<span data-ttu-id="73d2b-168">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="73d2b-168">Outlook Win 32</span></span>    |  <span data-ttu-id="73d2b-169">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="73d2b-169">not supported</span></span>       |
|<span data-ttu-id="73d2b-170">SharePoint</span><span class="sxs-lookup"><span data-stu-id="73d2b-170">SharePoint</span></span>   |   <span data-ttu-id="73d2b-171">com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-171">supported</span></span>      |
|<span data-ttu-id="73d2b-172">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="73d2b-172">OneDrive for Business</span></span>    |    <span data-ttu-id="73d2b-173">com suporte</span><span class="sxs-lookup"><span data-stu-id="73d2b-173">supported</span></span>     |
|<span data-ttu-id="73d2b-174">dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="73d2b-174">endpoint devices</span></span>   |  <span data-ttu-id="73d2b-175">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="73d2b-175">not supported</span></span>       |
