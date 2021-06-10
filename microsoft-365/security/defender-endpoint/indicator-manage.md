---
title: Gerenciar indicadores
ms.reviewer: ''
description: Gerencie indicadores para um hash de arquivo, endereço IP, URLs ou domínios que definem a detecção, a prevenção e a exclusão de entidades.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185940"
---
# <a name="manage-indicators"></a><span data-ttu-id="706b1-104">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="706b1-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="706b1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="706b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="706b1-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="706b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="706b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="706b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="706b1-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="706b1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="706b1-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="706b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="706b1-110">No painel de navegação, selecione **Configurações**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="706b1-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="706b1-111">Selecione a guia do tipo de entidade que você gostaria de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="706b1-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="706b1-112">Atualize os detalhes do indicador e clique em **Salvar** ou clique no botão **Excluir** se quiser remover a entidade da lista.</span><span class="sxs-lookup"><span data-stu-id="706b1-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="706b1-113">Importar uma lista de IoCs</span><span class="sxs-lookup"><span data-stu-id="706b1-113">Import a list of IoCs</span></span>

<span data-ttu-id="706b1-114">Você também pode optar por carregar um arquivo CSV que define os atributos dos indicadores, a ação a ser tomada e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="706b1-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="706b1-115">Baixe o CSV de exemplo para saber os atributos de coluna com suporte.</span><span class="sxs-lookup"><span data-stu-id="706b1-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="706b1-116">No painel de navegação, selecione **Configurações**  >  **Indicadores**.</span><span class="sxs-lookup"><span data-stu-id="706b1-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="706b1-117">Selecione a guia do tipo de entidade para o qual você gostaria de importar indicadores.</span><span class="sxs-lookup"><span data-stu-id="706b1-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="706b1-118">Selecione **Importar**  >  **Escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="706b1-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="706b1-119">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="706b1-119">Select **Import**.</span></span> <span data-ttu-id="706b1-120">Faça isso para todos os arquivos que você gostaria de importar.</span><span class="sxs-lookup"><span data-stu-id="706b1-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="706b1-121">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="706b1-121">Select **Done**.</span></span>

