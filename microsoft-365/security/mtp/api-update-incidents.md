---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando a API de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: 8ad47453c7163bfac99c17f42986b818cdca603f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203608"
---
# <a name="update-incidents-api"></a><span data-ttu-id="007fe-104">Atualizar a API de incidentes</span><span class="sxs-lookup"><span data-stu-id="007fe-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="007fe-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="007fe-105">**Applies to:**</span></span>
- <span data-ttu-id="007fe-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="007fe-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="007fe-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="007fe-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="007fe-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="007fe-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="007fe-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="007fe-109">API description</span></span>
<span data-ttu-id="007fe-110">Atualiza as propriedades de um incidente existente.</span><span class="sxs-lookup"><span data-stu-id="007fe-110">Updates properties of existing incident.</span></span>
<br><span data-ttu-id="007fe-111">As propriedades atualizáveis são: ```status``` , ```determination``` , ```classification``` , ```assignedTo``` e ```tags``` .</span><span class="sxs-lookup"><span data-stu-id="007fe-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo``` and ```tags```.</span></span>


## <a name="limitations"></a><span data-ttu-id="007fe-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="007fe-112">Limitations</span></span>
1. <span data-ttu-id="007fe-113">As limitações de taxa para esta API são de 50 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="007fe-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>
2. <span data-ttu-id="007fe-114">Você pode definir ```determination``` somente se a classificação for definida como TruePositive.</span><span class="sxs-lookup"><span data-stu-id="007fe-114">You can set the ```determination``` only if the classification is set to TruePositive.</span></span>


## <a name="permissions"></a><span data-ttu-id="007fe-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="007fe-115">Permissions</span></span>
<span data-ttu-id="007fe-116">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="007fe-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="007fe-117">Para saber mais, incluindo como escolher permissões, confira [acessar as APIs de proteção contra ameaças da Microsoft](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="007fe-117">To learn more, including how to choose permissions, see [Access the Microsoft Threat Protection APIs](api-access.md).</span></span>

<span data-ttu-id="007fe-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="007fe-118">Permission type</span></span> |   <span data-ttu-id="007fe-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="007fe-119">Permission</span></span>  |   <span data-ttu-id="007fe-120">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="007fe-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="007fe-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="007fe-121">Application</span></span> |   <span data-ttu-id="007fe-122">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="007fe-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="007fe-123">' Ler e gravar todos os incidentes '</span><span class="sxs-lookup"><span data-stu-id="007fe-123">'Read and write all incidents'</span></span>
<span data-ttu-id="007fe-124">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="007fe-124">Delegated (work or school account)</span></span> | <span data-ttu-id="007fe-125">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="007fe-125">Incident.ReadWrite</span></span> | <span data-ttu-id="007fe-126">' Ler e gravar incidentes '</span><span class="sxs-lookup"><span data-stu-id="007fe-126">'Read and write incidents'</span></span>

>[!NOTE]
> <span data-ttu-id="007fe-127">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="007fe-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="007fe-128">O usuário precisa ter permissão para atualizar o incidente no Portal.</span><span class="sxs-lookup"><span data-stu-id="007fe-128">The user needs to have permission to update the incident in the portal.</span></span>


## <a name="http-request"></a><span data-ttu-id="007fe-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="007fe-129">HTTP request</span></span>

