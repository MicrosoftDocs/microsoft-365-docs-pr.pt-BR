---
title: API de Busca Avançada
ms.reviewer: ''
description: Aprenda a usar a API de busca avançada para executar consultas avançadas no Microsoft Defender para Ponto de Extremidade. Saiba mais sobre limitações e consulte um exemplo.
keywords: apis, apis com suporte, busca avançada, consulta
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
ms.openlocfilehash: 40487143ff18cedb76c9f3f33c52cab24687c282
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604364"
---
# <a name="advanced-hunting-api"></a><span data-ttu-id="a1439-105">API de busca avançada</span><span class="sxs-lookup"><span data-stu-id="a1439-105">Advanced hunting API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a1439-106">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="a1439-106">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="a1439-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a1439-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a1439-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a1439-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="limitations"></a><span data-ttu-id="a1439-109">Limitações</span><span class="sxs-lookup"><span data-stu-id="a1439-109">Limitations</span></span>

1. <span data-ttu-id="a1439-110">Você só pode executar uma consulta em dados dos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a1439-110">You can only run a query on data from the last 30 days.</span></span>

2. <span data-ttu-id="a1439-111">Os resultados incluirão no máximo 100.000 linhas.</span><span class="sxs-lookup"><span data-stu-id="a1439-111">The results will include a maximum of 100,000 rows.</span></span>

3. <span data-ttu-id="a1439-112">O número de execuções é limitado por locatário:</span><span class="sxs-lookup"><span data-stu-id="a1439-112">The number of executions is limited per tenant:</span></span>
   - <span data-ttu-id="a1439-113">Chamadas de API: até 45 chamadas por minuto, até 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="a1439-113">API calls: Up to 45 calls per minute, up to 1500 calls per hour.</span></span>
   - <span data-ttu-id="a1439-114">Tempo de execução: 10 minutos de tempo de execução a cada hora e 3 horas de tempo de execução por dia.</span><span class="sxs-lookup"><span data-stu-id="a1439-114">Execution time: 10 minutes of running time every hour and 3 hours of running time a day.</span></span>

4. <span data-ttu-id="a1439-115">O tempo máximo de execução de uma única solicitação é de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="a1439-115">The maximal execution time of a single request is 10 minutes.</span></span>

5. <span data-ttu-id="a1439-116">A resposta 429 representará atingir o limite de cota por número de solicitações ou por CPU.</span><span class="sxs-lookup"><span data-stu-id="a1439-116">429 response will represent reaching quota limit either by number of requests or by CPU.</span></span> <span data-ttu-id="a1439-117">Leia o corpo da resposta para entender qual limite foi atingido.</span><span class="sxs-lookup"><span data-stu-id="a1439-117">Read response body to understand what limit has been reached.</span></span> 

## <a name="permissions"></a><span data-ttu-id="a1439-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="a1439-118">Permissions</span></span>

<span data-ttu-id="a1439-119">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="a1439-119">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="a1439-120">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="a1439-120">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="a1439-121">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="a1439-121">Permission type</span></span> |   <span data-ttu-id="a1439-122">Permissão</span><span class="sxs-lookup"><span data-stu-id="a1439-122">Permission</span></span>  |   <span data-ttu-id="a1439-123">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="a1439-123">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="a1439-124">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="a1439-124">Application</span></span> |   <span data-ttu-id="a1439-125">AdvancedQuery.Read.All</span><span class="sxs-lookup"><span data-stu-id="a1439-125">AdvancedQuery.Read.All</span></span> |    <span data-ttu-id="a1439-126">'Executar consultas avançadas'</span><span class="sxs-lookup"><span data-stu-id="a1439-126">'Run advanced queries'</span></span>
<span data-ttu-id="a1439-127">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="a1439-127">Delegated (work or school account)</span></span> | <span data-ttu-id="a1439-128">AdvancedQuery.Read</span><span class="sxs-lookup"><span data-stu-id="a1439-128">AdvancedQuery.Read</span></span> | <span data-ttu-id="a1439-129">'Executar consultas avançadas'</span><span class="sxs-lookup"><span data-stu-id="a1439-129">'Run advanced queries'</span></span>

>[!Note]
> <span data-ttu-id="a1439-130">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="a1439-130">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="a1439-131">O usuário precisa ter a função de AD "Exibir Dados"</span><span class="sxs-lookup"><span data-stu-id="a1439-131">The user needs to have 'View Data' AD role</span></span>
>- <span data-ttu-id="a1439-132">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="a1439-132">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="a1439-133">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="a1439-133">HTTP request</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

## <a name="request-headers"></a><span data-ttu-id="a1439-134">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="a1439-134">Request headers</span></span>

