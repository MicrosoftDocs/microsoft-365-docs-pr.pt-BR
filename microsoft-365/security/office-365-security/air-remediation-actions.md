---
title: Ações de correção no Office 365 investigação e resposta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Saiba mais sobre as ações de correção em recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955528"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a>Ações de correção após uma investigação automatizada no Office 365

## <a name="remediation-actions"></a>Ações de correção

[Recursos de investigação e resposta automatizados](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) no [Office 365 proteção avançada contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) plano 2 inclui determinadas ações de correção. Sempre que uma investigação automatizada estiver em execução ou concluída, você verá, em geral, uma ou mais ações de correção que exigem aprovação da equipe de operações de segurança para continuar. 

A tabela a seguir resume as ações de correção que estão atualmente disponíveis no Office 365 ATP. 

|Ação | Descrição |
|-----|-----|
|Bloquear URL (hora do clique) |Protege contra mensagens de email e documentos que contenham URLs mal-intencionadas. Isso permite o bloqueio de links mal-intencionados e quaisquer páginas da Web relacionadas por meio de [links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando o usuário clica em um link em um arquivo do Office existente ou em uma mensagem de email mais antiga. |
|Email de exclusão reversível  |Exclusão reversível de mensagens de email específicas da caixa de correio de um usuário. <br/>Uma mensagem excluída por software é movida para a pasta itens recuperáveis de um usuário e é mantida até que o período de retenção do item excluído expire. |
|Clusters de emails de exclusão reversível  |Exclusão reversível mensagens de email mal-intencionadas que correspondem a uma consulta de todas as caixas de correio dos usuários. <br/>As mensagens excluídas por software são movidas para a pasta itens recuperáveis dos usuários e são mantidas até que o período de retenção do item excluído expire. |
|Desativar o encaminhamento de emails externo |Remove uma regra de encaminhamento de uma caixa de correio de usuário final específica.|

> [!NOTE]
> No Office 365 ATP, nenhuma ação de correção é executada automaticamente. As ações de correção são executadas apenas após a aprovação da equipe de segurança da sua organização. 

## <a name="next-steps"></a>Próximas etapas

- [Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Office 365](air-review-approve-pending-completed-actions.md)

- [Detalhes e resultados de uma investigação automatizada no Office 365](air-view-investigation-results.md)

## <a name="related-articles"></a>Artigos relacionados

- [Investigação automatizada no Microsoft defender proteção avançada contra ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)