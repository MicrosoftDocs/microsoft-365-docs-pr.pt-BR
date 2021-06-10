---
title: Api machineActions de lista
description: Saiba como usar a API List MachineActions para recuperar uma coleção de Ações de Máquina no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, coleção machineaction
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
ms.openlocfilehash: 2ee9a4e29dded3e299ffbb2c2997fd02f32d1abf
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771100"
---
# <a name="list-machineactions-api"></a><span data-ttu-id="0dda4-104">Listar API MachineActions</span><span class="sxs-lookup"><span data-stu-id="0dda4-104">List MachineActions API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0dda4-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0dda4-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0dda4-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0dda4-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0dda4-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0dda4-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="0dda4-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="0dda4-108">API description</span></span>
<span data-ttu-id="0dda4-109">Recupera uma coleção de [Ações do Computador.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="0dda4-109">Retrieves a collection of [Machine Actions](machineaction.md).</span></span>
<br><span data-ttu-id="0dda4-110">Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="0dda4-110">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
<br><span data-ttu-id="0dda4-111">A consulta OData tem suporte ```$filter``` em: ```status``` , , ```machineId``` e ```type``` ```requestor``` ```creationDateTimeUtc``` propriedades.</span><span class="sxs-lookup"><span data-stu-id="0dda4-111">The OData's ```$filter``` query is supported on: ```status```, ```machineId```, ```type```, ```requestor``` and ```creationDateTimeUtc``` properties.</span></span>
<br><span data-ttu-id="0dda4-112">Consulte exemplos em [Consultas OData com o Microsoft Defender para Ponto de Extremidade](exposed-apis-odata-samples.md)</span><span class="sxs-lookup"><span data-stu-id="0dda4-112">See examples at [OData queries with Microsoft Defender for Endpoint](exposed-apis-odata-samples.md)</span></span>


## <a name="limitations"></a><span data-ttu-id="0dda4-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="0dda4-113">Limitations</span></span>
1. <span data-ttu-id="0dda4-114">O tamanho máximo da página é 10.000.</span><span class="sxs-lookup"><span data-stu-id="0dda4-114">Maximum page size is 10,000.</span></span>
2. <span data-ttu-id="0dda4-115">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="0dda4-115">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span> 


## <a name="permissions"></a><span data-ttu-id="0dda4-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="0dda4-116">Permissions</span></span>
<span data-ttu-id="0dda4-117">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="0dda4-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0dda4-118">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="0dda4-118">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="0dda4-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="0dda4-119">Permission type</span></span> |   <span data-ttu-id="0dda4-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="0dda4-120">Permission</span></span>  |   <span data-ttu-id="0dda4-121">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="0dda4-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0dda4-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="0dda4-122">Application</span></span> |   <span data-ttu-id="0dda4-123">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="0dda4-123">Machine.Read.All</span></span> |  <span data-ttu-id="0dda4-124">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="0dda4-124">'Read all machine profiles'</span></span>
<span data-ttu-id="0dda4-125">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="0dda4-125">Application</span></span> |   <span data-ttu-id="0dda4-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="0dda4-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="0dda4-127">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="0dda4-127">'Read and write all machine information'</span></span>
<span data-ttu-id="0dda4-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="0dda4-128">Delegated (work or school account)</span></span> | <span data-ttu-id="0dda4-129">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="0dda4-129">Machine.Read</span></span> | <span data-ttu-id="0dda4-130">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="0dda4-130">'Read machine information'</span></span>
<span data-ttu-id="0dda4-131">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="0dda4-131">Delegated (work or school account)</span></span> | <span data-ttu-id="0dda4-132">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="0dda4-132">Machine.ReadWrite</span></span> | <span data-ttu-id="0dda4-133">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="0dda4-133">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="0dda4-134">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="0dda4-134">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="0dda4-135">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="0dda4-135">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="0dda4-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="0dda4-136">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

## <a name="request-headers"></a><span data-ttu-id="0dda4-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="0dda4-137">Request headers</span></span>

<span data-ttu-id="0dda4-138">Nome</span><span class="sxs-lookup"><span data-stu-id="0dda4-138">Name</span></span> | <span data-ttu-id="0dda4-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="0dda4-139">Type</span></span> | <span data-ttu-id="0dda4-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="0dda4-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="0dda4-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="0dda4-141">Authorization</span></span> | <span data-ttu-id="0dda4-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0dda4-142">String</span></span> | <span data-ttu-id="0dda4-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="0dda4-143">Bearer {token}.</span></span> <span data-ttu-id="0dda4-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="0dda4-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0dda4-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="0dda4-145">Request body</span></span>
<span data-ttu-id="0dda4-146">Vazio</span><span class="sxs-lookup"><span data-stu-id="0dda4-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0dda4-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="0dda4-147">Response</span></span>
<span data-ttu-id="0dda4-148">Se tiver êxito, este método retornará 200, código de resposta Ok com uma coleção de [entidades machineAction.](machineaction.md)</span><span class="sxs-lookup"><span data-stu-id="0dda4-148">If successful, this method returns 200, Ok response code with a collection of [machineAction](machineaction.md) entities.</span></span>


## <a name="example-1"></a><span data-ttu-id="0dda4-149">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0dda4-149">Example 1</span></span>

<span data-ttu-id="0dda4-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="0dda4-150">**Request**</span></span>

<span data-ttu-id="0dda4-151">Aqui está um exemplo da solicitação em uma organização que tem três MachineActions.</span><span class="sxs-lookup"><span data-stu-id="0dda4-151">Here is an example of the request on an organization that has three MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions
```

<span data-ttu-id="0dda4-152">**Response**</span><span class="sxs-lookup"><span data-stu-id="0dda4-152">**Response**</span></span>

<span data-ttu-id="0dda4-153">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="0dda4-153">Here is an example of the response.</span></span>


```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        },
        {
            "id": "44cffc15-0e3d-4cbf-96aa-bf76f9b27f5e",
            "type": "StopAndQuarantineFile",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:15:40.6052029Z",
            "lastUpdateTimeUtc": "2018-12-04T12:16:14.2899973Z",
            "relatedFileInfo": {
                "fileIdentifier": "a0c659857ccbe457fdaf5fe21d54efdcbf6f6508",
                "fileIdentifierType": "Sha1"
            }
        }
    ]
}
```

## <a name="example-2"></a><span data-ttu-id="0dda4-154">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0dda4-154">Example 2</span></span>

<span data-ttu-id="0dda4-155">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="0dda4-155">**Request**</span></span>

<span data-ttu-id="0dda4-156">Aqui está um exemplo de uma solicitação que filtra o MachineActions por ID do computador e mostra os dois MachineActions mais recentes.</span><span class="sxs-lookup"><span data-stu-id="0dda4-156">Here is an example of a request that filters the MachineActions by machine ID and shows the latest two MachineActions.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machineactions?$filter=machineId eq 'f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f'&$top=2
```

