---
title: Integração do SIEM com o Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integre o servidor SIEM da sua organização ao Microsoft Defender para Office 365 e eventos de ameaças relacionados na API de Gerenciamento de Atividades do Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ca8f86c831df16568ae569e7b21c7e0a33475948
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202953"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integração do SIEM com o Microsoft Defender para Office 365

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se sua organização estiver usando um servidor siem (gerenciamento de informações de segurança e eventos), você poderá integrar o Microsoft Defender para Office 365 ao seu servidor SIEM. Você pode configurar essa integração usando a API de Gerenciamento de Atividades do [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)

A integração com SIEM permite exibir informações, como malware ou phishing detectados pelo Microsoft Defender para Office 365, nos relatórios do servidor SIEM.

- Para ver um exemplo de integração do SIEM com o Microsoft Defender para Office 365, consulte o blog comunidade técnica: Melhorar a eficácia do SOC com o Defender para Office 365 e a API de Gerenciamento [do O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Para saber mais sobre as APIs de Gerenciamento do Office 365, consulte Visão geral das APIs de Gerenciamento [do Office 365.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Como funciona a integração do SIEM

A API de Gerenciamento de Atividades do Office 365 recupera informações sobre ações e eventos de usuário, administrador, sistema e política dos logs de atividades do Microsoft 365 e do Azure Active Directory da sua organização. Se sua organização tiver o Microsoft Defender para Office 365 Plano 1 ou 2 ou Office 365 E5, você poderá usar o [esquema do Microsoft Defender para Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).

Recentemente, eventos de recursos automatizados de investigação e resposta no [Microsoft Defender para Office 365 Plano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) foram adicionados à API de Atividade de Gerenciamento do Office 365. Além de incluir dados sobre detalhes principais da investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações e entidades de investigação.

O servidor SIEM ou outro sistema semelhante sonda a carga de trabalho **audit.general** para acessar eventos de detecção. Para saber mais, confira Começar com AS APIs de [Gerenciamento do Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

A tabela a seguir resume os valores **de AuditLogRecordType** relevantes para eventos do Microsoft Defender para Office 365:

|Valor|Nome do membro|Descrição|
|---|---|---|
|28|ThreatIntelligence|Eventos de phishing e malware da Proteção do Exchange Online e do Microsoft Defender para Office 365.|
|41|ThreatIntelligenceUrl|Tempo de bloqueio e bloqueio de links seguros do Microsoft Defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Microsoft Defender para Office 365.|
|64|AirInvestigation|Eventos automatizados de investigação e resposta, como detalhes da investigação e artefatos relevantes, do Microsoft Defender para Office 365 Plan 2.|
|

> [!IMPORTANT]
> Você deve ser um administrador global ou ter a função de administrador de segurança atribuída ao Centro de Conformidade & Segurança para configurar a integração do SIEM com o Microsoft Defender para Office 365.
>
> O log de auditoria deve estar ligado para seu ambiente do Microsoft 365. Para obter ajuda com isso, consulte Ativar ou desativar a pesquisa [de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Confira também

[Investigação e resposta a ameaças do Office 365](office-365-ti.md)

[Investigação e resposta automatizadas (AIR) no Office 365](automated-investigation-response-office.md)