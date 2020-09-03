---
title: Investigação e resposta automatizadas (ar)-introdução
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
description: Comece a usar os recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: 14742df5d9dbd2f65a032250696dbc7c61210562
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336674"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Introdução ao uso de investigação e resposta automatizadas (AIR) no Office 365

[Office 365 proteção avançada contra ameaças](office-365-atp.md) (Office 365 ATP) o plano 2 inclui recursos avançados de investigação e resposta (Air) automatizados que podem economizar tempo e esforço da equipe de operações de segurança. À medida que os alertas são disparados, a equipe de operações de segurança pode revisar, priorizar e responder a esses alertas. Acompanhar o volume de alertas de entrada pode ser impressionante. A automação de algumas delas pode ajudar. Com o AIR, sua equipe de operações de segurança pode se concentrar nas tarefas de maior prioridade sem perder a visão dos alertas disparados.

Este artigo contém informações sobre:

- O [fluxo](#the-overall-flow-of-air) de ar geral
- [Como obter o AIR](#how-to-get-air)
- As [permissões necessárias](#required-permissions-to-use-air-capabilities) para configurar ou usar os recursos de ar

## <a name="the-overall-flow-of-air"></a>O fluxo de ar geral

Em um nível alto, um alerta é disparado e um guia de segurança inicia uma investigação automatizada, resultando em resultados e recomendações. Este é o fluxo de ar geral, passo a passo:

1. Uma investigação automatizada é iniciada de uma das seguintes maneiras:

   - Um [alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) é disparado por um evento do Office, que cria um incidente. Dependendo do tipo de incidente, um guia de [segurança](automated-investigation-response-office.md#security-playbooks) inicia uma investigação automatizada. 

     ---ou---
   
   - Um analista de segurança [inicia uma investigação automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) ao usar o [Explorador de ameaças](threat-explorer.md).

2. Enquanto uma investigação automatizada é executada, ela coleta dados adicionais sobre o email em questão e entidades relacionadas a esse email. Essas entidades podem incluir arquivos, URLs e destinatários.  O escopo da investigação pode aumentar à medida que os alertas novos e relacionados são acionados.

3. Durante e após uma investigação automatizada, [detalhes e resultados](air-view-investigation-results.md) estão disponíveis para exibição. Os resultados incluem [ações recomendadas](air-remediation-actions.md) que podem ser tomadas para responder e corrigir quaisquer ameaças encontradas. Além disso, um [log](air-view-investigation-results.md#playbook-log) de análise manual está disponível que controla todas as atividades de investigação.

    Se sua organização estiver usando uma solução de relatórios personalizada ou uma solução de terceiros, você poderá [usar a API da atividade de gerenciamento do Office 365](air-custom-reporting.md) para exibir informações sobre investigações e ameaças automatizadas.

4. Sua equipe de operações de segurança revisa os [resultados e recomendações da investigação](air-view-investigation-results.md)e [aprova ou rejeita ações de correção](air-review-approve-pending-completed-actions.md). 

    Como as ações de correção pendentes são aprovadas (ou rejeitadas), a investigação automatizada é concluída.

> [!NOTE]
> No Office 365 ATP, nenhuma ação de correção é executada automaticamente. As ações de correção só serão tomadas mediante a aprovação da equipe de segurança da sua organização. 

Durante e após um processo de investigação automatizado, a equipe de segurança pode fazer o seguinte:

- [Exibir detalhes sobre um alerta relacionado a uma investigação](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Exibir os detalhes dos resultados de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)

- [Revisar e aprovar ações como resultado de uma investigação](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Para obter mais detalhes, consulte [como o Air funciona](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Como obter o AIR

Os recursos de AIR do Office 365 estão incluídos no [office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). No entanto, suas [políticas ATP do Office 365 devem ser configuradas](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) para que o Air funcione conforme o esperado. Além disso, certifique-se de revisar e configurar potencialmente as [políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)da sua organização. 

A Microsoft 365 fornece várias políticas de alerta internas que ajudam a identificar abuso de permissões de administrador do Exchange, atividade de malware, ameaças externas e internas potenciais e riscos de governança de informações. Várias das [políticas de alerta padrão](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) podem disparar investigações automatizadas. Elas incluem o seguinte:

- Um clique em URL potencialmente mal-intencionado é detectado

- Uma mensagem de email é reportada por um usuário como phishing

- Mensagens de email com malware são removidos após a entrega

- Mensagens de email que contêm URLs de phishing são removidas após a entrega

- Padrões de envio de emails suspeitos detectados

- Um usuário não está restringindo o envio de email

[Saiba mais sobre alertas e ar](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar os recursos de ar

As permissões são concedidas por determinadas funções, como aquelas descritas na tabela a seguir: 

|Tarefas |Função (ões) necessária |
|--|--|
|Para configurar os recursos de ar |Uma das seguintes funções: <br/>-Administrador global<br/>-Administrador de segurança <br/>Essas funções podem ser atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade do & de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>-Administrador global <br/>-Administrador de segurança<br/>– Leitor de segurança <br/>---e---<br/>– Pesquisa e limpeza (esta função é atribuída somente no [centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Talvez seja necessário criar um novo grupo de função e adicionar a função de pesquisa e limpeza a esse novo grupo de função.)

As licenças [do plano ATP 2 do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) devem ser atribuídas a:
- Administradores de segurança (incluindo administradores globais)
- A equipe de operações de segurança da sua organização (incluindo leitores de segurança e aquelas com a função de pesquisa e limpeza)
- Usuários finais

Além disso, [as políticas ATP do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) devem ser definidas e aplicadas para que a proteção seja estabelecida.

## <a name="next-steps"></a>Próximas etapas

- [Veja detalhes e resultados de uma investigação automatizada](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Revisar e aprovar ações pendentes](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Artigos relacionados

- [Investigação e correção automatizadas no Microsoft defender proteção avançada contra ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
