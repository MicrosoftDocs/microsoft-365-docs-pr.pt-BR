---
title: Suporte de APIs do Microsoft Defender para Ponto de Extremidade
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
ms.openlocfilehash: 656aa26d80db73bfc52511f9dd94e58e771f3ac6
ms.sourcegitcommit: 9063c7a50a1d7dd6d2e1ca44f53d3c26f21f4ae8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "52073824"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="0ea2a-104">Suporte de APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0ea2a-104">Supported Microsoft Defender for Endpoint APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0ea2a-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="0ea2a-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="0ea2a-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0ea2a-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0ea2a-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a><span data-ttu-id="0ea2a-108">URI de ponto de extremidade e versão</span><span class="sxs-lookup"><span data-stu-id="0ea2a-108">Endpoint URI and versioning</span></span>

### <a name="endpoint-uri"></a><span data-ttu-id="0ea2a-109">URI do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="0ea2a-109">Endpoint URI</span></span>

> <span data-ttu-id="0ea2a-110">O URI de base de serviço é: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0ea2a-110">The service base URI is: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)</span></span>
>
> <span data-ttu-id="0ea2a-111">Os OData baseados em consultas têm o prefixo '/api'.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-111">The queries based OData have the '/api' prefix.</span></span> <span data-ttu-id="0ea2a-112">Por exemplo, para obter Alertas, você pode enviar solicitação GET para [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span><span class="sxs-lookup"><span data-stu-id="0ea2a-112">For example, to get Alerts you can send GET request to [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)</span></span>

### <a name="versioning"></a><span data-ttu-id="0ea2a-113">Controle de versão</span><span class="sxs-lookup"><span data-stu-id="0ea2a-113">Versioning</span></span>

> <span data-ttu-id="0ea2a-114">A API dá suporte ao versioning.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-114">The API supports versioning.</span></span>
>
> <span data-ttu-id="0ea2a-115">A versão atual é **V1.0**.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-115">The current version is **V1.0**.</span></span>
>
> <span data-ttu-id="0ea2a-116">Para usar uma versão específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` .</span><span class="sxs-lookup"><span data-stu-id="0ea2a-116">To use a specific version, use this format: `https://api.securitycenter.microsoft.com/api/{Version}`.</span></span> <span data-ttu-id="0ea2a-117">Por exemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span><span class="sxs-lookup"><span data-stu-id="0ea2a-117">For example: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`</span></span>
>
> <span data-ttu-id="0ea2a-118">Se você não especificar nenhuma versão (por exemplo), você `https://api.securitycenter.microsoft.com/api/alerts` obterá a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-118">If you don't specify any version (e.g. `https://api.securitycenter.microsoft.com/api/alerts` ) you will get to the latest version.</span></span>

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="0ea2a-119">Saiba mais sobre as entidades com suporte individual para as quais você pode executar chamadas de API e detalhes, como valores de solicitação HTTP, cabeçalhos de solicitação e respostas esperadas.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-119">Learn more about the individual supported entities where you can run API calls to and details such as HTTP request values, request headers and expected responses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0ea2a-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="0ea2a-120">In this section</span></span>

