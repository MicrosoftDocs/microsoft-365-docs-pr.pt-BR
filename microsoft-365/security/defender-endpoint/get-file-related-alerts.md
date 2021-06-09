---
title: Obter API de alertas relacionados a arquivos
description: Saiba como usar a API Obter alertas relacionados a arquivos para obter uma coleção de alertas relacionados a um determinado hash de arquivo no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, arquivo, hash
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
ms.openlocfilehash: b77946f4bfdb793ffbfdf102a7221df083fb92eb
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770288"
---
# <a name="get-file-related-alerts-api"></a><span data-ttu-id="4cd22-104">Obter API de alertas relacionados a arquivos</span><span class="sxs-lookup"><span data-stu-id="4cd22-104">Get file-related alerts API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4cd22-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4cd22-105">**Applies to:**</span></span>
- [<span data-ttu-id="4cd22-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4cd22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4cd22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4cd22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4cd22-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4cd22-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4cd22-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4cd22-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="4cd22-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="4cd22-110">API description</span></span>
<span data-ttu-id="4cd22-111">Recupera uma coleção de alertas relacionados a um determinado hash de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4cd22-111">Retrieves a collection of alerts related to a given file hash.</span></span>


## <a name="limitations"></a><span data-ttu-id="4cd22-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="4cd22-112">Limitations</span></span>
1. <span data-ttu-id="4cd22-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="4cd22-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="4cd22-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="4cd22-114">Permissions</span></span>
<span data-ttu-id="4cd22-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="4cd22-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="4cd22-116">Para saber mais, incluindo como escolher permissões, consulte [Use Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="4cd22-116">To learn more, including how to choose permissions, see [Use Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="4cd22-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="4cd22-117">Permission type</span></span> |   <span data-ttu-id="4cd22-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="4cd22-118">Permission</span></span>  |   <span data-ttu-id="4cd22-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="4cd22-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="4cd22-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4cd22-120">Application</span></span> |   <span data-ttu-id="4cd22-121">Alert.Read.All</span><span class="sxs-lookup"><span data-stu-id="4cd22-121">Alert.Read.All</span></span> |    <span data-ttu-id="4cd22-122">'Ler todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="4cd22-122">'Read all alerts'</span></span>
<span data-ttu-id="4cd22-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="4cd22-123">Application</span></span> |   <span data-ttu-id="4cd22-124">Alert.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="4cd22-124">Alert.ReadWrite.All</span></span> |   <span data-ttu-id="4cd22-125">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="4cd22-125">'Read and write all alerts'</span></span>
<span data-ttu-id="4cd22-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="4cd22-126">Delegated (work or school account)</span></span> | <span data-ttu-id="4cd22-127">Alert.Read</span><span class="sxs-lookup"><span data-stu-id="4cd22-127">Alert.Read</span></span> | <span data-ttu-id="4cd22-128">'Alertas de leitura'</span><span class="sxs-lookup"><span data-stu-id="4cd22-128">'Read alerts'</span></span>
<span data-ttu-id="4cd22-129">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="4cd22-129">Delegated (work or school account)</span></span> | <span data-ttu-id="4cd22-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="4cd22-130">Alert.ReadWrite</span></span> | <span data-ttu-id="4cd22-131">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="4cd22-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="4cd22-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="4cd22-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="4cd22-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="4cd22-133">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="4cd22-134">A resposta incluirá apenas alertas, associados a dispositivos, aos que o usuário tem acesso, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="4cd22-134">Response will include only alerts, associated with devices, that the user have access to, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="4cd22-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="4cd22-135">HTTP request</span></span>
```
GET /api/files/{id}/alerts
```

## <a name="request-headers"></a><span data-ttu-id="4cd22-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="4cd22-136">Request headers</span></span>

<span data-ttu-id="4cd22-137">Nome</span><span class="sxs-lookup"><span data-stu-id="4cd22-137">Name</span></span> | <span data-ttu-id="4cd22-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="4cd22-138">Type</span></span> | <span data-ttu-id="4cd22-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="4cd22-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="4cd22-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="4cd22-140">Authorization</span></span> | <span data-ttu-id="4cd22-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4cd22-141">String</span></span> | <span data-ttu-id="4cd22-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="4cd22-142">Bearer {token}.</span></span> <span data-ttu-id="4cd22-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="4cd22-143">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="4cd22-144">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="4cd22-144">Request body</span></span>
<span data-ttu-id="4cd22-145">Vazio</span><span class="sxs-lookup"><span data-stu-id="4cd22-145">Empty</span></span>

## <a name="response"></a><span data-ttu-id="4cd22-146">Resposta</span><span class="sxs-lookup"><span data-stu-id="4cd22-146">Response</span></span>
<span data-ttu-id="4cd22-147">Se houver êxito e houver arquivo - 200 OK com a [lista](alerts.md) de entidades de alerta no corpo.</span><span class="sxs-lookup"><span data-stu-id="4cd22-147">If successful and file exists - 200 OK with list of [alert](alerts.md) entities in the body.</span></span> <span data-ttu-id="4cd22-148">Se o arquivo não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="4cd22-148">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="4cd22-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="4cd22-149">Example</span></span>

<span data-ttu-id="4cd22-150">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="4cd22-150">**Request**</span></span>

<span data-ttu-id="4cd22-151">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="4cd22-151">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/6532ec91d513acc05f43ee0aa3002599729fd3e1/alerts
```
