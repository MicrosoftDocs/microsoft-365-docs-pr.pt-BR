---
title: Obter API de informações de arquivo
description: Saiba como usar a API Obter informações de arquivo para obter um arquivo pelo identificador Sha1, Sha256 ou MD5 no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, arquivo, informações, sha1, sha256, md5
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
ms.openlocfilehash: b7877fb2d9b616b487d23befd0f0af35ce2c0753
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770284"
---
# <a name="get-file-information-api"></a><span data-ttu-id="ff76c-104">Obter API de informações de arquivo</span><span class="sxs-lookup"><span data-stu-id="ff76c-104">Get file information API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ff76c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ff76c-105">**Applies to:**</span></span>
- [<span data-ttu-id="ff76c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ff76c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ff76c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff76c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ff76c-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ff76c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ff76c-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ff76c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="ff76c-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="ff76c-110">API description</span></span>
<span data-ttu-id="ff76c-111">Recupera um [arquivo pelo](files.md) identificador Sha1 ou Sha256</span><span class="sxs-lookup"><span data-stu-id="ff76c-111">Retrieves a [File](files.md) by identifier Sha1, or Sha256</span></span>


## <a name="limitations"></a><span data-ttu-id="ff76c-112">Limitações</span><span class="sxs-lookup"><span data-stu-id="ff76c-112">Limitations</span></span>
1. <span data-ttu-id="ff76c-113">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="ff76c-113">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>


## <a name="permissions"></a><span data-ttu-id="ff76c-114">Permissões</span><span class="sxs-lookup"><span data-stu-id="ff76c-114">Permissions</span></span>
<span data-ttu-id="ff76c-115">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ff76c-115">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ff76c-116">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ff76c-116">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="ff76c-117">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ff76c-117">Permission type</span></span> |   <span data-ttu-id="ff76c-118">Permissão</span><span class="sxs-lookup"><span data-stu-id="ff76c-118">Permission</span></span>  |   <span data-ttu-id="ff76c-119">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ff76c-119">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="ff76c-120">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ff76c-120">Application</span></span> |   <span data-ttu-id="ff76c-121">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="ff76c-121">File.Read.All</span></span> | <span data-ttu-id="ff76c-122">'Ler todos os perfis de arquivo'</span><span class="sxs-lookup"><span data-stu-id="ff76c-122">'Read all file profiles'</span></span>
<span data-ttu-id="ff76c-123">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ff76c-123">Delegated (work or school account)</span></span> | <span data-ttu-id="ff76c-124">File.Read.All</span><span class="sxs-lookup"><span data-stu-id="ff76c-124">File.Read.All</span></span> |    <span data-ttu-id="ff76c-125">'Ler todos os perfis de arquivo'</span><span class="sxs-lookup"><span data-stu-id="ff76c-125">'Read all file profiles'</span></span>

>[!Note]
> <span data-ttu-id="ff76c-126">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="ff76c-126">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="ff76c-127">O usuário precisa ter pelo menos a seguinte permissão de função: 'Exibir Dados' (Consulte [Criar e gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="ff76c-127">The user needs to have at least the following role permission: 'View Data' (See [Create and manage roles](user-roles.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="ff76c-128">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="ff76c-128">HTTP request</span></span>
```
GET /api/files/{id}
```

## <a name="request-headers"></a><span data-ttu-id="ff76c-129">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="ff76c-129">Request headers</span></span>

<span data-ttu-id="ff76c-130">Nome</span><span class="sxs-lookup"><span data-stu-id="ff76c-130">Name</span></span> | <span data-ttu-id="ff76c-131">Tipo</span><span class="sxs-lookup"><span data-stu-id="ff76c-131">Type</span></span> | <span data-ttu-id="ff76c-132">Descrição</span><span class="sxs-lookup"><span data-stu-id="ff76c-132">Description</span></span>
:---|:---|:---
<span data-ttu-id="ff76c-133">Autorização</span><span class="sxs-lookup"><span data-stu-id="ff76c-133">Authorization</span></span> | <span data-ttu-id="ff76c-134">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ff76c-134">String</span></span> | <span data-ttu-id="ff76c-135">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="ff76c-135">Bearer {token}.</span></span> <span data-ttu-id="ff76c-136">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="ff76c-136">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="ff76c-137">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="ff76c-137">Request body</span></span>
<span data-ttu-id="ff76c-138">Vazio</span><span class="sxs-lookup"><span data-stu-id="ff76c-138">Empty</span></span>

## <a name="response"></a><span data-ttu-id="ff76c-139">Resposta</span><span class="sxs-lookup"><span data-stu-id="ff76c-139">Response</span></span>
<span data-ttu-id="ff76c-140">Se houver êxito e houver arquivo - 200 OK com a [entidade de](files.md) arquivo no corpo.</span><span class="sxs-lookup"><span data-stu-id="ff76c-140">If successful and file exists - 200 OK with the [file](files.md) entity in the body.</span></span> <span data-ttu-id="ff76c-141">Se o arquivo não existir - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="ff76c-141">If file does not exist - 404 Not Found.</span></span>


## <a name="example"></a><span data-ttu-id="ff76c-142">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ff76c-142">Example</span></span>

<span data-ttu-id="ff76c-143">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="ff76c-143">**Request**</span></span>

<span data-ttu-id="ff76c-144">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="ff76c-144">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/files/4388963aaa83afe2042a46a3c017ad50bdcdafb3
```

<span data-ttu-id="ff76c-145">**Response**</span><span class="sxs-lookup"><span data-stu-id="ff76c-145">**Response**</span></span>

<span data-ttu-id="ff76c-146">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="ff76c-146">Here is an example of the response.</span></span>


```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Files/$entity",
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
