---
title: Obter API de alertas relacionados ao usuário
description: Recupere uma coleção de alertas relacionados a uma determinada ID de usuário usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, usuário, relacionado, alertas
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
ms.openlocfilehash: ab0d0e97365b5ce38b29f2b0d65e3aea48d6c28c
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769924"
---
# <a name="get-user-related-alerts-api"></a><span data-ttu-id="d2481-104">Obter API de alertas relacionados ao usuário</span><span class="sxs-lookup"><span data-stu-id="d2481-104">Get user-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d2481-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d2481-105">**Applies to:**</span></span>
- [<span data-ttu-id="d2481-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d2481-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d2481-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d2481-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d2481-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d2481-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d2481-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d2481-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="d2481-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="d2481-110">API description</span></span>
<span data-ttu-id="d2481-111">Recupera uma coleção de alertas relacionados a uma determinada ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="d2481-111">Retrieves a collection of alerts related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="d2481-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="d2481-112">Limitations</span></span>
1. <span data-ttu-id="d2481-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="d2481-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="d2481-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="d2481-114">Permissions</span></span>
<span data-ttu-id="d2481-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="d2481-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d2481-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="d2481-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="d2481-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="d2481-117">Permission type</span></span> |   <span data-ttu-id="d2481-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="d2481-118">Permission</span></span>  |   <span data-ttu-id="d2481-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="d2481-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="d2481-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="d2481-120">Application</span></span> |   <span data-ttu-id="d2481-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="d2481-121">Alert.Read.All</span></span> |    <span data-ttu-id="d2481-122">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="d2481-122">'Read all alerts'</span></span>
<span data-ttu-id="d2481-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="d2481-123">Application</span></span> |   <span data-ttu-id="d2481-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d2481-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="d2481-125">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="d2481-125">'Read and write all alerts'</span></span>
<span data-ttu-id="d2481-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="d2481-126">Delegated (work or school account)</span></span> | <span data-ttu-id="d2481-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="d2481-127">Alert.Read</span></span> | <span data-ttu-id="d2481-128">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="d2481-128">'Read alerts'</span></span>
<span data-ttu-id="d2481-129">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="d2481-129">Delegated (work or school account)</span></span> | <span data-ttu-id="d2481-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d2481-130">Alert.ReadWrite</span></span> | <span data-ttu-id="d2481-131">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="d2481-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="d2481-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="d2481-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="d2481-133">O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados".</span><span class="sxs-lookup"><span data-stu-id="d2481-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="d2481-134">Para obter mais informações, consulte [Create and manage roles](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d2481-134">For more information, see [Create and manage roles](user-roles.md).</span></span>
>- <span data-ttu-id="d2481-135">A resposta incluirá apenas alertas, associados a dispositivos, aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="d2481-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="d2481-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="d2481-136">HTTP request</span></span>
```
GET /api/users/{id}/alerts
```

<span data-ttu-id="d2481-137">**A ID não é o UPN completo, mas apenas o nome de usuário. (por exemplo, para recuperar alertas para user1@contoso.com /api/users/user1/alerts)**</span><span class="sxs-lookup"><span data-stu-id="d2481-137">**The ID is not the full UPN, but only the user name. (for example, to retrieve alerts for user1@contoso.com use /api/users/user1/alerts)**</span></span>

## <a name="request-headers"></a><span data-ttu-id="d2481-138">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="d2481-138">Request headers</span></span>

<span data-ttu-id="d2481-139">Nome</span><span class="sxs-lookup"><span data-stu-id="d2481-139">Name</span></span> | <span data-ttu-id="d2481-140">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2481-140">Type</span></span> | <span data-ttu-id="d2481-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="d2481-141">Description</span></span>
:---|:---|:---
<span data-ttu-id="d2481-142">Autorização</span><span class="sxs-lookup"><span data-stu-id="d2481-142">Authorization</span></span> | <span data-ttu-id="d2481-143">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d2481-143">String</span></span> | <span data-ttu-id="d2481-144">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d2481-144">Bearer {token}.</span></span> <span data-ttu-id="d2481-145">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="d2481-145">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="d2481-146">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="d2481-146">Request body</span></span>
<span data-ttu-id="d2481-147">Vazio</span><span class="sxs-lookup"><span data-stu-id="d2481-147">Empty</span></span>

## <a name="response"></a><span data-ttu-id="d2481-148">Resposta</span><span class="sxs-lookup"><span data-stu-id="d2481-148">Response</span></span>
<span data-ttu-id="d2481-149">Se bem-sucedido e o usuário existir - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="d2481-149">If successful and user exists - 200 OK.</span></span> <span data-ttu-id="d2481-150">Se o usuário não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="d2481-150">If the user does not exist - 404 Not Found.</span></span> 


## <a name="example"></a><span data-ttu-id="d2481-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2481-151">Example</span></span>

<span data-ttu-id="d2481-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d2481-152">**Request**</span></span>

<span data-ttu-id="d2481-153">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="d2481-153">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/alerts
```
