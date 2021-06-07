---
title: Coletar API do pacote de investigação
description: Use essa API para criar chamadas relacionadas à coleta de um pacote de investigação de um dispositivo.
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0083d806f3e52307e6dce30f74e255073a09c16a
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770488"
---
# <a name="collect-investigation-package-api"></a><span data-ttu-id="1acb5-104">Coletar API do pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="1acb5-104">Collect investigation package API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1acb5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1acb5-105">**Applies to:**</span></span>
- [<span data-ttu-id="1acb5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1acb5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1acb5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1acb5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="1acb5-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1acb5-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1acb5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1acb5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="1acb5-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="1acb5-110">API description</span></span>
<span data-ttu-id="1acb5-111">Coletar o pacote de investigação de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1acb5-111">Collect investigation package from a device.</span></span>


## <a name="limitations"></a><span data-ttu-id="1acb5-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="1acb5-112">Limitations</span></span>
1. <span data-ttu-id="1acb5-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="1acb5-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="1acb5-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="1acb5-114">Permissions</span></span>
<span data-ttu-id="1acb5-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="1acb5-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1acb5-116">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="1acb5-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="1acb5-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="1acb5-117">Permission type</span></span> |   <span data-ttu-id="1acb5-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="1acb5-118">Permission</span></span>  |   <span data-ttu-id="1acb5-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="1acb5-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="1acb5-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="1acb5-120">Application</span></span> |   <span data-ttu-id="1acb5-121">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="1acb5-121">Machine.CollectForensics</span></span> |  <span data-ttu-id="1acb5-122">'Coletar evidências forenses'</span><span class="sxs-lookup"><span data-stu-id="1acb5-122">'Collect forensics'</span></span>
<span data-ttu-id="1acb5-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="1acb5-123">Delegated (work or school account)</span></span> |    <span data-ttu-id="1acb5-124">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="1acb5-124">Machine.CollectForensics</span></span> |  <span data-ttu-id="1acb5-125">'Coletar evidências forenses'</span><span class="sxs-lookup"><span data-stu-id="1acb5-125">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="1acb5-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="1acb5-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="1acb5-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="1acb5-127">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="1acb5-128">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="1acb5-128">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="1acb5-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="1acb5-129">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/collectInvestigationPackage
```

## <a name="request-headers"></a><span data-ttu-id="1acb5-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="1acb5-130">Request headers</span></span>

<span data-ttu-id="1acb5-131">Nome</span><span class="sxs-lookup"><span data-stu-id="1acb5-131">Name</span></span> | <span data-ttu-id="1acb5-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="1acb5-132">Type</span></span> | <span data-ttu-id="1acb5-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="1acb5-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="1acb5-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="1acb5-134">Authorization</span></span> | <span data-ttu-id="1acb5-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1acb5-135">String</span></span> | <span data-ttu-id="1acb5-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="1acb5-136">Bearer {token}.</span></span> <span data-ttu-id="1acb5-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="1acb5-137">**Required**.</span></span>
<span data-ttu-id="1acb5-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1acb5-138">Content-Type</span></span> | <span data-ttu-id="1acb5-139">string</span><span class="sxs-lookup"><span data-stu-id="1acb5-139">string</span></span> | <span data-ttu-id="1acb5-140">application/json.</span><span class="sxs-lookup"><span data-stu-id="1acb5-140">application/json.</span></span> <span data-ttu-id="1acb5-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="1acb5-141">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="1acb5-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="1acb5-142">Request body</span></span>
<span data-ttu-id="1acb5-143">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="1acb5-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="1acb5-144">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="1acb5-144">Parameter</span></span> | <span data-ttu-id="1acb5-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="1acb5-145">Type</span></span>    | <span data-ttu-id="1acb5-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="1acb5-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="1acb5-147">Comentário</span><span class="sxs-lookup"><span data-stu-id="1acb5-147">Comment</span></span> |   <span data-ttu-id="1acb5-148">String</span><span class="sxs-lookup"><span data-stu-id="1acb5-148">String</span></span> |    <span data-ttu-id="1acb5-149">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="1acb5-149">Comment to associate with the action.</span></span> <span data-ttu-id="1acb5-150">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="1acb5-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="1acb5-151">Resposta</span><span class="sxs-lookup"><span data-stu-id="1acb5-151">Response</span></span>
<span data-ttu-id="1acb5-152">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="1acb5-152">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="1acb5-153">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1acb5-153">Example</span></span>

<span data-ttu-id="1acb5-154">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="1acb5-154">**Request**</span></span>

<span data-ttu-id="1acb5-155">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="1acb5-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/fb9ab6be3965095a09c057be7c90f0a2/collectInvestigationPackage
```

```json
{
  "Comment": "Collect forensics due to alert 1234"
}
```
