---
title: Definir preferências para o Microsoft Defender ATP para Mac
description: Configure o Microsoft Defender ATP para Mac em organizações corporativas.
keywords: microsoft, defender, atp, mac, gerenciamento, preferências, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 951c51c767ba09ebc6056481b4fac45da09c5671
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688544"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="ba1af-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="ba1af-104">Set preferences for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ba1af-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ba1af-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba1af-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="ba1af-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="ba1af-107">Este artigo contém instruções sobre como definir preferências do Microsoft Defender para Endpoint no macOS em organizações corporativas.</span><span class="sxs-lookup"><span data-stu-id="ba1af-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint on macOS in enterprise organizations.</span></span> <span data-ttu-id="ba1af-108">Para configurar o Microsoft Defender para Ponto de Extremidade no macOS usando a interface de linha de comando, consulte [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ba1af-108">To configure Microsoft Defender for Endpoint on macOS using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="ba1af-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="ba1af-109">Summary</span></span>

<span data-ttu-id="ba1af-110">Em organizações corporativas, o Microsoft Defender para Ponto de Extremidade no macOS pode ser gerenciado por meio de um perfil de configuração implantado usando uma das várias ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ba1af-110">In enterprise organizations, Microsoft Defender for Endpoint on macOS can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="ba1af-111">As preferências gerenciadas pela equipe de operações de segurança têm precedência sobre as preferências definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="ba1af-112">Alterar as preferências definidas por meio do perfil de configuração exige privilégios escalonados e não está disponível para usuários sem permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="ba1af-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="ba1af-113">Este artigo descreve a estrutura do perfil de configuração, inclui um perfil recomendado que você pode usar para começar e fornece instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="ba1af-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="ba1af-114">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="ba1af-114">Configuration profile structure</span></span>

<span data-ttu-id="ba1af-115">O perfil de configuração é um *arquivo .plist* que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="ba1af-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="ba1af-116">Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="ba1af-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="ba1af-117">O layout do perfil de configuração depende do console de gerenciamento que você está usando.</span><span class="sxs-lookup"><span data-stu-id="ba1af-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="ba1af-118">As seções a seguir contêm exemplos de perfis de configuração para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="ba1af-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="ba1af-119">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do Microsoft Defender para Ponto de Extremidade, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="ba1af-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="ba1af-120">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="ba1af-120">Antivirus engine preferences</span></span>

<span data-ttu-id="ba1af-121">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ba1af-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|<span data-ttu-id="ba1af-122">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-122">Section</span></span>|<span data-ttu-id="ba1af-123">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-123">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-124">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-124">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-125">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-125">**Key**</span></span> | <span data-ttu-id="ba1af-126">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="ba1af-126">antivirusEngine</span></span> |
| <span data-ttu-id="ba1af-127">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-127">**Data type**</span></span> | <span data-ttu-id="ba1af-128">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-128">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-129">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-129">**Comments**</span></span> | <span data-ttu-id="ba1af-130">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-130">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="ba1af-131">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="ba1af-131">Enable / disable real-time protection</span></span>

<span data-ttu-id="ba1af-132">Especifique se é necessário habilitar a proteção em tempo real, que verifica os arquivos conforme eles são acessados.</span><span class="sxs-lookup"><span data-stu-id="ba1af-132">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|<span data-ttu-id="ba1af-133">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-133">Section</span></span>|<span data-ttu-id="ba1af-134">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-134">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-135">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-135">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-136">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-136">**Key**</span></span> | <span data-ttu-id="ba1af-137">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="ba1af-137">enableRealTimeProtection</span></span> |
| <span data-ttu-id="ba1af-138">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-138">**Data type**</span></span> | <span data-ttu-id="ba1af-139">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-139">Boolean</span></span> |
| <span data-ttu-id="ba1af-140">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-140">**Possible values**</span></span> | <span data-ttu-id="ba1af-141">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-141">true (default)</span></span> <br/> <span data-ttu-id="ba1af-142">falso</span><span class="sxs-lookup"><span data-stu-id="ba1af-142">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="ba1af-143">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="ba1af-143">Enable / disable passive mode</span></span>

<span data-ttu-id="ba1af-144">Especifique se o mecanismo antivírus é executado no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-144">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="ba1af-145">O modo passivo tem as seguintes implicações:</span><span class="sxs-lookup"><span data-stu-id="ba1af-145">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="ba1af-146">A proteção em tempo real está desligada</span><span class="sxs-lookup"><span data-stu-id="ba1af-146">Real-time protection is turned off</span></span>
- <span data-ttu-id="ba1af-147">A verificação sob demanda está 24h</span><span class="sxs-lookup"><span data-stu-id="ba1af-147">On-demand scanning is turned on</span></span>
- <span data-ttu-id="ba1af-148">A correção automática de ameaças está desligada</span><span class="sxs-lookup"><span data-stu-id="ba1af-148">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="ba1af-149">Atualizações de inteligência de segurança estão ativas</span><span class="sxs-lookup"><span data-stu-id="ba1af-149">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="ba1af-150">O ícone do menu Status está oculto</span><span class="sxs-lookup"><span data-stu-id="ba1af-150">Status menu icon is hidden</span></span>

|<span data-ttu-id="ba1af-151">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-151">Section</span></span>|<span data-ttu-id="ba1af-152">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-152">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-153">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-153">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-154">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-154">**Key**</span></span> | <span data-ttu-id="ba1af-155">passiveMode</span><span class="sxs-lookup"><span data-stu-id="ba1af-155">passiveMode</span></span> |
| <span data-ttu-id="ba1af-156">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-156">**Data type**</span></span> | <span data-ttu-id="ba1af-157">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-157">Boolean</span></span> |
| <span data-ttu-id="ba1af-158">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-158">**Possible values**</span></span> | <span data-ttu-id="ba1af-159">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-159">false (default)</span></span> <br/> <span data-ttu-id="ba1af-160">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ba1af-160">true</span></span> |
| <span data-ttu-id="ba1af-161">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-161">**Comments**</span></span> | <span data-ttu-id="ba1af-162">Disponível no Microsoft Defender para Endpoint versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-162">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="ba1af-163">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="ba1af-163">Exclusion merge policy</span></span>

<span data-ttu-id="ba1af-164">Especifique a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="ba1af-164">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="ba1af-165">Isso pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ba1af-165">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="ba1af-166">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="ba1af-166">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|<span data-ttu-id="ba1af-167">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-167">Section</span></span>|<span data-ttu-id="ba1af-168">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-168">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-169">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-169">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-170">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-170">**Key**</span></span> | <span data-ttu-id="ba1af-171">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ba1af-171">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="ba1af-172">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-172">**Data type**</span></span> | <span data-ttu-id="ba1af-173">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-173">String</span></span> |
| <span data-ttu-id="ba1af-174">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-174">**Possible values**</span></span> | <span data-ttu-id="ba1af-175">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-175">merge (default)</span></span> <br/> <span data-ttu-id="ba1af-176">admin_only</span><span class="sxs-lookup"><span data-stu-id="ba1af-176">admin_only</span></span> |
| <span data-ttu-id="ba1af-177">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-177">**Comments**</span></span> | <span data-ttu-id="ba1af-178">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-178">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="ba1af-179">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="ba1af-179">Scan exclusions</span></span>

<span data-ttu-id="ba1af-180">Especifique entidades excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="ba1af-180">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="ba1af-181">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-181">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|<span data-ttu-id="ba1af-182">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-182">Section</span></span>|<span data-ttu-id="ba1af-183">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-183">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-184">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-184">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-185">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-185">**Key**</span></span> | <span data-ttu-id="ba1af-186">exclusões</span><span class="sxs-lookup"><span data-stu-id="ba1af-186">exclusions</span></span> |
| <span data-ttu-id="ba1af-187">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-187">**Data type**</span></span> | <span data-ttu-id="ba1af-188">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-188">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-189">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-189">**Comments**</span></span> | <span data-ttu-id="ba1af-190">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-190">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="ba1af-191">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="ba1af-191">Type of exclusion</span></span>

<span data-ttu-id="ba1af-192">Especifique o conteúdo excluído de ser verificado por tipo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-192">Specify content excluded from being scanned by type.</span></span>

|<span data-ttu-id="ba1af-193">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-193">Section</span></span>|<span data-ttu-id="ba1af-194">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-194">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-195">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-195">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-196">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-196">**Key**</span></span> | <span data-ttu-id="ba1af-197">$type</span><span class="sxs-lookup"><span data-stu-id="ba1af-197">$type</span></span> |
| <span data-ttu-id="ba1af-198">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-198">**Data type**</span></span> | <span data-ttu-id="ba1af-199">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-199">String</span></span> |
| <span data-ttu-id="ba1af-200">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-200">**Possible values**</span></span> | <span data-ttu-id="ba1af-201">excludedPath</span><span class="sxs-lookup"><span data-stu-id="ba1af-201">excludedPath</span></span> <br/> <span data-ttu-id="ba1af-202">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="ba1af-202">excludedFileExtension</span></span> <br/> <span data-ttu-id="ba1af-203">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="ba1af-203">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="ba1af-204">Caminho para conteúdo excluído</span><span class="sxs-lookup"><span data-stu-id="ba1af-204">Path to excluded content</span></span>

<span data-ttu-id="ba1af-205">Especifique o conteúdo excluído de ser verificado pelo caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-205">Specify content excluded from being scanned by full file path.</span></span>

|<span data-ttu-id="ba1af-206">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-206">Section</span></span>|<span data-ttu-id="ba1af-207">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-207">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-208">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-208">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-209">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-209">**Key**</span></span> | <span data-ttu-id="ba1af-210">caminho</span><span class="sxs-lookup"><span data-stu-id="ba1af-210">path</span></span> |
| <span data-ttu-id="ba1af-211">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-211">**Data type**</span></span> | <span data-ttu-id="ba1af-212">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-212">String</span></span> |
| <span data-ttu-id="ba1af-213">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-213">**Possible values**</span></span> | <span data-ttu-id="ba1af-214">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="ba1af-214">valid paths</span></span> |
| <span data-ttu-id="ba1af-215">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-215">**Comments**</span></span> | <span data-ttu-id="ba1af-216">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="ba1af-216">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="ba1af-217">Tipo de caminho (arquivo/diretório)</span><span class="sxs-lookup"><span data-stu-id="ba1af-217">Path type (file / directory)</span></span>

<span data-ttu-id="ba1af-218">Indique se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="ba1af-218">Indicate if the *path* property refers to a file or directory.</span></span> 

|<span data-ttu-id="ba1af-219">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-219">Section</span></span>|<span data-ttu-id="ba1af-220">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-220">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-221">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-221">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-222">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-222">**Key**</span></span> | <span data-ttu-id="ba1af-223">isDirectory</span><span class="sxs-lookup"><span data-stu-id="ba1af-223">isDirectory</span></span> |
| <span data-ttu-id="ba1af-224">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-224">**Data type**</span></span> | <span data-ttu-id="ba1af-225">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-225">Boolean</span></span> |
| <span data-ttu-id="ba1af-226">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-226">**Possible values**</span></span> | <span data-ttu-id="ba1af-227">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-227">false (default)</span></span> <br/> <span data-ttu-id="ba1af-228">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ba1af-228">true</span></span> |
| <span data-ttu-id="ba1af-229">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-229">**Comments**</span></span> | <span data-ttu-id="ba1af-230">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="ba1af-230">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="ba1af-231">Extensão de arquivo excluída da verificação</span><span class="sxs-lookup"><span data-stu-id="ba1af-231">File extension excluded from the scan</span></span>

<span data-ttu-id="ba1af-232">Especifique o conteúdo excluído de ser verificado por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-232">Specify content excluded from being scanned by file extension.</span></span>

|<span data-ttu-id="ba1af-233">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-233">Section</span></span>|<span data-ttu-id="ba1af-234">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-234">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-235">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-235">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-236">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-236">**Key**</span></span> | <span data-ttu-id="ba1af-237">extension</span><span class="sxs-lookup"><span data-stu-id="ba1af-237">extension</span></span> |
| <span data-ttu-id="ba1af-238">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-238">**Data type**</span></span> | <span data-ttu-id="ba1af-239">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-239">String</span></span> |
| <span data-ttu-id="ba1af-240">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-240">**Possible values**</span></span> | <span data-ttu-id="ba1af-241">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="ba1af-241">valid file extensions</span></span> |
| <span data-ttu-id="ba1af-242">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-242">**Comments**</span></span> | <span data-ttu-id="ba1af-243">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="ba1af-243">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="ba1af-244">Processo excluído da verificação</span><span class="sxs-lookup"><span data-stu-id="ba1af-244">Process excluded from the scan</span></span>

<span data-ttu-id="ba1af-245">Especifique um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="ba1af-245">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="ba1af-246">O processo pode ser especificado pelo nome (por exemplo) ou caminho `cat` completo (por `/bin/cat` exemplo).</span><span class="sxs-lookup"><span data-stu-id="ba1af-246">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|<span data-ttu-id="ba1af-247">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-247">Section</span></span>|<span data-ttu-id="ba1af-248">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-248">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-249">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-250">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-250">**Key**</span></span> | <span data-ttu-id="ba1af-251">nome</span><span class="sxs-lookup"><span data-stu-id="ba1af-251">name</span></span> |
| <span data-ttu-id="ba1af-252">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-252">**Data type**</span></span> | <span data-ttu-id="ba1af-253">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-253">String</span></span> |
| <span data-ttu-id="ba1af-254">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-254">**Possible values**</span></span> | <span data-ttu-id="ba1af-255">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-255">any string</span></span> |
| <span data-ttu-id="ba1af-256">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-256">**Comments**</span></span> | <span data-ttu-id="ba1af-257">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="ba1af-257">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="ba1af-258">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="ba1af-258">Allowed threats</span></span>

<span data-ttu-id="ba1af-259">Especifique ameaças por nome que não são bloqueadas pelo Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="ba1af-259">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="ba1af-260">Essas ameaças terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="ba1af-260">These threats will be allowed to run.</span></span>

|<span data-ttu-id="ba1af-261">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-261">Section</span></span>|<span data-ttu-id="ba1af-262">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-262">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-263">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-263">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-264">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-264">**Key**</span></span> | <span data-ttu-id="ba1af-265">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="ba1af-265">allowedThreats</span></span> |
| <span data-ttu-id="ba1af-266">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-266">**Data type**</span></span> | <span data-ttu-id="ba1af-267">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-267">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="ba1af-268">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="ba1af-268">Disallowed threat actions</span></span>

<span data-ttu-id="ba1af-269">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="ba1af-269">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="ba1af-270">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-270">The actions included in this list are not displayed in the user interface.</span></span>

|<span data-ttu-id="ba1af-271">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-271">Section</span></span>|<span data-ttu-id="ba1af-272">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-272">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-273">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-273">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-274">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-274">**Key**</span></span> | <span data-ttu-id="ba1af-275">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="ba1af-275">disallowedThreatActions</span></span> |
| <span data-ttu-id="ba1af-276">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-276">**Data type**</span></span> | <span data-ttu-id="ba1af-277">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-277">Array of strings</span></span> |
| <span data-ttu-id="ba1af-278">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-278">**Possible values**</span></span> | <span data-ttu-id="ba1af-279">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="ba1af-279">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="ba1af-280">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="ba1af-280">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="ba1af-281">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-281">**Comments**</span></span> | <span data-ttu-id="ba1af-282">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-282">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="ba1af-283">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="ba1af-283">Threat type settings</span></span>

<span data-ttu-id="ba1af-284">Especifique como determinados tipos de ameaça são manipulados pelo Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="ba1af-284">Specify how certain threat types are handled by Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="ba1af-285">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-285">Section</span></span>|<span data-ttu-id="ba1af-286">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-286">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-287">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-287">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-288">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-288">**Key**</span></span> | <span data-ttu-id="ba1af-289">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="ba1af-289">threatTypeSettings</span></span> |
| <span data-ttu-id="ba1af-290">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-290">**Data type**</span></span> | <span data-ttu-id="ba1af-291">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-291">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-292">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-292">**Comments**</span></span> | <span data-ttu-id="ba1af-293">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-293">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="ba1af-294">Tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="ba1af-294">Threat type</span></span>

<span data-ttu-id="ba1af-295">Especifique tipos de ameaça.</span><span class="sxs-lookup"><span data-stu-id="ba1af-295">Specify threat types.</span></span>

|<span data-ttu-id="ba1af-296">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-296">Section</span></span>|<span data-ttu-id="ba1af-297">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-297">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-298">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-298">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-299">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-299">**Key**</span></span> | <span data-ttu-id="ba1af-300">chave</span><span class="sxs-lookup"><span data-stu-id="ba1af-300">key</span></span> |
| <span data-ttu-id="ba1af-301">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-301">**Data type**</span></span> | <span data-ttu-id="ba1af-302">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-302">String</span></span> |
| <span data-ttu-id="ba1af-303">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-303">**Possible values**</span></span> | <span data-ttu-id="ba1af-304">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="ba1af-304">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="ba1af-305">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="ba1af-305">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="ba1af-306">O que fazer</span><span class="sxs-lookup"><span data-stu-id="ba1af-306">Action to take</span></span>

<span data-ttu-id="ba1af-307">Especifique qual ação tomar quando uma ameaça do tipo especificado na seção anterior for detectada.</span><span class="sxs-lookup"><span data-stu-id="ba1af-307">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="ba1af-308">Escolha entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ba1af-308">Choose from the following options:</span></span>

- <span data-ttu-id="ba1af-309">**Auditoria**: seu dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="ba1af-309">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="ba1af-310">**Bloquear**: seu dispositivo é protegido contra esse tipo de ameaça e você é notificado na interface do usuário e no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="ba1af-310">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="ba1af-311">**Off**: seu dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="ba1af-311">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|<span data-ttu-id="ba1af-312">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-312">Section</span></span>|<span data-ttu-id="ba1af-313">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-313">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-314">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-314">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-315">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-315">**Key**</span></span> | <span data-ttu-id="ba1af-316">valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-316">value</span></span> |
| <span data-ttu-id="ba1af-317">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-317">**Data type**</span></span> | <span data-ttu-id="ba1af-318">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-318">String</span></span> |
| <span data-ttu-id="ba1af-319">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-319">**Possible values**</span></span> | <span data-ttu-id="ba1af-320">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-320">audit (default)</span></span> <br/> <span data-ttu-id="ba1af-321">block</span><span class="sxs-lookup"><span data-stu-id="ba1af-321">block</span></span> <br/> <span data-ttu-id="ba1af-322">off</span><span class="sxs-lookup"><span data-stu-id="ba1af-322">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="ba1af-323">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="ba1af-323">Threat type settings merge policy</span></span>

<span data-ttu-id="ba1af-324">Especifique a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="ba1af-324">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="ba1af-325">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="ba1af-325">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="ba1af-326">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="ba1af-326">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|<span data-ttu-id="ba1af-327">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-327">Section</span></span>|<span data-ttu-id="ba1af-328">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-328">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-329">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-329">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-330">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-330">**Key**</span></span> | <span data-ttu-id="ba1af-331">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="ba1af-331">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="ba1af-332">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-332">**Data type**</span></span> | <span data-ttu-id="ba1af-333">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-333">String</span></span> |
| <span data-ttu-id="ba1af-334">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-334">**Possible values**</span></span> | <span data-ttu-id="ba1af-335">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-335">merge (default)</span></span> <br/> <span data-ttu-id="ba1af-336">admin_only</span><span class="sxs-lookup"><span data-stu-id="ba1af-336">admin_only</span></span> |
| <span data-ttu-id="ba1af-337">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-337">**Comments**</span></span> | <span data-ttu-id="ba1af-338">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-338">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="ba1af-339">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="ba1af-339">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="ba1af-340">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-340">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="ba1af-341">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="ba1af-341">Old scan results are removed from the history.</span></span> <span data-ttu-id="ba1af-342">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="ba1af-342">Old quarantined files that are also removed from the disk.</span></span>

|<span data-ttu-id="ba1af-343">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-343">Section</span></span>|<span data-ttu-id="ba1af-344">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-344">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-345">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-345">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-346">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-346">**Key**</span></span> | <span data-ttu-id="ba1af-347">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="ba1af-347">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="ba1af-348">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-348">**Data type**</span></span> | <span data-ttu-id="ba1af-349">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-349">String</span></span> |
| <span data-ttu-id="ba1af-350">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-350">**Possible values**</span></span> | <span data-ttu-id="ba1af-351">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="ba1af-351">90 (default).</span></span> <span data-ttu-id="ba1af-352">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="ba1af-352">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="ba1af-353">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-353">**Comments**</span></span> | <span data-ttu-id="ba1af-354">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-354">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="ba1af-355">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="ba1af-355">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="ba1af-356">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="ba1af-356">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="ba1af-357">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="ba1af-357">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|<span data-ttu-id="ba1af-358">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-358">Section</span></span>|<span data-ttu-id="ba1af-359">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-359">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-360">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-360">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-361">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-361">**Key**</span></span> | <span data-ttu-id="ba1af-362">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="ba1af-362">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="ba1af-363">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-363">**Data type**</span></span> | <span data-ttu-id="ba1af-364">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-364">String</span></span> |
| <span data-ttu-id="ba1af-365">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-365">**Possible values**</span></span> | <span data-ttu-id="ba1af-366">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="ba1af-366">10000 (default).</span></span> <span data-ttu-id="ba1af-367">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="ba1af-367">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="ba1af-368">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-368">**Comments**</span></span> | <span data-ttu-id="ba1af-369">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-369">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="ba1af-370">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="ba1af-370">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="ba1af-371">Configure os recursos de proteção orientados por nuvem do Microsoft Defender para Endpoint no macOS.</span><span class="sxs-lookup"><span data-stu-id="ba1af-371">Configure the cloud-driven protection features of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="ba1af-372">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-372">Section</span></span>|<span data-ttu-id="ba1af-373">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-373">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-374">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-374">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-375">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-375">**Key**</span></span> | <span data-ttu-id="ba1af-376">cloudService</span><span class="sxs-lookup"><span data-stu-id="ba1af-376">cloudService</span></span> |
| <span data-ttu-id="ba1af-377">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-377">**Data type**</span></span> | <span data-ttu-id="ba1af-378">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-378">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-379">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-379">**Comments**</span></span> | <span data-ttu-id="ba1af-380">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-380">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="ba1af-381">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="ba1af-381">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="ba1af-382">Especifique se o dispositivo deve ser habilitado ou não para a proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="ba1af-382">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="ba1af-383">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="ba1af-383">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|<span data-ttu-id="ba1af-384">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-384">Section</span></span>|<span data-ttu-id="ba1af-385">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-385">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-386">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-386">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-387">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-387">**Key**</span></span> | <span data-ttu-id="ba1af-388">habilitadas</span><span class="sxs-lookup"><span data-stu-id="ba1af-388">enabled</span></span> |
| <span data-ttu-id="ba1af-389">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-389">**Data type**</span></span> | <span data-ttu-id="ba1af-390">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-390">Boolean</span></span> |
| <span data-ttu-id="ba1af-391">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-391">**Possible values**</span></span> | <span data-ttu-id="ba1af-392">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-392">true (default)</span></span> <br/> <span data-ttu-id="ba1af-393">falso</span><span class="sxs-lookup"><span data-stu-id="ba1af-393">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="ba1af-394">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ba1af-394">Diagnostic collection level</span></span>

<span data-ttu-id="ba1af-395">Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="ba1af-395">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="ba1af-396">Essa configuração determina o nível de diagnóstico enviado pelo Microsoft Defender para o Ponto de Extremidade para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba1af-396">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|<span data-ttu-id="ba1af-397">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-397">Section</span></span>|<span data-ttu-id="ba1af-398">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-398">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-399">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-399">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-400">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-400">**Key**</span></span> | <span data-ttu-id="ba1af-401">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="ba1af-401">diagnosticLevel</span></span> |
| <span data-ttu-id="ba1af-402">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-402">**Data type**</span></span> | <span data-ttu-id="ba1af-403">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-403">String</span></span> |
| <span data-ttu-id="ba1af-404">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-404">**Possible values**</span></span> | <span data-ttu-id="ba1af-405">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-405">optional (default)</span></span> <br/> <span data-ttu-id="ba1af-406">obrigatório</span><span class="sxs-lookup"><span data-stu-id="ba1af-406">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="ba1af-407">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="ba1af-407">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="ba1af-408">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba1af-408">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="ba1af-409">Você será solicitado se o arquivo enviado provavelmente conter informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="ba1af-409">You are prompted if the submitted file is likely to contain personal information.</span></span>

|<span data-ttu-id="ba1af-410">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-410">Section</span></span>|<span data-ttu-id="ba1af-411">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-411">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-412">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-412">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-413">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-413">**Key**</span></span> | <span data-ttu-id="ba1af-414">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="ba1af-414">automaticSampleSubmission</span></span> |
| <span data-ttu-id="ba1af-415">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-415">**Data type**</span></span> | <span data-ttu-id="ba1af-416">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-416">Boolean</span></span> |
| <span data-ttu-id="ba1af-417">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-417">**Possible values**</span></span> | <span data-ttu-id="ba1af-418">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-418">true (default)</span></span> <br/> <span data-ttu-id="ba1af-419">falso</span><span class="sxs-lookup"><span data-stu-id="ba1af-419">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="ba1af-420">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="ba1af-420">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="ba1af-421">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="ba1af-421">Determines whether security intelligence updates are installed automatically:</span></span>

|<span data-ttu-id="ba1af-422">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-422">Section</span></span>|<span data-ttu-id="ba1af-423">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-423">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-424">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-424">**Key**</span></span> | <span data-ttu-id="ba1af-425">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="ba1af-425">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="ba1af-426">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-426">**Data type**</span></span> | <span data-ttu-id="ba1af-427">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-427">Boolean</span></span> |
| <span data-ttu-id="ba1af-428">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-428">**Possible values**</span></span> | <span data-ttu-id="ba1af-429">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-429">true (default)</span></span> <br/> <span data-ttu-id="ba1af-430">falso</span><span class="sxs-lookup"><span data-stu-id="ba1af-430">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="ba1af-431">Preferências de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="ba1af-431">User interface preferences</span></span>

<span data-ttu-id="ba1af-432">Gerencie as preferências para a interface do usuário do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="ba1af-432">Manage the preferences for the user interface of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="ba1af-433">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-433">Section</span></span>|<span data-ttu-id="ba1af-434">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-434">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-435">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-435">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-436">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-436">**Key**</span></span> | <span data-ttu-id="ba1af-437">userInterface</span><span class="sxs-lookup"><span data-stu-id="ba1af-437">userInterface</span></span> |
| <span data-ttu-id="ba1af-438">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-438">**Data type**</span></span> | <span data-ttu-id="ba1af-439">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-439">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-440">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-440">**Comments**</span></span> | <span data-ttu-id="ba1af-441">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-441">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="ba1af-442">Mostrar/ocultar ícone de menu de status</span><span class="sxs-lookup"><span data-stu-id="ba1af-442">Show / hide status menu icon</span></span>

<span data-ttu-id="ba1af-443">Especifique se deve mostrar ou ocultar o ícone do menu de status no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="ba1af-443">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|<span data-ttu-id="ba1af-444">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-444">Section</span></span>|<span data-ttu-id="ba1af-445">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-445">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-446">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-447">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-447">**Key**</span></span> | <span data-ttu-id="ba1af-448">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="ba1af-448">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="ba1af-449">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-449">**Data type**</span></span> | <span data-ttu-id="ba1af-450">Booliano</span><span class="sxs-lookup"><span data-stu-id="ba1af-450">Boolean</span></span> |
| <span data-ttu-id="ba1af-451">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-451">**Possible values**</span></span> | <span data-ttu-id="ba1af-452">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-452">false (default)</span></span> <br/> <span data-ttu-id="ba1af-453">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="ba1af-453">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="ba1af-454">Mostrar/ocultar opção para enviar comentários</span><span class="sxs-lookup"><span data-stu-id="ba1af-454">Show / hide option to send feedback</span></span>

<span data-ttu-id="ba1af-455">Especifique se os usuários podem enviar comentários para a Microsoft indo para `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="ba1af-455">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|<span data-ttu-id="ba1af-456">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-456">Section</span></span>|<span data-ttu-id="ba1af-457">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-457">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-458">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-458">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-459">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-459">**Key**</span></span> | <span data-ttu-id="ba1af-460">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="ba1af-460">userInitiatedFeedback</span></span> |
| <span data-ttu-id="ba1af-461">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-461">**Data type**</span></span> | <span data-ttu-id="ba1af-462">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-462">String</span></span> |
| <span data-ttu-id="ba1af-463">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-463">**Possible values**</span></span> | <span data-ttu-id="ba1af-464">habilitado (padrão)</span><span class="sxs-lookup"><span data-stu-id="ba1af-464">enabled (default)</span></span> <br/> <span data-ttu-id="ba1af-465">desabilitadas</span><span class="sxs-lookup"><span data-stu-id="ba1af-465">disabled</span></span> |
| <span data-ttu-id="ba1af-466">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-466">**Comments**</span></span> | <span data-ttu-id="ba1af-467">Disponível no Microsoft Defender para Endpoint versão 101.19.61 ou superior.</span><span class="sxs-lookup"><span data-stu-id="ba1af-467">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="ba1af-468">Preferências de detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="ba1af-468">Endpoint detection and response preferences</span></span>

<span data-ttu-id="ba1af-469">Gerencie as preferências do componente de detecção e resposta do ponto de extremidade (EDR) do Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="ba1af-469">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint on macOS.</span></span>

|<span data-ttu-id="ba1af-470">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-470">Section</span></span>|<span data-ttu-id="ba1af-471">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-471">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-472">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-472">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-473">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-473">**Key**</span></span> | <span data-ttu-id="ba1af-474">edr</span><span class="sxs-lookup"><span data-stu-id="ba1af-474">edr</span></span> |
| <span data-ttu-id="ba1af-475">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-475">**Data type**</span></span> | <span data-ttu-id="ba1af-476">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-476">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-477">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-477">**Comments**</span></span> | <span data-ttu-id="ba1af-478">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-478">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="ba1af-479">Marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba1af-479">Device tags</span></span>

<span data-ttu-id="ba1af-480">Especifique um nome de marca e seu valor.</span><span class="sxs-lookup"><span data-stu-id="ba1af-480">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="ba1af-481">A marca GROUP marca o dispositivo com o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="ba1af-481">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="ba1af-482">A marca é refletida no portal sob a página do dispositivo e pode ser usada para filtrar e agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba1af-482">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|<span data-ttu-id="ba1af-483">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-483">Section</span></span>|<span data-ttu-id="ba1af-484">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-484">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-485">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-485">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-486">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-486">**Key**</span></span> | <span data-ttu-id="ba1af-487">tags</span><span class="sxs-lookup"><span data-stu-id="ba1af-487">tags</span></span> |
| <span data-ttu-id="ba1af-488">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-488">**Data type**</span></span> | <span data-ttu-id="ba1af-489">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="ba1af-489">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ba1af-490">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="ba1af-490">**Comments**</span></span> | <span data-ttu-id="ba1af-491">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="ba1af-491">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="ba1af-492">Tipo de marca</span><span class="sxs-lookup"><span data-stu-id="ba1af-492">Type of tag</span></span>

<span data-ttu-id="ba1af-493">Especifica o tipo de marca</span><span class="sxs-lookup"><span data-stu-id="ba1af-493">Specifies the type of tag</span></span>

|<span data-ttu-id="ba1af-494">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-494">Section</span></span>|<span data-ttu-id="ba1af-495">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-495">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-496">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-496">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-497">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-497">**Key**</span></span> | <span data-ttu-id="ba1af-498">chave</span><span class="sxs-lookup"><span data-stu-id="ba1af-498">key</span></span> |
| <span data-ttu-id="ba1af-499">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-499">**Data type**</span></span> | <span data-ttu-id="ba1af-500">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-500">String</span></span> |
| <span data-ttu-id="ba1af-501">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-501">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="ba1af-502">Valor da marca</span><span class="sxs-lookup"><span data-stu-id="ba1af-502">Value of tag</span></span>

<span data-ttu-id="ba1af-503">Especifica o valor da marca</span><span class="sxs-lookup"><span data-stu-id="ba1af-503">Specifies the value of tag</span></span>

|<span data-ttu-id="ba1af-504">Section</span><span class="sxs-lookup"><span data-stu-id="ba1af-504">Section</span></span>|<span data-ttu-id="ba1af-505">Valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-505">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ba1af-506">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="ba1af-506">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ba1af-507">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="ba1af-507">**Key**</span></span> | <span data-ttu-id="ba1af-508">valor</span><span class="sxs-lookup"><span data-stu-id="ba1af-508">value</span></span> |
| <span data-ttu-id="ba1af-509">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ba1af-509">**Data type**</span></span> | <span data-ttu-id="ba1af-510">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-510">String</span></span> |
| <span data-ttu-id="ba1af-511">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="ba1af-511">**Possible values**</span></span> | <span data-ttu-id="ba1af-512">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="ba1af-512">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="ba1af-513">Somente um valor por tipo de marca pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="ba1af-513">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="ba1af-514">O tipo de marcas é exclusivo e não deve ser repetido no mesmo perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="ba1af-514">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="ba1af-515">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="ba1af-515">Recommended configuration profile</span></span>

<span data-ttu-id="ba1af-516">Para começar, recomendamos que a configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Microsoft Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="ba1af-516">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="ba1af-517">O perfil de configuração a seguir (ou, no caso de JAMF, uma lista de propriedades que poderia ser carregada no perfil de configuração de configurações personalizadas) será:</span><span class="sxs-lookup"><span data-stu-id="ba1af-517">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="ba1af-518">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="ba1af-518">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="ba1af-519">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="ba1af-519">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="ba1af-520">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="ba1af-520">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="ba1af-521">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para logs do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="ba1af-521">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="ba1af-522">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="ba1af-522">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="ba1af-523">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="ba1af-523">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="ba1af-524">Habilitar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="ba1af-524">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ba1af-525">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="ba1af-525">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ba1af-526">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="ba1af-526">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="ba1af-527">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="ba1af-527">Full configuration profile example</span></span>

<span data-ttu-id="ba1af-528">Os modelos a seguir contêm entradas para todas as configurações descritas neste documento e podem ser usadas para cenários mais avançados em que você deseja mais controle sobre o Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="ba1af-528">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="ba1af-529">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="ba1af-529">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="ba1af-530">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="ba1af-530">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="ba1af-531">Validação de lista de propriedades</span><span class="sxs-lookup"><span data-stu-id="ba1af-531">Property list validation</span></span>

<span data-ttu-id="ba1af-532">A lista de propriedades deve ser um arquivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="ba1af-532">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="ba1af-533">Isso pode ser verificado executando:</span><span class="sxs-lookup"><span data-stu-id="ba1af-533">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="ba1af-534">Se o arquivo for bem formado, o comando acima sairá e retornará um código `OK` de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="ba1af-534">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="ba1af-535">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="ba1af-535">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="ba1af-536">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="ba1af-536">Configuration profile deployment</span></span>

<span data-ttu-id="ba1af-537">Depois de construir o perfil de configuração da sua empresa, você pode implantá-lo por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="ba1af-537">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="ba1af-538">As seções a seguir fornecem instruções sobre como implantar esse perfil usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="ba1af-538">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="ba1af-539">Implantação jamf</span><span class="sxs-lookup"><span data-stu-id="ba1af-539">JAMF deployment</span></span>

<span data-ttu-id="ba1af-540">No console JAMF, **abra** Perfis de Configuração de Computadores, navegue até o perfil de configuração que você gostaria de  >  usar e selecione **Configurações Personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="ba1af-540">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="ba1af-541">Crie uma entrada com `com.microsoft.wdav` como o domínio de preferência e carregue o *.plist* produzido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba1af-541">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="ba1af-542">Você deve inserir o domínio de preferência correto ( ); caso contrário, as preferências não serão reconhecidas pelo `com.microsoft.wdav` Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ba1af-542">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="ba1af-543">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="ba1af-543">Intune deployment</span></span>

1. <span data-ttu-id="ba1af-544">Abra **Gerenciar**  >  **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-544">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="ba1af-545">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-545">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="ba1af-546">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="ba1af-546">Choose a name for the profile.</span></span> <span data-ttu-id="ba1af-547">Alterar **Platform=macOS** para **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-547">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="ba1af-548">Selecione Configurar.</span><span class="sxs-lookup"><span data-stu-id="ba1af-548">Select Configure.</span></span>

3. <span data-ttu-id="ba1af-549">Salve o .plist produzido anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="ba1af-549">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="ba1af-550">Insira `com.microsoft.wdav` como o nome do perfil de **configuração personalizado**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-550">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="ba1af-551">Abra o perfil de configuração e carregue o `com.microsoft.wdav.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="ba1af-551">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="ba1af-552">(Esse arquivo foi criado na etapa 3.)</span><span class="sxs-lookup"><span data-stu-id="ba1af-552">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="ba1af-553">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-553">Select **OK**.</span></span>

7. <span data-ttu-id="ba1af-554">Selecione **Gerenciar**  >  **atribuições**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-554">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="ba1af-555">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ba1af-555">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="ba1af-556">Você deve inserir o nome de perfil de configuração personalizado correto; caso contrário, essas preferências não serão reconhecidas pelo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="ba1af-556">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="ba1af-557">Recursos</span><span class="sxs-lookup"><span data-stu-id="ba1af-557">Resources</span></span>

- [<span data-ttu-id="ba1af-558">Referência do Perfil de Configuração (Documentação do desenvolvedor da Apple)</span><span class="sxs-lookup"><span data-stu-id="ba1af-558">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
