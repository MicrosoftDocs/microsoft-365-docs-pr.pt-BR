---
title: Cancelar API de ação de máquina
description: Saiba como cancelar uma ação de máquina já lançada
keywords: apis, api gráfica,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 490ee91d5f2d2c02174be94c52fc83fd0ec0fc5e
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879650"
---
#   <a name="cancel-machine-action-api"></a><span data-ttu-id="9b5bd-104">Cancelar API de ação de máquina</span><span class="sxs-lookup"><span data-stu-id="9b5bd-104">Cancel machine action API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9b5bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9b5bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="9b5bd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9b5bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="9b5bd-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9b5bd-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b5bd-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9b5bd-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9b5bd-109">API description</span></span>

<span data-ttu-id="9b5bd-110">Cancele uma ação de máquina já lançada que ainda não está no estado final (concluída, cancelada, com falha).</span><span class="sxs-lookup"><span data-stu-id="9b5bd-110">Cancel an already launched machine action that are not yet in final state (completed, cancelled, failed).</span></span>

## <a name="limitations"></a><span data-ttu-id="9b5bd-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="9b5bd-111">Limitations</span></span>

1.  <span data-ttu-id="9b5bd-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="9b5bd-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="9b5bd-113">Permissions</span></span>

<span data-ttu-id="9b5bd-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9b5bd-115">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="9b5bd-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

