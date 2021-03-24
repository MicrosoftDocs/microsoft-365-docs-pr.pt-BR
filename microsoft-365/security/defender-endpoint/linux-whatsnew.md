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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052946"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e547f-104">Novidades no Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="e547f-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="e547f-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="e547f-105">101.18.53</span></span>

- <span data-ttu-id="e547f-106">A EDR para Linux agora [está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="e547f-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="e547f-107">Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="e547f-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="e547f-108">Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="e547f-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="e547f-109">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="e547f-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="e547f-110">101.12.99</span></span>

- <span data-ttu-id="e547f-111">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="e547f-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="e547f-112">101.04.76</span></span>

- <span data-ttu-id="e547f-113">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="e547f-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="e547f-114">101.03.48</span></span>

- <span data-ttu-id="e547f-115">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="e547f-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="e547f-116">101.02.55</span></span>

- <span data-ttu-id="e547f-117">Corrigido um problema em que o produto às vezes não começa a seguir uma reinicialização/atualização</span><span class="sxs-lookup"><span data-stu-id="e547f-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="e547f-118">Correção de um problema em que as configurações de proxy não são persistentes nas atualizações do produto</span><span class="sxs-lookup"><span data-stu-id="e547f-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="e547f-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="e547f-119">101.00.75</span></span>

- <span data-ttu-id="e547f-120">Adicionado suporte para os seguintes tipos de sistema de arquivos: `ecryptfs` , , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`</span><span class="sxs-lookup"><span data-stu-id="e547f-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="e547f-121">Nova sintaxe para a [ferramenta de linha de comando](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="e547f-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="e547f-122">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="e547f-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="e547f-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="e547f-124">Ao atualizar o pacote instalado de uma versão do produto anterior a 100.90.70, a atualização pode falhar em distribuições SLES e baseadas em Red Hat.</span><span class="sxs-lookup"><span data-stu-id="e547f-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="e547f-125">Isso se deve a uma alteração importante em um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e547f-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="e547f-126">Uma solução temporária é remover o pacote mais antigo e instalar o mais novo.</span><span class="sxs-lookup"><span data-stu-id="e547f-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="e547f-127">Esse problema não existe em versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="e547f-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="e547f-128">As [exclusões de antivírus agora suportam curingas](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="e547f-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="e547f-129">Adicionada a capacidade de solucionar [problemas de desempenho](linux-support-perf.md) por meio da ferramenta de linha de `mdatp` comando</span><span class="sxs-lookup"><span data-stu-id="e547f-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="e547f-130">Melhorias para tornar a instalação do pacote mais robusta</span><span class="sxs-lookup"><span data-stu-id="e547f-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="e547f-131">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="e547f-131">Performance improvements & bug fixes</span></span>
