---
title: Isolar a API do computador
description: Saiba como usar a API isolar máquina para isolar um dispositivo de acessar rede externa no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, isolar dispositivo
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
ms.technology: mde
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187824"
---
# <a name="isolate-machine-api"></a><span data-ttu-id="de043-104">Isolar a API do computador</span><span class="sxs-lookup"><span data-stu-id="de043-104">Isolate machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="de043-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="de043-105">**Applies to:**</span></span>
- [<span data-ttu-id="de043-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="de043-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="de043-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de043-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="de043-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="de043-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="de043-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="de043-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="de043-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="de043-110">API description</span></span>
<span data-ttu-id="de043-111">Isola um dispositivo de acessar a rede externa.</span><span class="sxs-lookup"><span data-stu-id="de043-111">Isolates a device from accessing external network.</span></span>


## <a name="limitations"></a><span data-ttu-id="de043-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="de043-112">Limitations</span></span>
1. <span data-ttu-id="de043-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="de043-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="de043-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="de043-114">Permissions</span></span>
<span data-ttu-id="de043-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="de043-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="de043-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="de043-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="de043-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="de043-117">Permission type</span></span> |   <span data-ttu-id="de043-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="de043-118">Permission</span></span>  |   <span data-ttu-id="de043-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="de043-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="de043-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="de043-120">Application</span></span> |   <span data-ttu-id="de043-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="de043-121">Machine.Isolate</span></span> |   <span data-ttu-id="de043-122">'Isolar máquina'</span><span class="sxs-lookup"><span data-stu-id="de043-122">'Isolate machine'</span></span>
<span data-ttu-id="de043-123">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="de043-123">Delegated (work or school account)</span></span> | <span data-ttu-id="de043-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="de043-124">Machine.Isolate</span></span> |  <span data-ttu-id="de043-125">'Isolar máquina'</span><span class="sxs-lookup"><span data-stu-id="de043-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="de043-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="de043-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="de043-127">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="de043-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="de043-128">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="de043-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="de043-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="de043-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a><span data-ttu-id="de043-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="de043-130">Request headers</span></span>

<span data-ttu-id="de043-131">Nome</span><span class="sxs-lookup"><span data-stu-id="de043-131">Name</span></span> | <span data-ttu-id="de043-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="de043-132">Type</span></span> | <span data-ttu-id="de043-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="de043-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="de043-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="de043-134">Authorization</span></span> | <span data-ttu-id="de043-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de043-135">String</span></span> | <span data-ttu-id="de043-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="de043-136">Bearer {token}.</span></span> <span data-ttu-id="de043-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="de043-137">**Required**.</span></span>
<span data-ttu-id="de043-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="de043-138">Content-Type</span></span> | <span data-ttu-id="de043-139">string</span><span class="sxs-lookup"><span data-stu-id="de043-139">string</span></span> | <span data-ttu-id="de043-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="de043-140">application/json.</span></span> <span data-ttu-id="de043-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="de043-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="de043-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="de043-142">Request body</span></span>
<span data-ttu-id="de043-143">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="de043-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="de043-144">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="de043-144">Parameter</span></span> | <span data-ttu-id="de043-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="de043-145">Type</span></span>    | <span data-ttu-id="de043-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="de043-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="de043-147">Comentário</span><span class="sxs-lookup"><span data-stu-id="de043-147">Comment</span></span> |   <span data-ttu-id="de043-148">String</span><span class="sxs-lookup"><span data-stu-id="de043-148">String</span></span> |    <span data-ttu-id="de043-149">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="de043-149">Comment to associate with the action.</span></span> <span data-ttu-id="de043-150">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="de043-150">**Required**.</span></span>
<span data-ttu-id="de043-151">IsolationType</span><span class="sxs-lookup"><span data-stu-id="de043-151">IsolationType</span></span>   | <span data-ttu-id="de043-152">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de043-152">String</span></span> |  <span data-ttu-id="de043-153">Tipo de isolamento.</span><span class="sxs-lookup"><span data-stu-id="de043-153">Type of the isolation.</span></span> <span data-ttu-id="de043-154">Os valores permitidos são: 'Completo' ou 'Seletivo'.</span><span class="sxs-lookup"><span data-stu-id="de043-154">Allowed values are: 'Full' or 'Selective'.</span></span>

<span data-ttu-id="de043-155">**IsolationType** controla o tipo de isolamento a ser feito e pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="de043-155">**IsolationType** controls the type of isolation to perform and can be one of the following:</span></span>
- <span data-ttu-id="de043-156">Full – Isolamento total</span><span class="sxs-lookup"><span data-stu-id="de043-156">Full – Full isolation</span></span>
- <span data-ttu-id="de043-157">Seletiva – Restringir apenas o conjunto limitado de aplicativos de acessar a rede (consulte Isolar dispositivos [da rede](respond-machine-alerts.md#isolate-devices-from-the-network) para obter mais detalhes)</span><span class="sxs-lookup"><span data-stu-id="de043-157">Selective – Restrict only limited set of applications from accessing the network (see [Isolate devices from the network](respond-machine-alerts.md#isolate-devices-from-the-network) for more details)</span></span>


## <a name="response"></a><span data-ttu-id="de043-158">Resposta</span><span class="sxs-lookup"><span data-stu-id="de043-158">Response</span></span>
<span data-ttu-id="de043-159">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="de043-159">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="de043-160">Exemplo</span><span class="sxs-lookup"><span data-stu-id="de043-160">Example</span></span>

<span data-ttu-id="de043-161">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="de043-161">**Request**</span></span>

<span data-ttu-id="de043-162">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="de043-162">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- <span data-ttu-id="de043-163">Para liberar um dispositivo de isolamento, consulte [Release device from isolation](unisolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="de043-163">To release a device from isolation, see [Release device from isolation](unisolate-machine.md).</span></span>
