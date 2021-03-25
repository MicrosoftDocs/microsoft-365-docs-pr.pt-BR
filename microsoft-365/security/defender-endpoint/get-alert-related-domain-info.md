---
title: Obter informações de domínios relacionados ao alerta
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
ms.technology: mde
ms.openlocfilehash: 0cb09b23df8243d970069d087976ddc79394b67d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200408"
---
# <a name="get-alert-related-domain-information-api"></a><span data-ttu-id="8a5d8-104">Obter API de informações de domínio relacionadas ao alerta</span><span class="sxs-lookup"><span data-stu-id="8a5d8-104">Get alert related domain information API</span></span>

<span data-ttu-id="8a5d8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8a5d8-105">**Applies to:**</span></span> 
- [<span data-ttu-id="8a5d8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8a5d8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

- <span data-ttu-id="8a5d8-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8a5d8-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8a5d8-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="8a5d8-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="8a5d8-109">API description</span></span>
<span data-ttu-id="8a5d8-110">Recupera todos os domínios relacionados a um alerta específico.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-110">Retrieves all domains related to a specific alert.</span></span>


## <a name="limitations"></a><span data-ttu-id="8a5d8-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="8a5d8-111">Limitations</span></span>
1. <span data-ttu-id="8a5d8-112">Você pode consultar os alertas atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-112">You can query on alerts last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="8a5d8-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="8a5d8-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="8a5d8-114">Permissions</span></span>
<span data-ttu-id="8a5d8-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8a5d8-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8a5d8-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="8a5d8-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8a5d8-117">Permission type</span></span> | <span data-ttu-id="8a5d8-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="8a5d8-118">Permission</span></span> | <span data-ttu-id="8a5d8-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8a5d8-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="8a5d8-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8a5d8-120">Application</span></span> | <span data-ttu-id="8a5d8-121">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="8a5d8-121">URL.Read.All</span></span> | <span data-ttu-id="8a5d8-122">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="8a5d8-122">'Read URLs'</span></span>
<span data-ttu-id="8a5d8-123">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8a5d8-123">Delegated (work or school account)</span></span> | <span data-ttu-id="8a5d8-124">URL. Read.All</span><span class="sxs-lookup"><span data-stu-id="8a5d8-124">URL.Read.All</span></span> | <span data-ttu-id="8a5d8-125">'URLs de leitura'</span><span class="sxs-lookup"><span data-stu-id="8a5d8-125">'Read URLs'</span></span>

>[!Note]
> <span data-ttu-id="8a5d8-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="8a5d8-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="8a5d8-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="8a5d8-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="8a5d8-128">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="8a5d8-128">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="8a5d8-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="8a5d8-129">HTTP request</span></span>
```
GET /api/alerts/{id}/domains
```

## <a name="request-headers"></a><span data-ttu-id="8a5d8-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="8a5d8-130">Request headers</span></span>

<span data-ttu-id="8a5d8-131">Nome</span><span class="sxs-lookup"><span data-stu-id="8a5d8-131">Name</span></span> | <span data-ttu-id="8a5d8-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="8a5d8-132">Type</span></span> | <span data-ttu-id="8a5d8-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="8a5d8-133">Description</span></span>
:---|:---|:---
<span data-ttu-id="8a5d8-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="8a5d8-134">Authorization</span></span> | <span data-ttu-id="8a5d8-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8a5d8-135">String</span></span> | <span data-ttu-id="8a5d8-136">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-136">Bearer {token}.</span></span> <span data-ttu-id="8a5d8-137">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-137">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="8a5d8-138">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="8a5d8-138">Request body</span></span>
<span data-ttu-id="8a5d8-139">Vazio</span><span class="sxs-lookup"><span data-stu-id="8a5d8-139">Empty</span></span>

## <a name="response"></a><span data-ttu-id="8a5d8-140">Resposta</span><span class="sxs-lookup"><span data-stu-id="8a5d8-140">Response</span></span>
<span data-ttu-id="8a5d8-141">Se bem-sucedido e alerta e domínio existirem - 200 OK.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-141">If successful and alert and domain exist - 200 OK.</span></span> <span data-ttu-id="8a5d8-142">Se o alerta não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-142">If alert not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="8a5d8-143">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8a5d8-143">Example</span></span>

<span data-ttu-id="8a5d8-144">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="8a5d8-144">**Request**</span></span>

<span data-ttu-id="8a5d8-145">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-145">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/alerts/636688558380765161_2136280442/domains
```

<span data-ttu-id="8a5d8-146">**Response**</span><span class="sxs-lookup"><span data-stu-id="8a5d8-146">**Response**</span></span>

<span data-ttu-id="8a5d8-147">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="8a5d8-147">Here is an example of the response.</span></span>

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
