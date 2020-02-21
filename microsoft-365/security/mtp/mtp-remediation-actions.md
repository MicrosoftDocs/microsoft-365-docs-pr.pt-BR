---
title: Ações de correção em recursos de investigação e resposta automatizados no Microsoft Threat Protection
description: Obter uma visão geral dos recursos de investigação e resposta automatizados na Proteção contra Ameaça da Microsoft
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
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175895"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Ações de correção em recursos de investigação e resposta automatizados no Microsoft Threat Protection

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Os recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft incluem determinadas ações de correção. Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade. Outras ações de correção são executadas no conteúdo do email.

A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft: 

|Ações de correção de pontos de extremidade  |Ações de correção de email  |
|---------|---------|
|Arquivo de quarentena<br/>Remover chave do registro<br/>Finalizar processo <br/>Parar serviço <br/>Remover chave do registro <br/>Desabilitar o driver <br/>Remover tarefa agendada      |Exclusão reversível de mensagens de emails ou clusters<br/>Bloquear URL (hora do clique)<br/>Desativar o encaminhamento de emails externo          |

Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Saiba mais sobre a Central de Ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
