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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198772"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="553a9-104">Novidades no Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="553a9-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="553a9-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="553a9-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="553a9-106">Melhoria de desempenho para a situação em que um ponto de montagem inteiro é adicionado à lista de exclusão de antivírus.</span><span class="sxs-lookup"><span data-stu-id="553a9-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="553a9-107">Antes dessa versão, a atividade de arquivo proveniente do ponto de montagem ainda era processada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="553a9-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="553a9-108">A partir dessa versão, a atividade de arquivo para pontos de montagem excluídos é suprimida, levando a um melhor desempenho do produto</span><span class="sxs-lookup"><span data-stu-id="553a9-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="553a9-109">Adicionada uma nova opção à ferramenta de linha de comando para exibir informações sobre a última verificação sob demanda.</span><span class="sxs-lookup"><span data-stu-id="553a9-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="553a9-110">Para exibir informações sobre a última verificação sob demanda, execute `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="553a9-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="553a9-111">Outras melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="553a9-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="553a9-112">101.18.53</span></span>

- <span data-ttu-id="553a9-113">A EDR para Linux agora [está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="553a9-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="553a9-114">Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="553a9-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="553a9-115">Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="553a9-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="553a9-116">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="553a9-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="553a9-117">101.12.99</span></span>

- <span data-ttu-id="553a9-118">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="553a9-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="553a9-119">101.04.76</span></span>

- <span data-ttu-id="553a9-120">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="553a9-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="553a9-121">101.03.48</span></span>

- <span data-ttu-id="553a9-122">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="553a9-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="553a9-123">101.02.55</span></span>

- <span data-ttu-id="553a9-124">Corrigido um problema em que o produto às vezes não começa a seguir uma reinicialização/atualização</span><span class="sxs-lookup"><span data-stu-id="553a9-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="553a9-125">Correção de um problema em que as configurações de proxy não são persistentes nas atualizações do produto</span><span class="sxs-lookup"><span data-stu-id="553a9-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="553a9-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="553a9-126">101.00.75</span></span>

- <span data-ttu-id="553a9-127">Adicionado suporte para os seguintes tipos de sistema de arquivos: `ecryptfs` , , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="553a9-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="553a9-128">Nova sintaxe para a [ferramenta de linha de comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="553a9-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="553a9-129">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="553a9-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="553a9-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="553a9-131">Ao atualizar o pacote instalado de uma versão do produto anterior a 100.90.70, a atualização pode falhar em distribuições SLES e baseadas em Red Hat.</span><span class="sxs-lookup"><span data-stu-id="553a9-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="553a9-132">Isso se deve a uma alteração importante em um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="553a9-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="553a9-133">Uma solução temporária é remover o pacote mais antigo e instalar o mais novo.</span><span class="sxs-lookup"><span data-stu-id="553a9-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="553a9-134">Esse problema não existe em versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="553a9-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="553a9-135">As [exclusões de antivírus agora suportam curingas](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="553a9-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="553a9-136">Adicionada a capacidade de solucionar [problemas de desempenho](linux-support-perf.md) por meio da ferramenta de linha de `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="553a9-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="553a9-137">Melhorias para tornar a instalação do pacote mais robusta</span><span class="sxs-lookup"><span data-stu-id="553a9-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="553a9-138">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="553a9-138">Performance improvements & bug fixes</span></span>
