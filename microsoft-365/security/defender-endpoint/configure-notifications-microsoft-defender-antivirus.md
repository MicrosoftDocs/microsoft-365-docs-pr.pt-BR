---
title: Configurar Microsoft Defender Antivírus notificações
description: Saiba como configurar e personalizar notificações Microsoft Defender Antivírus padrão e adicionais nos pontos de extremidade.
keywords: notificações, defender, antivírus, ponto de extremidade, gerenciamento, administrador
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572340"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configurar as notificações que aparecem nos pontos de extremidade

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Em Windows 10, as notificações de aplicativos sobre detecção e correção de malware são mais robustas, consistentes e concisas.

As notificações são exibidas nos pontos de extremidade quando as verificações acionadas manualmente e agendadas são concluídas e as ameaças são detectadas. Essas notificações também aparecem na Central de Notificações **,** e um resumo de verificações e detecções de ameaças aparecem em intervalos de tempo regulares.

Você também pode configurar como as notificações padrão aparecem nos pontos de extremidade, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configurar as notificações adicionais que aparecem nos pontos de extremidade

Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no aplicativo Segurança do Windows [e](microsoft-defender-security-center-antivirus.md) com a Política de Grupo.

> [!NOTE]
> No Windows 10, versão 1607, o  recurso era chamado notificações aprimoradas e poderia ser configurado em **Windows Configurações**  >  **Atualização &** segurança  >  **Windows Defender**. Nas configurações da Política de Grupo em todas as versões do Windows 10, ela é chamada **notificações aprimoradas**.

> [!IMPORTANT]
> Desabilitar notificações adicionais não desabilitará notificações críticas, como alertas de detecção e correção de ameaças.

**Use o Segurança do Windows para desabilitar notificações adicionais:**

1. Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.

2. Selecione **O &** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e, em seguida, selecione **Configurações** de proteção contra vírus & ameaças

3. Role até a **seção Notificações** e clique em **Alterar configurações de notificação**.

4. Deslize a opção para **Off** ou **On** para desabilitar ou habilitar notificações adicionais.

**Use a Política de Grupo para desabilitar notificações adicionais:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Reporting**.

5. Clique duas **vezes em Desativar notificações aprimoradas** e de definir a opção como **Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="configure-standard-notifications-on-endpoints"></a>Configurar notificações padrão em pontos de extremidade

Você pode usar a Política de Grupo para:

- Exibir texto adicional e personalizado nos pontos de extremidade quando o usuário precisar executar uma ação
- Ocultar todas as notificações nos pontos de extremidade
- Ocultar notificações de reinicialização nos pontos de extremidade

Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a Microsoft Defender Antivírus interface. Consulte [Impedir que os usuários vejam ou interajam](prevent-end-user-interaction-microsoft-defender-antivirus.md) com Microsoft Defender Antivírus interface do usuário para obter mais informações. 

> [!NOTE]
> Ocultar notificações só ocorrerá nos pontos de extremidade aos quais a política foi implantada. As notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda serão exibidas no painel de monitoramento Microsoft Endpoint Manager Endpoint Protection [relatórios.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

Consulte [Personalizar o aplicativo Segurança do Windows para sua](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) organização para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em seus máquinas.

**Use a Política de Grupo para ocultar notificações:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Interface do Cliente.** 

4. Clique duas vezes **em Suprimir todas as notificações** e de definir a opção como **Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

**Use a Política de Grupo para ocultar notificações de reinicialização:**

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Interface do Cliente.**

5. Clique duas vezes **em Suprime notificações de reinicialização** e de definir a opção **como Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar a interação do usuário final com Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)
