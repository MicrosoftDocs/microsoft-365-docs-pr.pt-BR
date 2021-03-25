---
title: Definir preferências para o Microsoft Defender ATP para Linux
ms.reviewer: ''
description: Descreve como configurar o Microsoft Defender ATP para Linux em empresas.
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ed28d3b5b7bafaea2d72b7a8c45f66bf69033bc2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187788"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a73f6-104">Definir preferências para o Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="a73f6-104">Set preferences for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a73f6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a73f6-105">**Applies to:**</span></span>
- [<span data-ttu-id="a73f6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a73f6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="a73f6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a73f6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a73f6-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a73f6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a73f6-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a73f6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
><span data-ttu-id="a73f6-110">Este tópico contém instruções sobre como definir preferências para o Defender for Endpoint para Linux em ambientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="a73f6-110">This topic contains instructions for how to set preferences for Defender for Endpoint for Linux in enterprise environments.</span></span> <span data-ttu-id="a73f6-111">Se você estiver interessado em configurar o produto em um dispositivo da linha de comando, consulte [Resources](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="a73f6-111">If you are interested in configuring the product on a device from the command-line, see [Resources](linux-resources.md#configure-from-the-command-line).</span></span>

<span data-ttu-id="a73f6-112">Em ambientes corporativos, o Defender for Endpoint para Linux pode ser gerenciado por meio de um perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="a73f6-112">In enterprise environments, Defender for Endpoint for Linux can be managed through a configuration profile.</span></span> <span data-ttu-id="a73f6-113">Esse perfil é implantado a partir da ferramenta de gerenciamento de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="a73f6-113">This profile is deployed from the management tool of your choice.</span></span> <span data-ttu-id="a73f6-114">As preferências gerenciadas pela empresa têm precedência sobre as definidas localmente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a73f6-114">Preferences managed by the enterprise take precedence over the ones set locally on the device.</span></span> <span data-ttu-id="a73f6-115">Em outras palavras, os usuários em sua empresa não são capazes de alterar as preferências definidas por meio desse perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="a73f6-115">In other words, users in your enterprise are not able to change preferences that are set through this configuration profile.</span></span>

<span data-ttu-id="a73f6-116">Este artigo descreve a estrutura desse perfil (incluindo um perfil recomendado que você pode usar para começar) e instruções sobre como implantar o perfil.</span><span class="sxs-lookup"><span data-stu-id="a73f6-116">This article describes the structure of this profile (including a recommended profile that you can use to get started) and instructions on how to deploy the profile.</span></span>

## <a name="configuration-profile-structure"></a><span data-ttu-id="a73f6-117">Estrutura de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="a73f6-117">Configuration profile structure</span></span>

<span data-ttu-id="a73f6-118">O perfil de configuração é um arquivo .json que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência.</span><span class="sxs-lookup"><span data-stu-id="a73f6-118">The configuration profile is a .json file that consists of entries identified by a key (which denotes the name of the preference), followed by a value, which depends on the nature of the preference.</span></span> <span data-ttu-id="a73f6-119">Os valores podem ser simples, como um valor numérico ou complexo, como uma lista aninhada de preferências.</span><span class="sxs-lookup"><span data-stu-id="a73f6-119">Values can be simple, such as a numerical value, or complex, such as a nested list of preferences.</span></span>

<span data-ttu-id="a73f6-120">Normalmente, você usaria uma ferramenta de gerenciamento de configuração para pressionar um arquivo com o nome ```mdatp_managed.json``` no local ```/etc/opt/microsoft/mdatp/managed/``` .</span><span class="sxs-lookup"><span data-stu-id="a73f6-120">Typically, you would use a configuration management tool to push a file with the name ```mdatp_managed.json``` at the location ```/etc/opt/microsoft/mdatp/managed/```.</span></span>

<span data-ttu-id="a73f6-121">O nível superior do perfil de configuração inclui preferências e entradas para subáreas do produto, que são explicadas com mais detalhes nas próximas seções.</span><span class="sxs-lookup"><span data-stu-id="a73f6-121">The top level of the configuration profile includes product-wide preferences and entries for subareas of the product, which are explained in more detail in the next sections.</span></span>

### <a name="antivirus-engine-preferences"></a><span data-ttu-id="a73f6-122">Preferências do mecanismo antivírus</span><span class="sxs-lookup"><span data-stu-id="a73f6-122">Antivirus engine preferences</span></span>

<span data-ttu-id="a73f6-123">A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do produto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-123">The *antivirusEngine* section of the configuration profile is used to manage the preferences of the antivirus component of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-124">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-124">**Key**</span></span> | <span data-ttu-id="a73f6-125">antivirusEngine</span><span class="sxs-lookup"><span data-stu-id="a73f6-125">antivirusEngine</span></span> |
| <span data-ttu-id="a73f6-126">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-126">**Data type**</span></span> | <span data-ttu-id="a73f6-127">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="a73f6-127">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a73f6-128">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-128">**Comments**</span></span> | <span data-ttu-id="a73f6-129">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="a73f6-129">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-real-time-protection"></a><span data-ttu-id="a73f6-130">Habilitar/desabilitar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="a73f6-130">Enable / disable real-time protection</span></span>

<span data-ttu-id="a73f6-131">Determina se a proteção em tempo real (arquivos de verificação conforme eles são acessados) está habilitada ou não.</span><span class="sxs-lookup"><span data-stu-id="a73f6-131">Determines whether real-time protection (scan files as they are accessed) is enabled or not.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-132">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-132">**Key**</span></span> | <span data-ttu-id="a73f6-133">enableRealTimeProtection</span><span class="sxs-lookup"><span data-stu-id="a73f6-133">enableRealTimeProtection</span></span> |
| <span data-ttu-id="a73f6-134">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-134">**Data type**</span></span> | <span data-ttu-id="a73f6-135">Booliano</span><span class="sxs-lookup"><span data-stu-id="a73f6-135">Boolean</span></span> |
| <span data-ttu-id="a73f6-136">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-136">**Possible values**</span></span> | <span data-ttu-id="a73f6-137">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-137">true (default)</span></span> <br/> <span data-ttu-id="a73f6-138">falso</span><span class="sxs-lookup"><span data-stu-id="a73f6-138">false</span></span> |

#### <a name="enable--disable-passive-mode"></a><span data-ttu-id="a73f6-139">Habilitar/desabilitar o modo passivo</span><span class="sxs-lookup"><span data-stu-id="a73f6-139">Enable / disable passive mode</span></span>

<span data-ttu-id="a73f6-140">Determina se o mecanismo antivírus é executado no modo passivo ou não.</span><span class="sxs-lookup"><span data-stu-id="a73f6-140">Determines whether the antivirus engine runs in passive mode or not.</span></span> <span data-ttu-id="a73f6-141">No modo passivo:</span><span class="sxs-lookup"><span data-stu-id="a73f6-141">In passive mode:</span></span>
- <span data-ttu-id="a73f6-142">A proteção em tempo real está desligada.</span><span class="sxs-lookup"><span data-stu-id="a73f6-142">Real-time protection is turned off.</span></span>
- <span data-ttu-id="a73f6-143">A verificação sob demanda está 100% 100%.</span><span class="sxs-lookup"><span data-stu-id="a73f6-143">On-demand scanning is turned on.</span></span>
- <span data-ttu-id="a73f6-144">A correção automática de ameaças está desligada.</span><span class="sxs-lookup"><span data-stu-id="a73f6-144">Automatic threat remediation is turned off.</span></span>
- <span data-ttu-id="a73f6-145">As atualizações de inteligência de segurança estão ativas.</span><span class="sxs-lookup"><span data-stu-id="a73f6-145">Security intelligence updates are turned on.</span></span>
- <span data-ttu-id="a73f6-146">O ícone do menu Status está oculto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-146">Status menu icon is hidden.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-147">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-147">**Key**</span></span> | <span data-ttu-id="a73f6-148">passiveMode</span><span class="sxs-lookup"><span data-stu-id="a73f6-148">passiveMode</span></span> |
| <span data-ttu-id="a73f6-149">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-149">**Data type**</span></span> | <span data-ttu-id="a73f6-150">Booliano</span><span class="sxs-lookup"><span data-stu-id="a73f6-150">Boolean</span></span> |
| <span data-ttu-id="a73f6-151">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-151">**Possible values**</span></span> | <span data-ttu-id="a73f6-152">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-152">false (default)</span></span> <br/> <span data-ttu-id="a73f6-153">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a73f6-153">true</span></span> |
| <span data-ttu-id="a73f6-154">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-154">**Comments**</span></span> | <span data-ttu-id="a73f6-155">Disponível no Defender para Ponto de Extremidade versão 100.67.60 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-155">Available in Defender for Endpoint version 100.67.60 or higher.</span></span> |

#### <a name="exclusion-merge-policy"></a><span data-ttu-id="a73f6-156">Política de mesclagem de exclusão</span><span class="sxs-lookup"><span data-stu-id="a73f6-156">Exclusion merge policy</span></span>

<span data-ttu-id="a73f6-157">Especifica a política de mesclagem para exclusões.</span><span class="sxs-lookup"><span data-stu-id="a73f6-157">Specifies the merge policy for exclusions.</span></span> <span data-ttu-id="a73f6-158">Pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="a73f6-158">It can be a combination of administrator-defined and user-defined exclusions (`merge`) or only administrator-defined exclusions (`admin_only`).</span></span> <span data-ttu-id="a73f6-159">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.</span><span class="sxs-lookup"><span data-stu-id="a73f6-159">This setting can be used to restrict local users from defining their own exclusions.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-160">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-160">**Key**</span></span> | <span data-ttu-id="a73f6-161">exclusionsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="a73f6-161">exclusionsMergePolicy</span></span> |
| <span data-ttu-id="a73f6-162">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-162">**Data type**</span></span> | <span data-ttu-id="a73f6-163">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-163">String</span></span> |
| <span data-ttu-id="a73f6-164">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-164">**Possible values**</span></span> | <span data-ttu-id="a73f6-165">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-165">merge (default)</span></span> <br/> <span data-ttu-id="a73f6-166">admin_only</span><span class="sxs-lookup"><span data-stu-id="a73f6-166">admin_only</span></span> |
| <span data-ttu-id="a73f6-167">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-167">**Comments**</span></span> | <span data-ttu-id="a73f6-168">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-168">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="scan-exclusions"></a><span data-ttu-id="a73f6-169">Exclusões de verificação</span><span class="sxs-lookup"><span data-stu-id="a73f6-169">Scan exclusions</span></span>

<span data-ttu-id="a73f6-170">Entidades que foram excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="a73f6-170">Entities that have been excluded from the scan.</span></span> <span data-ttu-id="a73f6-171">As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a73f6-171">Exclusions can be specified by full paths, extensions, or file names.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-172">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-172">**Key**</span></span> | <span data-ttu-id="a73f6-173">exclusões</span><span class="sxs-lookup"><span data-stu-id="a73f6-173">exclusions</span></span> |
| <span data-ttu-id="a73f6-174">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-174">**Data type**</span></span> | <span data-ttu-id="a73f6-175">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="a73f6-175">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a73f6-176">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-176">**Comments**</span></span> | <span data-ttu-id="a73f6-177">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="a73f6-177">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="a73f6-178">**Tipo de exclusão**</span><span class="sxs-lookup"><span data-stu-id="a73f6-178">**Type of exclusion**</span></span>

<span data-ttu-id="a73f6-179">Especifica o tipo de conteúdo excluído da verificação.</span><span class="sxs-lookup"><span data-stu-id="a73f6-179">Specifies the type of content excluded from the scan.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-180">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-180">**Key**</span></span> | <span data-ttu-id="a73f6-181">$type</span><span class="sxs-lookup"><span data-stu-id="a73f6-181">$type</span></span> |
| <span data-ttu-id="a73f6-182">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-182">**Data type**</span></span> | <span data-ttu-id="a73f6-183">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-183">String</span></span> |
| <span data-ttu-id="a73f6-184">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-184">**Possible values**</span></span> | <span data-ttu-id="a73f6-185">excludedPath</span><span class="sxs-lookup"><span data-stu-id="a73f6-185">excludedPath</span></span> <br/> <span data-ttu-id="a73f6-186">excludedFileExtension</span><span class="sxs-lookup"><span data-stu-id="a73f6-186">excludedFileExtension</span></span> <br/> <span data-ttu-id="a73f6-187">excludedFileName</span><span class="sxs-lookup"><span data-stu-id="a73f6-187">excludedFileName</span></span> |

<span data-ttu-id="a73f6-188">**Caminho para conteúdo excluído**</span><span class="sxs-lookup"><span data-stu-id="a73f6-188">**Path to excluded content**</span></span>

<span data-ttu-id="a73f6-189">Usado para excluir conteúdo da verificação por caminho de arquivo completo.</span><span class="sxs-lookup"><span data-stu-id="a73f6-189">Used to exclude content from the scan by full file path.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-190">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-190">**Key**</span></span> | <span data-ttu-id="a73f6-191">caminho</span><span class="sxs-lookup"><span data-stu-id="a73f6-191">path</span></span> |
| <span data-ttu-id="a73f6-192">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-192">**Data type**</span></span> | <span data-ttu-id="a73f6-193">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-193">String</span></span> |
| <span data-ttu-id="a73f6-194">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-194">**Possible values**</span></span> | <span data-ttu-id="a73f6-195">caminhos válidos</span><span class="sxs-lookup"><span data-stu-id="a73f6-195">valid paths</span></span> |
| <span data-ttu-id="a73f6-196">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-196">**Comments**</span></span> | <span data-ttu-id="a73f6-197">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="a73f6-197">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="a73f6-198">**Tipo de caminho (arquivo/diretório)**</span><span class="sxs-lookup"><span data-stu-id="a73f6-198">**Path type (file / directory)**</span></span>

<span data-ttu-id="a73f6-199">Indica se a *propriedade path* se refere a um arquivo ou diretório.</span><span class="sxs-lookup"><span data-stu-id="a73f6-199">Indicates if the *path* property refers to a file or directory.</span></span> 

|||
|:---|:---|
| <span data-ttu-id="a73f6-200">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-200">**Key**</span></span> | <span data-ttu-id="a73f6-201">isDirectory</span><span class="sxs-lookup"><span data-stu-id="a73f6-201">isDirectory</span></span> |
| <span data-ttu-id="a73f6-202">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-202">**Data type**</span></span> | <span data-ttu-id="a73f6-203">Booliano</span><span class="sxs-lookup"><span data-stu-id="a73f6-203">Boolean</span></span> |
| <span data-ttu-id="a73f6-204">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-204">**Possible values**</span></span> | <span data-ttu-id="a73f6-205">falso (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-205">false (default)</span></span> <br/> <span data-ttu-id="a73f6-206">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="a73f6-206">true</span></span> |
| <span data-ttu-id="a73f6-207">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-207">**Comments**</span></span> | <span data-ttu-id="a73f6-208">Aplicável somente se *$type* *for excludedPath*</span><span class="sxs-lookup"><span data-stu-id="a73f6-208">Applicable only if *$type* is *excludedPath*</span></span> |

<span data-ttu-id="a73f6-209">**Extensão de arquivo excluída da verificação**</span><span class="sxs-lookup"><span data-stu-id="a73f6-209">**File extension excluded from the scan**</span></span>

<span data-ttu-id="a73f6-210">Usado para excluir conteúdo da verificação por extensão de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a73f6-210">Used to exclude content from the scan by file extension.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-211">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-211">**Key**</span></span> | <span data-ttu-id="a73f6-212">extension</span><span class="sxs-lookup"><span data-stu-id="a73f6-212">extension</span></span> |
| <span data-ttu-id="a73f6-213">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-213">**Data type**</span></span> | <span data-ttu-id="a73f6-214">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-214">String</span></span> |
| <span data-ttu-id="a73f6-215">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-215">**Possible values**</span></span> | <span data-ttu-id="a73f6-216">extensões de arquivo válidas</span><span class="sxs-lookup"><span data-stu-id="a73f6-216">valid file extensions</span></span> |
| <span data-ttu-id="a73f6-217">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-217">**Comments**</span></span> | <span data-ttu-id="a73f6-218">Aplicável somente se *$type* *for excludedFileExtension*</span><span class="sxs-lookup"><span data-stu-id="a73f6-218">Applicable only if *$type* is *excludedFileExtension*</span></span> |

<span data-ttu-id="a73f6-219">**Processo excluído da verificação**</span><span class="sxs-lookup"><span data-stu-id="a73f6-219">**Process excluded from the scan**</span></span>

<span data-ttu-id="a73f6-220">Especifica um processo para o qual todas as atividades de arquivo são excluídas da verificação.</span><span class="sxs-lookup"><span data-stu-id="a73f6-220">Specifies a process for which all file activity is excluded from scanning.</span></span> <span data-ttu-id="a73f6-221">O processo pode ser especificado pelo nome (por exemplo) `cat` ou caminho completo (por exemplo, `/bin/cat` ).</span><span class="sxs-lookup"><span data-stu-id="a73f6-221">The process can be specified either by its name (for example, `cat`) or full path (for example, `/bin/cat`).</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-222">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-222">**Key**</span></span> | <span data-ttu-id="a73f6-223">nome</span><span class="sxs-lookup"><span data-stu-id="a73f6-223">name</span></span> |
| <span data-ttu-id="a73f6-224">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-224">**Data type**</span></span> | <span data-ttu-id="a73f6-225">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-225">String</span></span> |
| <span data-ttu-id="a73f6-226">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-226">**Possible values**</span></span> | <span data-ttu-id="a73f6-227">qualquer cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-227">any string</span></span> |
| <span data-ttu-id="a73f6-228">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-228">**Comments**</span></span> | <span data-ttu-id="a73f6-229">Aplicável somente *se* $type *for excludedFileName*</span><span class="sxs-lookup"><span data-stu-id="a73f6-229">Applicable only if *$type* is *excludedFileName*</span></span> |

#### <a name="allowed-threats"></a><span data-ttu-id="a73f6-230">Ameaças permitidas</span><span class="sxs-lookup"><span data-stu-id="a73f6-230">Allowed threats</span></span>

<span data-ttu-id="a73f6-231">Lista de ameaças (identificadas pelo nome) que não são bloqueadas pelo produto e têm permissão para executar.</span><span class="sxs-lookup"><span data-stu-id="a73f6-231">List of threats (identified by their name) that are not blocked by the product and are instead allowed to run.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-232">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-232">**Key**</span></span> | <span data-ttu-id="a73f6-233">allowedThreats</span><span class="sxs-lookup"><span data-stu-id="a73f6-233">allowedThreats</span></span> |
| <span data-ttu-id="a73f6-234">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-234">**Data type**</span></span> | <span data-ttu-id="a73f6-235">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-235">Array of strings</span></span> |

#### <a name="disallowed-threat-actions"></a><span data-ttu-id="a73f6-236">Ações de ameaça não permitidos</span><span class="sxs-lookup"><span data-stu-id="a73f6-236">Disallowed threat actions</span></span>

<span data-ttu-id="a73f6-237">Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas.</span><span class="sxs-lookup"><span data-stu-id="a73f6-237">Restricts the actions that the local user of a device can take when threats are detected.</span></span> <span data-ttu-id="a73f6-238">As ações incluídas nesta lista não são exibidas na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="a73f6-238">The actions included in this list are not displayed in the user interface.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-239">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-239">**Key**</span></span> | <span data-ttu-id="a73f6-240">disallowedThreatActions</span><span class="sxs-lookup"><span data-stu-id="a73f6-240">disallowedThreatActions</span></span> |
| <span data-ttu-id="a73f6-241">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-241">**Data type**</span></span> | <span data-ttu-id="a73f6-242">Matriz de cadeias de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-242">Array of strings</span></span> |
| <span data-ttu-id="a73f6-243">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-243">**Possible values**</span></span> | <span data-ttu-id="a73f6-244">allow (restringe os usuários a permitir ameaças)</span><span class="sxs-lookup"><span data-stu-id="a73f6-244">allow (restricts users from allowing threats)</span></span> <br/> <span data-ttu-id="a73f6-245">restore (restringe os usuários de restaurar ameaças da quarentena)</span><span class="sxs-lookup"><span data-stu-id="a73f6-245">restore (restricts users from restoring threats from the quarantine)</span></span> |
| <span data-ttu-id="a73f6-246">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-246">**Comments**</span></span> | <span data-ttu-id="a73f6-247">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-247">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="threat-type-settings"></a><span data-ttu-id="a73f6-248">Configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="a73f6-248">Threat type settings</span></span>

<span data-ttu-id="a73f6-249">A *preferência threatTypeSettings* no mecanismo antivírus é usada para controlar como determinados tipos de ameaça são manipulados pelo produto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-249">The *threatTypeSettings* preference in the antivirus engine is used to control how certain threat types are handled by the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-250">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-250">**Key**</span></span> | <span data-ttu-id="a73f6-251">threatTypeSettings</span><span class="sxs-lookup"><span data-stu-id="a73f6-251">threatTypeSettings</span></span> |
| <span data-ttu-id="a73f6-252">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-252">**Data type**</span></span> | <span data-ttu-id="a73f6-253">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="a73f6-253">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a73f6-254">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-254">**Comments**</span></span> | <span data-ttu-id="a73f6-255">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="a73f6-255">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="a73f6-256">**Tipo de ameaça**</span><span class="sxs-lookup"><span data-stu-id="a73f6-256">**Threat type**</span></span>

<span data-ttu-id="a73f6-257">Tipo de ameaça para a qual o comportamento está configurado.</span><span class="sxs-lookup"><span data-stu-id="a73f6-257">Type of threat for which the behavior is configured.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-258">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-258">**Key**</span></span> | <span data-ttu-id="a73f6-259">chave</span><span class="sxs-lookup"><span data-stu-id="a73f6-259">key</span></span> |
| <span data-ttu-id="a73f6-260">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-260">**Data type**</span></span> | <span data-ttu-id="a73f6-261">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-261">String</span></span> |
| <span data-ttu-id="a73f6-262">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-262">**Possible values**</span></span> | <span data-ttu-id="a73f6-263">potentially_unwanted_application</span><span class="sxs-lookup"><span data-stu-id="a73f6-263">potentially_unwanted_application</span></span> <br/> <span data-ttu-id="a73f6-264">archive_bomb</span><span class="sxs-lookup"><span data-stu-id="a73f6-264">archive_bomb</span></span> |

<span data-ttu-id="a73f6-265">**O que fazer**</span><span class="sxs-lookup"><span data-stu-id="a73f6-265">**Action to take**</span></span>

<span data-ttu-id="a73f6-266">Ação a ser tomada ao se deparar com uma ameaça do tipo especificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-266">Action to take when coming across a threat of the type specified in the preceding section.</span></span> <span data-ttu-id="a73f6-267">Pode ser:</span><span class="sxs-lookup"><span data-stu-id="a73f6-267">Can be:</span></span>

- <span data-ttu-id="a73f6-268">**Auditoria**: o dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.</span><span class="sxs-lookup"><span data-stu-id="a73f6-268">**Audit**: The device is not protected against this type of threat, but an entry about the threat is logged.</span></span>
- <span data-ttu-id="a73f6-269">**Bloquear**: o dispositivo é protegido contra esse tipo de ameaça e você é notificado no console de segurança.</span><span class="sxs-lookup"><span data-stu-id="a73f6-269">**Block**: The device is protected against this type of threat and you are notified in the security console.</span></span>
- <span data-ttu-id="a73f6-270">**Off**: O dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.</span><span class="sxs-lookup"><span data-stu-id="a73f6-270">**Off**: The device is not protected against this type of threat and nothing is logged.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-271">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-271">**Key**</span></span> | <span data-ttu-id="a73f6-272">valor</span><span class="sxs-lookup"><span data-stu-id="a73f6-272">value</span></span> |
| <span data-ttu-id="a73f6-273">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-273">**Data type**</span></span> | <span data-ttu-id="a73f6-274">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-274">String</span></span> |
| <span data-ttu-id="a73f6-275">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-275">**Possible values**</span></span> | <span data-ttu-id="a73f6-276">audit (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-276">audit (default)</span></span> <br/> <span data-ttu-id="a73f6-277">block</span><span class="sxs-lookup"><span data-stu-id="a73f6-277">block</span></span> <br/> <span data-ttu-id="a73f6-278">off</span><span class="sxs-lookup"><span data-stu-id="a73f6-278">off</span></span> |

#### <a name="threat-type-settings-merge-policy"></a><span data-ttu-id="a73f6-279">Política de mesclagem de configurações de tipo de ameaça</span><span class="sxs-lookup"><span data-stu-id="a73f6-279">Threat type settings merge policy</span></span>

<span data-ttu-id="a73f6-280">Especifica a política de mesclagem para configurações de tipo de ameaça.</span><span class="sxs-lookup"><span data-stu-id="a73f6-280">Specifies the merge policy for threat type settings.</span></span> <span data-ttu-id="a73f6-281">Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ).</span><span class="sxs-lookup"><span data-stu-id="a73f6-281">This can be a combination of administrator-defined and user-defined settings (`merge`) or only administrator-defined settings (`admin_only`).</span></span> <span data-ttu-id="a73f6-282">Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.</span><span class="sxs-lookup"><span data-stu-id="a73f6-282">This setting can be used to restrict local users from defining their own settings for different threat types.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-283">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-283">**Key**</span></span> | <span data-ttu-id="a73f6-284">threatTypeSettingsMergePolicy</span><span class="sxs-lookup"><span data-stu-id="a73f6-284">threatTypeSettingsMergePolicy</span></span> |
| <span data-ttu-id="a73f6-285">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-285">**Data type**</span></span> | <span data-ttu-id="a73f6-286">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-286">String</span></span> |
| <span data-ttu-id="a73f6-287">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-287">**Possible values**</span></span> | <span data-ttu-id="a73f6-288">merge (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-288">merge (default)</span></span> <br/> <span data-ttu-id="a73f6-289">admin_only</span><span class="sxs-lookup"><span data-stu-id="a73f6-289">admin_only</span></span> |
| <span data-ttu-id="a73f6-290">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-290">**Comments**</span></span> | <span data-ttu-id="a73f6-291">Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-291">Available in Defender for Endpoint version 100.83.73 or higher.</span></span> |

#### <a name="antivirus-scan-history-retention-in-days"></a><span data-ttu-id="a73f6-292">Retenção de histórico de verificação de antivírus (em dias)</span><span class="sxs-lookup"><span data-stu-id="a73f6-292">Antivirus scan history retention (in days)</span></span>

<span data-ttu-id="a73f6-293">Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a73f6-293">Specify the number of days that results are retained in the scan history on the device.</span></span> <span data-ttu-id="a73f6-294">Os resultados antigos da verificação são removidos do histórico.</span><span class="sxs-lookup"><span data-stu-id="a73f6-294">Old scan results are removed from the history.</span></span> <span data-ttu-id="a73f6-295">Arquivos em quarentena antigos que também são removidos do disco.</span><span class="sxs-lookup"><span data-stu-id="a73f6-295">Old quarantined files that are also removed from the disk.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-296">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-296">**Key**</span></span> | <span data-ttu-id="a73f6-297">scanResultsRetentionDays</span><span class="sxs-lookup"><span data-stu-id="a73f6-297">scanResultsRetentionDays</span></span> |
| <span data-ttu-id="a73f6-298">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-298">**Data type**</span></span> | <span data-ttu-id="a73f6-299">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-299">String</span></span> |
| <span data-ttu-id="a73f6-300">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-300">**Possible values**</span></span> | <span data-ttu-id="a73f6-301">90 (padrão).</span><span class="sxs-lookup"><span data-stu-id="a73f6-301">90 (default).</span></span> <span data-ttu-id="a73f6-302">Os valores permitidos são de 1 dia a 180 dias.</span><span class="sxs-lookup"><span data-stu-id="a73f6-302">Allowed values are from 1 day to 180 days.</span></span> |
| <span data-ttu-id="a73f6-303">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-303">**Comments**</span></span> | <span data-ttu-id="a73f6-304">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-304">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a><span data-ttu-id="a73f6-305">Número máximo de itens no histórico de verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="a73f6-305">Maximum number of items in the antivirus scan history</span></span>

<span data-ttu-id="a73f6-306">Especifique o número máximo de entradas a manter no histórico de verificação.</span><span class="sxs-lookup"><span data-stu-id="a73f6-306">Specify the maximum number of entries to keep in the scan history.</span></span> <span data-ttu-id="a73f6-307">As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.</span><span class="sxs-lookup"><span data-stu-id="a73f6-307">Entries include all on-demand scans performed in the past and all antivirus detections.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-308">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-308">**Key**</span></span> | <span data-ttu-id="a73f6-309">scanHistoryMaximumItems</span><span class="sxs-lookup"><span data-stu-id="a73f6-309">scanHistoryMaximumItems</span></span> |
| <span data-ttu-id="a73f6-310">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-310">**Data type**</span></span> | <span data-ttu-id="a73f6-311">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-311">String</span></span> |
| <span data-ttu-id="a73f6-312">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-312">**Possible values**</span></span> | <span data-ttu-id="a73f6-313">10000 (padrão).</span><span class="sxs-lookup"><span data-stu-id="a73f6-313">10000 (default).</span></span> <span data-ttu-id="a73f6-314">Os valores permitidos são de 5.000 itens a 15.000 itens.</span><span class="sxs-lookup"><span data-stu-id="a73f6-314">Allowed values are from 5000 items to 15000 items.</span></span> |
| <span data-ttu-id="a73f6-315">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-315">**Comments**</span></span> | <span data-ttu-id="a73f6-316">Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a73f6-316">Available in Defender for Endpoint version 101.04.76 or higher.</span></span> |

### <a name="cloud-delivered-protection-preferences"></a><span data-ttu-id="a73f6-317">Preferências de proteção entregues na nuvem</span><span class="sxs-lookup"><span data-stu-id="a73f6-317">Cloud-delivered protection preferences</span></span>

<span data-ttu-id="a73f6-318">A *entrada do cloudService* no perfil de configuração é usada para configurar o recurso de proteção orientada por nuvem do produto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-318">The *cloudService* entry in the configuration profile is used to configure the cloud-driven protection feature of the product.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-319">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-319">**Key**</span></span> | <span data-ttu-id="a73f6-320">cloudService</span><span class="sxs-lookup"><span data-stu-id="a73f6-320">cloudService</span></span> |
| <span data-ttu-id="a73f6-321">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-321">**Data type**</span></span> | <span data-ttu-id="a73f6-322">Dicionário (preferência aninhada)</span><span class="sxs-lookup"><span data-stu-id="a73f6-322">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="a73f6-323">**Comments**</span><span class="sxs-lookup"><span data-stu-id="a73f6-323">**Comments**</span></span> | <span data-ttu-id="a73f6-324">Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário.</span><span class="sxs-lookup"><span data-stu-id="a73f6-324">See the following sections for a description of the dictionary contents.</span></span> |

#### <a name="enable--disable-cloud-delivered-protection"></a><span data-ttu-id="a73f6-325">Habilitar/desabilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="a73f6-325">Enable / disable cloud delivered protection</span></span>

<span data-ttu-id="a73f6-326">Determina se a proteção entregue na nuvem está habilitada no dispositivo ou não.</span><span class="sxs-lookup"><span data-stu-id="a73f6-326">Determines whether cloud-delivered protection is enabled on the device or not.</span></span> <span data-ttu-id="a73f6-327">Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.</span><span class="sxs-lookup"><span data-stu-id="a73f6-327">To improve the security of your services, we recommend keeping this feature turned on.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-328">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-328">**Key**</span></span> | <span data-ttu-id="a73f6-329">habilitadas</span><span class="sxs-lookup"><span data-stu-id="a73f6-329">enabled</span></span> |
| <span data-ttu-id="a73f6-330">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-330">**Data type**</span></span> | <span data-ttu-id="a73f6-331">Booliano</span><span class="sxs-lookup"><span data-stu-id="a73f6-331">Boolean</span></span> |
| <span data-ttu-id="a73f6-332">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-332">**Possible values**</span></span> | <span data-ttu-id="a73f6-333">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-333">true (default)</span></span> <br/> <span data-ttu-id="a73f6-334">falso</span><span class="sxs-lookup"><span data-stu-id="a73f6-334">false</span></span> |

#### <a name="diagnostic-collection-level"></a><span data-ttu-id="a73f6-335">Nível de coleta de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a73f6-335">Diagnostic collection level</span></span>

<span data-ttu-id="a73f6-336">Os dados de diagnóstico são usados para manter o Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-336">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span> <span data-ttu-id="a73f6-337">Essa configuração determina o nível de diagnóstico enviado pelo produto para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a73f6-337">This setting determines the level of diagnostics sent by the product to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-338">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-338">**Key**</span></span> | <span data-ttu-id="a73f6-339">diagnosticLevel</span><span class="sxs-lookup"><span data-stu-id="a73f6-339">diagnosticLevel</span></span> |
| <span data-ttu-id="a73f6-340">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-340">**Data type**</span></span> | <span data-ttu-id="a73f6-341">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-341">String</span></span> |
| <span data-ttu-id="a73f6-342">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-342">**Possible values**</span></span> | <span data-ttu-id="a73f6-343">opcional (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-343">optional (default)</span></span> <br/> <span data-ttu-id="a73f6-344">obrigatório</span><span class="sxs-lookup"><span data-stu-id="a73f6-344">required</span></span> |

#### <a name="enable--disable-automatic-sample-submissions"></a><span data-ttu-id="a73f6-345">Habilitar/desabilitar envios automáticos de exemplo</span><span class="sxs-lookup"><span data-stu-id="a73f6-345">Enable / disable automatic sample submissions</span></span>

<span data-ttu-id="a73f6-346">Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a73f6-346">Determines whether suspicious samples (that are likely to contain threats) are sent to Microsoft.</span></span> <span data-ttu-id="a73f6-347">Há três níveis para controlar o envio de exemplo:</span><span class="sxs-lookup"><span data-stu-id="a73f6-347">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="a73f6-348">**Nenhum**: nenhum exemplo suspeito é enviado à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a73f6-348">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="a73f6-349">**Seguro**: somente amostras suspeitas que não contêm informações de identificação pessoal (PII) são enviadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a73f6-349">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="a73f6-350">Esse é o valor padrão para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="a73f6-350">This is the default value for this setting.</span></span>
- <span data-ttu-id="a73f6-351">**All**: todos os exemplos suspeitos são enviados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a73f6-351">**All**: all suspicious samples are submitted to Microsoft.</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-352">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-352">**Key**</span></span> | <span data-ttu-id="a73f6-353">automaticSampleSubmissionConsent</span><span class="sxs-lookup"><span data-stu-id="a73f6-353">automaticSampleSubmissionConsent</span></span> |
| <span data-ttu-id="a73f6-354">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-354">**Data type**</span></span> | <span data-ttu-id="a73f6-355">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="a73f6-355">String</span></span> |
| <span data-ttu-id="a73f6-356">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-356">**Possible values**</span></span> | <span data-ttu-id="a73f6-357">nenhuma</span><span class="sxs-lookup"><span data-stu-id="a73f6-357">none</span></span> <br/> <span data-ttu-id="a73f6-358">safe (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-358">safe (default)</span></span> <br/> <span data-ttu-id="a73f6-359">all</span><span class="sxs-lookup"><span data-stu-id="a73f6-359">all</span></span> |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a><span data-ttu-id="a73f6-360">Habilitar/desabilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="a73f6-360">Enable / disable automatic security intelligence updates</span></span>

<span data-ttu-id="a73f6-361">Determina se as atualizações de inteligência de segurança são instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="a73f6-361">Determines whether security intelligence updates are installed automatically:</span></span>

|||
|:---|:---|
| <span data-ttu-id="a73f6-362">**Chave**</span><span class="sxs-lookup"><span data-stu-id="a73f6-362">**Key**</span></span> | <span data-ttu-id="a73f6-363">automaticDefinitionUpdateEnabled</span><span class="sxs-lookup"><span data-stu-id="a73f6-363">automaticDefinitionUpdateEnabled</span></span> |
| <span data-ttu-id="a73f6-364">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a73f6-364">**Data type**</span></span> | <span data-ttu-id="a73f6-365">Booliano</span><span class="sxs-lookup"><span data-stu-id="a73f6-365">Boolean</span></span> |
| <span data-ttu-id="a73f6-366">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="a73f6-366">**Possible values**</span></span> | <span data-ttu-id="a73f6-367">true (padrão)</span><span class="sxs-lookup"><span data-stu-id="a73f6-367">true (default)</span></span> <br/> <span data-ttu-id="a73f6-368">falso</span><span class="sxs-lookup"><span data-stu-id="a73f6-368">false</span></span> |

## <a name="recommended-configuration-profile"></a><span data-ttu-id="a73f6-369">Perfil de configuração recomendado</span><span class="sxs-lookup"><span data-stu-id="a73f6-369">Recommended configuration profile</span></span>

<span data-ttu-id="a73f6-370">Para começar, recomendamos que o perfil de configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Defender para Ponto de Extremidade fornece.</span><span class="sxs-lookup"><span data-stu-id="a73f6-370">To get started, we recommend the following configuration profile for your enterprise to take advantage of all protection features that Defender for Endpoint provides.</span></span>

<span data-ttu-id="a73f6-371">O seguinte perfil de configuração será:</span><span class="sxs-lookup"><span data-stu-id="a73f6-371">The following configuration profile will:</span></span>

- <span data-ttu-id="a73f6-372">Habilitar a proteção em tempo real (RTP)</span><span class="sxs-lookup"><span data-stu-id="a73f6-372">Enable real-time protection (RTP)</span></span>
- <span data-ttu-id="a73f6-373">Especifique como os seguintes tipos de ameaça são tratados:</span><span class="sxs-lookup"><span data-stu-id="a73f6-373">Specify how the following threat types are handled:</span></span>
  - <span data-ttu-id="a73f6-374">**Aplicativos potencialmente indesejados (PUA)** são bloqueados</span><span class="sxs-lookup"><span data-stu-id="a73f6-374">**Potentially unwanted applications (PUA)** are blocked</span></span>
  - <span data-ttu-id="a73f6-375">**As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para os logs do produto</span><span class="sxs-lookup"><span data-stu-id="a73f6-375">**Archive bombs** (file with a high compression rate) are audited to the product logs</span></span>
- <span data-ttu-id="a73f6-376">Habilitar atualizações automáticas de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="a73f6-376">Enable automatic security intelligence updates</span></span>
- <span data-ttu-id="a73f6-377">Habilitar a proteção entregue na nuvem</span><span class="sxs-lookup"><span data-stu-id="a73f6-377">Enable cloud-delivered protection</span></span>
- <span data-ttu-id="a73f6-378">Habilitar o envio automático de exemplo no `safe` nível</span><span class="sxs-lookup"><span data-stu-id="a73f6-378">Enable automatic sample submission at `safe` level</span></span>

### <a name="sample-profile"></a><span data-ttu-id="a73f6-379">Perfil de exemplo</span><span class="sxs-lookup"><span data-stu-id="a73f6-379">Sample profile</span></span>

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
   }
}
```

## <a name="full-configuration-profile-example"></a><span data-ttu-id="a73f6-380">Exemplo de perfil de configuração completa</span><span class="sxs-lookup"><span data-stu-id="a73f6-380">Full configuration profile example</span></span>

<span data-ttu-id="a73f6-381">O perfil de configuração a seguir contém entradas para todas as configurações descritas neste documento e pode ser usado para cenários mais avançados em que você deseja mais controle sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="a73f6-381">The following configuration profile contains entries for all settings described in this document and can be used for more advanced scenarios where you want more control over the product.</span></span>

### <a name="full-profile"></a><span data-ttu-id="a73f6-382">Perfil completo</span><span class="sxs-lookup"><span data-stu-id="a73f6-382">Full profile</span></span>

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
   }
}
```

