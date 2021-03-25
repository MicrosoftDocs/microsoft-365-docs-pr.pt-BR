---
title: Adicionar ou remover API de marcas de máquina
description: Saiba como usar a API Adicionar ou Remover marcas de máquina para adicionar ou remover uma marca para um computador no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, marcas, marcas de máquina
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
ms.openlocfilehash: 98dd513cc66683ff1b95f66d6d7b89916ce54bab
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51199765"
---
# <a name="add-or-remove-machine-tags-api"></a><span data-ttu-id="b10bb-104">Adicionar ou remover API de marcas de máquina</span><span class="sxs-lookup"><span data-stu-id="b10bb-104">Add or Remove Machine Tags API</span></span>

<span data-ttu-id="b10bb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b10bb-105">**Applies to:**</span></span>

- [<span data-ttu-id="b10bb-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b10bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> <span data-ttu-id="b10bb-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b10bb-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b10bb-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b10bb-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="b10bb-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="b10bb-109">API description</span></span>

<span data-ttu-id="b10bb-110">Adiciona ou remove marca a um [Computador específico.](machine.md)</span><span class="sxs-lookup"><span data-stu-id="b10bb-110">Adds or remove tag to a specific [Machine](machine.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="b10bb-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="b10bb-111">Limitations</span></span>

1. <span data-ttu-id="b10bb-112">Você pode postar em máquinas vistas pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="b10bb-112">You can post on machines last seen according to your configured retention period.</span></span>

2. <span data-ttu-id="b10bb-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="b10bb-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="b10bb-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="b10bb-114">Permissions</span></span>

<span data-ttu-id="b10bb-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="b10bb-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="b10bb-116">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="b10bb-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="b10bb-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="b10bb-117">Permission type</span></span> |    <span data-ttu-id="b10bb-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="b10bb-118">Permission</span></span>    |    <span data-ttu-id="b10bb-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="b10bb-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="b10bb-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b10bb-120">Application</span></span> |    <span data-ttu-id="b10bb-121">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="b10bb-121">Machine.ReadWrite.All</span></span> |    <span data-ttu-id="b10bb-122">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="b10bb-122">'Read and write all machine information'</span></span>
<span data-ttu-id="b10bb-123">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="b10bb-123">Delegated (work or school account)</span></span> | <span data-ttu-id="b10bb-124">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="b10bb-124">Machine.ReadWrite</span></span> | <span data-ttu-id="b10bb-125">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="b10bb-125">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="b10bb-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="b10bb-126">When obtaining a token using user credentials:</span></span>
>
>- <span data-ttu-id="b10bb-127">O usuário precisa ter pelo menos a seguinte permissão de função: "Gerenciar configuração de segurança".</span><span class="sxs-lookup"><span data-stu-id="b10bb-127">The user needs to have at least the following role permission: 'Manage security setting'.</span></span> <span data-ttu-id="b10bb-128">Para obter mais (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="b10bb-128">For more  (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="b10bb-129">O usuário precisa ter acesso ao computador, com base nas configurações do grupo de máquinas (Consulte Criar e gerenciar grupos [de máquinas](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="b10bb-129">User needs to have access to the machine, based on machine group settings (See [Create and manage machine groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="b10bb-130">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="b10bb-130">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a><span data-ttu-id="b10bb-131">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="b10bb-131">Request headers</span></span>

<span data-ttu-id="b10bb-132">Nome</span><span class="sxs-lookup"><span data-stu-id="b10bb-132">Name</span></span> | <span data-ttu-id="b10bb-133">Tipo</span><span class="sxs-lookup"><span data-stu-id="b10bb-133">Type</span></span> | <span data-ttu-id="b10bb-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="b10bb-134">Description</span></span>
:---|:---|:---
<span data-ttu-id="b10bb-135">Autorização</span><span class="sxs-lookup"><span data-stu-id="b10bb-135">Authorization</span></span> | <span data-ttu-id="b10bb-136">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b10bb-136">String</span></span> | <span data-ttu-id="b10bb-137">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="b10bb-137">Bearer {token}.</span></span> <span data-ttu-id="b10bb-138">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-138">**Required**.</span></span>
<span data-ttu-id="b10bb-139">Content-Type</span><span class="sxs-lookup"><span data-stu-id="b10bb-139">Content-Type</span></span> | <span data-ttu-id="b10bb-140">string</span><span class="sxs-lookup"><span data-stu-id="b10bb-140">string</span></span> | <span data-ttu-id="b10bb-141">application/json.</span><span class="sxs-lookup"><span data-stu-id="b10bb-141">application/json.</span></span> <span data-ttu-id="b10bb-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-142">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="b10bb-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="b10bb-143">Request body</span></span>

<span data-ttu-id="b10bb-144">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="b10bb-144">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="b10bb-145">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="b10bb-145">Parameter</span></span> |    <span data-ttu-id="b10bb-146">Tipo</span><span class="sxs-lookup"><span data-stu-id="b10bb-146">Type</span></span>    | <span data-ttu-id="b10bb-147">Descrição</span><span class="sxs-lookup"><span data-stu-id="b10bb-147">Description</span></span>
:---|:---|:---
<span data-ttu-id="b10bb-148">Valor</span><span class="sxs-lookup"><span data-stu-id="b10bb-148">Value</span></span> |    <span data-ttu-id="b10bb-149">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b10bb-149">String</span></span> |    <span data-ttu-id="b10bb-150">O nome da marca.</span><span class="sxs-lookup"><span data-stu-id="b10bb-150">The tag name.</span></span> <span data-ttu-id="b10bb-151">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-151">**Required**.</span></span>
<span data-ttu-id="b10bb-152">Action</span><span class="sxs-lookup"><span data-stu-id="b10bb-152">Action</span></span>    | <span data-ttu-id="b10bb-153">Enum</span><span class="sxs-lookup"><span data-stu-id="b10bb-153">Enum</span></span> |    <span data-ttu-id="b10bb-154">Adicionar ou Remover.</span><span class="sxs-lookup"><span data-stu-id="b10bb-154">Add or Remove.</span></span> <span data-ttu-id="b10bb-155">Os valores permitidos são: 'Adicionar' ou 'Remover'.</span><span class="sxs-lookup"><span data-stu-id="b10bb-155">Allowed values are: 'Add' or 'Remove'.</span></span> <span data-ttu-id="b10bb-156">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="b10bb-156">**Required**.</span></span>


## <a name="response"></a><span data-ttu-id="b10bb-157">Resposta</span><span class="sxs-lookup"><span data-stu-id="b10bb-157">Response</span></span>

<span data-ttu-id="b10bb-158">Se tiver êxito, este método retornará 200 - Código de resposta ok e o Computador atualizado no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="b10bb-158">If successful, this method returns 200 - Ok response code and the updated Machine in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="b10bb-159">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b10bb-159">Example</span></span>

<span data-ttu-id="b10bb-160">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="b10bb-160">**Request**</span></span>

<span data-ttu-id="b10bb-161">Aqui está um exemplo de uma solicitação que adiciona a marca de máquina.</span><span class="sxs-lookup"><span data-stu-id="b10bb-161">Here is an example of a request that adds machine tag.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- <span data-ttu-id="b10bb-162">Para remover a marca do computador, desmarcar a ação como 'Remover' em vez de 'Adicionar' no corpo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="b10bb-162">To remove machine tag, set the Action to 'Remove' instead of 'Add' in the request body.</span></span>
