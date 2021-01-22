---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando a API do Microsoft 365 Defender
keywords: update, api, incident
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
ms.openlocfilehash: 18be4565c2611457d0f5fdc135f99a301bb39e2a
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929065"
---
# <a name="update-incidents-api"></a><span data-ttu-id="199bf-104">Atualizar a API de incidentes</span><span class="sxs-lookup"><span data-stu-id="199bf-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="199bf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="199bf-105">**Applies to:**</span></span>

- <span data-ttu-id="199bf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="199bf-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="199bf-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="199bf-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="199bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="199bf-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="199bf-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="199bf-109">API description</span></span>

<span data-ttu-id="199bf-110">Atualiza as propriedades do incidente existente.</span><span class="sxs-lookup"><span data-stu-id="199bf-110">Updates properties of existing incident.</span></span> <span data-ttu-id="199bf-111">As propriedades atualizáveis ```status``` são: ```determination``` , , e ```classification``` ```assignedTo``` ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="199bf-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, and ```tags```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="199bf-112">Cotas, alocação de recursos e outras restrições</span><span class="sxs-lookup"><span data-stu-id="199bf-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="199bf-113">Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de limite.</span><span class="sxs-lookup"><span data-stu-id="199bf-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="199bf-114">Você só poderá definir `determination` a propriedade se estiver definida como `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="199bf-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="199bf-115">Se sua solicitação for acelerada, ela retornará um código `429` de resposta.</span><span class="sxs-lookup"><span data-stu-id="199bf-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="199bf-116">O corpo da resposta indicará a hora em que você poderá começar a fazer novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="199bf-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="199bf-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="199bf-117">Permissions</span></span>

