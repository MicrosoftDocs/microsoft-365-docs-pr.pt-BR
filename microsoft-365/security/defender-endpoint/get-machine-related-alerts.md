---
title: Obter API de alertas relacionados ao computador
description: Saiba como usar a API Obter alertas relacionados ao computador para recuperar todos os alertas relacionados a um dispositivo específico no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, dispositivos, relacionados, alertas
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: bf445332fed7b8661c510bf60f36088b79e2d8df
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770020"
---
# <a name="get-machine-related-alerts--api"></a><span data-ttu-id="702f8-104">Obter API de alertas relacionados ao computador</span><span class="sxs-lookup"><span data-stu-id="702f8-104">Get machine related alerts  API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="702f8-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="702f8-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="702f8-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="702f8-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="702f8-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="702f8-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="702f8-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="702f8-108">API description</span></span>
<span data-ttu-id="702f8-109">Recupera todos [os Alertas](alerts.md) relacionados a um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="702f8-109">Retrieves all [Alerts](alerts.md) related to a specific device.</span></span>


## <a name="limitations"></a><span data-ttu-id="702f8-110">Limitações</span><span class="sxs-lookup"><span data-stu-id="702f8-110">Limitations</span></span>
1. <span data-ttu-id="702f8-111">Você pode consultar os dispositivos atualizados pela última vez de acordo com o período de retenção configurado.</span><span class="sxs-lookup"><span data-stu-id="702f8-111">You can query on devices last updated according to your configured retention period.</span></span>
2. <span data-ttu-id="702f8-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="702f8-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


<span data-ttu-id="702f8-113">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="702f8-113">Permission type</span></span> |   <span data-ttu-id="702f8-114">Permissão</span><span class="sxs-lookup"><span data-stu-id="702f8-114">Permission</span></span>  |   <span data-ttu-id="702f8-115">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="702f8-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="702f8-116">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="702f8-116">Application</span></span> |   <span data-ttu-id="702f8-117">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="702f8-117">Alert.Read.All</span></span> |    <span data-ttu-id="702f8-118">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="702f8-118">'Read all alerts'</span></span>
<span data-ttu-id="702f8-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="702f8-119">Application</span></span> |   <span data-ttu-id="702f8-120">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="702f8-120">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="702f8-121">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="702f8-121">'Read and write all alerts'</span></span>
<span data-ttu-id="702f8-122">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="702f8-122">Delegated (work or school account)</span></span> | <span data-ttu-id="702f8-123">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="702f8-123">Alert.Read</span></span> | <span data-ttu-id="702f8-124">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="702f8-124">'Read alerts'</span></span>
<span data-ttu-id="702f8-125">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="702f8-125">Delegated (work or school account)</span></span> | <span data-ttu-id="702f8-126">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="702f8-126">Alert.ReadWrite</span></span> | <span data-ttu-id="702f8-127">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="702f8-127">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="702f8-128">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="702f8-128">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="702f8-129">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="702f8-129">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="702f8-130">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e [gerenciar grupos de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="702f8-130">User needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="702f8-131">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="702f8-131">HTTP request</span></span>
```http
GET /api/machines/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="702f8-132">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="702f8-132">Request headers</span></span>

<span data-ttu-id="702f8-133">Nome</span><span class="sxs-lookup"><span data-stu-id="702f8-133">Name</span></span> | <span data-ttu-id="702f8-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="702f8-134">Type</span></span> | <span data-ttu-id="702f8-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="702f8-135">Description</span></span>
:---|:---|:---
<span data-ttu-id="702f8-136">Autorização</span><span class="sxs-lookup"><span data-stu-id="702f8-136">Authorization</span></span> | <span data-ttu-id="702f8-137">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="702f8-137">String</span></span> | <span data-ttu-id="702f8-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="702f8-138">Bearer {token}.</span></span> <span data-ttu-id="702f8-139">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="702f8-139">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="702f8-140">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="702f8-140">Request body</span></span>
<span data-ttu-id="702f8-141">Vazio</span><span class="sxs-lookup"><span data-stu-id="702f8-141">Empty</span></span>

## <a name="response"></a><span data-ttu-id="702f8-142">Resposta</span><span class="sxs-lookup"><span data-stu-id="702f8-142">Response</span></span>
<span data-ttu-id="702f8-143">Se houver êxito e o dispositivo existir - 200 OK com a [lista](alerts.md) de entidades de alerta no corpo.</span><span class="sxs-lookup"><span data-stu-id="702f8-143">If successful and device exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="702f8-144">Se o dispositivo não foi encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="702f8-144">If device was not found - 404 Not Found.</span></span>
