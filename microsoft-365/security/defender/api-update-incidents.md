---
title: Atualizar a API incidente
description: Saiba como atualizar incidentes usando Microsoft 365 API do Defender
keywords: atualização, api, incidente
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
ms.openlocfilehash: e3f3919d067078ef1fd1e116dc52e8a73c0726d9
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571776"
---
# <a name="update-incident-api"></a><span data-ttu-id="9e488-104">Atualizar a API incidente</span><span class="sxs-lookup"><span data-stu-id="9e488-104">Update incident API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9e488-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9e488-105">**Applies to:**</span></span>

- <span data-ttu-id="9e488-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e488-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e488-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="9e488-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9e488-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="9e488-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="9e488-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9e488-109">API description</span></span>

<span data-ttu-id="9e488-110">Atualiza as propriedades do incidente existente.</span><span class="sxs-lookup"><span data-stu-id="9e488-110">Updates properties of existing incident.</span></span> <span data-ttu-id="9e488-111">As propriedades de updatable são: ```status``` , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="9e488-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="9e488-112">Cotas, alocação de recursos e outras restrições</span><span class="sxs-lookup"><span data-stu-id="9e488-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="9e488-113">Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de estrangulamento.</span><span class="sxs-lookup"><span data-stu-id="9e488-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="9e488-114">Você só pode definir a `determination` propriedade se estiver definida como `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="9e488-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="9e488-115">Se sua solicitação for estrangulada, ela retornará um `429` código de resposta.</span><span class="sxs-lookup"><span data-stu-id="9e488-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="9e488-116">O corpo de resposta indicará o momento em que você pode começar a fazer novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="9e488-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="9e488-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="9e488-117">Permissions</span></span>

