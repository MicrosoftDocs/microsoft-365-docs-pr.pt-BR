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
ms.openlocfilehash: 29505a6e975fdfa2283efe3391c615e40e678164
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346373"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c4285-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="c4285-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c4285-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c4285-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4285-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c4285-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4285-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4285-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c4285-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c4285-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c4285-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c4285-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="c4285-110">Este tópico contém instruções sobre como definir preferências para o Defender para o Ponto de Extremidade no Linux em ambientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="c4285-110">This topic contains instructions for how to set preferences for Defender for Endpoint on Linux in enterprise environments.</span></span> <span data-ttu-id="c4285-111">Se você estiver interessado em configurar o produto em um dispositivo da linha de comando, consulte [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="c4285-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="c4285-112">Em ambientes corporativos, o Defender for Endpoint no Linux pode ser gerenciado por meio de um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="c4285-112">In enterprise environments, Defender for Endpoint on Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="c4285-113">Esse perfil é implantado a partir da ferramenta de gerenciamento de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="c4285-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="c4285-114">As preferências gerenciadas pela empresa têm precedência sobre as definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4285-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="c4285-115">Em outras palavras, os usuários em sua empresa não são capazes de alterar as preferências definidas por meio desse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="c4285-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="c4285-116">Este artigo descreve a estrutura desse perfil (incluindo um perfil recomendado que você pode usar para começar) e instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="c4285-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="c4285-117">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="c4285-117">Configuration profile structure</span></span>

<span data-ttu-id="c4285-118">O perfil de configuração é um arquivo .json que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="c4285-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="c4285-119">Os valores podem ser simples, como um valor numérico ou complexo, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="c4285-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="c4285-120">Normalmente, você usaria uma ferramenta de gerenciamento de configuração para pressionar um arquivo com o nome ```mdatp_managed.json``` no local ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="c4285-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="c4285-121">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do produto, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="c4285-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="c4285-122">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="c4285-122">Antivirus engine preferences</span></span>

<span data-ttu-id="c4285-123">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do produto.</span><span class="sxs-lookup"><span data-stu-id="c4285-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-124">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-124">**Key**</span></span> | <span data-ttu-id="c4285-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="c4285-125">antivirusEngine</span></span> |
| <span data-ttu-id="c4285-126">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-126">**Data type**</span></span> | <span data-ttu-id="c4285-127">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="c4285-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c4285-128">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-128">**Comments**</span></span> | <span data-ttu-id="c4285-129">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="c4285-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="c4285-130">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="c4285-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="c4285-131">Determina se a proteção em tempo real (arquivos de verificação conforme eles são acessados) está habilitada ou não.</span><span class="sxs-lookup"><span data-stu-id="c4285-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-132">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-132">**Key**</span></span> | <span data-ttu-id="c4285-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="c4285-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="c4285-134">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-134">**Data type**</span></span> | <span data-ttu-id="c4285-135">Booliano</span><span class="sxs-lookup"><span data-stu-id="c4285-135">Boolean</span></span> |
| <span data-ttu-id="c4285-136">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-136">**Possible values**</span></span> | <span data-ttu-id="c4285-137">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-137">true (default)</span></span> <br/> <span data-ttu-id="c4285-138">falso</span><span class="sxs-lookup"><span data-stu-id="c4285-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="c4285-139">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="c4285-139">Enable / disable passive mode</span></span>

<span data-ttu-id="c4285-140">Determina se o mecanismo antivírus é executado no modo passivo ou não.</span><span class="sxs-lookup"><span data-stu-id="c4285-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="c4285-141">No modo passivo:</span><span class="sxs-lookup"><span data-stu-id="c4285-141">In passive mode:</span></span>
- <span data-ttu-id="c4285-142">A proteção em tempo real está desligada.</span><span class="sxs-lookup"><span data-stu-id="c4285-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="c4285-143">A verificação sob demanda está 100% 100%.</span><span class="sxs-lookup"><span data-stu-id="c4285-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="c4285-144">A correção automática de ameaças está desligada.</span><span class="sxs-lookup"><span data-stu-id="c4285-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="c4285-145">As atualizações de inteligência de segurança estão ativas.</span><span class="sxs-lookup"><span data-stu-id="c4285-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="c4285-146">O ícone do menu Status está oculto.</span><span class="sxs-lookup"><span data-stu-id="c4285-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-147">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-147">**Key**</span></span> | <span data-ttu-id="c4285-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="c4285-148">passiveMode</span></span> |
| <span data-ttu-id="c4285-149">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-149">**Data type**</span></span> | <span data-ttu-id="c4285-150">Booliano</span><span class="sxs-lookup"><span data-stu-id="c4285-150">Boolean</span></span> |
| <span data-ttu-id="c4285-151">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-151">**Possible values**</span></span> | <span data-ttu-id="c4285-152">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-152">false (default)</span></span> <br/> <span data-ttu-id="c4285-153">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="c4285-153">true</span></span> |
| <span data-ttu-id="c4285-154">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-154">**Comments**</span></span> | <span data-ttu-id="c4285-155">Disponível no Defender para Ponto de Extremidade versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="c4285-156">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="c4285-156">Exclusion merge policy</span></span>

<span data-ttu-id="c4285-157">Especifica a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="c4285-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="c4285-158">Pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c4285-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="c4285-159">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="c4285-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-160">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-160">**Key**</span></span> | <span data-ttu-id="c4285-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c4285-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="c4285-162">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-162">**Data type**</span></span> | <span data-ttu-id="c4285-163">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-163">String</span></span> |
| <span data-ttu-id="c4285-164">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-164">**Possible values**</span></span> | <span data-ttu-id="c4285-165">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-165">merge (default)</span></span> <br/> <span data-ttu-id="c4285-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="c4285-166">admin_only</span></span> |
| <span data-ttu-id="c4285-167">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-167">**Comments**</span></span> | <span data-ttu-id="c4285-168">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="c4285-169">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="c4285-169">Scan exclusions</span></span>

<span data-ttu-id="c4285-170">Entidades que foram excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="c4285-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="c4285-171">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4285-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="c4285-172">(As exclusões são especificadas como uma matriz de itens, o administrador pode especificar quantos elementos for necessário, em qualquer ordem.)</span><span class="sxs-lookup"><span data-stu-id="c4285-172">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-173">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-173">**Key**</span></span> | <span data-ttu-id="c4285-174">exclusões</span><span class="sxs-lookup"><span data-stu-id="c4285-174">exclusions</span></span> |
| <span data-ttu-id="c4285-175">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-175">**Data type**</span></span> | <span data-ttu-id="c4285-176">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="c4285-176">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c4285-177">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-177">**Comments**</span></span> | <span data-ttu-id="c4285-178">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="c4285-178">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c4285-179">**Tipo de exclusão**</span><span class="sxs-lookup"><span data-stu-id="c4285-179">**Type of exclusion**</span></span>

<span data-ttu-id="c4285-180">Especifica o tipo de conteúdo excluído da verificação.</span><span class="sxs-lookup"><span data-stu-id="c4285-180">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-181">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-181">**Key**</span></span> | <span data-ttu-id="c4285-182">$type</span><span class="sxs-lookup"><span data-stu-id="c4285-182">$type</span></span> |
| <span data-ttu-id="c4285-183">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-183">**Data type**</span></span> | <span data-ttu-id="c4285-184">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-184">String</span></span> |
| <span data-ttu-id="c4285-185">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-185">**Possible values**</span></span> | <span data-ttu-id="c4285-186">excludedPath</span><span class="sxs-lookup"><span data-stu-id="c4285-186">excludedPath</span></span> <br/> <span data-ttu-id="c4285-187">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="c4285-187">excludedFileExtension</span></span> <br/> <span data-ttu-id="c4285-188">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="c4285-188">excludedFileName</span></span> |
|||

<span data-ttu-id="c4285-189">**Caminho para conteúdo excluído**</span><span class="sxs-lookup"><span data-stu-id="c4285-189">**Path to excluded content**</span></span>

<span data-ttu-id="c4285-190">Usado para excluir conteúdo da verificação por caminho de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="c4285-190">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-191">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-191">**Key**</span></span> | <span data-ttu-id="c4285-192">caminho</span><span class="sxs-lookup"><span data-stu-id="c4285-192">path</span></span> |
| <span data-ttu-id="c4285-193">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-193">**Data type**</span></span> | <span data-ttu-id="c4285-194">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-194">String</span></span> |
| <span data-ttu-id="c4285-195">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-195">**Possible values**</span></span> | <span data-ttu-id="c4285-196">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="c4285-196">valid paths</span></span> |
| <span data-ttu-id="c4285-197">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-197">**Comments**</span></span> | <span data-ttu-id="c4285-198">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="c4285-198">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c4285-199">**Tipo de caminho (arquivo/diretório)**</span><span class="sxs-lookup"><span data-stu-id="c4285-199">**Path type (file / directory)**</span></span>

<span data-ttu-id="c4285-200">Indica se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="c4285-200">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="c4285-201">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-201">**Key**</span></span> | <span data-ttu-id="c4285-202">isDirectory</span><span class="sxs-lookup"><span data-stu-id="c4285-202">isDirectory</span></span> |
| <span data-ttu-id="c4285-203">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-203">**Data type**</span></span> | <span data-ttu-id="c4285-204">Booliano</span><span class="sxs-lookup"><span data-stu-id="c4285-204">Boolean</span></span> |
| <span data-ttu-id="c4285-205">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-205">**Possible values**</span></span> | <span data-ttu-id="c4285-206">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-206">false (default)</span></span> <br/> <span data-ttu-id="c4285-207">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="c4285-207">true</span></span> |
| <span data-ttu-id="c4285-208">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-208">**Comments**</span></span> | <span data-ttu-id="c4285-209">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="c4285-209">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="c4285-210">**Extensão de arquivo excluída da verificação**</span><span class="sxs-lookup"><span data-stu-id="c4285-210">**File extension excluded from the scan**</span></span>

<span data-ttu-id="c4285-211">Usado para excluir conteúdo da verificação por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c4285-211">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-212">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-212">**Key**</span></span> | <span data-ttu-id="c4285-213">extension</span><span class="sxs-lookup"><span data-stu-id="c4285-213">extension</span></span> |
| <span data-ttu-id="c4285-214">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-214">**Data type**</span></span> | <span data-ttu-id="c4285-215">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-215">String</span></span> |
| <span data-ttu-id="c4285-216">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-216">**Possible values**</span></span> | <span data-ttu-id="c4285-217">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="c4285-217">valid file extensions</span></span> |
| <span data-ttu-id="c4285-218">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-218">**Comments**</span></span> | <span data-ttu-id="c4285-219">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="c4285-219">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="c4285-220">**Processo excluído da verificação**</span><span class="sxs-lookup"><span data-stu-id="c4285-220">**Process excluded from the scan**</span></span>

<span data-ttu-id="c4285-221">Especifica um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="c4285-221">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="c4285-222">O processo pode ser especificado pelo nome (por exemplo) `cat` ou caminho completo (por exemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="c4285-222">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-223">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-223">**Key**</span></span> | <span data-ttu-id="c4285-224">nome</span><span class="sxs-lookup"><span data-stu-id="c4285-224">name</span></span> |
| <span data-ttu-id="c4285-225">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-225">**Data type**</span></span> | <span data-ttu-id="c4285-226">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-226">String</span></span> |
| <span data-ttu-id="c4285-227">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-227">**Possible values**</span></span> | <span data-ttu-id="c4285-228">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-228">any string</span></span> |
| <span data-ttu-id="c4285-229">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-229">**Comments**</span></span> | <span data-ttu-id="c4285-230">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="c4285-230">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="c4285-231">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="c4285-231">Allowed threats</span></span>

<span data-ttu-id="c4285-232">Lista de ameaças (identificadas pelo nome) que não são bloqueadas pelo produto e têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="c4285-232">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-233">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-233">**Key**</span></span> | <span data-ttu-id="c4285-234">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="c4285-234">allowedThreats</span></span> |
| <span data-ttu-id="c4285-235">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-235">**Data type**</span></span> | <span data-ttu-id="c4285-236">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-236">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="c4285-237">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="c4285-237">Disallowed threat actions</span></span>

<span data-ttu-id="c4285-238">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="c4285-238">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="c4285-239">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="c4285-239">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-240">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-240">**Key**</span></span> | <span data-ttu-id="c4285-241">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="c4285-241">disallowedThreatActions</span></span> |
| <span data-ttu-id="c4285-242">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-242">**Data type**</span></span> | <span data-ttu-id="c4285-243">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-243">Array of strings</span></span> |
| <span data-ttu-id="c4285-244">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-244">**Possible values**</span></span> | <span data-ttu-id="c4285-245">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="c4285-245">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="c4285-246">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="c4285-246">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="c4285-247">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-247">**Comments**</span></span> | <span data-ttu-id="c4285-248">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-248">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="c4285-249">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="c4285-249">Threat type settings</span></span>

<span data-ttu-id="c4285-250">A *preferência threatTypeSettings* no mecanismo antivírus é usada para controlar como determinados tipos de ameaça são manipulados pelo produto.</span><span class="sxs-lookup"><span data-stu-id="c4285-250">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-251">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-251">**Key**</span></span> | <span data-ttu-id="c4285-252">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="c4285-252">threatTypeSettings</span></span> |
| <span data-ttu-id="c4285-253">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-253">**Data type**</span></span> | <span data-ttu-id="c4285-254">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="c4285-254">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c4285-255">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-255">**Comments**</span></span> | <span data-ttu-id="c4285-256">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="c4285-256">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="c4285-257">**Tipo de ameaça**</span><span class="sxs-lookup"><span data-stu-id="c4285-257">**Threat type**</span></span>

<span data-ttu-id="c4285-258">Tipo de ameaça para a qual o comportamento está configurado.</span><span class="sxs-lookup"><span data-stu-id="c4285-258">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-259">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-259">**Key**</span></span> | <span data-ttu-id="c4285-260">chave</span><span class="sxs-lookup"><span data-stu-id="c4285-260">key</span></span> |
| <span data-ttu-id="c4285-261">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-261">**Data type**</span></span> | <span data-ttu-id="c4285-262">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-262">String</span></span> |
| <span data-ttu-id="c4285-263">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-263">**Possible values**</span></span> | <span data-ttu-id="c4285-264">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="c4285-264">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="c4285-265">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="c4285-265">archive_bomb</span></span> |
|||

<span data-ttu-id="c4285-266">**O que fazer**</span><span class="sxs-lookup"><span data-stu-id="c4285-266">**Action to take**</span></span>

<span data-ttu-id="c4285-267">Ação a ser tomada ao se deparar com uma ameaça do tipo especificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="c4285-267">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="c4285-268">Pode ser:</span><span class="sxs-lookup"><span data-stu-id="c4285-268">Can be:</span></span>

- <span data-ttu-id="c4285-269">**Auditoria**: o dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="c4285-269">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="c4285-270">**Bloquear**: o dispositivo é protegido contra esse tipo de ameaça e você é notificado no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="c4285-270">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="c4285-271">**Off**: O dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="c4285-271">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-272">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-272">**Key**</span></span> | <span data-ttu-id="c4285-273">valor</span><span class="sxs-lookup"><span data-stu-id="c4285-273">value</span></span> |
| <span data-ttu-id="c4285-274">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-274">**Data type**</span></span> | <span data-ttu-id="c4285-275">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-275">String</span></span> |
| <span data-ttu-id="c4285-276">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-276">**Possible values**</span></span> | <span data-ttu-id="c4285-277">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-277">audit (default)</span></span> <br/> <span data-ttu-id="c4285-278">block</span><span class="sxs-lookup"><span data-stu-id="c4285-278">block</span></span> <br/> <span data-ttu-id="c4285-279">off</span><span class="sxs-lookup"><span data-stu-id="c4285-279">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="c4285-280">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="c4285-280">Threat type settings merge policy</span></span>

<span data-ttu-id="c4285-281">Especifica a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c4285-281">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="c4285-282">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="c4285-282">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="c4285-283">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="c4285-283">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-284">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-284">**Key**</span></span> | <span data-ttu-id="c4285-285">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="c4285-285">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="c4285-286">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-286">**Data type**</span></span> | <span data-ttu-id="c4285-287">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-287">String</span></span> |
| <span data-ttu-id="c4285-288">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-288">**Possible values**</span></span> | <span data-ttu-id="c4285-289">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-289">merge (default)</span></span> <br/> <span data-ttu-id="c4285-290">admin_only</span><span class="sxs-lookup"><span data-stu-id="c4285-290">admin_only</span></span> |
| <span data-ttu-id="c4285-291">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-291">**Comments**</span></span> | <span data-ttu-id="c4285-292">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-292">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="c4285-293">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="c4285-293">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="c4285-294">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c4285-294">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="c4285-295">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="c4285-295">Old scan results are removed from the history.</span></span> <span data-ttu-id="c4285-296">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="c4285-296">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-297">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-297">**Key**</span></span> | <span data-ttu-id="c4285-298">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="c4285-298">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="c4285-299">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-299">**Data type**</span></span> | <span data-ttu-id="c4285-300">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-300">String</span></span> |
| <span data-ttu-id="c4285-301">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-301">**Possible values**</span></span> | <span data-ttu-id="c4285-302">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="c4285-302">90 (default).</span></span> <span data-ttu-id="c4285-303">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="c4285-303">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="c4285-304">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-304">**Comments**</span></span> | <span data-ttu-id="c4285-305">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-305">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="c4285-306">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="c4285-306">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="c4285-307">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="c4285-307">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="c4285-308">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="c4285-308">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-309">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-309">**Key**</span></span> | <span data-ttu-id="c4285-310">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="c4285-310">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="c4285-311">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-311">**Data type**</span></span> | <span data-ttu-id="c4285-312">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-312">String</span></span> |
| <span data-ttu-id="c4285-313">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-313">**Possible values**</span></span> | <span data-ttu-id="c4285-314">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="c4285-314">10000 (default).</span></span> <span data-ttu-id="c4285-315">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="c4285-315">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="c4285-316">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-316">**Comments**</span></span> | <span data-ttu-id="c4285-317">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="c4285-317">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="c4285-318">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="c4285-318">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="c4285-319">A *entrada do cloudService* no perfil de configuração é usada para configurar o recurso de proteção orientada por nuvem do produto.</span><span class="sxs-lookup"><span data-stu-id="c4285-319">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-320">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-320">**Key**</span></span> | <span data-ttu-id="c4285-321">cloudService</span><span class="sxs-lookup"><span data-stu-id="c4285-321">cloudService</span></span> |
| <span data-ttu-id="c4285-322">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-322">**Data type**</span></span> | <span data-ttu-id="c4285-323">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="c4285-323">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="c4285-324">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="c4285-324">**Comments**</span></span> | <span data-ttu-id="c4285-325">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="c4285-325">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="c4285-326">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="c4285-326">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="c4285-327">Determina se a proteção entregue na nuvem está habilitada no dispositivo ou não.</span><span class="sxs-lookup"><span data-stu-id="c4285-327">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="c4285-328">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="c4285-328">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-329">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-329">**Key**</span></span> | <span data-ttu-id="c4285-330">habilitadas</span><span class="sxs-lookup"><span data-stu-id="c4285-330">enabled</span></span> |
| <span data-ttu-id="c4285-331">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-331">**Data type**</span></span> | <span data-ttu-id="c4285-332">Booliano</span><span class="sxs-lookup"><span data-stu-id="c4285-332">Boolean</span></span> |
| <span data-ttu-id="c4285-333">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-333">**Possible values**</span></span> | <span data-ttu-id="c4285-334">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-334">true (default)</span></span> <br/> <span data-ttu-id="c4285-335">falso</span><span class="sxs-lookup"><span data-stu-id="c4285-335">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="c4285-336">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c4285-336">Diagnostic collection level</span></span>

<span data-ttu-id="c4285-337">Os dados de diagnóstico são usados para manter o Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="c4285-337">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="c4285-338">Essa configuração determina o nível de diagnóstico enviado pelo produto para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4285-338">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-339">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-339">**Key**</span></span> | <span data-ttu-id="c4285-340">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="c4285-340">diagnosticLevel</span></span> |
| <span data-ttu-id="c4285-341">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-341">**Data type**</span></span> | <span data-ttu-id="c4285-342">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-342">String</span></span> |
| <span data-ttu-id="c4285-343">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-343">**Possible values**</span></span> | <span data-ttu-id="c4285-344">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-344">optional (default)</span></span> <br/> <span data-ttu-id="c4285-345">obrigatório</span><span class="sxs-lookup"><span data-stu-id="c4285-345">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="c4285-346">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="c4285-346">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="c4285-347">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4285-347">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="c4285-348">Há três níveis para controlar o envio de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4285-348">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="c4285-349">**Nenhum**: nenhum exemplo suspeito é enviado à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4285-349">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="c4285-350">**Cofre**: somente amostras suspeitas que não contenham informações de identificação pessoal (PII) são enviadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c4285-350">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="c4285-351">Esse é o valor padrão para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="c4285-351">This is the default value for this setting.</span></span>
- <span data-ttu-id="c4285-352">**All**: todos os exemplos suspeitos são enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4285-352">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-353">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-353">**Key**</span></span> | <span data-ttu-id="c4285-354">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="c4285-354">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="c4285-355">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-355">**Data type**</span></span> | <span data-ttu-id="c4285-356">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c4285-356">String</span></span> |
| <span data-ttu-id="c4285-357">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-357">**Possible values**</span></span> | <span data-ttu-id="c4285-358">nenhuma</span><span class="sxs-lookup"><span data-stu-id="c4285-358">none</span></span> <br/> <span data-ttu-id="c4285-359">safe (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-359">safe (default)</span></span> <br/> <span data-ttu-id="c4285-360">all</span><span class="sxs-lookup"><span data-stu-id="c4285-360">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="c4285-361">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="c4285-361">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="c4285-362">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c4285-362">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="c4285-363">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c4285-363">**Key**</span></span> | <span data-ttu-id="c4285-364">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="c4285-364">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="c4285-365">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c4285-365">**Data type**</span></span> | <span data-ttu-id="c4285-366">Booliano</span><span class="sxs-lookup"><span data-stu-id="c4285-366">Boolean</span></span> |
| <span data-ttu-id="c4285-367">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c4285-367">**Possible values**</span></span> | <span data-ttu-id="c4285-368">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="c4285-368">true (default)</span></span> <br/> <span data-ttu-id="c4285-369">falso</span><span class="sxs-lookup"><span data-stu-id="c4285-369">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="c4285-370">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="c4285-370">Recommended configuration profile</span></span>

<span data-ttu-id="c4285-371">Para começar, recomendamos que o perfil de configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="c4285-371">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="c4285-372">O seguinte perfil de configuração será:</span><span class="sxs-lookup"><span data-stu-id="c4285-372">The following configuration profile will:</span></span>

- <span data-ttu-id="c4285-373">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="c4285-373">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="c4285-374">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="c4285-374">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="c4285-375">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="c4285-375">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="c4285-376">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para os logs do produto</span><span class="sxs-lookup"><span data-stu-id="c4285-376">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="c4285-377">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="c4285-377">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="c4285-378">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="c4285-378">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="c4285-379">Habilitar o envio automático de exemplo no `safe` nível</span><span class="sxs-lookup"><span data-stu-id="c4285-379">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="c4285-380">Perfil de exemplo</span><span class="sxs-lookup"><span data-stu-id="c4285-380">Sample profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="c4285-381">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="c4285-381">Full configuration profile example</span></span>

<span data-ttu-id="c4285-382">O perfil de configuração a seguir contém entradas para todas as configurações descritas neste documento e pode ser usado para cenários mais avançados em que você deseja mais controle sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="c4285-382">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="c4285-383">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="c4285-383">Full profile</span></span>

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
            "extension":"pdf"
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

## <a name="configuration-profile-validation"></a><span data-ttu-id="c4285-384">Validação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="c4285-384">Configuration profile validation</span></span>

<span data-ttu-id="c4285-385">O perfil de configuração deve ser um arquivo JSON formatado válido.</span><span class="sxs-lookup"><span data-stu-id="c4285-385">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="c4285-386">Há várias ferramentas que podem ser usadas para verificar isso.</span><span class="sxs-lookup"><span data-stu-id="c4285-386">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="c4285-387">Por exemplo, se você `python` tiver instalado em seu dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c4285-387">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="c4285-388">Se o JSON for bem formado, o comando acima o retornará ao Terminal e retornará um código de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="c4285-388">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="c4285-389">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="c4285-389">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="c4285-390">Verificar se o arquivo mdatp_managed.json está funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="c4285-390">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="c4285-391">Para verificar se o /etc/opt/microsoft/mdatp/managed/mdatp_managed.json está funcionando corretamente, você deve ver "[gerenciado]" ao lado dessas configurações:</span><span class="sxs-lookup"><span data-stu-id="c4285-391">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="c4285-392">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="c4285-392">cloud_enabled</span></span>
- <span data-ttu-id="c4285-393">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="c4285-393">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="c4285-394">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="c4285-394">passice_mode_enabled</span></span>
- <span data-ttu-id="c4285-395">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="c4285-395">real_time_protection_enabled</span></span>
- <span data-ttu-id="c4285-396">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="c4285-396">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="c4285-397">Para que mdatp_managed.jsa ação entre em vigor, nenhuma reinicialização do wdavdaemon é necessária.</span><span class="sxs-lookup"><span data-stu-id="c4285-397">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="c4285-398">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="c4285-398">Configuration profile deployment</span></span>

<span data-ttu-id="c4285-399">Depois de construir o perfil de configuração para sua empresa, você poderá implantá-lo por meio da ferramenta de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="c4285-399">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="c4285-400">O Defender para Ponto de Extremidade no Linux lê a configuração gerenciada do *arquivo /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="c4285-400">Defender for Endpoint on Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
