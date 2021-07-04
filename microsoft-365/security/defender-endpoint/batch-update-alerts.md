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
ms.openlocfilehash: 80f88b31c1e07d1f40f3f58a1bd21b4a5c58c60b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290202"
---
# <a name="batch-update-alerts"></a><span data-ttu-id="f4896-105">Alertas de atualização em lotes</span><span class="sxs-lookup"><span data-stu-id="f4896-105">Batch update alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f4896-106">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f4896-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>

- <span data-ttu-id="f4896-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f4896-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4896-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f4896-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="f4896-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="f4896-109">API description</span></span>

<span data-ttu-id="f4896-110">Atualiza as propriedades de um lote de [alertas existentes.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f4896-110">Updates properties of a batch of existing [Alerts](alerts.md).</span></span>

<span data-ttu-id="f4896-111">O envio **do comentário** está disponível com ou sem a atualização de propriedades.</span><span class="sxs-lookup"><span data-stu-id="f4896-111">Submission of **comment** is available with or without updating properties.</span></span>

<span data-ttu-id="f4896-112">As propriedades atualizáveis são: `status` `determination` , e `classification` `assignedTo` .</span><span class="sxs-lookup"><span data-stu-id="f4896-112">Updatable properties are: `status`, `determination`, `classification` and `assignedTo`.</span></span>

## <a name="limitations"></a><span data-ttu-id="f4896-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="f4896-113">Limitations</span></span>

1. <span data-ttu-id="f4896-114">Você pode atualizar alertas que estão disponíveis na API.</span><span class="sxs-lookup"><span data-stu-id="f4896-114">You can update alerts that are available in the API.</span></span> <span data-ttu-id="f4896-115">Confira [Listar Alertas](get-alerts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f4896-115">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="f4896-116">Limitações de taxa para essa API são 10 chamadas por minuto e 500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="f4896-116">Rate limitations for this API are 10 calls per minute and 500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="f4896-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="f4896-117">Permissions</span></span>

<span data-ttu-id="f4896-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="f4896-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="f4896-119">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="f4896-119">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="f4896-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="f4896-120">Permission type</span></span> | <span data-ttu-id="f4896-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="f4896-121">Permission</span></span> | <span data-ttu-id="f4896-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="f4896-122">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="f4896-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="f4896-123">Application</span></span> | <span data-ttu-id="f4896-124">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="f4896-124">Alerts.ReadWrite.All</span></span> | <span data-ttu-id="f4896-125">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="f4896-125">'Read and write all alerts'</span></span>
<span data-ttu-id="f4896-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="f4896-126">Delegated (work or school account)</span></span> | <span data-ttu-id="f4896-127">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="f4896-127">Alert.ReadWrite</span></span> | <span data-ttu-id="f4896-128">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="f4896-128">'Read and write alerts'</span></span>

> [!NOTE]
> <span data-ttu-id="f4896-129">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="f4896-129">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="f4896-130">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="f4896-130">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="f4896-131">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="f4896-131">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="f4896-132">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="f4896-132">HTTP request</span></span>

```http
POST /api/alerts/batchUpdate
```

## <a name="request-headers"></a><span data-ttu-id="f4896-133">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="f4896-133">Request headers</span></span>

<span data-ttu-id="f4896-134">Nome</span><span class="sxs-lookup"><span data-stu-id="f4896-134">Name</span></span> | <span data-ttu-id="f4896-135">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4896-135">Type</span></span> | <span data-ttu-id="f4896-136">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4896-136">Description</span></span>
:---|:---|:---
<span data-ttu-id="f4896-137">Autorização</span><span class="sxs-lookup"><span data-stu-id="f4896-137">Authorization</span></span> | <span data-ttu-id="f4896-138">String</span><span class="sxs-lookup"><span data-stu-id="f4896-138">String</span></span> | <span data-ttu-id="f4896-139">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="f4896-139">Bearer {token}.</span></span> <span data-ttu-id="f4896-140">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="f4896-140">**Required**.</span></span>
<span data-ttu-id="f4896-141">Content-Type</span><span class="sxs-lookup"><span data-stu-id="f4896-141">Content-Type</span></span> | <span data-ttu-id="f4896-142">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="f4896-142">String</span></span> | <span data-ttu-id="f4896-143">application/json.</span><span class="sxs-lookup"><span data-stu-id="f4896-143">application/json.</span></span> <span data-ttu-id="f4896-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="f4896-144">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="f4896-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="f4896-145">Request body</span></span>

<span data-ttu-id="f4896-146">No corpo da solicitação, fornece as IDs dos alertas a serem atualizados e os valores dos campos relevantes que você deseja atualizar para esses alertas.</span><span class="sxs-lookup"><span data-stu-id="f4896-146">In the request body, supply the IDs of the alerts to be updated and the values of the relevant fields that you wish to update for these alerts.</span></span>

<span data-ttu-id="f4896-147">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="f4896-147">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span>

<span data-ttu-id="f4896-148">Para obter um melhor desempenho, não inclua valores existentes que não foram alterados.</span><span class="sxs-lookup"><span data-stu-id="f4896-148">For best performance you shouldn't include existing values that haven't changed.</span></span>

<span data-ttu-id="f4896-149">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f4896-149">Property</span></span> | <span data-ttu-id="f4896-150">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4896-150">Type</span></span> | <span data-ttu-id="f4896-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="f4896-151">Description</span></span>
:---|:---|:---
<span data-ttu-id="f4896-152">alertIds</span><span class="sxs-lookup"><span data-stu-id="f4896-152">alertIds</span></span> | <span data-ttu-id="f4896-153">Cadeia de &lt; caracteres de lista&gt;</span><span class="sxs-lookup"><span data-stu-id="f4896-153">List&lt;String&gt;</span></span>| <span data-ttu-id="f4896-154">Uma lista das IDs dos alertas a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="f4896-154">A list of the IDs of the alerts to be updated.</span></span> <span data-ttu-id="f4896-155">**Required**</span><span class="sxs-lookup"><span data-stu-id="f4896-155">**Required**</span></span>
<span data-ttu-id="f4896-156">status</span><span class="sxs-lookup"><span data-stu-id="f4896-156">status</span></span> | <span data-ttu-id="f4896-157">String</span><span class="sxs-lookup"><span data-stu-id="f4896-157">String</span></span> | <span data-ttu-id="f4896-158">Especifica o status atualizado dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="f4896-158">Specifies the updated status of the specified alerts.</span></span> <span data-ttu-id="f4896-159">Os valores da propriedade são: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="f4896-159">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="f4896-160">assignedTo</span><span class="sxs-lookup"><span data-stu-id="f4896-160">assignedTo</span></span> | <span data-ttu-id="f4896-161">String</span><span class="sxs-lookup"><span data-stu-id="f4896-161">String</span></span> | <span data-ttu-id="f4896-162">Proprietário dos alertas especificados</span><span class="sxs-lookup"><span data-stu-id="f4896-162">Owner of the specified alerts</span></span>
<span data-ttu-id="f4896-163">classificação</span><span class="sxs-lookup"><span data-stu-id="f4896-163">classification</span></span> | <span data-ttu-id="f4896-164">String</span><span class="sxs-lookup"><span data-stu-id="f4896-164">String</span></span> | <span data-ttu-id="f4896-165">Especifica a especificação dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="f4896-165">Specifies the specification of the specified alerts.</span></span> <span data-ttu-id="f4896-166">Os valores da propriedade são: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="f4896-166">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="f4896-167">determinação</span><span class="sxs-lookup"><span data-stu-id="f4896-167">determination</span></span> | <span data-ttu-id="f4896-168">String</span><span class="sxs-lookup"><span data-stu-id="f4896-168">String</span></span> | <span data-ttu-id="f4896-169">Especifica a determinação dos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="f4896-169">Specifies the determination of the specified alerts.</span></span> <span data-ttu-id="f4896-170">Os valores da propriedade são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="f4896-170">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="f4896-171">comment</span><span class="sxs-lookup"><span data-stu-id="f4896-171">comment</span></span> | <span data-ttu-id="f4896-172">String</span><span class="sxs-lookup"><span data-stu-id="f4896-172">String</span></span> | <span data-ttu-id="f4896-173">Comentário a ser adicionado aos alertas especificados.</span><span class="sxs-lookup"><span data-stu-id="f4896-173">Comment to be added to the specified alerts.</span></span>

## <a name="response"></a><span data-ttu-id="f4896-174">Resposta</span><span class="sxs-lookup"><span data-stu-id="f4896-174">Response</span></span>

<span data-ttu-id="f4896-175">Se tiver êxito, este método retornará 200 OK, com um corpo de resposta vazio.</span><span class="sxs-lookup"><span data-stu-id="f4896-175">If successful, this method returns 200 OK, with an empty response body.</span></span>

## <a name="example"></a><span data-ttu-id="f4896-176">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f4896-176">Example</span></span>

### <a name="request"></a><span data-ttu-id="f4896-177">Solicitação</span><span class="sxs-lookup"><span data-stu-id="f4896-177">Request</span></span>

<span data-ttu-id="f4896-178">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="f4896-178">Here is an example of the request.</span></span>

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
