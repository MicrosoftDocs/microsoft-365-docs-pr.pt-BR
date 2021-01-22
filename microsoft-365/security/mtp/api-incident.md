---
title: APIs de incidentes do Microsoft 365 Defender e o tipo de recurso de incidente
description: Saiba mais sobre os métodos e as propriedades do tipo de recurso Incident no Microsoft 365 Defender
keywords: incidente, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 37413c3c7458527e90d4657ddfb3afb058e1dfaa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928349"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="d4eaa-104">API de incidentes do Microsoft 365 Defender e o tipo de recurso de incidente</span><span class="sxs-lookup"><span data-stu-id="d4eaa-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d4eaa-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d4eaa-105">**Applies to:**</span></span>

- <span data-ttu-id="d4eaa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4eaa-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4eaa-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d4eaa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="d4eaa-109">Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="d4eaa-110">Eventos de entidades diferentes em sua organização são automaticamente agregados pelo Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="d4eaa-111">Você pode usar a API de incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="d4eaa-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="d4eaa-112">Quotas and resource allocation</span></span>

<span data-ttu-id="d4eaa-113">Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="d4eaa-114">Cada método também tem suas próprias cotas.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-114">Each method also has its own quotas.</span></span> <span data-ttu-id="d4eaa-115">Para obter mais informações sobre cotas específicas do método, consulte o respectivo artigo sobre o método que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="d4eaa-116">Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou por tempo `429` de execução alocado.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="d4eaa-117">O corpo da resposta incluirá o tempo até que a cota alcançada seja redefinida.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="d4eaa-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="d4eaa-118">Permissions</span></span>

<span data-ttu-id="d4eaa-119">A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="d4eaa-120">Para obter mais informações sobre as permissões necessárias, consulte o artigo do respectivo método.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="d4eaa-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="d4eaa-121">Methods</span></span>

