---
title: Introdução à investigação e resposta automatizadas no Microsoft defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Comece a usar os recursos de investigação e resposta automatizados no Microsoft defender para Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925599"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Introdução ao uso de investigação e resposta automatizadas (AIR) no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[O Microsoft defender para Office 365](office-365-atp.md) inclui poderosos recursos avançados de investigação e resposta (Air) que podem economizar tempo e esforço da equipe de operações de segurança. À medida que os alertas são disparados, a equipe de operações de segurança pode revisar, priorizar e responder a esses alertas. Acompanhar o volume de alertas de entrada pode ser impressionante. A automatização de algumas dessas tarefas pode ajudar. Com o AIR, sua equipe de operações de segurança pode se concentrar nas tarefas de maior prioridade sem perder a visão de alertas importantes que são disparados.

Este artigo descreve:
- O [fluxo de ar geral](#the-overall-flow-of-air);
- [Como obter o ar](#how-to-get-air); e 
- As [permissões necessárias](#required-permissions-to-use-air-capabilities) para configurar ou usar os recursos de ar. 

## <a name="the-overall-flow-of-air"></a>O fluxo de ar geral

Um alerta é disparado, e um guia de segurança inicia uma investigação automatizada, resultando em conclusões e ações recomendadas. Este é o fluxo de ar geral, passo a passo:

1. Uma investigação automatizada é iniciada de uma das seguintes maneiras:

   - Um [alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) é disparado por algo suspeito no email (como uma mensagem, anexo ou URL). Um incidente é criado. Dependendo do tipo de incidente, um [guia estratégico de segurança](automated-investigation-response-office.md#security-playbooks) é executado e uma investigação automatizada é iniciada. 

     ---ou---
   
   - Um analista de segurança [inicia uma investigação automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) ao usar o [Explorador de ameaças](threat-explorer.md).

2. Enquanto uma investigação automatizada é executada, ela coleta dados adicionais sobre o email em questão e entidades relacionadas a esse email. Essas entidades podem incluir arquivos, URLs e destinatários.  O escopo da investigação pode aumentar à medida que os alertas novos e relacionados são acionados.

3. Durante e após uma investigação automatizada, [detalhes e resultados](air-view-investigation-results.md) estão disponíveis para exibição. Os resultados incluem [ações recomendadas](air-remediation-actions.md) que podem ser tomadas para responder e corrigir quaisquer ameaças encontradas. Além disso, um [log](air-view-investigation-results.md#playbook-log) de análise manual está disponível que controla todas as atividades de investigação.


4. Sua equipe de operações de segurança revisa os [resultados e recomendações da investigação](air-view-investigation-results.md)e [aprova ou rejeita ações de correção](air-review-approve-pending-completed-actions.md). 

5. Como as ações de correção pendentes são aprovadas (ou rejeitadas), a investigação automatizada é concluída.

> [!IMPORTANT]
> No Microsoft defender para Office 365, nenhuma ação de correção é executada automaticamente. As ações de correção só serão tomadas mediante a aprovação da equipe de segurança da sua organização. No entanto, os recursos de ar salvam o tempo da equipe de operações de segurança identificando ações de correção e fornecendo os detalhes necessários para tomar uma decisão informada.

Durante e após cada investigação automatizada, a equipe de operações de segurança pode:

- [Exibir detalhes sobre um alerta relacionado a uma investigação](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Exibir os detalhes dos resultados de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar e aprovar ações como resultado de uma investigação](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obter uma visão geral mais detalhada, confira [como funciona o Air](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Como obter o AIR

Os recursos de ar estão incluídos no [Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2), desde que suas políticas e alertas estejam configurados. Se você quiser alguma ajuda com isso, siga as orientações em [proteção contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) para definir ou definir as seguintes configurações de proteção: 

1. [Log de auditoria](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (deve ser ativado)

2. [Políticas Antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Proteção contra phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Proteção antispam](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Links seguros e anexos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Anexos seguros para o SharePoint, o onedrive e o Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Limpeza automática de zero horas para email](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Além disso, certifique-se de [revisar as políticas de alerta da sua organização](https://docs.microsoft.com/microsoft-365/compliance/alert-policies), especialmente as [políticas padrão na categoria gerenciamento de ameaças](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies). 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Quais políticas de alerta disparam investigações automatizadas?

A Microsoft 365 fornece várias políticas de alerta internas que ajudam a identificar abuso de permissões de administrador do Exchange, atividade de malware, ameaças externas e internas potenciais e riscos de governança de informações. Várias das [políticas de alerta padrão](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) podem disparar investigações automatizadas. Elas incluem o seguinte:

- Um clique em URL potencialmente mal-intencionado é detectado
- Uma mensagem de email é reportada por um usuário como phishing
- Mensagens de email com malware são removidos após a entrega
- Mensagens de email que contêm URLs de phishing são removidas após a entrega
- Padrões de envio de emails suspeitos detectados
- Um usuário não está restringindo o envio de email

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar os recursos de ar

As permissões são concedidas por determinadas funções, como aquelas descritas na tabela a seguir: 

|Tarefas |Função (ões) necessária |
|--|--|
|Para configurar os recursos de ar |Uma das seguintes funções: <br/>-Administrador global<br/>-Administrador de segurança <br/>Essas funções podem ser atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade do & de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Administrador global <br/>-Administrador de segurança<br/>– Leitor de segurança <br/>---e---<br/>– Pesquisa e limpeza (esta função é atribuída somente no [centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Talvez seja necessário criar um novo grupo de função e adicionar a função de pesquisa e limpeza a esse novo grupo de função.)

## <a name="required-licenses"></a>Licenças necessárias

As licenças do [Microsoft defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) devem ser atribuídas a:
- Administradores de segurança (incluindo administradores globais)
- A equipe de operações de segurança da sua organização (incluindo leitores de segurança e aquelas com a função de pesquisa e limpeza)
- Usuários finais


## <a name="next-steps"></a>Próximas etapas

- [Veja detalhes e resultados de uma investigação automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Revisar e aprovar ações pendentes](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Artigos relacionados

- [Investigação e correção automatizadas no Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigação e resposta automatizadas no Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