<span data-ttu-id="9e488-118">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="9e488-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9e488-119">Para saber mais, incluindo como escolher permissões, consulte [Acessar as APIs Microsoft 365 Defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="9e488-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="9e488-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9e488-120">Permission type</span></span> | <span data-ttu-id="9e488-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="9e488-121">Permission</span></span> | <span data-ttu-id="9e488-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9e488-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="9e488-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9e488-123">Application</span></span> | <span data-ttu-id="9e488-124">Incidente.ReadWrite.Todos</span><span class="sxs-lookup"><span data-stu-id="9e488-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="9e488-125">Leia e escreva todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="9e488-125">Read and write all incidents</span></span>
<span data-ttu-id="9e488-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9e488-126">Delegated (work or school account)</span></span> | <span data-ttu-id="9e488-127">Incidente.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9e488-127">Incident.ReadWrite</span></span> | <span data-ttu-id="9e488-128">Leia e escreva incidentes</span><span class="sxs-lookup"><span data-stu-id="9e488-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="9e488-129">Ao obter um token usando credenciais do usuário, o usuário precisa ter permissão para atualizar o incidente no portal.</span><span class="sxs-lookup"><span data-stu-id="9e488-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="9e488-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9e488-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="9e488-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9e488-131">Request headers</span></span>

<span data-ttu-id="9e488-132">Nome</span><span class="sxs-lookup"><span data-stu-id="9e488-132">Name</span></span> | <span data-ttu-id="9e488-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="9e488-133">Type</span></span> | <span data-ttu-id="9e488-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e488-134">Description</span></span>
-|-|-
<span data-ttu-id="9e488-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="9e488-135">Authorization</span></span> | <span data-ttu-id="9e488-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9e488-136">String</span></span> | <span data-ttu-id="9e488-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9e488-137">Bearer {token}.</span></span> <span data-ttu-id="9e488-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9e488-138">**Required**.</span></span>
<span data-ttu-id="9e488-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9e488-139">Content-Type</span></span> | <span data-ttu-id="9e488-140">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="9e488-140">String</span></span> | <span data-ttu-id="9e488-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="9e488-141">application/json.</span></span> <span data-ttu-id="9e488-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9e488-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9e488-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9e488-143">Request body</span></span>

<span data-ttu-id="9e488-144">No órgão de solicitação, forneça os valores para os campos que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="9e488-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="9e488-145">As propriedades existentes que não estão incluídas no órgão de solicitação manterão seus valores, a menos que tenham que ser recalculadas devido a alterações nos valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="9e488-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="9e488-146">Para obter melhor desempenho, você deve omitir valores existentes que não mudaram.</span><span class="sxs-lookup"><span data-stu-id="9e488-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="9e488-147">Propriedade</span><span class="sxs-lookup"><span data-stu-id="9e488-147">Property</span></span> | <span data-ttu-id="9e488-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="9e488-148">Type</span></span> | <span data-ttu-id="9e488-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="9e488-149">Description</span></span>
-|-|-
<span data-ttu-id="9e488-150">status</span><span class="sxs-lookup"><span data-stu-id="9e488-150">status</span></span> | <span data-ttu-id="9e488-151">Enum</span><span class="sxs-lookup"><span data-stu-id="9e488-151">Enum</span></span> | <span data-ttu-id="9e488-152">Especifica o estado atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="9e488-153">Os valores possíveis são: ```Active``` ```Resolved``` , , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="9e488-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="9e488-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="9e488-154">assignedTo</span></span> | <span data-ttu-id="9e488-155">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9e488-155">string</span></span> | <span data-ttu-id="9e488-156">O dono do incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-156">Owner of the incident.</span></span>
<span data-ttu-id="9e488-157">classificação</span><span class="sxs-lookup"><span data-stu-id="9e488-157">classification</span></span> | <span data-ttu-id="9e488-158">Enum</span><span class="sxs-lookup"><span data-stu-id="9e488-158">Enum</span></span> | <span data-ttu-id="9e488-159">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-159">Specification of the incident.</span></span> <span data-ttu-id="9e488-160">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="9e488-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="9e488-161">determinação</span><span class="sxs-lookup"><span data-stu-id="9e488-161">determination</span></span> | <span data-ttu-id="9e488-162">Enum</span><span class="sxs-lookup"><span data-stu-id="9e488-162">Enum</span></span> | <span data-ttu-id="9e488-163">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="9e488-164">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="9e488-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="9e488-165">tags</span><span class="sxs-lookup"><span data-stu-id="9e488-165">tags</span></span> | <span data-ttu-id="9e488-166">lista de strings</span><span class="sxs-lookup"><span data-stu-id="9e488-166">string List</span></span> | <span data-ttu-id="9e488-167">Lista de etiquetas de incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-167">List of Incident tags.</span></span>
<span data-ttu-id="9e488-168">comment</span><span class="sxs-lookup"><span data-stu-id="9e488-168">comment</span></span> | <span data-ttu-id="9e488-169">string</span><span class="sxs-lookup"><span data-stu-id="9e488-169">string</span></span> | <span data-ttu-id="9e488-170">Comentário a ser adicionado ao incidente.</span><span class="sxs-lookup"><span data-stu-id="9e488-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="9e488-171">Resposta</span><span class="sxs-lookup"><span data-stu-id="9e488-171">Response</span></span>

<span data-ttu-id="9e488-172">Se for bem sucedido, este método retorna `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="9e488-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="9e488-173">O corpo de resposta conterá a entidade incidente com propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="9e488-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="9e488-174">Se um incidente com a ID especificada não foi encontrado, o método retorna `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="9e488-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="9e488-175">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9e488-175">Example</span></span>

<span data-ttu-id="9e488-176">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9e488-176">**Request**</span></span>

<span data-ttu-id="9e488-177">Aqui está um exemplo do pedido.</span><span class="sxs-lookup"><span data-stu-id="9e488-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="9e488-178">**Response**</span><span class="sxs-lookup"><span data-stu-id="9e488-178">**Response**</span></span>

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "TruePositive",
    "determination": "Malware",
    "tags": ["Yossi's playground", "Don't mess with the Zohan"],
    "comments": [
          {
              "comment": "pen testing",
              "createdBy": "secop2@contoso.com",
              "createdTime": "2021-05-02T09:34:21.5519738Z"
          },
          {
              "comment": "valid incident",
              "createdBy": "secop2@contoso.comt",
              "createdTime": "2021-05-02T09:36:27.6652581Z"
          }
      ]
}
```

## <a name="related-articles"></a><span data-ttu-id="9e488-179">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="9e488-179">Related articles</span></span>

- [<span data-ttu-id="9e488-180">Acesse as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9e488-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9e488-181">Conheça os limites e licenciamento da API</span><span class="sxs-lookup"><span data-stu-id="9e488-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="9e488-182">Entenda códigos de erro</span><span class="sxs-lookup"><span data-stu-id="9e488-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="9e488-183">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="9e488-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="9e488-184">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="9e488-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="9e488-185">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="9e488-185">Incidents overview</span></span>](incidents-overview.md)
