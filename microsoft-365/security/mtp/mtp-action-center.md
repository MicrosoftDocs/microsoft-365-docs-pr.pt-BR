---
title: Vá para a Central de ações para exibir e aprovar suas tarefas automatizadas de investigação e correção
description: Use a Central de ações para exibir detalhes sobre investigação automatizada e aprovar ações pendentes
keywords: Central de ações, proteção contra ameaças, investigação, alerta, pendente, automatizado, detecção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 45e02e4ce7d5d813cc8215a1f27ed9c415707cb1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930421"
---
# <a name="the-action-center"></a>A Central de Ações

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Use a Central de ações ( ) para ver os resultados de investigações atuais e passadas nos dispositivos e caixas de [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) correio da sua organização. Dependendo do tipo de ameaça e veredito [resultante,](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) as ações de correção podem ocorrer automaticamente ou mediante aprovação da equipe de operações de segurança da sua organização. Todas as ações de correção, se estão aguardando aprovação ou que já foram aprovadas, estão consolidadas na Central de ações. 

![Central de Ações](../../media/air-actioncenter.png)

## <a name="a-single-pane-of-glass-experience"></a>Uma experiência de "painel único"

A Central de ações fornece uma experiência de "painel único" para tarefas, como:
- Aprovar ações de correção pendentes;
- Exibir um log de auditoria de ações de correção já aprovadas; e
- Revendo as ações de correção concluídas.

Sua equipe de operações de segurança pode operar de forma mais eficaz e eficiente, porque a Central de Ações fornece uma visão abrangente do Microsoft 365 Defender no trabalho.

## <a name="go-to-the-action-center"></a>Ir para a Central de ações

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de ações**. 

3. Na Central de ações, você verá duas **guias:** Pendente e **Histórico.**

    - A guia **Pendente** lista as investigações que exigem revisão e aprovação de alguém na sua equipe de operações de segurança para continuar. Certifique-se de revisar e executar ações em itens pendentes que você vê aqui.

    - A guia **Histórico** lista investigações anteriores e ações de correção que foram executadas automaticamente. Você pode exibir dados do dia, semana, mês ou seis meses anteriores.

4. Para mostrar somente as colunas que você deseja ver, selecione **Personalizar colunas**.<br/>![Central de Ações no Microsoft 365 Defender](../../media/mtp-action-center.png)

