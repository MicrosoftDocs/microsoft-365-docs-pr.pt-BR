---
title: Obter informações de IPs relacionadas ao alerta
description: Recupere todos os IPs relacionados a um alerta específico usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter informações de alerta, informações de alerta, ip relacionado
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: b6ac9746ff82f81772505daac7d7f36249687d7d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772324"
---
# <a name="get-alert-related-ips-information-api"></a><span data-ttu-id="9bfd4-104">Obter API de informações de IPs relacionadas ao alerta</span><span class="sxs-lookup"><span data-stu-id="9bfd4-104">Get alert related IPs information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9bfd4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9bfd4-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bfd4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9bfd4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9bfd4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bfd4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9bfd4-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9bfd4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9bfd4-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9bfd4-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9bfd4-110">API description</span></span>
<span data-ttu-id="9bfd4-111">Recupera todos os IPs relacionados a um alerta específico.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-111">Retrieves all IPs related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="9bfd4-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="9bfd4-112">Limitations</span></span>
1. <span data-ttu-id="9bfd4-113">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="9bfd4-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="9bfd4-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="9bfd4-115">Permissions</span></span>
<span data-ttu-id="9bfd4-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9bfd4-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9bfd4-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9bfd4-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9bfd4-118">Permission type</span></span> |   <span data-ttu-id="9bfd4-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="9bfd4-119">Permission</span></span>  |   <span data-ttu-id="9bfd4-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9bfd4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9bfd4-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9bfd4-121">Application</span></span> |   <span data-ttu-id="9bfd4-122">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="9bfd4-122">Ip.Read.All</span></span> |   <span data-ttu-id="9bfd4-123">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="9bfd4-123">'Read IP address profiles'</span></span>
<span data-ttu-id="9bfd4-124">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9bfd4-124">Delegated (work or school account)</span></span> | <span data-ttu-id="9bfd4-125">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="9bfd4-125">Ip.Read.All</span></span> |  <span data-ttu-id="9bfd4-126">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="9bfd4-126">'Read IP address profiles'</span></span>

>[!Note]
> <span data-ttu-id="9bfd4-127">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="9bfd4-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9bfd4-128">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9bfd4-128">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9bfd4-129">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9bfd4-129">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9bfd4-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9bfd4-130">HTTP request</span></span>
```
GET /api/alerts/{id}/ips
```

## <a name="request-headers"></a><span data-ttu-id="9bfd4-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9bfd4-131">Request headers</span></span>

<span data-ttu-id="9bfd4-132">Nome</span><span class="sxs-lookup"><span data-stu-id="9bfd4-132">Name</span></span> | <span data-ttu-id="9bfd4-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="9bfd4-133">Type</span></span> | <span data-ttu-id="9bfd4-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bfd4-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="9bfd4-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="9bfd4-135">Authorization</span></span> | <span data-ttu-id="9bfd4-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9bfd4-136">String</span></span> | <span data-ttu-id="9bfd4-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-137">Bearer {token}.</span></span> <span data-ttu-id="9bfd4-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-138">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9bfd4-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9bfd4-139">Request body</span></span>
<span data-ttu-id="9bfd4-140">Vazio</span><span class="sxs-lookup"><span data-stu-id="9bfd4-140">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9bfd4-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="9bfd4-141">Response</span></span>
<span data-ttu-id="9bfd4-142">Se bem-sucedido e alerta e um IP existir - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-142">If successful and alert and an IP exist - 200 OK.</span></span> <span data-ttu-id="9bfd4-143">Se o alerta não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-143">If alert not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="9bfd4-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9bfd4-144">Example</span></span>

<span data-ttu-id="9bfd4-145">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9bfd4-145">**Request**</span></span>

<span data-ttu-id="9bfd4-146">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-146">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/ips
```

<span data-ttu-id="9bfd4-147">**Response**</span><span class="sxs-lookup"><span data-stu-id="9bfd4-147">**Response**</span></span>

<span data-ttu-id="9bfd4-148">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="9bfd4-148">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Ips",    
    "value": [
                {
                    "id": "104.80.104.128"
                },
                {
                    "id": "23.203.232.228   
                }
                ...
    ]
}
 
```
