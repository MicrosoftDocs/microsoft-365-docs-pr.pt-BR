---
title: Tipo de recurso indicator
description: Especifique os detalhes da entidade e defina a expiração do indicador usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, get, TiIndicator, Indicator, recent
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
ms.openlocfilehash: bbd908c15f4d65d4923c088261c92de6d2d3cc35
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187024"
---
# <a name="indicator-resource-type"></a><span data-ttu-id="de96d-104">Tipo de recurso indicator</span><span class="sxs-lookup"><span data-stu-id="de96d-104">Indicator resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="de96d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="de96d-105">**Applies to:**</span></span>
- [<span data-ttu-id="de96d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="de96d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="de96d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="de96d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="de96d-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="de96d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="de96d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="de96d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- <span data-ttu-id="de96d-110">Consulte a página [Indicadores correspondentes](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) no portal.</span><span class="sxs-lookup"><span data-stu-id="de96d-110">See the corresponding [Indicators page](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) in the portal.</span></span> 

<span data-ttu-id="de96d-111">Método</span><span class="sxs-lookup"><span data-stu-id="de96d-111">Method</span></span>|<span data-ttu-id="de96d-112">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="de96d-112">Return Type</span></span> |<span data-ttu-id="de96d-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="de96d-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="de96d-114">Listar indicadores</span><span class="sxs-lookup"><span data-stu-id="de96d-114">List Indicators</span></span>](get-ti-indicators-collection.md) | <span data-ttu-id="de96d-115">[Indicador](ti-indicator.md) Coleção</span><span class="sxs-lookup"><span data-stu-id="de96d-115">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="de96d-116">Entidades [indicadoras](ti-indicator.md) de lista.</span><span class="sxs-lookup"><span data-stu-id="de96d-116">List [Indicator](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="de96d-117">Enviar Indicador</span><span class="sxs-lookup"><span data-stu-id="de96d-117">Submit Indicator</span></span>](post-ti-indicator.md) | [<span data-ttu-id="de96d-118">Indicador</span><span class="sxs-lookup"><span data-stu-id="de96d-118">Indicator</span></span>](ti-indicator.md) | <span data-ttu-id="de96d-119">Entidade Enviar ou atualizar [Indicador.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="de96d-119">Submit or update [Indicator](ti-indicator.md) entity.</span></span>
[<span data-ttu-id="de96d-120">Importar indicadores</span><span class="sxs-lookup"><span data-stu-id="de96d-120">Import Indicators</span></span>](import-ti-indicators.md) | <span data-ttu-id="de96d-121">[Indicador](ti-indicator.md) Coleção</span><span class="sxs-lookup"><span data-stu-id="de96d-121">[Indicator](ti-indicator.md) Collection</span></span> | <span data-ttu-id="de96d-122">Enviar ou atualizar [entidades de indicadores.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="de96d-122">Submit or update [Indicators](ti-indicator.md) entities.</span></span>
[<span data-ttu-id="de96d-123">Excluir Indicador</span><span class="sxs-lookup"><span data-stu-id="de96d-123">Delete Indicator</span></span>](delete-ti-indicator-by-id.md) | <span data-ttu-id="de96d-124">Sem Conteúdo</span><span class="sxs-lookup"><span data-stu-id="de96d-124">No Content</span></span> | <span data-ttu-id="de96d-125">Exclui entidade [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="de96d-125">Deletes [Indicator](ti-indicator.md) entity.</span></span>


## <a name="properties"></a><span data-ttu-id="de96d-126">Propriedades</span><span class="sxs-lookup"><span data-stu-id="de96d-126">Properties</span></span>
<span data-ttu-id="de96d-127">Propriedade</span><span class="sxs-lookup"><span data-stu-id="de96d-127">Property</span></span> |  <span data-ttu-id="de96d-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="de96d-128">Type</span></span>    |   <span data-ttu-id="de96d-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="de96d-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="de96d-130">id</span><span class="sxs-lookup"><span data-stu-id="de96d-130">id</span></span> | <span data-ttu-id="de96d-131">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-131">String</span></span> | <span data-ttu-id="de96d-132">Identidade da entidade [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="de96d-132">Identity of the [Indicator](ti-indicator.md) entity.</span></span>
<span data-ttu-id="de96d-133">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="de96d-133">indicatorValue</span></span> | <span data-ttu-id="de96d-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-134">String</span></span> | <span data-ttu-id="de96d-135">O valor do [Indicador](ti-indicator.md).</span><span class="sxs-lookup"><span data-stu-id="de96d-135">The value of the [Indicator](ti-indicator.md).</span></span>
<span data-ttu-id="de96d-136">indicatorType</span><span class="sxs-lookup"><span data-stu-id="de96d-136">indicatorType</span></span> | <span data-ttu-id="de96d-137">Enum</span><span class="sxs-lookup"><span data-stu-id="de96d-137">Enum</span></span> | <span data-ttu-id="de96d-138">Tipo do indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-138">Type of the indicator.</span></span> <span data-ttu-id="de96d-139">Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="de96d-139">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span>
<span data-ttu-id="de96d-140">aplicação</span><span class="sxs-lookup"><span data-stu-id="de96d-140">application</span></span> | <span data-ttu-id="de96d-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-141">String</span></span> | <span data-ttu-id="de96d-142">O aplicativo associado ao indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-142">The application associated with the indicator.</span></span> 
<span data-ttu-id="de96d-143">ação</span><span class="sxs-lookup"><span data-stu-id="de96d-143">action</span></span> | <span data-ttu-id="de96d-144">Enum</span><span class="sxs-lookup"><span data-stu-id="de96d-144">Enum</span></span> | <span data-ttu-id="de96d-145">A ação que será tomada se o indicador for descoberto na organização.</span><span class="sxs-lookup"><span data-stu-id="de96d-145">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="de96d-146">Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="de96d-146">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span>
<span data-ttu-id="de96d-147">sourceType</span><span class="sxs-lookup"><span data-stu-id="de96d-147">sourceType</span></span> | <span data-ttu-id="de96d-148">Enum</span><span class="sxs-lookup"><span data-stu-id="de96d-148">Enum</span></span> | <span data-ttu-id="de96d-149">"Usuário" caso o Indicador criado por um usuário (por exemplo, do portal), "AadApp" no caso de ter sido enviado usando aplicativo automatizado por meio da API.</span><span class="sxs-lookup"><span data-stu-id="de96d-149">"User" in case the Indicator created by a user (e.g. from the portal), "AadApp" in case it submitted using automated application via the API.</span></span>
<span data-ttu-id="de96d-150">source</span><span class="sxs-lookup"><span data-stu-id="de96d-150">source</span></span> | <span data-ttu-id="de96d-151">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-151">string</span></span> | <span data-ttu-id="de96d-152">O nome do usuário/aplicativo que enviou o indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-152">The name of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="de96d-153">createdBy</span><span class="sxs-lookup"><span data-stu-id="de96d-153">createdBy</span></span> | <span data-ttu-id="de96d-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-154">String</span></span> | <span data-ttu-id="de96d-155">Identidade exclusiva do usuário/aplicativo que enviou o indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-155">Unique identity of the user/application that submitted the indicator.</span></span>
<span data-ttu-id="de96d-156">lastUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="de96d-156">lastUpdatedBy</span></span> | <span data-ttu-id="de96d-157">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-157">String</span></span> | <span data-ttu-id="de96d-158">Identidade do usuário/aplicativo que atualizou o indicador pela última vez.</span><span class="sxs-lookup"><span data-stu-id="de96d-158">Identity of the user/application that last updated the indicator.</span></span>
<span data-ttu-id="de96d-159">creationTimeDateTimeUtc</span><span class="sxs-lookup"><span data-stu-id="de96d-159">creationTimeDateTimeUtc</span></span> | <span data-ttu-id="de96d-160">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="de96d-160">DateTimeOffset</span></span> | <span data-ttu-id="de96d-161">A data e a hora em que o indicador foi criado.</span><span class="sxs-lookup"><span data-stu-id="de96d-161">The date and time when the indicator was created.</span></span>
<span data-ttu-id="de96d-162">expirationTime</span><span class="sxs-lookup"><span data-stu-id="de96d-162">expirationTime</span></span> | <span data-ttu-id="de96d-163">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="de96d-163">DateTimeOffset</span></span> | <span data-ttu-id="de96d-164">O tempo de expiração do indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-164">The expiration time of the indicator.</span></span>
<span data-ttu-id="de96d-165">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="de96d-165">lastUpdateTime</span></span> | <span data-ttu-id="de96d-166">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="de96d-166">DateTimeOffset</span></span> | <span data-ttu-id="de96d-167">A última vez que o indicador foi atualizado.</span><span class="sxs-lookup"><span data-stu-id="de96d-167">The last time the indicator was updated.</span></span>
<span data-ttu-id="de96d-168">severity</span><span class="sxs-lookup"><span data-stu-id="de96d-168">severity</span></span> | <span data-ttu-id="de96d-169">Enum</span><span class="sxs-lookup"><span data-stu-id="de96d-169">Enum</span></span> | <span data-ttu-id="de96d-170">A gravidade do indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-170">The severity of the indicator.</span></span> <span data-ttu-id="de96d-171">os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto".</span><span class="sxs-lookup"><span data-stu-id="de96d-171">possible values are: "Informational", "Low", "Medium" and "High".</span></span>
<span data-ttu-id="de96d-172">title</span><span class="sxs-lookup"><span data-stu-id="de96d-172">title</span></span> | <span data-ttu-id="de96d-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-173">String</span></span> | <span data-ttu-id="de96d-174">Título do indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-174">Indicator title.</span></span>
<span data-ttu-id="de96d-175">descrição</span><span class="sxs-lookup"><span data-stu-id="de96d-175">description</span></span> | <span data-ttu-id="de96d-176">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-176">String</span></span> | <span data-ttu-id="de96d-177">Descrição do indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-177">Description of the indicator.</span></span>
<span data-ttu-id="de96d-178">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="de96d-178">recommendedActions</span></span> | <span data-ttu-id="de96d-179">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-179">String</span></span> | <span data-ttu-id="de96d-180">Ações recomendadas para o indicador.</span><span class="sxs-lookup"><span data-stu-id="de96d-180">Recommended actions for the indicator.</span></span>
<span data-ttu-id="de96d-181">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="de96d-181">rbacGroupNames</span></span> | <span data-ttu-id="de96d-182">Lista de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="de96d-182">List of strings</span></span> | <span data-ttu-id="de96d-183">Nomes de grupo de dispositivos RBAC onde o indicador é exposto e ativo.</span><span class="sxs-lookup"><span data-stu-id="de96d-183">RBAC device group names where the indicator is exposed and active.</span></span> <span data-ttu-id="de96d-184">Lista vazia caso ela seja exposta a todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="de96d-184">Empty list in case it exposed to all devices.</span></span>


## <a name="json-representation"></a><span data-ttu-id="de96d-185">Representação Json</span><span class="sxs-lookup"><span data-stu-id="de96d-185">Json representation</span></span>

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```