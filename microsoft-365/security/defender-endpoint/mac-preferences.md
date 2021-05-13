---
title: Definir preferências para o Microsoft Defender para Ponto de Extremidade no Mac
description: Configure o MMicrosoft Defender para Ponto de Extremidade no Mac em organizações corporativas.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b706cb8dbd43d545768c1c573021b5ef401e3c09
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346397"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="5ec52-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="5ec52-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ec52-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5ec52-105">**Applies to:**</span></span>

- [<span data-ttu-id="5ec52-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="5ec52-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="5ec52-107">Este artigo contém instruções sobre como definir preferências do Microsoft Defender para Endpoint no macOS em organizações corporativas.</span><span class="sxs-lookup"><span data-stu-id="5ec52-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="5ec52-108">Para configurar o Microsoft Defender para Ponto de Extremidade no macOS usando a interface de linha de comando, consulte [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5ec52-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="5ec52-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="5ec52-109">Summary</span></span>

<span data-ttu-id="5ec52-110">Em organizações corporativas, o Microsoft Defender para Ponto de Extremidade no macOS pode ser gerenciado por meio de um perfil de configuração implantado usando uma das várias ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="5ec52-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="5ec52-111">As preferências gerenciadas pela equipe de operações de segurança têm precedência sobre as preferências definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="5ec52-112">Alterar as preferências definidas por meio do perfil de configuração exige privilégios escalonados e não está disponível para usuários sem permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="5ec52-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="5ec52-113">Este artigo descreve a estrutura do perfil de configuração, inclui um perfil recomendado que você pode usar para começar e fornece instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="5ec52-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="5ec52-114">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="5ec52-114">Configuration profile structure</span></span>

<span data-ttu-id="5ec52-115">O perfil de configuração é um *arquivo .plist* que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="5ec52-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="5ec52-116">Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="5ec52-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="5ec52-117">O layout do perfil de configuração depende do console de gerenciamento que você está usando.</span><span class="sxs-lookup"><span data-stu-id="5ec52-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="5ec52-118">As seções a seguir contêm exemplos de perfis de configuração para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="5ec52-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="5ec52-119">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do Microsoft Defender para Ponto de Extremidade, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="5ec52-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="5ec52-120">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="5ec52-120">Antivirus engine preferences</span></span>

<span data-ttu-id="5ec52-121">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5ec52-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="5ec52-122">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-122">Section</span></span>|<span data-ttu-id="5ec52-123">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-124">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-125">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-125">**Key**</span></span> | <span data-ttu-id="5ec52-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="5ec52-126">antivirusEngine</span></span> |
| <span data-ttu-id="5ec52-127">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-127">**Data type**</span></span> | <span data-ttu-id="5ec52-128">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-129">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-129">**Comments**</span></span> | <span data-ttu-id="5ec52-130">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="5ec52-131">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="5ec52-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="5ec52-132">Especifique se é necessário habilitar a proteção em tempo real, que verifica os arquivos conforme eles são acessados.</span><span class="sxs-lookup"><span data-stu-id="5ec52-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="5ec52-133">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-133">Section</span></span>|<span data-ttu-id="5ec52-134">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-135">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-136">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-136">**Key**</span></span> | <span data-ttu-id="5ec52-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="5ec52-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="5ec52-138">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-138">**Data type**</span></span> | <span data-ttu-id="5ec52-139">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-139">Boolean</span></span> |
| <span data-ttu-id="5ec52-140">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-140">**Possible values**</span></span> | <span data-ttu-id="5ec52-141">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-141">true (default)</span></span> <br/> <span data-ttu-id="5ec52-142">falso</span><span class="sxs-lookup"><span data-stu-id="5ec52-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="5ec52-143">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="5ec52-143">Enable / disable passive mode</span></span>

<span data-ttu-id="5ec52-144">Especifique se o mecanismo antivírus é executado no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="5ec52-145">O modo passivo tem as seguintes implicações:</span><span class="sxs-lookup"><span data-stu-id="5ec52-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="5ec52-146">A proteção em tempo real está desligada</span><span class="sxs-lookup"><span data-stu-id="5ec52-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="5ec52-147">A verificação sob demanda está 24h</span><span class="sxs-lookup"><span data-stu-id="5ec52-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="5ec52-148">A correção automática de ameaças está desligada</span><span class="sxs-lookup"><span data-stu-id="5ec52-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="5ec52-149">Atualizações de inteligência de segurança estão ativas</span><span class="sxs-lookup"><span data-stu-id="5ec52-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="5ec52-150">O ícone do menu Status está oculto</span><span class="sxs-lookup"><span data-stu-id="5ec52-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="5ec52-151">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-151">Section</span></span>|<span data-ttu-id="5ec52-152">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-153">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-154">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-154">**Key**</span></span> | <span data-ttu-id="5ec52-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="5ec52-155">passiveMode</span></span> |
| <span data-ttu-id="5ec52-156">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-156">**Data type**</span></span> | <span data-ttu-id="5ec52-157">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-157">Boolean</span></span> |
| <span data-ttu-id="5ec52-158">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-158">**Possible values**</span></span> | <span data-ttu-id="5ec52-159">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-159">false (default)</span></span> <br/> <span data-ttu-id="5ec52-160">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="5ec52-160">true</span></span> |
| <span data-ttu-id="5ec52-161">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-161">**Comments**</span></span> | <span data-ttu-id="5ec52-162">Disponível no Microsoft Defender para Endpoint versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="5ec52-163">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="5ec52-163">Exclusion merge policy</span></span>

<span data-ttu-id="5ec52-164">Especifique a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="5ec52-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="5ec52-165">Isso pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5ec52-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="5ec52-166">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="5ec52-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="5ec52-167">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-167">Section</span></span>|<span data-ttu-id="5ec52-168">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-169">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-170">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-170">**Key**</span></span> | <span data-ttu-id="5ec52-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5ec52-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="5ec52-172">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-172">**Data type**</span></span> | <span data-ttu-id="5ec52-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-173">String</span></span> |
| <span data-ttu-id="5ec52-174">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-174">**Possible values**</span></span> | <span data-ttu-id="5ec52-175">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-175">merge (default)</span></span> <br/> <span data-ttu-id="5ec52-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="5ec52-176">admin_only</span></span> |
| <span data-ttu-id="5ec52-177">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-177">**Comments**</span></span> | <span data-ttu-id="5ec52-178">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="5ec52-179">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="5ec52-179">Scan exclusions</span></span>

<span data-ttu-id="5ec52-180">Especifique entidades excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="5ec52-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="5ec52-181">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="5ec52-182">(As exclusões são especificadas como uma matriz de itens, o administrador pode especificar quantos elementos for necessário, em qualquer ordem.)</span><span class="sxs-lookup"><span data-stu-id="5ec52-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="5ec52-183">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-183">Section</span></span>|<span data-ttu-id="5ec52-184">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-185">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-186">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-186">**Key**</span></span> | <span data-ttu-id="5ec52-187">exclusões</span><span class="sxs-lookup"><span data-stu-id="5ec52-187">exclusions</span></span> |
| <span data-ttu-id="5ec52-188">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-188">**Data type**</span></span> | <span data-ttu-id="5ec52-189">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-190">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-190">**Comments**</span></span> | <span data-ttu-id="5ec52-191">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="5ec52-192">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="5ec52-192">Type of exclusion</span></span>

<span data-ttu-id="5ec52-193">Especifique o conteúdo excluído de ser verificado por tipo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="5ec52-194">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-194">Section</span></span>|<span data-ttu-id="5ec52-195">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-196">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-197">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-197">**Key**</span></span> | <span data-ttu-id="5ec52-198">$type</span><span class="sxs-lookup"><span data-stu-id="5ec52-198">$type</span></span> |
| <span data-ttu-id="5ec52-199">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-199">**Data type**</span></span> | <span data-ttu-id="5ec52-200">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-200">String</span></span> |
| <span data-ttu-id="5ec52-201">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-201">**Possible values**</span></span> | <span data-ttu-id="5ec52-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="5ec52-202">excludedPath</span></span> <br/> <span data-ttu-id="5ec52-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="5ec52-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="5ec52-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="5ec52-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="5ec52-205">Caminho para conteúdo excluído</span><span class="sxs-lookup"><span data-stu-id="5ec52-205">Path to excluded content</span></span>

<span data-ttu-id="5ec52-206">Especifique o conteúdo excluído de ser verificado pelo caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="5ec52-207">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-207">Section</span></span>|<span data-ttu-id="5ec52-208">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-209">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-210">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-210">**Key**</span></span> | <span data-ttu-id="5ec52-211">caminho</span><span class="sxs-lookup"><span data-stu-id="5ec52-211">path</span></span> |
| <span data-ttu-id="5ec52-212">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-212">**Data type**</span></span> | <span data-ttu-id="5ec52-213">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-213">String</span></span> |
| <span data-ttu-id="5ec52-214">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-214">**Possible values**</span></span> | <span data-ttu-id="5ec52-215">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="5ec52-215">valid paths</span></span> |
| <span data-ttu-id="5ec52-216">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-216">**Comments**</span></span> | <span data-ttu-id="5ec52-217">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="5ec52-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="5ec52-218">Tipos de exclusão com suporte</span><span class="sxs-lookup"><span data-stu-id="5ec52-218">Supported exclusion types</span></span>

<span data-ttu-id="5ec52-219">A tabela a seguir mostra os tipos de exclusão suportados pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="5ec52-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="5ec52-220">Exclusão</span><span class="sxs-lookup"><span data-stu-id="5ec52-220">Exclusion</span></span> | <span data-ttu-id="5ec52-221">Definição</span><span class="sxs-lookup"><span data-stu-id="5ec52-221">Definition</span></span> | <span data-ttu-id="5ec52-222">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5ec52-222">Examples</span></span>
---|---|---
<span data-ttu-id="5ec52-223">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="5ec52-223">File extension</span></span> | <span data-ttu-id="5ec52-224">Todos os arquivos com a extensão, em qualquer lugar do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5ec52-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="5ec52-225">File</span><span class="sxs-lookup"><span data-stu-id="5ec52-225">File</span></span> | <span data-ttu-id="5ec52-226">Um arquivo específico identificado pelo caminho completo</span><span class="sxs-lookup"><span data-stu-id="5ec52-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="5ec52-227">Pasta</span><span class="sxs-lookup"><span data-stu-id="5ec52-227">Folder</span></span> | <span data-ttu-id="5ec52-228">Todos os arquivos na pasta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="5ec52-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="5ec52-229">Processo</span><span class="sxs-lookup"><span data-stu-id="5ec52-229">Process</span></span> | <span data-ttu-id="5ec52-230">Um processo específico (especificado pelo caminho completo ou nome do arquivo) e todos os arquivos abertos por ele</span><span class="sxs-lookup"><span data-stu-id="5ec52-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="5ec52-231">Os caminhos acima devem ser links rígidos, não links simbólicos, para serem excluídos com êxito.</span><span class="sxs-lookup"><span data-stu-id="5ec52-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="5ec52-232">Você pode verificar se um caminho é um link simbólico executando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="5ec52-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="5ec52-233">As exclusões de arquivo, pasta e processo suportam os seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="5ec52-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="5ec52-234">Curinga</span><span class="sxs-lookup"><span data-stu-id="5ec52-234">Wildcard</span></span> | <span data-ttu-id="5ec52-235">Descrição</span><span class="sxs-lookup"><span data-stu-id="5ec52-235">Description</span></span> | <span data-ttu-id="5ec52-236">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5ec52-236">Example</span></span> | <span data-ttu-id="5ec52-237">Matches</span><span class="sxs-lookup"><span data-stu-id="5ec52-237">Matches</span></span> | <span data-ttu-id="5ec52-238">Não se iguala</span><span class="sxs-lookup"><span data-stu-id="5ec52-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="5ec52-239">Corresponde a qualquer número de caracteres, incluindo nenhum (observe que quando esse caractere curinga é usado dentro de um caminho, ele substituirá apenas uma pasta)</span><span class="sxs-lookup"><span data-stu-id="5ec52-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="5ec52-240">?</span><span class="sxs-lookup"><span data-stu-id="5ec52-240">?</span></span> | <span data-ttu-id="5ec52-241">Corresponde a qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="5ec52-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="5ec52-242">Tipo de caminho (arquivo/diretório)</span><span class="sxs-lookup"><span data-stu-id="5ec52-242">Path type (file / directory)</span></span>

<span data-ttu-id="5ec52-243">Indique se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="5ec52-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="5ec52-244">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-244">Section</span></span>|<span data-ttu-id="5ec52-245">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-246">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-247">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-247">**Key**</span></span> | <span data-ttu-id="5ec52-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="5ec52-248">isDirectory</span></span> |
| <span data-ttu-id="5ec52-249">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-249">**Data type**</span></span> | <span data-ttu-id="5ec52-250">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-250">Boolean</span></span> |
| <span data-ttu-id="5ec52-251">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-251">**Possible values**</span></span> | <span data-ttu-id="5ec52-252">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-252">false (default)</span></span> <br/> <span data-ttu-id="5ec52-253">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="5ec52-253">true</span></span> |
| <span data-ttu-id="5ec52-254">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-254">**Comments**</span></span> | <span data-ttu-id="5ec52-255">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="5ec52-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="5ec52-256">Extensão de arquivo excluída da verificação</span><span class="sxs-lookup"><span data-stu-id="5ec52-256">File extension excluded from the scan</span></span>

<span data-ttu-id="5ec52-257">Especifique o conteúdo excluído de ser verificado por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="5ec52-258">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-258">Section</span></span>|<span data-ttu-id="5ec52-259">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-260">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-261">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-261">**Key**</span></span> | <span data-ttu-id="5ec52-262">extension</span><span class="sxs-lookup"><span data-stu-id="5ec52-262">extension</span></span> |
| <span data-ttu-id="5ec52-263">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-263">**Data type**</span></span> | <span data-ttu-id="5ec52-264">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-264">String</span></span> |
| <span data-ttu-id="5ec52-265">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-265">**Possible values**</span></span> | <span data-ttu-id="5ec52-266">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="5ec52-266">valid file extensions</span></span> |
| <span data-ttu-id="5ec52-267">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-267">**Comments**</span></span> | <span data-ttu-id="5ec52-268">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="5ec52-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="5ec52-269">Processo excluído da verificação</span><span class="sxs-lookup"><span data-stu-id="5ec52-269">Process excluded from the scan</span></span>

<span data-ttu-id="5ec52-270">Especifique um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="5ec52-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="5ec52-271">O processo pode ser especificado pelo nome (por exemplo) ou caminho `cat` completo (por `/bin/cat` exemplo).</span><span class="sxs-lookup"><span data-stu-id="5ec52-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="5ec52-272">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-272">Section</span></span>|<span data-ttu-id="5ec52-273">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-274">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-275">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-275">**Key**</span></span> | <span data-ttu-id="5ec52-276">nome</span><span class="sxs-lookup"><span data-stu-id="5ec52-276">name</span></span> |
| <span data-ttu-id="5ec52-277">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-277">**Data type**</span></span> | <span data-ttu-id="5ec52-278">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-278">String</span></span> |
| <span data-ttu-id="5ec52-279">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-279">**Possible values**</span></span> | <span data-ttu-id="5ec52-280">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-280">any string</span></span> |
| <span data-ttu-id="5ec52-281">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-281">**Comments**</span></span> | <span data-ttu-id="5ec52-282">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="5ec52-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="5ec52-283">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="5ec52-283">Allowed threats</span></span>

<span data-ttu-id="5ec52-284">Especifique ameaças por nome que não são bloqueadas pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="5ec52-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="5ec52-285">Essas ameaças terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="5ec52-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="5ec52-286">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-286">Section</span></span>|<span data-ttu-id="5ec52-287">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-288">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-289">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-289">**Key**</span></span> | <span data-ttu-id="5ec52-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="5ec52-290">allowedThreats</span></span> |
| <span data-ttu-id="5ec52-291">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-291">**Data type**</span></span> | <span data-ttu-id="5ec52-292">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="5ec52-293">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="5ec52-293">Disallowed threat actions</span></span>

<span data-ttu-id="5ec52-294">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="5ec52-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="5ec52-295">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="5ec52-296">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-296">Section</span></span>|<span data-ttu-id="5ec52-297">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-298">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-299">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-299">**Key**</span></span> | <span data-ttu-id="5ec52-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="5ec52-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="5ec52-301">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-301">**Data type**</span></span> | <span data-ttu-id="5ec52-302">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-302">Array of strings</span></span> |
| <span data-ttu-id="5ec52-303">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-303">**Possible values**</span></span> | <span data-ttu-id="5ec52-304">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="5ec52-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="5ec52-305">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="5ec52-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="5ec52-306">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-306">**Comments**</span></span> | <span data-ttu-id="5ec52-307">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="5ec52-308">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="5ec52-308">Threat type settings</span></span>

<span data-ttu-id="5ec52-309">Especifique como determinados tipos de ameaça são manipulados pelo Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="5ec52-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5ec52-310">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-310">Section</span></span>|<span data-ttu-id="5ec52-311">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-312">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-313">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-313">**Key**</span></span> | <span data-ttu-id="5ec52-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="5ec52-314">threatTypeSettings</span></span> |
| <span data-ttu-id="5ec52-315">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-315">**Data type**</span></span> | <span data-ttu-id="5ec52-316">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-317">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-317">**Comments**</span></span> | <span data-ttu-id="5ec52-318">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="5ec52-319">Tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="5ec52-319">Threat type</span></span>

<span data-ttu-id="5ec52-320">Especifique tipos de ameaça.</span><span class="sxs-lookup"><span data-stu-id="5ec52-320">Specify threat types.</span></span>

|<span data-ttu-id="5ec52-321">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-321">Section</span></span>|<span data-ttu-id="5ec52-322">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-323">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-324">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-324">**Key**</span></span> | <span data-ttu-id="5ec52-325">chave</span><span class="sxs-lookup"><span data-stu-id="5ec52-325">key</span></span> |
| <span data-ttu-id="5ec52-326">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-326">**Data type**</span></span> | <span data-ttu-id="5ec52-327">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-327">String</span></span> |
| <span data-ttu-id="5ec52-328">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-328">**Possible values**</span></span> | <span data-ttu-id="5ec52-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="5ec52-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="5ec52-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="5ec52-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="5ec52-331">O que fazer</span><span class="sxs-lookup"><span data-stu-id="5ec52-331">Action to take</span></span>

<span data-ttu-id="5ec52-332">Especifique qual ação tomar quando uma ameaça do tipo especificado na seção anterior for detectada.</span><span class="sxs-lookup"><span data-stu-id="5ec52-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="5ec52-333">Escolha entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5ec52-333">Choose from the following options:</span></span>

- <span data-ttu-id="5ec52-334">**Auditoria**: seu dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="5ec52-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="5ec52-335">**Bloquear**: seu dispositivo é protegido contra esse tipo de ameaça e você é notificado na interface do usuário e no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="5ec52-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="5ec52-336">**Off**: seu dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="5ec52-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="5ec52-337">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-337">Section</span></span>|<span data-ttu-id="5ec52-338">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-339">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-340">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-340">**Key**</span></span> | <span data-ttu-id="5ec52-341">valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-341">value</span></span> |
| <span data-ttu-id="5ec52-342">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-342">**Data type**</span></span> | <span data-ttu-id="5ec52-343">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-343">String</span></span> |
| <span data-ttu-id="5ec52-344">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-344">**Possible values**</span></span> | <span data-ttu-id="5ec52-345">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-345">audit (default)</span></span> <br/> <span data-ttu-id="5ec52-346">block</span><span class="sxs-lookup"><span data-stu-id="5ec52-346">block</span></span> <br/> <span data-ttu-id="5ec52-347">off</span><span class="sxs-lookup"><span data-stu-id="5ec52-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="5ec52-348">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="5ec52-348">Threat type settings merge policy</span></span>

<span data-ttu-id="5ec52-349">Especifique a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="5ec52-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="5ec52-350">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="5ec52-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="5ec52-351">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="5ec52-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="5ec52-352">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-352">Section</span></span>|<span data-ttu-id="5ec52-353">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-354">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-355">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-355">**Key**</span></span> | <span data-ttu-id="5ec52-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="5ec52-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="5ec52-357">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-357">**Data type**</span></span> | <span data-ttu-id="5ec52-358">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-358">String</span></span> |
| <span data-ttu-id="5ec52-359">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-359">**Possible values**</span></span> | <span data-ttu-id="5ec52-360">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-360">merge (default)</span></span> <br/> <span data-ttu-id="5ec52-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="5ec52-361">admin_only</span></span> |
| <span data-ttu-id="5ec52-362">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-362">**Comments**</span></span> | <span data-ttu-id="5ec52-363">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="5ec52-364">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="5ec52-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="5ec52-365">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="5ec52-366">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="5ec52-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="5ec52-367">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="5ec52-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="5ec52-368">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-368">Section</span></span>|<span data-ttu-id="5ec52-369">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-370">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-371">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-371">**Key**</span></span> | <span data-ttu-id="5ec52-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="5ec52-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="5ec52-373">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-373">**Data type**</span></span> | <span data-ttu-id="5ec52-374">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-374">String</span></span> |
| <span data-ttu-id="5ec52-375">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-375">**Possible values**</span></span> | <span data-ttu-id="5ec52-376">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="5ec52-376">90 (default).</span></span> <span data-ttu-id="5ec52-377">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="5ec52-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="5ec52-378">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-378">**Comments**</span></span> | <span data-ttu-id="5ec52-379">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="5ec52-380">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="5ec52-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="5ec52-381">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="5ec52-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="5ec52-382">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="5ec52-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="5ec52-383">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-383">Section</span></span>|<span data-ttu-id="5ec52-384">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-385">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-386">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-386">**Key**</span></span> | <span data-ttu-id="5ec52-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="5ec52-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="5ec52-388">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-388">**Data type**</span></span> | <span data-ttu-id="5ec52-389">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-389">String</span></span> |
| <span data-ttu-id="5ec52-390">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-390">**Possible values**</span></span> | <span data-ttu-id="5ec52-391">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="5ec52-391">10000 (default).</span></span> <span data-ttu-id="5ec52-392">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="5ec52-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="5ec52-393">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-393">**Comments**</span></span> | <span data-ttu-id="5ec52-394">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="5ec52-395">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="5ec52-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="5ec52-396">Configure os recursos de proteção orientados por nuvem do Microsoft Defender para Endpoint no macOS.</span><span class="sxs-lookup"><span data-stu-id="5ec52-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5ec52-397">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-397">Section</span></span>|<span data-ttu-id="5ec52-398">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-399">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-400">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-400">**Key**</span></span> | <span data-ttu-id="5ec52-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="5ec52-401">cloudService</span></span> |
| <span data-ttu-id="5ec52-402">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-402">**Data type**</span></span> | <span data-ttu-id="5ec52-403">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-404">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-404">**Comments**</span></span> | <span data-ttu-id="5ec52-405">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="5ec52-406">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="5ec52-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="5ec52-407">Especifique se o dispositivo deve ser habilitado ou não para a proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="5ec52-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="5ec52-408">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="5ec52-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="5ec52-409">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-409">Section</span></span>|<span data-ttu-id="5ec52-410">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-411">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-412">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-412">**Key**</span></span> | <span data-ttu-id="5ec52-413">habilitadas</span><span class="sxs-lookup"><span data-stu-id="5ec52-413">enabled</span></span> |
| <span data-ttu-id="5ec52-414">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-414">**Data type**</span></span> | <span data-ttu-id="5ec52-415">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-415">Boolean</span></span> |
| <span data-ttu-id="5ec52-416">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-416">**Possible values**</span></span> | <span data-ttu-id="5ec52-417">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-417">true (default)</span></span> <br/> <span data-ttu-id="5ec52-418">falso</span><span class="sxs-lookup"><span data-stu-id="5ec52-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="5ec52-419">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5ec52-419">Diagnostic collection level</span></span>

<span data-ttu-id="5ec52-420">Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="5ec52-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="5ec52-421">Essa configuração determina o nível de diagnóstico enviado pelo Microsoft Defender para o Ponto de Extremidade para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ec52-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="5ec52-422">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-422">Section</span></span>|<span data-ttu-id="5ec52-423">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-424">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-425">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-425">**Key**</span></span> | <span data-ttu-id="5ec52-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="5ec52-426">diagnosticLevel</span></span> |
| <span data-ttu-id="5ec52-427">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-427">**Data type**</span></span> | <span data-ttu-id="5ec52-428">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-428">String</span></span> |
| <span data-ttu-id="5ec52-429">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-429">**Possible values**</span></span> | <span data-ttu-id="5ec52-430">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-430">optional (default)</span></span> <br/> <span data-ttu-id="5ec52-431">obrigatório</span><span class="sxs-lookup"><span data-stu-id="5ec52-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="5ec52-432">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="5ec52-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="5ec52-433">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ec52-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="5ec52-434">Você será solicitado se o arquivo enviado provavelmente conter informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="5ec52-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="5ec52-435">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-435">Section</span></span>|<span data-ttu-id="5ec52-436">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-437">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-438">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-438">**Key**</span></span> | <span data-ttu-id="5ec52-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="5ec52-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="5ec52-440">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-440">**Data type**</span></span> | <span data-ttu-id="5ec52-441">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-441">Boolean</span></span> |
| <span data-ttu-id="5ec52-442">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-442">**Possible values**</span></span> | <span data-ttu-id="5ec52-443">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-443">true (default)</span></span> <br/> <span data-ttu-id="5ec52-444">falso</span><span class="sxs-lookup"><span data-stu-id="5ec52-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="5ec52-445">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="5ec52-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="5ec52-446">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="5ec52-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="5ec52-447">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-447">Section</span></span>|<span data-ttu-id="5ec52-448">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-449">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-449">**Key**</span></span> | <span data-ttu-id="5ec52-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="5ec52-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="5ec52-451">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-451">**Data type**</span></span> | <span data-ttu-id="5ec52-452">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-452">Boolean</span></span> |
| <span data-ttu-id="5ec52-453">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-453">**Possible values**</span></span> | <span data-ttu-id="5ec52-454">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-454">true (default)</span></span> <br/> <span data-ttu-id="5ec52-455">falso</span><span class="sxs-lookup"><span data-stu-id="5ec52-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="5ec52-456">Preferências de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="5ec52-456">User interface preferences</span></span>

<span data-ttu-id="5ec52-457">Gerencie as preferências para a interface do usuário do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="5ec52-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5ec52-458">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-458">Section</span></span>|<span data-ttu-id="5ec52-459">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-460">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-461">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-461">**Key**</span></span> | <span data-ttu-id="5ec52-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="5ec52-462">userInterface</span></span> |
| <span data-ttu-id="5ec52-463">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-463">**Data type**</span></span> | <span data-ttu-id="5ec52-464">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-465">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-465">**Comments**</span></span> | <span data-ttu-id="5ec52-466">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="5ec52-467">Mostrar/ocultar ícone de menu de status</span><span class="sxs-lookup"><span data-stu-id="5ec52-467">Show / hide status menu icon</span></span>

<span data-ttu-id="5ec52-468">Especifique se deve mostrar ou ocultar o ícone do menu de status no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="5ec52-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="5ec52-469">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-469">Section</span></span>|<span data-ttu-id="5ec52-470">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-471">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-472">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-472">**Key**</span></span> | <span data-ttu-id="5ec52-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="5ec52-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="5ec52-474">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-474">**Data type**</span></span> | <span data-ttu-id="5ec52-475">Booliano</span><span class="sxs-lookup"><span data-stu-id="5ec52-475">Boolean</span></span> |
| <span data-ttu-id="5ec52-476">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-476">**Possible values**</span></span> | <span data-ttu-id="5ec52-477">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-477">false (default)</span></span> <br/> <span data-ttu-id="5ec52-478">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="5ec52-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="5ec52-479">Mostrar/ocultar opção para enviar comentários</span><span class="sxs-lookup"><span data-stu-id="5ec52-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="5ec52-480">Especifique se os usuários podem enviar comentários para a Microsoft indo para `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="5ec52-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="5ec52-481">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-481">Section</span></span>|<span data-ttu-id="5ec52-482">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-483">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-484">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-484">**Key**</span></span> | <span data-ttu-id="5ec52-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="5ec52-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="5ec52-486">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-486">**Data type**</span></span> | <span data-ttu-id="5ec52-487">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-487">String</span></span> |
| <span data-ttu-id="5ec52-488">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-488">**Possible values**</span></span> | <span data-ttu-id="5ec52-489">habilitado (padrão)</span><span class="sxs-lookup"><span data-stu-id="5ec52-489">enabled (default)</span></span> <br/> <span data-ttu-id="5ec52-490">desabilitadas</span><span class="sxs-lookup"><span data-stu-id="5ec52-490">disabled</span></span> |
| <span data-ttu-id="5ec52-491">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-491">**Comments**</span></span> | <span data-ttu-id="5ec52-492">Disponível no Microsoft Defender para Endpoint versão 101.19.61 ou superior.</span><span class="sxs-lookup"><span data-stu-id="5ec52-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="5ec52-493">Preferências de detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="5ec52-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="5ec52-494">Gerencie as preferências do componente detecção e resposta de ponto de extremidade (EDR) do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="5ec52-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="5ec52-495">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-495">Section</span></span>|<span data-ttu-id="5ec52-496">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-497">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-498">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-498">**Key**</span></span> | <span data-ttu-id="5ec52-499">edr</span><span class="sxs-lookup"><span data-stu-id="5ec52-499">edr</span></span> |
| <span data-ttu-id="5ec52-500">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-500">**Data type**</span></span> | <span data-ttu-id="5ec52-501">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-502">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-502">**Comments**</span></span> | <span data-ttu-id="5ec52-503">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="5ec52-504">Marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="5ec52-504">Device tags</span></span>

<span data-ttu-id="5ec52-505">Especifique um nome de marca e seu valor.</span><span class="sxs-lookup"><span data-stu-id="5ec52-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="5ec52-506">A marca GROUP marca o dispositivo com o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="5ec52-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="5ec52-507">A marca é refletida no portal sob a página do dispositivo e pode ser usada para filtrar e agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5ec52-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="5ec52-508">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-508">Section</span></span>|<span data-ttu-id="5ec52-509">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-510">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-511">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-511">**Key**</span></span> | <span data-ttu-id="5ec52-512">tags</span><span class="sxs-lookup"><span data-stu-id="5ec52-512">tags</span></span> |
| <span data-ttu-id="5ec52-513">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-513">**Data type**</span></span> | <span data-ttu-id="5ec52-514">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="5ec52-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5ec52-515">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="5ec52-515">**Comments**</span></span> | <span data-ttu-id="5ec52-516">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="5ec52-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="5ec52-517">Tipo de marca</span><span class="sxs-lookup"><span data-stu-id="5ec52-517">Type of tag</span></span>

<span data-ttu-id="5ec52-518">Especifica o tipo de marca</span><span class="sxs-lookup"><span data-stu-id="5ec52-518">Specifies the type of tag</span></span>

|<span data-ttu-id="5ec52-519">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-519">Section</span></span>|<span data-ttu-id="5ec52-520">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-521">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-522">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-522">**Key**</span></span> | <span data-ttu-id="5ec52-523">chave</span><span class="sxs-lookup"><span data-stu-id="5ec52-523">key</span></span> |
| <span data-ttu-id="5ec52-524">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-524">**Data type**</span></span> | <span data-ttu-id="5ec52-525">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-525">String</span></span> |
| <span data-ttu-id="5ec52-526">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="5ec52-527">Valor da marca</span><span class="sxs-lookup"><span data-stu-id="5ec52-527">Value of tag</span></span>

<span data-ttu-id="5ec52-528">Especifica o valor da marca</span><span class="sxs-lookup"><span data-stu-id="5ec52-528">Specifies the value of tag</span></span>

|<span data-ttu-id="5ec52-529">Section</span><span class="sxs-lookup"><span data-stu-id="5ec52-529">Section</span></span>|<span data-ttu-id="5ec52-530">Valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5ec52-531">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="5ec52-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5ec52-532">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="5ec52-532">**Key**</span></span> | <span data-ttu-id="5ec52-533">valor</span><span class="sxs-lookup"><span data-stu-id="5ec52-533">value</span></span> |
| <span data-ttu-id="5ec52-534">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5ec52-534">**Data type**</span></span> | <span data-ttu-id="5ec52-535">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-535">String</span></span> |
| <span data-ttu-id="5ec52-536">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="5ec52-536">**Possible values**</span></span> | <span data-ttu-id="5ec52-537">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="5ec52-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="5ec52-538">Somente um valor por tipo de marca pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="5ec52-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="5ec52-539">O tipo de marcas é exclusivo e não deve ser repetido no mesmo perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="5ec52-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="5ec52-540">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="5ec52-540">Recommended configuration profile</span></span>

<span data-ttu-id="5ec52-541">Para começar, recomendamos que a configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Microsoft Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="5ec52-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="5ec52-542">O perfil de configuração a seguir (ou, no caso de JAMF, uma lista de propriedades que poderia ser carregada no perfil de configuração de configurações personalizadas) será:</span><span class="sxs-lookup"><span data-stu-id="5ec52-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="5ec52-543">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="5ec52-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="5ec52-544">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="5ec52-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="5ec52-545">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="5ec52-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="5ec52-546">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para logs do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="5ec52-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="5ec52-547">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="5ec52-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="5ec52-548">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="5ec52-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="5ec52-549">Habilitar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="5ec52-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="5ec52-550">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="5ec52-550">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="5ec52-551">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="5ec52-551">Intune profile</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="5ec52-552">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="5ec52-552">Full configuration profile example</span></span>

<span data-ttu-id="5ec52-553">Os modelos a seguir contêm entradas para todas as configurações descritas neste documento e podem ser usadas para cenários mais avançados em que você deseja mais controle sobre o Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="5ec52-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="5ec52-554">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="5ec52-554">Property list for JAMF configuration profile</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a><span data-ttu-id="5ec52-555">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="5ec52-555">Intune profile</span></span>

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a><span data-ttu-id="5ec52-556">Validação de lista de propriedades</span><span class="sxs-lookup"><span data-stu-id="5ec52-556">Property list validation</span></span>

<span data-ttu-id="5ec52-557">A lista de propriedades deve ser um arquivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="5ec52-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="5ec52-558">Isso pode ser verificado executando:</span><span class="sxs-lookup"><span data-stu-id="5ec52-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="5ec52-559">Se o arquivo for bem formado, o comando acima sairá e retornará um código `OK` de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="5ec52-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="5ec52-560">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="5ec52-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="5ec52-561">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="5ec52-561">Configuration profile deployment</span></span>

<span data-ttu-id="5ec52-562">Depois de construir o perfil de configuração da sua empresa, você pode implantá-lo por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="5ec52-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="5ec52-563">As seções a seguir fornecem instruções sobre como implantar esse perfil usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="5ec52-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="5ec52-564">Implantação jamf</span><span class="sxs-lookup"><span data-stu-id="5ec52-564">JAMF deployment</span></span>

<span data-ttu-id="5ec52-565">No console JAMF, **abra** Perfis de Configuração de Computadores , navegue até o perfil de configuração que você gostaria de  >  usar e selecione **Custom Configurações**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="5ec52-566">Crie uma entrada com `com.microsoft.wdav` como o domínio de preferência e carregue o *.plist* produzido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5ec52-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="5ec52-567">Você deve inserir o domínio de preferência correto ( ); caso contrário, as preferências não serão reconhecidas pelo `com.microsoft.wdav` Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5ec52-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="5ec52-568">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="5ec52-568">Intune deployment</span></span>

1. <span data-ttu-id="5ec52-569">Abra **Gerenciar**  >  **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="5ec52-570">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="5ec52-571">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="5ec52-571">Choose a name for the profile.</span></span> <span data-ttu-id="5ec52-572">Alterar **Platform=macOS** para **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="5ec52-573">Selecione Configurar.</span><span class="sxs-lookup"><span data-stu-id="5ec52-573">Select Configure.</span></span>

3. <span data-ttu-id="5ec52-574">Salve o .plist produzido anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="5ec52-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="5ec52-575">Insira `com.microsoft.wdav` como o nome do perfil de **configuração personalizado**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="5ec52-576">Abra o perfil de configuração e carregue o `com.microsoft.wdav.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="5ec52-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="5ec52-577">(Esse arquivo foi criado na etapa 3.)</span><span class="sxs-lookup"><span data-stu-id="5ec52-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="5ec52-578">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-578">Select **OK**.</span></span>

7. <span data-ttu-id="5ec52-579">Selecione **Gerenciar**  >  **atribuições**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="5ec52-580">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="5ec52-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="5ec52-581">Você deve inserir o nome de perfil de configuração personalizado correto; caso contrário, essas preferências não serão reconhecidas pelo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5ec52-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="5ec52-582">Recursos</span><span class="sxs-lookup"><span data-stu-id="5ec52-582">Resources</span></span>

- [<span data-ttu-id="5ec52-583">Referência do Perfil de Configuração (Documentação do desenvolvedor da Apple)</span><span class="sxs-lookup"><span data-stu-id="5ec52-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
