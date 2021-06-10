---
title: Encontrar informações do dispositivo por API IP interna
description: Use essa API para criar chamadas relacionadas a localizar uma entrada de dispositivo em torno de um data/hora específico por IP interno.
keywords: ip, apis, api gráfica, apis com suporte, encontrar dispositivo, informações de dispositivo
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166352"
---
# <a name="find-device-information-by-internal-ip-api"></a><span data-ttu-id="50188-104">Encontrar informações do dispositivo por API IP interna</span><span class="sxs-lookup"><span data-stu-id="50188-104">Find device information by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="50188-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="50188-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="50188-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="50188-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="50188-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="50188-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="50188-108">Encontre um dispositivo por IP interno.</span><span class="sxs-lookup"><span data-stu-id="50188-108">Find a device by internal IP.</span></span>

>[!NOTE]
><span data-ttu-id="50188-109">O data/hora deve estar dentro dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="50188-109">The timestamp must be within the last 30 days.</span></span>

## <a name="permissions"></a><span data-ttu-id="50188-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="50188-110">Permissions</span></span>
<span data-ttu-id="50188-111">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="50188-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="50188-112">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="50188-112">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="50188-113">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="50188-113">Permission type</span></span> | <span data-ttu-id="50188-114">Permissão</span><span class="sxs-lookup"><span data-stu-id="50188-114">Permission</span></span> | <span data-ttu-id="50188-115">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="50188-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="50188-116">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="50188-116">Application</span></span> | <span data-ttu-id="50188-117">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="50188-117">Machine.Read.All</span></span> | <span data-ttu-id="50188-118">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="50188-118">'Read all machine profiles'</span></span>
<span data-ttu-id="50188-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="50188-119">Application</span></span> | <span data-ttu-id="50188-120">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="50188-120">Machine.ReadWrite.All</span></span> | <span data-ttu-id="50188-121">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="50188-121">'Read and write all machine information'</span></span>

## <a name="http-request"></a><span data-ttu-id="50188-122">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="50188-122">HTTP request</span></span>
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a><span data-ttu-id="50188-123">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="50188-123">Request headers</span></span>

<span data-ttu-id="50188-124">Nome</span><span class="sxs-lookup"><span data-stu-id="50188-124">Name</span></span> | <span data-ttu-id="50188-125">Tipo</span><span class="sxs-lookup"><span data-stu-id="50188-125">Type</span></span> | <span data-ttu-id="50188-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="50188-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="50188-127">Autorização</span><span class="sxs-lookup"><span data-stu-id="50188-127">Authorization</span></span> | <span data-ttu-id="50188-128">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="50188-128">String</span></span> | <span data-ttu-id="50188-129">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="50188-129">Bearer {token}.</span></span> <span data-ttu-id="50188-130">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="50188-130">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="50188-131">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="50188-131">Request body</span></span>
<span data-ttu-id="50188-132">Vazio</span><span class="sxs-lookup"><span data-stu-id="50188-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="50188-133">Resposta</span><span class="sxs-lookup"><span data-stu-id="50188-133">Response</span></span>
<span data-ttu-id="50188-134">Se bem-sucedido e o computador existir - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="50188-134">If successful and machine exists - 200 OK.</span></span>
<span data-ttu-id="50188-135">Se nenhum computador for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="50188-135">If no machine found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="50188-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="50188-136">Example</span></span>

<span data-ttu-id="50188-137">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="50188-137">**Request**</span></span>

<span data-ttu-id="50188-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="50188-138">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

<span data-ttu-id="50188-139">**Response**</span><span class="sxs-lookup"><span data-stu-id="50188-139">**Response**</span></span>

<span data-ttu-id="50188-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="50188-140">Here is an example of the response.</span></span>

<span data-ttu-id="50188-141">A resposta retornará uma lista de todos os dispositivos que relataram esse endereço IP dentro de dezesseis minutos antes e após o data/hora.</span><span class="sxs-lookup"><span data-stu-id="50188-141">The response will return a list of all devices that reported this IP address within sixteen minutes prior and after the timestamp.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
