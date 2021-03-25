---
title: Listar software
description: Recupera uma lista de inventário de software
keywords: apis, api gráfica, apis com suporte, obter, listar, arquivo, informações, inventário de software, api de gerenciamento de & de ameaças, api de tvm mdatp
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
ms.openlocfilehash: 867fb57f61bd98b7c0afabd20b27e68d6bf45ef7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198560"
---
# <a name="list-software-inventory-api"></a><span data-ttu-id="dd71c-104">Listar API de inventário de software</span><span class="sxs-lookup"><span data-stu-id="dd71c-104">List software inventory API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dd71c-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="dd71c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="dd71c-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="dd71c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dd71c-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="dd71c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="dd71c-108">Recupera o inventário de software da organização.</span><span class="sxs-lookup"><span data-stu-id="dd71c-108">Retrieves the organization software inventory.</span></span>

## <a name="permissions"></a><span data-ttu-id="dd71c-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="dd71c-109">Permissions</span></span>
<span data-ttu-id="dd71c-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="dd71c-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="dd71c-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="dd71c-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="dd71c-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="dd71c-112">Permission type</span></span> |   <span data-ttu-id="dd71c-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="dd71c-113">Permission</span></span>  |   <span data-ttu-id="dd71c-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="dd71c-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="dd71c-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="dd71c-115">Application</span></span> |<span data-ttu-id="dd71c-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="dd71c-116">Software.Read.All</span></span> |    <span data-ttu-id="dd71c-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="dd71c-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="dd71c-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="dd71c-118">Delegated (work or school account)</span></span> | <span data-ttu-id="dd71c-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="dd71c-119">Software.Read</span></span> |    <span data-ttu-id="dd71c-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="dd71c-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="dd71c-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="dd71c-121">HTTP request</span></span>
```
GET /api/Software
```

## <a name="request-headers"></a><span data-ttu-id="dd71c-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="dd71c-122">Request headers</span></span>

<span data-ttu-id="dd71c-123">Nome</span><span class="sxs-lookup"><span data-stu-id="dd71c-123">Name</span></span> | <span data-ttu-id="dd71c-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="dd71c-124">Type</span></span> | <span data-ttu-id="dd71c-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd71c-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="dd71c-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="dd71c-126">Authorization</span></span> | <span data-ttu-id="dd71c-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dd71c-127">String</span></span> | <span data-ttu-id="dd71c-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="dd71c-128">Bearer {token}.</span></span> <span data-ttu-id="dd71c-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="dd71c-129">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="dd71c-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="dd71c-130">Request body</span></span>
<span data-ttu-id="dd71c-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="dd71c-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="dd71c-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="dd71c-132">Response</span></span>
<span data-ttu-id="dd71c-133">Se tiver êxito, este método retornará 200 OK com o inventário de software no corpo.</span><span class="sxs-lookup"><span data-stu-id="dd71c-133">If successful, this method returns 200 OK with the software inventory in the body.</span></span>


## <a name="example"></a><span data-ttu-id="dd71c-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dd71c-134">Example</span></span>

<span data-ttu-id="dd71c-135">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="dd71c-135">**Request**</span></span>

<span data-ttu-id="dd71c-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="dd71c-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software
```

<span data-ttu-id="dd71c-137">**Response**</span><span class="sxs-lookup"><span data-stu-id="dd71c-137">**Response**</span></span>

<span data-ttu-id="dd71c-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="dd71c-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
    "value": [
            {
                "id": "microsoft-_-edge",
                "name": "edge",
                "vendor": "microsoft",
                "weaknesses": 467,
                "publicExploit": true,
                "activeAlert": false,
                "exposedMachines": 172,
                "impactScore": 2.39947438
            }
            ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="dd71c-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="dd71c-139">Related topics</span></span>
- [<span data-ttu-id="dd71c-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="dd71c-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="dd71c-141">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="dd71c-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