<span data-ttu-id="0dda4-157">**Response**</span><span class="sxs-lookup"><span data-stu-id="0dda4-157">**Response**</span></span>

<span data-ttu-id="0dda4-158">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="0dda4-158">Here is an example of the response.</span></span>

```
HTTP/1.1 200 Ok
Content-type: application/json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions",
    "value": [
        {
            "id": "69dc3630-1ccc-4342-acf3-35286eec741d",
            "type": "CollectInvestigationPackage",
            "scope": null,
            "requestor": "Analyst@contoso.com",
            "requestorComment": "test",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:43:57.2011911Z",
            "lastUpdateTimeUtc": "2018-12-04T12:45:25.4049122Z",
            "relatedFileInfo": null
        },
        {
            "id": "2e9da30d-27f6-4208-81f2-9cd3d67893ba",
            "type": "RunAntiVirusScan",
            "scope": "Full",
            "requestor": "Analyst@contoso.com",
            "requestorComment": "Check machine for viruses due to alert 3212",
            "status": "Succeeded",
            "machineId": "f46b9bb259ed4a7fb9981b73510e3cc7aa81ec1f",
            "computerDnsName": "desktop-39g9tgl",
            "creationDateTimeUtc": "2018-12-04T12:18:27.1293487Z",
            "lastUpdateTimeUtc": "2018-12-04T12:18:57.5511934Z",
            "relatedFileInfo": null
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="0dda4-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0dda4-159">Related topics</span></span>
- [<span data-ttu-id="0dda4-160">Consultas OData com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0dda4-160">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
