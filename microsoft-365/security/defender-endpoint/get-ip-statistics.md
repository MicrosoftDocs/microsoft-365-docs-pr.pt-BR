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
ms.openlocfilehash: 4919f082c115d8a57960ec49532b6cda6a63833f
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998723"
---
# <a name="get-ip-statistics-api"></a><span data-ttu-id="05316-104">Obter API de estatísticas IP</span><span class="sxs-lookup"><span data-stu-id="05316-104">Get IP statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05316-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="05316-105">**Applies to:**</span></span>
- [<span data-ttu-id="05316-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="05316-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05316-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05316-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="05316-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="05316-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="05316-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="05316-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="05316-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="05316-110">API description</span></span>
<span data-ttu-id="05316-111">Recupera as estatísticas do IP determinado.</span><span class="sxs-lookup"><span data-stu-id="05316-111">Retrieves the statistics for the given IP.</span></span>

## <a name="limitations"></a><span data-ttu-id="05316-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="05316-112">Limitations</span></span>
1. <span data-ttu-id="05316-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="05316-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="05316-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="05316-114">Permissions</span></span>
<span data-ttu-id="05316-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="05316-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="05316-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="05316-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="05316-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="05316-117">Permission type</span></span> |   <span data-ttu-id="05316-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="05316-118">Permission</span></span>  |   <span data-ttu-id="05316-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="05316-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="05316-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="05316-120">Application</span></span> |   <span data-ttu-id="05316-121">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="05316-121">Ip.Read.All</span></span> |   <span data-ttu-id="05316-122">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="05316-122">'Read IP address profiles'</span></span>
<span data-ttu-id="05316-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="05316-123">Delegated (work or school account)</span></span> | <span data-ttu-id="05316-124">Ip.Read.All</span><span class="sxs-lookup"><span data-stu-id="05316-124">Ip.Read.All</span></span> |  <span data-ttu-id="05316-125">'Ler perfis de endereço IP'</span><span class="sxs-lookup"><span data-stu-id="05316-125">'Read IP address profiles'</span></span>

>[!NOTE]
> <span data-ttu-id="05316-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="05316-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="05316-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="05316-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="05316-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="05316-128">HTTP request</span></span>

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a><span data-ttu-id="05316-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="05316-129">Request headers</span></span>

<span data-ttu-id="05316-130">Nome</span><span class="sxs-lookup"><span data-stu-id="05316-130">Name</span></span> | <span data-ttu-id="05316-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="05316-131">Type</span></span> | <span data-ttu-id="05316-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="05316-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="05316-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="05316-133">Authorization</span></span> | <span data-ttu-id="05316-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="05316-134">String</span></span> | <span data-ttu-id="05316-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="05316-135">Bearer {token}.</span></span> <span data-ttu-id="05316-136">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="05316-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="05316-137">Solicitar parâmetros URI</span><span class="sxs-lookup"><span data-stu-id="05316-137">Request URI parameters</span></span>

<span data-ttu-id="05316-138">Nome</span><span class="sxs-lookup"><span data-stu-id="05316-138">Name</span></span> | <span data-ttu-id="05316-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="05316-139">Type</span></span> | <span data-ttu-id="05316-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="05316-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="05316-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="05316-141">lookBackHours</span></span> | <span data-ttu-id="05316-142">Int32</span><span class="sxs-lookup"><span data-stu-id="05316-142">Int32</span></span> | <span data-ttu-id="05316-143">Define as horas que pesquisamos de volta para obter as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="05316-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="05316-144">O padrão é 30 dias.</span><span class="sxs-lookup"><span data-stu-id="05316-144">Defaults to 30 days.</span></span> <span data-ttu-id="05316-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="05316-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="05316-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="05316-146">Request body</span></span>
<span data-ttu-id="05316-147">Vazio</span><span class="sxs-lookup"><span data-stu-id="05316-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="05316-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="05316-148">Response</span></span>
<span data-ttu-id="05316-149">Se bem-sucedido e ip existir - 200 OK com dados estatísticos no corpo.</span><span class="sxs-lookup"><span data-stu-id="05316-149">If successful and ip exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="05316-150">IP não existe - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="05316-150">IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="05316-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="05316-151">Example</span></span>

<span data-ttu-id="05316-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="05316-152">**Request**</span></span>

<span data-ttu-id="05316-153">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="05316-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

<span data-ttu-id="05316-154">**Response**</span><span class="sxs-lookup"><span data-stu-id="05316-154">**Response**</span></span>

<span data-ttu-id="05316-155">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="05316-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```


| <span data-ttu-id="05316-156">Nome</span><span class="sxs-lookup"><span data-stu-id="05316-156">Name</span></span> | <span data-ttu-id="05316-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="05316-157">Description</span></span> |
| :--- | :---------- |
| <span data-ttu-id="05316-158">Prevalência da organização</span><span class="sxs-lookup"><span data-stu-id="05316-158">Organization prevalence</span></span> | <span data-ttu-id="05316-159">a contagem distinta de dispositivos que abriram a conexão de rede a esse IP.</span><span class="sxs-lookup"><span data-stu-id="05316-159">the distinct count of devices that opened network connection to this IP.</span></span> |
| <span data-ttu-id="05316-160">Org visto pela primeira vez</span><span class="sxs-lookup"><span data-stu-id="05316-160">Org first seen</span></span> | <span data-ttu-id="05316-161">a primeira conexão para esse IP na organização.</span><span class="sxs-lookup"><span data-stu-id="05316-161">the first connection for this IP in the organization.</span></span> |
| <span data-ttu-id="05316-162">Org visto pela última vez</span><span class="sxs-lookup"><span data-stu-id="05316-162">Org last seen</span></span>  | <span data-ttu-id="05316-163">a última conexão para esse IP na organização.</span><span class="sxs-lookup"><span data-stu-id="05316-163">the last connection for this IP in the organization.</span></span> |

> [!NOTE]
> <span data-ttu-id="05316-164">Essas informações estatísticas se baseiam nos dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="05316-164">This statistic information is based on data from the past 30 days.</span></span> 
