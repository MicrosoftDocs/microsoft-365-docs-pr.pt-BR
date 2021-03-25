---
title: Obter pontuação de exposição
description: Recupera a pontuação de exposição organizacional.
keywords: apis, api gráfica, apis com suporte, obter, pontuação de exposição, pontuação de exposição organizacional
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7037e49a7f750597af15cfb16e1552aeb98859a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166261"
---
# <a name="get-exposure-score"></a><span data-ttu-id="bf23d-104">Obter pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="bf23d-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bf23d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bf23d-105">**Applies to:**</span></span>
- [<span data-ttu-id="bf23d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bf23d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bf23d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bf23d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bf23d-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bf23d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bf23d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bf23d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="bf23d-110">Recupera a pontuação de exposição organizacional.</span><span class="sxs-lookup"><span data-stu-id="bf23d-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="bf23d-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="bf23d-111">Permissions</span></span>

<span data-ttu-id="bf23d-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="bf23d-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="bf23d-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="bf23d-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="bf23d-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="bf23d-114">Permission type</span></span> | <span data-ttu-id="bf23d-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="bf23d-115">Permission</span></span> | <span data-ttu-id="bf23d-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="bf23d-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="bf23d-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="bf23d-117">Application</span></span> | <span data-ttu-id="bf23d-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="bf23d-118">Score.Read.All</span></span> | <span data-ttu-id="bf23d-119">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="bf23d-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="bf23d-120">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="bf23d-120">Delegated (work or school account)</span></span> | <span data-ttu-id="bf23d-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="bf23d-121">Score.Read</span></span> | <span data-ttu-id="bf23d-122">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="bf23d-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="bf23d-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="bf23d-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="bf23d-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="bf23d-124">Request headers</span></span>

<span data-ttu-id="bf23d-125">Nome</span><span class="sxs-lookup"><span data-stu-id="bf23d-125">Name</span></span> | <span data-ttu-id="bf23d-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf23d-126">Type</span></span> | <span data-ttu-id="bf23d-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="bf23d-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="bf23d-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="bf23d-128">Authorization</span></span> | <span data-ttu-id="bf23d-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="bf23d-129">String</span></span> | <span data-ttu-id="bf23d-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="bf23d-130">Bearer {token}.</span></span> <span data-ttu-id="bf23d-131">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="bf23d-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="bf23d-132">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="bf23d-132">Request body</span></span>

<span data-ttu-id="bf23d-133">Vazio</span><span class="sxs-lookup"><span data-stu-id="bf23d-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="bf23d-134">Resposta</span><span class="sxs-lookup"><span data-stu-id="bf23d-134">Response</span></span>

<span data-ttu-id="bf23d-135">Se tiver êxito, este método retornará 200 OK, com os dados de exposição no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="bf23d-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="bf23d-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bf23d-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="bf23d-137">Solicitação</span><span class="sxs-lookup"><span data-stu-id="bf23d-137">Request</span></span>

<span data-ttu-id="bf23d-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="bf23d-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="bf23d-139">Resposta</span><span class="sxs-lookup"><span data-stu-id="bf23d-139">Response</span></span>

<span data-ttu-id="bf23d-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="bf23d-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="bf23d-141">A lista de respostas mostrada aqui pode ser truncada para brevidade.</span><span class="sxs-lookup"><span data-stu-id="bf23d-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="bf23d-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="bf23d-142">See also</span></span>

- [<span data-ttu-id="bf23d-143">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="bf23d-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="bf23d-144">Classificação & de exposição de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="bf23d-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