<span data-ttu-id="a1439-135">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a1439-135">Header</span></span> | <span data-ttu-id="a1439-136">Valor</span><span class="sxs-lookup"><span data-stu-id="a1439-136">Value</span></span> 
:---|:---
<span data-ttu-id="a1439-137">Autorização</span><span class="sxs-lookup"><span data-stu-id="a1439-137">Authorization</span></span> | <span data-ttu-id="a1439-138">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="a1439-138">Bearer {token}.</span></span> <span data-ttu-id="a1439-139">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="a1439-139">**Required**.</span></span>
<span data-ttu-id="a1439-140">Content-Type</span><span class="sxs-lookup"><span data-stu-id="a1439-140">Content-Type</span></span>    | <span data-ttu-id="a1439-141">application/json</span><span class="sxs-lookup"><span data-stu-id="a1439-141">application/json</span></span>

## <a name="request-body"></a><span data-ttu-id="a1439-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="a1439-142">Request body</span></span>

<span data-ttu-id="a1439-143">No corpo da solicitação, fornece um objeto JSON com os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a1439-143">In the request body, supply a JSON object with the following parameters:</span></span>

<span data-ttu-id="a1439-144">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="a1439-144">Parameter</span></span> | <span data-ttu-id="a1439-145">Tipo</span><span class="sxs-lookup"><span data-stu-id="a1439-145">Type</span></span>    | <span data-ttu-id="a1439-146">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1439-146">Description</span></span>
:---|:---|:---
<span data-ttu-id="a1439-147">Consulta</span><span class="sxs-lookup"><span data-stu-id="a1439-147">Query</span></span> | <span data-ttu-id="a1439-148">Texto</span><span class="sxs-lookup"><span data-stu-id="a1439-148">Text</span></span> |  <span data-ttu-id="a1439-149">A consulta a ser executado.</span><span class="sxs-lookup"><span data-stu-id="a1439-149">The query to run.</span></span> <span data-ttu-id="a1439-150">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="a1439-150">**Required**.</span></span>

## <a name="response"></a><span data-ttu-id="a1439-151">Resposta</span><span class="sxs-lookup"><span data-stu-id="a1439-151">Response</span></span>

<span data-ttu-id="a1439-152">Se tiver êxito, este método retornará 200 OK e _o objeto QueryResponse_ no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="a1439-152">If successful, this method returns 200 OK, and _QueryResponse_ object in the response body.</span></span>


## <a name="example"></a><span data-ttu-id="a1439-153">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a1439-153">Example</span></span>

##### <a name="request"></a><span data-ttu-id="a1439-154">Solicitação</span><span class="sxs-lookup"><span data-stu-id="a1439-154">Request</span></span>

<span data-ttu-id="a1439-155">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="a1439-155">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/advancedqueries/run
```

```json
{
    "Query":"DeviceProcessEvents  
    | where InitiatingProcessFileName =~ 'powershell.exe'
    | where ProcessCommandLine contains 'appdata'
    | project Timestamp, FileName, InitiatingProcessFileName, DeviceId
    | limit 2"
}
```

##### <a name="response"></a><span data-ttu-id="a1439-156">Resposta</span><span class="sxs-lookup"><span data-stu-id="a1439-156">Response</span></span>

<span data-ttu-id="a1439-157">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="a1439-157">Here is an example of the response.</span></span>

>[!NOTE]
><span data-ttu-id="a1439-158">O objeto de resposta mostrado aqui pode ser truncado para brevidade.</span><span class="sxs-lookup"><span data-stu-id="a1439-158">The response object shown here may be truncated for brevity.</span></span> <span data-ttu-id="a1439-159">Todas as propriedades serão retornadas de uma chamada real.</span><span class="sxs-lookup"><span data-stu-id="a1439-159">All of the properties will be returned from an actual call.</span></span>

```json
{
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        },
        {
            "Name": "DeviceId",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-02-05T01:10:26.2648757Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        },
        {
            "Timestamp": "2020-02-05T01:10:26.5614772Z",
            "FileName": "csc.exe",
            "InitiatingProcessFileName": "powershell.exe",
            "DeviceId": "10cbf9182d4e95660362f65cfa67c7731f62fdb3"
        }
    ]
}
```

## <a name="related-topics"></a><span data-ttu-id="a1439-160">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a1439-160">Related topics</span></span>

- [<span data-ttu-id="a1439-161">Introdução às APIs do Microsoft Defender para Endpoint</span><span class="sxs-lookup"><span data-stu-id="a1439-161">Microsoft Defender for Endpoint APIs introduction</span></span>](apis-intro.md)
- [<span data-ttu-id="a1439-162">Busca Avançada do Portal</span><span class="sxs-lookup"><span data-stu-id="a1439-162">Advanced Hunting from Portal</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a1439-163">Busca avançada usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1439-163">Advanced Hunting using PowerShell</span></span>](run-advanced-query-sample-powershell.md)
