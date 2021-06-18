---
title: Ocultar a Microsoft Defender Antivírus interface
description: Você pode ocultar o tile de proteção contra vírus e ameaças no Segurança do Windows aplicativo.
keywords: bloqueio da interface do usuário, modo sem cabeça, ocultar aplicativo, ocultar configurações, ocultar interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007653"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>Impedir que os usuários vejam ou interajam com a Microsoft Defender Antivírus do usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode usar a Política de Grupo para impedir que os usuários nos pontos de extremidade possam ver a Microsoft Defender Antivírus interface. Você também pode impedi-los de pausar verificações.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>Ocultar a Microsoft Defender Antivírus interface

No Windows 10, versões 1703, ocultar Microsoft Defender Antivírus interface ocultará as notificações do Microsoft Defender Antivírus e impedirá que o & de proteção contra & vírus apareça no aplicativo Segurança do Windows.

Com a configuração definida como **Habilitado:**

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Segurança do Windows sem o ícone de escudo e a seção proteção contra vírus e ameaças":::

Com a configuração definida como **Desabilitada** ou não configurada:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Captura de tela de Segurança do Windows com ícone de escudo e seções de proteção contra ameaças":::

>[!NOTE]
>Ocultar a interface também impedirá que Microsoft Defender Antivírus notificações apareçam no ponto de extremidade. As notificações do Microsoft Defender para Ponto de Extremidade ainda serão exibidas. Você também pode configurar individualmente [as notificações que aparecem nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)

Em versões anteriores Windows 10, a configuração ocultará a interface Windows Defender cliente. Se o usuário tentar abri-lo, ele receberá um aviso informando: "O administrador do sistema tem acesso restrito a esse aplicativo".

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Mensagem de aviso quando o modo sem cabeça estiver habilitado Windows 10, versões anteriores a 1703":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>Usar a Política de Grupo para ocultar a interface do Microsoft Defender AV dos usuários

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Interface do Cliente.**

5. Clique duas vezes na **configuração Habilitar modo de interface** do usuário sem cabeça e de definir a opção **como Habilitado**. Clique em **OK**. 

Consulte [Impedir que os usuários modifiquem localmente](configure-local-policy-overrides-microsoft-defender-antivirus.md) as configurações de política para obter mais opções sobre como impedir que os usuários formem modificar a proteção em seus PCs.

## <a name="prevent-users-from-pausing-a-scan"></a>Impedir que os usuários pausem uma verificação

Você pode impedir que os usuários pausem verificações, o que pode ser útil para garantir que as verificações agendadas ou sob demanda não sejam interrompidas pelos usuários.

> [!NOTE]
> Essa configuração não é suportada no Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>Usar a Política de Grupo para impedir que os usuários pausem uma verificação

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. Usando o **Editor de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Scan**.

5. Clique duas vezes na **configuração Permitir que os usuários pausem a verificação** e de definir a opção como **Desabilitada**. Clique em **OK**. 

## <a name="related-articles"></a>Artigos relacionados

- [Configurar as notificações exibidas nos pontos de extremidade](configure-notifications-microsoft-defender-antivirus.md)

- [Configurar a interação do usuário final com Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)