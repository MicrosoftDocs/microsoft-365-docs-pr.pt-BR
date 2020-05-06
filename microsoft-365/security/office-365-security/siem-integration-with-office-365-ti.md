---
title: Integração do SIEM com proteção avançada contra ameaças
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com a proteção avançada contra ameaças do Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035267"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integração do SIEM com proteção avançada contra ameaças

Se sua organização estiver usando um servidor de gerenciamento de incidentes e eventos de segurança (SIEM), você poderá integrar a proteção avançada contra ameaças do Office 365 ao seu servidor SIEM. A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pela proteção avançada do Office 365, em seus relatórios do SIEM Server. Para configurar a integração do SIEM, use a [API de gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 para empresas e do Azure Active Directory da sua organização. O [esquema de proteção avançada contra ameaças do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funciona com a proteção avançada contra ameaças, portanto, se sua organização tiver o plano de proteção avançada contra ameaças do Office 365 ou o plano 2 ou o Office 365 e5, você ainda poderá usar essa mesma API para sua integração com o Siem Server. 

Como parte de nossas atualizações recentes, também adicionamos eventos de investigação automatizada e recursos de resposta no Office 365 ATP plano 2 dentro da API de atividade de gerenciamento do Office 365. Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, ele também contém informações de alto nível sobre ações de investigação e entidades.   

O servidor SIEM ou outro sistema semelhante deve sondar a **auditoria.** carga de trabalho geral para acessar eventos de detecção. Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Além disso, os seguintes valores de **AuditLogRecordType** são relevantes para eventos de ATP do Office 365:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Valor|Nome do membro|Descrição|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Eventos de phishing e malware da Proteção do Exchange Online e da Proteção Avançada contra Ameaças do Office 365.|
|41|ThreatIntelligenceUrl|Links seguros de ATP os eventos de tempo de bloqueio e substituição de bloqueio da proteção avançada contra ameaças do Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams da proteção avançada contra ameaças do Office 365.|
|64|AirInvestigation|Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes do plano de proteção avançada contra ameaças do Office 365.|


> [!IMPORTANT]
> Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com a proteção avançada contra ameaças do Office 365.<br/>O log de auditoria deve estar ativado para seu ambiente do Microsoft 365. Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Tópicos relacionados

[Investigação e resposta a ameaças do Office 365](office-365-ti.md)

[Investigação e resposta automatizadas (AIR) no Office 365](automated-investigation-response-office.md)

[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)

[Relatórios inteligentes e insights no centro de &amp; conformidade de segurança](reports-and-insights-in-security-and-compliance.md)
  
[Permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md)
  
