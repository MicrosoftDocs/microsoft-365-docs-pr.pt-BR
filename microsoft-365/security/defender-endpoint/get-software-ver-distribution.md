---
title: Listar distribuição das versões do software
description: Recupera uma lista da distribuição de versão de software da sua organização
keywords: apis, api gráfica, apis com suporte, obter, distribuição de versão de software, api de tvm do Microsoft Defender para Endpoint
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
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845001"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="53ab5-104">Listar distribuição das versões do software</span><span class="sxs-lookup"><span data-stu-id="53ab5-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53ab5-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="53ab5-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="53ab5-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="53ab5-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="53ab5-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="53ab5-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="53ab5-108">Recupera uma lista da distribuição de versão de software da sua organização.</span><span class="sxs-lookup"><span data-stu-id="53ab5-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="53ab5-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="53ab5-109">Permissions</span></span>
<span data-ttu-id="53ab5-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="53ab5-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="53ab5-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="53ab5-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="53ab5-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="53ab5-112">Permission type</span></span> |   <span data-ttu-id="53ab5-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="53ab5-113">Permission</span></span>  |   <span data-ttu-id="53ab5-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="53ab5-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="53ab5-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="53ab5-115">Application</span></span> | <span data-ttu-id="53ab5-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="53ab5-116">Software.Read.All</span></span> | <span data-ttu-id="53ab5-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="53ab5-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="53ab5-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="53ab5-118">Delegated (work or school account)</span></span> | <span data-ttu-id="53ab5-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="53ab5-119">Software.Read</span></span> | <span data-ttu-id="53ab5-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="53ab5-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="53ab5-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="53ab5-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="53ab5-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="53ab5-122">Request headers</span></span>

| <span data-ttu-id="53ab5-123">Nome</span><span class="sxs-lookup"><span data-stu-id="53ab5-123">Name</span></span>        | <span data-ttu-id="53ab5-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="53ab5-124">Type</span></span> | <span data-ttu-id="53ab5-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="53ab5-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="53ab5-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="53ab5-126">Authorization</span></span> | <span data-ttu-id="53ab5-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="53ab5-127">String</span></span> | <span data-ttu-id="53ab5-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="53ab5-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="53ab5-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="53ab5-129">Request body</span></span>
<span data-ttu-id="53ab5-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="53ab5-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="53ab5-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="53ab5-131">Response</span></span>
<span data-ttu-id="53ab5-132">Se tiver êxito, este método retornará 200 OK com uma lista de dados de distribuições de software no corpo.</span><span class="sxs-lookup"><span data-stu-id="53ab5-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="53ab5-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="53ab5-133">Example</span></span>

<span data-ttu-id="53ab5-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="53ab5-134">**Request**</span></span>

<span data-ttu-id="53ab5-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="53ab5-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="53ab5-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="53ab5-136">**Response**</span></span>

<span data-ttu-id="53ab5-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="53ab5-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="53ab5-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="53ab5-138">Related topics</span></span>
- [<span data-ttu-id="53ab5-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="53ab5-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="53ab5-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="53ab5-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
