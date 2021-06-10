---
title: Obter todas as vulnerabilidades
description: Recupera uma lista de todas as vulnerabilidades que afetam a organização
keywords: apis, api gráfica, apis com suporte, obter, informações de vulnerabilidade, api de tvm do Microsoft Defender para Endpoint
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6def1b64430ad70dc4b4898ba2b914288826873e
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861486"
---
# <a name="list-vulnerabilities"></a><span data-ttu-id="cd725-104">Listar vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cd725-104">List vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd725-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cd725-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd725-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cd725-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cd725-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd725-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cd725-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cd725-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cd725-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cd725-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="cd725-110">Recupera uma lista de todas as vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="cd725-110">Retrieves a list of all the vulnerabilities.</span></span>

## <a name="permissions"></a><span data-ttu-id="cd725-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="cd725-111">Permissions</span></span>
<span data-ttu-id="cd725-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="cd725-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cd725-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="cd725-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="cd725-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="cd725-114">Permission type</span></span> |   <span data-ttu-id="cd725-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="cd725-115">Permission</span></span>  |   <span data-ttu-id="cd725-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="cd725-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cd725-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="cd725-117">Application</span></span> |   <span data-ttu-id="cd725-118">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="cd725-118">Vulnerability.Read.All</span></span> |    <span data-ttu-id="cd725-119">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="cd725-119">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="cd725-120">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="cd725-120">Delegated (work or school account)</span></span> | <span data-ttu-id="cd725-121">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="cd725-121">Vulnerability.Read</span></span> |   <span data-ttu-id="cd725-122">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="cd725-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="cd725-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="cd725-123">HTTP request</span></span>
```
GET /api/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="cd725-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="cd725-124">Request headers</span></span>

<span data-ttu-id="cd725-125">Nome</span><span class="sxs-lookup"><span data-stu-id="cd725-125">Name</span></span> | <span data-ttu-id="cd725-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="cd725-126">Type</span></span> | <span data-ttu-id="cd725-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd725-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="cd725-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="cd725-128">Authorization</span></span> | <span data-ttu-id="cd725-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cd725-129">String</span></span> | <span data-ttu-id="cd725-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="cd725-130">Bearer {token}.</span></span> <span data-ttu-id="cd725-131">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="cd725-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cd725-132">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="cd725-132">Request body</span></span>
<span data-ttu-id="cd725-133">Vazio</span><span class="sxs-lookup"><span data-stu-id="cd725-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="cd725-134">Resposta</span><span class="sxs-lookup"><span data-stu-id="cd725-134">Response</span></span>
<span data-ttu-id="cd725-135">Se tiver êxito, este método retornará 200 OK com a lista de vulnerabilidades no corpo.</span><span class="sxs-lookup"><span data-stu-id="cd725-135">If successful, this method returns 200 OK with the list of vulnerabilities in the body.</span></span>


## <a name="example"></a><span data-ttu-id="cd725-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cd725-136">Example</span></span>

<span data-ttu-id="cd725-137">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="cd725-137">**Request**</span></span>

<span data-ttu-id="cd725-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="cd725-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Vulnerabilities
```

<span data-ttu-id="cd725-139">**Response**</span><span class="sxs-lookup"><span data-stu-id="cd725-139">**Response**</span></span>

<span data-ttu-id="cd725-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="cd725-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Vulnerabilities",
    "value": [
        {
            "id": "CVE-2019-0608",
            "name": "CVE-2019-0608",
            "description": "A spoofing vulnerability exists when Microsoft Browsers does not properly parse HTTP content. An attacker who successfully exploited this vulnerability could impersonate a user request by crafting HTTP queries. The specially crafted website could either spoof content or serve as a pivot to chain an attack with other vulnerabilities in web services.To exploit the vulnerability, the user must click a specially crafted URL. In an email attack scenario, an attacker could send an email message containing the specially crafted URL to the user in an attempt to convince the user to click it.In a web-based attack scenario, an attacker could host a specially crafted website designed to appear as a legitimate website to the user. However, the attacker would have no way to force the user to visit the specially crafted website. The attacker would have to convince the user to visit the specially crafted website, typically by way of enticement in an email or instant message, and then convince the user to interact with content on the website.The update addresses the vulnerability by correcting how Microsoft Browsers parses HTTP responses.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 4,
            "publishedOn": "2019-10-08T00:00:00Z",
            "updatedOn": "2019-12-16T16:20:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
        ...
    ]

}
```

## <a name="see-also"></a><span data-ttu-id="cd725-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd725-141">See also</span></span>
- [<span data-ttu-id="cd725-142">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="cd725-142">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="cd725-143">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="cd725-143">Vulnerabilities in your organization</span></span>](/microsoft-365/security/defender-endpoint/tvm-weaknesses)
