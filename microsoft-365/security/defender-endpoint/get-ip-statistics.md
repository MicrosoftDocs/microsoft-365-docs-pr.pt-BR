---
title: Obter API de estatísticas IP
description: Obter as estatísticas mais recentes para seu IP usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, get, ip, estatísticas, prevalência
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
ms.openlocfilehash: 55bf10d01093c17ba2d186ce0a1d1313db2c3a75
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770080"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="2a6fe-104">Obter API de estatísticas IP</span><span class="sxs-lookup"><span data-stu-id="2a6fe-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2a6fe-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2a6fe-105">**Applies to:**</span></span>
- [<span data-ttu-id="2a6fe-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2a6fe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2a6fe-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a6fe-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2a6fe-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2a6fe-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2a6fe-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="2a6fe-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="2a6fe-110">API description</span></span>
<span data-ttu-id="2a6fe-111">Recupera as estatísticas do IP determinado.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="2a6fe-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="2a6fe-112">Limitations</span></span>
1. <span data-ttu-id="2a6fe-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="2a6fe-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="2a6fe-114">Permissions</span></span>
<span data-ttu-id="2a6fe-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2a6fe-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2a6fe-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2a6fe-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="2a6fe-117">Permission type</span></span> |   <span data-ttu-id="2a6fe-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="2a6fe-118">Permission</span></span>  |   <span data-ttu-id="2a6fe-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="2a6fe-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2a6fe-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2a6fe-120">Application</span></span> |   <span data-ttu-id="2a6fe-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="2a6fe-121">Ip.Read.All</span></span> |   <span data-ttu-id="2a6fe-122">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="2a6fe-122">'Read IP address profiles'</span></span>
<span data-ttu-id="2a6fe-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2a6fe-123">Delegated (work or school account)</span></span> | <span data-ttu-id="2a6fe-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="2a6fe-124">Ip.Read.All</span></span> |  <span data-ttu-id="2a6fe-125">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="2a6fe-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="2a6fe-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="2a6fe-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2a6fe-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="2a6fe-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2a6fe-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="2a6fe-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="2a6fe-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="2a6fe-129">Request headers</span></span>

<span data-ttu-id="2a6fe-130">Nome</span><span class="sxs-lookup"><span data-stu-id="2a6fe-130">Name</span></span> | <span data-ttu-id="2a6fe-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="2a6fe-131">Type</span></span> | <span data-ttu-id="2a6fe-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a6fe-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="2a6fe-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="2a6fe-133">Authorization</span></span> | <span data-ttu-id="2a6fe-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2a6fe-134">String</span></span> | <span data-ttu-id="2a6fe-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-135">Bearer {token}.</span></span> <span data-ttu-id="2a6fe-136">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="2a6fe-137">Solicitar parâmetros URI</span><span class="sxs-lookup"><span data-stu-id="2a6fe-137">Request URI parameters</span></span>

<span data-ttu-id="2a6fe-138">Nome</span><span class="sxs-lookup"><span data-stu-id="2a6fe-138">Name</span></span> | <span data-ttu-id="2a6fe-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="2a6fe-139">Type</span></span> | <span data-ttu-id="2a6fe-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a6fe-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="2a6fe-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="2a6fe-141">lookBackHours</span></span> | <span data-ttu-id="2a6fe-142">Int32</span><span class="sxs-lookup"><span data-stu-id="2a6fe-142">Int32</span></span> | <span data-ttu-id="2a6fe-143">Define as horas que pesquisamos de volta para obter as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="2a6fe-144">O padrão é 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-144">Defaults to 30 days.</span></span> <span data-ttu-id="2a6fe-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="2a6fe-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="2a6fe-146">Request body</span></span>
<span data-ttu-id="2a6fe-147">Vazio</span><span class="sxs-lookup"><span data-stu-id="2a6fe-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2a6fe-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="2a6fe-148">Response</span></span>
<span data-ttu-id="2a6fe-149">Se bem-sucedido e ip existir - 200 OK com dados estatísticos no corpo.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="2a6fe-150">IP não existe - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2a6fe-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2a6fe-151">Example</span></span>

<span data-ttu-id="2a6fe-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="2a6fe-152">**Request**</span></span>

<span data-ttu-id="2a6fe-153">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="2a6fe-154">**Response**</span><span class="sxs-lookup"><span data-stu-id="2a6fe-154">**Response**</span></span>

<span data-ttu-id="2a6fe-155">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "orgPrevalence": "63515",
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="2a6fe-156">Nome</span><span class="sxs-lookup"><span data-stu-id="2a6fe-156">Name</span></span> | <span data-ttu-id="2a6fe-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="2a6fe-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="2a6fe-158">Prevalência de organização</span><span class="sxs-lookup"><span data-stu-id="2a6fe-158">Org prevalence</span></span> | <span data-ttu-id="2a6fe-159">a contagem distinta de dispositivos que abriram a conexão de rede a esse IP.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="2a6fe-160">Org visto pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="2a6fe-160">Org first seen</span></span> | <span data-ttu-id="2a6fe-161">a primeira conexão para esse IP na organização.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="2a6fe-162">Org visto pela última vez</span><span class="sxs-lookup"><span data-stu-id="2a6fe-162">Org last seen</span></span>  | <span data-ttu-id="2a6fe-163">a última conexão para esse IP na organização.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="2a6fe-164">Essas informações estatísticas se baseiam nos dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2a6fe-164">This statistic information is based on data from the past 30 days.</span></span> 
