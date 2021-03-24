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
ms.openlocfilehash: 578830d44a9a69c3ccafd78ceaf59ddfe100e43f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054568"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="92772-104">Definir preferências do Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="92772-104">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="92772-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="92772-105">**Applies to:**</span></span>

- [<span data-ttu-id="92772-106">Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="92772-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
><span data-ttu-id="92772-107">Este artigo contém instruções sobre como definir preferências do Microsoft Defender para Ponto de Extremidade para Mac em organizações corporativas.</span><span class="sxs-lookup"><span data-stu-id="92772-107">This article contains instructions for how to set preferences for Microsoft Defender for Endpoint for Mac in enterprise organizations.</span></span> <span data-ttu-id="92772-108">Para configurar o Microsoft Defender para Ponto de Extremidade para Mac usando a interface de linha de comando, [consulte Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="92772-108">To configure Microsoft Defender for Endpoint for Mac using the command-line interface, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

## <a name="summary"></a><span data-ttu-id="92772-109">Resumo</span><span class="sxs-lookup"><span data-stu-id="92772-109">Summary</span></span>

<span data-ttu-id="92772-110">Nas organizações empresariais, o Microsoft Defender para Ponto de Extremidade para Mac pode ser gerenciado por meio de um perfil de configuração implantado usando uma das várias ferramentas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="92772-110">In enterprise organizations, Microsoft Defender for Endpoint for Mac can be managed through a configuration profile that is deployed by using one of several management tools.</span></span> <span data-ttu-id="92772-111">As preferências gerenciadas pela equipe de operações de segurança têm precedência sobre as preferências definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92772-111">Preferences that are managed by your security operations team take precedence over preferences that are set locally on the device.</span></span> <span data-ttu-id="92772-112">Alterar as preferências definidas por meio do perfil de configuração exige privilégios escalonados e não está disponível para usuários sem permissões administrativas.</span><span class="sxs-lookup"><span data-stu-id="92772-112">Changing the preferences that are set through the configuration profile requires escalated privileges and is not available for users without administrative permissions.</span></span>

<span data-ttu-id="92772-113">Este artigo descreve a estrutura do perfil de configuração, inclui um perfil recomendado que você pode usar para começar e fornece instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="92772-113">This article describes the structure of the configuration profile, includes a recommended profile that you can use to get started, and provides instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="92772-114">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="92772-114">Configuration profile structure</span></span>

<span data-ttu-id="92772-115">O perfil de configuração é um *arquivo .plist* que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="92772-115">The configuration profile is a *.plist* file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="92772-116">Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="92772-116">Values can either be simple (such as a numerical value) or complex, such as a nested list of preferences.</span></span>

>[!CAUTION]
><span data-ttu-id="92772-117">O layout do perfil de configuração depende do console de gerenciamento que você está usando.</span><span class="sxs-lookup"><span data-stu-id="92772-117">The layout of the configuration profile depends on the management console that you are using.</span></span> <span data-ttu-id="92772-118">As seções a seguir contêm exemplos de perfis de configuração para JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="92772-118">The following sections contain examples of configuration profiles for JAMF and Intune.</span></span>

<span data-ttu-id="92772-119">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do Microsoft Defender para Ponto de Extremidade, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="92772-119">The top level of the configuration profile includes product-wide preferences and entries for subareas of Microsoft Defender for Endpoint, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="92772-120">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="92772-120">Antivirus engine preferences</span></span>

<span data-ttu-id="92772-121">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="92772-121">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of Microsoft Defender for Endpoint.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-122">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-123">**Key**</span></span> | <span data-ttu-id="92772-124">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="92772-124">antivirusEngine</span></span> |
| <span data-ttu-id="92772-125">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-125">**Data type**</span></span> | <span data-ttu-id="92772-126">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-127">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-127">**Comments**</span></span> | <span data-ttu-id="92772-128">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-128">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="92772-129">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="92772-129">Enable / disable real-time protection</span></span>

<span data-ttu-id="92772-130">Especifique se é necessário habilitar a proteção em tempo real, que verifica os arquivos conforme eles são acessados.</span><span class="sxs-lookup"><span data-stu-id="92772-130">Specify whether to enable real-time protection, which scans files as they are accessed.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-131">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-132">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-132">**Key**</span></span> | <span data-ttu-id="92772-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="92772-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="92772-134">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-134">**Data type**</span></span> | <span data-ttu-id="92772-135">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-135">Boolean</span></span> |
| <span data-ttu-id="92772-136">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-136">**Possible values**</span></span> | <span data-ttu-id="92772-137">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-137">true (default)</span></span> <br/> <span data-ttu-id="92772-138">falso</span><span class="sxs-lookup"><span data-stu-id="92772-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="92772-139">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="92772-139">Enable / disable passive mode</span></span>

<span data-ttu-id="92772-140">Especifique se o mecanismo antivírus é executado no modo passivo.</span><span class="sxs-lookup"><span data-stu-id="92772-140">Specify whether the antivirus engine runs in passive mode.</span></span> <span data-ttu-id="92772-141">O modo passivo tem as seguintes implicações:</span><span class="sxs-lookup"><span data-stu-id="92772-141">Passive mode has the following implications:</span></span> 
- <span data-ttu-id="92772-142">A proteção em tempo real está desligada</span><span class="sxs-lookup"><span data-stu-id="92772-142">Real-time protection is turned off</span></span>
- <span data-ttu-id="92772-143">A verificação sob demanda está 24h</span><span class="sxs-lookup"><span data-stu-id="92772-143">On-demand scanning is turned on</span></span>
- <span data-ttu-id="92772-144">A correção automática de ameaças está desligada</span><span class="sxs-lookup"><span data-stu-id="92772-144">Automatic threat remediation is turned off</span></span>
- <span data-ttu-id="92772-145">Atualizações de inteligência de segurança estão ativas</span><span class="sxs-lookup"><span data-stu-id="92772-145">Security intelligence updates are turned on</span></span>
- <span data-ttu-id="92772-146">O ícone do menu Status está oculto</span><span class="sxs-lookup"><span data-stu-id="92772-146">Status menu icon is hidden</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-147">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-147">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-148">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-148">**Key**</span></span> | <span data-ttu-id="92772-149">passiveMode</span><span class="sxs-lookup"><span data-stu-id="92772-149">passiveMode</span></span> |
| <span data-ttu-id="92772-150">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-150">**Data type**</span></span> | <span data-ttu-id="92772-151">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-151">Boolean</span></span> |
| <span data-ttu-id="92772-152">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-152">**Possible values**</span></span> | <span data-ttu-id="92772-153">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-153">false (default)</span></span> <br/> <span data-ttu-id="92772-154">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92772-154">true</span></span> |
| <span data-ttu-id="92772-155">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-155">**Comments**</span></span> | <span data-ttu-id="92772-156">Disponível no Microsoft Defender para Endpoint versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-156">Available in Microsoft Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="92772-157">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="92772-157">Exclusion merge policy</span></span>

<span data-ttu-id="92772-158">Especifique a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="92772-158">Specify the merge policy for exclusions.</span></span> <span data-ttu-id="92772-159">Isso pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="92772-159">This can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="92772-160">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="92772-160">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-161">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-161">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-162">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-162">**Key**</span></span> | <span data-ttu-id="92772-163">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="92772-163">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="92772-164">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-164">**Data type**</span></span> | <span data-ttu-id="92772-165">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-165">String</span></span> |
| <span data-ttu-id="92772-166">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-166">**Possible values**</span></span> | <span data-ttu-id="92772-167">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-167">merge (default)</span></span> <br/> <span data-ttu-id="92772-168">admin_only</span><span class="sxs-lookup"><span data-stu-id="92772-168">admin_only</span></span> |
| <span data-ttu-id="92772-169">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-169">**Comments**</span></span> | <span data-ttu-id="92772-170">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-170">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="92772-171">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="92772-171">Scan exclusions</span></span>

<span data-ttu-id="92772-172">Especifique entidades excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="92772-172">Specify entities excluded from being scanned.</span></span> <span data-ttu-id="92772-173">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="92772-173">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-174">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-174">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-175">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-175">**Key**</span></span> | <span data-ttu-id="92772-176">exclusões</span><span class="sxs-lookup"><span data-stu-id="92772-176">exclusions</span></span> |
| <span data-ttu-id="92772-177">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-177">**Data type**</span></span> | <span data-ttu-id="92772-178">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-178">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-179">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-179">**Comments**</span></span> | <span data-ttu-id="92772-180">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-180">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-exclusion"></a><span data-ttu-id="92772-181">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="92772-181">Type of exclusion</span></span>

<span data-ttu-id="92772-182">Especifique o conteúdo excluído de ser verificado por tipo.</span><span class="sxs-lookup"><span data-stu-id="92772-182">Specify content excluded from being scanned by type.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-183">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-184">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-184">**Key**</span></span> | <span data-ttu-id="92772-185">$type</span><span class="sxs-lookup"><span data-stu-id="92772-185">$type</span></span> |
| <span data-ttu-id="92772-186">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-186">**Data type**</span></span> | <span data-ttu-id="92772-187">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-187">String</span></span> |
| <span data-ttu-id="92772-188">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-188">**Possible values**</span></span> | <span data-ttu-id="92772-189">excludedPath</span><span class="sxs-lookup"><span data-stu-id="92772-189">excludedPath</span></span> <br/> <span data-ttu-id="92772-190">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="92772-190">excludedFileExtension</span></span> <br/> <span data-ttu-id="92772-191">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="92772-191">excludedFileName</span></span> |

##### <a name="path-to-excluded-content"></a><span data-ttu-id="92772-192">Caminho para conteúdo excluído</span><span class="sxs-lookup"><span data-stu-id="92772-192">Path to excluded content</span></span>

<span data-ttu-id="92772-193">Especifique o conteúdo excluído de ser verificado pelo caminho completo do arquivo.</span><span class="sxs-lookup"><span data-stu-id="92772-193">Specify content excluded from being scanned by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-194">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-194">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-195">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-195">**Key**</span></span> | <span data-ttu-id="92772-196">caminho</span><span class="sxs-lookup"><span data-stu-id="92772-196">path</span></span> |
| <span data-ttu-id="92772-197">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-197">**Data type**</span></span> | <span data-ttu-id="92772-198">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-198">String</span></span> |
| <span data-ttu-id="92772-199">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-199">**Possible values**</span></span> | <span data-ttu-id="92772-200">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="92772-200">valid paths</span></span> |
| <span data-ttu-id="92772-201">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-201">**Comments**</span></span> | <span data-ttu-id="92772-202">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="92772-202">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="path-type-file--directory"></a><span data-ttu-id="92772-203">Tipo de caminho (arquivo/diretório)</span><span class="sxs-lookup"><span data-stu-id="92772-203">Path type (file / directory)</span></span>

<span data-ttu-id="92772-204">Indique se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="92772-204">Indicate if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="92772-205">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-205">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-206">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-206">**Key**</span></span> | <span data-ttu-id="92772-207">isDirectory</span><span class="sxs-lookup"><span data-stu-id="92772-207">isDirectory</span></span> |
| <span data-ttu-id="92772-208">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-208">**Data type**</span></span> | <span data-ttu-id="92772-209">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-209">Boolean</span></span> |
| <span data-ttu-id="92772-210">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-210">**Possible values**</span></span> | <span data-ttu-id="92772-211">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-211">false (default)</span></span> <br/> <span data-ttu-id="92772-212">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92772-212">true</span></span> |
| <span data-ttu-id="92772-213">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-213">**Comments**</span></span> | <span data-ttu-id="92772-214">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="92772-214">Applicable only if *$type* is *excludedPath*</span></span> |

##### <a name="file-extension-excluded-from-the-scan"></a><span data-ttu-id="92772-215">Extensão de arquivo excluída da verificação</span><span class="sxs-lookup"><span data-stu-id="92772-215">File extension excluded from the scan</span></span>

<span data-ttu-id="92772-216">Especifique o conteúdo excluído de ser verificado por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="92772-216">Specify content excluded from being scanned by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-217">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-217">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-218">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-218">**Key**</span></span> | <span data-ttu-id="92772-219">extension</span><span class="sxs-lookup"><span data-stu-id="92772-219">extension</span></span> |
| <span data-ttu-id="92772-220">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-220">**Data type**</span></span> | <span data-ttu-id="92772-221">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-221">String</span></span> |
| <span data-ttu-id="92772-222">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-222">**Possible values**</span></span> | <span data-ttu-id="92772-223">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="92772-223">valid file extensions</span></span> |
| <span data-ttu-id="92772-224">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-224">**Comments**</span></span> | <span data-ttu-id="92772-225">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="92772-225">Applicable only if *$type* is *excludedFileExtension*</span></span> |

##### <a name="process-excluded-from-the-scan"></a><span data-ttu-id="92772-226">Processo excluído da verificação</span><span class="sxs-lookup"><span data-stu-id="92772-226">Process excluded from the scan</span></span>

<span data-ttu-id="92772-227">Especifique um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="92772-227">Specify a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="92772-228">O processo pode ser especificado pelo nome (por exemplo) ou caminho `cat` completo (por `/bin/cat` exemplo).</span><span class="sxs-lookup"><span data-stu-id="92772-228">The process can be specified either by its name (e.g. `cat`) or full path (e.g. `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-229">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-229">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-230">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-230">**Key**</span></span> | <span data-ttu-id="92772-231">nome</span><span class="sxs-lookup"><span data-stu-id="92772-231">name</span></span> |
| <span data-ttu-id="92772-232">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-232">**Data type**</span></span> | <span data-ttu-id="92772-233">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-233">String</span></span> |
| <span data-ttu-id="92772-234">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-234">**Possible values**</span></span> | <span data-ttu-id="92772-235">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-235">any string</span></span> |
| <span data-ttu-id="92772-236">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-236">**Comments**</span></span> | <span data-ttu-id="92772-237">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="92772-237">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="92772-238">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="92772-238">Allowed threats</span></span>

<span data-ttu-id="92772-239">Especifique ameaças por nome que não são bloqueadas pelo Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-239">Specify threats by name that are not blocked by Defender for Endpoint for Mac.</span></span> <span data-ttu-id="92772-240">Essas ameaças terão permissão para serem executados.</span><span class="sxs-lookup"><span data-stu-id="92772-240">These threats will be allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-241">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-241">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-242">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-242">**Key**</span></span> | <span data-ttu-id="92772-243">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="92772-243">allowedThreats</span></span> |
| <span data-ttu-id="92772-244">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-244">**Data type**</span></span> | <span data-ttu-id="92772-245">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-245">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="92772-246">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="92772-246">Disallowed threat actions</span></span>

<span data-ttu-id="92772-247">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="92772-247">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="92772-248">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="92772-248">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-249">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-249">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-250">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-250">**Key**</span></span> | <span data-ttu-id="92772-251">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="92772-251">disallowedThreatActions</span></span> |
| <span data-ttu-id="92772-252">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-252">**Data type**</span></span> | <span data-ttu-id="92772-253">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-253">Array of strings</span></span> |
| <span data-ttu-id="92772-254">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-254">**Possible values**</span></span> | <span data-ttu-id="92772-255">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="92772-255">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="92772-256">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="92772-256">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="92772-257">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-257">**Comments**</span></span> | <span data-ttu-id="92772-258">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-258">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="92772-259">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="92772-259">Threat type settings</span></span>

<span data-ttu-id="92772-260">Especifique como determinados tipos de ameaça são manipulados pelo Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-260">Specify how certain threat types are handled by Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-261">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-261">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-262">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-262">**Key**</span></span> | <span data-ttu-id="92772-263">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="92772-263">threatTypeSettings</span></span> |
| <span data-ttu-id="92772-264">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-264">**Data type**</span></span> | <span data-ttu-id="92772-265">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-265">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-266">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-266">**Comments**</span></span> | <span data-ttu-id="92772-267">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-267">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="threat-type"></a><span data-ttu-id="92772-268">Tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="92772-268">Threat type</span></span>

<span data-ttu-id="92772-269">Especifique tipos de ameaça.</span><span class="sxs-lookup"><span data-stu-id="92772-269">Specify threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-270">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-270">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-271">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-271">**Key**</span></span> | <span data-ttu-id="92772-272">chave</span><span class="sxs-lookup"><span data-stu-id="92772-272">key</span></span> |
| <span data-ttu-id="92772-273">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-273">**Data type**</span></span> | <span data-ttu-id="92772-274">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-274">String</span></span> |
| <span data-ttu-id="92772-275">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-275">**Possible values**</span></span> | <span data-ttu-id="92772-276">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="92772-276">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="92772-277">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="92772-277">archive_bomb</span></span> |

##### <a name="action-to-take"></a><span data-ttu-id="92772-278">O que fazer</span><span class="sxs-lookup"><span data-stu-id="92772-278">Action to take</span></span>

<span data-ttu-id="92772-279">Especifique qual ação tomar quando uma ameaça do tipo especificado na seção anterior for detectada.</span><span class="sxs-lookup"><span data-stu-id="92772-279">Specify what action to take when a threat of the type specified in the preceding section is detected.</span></span> <span data-ttu-id="92772-280">Escolha entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="92772-280">Choose from the following options:</span></span>

- <span data-ttu-id="92772-281">**Auditoria**: seu dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="92772-281">**Audit**: your device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="92772-282">**Bloquear**: seu dispositivo é protegido contra esse tipo de ameaça e você é notificado na interface do usuário e no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="92772-282">**Block**: your device is protected against this type of threat and you are notified in the user interface and the security console.</span></span>
- <span data-ttu-id="92772-283">**Off**: seu dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="92772-283">**Off**: your device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-284">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-284">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-285">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-285">**Key**</span></span> | <span data-ttu-id="92772-286">valor</span><span class="sxs-lookup"><span data-stu-id="92772-286">value</span></span> |
| <span data-ttu-id="92772-287">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-287">**Data type**</span></span> | <span data-ttu-id="92772-288">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-288">String</span></span> |
| <span data-ttu-id="92772-289">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-289">**Possible values**</span></span> | <span data-ttu-id="92772-290">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-290">audit (default)</span></span> <br/> <span data-ttu-id="92772-291">block</span><span class="sxs-lookup"><span data-stu-id="92772-291">block</span></span> <br/> <span data-ttu-id="92772-292">off</span><span class="sxs-lookup"><span data-stu-id="92772-292">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="92772-293">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="92772-293">Threat type settings merge policy</span></span>

<span data-ttu-id="92772-294">Especifique a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="92772-294">Specify the merge policy for threat type settings.</span></span> <span data-ttu-id="92772-295">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="92772-295">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="92772-296">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="92772-296">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-297">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-297">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-298">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-298">**Key**</span></span> | <span data-ttu-id="92772-299">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="92772-299">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="92772-300">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-300">**Data type**</span></span> | <span data-ttu-id="92772-301">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-301">String</span></span> |
| <span data-ttu-id="92772-302">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-302">**Possible values**</span></span> | <span data-ttu-id="92772-303">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-303">merge (default)</span></span> <br/> <span data-ttu-id="92772-304">admin_only</span><span class="sxs-lookup"><span data-stu-id="92772-304">admin_only</span></span> |
| <span data-ttu-id="92772-305">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-305">**Comments**</span></span> | <span data-ttu-id="92772-306">Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-306">Available in Microsoft Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="92772-307">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="92772-307">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="92772-308">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92772-308">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="92772-309">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="92772-309">Old scan results are removed from the history.</span></span> <span data-ttu-id="92772-310">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="92772-310">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-311">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-311">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-312">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-312">**Key**</span></span> | <span data-ttu-id="92772-313">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="92772-313">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="92772-314">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-314">**Data type**</span></span> | <span data-ttu-id="92772-315">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-315">String</span></span> |
| <span data-ttu-id="92772-316">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-316">**Possible values**</span></span> | <span data-ttu-id="92772-317">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="92772-317">90 (default).</span></span> <span data-ttu-id="92772-318">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="92772-318">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="92772-319">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-319">**Comments**</span></span> | <span data-ttu-id="92772-320">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-320">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="92772-321">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="92772-321">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="92772-322">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="92772-322">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="92772-323">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="92772-323">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-324">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-324">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-325">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-325">**Key**</span></span> | <span data-ttu-id="92772-326">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="92772-326">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="92772-327">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-327">**Data type**</span></span> | <span data-ttu-id="92772-328">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-328">String</span></span> |
| <span data-ttu-id="92772-329">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-329">**Possible values**</span></span> | <span data-ttu-id="92772-330">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="92772-330">10000 (default).</span></span> <span data-ttu-id="92772-331">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="92772-331">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="92772-332">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-332">**Comments**</span></span> | <span data-ttu-id="92772-333">Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-333">Available in Microsoft Defender for Endpoint version 101.07.23 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="92772-334">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="92772-334">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="92772-335">Configure os recursos de proteção orientados por nuvem do Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-335">Configure the cloud-driven protection features of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-336">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-336">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-337">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-337">**Key**</span></span> | <span data-ttu-id="92772-338">cloudService</span><span class="sxs-lookup"><span data-stu-id="92772-338">cloudService</span></span> |
| <span data-ttu-id="92772-339">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-339">**Data type**</span></span> | <span data-ttu-id="92772-340">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-340">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-341">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-341">**Comments**</span></span> | <span data-ttu-id="92772-342">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-342">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="92772-343">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="92772-343">Enable / disable cloud-delivered protection</span></span>

<span data-ttu-id="92772-344">Especifique se o dispositivo deve ser habilitado ou não para a proteção entregue na nuvem.</span><span class="sxs-lookup"><span data-stu-id="92772-344">Specify whether to enable cloud-delivered protection the device or not.</span></span> <span data-ttu-id="92772-345">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="92772-345">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-346">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-346">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-347">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-347">**Key**</span></span> | <span data-ttu-id="92772-348">habilitadas</span><span class="sxs-lookup"><span data-stu-id="92772-348">enabled</span></span> |
| <span data-ttu-id="92772-349">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-349">**Data type**</span></span> | <span data-ttu-id="92772-350">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-350">Boolean</span></span> |
| <span data-ttu-id="92772-351">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-351">**Possible values**</span></span> | <span data-ttu-id="92772-352">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-352">true (default)</span></span> <br/> <span data-ttu-id="92772-353">falso</span><span class="sxs-lookup"><span data-stu-id="92772-353">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="92772-354">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="92772-354">Diagnostic collection level</span></span>

<span data-ttu-id="92772-355">Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="92772-355">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="92772-356">Essa configuração determina o nível de diagnóstico enviado pelo Microsoft Defender para o Ponto de Extremidade para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92772-356">This setting determines the level of diagnostics sent by Microsoft Defender for Endpoint to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-357">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-357">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-358">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-358">**Key**</span></span> | <span data-ttu-id="92772-359">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="92772-359">diagnosticLevel</span></span> |
| <span data-ttu-id="92772-360">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-360">**Data type**</span></span> | <span data-ttu-id="92772-361">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-361">String</span></span> |
| <span data-ttu-id="92772-362">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-362">**Possible values**</span></span> | <span data-ttu-id="92772-363">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-363">optional (default)</span></span> <br/> <span data-ttu-id="92772-364">obrigatório</span><span class="sxs-lookup"><span data-stu-id="92772-364">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="92772-365">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="92772-365">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="92772-366">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="92772-366">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="92772-367">Você será solicitado se o arquivo enviado provavelmente conter informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="92772-367">You are prompted if the submitted file is likely to contain personal information.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-368">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-368">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-369">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-369">**Key**</span></span> | <span data-ttu-id="92772-370">automaticSampleSubmission</span><span class="sxs-lookup"><span data-stu-id="92772-370">automaticSampleSubmission</span></span> |
| <span data-ttu-id="92772-371">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-371">**Data type**</span></span> | <span data-ttu-id="92772-372">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-372">Boolean</span></span> |
| <span data-ttu-id="92772-373">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-373">**Possible values**</span></span> | <span data-ttu-id="92772-374">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-374">true (default)</span></span> <br/> <span data-ttu-id="92772-375">falso</span><span class="sxs-lookup"><span data-stu-id="92772-375">false</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="92772-376">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="92772-376">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="92772-377">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="92772-377">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-378">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-378">**Key**</span></span> | <span data-ttu-id="92772-379">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="92772-379">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="92772-380">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-380">**Data type**</span></span> | <span data-ttu-id="92772-381">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-381">Boolean</span></span> |
| <span data-ttu-id="92772-382">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-382">**Possible values**</span></span> | <span data-ttu-id="92772-383">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-383">true (default)</span></span> <br/> <span data-ttu-id="92772-384">falso</span><span class="sxs-lookup"><span data-stu-id="92772-384">false</span></span> |

### <a name="user-interface-preferences"></a><span data-ttu-id="92772-385">Preferências de interface do usuário</span><span class="sxs-lookup"><span data-stu-id="92772-385">User interface preferences</span></span>

<span data-ttu-id="92772-386">Gerencie as preferências para a interface do usuário do Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-386">Manage the preferences for the user interface of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-387">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-387">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-388">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-388">**Key**</span></span> | <span data-ttu-id="92772-389">userInterface</span><span class="sxs-lookup"><span data-stu-id="92772-389">userInterface</span></span> |
| <span data-ttu-id="92772-390">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-390">**Data type**</span></span> | <span data-ttu-id="92772-391">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-391">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-392">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-392">**Comments**</span></span> | <span data-ttu-id="92772-393">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-393">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="show--hide-status-menu-icon"></a><span data-ttu-id="92772-394">Mostrar/ocultar ícone de menu de status</span><span class="sxs-lookup"><span data-stu-id="92772-394">Show / hide status menu icon</span></span>

<span data-ttu-id="92772-395">Especifique se deve mostrar ou ocultar o ícone do menu de status no canto superior direito da tela.</span><span class="sxs-lookup"><span data-stu-id="92772-395">Specify whether to show or hide the status menu icon in the top-right corner of the screen.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-396">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-396">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-397">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-397">**Key**</span></span> | <span data-ttu-id="92772-398">hideStatusMenuIcon</span><span class="sxs-lookup"><span data-stu-id="92772-398">hideStatusMenuIcon</span></span> |
| <span data-ttu-id="92772-399">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-399">**Data type**</span></span> | <span data-ttu-id="92772-400">Booliano</span><span class="sxs-lookup"><span data-stu-id="92772-400">Boolean</span></span> |
| <span data-ttu-id="92772-401">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-401">**Possible values**</span></span> | <span data-ttu-id="92772-402">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-402">false (default)</span></span> <br/> <span data-ttu-id="92772-403">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="92772-403">true</span></span> |

#### <a name="show--hide-option-to-send-feedback"></a><span data-ttu-id="92772-404">Mostrar/ocultar opção para enviar comentários</span><span class="sxs-lookup"><span data-stu-id="92772-404">Show / hide option to send feedback</span></span>

<span data-ttu-id="92772-405">Especifique se os usuários podem enviar comentários para a Microsoft indo para `Help`  >  `Send Feedback` .</span><span class="sxs-lookup"><span data-stu-id="92772-405">Specify whether users can submit feedback to Microsoft by going to `Help` > `Send Feedback`.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-406">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-406">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-407">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-407">**Key**</span></span> | <span data-ttu-id="92772-408">userInitiatedFeedback</span><span class="sxs-lookup"><span data-stu-id="92772-408">userInitiatedFeedback</span></span> |
| <span data-ttu-id="92772-409">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-409">**Data type**</span></span> | <span data-ttu-id="92772-410">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-410">String</span></span> |
| <span data-ttu-id="92772-411">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-411">**Possible values**</span></span> | <span data-ttu-id="92772-412">habilitado (padrão)</span><span class="sxs-lookup"><span data-stu-id="92772-412">enabled (default)</span></span> <br/> <span data-ttu-id="92772-413">desabilitadas</span><span class="sxs-lookup"><span data-stu-id="92772-413">disabled</span></span> |
| <span data-ttu-id="92772-414">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-414">**Comments**</span></span> | <span data-ttu-id="92772-415">Disponível no Microsoft Defender para Endpoint versão 101.19.61 ou superior.</span><span class="sxs-lookup"><span data-stu-id="92772-415">Available in Microsoft Defender for Endpoint version 101.19.61 or higher.</span></span> |

### <a name="endpoint-detection-and-response-preferences"></a><span data-ttu-id="92772-416">Preferências de detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="92772-416">Endpoint detection and response preferences</span></span>

<span data-ttu-id="92772-417">Gerencie as preferências do componente de detecção e resposta do ponto de extremidade (EDR) do Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-417">Manage the preferences of the endpoint detection and response (EDR) component of Microsoft Defender for Endpoint for Mac.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-418">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-418">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-419">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-419">**Key**</span></span> | <span data-ttu-id="92772-420">edr</span><span class="sxs-lookup"><span data-stu-id="92772-420">edr</span></span> |
| <span data-ttu-id="92772-421">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-421">**Data type**</span></span> | <span data-ttu-id="92772-422">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-422">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-423">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-423">**Comments**</span></span> | <span data-ttu-id="92772-424">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-424">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="device-tags"></a><span data-ttu-id="92772-425">Marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="92772-425">Device tags</span></span>

<span data-ttu-id="92772-426">Especifique um nome de marca e seu valor.</span><span class="sxs-lookup"><span data-stu-id="92772-426">Specify a tag name and its value.</span></span> 

- <span data-ttu-id="92772-427">A marca GROUP marca o dispositivo com o valor especificado.</span><span class="sxs-lookup"><span data-stu-id="92772-427">The GROUP tag, tags the device with the specified value.</span></span> <span data-ttu-id="92772-428">A marca é refletida no portal sob a página do dispositivo e pode ser usada para filtrar e agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="92772-428">The tag is reflected in the portal under the device page and can be used for filtering and grouping devices.</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-429">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-429">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-430">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-430">**Key**</span></span> | <span data-ttu-id="92772-431">tags</span><span class="sxs-lookup"><span data-stu-id="92772-431">tags</span></span> |
| <span data-ttu-id="92772-432">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-432">**Data type**</span></span> | <span data-ttu-id="92772-433">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="92772-433">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="92772-434">**Comments**</span><span class="sxs-lookup"><span data-stu-id="92772-434">**Comments**</span></span> | <span data-ttu-id="92772-435">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="92772-435">See the following sections for a description of the dictionary contents.</span></span> |

##### <a name="type-of-tag"></a><span data-ttu-id="92772-436">Tipo de marca</span><span class="sxs-lookup"><span data-stu-id="92772-436">Type of tag</span></span>

<span data-ttu-id="92772-437">Especifica o tipo de marca</span><span class="sxs-lookup"><span data-stu-id="92772-437">Specifies the type of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-438">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-438">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-439">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-439">**Key**</span></span> | <span data-ttu-id="92772-440">chave</span><span class="sxs-lookup"><span data-stu-id="92772-440">key</span></span> |
| <span data-ttu-id="92772-441">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-441">**Data type**</span></span> | <span data-ttu-id="92772-442">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-442">String</span></span> |
| <span data-ttu-id="92772-443">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-443">**Possible values**</span></span> | `GROUP` |

##### <a name="value-of-tag"></a><span data-ttu-id="92772-444">Valor da marca</span><span class="sxs-lookup"><span data-stu-id="92772-444">Value of tag</span></span>

<span data-ttu-id="92772-445">Especifica o valor da marca</span><span class="sxs-lookup"><span data-stu-id="92772-445">Specifies the value of tag</span></span>

|||
|:---|:---|
| <span data-ttu-id="92772-446">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="92772-446">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="92772-447">**Chave**</span><span class="sxs-lookup"><span data-stu-id="92772-447">**Key**</span></span> | <span data-ttu-id="92772-448">valor</span><span class="sxs-lookup"><span data-stu-id="92772-448">value</span></span> |
| <span data-ttu-id="92772-449">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="92772-449">**Data type**</span></span> | <span data-ttu-id="92772-450">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-450">String</span></span> |
| <span data-ttu-id="92772-451">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="92772-451">**Possible values**</span></span> | <span data-ttu-id="92772-452">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92772-452">any string</span></span> |

> [!IMPORTANT]  
> - <span data-ttu-id="92772-453">Somente um valor por tipo de marca pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="92772-453">Only one value per tag type can be set.</span></span>
> - <span data-ttu-id="92772-454">O tipo de marcas é exclusivo e não deve ser repetido no mesmo perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="92772-454">Type of tags are unique, and should not be repeated in the same configuration profile.</span></span>

## <a name="recommended-configuration-profile"></a><span data-ttu-id="92772-455">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="92772-455">Recommended configuration profile</span></span>

<span data-ttu-id="92772-456">Para começar, recomendamos que a configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Microsoft Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="92772-456">To get started, we recommend the following configuration for your enterprise to take advantage of all protection features that Microsoft Defender for Endpoint provides.</span></span>

<span data-ttu-id="92772-457">O perfil de configuração a seguir (ou, no caso de JAMF, uma lista de propriedades que poderia ser carregada no perfil de configuração de configurações personalizadas) será:</span><span class="sxs-lookup"><span data-stu-id="92772-457">The following configuration profile (or, in case of JAMF, a property list that could be uploaded into the custom settings configuration profile) will:</span></span>
- <span data-ttu-id="92772-458">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="92772-458">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="92772-459">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="92772-459">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="92772-460">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="92772-460">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="92772-461">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para logs do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="92772-461">**Archive bombs** (file with a high compression rate) are audited to Microsoft Defender for Endpoint logs</span></span>
- <span data-ttu-id="92772-462">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="92772-462">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="92772-463">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="92772-463">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="92772-464">Habilitar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="92772-464">Enable automatic sample submission</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="92772-465">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="92772-465">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="92772-466">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="92772-466">Intune profile</span></span>

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

## <a name="full-configuration-profile-example"></a><span data-ttu-id="92772-467">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="92772-467">Full configuration profile example</span></span>

<span data-ttu-id="92772-468">Os modelos a seguir contêm entradas para todas as configurações descritas neste documento e podem ser usadas para cenários mais avançados em que você deseja mais controle sobre o Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="92772-468">The following templates contain entries for all settings described in this document and can be used for more advanced scenarios where you want more control over Microsoft Defender for Endpoint for Mac.</span></span>

### <a name="property-list-for-jamf-configuration-profile"></a><span data-ttu-id="92772-469">Lista de propriedades para perfil de configuração JAMF</span><span class="sxs-lookup"><span data-stu-id="92772-469">Property list for JAMF configuration profile</span></span>

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

### <a name="intune-profile"></a><span data-ttu-id="92772-470">Perfil do Intune</span><span class="sxs-lookup"><span data-stu-id="92772-470">Intune profile</span></span>

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

## <a name="property-list-validation"></a><span data-ttu-id="92772-471">Validação de lista de propriedades</span><span class="sxs-lookup"><span data-stu-id="92772-471">Property list validation</span></span>

<span data-ttu-id="92772-472">A lista de propriedades deve ser um arquivo *.plist* válido.</span><span class="sxs-lookup"><span data-stu-id="92772-472">The property list must be a valid *.plist* file.</span></span> <span data-ttu-id="92772-473">Isso pode ser verificado executando:</span><span class="sxs-lookup"><span data-stu-id="92772-473">This can be checked by executing:</span></span>

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

<span data-ttu-id="92772-474">Se o arquivo for bem formado, o comando acima sairá e retornará um código `OK` de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="92772-474">If the file is well-formed, the above command outputs `OK` and returns an exit code of `0`.</span></span> <span data-ttu-id="92772-475">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="92772-475">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="92772-476">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="92772-476">Configuration profile deployment</span></span>

<span data-ttu-id="92772-477">Depois de construir o perfil de configuração da sua empresa, você pode implantá-lo por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="92772-477">Once you've built the configuration profile for your enterprise, you can deploy it through the management console that your enterprise is using.</span></span> <span data-ttu-id="92772-478">As seções a seguir fornecem instruções sobre como implantar esse perfil usando JAMF e Intune.</span><span class="sxs-lookup"><span data-stu-id="92772-478">The following sections provide instructions on how to deploy this profile using JAMF and Intune.</span></span>

### <a name="jamf-deployment"></a><span data-ttu-id="92772-479">Implantação jamf</span><span class="sxs-lookup"><span data-stu-id="92772-479">JAMF deployment</span></span>

<span data-ttu-id="92772-480">No console JAMF, **abra** Perfis de Configuração de Computadores, navegue até o perfil de configuração que você gostaria de  >  usar e selecione **Configurações Personalizadas.**</span><span class="sxs-lookup"><span data-stu-id="92772-480">From the JAMF console, open **Computers** > **Configuration Profiles**, navigate to the configuration profile you'd like to use, then select **Custom Settings**.</span></span> <span data-ttu-id="92772-481">Crie uma entrada com `com.microsoft.wdav` como o domínio de preferência e carregue o *.plist* produzido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="92772-481">Create an entry with `com.microsoft.wdav` as the preference domain and upload the *.plist* produced earlier.</span></span>

>[!CAUTION]
><span data-ttu-id="92772-482">Você deve inserir o domínio de preferência correto ( ); caso contrário, as preferências não serão reconhecidas pelo `com.microsoft.wdav` Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="92772-482">You must enter the correct preference domain (`com.microsoft.wdav`); otherwise, the preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

### <a name="intune-deployment"></a><span data-ttu-id="92772-483">Implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="92772-483">Intune deployment</span></span>

1. <span data-ttu-id="92772-484">Abra **Gerenciar**  >  **Configuração do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="92772-484">Open **Manage** > **Device configuration**.</span></span> <span data-ttu-id="92772-485">Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="92772-485">Select **Manage** > **Profiles** > **Create Profile**.</span></span>

2. <span data-ttu-id="92772-486">Escolha um nome para o perfil.</span><span class="sxs-lookup"><span data-stu-id="92772-486">Choose a name for the profile.</span></span> <span data-ttu-id="92772-487">Alterar **Platform=macOS** para **Profile type=Custom**.</span><span class="sxs-lookup"><span data-stu-id="92772-487">Change **Platform=macOS** to **Profile type=Custom**.</span></span> <span data-ttu-id="92772-488">Selecione Configurar.</span><span class="sxs-lookup"><span data-stu-id="92772-488">Select Configure.</span></span>

3. <span data-ttu-id="92772-489">Salve o .plist produzido anteriormente como `com.microsoft.wdav.xml` .</span><span class="sxs-lookup"><span data-stu-id="92772-489">Save the .plist produced earlier as `com.microsoft.wdav.xml`.</span></span>

4. <span data-ttu-id="92772-490">Insira `com.microsoft.wdav` como o nome do perfil de **configuração personalizado**.</span><span class="sxs-lookup"><span data-stu-id="92772-490">Enter `com.microsoft.wdav` as the **custom configuration profile name**.</span></span>

5. <span data-ttu-id="92772-491">Abra o perfil de configuração e carregue o `com.microsoft.wdav.xml` arquivo.</span><span class="sxs-lookup"><span data-stu-id="92772-491">Open the configuration profile and upload the `com.microsoft.wdav.xml` file.</span></span> <span data-ttu-id="92772-492">(Esse arquivo foi criado na etapa 3.)</span><span class="sxs-lookup"><span data-stu-id="92772-492">(This file was created in step 3.)</span></span>

6. <span data-ttu-id="92772-493">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="92772-493">Select **OK**.</span></span>

7. <span data-ttu-id="92772-494">Selecione **Gerenciar**  >  **atribuições**.</span><span class="sxs-lookup"><span data-stu-id="92772-494">Select **Manage** > **Assignments**.</span></span> <span data-ttu-id="92772-495">Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="92772-495">In the **Include** tab, select **Assign to All Users & All devices**.</span></span>

>[!CAUTION]
><span data-ttu-id="92772-496">Você deve inserir o nome de perfil de configuração personalizado correto; caso contrário, essas preferências não serão reconhecidas pelo Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="92772-496">You must enter the correct custom configuration profile name; otherwise, these preferences will not be recognized by Microsoft Defender for Endpoint.</span></span>

## <a name="resources"></a><span data-ttu-id="92772-497">Recursos</span><span class="sxs-lookup"><span data-stu-id="92772-497">Resources</span></span>

- [<span data-ttu-id="92772-498">Referência do Perfil de Configuração (Documentação do desenvolvedor da Apple)</span><span class="sxs-lookup"><span data-stu-id="92772-498">Configuration Profile Reference (Apple developer documentation)</span></span>](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
