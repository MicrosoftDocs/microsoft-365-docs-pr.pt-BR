---
title: Obter API de mapa CVE-KB
description: Saiba como usar a API de mapa Get CVE-KB para recuperar um mapa de CVE para os detalhes de KB e CVE no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, get, cve, kb
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
ms.openlocfilehash: 85c4d82f07354193fb1e997abb98dbdaa02dc8ef
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166266"
---
# <a name="get-cve-kb-map-api"></a><span data-ttu-id="1fb3c-104">Obter API de mapa CVE-KB</span><span class="sxs-lookup"><span data-stu-id="1fb3c-104">Get CVE-KB map API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fb3c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1fb3c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fb3c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1fb3c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1fb3c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1fb3c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1fb3c-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1fb3c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1fb3c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="1fb3c-110">Recupera um mapa de CVE para os detalhes de KB e CVE.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-110">Retrieves a map of CVE's to KB's and CVE details.</span></span>

## <a name="permissions"></a><span data-ttu-id="1fb3c-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="1fb3c-111">Permissions</span></span>
<span data-ttu-id="1fb3c-112">O usuário precisa de permissões de leitura.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-112">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="1fb3c-113">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="1fb3c-113">HTTP request</span></span>
```
GET /testwdatppreview/cvekbmap
```

## <a name="request-headers"></a><span data-ttu-id="1fb3c-114">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="1fb3c-114">Request headers</span></span>

<span data-ttu-id="1fb3c-115">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="1fb3c-115">Header</span></span> | <span data-ttu-id="1fb3c-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1fb3c-116">Value</span></span> 
:---|:---
<span data-ttu-id="1fb3c-117">Autorização</span><span class="sxs-lookup"><span data-stu-id="1fb3c-117">Authorization</span></span> | <span data-ttu-id="1fb3c-118">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-118">Bearer {token}.</span></span> <span data-ttu-id="1fb3c-119">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-119">**Required**.</span></span>
<span data-ttu-id="1fb3c-120">Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="1fb3c-120">Content type</span></span> | <span data-ttu-id="1fb3c-121">application/json</span><span class="sxs-lookup"><span data-stu-id="1fb3c-121">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="1fb3c-122">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="1fb3c-122">Request body</span></span>
<span data-ttu-id="1fb3c-123">Vazio</span><span class="sxs-lookup"><span data-stu-id="1fb3c-123">Empty</span></span>

## <a name="response"></a><span data-ttu-id="1fb3c-124">Resposta</span><span class="sxs-lookup"><span data-stu-id="1fb3c-124">Response</span></span>
<span data-ttu-id="1fb3c-125">Se bem-sucedido e o mapa existir - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-125">If successful and map exists - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="1fb3c-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1fb3c-126">Example</span></span>

<span data-ttu-id="1fb3c-127">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="1fb3c-127">**Request**</span></span>

<span data-ttu-id="1fb3c-128">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-128">Here is an example of the request.</span></span>

```http
GET https://graph.microsoft.com/testwdatppreview/CveKbMap
```

<span data-ttu-id="1fb3c-129">**Response**</span><span class="sxs-lookup"><span data-stu-id="1fb3c-129">**Response**</span></span>

<span data-ttu-id="1fb3c-130">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="1fb3c-130">Here is an example of the response.</span></span>

```json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#CveKbMap",
    "@odata.count": 4168,
    "value": [
        {
            "cveKbId": "CVE-2015-2482-3097617",
            "cveId": "CVE-2015-2482",
            "kbId":"3097617",
            "title": "Cumulative Security Update for Internet Explorer",
            "severity": "Critical"
        },
    …
}

```
