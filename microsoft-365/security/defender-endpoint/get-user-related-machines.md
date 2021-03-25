---
title: Obter API de máquinas relacionadas ao usuário
description: Saiba como usar a API obter máquinas relacionadas ao usuário para recuperar uma coleção de dispositivos relacionados a uma ID de usuário no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, usuário, alertas relacionados ao usuário
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
ms.openlocfilehash: 135dc1d76a1a90cd7fffba0638211d716865cb0c
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166251"
---
# <a name="get-user-related-machines-api"></a><span data-ttu-id="5cecc-104">Obter API de máquinas relacionadas ao usuário</span><span class="sxs-lookup"><span data-stu-id="5cecc-104">Get user-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5cecc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5cecc-105">**Applies to:**</span></span>
- [<span data-ttu-id="5cecc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5cecc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5cecc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cecc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5cecc-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5cecc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5cecc-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5cecc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="5cecc-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="5cecc-110">API description</span></span>
<span data-ttu-id="5cecc-111">Recupera uma coleção de dispositivos relacionados a uma determinada ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="5cecc-111">Retrieves a collection of devices related to a given user ID.</span></span>


## <a name="limitations"></a><span data-ttu-id="5cecc-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="5cecc-112">Limitations</span></span>
1. <span data-ttu-id="5cecc-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="5cecc-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="5cecc-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="5cecc-114">Permissions</span></span>
<span data-ttu-id="5cecc-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="5cecc-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="5cecc-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="5cecc-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="5cecc-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="5cecc-117">Permission type</span></span> |   <span data-ttu-id="5cecc-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="5cecc-118">Permission</span></span>  |   <span data-ttu-id="5cecc-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="5cecc-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="5cecc-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5cecc-120">Application</span></span> |   <span data-ttu-id="5cecc-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="5cecc-121">Machine.Read.All</span></span> |  <span data-ttu-id="5cecc-122">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="5cecc-122">'Read all machine profiles'</span></span>
<span data-ttu-id="5cecc-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="5cecc-123">Application</span></span> |   <span data-ttu-id="5cecc-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="5cecc-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="5cecc-125">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="5cecc-125">'Read and write all machine information'</span></span>
<span data-ttu-id="5cecc-126">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5cecc-126">Delegated (work or school account)</span></span> | <span data-ttu-id="5cecc-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="5cecc-127">Machine.Read</span></span> | <span data-ttu-id="5cecc-128">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="5cecc-128">'Read machine information'</span></span>
<span data-ttu-id="5cecc-129">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="5cecc-129">Delegated (work or school account)</span></span> | <span data-ttu-id="5cecc-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="5cecc-130">Machine.ReadWrite</span></span> | <span data-ttu-id="5cecc-131">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="5cecc-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="5cecc-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="5cecc-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="5cecc-133">O usuário precisa ter pelo menos a seguinte permissão de função: "Exibir Dados".</span><span class="sxs-lookup"><span data-stu-id="5cecc-133">The user needs to have at least the following role permission: 'View Data'.</span></span> <span data-ttu-id="5cecc-134">Para obter mais informações, consulte [Create and manage roles](user-roles.md) )</span><span class="sxs-lookup"><span data-stu-id="5cecc-134">For more information, see [Create and manage roles](user-roles.md) )</span></span>
>- <span data-ttu-id="5cecc-135">A resposta incluirá apenas dispositivos que o usuário pode acessar, com base nas configurações do grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5cecc-135">Response will include only devices that the user can access, based on device group settings.</span></span> <span data-ttu-id="5cecc-136">Para obter mais informações, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5cecc-136">For more information, see [Create and manage device groups](machine-groups.md).</span></span>

## <a name="http-request"></a><span data-ttu-id="5cecc-137">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="5cecc-137">HTTP request</span></span>
```
GET /api/users/{id}/machines
```

<span data-ttu-id="5cecc-138">**A ID não é o UPN completo, mas apenas o nome de usuário. (por exemplo, para recuperar máquinas para user1@contoso.com /api/users/user1/machines)**</span><span class="sxs-lookup"><span data-stu-id="5cecc-138">**The ID is not the full UPN, but only the user name. (for example, to retrieve machines for user1@contoso.com use /api/users/user1/machines)**</span></span>


## <a name="request-headers"></a><span data-ttu-id="5cecc-139">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="5cecc-139">Request headers</span></span>

<span data-ttu-id="5cecc-140">Nome</span><span class="sxs-lookup"><span data-stu-id="5cecc-140">Name</span></span> | <span data-ttu-id="5cecc-141">Tipo</span><span class="sxs-lookup"><span data-stu-id="5cecc-141">Type</span></span> | <span data-ttu-id="5cecc-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="5cecc-142">Description</span></span>
:---|:---|:---
<span data-ttu-id="5cecc-143">Autorização</span><span class="sxs-lookup"><span data-stu-id="5cecc-143">Authorization</span></span> | <span data-ttu-id="5cecc-144">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5cecc-144">String</span></span> | <span data-ttu-id="5cecc-145">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="5cecc-145">Bearer {token}.</span></span> <span data-ttu-id="5cecc-146">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="5cecc-146">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="5cecc-147">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="5cecc-147">Request body</span></span>
<span data-ttu-id="5cecc-148">Vazio</span><span class="sxs-lookup"><span data-stu-id="5cecc-148">Empty</span></span>

## <a name="response"></a><span data-ttu-id="5cecc-149">Resposta</span><span class="sxs-lookup"><span data-stu-id="5cecc-149">Response</span></span>
<span data-ttu-id="5cecc-150">Se bem-sucedido e o usuário existir - 200 OK com a lista de [entidades](machine.md) do computador no corpo.</span><span class="sxs-lookup"><span data-stu-id="5cecc-150">If successful and user exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="5cecc-151">Se o usuário não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="5cecc-151">If user does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="5cecc-152">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5cecc-152">Example</span></span>

<span data-ttu-id="5cecc-153">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="5cecc-153">**Request**</span></span>

<span data-ttu-id="5cecc-154">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="5cecc-154">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/users/user1/machines
```
