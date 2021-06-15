---
title: Definir como os dispositivos móveis são atualizados por Microsoft Defender Antivírus
description: Gerencie como dispositivos móveis, como laptops, devem ser atualizados com Microsoft Defender Antivírus de proteção.
keywords: atualizações, proteção, agendar atualizações, bateria, dispositivo móvel, laptop, bloco de anotações, aceitação, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926002"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Dispositivos móveis e VMs podem exigir mais configuração para garantir que o desempenho não seja afetado pelas atualizações.

Há duas configurações úteis para esses dispositivos:

- Optar pelo Microsoft Update em computadores móveis sem uma conexão WSUS
- Impedir atualizações de inteligência de segurança ao executar na energia da bateria

Os artigos a seguir também podem ser úteis nessas situações:
- [Configurando verificações agendadas e de catch-up](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Guia de implantação do Microsoft Defender Antivírus em um ambiente virtual de área de trabalho (VDI)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Optar pelo Microsoft Update em computadores móveis sem uma conexão WSUS

Você pode usar o Microsoft Update para manter a inteligência de segurança em dispositivos móveis Microsoft Defender Antivírus atualizada quando eles não estão conectados à rede corporativa ou não têm uma conexão WSUS. 

Isso significa que as atualizações de proteção podem ser entregues a dispositivos (por meio do Microsoft Update) mesmo que você tenha definido o WSUS para substituir o Microsoft Update.

Você pode optar pelo Microsoft Update no dispositivo móvel de uma das seguintes maneiras:

- Altere a configuração com a Política de Grupo.
- Use um VBScript para criar um script e execute-o em cada computador em sua rede.
- Opte manualmente por todos os computadores em sua rede por meio **do menu Configurações.**

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Usar a Política de Grupo para optar pelo Microsoft Update

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Selecione **Políticas** e **modelos administrativos.**

4. Expanda a árvore para **Windows**  >  **componentes Microsoft Defender Antivírus**  >  **Atualizações de Assinatura.**

5. Definir **Permitir atualizações de inteligência de segurança do Microsoft Update** como **Habilitado** e selecione  **OK**.


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Usar um VBScript para optar pelo Microsoft Update

1. Use as instruções no artigo do MSDN [Opt-In to Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) para criar o VBScript.

2. Execute o VBScript criado em cada computador em sua rede.

### <a name="manually-opt-in-to-microsoft-update"></a>Optar manualmente pelo Microsoft Update

1. Abra **Windows Atualização** em Atualizar **&** configurações de segurança no computador em que você deseja optar.

2. Selecione **Opções** avançadas.

3. Marque a caixa de seleção para **Dar-me atualizações para outros produtos Microsoft quando eu atualizar Windows**.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Impedir atualizações de inteligência de segurança ao executar na energia da bateria

Você pode configurar o Microsoft Defender Antivírus para baixar apenas atualizações de proteção quando o computador estiver conectado a uma fonte de energia com fio. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Usar a Política de Grupo para impedir atualizações de inteligência de segurança na energia da bateria

1.  Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))escolha o Objeto de Política de Grupo que você deseja configurar e abra-o para edição.

2.  No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3.  Selecione **Políticas** e **modelos administrativos.**

4.  Expanda a árvore para **Windows componentes** Microsoft Defender Antivírus Atualizações de Assinatura e, em seguida, de definir Permitir atualizações de inteligência de segurança ao executar a energia da bateria  >    >  como **Desabilitada**.  Em seguida, selecione **OK**. 

Essa ação impede que as atualizações de proteção baixem quando o computador está com bateria.

## <a name="related-articles"></a>Artigos relacionados

- [Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Atualizar e gerenciar Microsoft Defender Antivírus no Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)