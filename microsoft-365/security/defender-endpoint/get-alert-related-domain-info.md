---
title: Obter informações de domínios relacionadas ao alerta
description: Recupere todos os domínios relacionados a um alerta específico usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter informações de alerta, informações de alerta, domínio relacionado
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
ms.openlocfilehash: a5f3db65b42d8dc98c11f2ef2c3c5d509340e386
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771256"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="c96fd-104">Obter API de informações de domínio relacionadas ao alerta</span><span class="sxs-lookup"><span data-stu-id="c96fd-104">Get alert related domain information API</span></span>

<span data-ttu-id="c96fd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c96fd-105">**Applies to:**</span></span> 
- [<span data-ttu-id="c96fd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c96fd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="c96fd-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c96fd-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c96fd-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c96fd-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="c96fd-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="c96fd-109">API description</span></span>
<span data-ttu-id="c96fd-110">Recupera todos os domínios relacionados a um alerta específico.</span><span class="sxs-lookup"><span data-stu-id="c96fd-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="c96fd-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="c96fd-111">Limitations</span></span>
1. <span data-ttu-id="c96fd-112">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="c96fd-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="c96fd-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="c96fd-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="c96fd-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="c96fd-114">Permissions</span></span>
<span data-ttu-id="c96fd-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="c96fd-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c96fd-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c96fd-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="c96fd-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="c96fd-117">Permission type</span></span> | <span data-ttu-id="c96fd-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="c96fd-118">Permission</span></span> | <span data-ttu-id="c96fd-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="c96fd-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c96fd-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="c96fd-120">Application</span></span> | <span data-ttu-id="c96fd-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="c96fd-121">URL.Read.All</span></span> | <span data-ttu-id="c96fd-122">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="c96fd-122">'Read URLs'</span></span>
<span data-ttu-id="c96fd-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="c96fd-123">Delegated (work or school account)</span></span> | <span data-ttu-id="c96fd-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="c96fd-124">URL.Read.All</span></span> | <span data-ttu-id="c96fd-125">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="c96fd-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="c96fd-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="c96fd-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="c96fd-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="c96fd-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="c96fd-128">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="c96fd-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="c96fd-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="c96fd-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="c96fd-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="c96fd-130">Request headers</span></span>

<span data-ttu-id="c96fd-131">Nome</span><span class="sxs-lookup"><span data-stu-id="c96fd-131">Name</span></span> | <span data-ttu-id="c96fd-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="c96fd-132">Type</span></span> | <span data-ttu-id="c96fd-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="c96fd-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="c96fd-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="c96fd-134">Authorization</span></span> | <span data-ttu-id="c96fd-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c96fd-135">String</span></span> | <span data-ttu-id="c96fd-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="c96fd-136">Bearer {token}.</span></span> <span data-ttu-id="c96fd-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="c96fd-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="c96fd-138">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="c96fd-138">Request body</span></span>
<span data-ttu-id="c96fd-139">Vazio</span><span class="sxs-lookup"><span data-stu-id="c96fd-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="c96fd-140">Resposta</span><span class="sxs-lookup"><span data-stu-id="c96fd-140">Response</span></span>
<span data-ttu-id="c96fd-141">Se bem-sucedido e alerta e domínio existirem - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="c96fd-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="c96fd-142">Se o alerta não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="c96fd-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="c96fd-143">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c96fd-143">Example</span></span>

<span data-ttu-id="c96fd-144">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="c96fd-144">**Request**</span></span>

<span data-ttu-id="c96fd-145">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="c96fd-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="c96fd-146">**Response**</span><span class="sxs-lookup"><span data-stu-id="c96fd-146">**Response**</span></span>

<span data-ttu-id="c96fd-147">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="c96fd-147">Here is an example of the response.</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/$metadata#Domains",
    "value": [
        {
            "host": "www.example.com"
        },
        {
            "host": "www.example2.com"
        }
        ...
    ]
}

```
