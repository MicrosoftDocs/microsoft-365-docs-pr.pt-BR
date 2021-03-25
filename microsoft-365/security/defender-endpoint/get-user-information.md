---
title: Obter API de informações do usuário
description: Saiba como usar a API Obter informações do usuário para recuperar uma entidade user por chave ou nome de usuário no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, usuário, informações do usuário
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
ms.openlocfilehash: 1c5b8fa6e0f1fd887c857bd4e6451a5e59b708af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198536"
---
# <a name="get-user-information-api"></a><span data-ttu-id="72059-104">Obter API de informações do usuário</span><span class="sxs-lookup"><span data-stu-id="72059-104">Get user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="72059-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="72059-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="72059-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="72059-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="72059-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="72059-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

> <span data-ttu-id="72059-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="72059-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="72059-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="72059-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)
<span data-ttu-id="72059-110">Recuperar uma entidade User por chave (nome de usuário).</span><span class="sxs-lookup"><span data-stu-id="72059-110">Retrieve a User entity by key (user name).</span></span>

## <a name="permissions"></a><span data-ttu-id="72059-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="72059-111">Permissions</span></span>
<span data-ttu-id="72059-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="72059-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="72059-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="72059-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="72059-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="72059-114">Permission type</span></span> |   <span data-ttu-id="72059-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="72059-115">Permission</span></span>  |   <span data-ttu-id="72059-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="72059-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="72059-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="72059-117">Application</span></span> |   <span data-ttu-id="72059-118">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="72059-118">User.Read.All</span></span> | <span data-ttu-id="72059-119">'Ler todos os perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="72059-119">'Read all user profiles'</span></span>

## <a name="http-request"></a><span data-ttu-id="72059-120">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="72059-120">HTTP request</span></span>
```
GET /api/users/{id}/
```

## <a name="request-headers"></a><span data-ttu-id="72059-121">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="72059-121">Request headers</span></span>

<span data-ttu-id="72059-122">Nome</span><span class="sxs-lookup"><span data-stu-id="72059-122">Name</span></span> | <span data-ttu-id="72059-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="72059-123">Type</span></span> | <span data-ttu-id="72059-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="72059-124">Description</span></span>
:---|:---|:---
<span data-ttu-id="72059-125">Autorização</span><span class="sxs-lookup"><span data-stu-id="72059-125">Authorization</span></span> | <span data-ttu-id="72059-126">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="72059-126">String</span></span> | <span data-ttu-id="72059-127">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="72059-127">Bearer {token}.</span></span> <span data-ttu-id="72059-128">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="72059-128">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="72059-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="72059-129">Request body</span></span>
<span data-ttu-id="72059-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="72059-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="72059-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="72059-131">Response</span></span>
<span data-ttu-id="72059-132">Se bem-sucedido e o usuário existir - 200 OK com [entidade de](user.md) usuário no corpo.</span><span class="sxs-lookup"><span data-stu-id="72059-132">If successful and user exists - 200 OK with [user](user.md) entity in the body.</span></span> <span data-ttu-id="72059-133">Se o usuário não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="72059-133">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="72059-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="72059-134">Example</span></span>

<span data-ttu-id="72059-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="72059-135">**Request**</span></span>

<span data-ttu-id="72059-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="72059-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/users/user1
Content-type: application/json
```

<span data-ttu-id="72059-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="72059-137">**Response**</span></span>

<span data-ttu-id="72059-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="72059-138">Here is an example of the response.</span></span>


```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "user1",
    "firstSeen": "2018-08-02T00:00:00Z",
    "lastSeen": "2018-08-04T00:00:00Z",
    "mostPrevalentMachineId": null,
    "leastPrevalentMachineId": null,
    "logonTypes": "Network",
    "logOnMachinesCount": 3,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": null
}
```
