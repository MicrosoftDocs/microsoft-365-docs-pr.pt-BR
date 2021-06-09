---
title: Atualizar a API da entidade de alerta
description: Saiba como atualizar um alerta do Microsoft Defender para Ponto de Extremidade usando essa API. Você pode atualizar as propriedades status, determinação, classificação e assignedTo.
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
ms.openlocfilehash: 043d423e1016d77cad4a175aa41718329f464252
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768916"
---
# <a name="update-alert"></a><span data-ttu-id="22bb8-105">Atualizar alerta</span><span class="sxs-lookup"><span data-stu-id="22bb8-105">Update alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="22bb8-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="22bb8-106">**Applies to:**</span></span>
- [<span data-ttu-id="22bb8-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="22bb8-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="22bb8-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="22bb8-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="22bb8-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="22bb8-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="22bb8-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="22bb8-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="22bb8-111">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="22bb8-111">API description</span></span>
<span data-ttu-id="22bb8-112">Atualiza as propriedades do [Alerta existente.](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="22bb8-112">Updates properties of existing [Alert](alerts.md).</span></span>
<br><span data-ttu-id="22bb8-113">O envio **do comentário** está disponível com ou sem a atualização de propriedades.</span><span class="sxs-lookup"><span data-stu-id="22bb8-113">Submission of **comment** is available with or without updating properties.</span></span>
<br><span data-ttu-id="22bb8-114">As propriedades atualizáveis são: ```status``` ```determination``` , e ```classification``` ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="22bb8-114">Updatable properties are: ```status```, ```determination```, ```classification``` and ```assignedTo```.</span></span>


## <a name="limitations"></a><span data-ttu-id="22bb8-115">Limitações</span><span class="sxs-lookup"><span data-stu-id="22bb8-115">Limitations</span></span>
1. <span data-ttu-id="22bb8-116">Você pode atualizar os alertas disponíveis na API.</span><span class="sxs-lookup"><span data-stu-id="22bb8-116">You can update alerts that available in the API.</span></span> <span data-ttu-id="22bb8-117">Confira [Listar Alertas](get-alerts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="22bb8-117">See [List Alerts](get-alerts.md) for more information.</span></span>
2. <span data-ttu-id="22bb8-118">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="22bb8-118">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="22bb8-119">Permissões</span><span class="sxs-lookup"><span data-stu-id="22bb8-119">Permissions</span></span>
<span data-ttu-id="22bb8-120">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="22bb8-120">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="22bb8-121">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="22bb8-121">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="22bb8-122">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="22bb8-122">Permission type</span></span> |   <span data-ttu-id="22bb8-123">Permissão</span><span class="sxs-lookup"><span data-stu-id="22bb8-123">Permission</span></span>  |   <span data-ttu-id="22bb8-124">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="22bb8-124">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="22bb8-125">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="22bb8-125">Application</span></span> |   <span data-ttu-id="22bb8-126">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="22bb8-126">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="22bb8-127">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="22bb8-127">'Read and write all alerts'</span></span>
<span data-ttu-id="22bb8-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="22bb8-128">Delegated (work or school account)</span></span> | <span data-ttu-id="22bb8-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="22bb8-129">Alert.ReadWrite</span></span> | <span data-ttu-id="22bb8-130">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="22bb8-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="22bb8-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="22bb8-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="22bb8-132">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="22bb8-132">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="22bb8-133">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="22bb8-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="22bb8-134">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="22bb8-134">HTTP request</span></span>
```
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="22bb8-135">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="22bb8-135">Request headers</span></span>

<span data-ttu-id="22bb8-136">Nome</span><span class="sxs-lookup"><span data-stu-id="22bb8-136">Name</span></span> | <span data-ttu-id="22bb8-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="22bb8-137">Type</span></span> | <span data-ttu-id="22bb8-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="22bb8-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="22bb8-139">Autorização</span><span class="sxs-lookup"><span data-stu-id="22bb8-139">Authorization</span></span> | <span data-ttu-id="22bb8-140">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="22bb8-140">String</span></span> | <span data-ttu-id="22bb8-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="22bb8-141">Bearer {token}.</span></span> <span data-ttu-id="22bb8-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="22bb8-142">**Required**.</span></span>
<span data-ttu-id="22bb8-143">Content-Type</span><span class="sxs-lookup"><span data-stu-id="22bb8-143">Content-Type</span></span> | <span data-ttu-id="22bb8-144">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="22bb8-144">String</span></span> | <span data-ttu-id="22bb8-145">application/json.</span><span class="sxs-lookup"><span data-stu-id="22bb8-145">application/json.</span></span> <span data-ttu-id="22bb8-146">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="22bb8-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="22bb8-147">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="22bb8-147">Request body</span></span>
<span data-ttu-id="22bb8-148">No corpo da solicitação, fornece os valores dos campos relevantes que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="22bb8-148">In the request body, supply the values for the relevant fields that should be updated.</span></span>
<br><span data-ttu-id="22bb8-149">Propriedades existentes que não estão incluídas no corpo da solicitação terão seus valores anteriores mantidos ou serão recalculadas com base nas alterações a outros valores de propriedade.</span><span class="sxs-lookup"><span data-stu-id="22bb8-149">Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values.</span></span> 
<br><span data-ttu-id="22bb8-150">Para melhor desempenho, você não deve incluir valores existentes que não mudaram.</span><span class="sxs-lookup"><span data-stu-id="22bb8-150">For best performance you shouldn't include existing values that haven't change.</span></span>

<span data-ttu-id="22bb8-151">Propriedade</span><span class="sxs-lookup"><span data-stu-id="22bb8-151">Property</span></span> | <span data-ttu-id="22bb8-152">Tipo</span><span class="sxs-lookup"><span data-stu-id="22bb8-152">Type</span></span> | <span data-ttu-id="22bb8-153">Descrição</span><span class="sxs-lookup"><span data-stu-id="22bb8-153">Description</span></span>
:---|:---|:---
<span data-ttu-id="22bb8-154">status</span><span class="sxs-lookup"><span data-stu-id="22bb8-154">status</span></span> | <span data-ttu-id="22bb8-155">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="22bb8-155">String</span></span> | <span data-ttu-id="22bb8-156">Especifica o status atual do alerta.</span><span class="sxs-lookup"><span data-stu-id="22bb8-156">Specifies the current status of the alert.</span></span> <span data-ttu-id="22bb8-157">Os valores da propriedade são: 'New', 'InProgress' e 'Resolved'.</span><span class="sxs-lookup"><span data-stu-id="22bb8-157">The property values are: 'New', 'InProgress' and 'Resolved'.</span></span>
<span data-ttu-id="22bb8-158">assignedTo</span><span class="sxs-lookup"><span data-stu-id="22bb8-158">assignedTo</span></span> | <span data-ttu-id="22bb8-159">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="22bb8-159">String</span></span> | <span data-ttu-id="22bb8-160">Proprietário do alerta</span><span class="sxs-lookup"><span data-stu-id="22bb8-160">Owner of the alert</span></span>
<span data-ttu-id="22bb8-161">classificação</span><span class="sxs-lookup"><span data-stu-id="22bb8-161">classification</span></span> | <span data-ttu-id="22bb8-162">String</span><span class="sxs-lookup"><span data-stu-id="22bb8-162">String</span></span> | <span data-ttu-id="22bb8-163">Especifica a especificação do alerta.</span><span class="sxs-lookup"><span data-stu-id="22bb8-163">Specifies the specification of the alert.</span></span> <span data-ttu-id="22bb8-164">Os valores da propriedade são: 'Unknown', 'FalsePositive', 'TruePositive'.</span><span class="sxs-lookup"><span data-stu-id="22bb8-164">The property values are: 'Unknown', 'FalsePositive', 'TruePositive'.</span></span> 
<span data-ttu-id="22bb8-165">determinação</span><span class="sxs-lookup"><span data-stu-id="22bb8-165">determination</span></span> | <span data-ttu-id="22bb8-166">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="22bb8-166">String</span></span> | <span data-ttu-id="22bb8-167">Especifica a determinação do alerta.</span><span class="sxs-lookup"><span data-stu-id="22bb8-167">Specifies the determination of the alert.</span></span> <span data-ttu-id="22bb8-168">Os valores da propriedade são: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span><span class="sxs-lookup"><span data-stu-id="22bb8-168">The property values are: 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'</span></span>
<span data-ttu-id="22bb8-169">comment</span><span class="sxs-lookup"><span data-stu-id="22bb8-169">comment</span></span> | <span data-ttu-id="22bb8-170">String</span><span class="sxs-lookup"><span data-stu-id="22bb8-170">String</span></span> | <span data-ttu-id="22bb8-171">Comentário a ser adicionado ao alerta.</span><span class="sxs-lookup"><span data-stu-id="22bb8-171">Comment to be added to the alert.</span></span>

## <a name="response"></a><span data-ttu-id="22bb8-172">Resposta</span><span class="sxs-lookup"><span data-stu-id="22bb8-172">Response</span></span>
<span data-ttu-id="22bb8-173">Se tiver êxito, este método retornará 200 OK e a entidade [de](alerts.md) alerta no corpo da resposta com as propriedades atualizadas.</span><span class="sxs-lookup"><span data-stu-id="22bb8-173">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body with the updated properties.</span></span> <span data-ttu-id="22bb8-174">Se o alerta com a id especificada não foi encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="22bb8-174">If alert with the specified id was not found - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="22bb8-175">Exemplo</span><span class="sxs-lookup"><span data-stu-id="22bb8-175">Example</span></span>

<span data-ttu-id="22bb8-176">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="22bb8-176">**Request**</span></span>

<span data-ttu-id="22bb8-177">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="22bb8-177">Here is an example of the request.</span></span>

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
