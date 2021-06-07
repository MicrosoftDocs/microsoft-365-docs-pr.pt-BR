---
title: Configurar o período Microsoft Defender Antivírus tempo de bloqueio de nuvem
description: Você pode configurar por quanto Microsoft Defender Antivírus impedirá que um arquivo seja executado enquanto aguarda uma determinação na nuvem.
keywords: Microsoft Defender Antivírus, antimalware, segurança, defensor, nuvem, tempo decoro, bloqueio, ponto, segundos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789082"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurar o período de tempo limite de bloqueio da nuvem

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Quando Microsoft Defender Antivírus um arquivo suspeito, ele pode impedir que o arquivo seja executado enquanto ele consulta o serviço Microsoft Defender Antivírus [nuvem](cloud-protection-microsoft-defender-antivirus.md).

O período padrão em que o arquivo é [bloqueado](configure-block-at-first-sight-microsoft-defender-antivirus.md) é de 10 segundos. Se você for um administrador de segurança, poderá especificar mais tempo para aguardar antes que o arquivo possa ser executado. Estender o período de tempo de tempo de bloqueio da nuvem pode ajudar a garantir que haja tempo suficiente para receber uma determinação adequada do serviço Microsoft Defender Antivírus nuvem.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Pré-requisitos para usar o tempo de tempo de bloqueio estendido na nuvem

[Bloqueie à primeira vista](configure-block-at-first-sight-microsoft-defender-antivirus.md) e seus pré-requisitos devem ser habilitados antes que você possa especificar um período de tempo de tempo estendido.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Especifique o período de tempo Microsoft Endpoint Manager

Você pode especificar o período de tempo de bloqueio da nuvem com uma política de segurança do ponto de extremidade [em Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).

1. Vá para o Endpoint Manager de administração ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e entre.

2. Selecione **Segurança do ponto de** extremidade e, em **Gerenciar,** escolha **Antivírus**.

3. Selecione (ou crie) uma política de antivírus.

4. Na seção **Configuração de configurações,** expanda **Proteção de nuvem**. Em seguida, na **caixa Tempo** Decoro Estendido da Nuvem do Defender em Segundos, especifique quanto mais tempo, em segundos, de 1 segundo a 50 segundos. O que você especificar é adicionado aos 10 segundos padrão.

5. (Esta etapa é opcional) Faça outras alterações em sua política de antivírus. (Precisa de ajuda? Consulte [Configurações para Microsoft Defender Antivírus política em Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. Escolha **Próximo** e termine de configurar sua política.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Especificar o período de tempo de tempo estendido usando a Política de Grupo

Você pode usar a Política de Grupo para especificar um tempo de tempo estendido para verificações na nuvem.

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento [de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **MpEngine**.

4. Clique duas vezes em **Configurar verificação de nuvem estendida** e certifique-se de que a opção está habilitada. 

   Especifique o tempo extra para impedir que o arquivo seja executado enquanto aguarda uma determinação na nuvem. Especifique o tempo extra, em segundos, de 1 segundo a 50 segundos. O que você especificar é adicionado aos 10 segundos padrão.

5. Selecione **OK**.

 