---
title: Obter pontuação segura do dispositivo
description: Recupera a pontuação segura do dispositivo organizacional.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: levinec
ms.author: ellevin
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 921334c937e3f211b032a5d24d4244d9a6fb3d61
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166265"
---
# <a name="get-device-secure-score"></a><span data-ttu-id="88890-104">Obter pontuação segura do dispositivo</span><span class="sxs-lookup"><span data-stu-id="88890-104">Get device secure score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="88890-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="88890-105">**Applies to:**</span></span>
- [<span data-ttu-id="88890-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="88890-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88890-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88890-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="88890-108">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="88890-108">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="88890-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="88890-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88890-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="88890-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="88890-111">Recupera a [pontuação segura da Microsoft para dispositivos.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="88890-111">Retrieves your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="88890-112">Uma pontuação segura da Microsoft mais alta para dispositivos significa que seus pontos de extremidade são mais resilientes contra ataques de ameaças de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="88890-112">A higher Microsoft Secure Score for Devices means your endpoints are more resilient from cybersecurity threat attacks.</span></span> 

## <a name="permissions"></a><span data-ttu-id="88890-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="88890-113">Permissions</span></span>

<span data-ttu-id="88890-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="88890-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="88890-115">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="88890-115">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="88890-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="88890-116">Permission type</span></span> |   <span data-ttu-id="88890-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="88890-117">Permission</span></span>  |   <span data-ttu-id="88890-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="88890-118">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="88890-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="88890-119">Application</span></span> |   <span data-ttu-id="88890-120">Score.Read.Alll</span><span class="sxs-lookup"><span data-stu-id="88890-120">Score.Read.Alll</span></span> |   <span data-ttu-id="88890-121">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="88890-121">'Read Threat and Vulnerability Management score'</span></span>
<span data-ttu-id="88890-122">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="88890-122">Delegated (work or school account)</span></span> | <span data-ttu-id="88890-123">Score.Read</span><span class="sxs-lookup"><span data-stu-id="88890-123">Score.Read</span></span> | <span data-ttu-id="88890-124">'Leitura da pontuação de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="88890-124">'Read Threat and Vulnerability Management score'</span></span>

## <a name="http-request"></a><span data-ttu-id="88890-125">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="88890-125">HTTP request</span></span>

```
GET /api/configurationScore
```

## <a name="request-headers"></a><span data-ttu-id="88890-126">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="88890-126">Request headers</span></span>

<span data-ttu-id="88890-127">Nome</span><span class="sxs-lookup"><span data-stu-id="88890-127">Name</span></span> | <span data-ttu-id="88890-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="88890-128">Type</span></span> | <span data-ttu-id="88890-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="88890-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="88890-130">Autorização</span><span class="sxs-lookup"><span data-stu-id="88890-130">Authorization</span></span> | <span data-ttu-id="88890-131">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="88890-131">String</span></span> | <span data-ttu-id="88890-132">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="88890-132">Bearer {token}.</span></span> <span data-ttu-id="88890-133">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="88890-133">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="88890-134">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="88890-134">Request body</span></span>

<span data-ttu-id="88890-135">Vazio</span><span class="sxs-lookup"><span data-stu-id="88890-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="88890-136">Resposta</span><span class="sxs-lookup"><span data-stu-id="88890-136">Response</span></span>

<span data-ttu-id="88890-137">Se tiver êxito, este método retornará 200 OK, com os dados de pontuação segura do dispositivo no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="88890-137">If successful, this method returns 200 OK, with the device secure score data in the response body.</span></span>

## <a name="example"></a><span data-ttu-id="88890-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="88890-138">Example</span></span>

### <a name="request"></a><span data-ttu-id="88890-139">Solicitação</span><span class="sxs-lookup"><span data-stu-id="88890-139">Request</span></span>

<span data-ttu-id="88890-140">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="88890-140">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response"></a><span data-ttu-id="88890-141">Resposta</span><span class="sxs-lookup"><span data-stu-id="88890-141">Response</span></span>

<span data-ttu-id="88890-142">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="88890-142">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="88890-143">A lista de respostas mostrada aqui pode ser truncada para brevidade.</span><span class="sxs-lookup"><span data-stu-id="88890-143">The response list shown here may be truncated for brevity.</span></span> 

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a><span data-ttu-id="88890-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="88890-144">See also</span></span>

- [<span data-ttu-id="88890-145">Consultas OData com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="88890-145">OData queries with Microsoft Defender for Endpoint</span></span>](exposed-apis-odata-samples.md)
