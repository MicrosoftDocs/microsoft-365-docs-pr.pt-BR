---
title: Obter API de máquinas relacionadas ao domínio
description: Saiba como usar a API obter máquinas relacionadas ao domínio para obter máquinas que se comunicaram com ou de um domínio no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, domínio, relacionado, dispositivos
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
ms.openlocfilehash: 362e3db0ed89924c58fa9662f7acbbe0c16c37c6
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772216"
---
# <a name="get-domain-related-machines-api"></a><span data-ttu-id="8d90b-104">Obter API de máquinas relacionadas ao domínio</span><span class="sxs-lookup"><span data-stu-id="8d90b-104">Get domain related machines API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8d90b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8d90b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8d90b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8d90b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8d90b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d90b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8d90b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8d90b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8d90b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8d90b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8d90b-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="8d90b-110">API description</span></span>
<span data-ttu-id="8d90b-111">Recupera uma coleção de [Máquinas](machine.md) que se comunicaram com ou com um determinado endereço de domínio.</span><span class="sxs-lookup"><span data-stu-id="8d90b-111">Retrieves a collection of [Machines](machine.md) that have communicated to or from a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="8d90b-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="8d90b-112">Limitations</span></span>
1. <span data-ttu-id="8d90b-113">Você pode consultar os dispositivos atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="8d90b-113">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="8d90b-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8d90b-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8d90b-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="8d90b-115">Permissions</span></span>
<span data-ttu-id="8d90b-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8d90b-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8d90b-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8d90b-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8d90b-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8d90b-118">Permission type</span></span> |   <span data-ttu-id="8d90b-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="8d90b-119">Permission</span></span>  |   <span data-ttu-id="8d90b-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8d90b-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8d90b-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d90b-121">Application</span></span> |   <span data-ttu-id="8d90b-122">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d90b-122">Machine.Read.All</span></span> |  <span data-ttu-id="8d90b-123">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="8d90b-123">'Read all machine profiles'</span></span>
<span data-ttu-id="8d90b-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8d90b-124">Application</span></span> |   <span data-ttu-id="8d90b-125">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d90b-125">Machine.ReadWrite.All</span></span> | <span data-ttu-id="8d90b-126">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="8d90b-126">'Read and write all machine information'</span></span>
<span data-ttu-id="8d90b-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8d90b-127">Delegated (work or school account)</span></span> | <span data-ttu-id="8d90b-128">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="8d90b-128">Machine.Read</span></span> | <span data-ttu-id="8d90b-129">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="8d90b-129">'Read machine information'</span></span>
<span data-ttu-id="8d90b-130">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8d90b-130">Delegated (work or school account)</span></span> | <span data-ttu-id="8d90b-131">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="8d90b-131">Machine.ReadWrite</span></span> | <span data-ttu-id="8d90b-132">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="8d90b-132">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="8d90b-133">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="8d90b-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8d90b-134">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="8d90b-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8d90b-135">A resposta incluirá apenas dispositivos que o usuário pode acessar, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="8d90b-135">Response will include only devices that the user can access, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8d90b-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="8d90b-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/machines
```

## <a name="request-headers"></a><span data-ttu-id="8d90b-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="8d90b-137">Request headers</span></span>

<span data-ttu-id="8d90b-138">Nome</span><span class="sxs-lookup"><span data-stu-id="8d90b-138">Name</span></span> | <span data-ttu-id="8d90b-139">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d90b-139">Type</span></span> | <span data-ttu-id="8d90b-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="8d90b-140">Description</span></span>
:---|:---|:---
<span data-ttu-id="8d90b-141">Autorização</span><span class="sxs-lookup"><span data-stu-id="8d90b-141">Authorization</span></span> | <span data-ttu-id="8d90b-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8d90b-142">String</span></span> | <span data-ttu-id="8d90b-143">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="8d90b-143">Bearer {token}.</span></span> <span data-ttu-id="8d90b-144">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="8d90b-144">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8d90b-145">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="8d90b-145">Request body</span></span>
<span data-ttu-id="8d90b-146">Vazio</span><span class="sxs-lookup"><span data-stu-id="8d90b-146">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8d90b-147">Resposta</span><span class="sxs-lookup"><span data-stu-id="8d90b-147">Response</span></span>
<span data-ttu-id="8d90b-148">Se bem-sucedido e o domínio existir - 200 OK com a lista de [entidades do](machine.md) computador.</span><span class="sxs-lookup"><span data-stu-id="8d90b-148">If successful and domain exists - 200 OK with list of [machine](machine.md) entities.</span></span> <span data-ttu-id="8d90b-149">Se o domínio não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="8d90b-149">If domain do not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="8d90b-150">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8d90b-150">Example</span></span>

<span data-ttu-id="8d90b-151">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="8d90b-151">**Request**</span></span>

<span data-ttu-id="8d90b-152">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8d90b-152">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/api.securitycenter.microsoft.com/machines
```
