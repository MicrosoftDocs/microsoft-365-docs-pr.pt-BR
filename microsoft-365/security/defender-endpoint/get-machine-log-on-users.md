---
title: Obter API de usuários de logon de máquina
description: Saiba como usar a API Obter usuários de logon do computador para recuperar uma coleção de usuários conectados em um dispositivo no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivo, fazer logoff, usuários
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
ms.openlocfilehash: 590bd1dee14e54359dd699e86795664819c23d05
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200085"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="3f0cf-104">Obter API de usuários de logon de máquina</span><span class="sxs-lookup"><span data-stu-id="3f0cf-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3f0cf-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3f0cf-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="3f0cf-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3f0cf-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3f0cf-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="3f0cf-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="3f0cf-108">API description</span></span>
<span data-ttu-id="3f0cf-109">Recupera uma coleção de usuários conectados em um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-109">Retrieves a collection of logged on users on a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="3f0cf-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="3f0cf-110">Limitations</span></span>
1. <span data-ttu-id="3f0cf-111">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="3f0cf-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="3f0cf-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="3f0cf-113">Permissions</span></span>
<span data-ttu-id="3f0cf-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3f0cf-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="3f0cf-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="3f0cf-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="3f0cf-116">Permission type</span></span> |   <span data-ttu-id="3f0cf-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="3f0cf-117">Permission</span></span>  |   <span data-ttu-id="3f0cf-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="3f0cf-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3f0cf-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3f0cf-119">Application</span></span> |   <span data-ttu-id="3f0cf-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="3f0cf-120">User.Read.All</span></span> | <span data-ttu-id="3f0cf-121">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="3f0cf-121">'Read user profiles'</span></span>
<span data-ttu-id="3f0cf-122">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="3f0cf-122">Delegated (work or school account)</span></span> | <span data-ttu-id="3f0cf-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="3f0cf-123">User.Read.All</span></span> | <span data-ttu-id="3f0cf-124">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="3f0cf-124">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="3f0cf-125">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="3f0cf-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="3f0cf-126">O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados".</span><span class="sxs-lookup"><span data-stu-id="3f0cf-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="3f0cf-127">Para obter mais informações, consulte [Create and manage roles](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="3f0cf-127">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="3f0cf-128">A resposta incluirá usuários somente se o dispositivo estiver visível para o usuário, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="3f0cf-129">Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3f0cf-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="3f0cf-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="3f0cf-130">HTTP request</span></span>
```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="3f0cf-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="3f0cf-131">Request headers</span></span>

<span data-ttu-id="3f0cf-132">Nome</span><span class="sxs-lookup"><span data-stu-id="3f0cf-132">Name</span></span> | <span data-ttu-id="3f0cf-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="3f0cf-133">Type</span></span> | <span data-ttu-id="3f0cf-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="3f0cf-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="3f0cf-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="3f0cf-135">Authorization</span></span> | <span data-ttu-id="3f0cf-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3f0cf-136">String</span></span> | <span data-ttu-id="3f0cf-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-137">Bearer {token}.</span></span> <span data-ttu-id="3f0cf-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3f0cf-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="3f0cf-139">Request body</span></span>
<span data-ttu-id="3f0cf-140">Vazio</span><span class="sxs-lookup"><span data-stu-id="3f0cf-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3f0cf-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="3f0cf-141">Response</span></span>
<span data-ttu-id="3f0cf-142">Se bem-sucedido e o dispositivo existir - 200 OK com a [lista](user.md) de entidades do usuário no corpo.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="3f0cf-143">Se o dispositivo não foi encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-143">If device was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="3f0cf-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3f0cf-144">Example</span></span>

<span data-ttu-id="3f0cf-145">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3f0cf-145">**Request**</span></span>

<span data-ttu-id="3f0cf-146">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

<span data-ttu-id="3f0cf-147">**Response**</span><span class="sxs-lookup"><span data-stu-id="3f0cf-147">**Response**</span></span>

<span data-ttu-id="3f0cf-148">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="3f0cf-148">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users",
    "value": [
        {
            "id": "contoso\\user1",
            "accountName": "user1",
            "accountDomain": "contoso",
            "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
            "firstSeen": "2019-12-18T08:02:54Z",
            "lastSeen": "2020-01-06T08:01:48Z",
            "logonTypes": "Interactive",
            "logOnMachinesCount": 8,
            "isDomainAdmin": true,
            "isOnlyNetworkUser": false
        },
        ...
    ]
}
```
