---
title: Listar distribuição de versão de software
description: Recupera uma lista da distribuição de versão de software da sua organização
keywords: apis, api gráfica, apis com suporte, obter, distribuição de versão de software, api mdatp tvm
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
ms.openlocfilehash: 88f446ddd87768817099c1a206bab17aa8be5b7b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198572"
---
# <a name="list-software-version-distribution"></a><span data-ttu-id="ce915-104">Listar distribuição de versão de software</span><span class="sxs-lookup"><span data-stu-id="ce915-104">List software version distribution</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ce915-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="ce915-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="ce915-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ce915-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ce915-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ce915-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="ce915-108">Recupera uma lista da distribuição de versão de software da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ce915-108">Retrieves a list of your organization's software version distribution.</span></span> 

## <a name="permissions"></a><span data-ttu-id="ce915-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="ce915-109">Permissions</span></span>
<span data-ttu-id="ce915-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ce915-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ce915-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ce915-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ce915-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ce915-112">Permission type</span></span> |   <span data-ttu-id="ce915-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="ce915-113">Permission</span></span>  |   <span data-ttu-id="ce915-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ce915-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ce915-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ce915-115">Application</span></span> | <span data-ttu-id="ce915-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="ce915-116">Software.Read.All</span></span> | <span data-ttu-id="ce915-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ce915-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="ce915-118">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ce915-118">Delegated (work or school account)</span></span> | <span data-ttu-id="ce915-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="ce915-119">Software.Read</span></span> | <span data-ttu-id="ce915-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="ce915-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="ce915-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="ce915-121">HTTP request</span></span>
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a><span data-ttu-id="ce915-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ce915-122">Request headers</span></span>

| <span data-ttu-id="ce915-123">Nome</span><span class="sxs-lookup"><span data-stu-id="ce915-123">Name</span></span>        | <span data-ttu-id="ce915-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="ce915-124">Type</span></span> | <span data-ttu-id="ce915-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="ce915-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="ce915-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="ce915-126">Authorization</span></span> | <span data-ttu-id="ce915-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ce915-127">String</span></span> | <span data-ttu-id="ce915-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ce915-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="ce915-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="ce915-129">Request body</span></span>
<span data-ttu-id="ce915-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="ce915-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ce915-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="ce915-131">Response</span></span>
<span data-ttu-id="ce915-132">Se tiver êxito, este método retornará 200 OK com uma lista de dados de distribuições de software no corpo.</span><span class="sxs-lookup"><span data-stu-id="ce915-132">If successful, this method returns 200 OK with a list of software distributions data in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="ce915-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ce915-133">Example</span></span>

<span data-ttu-id="ce915-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="ce915-134">**Request**</span></span>

<span data-ttu-id="ce915-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ce915-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

<span data-ttu-id="ce915-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="ce915-136">**Response**</span></span>

<span data-ttu-id="ce915-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="ce915-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="ce915-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ce915-138">Related topics</span></span>
- [<span data-ttu-id="ce915-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="ce915-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="ce915-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="ce915-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
