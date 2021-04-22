---
title: Obter recomendações de segurança
description: Recupera uma coleção de recomendações de segurança relacionadas a uma determinada ID de dispositivo.
keywords: apis, api gráfica, apis com suporte, obter, listar, arquivo, informações, recomendação de segurança por dispositivo, api de gerenciamento de & de ameaças, api de tvm do Microsoft Defender para Ponto de Extremidade
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
ms.openlocfilehash: bc209687d51b3e05bfcfd6028042ba5912b877f6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935300"
---
# <a name="get-security-recommendations"></a><span data-ttu-id="05d0d-104">Obter recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="05d0d-104">Get security recommendations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05d0d-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="05d0d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="05d0d-106">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="05d0d-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="05d0d-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="05d0d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="05d0d-108">Recupera uma coleção de recomendações de segurança relacionadas a uma determinada ID de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="05d0d-108">Retrieves a collection of security recommendations related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="05d0d-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="05d0d-109">Permissions</span></span>
<span data-ttu-id="05d0d-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="05d0d-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="05d0d-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="05d0d-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="05d0d-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="05d0d-112">Permission type</span></span> |   <span data-ttu-id="05d0d-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="05d0d-113">Permission</span></span>  |   <span data-ttu-id="05d0d-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="05d0d-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="05d0d-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="05d0d-115">Application</span></span> | <span data-ttu-id="05d0d-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="05d0d-116">SecurityRecommendation.Read.All</span></span> | <span data-ttu-id="05d0d-117">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="05d0d-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="05d0d-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="05d0d-118">Delegated (work or school account)</span></span> | <span data-ttu-id="05d0d-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="05d0d-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="05d0d-120">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="05d0d-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="05d0d-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="05d0d-121">HTTP request</span></span>
```
GET /api/machines/{machineId}/recommendations
```

## <a name="request-headers"></a><span data-ttu-id="05d0d-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="05d0d-122">Request headers</span></span>

<span data-ttu-id="05d0d-123">Nome</span><span class="sxs-lookup"><span data-stu-id="05d0d-123">Name</span></span> | <span data-ttu-id="05d0d-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="05d0d-124">Type</span></span> | <span data-ttu-id="05d0d-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="05d0d-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="05d0d-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="05d0d-126">Authorization</span></span> | <span data-ttu-id="05d0d-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="05d0d-127">String</span></span> | <span data-ttu-id="05d0d-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="05d0d-128">Bearer {token}.</span></span> <span data-ttu-id="05d0d-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="05d0d-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="05d0d-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="05d0d-130">Request body</span></span>
<span data-ttu-id="05d0d-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="05d0d-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="05d0d-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="05d0d-132">Response</span></span>
<span data-ttu-id="05d0d-133">Se tiver êxito, este método retornará 200 OK com as recomendações de segurança no corpo.</span><span class="sxs-lookup"><span data-stu-id="05d0d-133">If successful, this method returns 200 OK with the security recommendations in the body.</span></span>


## <a name="example"></a><span data-ttu-id="05d0d-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="05d0d-134">Example</span></span>

<span data-ttu-id="05d0d-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="05d0d-135">**Request**</span></span>

<span data-ttu-id="05d0d-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="05d0d-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/recommendations
```

<span data-ttu-id="05d0d-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="05d0d-137">**Response**</span></span>

<span data-ttu-id="05d0d-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="05d0d-138">Here is an example of the response.</span></span>


```
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Recommendations",
    "value": [
        {
            "id": "va-_-git-scm-_-git",
            "productName": "git",
            "recommendationName": "Update Git to version 2.24.1.2",
            "weaknesses": 3,
            "vendor": "git-scm",
            "recommendedVersion": "2.24.1.2",
            "recommendationCategory": "Application",
            "subCategory": "",
            "severityScore": 0,
            "publicExploit": false,
            "activeAlert": false,
            "associatedThreats": [],
            "remediationType": "Update",
            "status": "Active",
            "configScoreImpact": 0,
            "exposureImpact": 0,
            "totalMachineCount": 0,
            "exposedMachinesCount": 1,
            "nonProductivityImpactedAssets": 0,
            "relatedComponent": "Git"
        },
…
}
```

## <a name="related-topics"></a><span data-ttu-id="05d0d-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="05d0d-139">Related topics</span></span>
- [<span data-ttu-id="05d0d-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="05d0d-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="05d0d-141">Recomendação & segurança de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="05d0d-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
