---
title: Integração do SIEM com a proteção avançada contra ameaças do Office 365
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
ms.date: 03/11/2019
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com a proteção avançada contra ameaças do Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.openlocfilehash: a9d6c8db8ca3090bb2a10ec1bd9b6f5edb48991e
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033882"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>Integração do SIEM com a proteção avançada contra ameaças do Office 365

Se sua organização estiver usando um servidor de gerenciamento de incidentes e eventos de segurança (SIEM), você poderá integrar a proteção avançada contra ameaças do Office 365 ao seu servidor SIEM. A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pela proteção avançada do Office 365, em seus relatórios do SIEM Server. Para configurar a integração do SIEM, use a [API de gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure Active Directory da sua organização. O [esquema de proteção avançada contra ameaças do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) funciona com a proteção avançada contra ameaças, portanto, se sua organização tiver o plano de proteção avançada contra ameaças do Office 365 ou o plano 2 ou o Office 365 e5, você ainda poderá usar essa mesma API para sua integração com o Siem Server. 

O servidor SIEM ou outro sistema semelhante deve sondar a **auditoria.** carga de trabalho geral para acessar eventos de detecção. Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Além disso, os seguintes valores de **AuditLogRecordType** são relevantes para eventos de ATP do Office 365:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Valor|Nome do membro|Descrição|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Eventos de phishing e malware da Proteção do Exchange Online e da Proteção Avançada contra Ameaças do Office 365.|
|41|ThreatIntelligenceUrl|Links seguros de ATP os eventos de tempo de bloqueio e substituição de bloqueio da proteção avançada contra ameaças do Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, no OneDrive for Business e no Microsoft Teams da proteção avançada contra ameaças do Office 365.|

> [!IMPORTANT]
> Você deve ser um administrador global do Office 365 ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com a proteção avançada contra ameaças do Office 365.<br/>O log de auditoria deve estar ativado para o seu ambiente do Office 365. Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria do Office 365](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Tópicos relacionados

[Investigação e resposta contra ameaças do Office 365](office-365-ti.md)

[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)

[Relatórios inteligentes e insights no centro de conformidade de &amp; segurança do Office 365](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
