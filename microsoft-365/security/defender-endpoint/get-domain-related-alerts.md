---
title: Obter API de alertas relacionados ao domínio
description: Saiba como usar a API Obter alertas relacionados ao domínio para recuperar alertas relacionados a um determinado endereço de domínio no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, domínio, relacionados, alertas
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
ms.openlocfilehash: f8de54072c0b0ebef69b8e5586fee058b971c51f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166262"
---
# <a name="get-domain-related-alerts-api"></a><span data-ttu-id="2e973-104">Obter API de alertas relacionados ao domínio</span><span class="sxs-lookup"><span data-stu-id="2e973-104">Get domain-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2e973-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2e973-105">**Applies to:**</span></span>
- [<span data-ttu-id="2e973-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2e973-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2e973-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e973-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2e973-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2e973-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2e973-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2e973-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="2e973-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="2e973-110">API description</span></span>
<span data-ttu-id="2e973-111">Recupera uma coleção de [Alertas relacionados](alerts.md) a um determinado endereço de domínio.</span><span class="sxs-lookup"><span data-stu-id="2e973-111">Retrieves a collection of [Alerts](alerts.md) related to a given domain address.</span></span>


## <a name="limitations"></a><span data-ttu-id="2e973-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="2e973-112">Limitations</span></span>
1. <span data-ttu-id="2e973-113">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="2e973-113">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="2e973-114">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2e973-114">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="2e973-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="2e973-115">Permissions</span></span>
<span data-ttu-id="2e973-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="2e973-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2e973-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2e973-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="2e973-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="2e973-118">Permission type</span></span> |   <span data-ttu-id="2e973-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="2e973-119">Permission</span></span>  |   <span data-ttu-id="2e973-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="2e973-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="2e973-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2e973-121">Application</span></span> |   <span data-ttu-id="2e973-122">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="2e973-122">Alert.Read.All</span></span> |    <span data-ttu-id="2e973-123">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="2e973-123">'Read all alerts'</span></span>
<span data-ttu-id="2e973-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2e973-124">Application</span></span> |   <span data-ttu-id="2e973-125">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="2e973-125">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="2e973-126">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="2e973-126">'Read and write all alerts'</span></span>
<span data-ttu-id="2e973-127">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2e973-127">Delegated (work or school account)</span></span> | <span data-ttu-id="2e973-128">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="2e973-128">Alert.Read</span></span> | <span data-ttu-id="2e973-129">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="2e973-129">'Read alerts'</span></span>
<span data-ttu-id="2e973-130">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2e973-130">Delegated (work or school account)</span></span> | <span data-ttu-id="2e973-131">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="2e973-131">Alert.ReadWrite</span></span> | <span data-ttu-id="2e973-132">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="2e973-132">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="2e973-133">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="2e973-133">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="2e973-134">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="2e973-134">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="2e973-135">A resposta incluirá apenas alertas, associados a dispositivos, aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="2e973-135">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="2e973-136">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="2e973-136">HTTP request</span></span>
```http
GET /api/domains/{domain}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="2e973-137">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="2e973-137">Request headers</span></span>

| <span data-ttu-id="2e973-138">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="2e973-138">Header</span></span>        | <span data-ttu-id="2e973-139">Valor</span><span class="sxs-lookup"><span data-stu-id="2e973-139">Value</span></span>  |
|:--------------|:-------|
| <span data-ttu-id="2e973-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="2e973-140">Authorization</span></span> | <span data-ttu-id="2e973-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e973-141">String</span></span> |

## <a name="request-body"></a><span data-ttu-id="2e973-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="2e973-142">Request body</span></span>
<span data-ttu-id="2e973-143">Vazio</span><span class="sxs-lookup"><span data-stu-id="2e973-143">Empty</span></span>

## <a name="response"></a><span data-ttu-id="2e973-144">Resposta</span><span class="sxs-lookup"><span data-stu-id="2e973-144">Response</span></span>
<span data-ttu-id="2e973-145">Se bem-sucedido e o domínio existir - 200 OK com a lista de [entidades de](alerts.md) alerta.</span><span class="sxs-lookup"><span data-stu-id="2e973-145">If successful and domain exists - 200 OK with list of [alert](alerts.md) entities.</span></span> <span data-ttu-id="2e973-146">Se o domínio não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="2e973-146">If domain does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="2e973-147">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2e973-147">Example</span></span>

<span data-ttu-id="2e973-148">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="2e973-148">**Request**</span></span>

<span data-ttu-id="2e973-149">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="2e973-149">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/domains/client.wns.windows.com/alerts
```
