---
title: Novidades no Microsoft Defender para Ponto de Extremidade no Linux
description: Lista das principais alterações do Microsoft Defender ATP no Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 2866cd0c9ee9b40aa9c08c4ff7dce64f745d3d03
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688623"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ffb17-104">Novidades no Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="ffb17-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="ffb17-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ffb17-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ffb17-106">O Microsoft Defender para Ponto de Extremidade no Linux agora está disponível em versão prévia para clientes do Governo dos EUA.</span><span class="sxs-lookup"><span data-stu-id="ffb17-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="ffb17-107">Para obter mais informações, consulte [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="ffb17-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="ffb17-108">Correção de um problema em que o uso do Microsoft Defender para Ponto de Extremidade no Linux em sistemas com sistemas de arquivos FUSE estava levando ao travamento do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="ffb17-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="ffb17-109">Melhorias de desempenho & outras correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="ffb17-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ffb17-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ffb17-111">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="ffb17-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="ffb17-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="ffb17-113">Melhoria de desempenho para a situação em que um ponto de montagem inteiro é adicionado à lista de exclusão de antivírus.</span><span class="sxs-lookup"><span data-stu-id="ffb17-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="ffb17-114">Antes dessa versão, a atividade de arquivo proveniente do ponto de montagem ainda era processada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="ffb17-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="ffb17-115">A partir dessa versão, a atividade de arquivo para pontos de montagem excluídos é suprimida, levando a um melhor desempenho do produto</span><span class="sxs-lookup"><span data-stu-id="ffb17-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="ffb17-116">Adicionada uma nova opção à ferramenta de linha de comando para exibir informações sobre a última verificação sob demanda.</span><span class="sxs-lookup"><span data-stu-id="ffb17-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="ffb17-117">Para exibir informações sobre a última verificação sob demanda, execute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="ffb17-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="ffb17-118">Outras melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="ffb17-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="ffb17-119">101.18.53</span></span>

- <span data-ttu-id="ffb17-120">A EDR para Linux agora [está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="ffb17-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="ffb17-121">Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="ffb17-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="ffb17-122">Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="ffb17-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="ffb17-123">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="ffb17-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="ffb17-124">101.12.99</span></span>

- <span data-ttu-id="ffb17-125">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="ffb17-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="ffb17-126">101.04.76</span></span>

- <span data-ttu-id="ffb17-127">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="ffb17-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="ffb17-128">101.03.48</span></span>

- <span data-ttu-id="ffb17-129">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="ffb17-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="ffb17-130">101.02.55</span></span>

- <span data-ttu-id="ffb17-131">Corrigido um problema em que o produto às vezes não começa a seguir uma reinicialização/atualização</span><span class="sxs-lookup"><span data-stu-id="ffb17-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="ffb17-132">Correção de um problema em que as configurações de proxy não são persistentes nas atualizações do produto</span><span class="sxs-lookup"><span data-stu-id="ffb17-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="ffb17-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="ffb17-133">101.00.75</span></span>

- <span data-ttu-id="ffb17-134">Adicionado suporte para os seguintes tipos de sistema de arquivos: `ecryptfs` , , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="ffb17-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="ffb17-135">Nova sintaxe para a [ferramenta de linha de comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ffb17-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="ffb17-136">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="ffb17-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="ffb17-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="ffb17-138">Ao atualizar o pacote instalado de uma versão do produto anterior a 100.90.70, a atualização pode falhar em distribuições SLES e baseadas em Red Hat.</span><span class="sxs-lookup"><span data-stu-id="ffb17-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="ffb17-139">Isso se deve a uma alteração importante em um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ffb17-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="ffb17-140">Uma solução temporária é remover o pacote mais antigo e instalar o mais novo.</span><span class="sxs-lookup"><span data-stu-id="ffb17-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="ffb17-141">Esse problema não existe em versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ffb17-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="ffb17-142">As [exclusões de antivírus agora suportam curingas](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="ffb17-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="ffb17-143">Adicionada a capacidade de solucionar [problemas de desempenho](linux-support-perf.md) por meio da ferramenta de linha de `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="ffb17-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="ffb17-144">Melhorias para tornar a instalação do pacote mais robusta</span><span class="sxs-lookup"><span data-stu-id="ffb17-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="ffb17-145">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="ffb17-145">Performance improvements & bug fixes</span></span>
