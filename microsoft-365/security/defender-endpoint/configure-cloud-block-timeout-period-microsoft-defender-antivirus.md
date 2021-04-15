---
title: Configurar o período de tempo de bloqueio de nuvem do Microsoft Defender Antivírus
description: Você pode configurar por quanto tempo o Microsoft Defender Antivírus impedirá a execução de um arquivo enquanto aguarda uma determinação na nuvem.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defender, nuvem, tempo decoro, bloqueio, ponto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765798"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurar o período de tempo limite de bloqueio da nuvem

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Quando o Microsoft Defender Antivírus encontra um arquivo suspeito, ele pode impedir que o arquivo seja executado enquanto ele consulta o serviço de nuvem [do Microsoft Defender Antivírus.](cloud-protection-microsoft-defender-antivirus.md)

O período padrão em que o arquivo será [bloqueado](configure-block-at-first-sight-microsoft-defender-antivirus.md) é de 10 segundos. Você pode especificar um período adicional de tempo para aguardar antes que o arquivo possa ser executado. Isso pode ajudar a garantir que haja tempo suficiente para receber uma determinação adequada do serviço de nuvem do Microsoft Defender Antivírus.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Pré-requisitos para usar o tempo de tempo de bloqueio estendido na nuvem

[Bloqueie à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) e seus pré-requisitos devem ser habilitados antes que você possa especificar um período de tempo de tempo estendido.

## <a name="specify-the-extended-timeout-period"></a>Especificar o período de tempo de tempo estendido

Você pode usar a Política de Grupo para especificar um tempo de tempo estendido para verificações na nuvem.

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > MpEngine**

4. Clique duas vezes em **Configurar verificação de nuvem estendida** e certifique-se de que a opção está habilitada. Especifique o tempo adicional para impedir que o arquivo seja executado enquanto aguarda uma determinação na nuvem. Você pode especificar o tempo adicional, em segundos, de 1 segundo a 50 segundos. Este tempo será adicionado aos 10 segundos padrão.

5. Clique em **OK**.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Usar tecnologias antivírus de última geração por meio da proteção entregue na nuvem](cloud-protection-microsoft-defender-antivirus.md)
- [Configurar o bloco à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Habilitar a proteção entregue na nuvem](enable-cloud-protection-microsoft-defender-antivirus.md)