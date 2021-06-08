---
title: Exportar avaliação de configuração segura por dispositivo
description: Retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.
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
ms.openlocfilehash: fe6a4604852965bdcc563ac0e410ca165bc5a088
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789328"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="ca7bd-104">Exportar avaliação de configuração segura por dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca7bd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ca7bd-105">**Applies to:**</span></span>

- [<span data-ttu-id="ca7bd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ca7bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ca7bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca7bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ca7bd-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ca7bd-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca7bd-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
<span data-ttu-id="ca7bd-110">Retorna todas as configurações e seu status, por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="ca7bd-111">Há diferentes chamadas de API para obter diferentes tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="ca7bd-112">Como a quantidade de dados pode ser grande, há duas maneiras de recuperá-las:</span><span class="sxs-lookup"><span data-stu-id="ca7bd-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="ca7bd-113">[Exportar **OData** de avaliação](#1-export-secure-configuration-assessment-odata)de configuração segura : a API coleta todos os dados em sua organização como respostas Json, seguindo o protocolo OData.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-113">[Export secure configuration assessment **OData**](#1-export-secure-configuration-assessment-odata):  The API pulls all data in your organization as Json responses, following the OData protocol.</span></span> <span data-ttu-id="ca7bd-114">Esse método é melhor para _organizações pequenas com menos de 100 K dispositivos_.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="ca7bd-115">A resposta é paginada, portanto, você pode usar o campo odata.nextLink da resposta para \@ buscar os próximos resultados.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="ca7bd-116">[Exportar a avaliação de configuração](#2-export-secure-configuration-assessment-via-files)segura por meio de arquivos : essa solução de API permite a retirada de quantidades maiores de dados de forma mais rápida e confiável.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="ca7bd-117">Portanto, é recomendado para grandes organizações, com mais de 100 K dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="ca7bd-118">Essa API puxa todos os dados da sua organização como arquivos de download.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="ca7bd-119">A resposta contém URLs para baixar todos os dados do Azure Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="ca7bd-120">Essa API permite baixar todos os dados do Azure Armazenamento a seguir:</span><span class="sxs-lookup"><span data-stu-id="ca7bd-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="ca7bd-121">Chame a API para obter uma lista de URLs de download com todos os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="ca7bd-122">Baixe todos os arquivos usando as URLs de download e processe os dados conforme quiser.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="ca7bd-123">Os dados coletados (usando _OData_ ou _por_ meio de arquivos ) são o instantâneo atual do estado atual e não contêm dados históricos.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-123">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="ca7bd-124">Para coletar dados históricos, os clientes devem salvar os dados em seus próprios armazenamentos de dados.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="ca7bd-125">A menos que indicado de outra forma, todos os métodos de avaliação de exportação listados são **_exportação completa_** e **_por dispositivo_** (também chamado de **_por dispositivo)._**</span><span class="sxs-lookup"><span data-stu-id="ca7bd-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-odata"></a><span data-ttu-id="ca7bd-126">1. Exportar a avaliação de configuração segura (OData)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-126">1. Export secure configuration assessment (OData)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="ca7bd-127">Descrição do método API 1.1</span><span class="sxs-lookup"><span data-stu-id="ca7bd-127">1.1 API method description</span></span>

<span data-ttu-id="ca7bd-128">Esta resposta à API contém a Avaliação de Configuração Segura em seus dispositivos expostos e retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="ca7bd-129">1.1.1 Limitações</span><span class="sxs-lookup"><span data-stu-id="ca7bd-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="ca7bd-130">O tamanho máximo da página é 200.000.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="ca7bd-131">As limitações de taxa para essa API são 30 chamadas por minuto e 1.000 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="ca7bd-132">1.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="ca7bd-132">1.2 Permissions</span></span>

<span data-ttu-id="ca7bd-133">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ca7bd-134">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="ca7bd-135">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-135">Permission type</span></span> | <span data-ttu-id="ca7bd-136">Permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-136">Permission</span></span> | <span data-ttu-id="ca7bd-137">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="ca7bd-138">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-138">Application</span></span> | <span data-ttu-id="ca7bd-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="ca7bd-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="ca7bd-140">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="ca7bd-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="ca7bd-141">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-141">Delegated (work or school account)</span></span> | <span data-ttu-id="ca7bd-142">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="ca7bd-142">Vulnerability.Read</span></span> | <span data-ttu-id="ca7bd-143">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="ca7bd-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="ca7bd-144">URL 1.3</span><span class="sxs-lookup"><span data-stu-id="ca7bd-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="ca7bd-145">Parâmetros 1.4</span><span class="sxs-lookup"><span data-stu-id="ca7bd-145">1.4 Parameters</span></span>

- <span data-ttu-id="ca7bd-146">pageSize \( padrão = 50.000 \) – número de resultados em resposta</span><span class="sxs-lookup"><span data-stu-id="ca7bd-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="ca7bd-147">\$top – número de resultados a retornar \( não retorna \@ odata.nextLink e, portanto, não puxa todos os dados\)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="ca7bd-148">1.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="ca7bd-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="ca7bd-149">As propriedades definidas na tabela a seguir são listadas em ordem alfabética, por ID da propriedade.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="ca7bd-150">Ao executar essa API, a saída resultante não será necessariamente retornada na mesma ordem listada nesta tabela.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="ca7bd-151">Algumas colunas adicionais podem ser retornadas na resposta.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="ca7bd-152">Essas colunas são temporárias e podem ser removidas, use apenas as colunas documentadas.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="ca7bd-153">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-153">Property (ID)</span></span> | <span data-ttu-id="ca7bd-154">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ca7bd-154">Data type</span></span> | <span data-ttu-id="ca7bd-155">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca7bd-155">Description</span></span> | <span data-ttu-id="ca7bd-156">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="ca7bd-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="ca7bd-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="ca7bd-157">ConfigurationCategory</span></span> | <span data-ttu-id="ca7bd-158">string</span><span class="sxs-lookup"><span data-stu-id="ca7bd-158">string</span></span> | <span data-ttu-id="ca7bd-159">Categoria ou agrupamento ao qual a configuração pertence: aplicativo, sistema operacional, rede, contas, controles de segurança</span><span class="sxs-lookup"><span data-stu-id="ca7bd-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="ca7bd-160">Controles de segurança</span><span class="sxs-lookup"><span data-stu-id="ca7bd-160">Security controls</span></span>
<span data-ttu-id="ca7bd-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="ca7bd-161">ConfigurationId</span></span> | <span data-ttu-id="ca7bd-162">string</span><span class="sxs-lookup"><span data-stu-id="ca7bd-162">string</span></span> | <span data-ttu-id="ca7bd-163">Identificador exclusivo para uma configuração específica</span><span class="sxs-lookup"><span data-stu-id="ca7bd-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="ca7bd-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="ca7bd-164">scid-10000</span></span>
<span data-ttu-id="ca7bd-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="ca7bd-165">ConfigurationImpact</span></span> | <span data-ttu-id="ca7bd-166">string</span><span class="sxs-lookup"><span data-stu-id="ca7bd-166">string</span></span> | <span data-ttu-id="ca7bd-167">Impacto avaliado da configuração na classificação total (1-10)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="ca7bd-168">9 </span><span class="sxs-lookup"><span data-stu-id="ca7bd-168">9</span></span>
<span data-ttu-id="ca7bd-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="ca7bd-169">ConfigurationName</span></span> | <span data-ttu-id="ca7bd-170">string</span><span class="sxs-lookup"><span data-stu-id="ca7bd-170">string</span></span> | <span data-ttu-id="ca7bd-171">Exibir o nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ca7bd-171">Display name of the configuration</span></span> | <span data-ttu-id="ca7bd-172">Dispositivos integrados ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ca7bd-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="ca7bd-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="ca7bd-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="ca7bd-174">string</span><span class="sxs-lookup"><span data-stu-id="ca7bd-174">string</span></span> | <span data-ttu-id="ca7bd-175">Subcategoria ou subgrupo ao qual a configuração pertence.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="ca7bd-176">Em muitos casos, isso descreve capacidades ou recursos específicos.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="ca7bd-177">Dispositivos de integração</span><span class="sxs-lookup"><span data-stu-id="ca7bd-177">Onboard Devices</span></span>
<span data-ttu-id="ca7bd-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="ca7bd-178">DeviceId</span></span> | <span data-ttu-id="ca7bd-179">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-179">string</span></span> | <span data-ttu-id="ca7bd-180">Identificador exclusivo do dispositivo no serviço.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="ca7bd-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="ca7bd-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="ca7bd-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="ca7bd-182">DeviceName</span></span> | <span data-ttu-id="ca7bd-183">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-183">string</span></span> | <span data-ttu-id="ca7bd-184">Nome de domínio totalmente qualificado (FQDN) do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="ca7bd-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ca7bd-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="ca7bd-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="ca7bd-186">IsApplicable</span></span> | <span data-ttu-id="ca7bd-187">bool</span><span class="sxs-lookup"><span data-stu-id="ca7bd-187">bool</span></span> | <span data-ttu-id="ca7bd-188">Indica se a configuração ou a política é aplicável</span><span class="sxs-lookup"><span data-stu-id="ca7bd-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="ca7bd-189">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ca7bd-189">true</span></span>
<span data-ttu-id="ca7bd-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="ca7bd-190">IsCompliant</span></span> | <span data-ttu-id="ca7bd-191">bool</span><span class="sxs-lookup"><span data-stu-id="ca7bd-191">bool</span></span> | <span data-ttu-id="ca7bd-192">Indica se a configuração ou política está configurada corretamente</span><span class="sxs-lookup"><span data-stu-id="ca7bd-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="ca7bd-193">falso</span><span class="sxs-lookup"><span data-stu-id="ca7bd-193">false</span></span>
<span data-ttu-id="ca7bd-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="ca7bd-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="ca7bd-195">bool</span><span class="sxs-lookup"><span data-stu-id="ca7bd-195">bool</span></span> | <span data-ttu-id="ca7bd-196">Indica se haverá impacto do usuário se a configuração será aplicada</span><span class="sxs-lookup"><span data-stu-id="ca7bd-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="ca7bd-197">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ca7bd-197">true</span></span>
<span data-ttu-id="ca7bd-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="ca7bd-198">OSPlatform</span></span> | <span data-ttu-id="ca7bd-199">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-199">string</span></span> | <span data-ttu-id="ca7bd-200">Plataforma do sistema operacional em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="ca7bd-201">Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="ca7bd-202">Confira sistemas operacionais e plataformas com suporte para TVM para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="ca7bd-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="ca7bd-203">Windows10</span></span>
<span data-ttu-id="ca7bd-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="ca7bd-204">RbacGroupName</span></span> | <span data-ttu-id="ca7bd-205">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-205">string</span></span> | <span data-ttu-id="ca7bd-206">O grupo controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="ca7bd-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="ca7bd-207">Se esse dispositivo não for atribuído a nenhum grupo RBAC, o valor será "Não atribuído".</span><span class="sxs-lookup"><span data-stu-id="ca7bd-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="ca7bd-208">Se a organização não tiver nenhum grupo RBAC, o valor será "None".</span><span class="sxs-lookup"><span data-stu-id="ca7bd-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="ca7bd-209">Servidores</span><span class="sxs-lookup"><span data-stu-id="ca7bd-209">Servers</span></span>
<span data-ttu-id="ca7bd-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="ca7bd-210">RecommendationReference</span></span> | <span data-ttu-id="ca7bd-211">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-211">string</span></span> | <span data-ttu-id="ca7bd-212">Uma referência à ID de recomendação relacionada a este software.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="ca7bd-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="ca7bd-213">sca-_-scid-20000</span></span>
<span data-ttu-id="ca7bd-214">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="ca7bd-214">Timestamp</span></span> | <span data-ttu-id="ca7bd-215">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-215">string</span></span> | <span data-ttu-id="ca7bd-216">Última vez que a configuração foi vista no dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="ca7bd-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="ca7bd-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="ca7bd-218">1.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="ca7bd-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="ca7bd-219">1.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="ca7bd-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="ca7bd-220">Exemplo de resposta 1.6.2</span><span class="sxs-lookup"><span data-stu-id="ca7bd-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="ca7bd-221">2. Exportar a avaliação de configuração segura (por meio de arquivos)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="ca7bd-222">Descrição do método API 2.1</span><span class="sxs-lookup"><span data-stu-id="ca7bd-222">2.1 API method description</span></span>

<span data-ttu-id="ca7bd-223">Esta resposta à API contém a Avaliação de Configuração Segura em seus dispositivos expostos e retorna uma entrada para cada combinação exclusiva de DeviceId, ConfigurationId.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="ca7bd-224">2.1.2 Limitações</span><span class="sxs-lookup"><span data-stu-id="ca7bd-224">2.1.2 Limitations</span></span>

<span data-ttu-id="ca7bd-225">As limitações de taxa para essa API são 5 chamadas por minuto e 20 chamadas por hora.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="ca7bd-226">2.2 Permissões</span><span class="sxs-lookup"><span data-stu-id="ca7bd-226">2.2 Permissions</span></span>

<span data-ttu-id="ca7bd-227">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="ca7bd-228">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="ca7bd-229">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-229">Permission type</span></span> | <span data-ttu-id="ca7bd-230">Permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-230">Permission</span></span> | <span data-ttu-id="ca7bd-231">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="ca7bd-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="ca7bd-232">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-232">Application</span></span> | <span data-ttu-id="ca7bd-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="ca7bd-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="ca7bd-234">\'Ler informações de vulnerabilidade "Gerenciamento de Ameaças e Vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="ca7bd-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="ca7bd-235">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-235">Delegated (work or school account)</span></span> | <span data-ttu-id="ca7bd-236">Vulnerability.Read</span><span class="sxs-lookup"><span data-stu-id="ca7bd-236">Vulnerability.Read</span></span> | <span data-ttu-id="ca7bd-237">\'Ler informações de vulnerabilidade "Gerenciamento de Ameaças e Vulnerabilidades"\'</span><span class="sxs-lookup"><span data-stu-id="ca7bd-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="ca7bd-238">URL 2.3</span><span class="sxs-lookup"><span data-stu-id="ca7bd-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="ca7bd-239">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ca7bd-239">Parameters</span></span>

- <span data-ttu-id="ca7bd-240">sasValidHours – O número de horas em que as URLs de download serão válidas (Máximo de 24 horas).</span><span class="sxs-lookup"><span data-stu-id="ca7bd-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="ca7bd-241">2.5 Propriedades</span><span class="sxs-lookup"><span data-stu-id="ca7bd-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="ca7bd-242">Os arquivos são gzip compactados & no formato Json de várias linhas.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="ca7bd-243">As URLs de download só são válidas por 3 horas; caso contrário, você pode usar o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="ca7bd-244">Para a velocidade máxima de download de seus dados, você pode garantir que você está baixando da mesma região do Azure na qual seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="ca7bd-245">Propriedade (ID)</span><span class="sxs-lookup"><span data-stu-id="ca7bd-245">Property (ID)</span></span> | <span data-ttu-id="ca7bd-246">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ca7bd-246">Data type</span></span> | <span data-ttu-id="ca7bd-247">Descrição</span><span class="sxs-lookup"><span data-stu-id="ca7bd-247">Description</span></span> | <span data-ttu-id="ca7bd-248">Exemplo de um valor retornado</span><span class="sxs-lookup"><span data-stu-id="ca7bd-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="ca7bd-249">Exportar arquivos</span><span class="sxs-lookup"><span data-stu-id="ca7bd-249">Export files</span></span> | <span data-ttu-id="ca7bd-250">cadeia de \[ caracteres de matriz\]</span><span class="sxs-lookup"><span data-stu-id="ca7bd-250">array\[string\]</span></span> | <span data-ttu-id="ca7bd-251">Uma lista de URLs de download para arquivos que segurando o instantâneo atual da organização</span><span class="sxs-lookup"><span data-stu-id="ca7bd-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="ca7bd-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="ca7bd-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="ca7bd-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="ca7bd-253">GeneratedTime</span></span> | <span data-ttu-id="ca7bd-254">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ca7bd-254">string</span></span> | <span data-ttu-id="ca7bd-255">A hora em que a exportação foi gerada.</span><span class="sxs-lookup"><span data-stu-id="ca7bd-255">The time that the export was generated.</span></span> | <span data-ttu-id="ca7bd-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="ca7bd-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="ca7bd-257">2.6 Exemplos</span><span class="sxs-lookup"><span data-stu-id="ca7bd-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="ca7bd-258">2.6.1 Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="ca7bd-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="ca7bd-259">Exemplo de resposta 2.6.2</span><span class="sxs-lookup"><span data-stu-id="ca7bd-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="ca7bd-260">Confira também</span><span class="sxs-lookup"><span data-stu-id="ca7bd-260">See also</span></span>

- [<span data-ttu-id="ca7bd-261">Exportar métodos e propriedades de avaliação por dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="ca7bd-262">Exportar avaliação de inventário de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="ca7bd-263">Exportar a avaliação de vulnerabilidades de software por dispositivo</span><span class="sxs-lookup"><span data-stu-id="ca7bd-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="ca7bd-264">Outros relacionados</span><span class="sxs-lookup"><span data-stu-id="ca7bd-264">Other related</span></span>

- [<span data-ttu-id="ca7bd-265">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="ca7bd-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="ca7bd-266">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="ca7bd-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)