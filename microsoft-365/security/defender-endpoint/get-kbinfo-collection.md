---
title: Obter API de coleção KB
description: Recupere uma coleção de bases de conhecimento (KB's) e detalhes do KB com o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, get, kb
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ROBOTS: NOINDEX
ms.technology: mde
ms.openlocfilehash: 7becfc4a7246dc32aa244dc96ea423f5d31877f9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166358"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="77076-104">Obter API de coleção KB</span><span class="sxs-lookup"><span data-stu-id="77076-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77076-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="77076-105">**Applies to:**</span></span>
- [<span data-ttu-id="77076-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="77076-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77076-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77076-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="77076-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="77076-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77076-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="77076-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="77076-110">Recupera uma coleção de detalhes de KB e KB.</span><span class="sxs-lookup"><span data-stu-id="77076-110">Retrieves a collection of KB's and KB details.</span></span>

## <a name="permissions"></a><span data-ttu-id="77076-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="77076-111">Permissions</span></span>
<span data-ttu-id="77076-112">O usuário precisa de permissões de leitura.</span><span class="sxs-lookup"><span data-stu-id="77076-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="77076-113">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="77076-113">HTTP request</span></span>
```
GET /testwdatppreview/kbinfo
```

## <a name="request-headers"></a><span data-ttu-id="77076-114">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="77076-114">Request headers</span></span>

<span data-ttu-id="77076-115">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="77076-115">Header</span></span> | <span data-ttu-id="77076-116">Valor</span><span class="sxs-lookup"><span data-stu-id="77076-116">Value</span></span> 
:---|:---
<span data-ttu-id="77076-117">Autorização</span><span class="sxs-lookup"><span data-stu-id="77076-117">Authorization</span></span> | <span data-ttu-id="77076-118">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="77076-118">Bearer {token}.</span></span> <span data-ttu-id="77076-119">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="77076-119">**Required**.</span></span>
<span data-ttu-id="77076-120">Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="77076-120">Content type</span></span> | <span data-ttu-id="77076-121">application/json</span><span class="sxs-lookup"><span data-stu-id="77076-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="77076-122">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="77076-122">Request body</span></span>
<span data-ttu-id="77076-123">Vazio</span><span class="sxs-lookup"><span data-stu-id="77076-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="77076-124">Resposta</span><span class="sxs-lookup"><span data-stu-id="77076-124">Response</span></span>
<span data-ttu-id="77076-125">Se bem-sucedido - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="77076-125">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="77076-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="77076-126">Example</span></span>

<span data-ttu-id="77076-127">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="77076-127">**Request**</span></span>

<span data-ttu-id="77076-128">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="77076-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/KbInfo
```

<span data-ttu-id="77076-129">**Response**</span><span class="sxs-lookup"><span data-stu-id="77076-129">**Response**</span></span>

<span data-ttu-id="77076-130">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="77076-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#KbInfo",
    "@odata.count": 271,
    "value":[
        {
            "id": "KB3097617 (10240.16549) Amd64",
            "release": "KB3097617 (10240.16549)",
            "publishingDate": "2015-10-16T21:00:00Z",
            "version": "10.0.10240.16549",
            "architecture": "Amd64"
        },
        …
}
```
