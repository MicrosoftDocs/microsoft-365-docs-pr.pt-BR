---
title: Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Descreve como configurar o Microsoft Defender para Ponto de Extremidade no Linux em empresas.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7998e878ad03fdfb64c314dc8b7234ece46164ce
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289482"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="d83f5-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="d83f5-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d83f5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d83f5-105">**Applies to:**</span></span>
- [<span data-ttu-id="d83f5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d83f5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d83f5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d83f5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d83f5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d83f5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d83f5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d83f5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="d83f5-110">Este tópico contém instruções sobre como definir preferências para o Defender para o Ponto de Extremidade no Linux em ambientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="d83f5-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="d83f5-111">Se você estiver interessado em configurar o produto em um dispositivo da linha de comando, consulte [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="d83f5-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="d83f5-112">Em ambientes corporativos, o Defender for Endpoint no Linux pode ser gerenciado por meio de um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="d83f5-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="d83f5-113">Esse perfil é implantado a partir da ferramenta de gerenciamento de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="d83f5-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="d83f5-114">As preferências gerenciadas pela empresa têm precedência sobre as definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d83f5-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="d83f5-115">Em outras palavras, os usuários em sua empresa não são capazes de alterar as preferências definidas por meio desse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="d83f5-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="d83f5-116">Este artigo descreve a estrutura desse perfil (incluindo um perfil recomendado que você pode usar para começar) e instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="d83f5-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="d83f5-117">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="d83f5-117">Configuration profile structure</span></span>

<span data-ttu-id="d83f5-118">O perfil de configuração é um arquivo .json que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="d83f5-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="d83f5-119">Os valores podem ser simples, como um valor numérico ou complexo, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="d83f5-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="d83f5-120">Normalmente, você usaria uma ferramenta de gerenciamento de configuração para pressionar um arquivo com o nome ```mdatp_managed.json``` no local ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="d83f5-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="d83f5-121">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do produto, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="d83f5-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="d83f5-122">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="d83f5-122">Antivirus engine preferences</span></span>

<span data-ttu-id="d83f5-123">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do produto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

<br>

****

|<span data-ttu-id="d83f5-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-124">Description</span></span>|<span data-ttu-id="d83f5-125">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-125">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-126">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-126">**Key**</span></span>|<span data-ttu-id="d83f5-127">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="d83f5-127">antivirusEngine</span></span>|
|<span data-ttu-id="d83f5-128">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-128">**Data type**</span></span>|<span data-ttu-id="d83f5-129">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="d83f5-129">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="d83f5-130">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-130">**Comments**</span></span>|<span data-ttu-id="d83f5-131">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="d83f5-131">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="d83f5-132">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="d83f5-132">Enable / disable real-time protection</span></span>

<span data-ttu-id="d83f5-133">Determina se a proteção em tempo real (arquivos de verificação conforme eles são acessados) está habilitada ou não.</span><span class="sxs-lookup"><span data-stu-id="d83f5-133">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

<br>

****

|<span data-ttu-id="d83f5-134">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-134">Description</span></span>|<span data-ttu-id="d83f5-135">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-135">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-136">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-136">**Key**</span></span>|<span data-ttu-id="d83f5-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="d83f5-137">enableRealTimeProtection</span></span>|
|<span data-ttu-id="d83f5-138">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-138">**Data type**</span></span>|<span data-ttu-id="d83f5-139">Booliano</span><span class="sxs-lookup"><span data-stu-id="d83f5-139">Boolean</span></span>|
|<span data-ttu-id="d83f5-140">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-140">**Possible values**</span></span>|<span data-ttu-id="d83f5-141">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-141">true (default)</span></span> <p> <span data-ttu-id="d83f5-142">falso</span><span class="sxs-lookup"><span data-stu-id="d83f5-142">false</span></span>|
|

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="d83f5-143">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="d83f5-143">Enable / disable passive mode</span></span>

<span data-ttu-id="d83f5-144">Determina se o mecanismo antivírus é executado no modo passivo ou não.</span><span class="sxs-lookup"><span data-stu-id="d83f5-144">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="d83f5-145">No modo passivo:</span><span class="sxs-lookup"><span data-stu-id="d83f5-145">In passive mode:</span></span>

- <span data-ttu-id="d83f5-146">A proteção em tempo real está desligada.</span><span class="sxs-lookup"><span data-stu-id="d83f5-146">Real-time protection is turned off.</span></span>
- <span data-ttu-id="d83f5-147">A verificação sob demanda está 100% 100%.</span><span class="sxs-lookup"><span data-stu-id="d83f5-147">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="d83f5-148">A correção automática de ameaças está desligada.</span><span class="sxs-lookup"><span data-stu-id="d83f5-148">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="d83f5-149">As atualizações de inteligência de segurança estão ativas.</span><span class="sxs-lookup"><span data-stu-id="d83f5-149">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="d83f5-150">O ícone do menu Status está oculto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-150">Status menu icon is hidden.</span></span>

<br>

****

|<span data-ttu-id="d83f5-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-151">Description</span></span>|<span data-ttu-id="d83f5-152">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-152">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-153">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-153">**Key**</span></span>|<span data-ttu-id="d83f5-154">passiveMode</span><span class="sxs-lookup"><span data-stu-id="d83f5-154">passiveMode</span></span>|
|<span data-ttu-id="d83f5-155">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-155">**Data type**</span></span>|<span data-ttu-id="d83f5-156">Booliano</span><span class="sxs-lookup"><span data-stu-id="d83f5-156">Boolean</span></span>|
|<span data-ttu-id="d83f5-157">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-157">**Possible values**</span></span>|<span data-ttu-id="d83f5-158">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-158">false (default)</span></span> <p> <span data-ttu-id="d83f5-159">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="d83f5-159">true</span></span>|
|<span data-ttu-id="d83f5-160">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-160">**Comments**</span></span>|<span data-ttu-id="d83f5-161">Disponível no Defender para Ponto de Extremidade versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-161">Available in Defender for Endpoint version 100.67.60 or higher.</span></span>|
|

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="d83f5-162">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="d83f5-162">Exclusion merge policy</span></span>

<span data-ttu-id="d83f5-163">Especifica a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="d83f5-163">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="d83f5-164">Pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d83f5-164">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="d83f5-165">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="d83f5-165">This setting can be used to restrict local users from defining their own exclusions.</span></span>

<br>

****

|<span data-ttu-id="d83f5-166">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-166">Description</span></span>|<span data-ttu-id="d83f5-167">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-167">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-168">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-168">**Key**</span></span>|<span data-ttu-id="d83f5-169">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d83f5-169">exclusionsMergePolicy</span></span>|
|<span data-ttu-id="d83f5-170">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-170">**Data type**</span></span>|<span data-ttu-id="d83f5-171">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-171">String</span></span>|
|<span data-ttu-id="d83f5-172">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-172">**Possible values**</span></span>|<span data-ttu-id="d83f5-173">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-173">merge (default)</span></span> <p> <span data-ttu-id="d83f5-174">admin_only</span><span class="sxs-lookup"><span data-stu-id="d83f5-174">admin_only</span></span>|
|<span data-ttu-id="d83f5-175">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-175">**Comments**</span></span>|<span data-ttu-id="d83f5-176">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-176">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="scan-exclusions"></a><span data-ttu-id="d83f5-177">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="d83f5-177">Scan exclusions</span></span>

<span data-ttu-id="d83f5-178">Entidades que foram excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="d83f5-178">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="d83f5-179">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d83f5-179">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="d83f5-180">(As exclusões são especificadas como uma matriz de itens, o administrador pode especificar quantos elementos for necessário, em qualquer ordem.)</span><span class="sxs-lookup"><span data-stu-id="d83f5-180">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

<br>

****

|<span data-ttu-id="d83f5-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-181">Description</span></span>|<span data-ttu-id="d83f5-182">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-182">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-183">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-183">**Key**</span></span>|<span data-ttu-id="d83f5-184">exclusões</span><span class="sxs-lookup"><span data-stu-id="d83f5-184">exclusions</span></span>|
|<span data-ttu-id="d83f5-185">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-185">**Data type**</span></span>|<span data-ttu-id="d83f5-186">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="d83f5-186">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="d83f5-187">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-187">**Comments**</span></span>|<span data-ttu-id="d83f5-188">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="d83f5-188">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="type-of-exclusion"></a><span data-ttu-id="d83f5-189">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="d83f5-189">Type of exclusion</span></span>

<span data-ttu-id="d83f5-190">Especifica o tipo de conteúdo excluído da verificação.</span><span class="sxs-lookup"><span data-stu-id="d83f5-190">Specifies the type of content excluded from the scan.</span></span>

<br>

****

|<span data-ttu-id="d83f5-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-191">Description</span></span>|<span data-ttu-id="d83f5-192">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-192">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-193">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-193">**Key**</span></span>|<span data-ttu-id="d83f5-194">$type</span><span class="sxs-lookup"><span data-stu-id="d83f5-194">$type</span></span>|
|<span data-ttu-id="d83f5-195">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-195">**Data type**</span></span>|<span data-ttu-id="d83f5-196">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-196">String</span></span>|
|<span data-ttu-id="d83f5-197">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-197">**Possible values**</span></span>|<span data-ttu-id="d83f5-198">excludedPath</span><span class="sxs-lookup"><span data-stu-id="d83f5-198">excludedPath</span></span> <p> <span data-ttu-id="d83f5-199">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="d83f5-199">excludedFileExtension</span></span> <p> <span data-ttu-id="d83f5-200">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="d83f5-200">excludedFileName</span></span>|
|

##### <a name="path-to-excluded-content"></a><span data-ttu-id="d83f5-201">Caminho para conteúdo excluído</span><span class="sxs-lookup"><span data-stu-id="d83f5-201">Path to excluded content</span></span>

<span data-ttu-id="d83f5-202">Usado para excluir conteúdo da verificação por caminho de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="d83f5-202">Used to exclude content from the scan by full file path.</span></span>

<br>

****

|<span data-ttu-id="d83f5-203">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-203">Description</span></span>|<span data-ttu-id="d83f5-204">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-204">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-205">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-205">**Key**</span></span>|<span data-ttu-id="d83f5-206">caminho</span><span class="sxs-lookup"><span data-stu-id="d83f5-206">path</span></span>|
|<span data-ttu-id="d83f5-207">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-207">**Data type**</span></span>|<span data-ttu-id="d83f5-208">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-208">String</span></span>|
|<span data-ttu-id="d83f5-209">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-209">**Possible values**</span></span>|<span data-ttu-id="d83f5-210">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="d83f5-210">valid paths</span></span>|
|<span data-ttu-id="d83f5-211">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-211">**Comments**</span></span>|<span data-ttu-id="d83f5-212">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="d83f5-212">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="path-type-file--directory"></a><span data-ttu-id="d83f5-213">Tipo de caminho (arquivo/diretório)</span><span class="sxs-lookup"><span data-stu-id="d83f5-213">Path type (file / directory)</span></span>

<span data-ttu-id="d83f5-214">Indica se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="d83f5-214">Indicates if the *path* property refers to a file or directory.</span></span>

<br>

****

|<span data-ttu-id="d83f5-215">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-215">Description</span></span>|<span data-ttu-id="d83f5-216">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-216">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-217">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-217">**Key**</span></span>|<span data-ttu-id="d83f5-218">isDirectory</span><span class="sxs-lookup"><span data-stu-id="d83f5-218">isDirectory</span></span>|
|<span data-ttu-id="d83f5-219">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-219">**Data type**</span></span>|<span data-ttu-id="d83f5-220">Booliano</span><span class="sxs-lookup"><span data-stu-id="d83f5-220">Boolean</span></span>|
|<span data-ttu-id="d83f5-221">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-221">**Possible values**</span></span>|<span data-ttu-id="d83f5-222">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-222">false (default)</span></span> <p> <span data-ttu-id="d83f5-223">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="d83f5-223">true</span></span>|
|<span data-ttu-id="d83f5-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-224">**Comments**</span></span>|<span data-ttu-id="d83f5-225">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="d83f5-225">Applicable only if *$type* is *excludedPath*</span></span>|
|

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="d83f5-226">Extensão de arquivo excluída da verificação</span><span class="sxs-lookup"><span data-stu-id="d83f5-226">File extension excluded from the scan</span></span>

<span data-ttu-id="d83f5-227">Usado para excluir conteúdo da verificação por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="d83f5-227">Used to exclude content from the scan by file extension.</span></span>

<br>

****

|<span data-ttu-id="d83f5-228">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-228">Description</span></span>|<span data-ttu-id="d83f5-229">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-229">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-230">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-230">**Key**</span></span>|<span data-ttu-id="d83f5-231">extension</span><span class="sxs-lookup"><span data-stu-id="d83f5-231">extension</span></span>|
|<span data-ttu-id="d83f5-232">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-232">**Data type**</span></span>|<span data-ttu-id="d83f5-233">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-233">String</span></span>|
|<span data-ttu-id="d83f5-234">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-234">**Possible values**</span></span>|<span data-ttu-id="d83f5-235">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="d83f5-235">valid file extensions</span></span>|
|<span data-ttu-id="d83f5-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-236">**Comments**</span></span>|<span data-ttu-id="d83f5-237">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="d83f5-237">Applicable only if *$type* is *excludedFileExtension*</span></span>|
|

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="d83f5-238">Processo excluído da verificação\*</span><span class="sxs-lookup"><span data-stu-id="d83f5-238">Process excluded from the scan\*</span></span>

<span data-ttu-id="d83f5-239">Especifica um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="d83f5-239">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="d83f5-240">O processo pode ser especificado pelo nome (por exemplo) `cat` ou caminho completo (por exemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="d83f5-240">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

<br>

****

|<span data-ttu-id="d83f5-241">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-241">Description</span></span>|<span data-ttu-id="d83f5-242">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-242">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-243">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-243">**Key**</span></span>|<span data-ttu-id="d83f5-244">nome</span><span class="sxs-lookup"><span data-stu-id="d83f5-244">name</span></span>|
|<span data-ttu-id="d83f5-245">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-245">**Data type**</span></span>|<span data-ttu-id="d83f5-246">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-246">String</span></span>|
|<span data-ttu-id="d83f5-247">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-247">**Possible values**</span></span>|<span data-ttu-id="d83f5-248">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-248">any string</span></span>|
|<span data-ttu-id="d83f5-249">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-249">**Comments**</span></span>|<span data-ttu-id="d83f5-250">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="d83f5-250">Applicable only if *$type* is *excludedFileName*</span></span>|
|

#### <a name="allowed-threats"></a><span data-ttu-id="d83f5-251">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="d83f5-251">Allowed threats</span></span>

<span data-ttu-id="d83f5-252">Lista de ameaças (identificadas pelo nome) que não são bloqueadas pelo produto e têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="d83f5-252">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

<br>

****

|<span data-ttu-id="d83f5-253">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-253">Description</span></span>|<span data-ttu-id="d83f5-254">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-254">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-255">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-255">**Key**</span></span>|<span data-ttu-id="d83f5-256">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="d83f5-256">allowedThreats</span></span>|
|<span data-ttu-id="d83f5-257">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-257">**Data type**</span></span>|<span data-ttu-id="d83f5-258">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-258">Array of strings</span></span>|
|

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="d83f5-259">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="d83f5-259">Disallowed threat actions</span></span>

<span data-ttu-id="d83f5-260">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="d83f5-260">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="d83f5-261">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="d83f5-261">The actions included in this list are not displayed in the user interface.</span></span>

<br>

****

|<span data-ttu-id="d83f5-262">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-262">Description</span></span>|<span data-ttu-id="d83f5-263">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-263">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-264">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-264">**Key**</span></span>|<span data-ttu-id="d83f5-265">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="d83f5-265">disallowedThreatActions</span></span>|
|<span data-ttu-id="d83f5-266">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-266">**Data type**</span></span>|<span data-ttu-id="d83f5-267">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-267">Array of strings</span></span>|
|<span data-ttu-id="d83f5-268">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-268">**Possible values**</span></span>|<span data-ttu-id="d83f5-269">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="d83f5-269">allow (restricts users from allowing threats)</span></span> <p> <span data-ttu-id="d83f5-270">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="d83f5-270">restore (restricts users from restoring threats from the quarantine)</span></span>|
|<span data-ttu-id="d83f5-271">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-271">**Comments**</span></span>|<span data-ttu-id="d83f5-272">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-272">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="threat-type-settings"></a><span data-ttu-id="d83f5-273">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="d83f5-273">Threat type settings</span></span>

<span data-ttu-id="d83f5-274">A *preferência threatTypeSettings* no mecanismo antivírus é usada para controlar como determinados tipos de ameaça são manipulados pelo produto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-274">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

<br>

****

|<span data-ttu-id="d83f5-275">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-275">Description</span></span>|<span data-ttu-id="d83f5-276">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-276">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-277">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-277">**Key**</span></span>|<span data-ttu-id="d83f5-278">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="d83f5-278">threatTypeSettings</span></span>|
|<span data-ttu-id="d83f5-279">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-279">**Data type**</span></span>|<span data-ttu-id="d83f5-280">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="d83f5-280">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="d83f5-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-281">**Comments**</span></span>|<span data-ttu-id="d83f5-282">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="d83f5-282">See the following sections for a description of the dictionary contents.</span></span>|
|

##### <a name="threat-type"></a><span data-ttu-id="d83f5-283">Tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="d83f5-283">Threat type</span></span>

<span data-ttu-id="d83f5-284">Tipo de ameaça para a qual o comportamento está configurado.</span><span class="sxs-lookup"><span data-stu-id="d83f5-284">Type of threat for which the behavior is configured.</span></span>

<br>

****

|<span data-ttu-id="d83f5-285">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-285">Description</span></span>|<span data-ttu-id="d83f5-286">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-286">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-287">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-287">**Key**</span></span>|<span data-ttu-id="d83f5-288">chave</span><span class="sxs-lookup"><span data-stu-id="d83f5-288">key</span></span>|
|<span data-ttu-id="d83f5-289">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-289">**Data type**</span></span>|<span data-ttu-id="d83f5-290">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-290">String</span></span>|
|<span data-ttu-id="d83f5-291">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-291">**Possible values**</span></span>|<span data-ttu-id="d83f5-292">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="d83f5-292">potentially_unwanted_application</span></span> <p> <span data-ttu-id="d83f5-293">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="d83f5-293">archive_bomb</span></span>|
|

##### <a name="action-to-take"></a><span data-ttu-id="d83f5-294">O que fazer</span><span class="sxs-lookup"><span data-stu-id="d83f5-294">Action to take</span></span>

<span data-ttu-id="d83f5-295">Ação a ser tomada ao se deparar com uma ameaça do tipo especificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-295">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="d83f5-296">Pode ser:</span><span class="sxs-lookup"><span data-stu-id="d83f5-296">Can be:</span></span>

- <span data-ttu-id="d83f5-297">**Auditoria**: o dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="d83f5-297">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="d83f5-298">**Bloquear**: o dispositivo é protegido contra esse tipo de ameaça e você é notificado no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="d83f5-298">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="d83f5-299">**Off**: O dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="d83f5-299">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

<br>

****

|<span data-ttu-id="d83f5-300">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-300">Description</span></span>|<span data-ttu-id="d83f5-301">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-301">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-302">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-302">**Key**</span></span>|<span data-ttu-id="d83f5-303">valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-303">value</span></span>|
|<span data-ttu-id="d83f5-304">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-304">**Data type**</span></span>|<span data-ttu-id="d83f5-305">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-305">String</span></span>|
|<span data-ttu-id="d83f5-306">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-306">**Possible values**</span></span>|<span data-ttu-id="d83f5-307">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-307">audit (default)</span></span> <p> <span data-ttu-id="d83f5-308">block</span><span class="sxs-lookup"><span data-stu-id="d83f5-308">block</span></span> <p> <span data-ttu-id="d83f5-309">off</span><span class="sxs-lookup"><span data-stu-id="d83f5-309">off</span></span>|
|

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="d83f5-310">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="d83f5-310">Threat type settings merge policy</span></span>

<span data-ttu-id="d83f5-311">Especifica a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="d83f5-311">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="d83f5-312">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="d83f5-312">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="d83f5-313">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="d83f5-313">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

<br>

****

|<span data-ttu-id="d83f5-314">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-314">Description</span></span>|<span data-ttu-id="d83f5-315">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-315">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-316">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-316">**Key**</span></span>|<span data-ttu-id="d83f5-317">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="d83f5-317">threatTypeSettingsMergePolicy</span></span>|
|<span data-ttu-id="d83f5-318">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-318">**Data type**</span></span>|<span data-ttu-id="d83f5-319">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-319">String</span></span>|
|<span data-ttu-id="d83f5-320">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-320">**Possible values**</span></span>|<span data-ttu-id="d83f5-321">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-321">merge (default)</span></span> <p> <span data-ttu-id="d83f5-322">admin_only</span><span class="sxs-lookup"><span data-stu-id="d83f5-322">admin_only</span></span>|
|<span data-ttu-id="d83f5-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-323">**Comments**</span></span>|<span data-ttu-id="d83f5-324">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-324">Available in Defender for Endpoint version 100.83.73 or higher.</span></span>|
|

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="d83f5-325">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="d83f5-325">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="d83f5-326">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d83f5-326">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="d83f5-327">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="d83f5-327">Old scan results are removed from the history.</span></span> <span data-ttu-id="d83f5-328">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="d83f5-328">Old quarantined files that are also removed from the disk.</span></span>

<br>

****

|<span data-ttu-id="d83f5-329">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-329">Description</span></span>|<span data-ttu-id="d83f5-330">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-330">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-331">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-331">**Key**</span></span>|<span data-ttu-id="d83f5-332">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="d83f5-332">scanResultsRetentionDays</span></span>|
|<span data-ttu-id="d83f5-333">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-333">**Data type**</span></span>|<span data-ttu-id="d83f5-334">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-334">String</span></span>|
|<span data-ttu-id="d83f5-335">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-335">**Possible values**</span></span>|<span data-ttu-id="d83f5-336">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="d83f5-336">90 (default).</span></span> <span data-ttu-id="d83f5-337">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="d83f5-337">Allowed values are from 1 day to 180 days.</span></span>|
|<span data-ttu-id="d83f5-338">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-338">**Comments**</span></span>|<span data-ttu-id="d83f5-339">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-339">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="d83f5-340">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="d83f5-340">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="d83f5-341">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="d83f5-341">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="d83f5-342">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="d83f5-342">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

<br>

****

|<span data-ttu-id="d83f5-343">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-343">Description</span></span>|<span data-ttu-id="d83f5-344">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-344">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-345">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-345">**Key**</span></span>|<span data-ttu-id="d83f5-346">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="d83f5-346">scanHistoryMaximumItems</span></span>|
|<span data-ttu-id="d83f5-347">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-347">**Data type**</span></span>|<span data-ttu-id="d83f5-348">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-348">String</span></span>|
|<span data-ttu-id="d83f5-349">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-349">**Possible values**</span></span>|<span data-ttu-id="d83f5-350">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="d83f5-350">10000 (default).</span></span> <span data-ttu-id="d83f5-351">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="d83f5-351">Allowed values are from 5000 items to 15000 items.</span></span>|
|<span data-ttu-id="d83f5-352">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-352">**Comments**</span></span>|<span data-ttu-id="d83f5-353">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d83f5-353">Available in Defender for Endpoint version 101.04.76 or higher.</span></span>|
|

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="d83f5-354">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="d83f5-354">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="d83f5-355">A *entrada do cloudService* no perfil de configuração é usada para configurar o recurso de proteção orientada por nuvem do produto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-355">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

<br>

****

|<span data-ttu-id="d83f5-356">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-356">Description</span></span>|<span data-ttu-id="d83f5-357">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-357">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-358">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-358">**Key**</span></span>|<span data-ttu-id="d83f5-359">cloudService</span><span class="sxs-lookup"><span data-stu-id="d83f5-359">cloudService</span></span>|
|<span data-ttu-id="d83f5-360">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-360">**Data type**</span></span>|<span data-ttu-id="d83f5-361">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="d83f5-361">Dictionary (nested preference)</span></span>|
|<span data-ttu-id="d83f5-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="d83f5-362">**Comments**</span></span>|<span data-ttu-id="d83f5-363">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="d83f5-363">See the following sections for a description of the dictionary contents.</span></span>|
|

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="d83f5-364">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="d83f5-364">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="d83f5-365">Determina se a proteção entregue na nuvem está habilitada no dispositivo ou não.</span><span class="sxs-lookup"><span data-stu-id="d83f5-365">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="d83f5-366">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="d83f5-366">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

<br>

****

|<span data-ttu-id="d83f5-367">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-367">Description</span></span>|<span data-ttu-id="d83f5-368">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-368">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-369">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-369">**Key**</span></span>|<span data-ttu-id="d83f5-370">habilitadas</span><span class="sxs-lookup"><span data-stu-id="d83f5-370">enabled</span></span>|
|<span data-ttu-id="d83f5-371">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-371">**Data type**</span></span>|<span data-ttu-id="d83f5-372">Booliano</span><span class="sxs-lookup"><span data-stu-id="d83f5-372">Boolean</span></span>|
|<span data-ttu-id="d83f5-373">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-373">**Possible values**</span></span>|<span data-ttu-id="d83f5-374">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-374">true (default)</span></span> <p> <span data-ttu-id="d83f5-375">falso</span><span class="sxs-lookup"><span data-stu-id="d83f5-375">false</span></span>|
|

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="d83f5-376">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d83f5-376">Diagnostic collection level</span></span>

<span data-ttu-id="d83f5-377">Os dados de diagnóstico são usados para manter o Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-377">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="d83f5-378">Essa configuração determina o nível de diagnóstico enviado pelo produto para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d83f5-378">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="d83f5-379">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-379">Description</span></span>|<span data-ttu-id="d83f5-380">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-380">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-381">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-381">**Key**</span></span>|<span data-ttu-id="d83f5-382">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="d83f5-382">diagnosticLevel</span></span>|
|<span data-ttu-id="d83f5-383">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-383">**Data type**</span></span>|<span data-ttu-id="d83f5-384">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-384">String</span></span>|
|<span data-ttu-id="d83f5-385">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-385">**Possible values**</span></span>|<span data-ttu-id="d83f5-386">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-386">optional (default)</span></span> <p> <span data-ttu-id="d83f5-387">obrigatório</span><span class="sxs-lookup"><span data-stu-id="d83f5-387">required</span></span>|
|

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="d83f5-388">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="d83f5-388">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="d83f5-389">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d83f5-389">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="d83f5-390">Há três níveis para controlar o envio de exemplo:</span><span class="sxs-lookup"><span data-stu-id="d83f5-390">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="d83f5-391">**Nenhum**: nenhum exemplo suspeito é enviado à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d83f5-391">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="d83f5-392">**Cofre**: somente amostras suspeitas que não contenham informações de identificação pessoal (PII) são enviadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d83f5-392">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="d83f5-393">Esse é o valor padrão para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="d83f5-393">This is the default value for this setting.</span></span>
- <span data-ttu-id="d83f5-394">**All**: todos os exemplos suspeitos são enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d83f5-394">**All**: all suspicious samples are submitted to Microsoft.</span></span>

<br>

****

|<span data-ttu-id="d83f5-395">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-395">Description</span></span>|<span data-ttu-id="d83f5-396">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-396">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-397">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-397">**Key**</span></span>|<span data-ttu-id="d83f5-398">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="d83f5-398">automaticSampleSubmissionConsent</span></span>|
|<span data-ttu-id="d83f5-399">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-399">**Data type**</span></span>|<span data-ttu-id="d83f5-400">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d83f5-400">String</span></span>|
|<span data-ttu-id="d83f5-401">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-401">**Possible values**</span></span>|<span data-ttu-id="d83f5-402">nenhuma</span><span class="sxs-lookup"><span data-stu-id="d83f5-402">none</span></span> <p> <span data-ttu-id="d83f5-403">safe (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-403">safe (default)</span></span> <p> <span data-ttu-id="d83f5-404">all</span><span class="sxs-lookup"><span data-stu-id="d83f5-404">all</span></span>|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="d83f5-405">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="d83f5-405">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="d83f5-406">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="d83f5-406">Determines whether security intelligence updates are installed automatically:</span></span>

<br>

****

|<span data-ttu-id="d83f5-407">Descrição</span><span class="sxs-lookup"><span data-stu-id="d83f5-407">Description</span></span>|<span data-ttu-id="d83f5-408">Valor</span><span class="sxs-lookup"><span data-stu-id="d83f5-408">Value</span></span>|
|---|---|
|<span data-ttu-id="d83f5-409">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="d83f5-409">**Key**</span></span>|<span data-ttu-id="d83f5-410">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="d83f5-410">automaticDefinitionUpdateEnabled</span></span>|
|<span data-ttu-id="d83f5-411">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d83f5-411">**Data type**</span></span>|<span data-ttu-id="d83f5-412">Booliano</span><span class="sxs-lookup"><span data-stu-id="d83f5-412">Boolean</span></span>|
|<span data-ttu-id="d83f5-413">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="d83f5-413">**Possible values**</span></span>|<span data-ttu-id="d83f5-414">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="d83f5-414">true (default)</span></span> <p> <span data-ttu-id="d83f5-415">falso</span><span class="sxs-lookup"><span data-stu-id="d83f5-415">false</span></span>|
|

## <a name="recommended-configuration-profile"></a><span data-ttu-id="d83f5-416">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="d83f5-416">Recommended configuration profile</span></span>

<span data-ttu-id="d83f5-417">Para começar, recomendamos que o perfil de configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="d83f5-417">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="d83f5-418">O seguinte perfil de configuração será:</span><span class="sxs-lookup"><span data-stu-id="d83f5-418">The following configuration profile will:</span></span>

- <span data-ttu-id="d83f5-419">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="d83f5-419">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="d83f5-420">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="d83f5-420">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="d83f5-421">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="d83f5-421">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="d83f5-422">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para os logs do produto</span><span class="sxs-lookup"><span data-stu-id="d83f5-422">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="d83f5-423">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="d83f5-423">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="d83f5-424">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="d83f5-424">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="d83f5-425">Habilitar o envio automático de exemplo no `safe` nível</span><span class="sxs-lookup"><span data-stu-id="d83f5-425">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="d83f5-426">Perfil de exemplo</span><span class="sxs-lookup"><span data-stu-id="d83f5-426">Sample profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="d83f5-427">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="d83f5-427">Full configuration profile example</span></span>

<span data-ttu-id="d83f5-428">O perfil de configuração a seguir contém entradas para todas as configurações descritas neste documento e pode ser usado para cenários mais avançados em que você deseja mais controle sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="d83f5-428">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="d83f5-429">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="d83f5-429">Full profile</span></span>

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="d83f5-430">Validação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="d83f5-430">Configuration profile validation</span></span>

<span data-ttu-id="d83f5-431">O perfil de configuração deve ser um arquivo JSON formatado válido.</span><span class="sxs-lookup"><span data-stu-id="d83f5-431">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="d83f5-432">Há várias ferramentas que podem ser usadas para verificar isso.</span><span class="sxs-lookup"><span data-stu-id="d83f5-432">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="d83f5-433">Por exemplo, se você `python` tiver instalado em seu dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d83f5-433">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="d83f5-434">Se o JSON for bem formado, o comando acima o retornará ao Terminal e retornará um código de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="d83f5-434">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="d83f5-435">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="d83f5-435">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="d83f5-436">Verificar se o arquivo mdatp_managed.json está funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="d83f5-436">Verifying that the mdatp_managed.json file is working as expected</span></span>

<span data-ttu-id="d83f5-437">Para verificar se o /etc/opt/microsoft/mdatp/managed/mdatp_managed.json está funcionando corretamente, você deve ver "[gerenciado]" ao lado dessas configurações:</span><span class="sxs-lookup"><span data-stu-id="d83f5-437">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>

- <span data-ttu-id="d83f5-438">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="d83f5-438">cloud_enabled</span></span>
- <span data-ttu-id="d83f5-439">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="d83f5-439">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="d83f5-440">passive_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="d83f5-440">passive_mode_enabled</span></span>
- <span data-ttu-id="d83f5-441">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="d83f5-441">real_time_protection_enabled</span></span>
- <span data-ttu-id="d83f5-442">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="d83f5-442">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="d83f5-443">Para que mdatp_managed.jsa ação entre em vigor, nenhuma reinicialização do wdavdaemon é necessária.</span><span class="sxs-lookup"><span data-stu-id="d83f5-443">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="d83f5-444">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="d83f5-444">Configuration profile deployment</span></span>

<span data-ttu-id="d83f5-445">Depois de construir o perfil de configuração para sua empresa, você poderá implantá-lo por meio da ferramenta de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="d83f5-445">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="d83f5-446">O Defender para Ponto de Extremidade no Linux lê a configuração gerenciada do *arquivo /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="d83f5-446">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
