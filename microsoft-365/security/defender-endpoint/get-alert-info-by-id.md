---
title: Obter informações de alerta pela API de ID
description: Saiba como usar a API Obter informações de alerta pela ID para recuperar um alerta específico por sua ID no Microsoft Defender para Ponto de Extremidade.
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
ms.openlocfilehash: b9de7645abc59849b3ca28f64904b0ba49d4eef5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771892"
---
# <a name="get-alert-information-by-id-api"></a><span data-ttu-id="66964-104">Obter informações de alerta pela API de ID</span><span class="sxs-lookup"><span data-stu-id="66964-104">Get alert information by ID API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="66964-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="66964-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="66964-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="66964-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="66964-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="66964-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="66964-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="66964-108">API description</span></span>
<span data-ttu-id="66964-109">Recupera Alerta [específico por](alerts.md) sua ID.</span><span class="sxs-lookup"><span data-stu-id="66964-109">Retrieves specific [Alert](alerts.md) by its ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="66964-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="66964-110">Limitations</span></span>
1. <span data-ttu-id="66964-111">Você pode obter alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="66964-111">You can get alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="66964-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="66964-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="66964-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="66964-113">Permissions</span></span>
<span data-ttu-id="66964-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="66964-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="66964-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="66964-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="66964-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="66964-116">Permission type</span></span> |   <span data-ttu-id="66964-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="66964-117">Permission</span></span>  |   <span data-ttu-id="66964-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="66964-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="66964-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="66964-119">Application</span></span> |   <span data-ttu-id="66964-120">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="66964-120">Alert.Read.All</span></span> |    <span data-ttu-id="66964-121">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="66964-121">'Read all alerts'</span></span>
<span data-ttu-id="66964-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="66964-122">Application</span></span> |   <span data-ttu-id="66964-123">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="66964-123">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="66964-124">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="66964-124">'Read and write all alerts'</span></span>
<span data-ttu-id="66964-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="66964-125">Delegated (work or school account)</span></span> | <span data-ttu-id="66964-126">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="66964-126">Alert.Read</span></span> | <span data-ttu-id="66964-127">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="66964-127">'Read alerts'</span></span>
<span data-ttu-id="66964-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="66964-128">Delegated (work or school account)</span></span> | <span data-ttu-id="66964-129">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="66964-129">Alert.ReadWrite</span></span> | <span data-ttu-id="66964-130">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="66964-130">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="66964-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="66964-131">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="66964-132">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="66964-132">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="66964-133">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="66964-133">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="66964-134">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="66964-134">HTTP request</span></span>
```
GET /api/alerts/{id}
```

## <a name="request-headers"></a><span data-ttu-id="66964-135">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="66964-135">Request headers</span></span>

<span data-ttu-id="66964-136">Nome</span><span class="sxs-lookup"><span data-stu-id="66964-136">Name</span></span> | <span data-ttu-id="66964-137">Tipo</span><span class="sxs-lookup"><span data-stu-id="66964-137">Type</span></span> | <span data-ttu-id="66964-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="66964-138">Description</span></span>
:---|:---|:---
<span data-ttu-id="66964-139">Autorização</span><span class="sxs-lookup"><span data-stu-id="66964-139">Authorization</span></span> | <span data-ttu-id="66964-140">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="66964-140">String</span></span> | <span data-ttu-id="66964-141">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="66964-141">Bearer {token}.</span></span> <span data-ttu-id="66964-142">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="66964-142">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="66964-143">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="66964-143">Request body</span></span>
<span data-ttu-id="66964-144">Vazio</span><span class="sxs-lookup"><span data-stu-id="66964-144">Empty</span></span>

## <a name="response"></a><span data-ttu-id="66964-145">Resposta</span><span class="sxs-lookup"><span data-stu-id="66964-145">Response</span></span>
<span data-ttu-id="66964-146">Se tiver êxito, este método retornará 200 OK e a entidade [de](alerts.md) alerta no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="66964-146">If successful, this method returns 200 OK, and the [alert](alerts.md) entity in the response body.</span></span> <span data-ttu-id="66964-147">Se o alerta com a id especificada não foi encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="66964-147">If alert with the specified id was not found - 404 Not Found.</span></span>