```
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="007fe-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="007fe-130">Request headers</span></span>

<span data-ttu-id="007fe-131">Nome</span><span class="sxs-lookup"><span data-stu-id="007fe-131">Name</span></span> | <span data-ttu-id="007fe-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="007fe-132">Type</span></span> | <span data-ttu-id="007fe-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="007fe-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="007fe-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="007fe-134">Authorization</span></span> | <span data-ttu-id="007fe-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="007fe-135">String</span></span> | <span data-ttu-id="007fe-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="007fe-136">Bearer {token}.</span></span> <span data-ttu-id="007fe-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="007fe-137">**Required**.</span></span>
<span data-ttu-id="007fe-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="007fe-138">Content-Type</span></span> | <span data-ttu-id="007fe-139">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="007fe-139">String</span></span> | <span data-ttu-id="007fe-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="007fe-140">application/json.</span></span> <span data-ttu-id="007fe-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="007fe-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="007fe-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="007fe-142">Request body</span></span>
<span data-ttu-id="007fe-143">No corpo da solicitação, forneça os valores para os campos relevantes que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="007fe-143">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="007fe-144">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="007fe-144">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="007fe-145">Para obter um melhor desempenho, você não deve incluir valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="007fe-145">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="007fe-146">Propriedade</span><span class="sxs-lookup"><span data-stu-id="007fe-146">Property</span></span> | <span data-ttu-id="007fe-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="007fe-147">Type</span></span> | <span data-ttu-id="007fe-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="007fe-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="007fe-149">status</span><span class="sxs-lookup"><span data-stu-id="007fe-149">status</span></span> | <span data-ttu-id="007fe-150">Enum</span><span class="sxs-lookup"><span data-stu-id="007fe-150">Enum</span></span> | <span data-ttu-id="007fe-151">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="007fe-151">Specifies the current status of the alert.</span></span> <span data-ttu-id="007fe-152">Os valores possíveis são ```Active``` : ```Resolved``` e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="007fe-152">Possible values are: ```Active```, ```Resolved``` and ```Redirected```.</span></span>
<span data-ttu-id="007fe-153">assignedTo</span><span class="sxs-lookup"><span data-stu-id="007fe-153">assignedTo</span></span> | <span data-ttu-id="007fe-154">string</span><span class="sxs-lookup"><span data-stu-id="007fe-154">string</span></span> | <span data-ttu-id="007fe-155">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="007fe-155">Owner of the incident.</span></span>
<span data-ttu-id="007fe-156">classificação</span><span class="sxs-lookup"><span data-stu-id="007fe-156">classification</span></span> | <span data-ttu-id="007fe-157">Enum</span><span class="sxs-lookup"><span data-stu-id="007fe-157">Enum</span></span> | <span data-ttu-id="007fe-158">Especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="007fe-158">Specification of the alert.</span></span> <span data-ttu-id="007fe-159">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="007fe-159">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="007fe-160">determinação</span><span class="sxs-lookup"><span data-stu-id="007fe-160">determination</span></span> | <span data-ttu-id="007fe-161">Enum</span><span class="sxs-lookup"><span data-stu-id="007fe-161">Enum</span></span> | <span data-ttu-id="007fe-162">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="007fe-162">Specifies the determination of the alert.</span></span> <span data-ttu-id="007fe-163">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="007fe-163">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="007fe-164">categorias</span><span class="sxs-lookup"><span data-stu-id="007fe-164">tags</span></span> | <span data-ttu-id="007fe-165">Lista de cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="007fe-165">string List</span></span> | <span data-ttu-id="007fe-166">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="007fe-166">List of Incident tags.</span></span>



## <a name="response"></a><span data-ttu-id="007fe-167">Resposta</span><span class="sxs-lookup"><span data-stu-id="007fe-167">Response</span></span>
<span data-ttu-id="007fe-168">Se tiver êxito, este método retornará 200 OK e a entidade de incidente no corpo da resposta com as propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="007fe-168">If successful, this method returns 200 OK, and the incident entity in the response body with the updated properties.</span></span> <span data-ttu-id="007fe-169">Se o incidente com a ID especificada não for encontrado-404 não encontrado.</span><span class="sxs-lookup"><span data-stu-id="007fe-169">If incident with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="007fe-170">Exemplo</span><span class="sxs-lookup"><span data-stu-id="007fe-170">Example</span></span>

<span data-ttu-id="007fe-171">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="007fe-171">**Request**</span></span>

<span data-ttu-id="007fe-172">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="007fe-172">Here is an example of the request.</span></span>

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


## <a name="related-topic"></a><span data-ttu-id="007fe-173">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="007fe-173">Related topic</span></span>
- [<span data-ttu-id="007fe-174">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="007fe-174">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="007fe-175">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="007fe-175">List incidents</span></span>](api-list-incidents.md)
