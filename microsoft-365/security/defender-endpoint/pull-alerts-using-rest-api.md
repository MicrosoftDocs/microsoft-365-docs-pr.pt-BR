---
title: Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST
description: Saiba como chamar um ponto de extremidade da API do Microsoft Defender para Endpoint para puxar detecções no formato JSON usando a API REST siem.
keywords: detecções, detecções de pull, api de repouso, solicitação, resposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.custom: api
ms.openlocfilehash: 6716b0eb029b49ec08cb52ebefc23e50b19036ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771664"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="349f3-104">Puxar o Microsoft Defender para detecções de ponto de extremidade usando a API REST SIEM</span><span class="sxs-lookup"><span data-stu-id="349f3-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="349f3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="349f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="349f3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="349f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="349f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="349f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="349f3-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="349f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="349f3-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="349f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="349f3-110">[O Alerta do Microsoft Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções.</span><span class="sxs-lookup"><span data-stu-id="349f3-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="349f3-111">[O Microsoft Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Dispositivo e seus detalhes de Alerta relacionados.</span><span class="sxs-lookup"><span data-stu-id="349f3-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="349f3-112">-A API de alerta do Microsoft Defender for Endpoint é a API mais recente para consumo de alerta e contém uma lista detalhada de evidências relacionadas para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="349f3-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="349f3-113">Para obter mais informações, consulte [Métodos de alerta e propriedades](alerts.md) e [Alertas de lista.](get-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="349f3-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="349f3-114">O Microsoft Defender para Ponto de Extremidade oferece suporte ao protocolo OAuth 2.0 para puxar detecções da API.</span><span class="sxs-lookup"><span data-stu-id="349f3-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="349f3-115">Em geral, o protocolo OAuth 2.0 oferece suporte a quatro tipos de fluxos:</span><span class="sxs-lookup"><span data-stu-id="349f3-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="349f3-116">Fluxo de concessão de autorização</span><span class="sxs-lookup"><span data-stu-id="349f3-116">Authorization grant flow</span></span>
- <span data-ttu-id="349f3-117">Fluxo implícito</span><span class="sxs-lookup"><span data-stu-id="349f3-117">Implicit flow</span></span>
- <span data-ttu-id="349f3-118">Fluxo de credenciais do cliente</span><span class="sxs-lookup"><span data-stu-id="349f3-118">Client credentials flow</span></span>
- <span data-ttu-id="349f3-119">Fluxo do proprietário do recurso</span><span class="sxs-lookup"><span data-stu-id="349f3-119">Resource owner flow</span></span>

<span data-ttu-id="349f3-120">Para obter mais informações sobre as especificações do OAuth, consulte o [site OAuth](http://www.oauth.net).</span><span class="sxs-lookup"><span data-stu-id="349f3-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="349f3-121">O Microsoft Defender for  Endpoint  oferece suporte ao fluxo de concessão de autorização e ao fluxo de credenciais do cliente para obter acesso a detecções de pull, com Azure Active Directory (AAD) como o servidor de autorização.</span><span class="sxs-lookup"><span data-stu-id="349f3-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="349f3-122">O _fluxo de concessão de_ autorização usa credenciais de usuário para obter um código de autorização, que é usado para obter um token de acesso.</span><span class="sxs-lookup"><span data-stu-id="349f3-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="349f3-123">O _fluxo de credenciais do cliente_ usa credenciais de cliente para autenticar na URL do ponto de extremidade do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="349f3-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="349f3-124">Esse fluxo é adequado para cenários em que um cliente OAuth cria solicitações para uma API que não exige credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="349f3-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="349f3-125">Use o método a seguir na API do Microsoft Defender para Ponto de Extremidade para puxar detecções no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="349f3-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="349f3-126">Central de Segurança do Microsoft Defender mescla detecções de alerta semelhantes em um único alerta.</span><span class="sxs-lookup"><span data-stu-id="349f3-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="349f3-127">Essa API puxa detecções de alerta em sua forma bruta com base nos parâmetros de consulta que você definiu, permitindo que você aplique seu próprio grupo e filtragem.</span><span class="sxs-lookup"><span data-stu-id="349f3-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="349f3-128">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="349f3-128">Before you begin</span></span>
- <span data-ttu-id="349f3-129">Antes de chamar o ponto de extremidade do Microsoft Defender para Endpoint para detectar, você precisará habilitar o aplicativo de integração siem no Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="349f3-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="349f3-130">Para obter mais informações, consulte [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="349f3-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="349f3-p106">Anote os valores a seguir no registro do seu aplicativo Azure. Você precisa desses valores para configurar o fluxo OAuth em seu aplicativo de serviço ou daemon:</span><span class="sxs-lookup"><span data-stu-id="349f3-p106">Take note of the following values in your Azure application registration. You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="349f3-133">ID do aplicativo (exclusiva para o seu aplicativo)</span><span class="sxs-lookup"><span data-stu-id="349f3-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="349f3-134">Chave do aplicativo ou segredo (exclusiva para o seu aplicativo)</span><span class="sxs-lookup"><span data-stu-id="349f3-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="349f3-135">O ponto de extremidade de token OAuth 2.0 de seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="349f3-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="349f3-p107">Encontre esse valor clicando em **Exibir Pontos de Extremidade** na parte inferior do Portal de Gerenciamento do Azure, na página do seu aplicativo. O ponto de extremidade terá a seguinte aparência: `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span><span class="sxs-lookup"><span data-stu-id="349f3-p107">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page. The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="349f3-138">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="349f3-138">Get an access token</span></span>
<span data-ttu-id="349f3-139">Antes de criar chamadas para o ponto de extremidade, você precisará obter um token de acesso.</span><span class="sxs-lookup"><span data-stu-id="349f3-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="349f3-140">Você usará o token de acesso para acessar o recurso protegido, que é detecções no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="349f3-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="349f3-141">Para obter um token de acesso, você precisará fazer uma solicitação POST ao ponto de extremidade de emissão de token.</span><span class="sxs-lookup"><span data-stu-id="349f3-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="349f3-142">Aqui está uma solicitação de exemplo:</span><span class="sxs-lookup"><span data-stu-id="349f3-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="349f3-143">A resposta incluirá um token de acesso e informações sobre a expiração.</span><span class="sxs-lookup"><span data-stu-id="349f3-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="349f3-144">Agora você pode usar o valor no *campo* access_token em uma solicitação à API defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="349f3-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="349f3-145">Solicitação</span><span class="sxs-lookup"><span data-stu-id="349f3-145">Request</span></span>
<span data-ttu-id="349f3-146">Com um token de acesso, seu aplicativo pode fazer solicitações autenticadas para a API do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="349f3-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="349f3-147">Seu aplicativo deve anexar o token de acesso ao cabeçalho Authorization de cada solicitação.</span><span class="sxs-lookup"><span data-stu-id="349f3-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="349f3-148">Sintaxe de solicitação</span><span class="sxs-lookup"><span data-stu-id="349f3-148">Request syntax</span></span>
<span data-ttu-id="349f3-149">Método</span><span class="sxs-lookup"><span data-stu-id="349f3-149">Method</span></span> | <span data-ttu-id="349f3-150">Solicitar URI</span><span class="sxs-lookup"><span data-stu-id="349f3-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="349f3-151">GET</span><span class="sxs-lookup"><span data-stu-id="349f3-151">GET</span></span>| <span data-ttu-id="349f3-152">Use o URI aplicável à sua região.</span><span class="sxs-lookup"><span data-stu-id="349f3-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="349f3-153">**Para a UE**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="349f3-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="349f3-154">**Para NÓS**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="349f3-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="349f3-155">**Para o Reino Unido**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="349f3-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="349f3-156">Header de solicitação</span><span class="sxs-lookup"><span data-stu-id="349f3-156">Request header</span></span>
<span data-ttu-id="349f3-157">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="349f3-157">Header</span></span> | <span data-ttu-id="349f3-158">Tipo</span><span class="sxs-lookup"><span data-stu-id="349f3-158">Type</span></span> | <span data-ttu-id="349f3-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="349f3-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="349f3-160">Autorização</span><span class="sxs-lookup"><span data-stu-id="349f3-160">Authorization</span></span> | <span data-ttu-id="349f3-161">string</span><span class="sxs-lookup"><span data-stu-id="349f3-161">string</span></span> | <span data-ttu-id="349f3-162">Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="349f3-162">Required.</span></span> <span data-ttu-id="349f3-163">O token de acesso do Azure AD no token **do** &lt; *portador do formulário* &gt; .</span><span class="sxs-lookup"><span data-stu-id="349f3-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="349f3-164">Solicitar parâmetros</span><span class="sxs-lookup"><span data-stu-id="349f3-164">Request parameters</span></span>

<span data-ttu-id="349f3-165">Use parâmetros de consulta opcionais para especificar e controlar a quantidade de dados retornados em uma resposta.</span><span class="sxs-lookup"><span data-stu-id="349f3-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="349f3-166">Se você chamar esse método sem parâmetros, a resposta conterá todos os alertas em sua organização nas últimas 2 horas.</span><span class="sxs-lookup"><span data-stu-id="349f3-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="349f3-167">Nome</span><span class="sxs-lookup"><span data-stu-id="349f3-167">Name</span></span> | <span data-ttu-id="349f3-168">Valor</span><span class="sxs-lookup"><span data-stu-id="349f3-168">Value</span></span>| <span data-ttu-id="349f3-169">Descrição</span><span class="sxs-lookup"><span data-stu-id="349f3-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="349f3-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="349f3-170">sinceTimeUtc</span></span> | <span data-ttu-id="349f3-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="349f3-171">DateTime</span></span> | <span data-ttu-id="349f3-172">Define os alertas com limite de tempo inferior dos quais os alertas são recuperados, com base no campo:</span><span class="sxs-lookup"><span data-stu-id="349f3-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="349f3-173">O intervalo de tempo será: de sinceTimeUtc até a hora atual.</span><span class="sxs-lookup"><span data-stu-id="349f3-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="349f3-174">**OBSERVAÇÃO**: Quando não especificado, todos os alertas gerados nas últimas duas horas são recuperados.</span><span class="sxs-lookup"><span data-stu-id="349f3-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="349f3-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="349f3-175">untilTimeUtc</span></span> | <span data-ttu-id="349f3-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="349f3-176">DateTime</span></span> | <span data-ttu-id="349f3-177">Define que os alertas de limite de tempo superior são recuperados.</span><span class="sxs-lookup"><span data-stu-id="349f3-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="349f3-178">O intervalo de tempo será: de `sinceTimeUtc` vez em `untilTimeUtc` quando.</span><span class="sxs-lookup"><span data-stu-id="349f3-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="349f3-179">**OBSERVAÇÃO**: quando não especificado, o valor padrão será a hora atual.</span><span class="sxs-lookup"><span data-stu-id="349f3-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="349f3-180">ago</span><span class="sxs-lookup"><span data-stu-id="349f3-180">ago</span></span> | <span data-ttu-id="349f3-181">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="349f3-181">string</span></span> | <span data-ttu-id="349f3-182">Puxa alertas no seguinte intervalo de tempo: de `(current_time - ago)` vez em `current_time` quando.</span><span class="sxs-lookup"><span data-stu-id="349f3-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="349f3-183">O valor deve ser definido de acordo com o formato de duração **iso 8601**</span><span class="sxs-lookup"><span data-stu-id="349f3-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="349f3-184">Exemplo: `ago=PT10M` puxará alertas recebidos nos últimos 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="349f3-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="349f3-185">limite</span><span class="sxs-lookup"><span data-stu-id="349f3-185">limit</span></span> | <span data-ttu-id="349f3-186">int</span><span class="sxs-lookup"><span data-stu-id="349f3-186">int</span></span> | <span data-ttu-id="349f3-187">Define o número de alertas a serem recuperados.</span><span class="sxs-lookup"><span data-stu-id="349f3-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="349f3-188">Os alertas mais recentes serão recuperados com base no número definido.</span><span class="sxs-lookup"><span data-stu-id="349f3-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="349f3-189">**OBSERVAÇÃO**: Quando não especificado, todos os alertas disponíveis no intervalo de tempo serão recuperados.</span><span class="sxs-lookup"><span data-stu-id="349f3-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="349f3-190">machinegroups</span><span class="sxs-lookup"><span data-stu-id="349f3-190">machinegroups</span></span> | <span data-ttu-id="349f3-191">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="349f3-191">string</span></span> | <span data-ttu-id="349f3-192">Especifica grupos de dispositivos para puxar alertas.</span><span class="sxs-lookup"><span data-stu-id="349f3-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="349f3-193">**OBSERVAÇÃO**: Quando não especificado, os alertas de todos os grupos de dispositivos serão recuperados.</span><span class="sxs-lookup"><span data-stu-id="349f3-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="349f3-194">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="349f3-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="349f3-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="349f3-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="349f3-196">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="349f3-196">string</span></span> | <span data-ttu-id="349f3-197">Marca de dispositivo único do Registro.</span><span class="sxs-lookup"><span data-stu-id="349f3-197">Single device tag from the registry.</span></span>
<span data-ttu-id="349f3-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="349f3-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="349f3-199">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="349f3-199">string</span></span> | <span data-ttu-id="349f3-200">Marcas de dispositivo que foram criadas Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="349f3-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="349f3-201">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="349f3-201">Request example</span></span>
<span data-ttu-id="349f3-202">O exemplo a seguir demonstra como recuperar todas as detecções em sua organização.</span><span class="sxs-lookup"><span data-stu-id="349f3-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="349f3-203">O exemplo a seguir demonstra uma solicitação para obter as últimas 20 detecções desde 2016-09-12 00:00:00.</span><span class="sxs-lookup"><span data-stu-id="349f3-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="349f3-204">Resposta</span><span class="sxs-lookup"><span data-stu-id="349f3-204">Response</span></span>
<span data-ttu-id="349f3-205">O valor de retorno é uma matriz de objetos de alerta no formato JSON.</span><span class="sxs-lookup"><span data-stu-id="349f3-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="349f3-206">Aqui está um valor de retorno de exemplo:</span><span class="sxs-lookup"><span data-stu-id="349f3-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="349f3-207">Exemplos de código</span><span class="sxs-lookup"><span data-stu-id="349f3-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="349f3-208">Obter token de acesso</span><span class="sxs-lookup"><span data-stu-id="349f3-208">Get access token</span></span>
<span data-ttu-id="349f3-209">Os exemplos de código a seguir demonstram como obter um token de acesso para chamar a API SIEM do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="349f3-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="349f3-210">Usar token para se conectar ao ponto de extremidade de detecções</span><span class="sxs-lookup"><span data-stu-id="349f3-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="349f3-211">Os exemplos de código a seguir demonstram como usar um token de acesso para chamar a API SIEM do Defender para Ponto de Extremidade para obter alertas.</span><span class="sxs-lookup"><span data-stu-id="349f3-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="349f3-212">Códigos de erro</span><span class="sxs-lookup"><span data-stu-id="349f3-212">Error codes</span></span>
<span data-ttu-id="349f3-213">A API REST do Microsoft Defender para Ponto de Extremidade retorna os seguintes códigos de erro causados por uma solicitação inválida.</span><span class="sxs-lookup"><span data-stu-id="349f3-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="349f3-214">Código de erro HTTP</span><span class="sxs-lookup"><span data-stu-id="349f3-214">HTTP error code</span></span> | <span data-ttu-id="349f3-215">Descrição</span><span class="sxs-lookup"><span data-stu-id="349f3-215">Description</span></span>
:---|:---
<span data-ttu-id="349f3-216">401</span><span class="sxs-lookup"><span data-stu-id="349f3-216">401</span></span> | <span data-ttu-id="349f3-217">Solicitação malformada ou token inválido.</span><span class="sxs-lookup"><span data-stu-id="349f3-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="349f3-218">403</span><span class="sxs-lookup"><span data-stu-id="349f3-218">403</span></span> | <span data-ttu-id="349f3-219">Exceção não autorizada - qualquer um dos domínios não é gerenciado pelo administrador do locatário ou o estado do locatário é excluído.</span><span class="sxs-lookup"><span data-stu-id="349f3-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="349f3-220">500</span><span class="sxs-lookup"><span data-stu-id="349f3-220">500</span></span> | <span data-ttu-id="349f3-221">Erro no serviço.</span><span class="sxs-lookup"><span data-stu-id="349f3-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="349f3-222">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="349f3-222">Related topics</span></span>
- [<span data-ttu-id="349f3-223">Habilitar a integração do SIEM no Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="349f3-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="349f3-224">Configurar ArcSight para puxar o Microsoft Defender para detecções de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="349f3-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="349f3-225">Pull detections to your SIEM tools</span><span class="sxs-lookup"><span data-stu-id="349f3-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="349f3-226">Campos de Detecção de Ponto de Extremidade do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="349f3-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="349f3-227">Solucionar problemas de integração da ferramenta SIEM</span><span class="sxs-lookup"><span data-stu-id="349f3-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
