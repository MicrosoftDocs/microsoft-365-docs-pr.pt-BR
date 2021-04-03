---
title: Obter KBs ausentes por ID do dispositivo
description: Recupera atualizações de segurança ausentes por ID do dispositivo
keywords: apis, api gráfica, apis com suporte, get, list, file, information, device id, threat & vulnerability management api, mdatp tvm api
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
ms.openlocfilehash: 4364e6a38d4597a95d4d9a1f05dcce6fce5797ef
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500699"
---
# <a name="get-missing-kbs-by-device-id"></a><span data-ttu-id="5fae3-104">Obter KBs ausentes por ID do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5fae3-104">Get missing KBs by device ID</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5fae3-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5fae3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5fae3-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5fae3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5fae3-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5fae3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="5fae3-108">Recupera KBs ausentes (atualizações de segurança) por ID do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5fae3-108">Retrieves missing KBs (security updates) by device ID</span></span>

## <a name="http-request"></a><span data-ttu-id="5fae3-109">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5fae3-109">HTTP request</span></span>

```
GET /api/machines/{machineId}/getmissingkbs
```

## <a name="request-header"></a><span data-ttu-id="5fae3-110">Header de solicitação</span><span class="sxs-lookup"><span data-stu-id="5fae3-110">Request header</span></span>

<span data-ttu-id="5fae3-111">Nome</span><span class="sxs-lookup"><span data-stu-id="5fae3-111">Name</span></span> | <span data-ttu-id="5fae3-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="5fae3-112">Type</span></span> | <span data-ttu-id="5fae3-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="5fae3-113">Description</span></span>
:---|:---|:---
<span data-ttu-id="5fae3-114">Autorização</span><span class="sxs-lookup"><span data-stu-id="5fae3-114">Authorization</span></span> | <span data-ttu-id="5fae3-115">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5fae3-115">String</span></span> | <span data-ttu-id="5fae3-116">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5fae3-116">Bearer {token}.</span></span> <span data-ttu-id="5fae3-117">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5fae3-117">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5fae3-118">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5fae3-118">Request body</span></span>

<span data-ttu-id="5fae3-119">Vazio</span><span class="sxs-lookup"><span data-stu-id="5fae3-119">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5fae3-120">Resposta</span><span class="sxs-lookup"><span data-stu-id="5fae3-120">Response</span></span>

<span data-ttu-id="5fae3-121">Se tiver êxito, este método retornará 200 OK, com os dados kb do dispositivo especificado ausentes no corpo.</span><span class="sxs-lookup"><span data-stu-id="5fae3-121">If successful, this method returns 200 OK, with the specified device missing kb data in the body.</span></span>

## <a name="example"></a><span data-ttu-id="5fae3-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5fae3-122">Example</span></span>

### <a name="request"></a><span data-ttu-id="5fae3-123">Solicitação</span><span class="sxs-lookup"><span data-stu-id="5fae3-123">Request</span></span>

<span data-ttu-id="5fae3-124">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5fae3-124">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/machines/2339ad14a01bd0299afb93dfa2550136057bff96/getmissingkbs 
```

### <a name="response"></a><span data-ttu-id="5fae3-125">Resposta</span><span class="sxs-lookup"><span data-stu-id="5fae3-125">Response</span></span>

<span data-ttu-id="5fae3-126">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="5fae3-126">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.PublicProductFixDto)",
    "value": [
        {
            "id": "4540673",
            "name": "March 2020 Security Updates",
            "productsNames": [
                "windows_10",
                "edge",
                "internet_explorer"
            ],
            "url": "https://catalog.update.microsoft.com/v7/site/Search.aspx?q=KB4540673",
            "machineMissedOn": 1,
            "cveAddressed": 97
        },
         ...
        ]
}
```

## <a name="related-topics"></a><span data-ttu-id="5fae3-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5fae3-127">Related topics</span></span>

- [<span data-ttu-id="5fae3-128">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="5fae3-128">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="5fae3-129">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="5fae3-129">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
