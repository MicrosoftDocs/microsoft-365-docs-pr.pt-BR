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
ms.openlocfilehash: ea05d37ebcd0953dd109f524775a55cf8d6b3683
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984959"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a><span data-ttu-id="8ec6e-105">Exportar a avaliação de vulnerabilidades de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-105">Export software vulnerabilities assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8ec6e-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8ec6e-106">**Applies to:**</span></span>

- [<span data-ttu-id="8ec6e-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8ec6e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8ec6e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8ec6e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8ec6e-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8ec6e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8ec6e-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="8ec6e-111">Retorna todas as vulnerabilidades de software conhecidas e seus detalhes para todos os dispositivos, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-111">Returns all known software vulnerabilities and their details for all devices, on a per-device basis.</span></span>

<span data-ttu-id="8ec6e-112">Há diferentes chamadas de API para obter diferentes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-112">There are different API calls to get different types of data.</span></span> <span data-ttu-id="8ec6e-113">Como a quantidade de dados pode ser muito grande, há duas maneiras de recuperá-las:</span><span class="sxs-lookup"><span data-stu-id="8ec6e-113">Because the amount of data can be very large, there are two ways it can be retrieved:</span></span>

1. <span data-ttu-id="8ec6e-114">[Exportar a avaliação de vulnerabilidades de software OData](#1-export-software-vulnerabilities-assessment-odata)  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-114">[Export software vulnerabilities assessment OData](#1-export-software-vulnerabilities-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="8ec6e-115">Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-115">This method is best for _small organizations with less than 100 K devices_.</span></span> <span data-ttu-id="8ec6e-116">A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-116">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

2. <span data-ttu-id="8ec6e-117">[Exportar a avaliação de vulnerabilidades de software por meio de arquivos](#2-export-software-vulnerabilities-assessment-via-files) Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-117">[Export software vulnerabilities assessment via files](#2-export-software-vulnerabilities-assessment-via-files) This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="8ec6e-118">Os arquivos via são recomendados para grandes organizações, com mais de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-118">Via-files is recommended for large organizations, with more than 100 K devices.</span></span> <span data-ttu-id="8ec6e-119">Essa API puxa todos os dados da sua organização como arquivos de download.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-119">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="8ec6e-120">A resposta contém URLs para baixar todos os dados do Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-120">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="8ec6e-121">Essa API permite baixar todos os dados do Armazenamento do Azure da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8ec6e-121">This API enables you to download all your data from Azure Storage as follows:</span></span>

   - <span data-ttu-id="8ec6e-122">Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-122">Call the API to get a list of download URLs with all your organization data.</span></span>

   - <span data-ttu-id="8ec6e-123">Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-123">Download all the files using the download URLs and process the data as you like.</span></span>

3. <span data-ttu-id="8ec6e-124">[Avaliação de vulnerabilidades de software de exportação delta OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Retorna uma tabela com uma entrada para cada combinação exclusiva de: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId e EventTimestamp.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-124">[Delta export software vulnerabilities assessment OData](#3-delta-export-software-vulnerabilities-assessment-odata)  Returns a table with an entry for every unique combination of: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId, and EventTimestamp.</span></span>
<span data-ttu-id="8ec6e-125">A API coleta dados em sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-125">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="8ec6e-126">A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-126">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <br><br> <span data-ttu-id="8ec6e-127">Ao contrário da avaliação completa de vulnerabilidades de software (OData) - que é usada para obter um instantâneo inteiro da avaliação de vulnerabilidades de software da sua organização por dispositivo - a chamada da API OData de exportação delta é usada para buscar apenas as alterações que aconteceram entre uma data selecionada e a data atual (a chamada da API "delta").</span><span class="sxs-lookup"><span data-stu-id="8ec6e-127">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="8ec6e-128">Em vez de obter uma exportação completa com uma grande quantidade de dados sempre, você só obterá informações específicas sobre vulnerabilidades novas, fixas e atualizadas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-128">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="8ec6e-129">A chamada de API OData de exportação delta também pode ser usada para calcular KPIs diferentes, como "quantas vulnerabilidades foram corrigidas?"</span><span class="sxs-lookup"><span data-stu-id="8ec6e-129">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="8ec6e-130">ou "quantas novas vulnerabilidades foram adicionadas à minha organização?"</span><span class="sxs-lookup"><span data-stu-id="8ec6e-130">or “how many new vulnerabilities were added to my organization?”</span></span> <br><br> <span data-ttu-id="8ec6e-131">Como a chamada da API OData de exportação delta para vulnerabilidades de software retorna dados apenas para um intervalo de datas direcionado, ela não é considerada uma _exportação completa._</span><span class="sxs-lookup"><span data-stu-id="8ec6e-131">Because the Delta export OData API call for software vulnerabilities returns data for only a targeted date range, it is not considered a _full export_.</span></span>

<span data-ttu-id="8ec6e-132">Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-132">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="8ec6e-133">Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-133">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="8ec6e-134">A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="8ec6e-134">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="8ec6e-135">1. Avaliação de vulnerabilidades de software de exportação (OData)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-135">1. Export software vulnerabilities assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="8ec6e-136">Descrição do método API 1.1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-136">1.1 API method description</span></span>

<span data-ttu-id="8ec6e-137">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-137">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8ec6e-138">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-138">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="limitations"></a><span data-ttu-id="8ec6e-139">Limitações</span><span class="sxs-lookup"><span data-stu-id="8ec6e-139">Limitations</span></span>

>- <span data-ttu-id="8ec6e-140">O tamanho máximo da página é 200.000.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-140">Maximum page size is 200,000.</span></span>
>
>- <span data-ttu-id="8ec6e-141">As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-141">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="8ec6e-142">1.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="8ec6e-142">1.2 Permissions</span></span>

<span data-ttu-id="8ec6e-143">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-143">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ec6e-144">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-144">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8ec6e-145">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-145">Permission type</span></span> | <span data-ttu-id="8ec6e-146">Permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-146">Permission</span></span> | <span data-ttu-id="8ec6e-147">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-147">Permission display name</span></span>
---|---|---
<span data-ttu-id="8ec6e-148">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-148">Application</span></span> | <span data-ttu-id="8ec6e-149">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8ec6e-149">Vulnerability.Read.All</span></span> | <span data-ttu-id="8ec6e-150">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-150">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8ec6e-151">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-151">Delegated (work or school account)</span></span> | <span data-ttu-id="8ec6e-152">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8ec6e-152">Vulnerability.Read</span></span> | <span data-ttu-id="8ec6e-153">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-153">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="8ec6e-154">URL 1.3</span><span class="sxs-lookup"><span data-stu-id="8ec6e-154">1.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="8ec6e-155">Parâmetros 1.4</span><span class="sxs-lookup"><span data-stu-id="8ec6e-155">1.4 Parameters</span></span>

- <span data-ttu-id="8ec6e-156">pageSize (padrão = 50.000) – número de resultados em resposta</span><span class="sxs-lookup"><span data-stu-id="8ec6e-156">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="8ec6e-157">$top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-157">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="8ec6e-158">1.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="8ec6e-158">1.5 Properties</span></span>
>
>[!Note]
>
>- <span data-ttu-id="8ec6e-159">Cada registro é de aproximadamente 1KB de dados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-159">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="8ec6e-160">Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-160">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="8ec6e-161">Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-161">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8ec6e-162">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-162">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>
>- <span data-ttu-id="8ec6e-163">As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-163">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="8ec6e-164">Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-164">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>

<span data-ttu-id="8ec6e-165">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-165">Property (ID)</span></span> | <span data-ttu-id="8ec6e-166">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8ec6e-166">Data type</span></span> | <span data-ttu-id="8ec6e-167">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ec6e-167">Description</span></span> | <span data-ttu-id="8ec6e-168">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="8ec6e-168">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8ec6e-169">CveId</span><span class="sxs-lookup"><span data-stu-id="8ec6e-169">CveId</span></span> | <span data-ttu-id="8ec6e-170">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-170">string</span></span> | <span data-ttu-id="8ec6e-171">Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-171">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="8ec6e-172">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="8ec6e-172">CVE-2020-15992</span></span>
<span data-ttu-id="8ec6e-173">CvssScore</span><span class="sxs-lookup"><span data-stu-id="8ec6e-173">CvssScore</span></span> | <span data-ttu-id="8ec6e-174">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-174">string</span></span> | <span data-ttu-id="8ec6e-175">A pontuação CVSS do CVE.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-175">The CVSS score of the CVE.</span></span> | <span data-ttu-id="8ec6e-176">6.2</span><span class="sxs-lookup"><span data-stu-id="8ec6e-176">6.2</span></span>
<span data-ttu-id="8ec6e-177">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8ec6e-177">DeviceId</span></span> | <span data-ttu-id="8ec6e-178">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-178">string</span></span> | <span data-ttu-id="8ec6e-179">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-179">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="8ec6e-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-180">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="8ec6e-181">DeviceName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-181">DeviceName</span></span> | <span data-ttu-id="8ec6e-182">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-182">string</span></span> | <span data-ttu-id="8ec6e-183">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-183">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="8ec6e-184">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec6e-184">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="8ec6e-185">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="8ec6e-185">DiskPaths</span></span>  | <span data-ttu-id="8ec6e-186">Cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-186">Array\[string\]</span></span> | <span data-ttu-id="8ec6e-187">Evidência em disco de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-187">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="8ec6e-188">[ "C:\Arquivos de Programas (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-188">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>
<span data-ttu-id="8ec6e-189">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="8ec6e-189">ExploitabilityLevel</span></span> | <span data-ttu-id="8ec6e-190">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-190">string</span></span> | <span data-ttu-id="8ec6e-191">O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-191">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="8ec6e-192">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="8ec6e-192">ExploitIsInKit</span></span>
<span data-ttu-id="8ec6e-193">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8ec6e-193">FirstSeenTimestamp</span></span> | <span data-ttu-id="8ec6e-194">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-194">string</span></span> | <span data-ttu-id="8ec6e-195">Primeira vez que o CVE deste produto foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-195">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="8ec6e-196">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8ec6e-196">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="8ec6e-197">Id</span><span class="sxs-lookup"><span data-stu-id="8ec6e-197">Id</span></span> | <span data-ttu-id="8ec6e-198">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8ec6e-198">string</span></span> | <span data-ttu-id="8ec6e-199">Identificador exclusivo do registro.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-199">Unique identifier for the record.</span></span> | <span data-ttu-id="8ec6e-200">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="8ec6e-200">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="8ec6e-201">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8ec6e-201">LastSeenTimestamp</span></span> | <span data-ttu-id="8ec6e-202">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-202">string</span></span> | <span data-ttu-id="8ec6e-203">A última vez que o CVE foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-203">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="8ec6e-204">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8ec6e-204">2020-11-03 10:13:34.8476880</span></span>
<span data-ttu-id="8ec6e-205">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="8ec6e-205">OSPlatform</span></span> | <span data-ttu-id="8ec6e-206">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-206">string</span></span> | <span data-ttu-id="8ec6e-207">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-207">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8ec6e-208">Essa propriedade indica sistemas operacionais específicos, incluindo variações na mesma família, como Windows 10 e Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-208">This property indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="8ec6e-209">Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-209">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="8ec6e-210">Windows10</span><span class="sxs-lookup"><span data-stu-id="8ec6e-210">Windows10</span></span>
<span data-ttu-id="8ec6e-211">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-211">RbacGroupName</span></span>  | <span data-ttu-id="8ec6e-212">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-212">string</span></span> | <span data-ttu-id="8ec6e-213">O grupo controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-213">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="8ec6e-214">Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído".</span><span class="sxs-lookup"><span data-stu-id="8ec6e-214">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="8ec6e-215">Se a organização não tiver nenhum grupo RBAC, o valor será "None".</span><span class="sxs-lookup"><span data-stu-id="8ec6e-215">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="8ec6e-216">Servidores</span><span class="sxs-lookup"><span data-stu-id="8ec6e-216">Servers</span></span>
<span data-ttu-id="8ec6e-217">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="8ec6e-217">RecommendationReference</span></span> | <span data-ttu-id="8ec6e-218">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-218">string</span></span> | <span data-ttu-id="8ec6e-219">Uma referência à ID de recomendação relacionada a este software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-219">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="8ec6e-220">va-_-microsoft-_-silverlight</span><span class="sxs-lookup"><span data-stu-id="8ec6e-220">va-_-microsoft-_-silverlight</span></span>
<span data-ttu-id="8ec6e-221">RecommendedSecurityUpdate (opcional)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-221">RecommendedSecurityUpdate (optional)</span></span> | <span data-ttu-id="8ec6e-222">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-222">string</span></span> | <span data-ttu-id="8ec6e-223">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-223">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="8ec6e-224">Atualizações de segurança de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="8ec6e-224">April 2020 Security Updates</span></span>
<span data-ttu-id="8ec6e-225">RecommendedSecurityUpdateId (opcional)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-225">RecommendedSecurityUpdateId (optional)</span></span> | <span data-ttu-id="8ec6e-226">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-226">string</span></span> | <span data-ttu-id="8ec6e-227">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-227">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="8ec6e-228">4550961</span><span class="sxs-lookup"><span data-stu-id="8ec6e-228">4550961</span></span>
<span data-ttu-id="8ec6e-229">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="8ec6e-229">RegistryPaths</span></span>  | <span data-ttu-id="8ec6e-230">Cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-230">Array\[string\]</span></span> | <span data-ttu-id="8ec6e-231">Evidência do Registro de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-231">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="8ec6e-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-232">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]</span></span>
<span data-ttu-id="8ec6e-233">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-233">SoftwareName</span></span> | <span data-ttu-id="8ec6e-234">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-234">string</span></span> | <span data-ttu-id="8ec6e-235">Nome do produto de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-235">Name of the software product.</span></span> | <span data-ttu-id="8ec6e-236">chrome</span><span class="sxs-lookup"><span data-stu-id="8ec6e-236">chrome</span></span>
<span data-ttu-id="8ec6e-237">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="8ec6e-237">SoftwareVendor</span></span> | <span data-ttu-id="8ec6e-238">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-238">string</span></span> | <span data-ttu-id="8ec6e-239">Nome do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-239">Name of the software vendor.</span></span> | <span data-ttu-id="8ec6e-240">google</span><span class="sxs-lookup"><span data-stu-id="8ec6e-240">google</span></span>
<span data-ttu-id="8ec6e-241">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="8ec6e-241">SoftwareVersion</span></span> | <span data-ttu-id="8ec6e-242">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-242">string</span></span> | <span data-ttu-id="8ec6e-243">Número da versão do produto de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-243">Version number of the software product.</span></span> | <span data-ttu-id="8ec6e-244">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="8ec6e-244">81.0.4044.138</span></span>
<span data-ttu-id="8ec6e-245">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="8ec6e-245">VulnerabilitySeverityLevel</span></span>  | <span data-ttu-id="8ec6e-246">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-246">string</span></span> | <span data-ttu-id="8ec6e-247">Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-247">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="8ec6e-248">Médio</span><span class="sxs-lookup"><span data-stu-id="8ec6e-248">Medium</span></span>

### <a name="16-examples"></a><span data-ttu-id="8ec6e-249">1.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="8ec6e-249">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="8ec6e-250">1.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="8ec6e-250">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a><span data-ttu-id="8ec6e-251">Exemplo de resposta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="8ec6e-251">1.6.2 Response example</span></span>

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

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a><span data-ttu-id="8ec6e-252">2. Exportar a avaliação de vulnerabilidades de software (por meio de arquivos)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-252">2. Export software vulnerabilities assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="8ec6e-253">Descrição do método API 2.1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-253">2.1 API method description</span></span>

<span data-ttu-id="8ec6e-254">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-254">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="8ec6e-255">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-255">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="8ec6e-256">2.1.2 Limitações</span><span class="sxs-lookup"><span data-stu-id="8ec6e-256">2.1.2 Limitations</span></span>

<span data-ttu-id="8ec6e-257">As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-257">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="8ec6e-258">2.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="8ec6e-258">2.2 Permissions</span></span>

<span data-ttu-id="8ec6e-259">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-259">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ec6e-260">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-260">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details](apis-intro.md).</span></span>

<span data-ttu-id="8ec6e-261">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-261">Permission type</span></span> | <span data-ttu-id="8ec6e-262">Permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-262">Permission</span></span> | <span data-ttu-id="8ec6e-263">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-263">Permission display name</span></span>
---|---|---
<span data-ttu-id="8ec6e-264">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-264">Application</span></span> | <span data-ttu-id="8ec6e-265">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8ec6e-265">Vulnerability.Read.All</span></span> | <span data-ttu-id="8ec6e-266">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-266">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="8ec6e-267">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-267">Delegated (work or school account)</span></span> | <span data-ttu-id="8ec6e-268">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8ec6e-268">Vulnerability.Read</span></span> | <span data-ttu-id="8ec6e-269">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-269">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="8ec6e-270">URL 2.3</span><span class="sxs-lookup"><span data-stu-id="8ec6e-270">2.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a><span data-ttu-id="8ec6e-271">Parâmetros 2.4</span><span class="sxs-lookup"><span data-stu-id="8ec6e-271">2.4 Parameters</span></span>

- <span data-ttu-id="8ec6e-272">sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-272">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="8ec6e-273">2.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="8ec6e-273">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="8ec6e-274">Os arquivos são gzip compactados & no formato Json de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-274">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="8ec6e-275">As URLs de download só são válidas por 3 horas; caso contrário, você pode usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-275">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="8ec6e-276">Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure que seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-276">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>

>[!Note]
>
>- <span data-ttu-id="8ec6e-277">Cada registro é de aproximadamente 1KB de dados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-277">Each record is approximately 1KB of data.</span></span> <span data-ttu-id="8ec6e-278">Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-278">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="8ec6e-279">Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-279">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8ec6e-280">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-280">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="8ec6e-281">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-281">Property (ID)</span></span> | <span data-ttu-id="8ec6e-282">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8ec6e-282">Data type</span></span> | <span data-ttu-id="8ec6e-283">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ec6e-283">Description</span></span> | <span data-ttu-id="8ec6e-284">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="8ec6e-284">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8ec6e-285">Exportar arquivos</span><span class="sxs-lookup"><span data-stu-id="8ec6e-285">Export files</span></span> | <span data-ttu-id="8ec6e-286">cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-286">array\[string\]</span></span>  | <span data-ttu-id="8ec6e-287">Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-287">A list of download URLs for files holding the current snapshot of the organization.</span></span> | <span data-ttu-id="8ec6e-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-288">[  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]</span></span>
<span data-ttu-id="8ec6e-289">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="8ec6e-289">GeneratedTime</span></span> | <span data-ttu-id="8ec6e-290">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-290">string</span></span> | <span data-ttu-id="8ec6e-291">A hora em que a exportação foi gerada.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-291">The time that the export was generated.</span></span> | <span data-ttu-id="8ec6e-292">2021-05-20T08:00:00Z</span><span class="sxs-lookup"><span data-stu-id="8ec6e-292">2021-05-20T08:00:00Z</span></span>

### <a name="26-examples"></a><span data-ttu-id="8ec6e-293">2.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="8ec6e-293">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="8ec6e-294">2.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="8ec6e-294">2.6.1 Request example</span></span>

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a><span data-ttu-id="8ec6e-295">Exemplo de resposta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="8ec6e-295">2.6.2 Response example</span></span>

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

## <a name="3-delta-export-software-vulnerabilities-assessment-odata"></a><span data-ttu-id="8ec6e-296">3. Avaliação de vulnerabilidades de software de exportação delta (OData)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-296">3. Delta export software vulnerabilities assessment (OData)</span></span>

### <a name="31-api-method-description"></a><span data-ttu-id="8ec6e-297">Descrição do método API 3.1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-297">3.1 API method description</span></span>

<span data-ttu-id="8ec6e-298">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-298">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId.</span></span> <span data-ttu-id="8ec6e-299">A API coleta dados em sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-299">The API pulls data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="8ec6e-300">A resposta é paginada, portanto, você pode usar o campo @odata.nextLink da resposta para buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-300">The response is paginated, so you can use the @odata.nextLink field from the response to fetch the next results.</span></span> <span data-ttu-id="8ec6e-301">Ao contrário da avaliação completa de vulnerabilidades de software (OData) - que é usada para obter um instantâneo inteiro da avaliação de vulnerabilidades de software da sua organização por dispositivo - a chamada da API OData de exportação delta é usada para buscar apenas as alterações que aconteceram entre uma data selecionada e a data atual (a chamada da API "delta").</span><span class="sxs-lookup"><span data-stu-id="8ec6e-301">Unlike the full software vulnerabilities assessment (OData) - which is used to obtain an entire snapshot of the software vulnerabilities assessment of your organization by device - the delta export  OData API call is used to fetch only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span> <span data-ttu-id="8ec6e-302">Em vez de obter uma exportação completa com uma grande quantidade de dados sempre, você só obterá informações específicas sobre vulnerabilidades novas, fixas e atualizadas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-302">Instead of getting a full export with a large amount of data every time, you’ll only get specific information on new, fixed, and updated vulnerabilities.</span></span> <span data-ttu-id="8ec6e-303">A chamada de API OData de exportação delta também pode ser usada para calcular KPIs diferentes, como "quantas vulnerabilidades foram corrigidas?"</span><span class="sxs-lookup"><span data-stu-id="8ec6e-303">Delta export OData API call can also be used to calculate different KPIs such as “how many vulnerabilities were fixed?”</span></span> <span data-ttu-id="8ec6e-304">ou "quantas novas vulnerabilidades foram adicionadas à minha organização?"</span><span class="sxs-lookup"><span data-stu-id="8ec6e-304">or “how many new vulnerabilities were added to my organization?”</span></span>

>[!NOTE]
>
><span data-ttu-id="8ec6e-305">É altamente recomendável que você use a avaliação completa de vulnerabilidades de software de exportação por chamada de API de dispositivo pelo menos uma vez por semana, e essa exportação adicional de vulnerabilidades de software muda por api de dispositivo (delta) chamar todos os outros dias da semana.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-305">It is highly recommended you use the full export software vulnerabilities assessment by device API call at least once a week, and this additional export software vulnerabilities changes by device (delta) API call all the other days of the week.</span></span>  <span data-ttu-id="8ec6e-306">Ao contrário da outra API OData de Avaliações, a "exportação delta" não é uma exportação completa.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-306">Unlike the other Assessments OData API, the “delta export” is not a full export.</span></span> <span data-ttu-id="8ec6e-307">A exportação delta inclui apenas as alterações que aconteceram entre uma data selecionada e a data atual (a chamada da API "delta").</span><span class="sxs-lookup"><span data-stu-id="8ec6e-307">The delta export includes only the changes that have happened between a selected date and the current date (the “delta” API call).</span></span>

#### <a name="limitations"></a><span data-ttu-id="8ec6e-308">Limitações</span><span class="sxs-lookup"><span data-stu-id="8ec6e-308">Limitations</span></span>

- <span data-ttu-id="8ec6e-309">O tamanho máximo da página é 200.000.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-309">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="8ec6e-310">O parâmetro sinceTime tem no máximo 14 dias.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-310">The sinceTime parameter has a maximum of 14 days.</span></span>

- <span data-ttu-id="8ec6e-311">As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-311">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="32-permissions"></a><span data-ttu-id="8ec6e-312">3.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="8ec6e-312">3.2 Permissions</span></span>

<span data-ttu-id="8ec6e-313">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-313">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="8ec6e-314">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-314">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="8ec6e-315">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-315">Permission type</span></span> | <span data-ttu-id="8ec6e-316">Permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-316">Permission</span></span> | <span data-ttu-id="8ec6e-317">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="8ec6e-317">Permission display name</span></span>
---|---|---
<span data-ttu-id="8ec6e-318">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-318">Application</span></span> | <span data-ttu-id="8ec6e-319">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="8ec6e-319">Vulnerability.Read.All</span></span> | <span data-ttu-id="8ec6e-320">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-320">'Read Threat and Vulnerability Management vulnerability information'</span></span>
<span data-ttu-id="8ec6e-321">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-321">Delegated (work or school account)</span></span> | <span data-ttu-id="8ec6e-322">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="8ec6e-322">Vulnerability.Read</span></span> | <span data-ttu-id="8ec6e-323">'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades'</span><span class="sxs-lookup"><span data-stu-id="8ec6e-323">'Read Threat and Vulnerability Management vulnerability information'</span></span>

### <a name="33-url"></a><span data-ttu-id="8ec6e-324">URL 3.3</span><span class="sxs-lookup"><span data-stu-id="8ec6e-324">3.3 URL</span></span>

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine 
```

### <a name="34-parameters"></a><span data-ttu-id="8ec6e-325">Parâmetros 3.4</span><span class="sxs-lookup"><span data-stu-id="8ec6e-325">3.4 Parameters</span></span>

- <span data-ttu-id="8ec6e-326">sinceTime (obrigatório) – Os dados entre uma hora selecionada e hoje.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-326">sinceTime (required) – The data between a selected time and today.</span></span>
- <span data-ttu-id="8ec6e-327">pageSize (padrão = 50.000) – número de resultados em resposta</span><span class="sxs-lookup"><span data-stu-id="8ec6e-327">pageSize (default = 50,000) – number of results in response</span></span>
- <span data-ttu-id="8ec6e-328">$top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-328">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="35-properties"></a><span data-ttu-id="8ec6e-329">Propriedades 3.5</span><span class="sxs-lookup"><span data-stu-id="8ec6e-329">3.5 Properties</span></span>

<span data-ttu-id="8ec6e-330">Cada registro retornado contém todos os dados da avaliação completa de vulnerabilidades de software de exportação pela API OData do dispositivo, além de dois campos adicionais:  _**EventTimestamp**_ e _**Status**_.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-330">Each returned record contains all the data from the full export software vulnerabilities assessment by device OData API, plus two additional fields:  _**EventTimestamp**_ and _**Status**_.</span></span>

>[!NOTE]
><span data-ttu-id="8ec6e-331">-Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-331">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="8ec6e-332">Essas colunas são temporárias e podem ser removidas, portanto, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-332">These columns are temporary and might be removed, so please use only the documented columns.</span></span>
>
><span data-ttu-id="8ec6e-333">-As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-333">-The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="8ec6e-334">Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-334">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
<br>

<span data-ttu-id="8ec6e-335">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-335">Property (ID)</span></span> | <span data-ttu-id="8ec6e-336">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8ec6e-336">Data type</span></span> | <span data-ttu-id="8ec6e-337">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ec6e-337">Description</span></span> | <span data-ttu-id="8ec6e-338">Exemplo de valor retornado</span><span class="sxs-lookup"><span data-stu-id="8ec6e-338">Example of returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="8ec6e-339">CveId</span><span class="sxs-lookup"><span data-stu-id="8ec6e-339">CveId</span></span> | <span data-ttu-id="8ec6e-340">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-340">string</span></span> | <span data-ttu-id="8ec6e-341">Identificador exclusivo atribuído à vulnerabilidade de segurança no sistema CVE (Common Vulnerabilities and Exposures).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-341">Unique identifier assigned to the security vulnerability under the Common Vulnerabilities and Exposures (CVE) system.</span></span> | <span data-ttu-id="8ec6e-342">CVE-2020-15992</span><span class="sxs-lookup"><span data-stu-id="8ec6e-342">CVE-2020-15992</span></span>  
<span data-ttu-id="8ec6e-343">CvssScore</span><span class="sxs-lookup"><span data-stu-id="8ec6e-343">CvssScore</span></span> | <span data-ttu-id="8ec6e-344">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-344">string</span></span> | <span data-ttu-id="8ec6e-345">A pontuação CVSS do CVE.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-345">The CVSS score of the CVE.</span></span> | <span data-ttu-id="8ec6e-346">6.2</span><span class="sxs-lookup"><span data-stu-id="8ec6e-346">6.2</span></span>  
<span data-ttu-id="8ec6e-347">DeviceId</span><span class="sxs-lookup"><span data-stu-id="8ec6e-347">DeviceId</span></span> | <span data-ttu-id="8ec6e-348">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-348">string</span></span> | <span data-ttu-id="8ec6e-349">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-349">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="8ec6e-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-350">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>  
<span data-ttu-id="8ec6e-351">DeviceName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-351">DeviceName</span></span> | <span data-ttu-id="8ec6e-352">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-352">string</span></span> | <span data-ttu-id="8ec6e-353">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-353">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="8ec6e-354">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8ec6e-354">johnlaptop.europe.contoso.com</span></span>  
<span data-ttu-id="8ec6e-355">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="8ec6e-355">DiskPaths</span></span> | <span data-ttu-id="8ec6e-356">Array[string]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-356">Array[string]</span></span> | <span data-ttu-id="8ec6e-357">Evidência em disco de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-357">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="8ec6e-358">[ "C:\Arquivos de Programas (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-358">[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]</span></span>  
<span data-ttu-id="8ec6e-359">EventTimestamp</span><span class="sxs-lookup"><span data-stu-id="8ec6e-359">EventTimestamp</span></span> | <span data-ttu-id="8ec6e-360">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8ec6e-360">String</span></span> | <span data-ttu-id="8ec6e-361">A hora em que esse evento delta foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-361">The time this delta event was found.</span></span> | <span data-ttu-id="8ec6e-362">2021-01-11T11:06:08.291Z</span><span class="sxs-lookup"><span data-stu-id="8ec6e-362">2021-01-11T11:06:08.291Z</span></span>
<span data-ttu-id="8ec6e-363">ExploitabilityLevel</span><span class="sxs-lookup"><span data-stu-id="8ec6e-363">ExploitabilityLevel</span></span> | <span data-ttu-id="8ec6e-364">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-364">string</span></span> | <span data-ttu-id="8ec6e-365">O nível de exploração dessa vulnerabilidade (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-365">The exploitability level of this vulnerability (NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)</span></span> | <span data-ttu-id="8ec6e-366">ExploitIsInKit</span><span class="sxs-lookup"><span data-stu-id="8ec6e-366">ExploitIsInKit</span></span>  
<span data-ttu-id="8ec6e-367">FirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8ec6e-367">FirstSeenTimestamp</span></span> | <span data-ttu-id="8ec6e-368">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-368">string</span></span> | <span data-ttu-id="8ec6e-369">Primeira vez que o CVE deste produto foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-369">First time the CVE of this product was seen on the device.</span></span> | <span data-ttu-id="8ec6e-370">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8ec6e-370">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="8ec6e-371">Id</span><span class="sxs-lookup"><span data-stu-id="8ec6e-371">Id</span></span> | <span data-ttu-id="8ec6e-372">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8ec6e-372">string</span></span> | <span data-ttu-id="8ec6e-373">Identificador exclusivo do registro.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-373">Unique identifier for the record.</span></span> | <span data-ttu-id="8ec6e-374">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="8ec6e-374">123ABG55_573AG&mnp!</span></span>  
<span data-ttu-id="8ec6e-375">LastSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="8ec6e-375">LastSeenTimestamp</span></span> | <span data-ttu-id="8ec6e-376">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-376">string</span></span> | <span data-ttu-id="8ec6e-377">A última vez que o CVE foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-377">Last time the CVE was seen on the device.</span></span> | <span data-ttu-id="8ec6e-378">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="8ec6e-378">2020-11-03 10:13:34.8476880</span></span>  
<span data-ttu-id="8ec6e-379">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="8ec6e-379">OSPlatform</span></span> | <span data-ttu-id="8ec6e-380">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-380">string</span></span> | <span data-ttu-id="8ec6e-381">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-381">Platform of the operating system running on the device.</span></span> <span data-ttu-id="8ec6e-382">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-382">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="8ec6e-383">Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-383">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="8ec6e-384">Windows10</span><span class="sxs-lookup"><span data-stu-id="8ec6e-384">Windows10</span></span>  
<span data-ttu-id="8ec6e-385">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-385">RbacGroupName</span></span> | <span data-ttu-id="8ec6e-386">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-386">string</span></span> | <span data-ttu-id="8ec6e-387">O grupo controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-387">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="8ec6e-388">Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído".</span><span class="sxs-lookup"><span data-stu-id="8ec6e-388">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="8ec6e-389">Se a organização não tiver nenhum grupo RBAC, o valor será "None".</span><span class="sxs-lookup"><span data-stu-id="8ec6e-389">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="8ec6e-390">Servidores</span><span class="sxs-lookup"><span data-stu-id="8ec6e-390">Servers</span></span>  
<span data-ttu-id="8ec6e-391">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="8ec6e-391">RecommendationReference</span></span> | <span data-ttu-id="8ec6e-392">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-392">string</span></span> | <span data-ttu-id="8ec6e-393">Uma referência à ID de recomendação relacionada a este software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-393">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="8ec6e-394">va--microsoft--silverlight</span><span class="sxs-lookup"><span data-stu-id="8ec6e-394">va--microsoft--silverlight</span></span>  
<span data-ttu-id="8ec6e-395">RecommendedSecurityUpdate</span><span class="sxs-lookup"><span data-stu-id="8ec6e-395">RecommendedSecurityUpdate</span></span>  | <span data-ttu-id="8ec6e-396">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-396">string</span></span> | <span data-ttu-id="8ec6e-397">Nome ou descrição da atualização de segurança fornecida pelo fornecedor de software para resolver a vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-397">Name or description of the security update provided by the software vendor to address the vulnerability.</span></span> | <span data-ttu-id="8ec6e-398">Atualizações de segurança de abril de 2020</span><span class="sxs-lookup"><span data-stu-id="8ec6e-398">April 2020 Security Updates</span></span>  
<span data-ttu-id="8ec6e-399">RecommendedSecurityUpdateId</span><span class="sxs-lookup"><span data-stu-id="8ec6e-399">RecommendedSecurityUpdateId</span></span>  | <span data-ttu-id="8ec6e-400">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-400">string</span></span> | <span data-ttu-id="8ec6e-401">Identificador das atualizações de segurança ou identificador aplicáveis para os artigos de base de conhecimento ou orientação correspondentes (KB)</span><span class="sxs-lookup"><span data-stu-id="8ec6e-401">Identifier of the applicable security updates or identifier for the corresponding guidance or knowledge base (KB) articles</span></span> | <span data-ttu-id="8ec6e-402">4550961</span><span class="sxs-lookup"><span data-stu-id="8ec6e-402">4550961</span></span>  
<span data-ttu-id="8ec6e-403">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="8ec6e-403">RegistryPaths</span></span>  | <span data-ttu-id="8ec6e-404">Array[string]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-404">Array[string]</span></span> | <span data-ttu-id="8ec6e-405">Evidência do Registro de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-405">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="8ec6e-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span><span class="sxs-lookup"><span data-stu-id="8ec6e-406">[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]</span></span>  
<span data-ttu-id="8ec6e-407">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="8ec6e-407">SoftwareName</span></span> | <span data-ttu-id="8ec6e-408">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-408">string</span></span> | <span data-ttu-id="8ec6e-409">Nome do produto de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-409">Name of the software product.</span></span> | <span data-ttu-id="8ec6e-410">chrome</span><span class="sxs-lookup"><span data-stu-id="8ec6e-410">chrome</span></span>  
<span data-ttu-id="8ec6e-411">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="8ec6e-411">SoftwareVendor</span></span> | <span data-ttu-id="8ec6e-412">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-412">string</span></span> | <span data-ttu-id="8ec6e-413">Nome do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-413">Name of the software vendor.</span></span> | <span data-ttu-id="8ec6e-414">google</span><span class="sxs-lookup"><span data-stu-id="8ec6e-414">google</span></span>  
<span data-ttu-id="8ec6e-415">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="8ec6e-415">SoftwareVersion</span></span> | <span data-ttu-id="8ec6e-416">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-416">string</span></span> | <span data-ttu-id="8ec6e-417">Número da versão do produto de software.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-417">Version number of the software product.</span></span> | <span data-ttu-id="8ec6e-418">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="8ec6e-418">81.0.4044.138</span></span>  
<span data-ttu-id="8ec6e-419">Status</span><span class="sxs-lookup"><span data-stu-id="8ec6e-419">Status</span></span> | <span data-ttu-id="8ec6e-420">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8ec6e-420">String</span></span> | <span data-ttu-id="8ec6e-421">**Novo**   (para uma nova vulnerabilidade introduzida em um dispositivo)  (1) **Corrigido**(se essa vulnerabilidade não existir mais no dispositivo, o que significa   que foi corrigida).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-421">**New** (for a new vulnerability introduced on a device)  (1) **Fixed** (if this vulnerability doesn’t exist anymore on the device, which means it was remediated).</span></span> <span data-ttu-id="8ec6e-422">(2)  **Atualizado**   (se uma vulnerabilidade em um dispositivo tiver sido alterada.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-422">(2) **Updated** (if a vulnerability on a device has changed.</span></span> <span data-ttu-id="8ec6e-423">As alterações possíveis são: pontuação CVSS, nível de exploração, nível de gravidade, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span><span class="sxs-lookup"><span data-stu-id="8ec6e-423">The possible changes are: CVSS score, exploitability level, severity level, DiskPaths, RegistryPaths, RecommendedSecurityUpdate).</span></span> | <span data-ttu-id="8ec6e-424">Fixed</span><span class="sxs-lookup"><span data-stu-id="8ec6e-424">Fixed</span></span>
<span data-ttu-id="8ec6e-425">VulnerabilitySeverityLevel</span><span class="sxs-lookup"><span data-stu-id="8ec6e-425">VulnerabilitySeverityLevel</span></span> | <span data-ttu-id="8ec6e-426">string</span><span class="sxs-lookup"><span data-stu-id="8ec6e-426">string</span></span> | <span data-ttu-id="8ec6e-427">Nível de severidade atribuído à vulnerabilidade de segurança com base na pontuação cvss e fatores dinâmicos influenciados pelo cenário de ameaças.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-427">Severity level assigned to the security vulnerability based on the CVSS score and dynamic factors influenced by the threat landscape.</span></span> | <span data-ttu-id="8ec6e-428">Médio</span><span class="sxs-lookup"><span data-stu-id="8ec6e-428">Medium</span></span>  

#### <a name="clarifications"></a><span data-ttu-id="8ec6e-429">Esclarecimentos</span><span class="sxs-lookup"><span data-stu-id="8ec6e-429">Clarifications</span></span>

- <span data-ttu-id="8ec6e-430">Se o software foi atualizado da versão 1.0 para a versão 2.0 e ambas as versões são expostas ao CVE-A, você receberá dois eventos separados:</span><span class="sxs-lookup"><span data-stu-id="8ec6e-430">If the software was updated from version 1.0 to version 2.0, and both versions are exposed to CVE-A, you will receive 2 separate events:</span></span>  
   <span data-ttu-id="8ec6e-431">a.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-431">a.</span></span> <span data-ttu-id="8ec6e-432">Fixo – CVE-A na versão 1.0 foi corrigido</span><span class="sxs-lookup"><span data-stu-id="8ec6e-432">Fixed – CVE-A on version 1.0 was fixed</span></span>  
   <span data-ttu-id="8ec6e-433">b.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-433">b.</span></span> <span data-ttu-id="8ec6e-434">Novo – A CVE-A na versão 2.0 foi adicionada</span><span class="sxs-lookup"><span data-stu-id="8ec6e-434">New – CVE-A on version 2.0 was added</span></span>

- <span data-ttu-id="8ec6e-435">Se uma vulnerabilidade específica (por exemplo, CVE-A) foi vista pela primeira vez em um momento específico (por exemplo, 10 de janeiro) em software com a versão 1.0 e alguns dias depois esse software foi atualizado para a versão 2.0 que também foi exposto ao mesmo CVE-A, você receberá estes dois eventos separados:</span><span class="sxs-lookup"><span data-stu-id="8ec6e-435">If a specific vulnerability (for example, CVE-A) was first seen at a specific time (for example, January 10) on software with version 1.0, and a few days later that software was updated to version 2.0 which also exposed to the same CVE-A, you will receive these two separated events:</span></span>  
   <span data-ttu-id="8ec6e-436">a.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-436">a.</span></span> <span data-ttu-id="8ec6e-437">Fixo – CVE-X, FirstSeenTimestamp 10 de janeiro, versão 1,0.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-437">Fixed – CVE-X, FirstSeenTimestamp January 10, version 1,0.</span></span>  
   <span data-ttu-id="8ec6e-438">b.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-438">b.</span></span> <span data-ttu-id="8ec6e-439">Novo – CVE-X, FirstSeenTimestamp 10 de janeiro, versão 2.0.</span><span class="sxs-lookup"><span data-stu-id="8ec6e-439">New – CVE-X, FirstSeenTimestamp January 10, version 2.0.</span></span>

### <a name="36-examples"></a><span data-ttu-id="8ec6e-440">3.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="8ec6e-440">3.6 Examples</span></span>

#### <a name="361-request-example"></a><span data-ttu-id="8ec6e-441">Exemplo de solicitação 3.6.1</span><span class="sxs-lookup"><span data-stu-id="8ec6e-441">3.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a><span data-ttu-id="8ec6e-442">Exemplo de resposta 3.6.2</span><span class="sxs-lookup"><span data-stu-id="8ec6e-442">3.6.2 Response example</span></span>

```json
{ 
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)", 
    "value": [ 
        { 
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__", 
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "87.0.4280.88", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome" 
            ], 
            "lastSeenTimestamp": "2021-01-04 00:29:42", 
            "firstSeenTimestamp": "2020-11-06 03:12:44", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__", 
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "onedrive", 
            "softwareVersion": "20.64.329.3", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe" 
            ], 
            "lastSeenTimestamp": "2020-12-11 19:49:48", 
            "firstSeenTimestamp": "2020-12-07 18:25:47", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-onedrive", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_", 
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "mozilla", 
            "softwareName": "firefox", 
            "softwareVersion": "83.0.0.0", 
            "cveId": "CVE-2020-26971", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "193220", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)" 
            ], 
            "lastSeenTimestamp": "2021-01-05 17:04:30", 
            "firstSeenTimestamp": "2020-05-06 12:42:19", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-mozilla-_-firefox", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__", 
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e", 
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.19042.685", 
            "osArchitecture": "x64", 
            "softwareVendor": "microsoft", 
            "softwareName": "project", 
            "softwareVersion": "16.0.13701.20000", 
            "cveId": null, 
            "vulnerabilitySeverityLevel": null, 
            "recommendedSecurityUpdate": null, 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us" 
            ], 
            "lastSeenTimestamp": "2021-01-03 23:38:03", 
            "firstSeenTimestamp": "2019-08-01 22:56:12", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-microsoft-_-project", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        }, 
        { 
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_", 
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",  
            "rbacGroupName": "hhh", 
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net", 
            "osPlatform": "Windows10", 
            "osVersion": "10.0.18363.1256", 
            "osArchitecture": "x64", 
            "softwareVendor": "google", 
            "softwareName": "chrome", 
            "softwareVersion": "81.0.4044.138", 
            "cveId": "CVE-2020-16011", 
            "vulnerabilitySeverityLevel": "High", 
            "recommendedSecurityUpdate": "ADV 200002", 
            "recommendedSecurityUpdateId": null, 
            "recommendedSecurityUpdateUrl": null, 
            "diskPaths": [ 
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe" 
            ], 
            "registryPaths": [ 
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}" 
            ], 
            "lastSeenTimestamp": "2020-12-10 22:45:41", 
            "firstSeenTimestamp": "2020-07-26 02:13:43", 
            "exploitabilityLevel": "NoExploit", 
            "recommendationReference": "va-_-google-_-chrome", 
            "status": "Fixed", 
            "eventTimestamp": "2021-01-11T11:06:08.291Z" 
        } 
    ], 
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9" 
} 
```

## <a name="see-also"></a><span data-ttu-id="8ec6e-443">Confira também</span><span class="sxs-lookup"><span data-stu-id="8ec6e-443">See also</span></span>

- [<span data-ttu-id="8ec6e-444">Exportar métodos e propriedades de avaliação por dispositivo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-444">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="8ec6e-445">Exportar avaliação de configuração segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-445">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="8ec6e-446">Exportar avaliação de inventário de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="8ec6e-446">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

<span data-ttu-id="8ec6e-447">Outros relacionados</span><span class="sxs-lookup"><span data-stu-id="8ec6e-447">Other related</span></span>

- [<span data-ttu-id="8ec6e-448">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="8ec6e-448">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="8ec6e-449">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="8ec6e-449">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
