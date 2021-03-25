---
title: Obter todas as vulnerabilidades por computador e software
description: Recupera uma lista de todas as vulnerabilidades que afetam a organização por Computador e Software
keywords: apis, api gráfica, apis com suporte, obter, informações de vulnerabilidade, api mdatp tvm
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f7d67948e3b3e7a1a878386a397d2f4a6e8e998e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166268"
---
# <a name="list-vulnerabilities-by-machine-and-software"></a><span data-ttu-id="9add9-104">Listar vulnerabilidades por computador e software</span><span class="sxs-lookup"><span data-stu-id="9add9-104">List vulnerabilities by machine and software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9add9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9add9-105">**Applies to:**</span></span>
- [<span data-ttu-id="9add9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9add9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9add9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9add9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9add9-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9add9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9add9-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9add9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="9add9-110">Recupera uma lista de todas as vulnerabilidades que afetam a organização por [máquina](machine.md) e [software.](software.md)</span><span class="sxs-lookup"><span data-stu-id="9add9-110">Retrieves a list of all the vulnerabilities affecting the organization per [machine](machine.md) and [software](software.md).</span></span>
- <span data-ttu-id="9add9-111">Se a vulnerabilidade tiver um KB de correção, ela aparecerá na resposta.</span><span class="sxs-lookup"><span data-stu-id="9add9-111">If the vulnerability has a fixing KB, it will appear in the response.</span></span>
- <span data-ttu-id="9add9-112">Oferece suporte [a consultas OData V4.](https://www.odata.org/documentation/)</span><span class="sxs-lookup"><span data-stu-id="9add9-112">Supports [OData V4 queries](https://www.odata.org/documentation/).</span></span>
- <span data-ttu-id="9add9-113">O OData ```$filter``` é suportado em todas as propriedades.</span><span class="sxs-lookup"><span data-stu-id="9add9-113">The OData ```$filter``` is supported on all properties.</span></span>

>[!Tip]
><span data-ttu-id="9add9-114">Esta é uma ótima API para [integração do Power BI.](api-power-bi.md)</span><span class="sxs-lookup"><span data-stu-id="9add9-114">This is great API for [Power BI integration](api-power-bi.md).</span></span>

## <a name="permissions"></a><span data-ttu-id="9add9-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="9add9-115">Permissions</span></span>
<span data-ttu-id="9add9-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9add9-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9add9-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9add9-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="9add9-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9add9-118">Permission type</span></span> |   <span data-ttu-id="9add9-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="9add9-119">Permission</span></span>  |   <span data-ttu-id="9add9-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9add9-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9add9-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9add9-121">Application</span></span> |   <span data-ttu-id="9add9-122">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="9add9-122">Vulnerability.Read.All</span></span> |    <span data-ttu-id="9add9-123">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="9add9-123">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="9add9-124">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9add9-124">Delegated (work or school account)</span></span> | <span data-ttu-id="9add9-125">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="9add9-125">Vulnerability.Read</span></span> |   <span data-ttu-id="9add9-126">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="9add9-126">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="9add9-127">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9add9-127">HTTP request</span></span>
```
GET /api/vulnerabilities/machinesVulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="9add9-128">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9add9-128">Request headers</span></span>

<span data-ttu-id="9add9-129">Nome</span><span class="sxs-lookup"><span data-stu-id="9add9-129">Name</span></span> | <span data-ttu-id="9add9-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="9add9-130">Type</span></span> | <span data-ttu-id="9add9-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="9add9-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="9add9-132">Autorização</span><span class="sxs-lookup"><span data-stu-id="9add9-132">Authorization</span></span> | <span data-ttu-id="9add9-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9add9-133">String</span></span> | <span data-ttu-id="9add9-134">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9add9-134">Bearer {token}.</span></span> <span data-ttu-id="9add9-135">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9add9-135">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9add9-136">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9add9-136">Request body</span></span>
<span data-ttu-id="9add9-137">Vazio</span><span class="sxs-lookup"><span data-stu-id="9add9-137">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9add9-138">Resposta</span><span class="sxs-lookup"><span data-stu-id="9add9-138">Response</span></span>
<span data-ttu-id="9add9-139">Se tiver êxito, este método retornará 200 OK com a lista de vulnerabilidades no corpo.</span><span class="sxs-lookup"><span data-stu-id="9add9-139">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="9add9-140">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9add9-140">Example</span></span>

<span data-ttu-id="9add9-141">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9add9-141">**Request**</span></span>

<span data-ttu-id="9add9-142">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9add9-142">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/vulnerabilities/machinesVulnerabilities
```

<span data-ttu-id="9add9-143">**Response**</span><span class="sxs-lookup"><span data-stu-id="9add9-143">**Response**</span></span>

<span data-ttu-id="9add9-144">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="9add9-144">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicAssetVulnerabilityDto)",
    "value": [
        {
            "id": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21-_-CVE-2020-6494-_-microsoft-_-edge_chromium-based-_-81.0.416.77-_-",
            "cveId": "CVE-2020-6494",
            "machineId": "5afa3afc92a7c63d4b70129e0a6f33f63a427e21",
            "fixingKbId": null,
            "productName": "edge_chromium-based",
            "productVendor": "microsoft",
            "productVersion": "81.0.416.77",
            "severity": "Low"
        },
        {
            "id": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283-_-CVE-2016-3348-_-microsoft-_-windows_server_2012_r2-_-6.3.9600.19728-_-3185911",
            "cveId": "CVE-2016-3348",
            "machineId": "7a704e17d1c2977c0e7b665fb18ae6e1fe7f3283",
            "fixingKbId": "3185911",
            "productName": "windows_server_2012_r2",
            "productVendor": "microsoft",
            "productVersion": "6.3.9600.19728",
            "severity": "Low"
        },
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="9add9-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="9add9-145">See also</span></span>

- [<span data-ttu-id="9add9-146">Gerenciamento de ameaças e vulnerabilidades baseadas em risco</span><span class="sxs-lookup"><span data-stu-id="9add9-146">Risk-based threat and vulnerability management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="9add9-147">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="9add9-147">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
