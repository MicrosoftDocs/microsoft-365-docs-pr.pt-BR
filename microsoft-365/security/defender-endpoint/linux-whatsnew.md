---
title: Novidades no Microsoft Defender para Ponto de Extremidade para Linux
description: Lista das principais alterações do Microsoft Defender ATP para Linux.
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580997"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="4a2aa-104">Novidades no Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="4a2aa-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="4a2aa-105">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="4a2aa-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="4a2aa-106">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="4a2aa-107">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="4a2aa-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="4a2aa-108">Melhoria de desempenho para a situação em que um ponto de montagem inteiro é adicionado à lista de exclusão de antivírus.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="4a2aa-109">Antes dessa versão, a atividade de arquivo proveniente do ponto de montagem ainda era processada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="4a2aa-110">A partir dessa versão, a atividade de arquivo para pontos de montagem excluídos é suprimida, levando a um melhor desempenho do produto</span><span class="sxs-lookup"><span data-stu-id="4a2aa-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="4a2aa-111">Adicionada uma nova opção à ferramenta de linha de comando para exibir informações sobre a última verificação sob demanda.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="4a2aa-112">Para exibir informações sobre a última verificação sob demanda, execute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="4a2aa-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="4a2aa-113">Outras melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="4a2aa-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="4a2aa-114">101.18.53</span></span>

- <span data-ttu-id="4a2aa-115">A EDR para Linux agora [está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="4a2aa-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="4a2aa-116">Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="4a2aa-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="4a2aa-117">Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="4a2aa-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="4a2aa-118">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="4a2aa-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="4a2aa-119">101.12.99</span></span>

- <span data-ttu-id="4a2aa-120">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="4a2aa-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="4a2aa-121">101.04.76</span></span>

- <span data-ttu-id="4a2aa-122">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="4a2aa-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="4a2aa-123">101.03.48</span></span>

- <span data-ttu-id="4a2aa-124">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="4a2aa-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="4a2aa-125">101.02.55</span></span>

- <span data-ttu-id="4a2aa-126">Corrigido um problema em que o produto às vezes não começa a seguir uma reinicialização/atualização</span><span class="sxs-lookup"><span data-stu-id="4a2aa-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="4a2aa-127">Correção de um problema em que as configurações de proxy não são persistentes nas atualizações do produto</span><span class="sxs-lookup"><span data-stu-id="4a2aa-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="4a2aa-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="4a2aa-128">101.00.75</span></span>

- <span data-ttu-id="4a2aa-129">Adicionado suporte para os seguintes tipos de sistema de arquivos: `ecryptfs` , , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="4a2aa-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="4a2aa-130">Nova sintaxe para a [ferramenta de linha de comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="4a2aa-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="4a2aa-131">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="4a2aa-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="4a2aa-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="4a2aa-133">Ao atualizar o pacote instalado de uma versão do produto anterior a 100.90.70, a atualização pode falhar em distribuições SLES e baseadas em Red Hat.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="4a2aa-134">Isso se deve a uma alteração importante em um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="4a2aa-135">Uma solução temporária é remover o pacote mais antigo e instalar o mais novo.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="4a2aa-136">Esse problema não existe em versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="4a2aa-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="4a2aa-137">As [exclusões de antivírus agora suportam curingas](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="4a2aa-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="4a2aa-138">Adicionada a capacidade de solucionar [problemas de desempenho](linux-support-perf.md) por meio da ferramenta de linha de `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="4a2aa-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="4a2aa-139">Melhorias para tornar a instalação do pacote mais robusta</span><span class="sxs-lookup"><span data-stu-id="4a2aa-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="4a2aa-140">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="4a2aa-140">Performance improvements & bug fixes</span></span>
