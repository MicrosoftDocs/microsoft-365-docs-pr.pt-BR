---
title: Atualizar a API da entidade do computador
description: Saiba como atualizar marcas de máquina usando essa API. Você pode atualizar as marcas e as propriedades devicevalue.
keywords: apis, api gráfica, apis com suporte, obter, alerta, informações, id
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
ms.openlocfilehash: 8f08b1fdafd653561ac2aae10a73f37b21874b59
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985538"
---
# <a name="update-machine"></a><span data-ttu-id="40680-105">Atualizar máquina</span><span class="sxs-lookup"><span data-stu-id="40680-105">Update machine</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="40680-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="40680-106">**Applies to:**</span></span>
- [<span data-ttu-id="40680-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="40680-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="40680-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="40680-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="40680-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="40680-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="40680-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="40680-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="40680-111">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="40680-111">API description</span></span>
<span data-ttu-id="40680-112">Atualiza as propriedades do [Machine existente.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="40680-112">Updates properties of existing [Machine](machine.md).</span></span>
<br><span data-ttu-id="40680-113">As propriedades atualizáveis são: ```machineTags``` e ```deviceValue``` .</span><span class="sxs-lookup"><span data-stu-id="40680-113">Updatable properties are: ```machineTags``` and ```deviceValue```.</span></span>


## <a name="limitations"></a><span data-ttu-id="40680-114">Limitações</span><span class="sxs-lookup"><span data-stu-id="40680-114">Limitations</span></span>
1. <span data-ttu-id="40680-115">Você pode atualizar os máquinas que estão disponíveis na API.</span><span class="sxs-lookup"><span data-stu-id="40680-115">You can update machines that are available in the API.</span></span> 
2. <span data-ttu-id="40680-116">A máquina de atualização apenas anexa marcas à coleção de marcas.</span><span class="sxs-lookup"><span data-stu-id="40680-116">Update machine only appends tags to the tag collection.</span></span> <span data-ttu-id="40680-117">Se as marcas existirem, elas devem ser incluídas na coleção de marcas no corpo.</span><span class="sxs-lookup"><span data-stu-id="40680-117">If tags exist, they must be included in the tags collection in the body.</span></span>
3. <span data-ttu-id="40680-118">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="40680-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="40680-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="40680-119">Permissions</span></span>
<span data-ttu-id="40680-120">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="40680-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="40680-121">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="40680-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="40680-122">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="40680-122">Permission type</span></span> |   <span data-ttu-id="40680-123">Permissão</span><span class="sxs-lookup"><span data-stu-id="40680-123">Permission</span></span>  |   <span data-ttu-id="40680-124">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="40680-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="40680-125">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="40680-125">Application</span></span> |   <span data-ttu-id="40680-126">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="40680-126">Machine.ReadWrite.All</span></span> | <span data-ttu-id="40680-127">'Ler e gravar informações do computador para todos os computador'</span><span class="sxs-lookup"><span data-stu-id="40680-127">'Read and write machine information for all machines'</span></span>
<span data-ttu-id="40680-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="40680-128">Delegated (work or school account)</span></span> | <span data-ttu-id="40680-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="40680-129">Machine.ReadWrite</span></span> | <span data-ttu-id="40680-130">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="40680-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="40680-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="40680-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="40680-132">O usuário precisa ter pelo menos a seguinte permissão de função: "Investigação de alertas".</span><span class="sxs-lookup"><span data-stu-id="40680-132">The user needs to have at least the following role permission: 'Alerts investigation'.</span></span> <span data-ttu-id="40680-133">Para obter mais informações, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="40680-133">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="40680-134">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="40680-134">The user needs to have access to the device associated with the alert, based on device group settings.</span></span> <span data-ttu-id="40680-135">Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="40680-135">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="40680-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="40680-136">HTTP request</span></span>
```
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a><span data-ttu-id="40680-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="40680-137">Request headers</span></span>

<span data-ttu-id="40680-138">Nome</span><span class="sxs-lookup"><span data-stu-id="40680-138">Name</span></span> | <span data-ttu-id="40680-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="40680-139">Type</span></span> | <span data-ttu-id="40680-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="40680-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="40680-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="40680-141">Authorization</span></span> | <span data-ttu-id="40680-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="40680-142">String</span></span> | <span data-ttu-id="40680-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="40680-143">Bearer {token}.</span></span> <span data-ttu-id="40680-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="40680-144">**Required**.</span></span>
<span data-ttu-id="40680-145">Content-Type</span><span class="sxs-lookup"><span data-stu-id="40680-145">Content-Type</span></span> | <span data-ttu-id="40680-146">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="40680-146">String</span></span> | <span data-ttu-id="40680-147">application/json.</span><span class="sxs-lookup"><span data-stu-id="40680-147">application/json.</span></span> <span data-ttu-id="40680-148">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="40680-148">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="40680-149">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="40680-149">Request body</span></span>
<span data-ttu-id="40680-150">No corpo da solicitação, fornece os valores dos campos relevantes que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="40680-150">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="40680-151">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="40680-151">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="40680-152">Para melhor desempenho, você não deve incluir valores existentes que não mudaram.</span><span class="sxs-lookup"><span data-stu-id="40680-152">For best performance, you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="40680-153">Propriedade</span><span class="sxs-lookup"><span data-stu-id="40680-153">Property</span></span> | <span data-ttu-id="40680-154">Tipo</span><span class="sxs-lookup"><span data-stu-id="40680-154">Type</span></span> | <span data-ttu-id="40680-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="40680-155">Description</span></span>
:---|:---|:---
<span data-ttu-id="40680-156">machineTags</span><span class="sxs-lookup"><span data-stu-id="40680-156">machineTags</span></span> | <span data-ttu-id="40680-157">Conjunto de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="40680-157">String collection</span></span> | <span data-ttu-id="40680-158">Conjunto de [marcas de](machine.md) máquina.</span><span class="sxs-lookup"><span data-stu-id="40680-158">Set of [machine](machine.md) tags.</span></span>
<span data-ttu-id="40680-159">deviceValue</span><span class="sxs-lookup"><span data-stu-id="40680-159">deviceValue</span></span> | <span data-ttu-id="40680-160">Núm anulado</span><span class="sxs-lookup"><span data-stu-id="40680-160">Nullable Enum</span></span> | <span data-ttu-id="40680-161">O [valor do dispositivo](tvm-assign-device-value.md).</span><span class="sxs-lookup"><span data-stu-id="40680-161">The [value of the device](tvm-assign-device-value.md).</span></span> <span data-ttu-id="40680-162">Os valores possíveis são: 'Normal', 'Baixo' e 'Alto'.</span><span class="sxs-lookup"><span data-stu-id="40680-162">Possible values are: 'Normal', 'Low' and 'High'.</span></span>

## <a name="response"></a><span data-ttu-id="40680-163">Resposta</span><span class="sxs-lookup"><span data-stu-id="40680-163">Response</span></span>
<span data-ttu-id="40680-164">Se tiver êxito, este método retornará 200 OK e a entidade [do](machine.md) computador no corpo da resposta com as propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="40680-164">If successful, this method returns 200 OK, and the [machine](machine.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="40680-165">Se a coleção de marcas de máquina no corpo não conter marcas de máquina existentes - 400 Entrada Inválida e uma mensagem informando a marca/s ausente.</span><span class="sxs-lookup"><span data-stu-id="40680-165">If machine tags collection in body doesn't contain existing machine tags - 400 Invalid Input and a message informing of the missing tag/s.</span></span>
<span data-ttu-id="40680-166">Se o computador com a ID especificada não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="40680-166">If machine with the specified ID was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="40680-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="40680-167">Example</span></span>

<span data-ttu-id="40680-168">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="40680-168">**Request**</span></span>

<span data-ttu-id="40680-169">Veja um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="40680-169">Here's an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
