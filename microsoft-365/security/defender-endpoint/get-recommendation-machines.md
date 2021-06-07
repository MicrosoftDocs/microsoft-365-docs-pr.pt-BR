---
title: Listar dispositivos por recomendação
description: Recupera uma lista de dispositivos associados à recomendação de segurança.
keywords: apis, api gráfica, apis com suporte, obter, recomendação de segurança para dispositivos vulneráveis, Gerenciamento de Ameaças e Vulnerabilidades, Gerenciamento de Ameaças e Vulnerabilidades api
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
ms.openlocfilehash: 6c762a15051444ec950e92998317db4f7e51783c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771808"
---
# <a name="list-devices-by-recommendation"></a><span data-ttu-id="3078f-104">Listar dispositivos por recomendação</span><span class="sxs-lookup"><span data-stu-id="3078f-104">List devices by recommendation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3078f-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="3078f-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="3078f-106">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3078f-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3078f-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3078f-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="3078f-108">Recupera uma lista de dispositivos associados à recomendação de segurança.</span><span class="sxs-lookup"><span data-stu-id="3078f-108">Retrieves a list of devices associated with the security recommendation.</span></span>

## <a name="permissions"></a><span data-ttu-id="3078f-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="3078f-109">Permissions</span></span>
<span data-ttu-id="3078f-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="3078f-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3078f-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="3078f-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="3078f-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="3078f-112">Permission type</span></span> |   <span data-ttu-id="3078f-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="3078f-113">Permission</span></span>  |   <span data-ttu-id="3078f-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="3078f-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="3078f-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3078f-115">Application</span></span> |   <span data-ttu-id="3078f-116">SecurityRecommendation.Read.All</span><span class="sxs-lookup"><span data-stu-id="3078f-116">SecurityRecommendation.Read.All</span></span> |   <span data-ttu-id="3078f-117">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="3078f-117">'Read Threat and Vulnerability Management security recommendation information'</span></span>
<span data-ttu-id="3078f-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="3078f-118">Delegated (work or school account)</span></span> | <span data-ttu-id="3078f-119">SecurityRecommendation.Read</span><span class="sxs-lookup"><span data-stu-id="3078f-119">SecurityRecommendation.Read</span></span> |  <span data-ttu-id="3078f-120">'Ler informações de recomendação de segurança do Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="3078f-120">'Read Threat and Vulnerability Management security recommendation information'</span></span>

## <a name="http-request"></a><span data-ttu-id="3078f-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="3078f-121">HTTP request</span></span>
```
GET /api/recommendations/{id}/machineReferences
```

## <a name="request-headers"></a><span data-ttu-id="3078f-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="3078f-122">Request headers</span></span>

<span data-ttu-id="3078f-123">Nome</span><span class="sxs-lookup"><span data-stu-id="3078f-123">Name</span></span> | <span data-ttu-id="3078f-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="3078f-124">Type</span></span> | <span data-ttu-id="3078f-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="3078f-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="3078f-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="3078f-126">Authorization</span></span> | <span data-ttu-id="3078f-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="3078f-127">String</span></span> | <span data-ttu-id="3078f-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="3078f-128">Bearer {token}.</span></span> <span data-ttu-id="3078f-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="3078f-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="3078f-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="3078f-130">Request body</span></span>
<span data-ttu-id="3078f-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="3078f-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="3078f-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="3078f-132">Response</span></span>
<span data-ttu-id="3078f-133">Se tiver êxito, este método retornará 200 OK com a lista de dispositivos associados à recomendação de segurança.</span><span class="sxs-lookup"><span data-stu-id="3078f-133">If successful, this method returns 200 OK with the list of devices associated with the security recommendation.</span></span>


## <a name="example"></a><span data-ttu-id="3078f-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3078f-134">Example</span></span>

<span data-ttu-id="3078f-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="3078f-135">**Request**</span></span>

<span data-ttu-id="3078f-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="3078f-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/recommendations/va-_-google-_-chrome/machineReferences
```

<span data-ttu-id="3078f-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="3078f-137">**Response**</span></span>

<span data-ttu-id="3078f-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="3078f-138">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "e058770379bc199a9c179ce52a23e16fd44fd2ee",
            "computerDnsName": "niw_pc",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="3078f-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3078f-139">Related topics</span></span>
- [<span data-ttu-id="3078f-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="3078f-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="3078f-141">Recomendação & segurança de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="3078f-141">Threat & Vulnerability security recommendation</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation)
