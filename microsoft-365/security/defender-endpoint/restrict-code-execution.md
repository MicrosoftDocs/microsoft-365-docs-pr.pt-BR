---
title: Restringir a API de execução de aplicativos
description: Use essa API para criar chamadas relacionadas à restrição da execução de um aplicativo.
keywords: apis, api gráfica, apis com suporte, coletar pacote de investigação
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
ms.openlocfilehash: 149f3aefd963f15eafa15030a322ec588c0615ed
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186769"
---
# <a name="restrict-app-execution-api"></a><span data-ttu-id="65620-104">Restringir a API de execução de aplicativos</span><span class="sxs-lookup"><span data-stu-id="65620-104">Restrict app execution API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65620-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65620-105">**Applies to:**</span></span>
- [<span data-ttu-id="65620-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65620-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65620-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65620-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="65620-108">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="65620-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="65620-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="65620-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="65620-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="65620-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="65620-111">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="65620-111">API description</span></span>
<span data-ttu-id="65620-112">Restringir a execução de todos os aplicativos no dispositivo, exceto um conjunto predefinido.</span><span class="sxs-lookup"><span data-stu-id="65620-112">Restrict execution of all applications on the device except a predefined set.</span></span>


## <a name="limitations"></a><span data-ttu-id="65620-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="65620-113">Limitations</span></span>
1. <span data-ttu-id="65620-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="65620-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="65620-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="65620-115">Permissions</span></span>
<span data-ttu-id="65620-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="65620-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="65620-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="65620-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="65620-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="65620-118">Permission type</span></span> |   <span data-ttu-id="65620-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="65620-119">Permission</span></span>  |   <span data-ttu-id="65620-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="65620-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="65620-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="65620-121">Application</span></span> |   <span data-ttu-id="65620-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="65620-122">Machine.RestrictExecution</span></span> | <span data-ttu-id="65620-123">'Restringir a execução de código'</span><span class="sxs-lookup"><span data-stu-id="65620-123">'Restrict code execution'</span></span>
<span data-ttu-id="65620-124">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="65620-124">Delegated (work or school account)</span></span> | <span data-ttu-id="65620-125">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="65620-125">Machine.RestrictExecution</span></span> | <span data-ttu-id="65620-126">'Restringir a execução de código'</span><span class="sxs-lookup"><span data-stu-id="65620-126">'Restrict code execution'</span></span>

>[!Note]
> <span data-ttu-id="65620-127">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="65620-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="65620-128">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="65620-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="65620-129">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="65620-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="65620-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="65620-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/restrictCodeExecution
```

## <a name="request-headers"></a><span data-ttu-id="65620-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="65620-131">Request headers</span></span>

<span data-ttu-id="65620-132">Nome</span><span class="sxs-lookup"><span data-stu-id="65620-132">Name</span></span> | <span data-ttu-id="65620-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="65620-133">Type</span></span> | <span data-ttu-id="65620-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="65620-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="65620-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="65620-135">Authorization</span></span> | <span data-ttu-id="65620-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="65620-136">String</span></span> | <span data-ttu-id="65620-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="65620-137">Bearer {token}.</span></span> <span data-ttu-id="65620-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="65620-138">**Required**.</span></span>
<span data-ttu-id="65620-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="65620-139">Content-Type</span></span> | <span data-ttu-id="65620-140">string</span><span class="sxs-lookup"><span data-stu-id="65620-140">string</span></span> | <span data-ttu-id="65620-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="65620-141">application/json.</span></span> <span data-ttu-id="65620-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="65620-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="65620-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="65620-143">Request body</span></span>
<span data-ttu-id="65620-144">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="65620-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="65620-145">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="65620-145">Parameter</span></span> | <span data-ttu-id="65620-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="65620-146">Type</span></span>    | <span data-ttu-id="65620-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="65620-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="65620-148">Comentário</span><span class="sxs-lookup"><span data-stu-id="65620-148">Comment</span></span> |   <span data-ttu-id="65620-149">String</span><span class="sxs-lookup"><span data-stu-id="65620-149">String</span></span> |    <span data-ttu-id="65620-150">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="65620-150">Comment to associate with the action.</span></span> <span data-ttu-id="65620-151">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="65620-151">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="65620-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="65620-152">Response</span></span>
<span data-ttu-id="65620-153">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="65620-153">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="65620-154">Exemplo</span><span class="sxs-lookup"><span data-stu-id="65620-154">Example</span></span>

<span data-ttu-id="65620-155">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="65620-155">**Request**</span></span>

<span data-ttu-id="65620-156">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="65620-156">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/restrictCodeExecution 
```

```json
{
  "Comment": "Restrict code execution due to alert 1234"
}

```

- <span data-ttu-id="65620-157">Para remover a restrição de execução de código de um dispositivo, consulte [Remove app restriction](unrestrict-code-execution.md).</span><span class="sxs-lookup"><span data-stu-id="65620-157">To remove code execution restriction from a device, see [Remove app restriction](unrestrict-code-execution.md).</span></span>