<span data-ttu-id="d4eaa-122">Método</span><span class="sxs-lookup"><span data-stu-id="d4eaa-122">Method</span></span> | <span data-ttu-id="d4eaa-123">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="d4eaa-123">Return Type</span></span> | <span data-ttu-id="d4eaa-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4eaa-124">Description</span></span>
-|-|-
[<span data-ttu-id="d4eaa-125">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="d4eaa-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="d4eaa-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="d4eaa-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="d4eaa-127">Obter uma lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-127">Get a list of incidents.</span></span>
[<span data-ttu-id="d4eaa-128">Atualizar incidente</span><span class="sxs-lookup"><span data-stu-id="d4eaa-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="d4eaa-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="d4eaa-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="d4eaa-130">Atualizar um incidente específico.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="d4eaa-131">Solicitar corpo, resposta e exemplos</span><span class="sxs-lookup"><span data-stu-id="d4eaa-131">Request body, response, and examples</span></span>

<span data-ttu-id="d4eaa-132">Consulte os respectivos artigos de método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e para obter exemplos práticos.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="d4eaa-133">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="d4eaa-133">Common properties</span></span>

<span data-ttu-id="d4eaa-134">Propriedade</span><span class="sxs-lookup"><span data-stu-id="d4eaa-134">Property</span></span> | <span data-ttu-id="d4eaa-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="d4eaa-135">Type</span></span> | <span data-ttu-id="d4eaa-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="d4eaa-136">Description</span></span>
-|-|-
<span data-ttu-id="d4eaa-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="d4eaa-137">incidentId</span></span> | <span data-ttu-id="d4eaa-138">long</span><span class="sxs-lookup"><span data-stu-id="d4eaa-138">long</span></span> | <span data-ttu-id="d4eaa-139">ID exclusiva do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-139">Incident unique ID.</span></span>
<span data-ttu-id="d4eaa-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="d4eaa-140">redirectIncidentId</span></span> | <span data-ttu-id="d4eaa-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="d4eaa-141">nullable long</span></span> | <span data-ttu-id="d4eaa-142">A ID do incidente ao que o incidente atual foi mesclado.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="d4eaa-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="d4eaa-143">incidentName</span></span> | <span data-ttu-id="d4eaa-144">string</span><span class="sxs-lookup"><span data-stu-id="d4eaa-144">string</span></span> | <span data-ttu-id="d4eaa-145">O nome do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-145">The name of the Incident.</span></span>
<span data-ttu-id="d4eaa-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="d4eaa-146">createdTime</span></span> | <span data-ttu-id="d4eaa-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d4eaa-147">DateTimeOffset</span></span> | <span data-ttu-id="d4eaa-148">A data e a hora (em UTC) em que o incidente foi criado.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="d4eaa-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d4eaa-149">lastUpdateTime</span></span> | <span data-ttu-id="d4eaa-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="d4eaa-150">DateTimeOffset</span></span> | <span data-ttu-id="d4eaa-151">A data e a hora (em UTC) em que o incidente foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="d4eaa-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d4eaa-152">assignedTo</span></span> | <span data-ttu-id="d4eaa-153">string</span><span class="sxs-lookup"><span data-stu-id="d4eaa-153">string</span></span> | <span data-ttu-id="d4eaa-154">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-154">Owner of the Incident.</span></span>
<span data-ttu-id="d4eaa-155">severity</span><span class="sxs-lookup"><span data-stu-id="d4eaa-155">severity</span></span> | <span data-ttu-id="d4eaa-156">Enum</span><span class="sxs-lookup"><span data-stu-id="d4eaa-156">Enum</span></span> | <span data-ttu-id="d4eaa-157">Gravidade do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-157">Severity of the Incident.</span></span> <span data-ttu-id="d4eaa-158">Os valores possíveis ```UnSpecified``` são: ```Informational``` , , e ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="d4eaa-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="d4eaa-159">status</span><span class="sxs-lookup"><span data-stu-id="d4eaa-159">status</span></span> | <span data-ttu-id="d4eaa-160">Enum</span><span class="sxs-lookup"><span data-stu-id="d4eaa-160">Enum</span></span> | <span data-ttu-id="d4eaa-161">Especifica o status atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="d4eaa-162">Os valores possíveis ```Active``` são: ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="d4eaa-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="d4eaa-163">classificação</span><span class="sxs-lookup"><span data-stu-id="d4eaa-163">classification</span></span> | <span data-ttu-id="d4eaa-164">Enum</span><span class="sxs-lookup"><span data-stu-id="d4eaa-164">Enum</span></span> | <span data-ttu-id="d4eaa-165">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-165">Specification of the incident.</span></span> <span data-ttu-id="d4eaa-166">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="d4eaa-167">determinação</span><span class="sxs-lookup"><span data-stu-id="d4eaa-167">determination</span></span> | <span data-ttu-id="d4eaa-168">Enum</span><span class="sxs-lookup"><span data-stu-id="d4eaa-168">Enum</span></span> | <span data-ttu-id="d4eaa-169">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="d4eaa-170">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="d4eaa-171">categorias</span><span class="sxs-lookup"><span data-stu-id="d4eaa-171">tags</span></span> | <span data-ttu-id="d4eaa-172">string List</span><span class="sxs-lookup"><span data-stu-id="d4eaa-172">string List</span></span> | <span data-ttu-id="d4eaa-173">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-173">List of Incident tags.</span></span>
<span data-ttu-id="d4eaa-174">alerts</span><span class="sxs-lookup"><span data-stu-id="d4eaa-174">alerts</span></span> | <span data-ttu-id="d4eaa-175">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="d4eaa-175">Alert List</span></span> | <span data-ttu-id="d4eaa-176">Lista de alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-176">List of related alerts.</span></span> <span data-ttu-id="d4eaa-177">Veja exemplos na documentação da API [de incidentes](api-list-incidents.md) de lista.</span><span class="sxs-lookup"><span data-stu-id="d4eaa-177">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d4eaa-178">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d4eaa-178">Related articles</span></span>

- [<span data-ttu-id="d4eaa-179">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4eaa-179">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="d4eaa-180">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="d4eaa-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d4eaa-181">Listar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="d4eaa-181">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="d4eaa-182">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="d4eaa-182">Update incident API</span></span>](api-update-incidents.md)
