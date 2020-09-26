---
title: Usar rótulos de confidencialidade como condições em políticas DLP (visualização)
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
ms.openlocfilehash: bb06ed6919a396bef1e5d1f1cb04731fa11267ae
ms.sourcegitcommit: c1ee4ed3c5826872b57339e1e1aa33b4d2209711
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48235709"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="e3648-103">Usar rótulos de confidencialidade como condições em políticas DLP (visualização)</span><span class="sxs-lookup"><span data-stu-id="e3648-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="e3648-104">Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:</span><span class="sxs-lookup"><span data-stu-id="e3648-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="e3648-105">Mensagens de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e3648-105">Exchange Online email messages</span></span>
- <span data-ttu-id="e3648-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3648-106">SharePoint Online</span></span>
- <span data-ttu-id="e3648-107">Sites do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e3648-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="e3648-108">Dispositivos do Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3648-108">Windows 10 devices</span></span>

<span data-ttu-id="e3648-109">Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.</span><span class="sxs-lookup"><span data-stu-id="e3648-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

![rótulo de confidencialidade como uma condição](../media/dlp-sensitivity-label-as-a-condition.png)

## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="e3648-111">Itens com suporte, cenários e dicas de política</span><span class="sxs-lookup"><span data-stu-id="e3648-111">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="e3648-112">Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.</span><span class="sxs-lookup"><span data-stu-id="e3648-112">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="e3648-113">Itens com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-113">Supported items</span></span>

|<span data-ttu-id="e3648-114">serviço</span><span class="sxs-lookup"><span data-stu-id="e3648-114">service</span></span>  |<span data-ttu-id="e3648-115">tipo de item</span><span class="sxs-lookup"><span data-stu-id="e3648-115">item type</span></span>  |<span data-ttu-id="e3648-116">disponível para a dica de política</span><span class="sxs-lookup"><span data-stu-id="e3648-116">available to policy tip</span></span>  |<span data-ttu-id="e3648-117">aplicável</span><span class="sxs-lookup"><span data-stu-id="e3648-117">enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e3648-118">Exchange</span><span class="sxs-lookup"><span data-stu-id="e3648-118">Exchange</span></span>    |<span data-ttu-id="e3648-119">mensagem de email</span><span class="sxs-lookup"><span data-stu-id="e3648-119">email message</span></span>         |<span data-ttu-id="e3648-120">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-120">yes</span></span>         |<span data-ttu-id="e3648-121">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-121">yes</span></span>         |
|<span data-ttu-id="e3648-122">Exchange</span><span class="sxs-lookup"><span data-stu-id="e3648-122">Exchange</span></span>    |<span data-ttu-id="e3648-123">anexos de email</span><span class="sxs-lookup"><span data-stu-id="e3648-123">email attachment</span></span>         |<span data-ttu-id="e3648-124">não \*</span><span class="sxs-lookup"><span data-stu-id="e3648-124">no \*</span></span>         |<span data-ttu-id="e3648-125">não \*</span><span class="sxs-lookup"><span data-stu-id="e3648-125">no \*</span></span>         |
|<span data-ttu-id="e3648-126">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3648-126">SharePoint Online</span></span>     |<span data-ttu-id="e3648-127">itens no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e3648-127">items in SharePoint Online</span></span>         |<span data-ttu-id="e3648-128">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-128">yes</span></span>         |<span data-ttu-id="e3648-129">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-129">yes</span></span>         |
|<span data-ttu-id="e3648-130">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e3648-130">OneDrive for Business</span></span>     |<span data-ttu-id="e3648-131">itens</span><span class="sxs-lookup"><span data-stu-id="e3648-131">items</span></span>         |<span data-ttu-id="e3648-132">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-132">yes</span></span>         |<span data-ttu-id="e3648-133">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-133">yes</span></span>         |
|<span data-ttu-id="e3648-134">Teams</span><span class="sxs-lookup"><span data-stu-id="e3648-134">Teams</span></span>     |<span data-ttu-id="e3648-135">Teams e mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="e3648-135">Teams and channel messages</span></span>         |<span data-ttu-id="e3648-136">não se aplica</span><span class="sxs-lookup"><span data-stu-id="e3648-136">not applicable</span></span>         |<span data-ttu-id="e3648-137">não se aplica</span><span class="sxs-lookup"><span data-stu-id="e3648-137">not applicable</span></span>         |
|<span data-ttu-id="e3648-138">Teams</span><span class="sxs-lookup"><span data-stu-id="e3648-138">Teams</span></span>     |<span data-ttu-id="e3648-139">anexos</span><span class="sxs-lookup"><span data-stu-id="e3648-139">attachements</span></span>         |<span data-ttu-id="e3648-140">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="e3648-140">yes \*\*</span></span>         |<span data-ttu-id="e3648-141">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="e3648-141">yes \*\*</span></span>         |
|<span data-ttu-id="e3648-142">Dispositivos do Windows 10 (visualização)</span><span class="sxs-lookup"><span data-stu-id="e3648-142">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="e3648-143">itens</span><span class="sxs-lookup"><span data-stu-id="e3648-143">items</span></span>         |<span data-ttu-id="e3648-144">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-144">yes</span></span>         |<span data-ttu-id="e3648-145">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-145">yes</span></span>         |
|<span data-ttu-id="e3648-146">MCAS (visualização)</span><span class="sxs-lookup"><span data-stu-id="e3648-146">MCAS (preview)</span></span> |<span data-ttu-id="e3648-147">itens</span><span class="sxs-lookup"><span data-stu-id="e3648-147">items</span></span>         |<span data-ttu-id="e3648-148">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-148">yes</span></span>         |<span data-ttu-id="e3648-149">sim</span><span class="sxs-lookup"><span data-stu-id="e3648-149">yes</span></span>         |

