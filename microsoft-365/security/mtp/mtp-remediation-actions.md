---
title: Ações de correção após as investigações automatizadas no Microsoft Threat Protection
description: Obter uma visão geral das ações de correção que seguem as investigações automatizadas no Microsoft Threat Protection
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 5f6e7a1a3f9c19a0ecfdca922505d2b27ad466c6
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412305"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Ações de correção após as investigações automatizadas no Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


## <a name="remediation-actions"></a>Ações de correção

Durante e após uma investigação automatizada da proteção contra ameaças da Microsoft, as ações de correção são identificadas para itens mal-intencionados ou suspeitos. Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são executadas no conteúdo do email. Investigações automatizadas concluídas depois que as ações de correção são tomadas, aprovadas ou rejeitadas.

A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft: 

|Ações de correção de dispositivo (ponto de extremidade)  |Ações de correção de email  |
|---------|---------|
|– Coletar pacote de investigação <br/>-Isolar dispositivo (esta ação pode ser desfeita)<br/>-Máquina externamente <br/>-Liberar execução de código <br/>– Liberar da quarentena <br/>– Exemplo de solicitação <br/>– Restringir a execução de código (essa ação pode ser desfeita) <br/>– Executar verificação antivírus <br/>– Parar e colocar em quarentena      |-Bloquear URL (tempo de clique)<br/>– Excluir mensagens de email ou clusters<br/>– Email de quarentena<br/>-Colocar um anexo de email em quarentena<br/>– Desativar o encaminhamento de email externo          |

Ações de correção, se a aprovação pendente ou já concluída, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>As ações de correção seguem investigações automatizadas

Quando uma investigação automatizada é concluída, um veredicto é alcançado para cada evidência envolvida. Dependendo do veredicto, as ações de correção serão identificadas. Em alguns casos, as ações de correção são executadas automaticamente, em outros casos, as ações de correção aguardam aprovação. Tudo isso depende de como a [investigação e a resposta automáticas são configuradas](mtp-configure-auto-investigation-response.md).

A tabela a seguir lista os possíveis verditos e resultados:

|Verdito    |Área    |Resultados|
|------|------|------|
|Mal-intencionado    |Dispositivos (pontos de extremidade)    |As ações de correção são realizadas automaticamente (supondo que os [grupos de dispositivos](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) da sua organização estejam definidos para **corrigir ameaças automaticamente**)|
|Mal-intencionado    |Conteúdo do email (URLs ou anexos) | As ações de correção recomendadas estão aguardando aprovação|
|Suspeito    |Conteúdo de dispositivos ou emails |As ações de correção recomendadas estão aguardando aprovação|
|Nenhuma ameaça encontrada    |Conteúdo de dispositivos ou emails    |Nenhuma ação de correção é necessária|

> [!IMPORTANT]
> Se as ações de correção serão realizadas automaticamente ou apenas após a aprovação dependerá de determinadas configurações, como as políticas de grupo de dispositivos da sua organização. Para saber mais, confira os seguintes artigos:
> - [Configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection](mtp-configure-auto-investigation-response.md)
> - [Como as ameaças são corrigidas nos dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Próximas etapas

- [Visite a Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Aprovar ou rejeitar ações pendentes](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Lidar com falsos positivos/negativos em recursos de investigação e resposta automatizados](mtp-autoir-report-false-positives-negatives.md)
