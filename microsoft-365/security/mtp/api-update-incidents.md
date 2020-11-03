---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando a API do Microsoft 365 defender
keywords: atualização, API, incidente
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
ms.openlocfilehash: 3f77980863b0c232166d736a6b557444df98c8ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844831"
---
# <a name="update-incidents-api"></a><span data-ttu-id="af722-104">Atualizar a API de incidentes</span><span class="sxs-lookup"><span data-stu-id="af722-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="af722-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="af722-105">**Applies to:**</span></span>
- <span data-ttu-id="af722-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="af722-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="af722-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="af722-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="af722-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="af722-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="af722-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="af722-109">API description</span></span>
<span data-ttu-id="af722-110">Atualiza as propriedades de um incidente existente.</span><span class="sxs-lookup"><span data-stu-id="af722-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="af722-111">As propriedades atualizáveis são: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` e ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="af722-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="af722-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="af722-112">Limitations</span></span>
1. <span data-ttu-id="af722-113">As limitações de taxa para esta API são de 50 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="af722-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="af722-114">Você pode definir ```determination``` somente se a classificação for definida como TruePositive.</span><span class="sxs-lookup"><span data-stu-id="af722-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="af722-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="af722-115">Permissions</span></span>
<span data-ttu-id="af722-116">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="af722-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="af722-117">Para saber mais, incluindo como escolher permissões, consulte [Access The Microsoft 365 defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="af722-117">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="af722-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="af722-118">Permission type</span></span> |   <span data-ttu-id="af722-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="af722-119">Permission</span></span>  |   <span data-ttu-id="af722-120">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="af722-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="af722-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="af722-121">Application</span></span> |   <span data-ttu-id="af722-122">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="af722-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="af722-123">' Ler e gravar todos os incidentes '</span><span class="sxs-lookup"><span data-stu-id="af722-123">'Read and write all incidents'</span></span>
<span data-ttu-id="af722-124">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="af722-124">Delegated (work or school account)</span></span> | <span data-ttu-id="af722-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="af722-125">Incident.ReadWrite</span></span> | <span data-ttu-id="af722-126">' Ler e gravar incidentes '</span><span class="sxs-lookup"><span data-stu-id="af722-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="af722-127">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="af722-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="af722-128">O usuário precisa ter permissão para atualizar o incidente no Portal.</span><span class="sxs-lookup"><span data-stu-id="af722-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="af722-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="af722-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="af722-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="af722-130">Request headers</span></span>

<span data-ttu-id="af722-131">Nome</span><span class="sxs-lookup"><span data-stu-id="af722-131">Name</span></span> | <span data-ttu-id="af722-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="af722-132">Type</span></span> | <span data-ttu-id="af722-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="af722-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="af722-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="af722-134">Authorization</span></span> | <span data-ttu-id="af722-135">String</span><span class="sxs-lookup"><span data-stu-id="af722-135">String</span></span> | <span data-ttu-id="af722-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="af722-136">Bearer {token}.</span></span> <span data-ttu-id="af722-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="af722-137">**Required**.</span></span>
<span data-ttu-id="af722-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="af722-138">Content-Type</span></span> | <span data-ttu-id="af722-139">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="af722-139">String</span></span> | <span data-ttu-id="af722-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="af722-140">application/json.</span></span> <span data-ttu-id="af722-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="af722-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="af722-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="af722-142">Request body</span></span>
<span data-ttu-id="af722-143">No corpo da solicitação, forneça os valores para os campos relevantes que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="af722-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="af722-144">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="af722-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="af722-145">Para obter um melhor desempenho, você não deve incluir valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="af722-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="af722-146">Propriedade</span><span class="sxs-lookup"><span data-stu-id="af722-146">Property</span></span> | <span data-ttu-id="af722-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="af722-147">Type</span></span> | <span data-ttu-id="af722-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="af722-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="af722-149">status</span><span class="sxs-lookup"><span data-stu-id="af722-149">status</span></span> | <span data-ttu-id="af722-150">Enum</span><span class="sxs-lookup"><span data-stu-id="af722-150">Enum</span></span> | <span data-ttu-id="af722-151">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="af722-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="af722-152">Os valores possíveis são ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="af722-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="af722-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="af722-153">assignedTo</span></span> | <span data-ttu-id="af722-154">string</span><span class="sxs-lookup"><span data-stu-id="af722-154">string</span></span> | <span data-ttu-id="af722-155">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="af722-155">Owner of the incident.</span></span>
<span data-ttu-id="af722-156">classificação</span><span class="sxs-lookup"><span data-stu-id="af722-156">classification</span></span> | <span data-ttu-id="af722-157">Enum</span><span class="sxs-lookup"><span data-stu-id="af722-157">Enum</span></span> | <span data-ttu-id="af722-158">Especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="af722-158">Specification of the alert.</span></span> <span data-ttu-id="af722-159">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="af722-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="af722-160">determinação</span><span class="sxs-lookup"><span data-stu-id="af722-160">determination</span></span> | <span data-ttu-id="af722-161">Enum</span><span class="sxs-lookup"><span data-stu-id="af722-161">Enum</span></span> | <span data-ttu-id="af722-162">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="af722-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="af722-163">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="af722-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="af722-164">categorias</span><span class="sxs-lookup"><span data-stu-id="af722-164">tags</span></span> | <span data-ttu-id="af722-165">Lista de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="af722-165">string List</span></span> | <span data-ttu-id="af722-166">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="af722-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="af722-167">Resposta</span><span class="sxs-lookup"><span data-stu-id="af722-167">Response</span></span>
<span data-ttu-id="af722-168">Se tiver êxito, este método retornará 200 OK e a entidade de incidente no corpo da resposta com as propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="af722-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="af722-169">Se o incidente com a ID especificada não for encontrado-404 não encontrado.</span><span class="sxs-lookup"><span data-stu-id="af722-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="af722-170">Exemplo</span><span class="sxs-lookup"><span data-stu-id="af722-170">Example</span></span>

<span data-ttu-id="af722-171">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="af722-171">**Request**</span></span>

<span data-ttu-id="af722-172">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="af722-172">Here is an example of the request.</span></span>

```
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"]
}
```


## <a name="related-topic"></a><span data-ttu-id="af722-173">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="af722-173">Related topic</span></span>
- [<span data-ttu-id="af722-174">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="af722-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="af722-175">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="af722-175">List incidents</span></span>](api-list-incidents.md)
