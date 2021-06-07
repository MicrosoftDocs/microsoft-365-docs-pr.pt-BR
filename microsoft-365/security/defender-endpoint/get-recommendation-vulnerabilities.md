---
title: Listar vulnerabilidades por recomendação
description: Recupera uma lista de vulnerabilidades associadas à recomendação de segurança.
keywords: apis, api gráfica, apis com suporte, obter, lista de vulnerabilidades, recomendação de segurança, recomendação de segurança para vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 8fc9bb53fd2cfe768710129704c13ee751a695a2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770436"
---
# <a name="list-vulnerabilities-by-recommendation"></a><span data-ttu-id="09172-104">Listar vulnerabilidades por recomendação</span><span class="sxs-lookup"><span data-stu-id="09172-104">List vulnerabilities by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09172-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="09172-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="09172-106">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="09172-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="09172-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="09172-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="09172-108">Recupera uma lista de vulnerabilidades associadas à recomendação de segurança.</span><span class="sxs-lookup"><span data-stu-id="09172-108">Retrieves a list of vulnerabilities associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="09172-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="09172-109">Permissions</span></span>
<span data-ttu-id="09172-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="09172-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="09172-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="09172-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="09172-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="09172-112">Permission type</span></span> |   <span data-ttu-id="09172-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="09172-113">Permission</span></span>  |   <span data-ttu-id="09172-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="09172-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="09172-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="09172-115">Application</span></span> |   <span data-ttu-id="09172-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="09172-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="09172-117">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="09172-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="09172-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="09172-118">Delegated (work or school account)</span></span> | <span data-ttu-id="09172-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="09172-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="09172-120">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="09172-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="09172-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="09172-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/vulnerabilities
```

## <a name="request-headers"></a><span data-ttu-id="09172-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="09172-122">Request headers</span></span>

<span data-ttu-id="09172-123">Nome</span><span class="sxs-lookup"><span data-stu-id="09172-123">Name</span></span> | <span data-ttu-id="09172-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="09172-124">Type</span></span> | <span data-ttu-id="09172-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="09172-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="09172-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="09172-126">Authorization</span></span> | <span data-ttu-id="09172-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="09172-127">String</span></span> | <span data-ttu-id="09172-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="09172-128">Bearer {token}.</span></span> <span data-ttu-id="09172-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="09172-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="09172-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="09172-130">Request body</span></span>
<span data-ttu-id="09172-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="09172-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="09172-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="09172-132">Response</span></span>
<span data-ttu-id="09172-133">Se tiver êxito, este método retornará 200 OK, com a lista de vulnerabilidades associadas à recomendação de segurança.</span><span class="sxs-lookup"><span data-stu-id="09172-133">If successful, this method returns 200 OK, with the list of vulnerabilities associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="09172-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="09172-134">Example</span></span>

<span data-ttu-id="09172-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="09172-135">**Request**</span></span>

<span data-ttu-id="09172-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="09172-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/vulnerabilities
```

<span data-ttu-id="09172-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="09172-137">**Response**</span></span>

<span data-ttu-id="09172-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="09172-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(Analytics.Contracts.PublicAPI.PublicVulnerabilityDto)",
    "value": [
        {
            "id": "CVE-2019-13748",
            "name": "CVE-2019-13748",
            "description": "Insufficient policy enforcement in developer tools in Google Chrome prior to 79.0.3945.79 allowed a local attacker to obtain potentially sensitive information from process memory via a crafted HTML page.",
            "severity": "Medium",
            "cvssV3": 6.5,
            "exposedMachines": 0,
            "publishedOn": "2019-12-10T00:00:00Z",
            "updatedOn": "2019-12-16T12:15:00Z",
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

## <a name="related-topics"></a><span data-ttu-id="09172-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="09172-139">Related topics</span></span>
- [<span data-ttu-id="09172-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="09172-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="09172-141">Recomendação & segurança de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="09172-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
