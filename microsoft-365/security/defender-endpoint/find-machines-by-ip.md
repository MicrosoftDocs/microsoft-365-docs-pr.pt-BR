---
title: Encontrar dispositivos por API IP interna
description: Encontrar dispositivos vistos com o IP interno solicitado no intervalo de tempo de 15 minutos antes e depois de um determinado data/hora
keywords: apis, api gráfica, apis com suporte, obter, dispositivo, IP, encontrar, encontrar dispositivo, por ip, ip
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
ms.openlocfilehash: 46afa945ce86c35e3af1c542eb1a9770041b3430
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769432"
---
# <a name="find-devices-by-internal-ip-api"></a><span data-ttu-id="66e65-104">Encontrar dispositivos por API IP interna</span><span class="sxs-lookup"><span data-stu-id="66e65-104">Find devices by internal IP API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="66e65-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="66e65-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

> <span data-ttu-id="66e65-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="66e65-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="66e65-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="66e65-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="66e65-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="66e65-108">API description</span></span>
<span data-ttu-id="66e65-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span><span class="sxs-lookup"><span data-stu-id="66e65-109">Find [Machines](machine.md) seen with the requested internal IP in the time range of 15 minutes prior and after a given timestamp.</span></span>


## <a name="limitations"></a><span data-ttu-id="66e65-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="66e65-110">Limitations</span></span>
1. <span data-ttu-id="66e65-111">O data/hora determinado deve estar nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="66e65-111">The given timestamp must be in the past 30 days.</span></span>
2. <span data-ttu-id="66e65-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="66e65-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="66e65-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="66e65-113">Permissions</span></span>
<span data-ttu-id="66e65-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="66e65-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="66e65-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="66e65-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="66e65-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="66e65-116">Permission type</span></span> |   <span data-ttu-id="66e65-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="66e65-117">Permission</span></span>  |   <span data-ttu-id="66e65-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="66e65-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="66e65-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="66e65-119">Application</span></span> |   <span data-ttu-id="66e65-120">Machine.Read.All</span><span class="sxs-lookup"><span data-stu-id="66e65-120">Machine.Read.All</span></span> |  <span data-ttu-id="66e65-121">'Ler todos os perfis de máquina'</span><span class="sxs-lookup"><span data-stu-id="66e65-121">'Read all machine profiles'</span></span>
<span data-ttu-id="66e65-122">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="66e65-122">Application</span></span> |   <span data-ttu-id="66e65-123">Machine.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="66e65-123">Machine.ReadWrite.All</span></span> | <span data-ttu-id="66e65-124">'Ler e gravar todas as informações do computador'</span><span class="sxs-lookup"><span data-stu-id="66e65-124">'Read and write all machine information'</span></span>
<span data-ttu-id="66e65-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="66e65-125">Delegated (work or school account)</span></span> | <span data-ttu-id="66e65-126">Machine.Read</span><span class="sxs-lookup"><span data-stu-id="66e65-126">Machine.Read</span></span> | <span data-ttu-id="66e65-127">'Ler informações do computador'</span><span class="sxs-lookup"><span data-stu-id="66e65-127">'Read machine information'</span></span>
<span data-ttu-id="66e65-128">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="66e65-128">Delegated (work or school account)</span></span> | <span data-ttu-id="66e65-129">Machine.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="66e65-129">Machine.ReadWrite</span></span> | <span data-ttu-id="66e65-130">'Informações de máquina de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="66e65-130">'Read and write machine information'</span></span>

>[!Note]
> <span data-ttu-id="66e65-131">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="66e65-131">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="66e65-132">A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="66e65-132">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>
> - <span data-ttu-id="66e65-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="66e65-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
> - <span data-ttu-id="66e65-134">A resposta incluirá apenas dispositivos aos que o usuário tem acesso com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="66e65-134">Response will include only devices that the user have access to based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="66e65-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="66e65-135">HTTP request</span></span>
```
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a><span data-ttu-id="66e65-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="66e65-136">Request headers</span></span>

<span data-ttu-id="66e65-137">Nome</span><span class="sxs-lookup"><span data-stu-id="66e65-137">Name</span></span> | <span data-ttu-id="66e65-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="66e65-138">Type</span></span> | <span data-ttu-id="66e65-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="66e65-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="66e65-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="66e65-140">Authorization</span></span> | <span data-ttu-id="66e65-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="66e65-141">String</span></span> | <span data-ttu-id="66e65-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="66e65-142">Bearer {token}.</span></span> <span data-ttu-id="66e65-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="66e65-143">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="66e65-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="66e65-144">Request body</span></span>
<span data-ttu-id="66e65-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="66e65-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="66e65-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="66e65-146">Response</span></span>
<span data-ttu-id="66e65-147">Se bem-sucedido - 200 OK com a lista dos máquinas no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="66e65-147">If successful - 200 OK with list of the machines in the response body.</span></span>
<span data-ttu-id="66e65-148">Se o data/hora não estiver nos últimos 30 dias - 400 Solicitação Ruim.</span><span class="sxs-lookup"><span data-stu-id="66e65-148">If the timestamp is not in the past 30 days - 400 Bad Request.</span></span>

## <a name="example"></a><span data-ttu-id="66e65-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="66e65-149">Example</span></span>

<span data-ttu-id="66e65-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="66e65-150">**Request**</span></span>

<span data-ttu-id="66e65-151">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="66e65-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
