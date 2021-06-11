---
title: Obter API de incidente
description: Saiba como usar a API Obter incidentes para obter um único incidente no Microsoft 365 Defender.
keywords: apis, api gráfica, apis com suporte, obter, arquivo, hash
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c578a353501ac7b38ac541b0200ffaad1d6743e1
ms.sourcegitcommit: 03aa8ed22d9ef685a851e28c7d0cfb725732fe4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52888440"
---
# <a name="get-incident-information-api"></a><span data-ttu-id="260f9-104">Obter API de informações de incidentes</span><span class="sxs-lookup"><span data-stu-id="260f9-104">Get incident information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="260f9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="260f9-105">**Applies to:**</span></span>
- [<span data-ttu-id="260f9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="260f9-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="260f9-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="260f9-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="260f9-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="260f9-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="260f9-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="260f9-109">API description</span></span>
<span data-ttu-id="260f9-110">Recupera um incidente específico por sua ID</span><span class="sxs-lookup"><span data-stu-id="260f9-110">Retrieves a specific incident by its ID</span></span>


## <a name="limitations"></a><span data-ttu-id="260f9-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="260f9-111">Limitations</span></span>
1. <span data-ttu-id="260f9-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="260f9-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="260f9-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="260f9-113">Permissions</span></span>
<span data-ttu-id="260f9-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="260f9-114">One of the following permissions is required to call this API.</span></span> 

<span data-ttu-id="260f9-115">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="260f9-115">Permission type</span></span> |   <span data-ttu-id="260f9-116">Permissão</span><span class="sxs-lookup"><span data-stu-id="260f9-116">Permission</span></span>  |   <span data-ttu-id="260f9-117">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="260f9-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="260f9-118">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="260f9-118">Application</span></span> |   <span data-ttu-id="260f9-119">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="260f9-119">Incident.Read.All</span></span> | <span data-ttu-id="260f9-120">'Ler todos os incidentes'</span><span class="sxs-lookup"><span data-stu-id="260f9-120">'Read all Incidents'</span></span>
<span data-ttu-id="260f9-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="260f9-121">Application</span></span> |   <span data-ttu-id="260f9-122">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="260f9-122">Incident.ReadWrite.All</span></span> |    <span data-ttu-id="260f9-123">'Ler e gravar todos os incidentes'</span><span class="sxs-lookup"><span data-stu-id="260f9-123">'Read and write all Incidents'</span></span>
<span data-ttu-id="260f9-124">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="260f9-124">Delegated (work or school account)</span></span> | <span data-ttu-id="260f9-125">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="260f9-125">Incident.Read</span></span> | <span data-ttu-id="260f9-126">'Incidentes de leitura'</span><span class="sxs-lookup"><span data-stu-id="260f9-126">'Read Incidents'</span></span>
<span data-ttu-id="260f9-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="260f9-127">Delegated (work or school account)</span></span> | <span data-ttu-id="260f9-128">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="260f9-128">Incident.ReadWrite</span></span> | <span data-ttu-id="260f9-129">'Incidentes de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="260f9-129">'Read and write Incidents'</span></span>

>[!Note]
> <span data-ttu-id="260f9-130">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="260f9-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="260f9-131">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados'</span><span class="sxs-lookup"><span data-stu-id="260f9-131">The user needs to have at least the following role permission: 'View Data'</span></span>
>- <span data-ttu-id="260f9-132">A resposta incluirá apenas incidentes aos que o usuário está exposto</span><span class="sxs-lookup"><span data-stu-id="260f9-132">The response will only include incidents that the user is exposed to</span></span>

## <a name="http-request"></a><span data-ttu-id="260f9-133">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="260f9-133">HTTP request</span></span>

```console
GET .../api/incidents/{id} 
```

## <a name="request-headers"></a><span data-ttu-id="260f9-134">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="260f9-134">Request headers</span></span>

<span data-ttu-id="260f9-135">Nome</span><span class="sxs-lookup"><span data-stu-id="260f9-135">Name</span></span> | <span data-ttu-id="260f9-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="260f9-136">Type</span></span> | <span data-ttu-id="260f9-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="260f9-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="260f9-138">Autorização</span><span class="sxs-lookup"><span data-stu-id="260f9-138">Authorization</span></span> | <span data-ttu-id="260f9-139">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="260f9-139">String</span></span> | <span data-ttu-id="260f9-140">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="260f9-140">Bearer {token}.</span></span> <span data-ttu-id="260f9-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="260f9-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="260f9-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="260f9-142">Request body</span></span>
<span data-ttu-id="260f9-143">Vazio</span><span class="sxs-lookup"><span data-stu-id="260f9-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="260f9-144">Resposta</span><span class="sxs-lookup"><span data-stu-id="260f9-144">Response</span></span>

<span data-ttu-id="260f9-145">Se tiver êxito, este método retornará 200 OK e a entidade incidente no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="260f9-145">If successful, this method returns 200 OK, and the incident entity in the response body.</span></span> <span data-ttu-id="260f9-146">Se o incidente com a id especificada não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="260f9-146">If incident with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="260f9-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="260f9-147">Example</span></span>

<span data-ttu-id="260f9-148">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="260f9-148">**Request**</span></span>

<span data-ttu-id="260f9-149">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="260f9-149">Here is an example of the request.</span></span>

```http
GET https://api.security.microsoft.com/api/incidents/{id}
```
