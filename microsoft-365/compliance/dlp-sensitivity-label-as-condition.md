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
ms.openlocfilehash: 2f8eb30e23d722a5e8faf7d0ddaca6b9a94e279b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649630"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a><span data-ttu-id="bc6d8-103">Usar rótulos de confidencialidade como condições em políticas DLP (visualização)</span><span class="sxs-lookup"><span data-stu-id="bc6d8-103">Use sensitivity labels as conditions in DLP policies (preview)</span></span>

<span data-ttu-id="bc6d8-104">Você pode usar os [rótulos de confidencialidade](sensitivity-labels.md) como uma condição nas políticas DLP para esse local:</span><span class="sxs-lookup"><span data-stu-id="bc6d8-104">You can use [sensitivity labels](sensitivity-labels.md) as a condition in DLP policies for these location:</span></span>

- <span data-ttu-id="bc6d8-105">Mensagens de email do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bc6d8-105">Exchange Online email messages</span></span>
- <span data-ttu-id="bc6d8-106">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bc6d8-106">SharePoint Online</span></span>
- <span data-ttu-id="bc6d8-107">Sites do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="bc6d8-107">OneDrive for Business sites</span></span>
- <span data-ttu-id="bc6d8-108">Dispositivos do Windows 10</span><span class="sxs-lookup"><span data-stu-id="bc6d8-108">Windows 10 devices</span></span>

<span data-ttu-id="bc6d8-109">Os rótulos de confidencialidade aparecem como uma opção na lista **Conteúdo contém**.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-109">Sensitivity labels appear as an option in the **Content contains** list.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc6d8-110">![rótulo de confidencialidade como condição](../media/dlp-sensitivity-label-as-a-condition.png)</span><span class="sxs-lookup"><span data-stu-id="bc6d8-110">![sensitivity label as a condition](../media/dlp-sensitivity-label-as-a-condition.png)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc6d8-111">Como condição, os **Rótulos de Confidencialidade** não estarão disponíveis se você tiver selecionado o **chat do Teams e as mensagens do canal** como um local para aplicar a política DLP.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-111">**Sensitivity Labels** as a condition will not be available if you have selected **Teams chat and channel messages** as a location to apply the DLP policy.</span></span>


## <a name="supported-items-scenarios-and-policy-tips"></a><span data-ttu-id="bc6d8-112">Itens com suporte, cenários e dicas de política</span><span class="sxs-lookup"><span data-stu-id="bc6d8-112">Supported items, scenarios, and policy tips</span></span>

<span data-ttu-id="bc6d8-113">Você pode usar rótulos de confidencialidade como condições nestes itens e nestes cenários.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-113">You can use sensitivity labels as conditions on these items and in these scenarios.</span></span>

### <a name="supported-items"></a><span data-ttu-id="bc6d8-114">Itens com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-114">Supported items</span></span>