<span data-ttu-id="0ea2a-121">Tópico</span><span class="sxs-lookup"><span data-stu-id="0ea2a-121">Topic</span></span> | <span data-ttu-id="0ea2a-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="0ea2a-122">Description</span></span>
:---|:---
[<span data-ttu-id="0ea2a-123">Busca Avançada</span><span class="sxs-lookup"><span data-stu-id="0ea2a-123">Advanced Hunting</span></span>](run-advanced-query-api.md) | <span data-ttu-id="0ea2a-124">Execute consultas da API.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-124">Run queries from API.</span></span>
[<span data-ttu-id="0ea2a-125">Métodos e propriedades de alerta</span><span class="sxs-lookup"><span data-stu-id="0ea2a-125">Alert methods and properties</span></span>](alerts.md) | <span data-ttu-id="0ea2a-126">Execute chamadas de API, como \- obter alertas, criar alerta, atualizar alerta e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-126">Run API calls such as \- get alerts, create alert, update alert and more.</span></span>
[<span data-ttu-id="0ea2a-127">Métodos e propriedades de Investigação Automatizada</span><span class="sxs-lookup"><span data-stu-id="0ea2a-127">Automated Investigation methods and properties</span></span>](investigation.md) | <span data-ttu-id="0ea2a-128">Execute chamadas de API, como \- obter coleção de Investigação.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-128">Run API calls such as \- get collection of Investigation.</span></span>
[<span data-ttu-id="0ea2a-129">Obter alertas relacionados ao domínio</span><span class="sxs-lookup"><span data-stu-id="0ea2a-129">Get domain related alerts</span></span>](get-domain-related-alerts.md) | <span data-ttu-id="0ea2a-130">Execute chamadas de API, como \- obter dispositivos relacionados ao domínio, estatísticas de domínio e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-130">Run API calls such as \- get domain-related devices, domain statistics and more.</span></span>
[<span data-ttu-id="0ea2a-131">Métodos e propriedades de arquivo</span><span class="sxs-lookup"><span data-stu-id="0ea2a-131">File methods and properties</span></span>](files.md) | <span data-ttu-id="0ea2a-132">Execute chamadas de API, como \- obter informações de arquivo, alertas relacionados a arquivos, dispositivos relacionados a arquivos e estatísticas de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-132">Run API calls such as \- get file information, file related alerts, file related devices, and file statistics.</span></span>
[<span data-ttu-id="0ea2a-133">Métodos e propriedades de indicadores</span><span class="sxs-lookup"><span data-stu-id="0ea2a-133">Indicators methods and properties</span></span>](ti-indicator.md) | <span data-ttu-id="0ea2a-134">Execute uma chamada de API, como \- obter Indicadores, criar Indicador e excluir Indicadores.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-134">Run API call such as \- get Indicators, create Indicator, and delete Indicators.</span></span>
[<span data-ttu-id="0ea2a-135">Obter alertas relacionados ao IP</span><span class="sxs-lookup"><span data-stu-id="0ea2a-135">Get IP related alerts</span></span>](get-ip-related-alerts.md) | <span data-ttu-id="0ea2a-136">Execute chamadas de API, como \- obter alertas relacionados a IP e obter estatísticas de IP.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-136">Run API calls such as \- get IP-related alerts and get IP statistics.</span></span>
[<span data-ttu-id="0ea2a-137">Métodos e propriedades de computadores</span><span class="sxs-lookup"><span data-stu-id="0ea2a-137">Machine methods and properties</span></span>](machine.md) | <span data-ttu-id="0ea2a-138">Execute chamadas de API, como obter dispositivos, obter dispositivos por ID, informações sobre \- usuários conectados, editar marcas e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-138">Run API calls such as \- get devices, get devices by ID, information about logged on users, edit tags and more.</span></span>
[<span data-ttu-id="0ea2a-139">Métodos e propriedades de Ação do Computador</span><span class="sxs-lookup"><span data-stu-id="0ea2a-139">Machine Action methods and properties</span></span>](machineaction.md) | <span data-ttu-id="0ea2a-140">Execute uma chamada de API, como \- Isolamento, Executar verificação antivírus e muito mais.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-140">Run API call such as \- Isolation, Run anti-virus scan and more.</span></span>
[<span data-ttu-id="0ea2a-141">Métodos e propriedades da recomendação</span><span class="sxs-lookup"><span data-stu-id="0ea2a-141">Recommendation methods and properties</span></span>](recommendation.md) | <span data-ttu-id="0ea2a-142">Execute chamadas de API, como \- obter recomendação por ID.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-142">Run API calls such as \- get recommendation by ID.</span></span>
[<span data-ttu-id="0ea2a-143">Métodos e propriedades de pontuação</span><span class="sxs-lookup"><span data-stu-id="0ea2a-143">Score methods and properties</span></span>](score.md) | <span data-ttu-id="0ea2a-144">Execute chamadas de API, como \- obter pontuação de exposição ou obter pontuação segura do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-144">Run API calls such as \- get exposure score or get device secure score.</span></span>
[<span data-ttu-id="0ea2a-145">Métodos e propriedades de software</span><span class="sxs-lookup"><span data-stu-id="0ea2a-145">Software methods and properties</span></span>](software.md) | <span data-ttu-id="0ea2a-146">Execute chamadas de API, como \- vulnerabilidades de lista por software.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-146">Run API calls such as \- list vulnerabilities by software.</span></span>
[<span data-ttu-id="0ea2a-147">Métodos do usuário</span><span class="sxs-lookup"><span data-stu-id="0ea2a-147">User methods</span></span>](user.md) | <span data-ttu-id="0ea2a-148">Execute chamadas de API, como \- obter alertas relacionados ao usuário e dispositivos relacionados ao usuário.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-148">Run API calls such as \- get user-related alerts and user-related devices.</span></span>
[<span data-ttu-id="0ea2a-149">Métodos e propriedades da vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="0ea2a-149">Vulnerability methods and properties</span></span>](vulnerability.md) | <span data-ttu-id="0ea2a-150">Execute chamadas de API, como \- dispositivos de lista por vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="0ea2a-150">Run API calls such as \- list devices by vulnerability.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ea2a-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="0ea2a-151">See also</span></span>

- [<span data-ttu-id="0ea2a-152">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0ea2a-152">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)

- [<span data-ttu-id="0ea2a-153">Notas de versão da API do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0ea2a-153">Microsoft Defender for Endpoint API release notes</span></span>](api-release-notes.md)