<span data-ttu-id="e3648-150">\* A detecção de DLP de rótulos de confidencialidade em emails possui suporte.</span><span class="sxs-lookup"><span data-stu-id="e3648-150">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="e3648-151">A detecção de DLP de anexos de email rotulados como confidenciais não.</span><span class="sxs-lookup"><span data-stu-id="e3648-151">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="e3648-152">\*\* Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o One Drive for Business e para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="e3648-152">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to One drive for business and SharePoint.</span></span> <span data-ttu-id="e3648-153">Portanto, se o SharePoint Online ou One Drive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição.</span><span class="sxs-lookup"><span data-stu-id="e3648-153">So if SharePoint Online or One Drive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="e3648-154">O Teams como local não precisa ser selecionado na política de DLP.</span><span class="sxs-lookup"><span data-stu-id="e3648-154">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="e3648-155">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-155">Supported scenarios</span></span>

- <span data-ttu-id="e3648-156">O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="e3648-156">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>
- <span data-ttu-id="e3648-157">O uso de rótulos de confidencialidade como uma condição tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima</span><span class="sxs-lookup"><span data-stu-id="e3648-157">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above</span></span>
- <span data-ttu-id="e3648-158">As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="e3648-158">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>
- <span data-ttu-id="e3648-159">Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.</span><span class="sxs-lookup"><span data-stu-id="e3648-159">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>
- <span data-ttu-id="e3648-160">Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="e3648-160">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="e3648-161">Dicas de política com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-161">Support policy tips</span></span>


|<span data-ttu-id="e3648-162">carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="e3648-162">workload</span></span>  |<span data-ttu-id="e3648-163">dicas de política com suporte/sem suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-163">policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="e3648-164">OWA</span><span class="sxs-lookup"><span data-stu-id="e3648-164">OWA</span></span> |    <span data-ttu-id="e3648-165">com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-165">supported</span></span>     |
|<span data-ttu-id="e3648-166">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="e3648-166">Outlook Win 32</span></span>    |  <span data-ttu-id="e3648-167">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="e3648-167">not supported</span></span>       |
|<span data-ttu-id="e3648-168">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e3648-168">SharePoint</span></span>   |   <span data-ttu-id="e3648-169">com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-169">supported</span></span>      |
|<span data-ttu-id="e3648-170">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="e3648-170">OneDrive for Business</span></span>    |    <span data-ttu-id="e3648-171">com suporte</span><span class="sxs-lookup"><span data-stu-id="e3648-171">supported</span></span>     |
|<span data-ttu-id="e3648-172">dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e3648-172">endpoint devices</span></span>   |  <span data-ttu-id="e3648-173">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="e3648-173">not supported</span></span>       |
