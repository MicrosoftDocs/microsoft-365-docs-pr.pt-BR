---
title: Obter software por ID
description: Recupera uma lista de pontuações de exposição por grupo de dispositivos.
keywords: apis, api gráfica, apis com suporte, obter, software, api mdatp tvm
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
ms.openlocfilehash: 57d6ccd2c5387d478b75cfb6fb32a5b1052e491c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198584"
---
# <a name="get-software-by-id"></a><span data-ttu-id="31b12-104">Obter software por ID</span><span class="sxs-lookup"><span data-stu-id="31b12-104">Get software by Id</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="31b12-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="31b12-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="31b12-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="31b12-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31b12-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="31b12-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="31b12-108">Recupera os detalhes do software por ID.</span><span class="sxs-lookup"><span data-stu-id="31b12-108">Retrieves software details by ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="31b12-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="31b12-109">Permissions</span></span>
<span data-ttu-id="31b12-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="31b12-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31b12-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="31b12-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="31b12-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="31b12-112">Permission type</span></span> |   <span data-ttu-id="31b12-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="31b12-113">Permission</span></span>  |   <span data-ttu-id="31b12-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="31b12-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31b12-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="31b12-115">Application</span></span> | <span data-ttu-id="31b12-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="31b12-116">Software.Read.All</span></span> | <span data-ttu-id="31b12-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="31b12-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="31b12-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="31b12-118">Delegated (work or school account)</span></span> | <span data-ttu-id="31b12-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="31b12-119">Software.Read</span></span> | <span data-ttu-id="31b12-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="31b12-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="31b12-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="31b12-121">HTTP request</span></span>
```
GET /api/Software/{Id}
```

## <a name="request-headers"></a><span data-ttu-id="31b12-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="31b12-122">Request headers</span></span>

| <span data-ttu-id="31b12-123">Nome</span><span class="sxs-lookup"><span data-stu-id="31b12-123">Name</span></span>        | <span data-ttu-id="31b12-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="31b12-124">Type</span></span> | <span data-ttu-id="31b12-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="31b12-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="31b12-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="31b12-126">Authorization</span></span> | <span data-ttu-id="31b12-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="31b12-127">String</span></span> | <span data-ttu-id="31b12-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="31b12-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="31b12-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="31b12-129">Request body</span></span>
<span data-ttu-id="31b12-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="31b12-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31b12-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="31b12-131">Response</span></span>
<span data-ttu-id="31b12-132">Se tiver êxito, este método retornará 200 OK com os dados de software especificados no corpo.</span><span class="sxs-lookup"><span data-stu-id="31b12-132">If successful, this method returns 200 OK with the specified software data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="31b12-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="31b12-133">Example</span></span>

<span data-ttu-id="31b12-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="31b12-134">**Request**</span></span>

<span data-ttu-id="31b12-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="31b12-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

<span data-ttu-id="31b12-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="31b12-136">**Response**</span></span>

<span data-ttu-id="31b12-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="31b12-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="31b12-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="31b12-138">Related topics</span></span>
- [<span data-ttu-id="31b12-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="31b12-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="31b12-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="31b12-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
