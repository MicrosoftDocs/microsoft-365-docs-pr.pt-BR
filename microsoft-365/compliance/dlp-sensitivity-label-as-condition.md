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
ms.openlocfilehash: b33e6704a3311740c1e386f77f1c751382ee6958
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651087"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="f0eec-103">Use rótulos de confidencialidade como condições em políticas DLP</span><span class="sxs-lookup"><span data-stu-id="f0eec-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="f0eec-104">Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:</span><span class="sxs-lookup"><span data-stu-id="f0eec-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="f0eec-105">Mensagens de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f0eec-105">Exchange Online email messages</span></span>
- <span data-ttu-id="f0eec-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f0eec-106">SharePoint Online</span></span>
- <span data-ttu-id="f0eec-107">Sites do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f0eec-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="f0eec-108">Dispositivos do Windows 10</span><span class="sxs-lookup"><span data-stu-id="f0eec-108">Windows 10 devices</span></span>

<span data-ttu-id="f0eec-109">Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.</span><span class="sxs-lookup"><span data-stu-id="f0eec-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f0eec-110">![rótulo de confidencialidade como condição](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="f0eec-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0eec-111">Como condição, os **Rótulos de Confidencialidade** não estarão disponíveis se você tiver selecionado o **chat do Teams e as mensagens do canal** como um local para aplicar a política DLP.</span><span class="sxs-lookup"><span data-stu-id="f0eec-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="f0eec-112">Itens com suporte, cenários e dicas de política</span><span class="sxs-lookup"><span data-stu-id="f0eec-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="f0eec-113">Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.</span><span class="sxs-lookup"><span data-stu-id="f0eec-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="f0eec-114">Itens com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-114">Supported items</span></span>

|<span data-ttu-id="f0eec-115">Serviço</span><span class="sxs-lookup"><span data-stu-id="f0eec-115">Service</span></span>  |<span data-ttu-id="f0eec-116">Tipo de item</span><span class="sxs-lookup"><span data-stu-id="f0eec-116">Item type</span></span>  |<span data-ttu-id="f0eec-117">Disponível para a dica de política</span><span class="sxs-lookup"><span data-stu-id="f0eec-117">Available to policy tip</span></span>  |<span data-ttu-id="f0eec-118">Aplicável</span><span class="sxs-lookup"><span data-stu-id="f0eec-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f0eec-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="f0eec-119">Exchange</span></span>    |<span data-ttu-id="f0eec-120">mensagem de email</span><span class="sxs-lookup"><span data-stu-id="f0eec-120">email message</span></span>         |<span data-ttu-id="f0eec-121">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-121">yes</span></span>         |<span data-ttu-id="f0eec-122">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-122">yes</span></span>         |
|<span data-ttu-id="f0eec-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="f0eec-123">Exchange</span></span>    |<span data-ttu-id="f0eec-124">anexos de email</span><span class="sxs-lookup"><span data-stu-id="f0eec-124">email attachment</span></span>         |<span data-ttu-id="f0eec-125">não</span><span class="sxs-lookup"><span data-stu-id="f0eec-125">no</span></span>         |<span data-ttu-id="f0eec-126">sim \*</span><span class="sxs-lookup"><span data-stu-id="f0eec-126">yes \*</span></span>         |
|<span data-ttu-id="f0eec-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f0eec-127">SharePoint Online</span></span>     |<span data-ttu-id="f0eec-128">itens no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f0eec-128">items in SharePoint Online</span></span>         |<span data-ttu-id="f0eec-129">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-129">yes</span></span>         |<span data-ttu-id="f0eec-130">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-130">yes</span></span>         |
|<span data-ttu-id="f0eec-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f0eec-131">OneDrive for Business</span></span>     |<span data-ttu-id="f0eec-132">itens</span><span class="sxs-lookup"><span data-stu-id="f0eec-132">items</span></span>         |<span data-ttu-id="f0eec-133">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-133">yes</span></span>         |<span data-ttu-id="f0eec-134">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-134">yes</span></span>         |
|<span data-ttu-id="f0eec-135">Teams</span><span class="sxs-lookup"><span data-stu-id="f0eec-135">Teams</span></span>     |<span data-ttu-id="f0eec-136">Teams e mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="f0eec-136">Teams and channel messages</span></span>         |<span data-ttu-id="f0eec-137">não se aplica</span><span class="sxs-lookup"><span data-stu-id="f0eec-137">not applicable</span></span>         |<span data-ttu-id="f0eec-138">não se aplica</span><span class="sxs-lookup"><span data-stu-id="f0eec-138">not applicable</span></span>         |
|<span data-ttu-id="f0eec-139">Teams</span><span class="sxs-lookup"><span data-stu-id="f0eec-139">Teams</span></span>     |<span data-ttu-id="f0eec-140">anexos</span><span class="sxs-lookup"><span data-stu-id="f0eec-140">attachments</span></span>         |<span data-ttu-id="f0eec-141">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="f0eec-141">yes \*\*</span></span>         |<span data-ttu-id="f0eec-142">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="f0eec-142">yes \*\*</span></span>         |
|<span data-ttu-id="f0eec-143">Dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="f0eec-143">Windows 10 devices</span></span>     |<span data-ttu-id="f0eec-144">itens</span><span class="sxs-lookup"><span data-stu-id="f0eec-144">items</span></span>         |<span data-ttu-id="f0eec-145">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-145">yes</span></span>         |<span data-ttu-id="f0eec-146">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-146">yes</span></span>         |
|<span data-ttu-id="f0eec-147">MCAS (visualização)</span><span class="sxs-lookup"><span data-stu-id="f0eec-147">MCAS (preview)</span></span> |<span data-ttu-id="f0eec-148">itens</span><span class="sxs-lookup"><span data-stu-id="f0eec-148">items</span></span>         |<span data-ttu-id="f0eec-149">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-149">yes</span></span>         |<span data-ttu-id="f0eec-150">sim</span><span class="sxs-lookup"><span data-stu-id="f0eec-150">yes</span></span>         |

<span data-ttu-id="f0eec-151">\* A detecção de DLP de anexos de email rotulados como confidenciais são compatíveis apenas com tipos de arquivos do Office.</span><span class="sxs-lookup"><span data-stu-id="f0eec-151">\* DLP detection of sensitivity labeled email attachments are supported for Office file types only.</span></span>

<span data-ttu-id="f0eec-152">\*\* Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o OneDrive for Business e para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f0eec-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="f0eec-153">Portanto, se o SharePoint Online ou OneDrive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição.</span><span class="sxs-lookup"><span data-stu-id="f0eec-153">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="f0eec-154">O Teams como local não precisa ser selecionado na política de DLP.</span><span class="sxs-lookup"><span data-stu-id="f0eec-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="f0eec-155">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-155">Supported scenarios</span></span>

- <span data-ttu-id="f0eec-156">O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f0eec-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="f0eec-157">Como condição, o uso de rótulos de confidencialidade tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima.</span><span class="sxs-lookup"><span data-stu-id="f0eec-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="f0eec-158">As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f0eec-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="f0eec-159">Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.</span><span class="sxs-lookup"><span data-stu-id="f0eec-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="f0eec-160">Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f0eec-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="f0eec-161">Dicas de política com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-161">Support policy tips</span></span>


|<span data-ttu-id="f0eec-162">Carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f0eec-162">Workload</span></span>  |<span data-ttu-id="f0eec-163">Dicas de política com suporte/sem suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-163">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="f0eec-164">OWA</span><span class="sxs-lookup"><span data-stu-id="f0eec-164">OWA</span></span> |    <span data-ttu-id="f0eec-165">com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-165">supported</span></span>     |
|<span data-ttu-id="f0eec-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="f0eec-166">Outlook Win 32</span></span>    |  <span data-ttu-id="f0eec-167">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="f0eec-167">not supported</span></span>       |
|<span data-ttu-id="f0eec-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f0eec-168">SharePoint</span></span>   |   <span data-ttu-id="f0eec-169">com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-169">supported</span></span>      |
|<span data-ttu-id="f0eec-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f0eec-170">OneDrive for Business</span></span>    |    <span data-ttu-id="f0eec-171">com suporte</span><span class="sxs-lookup"><span data-stu-id="f0eec-171">supported</span></span>     |
|<span data-ttu-id="f0eec-172">dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f0eec-172">endpoint devices</span></span>   |  <span data-ttu-id="f0eec-173">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="f0eec-173">not supported</span></span>       |
