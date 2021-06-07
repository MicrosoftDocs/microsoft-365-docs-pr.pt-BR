---
title: Obter vulnerabilidades descobertas
description: Recupera uma coleção de vulnerabilidades descobertas relacionadas a uma determinada ID de dispositivo.
keywords: apis, api gráfica, apis com suporte, obter, listar, arquivo, informações, vulnerabilidades descobertas, api de & Gerenciamento de Vulnerabilidades de ameaças, api de tvm do Microsoft Defender para Endpoint
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: ac7a9ef932f2640bbc5325f0154c0ceb48ae3018
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772288"
---
# <a name="get-discovered-vulnerabilities"></a><span data-ttu-id="8df8b-104">Obter vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="8df8b-104">Get discovered vulnerabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8df8b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8df8b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8df8b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8df8b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8df8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8df8b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8df8b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8df8b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8df8b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8df8b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8df8b-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="8df8b-110">API description</span></span>
<span data-ttu-id="8df8b-111">Recupera uma coleção de vulnerabilidades descobertas relacionadas a uma determinada ID de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8df8b-111">Retrieves a collection of discovered vulnerabilities related to a given device ID.</span></span>

## <a name="limitations"></a><span data-ttu-id="8df8b-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="8df8b-112">Limitations</span></span>
1. <span data-ttu-id="8df8b-113">Limitações de taxa para essa API são 50 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8df8b-113">Rate limitations for this API are 50 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="8df8b-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="8df8b-114">Permissions</span></span>

<span data-ttu-id="8df8b-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8df8b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8df8b-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8df8b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8df8b-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8df8b-117">Permission type</span></span> | <span data-ttu-id="8df8b-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="8df8b-118">Permission</span></span> | <span data-ttu-id="8df8b-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8df8b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8df8b-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8df8b-120">Application</span></span> |<span data-ttu-id="8df8b-121">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8df8b-121">Vulnerability.Read.All</span></span> | <span data-ttu-id="8df8b-122">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8df8b-122">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8df8b-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8df8b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8df8b-124">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8df8b-124">Vulnerability.Read</span></span> | <span data-ttu-id="8df8b-125">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8df8b-125">'Read Threat and Vulnerability Management vulnerability information'</span></span>

## <a name="http-request"></a><span data-ttu-id="8df8b-126">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="8df8b-126">HTTP request</span></span>

```
GET /api/machines/{machineId}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="8df8b-127">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="8df8b-127">Request headers</span></span>

<span data-ttu-id="8df8b-128">Nome</span><span class="sxs-lookup"><span data-stu-id="8df8b-128">Name</span></span> | <span data-ttu-id="8df8b-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="8df8b-129">Type</span></span> | <span data-ttu-id="8df8b-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="8df8b-130">Description</span></span>
:---|:---|:---
<span data-ttu-id="8df8b-131">Autorização</span><span class="sxs-lookup"><span data-stu-id="8df8b-131">Authorization</span></span> | <span data-ttu-id="8df8b-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8df8b-132">String</span></span> | <span data-ttu-id="8df8b-133">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="8df8b-133">Bearer {token}.</span></span> <span data-ttu-id="8df8b-134">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="8df8b-134">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="8df8b-135">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="8df8b-135">Request body</span></span>

<span data-ttu-id="8df8b-136">Vazio</span><span class="sxs-lookup"><span data-stu-id="8df8b-136">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8df8b-137">Resposta</span><span class="sxs-lookup"><span data-stu-id="8df8b-137">Response</span></span>

<span data-ttu-id="8df8b-138">Se tiver êxito, este método retornará 200 OK com as informações de vulnerabilidade descobertas no corpo.</span><span class="sxs-lookup"><span data-stu-id="8df8b-138">If successful, this method returns 200 OK with the discovered vulnerability information in the body.</span></span>

## <a name="example"></a><span data-ttu-id="8df8b-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8df8b-139">Example</span></span>

### <a name="request"></a><span data-ttu-id="8df8b-140">Solicitação</span><span class="sxs-lookup"><span data-stu-id="8df8b-140">Request</span></span>

<span data-ttu-id="8df8b-141">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8df8b-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/vulnerabilities
```

### <a name="response"></a><span data-ttu-id="8df8b-142">Resposta</span><span class="sxs-lookup"><span data-stu-id="8df8b-142">Response</span></span>

<span data-ttu-id="8df8b-143">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="8df8b-143">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-1348",
            "name": "CVE-2019-1348",
            "description": "Git could allow a remote attacker to bypass security restrictions, caused by a flaw in the --export-marks option of git fast-import. By persuading a victim to import specially-crafted content, an attacker could exploit this vulnerability to overwrite arbitrary paths.",
            "severity": "Medium",
            "cvssV3": 4.3,
            "exposedMachines": 1,
            "publishedOn": "2019-12-13T00:00:00Z",
            "updatedOn": "2019-12-13T00:00:00Z",
            "publicExploit": false,
            "exploitVerified": false,
            "exploitInKit": false,
            "exploitTypes": [],
            "exploitUris": []
        }
}
```

## <a name="see-also"></a><span data-ttu-id="8df8b-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="8df8b-144">See also</span></span>

- [<span data-ttu-id="8df8b-145">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="8df8b-145">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="8df8b-146">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="8df8b-146">Vulnerabilities in your organization</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-weaknesses)
