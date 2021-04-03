---
title: Listar pontuação de exposição por grupo de dispositivos
description: Recupera uma lista de pontuações de exposição por grupo de dispositivos.
keywords: apis, api gráfica, apis com suporte, obter, pontuação de exposição, grupo de dispositivos, pontuação de exposição do grupo de dispositivos
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 54b3e0cd63189e67de0aa101634508ff8833dc6a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500251"
---
# <a name="list-exposure-score-by-device-group"></a><span data-ttu-id="2740a-104">Listar pontuação de exposição por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2740a-104">List exposure score by device group</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2740a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2740a-105">**Applies to:**</span></span>
- [<span data-ttu-id="2740a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2740a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2740a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2740a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2740a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2740a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2740a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2740a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="2740a-110">Recupera uma coleção de alertas relacionados a um determinado endereço de domínio.</span><span class="sxs-lookup"><span data-stu-id="2740a-110">Retrieves a collection of alerts related to a given domain address.</span></span>

## <a name="permissions"></a><span data-ttu-id="2740a-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="2740a-111">Permissions</span></span>

<span data-ttu-id="2740a-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="2740a-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2740a-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2740a-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2740a-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="2740a-114">Permission type</span></span> |   <span data-ttu-id="2740a-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="2740a-115">Permission</span></span>  |   <span data-ttu-id="2740a-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="2740a-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2740a-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2740a-117">Application</span></span> | <span data-ttu-id="2740a-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="2740a-118">Score.Read.All</span></span> | <span data-ttu-id="2740a-119">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2740a-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="2740a-120">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2740a-120">Delegated (work or school account)</span></span> | <span data-ttu-id="2740a-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="2740a-121">Score.Read</span></span> | <span data-ttu-id="2740a-122">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="2740a-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="2740a-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="2740a-123">HTTP request</span></span>

```
GET /api/exposureScore/ByMachineGroups
```

## <a name="request-headers"></a><span data-ttu-id="2740a-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="2740a-124">Request headers</span></span>

| <span data-ttu-id="2740a-125">Nome</span><span class="sxs-lookup"><span data-stu-id="2740a-125">Name</span></span>        | <span data-ttu-id="2740a-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="2740a-126">Type</span></span> | <span data-ttu-id="2740a-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="2740a-127">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="2740a-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="2740a-128">Authorization</span></span> | <span data-ttu-id="2740a-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2740a-129">String</span></span> | <span data-ttu-id="2740a-130">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="2740a-130">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2740a-131">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="2740a-131">Request body</span></span>

<span data-ttu-id="2740a-132">Vazio</span><span class="sxs-lookup"><span data-stu-id="2740a-132">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2740a-133">Resposta</span><span class="sxs-lookup"><span data-stu-id="2740a-133">Response</span></span>

<span data-ttu-id="2740a-134">Se tiver êxito, este método retornará 200 OK, com uma lista de pontuação de exposição por dados do grupo de dispositivos no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="2740a-134">If successful, this method returns 200 OK, with a list of exposure score per device group data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="2740a-135">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2740a-135">Example</span></span>

### <a name="request"></a><span data-ttu-id="2740a-136">Solicitação</span><span class="sxs-lookup"><span data-stu-id="2740a-136">Request</span></span>

<span data-ttu-id="2740a-137">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2740a-137">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/exposureScore/ByMachineGroups
```

### <a name="response"></a><span data-ttu-id="2740a-138">Resposta</span><span class="sxs-lookup"><span data-stu-id="2740a-138">Response</span></span>

<span data-ttu-id="2740a-139">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="2740a-139">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore",
    "value": [
        {
            "time": "2019-12-03T09:51:28.214338Z",
            "score": 41.38041766305988,
            "rbacGroupName": "GroupOne"
        },
        {
            "time": "2019-12-03T09:51:28.2143399Z",
            "score": 37.403726933165366,
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="2740a-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2740a-140">Related topics</span></span>

- [<span data-ttu-id="2740a-141">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="2740a-141">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="2740a-142">Classificação & de exposição de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="2740a-142">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