|<span data-ttu-id="bc6d8-115">Serviço</span><span class="sxs-lookup"><span data-stu-id="bc6d8-115">Service</span></span>  |<span data-ttu-id="bc6d8-116">Tipo de item</span><span class="sxs-lookup"><span data-stu-id="bc6d8-116">Item type</span></span>  |<span data-ttu-id="bc6d8-117">Disponível para a dica de política</span><span class="sxs-lookup"><span data-stu-id="bc6d8-117">Available to policy tip</span></span>  |<span data-ttu-id="bc6d8-118">Aplicável</span><span class="sxs-lookup"><span data-stu-id="bc6d8-118">Enforceable</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="bc6d8-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="bc6d8-119">Exchange</span></span>    |<span data-ttu-id="bc6d8-120">mensagem de email</span><span class="sxs-lookup"><span data-stu-id="bc6d8-120">email message</span></span>         |<span data-ttu-id="bc6d8-121">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-121">yes</span></span>         |<span data-ttu-id="bc6d8-122">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-122">yes</span></span>         |
|<span data-ttu-id="bc6d8-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="bc6d8-123">Exchange</span></span>    |<span data-ttu-id="bc6d8-124">anexos de email</span><span class="sxs-lookup"><span data-stu-id="bc6d8-124">email attachment</span></span>         |<span data-ttu-id="bc6d8-125">não \*</span><span class="sxs-lookup"><span data-stu-id="bc6d8-125">no \*</span></span>         |<span data-ttu-id="bc6d8-126">não \*</span><span class="sxs-lookup"><span data-stu-id="bc6d8-126">no \*</span></span>         |
|<span data-ttu-id="bc6d8-127">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bc6d8-127">SharePoint Online</span></span>     |<span data-ttu-id="bc6d8-128">itens no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bc6d8-128">items in SharePoint Online</span></span>         |<span data-ttu-id="bc6d8-129">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-129">yes</span></span>         |<span data-ttu-id="bc6d8-130">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-130">yes</span></span>         |
|<span data-ttu-id="bc6d8-131">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="bc6d8-131">OneDrive for Business</span></span>     |<span data-ttu-id="bc6d8-132">itens</span><span class="sxs-lookup"><span data-stu-id="bc6d8-132">items</span></span>         |<span data-ttu-id="bc6d8-133">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-133">yes</span></span>         |<span data-ttu-id="bc6d8-134">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-134">yes</span></span>         |
|<span data-ttu-id="bc6d8-135">Teams</span><span class="sxs-lookup"><span data-stu-id="bc6d8-135">Teams</span></span>     |<span data-ttu-id="bc6d8-136">Teams e mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="bc6d8-136">Teams and channel messages</span></span>         |<span data-ttu-id="bc6d8-137">não se aplica</span><span class="sxs-lookup"><span data-stu-id="bc6d8-137">not applicable</span></span>         |<span data-ttu-id="bc6d8-138">não se aplica</span><span class="sxs-lookup"><span data-stu-id="bc6d8-138">not applicable</span></span>         |
|<span data-ttu-id="bc6d8-139">Teams</span><span class="sxs-lookup"><span data-stu-id="bc6d8-139">Teams</span></span>     |<span data-ttu-id="bc6d8-140">anexos</span><span class="sxs-lookup"><span data-stu-id="bc6d8-140">attachments</span></span>         |<span data-ttu-id="bc6d8-141">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="bc6d8-141">yes \*\*</span></span>         |<span data-ttu-id="bc6d8-142">sim \*\*</span><span class="sxs-lookup"><span data-stu-id="bc6d8-142">yes \*\*</span></span>         |
|<span data-ttu-id="bc6d8-143">Dispositivos do Windows 10 (visualização)</span><span class="sxs-lookup"><span data-stu-id="bc6d8-143">Windows 10 devices (preview)</span></span>     |<span data-ttu-id="bc6d8-144">itens</span><span class="sxs-lookup"><span data-stu-id="bc6d8-144">items</span></span>         |<span data-ttu-id="bc6d8-145">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-145">yes</span></span>         |<span data-ttu-id="bc6d8-146">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-146">yes</span></span>         |
|<span data-ttu-id="bc6d8-147">MCAS (visualização)</span><span class="sxs-lookup"><span data-stu-id="bc6d8-147">MCAS (preview)</span></span> |<span data-ttu-id="bc6d8-148">itens</span><span class="sxs-lookup"><span data-stu-id="bc6d8-148">items</span></span>         |<span data-ttu-id="bc6d8-149">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-149">yes</span></span>         |<span data-ttu-id="bc6d8-150">sim</span><span class="sxs-lookup"><span data-stu-id="bc6d8-150">yes</span></span>         |

<span data-ttu-id="bc6d8-151">\* A detecção de DLP de rótulos de confidencialidade em emails possui suporte.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-151">\* DLP detection of sensitivity labels on emails are supported.</span></span> <span data-ttu-id="bc6d8-152">A detecção de DLP de anexos de email rotulados como confidenciais não.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-152">DLP detection of sensitivity labeled email attachments are not.</span></span>

