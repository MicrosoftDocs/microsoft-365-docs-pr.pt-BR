---
title: Tipo de recurso File
description: Recupere alertas recentes do Microsoft Defender para Endpoint relacionados a arquivos.
keywords: apis, api gráfica, apis com suporte, obter, alertas, recentes
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
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771184"
---
# <a name="file-resource-type"></a><span data-ttu-id="2e4fc-104">Tipo de recurso File</span><span class="sxs-lookup"><span data-stu-id="2e4fc-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2e4fc-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="2e4fc-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="2e4fc-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2e4fc-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2e4fc-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="2e4fc-108">Represente uma entidade de arquivo no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="2e4fc-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e4fc-109">Methods</span></span>
<span data-ttu-id="2e4fc-110">Método</span><span class="sxs-lookup"><span data-stu-id="2e4fc-110">Method</span></span>|<span data-ttu-id="2e4fc-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="2e4fc-111">Return Type</span></span> |<span data-ttu-id="2e4fc-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e4fc-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="2e4fc-113">Obter arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="2e4fc-114">file</span><span class="sxs-lookup"><span data-stu-id="2e4fc-114">file</span></span>](files.md) | <span data-ttu-id="2e4fc-115">Obter um único arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-115">Get a single file</span></span> 
[<span data-ttu-id="2e4fc-116">Listar alertas relacionados ao arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="2e4fc-117">conjunto [alerta](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="2e4fc-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="2e4fc-118">Obter as [entidades](alerts.md) de alerta associadas ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="2e4fc-119">Listar máquinas relacionadas a arquivos</span><span class="sxs-lookup"><span data-stu-id="2e4fc-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="2e4fc-120">[coleção machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="2e4fc-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="2e4fc-121">Obter as [entidades](machine.md) do computador associadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="2e4fc-122">estatísticas de arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="2e4fc-123">Resumo de estatísticas</span><span class="sxs-lookup"><span data-stu-id="2e4fc-123">Statistics summary</span></span> | <span data-ttu-id="2e4fc-124">Recupera a prevalência do arquivo determinado.</span><span class="sxs-lookup"><span data-stu-id="2e4fc-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="2e4fc-125">Propriedades</span><span class="sxs-lookup"><span data-stu-id="2e4fc-125">Properties</span></span>
|<span data-ttu-id="2e4fc-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="2e4fc-126">Property</span></span> | <span data-ttu-id="2e4fc-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-127">Type</span></span>    |   <span data-ttu-id="2e4fc-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e4fc-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="2e4fc-129">sha1</span><span class="sxs-lookup"><span data-stu-id="2e4fc-129">sha1</span></span> | <span data-ttu-id="2e4fc-130">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-130">String</span></span> | <span data-ttu-id="2e4fc-131">Hash sha1 do conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="2e4fc-132">sha256</span><span class="sxs-lookup"><span data-stu-id="2e4fc-132">sha256</span></span> | <span data-ttu-id="2e4fc-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-133">String</span></span> | <span data-ttu-id="2e4fc-134">Hash sha256 do conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="2e4fc-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="2e4fc-135">globalPrevalence</span></span> | <span data-ttu-id="2e4fc-136">Long anulado</span><span class="sxs-lookup"><span data-stu-id="2e4fc-136">Nullable long</span></span> | <span data-ttu-id="2e4fc-137">Prevalência de arquivo em toda a organização</span><span class="sxs-lookup"><span data-stu-id="2e4fc-137">File prevalence across organization</span></span> |
|<span data-ttu-id="2e4fc-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="2e4fc-138">globalFirstObserved</span></span> | <span data-ttu-id="2e4fc-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2e4fc-139">DateTimeOffset</span></span> | <span data-ttu-id="2e4fc-140">Primeira vez que o arquivo foi observado</span><span class="sxs-lookup"><span data-stu-id="2e4fc-140">First time the file was observed</span></span> |
|<span data-ttu-id="2e4fc-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="2e4fc-141">globalLastObserved</span></span> | <span data-ttu-id="2e4fc-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="2e4fc-142">DateTimeOffset</span></span> | <span data-ttu-id="2e4fc-143">Última vez que o arquivo foi observado</span><span class="sxs-lookup"><span data-stu-id="2e4fc-143">Last time the file was observed</span></span> |
|<span data-ttu-id="2e4fc-144">size</span><span class="sxs-lookup"><span data-stu-id="2e4fc-144">size</span></span> | <span data-ttu-id="2e4fc-145">Long anulado</span><span class="sxs-lookup"><span data-stu-id="2e4fc-145">Nullable long</span></span> | <span data-ttu-id="2e4fc-146">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-146">Size of the file</span></span> |
|<span data-ttu-id="2e4fc-147">fileType</span><span class="sxs-lookup"><span data-stu-id="2e4fc-147">fileType</span></span> | <span data-ttu-id="2e4fc-148">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-148">String</span></span> | <span data-ttu-id="2e4fc-149">Tipo do arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-149">Type of the file</span></span> |
|<span data-ttu-id="2e4fc-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="2e4fc-150">isPeFile</span></span> | <span data-ttu-id="2e4fc-151">Booliano</span><span class="sxs-lookup"><span data-stu-id="2e4fc-151">Boolean</span></span> | <span data-ttu-id="2e4fc-152">true se o arquivo for executável portátil (por exemplo, "DLL", "EXE", etc.)</span><span class="sxs-lookup"><span data-stu-id="2e4fc-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="2e4fc-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="2e4fc-153">filePublisher</span></span> | <span data-ttu-id="2e4fc-154">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-154">String</span></span> | <span data-ttu-id="2e4fc-155">Editor de arquivos</span><span class="sxs-lookup"><span data-stu-id="2e4fc-155">File publisher</span></span> |
|<span data-ttu-id="2e4fc-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="2e4fc-156">fileProductName</span></span> | <span data-ttu-id="2e4fc-157">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-157">String</span></span> | <span data-ttu-id="2e4fc-158">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="2e4fc-158">Product name</span></span> |
|<span data-ttu-id="2e4fc-159">signer</span><span class="sxs-lookup"><span data-stu-id="2e4fc-159">signer</span></span> | <span data-ttu-id="2e4fc-160">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-160">String</span></span> | <span data-ttu-id="2e4fc-161">Signante de arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-161">File signer</span></span> |
|<span data-ttu-id="2e4fc-162">emissor</span><span class="sxs-lookup"><span data-stu-id="2e4fc-162">issuer</span></span> | <span data-ttu-id="2e4fc-163">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-163">String</span></span> | <span data-ttu-id="2e4fc-164">Emissor de arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-164">File issuer</span></span> |
|<span data-ttu-id="2e4fc-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="2e4fc-165">signerHash</span></span> | <span data-ttu-id="2e4fc-166">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-166">String</span></span> | <span data-ttu-id="2e4fc-167">Hash do certificado de assinatura</span><span class="sxs-lookup"><span data-stu-id="2e4fc-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="2e4fc-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="2e4fc-168">isValidCertificate</span></span> | <span data-ttu-id="2e4fc-169">Booliano</span><span class="sxs-lookup"><span data-stu-id="2e4fc-169">Boolean</span></span> | <span data-ttu-id="2e4fc-170">Foi verificado com êxito o certificado de assinatura pelo Microsoft Defender para agente do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2e4fc-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="2e4fc-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="2e4fc-171">determinationType</span></span> | <span data-ttu-id="2e4fc-172">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-172">String</span></span> | <span data-ttu-id="2e4fc-173">O tipo de determinação do arquivo</span><span class="sxs-lookup"><span data-stu-id="2e4fc-173">The determination type of the file</span></span> |
|<span data-ttu-id="2e4fc-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="2e4fc-174">determinationValue</span></span> | <span data-ttu-id="2e4fc-175">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2e4fc-175">String</span></span> | <span data-ttu-id="2e4fc-176">Valor de determinação</span><span class="sxs-lookup"><span data-stu-id="2e4fc-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="2e4fc-177">Representação Json</span><span class="sxs-lookup"><span data-stu-id="2e4fc-177">Json representation</span></span>

```json
{
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
