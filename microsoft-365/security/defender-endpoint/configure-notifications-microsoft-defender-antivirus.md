---
title: Configurar Microsoft Defender Antivírus notificações
description: Saiba como configurar e personalizar notificações padrão e outras Microsoft Defender Antivírus nos pontos de extremidade.
keywords: notificações, defender, antivírus, ponto de extremidade, gerenciamento, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985403"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>Configurar Microsoft Defender Antivírus notificações que aparecem nos pontos de extremidade

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Em Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas. Microsoft Defender Antivírus as notificações aparecem nos pontos de extremidade quando as verificações são concluídas e as ameaças são detectadas. As notificações seguem verificações agendadas e disparadas manualmente. Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.

Se você faz parte da equipe de segurança da sua organização, pode configurar como as notificações aparecem nos pontos de extremidade, como notificações que solicitam uma reinicialização do sistema ou que indicam que uma ameaça foi detectada e remediada.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>Configurar notificações antivírus usando a Política de Grupo ou o Segurança do Windows app

Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo Segurança do Windows [e](microsoft-defender-security-center-antivirus.md) com a Política de Grupo.

> [!NOTE]
> No Windows 10, versão 1607, o  recurso era chamado notificações aprimoradas e foi configurado em **Windows Configurações**  >  **Atualização & segurança**  >  **Windows Defender**. Nas configurações da Política de Grupo para todas as versões do Windows 10, o recurso de notificação é chamado **notificações aprimoradas.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>Usar a Política de Grupo para desabilitar notificações adicionais

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

4. Selecione **Modelos administrativos**.

5. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus** > Reporting**.

6. Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**. Em seguida, selecione **OK**. Isso impedirá que notificações adicionais apareçam.

> [!IMPORTANT]
> Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>Usar o Segurança do Windows para desabilitar notificações adicionais

1. Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.

2. Selecione **O &** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, selecione **Configurações** de proteção contra vírus & ameaças

3. Role até a **seção Notificações** e selecione **Alterar configurações de notificação**.

4. Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.

> [!IMPORTANT]
> Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>Configurar notificações padrão em pontos de extremidade usando a Política de Grupo

Você pode usar a Política de Grupo para:

- Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação
- Ocultar todas as notificações nos pontos de extremidade
- Ocultar notificações de reinicialização nos pontos de extremidade

Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a Microsoft Defender Antivírus interface. Consulte [Impedir que os usuários vejam ou interajam](prevent-end-user-interaction-microsoft-defender-antivirus.md) com Microsoft Defender Antivírus interface do usuário para obter mais informações. Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada. As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento Microsoft Endpoint Manager Endpoint Protection [relatórios.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Para adicionar informações de contato personalizadas às notificações do ponto de extremidade, consulte [Personalizar o aplicativo Segurança do Windows para sua organização.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>Usar a Política de Grupo para ocultar notificações

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

3. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador e selecione **Modelos administrativos.**

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **interface do cliente.** 

5. Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**. 

6. Selecione **OK**. Isso impedirá que notificações adicionais apareçam.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>Usar a Política de Grupo para ocultar notificações de reinicialização

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).

2. Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **interface do cliente.**

5. Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**. 

5. Selecione **OK**. Isso impedirá que notificações adicionais apareçam.