5. Selecione um item na lista para exibir mais detalhes sobre uma investigação. A visualização de detalhes da investigação abrirá.<br/>![Detalhes da investigação](../../media/mtp-air-investdetails.png)

    - Se a investigação pertencer ao conteúdo do email (como, por exemplo, a entidade é uma caixa de correio), os detalhes da investigação serão abertos no Centro de Conformidade & Segurança ( [https://protection.office.com/threatinvestigation](https://protection.office.com/threatinvestigation) ). 

    - Se a investigação envolve um dispositivo, detalhes de investigação abrirão na central de segurança ([https://security.microsoft.com](https://security.microsoft.com)). 

> [!TIP]
> Se você acha que algo foi perdido ou detectado incorretamente pelos recursos de investigação e resposta automatizadas no Microsoft 365 Defender, nos avise! Veja como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta [(AIR) no Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

## <a name="available-actions"></a>Ações disponíveis

À medida que as ações de correção são tomadas, elas são listadas na guia **Histórico** da Central de Ações. Essas ações incluem o seguinte:

- Coletar pacote de investigação 
- Isolar dispositivo (essa ação pode ser desfeita) 
- Computador de redação 
- Liberar execução de código 
- Liberar da quarentena 
- Exemplo de solicitação 
- Restringir a execução de código (essa ação pode ser desfeita) 
- Executar a verificação antivírus 
- Parar e colocar em quarentena 

> [!NOTE]
> Além das ações de correção que são realizadas automaticamente, sua equipe de operações de segurança pode realizar ações manuais para lidar com ameaças detectadas. Para obter mais informações sobre ações de correção automáticas e manuais, consulte [Ações de correção.](mtp-remediation-actions.md)

## <a name="action-source"></a>Origem da ação

(**NOVO!**) Como você sabe, o Microsoft 365 Defender reúne recursos automatizados de investigação e resposta em vários serviços, como [o Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Ponto de Extremidade e o Microsoft Defender para Office [365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) A central de ações nova e  aprimorada agora inclui uma coluna de origem de ação que informa de onde cada ação de correção veio. 

A tabela a seguir descreve os valores **de origem de ação possíveis:**

| Valor de origem da ação | Descrição |
|:-----|:---|
| **Ação manual do dispositivo** | Uma ação manual realizada em um dispositivo. Exemplos incluem [isolamento de dispositivo ou](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network) quarentena de [arquivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#stop-and-quarantine-files) |
| **Ação manual de email** | Uma ação manual realizada no email. Um exemplo inclui a exclusão suave de mensagens de email ou [a correção de uma mensagem de email.](https://docs.microsoft.com/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365) |
| **Ação automatizada do dispositivo** | Uma ação automatizada realizada em uma entidade, como um arquivo ou processo. Exemplos de ações automatizadas incluem o envio de um arquivo para a quarentena, a interrupção de um processo e a remoção de uma chave do Registro. (Consulte [Ações de correção no Microsoft Defender para o ponto de extremidade.)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-auto-investigation#remediation-actions) |
| **Ação de email automatizada** | Uma ação automatizada realizada no conteúdo do email, como uma mensagem de email, anexo ou URL. Exemplos de ações automatizadas incluem a exclusão suave de mensagens de email, o bloqueio de URLs e a exclusão do encaminhamento de emails externos. (Consulte [Ações de correção no Microsoft Defender para Office 365.)](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions) |
| **Ação de busca avançada** | Ações tomadas em dispositivos ou emails com [busca avançada.](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-overview) |
| **Ação do Explorer** | Ações tomadas no conteúdo de email com o [Explorer.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) |
| **Ação manual de resposta ao vivo** | Ações tomadas em um dispositivo com [resposta ao vivo.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) Exemplos incluem a exclusão de um arquivo, a interrupção de um processo e a remoção de uma tarefa agendada. |
| **Ação de resposta ao vivo** | Ações tomadas em um dispositivo com [o Microsoft Defender para APIs de ponto de extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis) Exemplos de ações incluem isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo. |

## <a name="required-permissions-for-action-center-tasks"></a>Permissões necessárias para tarefas da Central de ações

Para aprovar ou rejeitar ações pendentes na Central de ações, você deve ter permissões atribuídas conforme listado na tabela a seguir:

|Ação de correção |Funções e permissões necessárias |
|--|----|
|Correção do Microsoft Defender para Pontos de Extremidade (dispositivos) |Função Administrador de Segurança atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>---ou---<br/>Função de ações de correção ativas atribuídas no Microsoft Defender para Ponto de Extremidade <br/> <br/> Para saber mais, confira os seguintes recursos: <br/>- [Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Criar e gerenciar funções para controle de acesso baseado em função (Microsoft Defender para Ponto de Extremidade)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles)  |
|Correção do Microsoft Defender para Office 365 (conteúdo do Office e email)  |Função Administrador de Segurança atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com))<br/>---e--- <br/>Função pesquisar e limpar atribuída ao Centro de Conformidade & Segurança ( [https://protection.office.com](https://protection.office.com) ) <br/><br/>**IMPORTANTE:**& se você tiver a função Administrador de Segurança atribuída apenas no Centro de Conformidade e Segurança, não poderá acessar a Central de Ações ou os recursos do Microsoft 365 Defender. Você deve ter a função Administrador de Segurança atribuída no Azure Active Directory ou no centro de administração do Microsoft 365. <br/><br/>Para saber mais, confira os seguintes recursos: <br/>- [Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)<br/>- [Permissões no Centro de Conformidade & segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) |

> [!NOTE]
> Os usuários que têm a função Administrador Global atribuída no Azure Active Directory podem aprovar ou rejeitar qualquer ação pendente na Central de ações. No entanto, como uma prática recomendada, sua organização deve limitar o número de pessoas que têm a função de Administrador Global atribuída. É recomendável usar o Administrador de Segurança, Ações de correção ativa e as funções Pesquisar e Limpar, listadas acima, para permissões da Central de ações.

## <a name="next-steps"></a>Próximas etapas 

- [Aprovar ou rejeitar ações pendentes após uma investigação automatizada](mtp-autoir-actions.md)
- [Exibir os resultados de uma investigação automatizada](mtp-autoir-results.md)

