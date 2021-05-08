---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, Microsoft Defender for Endpoint, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como integrar a investigação e a resposta automatizadas a uma solução de relatórios personalizada ou de terceiros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275007"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365

Com [o Microsoft Defender para Office 365](defender-for-office-365.md), você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se a sua organização quiser integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API Office 365 Atividade de Gerenciamento.

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Com [o Microsoft Defender para Office 365](defender-for-office-365.md), você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se a sua organização quiser integrar informações sobre investigações automatizadas com essa solução, você pode usar a API Office 365 Atividade de Gerenciamento.

|Recurso|Descrição|
|:---|:---|
|[Visão geral das APIs de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-apis-overview)|A API Office 365 de Atividade de Gerenciamento fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas de Microsoft 365 e Azure Active Directory de atividades.|
|[Introdução às APIs de Gerenciamento do Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|A OFFICE 365 de Gerenciamento usa o Azure AD para fornecer serviços de autenticação para seu aplicativo acessar Microsoft 365 dados. Siga as etapas deste artigo para configurar isso.|
|[Referência da API da Atividade de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)|Você pode usar Office 365 API de Atividade de Gerenciamento para recuperar informações sobre ações e eventos de usuários, administradores, sistemas e políticas de logs de atividades do Microsoft 365 e do Azure AD. Leia este artigo para saber mais sobre como isso funciona.|
|[Esquema da API da Atividade de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-schema)|Obter uma visão [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do Defender para Office 365 e investigação de ameaças e [esquema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) de resposta para saber mais sobre tipos específicos de dados disponíveis por meio da API de Atividade de Gerenciamento Office 365.|
|

## <a name="see-also"></a>Confira também

- [Obter o Microsoft Defender para Office 365](defender-for-office-365.md)
- [Investigação e resposta automatizadas no Microsoft 365 Defender](/microsoft-365/security/defender/m365d-autoir)
