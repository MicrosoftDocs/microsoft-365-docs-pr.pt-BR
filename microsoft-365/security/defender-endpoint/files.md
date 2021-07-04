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
ms.openlocfilehash: 83a011e649a7289f62acd6a8d985f020b27b1e10
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290010"
---
# <a name="file-resource-type"></a><span data-ttu-id="f5d90-104">Tipo de recurso File</span><span class="sxs-lookup"><span data-stu-id="f5d90-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f5d90-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f5d90-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f5d90-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f5d90-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5d90-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f5d90-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

<span data-ttu-id="f5d90-108">Represente uma entidade de arquivo no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f5d90-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="f5d90-109">Métodos</span><span class="sxs-lookup"><span data-stu-id="f5d90-109">Methods</span></span>

<span data-ttu-id="f5d90-110">Método</span><span class="sxs-lookup"><span data-stu-id="f5d90-110">Method</span></span>|<span data-ttu-id="f5d90-111">Tipo de retorno</span><span class="sxs-lookup"><span data-stu-id="f5d90-111">Return Type</span></span> |<span data-ttu-id="f5d90-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5d90-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f5d90-113">Obter arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="f5d90-114">file</span><span class="sxs-lookup"><span data-stu-id="f5d90-114">file</span></span>](files.md) | <span data-ttu-id="f5d90-115">Obter um único arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-115">Get a single file</span></span> 
[<span data-ttu-id="f5d90-116">Listar alertas relacionados ao arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="f5d90-117">conjunto [alerta](alerts.md) </span><span class="sxs-lookup"><span data-stu-id="f5d90-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="f5d90-118">Obter as [entidades](alerts.md) de alerta associadas ao arquivo.</span><span class="sxs-lookup"><span data-stu-id="f5d90-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="f5d90-119">Listar máquinas relacionadas a arquivos</span><span class="sxs-lookup"><span data-stu-id="f5d90-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="f5d90-120">[coleção machine](machine.md)</span><span class="sxs-lookup"><span data-stu-id="f5d90-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="f5d90-121">Obter as [entidades](machine.md) do computador associadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="f5d90-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="f5d90-122">estatísticas de arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="f5d90-123">Resumo de estatísticas</span><span class="sxs-lookup"><span data-stu-id="f5d90-123">Statistics summary</span></span> | <span data-ttu-id="f5d90-124">Recupera a prevalência do arquivo determinado.</span><span class="sxs-lookup"><span data-stu-id="f5d90-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="f5d90-125">Propriedades</span><span class="sxs-lookup"><span data-stu-id="f5d90-125">Properties</span></span>

|<span data-ttu-id="f5d90-126">Propriedade</span><span class="sxs-lookup"><span data-stu-id="f5d90-126">Property</span></span> | <span data-ttu-id="f5d90-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="f5d90-127">Type</span></span> | <span data-ttu-id="f5d90-128">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5d90-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="f5d90-129">sha1</span><span class="sxs-lookup"><span data-stu-id="f5d90-129">sha1</span></span> | <span data-ttu-id="f5d90-130">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-130">String</span></span> | <span data-ttu-id="f5d90-131">Hash sha1 do conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="f5d90-132">sha256</span><span class="sxs-lookup"><span data-stu-id="f5d90-132">sha256</span></span> | <span data-ttu-id="f5d90-133">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-133">String</span></span> | <span data-ttu-id="f5d90-134">Hash sha256 do conteúdo do arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="f5d90-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="f5d90-135">globalPrevalence</span></span> | <span data-ttu-id="f5d90-136">Long anulado</span><span class="sxs-lookup"><span data-stu-id="f5d90-136">Nullable long</span></span> | <span data-ttu-id="f5d90-137">Prevalência de arquivo em toda a organização</span><span class="sxs-lookup"><span data-stu-id="f5d90-137">File prevalence across organization</span></span> |
|<span data-ttu-id="f5d90-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="f5d90-138">globalFirstObserved</span></span> | <span data-ttu-id="f5d90-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f5d90-139">DateTimeOffset</span></span> | <span data-ttu-id="f5d90-140">Primeira vez que o arquivo foi observado</span><span class="sxs-lookup"><span data-stu-id="f5d90-140">First time the file was observed</span></span> |
|<span data-ttu-id="f5d90-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="f5d90-141">globalLastObserved</span></span> | <span data-ttu-id="f5d90-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f5d90-142">DateTimeOffset</span></span> | <span data-ttu-id="f5d90-143">Última vez que o arquivo foi observado</span><span class="sxs-lookup"><span data-stu-id="f5d90-143">Last time the file was observed</span></span> |
|<span data-ttu-id="f5d90-144">size</span><span class="sxs-lookup"><span data-stu-id="f5d90-144">size</span></span> | <span data-ttu-id="f5d90-145">Long anulado</span><span class="sxs-lookup"><span data-stu-id="f5d90-145">Nullable long</span></span> | <span data-ttu-id="f5d90-146">Tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-146">Size of the file</span></span> |
|<span data-ttu-id="f5d90-147">fileType</span><span class="sxs-lookup"><span data-stu-id="f5d90-147">fileType</span></span> | <span data-ttu-id="f5d90-148">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-148">String</span></span> | <span data-ttu-id="f5d90-149">Tipo do arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-149">Type of the file</span></span> |
|<span data-ttu-id="f5d90-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="f5d90-150">isPeFile</span></span> | <span data-ttu-id="f5d90-151">Booliano</span><span class="sxs-lookup"><span data-stu-id="f5d90-151">Boolean</span></span> | <span data-ttu-id="f5d90-152">true se o arquivo for executável portátil (por exemplo, "DLL", "EXE", etc.)</span><span class="sxs-lookup"><span data-stu-id="f5d90-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="f5d90-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="f5d90-153">filePublisher</span></span> | <span data-ttu-id="f5d90-154">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-154">String</span></span> | <span data-ttu-id="f5d90-155">Editor de arquivos</span><span class="sxs-lookup"><span data-stu-id="f5d90-155">File publisher</span></span> |
|<span data-ttu-id="f5d90-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="f5d90-156">fileProductName</span></span> | <span data-ttu-id="f5d90-157">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-157">String</span></span> | <span data-ttu-id="f5d90-158">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="f5d90-158">Product name</span></span> |
|<span data-ttu-id="f5d90-159">signer</span><span class="sxs-lookup"><span data-stu-id="f5d90-159">signer</span></span> | <span data-ttu-id="f5d90-160">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-160">String</span></span> | <span data-ttu-id="f5d90-161">Signante de arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-161">File signer</span></span> |
|<span data-ttu-id="f5d90-162">emissor</span><span class="sxs-lookup"><span data-stu-id="f5d90-162">issuer</span></span> | <span data-ttu-id="f5d90-163">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-163">String</span></span> | <span data-ttu-id="f5d90-164">Emissor de arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-164">File issuer</span></span> |
|<span data-ttu-id="f5d90-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="f5d90-165">signerHash</span></span> | <span data-ttu-id="f5d90-166">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-166">String</span></span> | <span data-ttu-id="f5d90-167">Hash do certificado de assinatura</span><span class="sxs-lookup"><span data-stu-id="f5d90-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="f5d90-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="f5d90-168">isValidCertificate</span></span> | <span data-ttu-id="f5d90-169">Booliano</span><span class="sxs-lookup"><span data-stu-id="f5d90-169">Boolean</span></span> | <span data-ttu-id="f5d90-170">Foi verificado com êxito o certificado de assinatura pelo Microsoft Defender para agente do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f5d90-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="f5d90-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="f5d90-171">determinationType</span></span> | <span data-ttu-id="f5d90-172">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-172">String</span></span> | <span data-ttu-id="f5d90-173">O tipo de determinação do arquivo</span><span class="sxs-lookup"><span data-stu-id="f5d90-173">The determination type of the file</span></span> |
|<span data-ttu-id="f5d90-174">determinationValue</span><span class="sxs-lookup"><span data-stu-id="f5d90-174">determinationValue</span></span> | <span data-ttu-id="f5d90-175">String</span><span class="sxs-lookup"><span data-stu-id="f5d90-175">String</span></span> | <span data-ttu-id="f5d90-176">Valor de determinação</span><span class="sxs-lookup"><span data-stu-id="f5d90-176">Determination value</span></span> |

## <a name="json-representation"></a><span data-ttu-id="f5d90-177">Representação Json</span><span class="sxs-lookup"><span data-stu-id="f5d90-177">Json representation</span></span>

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
