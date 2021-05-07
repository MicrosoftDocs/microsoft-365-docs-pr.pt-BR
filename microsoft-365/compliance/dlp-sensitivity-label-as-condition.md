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
ms.openlocfilehash: 19bd80de225f703b5c280163e94826498fa097bd
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876290"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies"></a><span data-ttu-id="f377a-103">Use rótulos de confidencialidade como condições em políticas DLP</span><span class="sxs-lookup"><span data-stu-id="f377a-103">Use sensitivity labels as conditions in DLP policies</span></span>

<span data-ttu-id="f377a-104">Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:</span><span class="sxs-lookup"><span data-stu-id="f377a-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="f377a-105">Mensagens de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f377a-105">Exchange Online email messages</span></span>
- <span data-ttu-id="f377a-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f377a-106">SharePoint Online</span></span>
- <span data-ttu-id="f377a-107">Sites do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f377a-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="f377a-108">Dispositivos do Windows 10</span><span class="sxs-lookup"><span data-stu-id="f377a-108">Windows 10 devices</span></span>

<span data-ttu-id="f377a-109">Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.</span><span class="sxs-lookup"><span data-stu-id="f377a-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f377a-110">![rótulo de confidencialidade como condição](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="f377a-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f377a-111">Como condição, os **Rótulos de Confidencialidade** não estarão disponíveis se você tiver selecionado o **chat do Teams e as mensagens do canal** como um local para aplicar a política DLP.</span><span class="sxs-lookup"><span data-stu-id="f377a-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="f377a-112">Itens com suporte, cenários e dicas de política</span><span class="sxs-lookup"><span data-stu-id="f377a-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="f377a-113">Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.</span><span class="sxs-lookup"><span data-stu-id="f377a-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="f377a-114">Itens com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-114">Supported items</span></span>

|<span data-ttu-id="f377a-115">Serviço</span><span class="sxs-lookup"><span data-stu-id="f377a-115">Service</span></span>  |<span data-ttu-id="f377a-116">Tipo de item</span><span class="sxs-lookup"><span data-stu-id="f377a-116">Item type</span></span>  |<span data-ttu-id="f377a-117">Disponível para a dica de política</span><span class="sxs-lookup"><span data-stu-id="f377a-117">Available to policy tip</span></span>  |<span data-ttu-id="f377a-118">Aplicável</span><span class="sxs-lookup"><span data-stu-id="f377a-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="f377a-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="f377a-119">Exchange</span></span>    |<span data-ttu-id="f377a-120">mensagem de email</span><span class="sxs-lookup"><span data-stu-id="f377a-120">email message</span></span>         |<span data-ttu-id="f377a-121">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-121">yes</span></span>         |<span data-ttu-id="f377a-122">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-122">yes</span></span>         |
|<span data-ttu-id="f377a-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="f377a-123">Exchange</span></span>    |<span data-ttu-id="f377a-124">anexos de email</span><span class="sxs-lookup"><span data-stu-id="f377a-124">email attachment</span></span>         |<span data-ttu-id="f377a-125">não \*</span><span class="sxs-lookup"><span data-stu-id="f377a-125">no \*</span></span>         |<span data-ttu-id="f377a-126">sim \*</span><span class="sxs-lookup"><span data-stu-id="f377a-126">yes \*</span></span>         |
|<span data-ttu-id="f377a-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f377a-127">SharePoint Online</span></span>     |<span data-ttu-id="f377a-128">itens no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f377a-128">items in SharePoint Online</span></span>         |<span data-ttu-id="f377a-129">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-129">yes</span></span>         |<span data-ttu-id="f377a-130">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-130">yes</span></span>         |
|<span data-ttu-id="f377a-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f377a-131">OneDrive for Business</span></span>     |<span data-ttu-id="f377a-132">itens</span><span class="sxs-lookup"><span data-stu-id="f377a-132">items</span></span>         |<span data-ttu-id="f377a-133">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-133">yes</span></span>         |<span data-ttu-id="f377a-134">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-134">yes</span></span>         |
|<span data-ttu-id="f377a-135">Teams</span><span class="sxs-lookup"><span data-stu-id="f377a-135">Teams</span></span>     |<span data-ttu-id="f377a-136">Teams e mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="f377a-136">Teams and channel messages</span></span>         |<span data-ttu-id="f377a-137">não se aplica</span><span class="sxs-lookup"><span data-stu-id="f377a-137">not applicable</span></span>         |<span data-ttu-id="f377a-138">não se aplica</span><span class="sxs-lookup"><span data-stu-id="f377a-138">not applicable</span></span>         |
|<span data-ttu-id="f377a-139">Teams</span><span class="sxs-lookup"><span data-stu-id="f377a-139">Teams</span></span>     |<span data-ttu-id="f377a-140">anexos</span><span class="sxs-lookup"><span data-stu-id="f377a-140">attachments</span></span>         |<span data-ttu-id="f377a-141">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="f377a-141">yes \*\*</span></span>         |<span data-ttu-id="f377a-142">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="f377a-142">yes \*\*</span></span>         |
|<span data-ttu-id="f377a-143">Dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="f377a-143">Windows 10 devices</span></span>     |<span data-ttu-id="f377a-144">itens</span><span class="sxs-lookup"><span data-stu-id="f377a-144">items</span></span>         |<span data-ttu-id="f377a-145">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-145">yes</span></span>         |<span data-ttu-id="f377a-146">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-146">yes</span></span>         |
|<span data-ttu-id="f377a-147">MCAS (visualização)</span><span class="sxs-lookup"><span data-stu-id="f377a-147">MCAS (preview)</span></span> |<span data-ttu-id="f377a-148">itens</span><span class="sxs-lookup"><span data-stu-id="f377a-148">items</span></span>         |<span data-ttu-id="f377a-149">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-149">yes</span></span>         |<span data-ttu-id="f377a-150">sim</span><span class="sxs-lookup"><span data-stu-id="f377a-150">yes</span></span>         |

<span data-ttu-id="f377a-151">\* A detecção de DLP e a aplicação de rótulos de confidencialidade em emails e anexos são suportados em trânsito.</span><span class="sxs-lookup"><span data-stu-id="f377a-151">\* DLP detection and enforcement of sensitivity labels on emails and attachments are supported in-transit.</span></span> <span data-ttu-id="f377a-152">As dicas de política DLP de rotulagem de confidencialidade não são anexos de email.</span><span class="sxs-lookup"><span data-stu-id="f377a-152">DLP policy tips of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="f377a-153">\*\* Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o OneDrive for Business e para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f377a-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="f377a-154">Portanto, se o SharePoint Online ou OneDrive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição.</span><span class="sxs-lookup"><span data-stu-id="f377a-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="f377a-155">O Teams como local não precisa ser selecionado na política de DLP.</span><span class="sxs-lookup"><span data-stu-id="f377a-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="f377a-156">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-156">Supported scenarios</span></span>

- <span data-ttu-id="f377a-157">O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f377a-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="f377a-158">Como condição, o uso de rótulos de confidencialidade tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima.</span><span class="sxs-lookup"><span data-stu-id="f377a-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="f377a-159">As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f377a-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="f377a-160">Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.</span><span class="sxs-lookup"><span data-stu-id="f377a-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="f377a-161">Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="f377a-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="f377a-162">Dicas de política com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-162">Support policy tips</span></span>


|<span data-ttu-id="f377a-163">Carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="f377a-163">Workload</span></span>  |<span data-ttu-id="f377a-164">Dicas de política com suporte/sem suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="f377a-165">OWA</span><span class="sxs-lookup"><span data-stu-id="f377a-165">OWA</span></span> |    <span data-ttu-id="f377a-166">com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-166">supported</span></span>     |
|<span data-ttu-id="f377a-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="f377a-167">Outlook Win 32</span></span>    |  <span data-ttu-id="f377a-168">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="f377a-168">not supported</span></span>       |
|<span data-ttu-id="f377a-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f377a-169">SharePoint</span></span>   |   <span data-ttu-id="f377a-170">com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-170">supported</span></span>      |
|<span data-ttu-id="f377a-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f377a-171">OneDrive for Business</span></span>    |    <span data-ttu-id="f377a-172">com suporte</span><span class="sxs-lookup"><span data-stu-id="f377a-172">supported</span></span>     |
|<span data-ttu-id="f377a-173">dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="f377a-173">endpoint devices</span></span>   |  <span data-ttu-id="f377a-174">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="f377a-174">not supported</span></span>       |
