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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 634a381ca862dc7580d82168a4b9540acc0cd394
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229018"
---
# <a name="get-machine-logon-users-api"></a><span data-ttu-id="e7984-104">Obter API de usuários de logon de máquina</span><span class="sxs-lookup"><span data-stu-id="e7984-104">Get machine logon users API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e7984-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="e7984-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="e7984-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e7984-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e7984-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e7984-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e7984-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="e7984-108">API description</span></span>
<span data-ttu-id="e7984-109">Recupera uma coleção de usuários conectados em um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="e7984-109">Retrieves a collection of logged on users on a specific device.</span></span>

## <a name="limitations"></a><span data-ttu-id="e7984-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="e7984-110">Limitations</span></span>
1. <span data-ttu-id="e7984-111">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="e7984-111">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="e7984-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="e7984-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="e7984-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="e7984-113">Permissions</span></span>
<span data-ttu-id="e7984-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="e7984-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e7984-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="e7984-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e7984-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="e7984-116">Permission type</span></span> |<span data-ttu-id="e7984-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="e7984-117">Permission</span></span>|<span data-ttu-id="e7984-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="e7984-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e7984-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="e7984-119">Application</span></span> |<span data-ttu-id="e7984-120">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="e7984-120">User.Read.All</span></span> |<span data-ttu-id="e7984-121">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="e7984-121">'Read user profiles'</span></span>
<span data-ttu-id="e7984-122">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="e7984-122">Delegated (work or school account)</span></span> | <span data-ttu-id="e7984-123">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="e7984-123">User.Read.All</span></span> | <span data-ttu-id="e7984-124">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="e7984-124">'Read user profiles'</span></span>

> [!NOTE]
> <span data-ttu-id="e7984-125">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="e7984-125">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="e7984-126">O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados".</span><span class="sxs-lookup"><span data-stu-id="e7984-126">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="e7984-127">Para obter mais informações, consulte [Create and manage roles](user-roles.md)).</span><span class="sxs-lookup"><span data-stu-id="e7984-127">For more information, see [Create and manage roles](user-roles.md)).</span></span>
> - <span data-ttu-id="e7984-128">A resposta incluirá usuários somente se o dispositivo estiver visível para o usuário, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e7984-128">Response will include users only if the device is visible to the user, based on device group settings.</span></span> <span data-ttu-id="e7984-129">Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e7984-129">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="e7984-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="e7984-130">HTTP request</span></span>

```http
GET /api/machines/{id}/logonusers
```

## <a name="request-headers"></a><span data-ttu-id="e7984-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="e7984-131">Request headers</span></span>

<span data-ttu-id="e7984-132">Nome</span><span class="sxs-lookup"><span data-stu-id="e7984-132">Name</span></span> | <span data-ttu-id="e7984-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="e7984-133">Type</span></span> | <span data-ttu-id="e7984-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7984-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="e7984-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="e7984-135">Authorization</span></span> | <span data-ttu-id="e7984-136">String</span><span class="sxs-lookup"><span data-stu-id="e7984-136">String</span></span> | <span data-ttu-id="e7984-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="e7984-137">Bearer {token}.</span></span> <span data-ttu-id="e7984-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="e7984-138">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e7984-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="e7984-139">Request body</span></span>

<span data-ttu-id="e7984-140">Vazio</span><span class="sxs-lookup"><span data-stu-id="e7984-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="e7984-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="e7984-141">Response</span></span>

<span data-ttu-id="e7984-142">Se bem-sucedido e o dispositivo existir - 200 OK com a [lista](user.md) de entidades do usuário no corpo.</span><span class="sxs-lookup"><span data-stu-id="e7984-142">If successful and device exists - 200 OK with list of [user](user.md) entities in the body.</span></span> <span data-ttu-id="e7984-143">Se o dispositivo não foi encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="e7984-143">If device was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e7984-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e7984-144">Example</span></span>

### <a name="request"></a><span data-ttu-id="e7984-145">Solicitação</span><span class="sxs-lookup"><span data-stu-id="e7984-145">Request</span></span>

<span data-ttu-id="e7984-146">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="e7984-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/logonusers
```

### <a name="response"></a><span data-ttu-id="e7984-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="e7984-147">Response</span></span>

<span data-ttu-id="e7984-148">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="e7984-148">Here is an example of the response.</span></span>

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
