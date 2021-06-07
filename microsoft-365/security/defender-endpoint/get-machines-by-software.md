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
ms.openlocfilehash: e1adf28823d6b86417c32578a89480958946c50d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770548"
---
# <a name="list-devices-by-software"></a><span data-ttu-id="945b3-104">Listar dispositivos por software</span><span class="sxs-lookup"><span data-stu-id="945b3-104">List devices by software</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="945b3-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="945b3-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="945b3-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="945b3-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="945b3-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="945b3-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="945b3-108">Recupere uma lista de referências de dispositivo que tenha esse software instalado.</span><span class="sxs-lookup"><span data-stu-id="945b3-108">Retrieve a list of device references that has this software installed.</span></span>

## <a name="permissions"></a><span data-ttu-id="945b3-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="945b3-109">Permissions</span></span>
<span data-ttu-id="945b3-110">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="945b3-110">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="945b3-111">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="945b3-111">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="945b3-112">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="945b3-112">Permission type</span></span> |   <span data-ttu-id="945b3-113">Permissão</span><span class="sxs-lookup"><span data-stu-id="945b3-113">Permission</span></span>  |   <span data-ttu-id="945b3-114">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="945b3-114">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="945b3-115">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="945b3-115">Application</span></span> | <span data-ttu-id="945b3-116">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="945b3-116">Software.Read.All</span></span> | <span data-ttu-id="945b3-117">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="945b3-117">'Read Threat and Vulnerability Management Software information'</span></span>
<span data-ttu-id="945b3-118">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="945b3-118">Delegated (work or school account)</span></span> | <span data-ttu-id="945b3-119">Software.Read</span><span class="sxs-lookup"><span data-stu-id="945b3-119">Software.Read</span></span> | <span data-ttu-id="945b3-120">'Ler informações do Software de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="945b3-120">'Read Threat and Vulnerability Management Software information'</span></span>

## <a name="http-request"></a><span data-ttu-id="945b3-121">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="945b3-121">HTTP request</span></span>
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a><span data-ttu-id="945b3-122">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="945b3-122">Request headers</span></span>

| <span data-ttu-id="945b3-123">Nome</span><span class="sxs-lookup"><span data-stu-id="945b3-123">Name</span></span>        | <span data-ttu-id="945b3-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="945b3-124">Type</span></span> | <span data-ttu-id="945b3-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="945b3-125">Description</span></span>
|:--------------|:-------|:--------------|
| <span data-ttu-id="945b3-126">Autorização</span><span class="sxs-lookup"><span data-stu-id="945b3-126">Authorization</span></span> | <span data-ttu-id="945b3-127">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="945b3-127">String</span></span> | <span data-ttu-id="945b3-128">Portador {token}. **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="945b3-128">Bearer {token}.**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="945b3-129">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="945b3-129">Request body</span></span>
<span data-ttu-id="945b3-130">Vazio</span><span class="sxs-lookup"><span data-stu-id="945b3-130">Empty</span></span>

## <a name="response"></a><span data-ttu-id="945b3-131">Resposta</span><span class="sxs-lookup"><span data-stu-id="945b3-131">Response</span></span>
<span data-ttu-id="945b3-132">Se tiver êxito, este método retornará 200 OK e uma lista de dispositivos com o software instalado no corpo.</span><span class="sxs-lookup"><span data-stu-id="945b3-132">If successful, this method returns 200 OK and a list of devices with the software installed in the body.</span></span> 


## <a name="example"></a><span data-ttu-id="945b3-133">Exemplo</span><span class="sxs-lookup"><span data-stu-id="945b3-133">Example</span></span>

<span data-ttu-id="945b3-134">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="945b3-134">**Request**</span></span>

<span data-ttu-id="945b3-135">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="945b3-135">Here is an example of the request.</span></span>

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

<span data-ttu-id="945b3-136">**Response**</span><span class="sxs-lookup"><span data-stu-id="945b3-136">**Response**</span></span>

<span data-ttu-id="945b3-137">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="945b3-137">Here is an example of the response.</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="945b3-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="945b3-138">Related topics</span></span>
- [<span data-ttu-id="945b3-139">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="945b3-139">Risk-based Threat & Vulnerability Management</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [<span data-ttu-id="945b3-140">Inventário & software de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="945b3-140">Threat & Vulnerability software inventory</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
