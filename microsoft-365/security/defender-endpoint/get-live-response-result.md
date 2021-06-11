---
title: Obter resultados de resposta ao vivo
description: Saiba como recuperar um resultado de comando de resposta ao vivo específico pelo índice.
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
ms.openlocfilehash: d58fc87d16bb58199c95933d85752008a08a0e81
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879645"
---
#  <a name="get-live-response-results"></a><span data-ttu-id="aee27-104">Obter resultados de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="aee27-104">Get live response results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="aee27-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="aee27-105">**Applies to:**</span></span>
- [<span data-ttu-id="aee27-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="aee27-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!include[Prerelease information](../../includes/prerelease.md)]

><span data-ttu-id="aee27-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="aee27-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="aee27-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="aee27-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="aee27-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="aee27-109">API description</span></span>

<span data-ttu-id="aee27-110">Recupera um resultado de comando de resposta ao vivo específico pelo índice.</span><span class="sxs-lookup"><span data-stu-id="aee27-110">Retrieves a specific live response command result by its index.</span></span>

## <a name="limitations"></a><span data-ttu-id="aee27-111">Limitações</span><span class="sxs-lookup"><span data-stu-id="aee27-111">Limitations</span></span>

1.  <span data-ttu-id="aee27-112">Limitações de taxa para essa API são 100 chamadas por minuto e 1500 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="aee27-112">Rate limitations for this API are 100 calls per minute and 1500 calls per hour.</span></span>

## <a name="permissions"></a><span data-ttu-id="aee27-113">Permissões</span><span class="sxs-lookup"><span data-stu-id="aee27-113">Permissions</span></span>

<span data-ttu-id="aee27-114">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="aee27-114">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="aee27-115">Para saber mais, incluindo como escolher permissões, consulte [Get started](apis-intro.md).</span><span class="sxs-lookup"><span data-stu-id="aee27-115">To learn more, including how to choose permissions, see [Get started](apis-intro.md).</span></span>

| <span data-ttu-id="aee27-116">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="aee27-116">Permission type</span></span>                    | <span data-ttu-id="aee27-117">Permissão</span><span class="sxs-lookup"><span data-stu-id="aee27-117">Permission</span></span>           | <span data-ttu-id="aee27-118">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="aee27-118">Permission display name</span></span>                   |
|------------------------------------|----------------------|-------------------------------------------|
| <span data-ttu-id="aee27-119">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="aee27-119">Application</span></span>                        | <span data-ttu-id="aee27-120">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="aee27-120">Machine.LiveResponse</span></span> | <span data-ttu-id="aee27-121">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="aee27-121">Run live response on a specific machine</span></span> |
| <span data-ttu-id="aee27-122">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="aee27-122">Delegated (work or school account)</span></span> | <span data-ttu-id="aee27-123">Machine.LiveResponse</span><span class="sxs-lookup"><span data-stu-id="aee27-123">Machine.LiveResponse</span></span> | <span data-ttu-id="aee27-124">Executar resposta ao vivo em um computador específico</span><span class="sxs-lookup"><span data-stu-id="aee27-124">Run live response on a specific machine</span></span> |

## <a name="http-request"></a><span data-ttu-id="aee27-125">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="aee27-125">HTTP request</span></span>

```HTTP
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action
id}/GetLiveResponseResultDownloadLink(index={command-index})
```

## <a name="request-headers"></a><span data-ttu-id="aee27-126">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="aee27-126">Request headers</span></span>

| <span data-ttu-id="aee27-127">Nome</span><span class="sxs-lookup"><span data-stu-id="aee27-127">Name</span></span>      | <span data-ttu-id="aee27-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="aee27-128">Type</span></span> | <span data-ttu-id="aee27-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="aee27-129">Description</span></span>               |
|---------------|----------|-------------------------------|
| <span data-ttu-id="aee27-130">Autorização</span><span class="sxs-lookup"><span data-stu-id="aee27-130">Authorization</span></span> | <span data-ttu-id="aee27-131">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="aee27-131">String</span></span>   | <span data-ttu-id="aee27-p103">{token} de portador. Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="aee27-p103">Bearer {token}. Required.</span></span> |

## <a name="request-body"></a><span data-ttu-id="aee27-134">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="aee27-134">Request body</span></span>

<span data-ttu-id="aee27-135">Vazio</span><span class="sxs-lookup"><span data-stu-id="aee27-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="aee27-136">Resposta</span><span class="sxs-lookup"><span data-stu-id="aee27-136">Response</span></span>

<span data-ttu-id="aee27-137">Se tiver êxito, este método retornará 200, código de resposta Ok com o objeto que contém o link para o resultado do comando na *propriedade value.*</span><span class="sxs-lookup"><span data-stu-id="aee27-137">If successful, this method returns 200, Ok response code with object that holds the link to the command result in the *value* property.</span></span> <span data-ttu-id="aee27-138">Esse link é válido por 30 minutos e deve ser usado imediatamente para baixar o pacote para um armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="aee27-138">This link is valid for 30 minutes and should be used immediately for downloading the package to a local storage.</span></span> <span data-ttu-id="aee27-139">Um link expirado pode ser re-criado por outra chamada e não é necessário executar a resposta ao vivo novamente.</span><span class="sxs-lookup"><span data-stu-id="aee27-139">An expired link can be re-created by another call, and there is no need to run live response again.</span></span>

