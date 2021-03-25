---
title: Encontrar dispositivos por API de marca
description: Encontre todos os dispositivos que contenham a marca specifc
keywords: apis, apis com suporte, obter, dispositivo, encontrar, encontrar dispositivo, por marca, marca
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: 6460860828acd5ea0c3509e9eb06061d2a9a0cc2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200144"
---
# <a name="find-devices-by-tag-api"></a><span data-ttu-id="31858-104">Encontrar dispositivos por API de marca</span><span class="sxs-lookup"><span data-stu-id="31858-104">Find devices by tag API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="31858-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="31858-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="31858-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="31858-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31858-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="31858-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="31858-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="31858-108">API description</span></span>
<span data-ttu-id="31858-109">Encontre [máquinas](machine.md) por [marca](machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="31858-109">Find [Machines](machine.md) by [Tag](machine-tags.md).</span></span>
<br><span data-ttu-id="31858-110">```startswith``` a consulta é suportada.</span><span class="sxs-lookup"><span data-stu-id="31858-110">```startswith``` query is supported.</span></span> 

## <a name="limitations"></a><span data-ttu-id="31858-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="31858-111">Limitations</span></span>
1. <span data-ttu-id="31858-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="31858-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="31858-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="31858-113">Permissions</span></span>
<span data-ttu-id="31858-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="31858-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="31858-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="31858-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="31858-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="31858-116">Permission type</span></span> |   <span data-ttu-id="31858-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="31858-117">Permission</span></span>  |   <span data-ttu-id="31858-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="31858-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="31858-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="31858-119">Application</span></span> |   <span data-ttu-id="31858-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="31858-120">Machine.Read.All</span></span> |  <span data-ttu-id="31858-121">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="31858-121">'Read all machine profiles'</span></span>
<span data-ttu-id="31858-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="31858-122">Application</span></span> |   <span data-ttu-id="31858-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="31858-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="31858-124">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="31858-124">'Read and write all machine information'</span></span>
<span data-ttu-id="31858-125">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="31858-125">Delegated (work or school account)</span></span> | <span data-ttu-id="31858-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="31858-126">Machine.Read</span></span> | <span data-ttu-id="31858-127">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="31858-127">'Read machine information'</span></span>
<span data-ttu-id="31858-128">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="31858-128">Delegated (work or school account)</span></span> | <span data-ttu-id="31858-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="31858-129">Machine.ReadWrite</span></span> | <span data-ttu-id="31858-130">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="31858-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="31858-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="31858-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="31858-132">A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="31858-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="31858-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="31858-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="31858-134">A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="31858-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="31858-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="31858-135">HTTP request</span></span>
```
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a><span data-ttu-id="31858-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="31858-136">Request headers</span></span>

<span data-ttu-id="31858-137">Nome</span><span class="sxs-lookup"><span data-stu-id="31858-137">Name</span></span> | <span data-ttu-id="31858-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="31858-138">Type</span></span> | <span data-ttu-id="31858-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="31858-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="31858-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="31858-140">Authorization</span></span> | <span data-ttu-id="31858-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="31858-141">String</span></span> | <span data-ttu-id="31858-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="31858-142">Bearer {token}.</span></span> <span data-ttu-id="31858-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="31858-143">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="31858-144">Solicitar parâmetros URI</span><span class="sxs-lookup"><span data-stu-id="31858-144">Request URI parameters</span></span>

<span data-ttu-id="31858-145">Nome</span><span class="sxs-lookup"><span data-stu-id="31858-145">Name</span></span> | <span data-ttu-id="31858-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="31858-146">Type</span></span> | <span data-ttu-id="31858-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="31858-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="31858-148">tag</span><span class="sxs-lookup"><span data-stu-id="31858-148">tag</span></span> | <span data-ttu-id="31858-149">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="31858-149">String</span></span> | <span data-ttu-id="31858-150">O nome da marca.</span><span class="sxs-lookup"><span data-stu-id="31858-150">The tag name.</span></span> <span data-ttu-id="31858-151">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="31858-151">**Required**.</span></span>
<span data-ttu-id="31858-152">useStartsWithFilter</span><span class="sxs-lookup"><span data-stu-id="31858-152">useStartsWithFilter</span></span> | <span data-ttu-id="31858-153">Booleano</span><span class="sxs-lookup"><span data-stu-id="31858-153">Boolean</span></span> | <span data-ttu-id="31858-154">Quando definida como true, a pesquisa encontrará todos os dispositivos com o nome da marca que começa com a marca determinada na consulta.</span><span class="sxs-lookup"><span data-stu-id="31858-154">When set to true, the search will find all devices with tag name that starts with the given tag in the query.</span></span> <span data-ttu-id="31858-155">O padão é falso.</span><span class="sxs-lookup"><span data-stu-id="31858-155">Defaults to false.</span></span> <span data-ttu-id="31858-156">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="31858-156">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="31858-157">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="31858-157">Request body</span></span>
<span data-ttu-id="31858-158">Vazio</span><span class="sxs-lookup"><span data-stu-id="31858-158">Empty</span></span>

## <a name="response"></a><span data-ttu-id="31858-159">Resposta</span><span class="sxs-lookup"><span data-stu-id="31858-159">Response</span></span>
<span data-ttu-id="31858-160">Se bem-sucedido - 200 OK com a lista dos máquinas no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="31858-160">If successful - 200 OK with list of the machines in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="31858-161">Exemplo</span><span class="sxs-lookup"><span data-stu-id="31858-161">Example</span></span>

<span data-ttu-id="31858-162">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="31858-162">**Request**</span></span>

<span data-ttu-id="31858-163">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="31858-163">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```