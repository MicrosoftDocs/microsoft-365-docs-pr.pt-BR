---
title: API de arquivo de parada e quarentena
description: Saiba como parar de executar um arquivo em um dispositivo e excluir o arquivo no Microsoft Defender para Ponto de Extremidade. Veja um exemplo.
keywords: apis, api gráfica, apis com suporte, arquivo de parada e quarentena
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
ms.openlocfilehash: 670282f0f87092437bb1f3c6bf7be908e4649042
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199724"
---
# <a name="stop-and-quarantine-file-api"></a><span data-ttu-id="5c482-105">API de arquivo de parada e quarentena</span><span class="sxs-lookup"><span data-stu-id="5c482-105">Stop and quarantine file API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c482-106">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="5c482-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="5c482-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5c482-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5c482-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5c482-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5c482-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="5c482-109">API description</span></span>
<span data-ttu-id="5c482-110">Pare a execução de um arquivo em um dispositivo e exclua-o.</span><span class="sxs-lookup"><span data-stu-id="5c482-110">Stop execution of a file on a device and delete it.</span></span>


## <a name="limitations"></a><span data-ttu-id="5c482-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="5c482-111">Limitations</span></span>
1. <span data-ttu-id="5c482-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="5c482-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="5c482-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="5c482-113">Permissions</span></span>
<span data-ttu-id="5c482-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="5c482-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c482-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5c482-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5c482-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="5c482-116">Permission type</span></span> |   <span data-ttu-id="5c482-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="5c482-117">Permission</span></span>  |   <span data-ttu-id="5c482-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="5c482-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5c482-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5c482-119">Application</span></span> |   <span data-ttu-id="5c482-120">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="5c482-120">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="5c482-121">'Parar e Quarentena'</span><span class="sxs-lookup"><span data-stu-id="5c482-121">'Stop And Quarantine'</span></span>
<span data-ttu-id="5c482-122">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5c482-122">Delegated (work or school account)</span></span> | <span data-ttu-id="5c482-123">Machine.StopAndQuarantine</span><span class="sxs-lookup"><span data-stu-id="5c482-123">Machine.StopAndQuarantine</span></span> | <span data-ttu-id="5c482-124">'Parar e Quarentena'</span><span class="sxs-lookup"><span data-stu-id="5c482-124">'Stop And Quarantine'</span></span>

>[!Note]
> <span data-ttu-id="5c482-125">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="5c482-125">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5c482-126">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="5c482-126">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5c482-127">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="5c482-127">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5c482-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5c482-128">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/StopAndQuarantineFile
```

## <a name="request-headers"></a><span data-ttu-id="5c482-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="5c482-129">Request headers</span></span>

<span data-ttu-id="5c482-130">Nome</span><span class="sxs-lookup"><span data-stu-id="5c482-130">Name</span></span> | <span data-ttu-id="5c482-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c482-131">Type</span></span> | <span data-ttu-id="5c482-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c482-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c482-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="5c482-133">Authorization</span></span> | <span data-ttu-id="5c482-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5c482-134">String</span></span> | <span data-ttu-id="5c482-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5c482-135">Bearer {token}.</span></span> <span data-ttu-id="5c482-136">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c482-136">**Required**.</span></span>
<span data-ttu-id="5c482-137">Content-Type</span><span class="sxs-lookup"><span data-stu-id="5c482-137">Content-Type</span></span> | <span data-ttu-id="5c482-138">string</span><span class="sxs-lookup"><span data-stu-id="5c482-138">string</span></span> | <span data-ttu-id="5c482-139">application/json.</span><span class="sxs-lookup"><span data-stu-id="5c482-139">application/json.</span></span> <span data-ttu-id="5c482-140">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c482-140">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5c482-141">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5c482-141">Request body</span></span>
<span data-ttu-id="5c482-142">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="5c482-142">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="5c482-143">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="5c482-143">Parameter</span></span> | <span data-ttu-id="5c482-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c482-144">Type</span></span>    | <span data-ttu-id="5c482-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c482-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c482-146">Comentário</span><span class="sxs-lookup"><span data-stu-id="5c482-146">Comment</span></span> |   <span data-ttu-id="5c482-147">String</span><span class="sxs-lookup"><span data-stu-id="5c482-147">String</span></span> |    <span data-ttu-id="5c482-148">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="5c482-148">Comment to associate with the action.</span></span> <span data-ttu-id="5c482-149">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c482-149">**Required**.</span></span>
<span data-ttu-id="5c482-150">Sha1</span><span class="sxs-lookup"><span data-stu-id="5c482-150">Sha1</span></span> |  <span data-ttu-id="5c482-151">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5c482-151">String</span></span>   | <span data-ttu-id="5c482-152">Sha1 do arquivo para parar e colocar em quarentena no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5c482-152">Sha1 of the file to stop and quarantine on the device.</span></span> <span data-ttu-id="5c482-153">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c482-153">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="5c482-154">Resposta</span><span class="sxs-lookup"><span data-stu-id="5c482-154">Response</span></span>
<span data-ttu-id="5c482-155">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="5c482-155">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="5c482-156">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5c482-156">Example</span></span>

<span data-ttu-id="5c482-157">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5c482-157">**Request**</span></span>

<span data-ttu-id="5c482-158">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5c482-158">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/StopAndQuarantineFile 
```

```json
{
  "Comment": "Stop and quarantine file on machine due to alert 441688558380765161_2136280442",
  "Sha1": "87662bc3d60e4200ceaf7aae249d1c343f4b83c9"
}

```
