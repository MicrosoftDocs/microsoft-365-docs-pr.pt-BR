---
title: Definir API de valor do dispositivo
description: Saiba como especificar o valor de um dispositivo usando uma API do Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, marcas, marcas de máquina
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498314"
---
# <a name="set-device-value-api"></a><span data-ttu-id="281c1-104">Definir API de valor do dispositivo</span><span class="sxs-lookup"><span data-stu-id="281c1-104">Set device value API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="281c1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="281c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="281c1-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="281c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="281c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="281c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="281c1-108">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="281c1-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="281c1-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="281c1-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="281c1-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="281c1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="281c1-111">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="281c1-111">API description</span></span>

<span data-ttu-id="281c1-112">De definir o valor do dispositivo de um [Computador específico.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="281c1-112">Set the device value of a specific [Machine](machine.md).</span></span><br>
<span data-ttu-id="281c1-113">Confira [atribuir valores de dispositivo](tvm-assign-device-value.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="281c1-113">See [assign device values](tvm-assign-device-value.md) for more information.</span></span>

## <a name="limitations"></a><span data-ttu-id="281c1-114">Limitações</span><span class="sxs-lookup"><span data-stu-id="281c1-114">Limitations</span></span>

1. <span data-ttu-id="281c1-115">Você pode postar em dispositivos vistos pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="281c1-115">You can post on devices last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="281c1-116">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="281c1-116">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="281c1-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="281c1-117">Permissions</span></span>

<span data-ttu-id="281c1-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="281c1-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="281c1-119">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="281c1-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="281c1-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="281c1-120">Permission type</span></span> |    <span data-ttu-id="281c1-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="281c1-121">Permission</span></span>    |    <span data-ttu-id="281c1-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="281c1-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="281c1-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="281c1-123">Application</span></span> |    <span data-ttu-id="281c1-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="281c1-124">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="281c1-125">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="281c1-125">'Read and write all machine information'</span></span>
<span data-ttu-id="281c1-126">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="281c1-126">Delegated (work or school account)</span></span> | <span data-ttu-id="281c1-127">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="281c1-127">Machine.ReadWrite</span></span> | <span data-ttu-id="281c1-128">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="281c1-128">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="281c1-129">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="281c1-129">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="281c1-130">O usuário precisa ter pelo menos a seguinte permissão de função: "Gerenciar configuração de segurança".</span><span class="sxs-lookup"><span data-stu-id="281c1-130">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="281c1-131">Para obter mais (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="281c1-131">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="281c1-132">O usuário precisa ter acesso ao computador, com base nas configurações do grupo de máquinas (Consulte Criar e gerenciar grupos [de máquinas](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="281c1-132">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="281c1-133">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="281c1-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a><span data-ttu-id="281c1-134">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="281c1-134">Request headers</span></span>

<span data-ttu-id="281c1-135">Nome</span><span class="sxs-lookup"><span data-stu-id="281c1-135">Name</span></span> | <span data-ttu-id="281c1-136">Tipo</span><span class="sxs-lookup"><span data-stu-id="281c1-136">Type</span></span> | <span data-ttu-id="281c1-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="281c1-137">Description</span></span>
:---|:---|:---
<span data-ttu-id="281c1-138">Autorização</span><span class="sxs-lookup"><span data-stu-id="281c1-138">Authorization</span></span> | <span data-ttu-id="281c1-139">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="281c1-139">String</span></span> | <span data-ttu-id="281c1-140">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="281c1-140">Bearer {token}.</span></span> <span data-ttu-id="281c1-141">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="281c1-141">**Required**.</span></span>
<span data-ttu-id="281c1-142">Content-Type</span><span class="sxs-lookup"><span data-stu-id="281c1-142">Content-Type</span></span> | <span data-ttu-id="281c1-143">string</span><span class="sxs-lookup"><span data-stu-id="281c1-143">string</span></span> | <span data-ttu-id="281c1-144">application/json.</span><span class="sxs-lookup"><span data-stu-id="281c1-144">application/json.</span></span> <span data-ttu-id="281c1-145">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="281c1-145">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="281c1-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="281c1-146">Request body</span></span>

<span data-ttu-id="281c1-147">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="281c1-147">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="281c1-148">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="281c1-148">Parameter</span></span> |    <span data-ttu-id="281c1-149">Tipo</span><span class="sxs-lookup"><span data-stu-id="281c1-149">Type</span></span>    | <span data-ttu-id="281c1-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="281c1-150">Description</span></span>
:---|:---|:---
<span data-ttu-id="281c1-151">DeviceValue</span><span class="sxs-lookup"><span data-stu-id="281c1-151">DeviceValue</span></span> |    <span data-ttu-id="281c1-152">Enum</span><span class="sxs-lookup"><span data-stu-id="281c1-152">Enum</span></span> |    <span data-ttu-id="281c1-153">Valor do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="281c1-153">Device value.</span></span> <span data-ttu-id="281c1-154">Os valores permitidos são: 'Normal', 'Baixo' e 'Alto'.</span><span class="sxs-lookup"><span data-stu-id="281c1-154">Allowed values are: 'Normal', 'Low' and 'High'.</span></span> <span data-ttu-id="281c1-155">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="281c1-155">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="281c1-156">Resposta</span><span class="sxs-lookup"><span data-stu-id="281c1-156">Response</span></span>

<span data-ttu-id="281c1-157">Se tiver êxito, este método retornará 200 - Código de resposta ok e o Computador atualizado no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="281c1-157">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="281c1-158">Exemplo</span><span class="sxs-lookup"><span data-stu-id="281c1-158">Example</span></span>

<span data-ttu-id="281c1-159">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="281c1-159">**Request**</span></span>

<span data-ttu-id="281c1-160">Aqui está um exemplo de uma solicitação que adiciona a marca de máquina.</span><span class="sxs-lookup"><span data-stu-id="281c1-160">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
