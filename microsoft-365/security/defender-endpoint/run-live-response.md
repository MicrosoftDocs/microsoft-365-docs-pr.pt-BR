---
title: Executar comandos de resposta ao vivo em um dispositivo
description: Saiba como executar uma sequência de comandos de resposta ao vivo em um dispositivo.
keywords: apis, api gráfica, apis com suporte, upload na biblioteca
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879638"
---
#  <a name="run-live-response-commands-on-a-device"></a><span data-ttu-id="1d684-104">Executar comandos de resposta ao vivo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="1d684-104">Run live response commands on a device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1d684-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1d684-105">**Applies to:**</span></span>
- [<span data-ttu-id="1d684-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="1d684-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="1d684-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="1d684-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1d684-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="1d684-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="1d684-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="1d684-109">API description</span></span>

<span data-ttu-id="1d684-110">Executa uma sequência de comandos de resposta ao vivo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="1d684-110">Runs a sequence of live response commands on a device</span></span>

## <a name="limitations"></a><span data-ttu-id="1d684-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="1d684-111">Limitations</span></span>

1.  <span data-ttu-id="1d684-112">Limitações de taxa para essa API são 10 chamadas por minuto (solicitações adicionais são atendidas com HTTP 429).</span><span class="sxs-lookup"><span data-stu-id="1d684-112">Rate limitations for this API are 10 calls per minute (additional requests are responded with HTTP 429).</span></span>

2.  <span data-ttu-id="1d684-113">25 sessões em execução simultâneas (solicitações que excedem o limite de limitação receberão uma resposta "429 - Solicitações excessivas").</span><span class="sxs-lookup"><span data-stu-id="1d684-113">25 concurrently running sessions (requests exceeding the throttling limit will receive a "429 - Too many requests" response).</span></span>

3.  <span data-ttu-id="1d684-114">Se o computador não estiver disponível, a sessão será en fila por até 3 dias.</span><span class="sxs-lookup"><span data-stu-id="1d684-114">If the machine is not available, the session will be queued for up to 3 days.</span></span>

4.  <span data-ttu-id="1d684-115">Tempo de tempo de comando RunScript após 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="1d684-115">RunScript command timeouts after 10 minutes.</span></span>

5.  <span data-ttu-id="1d684-116">Quando um comando de resposta ao vivo falhar, todas as ações seguidas não serão executadas.</span><span class="sxs-lookup"><span data-stu-id="1d684-116">When a live response command fails all followed actions will not be executed.</span></span>

## <a name="permissions"></a><span data-ttu-id="1d684-117">Permissões</span><span class="sxs-lookup"><span data-stu-id="1d684-117">Permissions</span></span>

<span data-ttu-id="1d684-118">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="1d684-118">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="1d684-119">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="1d684-119">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="1d684-120">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="1d684-120">Permission type</span></span>                    | <span data-ttu-id="1d684-121">Permissão</span><span class="sxs-lookup"><span data-stu-id="1d684-121">Permission</span></span>           | <span data-ttu-id="1d684-122">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="1d684-122">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="1d684-123">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="1d684-123">Application</span></span>                        | <span data-ttu-id="1d684-124">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="1d684-124">Machine.LiveResponse</span></span> | <span data-ttu-id="1d684-125">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="1d684-125">Run live response on a specific machine</span></span> |
| <span data-ttu-id="1d684-126">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="1d684-126">Delegated (work or school account)</span></span> | <span data-ttu-id="1d684-127">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="1d684-127">Machine.LiveResponse</span></span> | <span data-ttu-id="1d684-128">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="1d684-128">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="1d684-129">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="1d684-129">HTTP request</span></span>

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a><span data-ttu-id="1d684-130">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="1d684-130">Request headers</span></span>

| <span data-ttu-id="1d684-131">Nome</span><span class="sxs-lookup"><span data-stu-id="1d684-131">Name</span></span>      | <span data-ttu-id="1d684-132">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d684-132">Type</span></span> | <span data-ttu-id="1d684-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d684-133">Description</span></span>                 |
|---------------|----------|---------------------------------|
| <span data-ttu-id="1d684-134">Autorização</span><span class="sxs-lookup"><span data-stu-id="1d684-134">Authorization</span></span> | <span data-ttu-id="1d684-135">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1d684-135">String</span></span>   | <span data-ttu-id="1d684-136">Portador\<token>\.</span><span class="sxs-lookup"><span data-stu-id="1d684-136">Bearer\<token>\.</span></span> <span data-ttu-id="1d684-137">Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="1d684-137">Required.</span></span>   |
| <span data-ttu-id="1d684-138">Content-Type</span><span class="sxs-lookup"><span data-stu-id="1d684-138">Content-Type</span></span>  | <span data-ttu-id="1d684-139">string</span><span class="sxs-lookup"><span data-stu-id="1d684-139">string</span></span>   | <span data-ttu-id="1d684-p104">application/json. Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="1d684-p104">application/json. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="1d684-142">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="1d684-142">Request body</span></span>

| <span data-ttu-id="1d684-143">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="1d684-143">Parameter</span></span> | <span data-ttu-id="1d684-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="1d684-144">Type</span></span> | <span data-ttu-id="1d684-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d684-145">Description</span></span>                                                        |
|---------------|----------|------------------------------------------------------------------------|
| <span data-ttu-id="1d684-146">Comentário</span><span class="sxs-lookup"><span data-stu-id="1d684-146">Comment</span></span>       | <span data-ttu-id="1d684-147">String</span><span class="sxs-lookup"><span data-stu-id="1d684-147">String</span></span>   | <span data-ttu-id="1d684-148">Comentário para associar à ação.</span><span class="sxs-lookup"><span data-stu-id="1d684-148">Comment to associate with the action.</span></span>                                 |
| <span data-ttu-id="1d684-149">Comandos</span><span class="sxs-lookup"><span data-stu-id="1d684-149">Commands</span></span>      | <span data-ttu-id="1d684-150">Matriz</span><span class="sxs-lookup"><span data-stu-id="1d684-150">Array</span></span>    | <span data-ttu-id="1d684-151">Comandos a executar.</span><span class="sxs-lookup"><span data-stu-id="1d684-151">Commands to run.</span></span> <span data-ttu-id="1d684-152">Os valores permitidos são PutFile, RunScript, GetFile.</span><span class="sxs-lookup"><span data-stu-id="1d684-152">Allowed values are PutFile, RunScript, GetFile.</span></span> |

<span data-ttu-id="1d684-153">Comandos:</span><span class="sxs-lookup"><span data-stu-id="1d684-153">Commands:</span></span>

| <span data-ttu-id="1d684-154">Tipo de Comando</span><span class="sxs-lookup"><span data-stu-id="1d684-154">Command Type</span></span> | <span data-ttu-id="1d684-155">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1d684-155">Parameters</span></span>                                                                          | <span data-ttu-id="1d684-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="1d684-156">Description</span></span>                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1d684-157">PutFile</span><span class="sxs-lookup"><span data-stu-id="1d684-157">PutFile</span></span>      | <span data-ttu-id="1d684-158">Chave: FileName</span><span class="sxs-lookup"><span data-stu-id="1d684-158">Key: FileName</span></span>  <br><br>  <span data-ttu-id="1d684-159">Valor: \<file name\></span><span class="sxs-lookup"><span data-stu-id="1d684-159">Value: \<file name\></span></span>                                                                          | <span data-ttu-id="1d684-160">Coloca um arquivo da biblioteca no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d684-160">Puts a file from the library to the device.</span></span> <span data-ttu-id="1d684-161">Os arquivos são salvos em uma pasta de trabalho e são excluídos quando o dispositivo é reiniciado por padrão.</span><span class="sxs-lookup"><span data-stu-id="1d684-161">Files are saved in a working folder and are deleted when the device restarts by default.</span></span>
| <span data-ttu-id="1d684-162">RunScript</span><span class="sxs-lookup"><span data-stu-id="1d684-162">RunScript</span></span>    | <span data-ttu-id="1d684-163">Chave: ScriptName</span><span class="sxs-lookup"><span data-stu-id="1d684-163">Key: ScriptName</span></span><br><span data-ttu-id="1d684-164">Valor: \<Script from library\></span><span class="sxs-lookup"><span data-stu-id="1d684-164">Value: \<Script from library\></span></span> <br><br> <span data-ttu-id="1d684-165">Chave: Args</span><span class="sxs-lookup"><span data-stu-id="1d684-165">Key: Args</span></span>  <br> <span data-ttu-id="1d684-166">Valor: \<Script arguments\></span><span class="sxs-lookup"><span data-stu-id="1d684-166">Value: \<Script arguments\></span></span>                          | <span data-ttu-id="1d684-167">Executa um script da biblioteca em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d684-167">Runs a script from the library on a device.</span></span>    <br><br>  <span data-ttu-id="1d684-168">O parâmetro Args é passado para seu script.</span><span class="sxs-lookup"><span data-stu-id="1d684-168">The Args parameter is passed to your script.</span></span> <br><br> <span data-ttu-id="1d684-169">Tempo de duração após 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="1d684-169">Timeouts after 10 minutes.</span></span>     
| <span data-ttu-id="1d684-170">GetFile</span><span class="sxs-lookup"><span data-stu-id="1d684-170">GetFile</span></span>      | <span data-ttu-id="1d684-171">Chave: Caminho</span><span class="sxs-lookup"><span data-stu-id="1d684-171">Key: Path</span></span> <br> <span data-ttu-id="1d684-172">Valor: \<File path\></span><span class="sxs-lookup"><span data-stu-id="1d684-172">Value: \<File path\></span></span>                                                        | <span data-ttu-id="1d684-173">Coletar arquivo de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d684-173">Collect file from a device.</span></span> <span data-ttu-id="1d684-174">OBSERVAÇÃO: backslashes in path deve ser escape.</span><span class="sxs-lookup"><span data-stu-id="1d684-174">NOTE: Backslashes in path must be escaped.</span></span>                                                                      |

## <a name="response"></a><span data-ttu-id="1d684-175">Resposta</span><span class="sxs-lookup"><span data-stu-id="1d684-175">Response</span></span>

-   <span data-ttu-id="1d684-176">Se tiver êxito, este método retornará 200, ok.</span><span class="sxs-lookup"><span data-stu-id="1d684-176">If successful, this method returns 200, Ok.</span></span>
    <span data-ttu-id="1d684-177">Entidade Action.</span><span class="sxs-lookup"><span data-stu-id="1d684-177">Action entity.</span></span> <span data-ttu-id="1d684-178">Se o computador com a ID especificada não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="1d684-178">If machine with the specified ID was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="1d684-179">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1d684-179">Example</span></span>

<span data-ttu-id="1d684-180">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="1d684-180">**Request**</span></span>

<span data-ttu-id="1d684-181">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="1d684-181">Here is an example of the request.</span></span>

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
<span data-ttu-id="1d684-182">**JSON**</span><span class="sxs-lookup"><span data-stu-id="1d684-182">**JSON**</span></span>

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

<span data-ttu-id="1d684-183">**Response**</span><span class="sxs-lookup"><span data-stu-id="1d684-183">**Response**</span></span>

<span data-ttu-id="1d684-184">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="1d684-184">Here is an example of the response.</span></span>

```HTTP
HTTP/1.1 200 Ok
```

<span data-ttu-id="1d684-185">Tipo de conteúdo: application/json</span><span class="sxs-lookup"><span data-stu-id="1d684-185">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a><span data-ttu-id="1d684-186">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1d684-186">Related topics</span></span>
- [<span data-ttu-id="1d684-187">Obter API de ação de máquina</span><span class="sxs-lookup"><span data-stu-id="1d684-187">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="1d684-188">Obter resultado de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="1d684-188">Get live response result</span></span>](get-live-response-result.md)
- [<span data-ttu-id="1d684-189">Cancelar ação do computador</span><span class="sxs-lookup"><span data-stu-id="1d684-189">Cancel machine action</span></span>](cancel-machine-action.md)
