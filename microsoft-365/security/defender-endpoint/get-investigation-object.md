---
title: Obter API do objeto Investigation
description: Use essa API para criar chamadas relacionadas para obter o objeto Investigation
keywords: apis, api gráfica, apis com suporte, objeto Investigation
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
ms.openlocfilehash: 001b8dcf4b0bfd2550f41454fc840602a6e4361f
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770122"
---
# <a name="get-investigation-api"></a><span data-ttu-id="fe7c4-104">Obter API de Investigação</span><span class="sxs-lookup"><span data-stu-id="fe7c4-104">Get Investigation API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe7c4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fe7c4-105">**Applies to:**</span></span>
- [<span data-ttu-id="fe7c4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fe7c4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fe7c4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe7c4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="fe7c4-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="fe7c4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="fe7c4-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="fe7c4-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="fe7c4-110">API description</span></span>
<span data-ttu-id="fe7c4-111">Recupera a [Investigação específica](investigation.md) por sua ID.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-111">Retrieves specific [Investigation](investigation.md) by its ID.</span></span>
<br> <span data-ttu-id="fe7c4-112">A ID pode ser a ID da investigação ou a ID do alerta de acionamento da investigação.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-112">ID can be the investigation ID or the investigation triggering alert ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="fe7c4-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="fe7c4-113">Limitations</span></span>
1. <span data-ttu-id="fe7c4-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="fe7c4-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="fe7c4-115">Permissions</span></span>
<span data-ttu-id="fe7c4-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="fe7c4-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="fe7c4-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="fe7c4-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="fe7c4-118">Permission type</span></span> |   <span data-ttu-id="fe7c4-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="fe7c4-119">Permission</span></span>  |   <span data-ttu-id="fe7c4-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="fe7c4-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="fe7c4-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe7c4-121">Application</span></span> |   <span data-ttu-id="fe7c4-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="fe7c4-122">Alert.Read.All</span></span> |    <span data-ttu-id="fe7c4-123">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="fe7c4-123">'Read all alerts'</span></span>
<span data-ttu-id="fe7c4-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe7c4-124">Application</span></span> |   <span data-ttu-id="fe7c4-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="fe7c4-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="fe7c4-126">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="fe7c4-126">'Read and write all alerts'</span></span>
<span data-ttu-id="fe7c4-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="fe7c4-127">Delegated (work or school account)</span></span> | <span data-ttu-id="fe7c4-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="fe7c4-128">Alert.Read</span></span> | <span data-ttu-id="fe7c4-129">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="fe7c4-129">'Read alerts'</span></span>
<span data-ttu-id="fe7c4-130">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="fe7c4-130">Delegated (work or school account)</span></span> | <span data-ttu-id="fe7c4-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="fe7c4-131">Alert.ReadWrite</span></span> | <span data-ttu-id="fe7c4-132">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="fe7c4-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="fe7c4-133">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="fe7c4-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="fe7c4-134">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="fe7c4-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="fe7c4-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="fe7c4-135">HTTP request</span></span>
```
GET https://api.securitycenter.microsoft.com/api/investigations/{id}
```

## <a name="request-headers"></a><span data-ttu-id="fe7c4-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="fe7c4-136">Request headers</span></span>

<span data-ttu-id="fe7c4-137">Nome</span><span class="sxs-lookup"><span data-stu-id="fe7c4-137">Name</span></span> | <span data-ttu-id="fe7c4-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="fe7c4-138">Type</span></span> | <span data-ttu-id="fe7c4-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="fe7c4-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="fe7c4-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="fe7c4-140">Authorization</span></span> | <span data-ttu-id="fe7c4-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fe7c4-141">String</span></span> | <span data-ttu-id="fe7c4-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-142">Bearer {token}.</span></span> <span data-ttu-id="fe7c4-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="fe7c4-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="fe7c4-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="fe7c4-144">Request body</span></span>
<span data-ttu-id="fe7c4-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="fe7c4-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="fe7c4-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="fe7c4-146">Response</span></span>
<span data-ttu-id="fe7c4-147">Se tiver êxito, este método retornará 200, código de resposta Ok com uma [entidade Investigations.](investigation.md)</span><span class="sxs-lookup"><span data-stu-id="fe7c4-147">If successful, this method returns 200, Ok response code with a [Investigations](investigation.md) entity.</span></span>

