---
title: Obter pontuação de exposição
description: Recupera a pontuação de exposição organizacional.
keywords: apis, api gráfica, apis com suporte, obter, pontuação de exposição, pontuação de exposição organizacional
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9da87dcb64f8c62966382e3a2888f03c49149a09
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770419"
---
# <a name="get-exposure-score"></a><span data-ttu-id="b1100-104">Obter pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="b1100-104">Get exposure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b1100-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b1100-105">**Applies to:**</span></span>
- [<span data-ttu-id="b1100-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b1100-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b1100-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1100-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b1100-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b1100-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b1100-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b1100-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="b1100-110">Recupera a pontuação de exposição organizacional.</span><span class="sxs-lookup"><span data-stu-id="b1100-110">Retrieves the organizational exposure score.</span></span>

## <a name="permissions"></a><span data-ttu-id="b1100-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="b1100-111">Permissions</span></span>

<span data-ttu-id="b1100-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="b1100-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b1100-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b1100-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b1100-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="b1100-114">Permission type</span></span> | <span data-ttu-id="b1100-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="b1100-115">Permission</span></span> | <span data-ttu-id="b1100-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="b1100-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b1100-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b1100-117">Application</span></span> | <span data-ttu-id="b1100-118">Score.Read.All</span><span class="sxs-lookup"><span data-stu-id="b1100-118">Score.Read.All</span></span> | <span data-ttu-id="b1100-119">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b1100-119">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="b1100-120">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="b1100-120">Delegated (work or school account)</span></span> | <span data-ttu-id="b1100-121">Score.Read</span><span class="sxs-lookup"><span data-stu-id="b1100-121">Score.Read</span></span> | <span data-ttu-id="b1100-122">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="b1100-122">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="b1100-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="b1100-123">HTTP request</span></span>

```
GET /api/exposureScore
```

## <a name="request-headers"></a><span data-ttu-id="b1100-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="b1100-124">Request headers</span></span>

<span data-ttu-id="b1100-125">Nome</span><span class="sxs-lookup"><span data-stu-id="b1100-125">Name</span></span> | <span data-ttu-id="b1100-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="b1100-126">Type</span></span> | <span data-ttu-id="b1100-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="b1100-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="b1100-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="b1100-128">Authorization</span></span> | <span data-ttu-id="b1100-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b1100-129">String</span></span> | <span data-ttu-id="b1100-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b1100-130">Bearer {token}.</span></span> <span data-ttu-id="b1100-131">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b1100-131">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b1100-132">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="b1100-132">Request body</span></span>

<span data-ttu-id="b1100-133">Vazio</span><span class="sxs-lookup"><span data-stu-id="b1100-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="b1100-134">Resposta</span><span class="sxs-lookup"><span data-stu-id="b1100-134">Response</span></span>

<span data-ttu-id="b1100-135">Se tiver êxito, este método retornará 200 OK, com os dados de exposição no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="b1100-135">If successful, this method returns 200 OK, with the exposure data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="b1100-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b1100-136">Example</span></span>

### <a name="request"></a><span data-ttu-id="b1100-137">Solicitação</span><span class="sxs-lookup"><span data-stu-id="b1100-137">Request</span></span>

<span data-ttu-id="b1100-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="b1100-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/exposureScore
```

### <a name="response"></a><span data-ttu-id="b1100-139">Resposta</span><span class="sxs-lookup"><span data-stu-id="b1100-139">Response</span></span>

<span data-ttu-id="b1100-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="b1100-140">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="b1100-141">A lista de respostas mostrada aqui pode ser truncada para brevidade.</span><span class="sxs-lookup"><span data-stu-id="b1100-141">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ExposureScore/$entity",
    "time": "2019-12-03T07:23:53.280499Z",
    "score": 33.491554051195706
}

```

## <a name="see-also"></a><span data-ttu-id="b1100-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="b1100-142">See also</span></span>

- [<span data-ttu-id="b1100-143">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="b1100-143">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="b1100-144">Classificação & de exposição de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="b1100-144">Threat & Vulnerability exposure score</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-exposure-score)
