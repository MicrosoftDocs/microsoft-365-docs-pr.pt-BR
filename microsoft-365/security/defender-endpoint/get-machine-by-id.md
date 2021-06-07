---
title: Obter máquina por API de ID
description: Saiba como usar a API Get machine by ID para recuperar um computador pela ID do dispositivo ou nome do computador no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos, entidade, id
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
ms.openlocfilehash: e4ed5a68b0f4c5e9472702d3cc2798a810e4f84e
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769468"
---
# <a name="get-machine-by-id-api"></a><span data-ttu-id="95919-104">Obter máquina por API de ID</span><span class="sxs-lookup"><span data-stu-id="95919-104">Get machine by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95919-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="95919-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>


> <span data-ttu-id="95919-106">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="95919-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95919-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="95919-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="95919-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="95919-108">API description</span></span>
<span data-ttu-id="95919-109">Recupera o [Computador específico](machine.md) por sua ID do dispositivo ou nome do computador.</span><span class="sxs-lookup"><span data-stu-id="95919-109">Retrieves specific [Machine](machine.md) by its device ID or computer name.</span></span>


## <a name="limitations"></a><span data-ttu-id="95919-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="95919-110">Limitations</span></span>
1. <span data-ttu-id="95919-111">Você pode obter dispositivos vistos pela última vez de acordo com sua política de retenção configurada.</span><span class="sxs-lookup"><span data-stu-id="95919-111">You can get devices last seen according to your configured retention policy.</span></span>
2. <span data-ttu-id="95919-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="95919-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="95919-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="95919-113">Permissions</span></span>
<span data-ttu-id="95919-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="95919-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="95919-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="95919-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="95919-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="95919-116">Permission type</span></span> |   <span data-ttu-id="95919-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="95919-117">Permission</span></span>  |   <span data-ttu-id="95919-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="95919-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="95919-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="95919-119">Application</span></span> |   <span data-ttu-id="95919-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="95919-120">Machine.Read.All</span></span> |  <span data-ttu-id="95919-121">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="95919-121">'Read all machine profiles'</span></span>
<span data-ttu-id="95919-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="95919-122">Application</span></span> |   <span data-ttu-id="95919-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="95919-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="95919-124">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="95919-124">'Read and write all machine information'</span></span>
<span data-ttu-id="95919-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="95919-125">Delegated (work or school account)</span></span> | <span data-ttu-id="95919-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="95919-126">Machine.Read</span></span> | <span data-ttu-id="95919-127">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="95919-127">'Read machine information'</span></span>
<span data-ttu-id="95919-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="95919-128">Delegated (work or school account)</span></span> | <span data-ttu-id="95919-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="95919-129">Machine.ReadWrite</span></span> | <span data-ttu-id="95919-130">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="95919-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="95919-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="95919-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="95919-132">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="95919-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="95919-133">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e [gerenciar grupos de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="95919-133">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="95919-134">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="95919-134">HTTP request</span></span>
```http
GET /api/machines/{id}
```

## <a name="request-headers"></a><span data-ttu-id="95919-135">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="95919-135">Request headers</span></span>

<span data-ttu-id="95919-136">Nome</span><span class="sxs-lookup"><span data-stu-id="95919-136">Name</span></span> | <span data-ttu-id="95919-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="95919-137">Type</span></span> | <span data-ttu-id="95919-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="95919-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="95919-139">Autorização</span><span class="sxs-lookup"><span data-stu-id="95919-139">Authorization</span></span> | <span data-ttu-id="95919-140">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="95919-140">String</span></span> | <span data-ttu-id="95919-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="95919-141">Bearer {token}.</span></span> <span data-ttu-id="95919-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="95919-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="95919-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="95919-143">Request body</span></span>
<span data-ttu-id="95919-144">Vazio</span><span class="sxs-lookup"><span data-stu-id="95919-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="95919-145">Resposta</span><span class="sxs-lookup"><span data-stu-id="95919-145">Response</span></span>
<span data-ttu-id="95919-146">Se bem-sucedido e o dispositivo existir - 200 OK com a [entidade do](machine.md) computador no corpo.</span><span class="sxs-lookup"><span data-stu-id="95919-146">If successful and device exists - 200 OK with the [machine](machine.md) entity in the body.</span></span>
<span data-ttu-id="95919-147">Se o computador com a ID especificada não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="95919-147">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="95919-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="95919-148">Example</span></span>

<span data-ttu-id="95919-149">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="95919-149">**Request**</span></span>

<span data-ttu-id="95919-150">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="95919-150">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07
```

<span data-ttu-id="95919-151">**Response**</span><span class="sxs-lookup"><span data-stu-id="95919-151">**Response**</span></span>

<span data-ttu-id="95919-152">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="95919-152">Here is an example of the response.</span></span>


```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machine",
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2018-08-02T14:55:03.7791856Z",
    "osPlatform": "Windows10",
    "version": "1709",
    "osProcessor": "x64",
    "lastIpAddress": "172.17.230.209",
    "lastExternalIpAddress": "167.220.196.71",
    "osBuild": 18209,
    "healthStatus": "Active",
    "rbacGroupId": 140,
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Medium",
    "isAadJoined": true,
    "aadDeviceId": "80fe8ff8-2624-418e-9591-41f0491218f9",
    "machineTags": [ "test tag 1", "test tag 2" ]
}

```
