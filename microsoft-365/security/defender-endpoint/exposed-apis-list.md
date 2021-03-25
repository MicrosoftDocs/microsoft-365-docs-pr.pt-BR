---
title: Microsoft Defender para APIs de Ponto de Extremidade com suporte
ms.reviewer: ''
description: Saiba mais sobre as entidades específicas com suporte do Microsoft Defender para Endpoint para as quais você pode criar chamadas de API.
keywords: apis, apis com suporte, ator, alertas, dispositivo, usuário, domínio, ip, arquivo, consultas avançadas, busca avançada
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
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198312"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4bc0d-104">Microsoft Defender para APIs de Ponto de Extremidade com suporte</span><span class="sxs-lookup"><span data-stu-id="4bc0d-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4bc0d-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="4bc0d-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="4bc0d-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4bc0d-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4bc0d-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="4bc0d-108">URI de ponto de extremidade e versão</span><span class="sxs-lookup"><span data-stu-id="4bc0d-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="4bc0d-109">Ponto de extremidade URI:            </span><span class="sxs-lookup"><span data-stu-id="4bc0d-109">Endpoint URI:</span></span>

> <span data-ttu-id="4bc0d-110">O URI de base de serviço é: https://api.securitycenter.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="4bc0d-110">The service base URI is: https://api.securitycenter.microsoft.com</span></span>
> 
> <span data-ttu-id="4bc0d-111">Os OData baseados em consultas têm o prefixo '/api'.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="4bc0d-112">Por exemplo, para obter Alertas, você pode enviar solicitação GET para https://api.securitycenter.microsoft.com/api/alerts</span><span class="sxs-lookup"><span data-stu-id="4bc0d-112">For example, to get Alerts you can send GET request to https://api.securitycenter.microsoft.com/api/alerts</span></span>

### <a name="versioning"></a><span data-ttu-id="4bc0d-113">Versão:</span><span class="sxs-lookup"><span data-stu-id="4bc0d-113">Versioning:</span></span>

> <span data-ttu-id="4bc0d-114">A API dá suporte ao versioning.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-114">The API supports versioning.</span></span>
> 
> <span data-ttu-id="4bc0d-115">A versão atual é **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-115">The current version is **V1.0**.</span></span>
> 
> <span data-ttu-id="4bc0d-116">Para usar uma versão específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="4bc0d-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="4bc0d-117">Por exemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="4bc0d-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
> 
> <span data-ttu-id="4bc0d-118">Se você não especificar nenhuma versão (por exemplo), você https://api.securitycenter.microsoft.com/api/alerts obterá a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-118">If you don't specify any version (e.g. https://api.securitycenter.microsoft.com/api/alerts ) you will get to the latest version.</span></span>


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="4bc0d-119">Saiba mais sobre as entidades com suporte individual para as quais você pode executar chamadas de API e detalhes, como valores de solicitação HTTP, cabeçalhos de solicitação e respostas esperadas.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="4bc0d-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="4bc0d-120">In this section</span></span>