<span data-ttu-id="aee27-140">*Propriedades de transcrição de runscript:*</span><span class="sxs-lookup"><span data-stu-id="aee27-140">*Runscript transcript properties:*</span></span>

| <span data-ttu-id="aee27-141">Propriedade</span><span class="sxs-lookup"><span data-stu-id="aee27-141">Property</span></span>  | <span data-ttu-id="aee27-142">Descrição</span><span class="sxs-lookup"><span data-stu-id="aee27-142">Description</span></span>                       |
|---------------|---------------------------------------|
| <span data-ttu-id="aee27-143">name</span><span class="sxs-lookup"><span data-stu-id="aee27-143">name</span></span>          | <span data-ttu-id="aee27-144">Nome do script executado</span><span class="sxs-lookup"><span data-stu-id="aee27-144">Executed script name</span></span>                  |
| <span data-ttu-id="aee27-145">exit_code</span><span class="sxs-lookup"><span data-stu-id="aee27-145">exit_code</span></span>     | <span data-ttu-id="aee27-146">Código de saída de script executado</span><span class="sxs-lookup"><span data-stu-id="aee27-146">Executed script exit code</span></span>             |
| <span data-ttu-id="aee27-147">script_output</span><span class="sxs-lookup"><span data-stu-id="aee27-147">script_output</span></span> | <span data-ttu-id="aee27-148">Saída padrão de script executada</span><span class="sxs-lookup"><span data-stu-id="aee27-148">Executed script standard output</span></span>       |
| <span data-ttu-id="aee27-149">script_error</span><span class="sxs-lookup"><span data-stu-id="aee27-149">script_error</span></span>  | <span data-ttu-id="aee27-150">Saída de erro padrão de script executada</span><span class="sxs-lookup"><span data-stu-id="aee27-150">Executed script standard error output</span></span> |

## <a name="example"></a><span data-ttu-id="aee27-151">Exemplo</span><span class="sxs-lookup"><span data-stu-id="aee27-151">Example</span></span>

<span data-ttu-id="aee27-152">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="aee27-152">**Request**</span></span>

<span data-ttu-id="aee27-153">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="aee27-153">Here is an example of the request.</span></span>

```HTTP
GET
https://api.securitycenter.microsoft.com/api/machineactions/988cc94e-7a8f-4b28-ab65-54970c5d5018/GetLiveResponseResultDownloadLink(index=0)
```

<span data-ttu-id="aee27-154">**Response**</span><span class="sxs-lookup"><span data-stu-id="aee27-154">**Response**</span></span>

<span data-ttu-id="aee27-155">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="aee27-155">Here is an example of the response.</span></span>

<span data-ttu-id="aee27-156">HTTP/1.1 200 Ok</span><span class="sxs-lookup"><span data-stu-id="aee27-156">HTTP/1.1 200 Ok</span></span>

<span data-ttu-id="aee27-157">Tipo de conteúdo: application/json</span><span class="sxs-lookup"><span data-stu-id="aee27-157">Content-type: application/json</span></span>

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "https://core.windows.net/investigation-actions-data/ID/CustomPlaybookCommandOutput/4ed5e7807ad1fe59b00b664fe06a0f07?se=2021-02-04T16%3A13%3A50Z&sp=r&sv=2019-07-07&sr=b&sig=1dYGe9rPvUlXBPvYSmr6/OLXPY98m8qWqfIQCBbyZTY%3D"
}
```

<span data-ttu-id="aee27-158">*Conteúdo do arquivo:*</span><span class="sxs-lookup"><span data-stu-id="aee27-158">*File content:*</span></span> 

```JSON
{
    "script_name": "minidump.ps1",
    "exit_code": 0,
    "script_output": "Transcript started, output file is C:\\ProgramData\\Microsoft\\Windows Defender Advanced Threat Protection\\Temp\\PSScriptOutputs\\PSScript_Transcript_{TRANSCRIPT_ID}.txt
C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip\n51 MB\n\u0000\u0000\u0000",
    "script_error":""
}
```

## <a name="related-topics"></a><span data-ttu-id="aee27-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aee27-159">Related topics</span></span>

- [<span data-ttu-id="aee27-160">Obter API de ação de máquina</span><span class="sxs-lookup"><span data-stu-id="aee27-160">Get machine action API</span></span>](get-machineaction-object.md)
- [<span data-ttu-id="aee27-161">Cancelar ação do computador</span><span class="sxs-lookup"><span data-stu-id="aee27-161">Cancel machine action</span></span>](cancel-machine-action.md)
- [<span data-ttu-id="aee27-162">Executar resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="aee27-162">Run live response</span></span>](run-live-response.md) 
