---
title: Obter informações de usuário relacionadas ao alerta
description: Saiba como usar a API Obter informações do usuário relacionadas ao alerta para recuperar o usuário relacionado a um alerta específico no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, get, alert, information, related, user
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
ms.technology: mde
ms.openlocfilehash: aee3c6fb381341c6823fbcb6766c0b761cb3413d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166281"
---
# <a name="get-alert-related-user-information-api"></a><span data-ttu-id="f3885-104">Obter API de informações de usuário relacionadas ao alerta</span><span class="sxs-lookup"><span data-stu-id="f3885-104">Get alert related user information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3885-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f3885-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3885-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f3885-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3885-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3885-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="f3885-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f3885-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f3885-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f3885-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f3885-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="f3885-110">API description</span></span>
<span data-ttu-id="f3885-111">Recupera o Usuário relacionado a um alerta específico.</span><span class="sxs-lookup"><span data-stu-id="f3885-111">Retrieves the User related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="f3885-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="f3885-112">Limitations</span></span>
1. <span data-ttu-id="f3885-113">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="f3885-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="f3885-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="f3885-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="f3885-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="f3885-115">Permissions</span></span>
<span data-ttu-id="f3885-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="f3885-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f3885-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f3885-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f3885-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="f3885-118">Permission type</span></span> |   <span data-ttu-id="f3885-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="f3885-119">Permission</span></span>  |   <span data-ttu-id="f3885-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="f3885-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f3885-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="f3885-121">Application</span></span> |   <span data-ttu-id="f3885-122">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f3885-122">User.Read.All</span></span> | <span data-ttu-id="f3885-123">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="f3885-123">'Read user profiles'</span></span>
<span data-ttu-id="f3885-124">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="f3885-124">Delegated (work or school account)</span></span> | <span data-ttu-id="f3885-125">User.Read.All</span><span class="sxs-lookup"><span data-stu-id="f3885-125">User.Read.All</span></span> | <span data-ttu-id="f3885-126">'Ler perfis de usuário'</span><span class="sxs-lookup"><span data-stu-id="f3885-126">'Read user profiles'</span></span>

>[!Note]
> <span data-ttu-id="f3885-127">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="f3885-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="f3885-128">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="f3885-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="f3885-129">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="f3885-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f3885-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="f3885-130">HTTP request</span></span>
```
GET /api/alerts/{id}/user
```

## <a name="request-headers"></a><span data-ttu-id="f3885-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="f3885-131">Request headers</span></span>

<span data-ttu-id="f3885-132">Nome</span><span class="sxs-lookup"><span data-stu-id="f3885-132">Name</span></span> | <span data-ttu-id="f3885-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="f3885-133">Type</span></span> | <span data-ttu-id="f3885-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="f3885-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="f3885-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="f3885-135">Authorization</span></span> | <span data-ttu-id="f3885-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f3885-136">String</span></span> | <span data-ttu-id="f3885-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f3885-137">Bearer {token}.</span></span> <span data-ttu-id="f3885-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="f3885-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="f3885-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="f3885-139">Request body</span></span>
<span data-ttu-id="f3885-140">Vazio</span><span class="sxs-lookup"><span data-stu-id="f3885-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f3885-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="f3885-141">Response</span></span>
<span data-ttu-id="f3885-142">Se bem-sucedido e alerta e um usuário existir - 200 OK com o usuário no corpo.</span><span class="sxs-lookup"><span data-stu-id="f3885-142">If successful and alert and a user exists - 200 OK with user in the body.</span></span> <span data-ttu-id="f3885-143">Se o alerta ou o usuário não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="f3885-143">If alert or user not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="f3885-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f3885-144">Example</span></span>

<span data-ttu-id="f3885-145">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="f3885-145">**Request**</span></span>

<span data-ttu-id="f3885-146">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f3885-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/user
```

<span data-ttu-id="f3885-147">**Response**</span><span class="sxs-lookup"><span data-stu-id="f3885-147">**Response**</span></span>

<span data-ttu-id="f3885-148">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="f3885-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Users/$entity",
    "id": "contoso\\user1",
    "accountName": "user1",
    "accountDomain": "contoso",
    "accountSid": "S-1-5-21-72051607-1745760036-109187956-93922",
    "firstSeen": "2019-12-08T06:33:39Z",
    "lastSeen": "2020-01-05T06:58:34Z",
    "mostPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "leastPrevalentMachineId": "0111b647235c26159bec3e5eb6c8c3a0cc3ab766",
    "logonTypes": "Network",
    "logOnMachinesCount": 1,
    "isDomainAdmin": false,
    "isOnlyNetworkUser": false
}
```