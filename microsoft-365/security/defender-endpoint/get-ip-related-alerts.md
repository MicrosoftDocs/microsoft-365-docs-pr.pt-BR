---
title: Obter API de alertas de IP
description: Recuperar uma coleção de alertas relacionados a um determinado endereço IP usando o Microsoft Defender para Ponto de Extremidade
keywords: apis, api gráfica, apis com suporte, get, ip, relacionados, alertas
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
ms.openlocfilehash: dbcde70b32f9a10280dd43e98c5a237a0027a33c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166360"
---
# <a name="get-ip-related-alerts-api"></a><span data-ttu-id="5c411-104">Obter API de alertas de IP</span><span class="sxs-lookup"><span data-stu-id="5c411-104">Get IP related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5c411-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5c411-105">**Applies to:**</span></span>
- [<span data-ttu-id="5c411-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5c411-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5c411-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5c411-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5c411-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5c411-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5c411-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5c411-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="5c411-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="5c411-110">API description</span></span>
<span data-ttu-id="5c411-111">Recupera uma coleção de alertas relacionados a um determinado endereço IP.</span><span class="sxs-lookup"><span data-stu-id="5c411-111">Retrieves a collection of alerts related to a given IP address.</span></span>


## <a name="limitations"></a><span data-ttu-id="5c411-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="5c411-112">Limitations</span></span>
1. <span data-ttu-id="5c411-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="5c411-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5c411-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="5c411-114">Permissions</span></span>
<span data-ttu-id="5c411-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="5c411-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5c411-116">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5c411-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5c411-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="5c411-117">Permission type</span></span> |   <span data-ttu-id="5c411-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="5c411-118">Permission</span></span>  |   <span data-ttu-id="5c411-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="5c411-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5c411-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5c411-120">Application</span></span> |   <span data-ttu-id="5c411-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="5c411-121">Alert.Read.All</span></span> |    <span data-ttu-id="5c411-122">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="5c411-122">'Read all alerts'</span></span>
<span data-ttu-id="5c411-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5c411-123">Application</span></span> |   <span data-ttu-id="5c411-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5c411-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="5c411-125">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="5c411-125">'Read and write all alerts'</span></span>
<span data-ttu-id="5c411-126">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5c411-126">Delegated (work or school account)</span></span> | <span data-ttu-id="5c411-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="5c411-127">Alert.Read</span></span> | <span data-ttu-id="5c411-128">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="5c411-128">'Read alerts'</span></span>
<span data-ttu-id="5c411-129">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5c411-129">Delegated (work or school account)</span></span> | <span data-ttu-id="5c411-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5c411-130">Alert.ReadWrite</span></span> | <span data-ttu-id="5c411-131">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="5c411-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="5c411-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="5c411-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5c411-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="5c411-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="5c411-134">A resposta incluirá apenas alertas, associados a dispositivos, aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="5c411-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="5c411-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5c411-135">HTTP request</span></span>
```
GET /api/ips/{ip}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="5c411-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="5c411-136">Request headers</span></span>

<span data-ttu-id="5c411-137">Nome</span><span class="sxs-lookup"><span data-stu-id="5c411-137">Name</span></span> | <span data-ttu-id="5c411-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c411-138">Type</span></span> | <span data-ttu-id="5c411-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="5c411-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="5c411-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="5c411-140">Authorization</span></span> | <span data-ttu-id="5c411-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5c411-141">String</span></span> | <span data-ttu-id="5c411-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5c411-142">Bearer {token}.</span></span> <span data-ttu-id="5c411-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5c411-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5c411-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5c411-144">Request body</span></span>
<span data-ttu-id="5c411-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="5c411-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5c411-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="5c411-146">Response</span></span>
<span data-ttu-id="5c411-147">Se bem-sucedido e o IP existir - 200 OK com a [lista](alerts.md) de entidades de alerta no corpo.</span><span class="sxs-lookup"><span data-stu-id="5c411-147">If successful and IP exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="5c411-148">Se o IP não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="5c411-148">If IP do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5c411-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5c411-149">Example</span></span>

<span data-ttu-id="5c411-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5c411-150">**Request**</span></span>

<span data-ttu-id="5c411-151">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5c411-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/alerts
```