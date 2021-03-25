---
title: Obter a API do objeto MachineAction
description: Saiba como usar a API Get MachineAction para recuperar uma Ação de Máquina específica por sua ID no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, objeto machineaction
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 180179d5b1362ad4952618148b11007aa9efe91c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200060"
---
# <a name="get-machineaction-api"></a><span data-ttu-id="06c01-104">Obter a API machineAction</span><span class="sxs-lookup"><span data-stu-id="06c01-104">Get machineAction API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="06c01-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="06c01-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="06c01-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="06c01-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="06c01-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="06c01-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="06c01-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="06c01-108">API description</span></span>
<span data-ttu-id="06c01-109">Recupera a [Ação do Computador específica](machineaction.md) por sua ID.</span><span class="sxs-lookup"><span data-stu-id="06c01-109">Retrieves specific [Machine Action](machineaction.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="06c01-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="06c01-110">Limitations</span></span>
1. <span data-ttu-id="06c01-111">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="06c01-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="06c01-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="06c01-112">Permissions</span></span>
<span data-ttu-id="06c01-113">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="06c01-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="06c01-114">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="06c01-114">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="06c01-115">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="06c01-115">Permission type</span></span> |   <span data-ttu-id="06c01-116">Permissão</span><span class="sxs-lookup"><span data-stu-id="06c01-116">Permission</span></span>  |   <span data-ttu-id="06c01-117">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="06c01-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="06c01-118">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="06c01-118">Application</span></span> |   <span data-ttu-id="06c01-119">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="06c01-119">Machine.Read.All</span></span> |  <span data-ttu-id="06c01-120">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="06c01-120">'Read all machine profiles'</span></span>
<span data-ttu-id="06c01-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="06c01-121">Application</span></span> |   <span data-ttu-id="06c01-122">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="06c01-122">Machine.ReadWrite.All</span></span> | <span data-ttu-id="06c01-123">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="06c01-123">'Read and write all machine information'</span></span>
<span data-ttu-id="06c01-124">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="06c01-124">Delegated (work or school account)</span></span> | <span data-ttu-id="06c01-125">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="06c01-125">Machine.Read</span></span> | <span data-ttu-id="06c01-126">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="06c01-126">'Read machine information'</span></span>
<span data-ttu-id="06c01-127">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="06c01-127">Delegated (work or school account)</span></span> | <span data-ttu-id="06c01-128">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="06c01-128">Machine.ReadWrite</span></span> | <span data-ttu-id="06c01-129">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="06c01-129">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="06c01-130">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="06c01-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="06c01-131">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="06c01-131">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="06c01-132">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="06c01-132">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions/{id}
```

## <a name="request-headers"></a><span data-ttu-id="06c01-133">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="06c01-133">Request headers</span></span>

<span data-ttu-id="06c01-134">Nome</span><span class="sxs-lookup"><span data-stu-id="06c01-134">Name</span></span> | <span data-ttu-id="06c01-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="06c01-135">Type</span></span> | <span data-ttu-id="06c01-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="06c01-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="06c01-137">Autorização</span><span class="sxs-lookup"><span data-stu-id="06c01-137">Authorization</span></span> | <span data-ttu-id="06c01-138">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="06c01-138">String</span></span> | <span data-ttu-id="06c01-139">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="06c01-139">Bearer {token}.</span></span> <span data-ttu-id="06c01-140">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="06c01-140">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="06c01-141">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="06c01-141">Request body</span></span>
<span data-ttu-id="06c01-142">Vazio</span><span class="sxs-lookup"><span data-stu-id="06c01-142">Empty</span></span>

## <a name="response"></a><span data-ttu-id="06c01-143">Resposta</span><span class="sxs-lookup"><span data-stu-id="06c01-143">Response</span></span>
<span data-ttu-id="06c01-144">Se tiver êxito, este método retornará 200, código de resposta Ok com uma [entidade Ação de](machineaction.md) Máquina.</span><span class="sxs-lookup"><span data-stu-id="06c01-144">If successful, this method returns 200, Ok response code with a [Machine Action](machineaction.md) entity.</span></span> <span data-ttu-id="06c01-145">Se a entidade de ação do computador com a id especificada não for encontrada - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="06c01-145">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="06c01-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="06c01-146">Example</span></span>

<span data-ttu-id="06c01-147">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="06c01-147">**Request**</span></span>

<span data-ttu-id="06c01-148">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="06c01-148">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions/2e9da30d-27f6-4208-81f2-9cd3d67893ba
```

<span data-ttu-id="06c01-149">**Response**</span><span class="sxs-lookup"><span data-stu-id="06c01-149">**Response**</span></span>

<span data-ttu-id="06c01-150">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="06c01-150">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
    "type": "Isolate",
    "scope": "Selective",
    "requestor": "Analyst@TestPrd.onmicrosoft.com",
    "requestorComment": "test for docs",
    "status": "Succeeded",
    "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
    "computerDnsName": "desktop-test",
    "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
    "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
    "relatedFileInfo": null
}


```