|     <span data-ttu-id="9b5bd-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9b5bd-116">Permission    type</span></span>     |     <span data-ttu-id="9b5bd-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="9b5bd-117">Permission</span></span>     |    <span data-ttu-id="9b5bd-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9b5bd-118">Permission    display name</span></span>     |
|-|-|-|
|    <br><span data-ttu-id="9b5bd-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9b5bd-119">Application</span></span>    |    <br><span data-ttu-id="9b5bd-120">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="9b5bd-120">Machine.CollectForensic</span></span><br>   <span data-ttu-id="9b5bd-121">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="9b5bd-121">Machine.Isolate</span></span>   <br><span data-ttu-id="9b5bd-122">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="9b5bd-122">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="9b5bd-123">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="9b5bd-123">Machine.Scan</span></span><br>   <span data-ttu-id="9b5bd-124">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="9b5bd-124">Machine.Offboard</span></span><br>   <span data-ttu-id="9b5bd-125">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="9b5bd-125">Machine.StopAndQuarantine</span></span><br>   <span data-ttu-id="9b5bd-126">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="9b5bd-126">Machine.LiveResponse</span></span>    |    <span data-ttu-id="9b5bd-127">Coletar forenses</span><span class="sxs-lookup"><span data-stu-id="9b5bd-127">Collect   forensics</span></span>   <br><span data-ttu-id="9b5bd-128">Isolar máquina</span><span class="sxs-lookup"><span data-stu-id="9b5bd-128">Isolate   machine</span></span><br><span data-ttu-id="9b5bd-129">Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="9b5bd-129">Restrict   code execution</span></span><br>  <span data-ttu-id="9b5bd-130">Máquina de verificação</span><span class="sxs-lookup"><span data-stu-id="9b5bd-130">Scan   machine</span></span><br>  <span data-ttu-id="9b5bd-131">Máquina de offboard</span><span class="sxs-lookup"><span data-stu-id="9b5bd-131">Offboard   machine</span></span><br>   <span data-ttu-id="9b5bd-132">Parar e quarentena</span><span class="sxs-lookup"><span data-stu-id="9b5bd-132">Stop And   Quarantine</span></span><br>   <span data-ttu-id="9b5bd-133">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="9b5bd-133">Run live   response on a specific machine</span></span>    |
|    <br><span data-ttu-id="9b5bd-134">Delegada (conta de trabalho ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9b5bd-134">Delegated   (work or school account)</span></span>    |    <span data-ttu-id="9b5bd-135">Machine.CollectForensic</span><span class="sxs-lookup"><span data-stu-id="9b5bd-135">Machine.CollectForensic</span></span><br>   <span data-ttu-id="9b5bd-136">Machine.Isolate</span><span class="sxs-lookup"><span data-stu-id="9b5bd-136">Machine.Isolate</span></span>    <br><span data-ttu-id="9b5bd-137">Machine.RestrictExecution</span><span class="sxs-lookup"><span data-stu-id="9b5bd-137">Machine.RestrictExecution</span></span><br>   <span data-ttu-id="9b5bd-138">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="9b5bd-138">Machine.Scan</span></span><br>   <span data-ttu-id="9b5bd-139">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="9b5bd-139">Machine.Offboard</span></span><br>   <span data-ttu-id="9b5bd-140">Machine.StopAndQuarantineMachine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="9b5bd-140">Machine.StopAndQuarantineMachine.LiveResponse</span></span>    |    <span data-ttu-id="9b5bd-141">Coletar forenses</span><span class="sxs-lookup"><span data-stu-id="9b5bd-141">Collect   forensics</span></span><br>   <span data-ttu-id="9b5bd-142">Isolar máquina</span><span class="sxs-lookup"><span data-stu-id="9b5bd-142">Isolate   machine</span></span><br>  <span data-ttu-id="9b5bd-143">Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="9b5bd-143">Restrict   code execution</span></span><br> <span data-ttu-id="9b5bd-144">Máquina de verificação</span><span class="sxs-lookup"><span data-stu-id="9b5bd-144">Scan   machine</span></span><br><span data-ttu-id="9b5bd-145">Máquina de offboard</span><span class="sxs-lookup"><span data-stu-id="9b5bd-145">Offboard   machine</span></span><br> <span data-ttu-id="9b5bd-146">Parar e quarentena</span><span class="sxs-lookup"><span data-stu-id="9b5bd-146">Stop And   Quarantine</span></span><br> <span data-ttu-id="9b5bd-147">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="9b5bd-147">Run live   response on a specific machine</span></span>    |


## <a name="http-request"></a><span data-ttu-id="9b5bd-148">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9b5bd-148">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/machineactions/<machineactionid>/cancel  
```


## <a name="request-headers"></a><span data-ttu-id="9b5bd-149">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9b5bd-149">Request headers</span></span>

| <span data-ttu-id="9b5bd-150">Nome</span><span class="sxs-lookup"><span data-stu-id="9b5bd-150">Name</span></span>      | <span data-ttu-id="9b5bd-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="9b5bd-151">Type</span></span> | <span data-ttu-id="9b5bd-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5bd-152">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="9b5bd-153">Autorização</span><span class="sxs-lookup"><span data-stu-id="9b5bd-153">Authorization</span></span> | <span data-ttu-id="9b5bd-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9b5bd-154">String</span></span>   | <span data-ttu-id="9b5bd-p103">{token} de portador. Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-p103">Bearer {token}. Required.</span></span>   |
| <span data-ttu-id="9b5bd-157">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9b5bd-157">Content-Type</span></span>  | <span data-ttu-id="9b5bd-158">string</span><span class="sxs-lookup"><span data-stu-id="9b5bd-158">string</span></span>   | <span data-ttu-id="9b5bd-p104">application/json. Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="9b5bd-161">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9b5bd-161">Request body</span></span>

| <span data-ttu-id="9b5bd-162">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="9b5bd-162">Parameter</span></span> | <span data-ttu-id="9b5bd-163">Tipo</span><span class="sxs-lookup"><span data-stu-id="9b5bd-163">Type</span></span> | <span data-ttu-id="9b5bd-164">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5bd-164">Description</span></span>                        |
|---------------|----------|----------------------------------------|
| <span data-ttu-id="9b5bd-165">Comentário</span><span class="sxs-lookup"><span data-stu-id="9b5bd-165">Comment</span></span>       | <span data-ttu-id="9b5bd-166">String</span><span class="sxs-lookup"><span data-stu-id="9b5bd-166">String</span></span>   | <span data-ttu-id="9b5bd-167">Comentário para associar à ação de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-167">Comment to associate with the cancellation action.</span></span>  |

## <a name="response"></a><span data-ttu-id="9b5bd-168">Resposta</span><span class="sxs-lookup"><span data-stu-id="9b5bd-168">Response</span></span>

<span data-ttu-id="9b5bd-169">Se tiver êxito, este método retornará 200, código de resposta Ok com uma entidade Ação de Máquina.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-169">If successful, this method returns 200, Ok response code with a Machine Action entity.</span></span> <span data-ttu-id="9b5bd-170">Se a entidade de ação do computador com a id especificada não for encontrada - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-170">If machine action entity with the specified id was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9b5bd-171">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9b5bd-171">Example</span></span>

<span data-ttu-id="9b5bd-172">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9b5bd-172">**Request**</span></span>

<span data-ttu-id="9b5bd-173">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9b5bd-173">Here is an example of the request.</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/cancel
```


```JSON
{
    "Comment": "Machine action was canceled by automation"
}
```

## <a name="related-topic"></a><span data-ttu-id="9b5bd-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9b5bd-174">Related topic</span></span>

- [<span data-ttu-id="9b5bd-175">Obter API de ação de máquina</span><span class="sxs-lookup"><span data-stu-id="9b5bd-175">Get machine action API</span></span>](get-machineaction-object.md)