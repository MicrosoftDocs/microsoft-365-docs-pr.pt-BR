---
title: Atualizar a API de incidentes
description: Saiba como atualizar incidentes usando Microsoft 365 API do Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e3b445b2f9612f0113f353450ca7bf0b8a1a2bb2
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730853"
---
# <a name="update-incidents-api"></a><span data-ttu-id="23987-104">Atualizar a API de incidentes</span><span class="sxs-lookup"><span data-stu-id="23987-104">Update incidents API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="23987-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="23987-105">**Applies to:**</span></span>

- [<span data-ttu-id="23987-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23987-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="23987-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="23987-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="23987-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="23987-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="23987-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="23987-109">API description</span></span>

<span data-ttu-id="23987-110">Atualiza as propriedades do incidente existente.</span><span class="sxs-lookup"><span data-stu-id="23987-110">Updates properties of existing incident.</span></span> <span data-ttu-id="23987-111">As propriedades atualizáveis são: ```status``` , , , , e ```determination``` ```classification``` ```assignedTo``` ```tags``` ```comments``` .</span><span class="sxs-lookup"><span data-stu-id="23987-111">Updatable properties are: ```status```, ```determination```, ```classification```, ```assignedTo```, ```tags```, and ```comments```.</span></span>

### <a name="quotas-resource-allocation-and-other-constraints"></a><span data-ttu-id="23987-112">Cotas, alocação de recursos e outras restrições</span><span class="sxs-lookup"><span data-stu-id="23987-112">Quotas, resource allocation, and other constraints</span></span>

1. <span data-ttu-id="23987-113">Você pode fazer até 50 chamadas por minuto ou 1500 chamadas por hora antes de atingir o limite de limite de limite.</span><span class="sxs-lookup"><span data-stu-id="23987-113">You can make up to 50 calls per minute or 1500 calls per hour before you hit the throttling threshold.</span></span>
2. <span data-ttu-id="23987-114">Você só pode definir `determination` a propriedade se estiver definida como `classification` TruePositive.</span><span class="sxs-lookup"><span data-stu-id="23987-114">You can set the `determination` property only if `classification` is set to TruePositive.</span></span>

<span data-ttu-id="23987-115">Se sua solicitação for acelerada, ela retornará um `429` código de resposta.</span><span class="sxs-lookup"><span data-stu-id="23987-115">If your request is throttled, it will return a `429` response code.</span></span> <span data-ttu-id="23987-116">O corpo da resposta indicará a hora em que você pode começar a fazer novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="23987-116">The response body will indicate the time when you can begin making new calls.</span></span>

## <a name="permissions"></a><span data-ttu-id="23987-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="23987-117">Permissions</span></span>

<span data-ttu-id="23987-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="23987-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="23987-119">Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft 365 Defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="23987-119">To learn more, including how to choose permissions, see [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="23987-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="23987-120">Permission type</span></span> | <span data-ttu-id="23987-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="23987-121">Permission</span></span> | <span data-ttu-id="23987-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="23987-122">Permission display name</span></span>
-|-|-
<span data-ttu-id="23987-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="23987-123">Application</span></span> | <span data-ttu-id="23987-124">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="23987-124">Incident.ReadWrite.All</span></span> | <span data-ttu-id="23987-125">Ler e gravar todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="23987-125">Read and write all incidents</span></span>
<span data-ttu-id="23987-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="23987-126">Delegated (work or school account)</span></span> | <span data-ttu-id="23987-127">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="23987-127">Incident.ReadWrite</span></span> | <span data-ttu-id="23987-128">Incidentes de leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="23987-128">Read and write incidents</span></span>

> [!NOTE]
> <span data-ttu-id="23987-129">Ao obter um token usando credenciais de usuário, o usuário precisa ter permissão para atualizar o incidente no portal.</span><span class="sxs-lookup"><span data-stu-id="23987-129">When obtaining a token using user credentials, the user needs to have permission to update the incident in the portal.</span></span>

## <a name="http-request"></a><span data-ttu-id="23987-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="23987-130">HTTP request</span></span>

```HTTP
PATCH /api/incidents/{id}
```

## <a name="request-headers"></a><span data-ttu-id="23987-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="23987-131">Request headers</span></span>

<span data-ttu-id="23987-132">Nome</span><span class="sxs-lookup"><span data-stu-id="23987-132">Name</span></span> | <span data-ttu-id="23987-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="23987-133">Type</span></span> | <span data-ttu-id="23987-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="23987-134">Description</span></span>
-|-|-
<span data-ttu-id="23987-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="23987-135">Authorization</span></span> | <span data-ttu-id="23987-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="23987-136">String</span></span> | <span data-ttu-id="23987-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="23987-137">Bearer {token}.</span></span> <span data-ttu-id="23987-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="23987-138">**Required**.</span></span>
<span data-ttu-id="23987-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="23987-139">Content-Type</span></span> | <span data-ttu-id="23987-140">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="23987-140">String</span></span> | <span data-ttu-id="23987-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="23987-141">application/json.</span></span> <span data-ttu-id="23987-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="23987-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="23987-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="23987-143">Request body</span></span>

<span data-ttu-id="23987-144">No corpo da solicitação, fornece os valores para os campos que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="23987-144">In the request body, supply the values for the fields that should be updated.</span></span> <span data-ttu-id="23987-145">As propriedades existentes que não estão incluídas no corpo da solicitação manterão seus valores, a menos que elas tenham que ser recalculadas devido a alterações nos valores relacionados.</span><span class="sxs-lookup"><span data-stu-id="23987-145">Existing properties that aren't included in the request body will maintain their values, unless they have to be recalculated due to changes to related values.</span></span> <span data-ttu-id="23987-146">Para melhor desempenho, você deve omitir valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="23987-146">For best performance, you should omit existing values that haven't changed.</span></span>

<span data-ttu-id="23987-147">Propriedade</span><span class="sxs-lookup"><span data-stu-id="23987-147">Property</span></span> | <span data-ttu-id="23987-148">Tipo</span><span class="sxs-lookup"><span data-stu-id="23987-148">Type</span></span> | <span data-ttu-id="23987-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="23987-149">Description</span></span>
-|-|-
<span data-ttu-id="23987-150">status</span><span class="sxs-lookup"><span data-stu-id="23987-150">status</span></span> | <span data-ttu-id="23987-151">Enum</span><span class="sxs-lookup"><span data-stu-id="23987-151">Enum</span></span> | <span data-ttu-id="23987-152">Especifica o status atual do incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-152">Specifies the current status of the incident.</span></span> <span data-ttu-id="23987-153">Os valores possíveis são: ```Active``` ```Resolved``` , e ```Redirected``` .</span><span class="sxs-lookup"><span data-stu-id="23987-153">Possible values are: ```Active```, ```Resolved```, and ```Redirected```.</span></span>
<span data-ttu-id="23987-154">assignedTo</span><span class="sxs-lookup"><span data-stu-id="23987-154">assignedTo</span></span> | <span data-ttu-id="23987-155">string</span><span class="sxs-lookup"><span data-stu-id="23987-155">string</span></span> | <span data-ttu-id="23987-156">Proprietário do incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-156">Owner of the incident.</span></span>
<span data-ttu-id="23987-157">classificação</span><span class="sxs-lookup"><span data-stu-id="23987-157">classification</span></span> | <span data-ttu-id="23987-158">Enum</span><span class="sxs-lookup"><span data-stu-id="23987-158">Enum</span></span> | <span data-ttu-id="23987-159">Especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-159">Specification of the incident.</span></span> <span data-ttu-id="23987-160">Os valores possíveis são: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span><span class="sxs-lookup"><span data-stu-id="23987-160">Possible values are: ```Unknown```, ```FalsePositive```, ```TruePositive```.</span></span>
<span data-ttu-id="23987-161">determinação</span><span class="sxs-lookup"><span data-stu-id="23987-161">determination</span></span> | <span data-ttu-id="23987-162">Enum</span><span class="sxs-lookup"><span data-stu-id="23987-162">Enum</span></span> | <span data-ttu-id="23987-163">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-163">Specifies the determination of the incident.</span></span> <span data-ttu-id="23987-164">Os valores possíveis são: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span><span class="sxs-lookup"><span data-stu-id="23987-164">Possible values are: ```NotAvailable```, ```Apt```, ```Malware```, ```SecurityPersonnel```, ```SecurityTesting```, ```UnwantedSoftware```, ```Other```.</span></span>
<span data-ttu-id="23987-165">categorias</span><span class="sxs-lookup"><span data-stu-id="23987-165">tags</span></span> | <span data-ttu-id="23987-166">string List</span><span class="sxs-lookup"><span data-stu-id="23987-166">string List</span></span> | <span data-ttu-id="23987-167">Lista de marcas de incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-167">List of Incident tags.</span></span>
<span data-ttu-id="23987-168">comment</span><span class="sxs-lookup"><span data-stu-id="23987-168">comment</span></span> | <span data-ttu-id="23987-169">string</span><span class="sxs-lookup"><span data-stu-id="23987-169">string</span></span> | <span data-ttu-id="23987-170">Comentário a ser adicionado ao incidente.</span><span class="sxs-lookup"><span data-stu-id="23987-170">Comment to be added to the incident.</span></span>

## <a name="response"></a><span data-ttu-id="23987-171">Resposta</span><span class="sxs-lookup"><span data-stu-id="23987-171">Response</span></span>

<span data-ttu-id="23987-172">Se tiver êxito, este método retornará `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="23987-172">If successful, this method returns `200 OK`.</span></span> <span data-ttu-id="23987-173">O corpo da resposta conterá a entidade de incidente com propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="23987-173">The response body will contain the incident entity with updated properties.</span></span> <span data-ttu-id="23987-174">Se um incidente com a ID especificada não for encontrado, o método retornará `404 Not Found` .</span><span class="sxs-lookup"><span data-stu-id="23987-174">If an incident with the specified ID wasn't found, the method returns `404 Not Found`.</span></span>

## <a name="example"></a><span data-ttu-id="23987-175">Exemplo</span><span class="sxs-lookup"><span data-stu-id="23987-175">Example</span></span>

<span data-ttu-id="23987-176">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="23987-176">**Request**</span></span>

<span data-ttu-id="23987-177">Veja um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="23987-177">Here's an example of the request.</span></span>

```HTTP
 PATCH https://api.security.microsoft.com/api/incidents/{id}
```

<span data-ttu-id="23987-178">**Response**</span><span class="sxs-lookup"><span data-stu-id="23987-178">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="23987-179">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="23987-179">Related articles</span></span>

- [<span data-ttu-id="23987-180">Acessar as APIs Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23987-180">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="23987-181">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="23987-181">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="23987-182">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="23987-182">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="23987-183">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="23987-183">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="23987-184">Listar incidentes</span><span class="sxs-lookup"><span data-stu-id="23987-184">List incidents</span></span>](api-list-incidents.md)
- [<span data-ttu-id="23987-185">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="23987-185">Incidents overview</span></span>](incidents-overview.md)
