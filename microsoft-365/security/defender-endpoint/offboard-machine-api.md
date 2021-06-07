---
title: API de máquina de offboard
description: Saiba como usar uma API para offboard de um dispositivo do Microsoft Defender para Ponto de Extremidade.
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
ms.openlocfilehash: e2b1114cd091c9cd42aa8e4525416f9d73358a65
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771988"
---
# <a name="offboard-machine-api"></a><span data-ttu-id="29757-104">API de máquina de offboard</span><span class="sxs-lookup"><span data-stu-id="29757-104">Offboard machine API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="29757-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="29757-105">**Applies to:**</span></span>
- [<span data-ttu-id="29757-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="29757-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="29757-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29757-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="29757-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="29757-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="29757-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="29757-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="29757-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="29757-110">API description</span></span>
<span data-ttu-id="29757-111">Dispositivo offboard do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="29757-111">Offboard device from Defender for Endpoint.</span></span>


## <a name="limitations"></a><span data-ttu-id="29757-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="29757-112">Limitations</span></span>
 - <span data-ttu-id="29757-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="29757-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> <span data-ttu-id="29757-114">Essa API é suportada Windows 10, versão 1703 e posterior, ou Windows Server 2019 e posterior.</span><span class="sxs-lookup"><span data-stu-id="29757-114">This API is supported on Windows 10, version 1703 and later, or Windows Server 2019 and later.</span></span> <span data-ttu-id="29757-115">Essa API não tem suporte em dispositivos MacOS ou Linux.</span><span class="sxs-lookup"><span data-stu-id="29757-115">This API is not supported on MacOS or Linux devices.</span></span>

## <a name="permissions"></a><span data-ttu-id="29757-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="29757-116">Permissions</span></span>
<span data-ttu-id="29757-117">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="29757-117">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="29757-118">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="29757-118">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="29757-119">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="29757-119">Permission type</span></span> |   <span data-ttu-id="29757-120">Permissão</span><span class="sxs-lookup"><span data-stu-id="29757-120">Permission</span></span>  |   <span data-ttu-id="29757-121">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="29757-121">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="29757-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="29757-122">Application</span></span> |   <span data-ttu-id="29757-123">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="29757-123">Machine.Offboard</span></span> |  <span data-ttu-id="29757-124">'Máquina de offboard'</span><span class="sxs-lookup"><span data-stu-id="29757-124">'Offboard machine'</span></span>
<span data-ttu-id="29757-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="29757-125">Delegated (work or school account)</span></span> |    <span data-ttu-id="29757-126">Machine.Offboard</span><span class="sxs-lookup"><span data-stu-id="29757-126">Machine.Offboard</span></span> |  <span data-ttu-id="29757-127">'Máquina de offboard'</span><span class="sxs-lookup"><span data-stu-id="29757-127">'Offboard machine'</span></span>

>[!Note]
> <span data-ttu-id="29757-128">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="29757-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="29757-129">O usuário precisa de função de AD 'Administrador Global'</span><span class="sxs-lookup"><span data-stu-id="29757-129">The user needs to 'Global Admin' AD role</span></span>
>- <span data-ttu-id="29757-130">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="29757-130">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="29757-131">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="29757-131">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

## <a name="request-headers"></a><span data-ttu-id="29757-132">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="29757-132">Request headers</span></span>

<span data-ttu-id="29757-133">Nome</span><span class="sxs-lookup"><span data-stu-id="29757-133">Name</span></span> | <span data-ttu-id="29757-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="29757-134">Type</span></span> | <span data-ttu-id="29757-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="29757-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="29757-136">Autorização</span><span class="sxs-lookup"><span data-stu-id="29757-136">Authorization</span></span> | <span data-ttu-id="29757-137">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="29757-137">String</span></span> | <span data-ttu-id="29757-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="29757-138">Bearer {token}.</span></span> <span data-ttu-id="29757-139">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="29757-139">**Required**.</span></span>
<span data-ttu-id="29757-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="29757-140">Content-Type</span></span> | <span data-ttu-id="29757-141">string</span><span class="sxs-lookup"><span data-stu-id="29757-141">string</span></span> | <span data-ttu-id="29757-142">application/json.</span><span class="sxs-lookup"><span data-stu-id="29757-142">application/json.</span></span> <span data-ttu-id="29757-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="29757-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="29757-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="29757-144">Request body</span></span>
<span data-ttu-id="29757-145">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="29757-145">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="29757-146">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="29757-146">Parameter</span></span> | <span data-ttu-id="29757-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="29757-147">Type</span></span>    | <span data-ttu-id="29757-148">Descrição</span><span class="sxs-lookup"><span data-stu-id="29757-148">Description</span></span>
:---|:---|:---
<span data-ttu-id="29757-149">Comentário</span><span class="sxs-lookup"><span data-stu-id="29757-149">Comment</span></span> |   <span data-ttu-id="29757-150">String</span><span class="sxs-lookup"><span data-stu-id="29757-150">String</span></span> |    <span data-ttu-id="29757-151">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="29757-151">Comment to associate with the action.</span></span> <span data-ttu-id="29757-152">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="29757-152">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="29757-153">Resposta</span><span class="sxs-lookup"><span data-stu-id="29757-153">Response</span></span>
<span data-ttu-id="29757-154">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Ação do Computador](machineaction.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="29757-154">If successful, this method returns 201 - Created response code and [Machine Action](machineaction.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="29757-155">Exemplo</span><span class="sxs-lookup"><span data-stu-id="29757-155">Example</span></span>

<span data-ttu-id="29757-156">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="29757-156">**Request**</span></span>

<span data-ttu-id="29757-157">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="29757-157">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
