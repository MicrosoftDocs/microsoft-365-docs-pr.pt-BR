---
title: Tipo de recurso de incidente na API do Microsoft 365 defender
description: Saiba mais sobre os métodos e as propriedades do tipo de recurso incidente no Microsoft 365 defender
keywords: incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 68bee647cdd5687dbaad08ce3cd01b427dabf030
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844015"
---
# <a name="incident-resource-type"></a><span data-ttu-id="83c3d-104">Tipo de recurso incidente</span><span class="sxs-lookup"><span data-stu-id="83c3d-104">Incident resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="83c3d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="83c3d-105">**Applies to:**</span></span>
- <span data-ttu-id="83c3d-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="83c3d-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="83c3d-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="83c3d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="83c3d-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="methods"></a><span data-ttu-id="83c3d-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="83c3d-109">Methods</span></span>

<span data-ttu-id="83c3d-110">Método</span><span class="sxs-lookup"><span data-stu-id="83c3d-110">Method</span></span> |<span data-ttu-id="83c3d-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="83c3d-111">Return Type</span></span> |<span data-ttu-id="83c3d-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="83c3d-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="83c3d-113">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="83c3d-113">List incidents</span></span>](api-list-incidents.md) | <span data-ttu-id="83c3d-114">Lista de [incidentes](api-incident.md)</span><span class="sxs-lookup"><span data-stu-id="83c3d-114">[Incident](api-incident.md) list</span></span> | <span data-ttu-id="83c3d-115">Obter uma lista de incidentes.</span><span class="sxs-lookup"><span data-stu-id="83c3d-115">Get a list of incidents.</span></span>
[<span data-ttu-id="83c3d-116">Atualizar incidente</span><span class="sxs-lookup"><span data-stu-id="83c3d-116">Update incident</span></span>](api-update-incidents.md) | [<span data-ttu-id="83c3d-117">Incidente</span><span class="sxs-lookup"><span data-stu-id="83c3d-117">Incident</span></span>](api-incident.md) | <span data-ttu-id="83c3d-118">Atualize o incidente específico.</span><span class="sxs-lookup"><span data-stu-id="83c3d-118">Update specific incident.</span></span>


## <a name="properties"></a><span data-ttu-id="83c3d-119">Propriedades</span><span class="sxs-lookup"><span data-stu-id="83c3d-119">Properties</span></span>

