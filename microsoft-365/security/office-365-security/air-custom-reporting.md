---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: 9f62d73417cc4d7ecaa113ae1c304630ef1852eb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921427"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365

Com [o Microsoft Defender para Office 365,](office-365-atp.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se sua organização quiser integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API de Atividade de Gerenciamento do Office 365.

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Com [o Microsoft Defender para Office 365,](office-365-atp.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se sua organização quiser integrar informações sobre investigações automatizadas com essa solução, você pode usar a API de Atividade de Gerenciamento do Office 365.

|Recurso|Descrição|
|:---|:---|
|[Visão geral das APIs de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-apis-overview)|A API de Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas do Microsoft 365 e do Azure Active Directory.|
|[Introdução às APIs de Gerenciamento do Office 365](/office/office-365-management-api/get-started-with-office-365-management-apis)|A API de Gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para seu aplicativo acessar dados do Microsoft 365. Siga as etapas deste artigo para configurar isso.|
|[Referência da API da Atividade de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-reference)|Você pode usar a API de Atividade de Gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administrador, sistema e política dos logs de atividades do Microsoft 365 e do Azure AD. Leia este artigo para saber mais sobre como isso funciona.|
|[Esquema da API da Atividade de Gerenciamento do Office 365](/office/office-365-management-api/office-365-management-activity-api-schema)|Obter uma visão [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do [Defender for Office 365](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e do esquema de investigação e resposta contra ameaças para saber mais sobre tipos específicos de dados disponíveis por meio da API de Atividade de Gerenciamento do Office 365.|
|

## <a name="see-also"></a>Confira também

- [Obter o Microsoft Defender para Office 365](office-365-atp.md)
- [Investigação e resposta automatizadas no Microsoft 365 Defender](../mtp/mtp-autoir.md)