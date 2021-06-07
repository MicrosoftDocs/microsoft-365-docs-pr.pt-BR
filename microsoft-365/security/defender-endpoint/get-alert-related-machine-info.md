---
title: Obter informações relacionadas ao computador de alerta
description: Recupere todos os dispositivos relacionados a um alerta específico usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter informações de alerta, informações de alerta, dispositivo relacionado
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
ms.openlocfilehash: ef10d2bd7193fc7b4a1604658f496ef38ef33555
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772336"
---
# <a name="get-alert-related-machine-information-api"></a><span data-ttu-id="4eeec-104">Obter API de informações relacionadas ao computador de alerta</span><span class="sxs-lookup"><span data-stu-id="4eeec-104">Get alert related machine information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4eeec-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4eeec-105">**Applies to:**</span></span>
- [<span data-ttu-id="4eeec-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4eeec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4eeec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4eeec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="4eeec-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4eeec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4eeec-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4eeec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4eeec-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="4eeec-110">API description</span></span>
<span data-ttu-id="4eeec-111">Recupera Dispositivo [relacionado](machine.md) a um alerta específico.</span><span class="sxs-lookup"><span data-stu-id="4eeec-111">Retrieves [Device](machine.md) related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="4eeec-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="4eeec-112">Limitations</span></span>
1. <span data-ttu-id="4eeec-113">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="4eeec-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="4eeec-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4eeec-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4eeec-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="4eeec-115">Permissions</span></span>
<span data-ttu-id="4eeec-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="4eeec-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4eeec-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4eeec-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4eeec-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="4eeec-118">Permission type</span></span> |   <span data-ttu-id="4eeec-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="4eeec-119">Permission</span></span>  |   <span data-ttu-id="4eeec-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="4eeec-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4eeec-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4eeec-121">Application</span></span> |   <span data-ttu-id="4eeec-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="4eeec-122">Machine.Read.All</span></span> |  <span data-ttu-id="4eeec-123">'Ler todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="4eeec-123">'Read all machine information'</span></span>
<span data-ttu-id="4eeec-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4eeec-124">Application</span></span> |   <span data-ttu-id="4eeec-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4eeec-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="4eeec-126">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="4eeec-126">'Read and write all machine information'</span></span>
<span data-ttu-id="4eeec-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="4eeec-127">Delegated (work or school account)</span></span> | <span data-ttu-id="4eeec-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="4eeec-128">Machine.Read</span></span> | <span data-ttu-id="4eeec-129">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="4eeec-129">'Read machine information'</span></span>
<span data-ttu-id="4eeec-130">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="4eeec-130">Delegated (work or school account)</span></span> | <span data-ttu-id="4eeec-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4eeec-131">Machine.ReadWrite</span></span> | <span data-ttu-id="4eeec-132">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="4eeec-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="4eeec-133">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="4eeec-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4eeec-134">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="4eeec-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4eeec-135">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="4eeec-135">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4eeec-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="4eeec-136">HTTP request</span></span>

```http
GET /api/alerts/{id}/machine
```

## <a name="request-headers"></a><span data-ttu-id="4eeec-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="4eeec-137">Request headers</span></span>

<span data-ttu-id="4eeec-138">Nome</span><span class="sxs-lookup"><span data-stu-id="4eeec-138">Name</span></span> | <span data-ttu-id="4eeec-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="4eeec-139">Type</span></span> | <span data-ttu-id="4eeec-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="4eeec-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="4eeec-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="4eeec-141">Authorization</span></span> | <span data-ttu-id="4eeec-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4eeec-142">String</span></span> | <span data-ttu-id="4eeec-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4eeec-143">Bearer {token}.</span></span> <span data-ttu-id="4eeec-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="4eeec-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4eeec-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="4eeec-145">Request body</span></span>
<span data-ttu-id="4eeec-146">Vazio</span><span class="sxs-lookup"><span data-stu-id="4eeec-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4eeec-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="4eeec-147">Response</span></span>
<span data-ttu-id="4eeec-148">Se bem-sucedido e alerta e dispositivo existem - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="4eeec-148">If successful and alert and device exist - 200 OK.</span></span> <span data-ttu-id="4eeec-149">Se o alerta não for encontrado ou o dispositivo não encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="4eeec-149">If alert not found or device not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="4eeec-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4eeec-150">Example</span></span>

<span data-ttu-id="4eeec-151">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="4eeec-151">**Request**</span></span>

<span data-ttu-id="4eeec-152">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="4eeec-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/alerts/636688558380765161_2136280442/machine
```

<span data-ttu-id="4eeec-153">**Response**</span><span class="sxs-lookup"><span data-stu-id="4eeec-153">**Response**</span></span>

<span data-ttu-id="4eeec-154">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="4eeec-154">Here is an example of the response.</span></span>


```json
{
    "id": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "computerDnsName": "mymachine1.contoso.com",
    "firstSeen": "2018-08-02T14:55:03.7791856Z",
    "lastSeen": "2021-01-25T07:27:36.052313Z",
    "osPlatform": "Windows10",
    "osProcessor": "x64",
    "version": "1901",
    "lastIpAddress": "10.166.113.46",
    "lastExternalIpAddress": "167.220.203.175",
    "osBuild": 19042,
    "healthStatus": "Active",
    "deviceValue": "Normal",
    "rbacGroupName": "The-A-Team",
    "riskScore": "Low",
    "exposureLevel": "Low",
    "aadDeviceId": "fd2e4d29-7072-4195-aaa5-1af139b78028",
    "machineTags": [
        "Tag1",
        "Tag2"
    ],
    "ipAddresses": [
        {
            "ipAddress": "10.166.113.47",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        },
        {
            "ipAddress": "2a01:110:68:4:59e4:3916:3b3e:4f96",
            "macAddress": "8CEC4B897E73",
            "operationalStatus": "Up"
        }
    ]
}
```
