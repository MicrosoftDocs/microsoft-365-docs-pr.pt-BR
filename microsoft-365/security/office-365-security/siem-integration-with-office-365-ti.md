---
title: Integração siem com o Microsoft Defender para Office 365
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
description: Integre o servidor SIEM da sua organização ao Microsoft Defender para Office 365 e eventos de ameaças relacionados na API Office 365 Gerenciamento de Atividades.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e11d1e64b7c8c3b9d5b93516fe05aed3d5937290
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105627"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>Integração siem com o Microsoft Defender para Office 365

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se sua organização estiver usando um servidor SIEM (gerenciamento de informações de segurança e eventos), você poderá integrar o Microsoft Defender para Office 365 com seu servidor SIEM. Você pode configurar essa integração usando a API Office 365 Gerenciamento de [Atividades.](/office/office-365-management-api/office-365-management-activity-api-reference)

A integração com SIEM permite exibir informações, como malware ou phishing detectados pelo Microsoft Defender para Office 365, nos relatórios do servidor SIEM.

- Para ver um exemplo de integração do SIEM com o Microsoft Defender para Office 365, consulte o blog do Tech Community: Melhorar a eficácia do soc com o Defender para Office 365 e a API de Gerenciamento [do O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)
- Para saber mais sobre as APIs Office 365 Gerenciamento, consulte Office 365 Visão geral das [APIs de Gerenciamento.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Como funciona a integração do SIEM

A OFFICE 365 de Gerenciamento de Atividades recupera informações sobre ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades Microsoft 365 e Azure Active Directory sua organização. Se sua organização tiver o Microsoft Defender para Office 365 Plano 1 ou 2 ou Office 365 E5, você poderá usar [o Microsoft Defender](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)para Office 365 esquema .

Recentemente, eventos de recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 [Plano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) foram adicionados à API Office 365 Atividade de Gerenciamento. Além de incluir dados sobre detalhes principais da investigação, como ID, nome e status, a API também contém informações de alto nível sobre ações e entidades de investigação.

O servidor SIEM ou outro sistema semelhante sonda a carga de trabalho **audit.general** para acessar eventos de detecção. Para saber mais, consulte [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enumeração: AuditLogRecordType - Tipo: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

A tabela a seguir resume os valores **de AuditLogRecordType** que são relevantes para o Microsoft Defender para Office 365 eventos:

<br>

****

|Valor|Nome do membro|Descrição|
|---|---|---|
|28|ThreatIntelligence|Eventos de phishing e malware da Proteção do Exchange Online e do Microsoft Defender para Office 365.|
|41|ThreatIntelligenceUrl|Cofre Vincula eventos de substituição de tempo de bloqueio e bloqueio do Microsoft Defender para Office 365.|
|47|ThreatIntelligenceAtpContent|Eventos de phishing e malware para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams, do Microsoft Defender para Office 365.|
|64|AirInvestigation|Eventos automatizados de investigação e resposta, como detalhes da investigação e artefatos relevantes, do Microsoft Defender para Office 365 Plano 2.|
|

> [!IMPORTANT]
> Você deve ser um administrador global ou ter a função de Administrador de Segurança atribuída no portal Microsoft 365 Defender para configurar a integração siem com o Microsoft Defender para Office 365. Para obter mais informações, veja [Permissões no portal do Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
>
> O log de auditoria deve estar ligado para seu Microsoft 365 ambiente. Para obter ajuda com isso, consulte Ativar ou desativar a pesquisa [de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Confira também

[Investigação e resposta a ameaças do Office 365](office-365-ti.md)

[Investigação e resposta automatizadas (AIR) em Office 365](automated-investigation-response-office.md)