<span data-ttu-id="bc6d8-153">\*\* Anexos enviados no Teams em chats individuais ou canais são carregados automaticamente para o OneDrive for Business e para o SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-153">\*\* Attachments sent in Teams over 1:1 chat or channels are automatically uploaded to OneDrive for Business and SharePoint.</span></span> <span data-ttu-id="bc6d8-154">Portanto, se o SharePoint Online ou OneDrive for Business estiverem incluídos como locais na sua política de DLP, os anexos enviados pelo Teams serão incluídos automaticamente no escopo dessa condição.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-154">So if SharePoint Online or OneDrive for Business are included as locations in your DLP policy, then labeled attachments sent in Teams will be automatically included in the scope of this condition.</span></span> <span data-ttu-id="bc6d8-155">O Teams como local não precisa ser selecionado na política de DLP.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-155">Teams as a location does not need to be selected in the DLP policy.</span></span>

### <a name="supported-scenarios"></a><span data-ttu-id="bc6d8-156">Cenários com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-156">Supported scenarios</span></span>

- <span data-ttu-id="bc6d8-157">O administrador de DLP poderá ver uma lista de todos os rótulos de confidencialidade no locatário quando eles optarem por incluir um ou mais rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-157">DLP Admin will be able to see a list of all sensitivity labels in the tenant when they choose to include one or more sensitivity labels as a condition.</span></span>

- <span data-ttu-id="bc6d8-158">Como condição, o uso de rótulos de confidencialidade tem suporte em todas as cargas de trabalho, como indicado na matriz de suporte acima.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-158">Using sensitivity labels as a condition is supported across all workloads as indicated in the support matrix above.</span></span>

- <span data-ttu-id="bc6d8-159">As dicas de política DLP continuarão a ser mostradas entre cargas de trabalho (exceto o Outlook Win32) para políticas DLP que contêm rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-159">DLP policy tips will continue to be shown across workloads (except Outlook Win32) for DLP policies which contain sensitivity label as a condition.</span></span>

- <span data-ttu-id="bc6d8-160">Os rótulos de confidencialidade também serão exibidos como parte do email do relatório de incidentes se uma política DLP com rótulos de confidencialidade for correspondida.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-160">Sensitivity labels will also appear as a part of the incident report email if a DLP policy with sensitivity label as a condition is matched.</span></span>

- <span data-ttu-id="bc6d8-161">Os detalhes dos rótulos de confidencialidade também serão mostrados na regra de correspondência do log de auditoria da DLP para obter uma correspondência à política DLP que contenha o rótulos de confidencialidade como uma condição.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-161">Sensitivity label details will also be shown in the DLP rule match audit log for a DLP policy match which contains sensitivity label as a condition.</span></span>


### <a name="support-policy-tips"></a><span data-ttu-id="bc6d8-162">Dicas de política com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-162">Support policy tips</span></span>


|<span data-ttu-id="bc6d8-163">Carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="bc6d8-163">Workload</span></span>  |<span data-ttu-id="bc6d8-164">Dicas de política com suporte/sem suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-164">Policy tips supported/not supported</span></span>  |
|---------|---------|
|<span data-ttu-id="bc6d8-165">OWA</span><span class="sxs-lookup"><span data-stu-id="bc6d8-165">OWA</span></span> |    <span data-ttu-id="bc6d8-166">com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-166">supported</span></span>     |
|<span data-ttu-id="bc6d8-167">Outlook Win 32</span><span class="sxs-lookup"><span data-stu-id="bc6d8-167">Outlook Win 32</span></span>    |  <span data-ttu-id="bc6d8-168">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-168">not supported</span></span>       |
|<span data-ttu-id="bc6d8-169">SharePoint</span><span class="sxs-lookup"><span data-stu-id="bc6d8-169">SharePoint</span></span>   |   <span data-ttu-id="bc6d8-170">com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-170">supported</span></span>      |
|<span data-ttu-id="bc6d8-171">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="bc6d8-171">OneDrive for Business</span></span>    |    <span data-ttu-id="bc6d8-172">com suporte</span><span class="sxs-lookup"><span data-stu-id="bc6d8-172">supported</span></span>     |
|<span data-ttu-id="bc6d8-173">dispositivos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="bc6d8-173">endpoint devices</span></span>   |  <span data-ttu-id="bc6d8-174">sem suporte.</span><span class="sxs-lookup"><span data-stu-id="bc6d8-174">not supported</span></span>       |
