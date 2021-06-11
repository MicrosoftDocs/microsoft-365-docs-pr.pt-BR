---
title: Microsoft 365 APIs de incidentes do Defender e o tipo de recurso de incidentes
description: Saiba mais sobre os métodos e propriedades do tipo de recurso Incidentes no Microsoft 365 Defender
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
ms.openlocfilehash: 0c0c2e280f63076687a0854e25c47577b050a8f7
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888428"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incidents-resource-type"></a><span data-ttu-id="1c4d9-104">Microsoft 365 API de incidentes do Defender e o tipo de recurso de incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-104">Microsoft 365 Defender incidents API and the incidents resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="1c4d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1c4d9-105">**Applies to:**</span></span>

- [<span data-ttu-id="1c4d9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1c4d9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="1c4d9-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1c4d9-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="1c4d9-109">Um [incidente](incidents-overview.md) é uma coleção de alertas relacionados que ajudam a descrever um ataque.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-109">An [incident](incidents-overview.md) is a collection of related alerts that help describe an attack.</span></span> <span data-ttu-id="1c4d9-110">Eventos de entidades diferentes em sua organização são automaticamente agregados pelo Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-110">Events from different entities in your organization are automatically aggregated by Microsoft 365 Defender.</span></span> <span data-ttu-id="1c4d9-111">Você pode usar a API de incidentes para acessar programaticamente os incidentes e alertas relacionados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-111">You can use the incidents API to programatically access your organization's incidents and related alerts.</span></span>

## <a name="quotas-and-resource-allocation"></a><span data-ttu-id="1c4d9-112">Cotas e alocação de recursos</span><span class="sxs-lookup"><span data-stu-id="1c4d9-112">Quotas and resource allocation</span></span>

<span data-ttu-id="1c4d9-113">Você pode solicitar até 50 chamadas por minuto ou 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-113">You can request up to 50 calls per minute or 1500 calls per hour.</span></span> <span data-ttu-id="1c4d9-114">Cada método também tem suas próprias cotas.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-114">Each method also has its own quotas.</span></span> <span data-ttu-id="1c4d9-115">Para obter mais informações sobre cotas específicas do método, consulte o artigo respectivo para o método que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-115">For more information on method-specific quotas, see the respective article for the method you want to use.</span></span>

<span data-ttu-id="1c4d9-116">Um código de resposta HTTP indica que você atingiu uma cota, por número de solicitações enviadas ou pelo tempo de `429` execução alocado.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-116">A `429` HTTP response code indicates that you've reached a quota, either by number of requests sent, or by allotted running time.</span></span> <span data-ttu-id="1c4d9-117">O corpo da resposta incluirá o tempo até que a cota atingida seja redefinida.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-117">The response body will include the time until the quota you reached will be reset.</span></span>

## <a name="permissions"></a><span data-ttu-id="1c4d9-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="1c4d9-118">Permissions</span></span>

<span data-ttu-id="1c4d9-119">A API de incidentes requer diferentes tipos de permissões para cada um de seus métodos.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-119">The incidents API requires different kinds of permissions for each of its methods.</span></span> <span data-ttu-id="1c4d9-120">Para obter mais informações sobre permissões necessárias, consulte o artigo do método respectivo.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-120">For more information about required permissions, see the respective method's article.</span></span>

## <a name="methods"></a><span data-ttu-id="1c4d9-121">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c4d9-121">Methods</span></span>

<span data-ttu-id="1c4d9-122">Método</span><span class="sxs-lookup"><span data-stu-id="1c4d9-122">Method</span></span> | <span data-ttu-id="1c4d9-123">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="1c4d9-123">Return Type</span></span> | <span data-ttu-id="1c4d9-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="1c4d9-124">Description</span></span>
-|-|-
[<span data-ttu-id="1c4d9-125">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-125">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="1c4d9-126">[Lista de](api-incident.md) incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-126">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="1c4d9-127">Obter uma lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-127">Get a list of incidents.</span></span>
[<span data-ttu-id="1c4d9-128">Atualizar incidente</span><span class="sxs-lookup"><span data-stu-id="1c4d9-128">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="1c4d9-129">Incidente</span><span class="sxs-lookup"><span data-stu-id="1c4d9-129">Incident</span></span>](api-incident.md) | <span data-ttu-id="1c4d9-130">Atualize um incidente específico.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-130">Update a specific incident.</span></span>
[<span data-ttu-id="1c4d9-131">Obter incidente</span><span class="sxs-lookup"><span data-stu-id="1c4d9-131">Get incident</span></span>](api-get-incident.md) | [<span data-ttu-id="1c4d9-132">Incidente</span><span class="sxs-lookup"><span data-stu-id="1c4d9-132">Incident</span></span>](api-incident.md) | <span data-ttu-id="1c4d9-133">Obter um único incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-133">Get a single incident.</span></span>

## <a name="request-body-response-and-examples"></a><span data-ttu-id="1c4d9-134">Solicitar corpo, resposta e exemplos</span><span class="sxs-lookup"><span data-stu-id="1c4d9-134">Request body, response, and examples</span></span>

<span data-ttu-id="1c4d9-135">Consulte os respectivos artigos de método para obter mais detalhes sobre como construir uma solicitação ou analisar uma resposta e para obter exemplos práticos.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-135">Refer to the respective method articles for more details on how to construct a request or parse a response, and for practical examples.</span></span>

## <a name="common-properties"></a><span data-ttu-id="1c4d9-136">Propriedades comuns</span><span class="sxs-lookup"><span data-stu-id="1c4d9-136">Common properties</span></span>

<span data-ttu-id="1c4d9-137">Propriedade</span><span class="sxs-lookup"><span data-stu-id="1c4d9-137">Property</span></span> | <span data-ttu-id="1c4d9-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="1c4d9-138">Type</span></span> | <span data-ttu-id="1c4d9-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="1c4d9-139">Description</span></span>
-|-|-
<span data-ttu-id="1c4d9-140">incidentId</span><span class="sxs-lookup"><span data-stu-id="1c4d9-140">incidentId</span></span> | <span data-ttu-id="1c4d9-141">long</span><span class="sxs-lookup"><span data-stu-id="1c4d9-141">long</span></span> | <span data-ttu-id="1c4d9-142">ID exclusiva do incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-142">Incident unique ID.</span></span>
<span data-ttu-id="1c4d9-143">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="1c4d9-143">redirectIncidentId</span></span> | <span data-ttu-id="1c4d9-144">nullable long</span><span class="sxs-lookup"><span data-stu-id="1c4d9-144">nullable long</span></span> | <span data-ttu-id="1c4d9-145">A ID do Incidente à que o Incidente atual foi mesclado.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-145">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="1c4d9-146">incidentName</span><span class="sxs-lookup"><span data-stu-id="1c4d9-146">incidentName</span></span> | <span data-ttu-id="1c4d9-147">string</span><span class="sxs-lookup"><span data-stu-id="1c4d9-147">string</span></span> | <span data-ttu-id="1c4d9-148">O nome do Incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-148">The name of the Incident.</span></span>
<span data-ttu-id="1c4d9-149">createdTime</span><span class="sxs-lookup"><span data-stu-id="1c4d9-149">createdTime</span></span> | <span data-ttu-id="1c4d9-150">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1c4d9-150">DateTimeOffset</span></span> | <span data-ttu-id="1c4d9-151">A data e a hora (em UTC) que o Incidente foi criado.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-151">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="1c4d9-152">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="1c4d9-152">lastUpdateTime</span></span> | <span data-ttu-id="1c4d9-153">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="1c4d9-153">DateTimeOffset</span></span> | <span data-ttu-id="1c4d9-154">A data e a hora (em UTC) que o Incidente foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-154">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="1c4d9-155">assignedTo</span><span class="sxs-lookup"><span data-stu-id="1c4d9-155">assignedTo</span></span> | <span data-ttu-id="1c4d9-156">string</span><span class="sxs-lookup"><span data-stu-id="1c4d9-156">string</span></span> | <span data-ttu-id="1c4d9-157">Proprietário do Incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-157">Owner of the Incident.</span></span>
<span data-ttu-id="1c4d9-158">severity</span><span class="sxs-lookup"><span data-stu-id="1c4d9-158">severity</span></span> | <span data-ttu-id="1c4d9-159">Enum</span><span class="sxs-lookup"><span data-stu-id="1c4d9-159">Enum</span></span> | <span data-ttu-id="1c4d9-160">Gravidade do Incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-160">Severity of the Incident.</span></span> <span data-ttu-id="1c4d9-161">Os valores possíveis são: ```UnSpecified``` , , , e ```Informational``` ```Low``` ```Medium``` ```High``` .</span><span class="sxs-lookup"><span data-stu-id="1c4d9-161">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium```, and ```High```.</span></span>
<span data-ttu-id="1c4d9-162">status</span><span class="sxs-lookup"><span data-stu-id="1c4d9-162">status</span></span> | <span data-ttu-id="1c4d9-163">Enum</span><span class="sxs-lookup"><span data-stu-id="1c4d9-163">Enum</span></span> | <span data-ttu-id="1c4d9-164">Especifica o status atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-164">Specifies the current status of the incident.</span></span> <span data-ttu-id="1c4d9-165">Os valores possíveis são: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="1c4d9-165">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="1c4d9-166">classificação</span><span class="sxs-lookup"><span data-stu-id="1c4d9-166">classification</span></span> | <span data-ttu-id="1c4d9-167">Enum</span><span class="sxs-lookup"><span data-stu-id="1c4d9-167">Enum</span></span> | <span data-ttu-id="1c4d9-168">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-168">Specification of the incident.</span></span> <span data-ttu-id="1c4d9-169">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-169">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="1c4d9-170">determinação</span><span class="sxs-lookup"><span data-stu-id="1c4d9-170">determination</span></span> | <span data-ttu-id="1c4d9-171">Enum</span><span class="sxs-lookup"><span data-stu-id="1c4d9-171">Enum</span></span> | <span data-ttu-id="1c4d9-172">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-172">Specifies the determination of the incident.</span></span> <span data-ttu-id="1c4d9-173">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-173">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="1c4d9-174">categorias</span><span class="sxs-lookup"><span data-stu-id="1c4d9-174">tags</span></span> | <span data-ttu-id="1c4d9-175">string List</span><span class="sxs-lookup"><span data-stu-id="1c4d9-175">string List</span></span> | <span data-ttu-id="1c4d9-176">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-176">List of Incident tags.</span></span>
<span data-ttu-id="1c4d9-177">comentários</span><span class="sxs-lookup"><span data-stu-id="1c4d9-177">comments</span></span> | <span data-ttu-id="1c4d9-178">Lista de comentários de incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-178">List of incident comments</span></span> | <span data-ttu-id="1c4d9-179">O objeto Comentário de Incidente contém: cadeia de caracteres de comentários, createdBy string e createTime date time.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-179">Incident Comment object contains: comment string, createdBy string, and createTime date time.</span></span>
<span data-ttu-id="1c4d9-180">alerts</span><span class="sxs-lookup"><span data-stu-id="1c4d9-180">alerts</span></span> | <span data-ttu-id="1c4d9-181">Lista de alertas</span><span class="sxs-lookup"><span data-stu-id="1c4d9-181">Alert List</span></span> | <span data-ttu-id="1c4d9-182">Lista de alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-182">List of related alerts.</span></span> <span data-ttu-id="1c4d9-183">Consulte exemplos na documentação da API [de incidentes](api-list-incidents.md) de lista.</span><span class="sxs-lookup"><span data-stu-id="1c4d9-183">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1c4d9-184">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="1c4d9-184">Related articles</span></span>

- [<span data-ttu-id="1c4d9-185">Microsoft 365 Visão geral das APIs do Defender</span><span class="sxs-lookup"><span data-stu-id="1c4d9-185">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="1c4d9-186">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1c4d9-187">Api de incidentes de lista</span><span class="sxs-lookup"><span data-stu-id="1c4d9-187">List incidents API</span></span>](api-list-incidents.md)
- [<span data-ttu-id="1c4d9-188">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="1c4d9-188">Update incident API</span></span>](api-update-incidents.md)
