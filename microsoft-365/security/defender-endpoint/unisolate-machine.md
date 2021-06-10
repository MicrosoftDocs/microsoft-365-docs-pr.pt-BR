---
title: Liberar dispositivo da API de isolamento
description: Use essa API para criar chamadas relacionadas a liberar um dispositivo de isolamento.
keywords: apis, api gráfica, apis com suporte, remover dispositivo do isolamento
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
ms.openlocfilehash: 3ed2e7968464320e41e47ad734026bdd9b323ceb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771268"
---
# <a name="release-device-from-isolation-api"></a><span data-ttu-id="68802-104">Liberar dispositivo da API de isolamento</span><span class="sxs-lookup"><span data-stu-id="68802-104">Release device from isolation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68802-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="68802-105">**Applies to:**</span></span> 
- [<span data-ttu-id="68802-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="68802-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="68802-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68802-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="68802-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="68802-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="68802-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="68802-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="68802-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="68802-110">API description</span></span>
<span data-ttu-id="68802-111">Desfazer o isolamento de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="68802-111">Undo isolation of a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="68802-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="68802-112">Limitations</span></span>
1. <span data-ttu-id="68802-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="68802-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="68802-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="68802-114">Permissions</span></span>
<span data-ttu-id="68802-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="68802-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="68802-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="68802-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="68802-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="68802-117">Permission type</span></span> |   <span data-ttu-id="68802-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="68802-118">Permission</span></span>  |   <span data-ttu-id="68802-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="68802-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="68802-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="68802-120">Application</span></span> |   <span data-ttu-id="68802-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="68802-121">Machine.Isolate</span></span> |   <span data-ttu-id="68802-122">'Isolar máquina'</span><span class="sxs-lookup"><span data-stu-id="68802-122">'Isolate machine'</span></span>
<span data-ttu-id="68802-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="68802-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="68802-124">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="68802-124">Machine.Isolate</span></span> |   <span data-ttu-id="68802-125">'Isolar máquina'</span><span class="sxs-lookup"><span data-stu-id="68802-125">'Isolate machine'</span></span>

>[!Note]
> <span data-ttu-id="68802-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="68802-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="68802-127">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="68802-127">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="68802-128">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="68802-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="68802-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="68802-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
```

## <a name="request-headers"></a><span data-ttu-id="68802-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="68802-130">Request headers</span></span>

<span data-ttu-id="68802-131">Nome</span><span class="sxs-lookup"><span data-stu-id="68802-131">Name</span></span> | <span data-ttu-id="68802-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="68802-132">Type</span></span> | <span data-ttu-id="68802-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="68802-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="68802-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="68802-134">Authorization</span></span> | <span data-ttu-id="68802-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="68802-135">String</span></span> | <span data-ttu-id="68802-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="68802-136">Bearer {token}.</span></span> <span data-ttu-id="68802-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="68802-137">**Required**.</span></span>
<span data-ttu-id="68802-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="68802-138">Content-Type</span></span> | <span data-ttu-id="68802-139">string</span><span class="sxs-lookup"><span data-stu-id="68802-139">string</span></span> | <span data-ttu-id="68802-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="68802-140">application/json.</span></span> <span data-ttu-id="68802-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="68802-141">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="68802-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="68802-142">Request body</span></span>
<span data-ttu-id="68802-143">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="68802-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="68802-144">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="68802-144">Parameter</span></span> | <span data-ttu-id="68802-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="68802-145">Type</span></span>    | <span data-ttu-id="68802-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="68802-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="68802-147">Comentário</span><span class="sxs-lookup"><span data-stu-id="68802-147">Comment</span></span> |   <span data-ttu-id="68802-148">String</span><span class="sxs-lookup"><span data-stu-id="68802-148">String</span></span> |    <span data-ttu-id="68802-149">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="68802-149">Comment to associate with the action.</span></span> <span data-ttu-id="68802-150">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="68802-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="68802-151">Resposta</span><span class="sxs-lookup"><span data-stu-id="68802-151">Response</span></span>
<span data-ttu-id="68802-152">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="68802-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="68802-153">Exemplo</span><span class="sxs-lookup"><span data-stu-id="68802-153">Example</span></span>

<span data-ttu-id="68802-154">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="68802-154">**Request**</span></span>

<span data-ttu-id="68802-155">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="68802-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}

```


- <span data-ttu-id="68802-156">Para isolar um dispositivo, consulte [Isolar dispositivo](isolate-machine.md).</span><span class="sxs-lookup"><span data-stu-id="68802-156">To isolate a device, see [Isolate device](isolate-machine.md).</span></span>

