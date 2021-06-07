---
title: Iniciar API de Investigação
description: Use essa API para iniciar a investigação em um dispositivo.
keywords: apis, api gráfica, apis com suporte, investigação
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
ms.openlocfilehash: b7a6a3e7f6f705f322ee3eb1c1b561bc01c55d29
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770884"
---
# <a name="start-investigation-api"></a><span data-ttu-id="7cd38-104">Iniciar API de Investigação</span><span class="sxs-lookup"><span data-stu-id="7cd38-104">Start Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7cd38-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7cd38-105">**Applies to:**</span></span>
- [<span data-ttu-id="7cd38-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7cd38-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7cd38-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7cd38-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7cd38-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7cd38-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7cd38-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7cd38-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="7cd38-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="7cd38-110">API description</span></span>
<span data-ttu-id="7cd38-111">Inicie a investigação automatizada em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7cd38-111">Start automated investigation on a device.</span></span>
<br><span data-ttu-id="7cd38-112">Confira [Visão geral das investigações automatizadas](automated-investigations.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7cd38-112">See [Overview of automated investigations](automated-investigations.md) for more information.</span></span>


## <a name="limitations"></a><span data-ttu-id="7cd38-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="7cd38-113">Limitations</span></span>
1. <span data-ttu-id="7cd38-114">Limitações de taxa para essa API são 50 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="7cd38-114">Rate limitations for this API are 50 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="7cd38-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="7cd38-115">Permissions</span></span>
<span data-ttu-id="7cd38-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="7cd38-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="7cd38-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="7cd38-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="7cd38-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="7cd38-118">Permission type</span></span> |   <span data-ttu-id="7cd38-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="7cd38-119">Permission</span></span>  |   <span data-ttu-id="7cd38-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="7cd38-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="7cd38-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="7cd38-121">Application</span></span> |   <span data-ttu-id="7cd38-122">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="7cd38-122">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="7cd38-123">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="7cd38-123">'Read and write all alerts'</span></span>
<span data-ttu-id="7cd38-124">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="7cd38-124">Delegated (work or school account)</span></span> | <span data-ttu-id="7cd38-125">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="7cd38-125">Alert.ReadWrite</span></span> | <span data-ttu-id="7cd38-126">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="7cd38-126">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="7cd38-127">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="7cd38-127">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="7cd38-128">O usuário precisa ter pelo menos a seguinte permissão de função: "Ações de correção ativas" (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="7cd38-128">The user needs to have at least the following role permission: 'Active remediation actions' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="7cd38-129">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="7cd38-129">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>


## <a name="http-request"></a><span data-ttu-id="7cd38-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="7cd38-130">HTTP request</span></span>
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/startInvestigation
```

## <a name="request-headers"></a><span data-ttu-id="7cd38-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="7cd38-131">Request headers</span></span>

<span data-ttu-id="7cd38-132">Nome</span><span class="sxs-lookup"><span data-stu-id="7cd38-132">Name</span></span> | <span data-ttu-id="7cd38-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="7cd38-133">Type</span></span> | <span data-ttu-id="7cd38-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cd38-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="7cd38-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="7cd38-135">Authorization</span></span> | <span data-ttu-id="7cd38-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7cd38-136">String</span></span> | <span data-ttu-id="7cd38-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="7cd38-137">Bearer {token}.</span></span> <span data-ttu-id="7cd38-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="7cd38-138">**Required**.</span></span>
<span data-ttu-id="7cd38-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="7cd38-139">Content-Type</span></span> | <span data-ttu-id="7cd38-140">string</span><span class="sxs-lookup"><span data-stu-id="7cd38-140">string</span></span> | <span data-ttu-id="7cd38-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="7cd38-141">application/json.</span></span> <span data-ttu-id="7cd38-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="7cd38-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="7cd38-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="7cd38-143">Request body</span></span>
<span data-ttu-id="7cd38-144">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="7cd38-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="7cd38-145">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="7cd38-145">Parameter</span></span> | <span data-ttu-id="7cd38-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="7cd38-146">Type</span></span>    | <span data-ttu-id="7cd38-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cd38-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="7cd38-148">Comentário</span><span class="sxs-lookup"><span data-stu-id="7cd38-148">Comment</span></span> |   <span data-ttu-id="7cd38-149">String</span><span class="sxs-lookup"><span data-stu-id="7cd38-149">String</span></span> |    <span data-ttu-id="7cd38-150">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="7cd38-150">Comment to associate with the action.</span></span> <span data-ttu-id="7cd38-151">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="7cd38-151">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="7cd38-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="7cd38-152">Response</span></span>
<span data-ttu-id="7cd38-153">Se tiver êxito, este método retornará 201 - Código de resposta criado e [Investigação](investigation.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="7cd38-153">If successful, this method returns 201 - Created response code and [Investigation](investigation.md) in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="7cd38-154">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7cd38-154">Example</span></span>

<span data-ttu-id="7cd38-155">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="7cd38-155">**Request**</span></span>

<span data-ttu-id="7cd38-156">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="7cd38-156">Here is an example of the request.</span></span>

```https
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
