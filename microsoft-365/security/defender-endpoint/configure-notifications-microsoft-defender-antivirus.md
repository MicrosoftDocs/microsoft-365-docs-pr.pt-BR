---
title: Configure notificações Microsoft Defender Antivírus
description: Saiba como configurar e personalizar notificações de Microsoft Defender Antivírus padrão e adicionais em pontos finais.
keywords: notificações, defender, antivírus, ponto final, gerenciamento, administração
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
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>Configure as notificações que aparecem em pontos finais

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Em Windows 10, as notificações de aplicativos sobre detecção e remediação de malware são mais robustas, consistentes e concisas.

As notificações aparecem nos pontos finais quando acionadas manualmente e as varreduras programadas são concluídas e as ameaças são detectadas. Essas notificações também aparecem na Central de **Notificação**, e um resumo de varreduras e detecções de ameaças aparecem em intervalos de tempo regulares.

Você também pode configurar como as notificações padrão aparecem em pontos finais, como notificações para reinicialização ou quando uma ameaça foi detectada e remediada.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>Configure as notificações adicionais que aparecem em pontos finais

Você pode configurar a exibição de notificações adicionais, como resumos recentes de detecção de ameaças, no [aplicativo Segurança do Windows](microsoft-defender-security-center-antivirus.md) e com a Política de Grupo.

> [!NOTE]
> Em Windows 10, a versão 1607 do recurso foi chamada **de Notificações Aprimoradas** e poderia ser configurada sob **Windows Configurações**  >  **Update & Windows Defender de segurança**  >  . Nas configurações de Política de Grupo em todas as versões de Windows 10, são **chamadas notificações aprimoradas**.

> [!IMPORTANT]
> A desativação de notificações adicionais não desativará notificações críticas, como alertas de detecção e remediação de ameaças.

**Use o aplicativo Segurança do Windows para desativar notificações adicionais:**

1. Abra o aplicativo Segurança do Windows clicando no ícone do escudo na barra de tarefas ou pesquisando no menu iniciar para **segurança**.

2. Selecione o vírus & ladrilho **de proteção contra ameaças** (ou o ícone do escudo na barra de menu esquerda) e, em seguida, selecione **Configurações de proteção contra ameaças do Vírus &**

3. Role para a seção **Notificações** e clique em **Alterar as configurações de notificação**.

4. Deslize o interruptor para **Desligar** ou **Ligar** para desativar ou ativar notificações adicionais.

**Use a Política de Grupo para desativar notificações adicionais:**

1. No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.

2. No **Editor de Gerenciamento de Políticas de Grupo** vá para **configuração de computador**.

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Reporting**.

5. Clique duas **vezes Desligue notificações aprimoradas** e defina a opção para **Habilitar**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="configure-standard-notifications-on-endpoints"></a>Configure notificações padrão em pontos finais

Você pode usar a Política de Grupo para:

- Exibir texto adicional e personalizado em pontos finais quando o usuário precisa executar uma ação
- Ocultar todas as notificações em pontos finais
- Ocultar notificações de reinicialização em pontos finais

Ocultar notificações pode ser útil em situações em que você não pode ocultar toda a interface Microsoft Defender Antivírus. Consulte [Impedir que os usuários vejam ou interajam com a interface de usuário Microsoft Defender Antivírus](prevent-end-user-interaction-microsoft-defender-antivirus.md) para obter mais informações. 

> [!NOTE]
> Ocultar notificações só ocorrerá em pontos finais aos quais a política foi implantada. Notificações relacionadas a ações que devem ser tomadas (como uma reinicialização) ainda aparecerão no [painel de monitoramento de Microsoft Endpoint Manager Endpoint Protection e relatórios](/configmgr/protect/deploy-use/monitor-endpoint-protection). 

Consulte [Personalizar o aplicativo Segurança do Windows para sua organização](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) para obter instruções para adicionar informações de contato personalizadas às notificações que os usuários veem em suas máquinas.

**Use a Política de Grupo para ocultar notificações:**

1. No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.

2. No **Editor de Gerenciamento de Políticas de Grupo** vá para a **configuração de computador** e clique em **modelos administrativos**.

3. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > interface cliente**. 

4. Clique duas vezes **em Suprimir todas as notificações** e defina a opção para **Habilitar**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

**Use a política do grupo para ocultar notificações de reinicialização:**

1. No computador de gerenciamento de políticas de grupo, abra o [Console de Gerenciamento de Políticas de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que deseja configurar e clique em **Editar**.

2. No **Editor de Gerenciamento de Políticas de Grupo** vá para **configuração de computador**.

3. Clique **em Modelos Administrativos**.

4. Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > interface cliente**.

5. Clique duas vezes **em Suprimir notificações de reinicialização** e defina a opção para **Habilitado**. Clique em **OK**. Isso impedirá que notificações adicionais apareçam.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configure a interação do usuário final com Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md)
