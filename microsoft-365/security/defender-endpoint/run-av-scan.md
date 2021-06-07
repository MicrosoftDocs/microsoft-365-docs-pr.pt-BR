---
title: Executar API de verificação antivírus
description: Use essa API para criar chamadas relacionadas à execução de uma verificação antivírus em um dispositivo.
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
ms.openlocfilehash: 3df703fd84c87a2bd34bb2a81f8c83063e468b17
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771440"
---
# <a name="run-antivirus-scan-api"></a><span data-ttu-id="9f193-104">Executar API de verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="9f193-104">Run antivirus scan API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9f193-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9f193-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9f193-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9f193-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9f193-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9f193-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9f193-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9f193-108">API description</span></span>
<span data-ttu-id="9f193-109">Inicie Microsoft Defender Antivírus verificação em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9f193-109">Initiate Microsoft Defender Antivirus scan on a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="9f193-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="9f193-110">Limitations</span></span>
1. <span data-ttu-id="9f193-111">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="9f193-111">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a><span data-ttu-id="9f193-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="9f193-112">Permissions</span></span>
<span data-ttu-id="9f193-113">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9f193-113">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9f193-114">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9f193-114">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9f193-115">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9f193-115">Permission type</span></span> |   <span data-ttu-id="9f193-116">Permissão</span><span class="sxs-lookup"><span data-stu-id="9f193-116">Permission</span></span>  |   <span data-ttu-id="9f193-117">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9f193-117">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9f193-118">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9f193-118">Application</span></span> |   <span data-ttu-id="9f193-119">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="9f193-119">Machine.Scan</span></span> |  <span data-ttu-id="9f193-120">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="9f193-120">'Scan machine'</span></span>
<span data-ttu-id="9f193-121">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9f193-121">Delegated (work or school account)</span></span> |    <span data-ttu-id="9f193-122">Machine.Scan</span><span class="sxs-lookup"><span data-stu-id="9f193-122">Machine.Scan</span></span> |  <span data-ttu-id="9f193-123">'Scan machine'</span><span class="sxs-lookup"><span data-stu-id="9f193-123">'Scan machine'</span></span>

>[!Note]
> <span data-ttu-id="9f193-124">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="9f193-124">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9f193-125">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9f193-125">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9f193-126">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9f193-126">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9f193-127">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9f193-127">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a><span data-ttu-id="9f193-128">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9f193-128">Request headers</span></span>

<span data-ttu-id="9f193-129">Nome</span><span class="sxs-lookup"><span data-stu-id="9f193-129">Name</span></span> | <span data-ttu-id="9f193-130">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f193-130">Type</span></span> | <span data-ttu-id="9f193-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f193-131">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f193-132">Autorização</span><span class="sxs-lookup"><span data-stu-id="9f193-132">Authorization</span></span> | <span data-ttu-id="9f193-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9f193-133">String</span></span> | <span data-ttu-id="9f193-134">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9f193-134">Bearer {token}.</span></span> <span data-ttu-id="9f193-135">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9f193-135">**Required**.</span></span>
<span data-ttu-id="9f193-136">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9f193-136">Content-Type</span></span> | <span data-ttu-id="9f193-137">string</span><span class="sxs-lookup"><span data-stu-id="9f193-137">string</span></span> | <span data-ttu-id="9f193-138">application/json</span><span class="sxs-lookup"><span data-stu-id="9f193-138">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="9f193-139">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9f193-139">Request body</span></span>
<span data-ttu-id="9f193-140">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9f193-140">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="9f193-141">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="9f193-141">Parameter</span></span> | <span data-ttu-id="9f193-142">Tipo</span><span class="sxs-lookup"><span data-stu-id="9f193-142">Type</span></span>    | <span data-ttu-id="9f193-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="9f193-143">Description</span></span>
:---|:---|:---
<span data-ttu-id="9f193-144">Comentário</span><span class="sxs-lookup"><span data-stu-id="9f193-144">Comment</span></span> |   <span data-ttu-id="9f193-145">String</span><span class="sxs-lookup"><span data-stu-id="9f193-145">String</span></span> | <span data-ttu-id="9f193-146">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="9f193-146">Comment to associate with the action.</span></span> <span data-ttu-id="9f193-147">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9f193-147">**Required**.</span></span>
<span data-ttu-id="9f193-148">ScanType</span><span class="sxs-lookup"><span data-stu-id="9f193-148">ScanType</span></span>|   <span data-ttu-id="9f193-149">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9f193-149">String</span></span>  | <span data-ttu-id="9f193-150">Define o tipo da Verificação.</span><span class="sxs-lookup"><span data-stu-id="9f193-150">Defines the type of the Scan.</span></span> <span data-ttu-id="9f193-151">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9f193-151">**Required**.</span></span>

<span data-ttu-id="9f193-152">**ScanType** controla o tipo de verificação a ser feito e pode ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="9f193-152">**ScanType** controls the type of scan to perform and can be one of the following:</span></span>

- <span data-ttu-id="9f193-153">**Rápido** – Executar uma verificação rápida no dispositivo</span><span class="sxs-lookup"><span data-stu-id="9f193-153">**Quick** – Perform quick scan on the device</span></span>
- <span data-ttu-id="9f193-154">**Completo** – Execute a verificação completa no dispositivo</span><span class="sxs-lookup"><span data-stu-id="9f193-154">**Full** – Perform full scan on the device</span></span>



## <a name="response"></a><span data-ttu-id="9f193-155">Resposta</span><span class="sxs-lookup"><span data-stu-id="9f193-155">Response</span></span>
<span data-ttu-id="9f193-156">Se tiver êxito, este método retornará 201, código de resposta criado e _objeto MachineAction_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="9f193-156">If successful, this method returns 201, Created response code and _MachineAction_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="9f193-157">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9f193-157">Example</span></span>

<span data-ttu-id="9f193-158">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9f193-158">**Request**</span></span>

<span data-ttu-id="9f193-159">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9f193-159">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```

