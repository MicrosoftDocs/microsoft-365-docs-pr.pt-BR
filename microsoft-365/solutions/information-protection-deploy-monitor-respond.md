---
title: Monitorar e responder a incidentes de privacidade de dados em sua organização
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Use políticas de auditoria e alerta e solicitações de assunto de dados para monitorar e responder a incidentes de dados pessoais.
ms.openlocfilehash: 3ae0f2a6528f6188500c7cee7732c6447013eaa6
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749582"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Monitorar e responder a incidentes de privacidade de dados em sua organização

Os recursos do Microsoft 365 estão disponíveis para ajudá-lo a monitorar, investigar e responder a incidentes de privacidade de dados em sua organização à medida que você operacionaliza os recursos relacionados. Ter processos, procedimentos e outras documentações para cada um deles também pode ser importante para demonstrar a conformidade com órgãos regulamentadores.

Entre eles: 

- Políticas de auditoria e alerta
- Solicitações de assunto de dados (incluindo pesquisa de conteúdo e Descoberta e Descoberta)
- Ferramentas e relatórios de investigação adicionais

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>Regulamentações de privacidade de dados que impactam no uso de ferramentas de monitoramento e resposta

Aqui está um exemplo de listagem de regulamentações de privacidade de dados que podem estar relacionadas a controles de governança de informações:

- Artigo 46 do LGPD
- Artigo 48 do LGPD
- Artigo RGPD (5)(1)(f)
- Artigo RGPD (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Para obter mais informações, consulte [Avaliar os riscos de privacidade de dados e identificar informações confidenciais.](information-protection-deploy-assess.md)

Os regulamentos de privacidade de dados geralmente chamam o seguinte para monitoramento e resposta:

- Auditoria, alerta e relatório para atividades relacionadas ao armazenamento, compartilhamento e processamento de dados pessoais
- A capacidade de responder a uma solicitação de assunto de dados (DSR) e, em alguns casos, executar medidas de investigação e outras medidas administrativas para atender a essas solicitações.

Sua organização também pode desejar realizar atividades de monitoramento e resposta para outros fins, como outras necessidades de conformidade ou por motivos comerciais. O estabelecimento do seu esquema de monitoramento e resposta para privacidade de dados deve ser feito como parte do planejamento, implementação e gerenciamento geral de monitoramento e resposta.

Para ajudá-lo a começar a trabalhar com um esquema de monitoramento e resposta no Microsoft 365 para regulamentações de privacidade de dados, este artigo lista recursos úteis no Microsoft 365 para responder perguntas como: 

- Que tipo de monitoramento, investigação e técnicas de relatório diárias estão disponíveis para os diferentes tipos e fontes de dados?
- Quais mecanismos serão necessários para lidar com solicitações de assunto de dados (DSRs) e quaisquer ações corretivas, como anonimato, redação e exclusão.

## <a name="auditing-and-alert-policies-in-the-security-and-compliance-center"></a>Políticas de Auditoria e Alerta no Centro de Conformidade e Segurança

Consulte estes artigos para configurar auditoria, auditoria avançada e políticas de alerta:

- [Auditoria unificada](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Auditoria de caixa de correio](../compliance/enable-mailbox-auditing.md)
- [Auditoria avançada](../compliance/advanced-audit.md)
- [Políticas de alerta](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de assunto de dados para o RGPD e CCPA

Consulte [Solicitações de Assunto de Dados para o RGPD](../compliance/gdpr-dsr-office365.md) e o CCPA para obter informações sobre como responder a uma DSR no Microsoft 365.

## <a name="manage-deleted-users-in-microsoft-stream"></a>Gerenciar usuários excluídos no Microsoft Stream

Para o Microsoft Stream, quando um usuário é excluído do Azure Active Directory (Azure AD), se seu nome estava associado a um vídeo postado do Stream antes desse ponto, seu endereço de email permanece associado ao vídeo. Consulte [Gerenciar usuários excluídos do Microsoft Stream para](https://docs.microsoft.com/stream/managing-deleted-users) removê-lo.

## <a name="insider-risk-management-as-an-investigative-tool"></a>Gerenciamento de riscos insider como uma ferramenta de investigação

O gerenciamento de riscos internos no [Microsoft 365](../compliance/insider-risk-management.md) é um recurso do Centro de administração de Conformidade da Microsoft para ajudá-lo a minimizar os riscos internos, permitindo que você detecte, investigue e tome medidas em atividades arriscadas em sua organização.