<span data-ttu-id="199bf-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="199bf-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="199bf-119">Para saber mais, incluindo como escolher permissões, confira [Acessar as APIs do Microsoft 365 Defender.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="199bf-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="199bf-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="199bf-120">Permission type</span></span> | <span data-ttu-id="199bf-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="199bf-121">Permission</span></span> | <span data-ttu-id="199bf-122">Nome de exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="199bf-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="199bf-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="199bf-123">Application</span></span> | <span data-ttu-id="199bf-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="199bf-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="199bf-125">Ler e gravar todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="199bf-125">Read and write all incidents</span></span>
<span data-ttu-id="199bf-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="199bf-126">Delegated (work or school account)</span></span> | <span data-ttu-id="199bf-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="199bf-127">Incident.ReadWrite</span></span> | <span data-ttu-id="199bf-128">Ler e gravar incidentes</span><span class="sxs-lookup"><span data-stu-id="199bf-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="199bf-129">Ao obter um token usando credenciais de usuário, o usuário precisa ter permissão para atualizar o incidente no portal.</span><span class="sxs-lookup"><span data-stu-id="199bf-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="199bf-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="199bf-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="199bf-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="199bf-131">Request headers</span></span>

<span data-ttu-id="199bf-132">Nome</span><span class="sxs-lookup"><span data-stu-id="199bf-132">Name</span></span> | <span data-ttu-id="199bf-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="199bf-133">Type</span></span> | <span data-ttu-id="199bf-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="199bf-134">Description</span></span>
-|-|-
<span data-ttu-id="199bf-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="199bf-135">Authorization</span></span> | <span data-ttu-id="199bf-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="199bf-136">String</span></span> | <span data-ttu-id="199bf-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="199bf-137">Bearer {token}.</span></span> <span data-ttu-id="199bf-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="199bf-138">**Required**.</span></span>
<span data-ttu-id="199bf-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="199bf-139">Content-Type</span></span> | <span data-ttu-id="199bf-140">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="199bf-140">String</span></span> | <span data-ttu-id="199bf-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="199bf-141">application/json.</span></span> <span data-ttu-id="199bf-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="199bf-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="199bf-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="199bf-143">Request body</span></span>

<span data-ttu-id="199bf-144">No corpo da solicitação, fornece os valores para os campos que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="199bf-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="199bf-145">Propriedades existentes que não estão incluídas no corpo da solicitação manterão seus valores, a menos que tenham que ser recalculadas devido a alterações nos valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="199bf-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="199bf-146">Para melhor desempenho, você deve omitir valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="199bf-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="199bf-147">Propriedade</span><span class="sxs-lookup"><span data-stu-id="199bf-147">Property</span></span> | <span data-ttu-id="199bf-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="199bf-148">Type</span></span> | <span data-ttu-id="199bf-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="199bf-149">Description</span></span>
-|-|-
<span data-ttu-id="199bf-150">status</span><span class="sxs-lookup"><span data-stu-id="199bf-150">status</span></span> | <span data-ttu-id="199bf-151">Enum</span><span class="sxs-lookup"><span data-stu-id="199bf-151">Enum</span></span> | <span data-ttu-id="199bf-152">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="199bf-152">Specifies the current status of the alert.</span></span> <span data-ttu-id="199bf-153">Os valores possíveis ```Active``` são: ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="199bf-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="199bf-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="199bf-154">assignedTo</span></span> | <span data-ttu-id="199bf-155">string</span><span class="sxs-lookup"><span data-stu-id="199bf-155">string</span></span> | <span data-ttu-id="199bf-156">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="199bf-156">Owner of the incident.</span></span>
<span data-ttu-id="199bf-157">classificação</span><span class="sxs-lookup"><span data-stu-id="199bf-157">classification</span></span> | <span data-ttu-id="199bf-158">Enum</span><span class="sxs-lookup"><span data-stu-id="199bf-158">Enum</span></span> | <span data-ttu-id="199bf-159">Especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="199bf-159">Specification of the alert.</span></span> <span data-ttu-id="199bf-160">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="199bf-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="199bf-161">determinação</span><span class="sxs-lookup"><span data-stu-id="199bf-161">determination</span></span> | <span data-ttu-id="199bf-162">Enum</span><span class="sxs-lookup"><span data-stu-id="199bf-162">Enum</span></span> | <span data-ttu-id="199bf-163">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="199bf-163">Specifies the determination of the alert.</span></span> <span data-ttu-id="199bf-164">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="199bf-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="199bf-165">categorias</span><span class="sxs-lookup"><span data-stu-id="199bf-165">tags</span></span> | <span data-ttu-id="199bf-166">string List</span><span class="sxs-lookup"><span data-stu-id="199bf-166">string List</span></span> | <span data-ttu-id="199bf-167">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="199bf-167">List of Incident tags.</span></span>

## <a name="response"></a><span data-ttu-id="199bf-168">Resposta</span><span class="sxs-lookup"><span data-stu-id="199bf-168">Response</span></span>

<span data-ttu-id="199bf-169">Se bem-sucedido, este método retorna `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="199bf-169">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="199bf-170">O corpo da resposta conterá a entidade de incidente com propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="199bf-170">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="199bf-171">Se um incidente com a ID especificada não for encontrado, o método `404 Not Found` retornará.</span><span class="sxs-lookup"><span data-stu-id="199bf-171">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="199bf-172">Exemplo</span><span class="sxs-lookup"><span data-stu-id="199bf-172">Example</span></span>

<span data-ttu-id="199bf-173">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="199bf-173">**Request**</span></span>

<span data-ttu-id="199bf-174">Veja um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="199bf-174">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="199bf-175">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="199bf-175">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```

## <a name="related-articles"></a><span data-ttu-id="199bf-176">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="199bf-176">Related articles</span></span>

- [<span data-ttu-id="199bf-177">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="199bf-177">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="199bf-178">Saiba mais sobre limites e licenciamento da API</span><span class="sxs-lookup"><span data-stu-id="199bf-178">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="199bf-179">Noções sobre códigos de erro</span><span class="sxs-lookup"><span data-stu-id="199bf-179">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="199bf-180">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="199bf-180">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="199bf-181">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="199bf-181">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="199bf-182">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="199bf-182">Incidents overview</span></span>](incidents-overview.md)
