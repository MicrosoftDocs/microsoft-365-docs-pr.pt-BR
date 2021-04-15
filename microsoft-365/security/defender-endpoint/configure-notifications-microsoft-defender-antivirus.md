---
title: Configurar notificações do Microsoft Defender Antivírus
description: Saiba como configurar e personalizar notificações padrão e adicionais do Microsoft Defender Antivírus nos pontos de extremidade.
keywords: notificações, defender, antivírus, ponto de extremidade, gerenciamento, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765090"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurar as notificações que aparecem nos pontos de extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

No Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas.

As notificações são exibidas nos pontos de extremidade quando as verificações acionadas manualmente e agendadas são concluídas e as ameaças são detectadas. Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.

Você também pode configurar como as notificações padrão aparecem nos pontos de extremidade, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurar as notificações adicionais que aparecem nos pontos de extremidade

Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo segurança do [Windows](microsoft-defender-security-center-antivirus.md) e com a Política de Grupo.

> [!NOTE]
> No Windows 10, versão 1607, o recurso era chamado notificações aprimoradas e poderia ser configurado em **Windows Settings** Update &   >  **segurança**  >  **Windows Defender**. Nas configurações da Política de Grupo em todas as versões do Windows 10, ela é chamada **de Notificações aprimoradas.**

> [!IMPORTANT]
> Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.

**Use o aplicativo segurança do Windows para desabilitar notificações adicionais:**

1. Abra o aplicativo segurança do Windows clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.

2. Clique no **&** de proteção contra ameaças (ou o ícone de escudo na barra de **menus** esquerda) e, em seguida, o rótulo de configurações de proteção contra ameaças & vírus:

    ![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

3. Role até a **seção Notificações** e clique em **Alterar configurações de notificação**.

4. Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.

**Use a Política de Grupo para desabilitar notificações adicionais:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > Reporting**.

5. Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurar notificações padrão em pontos de extremidade

Você pode usar a Política de Grupo para:

- Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação
- Ocultar todas as notificações nos pontos de extremidade
- Ocultar notificações de reinicialização nos pontos de extremidade

Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a interface do Microsoft Defender Antivírus. Confira [Impedir que os usuários vejam ou interajam com a interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) do usuário do Microsoft Defender Antivírus para obter mais informações. 

> [!NOTE]
> Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada. As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento e relatórios do [Microsoft Endpoint Manager Endpoint Protection.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Confira [Personalizar o aplicativo de Segurança](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) do Windows para sua organização para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em seus computadores.

**Use a Política de Grupo para ocultar notificações:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.** 

4. Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

**Use a Política de Grupo para ocultar notificações de reinicialização:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para componentes do Windows > interface do Cliente do **Microsoft Defender Antivírus >.**

5. Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar a interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)