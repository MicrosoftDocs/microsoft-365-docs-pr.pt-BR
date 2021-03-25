---
title: Obter API de máquinas relacionadas a arquivos
description: Saiba como usar a API obter máquinas relacionadas a arquivos para obter uma coleção de máquinas relacionadas a um hash de arquivo no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos, hash
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
ms.openlocfilehash: 051bdad362e142446d248e90fad608fe5c0f016f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166253"
---
# <a name="get-file-related-machines-api"></a><span data-ttu-id="c436e-104">Obter API de máquinas relacionadas a arquivos</span><span class="sxs-lookup"><span data-stu-id="c436e-104">Get file-related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c436e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c436e-105">**Applies to:**</span></span>
- [<span data-ttu-id="c436e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c436e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c436e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c436e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c436e-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c436e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c436e-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c436e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c436e-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="c436e-110">API description</span></span>
<span data-ttu-id="c436e-111">Recupera uma coleção de [Máquinas relacionada](machine.md) a um determinado hash de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c436e-111">Retrieves a collection of [Machines](machine.md) related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="c436e-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="c436e-112">Limitations</span></span>
1. <span data-ttu-id="c436e-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="c436e-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c436e-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="c436e-114">Permissions</span></span>
<span data-ttu-id="c436e-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="c436e-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c436e-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c436e-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c436e-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="c436e-117">Permission type</span></span> |   <span data-ttu-id="c436e-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="c436e-118">Permission</span></span>  |   <span data-ttu-id="c436e-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="c436e-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c436e-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="c436e-120">Application</span></span> |   <span data-ttu-id="c436e-121">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="c436e-121">Machine.Read.All</span></span> |  <span data-ttu-id="c436e-122">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="c436e-122">'Read all machine profiles'</span></span>
<span data-ttu-id="c436e-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="c436e-123">Application</span></span> |   <span data-ttu-id="c436e-124">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c436e-124">Machine.ReadWrite.All</span></span> | <span data-ttu-id="c436e-125">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="c436e-125">'Read and write all machine information'</span></span>
<span data-ttu-id="c436e-126">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="c436e-126">Delegated (work or school account)</span></span> | <span data-ttu-id="c436e-127">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="c436e-127">Machine.Read</span></span> | <span data-ttu-id="c436e-128">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="c436e-128">'Read machine information'</span></span>
<span data-ttu-id="c436e-129">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="c436e-129">Delegated (work or school account)</span></span> | <span data-ttu-id="c436e-130">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c436e-130">Machine.ReadWrite</span></span> | <span data-ttu-id="c436e-131">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="c436e-131">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="c436e-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="c436e-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c436e-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="c436e-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c436e-134">A resposta incluirá apenas dispositivos aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="c436e-134">Response will include only devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c436e-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="c436e-135">HTTP request</span></span>
```
GET /api/files/{id}/machines
```

## <a name="request-headers"></a><span data-ttu-id="c436e-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="c436e-136">Request headers</span></span>

<span data-ttu-id="c436e-137">Nome</span><span class="sxs-lookup"><span data-stu-id="c436e-137">Name</span></span> | <span data-ttu-id="c436e-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="c436e-138">Type</span></span> | <span data-ttu-id="c436e-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="c436e-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="c436e-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="c436e-140">Authorization</span></span> | <span data-ttu-id="c436e-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c436e-141">String</span></span> | <span data-ttu-id="c436e-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="c436e-142">Bearer {token}.</span></span> <span data-ttu-id="c436e-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="c436e-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c436e-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="c436e-144">Request body</span></span>
<span data-ttu-id="c436e-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="c436e-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c436e-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="c436e-146">Response</span></span>
<span data-ttu-id="c436e-147">Se houver êxito e houver arquivo - 200 OK com a lista de [entidades](machine.md) do computador no corpo.</span><span class="sxs-lookup"><span data-stu-id="c436e-147">If successful and file exists - 200 OK with list of [machine](machine.md) entities in the body.</span></span> <span data-ttu-id="c436e-148">Se o arquivo não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="c436e-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="c436e-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c436e-149">Example</span></span>

<span data-ttu-id="c436e-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="c436e-150">**Request**</span></span>

<span data-ttu-id="c436e-151">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="c436e-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/machines
```
