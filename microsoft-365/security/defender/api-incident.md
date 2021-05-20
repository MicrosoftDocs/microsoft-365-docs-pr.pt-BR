---
title: Microsoft 365 APIs de incidentes do Defender e o tipo de recurso de incidente
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Incident no Microsoft 365 Defender
keywords: incidentes, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572580"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a><span data-ttu-id="5f1dd-104">Microsoft 365 API de incidentes do Defender e o tipo de recurso de incidente</span><span class="sxs-lookup"><span data-stu-id="5f1dd-104">Microsoft 365 Defender incidents API and the incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5f1dd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5f1dd-105">**Applies to:**</span></span>

- <span data-ttu-id="5f1dd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f1dd-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f1dd-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5f1dd-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5f1dd-109">Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="5f1dd-110">Eventos de entidades diferentes em sua organização são automaticamente agregados pelo Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="5f1dd-111">Você pode usar a API de incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="5f1dd-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="5f1dd-112">Quotas and resource allocation</span></span>

<span data-ttu-id="5f1dd-113">Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="5f1dd-114">Cada método também tem suas próprias cotas.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-114">Each method also has its own quotas.</span></span> <span data-ttu-id="5f1dd-115">Para obter mais informações sobre cotas específicas do método, consulte o artigo respectivo para o método que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="5f1dd-116">Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="5f1dd-117">O corpo da resposta incluirá o tempo até que a cota atingida seja redefinida.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="5f1dd-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="5f1dd-118">Permissions</span></span>

<span data-ttu-id="5f1dd-119">A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="5f1dd-120">Para obter mais informações sobre permissões necessárias, consulte o artigo do método respectivo.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="5f1dd-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="5f1dd-121">Methods</span></span>

