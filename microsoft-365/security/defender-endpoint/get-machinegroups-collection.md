---
title: Obter API da coleção de grupos de máquinas RBAC
description: Saiba como usar a API da coleção Get KB para recuperar uma coleção de grupos de dispositivos RBAC na Proteção Avançada contra Ameaças do Microsoft Defender.
keywords: apis, api gráfica, apis com suporte, get, RBAC, group
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: leonidzh
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/07/2018
ms.openlocfilehash: 54a0edb47204fe6e48666f0927d05121af95e00a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166288"
---
# <a name="get-kb-collection-api"></a><span data-ttu-id="62fa6-104">Obter API de coleção KB</span><span class="sxs-lookup"><span data-stu-id="62fa6-104">Get KB collection API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="62fa6-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="62fa6-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="62fa6-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="62fa6-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="62fa6-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="62fa6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="62fa6-108">Recupera uma coleção de grupos de dispositivos RBAC.</span><span class="sxs-lookup"><span data-stu-id="62fa6-108">Retrieves a collection of RBAC device groups.</span></span>

## <a name="permissions"></a><span data-ttu-id="62fa6-109">Permissões</span><span class="sxs-lookup"><span data-stu-id="62fa6-109">Permissions</span></span>
<span data-ttu-id="62fa6-110">O usuário precisa de permissões de leitura.</span><span class="sxs-lookup"><span data-stu-id="62fa6-110">User needs read permissions.</span></span>

## <a name="http-request"></a><span data-ttu-id="62fa6-111">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="62fa6-111">HTTP request</span></span>
```
GET /testwdatppreview/machinegroups
```

## <a name="request-headers"></a><span data-ttu-id="62fa6-112">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="62fa6-112">Request headers</span></span>

<span data-ttu-id="62fa6-113">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="62fa6-113">Header</span></span> | <span data-ttu-id="62fa6-114">Valor</span><span class="sxs-lookup"><span data-stu-id="62fa6-114">Value</span></span> 
:---|:---
<span data-ttu-id="62fa6-115">Autorização</span><span class="sxs-lookup"><span data-stu-id="62fa6-115">Authorization</span></span> | <span data-ttu-id="62fa6-116">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="62fa6-116">Bearer {token}.</span></span> <span data-ttu-id="62fa6-117">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="62fa6-117">**Required**.</span></span>
<span data-ttu-id="62fa6-118">Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="62fa6-118">Content type</span></span> | <span data-ttu-id="62fa6-119">application/json</span><span class="sxs-lookup"><span data-stu-id="62fa6-119">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="62fa6-120">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="62fa6-120">Request body</span></span>
<span data-ttu-id="62fa6-121">Vazio</span><span class="sxs-lookup"><span data-stu-id="62fa6-121">Empty</span></span>

## <a name="response"></a><span data-ttu-id="62fa6-122">Resposta</span><span class="sxs-lookup"><span data-stu-id="62fa6-122">Response</span></span>
<span data-ttu-id="62fa6-123">Se bem-sucedido - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="62fa6-123">If successful - 200 OK.</span></span>

## <a name="example"></a><span data-ttu-id="62fa6-124">Exemplo</span><span class="sxs-lookup"><span data-stu-id="62fa6-124">Example</span></span>

<span data-ttu-id="62fa6-125">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="62fa6-125">**Request**</span></span>

<span data-ttu-id="62fa6-126">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="62fa6-126">Here is an example of the request.</span></span>

```
GET https://graph.microsoft.com/testwdatppreview/machinegroups
Content-type: application/json
```

<span data-ttu-id="62fa6-127">**Response**</span><span class="sxs-lookup"><span data-stu-id="62fa6-127">**Response**</span></span>

<span data-ttu-id="62fa6-128">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="62fa6-128">Here is an example of the response.</span></span>
<span data-ttu-id="62fa6-129">A id de campo contém **id** do grupo de dispositivos e igual ao campo **rbacGroupId** em informações de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="62fa6-129">Field id contains device group **id** and equal to field **rbacGroupId** in devices info.</span></span> <span data-ttu-id="62fa6-130">O **campo desagrupado** só é verdadeiro para um grupo para todos os dispositivos que não foram atribuídos a nenhum grupo.</span><span class="sxs-lookup"><span data-stu-id="62fa6-130">Field **ungrouped** is true only for one group for all devices that have not been assigned to any group.</span></span> <span data-ttu-id="62fa6-131">Esse grupo, como de costume, tem o nome "UnassignedGroup".</span><span class="sxs-lookup"><span data-stu-id="62fa6-131">This group as usual has name "UnassignedGroup".</span></span>

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context":"https://graph.microsoft.com/testwdatppreview/$metadata#MachineGroups",
    "@odata.count":7,
    "value":[
        {
            "id":86,
            "name":"UnassignedGroup",
            "description":"",
            "ungrouped":true},
        …
}
```
