---
title: Exportar avaliação de inventário de software por dispositivo
description: Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.
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
ms.openlocfilehash: 3a65fb6d5d3e5c6e68e100aa3ea2b4cf896dc281
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789327"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="2269d-104">Exportar avaliação de inventário de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2269d-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2269d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2269d-105">**Applies to:**</span></span>

- [<span data-ttu-id="2269d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2269d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2269d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2269d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2269d-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2269d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2269d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2269d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="2269d-110">Há diferentes chamadas de API para obter diferentes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="2269d-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="2269d-111">Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:</span><span class="sxs-lookup"><span data-stu-id="2269d-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="2269d-112">[Exportar o **OData** de avaliação do inventário de software](#1-export-software-inventory-assessment-odata)  A API puxa todos os dados da sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="2269d-112">[Export software inventory assessment **OData**](#1-export-software-inventory-assessment-odata)  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="2269d-113">Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_.</span><span class="sxs-lookup"><span data-stu-id="2269d-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="2269d-114">A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="2269d-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="2269d-115">[Exportar a avaliação do inventário de software **por meio de arquivos**](#2-export-software-inventory-assessment-via-files)  Essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável.</span><span class="sxs-lookup"><span data-stu-id="2269d-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="2269d-116">Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2269d-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="2269d-117">Essa API puxa todos os dados da sua organização como arquivos de download.</span><span class="sxs-lookup"><span data-stu-id="2269d-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="2269d-118">A resposta contém URLs para baixar todos os dados do Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="2269d-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="2269d-119">Essa API permite baixar todos os dados do Azure Armazenamento a seguir:</span><span class="sxs-lookup"><span data-stu-id="2269d-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="2269d-120">Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2269d-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="2269d-121">Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.</span><span class="sxs-lookup"><span data-stu-id="2269d-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="2269d-122">Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos.</span><span class="sxs-lookup"><span data-stu-id="2269d-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="2269d-123">Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="2269d-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="2269d-124">A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="2269d-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-odata"></a><span data-ttu-id="2269d-125">1. Exportar avaliação de inventário de software (OData)</span><span class="sxs-lookup"><span data-stu-id="2269d-125">1. Export software inventory assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="2269d-126">Descrição do método API 1.1</span><span class="sxs-lookup"><span data-stu-id="2269d-126">1.1 API method description</span></span>

<span data-ttu-id="2269d-127">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="2269d-128">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="2269d-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="2269d-129">Limitações</span><span class="sxs-lookup"><span data-stu-id="2269d-129">Limitations</span></span>

- <span data-ttu-id="2269d-130">O tamanho máximo da página é 200.000.</span><span class="sxs-lookup"><span data-stu-id="2269d-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="2269d-131">As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2269d-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="2269d-132">1.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="2269d-132">1.2 Permissions</span></span>

<span data-ttu-id="2269d-133">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="2269d-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2269d-134">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2269d-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2269d-135">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-135">Permission type</span></span> | <span data-ttu-id="2269d-136">Permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-136">Permission</span></span> | <span data-ttu-id="2269d-137">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="2269d-138">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2269d-138">Application</span></span> | <span data-ttu-id="2269d-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2269d-139">Software.Read.All</span></span> | <span data-ttu-id="2269d-140">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="2269d-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2269d-141">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2269d-141">Delegated (work or school account)</span></span> | <span data-ttu-id="2269d-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2269d-142">Software.Read</span></span> | <span data-ttu-id="2269d-143">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="2269d-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="2269d-144">URL 1.3</span><span class="sxs-lookup"><span data-stu-id="2269d-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="2269d-145">Parâmetros 1.4</span><span class="sxs-lookup"><span data-stu-id="2269d-145">1.4 Parameters</span></span>

- <span data-ttu-id="2269d-146">pageSize (padrão = 50.000) – número de resultados em resposta.</span><span class="sxs-lookup"><span data-stu-id="2269d-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="2269d-147">$top – número de resultados a retornar (não retorna @odata.nextLink e, portanto, não puxa todos os dados)</span><span class="sxs-lookup"><span data-stu-id="2269d-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="2269d-148">1.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="2269d-148">1.5 Properties</span></span>

>[!NOTE]
>
><span data-ttu-id="2269d-149">-Cada registro é de aproximadamente 0,5KB de dados.</span><span class="sxs-lookup"><span data-stu-id="2269d-149">-Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="2269d-150">Você deve levar isso em consideração ao escolher o parâmetro pageSize correto para você.</span><span class="sxs-lookup"><span data-stu-id="2269d-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>

><span data-ttu-id="2269d-151">-As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.</span><span class="sxs-lookup"><span data-stu-id="2269d-151">-The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="2269d-152">Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="2269d-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
><span data-ttu-id="2269d-153">-Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="2269d-153">-Some additional columns might be returned in the response.</span></span> <span data-ttu-id="2269d-154">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="2269d-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<span data-ttu-id="2269d-155">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="2269d-155">Property (ID)</span></span> | <span data-ttu-id="2269d-156">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2269d-156">Data type</span></span> | <span data-ttu-id="2269d-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="2269d-157">Description</span></span> | <span data-ttu-id="2269d-158">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="2269d-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2269d-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="2269d-159">DeviceId</span></span> | <span data-ttu-id="2269d-160">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-160">string</span></span> | <span data-ttu-id="2269d-161">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="2269d-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="2269d-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="2269d-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="2269d-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="2269d-163">DeviceName</span></span> | <span data-ttu-id="2269d-164">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-164">string</span></span> | <span data-ttu-id="2269d-165">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="2269d-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2269d-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="2269d-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="2269d-167">DiskPaths</span></span> | <span data-ttu-id="2269d-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="2269d-168">Array[string]</span></span>  | <span data-ttu-id="2269d-169">Evidência em disco de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="2269d-170">[ "C: \\ Arquivos de Programa (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="2269d-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="2269d-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="2269d-171">EndOfSupportDate</span></span> | <span data-ttu-id="2269d-172">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-172">string</span></span> | <span data-ttu-id="2269d-173">A data em que o suporte para este software tem ou terminará.</span><span class="sxs-lookup"><span data-stu-id="2269d-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="2269d-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="2269d-174">2020-12-30</span></span>
<span data-ttu-id="2269d-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="2269d-175">EndOfSupportStatus</span></span> | <span data-ttu-id="2269d-176">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-176">string</span></span> | <span data-ttu-id="2269d-177">Status do fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="2269d-177">End of support status.</span></span> <span data-ttu-id="2269d-178">Pode conter esses valores possíveis: None, Versão EOS, Versão EOS futura, Software EOS, Software EOS futuro.</span><span class="sxs-lookup"><span data-stu-id="2269d-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="2269d-179">EOS futuro</span><span class="sxs-lookup"><span data-stu-id="2269d-179">Upcoming EOS</span></span>
<span data-ttu-id="2269d-180">Id</span><span class="sxs-lookup"><span data-stu-id="2269d-180">Id</span></span> | <span data-ttu-id="2269d-181">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-181">string</span></span> | <span data-ttu-id="2269d-182">Identificador exclusivo do registro.</span><span class="sxs-lookup"><span data-stu-id="2269d-182">Unique identifier for the record.</span></span> | <span data-ttu-id="2269d-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="2269d-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="2269d-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="2269d-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="2269d-185">int</span><span class="sxs-lookup"><span data-stu-id="2269d-185">int</span></span> | <span data-ttu-id="2269d-186">Número de pontos fracos neste software neste dispositivo</span><span class="sxs-lookup"><span data-stu-id="2269d-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="2269d-187">3</span><span class="sxs-lookup"><span data-stu-id="2269d-187">3</span></span>
<span data-ttu-id="2269d-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="2269d-188">OSPlatform</span></span> | <span data-ttu-id="2269d-189">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-189">string</span></span> | <span data-ttu-id="2269d-190">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="2269d-191">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="2269d-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="2269d-192">Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="2269d-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="2269d-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="2269d-193">Windows10</span></span>
<span data-ttu-id="2269d-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="2269d-194">RbacGroupName</span></span> | <span data-ttu-id="2269d-195">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-195">string</span></span> | <span data-ttu-id="2269d-196">O grupo controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="2269d-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="2269d-197">Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído".</span><span class="sxs-lookup"><span data-stu-id="2269d-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="2269d-198">Se a organização não tiver nenhum grupo RBAC, o valor será "None".</span><span class="sxs-lookup"><span data-stu-id="2269d-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="2269d-199">Servidores</span><span class="sxs-lookup"><span data-stu-id="2269d-199">Servers</span></span>
<span data-ttu-id="2269d-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="2269d-200">RegistryPaths</span></span> | <span data-ttu-id="2269d-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="2269d-201">Array[string]</span></span> | <span data-ttu-id="2269d-202">Evidência do Registro de que o produto está instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="2269d-203">[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Desinstalar \\ o Microsoft Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="2269d-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="2269d-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="2269d-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="2269d-205">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-205">string</span></span> | <span data-ttu-id="2269d-206">A primeira vez que esse software foi visto no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="2269d-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="2269d-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="2269d-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="2269d-208">SoftwareName</span></span> | <span data-ttu-id="2269d-209">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-209">string</span></span> | <span data-ttu-id="2269d-210">Nome do produto de software.</span><span class="sxs-lookup"><span data-stu-id="2269d-210">Name of the software product.</span></span> | <span data-ttu-id="2269d-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="2269d-211">Silverlight</span></span>
<span data-ttu-id="2269d-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="2269d-212">SoftwareVendor</span></span> | <span data-ttu-id="2269d-213">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-213">string</span></span> | <span data-ttu-id="2269d-214">Nome do fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="2269d-214">Name of the software vendor.</span></span> | <span data-ttu-id="2269d-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="2269d-215">microsoft</span></span>
<span data-ttu-id="2269d-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="2269d-216">SoftwareVersion</span></span> | <span data-ttu-id="2269d-217">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-217">string</span></span> | <span data-ttu-id="2269d-218">Número da versão do produto de software.</span><span class="sxs-lookup"><span data-stu-id="2269d-218">Version number of the software product.</span></span> | <span data-ttu-id="2269d-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="2269d-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="2269d-220">1.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="2269d-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="2269d-221">1.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="2269d-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="2269d-222">Exemplo de resposta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="2269d-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="2269d-223">2. Exportar avaliação de inventário de software (por meio de arquivos)</span><span class="sxs-lookup"><span data-stu-id="2269d-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="2269d-224">Descrição do método API 2.1</span><span class="sxs-lookup"><span data-stu-id="2269d-224">2.1 API method description</span></span>

<span data-ttu-id="2269d-225">Esta resposta à API contém todos os dados de software instalado por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2269d-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="2269d-226">Retorna uma tabela com uma entrada para cada combinação exclusiva de DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span><span class="sxs-lookup"><span data-stu-id="2269d-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="2269d-227">2.1.1 Limitações</span><span class="sxs-lookup"><span data-stu-id="2269d-227">2.1.1 Limitations</span></span>

<span data-ttu-id="2269d-228">As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="2269d-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="2269d-229">2.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="2269d-229">2.2 Permissions</span></span>

<span data-ttu-id="2269d-230">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="2269d-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="2269d-231">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="2269d-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="2269d-232">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-232">Permission type</span></span> | <span data-ttu-id="2269d-233">Permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-233">Permission</span></span> | <span data-ttu-id="2269d-234">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="2269d-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="2269d-235">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="2269d-235">Application</span></span> | <span data-ttu-id="2269d-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="2269d-236">Software.Read.All</span></span> | <span data-ttu-id="2269d-237">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="2269d-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="2269d-238">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="2269d-238">Delegated (work or school account)</span></span> | <span data-ttu-id="2269d-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="2269d-239">Software.Read</span></span> | <span data-ttu-id="2269d-240">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="2269d-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="2269d-241">URL 2.3</span><span class="sxs-lookup"><span data-stu-id="2269d-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="2269d-242">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2269d-242">Parameters</span></span>

- <span data-ttu-id="2269d-243">sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas)</span><span class="sxs-lookup"><span data-stu-id="2269d-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="2269d-244">2.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="2269d-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="2269d-245">Os arquivos são gzip compactados & no formato Json de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="2269d-245">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="2269d-246">As URLs de download só são válidas por 3 horas.</span><span class="sxs-lookup"><span data-stu-id="2269d-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="2269d-247">Caso contrário, você pode usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="2269d-247">Otherwise you can use the parameter.</span></span>
>
><span data-ttu-id="2269d-248">_ Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure que seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="2269d-248">_ For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>
>
<span data-ttu-id="2269d-249">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="2269d-249">Property (ID)</span></span> | <span data-ttu-id="2269d-250">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2269d-250">Data type</span></span> | <span data-ttu-id="2269d-251">Descrição</span><span class="sxs-lookup"><span data-stu-id="2269d-251">Description</span></span> | <span data-ttu-id="2269d-252">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="2269d-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="2269d-253">Exportar arquivos</span><span class="sxs-lookup"><span data-stu-id="2269d-253">Export files</span></span> | <span data-ttu-id="2269d-254">cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="2269d-254">array\[string\]</span></span> | <span data-ttu-id="2269d-255">Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização</span><span class="sxs-lookup"><span data-stu-id="2269d-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="2269d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="2269d-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="2269d-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="2269d-257">GeneratedTime</span></span> | <span data-ttu-id="2269d-258">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2269d-258">string</span></span> | <span data-ttu-id="2269d-259">A hora em que a exportação foi gerada.</span><span class="sxs-lookup"><span data-stu-id="2269d-259">The time that the export was generated.</span></span> | <span data-ttu-id="2269d-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="2269d-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="2269d-261">2.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="2269d-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="2269d-262">2.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="2269d-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="2269d-263">Exemplo de resposta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="2269d-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="2269d-264">Confira também</span><span class="sxs-lookup"><span data-stu-id="2269d-264">See also</span></span>

- [<span data-ttu-id="2269d-265">Exportar métodos e propriedades de avaliação por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2269d-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="2269d-266">Exportar avaliação de configuração segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2269d-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="2269d-267">Exportar a avaliação de vulnerabilidades de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="2269d-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="2269d-268">Outros relacionados</span><span class="sxs-lookup"><span data-stu-id="2269d-268">Other related</span></span>

- [<span data-ttu-id="2269d-269">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="2269d-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="2269d-270">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="2269d-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)