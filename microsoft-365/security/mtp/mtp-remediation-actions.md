---
title: Ações de correção no Microsoft 365 Defender
description: Obter uma visão geral das ações de correção que seguem investigações automatizadas no Microsoft 365 Defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932845"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Ações de correção no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada no Microsoft 365 Defender, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são realizadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são realizadas no conteúdo do email. Investigações automatizadas são concluídas após ações de correção, aprovadas ou rejeitadas.

> [!IMPORTANT]
> Se as ações de correção são realizadas automaticamente ou somente mediante aprovação depende de determinadas configurações, como a forma como os níveis de automação. Para saber mais, consulte os seguintes artigos:
> - [Configurar seus recursos automatizados de investigação e resposta no Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Como as ameaças são remediadas em dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Ameaças e ações de correção no conteúdo de colaboração & email](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

A tabela a seguir resume as ações de correção com suporte no momento no Microsoft 365 Defender: 

|Ações de correção do dispositivo (ponto de extremidade)  |Ações de correção de email  |
|---------|---------|
|- Coletar pacote de investigação <br/>- Isolar dispositivo (esta ação pode ser desfeita)<br/>- Computador de redação <br/>- Liberar execução de código <br/>- Liberar da quarentena <br/>- Exemplo de solicitação <br/>- Restringir a execução de código (esta ação pode ser desfeita) <br/>- Executar a verificação antivírus <br/>- Parar e colocar em quarentena      |- Bloquear URL (hora do clique)<br/>- Excluir mensagens de email ou clusters de forma suave<br/>- Colocar o email em quarentena<br/>- Colocar em quarentena um anexo de email<br/>- Desativar o encaminhamento de email externo          |

Ações de correção, se a aprovação pendente ou já concluída, podem ser exibidas na Central [de Ações.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Ações de correção que seguem investigações automatizadas

Quando uma investigação automatizada é concluída, um veredito é atingido para cada evidência envolvida. Dependendo do veredito, as ações de correção são identificadas. Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação. Tudo depende de como [a investigação e resposta automatizadas são configuradas.](mtp-configure-auto-investigation-response.md)

A tabela a seguir lista os possíveis verditos e resultados:

| Verdito    | Área    | Resultados|
|------|------|------|
| Mal-intencionado    | Dispositivos (pontos de extremidade)    | As ações de correção são realizadas [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) automaticamente (supondo que os grupos de dispositivos da sua organização estão definidos como **Completo - correção de ameaças automaticamente**)|
| Mal-intencionado    | Conteúdo do email (URLs ou anexos) | As ações de correção recomendadas estão aguardando aprovação|
| Suspeito    | Conteúdo de dispositivos ou emails | As ações de correção recomendadas estão aguardando aprovação|
| Nenhuma ameaça encontrada    | Conteúdo de dispositivos ou emails    | Nenhuma ação de correção é necessária|


## <a name="remediation-actions-that-are-taken-manually"></a>Ações de correção que são realizadas manualmente

Além das ações de correção que seguem investigações automatizadas, sua equipe de operações de segurança pode realizar determinadas ações de correção manualmente. Elas incluem as seguintes ações:

- Ação manual do dispositivo, como isolamento de dispositivo ou quarentena de arquivo.
- Ação manual de email, como exclusão suave de mensagens de email. 
- [Ação de busca](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) avançada em dispositivos ou emails.
- [Ação](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) do Explorer no conteúdo de email, como mover emails para lixo eletrônico, excluir emails de forma fácil ou excluir emails ilegíveis.
- Ação [manual de resposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) ao vivo, como excluir um arquivo, interromper um processo e remover uma tarefa agendada.
- Ação de resposta ao vivo com o Microsoft Defender para [APIs](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)de ponto de extremidade, como isolar um dispositivo, executar uma verificação antivírus e obter informações sobre um arquivo. 

## <a name="next-steps"></a>Próximas etapas

- [Visite a Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprovar ou rejeitar ações pendentes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta](mtp-autoir-report-false-positives-negatives.md)
