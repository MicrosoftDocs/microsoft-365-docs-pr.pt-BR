---
title: Integração do SIEM com o Microsoft defender para Office 365
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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com o Microsoft defender para Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843571"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integração do SIEM com o Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM), você poderá integrar o Microsoft defender para Office 365 com seu servidor SIEM. Você pode configurar essa integração usando a API de [Gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pelo Microsoft defender para Office 365, em seus relatórios do SIEM Server. 

- Para ver um exemplo de integração do SIEM com o Microsoft defender para Office 365, consulte [blog da comunidade técnica: aprimore a eficácia do seu SoC com o defender para Office 365 e a API de gerenciamento do O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Para saber mais sobre as APIs de gerenciamento do Office 365, confira [visão geral das APIs de gerenciamento do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Como funciona a integração do SIEM

A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização. Se sua organização tiver o Microsoft defender para Office 365 plano 1 ou 2 ou o Office 365 e5, você poderá usar o [esquema do Microsoft defender para office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Recentemente, eventos de investigação automatizada e recursos de resposta no [Microsoft defender para Office 365 plano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) foram adicionados à API da atividade de gerenciamento do Office 365. Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações de investigação e entidades.

O servidor SIEM ou outro sistema semelhante pesquisa a **auditoria.** a carga de trabalho geral para acessar eventos de detecção. Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

A tabela a seguir resume os valores de **AuditLogRecordType** que são relevantes para eventos do Microsoft defender for Office 365:

|Valor|Nome do membro|Descrição|
|---|---|---|
|28|ThreatIntelligence|Eventos de phishing e malware da proteção do Exchange Online e do Microsoft defender para Office 365.|
|41|ThreatIntelligenceUrl|Links seguros de tempo de bloqueio e substituição de eventos do Microsoft defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Microsoft defender para Office 365.|
|64|AirInvestigation|Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes, do Microsoft defender para Office 365 plano 2.|
|

> [!IMPORTANT]
> Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com o Microsoft defender para Office 365.<br/>O log de auditoria deve estar ativado para seu ambiente do Microsoft 365. Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Confira também

[Investigação e resposta a ameaças do Office 365](office-365-ti.md)

[Investigação e resposta automatizadas (AIR) no Office 365](automated-investigation-response-office.md)

