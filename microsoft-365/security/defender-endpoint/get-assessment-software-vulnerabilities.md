---
title: Exportar a avaliação de vulnerabilidades de software por dispositivo
description: A resposta da API é por dispositivo e contém software vulnerável instalado em seus dispositivos expostos, bem como quaisquer vulnerabilidades conhecidas nesses produtos de software. Esta tabela também inclui informações sobre o sistema operacional, as IDs do CVE e as informações sobre a severidade da vulnerabilidade.
keywords: api, apis, avaliação de exportação, avaliação por dispositivo, relatório de avaliação de vulnerabilidade, avaliação de vulnerabilidade de dispositivo, relatório de vulnerabilidade de dispositivo, avaliação de configuração segura, relatório de configuração segura, avaliação de vulnerabilidades de software, relatório de vulnerabilidade de software, relatório de vulnerabilidade por máquina,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 849d1ab2bbc3b8f6d883d6041adda5fe4577741d
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789325"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="52fc6-105">Exportar a avaliação de vulnerabilidades de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="52fc6-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="52fc6-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="52fc6-106">**Applies to:**</span></span>

- [<span data-ttu-id="52fc6-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="52fc6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="52fc6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52fc6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="52fc6-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="52fc6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="52fc6-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="52fc6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="52fc6-111">Retorna todas as vulnerabilidades de software conhecidas e seus detalhes para todos os dispositivos, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="52fc6-112">Há diferentes chamadas de API para obter diferentes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="52fc6-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="52fc6-113">Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:</span><span class="sxs-lookup"><span data-stu-id="52fc6-113">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="52fc6-114">[Exportar a avaliação de vulnerabilidades de software OData](#1-export-software-vulnerabilities-assessment-odata)  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="52fc6-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="52fc6-115">Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_.</span><span class="sxs-lookup"><span data-stu-id="52fc6-115">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="52fc6-116">A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="52fc6-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="52fc6-117">[Exportar a avaliação de vulnerabilidades de software por meio de arquivos](#2-export-software-vulnerabilities-assessment-via-files) Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável.</span><span class="sxs-lookup"><span data-stu-id="52fc6-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="52fc6-118">Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52fc6-118">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="52fc6-119">Essa API puxa todos os dados da sua organização como arquivos de download.</span><span class="sxs-lookup"><span data-stu-id="52fc6-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="52fc6-120">A resposta contém URLs para baixar todos os dados do Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="52fc6-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="52fc6-121">Essa API permite baixar todos os dados do Azure Armazenamento a seguir:</span><span class="sxs-lookup"><span data-stu-id="52fc6-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="52fc6-122">Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="52fc6-122">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="52fc6-123">Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.</span><span class="sxs-lookup"><span data-stu-id="52fc6-123">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="52fc6-124">Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos.</span><span class="sxs-lookup"><span data-stu-id="52fc6-124">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="52fc6-125">Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="52fc6-125">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="52fc6-126">A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="52fc6-126">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="52fc6-127">1. Avaliação de vulnerabilidades de software de exportação (OData)</span><span class="sxs-lookup"><span data-stu-id="52fc6-127">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="52fc6-128">Descrição do método API 1.1</span><span class="sxs-lookup"><span data-stu-id="52fc6-128">1.1 API method description</span></span>

<span data-ttu-id="52fc6-129">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-129">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="52fc6-130">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="52fc6-130">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="52fc6-131">Limitações</span><span class="sxs-lookup"><span data-stu-id="52fc6-131">Limitations</span></span>

>- <span data-ttu-id="52fc6-132">O tamanho máximo da página é 200.000.</span><span class="sxs-lookup"><span data-stu-id="52fc6-132">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="52fc6-133">As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="52fc6-133">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="52fc6-134">1.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="52fc6-134">1.2 Permissions</span></span>

<span data-ttu-id="52fc6-135">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="52fc6-135">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52fc6-136">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="52fc6-136">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="52fc6-137">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-137">Permission type</span></span> | <span data-ttu-id="52fc6-138">Permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-138">Permission</span></span> | <span data-ttu-id="52fc6-139">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-139">Permission display name</span></span>
---|---|---
<span data-ttu-id="52fc6-140">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="52fc6-140">Application</span></span> | <span data-ttu-id="52fc6-141">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="52fc6-141">Vulnerability.Read.All</span></span> | <span data-ttu-id="52fc6-142">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="52fc6-142">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="52fc6-143">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="52fc6-143">Delegated (work or school account)</span></span> | <span data-ttu-id="52fc6-144">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="52fc6-144">Vulnerability.Read</span></span> | <span data-ttu-id="52fc6-145">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="52fc6-145">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="52fc6-146">URL 1.3</span><span class="sxs-lookup"><span data-stu-id="52fc6-146">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="52fc6-147">Parâmetros 1.4</span><span class="sxs-lookup"><span data-stu-id="52fc6-147">1.4 Parameters</span></span>

- <span data-ttu-id="52fc6-148">pageSize (padrão = 50.000) – número de resultados em resposta</span><span class="sxs-lookup"><span data-stu-id="52fc6-148">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="52fc6-149">$top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)</span><span class="sxs-lookup"><span data-stu-id="52fc6-149">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="52fc6-150">1.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="52fc6-150">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="52fc6-151">Cada registro é de aproximadamente 1KB de dados.</span><span class="sxs-lookup"><span data-stu-id="52fc6-151">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="52fc6-152">Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.</span><span class="sxs-lookup"><span data-stu-id="52fc6-152">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="52fc6-153">Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="52fc6-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="52fc6-154">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="52fc6-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="52fc6-155">As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.</span><span class="sxs-lookup"><span data-stu-id="52fc6-155">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="52fc6-156">Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="52fc6-156">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="52fc6-157">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="52fc6-157">Property (ID)</span></span> | <span data-ttu-id="52fc6-158">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="52fc6-158">Data type</span></span> | <span data-ttu-id="52fc6-159">Descrição</span><span class="sxs-lookup"><span data-stu-id="52fc6-159">Description</span></span> | <span data-ttu-id="52fc6-160">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="52fc6-160">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="52fc6-161">CveId</span><span class="sxs-lookup"><span data-stu-id="52fc6-161">CveId</span></span> | <span data-ttu-id="52fc6-162">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-162">string</span></span> | <span data-ttu-id="52fc6-163">Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="52fc6-163">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="52fc6-164">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="52fc6-164">CVE-2020-15992</span></span>
<span data-ttu-id="52fc6-165">CvssScore</span><span class="sxs-lookup"><span data-stu-id="52fc6-165">CvssScore</span></span> | <span data-ttu-id="52fc6-166">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-166">string</span></span> | <span data-ttu-id="52fc6-167">A pontuação CVSS do CVE.</span><span class="sxs-lookup"><span data-stu-id="52fc6-167">The CVSS score of the CVE.</span></span> | <span data-ttu-id="52fc6-168">6.2</span><span class="sxs-lookup"><span data-stu-id="52fc6-168">6.2</span></span>
<span data-ttu-id="52fc6-169">DeviceId</span><span class="sxs-lookup"><span data-stu-id="52fc6-169">DeviceId</span></span> | <span data-ttu-id="52fc6-170">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-170">string</span></span> | <span data-ttu-id="52fc6-171">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="52fc6-171">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="52fc6-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="52fc6-172">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="52fc6-173">DeviceName</span><span class="sxs-lookup"><span data-stu-id="52fc6-173">DeviceName</span></span> | <span data-ttu-id="52fc6-174">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-174">string</span></span> | <span data-ttu-id="52fc6-175">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-175">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="52fc6-176">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="52fc6-176">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="52fc6-177">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="52fc6-177">DiskPaths</span></span>  | <span data-ttu-id="52fc6-178">Cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="52fc6-178">Array\[string\]</span></span> | <span data-ttu-id="52fc6-179">Evidência em disco de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-179">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="52fc6-180">[ "C:\Arquivos de Programas (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="52fc6-180">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="52fc6-181">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="52fc6-181">ExploitabilityLevel</span></span> | <span data-ttu-id="52fc6-182">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-182">string</span></span> | <span data-ttu-id="52fc6-183">O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="52fc6-183">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="52fc6-184">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="52fc6-184">ExploitIsInKit</span></span>
<span data-ttu-id="52fc6-185">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="52fc6-185">FirstSeenTimestamp</span></span> | <span data-ttu-id="52fc6-186">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-186">string</span></span> | <span data-ttu-id="52fc6-187">Primeira vez que o CVE deste produto foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-187">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="52fc6-188">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="52fc6-188">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="52fc6-189">Id</span><span class="sxs-lookup"><span data-stu-id="52fc6-189">Id</span></span> | <span data-ttu-id="52fc6-190">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-190">string</span></span> | <span data-ttu-id="52fc6-191">Identificador exclusivo do registro.</span><span class="sxs-lookup"><span data-stu-id="52fc6-191">Unique identifier for the record.</span></span> | <span data-ttu-id="52fc6-192">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="52fc6-192">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="52fc6-193">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="52fc6-193">LastSeenTimestamp</span></span> | <span data-ttu-id="52fc6-194">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-194">string</span></span> | <span data-ttu-id="52fc6-195">A última vez que o CVE foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-195">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="52fc6-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="52fc6-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="52fc6-197">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="52fc6-197">OSPlatform</span></span> | <span data-ttu-id="52fc6-198">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-198">string</span></span> | <span data-ttu-id="52fc6-199">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-199">Platform of the operating system running on the device.</span></span> <span data-ttu-id="52fc6-200">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="52fc6-200">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="52fc6-201">Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="52fc6-201">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="52fc6-202">Windows10</span><span class="sxs-lookup"><span data-stu-id="52fc6-202">Windows10</span></span>
<span data-ttu-id="52fc6-203">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="52fc6-203">RbacGroupName</span></span>  | <span data-ttu-id="52fc6-204">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-204">string</span></span> | <span data-ttu-id="52fc6-205">O grupo controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="52fc6-205">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="52fc6-206">Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído".</span><span class="sxs-lookup"><span data-stu-id="52fc6-206">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="52fc6-207">Se a organização não tiver nenhum grupo RBAC, o valor será "None".</span><span class="sxs-lookup"><span data-stu-id="52fc6-207">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="52fc6-208">Servidores</span><span class="sxs-lookup"><span data-stu-id="52fc6-208">Servers</span></span>
<span data-ttu-id="52fc6-209">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="52fc6-209">RecommendationReference</span></span> | <span data-ttu-id="52fc6-210">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-210">string</span></span> | <span data-ttu-id="52fc6-211">Uma referência à ID de recomendação relacionada a este software.</span><span class="sxs-lookup"><span data-stu-id="52fc6-211">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="52fc6-212">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="52fc6-212">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="52fc6-213">RecommendedSecurityUpdate (opcional)</span><span class="sxs-lookup"><span data-stu-id="52fc6-213">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="52fc6-214">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-214">string</span></span> | <span data-ttu-id="52fc6-215">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="52fc6-215">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="52fc6-216">Atualizações de segurança de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="52fc6-216">April 2020 Security Updates</span></span>
<span data-ttu-id="52fc6-217">RecommendedSecurityUpdateId (opcional)</span><span class="sxs-lookup"><span data-stu-id="52fc6-217">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="52fc6-218">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-218">string</span></span> | <span data-ttu-id="52fc6-219">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="52fc6-219">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="52fc6-220">4550961</span><span class="sxs-lookup"><span data-stu-id="52fc6-220">4550961</span></span>
<span data-ttu-id="52fc6-221">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="52fc6-221">RegistryPaths</span></span>  | <span data-ttu-id="52fc6-222">Cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="52fc6-222">Array\[string\]</span></span> | <span data-ttu-id="52fc6-223">Evidência do Registro de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-223">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="52fc6-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="52fc6-224">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="52fc6-225">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="52fc6-225">SoftwareName</span></span> | <span data-ttu-id="52fc6-226">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-226">string</span></span> | <span data-ttu-id="52fc6-227">Nome do produto de software.</span><span class="sxs-lookup"><span data-stu-id="52fc6-227">Name of the software product.</span></span> | <span data-ttu-id="52fc6-228">chrome</span><span class="sxs-lookup"><span data-stu-id="52fc6-228">chrome</span></span>
<span data-ttu-id="52fc6-229">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="52fc6-229">SoftwareVendor</span></span> | <span data-ttu-id="52fc6-230">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-230">string</span></span> | <span data-ttu-id="52fc6-231">Nome do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="52fc6-231">Name of the software vendor.</span></span> | <span data-ttu-id="52fc6-232">google</span><span class="sxs-lookup"><span data-stu-id="52fc6-232">google</span></span>
<span data-ttu-id="52fc6-233">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="52fc6-233">SoftwareVersion</span></span> | <span data-ttu-id="52fc6-234">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-234">string</span></span> | <span data-ttu-id="52fc6-235">Número da versão do produto de software.</span><span class="sxs-lookup"><span data-stu-id="52fc6-235">Version number of the software product.</span></span> | <span data-ttu-id="52fc6-236">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="52fc6-236">81.0.4044.138</span></span>
<span data-ttu-id="52fc6-237">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="52fc6-237">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="52fc6-238">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-238">string</span></span> | <span data-ttu-id="52fc6-239">Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.</span><span class="sxs-lookup"><span data-stu-id="52fc6-239">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="52fc6-240">Médio</span><span class="sxs-lookup"><span data-stu-id="52fc6-240">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="52fc6-241">1.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="52fc6-241">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="52fc6-242">1.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="52fc6-242">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="52fc6-243">Exemplo de resposta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="52fc6-243">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="52fc6-244">2. Exportar a avaliação de vulnerabilidades de software (por meio de arquivos)</span><span class="sxs-lookup"><span data-stu-id="52fc6-244">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="52fc6-245">Descrição do método API 2.1</span><span class="sxs-lookup"><span data-stu-id="52fc6-245">2.1 API method description</span></span>

<span data-ttu-id="52fc6-246">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52fc6-246">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="52fc6-247">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="52fc6-247">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="52fc6-248">2.1.2 Limitações</span><span class="sxs-lookup"><span data-stu-id="52fc6-248">2.1.2 Limitations</span></span>

<span data-ttu-id="52fc6-249">As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="52fc6-249">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="52fc6-250">2.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="52fc6-250">2.2 Permissions</span></span>

<span data-ttu-id="52fc6-251">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="52fc6-251">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="52fc6-252">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="52fc6-252">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="52fc6-253">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-253">Permission type</span></span> | <span data-ttu-id="52fc6-254">Permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-254">Permission</span></span> | <span data-ttu-id="52fc6-255">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="52fc6-255">Permission display name</span></span>
---|---|---
<span data-ttu-id="52fc6-256">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="52fc6-256">Application</span></span> | <span data-ttu-id="52fc6-257">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="52fc6-257">Vulnerability.Read.All</span></span> | <span data-ttu-id="52fc6-258">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="52fc6-258">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="52fc6-259">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="52fc6-259">Delegated (work or school account)</span></span> | <span data-ttu-id="52fc6-260">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="52fc6-260">Vulnerability.Read</span></span> | <span data-ttu-id="52fc6-261">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="52fc6-261">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="52fc6-262">URL 2.3</span><span class="sxs-lookup"><span data-stu-id="52fc6-262">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="52fc6-263">Parâmetros 2.4</span><span class="sxs-lookup"><span data-stu-id="52fc6-263">2.4 Parameters</span></span>

- <span data-ttu-id="52fc6-264">sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="52fc6-264">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="52fc6-265">2.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="52fc6-265">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="52fc6-266">Os arquivos são gzip compactados & no formato Json de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="52fc6-266">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="52fc6-267">As URLs de download só são válidas por 3 horas; caso contrário, você pode usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="52fc6-267">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="52fc6-268">Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure que seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="52fc6-268">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="52fc6-269">Cada registro é de aproximadamente 1KB de dados.</span><span class="sxs-lookup"><span data-stu-id="52fc6-269">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="52fc6-270">Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.</span><span class="sxs-lookup"><span data-stu-id="52fc6-270">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="52fc6-271">Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="52fc6-271">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="52fc6-272">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="52fc6-272">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="52fc6-273">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="52fc6-273">Property (ID)</span></span> | <span data-ttu-id="52fc6-274">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="52fc6-274">Data type</span></span> | <span data-ttu-id="52fc6-275">Descrição</span><span class="sxs-lookup"><span data-stu-id="52fc6-275">Description</span></span> | <span data-ttu-id="52fc6-276">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="52fc6-276">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="52fc6-277">Exportar arquivos</span><span class="sxs-lookup"><span data-stu-id="52fc6-277">Export files</span></span> | <span data-ttu-id="52fc6-278">cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="52fc6-278">array\[string\]</span></span>  | <span data-ttu-id="52fc6-279">Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.</span><span class="sxs-lookup"><span data-stu-id="52fc6-279">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="52fc6-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="52fc6-280">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="52fc6-281">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="52fc6-281">GeneratedTime</span></span> | <span data-ttu-id="52fc6-282">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="52fc6-282">string</span></span> | <span data-ttu-id="52fc6-283">A hora em que a exportação foi gerada.</span><span class="sxs-lookup"><span data-stu-id="52fc6-283">The time that the export was generated.</span></span> | <span data-ttu-id="52fc6-284">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="52fc6-284">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="52fc6-285">2.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="52fc6-285">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="52fc6-286">2.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="52fc6-286">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="52fc6-287">Exemplo de resposta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="52fc6-287">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="52fc6-288">Confira também</span><span class="sxs-lookup"><span data-stu-id="52fc6-288">See also</span></span>

- [<span data-ttu-id="52fc6-289">Exportar métodos e propriedades de avaliação por dispositivo</span><span class="sxs-lookup"><span data-stu-id="52fc6-289">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="52fc6-290">Exportar avaliação de configuração segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="52fc6-290">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="52fc6-291">Exportar avaliação de inventário de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="52fc6-291">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="52fc6-292">Outros relacionados</span><span class="sxs-lookup"><span data-stu-id="52fc6-292">Other related</span></span>

- [<span data-ttu-id="52fc6-293">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="52fc6-293">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="52fc6-294">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="52fc6-294">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
