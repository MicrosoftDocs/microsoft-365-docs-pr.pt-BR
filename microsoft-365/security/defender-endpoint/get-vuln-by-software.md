---
title: Listar vulnerabilidades por software
description: Recupere uma lista de vulnerabilidades no software instalado.
keywords: apis, api gráfica, apis com suporte, obter, lista de vulnerabilidades, api de tvm do Microsoft Defender para Endpoint
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
ms.openlocfilehash: 18a2cf87cd0e6b898a9f2aa4d6ecd47a86a8c7f6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769912"
---
# <a name="list-vulnerabilities-by-software"></a><span data-ttu-id="ace13-104">Listar vulnerabilidades por software</span><span class="sxs-lookup"><span data-stu-id="ace13-104">List vulnerabilities by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ace13-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ace13-105">**Applies to:**</span></span>
- [<span data-ttu-id="ace13-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ace13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ace13-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ace13-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ace13-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ace13-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ace13-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ace13-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ace13-110">Recupere uma lista de vulnerabilidades no software instalado.</span><span class="sxs-lookup"><span data-stu-id="ace13-110">Retrieve a list of vulnerabilities in the installed software.</span></span> 

## <a name="permissions"></a><span data-ttu-id="ace13-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="ace13-111">Permissions</span></span>
<span data-ttu-id="ace13-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ace13-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ace13-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ace13-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ace13-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ace13-114">Permission type</span></span> |   <span data-ttu-id="ace13-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="ace13-115">Permission</span></span>  |   <span data-ttu-id="ace13-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ace13-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ace13-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ace13-117">Application</span></span> | <span data-ttu-id="ace13-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="ace13-118">Software.Read.All</span></span> | <span data-ttu-id="ace13-119">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ace13-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="ace13-120">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ace13-120">Delegated (work or school account)</span></span> | <span data-ttu-id="ace13-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="ace13-121">Software.Read</span></span> | <span data-ttu-id="ace13-122">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ace13-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ace13-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="ace13-123">HTTP request</span></span>
```
GET /api/Software/{Id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="ace13-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ace13-124">Request headers</span></span>

| <span data-ttu-id="ace13-125">Nome</span><span class="sxs-lookup"><span data-stu-id="ace13-125">Name</span></span>        | <span data-ttu-id="ace13-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="ace13-126">Type</span></span> | <span data-ttu-id="ace13-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="ace13-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="ace13-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="ace13-128">Authorization</span></span> | <span data-ttu-id="ace13-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ace13-129">String</span></span> | <span data-ttu-id="ace13-130">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ace13-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ace13-131">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="ace13-131">Request body</span></span>
<span data-ttu-id="ace13-132">Vazio</span><span class="sxs-lookup"><span data-stu-id="ace13-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ace13-133">Resposta</span><span class="sxs-lookup"><span data-stu-id="ace13-133">Response</span></span>
<span data-ttu-id="ace13-134">Se tiver êxito, este método retornará 200 OK com uma lista de vulnerabilidades expostas pelo software especificado.</span><span class="sxs-lookup"><span data-stu-id="ace13-134">If successful, this method returns 200 OK with a list of vulnerabilities exposed by the specified software.</span></span> 


## <a name="example"></a><span data-ttu-id="ace13-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ace13-135">Example</span></span>

<span data-ttu-id="ace13-136">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="ace13-136">**Request**</span></span>

<span data-ttu-id="ace13-137">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ace13-137">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/vulnerabilities 
```

<span data-ttu-id="ace13-138">**Response**</span><span class="sxs-lookup"><span data-stu-id="ace13-138">**Response**</span></span>

<span data-ttu-id="ace13-139">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="ace13-139">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
            {
                "id": "CVE-2017-0140",
                "name": "CVE-2017-0140",
                "description": "A security feature bypass vulnerability exists when Microsoft Edge improperly handles requests of different origins. The vulnerability allows Microsoft Edge to bypass Same-Origin Policy (SOP) restrictions, and to allow requests that should otherwise be ignored. An attacker who successfully exploited the vulnerability could force the browser to send data that would otherwise be restricted.In a web-based attack scenario, an attacker could host a specially crafted website that is designed to exploit the vulnerability through Microsoft Edge and then convince a user to view the website. The attacker could also take advantage of compromised websites, and websites that accept or host user-provided content or advertisements. These websites could contain specially crafted content that could exploit the vulnerability.The security update addresses the vulnerability by modifying how affected Microsoft Edge handles different-origin requests.",
                "severity": "Medium",
                "cvssV3": 4.2,
                "exposedMachines": 1,
                "publishedOn": "2017-03-14T00:00:00Z",
                "updatedOn": "2019-10-03T00:03:00Z",
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

