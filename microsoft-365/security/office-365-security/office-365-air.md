---
title: Investigação e resposta automatizadas (AIR) no Office 365
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
ms.openlocfilehash: 3a362f7d15a9cc8e1f5784ec03c8c04d3d77886d
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42262008"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Investigação e resposta automatizadas (AIR) no Office 365

[Proteção avançada contra ameaças do Office 365](office-365-atp.md) O plano 2 inclui recursos avançados de investigação e resposta (AIR), que podem economizar tempo e esforço da equipe de operações de segurança. Quando determinados alertas são acionados, um ou mais guias estratégicos de segurança iniciam e o processo de investigação automatizado é iniciado. Isso permite que sua equipe de operações de segurança se concentre nas tarefas de alta prioridade sem perder a visão dos alertas disparados. 

## <a name="the-overall-flow-of-air"></a>O fluxo de ar geral

Em um nível alto, o fluxo de ar funciona da seguinte maneira:

|Etapa  |O que acontece  |
|---------|---------|
|1     |Um alerta é disparado por um evento do Office e um [Guia de segurança](automated-investigation-response-office.md#security-playbooks) inicia uma investigação automatizada para alertas selecionados. <br/><br/>Como alternativa, um analista de segurança pode [disparar uma investigação automatizada](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) ao usar o [Explorador de ameaças](threat-explorer.md).        |
|duas     |Enquanto uma investigação automatizada é executada, ela coleta dados adicionais sobre o email e as entidades relacionadas a esse email – arquivos, URLs e destinatários.  O escopo da investigação pode aumentar, pois novos alertas relacionados são acionados.         |
|3D     |Durante e após uma investigação automatizada, [detalhes e resultados](air-view-investigation-results.md) estão disponíveis para exibição. Os resultados incluem [ações recomendadas](air-remediation-actions.md) que podem ser tomadas para responder e corrigir quaisquer ameaças encontradas. Além disso, um [log](air-view-investigation-results.md#playbook-log) de análise manual está disponível que controla todas as atividades de investigação.<br/><br/>Se sua organização estiver usando uma solução de relatórios personalizada ou uma solução de terceiros, você poderá [usar a API da atividade de gerenciamento do Office 365](air-custom-reporting.md) para exibir informações sobre investigações e ameaças automatizadas.         |
|quatro     |Sua equipe de operações de segurança revisa os [resultados e recomendações da investigação](air-view-investigation-results.md)e [aprova ações de correção](air-remediation-actions.md#approve-or-reject-pending-actions). No Office 365, nenhuma ação é executada automaticamente. As ações de correção são executadas apenas após a aprovação da equipe de segurança da sua organização.         |

Durante e após um processo de investigação automatizado, a equipe de segurança pode fazer o seguinte:

- [Exibir detalhes sobre um alerta relacionado a uma investigação](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [Exibir os detalhes dos resultados de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)
- [Revisar e aprovar ações como resultado de uma investigação](air-remediation-actions.md#approve-or-reject-pending-actions)

Para saber mais, confira [como o Air funciona](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="how-to-get-air"></a>Como obter o AIR

O Office 365 AIR está incluído nas seguintes assinaturas:

- Microsoft 365 E5
- Office 365 E5
- Proteção contra Ameaças da Microsoft
- Plano 2 de proteção avançada contra ameaças do Office 365

Se você não tiver nenhuma dessas assinaturas, [inicie uma avaliação gratuita](https://go.microsoft.com/fwlink/p/?LinkID=698279&culture=en-US&country=US).

Para saber mais sobre a disponibilidade de recursos, visite a [disponibilidade de recursos nos planos de proteção avançada contra ameaças (ATP)](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-permissions-to-use-air-capabilities"></a>Permissões necessárias para usar os recursos de ar

As permissões são concedidas por determinadas funções, como aquelas descritas na tabela a seguir: 

|Tarefa |Função (ões) necessária |
|--|--|
|Para configurar os recursos de ar |Uma das seguintes funções: <br/>- **Administrador global**<br/>- **Administrador de segurança** <br/>Essas funções podem ser atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Para aprovar ou rejeitar ações recomendadas|Uma das seguintes funções, atribuídas no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) ou no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)):<br/>- **Administrador global** <br/>- **Administrador de segurança**<br/>- **Leitor de segurança** <br/>---e---<br/>- **Pesquisa e limpeza** (esta função é atribuída somente no [centro de conformidade & segurança do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Talvez seja necessário criar um novo grupo de função e adicionar a função de pesquisa e limpeza a esse novo grupo de função.)

## <a name="related-articles"></a>Artigos relacionados

- [Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

- [Investigação e correção automatizadas no Microsoft defender proteção avançada contra ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)