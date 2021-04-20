---
title: API de máquinas de lista
description: Saiba como usar a API de máquinas de lista para recuperar uma coleção de máquinas que se comunicaram com o Microsoft Defender para a nuvem do Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos
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
ms.openlocfilehash: 01e36427116ad7bd845901e7da7f5aa152bd44f9
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893348"
---
# <a name="list-machines-api"></a><span data-ttu-id="64d82-104">API de máquinas de lista</span><span class="sxs-lookup"><span data-stu-id="64d82-104">List machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64d82-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="64d82-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="64d82-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="64d82-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64d82-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="64d82-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="64d82-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="64d82-108">API description</span></span>
<span data-ttu-id="64d82-109">Recupera uma coleção de [máquinas](machine.md) que se comunicaram com o Microsoft Defender para nuvem do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="64d82-109">Retrieves a collection of [Machines](machine.md) that have communicated with  Microsoft Defender for Endpoint cloud.</span></span>
<br><span data-ttu-id="64d82-110">Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="64d82-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="64d82-111">A consulta OData é suportada `$filter` em: `computerDnsName` , , , e `lastSeen` `healthStatus` `osPlatform` `riskScore` `rbacGroupId` .</span><span class="sxs-lookup"><span data-stu-id="64d82-111">The OData's `$filter` query is supported on: `computerDnsName`, `lastSeen`, `healthStatus`, `osPlatform`, `riskScore` and `rbacGroupId`.</span></span>
<br><span data-ttu-id="64d82-112">Consulte exemplos em [Consultas OData com o Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="64d82-112">See examples at [OData queries with Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="64d82-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="64d82-113">Limitations</span></span>
1. <span data-ttu-id="64d82-114">Você pode obter dispositivos vistos pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="64d82-114">You can get devices last seen according to your configured retention period.</span></span>
2. <span data-ttu-id="64d82-115">O tamanho máximo da página é 10.000.</span><span class="sxs-lookup"><span data-stu-id="64d82-115">Maximum page size is 10,000.</span></span>
3. <span data-ttu-id="64d82-116">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="64d82-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="64d82-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="64d82-117">Permissions</span></span>

<span data-ttu-id="64d82-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="64d82-118">Permission type</span></span> |   <span data-ttu-id="64d82-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="64d82-119">Permission</span></span>  |   <span data-ttu-id="64d82-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="64d82-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="64d82-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="64d82-121">Application</span></span> |   <span data-ttu-id="64d82-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="64d82-122">Machine.Read.All</span></span> |  <span data-ttu-id="64d82-123">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="64d82-123">'Read all machine profiles'</span></span>
<span data-ttu-id="64d82-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="64d82-124">Application</span></span> |   <span data-ttu-id="64d82-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="64d82-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="64d82-126">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="64d82-126">'Read and write all machine information'</span></span>
<span data-ttu-id="64d82-127">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="64d82-127">Delegated (work or school account)</span></span> | <span data-ttu-id="64d82-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="64d82-128">Machine.Read</span></span> | <span data-ttu-id="64d82-129">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="64d82-129">'Read machine information'</span></span>
<span data-ttu-id="64d82-130">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="64d82-130">Delegated (work or school account)</span></span> | <span data-ttu-id="64d82-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="64d82-131">Machine.ReadWrite</span></span> | <span data-ttu-id="64d82-132">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="64d82-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="64d82-133">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="64d82-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="64d82-134">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="64d82-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="64d82-135">A resposta incluirá apenas dispositivos aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="64d82-135">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="64d82-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="64d82-136">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

## <a name="request-headers"></a><span data-ttu-id="64d82-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="64d82-137">Request headers</span></span>

<span data-ttu-id="64d82-138">Nome</span><span class="sxs-lookup"><span data-stu-id="64d82-138">Name</span></span> | <span data-ttu-id="64d82-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="64d82-139">Type</span></span> | <span data-ttu-id="64d82-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="64d82-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="64d82-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="64d82-141">Authorization</span></span> | <span data-ttu-id="64d82-142">String</span><span class="sxs-lookup"><span data-stu-id="64d82-142">String</span></span> | <span data-ttu-id="64d82-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="64d82-143">Bearer {token}.</span></span> <span data-ttu-id="64d82-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="64d82-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="64d82-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="64d82-145">Request body</span></span>
<span data-ttu-id="64d82-146">Vazio</span><span class="sxs-lookup"><span data-stu-id="64d82-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="64d82-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="64d82-147">Response</span></span>
<span data-ttu-id="64d82-148">Se houver êxito e houver máquinas - 200 OK com a lista de [entidades](machine.md) do computador no corpo.</span><span class="sxs-lookup"><span data-stu-id="64d82-148">If successful and machines exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="64d82-149">Se nenhum aparelho recente - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="64d82-149">If no recent machines - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="64d82-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="64d82-150">Example</span></span>

<span data-ttu-id="64d82-151">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="64d82-151">**Request**</span></span>

<span data-ttu-id="64d82-152">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="64d82-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines
```

<span data-ttu-id="64d82-153">**Response**</span><span class="sxs-lookup"><span data-stu-id="64d82-153">**Response**</span></span>

<span data-ttu-id="64d82-154">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="64d82-154">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Machines",
    "value": [
        {
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
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="64d82-155">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="64d82-155">Related topics</span></span>
- [<span data-ttu-id="64d82-156">Consultas OData com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="64d82-156">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
