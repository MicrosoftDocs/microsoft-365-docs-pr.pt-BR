---
title: Listar dispositivos por software
description: Recupere uma lista de dispositivos que têm esse software instalado.
keywords: apis, api gráfica, apis com suporte, obter, listar dispositivos, lista de dispositivos, listar dispositivos por software, Api de tvm do Microsoft Defender para Endpoint
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
ms.openlocfilehash: 8312818fe06b5a25ae32bf1f9585a51fe8848de6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845373"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="4740c-104">Listar dispositivos por software</span><span class="sxs-lookup"><span data-stu-id="4740c-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4740c-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4740c-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4740c-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4740c-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4740c-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4740c-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="4740c-108">Recupere uma lista de referências de dispositivo que tenha esse software instalado.</span><span class="sxs-lookup"><span data-stu-id="4740c-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="4740c-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="4740c-109">Permissions</span></span>
<span data-ttu-id="4740c-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="4740c-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4740c-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="4740c-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="4740c-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="4740c-112">Permission type</span></span> |   <span data-ttu-id="4740c-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="4740c-113">Permission</span></span>  |   <span data-ttu-id="4740c-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="4740c-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4740c-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4740c-115">Application</span></span> | <span data-ttu-id="4740c-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="4740c-116">Software.Read.All</span></span> | <span data-ttu-id="4740c-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="4740c-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="4740c-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="4740c-118">Delegated (work or school account)</span></span> | <span data-ttu-id="4740c-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="4740c-119">Software.Read</span></span> | <span data-ttu-id="4740c-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="4740c-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="4740c-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="4740c-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="4740c-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="4740c-122">Request headers</span></span>

| <span data-ttu-id="4740c-123">Nome</span><span class="sxs-lookup"><span data-stu-id="4740c-123">Name</span></span>        | <span data-ttu-id="4740c-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="4740c-124">Type</span></span> | <span data-ttu-id="4740c-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="4740c-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="4740c-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="4740c-126">Authorization</span></span> | <span data-ttu-id="4740c-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4740c-127">String</span></span> | <span data-ttu-id="4740c-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="4740c-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="4740c-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="4740c-129">Request body</span></span>
<span data-ttu-id="4740c-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="4740c-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4740c-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="4740c-131">Response</span></span>
<span data-ttu-id="4740c-132">Se tiver êxito, este método retornará 200 OK e uma lista de dispositivos com o software instalado no corpo.</span><span class="sxs-lookup"><span data-stu-id="4740c-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="4740c-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4740c-133">Example</span></span>

<span data-ttu-id="4740c-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="4740c-134">**Request**</span></span>

<span data-ttu-id="4740c-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="4740c-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="4740c-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="4740c-136">**Response**</span></span>

<span data-ttu-id="4740c-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="4740c-137">Here is an example of the response.</span></span>

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="4740c-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4740c-138">Related topics</span></span>
- [<span data-ttu-id="4740c-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="4740c-139">Risk-based Threat & Vulnerability Management</span></span>](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="4740c-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="4740c-140">Threat & Vulnerability software inventory</span></span>](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