<span data-ttu-id="5f1dd-122">Método</span><span class="sxs-lookup"><span data-stu-id="5f1dd-122">Method</span></span> | <span data-ttu-id="5f1dd-123">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="5f1dd-123">Return Type</span></span> | <span data-ttu-id="5f1dd-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f1dd-124">Description</span></span>
-|-|-
[<span data-ttu-id="5f1dd-125">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="5f1dd-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="5f1dd-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="5f1dd-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="5f1dd-127">Obter uma lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-127">Get a list of incidents.</span></span>
[<span data-ttu-id="5f1dd-128">Atualizar incidente</span><span class="sxs-lookup"><span data-stu-id="5f1dd-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="5f1dd-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="5f1dd-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="5f1dd-130">Atualize um incidente específico.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-130">Update a specific incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="5f1dd-131">Solicitar corpo, resposta e exemplos</span><span class="sxs-lookup"><span data-stu-id="5f1dd-131">Request body, response, and examples</span></span>

<span data-ttu-id="5f1dd-132">Consulte os respectivos artigos de método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e para obter exemplos práticos.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-132">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="5f1dd-133">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="5f1dd-133">Common properties</span></span>

<span data-ttu-id="5f1dd-134">Propriedade</span><span class="sxs-lookup"><span data-stu-id="5f1dd-134">Property</span></span> | <span data-ttu-id="5f1dd-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="5f1dd-135">Type</span></span> | <span data-ttu-id="5f1dd-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f1dd-136">Description</span></span>
-|-|-
<span data-ttu-id="5f1dd-137">incidentId</span><span class="sxs-lookup"><span data-stu-id="5f1dd-137">incidentId</span></span> | <span data-ttu-id="5f1dd-138">long</span><span class="sxs-lookup"><span data-stu-id="5f1dd-138">long</span></span> | <span data-ttu-id="5f1dd-139">ID exclusiva do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-139">Incident unique ID.</span></span>
<span data-ttu-id="5f1dd-140">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="5f1dd-140">redirectIncidentId</span></span> | <span data-ttu-id="5f1dd-141">nullable long</span><span class="sxs-lookup"><span data-stu-id="5f1dd-141">nullable long</span></span> | <span data-ttu-id="5f1dd-142">A ID do Incidente à que o Incidente atual foi mesclado.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-142">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="5f1dd-143">incidentName</span><span class="sxs-lookup"><span data-stu-id="5f1dd-143">incidentName</span></span> | <span data-ttu-id="5f1dd-144">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5f1dd-144">string</span></span> | <span data-ttu-id="5f1dd-145">O nome do Incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-145">The name of the Incident.</span></span>
<span data-ttu-id="5f1dd-146">createdTime</span><span class="sxs-lookup"><span data-stu-id="5f1dd-146">createdTime</span></span> | <span data-ttu-id="5f1dd-147">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5f1dd-147">DateTimeOffset</span></span> | <span data-ttu-id="5f1dd-148">A data e a hora (em UTC) que o Incidente foi criado.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-148">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="5f1dd-149">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="5f1dd-149">lastUpdateTime</span></span> | <span data-ttu-id="5f1dd-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="5f1dd-150">DateTimeOffset</span></span> | <span data-ttu-id="5f1dd-151">A data e a hora (em UTC) que o Incidente foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-151">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="5f1dd-152">assignedTo</span><span class="sxs-lookup"><span data-stu-id="5f1dd-152">assignedTo</span></span> | <span data-ttu-id="5f1dd-153">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5f1dd-153">string</span></span> | <span data-ttu-id="5f1dd-154">Proprietário do Incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-154">Owner of the Incident.</span></span>
<span data-ttu-id="5f1dd-155">severity</span><span class="sxs-lookup"><span data-stu-id="5f1dd-155">severity</span></span> | <span data-ttu-id="5f1dd-156">Enum</span><span class="sxs-lookup"><span data-stu-id="5f1dd-156">Enum</span></span> | <span data-ttu-id="5f1dd-157">Gravidade do Incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-157">Severity of the Incident.</span></span> <span data-ttu-id="5f1dd-158">Os valores possíveis são: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="5f1dd-158">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="5f1dd-159">status</span><span class="sxs-lookup"><span data-stu-id="5f1dd-159">status</span></span> | <span data-ttu-id="5f1dd-160">Enum</span><span class="sxs-lookup"><span data-stu-id="5f1dd-160">Enum</span></span> | <span data-ttu-id="5f1dd-161">Especifica o status atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-161">Specifies the current status of the incident.</span></span> <span data-ttu-id="5f1dd-162">Os valores possíveis são: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="5f1dd-162">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="5f1dd-163">classificação</span><span class="sxs-lookup"><span data-stu-id="5f1dd-163">classification</span></span> | <span data-ttu-id="5f1dd-164">Enum</span><span class="sxs-lookup"><span data-stu-id="5f1dd-164">Enum</span></span> | <span data-ttu-id="5f1dd-165">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-165">Specification of the incident.</span></span> <span data-ttu-id="5f1dd-166">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-166">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="5f1dd-167">determinação</span><span class="sxs-lookup"><span data-stu-id="5f1dd-167">determination</span></span> | <span data-ttu-id="5f1dd-168">Enum</span><span class="sxs-lookup"><span data-stu-id="5f1dd-168">Enum</span></span> | <span data-ttu-id="5f1dd-169">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-169">Specifies the determination of the incident.</span></span> <span data-ttu-id="5f1dd-170">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-170">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="5f1dd-171">tags</span><span class="sxs-lookup"><span data-stu-id="5f1dd-171">tags</span></span> | <span data-ttu-id="5f1dd-172">string List</span><span class="sxs-lookup"><span data-stu-id="5f1dd-172">string List</span></span> | <span data-ttu-id="5f1dd-173">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-173">List of Incident tags.</span></span>
<span data-ttu-id="5f1dd-174">comentários</span><span class="sxs-lookup"><span data-stu-id="5f1dd-174">comments</span></span> | <span data-ttu-id="5f1dd-175">Lista de comentários de incidentes</span><span class="sxs-lookup"><span data-stu-id="5f1dd-175">List of incident comments</span></span> | <span data-ttu-id="5f1dd-176">O objeto Comentário de Incidente contém: cadeia de caracteres de comentários, createdBy string e createTime date time.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-176">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="5f1dd-177">alerts</span><span class="sxs-lookup"><span data-stu-id="5f1dd-177">alerts</span></span> | <span data-ttu-id="5f1dd-178">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="5f1dd-178">Alert List</span></span> | <span data-ttu-id="5f1dd-179">Lista de alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-179">List of related alerts.</span></span> <span data-ttu-id="5f1dd-180">Consulte exemplos na documentação da API [de incidentes](api-list-incidents.md) de lista.</span><span class="sxs-lookup"><span data-stu-id="5f1dd-180">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5f1dd-181">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="5f1dd-181">Related articles</span></span>

- [<span data-ttu-id="5f1dd-182">Microsoft 365 Visão geral das APIs do Defender</span><span class="sxs-lookup"><span data-stu-id="5f1dd-182">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5f1dd-183">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="5f1dd-183">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5f1dd-184">Api de incidentes de lista</span><span class="sxs-lookup"><span data-stu-id="5f1dd-184">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="5f1dd-185">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="5f1dd-185">Update incident API</span></span>](api-update-incidents.md)
