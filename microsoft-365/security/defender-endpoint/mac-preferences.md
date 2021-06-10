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
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b7dd8-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="b7dd8-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7dd8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-105">**Applies to:**</span></span>

- [<span data-ttu-id="b7dd8-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="b7dd8-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="b7dd8-107">Este artigo contém instruções sobre como definir preferências do Microsoft Defender para Endpoint no macOS em organizações corporativas.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="b7dd8-108">Para configurar o Microsoft Defender para Ponto de Extremidade no macOS usando a interface de linha de comando, consulte [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="b7dd8-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-109">Summary</span></span>

<span data-ttu-id="b7dd8-110">Em organizações corporativas, o Microsoft Defender para Ponto de Extremidade no macOS pode ser gerenciado por meio de um perfil de configuração implantado usando uma das várias ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="b7dd8-111">As preferências gerenciadas pela equipe de operações de segurança têm precedência sobre as preferências definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="b7dd8-112">Alterar as preferências definidas por meio do perfil de configuração exige privilégios escalonados e não está disponível para usuários sem permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="b7dd8-113">Este artigo descreve a estrutura do perfil de configuração, inclui um perfil recomendado que você pode usar para começar e fornece instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="b7dd8-114">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="b7dd8-114">Configuration profile structure</span></span>

<span data-ttu-id="b7dd8-115">O perfil de configuração é um *arquivo .plist* que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="b7dd8-116">Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="b7dd8-117">O layout do perfil de configuração depende do console de gerenciamento que você está usando.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="b7dd8-118">As seções a seguir contêm exemplos de perfis de configuração para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="b7dd8-119">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do Microsoft Defender para Ponto de Extremidade, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="b7dd8-120">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="b7dd8-120">Antivirus engine preferences</span></span>

<span data-ttu-id="b7dd8-121">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="b7dd8-122">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-122">Section</span></span>|<span data-ttu-id="b7dd8-123">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-124">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-125">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-125">**Key**</span></span> | <span data-ttu-id="b7dd8-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="b7dd8-126">antivirusEngine</span></span> |
| <span data-ttu-id="b7dd8-127">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-127">**Data type**</span></span> | <span data-ttu-id="b7dd8-128">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-129">**Comments**</span></span> | <span data-ttu-id="b7dd8-130">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="b7dd8-131">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="b7dd8-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="b7dd8-132">Especifique se é necessário habilitar a proteção em tempo real, que verifica os arquivos conforme eles são acessados.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="b7dd8-133">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-133">Section</span></span>|<span data-ttu-id="b7dd8-134">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-135">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-136">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-136">**Key**</span></span> | <span data-ttu-id="b7dd8-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="b7dd8-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="b7dd8-138">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-138">**Data type**</span></span> | <span data-ttu-id="b7dd8-139">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-139">Boolean</span></span> |
| <span data-ttu-id="b7dd8-140">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-140">**Possible values**</span></span> | <span data-ttu-id="b7dd8-141">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-141">true (default)</span></span> <br/> <span data-ttu-id="b7dd8-142">falso</span><span class="sxs-lookup"><span data-stu-id="b7dd8-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="b7dd8-143">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-143">Enable / disable passive mode</span></span>

<span data-ttu-id="b7dd8-144">Especifique se o mecanismo antivírus é executado no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="b7dd8-145">O modo passivo tem as seguintes implicações:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="b7dd8-146">A proteção em tempo real está desligada</span><span class="sxs-lookup"><span data-stu-id="b7dd8-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="b7dd8-147">A verificação sob demanda está 24h</span><span class="sxs-lookup"><span data-stu-id="b7dd8-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="b7dd8-148">A correção automática de ameaças está desligada</span><span class="sxs-lookup"><span data-stu-id="b7dd8-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="b7dd8-149">Atualizações de inteligência de segurança estão ativas</span><span class="sxs-lookup"><span data-stu-id="b7dd8-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="b7dd8-150">O ícone do menu Status está oculto</span><span class="sxs-lookup"><span data-stu-id="b7dd8-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="b7dd8-151">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-151">Section</span></span>|<span data-ttu-id="b7dd8-152">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-153">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-154">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-154">**Key**</span></span> | <span data-ttu-id="b7dd8-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="b7dd8-155">passiveMode</span></span> |
| <span data-ttu-id="b7dd8-156">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-156">**Data type**</span></span> | <span data-ttu-id="b7dd8-157">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-157">Boolean</span></span> |
| <span data-ttu-id="b7dd8-158">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-158">**Possible values**</span></span> | <span data-ttu-id="b7dd8-159">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-159">false (default)</span></span> <br/> <span data-ttu-id="b7dd8-160">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7dd8-160">true</span></span> |
| <span data-ttu-id="b7dd8-161">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-161">**Comments**</span></span> | <span data-ttu-id="b7dd8-162">Disponível no Microsoft Defender para Endpoint versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="b7dd8-163">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="b7dd8-163">Exclusion merge policy</span></span>

<span data-ttu-id="b7dd8-164">Especifique a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="b7dd8-165">Isso pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="b7dd8-166">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="b7dd8-167">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-167">Section</span></span>|<span data-ttu-id="b7dd8-168">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-169">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-170">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-170">**Key**</span></span> | <span data-ttu-id="b7dd8-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="b7dd8-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="b7dd8-172">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-172">**Data type**</span></span> | <span data-ttu-id="b7dd8-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-173">String</span></span> |
| <span data-ttu-id="b7dd8-174">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-174">**Possible values**</span></span> | <span data-ttu-id="b7dd8-175">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-175">merge (default)</span></span> <br/> <span data-ttu-id="b7dd8-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="b7dd8-176">admin_only</span></span> |
| <span data-ttu-id="b7dd8-177">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-177">**Comments**</span></span> | <span data-ttu-id="b7dd8-178">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="b7dd8-179">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="b7dd8-179">Scan exclusions</span></span>

<span data-ttu-id="b7dd8-180">Especifique entidades excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="b7dd8-181">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>
<span data-ttu-id="b7dd8-182">(As exclusões são especificadas como uma matriz de itens, o administrador pode especificar quantos elementos for necessário, em qualquer ordem.)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-182">(Exclusions are specified as an array of items, administrator can specify as many elements as necessary, in any order.)</span></span>

|<span data-ttu-id="b7dd8-183">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-183">Section</span></span>|<span data-ttu-id="b7dd8-184">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-184">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-185">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-185">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-186">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-186">**Key**</span></span> | <span data-ttu-id="b7dd8-187">exclusões</span><span class="sxs-lookup"><span data-stu-id="b7dd8-187">exclusions</span></span> |
| <span data-ttu-id="b7dd8-188">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-188">**Data type**</span></span> | <span data-ttu-id="b7dd8-189">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-189">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-190">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-190">**Comments**</span></span> | <span data-ttu-id="b7dd8-191">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-191">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="b7dd8-192">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="b7dd8-192">Type of exclusion</span></span>

<span data-ttu-id="b7dd8-193">Especifique o conteúdo excluído de ser verificado por tipo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-193">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="b7dd8-194">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-194">Section</span></span>|<span data-ttu-id="b7dd8-195">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-196">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-197">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-197">**Key**</span></span> | <span data-ttu-id="b7dd8-198">$type</span><span class="sxs-lookup"><span data-stu-id="b7dd8-198">$type</span></span> |
| <span data-ttu-id="b7dd8-199">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-199">**Data type**</span></span> | <span data-ttu-id="b7dd8-200">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-200">String</span></span> |
| <span data-ttu-id="b7dd8-201">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-201">**Possible values**</span></span> | <span data-ttu-id="b7dd8-202">excludedPath</span><span class="sxs-lookup"><span data-stu-id="b7dd8-202">excludedPath</span></span> <br/> <span data-ttu-id="b7dd8-203">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="b7dd8-203">excludedFileExtension</span></span> <br/> <span data-ttu-id="b7dd8-204">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="b7dd8-204">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="b7dd8-205">Caminho para conteúdo excluído</span><span class="sxs-lookup"><span data-stu-id="b7dd8-205">Path to excluded content</span></span>

<span data-ttu-id="b7dd8-206">Especifique o conteúdo excluído de ser verificado pelo caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-206">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="b7dd8-207">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-207">Section</span></span>|<span data-ttu-id="b7dd8-208">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-208">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-209">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-209">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-210">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-210">**Key**</span></span> | <span data-ttu-id="b7dd8-211">caminho</span><span class="sxs-lookup"><span data-stu-id="b7dd8-211">path</span></span> |
| <span data-ttu-id="b7dd8-212">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-212">**Data type**</span></span> | <span data-ttu-id="b7dd8-213">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-213">String</span></span> |
| <span data-ttu-id="b7dd8-214">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-214">**Possible values**</span></span> | <span data-ttu-id="b7dd8-215">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="b7dd8-215">valid paths</span></span> |
| <span data-ttu-id="b7dd8-216">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-216">**Comments**</span></span> | <span data-ttu-id="b7dd8-217">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="b7dd8-217">Applicable only if *$type* is *excludedPath*</span></span> |

## <a name="supported-exclusion-types"></a><span data-ttu-id="b7dd8-218">Tipos de exclusão com suporte</span><span class="sxs-lookup"><span data-stu-id="b7dd8-218">Supported exclusion types</span></span>

<span data-ttu-id="b7dd8-219">A tabela a seguir mostra os tipos de exclusão suportados pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-219">The follow table shows the exclusion types supported by Defender for Endpoint on Mac.</span></span>

<span data-ttu-id="b7dd8-220">Exclusão</span><span class="sxs-lookup"><span data-stu-id="b7dd8-220">Exclusion</span></span> | <span data-ttu-id="b7dd8-221">Definição</span><span class="sxs-lookup"><span data-stu-id="b7dd8-221">Definition</span></span> | <span data-ttu-id="b7dd8-222">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b7dd8-222">Examples</span></span>
---|---|---
<span data-ttu-id="b7dd8-223">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-223">File extension</span></span> | <span data-ttu-id="b7dd8-224">Todos os arquivos com a extensão, em qualquer lugar do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-224">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="b7dd8-225">Arquivo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-225">File</span></span> | <span data-ttu-id="b7dd8-226">Um arquivo específico identificado pelo caminho completo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-226">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="b7dd8-227">Pasta</span><span class="sxs-lookup"><span data-stu-id="b7dd8-227">Folder</span></span> | <span data-ttu-id="b7dd8-228">Todos os arquivos na pasta especificada (recursivamente)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-228">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="b7dd8-229">Processo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-229">Process</span></span> | <span data-ttu-id="b7dd8-230">Um processo específico (especificado pelo caminho completo ou nome do arquivo) e todos os arquivos abertos por ele</span><span class="sxs-lookup"><span data-stu-id="b7dd8-230">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="b7dd8-231">Os caminhos acima devem ser links rígidos, não links simbólicos, para serem excluídos com êxito.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-231">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="b7dd8-232">Você pode verificar se um caminho é um link simbólico executando `file <path-name>` .</span><span class="sxs-lookup"><span data-stu-id="b7dd8-232">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="b7dd8-233">As exclusões de arquivo, pasta e processo suportam os seguintes caracteres curinga:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-233">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="b7dd8-234">Curinga</span><span class="sxs-lookup"><span data-stu-id="b7dd8-234">Wildcard</span></span> | <span data-ttu-id="b7dd8-235">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7dd8-235">Description</span></span> | <span data-ttu-id="b7dd8-236">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-236">Example</span></span> | <span data-ttu-id="b7dd8-237">Matches</span><span class="sxs-lookup"><span data-stu-id="b7dd8-237">Matches</span></span> | <span data-ttu-id="b7dd8-238">Não se iguala</span><span class="sxs-lookup"><span data-stu-id="b7dd8-238">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="b7dd8-239">Corresponde a qualquer número de caracteres, incluindo nenhum (observe que quando esse caractere curinga é usado dentro de um caminho, ele substituirá apenas uma pasta)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-239">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="b7dd8-240">?</span><span class="sxs-lookup"><span data-stu-id="b7dd8-240">?</span></span> | <span data-ttu-id="b7dd8-241">Corresponde a qualquer caractere único</span><span class="sxs-lookup"><span data-stu-id="b7dd8-241">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

##### <a name="path-type-file--directory"></a><span data-ttu-id="b7dd8-242">Tipo de caminho (arquivo/diretório)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-242">Path type (file / directory)</span></span>

<span data-ttu-id="b7dd8-243">Indique se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-243">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="b7dd8-244">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-244">Section</span></span>|<span data-ttu-id="b7dd8-245">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-245">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-246">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-246">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-247">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-247">**Key**</span></span> | <span data-ttu-id="b7dd8-248">isDirectory</span><span class="sxs-lookup"><span data-stu-id="b7dd8-248">isDirectory</span></span> |
| <span data-ttu-id="b7dd8-249">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-249">**Data type**</span></span> | <span data-ttu-id="b7dd8-250">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-250">Boolean</span></span> |
| <span data-ttu-id="b7dd8-251">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-251">**Possible values**</span></span> | <span data-ttu-id="b7dd8-252">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-252">false (default)</span></span> <br/> <span data-ttu-id="b7dd8-253">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7dd8-253">true</span></span> |
| <span data-ttu-id="b7dd8-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-254">**Comments**</span></span> | <span data-ttu-id="b7dd8-255">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="b7dd8-255">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="b7dd8-256">Extensão de arquivo excluída da verificação</span><span class="sxs-lookup"><span data-stu-id="b7dd8-256">File extension excluded from the scan</span></span>

<span data-ttu-id="b7dd8-257">Especifique o conteúdo excluído de ser verificado por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-257">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="b7dd8-258">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-258">Section</span></span>|<span data-ttu-id="b7dd8-259">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-259">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-260">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-260">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-261">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-261">**Key**</span></span> | <span data-ttu-id="b7dd8-262">extension</span><span class="sxs-lookup"><span data-stu-id="b7dd8-262">extension</span></span> |
| <span data-ttu-id="b7dd8-263">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-263">**Data type**</span></span> | <span data-ttu-id="b7dd8-264">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-264">String</span></span> |
| <span data-ttu-id="b7dd8-265">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-265">**Possible values**</span></span> | <span data-ttu-id="b7dd8-266">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="b7dd8-266">valid file extensions</span></span> |
| <span data-ttu-id="b7dd8-267">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-267">**Comments**</span></span> | <span data-ttu-id="b7dd8-268">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="b7dd8-268">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="b7dd8-269">Processo excluído da verificação</span><span class="sxs-lookup"><span data-stu-id="b7dd8-269">Process excluded from the scan</span></span>

<span data-ttu-id="b7dd8-270">Especifique um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-270">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="b7dd8-271">O processo pode ser especificado pelo nome (por exemplo) ou caminho `cat` completo (por `/bin/cat` exemplo).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-271">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="b7dd8-272">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-272">Section</span></span>|<span data-ttu-id="b7dd8-273">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-273">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-274">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-274">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-275">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-275">**Key**</span></span> | <span data-ttu-id="b7dd8-276">nome</span><span class="sxs-lookup"><span data-stu-id="b7dd8-276">name</span></span> |
| <span data-ttu-id="b7dd8-277">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-277">**Data type**</span></span> | <span data-ttu-id="b7dd8-278">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-278">String</span></span> |
| <span data-ttu-id="b7dd8-279">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-279">**Possible values**</span></span> | <span data-ttu-id="b7dd8-280">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-280">any string</span></span> |
| <span data-ttu-id="b7dd8-281">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-281">**Comments**</span></span> | <span data-ttu-id="b7dd8-282">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="b7dd8-282">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="b7dd8-283">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="b7dd8-283">Allowed threats</span></span>

<span data-ttu-id="b7dd8-284">Especifique ameaças por nome que não são bloqueadas pelo Defender para Ponto de Extremidade no Mac.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-284">Specify threats by name that are not blocked by Defender for Endpoint on Mac.</span></span> <span data-ttu-id="b7dd8-285">Essas ameaças terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-285">These threats will be allowed to run.</span></span>

|<span data-ttu-id="b7dd8-286">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-286">Section</span></span>|<span data-ttu-id="b7dd8-287">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-287">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-288">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-288">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-289">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-289">**Key**</span></span> | <span data-ttu-id="b7dd8-290">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="b7dd8-290">allowedThreats</span></span> |
| <span data-ttu-id="b7dd8-291">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-291">**Data type**</span></span> | <span data-ttu-id="b7dd8-292">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-292">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="b7dd8-293">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="b7dd8-293">Disallowed threat actions</span></span>

<span data-ttu-id="b7dd8-294">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-294">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="b7dd8-295">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-295">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="b7dd8-296">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-296">Section</span></span>|<span data-ttu-id="b7dd8-297">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-298">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-299">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-299">**Key**</span></span> | <span data-ttu-id="b7dd8-300">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="b7dd8-300">disallowedThreatActions</span></span> |
| <span data-ttu-id="b7dd8-301">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-301">**Data type**</span></span> | <span data-ttu-id="b7dd8-302">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-302">Array of strings</span></span> |
| <span data-ttu-id="b7dd8-303">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-303">**Possible values**</span></span> | <span data-ttu-id="b7dd8-304">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-304">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="b7dd8-305">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-305">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="b7dd8-306">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-306">**Comments**</span></span> | <span data-ttu-id="b7dd8-307">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-307">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="b7dd8-308">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="b7dd8-308">Threat type settings</span></span>

<span data-ttu-id="b7dd8-309">Especifique como determinados tipos de ameaça são manipulados pelo Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-309">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="b7dd8-310">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-310">Section</span></span>|<span data-ttu-id="b7dd8-311">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-311">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-312">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-312">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-313">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-313">**Key**</span></span> | <span data-ttu-id="b7dd8-314">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="b7dd8-314">threatTypeSettings</span></span> |
| <span data-ttu-id="b7dd8-315">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-315">**Data type**</span></span> | <span data-ttu-id="b7dd8-316">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-316">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-317">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-317">**Comments**</span></span> | <span data-ttu-id="b7dd8-318">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-318">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="b7dd8-319">Tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="b7dd8-319">Threat type</span></span>

<span data-ttu-id="b7dd8-320">Especifique tipos de ameaça.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-320">Specify threat types.</span></span>

|<span data-ttu-id="b7dd8-321">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-321">Section</span></span>|<span data-ttu-id="b7dd8-322">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-322">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-323">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-323">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-324">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-324">**Key**</span></span> | <span data-ttu-id="b7dd8-325">chave</span><span class="sxs-lookup"><span data-stu-id="b7dd8-325">key</span></span> |
| <span data-ttu-id="b7dd8-326">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-326">**Data type**</span></span> | <span data-ttu-id="b7dd8-327">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-327">String</span></span> |
| <span data-ttu-id="b7dd8-328">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-328">**Possible values**</span></span> | <span data-ttu-id="b7dd8-329">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="b7dd8-329">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="b7dd8-330">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="b7dd8-330">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="b7dd8-331">O que fazer</span><span class="sxs-lookup"><span data-stu-id="b7dd8-331">Action to take</span></span>

<span data-ttu-id="b7dd8-332">Especifique qual ação tomar quando uma ameaça do tipo especificado na seção anterior for detectada.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-332">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="b7dd8-333">Escolha entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-333">Choose from the following options:</span></span>

- <span data-ttu-id="b7dd8-334">**Auditoria**: seu dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-334">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="b7dd8-335">**Bloquear**: seu dispositivo é protegido contra esse tipo de ameaça e você é notificado na interface do usuário e no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-335">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="b7dd8-336">**Off**: seu dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-336">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="b7dd8-337">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-337">Section</span></span>|<span data-ttu-id="b7dd8-338">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-338">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-339">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-339">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-340">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-340">**Key**</span></span> | <span data-ttu-id="b7dd8-341">valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-341">value</span></span> |
| <span data-ttu-id="b7dd8-342">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-342">**Data type**</span></span> | <span data-ttu-id="b7dd8-343">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-343">String</span></span> |
| <span data-ttu-id="b7dd8-344">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-344">**Possible values**</span></span> | <span data-ttu-id="b7dd8-345">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-345">audit (default)</span></span> <br/> <span data-ttu-id="b7dd8-346">block</span><span class="sxs-lookup"><span data-stu-id="b7dd8-346">block</span></span> <br/> <span data-ttu-id="b7dd8-347">off</span><span class="sxs-lookup"><span data-stu-id="b7dd8-347">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="b7dd8-348">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="b7dd8-348">Threat type settings merge policy</span></span>

<span data-ttu-id="b7dd8-349">Especifique a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-349">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="b7dd8-350">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-350">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="b7dd8-351">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-351">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="b7dd8-352">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-352">Section</span></span>|<span data-ttu-id="b7dd8-353">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-353">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-354">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-354">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-355">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-355">**Key**</span></span> | <span data-ttu-id="b7dd8-356">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="b7dd8-356">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="b7dd8-357">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-357">**Data type**</span></span> | <span data-ttu-id="b7dd8-358">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-358">String</span></span> |
| <span data-ttu-id="b7dd8-359">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-359">**Possible values**</span></span> | <span data-ttu-id="b7dd8-360">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-360">merge (default)</span></span> <br/> <span data-ttu-id="b7dd8-361">admin_only</span><span class="sxs-lookup"><span data-stu-id="b7dd8-361">admin_only</span></span> |
| <span data-ttu-id="b7dd8-362">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-362">**Comments**</span></span> | <span data-ttu-id="b7dd8-363">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-363">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="b7dd8-364">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-364">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="b7dd8-365">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-365">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="b7dd8-366">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-366">Old scan results are removed from the history.</span></span> <span data-ttu-id="b7dd8-367">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-367">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="b7dd8-368">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-368">Section</span></span>|<span data-ttu-id="b7dd8-369">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-369">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-370">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-370">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-371">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-371">**Key**</span></span> | <span data-ttu-id="b7dd8-372">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="b7dd8-372">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="b7dd8-373">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-373">**Data type**</span></span> | <span data-ttu-id="b7dd8-374">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-374">String</span></span> |
| <span data-ttu-id="b7dd8-375">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-375">**Possible values**</span></span> | <span data-ttu-id="b7dd8-376">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-376">90 (default).</span></span> <span data-ttu-id="b7dd8-377">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-377">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="b7dd8-378">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-378">**Comments**</span></span> | <span data-ttu-id="b7dd8-379">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-379">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="b7dd8-380">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="b7dd8-380">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="b7dd8-381">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-381">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="b7dd8-382">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-382">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="b7dd8-383">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-383">Section</span></span>|<span data-ttu-id="b7dd8-384">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-384">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-385">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-385">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-386">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-386">**Key**</span></span> | <span data-ttu-id="b7dd8-387">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="b7dd8-387">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="b7dd8-388">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-388">**Data type**</span></span> | <span data-ttu-id="b7dd8-389">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-389">String</span></span> |
| <span data-ttu-id="b7dd8-390">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-390">**Possible values**</span></span> | <span data-ttu-id="b7dd8-391">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="b7dd8-391">10000 (default).</span></span> <span data-ttu-id="b7dd8-392">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-392">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="b7dd8-393">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-393">**Comments**</span></span> | <span data-ttu-id="b7dd8-394">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-394">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="b7dd8-395">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="b7dd8-395">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="b7dd8-396">Configure os recursos de proteção orientados por nuvem do Microsoft Defender para Endpoint no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-396">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="b7dd8-397">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-397">Section</span></span>|<span data-ttu-id="b7dd8-398">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-399">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-400">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-400">**Key**</span></span> | <span data-ttu-id="b7dd8-401">cloudService</span><span class="sxs-lookup"><span data-stu-id="b7dd8-401">cloudService</span></span> |
| <span data-ttu-id="b7dd8-402">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-402">**Data type**</span></span> | <span data-ttu-id="b7dd8-403">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-403">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-404">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-404">**Comments**</span></span> | <span data-ttu-id="b7dd8-405">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-405">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="b7dd8-406">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="b7dd8-406">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="b7dd8-407">Especifique se o dispositivo deve ser habilitado ou não para a proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-407">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="b7dd8-408">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-408">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="b7dd8-409">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-409">Section</span></span>|<span data-ttu-id="b7dd8-410">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-410">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-411">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-411">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-412">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-412">**Key**</span></span> | <span data-ttu-id="b7dd8-413">habilitadas</span><span class="sxs-lookup"><span data-stu-id="b7dd8-413">enabled</span></span> |
| <span data-ttu-id="b7dd8-414">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-414">**Data type**</span></span> | <span data-ttu-id="b7dd8-415">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-415">Boolean</span></span> |
| <span data-ttu-id="b7dd8-416">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-416">**Possible values**</span></span> | <span data-ttu-id="b7dd8-417">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-417">true (default)</span></span> <br/> <span data-ttu-id="b7dd8-418">falso</span><span class="sxs-lookup"><span data-stu-id="b7dd8-418">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="b7dd8-419">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b7dd8-419">Diagnostic collection level</span></span>

<span data-ttu-id="b7dd8-420">Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-420">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="b7dd8-421">Essa configuração determina o nível de diagnóstico enviado pelo Microsoft Defender para o Ponto de Extremidade para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-421">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="b7dd8-422">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-422">Section</span></span>|<span data-ttu-id="b7dd8-423">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-424">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-424">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-425">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-425">**Key**</span></span> | <span data-ttu-id="b7dd8-426">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="b7dd8-426">diagnosticLevel</span></span> |
| <span data-ttu-id="b7dd8-427">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-427">**Data type**</span></span> | <span data-ttu-id="b7dd8-428">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-428">String</span></span> |
| <span data-ttu-id="b7dd8-429">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-429">**Possible values**</span></span> | <span data-ttu-id="b7dd8-430">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-430">optional (default)</span></span> <br/> <span data-ttu-id="b7dd8-431">obrigatório</span><span class="sxs-lookup"><span data-stu-id="b7dd8-431">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="b7dd8-432">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-432">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="b7dd8-433">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-433">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="b7dd8-434">Você será solicitado se o arquivo enviado provavelmente conter informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-434">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="b7dd8-435">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-435">Section</span></span>|<span data-ttu-id="b7dd8-436">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-436">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-437">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-437">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-438">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-438">**Key**</span></span> | <span data-ttu-id="b7dd8-439">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="b7dd8-439">automaticSampleSubmission</span></span> |
| <span data-ttu-id="b7dd8-440">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-440">**Data type**</span></span> | <span data-ttu-id="b7dd8-441">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-441">Boolean</span></span> |
| <span data-ttu-id="b7dd8-442">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-442">**Possible values**</span></span> | <span data-ttu-id="b7dd8-443">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-443">true (default)</span></span> <br/> <span data-ttu-id="b7dd8-444">falso</span><span class="sxs-lookup"><span data-stu-id="b7dd8-444">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="b7dd8-445">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="b7dd8-445">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="b7dd8-446">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-446">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="b7dd8-447">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-447">Section</span></span>|<span data-ttu-id="b7dd8-448">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-448">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-449">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-449">**Key**</span></span> | <span data-ttu-id="b7dd8-450">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="b7dd8-450">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="b7dd8-451">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-451">**Data type**</span></span> | <span data-ttu-id="b7dd8-452">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-452">Boolean</span></span> |
| <span data-ttu-id="b7dd8-453">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-453">**Possible values**</span></span> | <span data-ttu-id="b7dd8-454">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-454">true (default)</span></span> <br/> <span data-ttu-id="b7dd8-455">falso</span><span class="sxs-lookup"><span data-stu-id="b7dd8-455">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="b7dd8-456">Preferências de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="b7dd8-456">User interface preferences</span></span>

<span data-ttu-id="b7dd8-457">Gerencie as preferências para a interface do usuário do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-457">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="b7dd8-458">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-458">Section</span></span>|<span data-ttu-id="b7dd8-459">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-459">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-460">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-460">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-461">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-461">**Key**</span></span> | <span data-ttu-id="b7dd8-462">userInterface</span><span class="sxs-lookup"><span data-stu-id="b7dd8-462">userInterface</span></span> |
| <span data-ttu-id="b7dd8-463">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-463">**Data type**</span></span> | <span data-ttu-id="b7dd8-464">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-464">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-465">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-465">**Comments**</span></span> | <span data-ttu-id="b7dd8-466">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-466">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="b7dd8-467">Mostrar/ocultar ícone de menu de status</span><span class="sxs-lookup"><span data-stu-id="b7dd8-467">Show / hide status menu icon</span></span>

<span data-ttu-id="b7dd8-468">Especifique se deve mostrar ou ocultar o ícone do menu de status no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-468">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="b7dd8-469">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-469">Section</span></span>|<span data-ttu-id="b7dd8-470">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-470">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-471">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-471">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-472">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-472">**Key**</span></span> | <span data-ttu-id="b7dd8-473">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="b7dd8-473">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="b7dd8-474">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-474">**Data type**</span></span> | <span data-ttu-id="b7dd8-475">Booliano</span><span class="sxs-lookup"><span data-stu-id="b7dd8-475">Boolean</span></span> |
| <span data-ttu-id="b7dd8-476">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-476">**Possible values**</span></span> | <span data-ttu-id="b7dd8-477">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-477">false (default)</span></span> <br/> <span data-ttu-id="b7dd8-478">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="b7dd8-478">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="b7dd8-479">Mostrar/ocultar opção para enviar comentários</span><span class="sxs-lookup"><span data-stu-id="b7dd8-479">Show / hide option to send feedback</span></span>

<span data-ttu-id="b7dd8-480">Especifique se os usuários podem enviar comentários para a Microsoft indo para `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="b7dd8-480">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="b7dd8-481">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-481">Section</span></span>|<span data-ttu-id="b7dd8-482">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-482">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-483">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-483">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-484">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-484">**Key**</span></span> | <span data-ttu-id="b7dd8-485">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="b7dd8-485">userInitiatedFeedback</span></span> |
| <span data-ttu-id="b7dd8-486">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-486">**Data type**</span></span> | <span data-ttu-id="b7dd8-487">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-487">String</span></span> |
| <span data-ttu-id="b7dd8-488">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-488">**Possible values**</span></span> | <span data-ttu-id="b7dd8-489">habilitado (padrão)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-489">enabled (default)</span></span> <br/> <span data-ttu-id="b7dd8-490">desabilitadas</span><span class="sxs-lookup"><span data-stu-id="b7dd8-490">disabled</span></span> |
| <span data-ttu-id="b7dd8-491">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-491">**Comments**</span></span> | <span data-ttu-id="b7dd8-492">Disponível no Microsoft Defender para Endpoint versão 101.19.61 ou superior.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-492">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="b7dd8-493">Preferências de detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="b7dd8-493">Endpoint detection and response preferences</span></span>

<span data-ttu-id="b7dd8-494">Gerencie as preferências do componente detecção e resposta de ponto de extremidade (EDR) do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-494">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="b7dd8-495">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-495">Section</span></span>|<span data-ttu-id="b7dd8-496">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-496">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-497">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-497">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-498">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-498">**Key**</span></span> | <span data-ttu-id="b7dd8-499">edr</span><span class="sxs-lookup"><span data-stu-id="b7dd8-499">edr</span></span> |
| <span data-ttu-id="b7dd8-500">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-500">**Data type**</span></span> | <span data-ttu-id="b7dd8-501">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-501">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-502">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-502">**Comments**</span></span> | <span data-ttu-id="b7dd8-503">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-503">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="b7dd8-504">Marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-504">Device tags</span></span>

<span data-ttu-id="b7dd8-505">Especifique um nome de marca e seu valor.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-505">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="b7dd8-506">A marca GROUP marca o dispositivo com o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-506">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="b7dd8-507">A marca é refletida no portal sob a página do dispositivo e pode ser usada para filtrar e agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-507">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="b7dd8-508">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-508">Section</span></span>|<span data-ttu-id="b7dd8-509">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-509">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-510">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-510">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-511">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-511">**Key**</span></span> | <span data-ttu-id="b7dd8-512">categorias</span><span class="sxs-lookup"><span data-stu-id="b7dd8-512">tags</span></span> |
| <span data-ttu-id="b7dd8-513">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-513">**Data type**</span></span> | <span data-ttu-id="b7dd8-514">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-514">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="b7dd8-515">**Comments**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-515">**Comments**</span></span> | <span data-ttu-id="b7dd8-516">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-516">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="b7dd8-517">Tipo de marca</span><span class="sxs-lookup"><span data-stu-id="b7dd8-517">Type of tag</span></span>

<span data-ttu-id="b7dd8-518">Especifica o tipo de marca</span><span class="sxs-lookup"><span data-stu-id="b7dd8-518">Specifies the type of tag</span></span>

|<span data-ttu-id="b7dd8-519">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-519">Section</span></span>|<span data-ttu-id="b7dd8-520">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-520">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-521">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-521">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-522">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-522">**Key**</span></span> | <span data-ttu-id="b7dd8-523">chave</span><span class="sxs-lookup"><span data-stu-id="b7dd8-523">key</span></span> |
| <span data-ttu-id="b7dd8-524">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-524">**Data type**</span></span> | <span data-ttu-id="b7dd8-525">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-525">String</span></span> |
| <span data-ttu-id="b7dd8-526">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-526">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="b7dd8-527">Valor da marca</span><span class="sxs-lookup"><span data-stu-id="b7dd8-527">Value of tag</span></span>

<span data-ttu-id="b7dd8-528">Especifica o valor da marca</span><span class="sxs-lookup"><span data-stu-id="b7dd8-528">Specifies the value of tag</span></span>

|<span data-ttu-id="b7dd8-529">Section</span><span class="sxs-lookup"><span data-stu-id="b7dd8-529">Section</span></span>|<span data-ttu-id="b7dd8-530">Valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-530">Value</span></span>|
|:---|:---|
| <span data-ttu-id="b7dd8-531">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-531">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="b7dd8-532">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-532">**Key**</span></span> | <span data-ttu-id="b7dd8-533">valor</span><span class="sxs-lookup"><span data-stu-id="b7dd8-533">value</span></span> |
| <span data-ttu-id="b7dd8-534">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-534">**Data type**</span></span> | <span data-ttu-id="b7dd8-535">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-535">String</span></span> |
| <span data-ttu-id="b7dd8-536">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="b7dd8-536">**Possible values**</span></span> | <span data-ttu-id="b7dd8-537">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="b7dd8-537">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="b7dd8-538">Somente um valor por tipo de marca pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-538">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="b7dd8-539">O tipo de marcas é exclusivo e não deve ser repetido no mesmo perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-539">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="b7dd8-540">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="b7dd8-540">Recommended configuration profile</span></span>

<span data-ttu-id="b7dd8-541">Para começar, recomendamos que a configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Microsoft Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-541">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="b7dd8-542">O perfil de configuração a seguir (ou, no caso de JAMF, uma lista de propriedades que poderia ser carregada no perfil de configuração de configurações personalizadas) será:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-542">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="b7dd8-543">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-543">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="b7dd8-544">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-544">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="b7dd8-545">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="b7dd8-545">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="b7dd8-546">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para logs do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="b7dd8-546">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="b7dd8-547">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="b7dd8-547">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="b7dd8-548">Ativar proteção fornecida pela nuvem</span><span class="sxs-lookup"><span data-stu-id="b7dd8-548">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="b7dd8-549">Habilitar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="b7dd8-549">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="b7dd8-550">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="b7dd8-550">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="b7dd8-551">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="b7dd8-551">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="b7dd8-552">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="b7dd8-552">Full configuration profile example</span></span>

<span data-ttu-id="b7dd8-553">Os modelos a seguir contêm entradas para todas as configurações descritas neste documento e podem ser usadas para cenários mais avançados em que você deseja mais controle sobre o Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-553">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="b7dd8-554">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="b7dd8-554">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="b7dd8-555">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="b7dd8-555">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="b7dd8-556">Validação de lista de propriedades</span><span class="sxs-lookup"><span data-stu-id="b7dd8-556">Property list validation</span></span>

<span data-ttu-id="b7dd8-557">A lista de propriedades deve ser um arquivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-557">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="b7dd8-558">Isso pode ser verificado executando:</span><span class="sxs-lookup"><span data-stu-id="b7dd8-558">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="b7dd8-559">Se o arquivo for bem formado, o comando acima sairá e retornará um código `OK` de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="b7dd8-559">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="b7dd8-560">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="b7dd8-560">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="b7dd8-561">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="b7dd8-561">Configuration profile deployment</span></span>

<span data-ttu-id="b7dd8-562">Depois de construir o perfil de configuração da sua empresa, você pode implantá-lo por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-562">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="b7dd8-563">As seções a seguir fornecem instruções sobre como implantar esse perfil usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-563">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="b7dd8-564">Implantação jamf</span><span class="sxs-lookup"><span data-stu-id="b7dd8-564">JAMF deployment</span></span>

<span data-ttu-id="b7dd8-565">No console JAMF, **abra** Perfis de Configuração de Computadores , navegue até o perfil de configuração que você gostaria de  >  usar e selecione **Custom Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-565">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="b7dd8-566">Crie uma entrada com `com.microsoft.wdav` como o domínio de preferência e carregue o *.plist* produzido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-566">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="b7dd8-567">Você deve inserir o domínio de preferência correto ( ); caso contrário, as preferências não serão reconhecidas pelo `com.microsoft.wdav` Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-567">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="b7dd8-568">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="b7dd8-568">Intune deployment</span></span>

1. <span data-ttu-id="b7dd8-569">Abra **Gerenciar**  >  **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-569">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="b7dd8-570">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-570">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="b7dd8-571">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-571">Choose a name for the profile.</span></span> <span data-ttu-id="b7dd8-572">Alterar **Platform=macOS** para **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-572">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="b7dd8-573">Selecione Configurar.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-573">Select Configure.</span></span>

3. <span data-ttu-id="b7dd8-574">Salve o .plist produzido anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="b7dd8-574">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="b7dd8-575">Insira `com.microsoft.wdav` como o nome do perfil de **configuração personalizado**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-575">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="b7dd8-576">Abra o perfil de configuração e carregue o `com.microsoft.wdav.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-576">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="b7dd8-577">(Esse arquivo foi criado na etapa 3.)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-577">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="b7dd8-578">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-578">Select **OK**.</span></span>

7. <span data-ttu-id="b7dd8-579">Selecione **Gerenciar**  >  **atribuições**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-579">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="b7dd8-580">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-580">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="b7dd8-581">Você deve inserir o nome de perfil de configuração personalizado correto; caso contrário, essas preferências não serão reconhecidas pelo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7dd8-581">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="b7dd8-582">Recursos</span><span class="sxs-lookup"><span data-stu-id="b7dd8-582">Resources</span></span>

- [<span data-ttu-id="b7dd8-583">Referência do Perfil de Configuração (Documentação do desenvolvedor da Apple)</span><span class="sxs-lookup"><span data-stu-id="b7dd8-583">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
