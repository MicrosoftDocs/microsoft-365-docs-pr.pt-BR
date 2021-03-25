---
title: Obter API de conjunto de estados de segurança de máquinas
description: Recupere uma coleção de estados de segurança de dispositivo usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivo, segurança, estado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9dab4bdccc1fead5bc2cc5b9bdff8f2a45b6c8db
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200360"
---
# <a name="get-machines-security-states-collection-api"></a><span data-ttu-id="f626e-104">Get Machines security states collection API</span><span class="sxs-lookup"><span data-stu-id="f626e-104">Get Machines security states collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f626e-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f626e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f626e-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f626e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f626e-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f626e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f626e-108">Recupera uma coleção de estados de segurança de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f626e-108">Retrieves a collection of devices security states.</span></span>

## <a name="permissions"></a><span data-ttu-id="f626e-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="f626e-109">Permissions</span></span>
<span data-ttu-id="f626e-110">O usuário precisa de permissões de leitura.</span><span class="sxs-lookup"><span data-stu-id="f626e-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="f626e-111">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="f626e-111">HTTP request</span></span>
```
GET /testwdatppreview/machinesecuritystates
```

## <a name="request-headers"></a><span data-ttu-id="f626e-112">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="f626e-112">Request headers</span></span>

<span data-ttu-id="f626e-113">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="f626e-113">Header</span></span> | <span data-ttu-id="f626e-114">Valor</span><span class="sxs-lookup"><span data-stu-id="f626e-114">Value</span></span> 
:---|:---
<span data-ttu-id="f626e-115">Autorização</span><span class="sxs-lookup"><span data-stu-id="f626e-115">Authorization</span></span> | <span data-ttu-id="f626e-116">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f626e-116">Bearer {token}.</span></span> <span data-ttu-id="f626e-117">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="f626e-117">**Required**.</span></span>
<span data-ttu-id="f626e-118">Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f626e-118">Content type</span></span> | <span data-ttu-id="f626e-119">application/json</span><span class="sxs-lookup"><span data-stu-id="f626e-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="f626e-120">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="f626e-120">Request body</span></span>
<span data-ttu-id="f626e-121">Vazio</span><span class="sxs-lookup"><span data-stu-id="f626e-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="f626e-122">Resposta</span><span class="sxs-lookup"><span data-stu-id="f626e-122">Response</span></span>
<span data-ttu-id="f626e-123">Se bem-sucedido - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="f626e-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="f626e-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f626e-124">Example</span></span>

<span data-ttu-id="f626e-125">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="f626e-125">**Request**</span></span>

<span data-ttu-id="f626e-126">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f626e-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinesecuritystates
Content-type: application/json
```

<span data-ttu-id="f626e-127">**Response**</span><span class="sxs-lookup"><span data-stu-id="f626e-127">**Response**</span></span>

<span data-ttu-id="f626e-128">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="f626e-128">Here is an example of the response.</span></span>
<span data-ttu-id="f626e-129">A *id de campo* contém id do dispositivo e igual à *id* do campo \* em informações de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f626e-129">Field *id* contains device id and equal to the field *id*\* in devices info.</span></span> 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineSecurityStates",
    "@odata.count":444,
    "@odata.nextLink":"https://graph.microsoft.com/testwdatppreview/machinesecuritystates?$skiptoken=[continuation token]",
    "value":[
        {
            "id":"000050e1b4afeee3742489ede9ad7a3e16bbd9c4",
            "build":14393,
            "revision":2485,
            "architecture":"Amd64",
            "osVersion":"10.0.14393.2485.amd64fre.rs1_release.180827-1809",
            "propertiesRequireAttention":[
                "AntivirusNotReporting",
                "EdrImpairedCommunications"
            ]
        },
        …
    ]
}
```