<span data-ttu-id="4bc0d-121">Tópico</span><span class="sxs-lookup"><span data-stu-id="4bc0d-121">Topic</span></span> | <span data-ttu-id="4bc0d-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="4bc0d-122">Description</span></span>
:---|:---
<span data-ttu-id="4bc0d-123">Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="4bc0d-123">Advanced Hunting</span></span> | <span data-ttu-id="4bc0d-124">Execute consultas da API.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-124">Run queries from API.</span></span>
<span data-ttu-id="4bc0d-125">Alertas</span><span class="sxs-lookup"><span data-stu-id="4bc0d-125">Alerts</span></span> | <span data-ttu-id="4bc0d-126">Execute chamadas de API, como obter alertas, criar alerta, atualizar alerta e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-126">Run API calls such as get alerts, create alert, update alert and more.</span></span>
<span data-ttu-id="4bc0d-127">Domínios</span><span class="sxs-lookup"><span data-stu-id="4bc0d-127">Domains</span></span> | <span data-ttu-id="4bc0d-128">Execute chamadas de API, como obter dispositivos relacionados ao domínio, estatísticas de domínio e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-128">Run API calls such as get domain-related devices, domain statistics and more.</span></span>
<span data-ttu-id="4bc0d-129">Arquivos</span><span class="sxs-lookup"><span data-stu-id="4bc0d-129">Files</span></span> | <span data-ttu-id="4bc0d-130">Execute chamadas de API, como obter informações de arquivo, alertas relacionados a arquivos, dispositivos relacionados a arquivos e estatísticas de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-130">Run API calls such as get file information, file related alerts, file related devices, and file statistics.</span></span>
<span data-ttu-id="4bc0d-131">IPs</span><span class="sxs-lookup"><span data-stu-id="4bc0d-131">IPs</span></span> | <span data-ttu-id="4bc0d-132">Execute chamadas de API, como obter alertas relacionados a IP e obter estatísticas de IP.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-132">Run API calls such as get IP-related alerts and get IP statistics.</span></span>
<span data-ttu-id="4bc0d-133">Máquinas</span><span class="sxs-lookup"><span data-stu-id="4bc0d-133">Machines</span></span> | <span data-ttu-id="4bc0d-134">Execute chamadas de API, como obter dispositivos, obter dispositivos por ID, informações sobre usuários conectados, editar marcas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-134">Run API calls such as get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
<span data-ttu-id="4bc0d-135">Ações do computador</span><span class="sxs-lookup"><span data-stu-id="4bc0d-135">Machine Actions</span></span> | <span data-ttu-id="4bc0d-136">Execute uma chamada de API, como Isolamento, Executar verificação antivírus e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-136">Run API call such as Isolation, Run anti-virus scan and more.</span></span>
<span data-ttu-id="4bc0d-137">Indicadores</span><span class="sxs-lookup"><span data-stu-id="4bc0d-137">Indicators</span></span> | <span data-ttu-id="4bc0d-138">Execute uma chamada de API, como criar Indicador, obter Indicadores e excluir Indicadores.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-138">Run API call such as create Indicator, get Indicators and delete Indicators.</span></span>
<span data-ttu-id="4bc0d-139">Usuários</span><span class="sxs-lookup"><span data-stu-id="4bc0d-139">Users</span></span> | <span data-ttu-id="4bc0d-140">Execute chamadas de API, como obter alertas relacionados ao usuário e dispositivos relacionados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-140">Run API calls such as get user-related alerts and user-related devices.</span></span>
<span data-ttu-id="4bc0d-141">Pontuação</span><span class="sxs-lookup"><span data-stu-id="4bc0d-141">Score</span></span> | <span data-ttu-id="4bc0d-142">Execute chamadas de API, como obter pontuação de exposição ou obter pontuação segura do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-142">Run API calls such as get exposure score or get device secure score.</span></span>
<span data-ttu-id="4bc0d-143">Software</span><span class="sxs-lookup"><span data-stu-id="4bc0d-143">Software</span></span> | <span data-ttu-id="4bc0d-144">Execute chamadas de API, como vulnerabilidades de lista por software.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-144">Run API calls such as list vulnerabilities by software.</span></span>
<span data-ttu-id="4bc0d-145">Vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="4bc0d-145">Vulnerability</span></span> | <span data-ttu-id="4bc0d-146">Execute chamadas de API, como dispositivos de lista por vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-146">Run API calls such as list devices by vulnerability.</span></span>
<span data-ttu-id="4bc0d-147">Recomendação</span><span class="sxs-lookup"><span data-stu-id="4bc0d-147">Recommendation</span></span> | <span data-ttu-id="4bc0d-148">Execute chamadas de API, como Obter recomendação por ID.</span><span class="sxs-lookup"><span data-stu-id="4bc0d-148">Run API calls such as Get recommendation by ID.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bc0d-149">Confira também</span><span class="sxs-lookup"><span data-stu-id="4bc0d-149">See also</span></span>
- [<span data-ttu-id="4bc0d-150">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4bc0d-150">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
