---
title: Obter KBs ausentes por ID de software
description: Recupera atualizações de segurança ausentes por ID de software
keywords: apis, api gráfica, apis com suporte, get, list, file, information, software id, threat & vulnerability management api, mdatp tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: e5d84a3eadab85713779dd70848bc11d27484dcc
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499388"
---
# <a name="get-missing-kbs-by-software-id"></a><span data-ttu-id="b5252-104">Obter KBs ausentes por ID de software</span><span class="sxs-lookup"><span data-stu-id="b5252-104">Get missing KBs by software ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b5252-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="b5252-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="b5252-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b5252-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b5252-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b5252-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="b5252-108">Recupera KBs ausentes (atualizações de segurança) por ID de software</span><span class="sxs-lookup"><span data-stu-id="b5252-108">Retrieves missing KBs (security updates) by software ID</span></span>

## <a name="permissions"></a><span data-ttu-id="b5252-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="b5252-109">Permissions</span></span>

<span data-ttu-id="b5252-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="b5252-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b5252-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b5252-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="b5252-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="b5252-112">Permission type</span></span> |   <span data-ttu-id="b5252-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="b5252-113">Permission</span></span>   |   <span data-ttu-id="b5252-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="b5252-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b5252-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b5252-115">Application</span></span> |<span data-ttu-id="b5252-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="b5252-116">Software.Read.All</span></span> |   <span data-ttu-id="b5252-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b5252-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="b5252-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="b5252-118">Delegated (work or school account)</span></span> | <span data-ttu-id="b5252-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="b5252-119">Software.Read</span></span> |   <span data-ttu-id="b5252-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b5252-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="b5252-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="b5252-121">HTTP request</span></span>

```
GET /api/Software/{Id}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="b5252-122">Header de solicitação</span><span class="sxs-lookup"><span data-stu-id="b5252-122">Request header</span></span>

<span data-ttu-id="b5252-123">Nome</span><span class="sxs-lookup"><span data-stu-id="b5252-123">Name</span></span> | <span data-ttu-id="b5252-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="b5252-124">Type</span></span> | <span data-ttu-id="b5252-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="b5252-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="b5252-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="b5252-126">Authorization</span></span> | <span data-ttu-id="b5252-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b5252-127">String</span></span> | <span data-ttu-id="b5252-128">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b5252-128">Bearer {token}.</span></span> <span data-ttu-id="b5252-129">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b5252-129">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b5252-130">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="b5252-130">Request body</span></span>

<span data-ttu-id="b5252-131">Vazio</span><span class="sxs-lookup"><span data-stu-id="b5252-131">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b5252-132">Resposta</span><span class="sxs-lookup"><span data-stu-id="b5252-132">Response</span></span>

<span data-ttu-id="b5252-133">Se tiver êxito, este método retornará 200 OK, com os dados kb do software especificado ausentes no corpo.</span><span class="sxs-lookup"><span data-stu-id="b5252-133">If successful, this method returns 200 OK, with the specified software missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="b5252-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b5252-134">Example</span></span>

### <a name="request"></a><span data-ttu-id="b5252-135">Solicitação</span><span class="sxs-lookup"><span data-stu-id="b5252-135">Request</span></span>

<span data-ttu-id="b5252-136">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="b5252-136">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/getmissingkbs
```

### <a name="response"></a><span data-ttu-id="b5252-137">Resposta</span><span class="sxs-lookup"><span data-stu-id="b5252-137">Response</span></span>

<span data-ttu-id="b5252-138">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="b5252-138">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
         {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "edge"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 240,
            "cveAddressed": 14
         },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="b5252-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b5252-139">Related topics</span></span>

- [<span data-ttu-id="b5252-140">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="b5252-140">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b5252-141">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="b5252-141">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