<span data-ttu-id="83c3d-120">Propriedade</span><span class="sxs-lookup"><span data-stu-id="83c3d-120">Property</span></span> |    <span data-ttu-id="83c3d-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="83c3d-121">Type</span></span>    |    <span data-ttu-id="83c3d-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="83c3d-122">Description</span></span>
:---|:---|:---
<span data-ttu-id="83c3d-123">incidentalid</span><span class="sxs-lookup"><span data-stu-id="83c3d-123">incidentId</span></span> | <span data-ttu-id="83c3d-124">long</span><span class="sxs-lookup"><span data-stu-id="83c3d-124">long</span></span> | <span data-ttu-id="83c3d-125">ID exclusiva do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-125">Incident unique ID.</span></span>
<span data-ttu-id="83c3d-126">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="83c3d-126">redirectIncidentId</span></span> | <span data-ttu-id="83c3d-127">Long anulável</span><span class="sxs-lookup"><span data-stu-id="83c3d-127">nullable long</span></span> | <span data-ttu-id="83c3d-128">A ID de incidente à qual o incidente atual foi mesclado.</span><span class="sxs-lookup"><span data-stu-id="83c3d-128">The Incident ID the current Incident was merged to.</span></span>
<span data-ttu-id="83c3d-129">incidentalname</span><span class="sxs-lookup"><span data-stu-id="83c3d-129">incidentName</span></span> | <span data-ttu-id="83c3d-130">string</span><span class="sxs-lookup"><span data-stu-id="83c3d-130">string</span></span> | <span data-ttu-id="83c3d-131">O nome do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-131">The name of the Incident.</span></span>
<span data-ttu-id="83c3d-132">createdtime</span><span class="sxs-lookup"><span data-stu-id="83c3d-132">createdTime</span></span> | <span data-ttu-id="83c3d-133">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="83c3d-133">DateTimeOffset</span></span> | <span data-ttu-id="83c3d-134">A data e a hora (em UTC) que o incidente foi criado.</span><span class="sxs-lookup"><span data-stu-id="83c3d-134">The date and time (in UTC) the Incident was created.</span></span>
<span data-ttu-id="83c3d-135">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="83c3d-135">lastUpdateTime</span></span> | <span data-ttu-id="83c3d-136">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="83c3d-136">DateTimeOffset</span></span> | <span data-ttu-id="83c3d-137">A data e a hora (em UTC) que o incidente foi atualizado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="83c3d-137">The date and time (in UTC) the Incident was last updated.</span></span>
<span data-ttu-id="83c3d-138">assignedTo</span><span class="sxs-lookup"><span data-stu-id="83c3d-138">assignedTo</span></span> | <span data-ttu-id="83c3d-139">string</span><span class="sxs-lookup"><span data-stu-id="83c3d-139">string</span></span> | <span data-ttu-id="83c3d-140">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-140">Owner of the Incident.</span></span>
<span data-ttu-id="83c3d-141">severity</span><span class="sxs-lookup"><span data-stu-id="83c3d-141">severity</span></span> | <span data-ttu-id="83c3d-142">Enum</span><span class="sxs-lookup"><span data-stu-id="83c3d-142">Enum</span></span> | <span data-ttu-id="83c3d-143">Gravidade do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-143">Severity of the Incident.</span></span> <span data-ttu-id="83c3d-144">Os valores possíveis são: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` e ```High``` .</span><span class="sxs-lookup"><span data-stu-id="83c3d-144">Possible values are: ```UnSpecified```, ```Informational```, ```Low```, ```Medium``` and ```High```.</span></span>
<span data-ttu-id="83c3d-145">status</span><span class="sxs-lookup"><span data-stu-id="83c3d-145">status</span></span> | <span data-ttu-id="83c3d-146">Enum</span><span class="sxs-lookup"><span data-stu-id="83c3d-146">Enum</span></span> | <span data-ttu-id="83c3d-147">Especifica o status atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-147">Specifies the current status of the incident.</span></span> <span data-ttu-id="83c3d-148">Os valores possíveis são ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="83c3d-148">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="83c3d-149">classificação</span><span class="sxs-lookup"><span data-stu-id="83c3d-149">classification</span></span> | <span data-ttu-id="83c3d-150">Enum</span><span class="sxs-lookup"><span data-stu-id="83c3d-150">Enum</span></span> | <span data-ttu-id="83c3d-151">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-151">Specification of the incident.</span></span> <span data-ttu-id="83c3d-152">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="83c3d-152">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="83c3d-153">determinação</span><span class="sxs-lookup"><span data-stu-id="83c3d-153">determination</span></span> | <span data-ttu-id="83c3d-154">Enum</span><span class="sxs-lookup"><span data-stu-id="83c3d-154">Enum</span></span> | <span data-ttu-id="83c3d-155">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-155">Specifies the determination of the incident.</span></span> <span data-ttu-id="83c3d-156">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="83c3d-156">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="83c3d-157">categorias</span><span class="sxs-lookup"><span data-stu-id="83c3d-157">tags</span></span> | <span data-ttu-id="83c3d-158">Lista de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="83c3d-158">string List</span></span> | <span data-ttu-id="83c3d-159">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="83c3d-159">List of Incident tags.</span></span>
<span data-ttu-id="83c3d-160">alerts</span><span class="sxs-lookup"><span data-stu-id="83c3d-160">alerts</span></span> | <span data-ttu-id="83c3d-161">Lista de alerta</span><span class="sxs-lookup"><span data-stu-id="83c3d-161">Alert List</span></span> | <span data-ttu-id="83c3d-162">Lista de alertas relacionados.</span><span class="sxs-lookup"><span data-stu-id="83c3d-162">List of related alerts.</span></span> <span data-ttu-id="83c3d-163">Consulte exemplos na documentação da API de [incidentes de lista](api-list-incidents.md) .</span><span class="sxs-lookup"><span data-stu-id="83c3d-163">See examples at [List incidents](api-list-incidents.md) API documentation.</span></span>
