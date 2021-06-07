---
title: Obter API de estatísticas de arquivo
description: Saiba como usar a API Obter estatísticas de arquivo para recuperar as estatísticas do arquivo determinado no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, arquivo, estatísticas
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
ms.openlocfilehash: 6063d29562be40aed3060e241b52b1a2936aa36d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770200"
---
# <a name="get-file-statistics-api"></a><span data-ttu-id="5284b-104">Obter API de estatísticas de arquivo</span><span class="sxs-lookup"><span data-stu-id="5284b-104">Get file statistics API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5284b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5284b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5284b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5284b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5284b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5284b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5284b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5284b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5284b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5284b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="5284b-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="5284b-110">API description</span></span>
<span data-ttu-id="5284b-111">Recupera as estatísticas do arquivo determinado.</span><span class="sxs-lookup"><span data-stu-id="5284b-111">Retrieves the statistics for the given file.</span></span>


## <a name="limitations"></a><span data-ttu-id="5284b-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="5284b-112">Limitations</span></span>
1. <span data-ttu-id="5284b-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="5284b-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5284b-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="5284b-114">Permissions</span></span>
<span data-ttu-id="5284b-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="5284b-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5284b-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5284b-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5284b-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="5284b-117">Permission type</span></span> |   <span data-ttu-id="5284b-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="5284b-118">Permission</span></span>  |   <span data-ttu-id="5284b-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="5284b-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5284b-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5284b-120">Application</span></span> |   <span data-ttu-id="5284b-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="5284b-121">File.Read.All</span></span> | <span data-ttu-id="5284b-122">'Ler perfis de arquivo'</span><span class="sxs-lookup"><span data-stu-id="5284b-122">'Read file profiles'</span></span>
<span data-ttu-id="5284b-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5284b-123">Delegated (work or school account)</span></span> | <span data-ttu-id="5284b-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="5284b-124">File.Read.All</span></span> | <span data-ttu-id="5284b-125">'Ler perfis de arquivo'</span><span class="sxs-lookup"><span data-stu-id="5284b-125">'Read file profiles'</span></span>

>[!Note]
> <span data-ttu-id="5284b-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="5284b-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5284b-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="5284b-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5284b-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5284b-128">HTTP request</span></span>
```
GET /api/files/{id}/stats
```

## <a name="request-headers"></a><span data-ttu-id="5284b-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="5284b-129">Request headers</span></span>

<span data-ttu-id="5284b-130">Nome</span><span class="sxs-lookup"><span data-stu-id="5284b-130">Name</span></span> | <span data-ttu-id="5284b-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="5284b-131">Type</span></span> | <span data-ttu-id="5284b-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="5284b-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="5284b-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="5284b-133">Authorization</span></span> | <span data-ttu-id="5284b-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5284b-134">String</span></span> | <span data-ttu-id="5284b-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5284b-135">Bearer {token}.</span></span> <span data-ttu-id="5284b-136">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5284b-136">**Required**.</span></span>

## <a name="request-uri-parameters"></a><span data-ttu-id="5284b-137">Solicitar parâmetros URI</span><span class="sxs-lookup"><span data-stu-id="5284b-137">Request URI parameters</span></span>

<span data-ttu-id="5284b-138">Nome</span><span class="sxs-lookup"><span data-stu-id="5284b-138">Name</span></span> | <span data-ttu-id="5284b-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="5284b-139">Type</span></span> | <span data-ttu-id="5284b-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="5284b-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="5284b-141">lookBackHours</span><span class="sxs-lookup"><span data-stu-id="5284b-141">lookBackHours</span></span> | <span data-ttu-id="5284b-142">Int32</span><span class="sxs-lookup"><span data-stu-id="5284b-142">Int32</span></span> | <span data-ttu-id="5284b-143">Define as horas que pesquisamos de volta para obter as estatísticas.</span><span class="sxs-lookup"><span data-stu-id="5284b-143">Defines the hours we search back to get the statistics.</span></span> <span data-ttu-id="5284b-144">O padrão é 30 dias.</span><span class="sxs-lookup"><span data-stu-id="5284b-144">Defaults to 30 days.</span></span> <span data-ttu-id="5284b-145">**Opcional**.</span><span class="sxs-lookup"><span data-stu-id="5284b-145">**Optional**.</span></span>

## <a name="request-body"></a><span data-ttu-id="5284b-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5284b-146">Request body</span></span>
<span data-ttu-id="5284b-147">Vazio</span><span class="sxs-lookup"><span data-stu-id="5284b-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5284b-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="5284b-148">Response</span></span>
<span data-ttu-id="5284b-149">Se houver êxito e houver arquivo - 200 OK com dados estatísticos no corpo.</span><span class="sxs-lookup"><span data-stu-id="5284b-149">If successful and file exists - 200 OK with statistical data in the body.</span></span> <span data-ttu-id="5284b-150">Se o arquivo não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="5284b-150">If file do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5284b-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5284b-151">Example</span></span>

<span data-ttu-id="5284b-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5284b-152">**Request**</span></span>

<span data-ttu-id="5284b-153">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5284b-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/0991a395da64e1c5fbe8732ed11e6be064081d9f/stats?lookBackHours=48
```

<span data-ttu-id="5284b-154">**Response**</span><span class="sxs-lookup"><span data-stu-id="5284b-154">**Response**</span></span>

<span data-ttu-id="5284b-155">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="5284b-155">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgFileStats",
    "sha1": "0991a395da64e1c5fbe8732ed11e6be064081d9f",
    "orgPrevalence": "14850",
    "orgFirstSeen": "2019-12-07T13:44:16Z",
    "orgLastSeen": "2020-01-06T13:39:36Z",
    "globalPrevalence": "705012",
    "globalFirstObserved": "2015-03-19T12:20:07.3432441Z",
    "globalLastObserved": "2020-01-06T13:39:36Z",
    "topFileNames": [
        "MREC.exe"
    ]
}

```
