---
title: Obter recomendação por ID
description: Recupera uma recomendação de segurança por sua ID.
keywords: apis, api gráfica, apis com suporte, get, recomendação de segurança, recomendação de segurança por ID, gerenciamento de ameaças e vulnerabilidades, api de gerenciamento de ameaças e vulnerabilidades
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
ms.openlocfilehash: 45a151fc5855a4a2b1ba63a50b54737c90e6bdd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199508"
---
# <a name="get-recommendation-by-id"></a><span data-ttu-id="5c7f9-104">Obter recomendação por ID</span><span class="sxs-lookup"><span data-stu-id="5c7f9-104">Get recommendation by ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c7f9-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5c7f9-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5c7f9-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5c7f9-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c7f9-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="5c7f9-108">Recupera uma recomendação de segurança por sua ID.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-108">Retrieves a security recommendation by its ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="5c7f9-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="5c7f9-109">Permissions</span></span>
<span data-ttu-id="5c7f9-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c7f9-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="5c7f9-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="5c7f9-112">Permission type</span></span> |   <span data-ttu-id="5c7f9-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="5c7f9-113">Permission</span></span>  |   <span data-ttu-id="5c7f9-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="5c7f9-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5c7f9-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5c7f9-115">Application</span></span> |   <span data-ttu-id="5c7f9-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="5c7f9-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="5c7f9-117">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="5c7f9-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="5c7f9-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5c7f9-118">Delegated (work or school account)</span></span> | <span data-ttu-id="5c7f9-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="5c7f9-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="5c7f9-120">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="5c7f9-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="5c7f9-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5c7f9-121">HTTP request</span></span>
```
GET /api/recommendations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="5c7f9-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="5c7f9-122">Request headers</span></span>

<span data-ttu-id="5c7f9-123">Nome</span><span class="sxs-lookup"><span data-stu-id="5c7f9-123">Name</span></span> | <span data-ttu-id="5c7f9-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c7f9-124">Type</span></span> | <span data-ttu-id="5c7f9-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c7f9-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c7f9-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="5c7f9-126">Authorization</span></span> | <span data-ttu-id="5c7f9-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5c7f9-127">String</span></span> | <span data-ttu-id="5c7f9-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-128">Bearer {token}.</span></span> <span data-ttu-id="5c7f9-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5c7f9-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5c7f9-130">Request body</span></span>
<span data-ttu-id="5c7f9-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="5c7f9-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5c7f9-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="5c7f9-132">Response</span></span>
<span data-ttu-id="5c7f9-133">Se tiver êxito, este método retornará 200 OK com as recomendações de segurança no corpo.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="5c7f9-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5c7f9-134">Example</span></span>

<span data-ttu-id="5c7f9-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5c7f9-135">**Request**</span></span>

<span data-ttu-id="5c7f9-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome
```

<span data-ttu-id="5c7f9-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="5c7f9-137">**Response**</span></span>

<span data-ttu-id="5c7f9-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="5c7f9-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations/$entity",
    "id": "va-_-google-_-chrome",
    "productName": "chrome",
    "recommendationName": "Update Chrome",
    "weaknesses": 38,
    "vendor": "google",
    "recommendedVersion": "",
    "recommendationCategory": "Application",
    "subCategory": "",
    "severityScore": 0,
    "publicExploit": false,
    "activeAlert": false,
    "associatedThreats": [],
    "remediationType": "Update",
    "status": "Active",
    "configScoreImpact": 0,
    "exposureImpact": 3.9441860465116285,
    "totalMachineCount": 6,
    "exposedMachinesCount": 5,
    "nonProductivityImpactedAssets": 0,
    "relatedComponent": "Chrome"
}
```

## <a name="related-topics"></a><span data-ttu-id="5c7f9-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5c7f9-139">Related topics</span></span>
- [<span data-ttu-id="5c7f9-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="5c7f9-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="5c7f9-141">Recomendação & segurança de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="5c7f9-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
