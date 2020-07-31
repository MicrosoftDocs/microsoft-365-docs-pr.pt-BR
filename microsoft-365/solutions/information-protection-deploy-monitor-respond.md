---
title: Monitorar e responder a incidentes de privacidade de dados em sua organização
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Use as políticas de auditoria e de alerta e as solicitações de entidades de dados para monitorar e responder a incidentes de dados pessoais.
ms.openlocfilehash: 8fdba5799ca9ee97a013c1322e5e79f6bf38764a
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/29/2020
ms.locfileid: "46522068"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Monitorar e responder a incidentes de privacidade de dados em sua organização

Os recursos do Microsoft 365 estão disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você opera os recursos relacionados. Ter processos, procedimentos e outras documentações para cada um deles também pode ser importante para demonstrar conformidade com órgãos regulamentares.

Entre eles: 

- Políticas de auditoria e alertas
- Solicitações de entidades de dados (incluindo pesquisa de conteúdo e descoberta eletrônica)
- Ferramentas e relatórios adicionais investigativos

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Regulamentações de privacidade de dados que afetam o uso de ferramentas de monitoramento e resposta

Aqui está uma lista de exemplos de regulamentos de privacidade de dados que podem se relacionar aos controles de governança de informações:

- LGPD artigo 46
- LGPD artigo 48
- RGPD artigo (5) (1) (f)
- Artigo RGPD (15) (1) (e)
- HIPAA-ALTA TECNOLOGIA (45 C.F.R. 164.308 (a) (1) (II) (D))
- HIPAA-ALTA TECNOLOGIA (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-ALTA TECNOLOGIA (45 C.F.R. 164.312 (b))
- CCPA (1798.105 (c))

Para obter mais informações, consulte [avaliar riscos de privacidade de dados e identificar informações confidenciais](information-protection-deploy-assess.md).

Os regulamentos de privacidade de dados geralmente chamam os seguintes itens para monitoramento e resposta:

- Auditoria, alerta e emissão de relatórios para atividades relacionadas ao armazenamento, compartilhamento e processamento de dados pessoais
- A capacidade de responder a uma solicitação de entidades de dados (DSR) e, em alguns casos, executar investigação e outras medidas administrativas para cumprir essas solicitações.

Sua organização também pode desejar realizar atividades de monitoramento e resposta para outros fins, como outras necessidades de conformidade ou por motivos de negócios. O estabelecimento do esquema de monitoramento e resposta para privacidade de dados deve ser feito como parte do planejamento, da implementação e do gerenciamento de resposta e monitoramento geral.

Para ajudá-lo a começar a usar um esquema de monitoramento e resposta no Microsoft 365 for Data Privacy Regulations, este artigo lista recursos úteis no Microsoft 365 para responder a perguntas como: 

- Que espécie de monitoramento de dia a dia, técnicas investigativas e de relatórios estão disponíveis para os diferentes tipos de dados e fontes?
- Quais mecanismos serão necessários para lidar com as solicitações de entidades de dados (DSRs) e quaisquer ações corretivas, como anonimato, redação e exclusão.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Auditoria e políticas de alerta no centro de conformidade e segurança

Consulte estes artigos para configurar auditorias, auditoria avançada e políticas de alerta:

- [Auditoria unificada](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Auditoria de caixa de correio](../compliance/enable-mailbox-auditing.md)
- [Auditoria avançada](../compliance/advanced-audit.md)
- [Políticas de alerta](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de entidades de dados para o RGPD e o CCPA

Consulte [solicitações de entidades de dados para o rgpd e o CCPA](../compliance/gdpr-dsr-office365.md) para obter informações sobre como responder a um DSR no Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Gerenciar usuários excluídos no Microsoft Stream

Para o Microsoft Stream, quando um usuário é excluído do Azure Active Directory (Azure AD), se o nome tiver sido associado a um vídeo de fluxo Postado antes desse ponto, o endereço de email permanecerá associado ao vídeo. Consulte [Manage Deleted users from Microsoft Stream](https://docs.microsoft.com/stream/managing-deleted-users) para removê-lo.

## <a name="additional-investigative-tools"></a>Ferramentas adicionais investigativas

Aqui estão duas ferramentas adicionais que podem ser úteis para monitorar, investigar e corrigir incidentes relacionados à privacidade de dados em sua organização:

- [Gerenciamento de risco do insider no microsoft 365](../compliance/insider-risk-management.md), um recurso do centro de administração de conformidade da Microsoft para ajudar a minimizar o risco interno, permitindo que você detecte, investigue e execute ações sobre atividades arriscadas em sua organização.
- [Investigações de dados no microsoft 365](../compliance/overview-data-investigations.md), um recurso do centro de administração de conformidade da Microsoft para pesquisar dados confidenciais, maliciosos ou incorretos no Microsoft 365 e, em seguida, investigue o que aconteceu em tomar as ações apropriadas para corrigir o incidente.
