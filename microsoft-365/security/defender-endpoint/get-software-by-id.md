---
title: Obter software por ID
description: Recupera uma lista de pontuações de exposição por grupo de dispositivos.
keywords: apis, api gráfica, apis com suporte, get, software, api de tvm do Microsoft Defender para Endpoint
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
ms.openlocfilehash: d9a7d97cea96f919f1ec7cd1e37e7a8f27042c79
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845085"
---
# <a name="get-software-by-id"></a><span data-ttu-id="68ca8-104">Obter software por ID</span><span class="sxs-lookup"><span data-stu-id="68ca8-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68ca8-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="68ca8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="68ca8-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="68ca8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68ca8-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="68ca8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="68ca8-108">Recupera os detalhes do software por ID.</span><span class="sxs-lookup"><span data-stu-id="68ca8-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="68ca8-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="68ca8-109">Permissions</span></span>
<span data-ttu-id="68ca8-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="68ca8-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="68ca8-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="68ca8-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="68ca8-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="68ca8-112">Permission type</span></span> |   <span data-ttu-id="68ca8-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="68ca8-113">Permission</span></span>  |   <span data-ttu-id="68ca8-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="68ca8-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="68ca8-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="68ca8-115">Application</span></span> | <span data-ttu-id="68ca8-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="68ca8-116">Software.Read.All</span></span> | <span data-ttu-id="68ca8-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="68ca8-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="68ca8-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="68ca8-118">Delegated (work or school account)</span></span> | <span data-ttu-id="68ca8-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="68ca8-119">Software.Read</span></span> | <span data-ttu-id="68ca8-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="68ca8-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="68ca8-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="68ca8-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="68ca8-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="68ca8-122">Request headers</span></span>

| <span data-ttu-id="68ca8-123">Nome</span><span class="sxs-lookup"><span data-stu-id="68ca8-123">Name</span></span>        | <span data-ttu-id="68ca8-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="68ca8-124">Type</span></span> | <span data-ttu-id="68ca8-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="68ca8-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="68ca8-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="68ca8-126">Authorization</span></span> | <span data-ttu-id="68ca8-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="68ca8-127">String</span></span> | <span data-ttu-id="68ca8-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="68ca8-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="68ca8-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="68ca8-129">Request body</span></span>
<span data-ttu-id="68ca8-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="68ca8-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="68ca8-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="68ca8-131">Response</span></span>
<span data-ttu-id="68ca8-132">Se tiver êxito, este método retornará 200 OK com os dados de software especificados no corpo.</span><span class="sxs-lookup"><span data-stu-id="68ca8-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="68ca8-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="68ca8-133">Example</span></span>

<span data-ttu-id="68ca8-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="68ca8-134">**Request**</span></span>

<span data-ttu-id="68ca8-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="68ca8-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="68ca8-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="68ca8-136">**Response**</span></span>

<span data-ttu-id="68ca8-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="68ca8-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a><span data-ttu-id="68ca8-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="68ca8-138">Related topics</span></span>
- [<span data-ttu-id="68ca8-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="68ca8-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="68ca8-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="68ca8-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
