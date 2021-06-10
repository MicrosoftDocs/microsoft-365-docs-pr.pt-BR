---
title: API de entidades de alerta de Atualização em Lote
description: Saiba como atualizar alertas do Microsoft Defender para Ponto de Extremidade em um lote usando essa API. Você pode atualizar as propriedades status, determinação, classificação e assignedTo.
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
ms.technology: mde
ms.openlocfilehash: db745c1b12c64baff5bf2c0a212446ce0f773709
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166299"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="cb462-105">Alertas de atualização em lotes</span><span class="sxs-lookup"><span data-stu-id="cb462-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cb462-106">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="cb462-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="cb462-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cb462-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb462-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cb462-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="cb462-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="cb462-109">API description</span></span>
<span data-ttu-id="cb462-110">Atualiza as propriedades de um lote de [alertas existentes.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="cb462-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>
<br><span data-ttu-id="cb462-111">O envio **do comentário** está disponível com ou sem a atualização de propriedades.</span><span class="sxs-lookup"><span data-stu-id="cb462-111">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="cb462-112">As propriedades atualizáveis são: `status` `determination` , e `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="cb462-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>


## <a name="limitations"></a><span data-ttu-id="cb462-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="cb462-113">Limitations</span></span>
1. <span data-ttu-id="cb462-114">Você pode atualizar alertas que estão disponíveis na API.</span><span class="sxs-lookup"><span data-stu-id="cb462-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="cb462-115">Confira [Listar Alertas](get-alerts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="cb462-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="cb462-116">Limitações de taxa para essa API são 10 chamadas por minuto e 500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="cb462-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="cb462-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="cb462-117">Permissions</span></span>
<span data-ttu-id="cb462-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="cb462-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="cb462-119">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="cb462-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="cb462-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="cb462-120">Permission type</span></span> |   <span data-ttu-id="cb462-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="cb462-121">Permission</span></span>  |   <span data-ttu-id="cb462-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="cb462-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="cb462-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="cb462-123">Application</span></span> |   <span data-ttu-id="cb462-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="cb462-124">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="cb462-125">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="cb462-125">'Read and write all alerts'</span></span>
<span data-ttu-id="cb462-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="cb462-126">Delegated (work or school account)</span></span> | <span data-ttu-id="cb462-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="cb462-127">Alert.ReadWrite</span></span> | <span data-ttu-id="cb462-128">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="cb462-128">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="cb462-129">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="cb462-129">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="cb462-130">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="cb462-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="cb462-131">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="cb462-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="cb462-132">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="cb462-132">HTTP request</span></span>
```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="cb462-133">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="cb462-133">Request headers</span></span>

<span data-ttu-id="cb462-134">Nome</span><span class="sxs-lookup"><span data-stu-id="cb462-134">Name</span></span> | <span data-ttu-id="cb462-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb462-135">Type</span></span> | <span data-ttu-id="cb462-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb462-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="cb462-137">Autorização</span><span class="sxs-lookup"><span data-stu-id="cb462-137">Authorization</span></span> | <span data-ttu-id="cb462-138">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cb462-138">String</span></span> | <span data-ttu-id="cb462-139">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="cb462-139">Bearer {token}.</span></span> <span data-ttu-id="cb462-140">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="cb462-140">**Required**.</span></span>
<span data-ttu-id="cb462-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="cb462-141">Content-Type</span></span> | <span data-ttu-id="cb462-142">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="cb462-142">String</span></span> | <span data-ttu-id="cb462-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="cb462-143">application/json.</span></span> <span data-ttu-id="cb462-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="cb462-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="cb462-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="cb462-145">Request body</span></span>
<span data-ttu-id="cb462-146">No corpo da solicitação, fornece as IDs dos alertas a serem atualizados e os valores dos campos relevantes que você deseja atualizar para esses alertas.</span><span class="sxs-lookup"><span data-stu-id="cb462-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>
<br><span data-ttu-id="cb462-147">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="cb462-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="cb462-148">Para obter um melhor desempenho, não inclua valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="cb462-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="cb462-149">Propriedade</span><span class="sxs-lookup"><span data-stu-id="cb462-149">Property</span></span> | <span data-ttu-id="cb462-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="cb462-150">Type</span></span> | <span data-ttu-id="cb462-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb462-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="cb462-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="cb462-152">alertIds</span></span> | <span data-ttu-id="cb462-153">Cadeia de &lt; caracteres de lista&gt;</span><span class="sxs-lookup"><span data-stu-id="cb462-153">List&lt;String&gt;</span></span>| <span data-ttu-id="cb462-154">Uma lista das IDs dos alertas a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="cb462-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="cb462-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="cb462-155">**Required**</span></span>
<span data-ttu-id="cb462-156">status</span><span class="sxs-lookup"><span data-stu-id="cb462-156">status</span></span> | <span data-ttu-id="cb462-157">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cb462-157">String</span></span> | <span data-ttu-id="cb462-158">Especifica o status atualizado dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="cb462-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="cb462-159">Os valores da propriedade são: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="cb462-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="cb462-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="cb462-160">assignedTo</span></span> | <span data-ttu-id="cb462-161">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cb462-161">String</span></span> | <span data-ttu-id="cb462-162">Proprietário dos alertas especificados</span><span class="sxs-lookup"><span data-stu-id="cb462-162">Owner of the specified alerts</span></span>
<span data-ttu-id="cb462-163">classificação</span><span class="sxs-lookup"><span data-stu-id="cb462-163">classification</span></span> | <span data-ttu-id="cb462-164">String</span><span class="sxs-lookup"><span data-stu-id="cb462-164">String</span></span> | <span data-ttu-id="cb462-165">Especifica a especificação dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="cb462-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="cb462-166">Os valores da propriedade são: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="cb462-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="cb462-167">determinação</span><span class="sxs-lookup"><span data-stu-id="cb462-167">determination</span></span> | <span data-ttu-id="cb462-168">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="cb462-168">String</span></span> | <span data-ttu-id="cb462-169">Especifica a determinação dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="cb462-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="cb462-170">Os valores da propriedade são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="cb462-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="cb462-171">comment</span><span class="sxs-lookup"><span data-stu-id="cb462-171">comment</span></span> | <span data-ttu-id="cb462-172">String</span><span class="sxs-lookup"><span data-stu-id="cb462-172">String</span></span> | <span data-ttu-id="cb462-173">Comentário a ser adicionado aos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="cb462-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="cb462-174">Resposta</span><span class="sxs-lookup"><span data-stu-id="cb462-174">Response</span></span>
<span data-ttu-id="cb462-175">Se tiver êxito, este método retornará 200 OK, com um corpo de resposta vazio.</span><span class="sxs-lookup"><span data-stu-id="cb462-175">If successful, this method returns 200 OK, with an empty response body.</span></span>


## <a name="example"></a><span data-ttu-id="cb462-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cb462-176">Example</span></span>

<span data-ttu-id="cb462-177">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="cb462-177">**Request**</span></span>

<span data-ttu-id="cb462-178">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="cb462-178">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/batchUpdate
```

```json
{
    "alertIds": ["da637399794050273582_760707377", "da637399989469816469_51697947354"],
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
