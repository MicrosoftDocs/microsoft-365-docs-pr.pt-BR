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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização com a proteção avançada contra ameaças do Office 365 e eventos de ameaça relacionados na API de gerenciamento de atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600548"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>Integração do SIEM com proteção avançada contra ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM), você poderá integrar a proteção avançada contra ameaças do Office 365 (Office 365 ATP) com seu servidor SIEM. Você pode configurar essa integração usando a API de [Gerenciamento de atividades do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

A integração do SIEM permite que você visualize informações, como malware ou phishing detectado pelo Office 365 ATP, em seus relatórios do SIEM Server. 

- Para ver um exemplo de integração do SIEM com o Office 365 ATP, consulte [blog da comunidade técnica: aprimore a eficácia do seu SoC com o Office 365 ATP e a API de gerenciamento do O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Para saber mais sobre as APIs de gerenciamento do Office 365, confira [visão geral das APIs de gerenciamento do office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Como funciona a integração do SIEM

A API de gerenciamento de atividades do Office 365 recupera informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização. Se sua organização tiver o plano de ATP 1 ou 2 do Office 365 ou o Office 365 e5, você poderá usar o [esquema ATP do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Recentemente, eventos de investigação automatizada e recursos de resposta no [office 365 ATP plano 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) foram adicionados à API da atividade de gerenciamento do Office 365. Além de incluir dados sobre detalhes principais de investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações de investigação e entidades.

O servidor SIEM ou outro sistema semelhante pesquisa a **auditoria.** a carga de trabalho geral para acessar eventos de detecção. Para saber mais, confira [introdução às APIs de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

A tabela a seguir resume os valores de **AuditLogRecordType** que são relevantes para eventos de ATP do Office 365:

|Valor|Nome do membro|Descrição|
|---|---|---|
|28|ThreatIntelligence|Eventos de phishing e malware de proteção do Exchange Online e do Office 365 ATP.|
|41|ThreatIntelligenceUrl|Links seguros de tempo de bloqueio e substituição de bloqueio de eventos do Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Office 365 ATP.|
|64|AirInvestigation|Eventos de investigação e resposta automatizados, como detalhes de investigação e artefatos relevantes, do plano de ATP 2 do Office 365.|
|

> [!IMPORTANT]
> Você deve ser um administrador global ou ter a função de administrador de segurança atribuída para o centro de conformidade de & de segurança para configurar a integração do SIEM com a proteção avançada contra ameaças do Office 365.<br/>O log de auditoria deve estar ativado para seu ambiente do Microsoft 365. Para obter ajuda com isso, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Confira também

[Investigação e resposta a ameaças do Office 365](office-365-ti.md)

[Investigação e resposta automatizadas (AIR) no Office 365](automated-investigation-response-office.md)

