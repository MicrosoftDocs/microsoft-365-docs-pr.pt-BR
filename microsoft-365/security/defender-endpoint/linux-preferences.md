---
title: Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Descreve como configurar o Microsoft Defender para Ponto de Extremidade no Linux em empresas.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 2c162d652656afb61f1d74bad9ec963825d25a14
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903865"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="e49b3-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="e49b3-104">Set preferences for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e49b3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e49b3-105">**Applies to:**</span></span>
- [<span data-ttu-id="e49b3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e49b3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e49b3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e49b3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e49b3-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e49b3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e49b3-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e49b3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="e49b3-110">Este tópico contém instruções sobre como definir preferências para o Defender for Endpoint para Linux em ambientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="e49b3-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="e49b3-111">Se você estiver interessado em configurar o produto em um dispositivo da linha de comando, consulte [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="e49b3-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="e49b3-112">Em ambientes corporativos, o Defender for Endpoint para Linux pode ser gerenciado por meio de um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="e49b3-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="e49b3-113">Esse perfil é implantado a partir da ferramenta de gerenciamento de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="e49b3-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="e49b3-114">As preferências gerenciadas pela empresa têm precedência sobre as definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e49b3-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="e49b3-115">Em outras palavras, os usuários em sua empresa não são capazes de alterar as preferências definidas por meio desse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="e49b3-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="e49b3-116">Este artigo descreve a estrutura desse perfil (incluindo um perfil recomendado que você pode usar para começar) e instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="e49b3-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="e49b3-117">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="e49b3-117">Configuration profile structure</span></span>

<span data-ttu-id="e49b3-118">O perfil de configuração é um arquivo .json que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="e49b3-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="e49b3-119">Os valores podem ser simples, como um valor numérico ou complexo, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="e49b3-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="e49b3-120">Normalmente, você usaria uma ferramenta de gerenciamento de configuração para pressionar um arquivo com o nome ```mdatp_managed.json``` no local ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="e49b3-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="e49b3-121">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do produto, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="e49b3-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="e49b3-122">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="e49b3-122">Antivirus engine preferences</span></span>

<span data-ttu-id="e49b3-123">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do produto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-124">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-124">**Key**</span></span> | <span data-ttu-id="e49b3-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="e49b3-125">antivirusEngine</span></span> |
| <span data-ttu-id="e49b3-126">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-126">**Data type**</span></span> | <span data-ttu-id="e49b3-127">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e49b3-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e49b3-128">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-128">**Comments**</span></span> | <span data-ttu-id="e49b3-129">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e49b3-129">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="e49b3-130">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="e49b3-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="e49b3-131">Determina se a proteção em tempo real (arquivos de verificação conforme eles são acessados) está habilitada ou não.</span><span class="sxs-lookup"><span data-stu-id="e49b3-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-132">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-132">**Key**</span></span> | <span data-ttu-id="e49b3-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="e49b3-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="e49b3-134">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-134">**Data type**</span></span> | <span data-ttu-id="e49b3-135">Booliano</span><span class="sxs-lookup"><span data-stu-id="e49b3-135">Boolean</span></span> |
| <span data-ttu-id="e49b3-136">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-136">**Possible values**</span></span> | <span data-ttu-id="e49b3-137">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-137">true (default)</span></span> <br/> <span data-ttu-id="e49b3-138">falso</span><span class="sxs-lookup"><span data-stu-id="e49b3-138">false</span></span> |
|||

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="e49b3-139">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="e49b3-139">Enable / disable passive mode</span></span>

<span data-ttu-id="e49b3-140">Determina se o mecanismo antivírus é executado no modo passivo ou não.</span><span class="sxs-lookup"><span data-stu-id="e49b3-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="e49b3-141">No modo passivo:</span><span class="sxs-lookup"><span data-stu-id="e49b3-141">In passive mode:</span></span>
- <span data-ttu-id="e49b3-142">A proteção em tempo real está desligada.</span><span class="sxs-lookup"><span data-stu-id="e49b3-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="e49b3-143">A verificação sob demanda está 100% 100%.</span><span class="sxs-lookup"><span data-stu-id="e49b3-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="e49b3-144">A correção automática de ameaças está desligada.</span><span class="sxs-lookup"><span data-stu-id="e49b3-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="e49b3-145">As atualizações de inteligência de segurança estão ativas.</span><span class="sxs-lookup"><span data-stu-id="e49b3-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="e49b3-146">O ícone do menu Status está oculto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-147">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-147">**Key**</span></span> | <span data-ttu-id="e49b3-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="e49b3-148">passiveMode</span></span> |
| <span data-ttu-id="e49b3-149">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-149">**Data type**</span></span> | <span data-ttu-id="e49b3-150">Booliano</span><span class="sxs-lookup"><span data-stu-id="e49b3-150">Boolean</span></span> |
| <span data-ttu-id="e49b3-151">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-151">**Possible values**</span></span> | <span data-ttu-id="e49b3-152">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-152">false (default)</span></span> <br/> <span data-ttu-id="e49b3-153">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="e49b3-153">true</span></span> |
| <span data-ttu-id="e49b3-154">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-154">**Comments**</span></span> | <span data-ttu-id="e49b3-155">Disponível no Defender para Ponto de Extremidade versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |
|||

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="e49b3-156">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="e49b3-156">Exclusion merge policy</span></span>

<span data-ttu-id="e49b3-157">Especifica a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="e49b3-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="e49b3-158">Pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="e49b3-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="e49b3-159">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="e49b3-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-160">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-160">**Key**</span></span> | <span data-ttu-id="e49b3-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="e49b3-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="e49b3-162">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-162">**Data type**</span></span> | <span data-ttu-id="e49b3-163">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-163">String</span></span> |
| <span data-ttu-id="e49b3-164">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-164">**Possible values**</span></span> | <span data-ttu-id="e49b3-165">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-165">merge (default)</span></span> <br/> <span data-ttu-id="e49b3-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="e49b3-166">admin_only</span></span> |
| <span data-ttu-id="e49b3-167">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-167">**Comments**</span></span> | <span data-ttu-id="e49b3-168">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="scan-exclusions"></a><span data-ttu-id="e49b3-169">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="e49b3-169">Scan exclusions</span></span>

<span data-ttu-id="e49b3-170">Entidades que foram excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="e49b3-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="e49b3-171">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e49b3-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-172">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-172">**Key**</span></span> | <span data-ttu-id="e49b3-173">exclusões</span><span class="sxs-lookup"><span data-stu-id="e49b3-173">exclusions</span></span> |
| <span data-ttu-id="e49b3-174">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-174">**Data type**</span></span> | <span data-ttu-id="e49b3-175">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e49b3-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e49b3-176">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-176">**Comments**</span></span> | <span data-ttu-id="e49b3-177">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e49b3-177">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="e49b3-178">**Tipo de exclusão**</span><span class="sxs-lookup"><span data-stu-id="e49b3-178">**Type of exclusion**</span></span>

<span data-ttu-id="e49b3-179">Especifica o tipo de conteúdo excluído da verificação.</span><span class="sxs-lookup"><span data-stu-id="e49b3-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-180">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-180">**Key**</span></span> | <span data-ttu-id="e49b3-181">$type</span><span class="sxs-lookup"><span data-stu-id="e49b3-181">$type</span></span> |
| <span data-ttu-id="e49b3-182">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-182">**Data type**</span></span> | <span data-ttu-id="e49b3-183">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-183">String</span></span> |
| <span data-ttu-id="e49b3-184">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-184">**Possible values**</span></span> | <span data-ttu-id="e49b3-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="e49b3-185">excludedPath</span></span> <br/> <span data-ttu-id="e49b3-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="e49b3-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="e49b3-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="e49b3-187">excludedFileName</span></span> |
|||

<span data-ttu-id="e49b3-188">**Caminho para conteúdo excluído**</span><span class="sxs-lookup"><span data-stu-id="e49b3-188">**Path to excluded content**</span></span>

<span data-ttu-id="e49b3-189">Usado para excluir conteúdo da verificação por caminho de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="e49b3-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-190">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-190">**Key**</span></span> | <span data-ttu-id="e49b3-191">caminho</span><span class="sxs-lookup"><span data-stu-id="e49b3-191">path</span></span> |
| <span data-ttu-id="e49b3-192">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-192">**Data type**</span></span> | <span data-ttu-id="e49b3-193">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-193">String</span></span> |
| <span data-ttu-id="e49b3-194">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-194">**Possible values**</span></span> | <span data-ttu-id="e49b3-195">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="e49b3-195">valid paths</span></span> |
| <span data-ttu-id="e49b3-196">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-196">**Comments**</span></span> | <span data-ttu-id="e49b3-197">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="e49b3-197">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="e49b3-198">**Tipo de caminho (arquivo/diretório)**</span><span class="sxs-lookup"><span data-stu-id="e49b3-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="e49b3-199">Indica se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="e49b3-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="e49b3-200">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-200">**Key**</span></span> | <span data-ttu-id="e49b3-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="e49b3-201">isDirectory</span></span> |
| <span data-ttu-id="e49b3-202">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-202">**Data type**</span></span> | <span data-ttu-id="e49b3-203">Booliano</span><span class="sxs-lookup"><span data-stu-id="e49b3-203">Boolean</span></span> |
| <span data-ttu-id="e49b3-204">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-204">**Possible values**</span></span> | <span data-ttu-id="e49b3-205">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-205">false (default)</span></span> <br/> <span data-ttu-id="e49b3-206">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="e49b3-206">true</span></span> |
| <span data-ttu-id="e49b3-207">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-207">**Comments**</span></span> | <span data-ttu-id="e49b3-208">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="e49b3-208">Applicable only if *$type* is *excludedPath*</span></span> |
|||

<span data-ttu-id="e49b3-209">**Extensão de arquivo excluída da verificação**</span><span class="sxs-lookup"><span data-stu-id="e49b3-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="e49b3-210">Usado para excluir conteúdo da verificação por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e49b3-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-211">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-211">**Key**</span></span> | <span data-ttu-id="e49b3-212">extension</span><span class="sxs-lookup"><span data-stu-id="e49b3-212">extension</span></span> |
| <span data-ttu-id="e49b3-213">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-213">**Data type**</span></span> | <span data-ttu-id="e49b3-214">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-214">String</span></span> |
| <span data-ttu-id="e49b3-215">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-215">**Possible values**</span></span> | <span data-ttu-id="e49b3-216">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="e49b3-216">valid file extensions</span></span> |
| <span data-ttu-id="e49b3-217">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-217">**Comments**</span></span> | <span data-ttu-id="e49b3-218">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="e49b3-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |
|||

<span data-ttu-id="e49b3-219">**Processo excluído da verificação**</span><span class="sxs-lookup"><span data-stu-id="e49b3-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="e49b3-220">Especifica um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="e49b3-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="e49b3-221">O processo pode ser especificado pelo nome (por exemplo) `cat` ou caminho completo (por exemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="e49b3-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-222">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-222">**Key**</span></span> | <span data-ttu-id="e49b3-223">nome</span><span class="sxs-lookup"><span data-stu-id="e49b3-223">name</span></span> |
| <span data-ttu-id="e49b3-224">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-224">**Data type**</span></span> | <span data-ttu-id="e49b3-225">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-225">String</span></span> |
| <span data-ttu-id="e49b3-226">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-226">**Possible values**</span></span> | <span data-ttu-id="e49b3-227">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-227">any string</span></span> |
| <span data-ttu-id="e49b3-228">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-228">**Comments**</span></span> | <span data-ttu-id="e49b3-229">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="e49b3-229">Applicable only if *$type* is *excludedFileName*</span></span> |
|||

#### <a name="allowed-threats"></a><span data-ttu-id="e49b3-230">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="e49b3-230">Allowed threats</span></span>

<span data-ttu-id="e49b3-231">Lista de ameaças (identificadas pelo nome) que não são bloqueadas pelo produto e têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="e49b3-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-232">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-232">**Key**</span></span> | <span data-ttu-id="e49b3-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="e49b3-233">allowedThreats</span></span> |
| <span data-ttu-id="e49b3-234">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-234">**Data type**</span></span> | <span data-ttu-id="e49b3-235">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-235">Array of strings</span></span> |
|||

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="e49b3-236">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="e49b3-236">Disallowed threat actions</span></span>

<span data-ttu-id="e49b3-237">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="e49b3-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="e49b3-238">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e49b3-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-239">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-239">**Key**</span></span> | <span data-ttu-id="e49b3-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="e49b3-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="e49b3-241">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-241">**Data type**</span></span> | <span data-ttu-id="e49b3-242">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-242">Array of strings</span></span> |
| <span data-ttu-id="e49b3-243">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-243">**Possible values**</span></span> | <span data-ttu-id="e49b3-244">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="e49b3-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="e49b3-245">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="e49b3-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="e49b3-246">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-246">**Comments**</span></span> | <span data-ttu-id="e49b3-247">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="threat-type-settings"></a><span data-ttu-id="e49b3-248">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="e49b3-248">Threat type settings</span></span>

<span data-ttu-id="e49b3-249">A *preferência threatTypeSettings* no mecanismo antivírus é usada para controlar como determinados tipos de ameaça são manipulados pelo produto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-250">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-250">**Key**</span></span> | <span data-ttu-id="e49b3-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="e49b3-251">threatTypeSettings</span></span> |
| <span data-ttu-id="e49b3-252">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-252">**Data type**</span></span> | <span data-ttu-id="e49b3-253">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e49b3-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e49b3-254">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-254">**Comments**</span></span> | <span data-ttu-id="e49b3-255">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e49b3-255">See the following sections for a description of the dictionary contents.</span></span> |
|||

<span data-ttu-id="e49b3-256">**Tipo de ameaça**</span><span class="sxs-lookup"><span data-stu-id="e49b3-256">**Threat type**</span></span>

<span data-ttu-id="e49b3-257">Tipo de ameaça para a qual o comportamento está configurado.</span><span class="sxs-lookup"><span data-stu-id="e49b3-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-258">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-258">**Key**</span></span> | <span data-ttu-id="e49b3-259">chave</span><span class="sxs-lookup"><span data-stu-id="e49b3-259">key</span></span> |
| <span data-ttu-id="e49b3-260">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-260">**Data type**</span></span> | <span data-ttu-id="e49b3-261">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-261">String</span></span> |
| <span data-ttu-id="e49b3-262">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-262">**Possible values**</span></span> | <span data-ttu-id="e49b3-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="e49b3-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="e49b3-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="e49b3-264">archive_bomb</span></span> |
|||

<span data-ttu-id="e49b3-265">**O que fazer**</span><span class="sxs-lookup"><span data-stu-id="e49b3-265">**Action to take**</span></span>

<span data-ttu-id="e49b3-266">Ação a ser tomada ao se deparar com uma ameaça do tipo especificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="e49b3-267">Pode ser:</span><span class="sxs-lookup"><span data-stu-id="e49b3-267">Can be:</span></span>

- <span data-ttu-id="e49b3-268">**Auditoria**: o dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="e49b3-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="e49b3-269">**Bloquear**: o dispositivo é protegido contra esse tipo de ameaça e você é notificado no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="e49b3-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="e49b3-270">**Off**: O dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="e49b3-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-271">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-271">**Key**</span></span> | <span data-ttu-id="e49b3-272">valor</span><span class="sxs-lookup"><span data-stu-id="e49b3-272">value</span></span> |
| <span data-ttu-id="e49b3-273">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-273">**Data type**</span></span> | <span data-ttu-id="e49b3-274">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-274">String</span></span> |
| <span data-ttu-id="e49b3-275">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-275">**Possible values**</span></span> | <span data-ttu-id="e49b3-276">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-276">audit (default)</span></span> <br/> <span data-ttu-id="e49b3-277">block</span><span class="sxs-lookup"><span data-stu-id="e49b3-277">block</span></span> <br/> <span data-ttu-id="e49b3-278">off</span><span class="sxs-lookup"><span data-stu-id="e49b3-278">off</span></span> |
|||

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="e49b3-279">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="e49b3-279">Threat type settings merge policy</span></span>

<span data-ttu-id="e49b3-280">Especifica a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="e49b3-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="e49b3-281">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="e49b3-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="e49b3-282">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="e49b3-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-283">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-283">**Key**</span></span> | <span data-ttu-id="e49b3-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="e49b3-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="e49b3-285">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-285">**Data type**</span></span> | <span data-ttu-id="e49b3-286">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-286">String</span></span> |
| <span data-ttu-id="e49b3-287">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-287">**Possible values**</span></span> | <span data-ttu-id="e49b3-288">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-288">merge (default)</span></span> <br/> <span data-ttu-id="e49b3-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="e49b3-289">admin_only</span></span> |
| <span data-ttu-id="e49b3-290">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-290">**Comments**</span></span> | <span data-ttu-id="e49b3-291">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="e49b3-292">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="e49b3-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="e49b3-293">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e49b3-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="e49b3-294">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="e49b3-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="e49b3-295">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="e49b3-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-296">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-296">**Key**</span></span> | <span data-ttu-id="e49b3-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="e49b3-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="e49b3-298">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-298">**Data type**</span></span> | <span data-ttu-id="e49b3-299">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-299">String</span></span> |
| <span data-ttu-id="e49b3-300">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-300">**Possible values**</span></span> | <span data-ttu-id="e49b3-301">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="e49b3-301">90 (default).</span></span> <span data-ttu-id="e49b3-302">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="e49b3-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="e49b3-303">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-303">**Comments**</span></span> | <span data-ttu-id="e49b3-304">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="e49b3-305">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="e49b3-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="e49b3-306">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="e49b3-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="e49b3-307">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="e49b3-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-308">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-308">**Key**</span></span> | <span data-ttu-id="e49b3-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="e49b3-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="e49b3-310">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-310">**Data type**</span></span> | <span data-ttu-id="e49b3-311">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-311">String</span></span> |
| <span data-ttu-id="e49b3-312">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-312">**Possible values**</span></span> | <span data-ttu-id="e49b3-313">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="e49b3-313">10000 (default).</span></span> <span data-ttu-id="e49b3-314">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="e49b3-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="e49b3-315">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-315">**Comments**</span></span> | <span data-ttu-id="e49b3-316">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="e49b3-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |
|||

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="e49b3-317">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="e49b3-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="e49b3-318">A *entrada do cloudService* no perfil de configuração é usada para configurar o recurso de proteção orientada por nuvem do produto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-319">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-319">**Key**</span></span> | <span data-ttu-id="e49b3-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="e49b3-320">cloudService</span></span> |
| <span data-ttu-id="e49b3-321">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-321">**Data type**</span></span> | <span data-ttu-id="e49b3-322">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="e49b3-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="e49b3-323">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="e49b3-323">**Comments**</span></span> | <span data-ttu-id="e49b3-324">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="e49b3-324">See the following sections for a description of the dictionary contents.</span></span> |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="e49b3-325">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="e49b3-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="e49b3-326">Determina se a proteção entregue na nuvem está habilitada no dispositivo ou não.</span><span class="sxs-lookup"><span data-stu-id="e49b3-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="e49b3-327">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="e49b3-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-328">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-328">**Key**</span></span> | <span data-ttu-id="e49b3-329">habilitadas</span><span class="sxs-lookup"><span data-stu-id="e49b3-329">enabled</span></span> |
| <span data-ttu-id="e49b3-330">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-330">**Data type**</span></span> | <span data-ttu-id="e49b3-331">Booliano</span><span class="sxs-lookup"><span data-stu-id="e49b3-331">Boolean</span></span> |
| <span data-ttu-id="e49b3-332">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-332">**Possible values**</span></span> | <span data-ttu-id="e49b3-333">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-333">true (default)</span></span> <br/> <span data-ttu-id="e49b3-334">falso</span><span class="sxs-lookup"><span data-stu-id="e49b3-334">false</span></span> |
|||

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="e49b3-335">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="e49b3-335">Diagnostic collection level</span></span>

<span data-ttu-id="e49b3-336">Os dados de diagnóstico são usados para manter o Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="e49b3-337">Essa configuração determina o nível de diagnóstico enviado pelo produto para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e49b3-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-338">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-338">**Key**</span></span> | <span data-ttu-id="e49b3-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="e49b3-339">diagnosticLevel</span></span> |
| <span data-ttu-id="e49b3-340">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-340">**Data type**</span></span> | <span data-ttu-id="e49b3-341">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-341">String</span></span> |
| <span data-ttu-id="e49b3-342">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-342">**Possible values**</span></span> | <span data-ttu-id="e49b3-343">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-343">optional (default)</span></span> <br/> <span data-ttu-id="e49b3-344">obrigatório</span><span class="sxs-lookup"><span data-stu-id="e49b3-344">required</span></span> |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="e49b3-345">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="e49b3-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="e49b3-346">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e49b3-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="e49b3-347">Há três níveis para controlar o envio de exemplo:</span><span class="sxs-lookup"><span data-stu-id="e49b3-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="e49b3-348">**Nenhum**: nenhum exemplo suspeito é enviado à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e49b3-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="e49b3-349">**Seguro**: somente amostras suspeitas que não contêm informações de identificação pessoal (PII) são enviadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e49b3-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="e49b3-350">Esse é o valor padrão para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="e49b3-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="e49b3-351">**All**: todos os exemplos suspeitos são enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e49b3-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-352">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-352">**Key**</span></span> | <span data-ttu-id="e49b3-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="e49b3-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="e49b3-354">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-354">**Data type**</span></span> | <span data-ttu-id="e49b3-355">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="e49b3-355">String</span></span> |
| <span data-ttu-id="e49b3-356">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-356">**Possible values**</span></span> | <span data-ttu-id="e49b3-357">nenhuma</span><span class="sxs-lookup"><span data-stu-id="e49b3-357">none</span></span> <br/> <span data-ttu-id="e49b3-358">safe (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-358">safe (default)</span></span> <br/> <span data-ttu-id="e49b3-359">all</span><span class="sxs-lookup"><span data-stu-id="e49b3-359">all</span></span> |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="e49b3-360">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="e49b3-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="e49b3-361">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e49b3-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="e49b3-362">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="e49b3-362">**Key**</span></span> | <span data-ttu-id="e49b3-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="e49b3-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="e49b3-364">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e49b3-364">**Data type**</span></span> | <span data-ttu-id="e49b3-365">Booliano</span><span class="sxs-lookup"><span data-stu-id="e49b3-365">Boolean</span></span> |
| <span data-ttu-id="e49b3-366">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="e49b3-366">**Possible values**</span></span> | <span data-ttu-id="e49b3-367">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="e49b3-367">true (default)</span></span> <br/> <span data-ttu-id="e49b3-368">falso</span><span class="sxs-lookup"><span data-stu-id="e49b3-368">false</span></span> |
|||

## <a name="recommended-configuration-profile"></a><span data-ttu-id="e49b3-369">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="e49b3-369">Recommended configuration profile</span></span>

<span data-ttu-id="e49b3-370">Para começar, recomendamos que o perfil de configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="e49b3-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="e49b3-371">O seguinte perfil de configuração será:</span><span class="sxs-lookup"><span data-stu-id="e49b3-371">The following configuration profile will:</span></span>

- <span data-ttu-id="e49b3-372">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="e49b3-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="e49b3-373">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="e49b3-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="e49b3-374">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="e49b3-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="e49b3-375">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para os logs do produto</span><span class="sxs-lookup"><span data-stu-id="e49b3-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="e49b3-376">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="e49b3-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="e49b3-377">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="e49b3-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="e49b3-378">Habilitar o envio automático de exemplo no `safe` nível</span><span class="sxs-lookup"><span data-stu-id="e49b3-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="e49b3-379">Perfil de exemplo</span><span class="sxs-lookup"><span data-stu-id="e49b3-379">Sample profile</span></span>

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
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="e49b3-380">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="e49b3-380">Full configuration profile example</span></span>

<span data-ttu-id="e49b3-381">O perfil de configuração a seguir contém entradas para todas as configurações descritas neste documento e pode ser usado para cenários mais avançados em que você deseja mais controle sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="e49b3-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="e49b3-382">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="e49b3-382">Full profile</span></span>

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
            "path":"/home"
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
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="e49b3-383">Validação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="e49b3-383">Configuration profile validation</span></span>

<span data-ttu-id="e49b3-384">O perfil de configuração deve ser um arquivo JSON formatado válido.</span><span class="sxs-lookup"><span data-stu-id="e49b3-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="e49b3-385">Há várias ferramentas que podem ser usadas para verificar isso.</span><span class="sxs-lookup"><span data-stu-id="e49b3-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="e49b3-386">Por exemplo, se você `python` tiver instalado em seu dispositivo:</span><span class="sxs-lookup"><span data-stu-id="e49b3-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="e49b3-387">Se o JSON for bem formado, o comando acima o retornará ao Terminal e retornará um código de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="e49b3-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="e49b3-388">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="e49b3-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a><span data-ttu-id="e49b3-389">Verificar se o arquivo mdatp_managed.json está funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="e49b3-389">Verifying that the mdatp_managed.json file is working as expected</span></span>
<span data-ttu-id="e49b3-390">Para verificar se o /etc/opt/microsoft/mdatp/managed/mdatp_managed.json está funcionando corretamente, você deve ver "[gerenciado]" ao lado dessas configurações:</span><span class="sxs-lookup"><span data-stu-id="e49b3-390">To verify that your /etc/opt/microsoft/mdatp/managed/mdatp_managed.json is working properly, you should see "[managed]" next to these settings:</span></span>  
- <span data-ttu-id="e49b3-391">cloud_enabled</span><span class="sxs-lookup"><span data-stu-id="e49b3-391">cloud_enabled</span></span>
- <span data-ttu-id="e49b3-392">cloud_automatic_sample_submission_consent</span><span class="sxs-lookup"><span data-stu-id="e49b3-392">cloud_automatic_sample_submission_consent</span></span>
- <span data-ttu-id="e49b3-393">passice_mode_enabled</span><span class="sxs-lookup"><span data-stu-id="e49b3-393">passice_mode_enabled</span></span>
- <span data-ttu-id="e49b3-394">real_time_protection_enabled</span><span class="sxs-lookup"><span data-stu-id="e49b3-394">real_time_protection_enabled</span></span>
- <span data-ttu-id="e49b3-395">automatic_definition_update_enabled</span><span class="sxs-lookup"><span data-stu-id="e49b3-395">automatic_definition_update_enabled</span></span>

> [!NOTE]
> <span data-ttu-id="e49b3-396">Para que mdatp_managed.jsa ação entre em vigor, nenhuma reinicialização do wdavdaemon é necessária.</span><span class="sxs-lookup"><span data-stu-id="e49b3-396">For the mdatp_managed.json to take effect, no restart of the wdavdaemon is required.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="e49b3-397">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="e49b3-397">Configuration profile deployment</span></span>

<span data-ttu-id="e49b3-398">Depois de construir o perfil de configuração para sua empresa, você poderá implantá-lo por meio da ferramenta de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="e49b3-398">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="e49b3-399">O Defender for Endpoint para Linux lê a configuração gerenciada do *arquivo /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="e49b3-399">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
