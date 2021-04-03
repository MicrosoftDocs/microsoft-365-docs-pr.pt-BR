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
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Novidades no Microsoft Defender para Ponto de Extremidade para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Melhorias de desempenho & correções de bugs

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Melhoria de desempenho para a situação em que um ponto de montagem inteiro é adicionado à lista de exclusão de antivírus. Antes dessa versão, a atividade de arquivo proveniente do ponto de montagem ainda era processada pelo produto. A partir dessa versão, a atividade de arquivo para pontos de montagem excluídos é suprimida, levando a um melhor desempenho do produto
- Adicionada uma nova opção à ferramenta de linha de comando para exibir informações sobre a última verificação sob demanda. Para exibir informações sobre a última verificação sob demanda, execute `mdatp health --details antivirus`
- Outras melhorias de desempenho & correções de bugs

## <a name="1011853"></a>101.18.53

- A EDR para Linux agora [está geralmente disponível](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )
- Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente
- Melhorias de desempenho & correções de bugs

## <a name="1011299"></a>101.12.99

- Melhorias de desempenho & correções de bugs

## <a name="1010476"></a>101.04.76

- Correções de bugs

## <a name="1010348"></a>101.03.48

- Correções de bugs

## <a name="1010255"></a>101.02.55

- Corrigido um problema em que o produto às vezes não começa a seguir uma reinicialização/atualização
- Correção de um problema em que as configurações de proxy não são persistentes nas atualizações do produto

## <a name="1010075"></a>101.00.75

- Adicionado suporte para os seguintes tipos de sistema de arquivos: `ecryptfs` , , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`
- Nova sintaxe para a [ferramenta de linha de comando](linux-resources.md#configure-from-the-command-line).
- Melhorias de desempenho & correções de bugs

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Ao atualizar o pacote instalado de uma versão do produto anterior a 100.90.70, a atualização pode falhar em distribuições SLES e baseadas em Red Hat. Isso se deve a uma alteração importante em um caminho de arquivo. Uma solução temporária é remover o pacote mais antigo e instalar o mais novo. Esse problema não existe em versões mais recentes.

- As [exclusões de antivírus agora suportam curingas](linux-exclusions.md#supported-exclusion-types)
- Adicionada a capacidade de solucionar [problemas de desempenho](linux-support-perf.md) por meio da ferramenta de linha de `mdatp` comando
- Melhorias para tornar a instalação do pacote mais robusta
- Melhorias de desempenho & correções de bugs
