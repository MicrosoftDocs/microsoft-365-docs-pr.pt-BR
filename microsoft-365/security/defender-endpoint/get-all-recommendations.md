---
title: Listar todas as recomendações
description: Recupera uma lista de todas as recomendações de segurança que afetam a organização.
keywords: apis, api gráfica, apis com suporte, get, recomendações de segurança, api de tvm mdatp, gerenciamento de ameaças e vulnerabilidades, api de gerenciamento de ameaças e vulnerabilidades
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
ms.openlocfilehash: 5fb68572ee1b154be1db5eb5a092013a1c1a257e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166270"
---
# <a name="list-all-recommendations"></a><span data-ttu-id="0da88-104">Listar todas as recomendações</span><span class="sxs-lookup"><span data-stu-id="0da88-104">List all recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0da88-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0da88-105">**Applies to:**</span></span>
- [<span data-ttu-id="0da88-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0da88-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0da88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0da88-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="0da88-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0da88-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0da88-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0da88-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="0da88-110">Recupera uma lista de todas as recomendações de segurança que afetam a organização.</span><span class="sxs-lookup"><span data-stu-id="0da88-110">Retrieves a list of all security recommendations affecting the organization.</span></span>

## <a name="permissions"></a><span data-ttu-id="0da88-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="0da88-111">Permissions</span></span>
<span data-ttu-id="0da88-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="0da88-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="0da88-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="0da88-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="0da88-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="0da88-114">Permission type</span></span> |   <span data-ttu-id="0da88-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="0da88-115">Permission</span></span>  |   <span data-ttu-id="0da88-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="0da88-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="0da88-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="0da88-117">Application</span></span> |   <span data-ttu-id="0da88-118">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="0da88-118">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="0da88-119">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="0da88-119">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="0da88-120">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="0da88-120">Delegated (work or school account)</span></span> | <span data-ttu-id="0da88-121">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="0da88-121">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="0da88-122">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="0da88-122">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="0da88-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="0da88-123">HTTP request</span></span>
```
GET /api/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="0da88-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="0da88-124">Request headers</span></span>

<span data-ttu-id="0da88-125">Nome</span><span class="sxs-lookup"><span data-stu-id="0da88-125">Name</span></span> | <span data-ttu-id="0da88-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="0da88-126">Type</span></span> | <span data-ttu-id="0da88-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="0da88-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="0da88-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="0da88-128">Authorization</span></span> | <span data-ttu-id="0da88-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="0da88-129">String</span></span> | <span data-ttu-id="0da88-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="0da88-130">Bearer {token}.</span></span> <span data-ttu-id="0da88-131">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="0da88-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="0da88-132">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="0da88-132">Request body</span></span>
<span data-ttu-id="0da88-133">Vazio</span><span class="sxs-lookup"><span data-stu-id="0da88-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="0da88-134">Resposta</span><span class="sxs-lookup"><span data-stu-id="0da88-134">Response</span></span>
<span data-ttu-id="0da88-135">Se tiver êxito, este método retornará 200 OK com a lista de recomendações de segurança no corpo.</span><span class="sxs-lookup"><span data-stu-id="0da88-135">If successful, this method returns 200 OK with the list of security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="0da88-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0da88-136">Example</span></span>

<span data-ttu-id="0da88-137">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="0da88-137">**Request**</span></span>

<span data-ttu-id="0da88-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="0da88-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/recommendations
```

<span data-ttu-id="0da88-139">**Response**</span><span class="sxs-lookup"><span data-stu-id="0da88-139">**Response**</span></span>

<span data-ttu-id="0da88-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="0da88-140">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-microsoft-_-windows_10",
            "productName": "windows_10",
            "recommendationName": "Update Windows 10",
            "weaknesses": 397,
            "vendor": "microsoft",
            "recommendedVersion": "",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": true,
            "activeAlert": false,
            "associatedThreats": [
                "3098b8ef-23b1-46b3-aed4-499e1928f9ed",
                "40c189d5-0330-4654-a816-e48c2b7f9c4b",
                "4b0c9702-9b6c-4ca2-9d02-1556869f56f8",
                "e8fc2121-3cf3-4dd2-9ea0-87d7e1d2b29d",
                "94b6e94b-0c1d-4817-ac06-c3b8639be3ab"
            ],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 7.674418604651163,
            "totalMachineCount": 37,
            "exposedMachinesCount": 7,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Windows 10"
        }
        ...
     ]
}
```
## <a name="see-also"></a><span data-ttu-id="0da88-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="0da88-141">See also</span></span>
- [<span data-ttu-id="0da88-142">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="0da88-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="0da88-143">Recomendação & segurança de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="0da88-143">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)

