---
title: Obter o software instalado
description: Recupera uma coleção de softwares instalados relacionados a uma determinada ID de dispositivo.
keywords: apis, api gráfica, apis com suporte, get, list, file, information, software inventory, installed software per device, threat & Gerenciamento de Vulnerabilidades api, Microsoft Defender for Endpoint tvm api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.openlocfilehash: 35cbeedc5d13f5eeb99718b4f98e2d8aabe1e965
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770152"
---
# <a name="get-installed-software"></a><span data-ttu-id="260ff-104">Obter o software instalado</span><span class="sxs-lookup"><span data-stu-id="260ff-104">Get installed software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="260ff-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="260ff-105">**Applies to:**</span></span>
- [<span data-ttu-id="260ff-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="260ff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="260ff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="260ff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="260ff-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="260ff-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="260ff-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="260ff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="260ff-110">Recupera uma coleção de softwares instalados relacionados a uma determinada ID de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="260ff-110">Retrieves a collection of installed software related to a given device ID.</span></span>

## <a name="permissions"></a><span data-ttu-id="260ff-111">Permissões</span><span class="sxs-lookup"><span data-stu-id="260ff-111">Permissions</span></span>
<span data-ttu-id="260ff-112">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="260ff-112">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="260ff-113">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="260ff-113">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="260ff-114">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="260ff-114">Permission type</span></span> |   <span data-ttu-id="260ff-115">Permissão</span><span class="sxs-lookup"><span data-stu-id="260ff-115">Permission</span></span>  |   <span data-ttu-id="260ff-116">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="260ff-116">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="260ff-117">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="260ff-117">Application</span></span> |<span data-ttu-id="260ff-118">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="260ff-118">Software.Read.All</span></span> |    <span data-ttu-id="260ff-119">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="260ff-119">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="260ff-120">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="260ff-120">Delegated (work or school account)</span></span> | <span data-ttu-id="260ff-121">Software.Read</span><span class="sxs-lookup"><span data-stu-id="260ff-121">Software.Read</span></span> |    <span data-ttu-id="260ff-122">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="260ff-122">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="260ff-123">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="260ff-123">HTTP request</span></span>
```
GET /api/machines/{machineId}/software
```

## <a name="request-headers"></a><span data-ttu-id="260ff-124">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="260ff-124">Request headers</span></span>

<span data-ttu-id="260ff-125">Nome</span><span class="sxs-lookup"><span data-stu-id="260ff-125">Name</span></span> | <span data-ttu-id="260ff-126">Tipo</span><span class="sxs-lookup"><span data-stu-id="260ff-126">Type</span></span> | <span data-ttu-id="260ff-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="260ff-127">Description</span></span>
:---|:---|:---
<span data-ttu-id="260ff-128">Autorização</span><span class="sxs-lookup"><span data-stu-id="260ff-128">Authorization</span></span> | <span data-ttu-id="260ff-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="260ff-129">String</span></span> | <span data-ttu-id="260ff-130">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="260ff-130">Bearer {token}.</span></span> <span data-ttu-id="260ff-131">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="260ff-131">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="260ff-132">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="260ff-132">Request body</span></span>
<span data-ttu-id="260ff-133">Vazio</span><span class="sxs-lookup"><span data-stu-id="260ff-133">Empty</span></span>

## <a name="response"></a><span data-ttu-id="260ff-134">Resposta</span><span class="sxs-lookup"><span data-stu-id="260ff-134">Response</span></span>
<span data-ttu-id="260ff-135">Se tiver êxito, este método retornará 200 OK com as informações de software instaladas no corpo.</span><span class="sxs-lookup"><span data-stu-id="260ff-135">If successful, this method returns 200 OK with the installed software information in the body.</span></span>


## <a name="example"></a><span data-ttu-id="260ff-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="260ff-136">Example</span></span>

<span data-ttu-id="260ff-137">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="260ff-137">**Request**</span></span>

<span data-ttu-id="260ff-138">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="260ff-138">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/ac233fa6208e1579620bf44207c4006ed7cc4501/software
```

<span data-ttu-id="260ff-139">**Response**</span><span class="sxs-lookup"><span data-stu-id="260ff-139">**Response**</span></span>

<span data-ttu-id="260ff-140">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="260ff-140">Here is an example of the response.</span></span>


```
{
"@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software",
"value": [
        {
"id": "microsoft-_-internet_explorer",
"name": "internet_explorer",
"vendor": "microsoft",
"weaknesses": 67,
"publicExploit": true,
"activeAlert": false,
"exposedMachines": 42115,
"impactScore": 46.2037163
        }
    ]
}
```

## <a name="see-also"></a><span data-ttu-id="260ff-141">Confira também</span><span class="sxs-lookup"><span data-stu-id="260ff-141">See also</span></span>

- [<span data-ttu-id="260ff-142">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="260ff-142">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="260ff-143">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="260ff-143">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