<span data-ttu-id="706b1-122">A tabela a seguir mostra os parâmetros com suporte.</span><span class="sxs-lookup"><span data-stu-id="706b1-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="706b1-123">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="706b1-123">Parameter</span></span> | <span data-ttu-id="706b1-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="706b1-124">Type</span></span>    |   <span data-ttu-id="706b1-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="706b1-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="706b1-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="706b1-126">indicatorType</span></span> | <span data-ttu-id="706b1-127">Enum</span><span class="sxs-lookup"><span data-stu-id="706b1-127">Enum</span></span> | <span data-ttu-id="706b1-128">Tipo do indicador.</span><span class="sxs-lookup"><span data-stu-id="706b1-128">Type of the indicator.</span></span> <span data-ttu-id="706b1-129">Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="706b1-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="706b1-130">**Required**</span><span class="sxs-lookup"><span data-stu-id="706b1-130">**Required**</span></span>
<span data-ttu-id="706b1-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="706b1-131">indicatorValue</span></span> | <span data-ttu-id="706b1-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-132">String</span></span> | <span data-ttu-id="706b1-133">Identidade da entidade [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="706b1-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="706b1-134">**Required**</span><span class="sxs-lookup"><span data-stu-id="706b1-134">**Required**</span></span>
<span data-ttu-id="706b1-135">ação</span><span class="sxs-lookup"><span data-stu-id="706b1-135">action</span></span> | <span data-ttu-id="706b1-136">Enum</span><span class="sxs-lookup"><span data-stu-id="706b1-136">Enum</span></span> | <span data-ttu-id="706b1-137">A ação que será tomada se o indicador for descoberto na organização.</span><span class="sxs-lookup"><span data-stu-id="706b1-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="706b1-138">Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="706b1-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="706b1-139">**Required**</span><span class="sxs-lookup"><span data-stu-id="706b1-139">**Required**</span></span>
<span data-ttu-id="706b1-140">title</span><span class="sxs-lookup"><span data-stu-id="706b1-140">title</span></span> | <span data-ttu-id="706b1-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-141">String</span></span> | <span data-ttu-id="706b1-142">Título de alerta de indicador.</span><span class="sxs-lookup"><span data-stu-id="706b1-142">Indicator alert title.</span></span> <span data-ttu-id="706b1-143">**Required**</span><span class="sxs-lookup"><span data-stu-id="706b1-143">**Required**</span></span>
<span data-ttu-id="706b1-144">descrição</span><span class="sxs-lookup"><span data-stu-id="706b1-144">description</span></span> | <span data-ttu-id="706b1-145">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-145">String</span></span> |  <span data-ttu-id="706b1-146">Descrição do indicador.</span><span class="sxs-lookup"><span data-stu-id="706b1-146">Description of the indicator.</span></span> <span data-ttu-id="706b1-147">**Required**</span><span class="sxs-lookup"><span data-stu-id="706b1-147">**Required**</span></span>
<span data-ttu-id="706b1-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="706b1-148">expirationTime</span></span> | <span data-ttu-id="706b1-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="706b1-149">DateTimeOffset</span></span> | <span data-ttu-id="706b1-150">O tempo de expiração do indicador no formato a seguir YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="706b1-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="706b1-151">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="706b1-151">**Optional**</span></span>
<span data-ttu-id="706b1-152">severity</span><span class="sxs-lookup"><span data-stu-id="706b1-152">severity</span></span> | <span data-ttu-id="706b1-153">Enum</span><span class="sxs-lookup"><span data-stu-id="706b1-153">Enum</span></span> | <span data-ttu-id="706b1-154">A gravidade do indicador.</span><span class="sxs-lookup"><span data-stu-id="706b1-154">The severity of the indicator.</span></span> <span data-ttu-id="706b1-155">Os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto".</span><span class="sxs-lookup"><span data-stu-id="706b1-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="706b1-156">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="706b1-156">**Optional**</span></span>
<span data-ttu-id="706b1-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="706b1-157">recommendedActions</span></span> | <span data-ttu-id="706b1-158">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-158">String</span></span> | <span data-ttu-id="706b1-159">Ações recomendadas do alerta de ti.</span><span class="sxs-lookup"><span data-stu-id="706b1-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="706b1-160">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="706b1-160">**Optional**</span></span>
<span data-ttu-id="706b1-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="706b1-161">rbacGroupNames</span></span> | <span data-ttu-id="706b1-162">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-162">String</span></span> | <span data-ttu-id="706b1-163">Lista separada por vírgulas de nomes de grupo do RBAC aos que o indicador seria aplicado.</span><span class="sxs-lookup"><span data-stu-id="706b1-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="706b1-164">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="706b1-164">**Optional**</span></span>
<span data-ttu-id="706b1-165">category</span><span class="sxs-lookup"><span data-stu-id="706b1-165">category</span></span> | <span data-ttu-id="706b1-166">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-166">String</span></span> | <span data-ttu-id="706b1-167">Categoria do alerta.</span><span class="sxs-lookup"><span data-stu-id="706b1-167">Category of the alert.</span></span> <span data-ttu-id="706b1-168">Exemplos incluem: execução e acesso de credenciais.</span><span class="sxs-lookup"><span data-stu-id="706b1-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="706b1-169">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="706b1-169">**Optional**</span></span>
<span data-ttu-id="706b1-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="706b1-170">mitretechniques</span></span>| <span data-ttu-id="706b1-171">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="706b1-171">String</span></span> | <span data-ttu-id="706b1-172">Código/id de técnicas MITRE (vírgula separada).</span><span class="sxs-lookup"><span data-stu-id="706b1-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="706b1-173">Para obter mais informações, [consulte Enterprise táticas](https://attack.mitre.org/tactics/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="706b1-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="706b1-174">**Opcional** É recomendável adicionar um valor na categoria quando uma técnica MITRE.</span><span class="sxs-lookup"><span data-stu-id="706b1-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="706b1-175">Para obter mais informações, consulte Categorias de alerta do Microsoft Defender for Endpoint agora estão alinhadas com [o MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span><span class="sxs-lookup"><span data-stu-id="706b1-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="706b1-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="706b1-176">See also</span></span>
- [<span data-ttu-id="706b1-177">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="706b1-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="706b1-178">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="706b1-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="706b1-179">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="706b1-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="706b1-180">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="706b1-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