## <a name="configuration-profile-validation"></a><span data-ttu-id="a73f6-383">Validação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="a73f6-383">Configuration profile validation</span></span>

<span data-ttu-id="a73f6-384">O perfil de configuração deve ser um arquivo JSON formatado válido.</span><span class="sxs-lookup"><span data-stu-id="a73f6-384">The configuration profile must be a valid JSON-formatted file.</span></span> <span data-ttu-id="a73f6-385">Há várias ferramentas que podem ser usadas para verificar isso.</span><span class="sxs-lookup"><span data-stu-id="a73f6-385">There are a number of tools that can be used to verify this.</span></span> <span data-ttu-id="a73f6-386">Por exemplo, se você `python` tiver instalado em seu dispositivo:</span><span class="sxs-lookup"><span data-stu-id="a73f6-386">For example, if you have `python` installed on your device:</span></span>

```bash
python -m json.tool mdatp_managed.json
```

<span data-ttu-id="a73f6-387">Se o JSON for bem formado, o comando acima o retornará ao Terminal e retornará um código de saída de `0` .</span><span class="sxs-lookup"><span data-stu-id="a73f6-387">If the JSON is well-formed, the above command outputs it back to the Terminal and returns an exit code of `0`.</span></span> <span data-ttu-id="a73f6-388">Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .</span><span class="sxs-lookup"><span data-stu-id="a73f6-388">Otherwise, an error that describes the issue is displayed and the command returns an exit code of `1`.</span></span>

## <a name="configuration-profile-deployment"></a><span data-ttu-id="a73f6-389">Implantação de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="a73f6-389">Configuration profile deployment</span></span>

<span data-ttu-id="a73f6-390">Depois de construir o perfil de configuração para sua empresa, você poderá implantá-lo por meio da ferramenta de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="a73f6-390">Once you've built the configuration profile for your enterprise, you can deploy it through the management tool that your enterprise is using.</span></span> <span data-ttu-id="a73f6-391">O Defender for Endpoint para Linux lê a configuração gerenciada do *arquivo /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*</span><span class="sxs-lookup"><span data-stu-id="a73f6-391">Defender for Endpoint for Linux reads the managed configuration from the */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* file.</span></span>
