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
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054271"
---
# <a name="manage-indicators"></a><span data-ttu-id="45da0-104">Gerenciar indicadores</span><span class="sxs-lookup"><span data-stu-id="45da0-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="45da0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="45da0-105">**Applies to:**</span></span>
- [<span data-ttu-id="45da0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="45da0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="45da0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="45da0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="45da0-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="45da0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45da0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="45da0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="45da0-110">No painel de navegação, selecione **Indicadores de**  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="45da0-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="45da0-111">Selecione a guia do tipo de entidade que você gostaria de gerenciar.</span><span class="sxs-lookup"><span data-stu-id="45da0-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="45da0-112">Atualize os detalhes do indicador e clique em **Salvar** ou clique no botão **Excluir** se quiser remover a entidade da lista.</span><span class="sxs-lookup"><span data-stu-id="45da0-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="45da0-113">Importar uma lista de IoCs</span><span class="sxs-lookup"><span data-stu-id="45da0-113">Import a list of IoCs</span></span>

<span data-ttu-id="45da0-114">Você também pode optar por carregar um arquivo CSV que define os atributos dos indicadores, a ação a ser tomada e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="45da0-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="45da0-115">Baixe o CSV de exemplo para saber os atributos de coluna com suporte.</span><span class="sxs-lookup"><span data-stu-id="45da0-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="45da0-116">No painel de navegação, selecione **Indicadores de**  >  **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="45da0-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="45da0-117">Selecione a guia do tipo de entidade para o qual você gostaria de importar indicadores.</span><span class="sxs-lookup"><span data-stu-id="45da0-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="45da0-118">Selecione **Importar**  >  **Escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="45da0-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="45da0-119">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="45da0-119">Select **Import**.</span></span> <span data-ttu-id="45da0-120">Faça isso para todos os arquivos que você gostaria de importar.</span><span class="sxs-lookup"><span data-stu-id="45da0-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="45da0-121">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="45da0-121">Select **Done**.</span></span>

<span data-ttu-id="45da0-122">A tabela a seguir mostra os parâmetros com suporte.</span><span class="sxs-lookup"><span data-stu-id="45da0-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="45da0-123">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="45da0-123">Parameter</span></span> | <span data-ttu-id="45da0-124">Tipo</span><span class="sxs-lookup"><span data-stu-id="45da0-124">Type</span></span>    |   <span data-ttu-id="45da0-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="45da0-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="45da0-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="45da0-126">indicatorType</span></span> | <span data-ttu-id="45da0-127">Enum</span><span class="sxs-lookup"><span data-stu-id="45da0-127">Enum</span></span> | <span data-ttu-id="45da0-128">Tipo do indicador.</span><span class="sxs-lookup"><span data-stu-id="45da0-128">Type of the indicator.</span></span> <span data-ttu-id="45da0-129">Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".</span><span class="sxs-lookup"><span data-stu-id="45da0-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="45da0-130">**Required**</span><span class="sxs-lookup"><span data-stu-id="45da0-130">**Required**</span></span>
<span data-ttu-id="45da0-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="45da0-131">indicatorValue</span></span> | <span data-ttu-id="45da0-132">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-132">String</span></span> | <span data-ttu-id="45da0-133">Identidade da entidade [Indicator.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="45da0-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="45da0-134">**Required**</span><span class="sxs-lookup"><span data-stu-id="45da0-134">**Required**</span></span>
<span data-ttu-id="45da0-135">ação</span><span class="sxs-lookup"><span data-stu-id="45da0-135">action</span></span> | <span data-ttu-id="45da0-136">Enum</span><span class="sxs-lookup"><span data-stu-id="45da0-136">Enum</span></span> | <span data-ttu-id="45da0-137">A ação que será tomada se o indicador for descoberto na organização.</span><span class="sxs-lookup"><span data-stu-id="45da0-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="45da0-138">Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed".</span><span class="sxs-lookup"><span data-stu-id="45da0-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="45da0-139">**Required**</span><span class="sxs-lookup"><span data-stu-id="45da0-139">**Required**</span></span>
<span data-ttu-id="45da0-140">title</span><span class="sxs-lookup"><span data-stu-id="45da0-140">title</span></span> | <span data-ttu-id="45da0-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-141">String</span></span> | <span data-ttu-id="45da0-142">Título de alerta de indicador.</span><span class="sxs-lookup"><span data-stu-id="45da0-142">Indicator alert title.</span></span> <span data-ttu-id="45da0-143">**Required**</span><span class="sxs-lookup"><span data-stu-id="45da0-143">**Required**</span></span>
<span data-ttu-id="45da0-144">descrição</span><span class="sxs-lookup"><span data-stu-id="45da0-144">description</span></span> | <span data-ttu-id="45da0-145">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-145">String</span></span> |  <span data-ttu-id="45da0-146">Descrição do indicador.</span><span class="sxs-lookup"><span data-stu-id="45da0-146">Description of the indicator.</span></span> <span data-ttu-id="45da0-147">**Required**</span><span class="sxs-lookup"><span data-stu-id="45da0-147">**Required**</span></span>
<span data-ttu-id="45da0-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="45da0-148">expirationTime</span></span> | <span data-ttu-id="45da0-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="45da0-149">DateTimeOffset</span></span> | <span data-ttu-id="45da0-150">O tempo de expiração do indicador no formato a seguir YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="45da0-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="45da0-151">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="45da0-151">**Optional**</span></span>
<span data-ttu-id="45da0-152">severity</span><span class="sxs-lookup"><span data-stu-id="45da0-152">severity</span></span> | <span data-ttu-id="45da0-153">Enum</span><span class="sxs-lookup"><span data-stu-id="45da0-153">Enum</span></span> | <span data-ttu-id="45da0-154">A gravidade do indicador.</span><span class="sxs-lookup"><span data-stu-id="45da0-154">The severity of the indicator.</span></span> <span data-ttu-id="45da0-155">Os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto".</span><span class="sxs-lookup"><span data-stu-id="45da0-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="45da0-156">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="45da0-156">**Optional**</span></span>
<span data-ttu-id="45da0-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="45da0-157">recommendedActions</span></span> | <span data-ttu-id="45da0-158">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-158">String</span></span> | <span data-ttu-id="45da0-159">Ações recomendadas do alerta de ti.</span><span class="sxs-lookup"><span data-stu-id="45da0-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="45da0-160">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="45da0-160">**Optional**</span></span>
<span data-ttu-id="45da0-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="45da0-161">rbacGroupNames</span></span> | <span data-ttu-id="45da0-162">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-162">String</span></span> | <span data-ttu-id="45da0-163">Lista separada por vírgulas de nomes de grupo do RBAC aos que o indicador seria aplicado.</span><span class="sxs-lookup"><span data-stu-id="45da0-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="45da0-164">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="45da0-164">**Optional**</span></span>
<span data-ttu-id="45da0-165">category</span><span class="sxs-lookup"><span data-stu-id="45da0-165">category</span></span> | <span data-ttu-id="45da0-166">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-166">String</span></span> | <span data-ttu-id="45da0-167">Categoria do alerta.</span><span class="sxs-lookup"><span data-stu-id="45da0-167">Category of the alert.</span></span> <span data-ttu-id="45da0-168">Exemplos incluem: execução e acesso de credenciais.</span><span class="sxs-lookup"><span data-stu-id="45da0-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="45da0-169">**Opcional**</span><span class="sxs-lookup"><span data-stu-id="45da0-169">**Optional**</span></span>
<span data-ttu-id="45da0-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="45da0-170">mitretechniques</span></span>| <span data-ttu-id="45da0-171">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="45da0-171">String</span></span> | <span data-ttu-id="45da0-172">Código/id de técnicas MITRE (vírgula separada).</span><span class="sxs-lookup"><span data-stu-id="45da0-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="45da0-173">Para obter mais informações, consulte [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="45da0-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="45da0-174">**Opcional** É recomendável adicionar um valor na categoria quando uma técnica MITRE.</span><span class="sxs-lookup"><span data-stu-id="45da0-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="45da0-175">Para obter mais informações, consulte Categorias de alerta do Microsoft Defender for Endpoint agora estão alinhadas com [o MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span><span class="sxs-lookup"><span data-stu-id="45da0-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="45da0-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="45da0-176">See also</span></span>
- [<span data-ttu-id="45da0-177">Criar indicadores</span><span class="sxs-lookup"><span data-stu-id="45da0-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="45da0-178">Criar indicadores para arquivos</span><span class="sxs-lookup"><span data-stu-id="45da0-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="45da0-179">Criar indicadores para IPs e URLs/domínios</span><span class="sxs-lookup"><span data-stu-id="45da0-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="45da0-180">Criar indicadores com base em certificados</span><span class="sxs-lookup"><span data-stu-id="45da0-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
